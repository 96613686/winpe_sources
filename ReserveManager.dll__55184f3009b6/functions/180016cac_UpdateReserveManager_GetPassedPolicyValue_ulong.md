# UpdateReserveManager::GetPassedPolicyValue(ulong *)

- ea: `0x180016cac`
- end: `0x180016d92`
- name: `?GetPassedPolicyValue@UpdateReserveManager@@AEAAJPEAK@Z`
- size: `230`
- prototype: `__int64 __fastcall(UpdateReserveManager *__hidden this, unsigned int *)`
- caller_count: `5`
- callee_count: `3`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1800155e0`
- `0x1800170ec`
- `0x1800177f8`
- `0x1800192e0`
- `0x18001edb0`

## callees

- `0x180003870`
- `0x18000fafc`
- `0x180016cac`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180016d0a`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180016d0a`

## string_xrefs

- `0x180016d1f`: `onecore\base\servicing\updatereservemanager\lib\updatereservemanager.cpp`
- `0x180016d34`: `UpdateReserveManager::GetPassedPolicyValue`

## pseudocode

```c
__int64 __fastcall UpdateReserveManager::GetPassedPolicyValue(UpdateReserveManager *this, unsigned int *a2)
{
  HKEY v2; // rcx
  int ValueW; // ebx
  unsigned int v5; // eax
  _QWORD v7[4]; // [rsp+40h] [rbp-38h] BYREF
  unsigned int v8; // [rsp+60h] [rbp-18h] BYREF
  DWORD v9; // [rsp+64h] [rbp-14h] BYREF

  v2 = (HKEY)*((_QWORD *)this + 13);
  v8 = 0;
  v9 = 4;
  ValueW = RegGetValueW(v2, L"Microsoft\\Windows\\CurrentVersion\\ReserveManager", L"PassedPolicy", 0x10u, 0, &v8, &v9);
  if ( ValueW == 2 )
  {
    v5 = 0;
LABEL_8:
    *a2 = v5;
    return 0;
  }
  if ( !ValueW )
  {
    v5 = v8;
    goto LABEL_8;
  }
  v7[2] = 3634;
  v7[0] = "onecore\\base\\servicing\\updatereservemanager\\lib\\updatereservemanager.cpp";
  v7[1] = "UpdateReserveManager::GetPassedPolicyValue";
  v7[3] = "RetValue";
  if ( ValueW > 0 )
    ValueW = (unsigned __int16)ValueW | 0x80070000;
  RtlReportErrorOrigination(v7, &GUID_e323b7c4_7a1a_4e06_bf6d_56ccd7377627, (unsigned int)ValueW);
  return (unsigned int)ValueW;
}

```

## disassembly

```asm
0x180016cac  mov     r11, rsp
0x180016caf  mov     [r11+18h], rbx
0x180016cb3  push    rdi
0x180016cb4  sub     rsp, 70h
0x180016cb8  mov     rax, cs:__security_cookie
0x180016cbf  xor     rax, rsp
0x180016cc2  mov     [rsp+78h+var_10], rax
0x180016cc7  mov     rcx, [rcx+68h]; hkey
0x180016ccb  lea     rax, [r11-14h]
0x180016ccf  mov     [r11-48h], rax
0x180016cd3  lea     r8, aPassedpolicy; "PassedPolicy"
0x180016cda  lea     rax, [r11-18h]
0x180016cde  mov     [rsp+78h+var_18], 0
0x180016ce6  mov     rdi, rdx
0x180016ce9  mov     [r11-50h], rax
0x180016ced  mov     r9d, 10h; dwFlags
0x180016cf3  mov     qword ptr [r11-58h], 0
0x180016cfb  lea     rdx, aMicrosoftWindo_2; "Microsoft\\Windows\\CurrentVersion\\Res"...
0x180016d02  mov     [rsp+78h+var_14], 4
0x180016d0a  call    cs:__imp_RegGetValueW
0x180016d10  mov     ebx, eax
0x180016d12  cmp     eax, 2
0x180016d15  jnz     short loc_180016D1B
0x180016d17  xor     eax, eax
0x180016d19  jmp     short loc_180016D73
0x180016d1b  test    ebx, ebx
0x180016d1d  jz      short loc_180016D6F
0x180016d1f  lea     rax, aOnecoreBaseSer_1; "onecore\\base\\servicing\\updatereserve"...
0x180016d26  mov     [rsp+78h+var_28], 0E32h
0x180016d2f  mov     [rsp+78h+var_38], rax
0x180016d34  lea     rax, aUpdatereservem_26; "UpdateReserveManager::GetPassedPolicyVa"...
0x180016d3b  mov     [rsp+78h+var_30], rax
0x180016d40  lea     rax, aRetvalue; "RetValue"
0x180016d47  mov     [rsp+78h+var_20], rax
0x180016d4c  jle     short loc_180016D57
0x180016d4e  movzx   ebx, bx
0x180016d51  or      ebx, 80070000h
0x180016d57  mov     r8d, ebx
0x180016d5a  lea     rdx, _GUID_e323b7c4_7a1a_4e06_bf6d_56ccd7377627
0x180016d61  lea     rcx, [rsp+78h+var_38]
0x180016d66  call    RtlReportErrorOrigination
0x180016d6b  mov     eax, ebx
0x180016d6d  jmp     short loc_180016D77
0x180016d6f  mov     eax, [rsp+78h+var_18]
0x180016d73  mov     [rdi], eax
0x180016d75  xor     eax, eax
0x180016d77  mov     rcx, [rsp+78h+var_10]
0x180016d7c  xor     rcx, rsp; StackCookie
0x180016d7f  call    __security_check_cookie
0x180016d84  mov     rbx, [rsp+78h+arg_10]
0x180016d8c  add     rsp, 70h
0x180016d90  pop     rdi
0x180016d91  retn
```
