# UpdateReserveManager::ClearTemporaryReserveInitParams(void)

- ea: `0x180013770`
- end: `0x18001383f`
- name: `?ClearTemporaryReserveInitParams@UpdateReserveManager@@AEAAJXZ`
- size: `207`
- prototype: `__int64 __fastcall(HKEY *this)`
- caller_count: `4`
- callee_count: `3`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180014960`
- `0x180015240`
- `0x1800192e0`
- `0x180019634`

## callees

- `0x18000fafc`
- `0x180013770`
- `0x180015ad0`

## import_xrefs

- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyValueW` at `0x1800137a4`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyValueW` at `0x180013812`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyValueW` at `0x1800137a4`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyValueW` at `0x180013812`

## string_xrefs

- `0x1800137bd`: `onecore\base\servicing\updatereservemanager\lib\updatereservemanager.cpp`
- `0x1800137c8`: `UpdateReserveManager::ClearTemporaryReserveInitParams`

## pseudocode

```c
__int64 __fastcall UpdateReserveManager::ClearTemporaryReserveInitParams(HKEY *this)
{
  __int64 result; // rax
  LSTATUS v3; // eax
  unsigned int v4; // ebx
  bool v5; // zf
  bool v6; // sf
  LSTATUS v7; // eax
  _QWORD v8[2]; // [rsp+20h] [rbp-20h] BYREF
  __int64 v9; // [rsp+30h] [rbp-10h]
  const char *v10; // [rsp+38h] [rbp-8h]

  result = UpdateReserveManager::EnsureNotInSafeMode((UpdateReserveManager *)this);
  if ( (int)result >= 0 )
  {
    v3 = RegDeleteKeyValueW(this[13], L"Microsoft\\Windows\\CurrentVersion\\ReserveManager", L"UserFreeSpaceMarker");
    v4 = v3;
    if ( v3 == 2 || (v5 = v3 == 0, v6 = v3 < 0, !v3) )
    {
      v7 = RegDeleteKeyValueW(this[13], L"Microsoft\\Windows\\CurrentVersion\\ReserveManager", L"PostUpgradeFreeSpace");
      v4 = v7;
      if ( v7 == 2 )
        return 0;
      v5 = v7 == 0;
      v6 = v7 < 0;
      if ( !v7 )
        return 0;
      v9 = 2753;
    }
    else
    {
      v9 = 2745;
    }
    v8[0] = "onecore\\base\\servicing\\updatereservemanager\\lib\\updatereservemanager.cpp";
    v8[1] = "UpdateReserveManager::ClearTemporaryReserveInitParams";
    v10 = "RetValue";
    if ( !v6 && !v5 )
      v4 = (unsigned __int16)v4 | 0x80070000;
    RtlReportErrorOrigination(v8, &GUID_e323b7c4_7a1a_4e06_bf6d_56ccd7377627, v4);
    return v4;
  }
  return result;
}

```

## disassembly

```asm
0x180013770  mov     [rsp-8+arg_8], rbx
0x180013775  mov     [rsp-8+arg_10], rdi
0x18001377a  push    rbp
0x18001377b  mov     rbp, rsp
0x18001377e  sub     rsp, 40h
0x180013782  mov     rdi, rcx
0x180013785  call    ?EnsureNotInSafeMode@UpdateReserveManager@@AEAAJXZ; UpdateReserveManager::EnsureNotInSafeMode(void)
0x18001378a  test    eax, eax
0x18001378c  js      loc_18001382F
0x180013792  mov     rcx, [rdi+68h]; hKey
0x180013796  lea     r8, aUserfreespacem; "UserFreeSpaceMarker"
0x18001379d  lea     rdx, aMicrosoftWindo_2; "Microsoft\\Windows\\CurrentVersion\\Res"...
0x1800137a4  call    cs:__imp_RegDeleteKeyValueW
0x1800137aa  mov     ebx, eax
0x1800137ac  cmp     eax, 2
0x1800137af  jz      short loc_180013800
0x1800137b1  test    eax, eax
0x1800137b3  jz      short loc_180013800
0x1800137b5  mov     [rbp+var_10], 0AB9h
0x1800137bd  lea     rax, aOnecoreBaseSer_1; "onecore\\base\\servicing\\updatereserve"...
0x1800137c4  mov     [rbp+var_20], rax
0x1800137c8  lea     rax, aUpdatereservem_31; "UpdateReserveManager::ClearTemporaryRes"...
0x1800137cf  mov     [rbp+var_18], rax
0x1800137d3  lea     rax, aRetvalue; "RetValue"
0x1800137da  mov     [rbp+var_8], rax
0x1800137de  jle     short loc_1800137E9
0x1800137e0  movzx   ebx, bx
0x1800137e3  or      ebx, 80070000h
0x1800137e9  mov     r8d, ebx
0x1800137ec  lea     rdx, _GUID_e323b7c4_7a1a_4e06_bf6d_56ccd7377627
0x1800137f3  lea     rcx, [rbp+var_20]
0x1800137f7  call    RtlReportErrorOrigination
0x1800137fc  mov     eax, ebx
0x1800137fe  jmp     short loc_18001382F
0x180013800  mov     rcx, [rdi+68h]; hKey
0x180013804  lea     r8, aPostupgradefre; "PostUpgradeFreeSpace"
0x18001380b  lea     rdx, aMicrosoftWindo_2; "Microsoft\\Windows\\CurrentVersion\\Res"...
0x180013812  call    cs:__imp_RegDeleteKeyValueW
0x180013818  mov     ebx, eax
0x18001381a  cmp     eax, 2
0x18001381d  jz      short loc_18001382D
0x18001381f  test    eax, eax
0x180013821  jz      short loc_18001382D
0x180013823  mov     [rbp+var_10], 0AC1h
0x18001382b  jmp     short loc_1800137BD
0x18001382d  xor     eax, eax
0x18001382f  mov     rbx, [rsp+40h+arg_8]
0x180013834  mov     rdi, [rsp+40h+arg_10]
0x180013839  add     rsp, 40h
0x18001383d  pop     rbp
0x18001383e  retn
```
