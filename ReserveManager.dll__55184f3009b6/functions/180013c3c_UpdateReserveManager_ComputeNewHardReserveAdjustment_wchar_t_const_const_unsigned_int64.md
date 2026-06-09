# UpdateReserveManager::ComputeNewHardReserveAdjustment(wchar_t const * const,unsigned __int64 *)

- ea: `0x180013c3c`
- end: `0x180013e7c`
- name: `?ComputeNewHardReserveAdjustment@UpdateReserveManager@@AEAAJQEB_WPEA_K@Z`
- size: `576`
- prototype: `__int64 __fastcall(HKEY *this, const WCHAR *, unsigned __int64 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180013850`

## callees

- `0x180003870`
- `0x18000fafc`
- `0x180013c3c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180013ca1`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180013cf8`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180013d53`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180013ca1`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180013cf8`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180013d53`

## string_xrefs

- `0x180013d78`: `onecore\base\servicing\updatereservemanager\lib\updatereservemanager.cpp`
- `0x180013dfd`: `onecore\base\servicing\updatereservemanager\lib\updatereservemanager.cpp`
- `0x180013d83`: `UpdateReserveManager::ComputeNewHardReserveAdjustment`
- `0x180013e17`: `UpdateReserveManager::ComputeNewHardReserveAdjustment`

## pseudocode

```c
__int64 __fastcall UpdateReserveManager::ComputeNewHardReserveAdjustment(
        HKEY *this,
        const WCHAR *a2,
        unsigned __int64 *a3)
{
  signed int ValueW; // ebx
  HKEY v7; // rcx
  HKEY v8; // rcx
  unsigned __int64 v9; // rcx
  bool v10; // cc
  unsigned __int64 v12; // r8
  const char *v13; // [rsp+40h] [rbp-19h] BYREF
  const char *v14; // [rsp+48h] [rbp-11h]
  __int64 v15; // [rsp+50h] [rbp-9h]
  const char *v16; // [rsp+58h] [rbp-1h]
  DWORD pcbData; // [rsp+60h] [rbp+7h] BYREF
  unsigned __int64 v18; // [rsp+68h] [rbp+Fh] BYREF
  unsigned __int64 pvData; // [rsp+70h] [rbp+17h] BYREF
  unsigned __int64 v20; // [rsp+78h] [rbp+1Fh] BYREF

  pvData = 0;
  pcbData = 8;
  ValueW = RegGetValueW(this[13], a2, L"PendingHardReserveIncrease", 0x40u, 0, &pvData, &pcbData);
  if ( ValueW == 2 )
  {
    pvData = 0;
  }
  else
  {
    v10 = ValueW <= 0;
    if ( ValueW )
    {
      v15 = 3726;
      goto LABEL_9;
    }
  }
  v7 = this[13];
  v20 = 0;
  pcbData = 8;
  ValueW = RegGetValueW(v7, a2, L"PendingHardReserveDecrease", 0x40u, 0, &v20, &pcbData);
  if ( ValueW == 2 )
  {
    v20 = 0;
  }
  else
  {
    v10 = ValueW <= 0;
    if ( ValueW )
    {
      v15 = 3745;
      goto LABEL_9;
    }
  }
  v8 = this[13];
  v18 = 0;
  pcbData = 8;
  ValueW = RegGetValueW(
             v8,
             L"Microsoft\\Windows\\CurrentVersion\\ReserveManager",
             L"HardReserveAdjustment",
             0x40u,
             0,
             &v18,
             &pcbData);
  if ( ValueW != 2 )
  {
    v10 = ValueW <= 0;
    if ( !ValueW )
    {
      v9 = v18;
      goto LABEL_17;
    }
    v15 = 3764;
LABEL_9:
    v13 = "onecore\\base\\servicing\\updatereservemanager\\lib\\updatereservemanager.cpp";
    v14 = "UpdateReserveManager::ComputeNewHardReserveAdjustment";
    v16 = "RetValue";
    if ( !v10 )
      ValueW = (unsigned __int16)ValueW | 0x80070000;
    RtlReportErrorOrigination(&v13, &GUID_e323b7c4_7a1a_4e06_bf6d_56ccd7377627, (unsigned int)ValueW);
    return (unsigned int)ValueW;
  }
  v9 = 0;
  v18 = 0;
LABEL_17:
  if ( pvData <= v20 )
  {
    if ( pvData >= v20 )
    {
      v12 = v9;
    }
    else if ( v20 - pvData < v9 )
    {
      v12 = v9 - (v20 - pvData);
    }
    else
    {
      v12 = 0;
    }
  }
  else
  {
    v12 = v9 - v20 + pvData;
    if ( v12 < v9 )
    {
      v15 = 3773;
      v13 = "onecore\\base\\servicing\\updatereservemanager\\lib\\updatereservemanager.cpp";
      v14 = "UpdateReserveManager::ComputeNewHardReserveAdjustment";
      v16 = "::ULongLongAdd(CurrentHardReserveAdjustment, PendingAdjustment, &NewHardReserveAdjustment)";
      RtlReportErrorOrigination(&v13, &GUID_e323b7c4_7a1a_4e06_bf6d_56ccd7377627, 2147942934LL);
      return 2147942934LL;
    }
  }
  *a3 = v12;
  return 0;
}

```

## disassembly

```asm
0x180013c3c  push    rbp
0x180013c3e  push    rbx
0x180013c3f  push    rsi
0x180013c40  push    rdi
0x180013c41  push    r14
0x180013c43  lea     rbp, [rsp-37h]
0x180013c48  sub     rsp, 90h
0x180013c4f  mov     rax, cs:__security_cookie
0x180013c56  xor     rax, rsp
0x180013c59  mov     [rbp+57h+var_30], rax
0x180013c5d  lea     rax, [rbp+57h+var_50]
0x180013c61  mov     [rbp+57h+var_40], 0
0x180013c69  mov     [rsp+0B0h+pcbData], rax; pcbData
0x180013c6e  mov     r14, r8
0x180013c71  lea     rax, [rbp+57h+var_40]
0x180013c75  mov     [rbp+57h+var_50], 8
0x180013c7c  mov     rdi, rcx
0x180013c7f  mov     [rsp+0B0h+pvData], rax; pvData
0x180013c84  mov     rcx, [rcx+68h]; hkey
0x180013c88  lea     r8, aPendinghardres; "PendingHardReserveIncrease"
0x180013c8f  mov     r9d, 40h ; '@'; dwFlags
0x180013c95  mov     [rsp+0B0h+pdwType], 0; pdwType
0x180013c9e  mov     rsi, rdx
0x180013ca1  call    cs:__imp_RegGetValueW
0x180013ca7  mov     ebx, eax
0x180013ca9  cmp     eax, 2
0x180013cac  jnz     loc_180013D68
0x180013cb2  mov     [rbp+57h+var_40], 0
0x180013cba  mov     rcx, [rdi+68h]; hkey
0x180013cbe  lea     rax, [rbp+57h+var_50]
0x180013cc2  mov     [rsp+0B0h+pcbData], rax; pcbData
0x180013cc7  lea     r8, aPendinghardres_0; "PendingHardReserveDecrease"
0x180013cce  lea     rax, [rbp+57h+var_38]
0x180013cd2  mov     [rbp+57h+var_38], 0
0x180013cda  mov     [rsp+0B0h+pvData], rax; pvData
0x180013cdf  mov     r9d, 40h ; '@'; dwFlags
0x180013ce5  mov     rdx, rsi; lpSubKey
0x180013ce8  mov     [rsp+0B0h+pdwType], 0; pdwType
0x180013cf1  mov     [rbp+57h+var_50], 8
0x180013cf8  call    cs:__imp_RegGetValueW
0x180013cfe  mov     ebx, eax
0x180013d00  cmp     eax, 2
0x180013d03  jnz     loc_180013DBE
0x180013d09  mov     [rbp+57h+var_38], 0
0x180013d11  mov     rcx, [rdi+68h]; hkey
0x180013d15  lea     rax, [rbp+57h+var_50]
0x180013d19  mov     [rsp+0B0h+pcbData], rax; pcbData
0x180013d1e  lea     r8, aHardreserveadj; "HardReserveAdjustment"
0x180013d25  lea     rax, [rbp+57h+var_48]
0x180013d29  mov     [rbp+57h+var_48], 0
0x180013d31  mov     [rsp+0B0h+pvData], rax; pvData
0x180013d36  lea     rdx, aMicrosoftWindo_2; "Microsoft\\Windows\\CurrentVersion\\Res"...
0x180013d3d  mov     r9d, 40h ; '@'; dwFlags
0x180013d43  mov     [rsp+0B0h+pdwType], 0; pdwType
0x180013d4c  mov     [rbp+57h+var_50], 8
0x180013d53  call    cs:__imp_RegGetValueW
0x180013d59  mov     ebx, eax
0x180013d5b  cmp     eax, 2
0x180013d5e  jnz     short loc_180013DD0
0x180013d60  xor     ecx, ecx
0x180013d62  mov     [rbp+57h+var_48], rcx
0x180013d66  jmp     short loc_180013DE2
0x180013d68  test    ebx, ebx
0x180013d6a  jz      loc_180013CBA
0x180013d70  mov     [rbp+57h+var_60], 0E8Eh
0x180013d78  lea     rax, aOnecoreBaseSer_1; "onecore\\base\\servicing\\updatereserve"...
0x180013d7f  mov     [rbp+57h+var_70], rax
0x180013d83  lea     rax, aUpdatereservem_23; "UpdateReserveManager::ComputeNewHardRes"...
0x180013d8a  mov     [rbp+57h+var_68], rax
0x180013d8e  lea     rax, aRetvalue; "RetValue"
0x180013d95  mov     [rbp+57h+var_58], rax
0x180013d99  jle     short loc_180013DA4
0x180013d9b  movzx   ebx, bx
0x180013d9e  or      ebx, 80070000h
0x180013da4  mov     r8d, ebx
0x180013da7  lea     rdx, _GUID_e323b7c4_7a1a_4e06_bf6d_56ccd7377627
0x180013dae  lea     rcx, [rbp+57h+var_70]
0x180013db2  call    RtlReportErrorOrigination
0x180013db7  mov     eax, ebx
0x180013db9  jmp     loc_180013E62
0x180013dbe  test    ebx, ebx
0x180013dc0  jz      loc_180013D11
0x180013dc6  mov     [rbp+57h+var_60], 0EA1h
0x180013dce  jmp     short loc_180013D78
0x180013dd0  test    ebx, ebx
0x180013dd2  jz      short loc_180013DDE
0x180013dd4  mov     [rbp+57h+var_60], 0EB4h
0x180013ddc  jmp     short loc_180013D78
0x180013dde  mov     rcx, [rbp+57h+var_48]
0x180013de2  mov     r8, [rbp+57h+var_40]
0x180013de6  mov     rdx, [rbp+57h+var_38]
0x180013dea  cmp     r8, rdx
0x180013ded  jbe     short loc_180013E43
0x180013def  mov     rax, rcx
0x180013df2  sub     rax, rdx
0x180013df5  add     r8, rax
0x180013df8  cmp     r8, rcx
0x180013dfb  jnb     short loc_180013E5D
0x180013dfd  lea     rax, aOnecoreBaseSer_1; "onecore\\base\\servicing\\updatereserve"...
0x180013e04  mov     [rbp+57h+var_60], 0EBDh
0x180013e0c  mov     [rbp+57h+var_70], rax
0x180013e10  lea     rdx, _GUID_e323b7c4_7a1a_4e06_bf6d_56ccd7377627
0x180013e17  lea     rax, aUpdatereservem_23; "UpdateReserveManager::ComputeNewHardRes"...
0x180013e1e  mov     r8d, 80070216h
0x180013e24  mov     [rbp+57h+var_68], rax
0x180013e28  lea     rcx, [rbp+57h+var_70]
0x180013e2c  lea     rax, aUlonglongaddCu; "::ULongLongAdd(CurrentHardReserveAdjust"...
0x180013e33  mov     [rbp+57h+var_58], rax
0x180013e37  call    RtlReportErrorOrigination
0x180013e3c  mov     eax, 80070216h
0x180013e41  jmp     short loc_180013E62
0x180013e43  jnb     short loc_180013E5A
0x180013e45  sub     rdx, r8
0x180013e48  cmp     rdx, rcx
0x180013e4b  jb      short loc_180013E52
0x180013e4d  xor     r8d, r8d
0x180013e50  jmp     short loc_180013E5D
0x180013e52  mov     r8, rcx
0x180013e55  sub     r8, rdx
0x180013e58  jmp     short loc_180013E5D
0x180013e5a  mov     r8, rcx
0x180013e5d  mov     [r14], r8
0x180013e60  xor     eax, eax
0x180013e62  mov     rcx, [rbp+57h+var_30]
0x180013e66  xor     rcx, rsp; StackCookie
0x180013e69  call    __security_check_cookie
0x180013e6e  add     rsp, 90h
0x180013e75  pop     r14
0x180013e77  pop     rdi
0x180013e78  pop     rsi
0x180013e79  pop     rbx
0x180013e7a  pop     rbp
0x180013e7b  retn
```
