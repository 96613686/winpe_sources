# EdppInitializeCallback

- ea: `0x14002bb30`
- end: `0x14002bbf1`
- name: `EdppInitializeCallback`
- size: `193`
- prototype: `__int64 __fastcall(__int64, PVOID, PVOID *)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callees

- `0x1400293ac`
- `0x14002bb30`
- `0x14002bf44`
- `0x14002e604`

## import_xrefs

- `ntoskrnl!ExSubscribeWnfStateChange` at `0x14002bbc9`
- `ntoskrnl!ExSubscribeWnfStateChange` at `0x14002bbc9`

## string_xrefs

- `0x14002bb39`: `\REGISTRY\MACHINE\System\CurrentControlSet\Control\AppID\Configuration\EDP`

## pseudocode

```c
__int64 __fastcall EdppInitializeCallback(__int64 a1, PVOID a2, PVOID *a3)
{
  struct _UNICODE_STRING v4; // [rsp+30h] [rbp-20h] BYREF
  struct _UNICODE_STRING v5; // [rsp+40h] [rbp-10h] BYREF
  int v6; // [rsp+78h] [rbp+28h] BYREF

  *(_QWORD *)&v5.Length = 9830548;
  v5.Buffer = L"\\REGISTRY\\MACHINE\\System\\CurrentControlSet\\Control\\AppID\\Configuration\\EDP";
  *(_QWORD *)&v4.Length = 2097182;
  v4.Buffer = L"EdpDisableAudit";
  v6 = 0;
  if ( (int)AiRegReadDwordValue(a1, &v5, &v4, &v6) >= 0 && v6 == 1 )
    return 1;
  if ( (int)EdppDoWorkAsSystem((__int64)EdppEnableAudit) < 0 )
  {
    EdppAuditEnabled = 0;
  }
  else
  {
    EdppAuditEnabled = 1;
    ExSubscribeWnfStateChange(&EdppPurgeWnfEvtHandle, &WNF_EDP_PURGE_APP_LEARNING_EVT, 1);
  }
  EdpInitPluginRuntimeConfig();
  return (unsigned __int8)EdppAuditEnabled;
}

```

## disassembly

```asm
0x14002bb30  push    rbp
0x14002bb32  mov     rbp, rsp
0x14002bb35  sub     rsp, 50h
0x14002bb39  lea     rax, aRegistryMachin_2; "\\REGISTRY\\MACHINE\\System\\CurrentCon"...
0x14002bb40  mov     [rbp+var_10], 960094h
0x14002bb48  mov     [rbp+var_8], rax
0x14002bb4c  lea     r9, [rbp+arg_18]
0x14002bb50  lea     rax, aEdpdisableaudi; "EdpDisableAudit"
0x14002bb57  mov     [rbp+var_20], 20001Eh
0x14002bb5f  lea     r8, [rbp+var_20]
0x14002bb63  mov     [rbp+var_18], rax
0x14002bb67  lea     rdx, [rbp+var_10]
0x14002bb6b  mov     [rbp+arg_18], 0
0x14002bb72  call    AiRegReadDwordValue
0x14002bb77  test    eax, eax
0x14002bb79  js      short loc_14002BB88
0x14002bb7b  cmp     [rbp+arg_18], 1
0x14002bb7f  jnz     short loc_14002BB88
0x14002bb81  mov     eax, 1
0x14002bb86  jmp     short loc_14002BBEA
0x14002bb88  lea     rcx, EdppEnableAudit
0x14002bb8f  call    EdppDoWorkAsSystem
0x14002bb94  test    eax, eax
0x14002bb96  js      short loc_14002BBD7
0x14002bb98  xor     r9d, r9d
0x14002bb9b  mov     [rsp+50h+var_28], 0
0x14002bba4  lea     rax, EdppAppEventsPurgeCallback
0x14002bbab  mov     cs:EdppAuditEnabled, 1
0x14002bbb2  lea     rdx, WNF_EDP_PURGE_APP_LEARNING_EVT
0x14002bbb9  mov     [rsp+50h+var_30], rax
0x14002bbbe  lea     rcx, EdppPurgeWnfEvtHandle
0x14002bbc5  lea     r8d, [r9+1]
0x14002bbc9  call    cs:__imp_ExSubscribeWnfStateChange
0x14002bbd0  nop     dword ptr [rax+rax+00h]
0x14002bbd5  jmp     short loc_14002BBDE
0x14002bbd7  mov     cs:EdppAuditEnabled, 0
0x14002bbde  call    EdpInitPluginRuntimeConfig
0x14002bbe3  movzx   eax, cs:EdppAuditEnabled
0x14002bbea  add     rsp, 50h
0x14002bbee  pop     rbp
0x14002bbef  retn
```
