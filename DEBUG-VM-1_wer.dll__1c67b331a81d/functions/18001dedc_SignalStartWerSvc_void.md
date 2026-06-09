# SignalStartWerSvc(void)

- ea: `0x18001dedc`
- end: `0x18001dfa6`
- name: `?SignalStartWerSvc@@YAJXZ`
- size: `202`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, service_task, installer_update`

## callers

- `0x18001dc54`

## callees

- `0x18001dedc`
- `0x180050db0`

## import_xrefs

- `ntdll!ZwQueryWnfStateNameInformation` at `0x18001df23`
- `ntdll!ZwQueryWnfStateNameInformation` at `0x18001df23`
- `ntdll!ZwUpdateWnfStateData` at `0x18001df4f`
- `ntdll!ZwUpdateWnfStateData` at `0x18001df4f`
- `ntdll!EtwEventWriteNoRegistration` at `0x18001df74`
- `ntdll!EtwEventWriteNoRegistration` at `0x18001df74`

## pseudocode

```c
__int64 SignalStartWerSvc(void)
{
  BOOL v0; // ebx
  int v1; // eax
  int v2; // ecx
  __int64 result; // rax
  int v4; // [rsp+40h] [rbp-28h] BYREF
  __int128 v5; // [rsp+48h] [rbp-20h] BYREF

  v4 = 0;
  v0 = 0;
  v5 = 0;
  if ( (int)ZwQueryWnfStateNameInformation(&WNF_WER_SERVICE_START, 1, 0, &v4, 4) >= 0 && v4 )
    v0 = (int)ZwUpdateWnfStateData(&WNF_WER_SERVICE_START, 0, 0, 0, 0, 0, 0) >= 0;
  v5 = 0;
  v1 = EtwEventWriteNoRegistration(&`SignalStartWerSvc'::`2'::WerSvcTriggerGuid, &v5, 0, 0);
  v2 = v0 + 1;
  if ( v1 )
    v2 = v0;
  result = 0;
  if ( !v2 )
    return 3221225600LL;
  return result;
}

```

## disassembly

```asm
0x18001dedc  mov     [rsp+arg_0], rbx
0x18001dee1  push    rsi
0x18001dee2  sub     rsp, 60h
0x18001dee6  mov     rax, cs:__security_cookie
0x18001deed  xor     rax, rsp
0x18001def0  mov     [rsp+68h+var_10], rax
0x18001def5  xorps   xmm0, xmm0
0x18001def8  mov     [rsp+68h+var_28], 0
0x18001df00  xor     ebx, ebx
0x18001df02  mov     dword ptr [rsp+68h+var_48], 4
0x18001df0a  lea     r9, [rsp+68h+var_28]
0x18001df0f  xor     r8d, r8d
0x18001df12  lea     rcx, WNF_WER_SERVICE_START
0x18001df19  movups  [rsp+68h+var_20], xmm0
0x18001df1e  lea     esi, [rbx+1]
0x18001df21  mov     edx, esi
0x18001df23  call    cs:__imp_ZwQueryWnfStateNameInformation
0x18001df29  test    eax, eax
0x18001df2b  js      short loc_18001DF5A
0x18001df2d  cmp     [rsp+68h+var_28], ebx
0x18001df31  jz      short loc_18001DF5A
0x18001df33  mov     [rsp+68h+var_38], ebx
0x18001df37  lea     rcx, WNF_WER_SERVICE_START
0x18001df3e  mov     [rsp+68h+var_40], ebx
0x18001df42  xor     r9d, r9d
0x18001df45  xor     r8d, r8d
0x18001df48  mov     [rsp+68h+var_48], rbx
0x18001df4d  xor     edx, edx
0x18001df4f  call    cs:__imp_ZwUpdateWnfStateData
0x18001df55  test    eax, eax
0x18001df57  cmovns  ebx, esi
0x18001df5a  xorps   xmm0, xmm0
0x18001df5d  lea     rdx, [rsp+68h+var_20]
0x18001df62  xor     r9d, r9d
0x18001df65  lea     rcx, ?WerSvcTriggerGuid@?1??SignalStartWerSvc@@YAJXZ@4U_GUID@@B; _GUID const `SignalStartWerSvc(void)'::`2'::WerSvcTriggerGuid
0x18001df6c  xor     r8d, r8d
0x18001df6f  movups  [rsp+68h+var_20], xmm0
0x18001df74  call    cs:__imp_EtwEventWriteNoRegistration
0x18001df7a  lea     ecx, [rbx+1]
0x18001df7d  mov     edx, 0C0000080h
0x18001df82  test    eax, eax
0x18001df84  cmovnz  ecx, ebx
0x18001df87  xor     eax, eax
0x18001df89  test    ecx, ecx
0x18001df8b  cmovz   eax, edx
0x18001df8e  mov     rcx, [rsp+68h+var_10]
0x18001df93  xor     rcx, rsp; StackCookie
0x18001df96  call    __security_check_cookie
0x18001df9b  mov     rbx, [rsp+68h+arg_0]
0x18001dfa0  add     rsp, 60h
0x18001dfa4  pop     rsi
0x18001dfa5  retn
```
