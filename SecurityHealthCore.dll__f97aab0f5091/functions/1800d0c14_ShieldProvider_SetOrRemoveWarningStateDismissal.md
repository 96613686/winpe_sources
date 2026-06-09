# ShieldProvider::SetOrRemoveWarningStateDismissal

- ea: `0x1800d0c14`
- end: `0x1800d10e2`
- name: `ShieldProvider::SetOrRemoveWarningStateDismissal`
- size: `1230`
- prototype: ``
- caller_count: `21`
- callee_count: `16`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18002c550`
- `0x18002ca78`
- `0x18002de5c`
- `0x180036140`
- `0x1800376b0`
- `0x18004f18c`
- `0x180051800`
- `0x180051c78`
- `0x18006e0f0`
- `0x180073170`
- `0x180073390`
- `0x180073670`
- `0x180074174`
- `0x180074b50`
- `0x180074f40`
- `0x180095e50`
- `0x1800bc530`
- `0x1800c5970`
- `0x1800c8b44`
- `0x1800c9520`
- `0x1800ca510`

## callees

- `0x180004ae0`
- `0x18000d7fc`
- `0x18000f02c`
- `0x18000f094`
- `0x1800cd524`
- `0x1800ceb24`
- `0x1800cf91c`
- `0x1800cfa28`
- `0x1800d012c`
- `0x1800d015c`
- `0x1800d0c14`
- `0x1800d3750`
- `0x1800dd3e8`
- `0x1800dd4ec`
- `0x1800de1bc`
- `0x1800df118`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1800d0fb2`
- `KERNEL32!GetLastError` at `0x1800d0fb2`
- `KERNEL32!CloseHandle` at `0x1800d1051`
- `KERNEL32!CloseHandle` at `0x1800d1090`
- `KERNEL32!CloseHandle` at `0x1800d1051`
- `KERNEL32!CloseHandle` at `0x1800d1090`
- `KERNEL32!GetCurrentThread` at `0x1800d0f94`
- `KERNEL32!GetCurrentThread` at `0x1800d0f94`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800d0d3b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800d0da3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800d0e0b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800d0e87`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800d0e96`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800d0ea5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800d0ec7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800d0ed6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800d0ee5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800d0d3b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800d0da3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800d0e0b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800d0e87`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800d0e96`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800d0ea5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800d0ec7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800d0ed6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800d0ee5`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x1800d0ce6`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x1800d0ce6`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800d0fa8`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800d0fa8`

## string_xrefs

- `0x1800d0f4f`: `SecurityHealthHost.exe`

## pseudocode

```c
__int64 __fastcall ShieldProvider::SetOrRemoveWarningStateDismissal(unsigned int a1, char a2)
{
  _QWORD *v4; // rcx
  signed int IsDevMode; // ebx
  __int64 v6; // rdx
  ShieldProvider *v8; // rcx
  const struct std::nothrow_t *v9; // rdx
  LSTATUS v10; // eax
  const unsigned __int16 *v11; // r8
  HKEY v12; // rbx
  HKEY v13; // rdi
  int v14; // eax
  const struct std::nothrow_t *v15; // rdx
  unsigned int v16; // esi
  bool *v17; // rdx
  ShieldProvider *v18; // rcx
  unsigned __int16 *v19; // r8
  HANDLE CurrentThread; // rax
  void *v21; // r8
  unsigned int v22; // r9d
  signed int LastError; // eax
  _QWORD *v24; // rcx
  __int64 v25; // rdx
  __int64 IndexForDeviceWideWarningDismissalState; // rbx
  unsigned int v27; // [rsp+20h] [rbp-40h]
  struct _SECURITY_ATTRIBUTES *v28; // [rsp+28h] [rbp-38h]
  struct _SECURITY_ATTRIBUTES *v29; // [rsp+28h] [rbp-38h]
  const void *v30; // [rsp+28h] [rbp-38h]
  HKEY v31; // [rsp+30h] [rbp-30h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-28h] BYREF
  HKEY v33; // [rsp+40h] [rbp-20h] BYREF
  _BYTE v34[24]; // [rsp+48h] [rbp-18h] BYREF
  ShieldProvider *v35; // [rsp+90h] [rbp+30h] BYREF
  HKEY phkResult; // [rsp+98h] [rbp+38h] BYREF

  if ( !(unsigned __int8)ShieldProvider::IsValidWarningState() )
  {
    v4 = WPP_GLOBAL_Control;
    IsDevMode = -2147024809;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      return (unsigned int)IsDevMode;
    v6 = 18;
LABEL_5:
    WPP_SF_d(v4[2], v6, WPP_154eeafd5d0d31ef67e6778b817bc92a_Traceguids, (unsigned int)IsDevMode);
    return (unsigned int)IsDevMode;
  }
  if ( !(unsigned __int8)ShieldProvider::IsPerUserWarningState() )
  {
    if ( ShieldProvider::IsOSWcos(v8) )
    {
      LOBYTE(v35) = 0;
      IsDevMode = ShieldProvider::GetIsDevMode((ShieldProvider *)&v35, v17);
      if ( IsDevMode < 0 )
      {
        v4 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          return (unsigned int)IsDevMode;
        v6 = 24;
        goto LABEL_5;
      }
      LOBYTE(v18) = (_BYTE)v35;
      IsDevMode = ShieldProvider::ValidateCaller(v18, (bool)L"SecurityHealthHost.exe", v19);
      if ( IsDevMode < 0 )
      {
        v4 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          return (unsigned int)IsDevMode;
        v6 = 25;
        goto LABEL_5;
      }
      goto LABEL_90;
    }
    phkResult = 0;
    CurrentThread = GetCurrentThread();
    if ( OpenThreadToken(CurrentThread, 8u, 0, (PHANDLE)&phkResult) )
      goto LABEL_77;
    LastError = GetLastError();
    IsDevMode = LastError;
    if ( LastError > 0 )
      IsDevMode = (unsigned __int16)LastError | 0x80070000;
    if ( IsDevMode >= 0 )
    {
LABEL_77:
      LOBYTE(v35) = 0;
      IsDevMode = CommonUtil::UtilCheckTokenMembershipByRid((CommonUtil *)&v35, (bool *)phkResult, v21, v22, v27);
      if ( IsDevMode < 0 )
      {
        v24 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v25 = 26;
          goto LABEL_81;
        }
LABEL_82:
        if ( phkResult )
          CloseHandle(phkResult);
        return (unsigned int)IsDevMode;
      }
      if ( !(_BYTE)v35 )
      {
        v24 = WPP_GLOBAL_Control;
        IsDevMode = -2147024891;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v25 = 27;
          goto LABEL_81;
        }
        goto LABEL_82;
      }
    }
    else if ( !a2 || IsDevMode != -2147023888 )
    {
      v24 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v25 = 28;
LABEL_81:
        WPP_SF_d(v24[2], v25, WPP_154eeafd5d0d31ef67e6778b817bc92a_Traceguids, (unsigned int)IsDevMode);
        goto LABEL_82;
      }
      goto LABEL_82;
    }
    if ( phkResult )
      CloseHandle(phkResult);
LABEL_90:
    IndexForDeviceWideWarningDismissalState = (unsigned int)ShieldProvider::GetIndexForDeviceWideWarningDismissalState(a1);
    CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>(
      v34,
      ShieldProvider::g_aCSwarningStates);
    v34[16] = 0;
    *((_BYTE *)qword_18013A630 + IndexForDeviceWideWarningDismissalState) = a2 ^ 1;
    CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::~CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>(v34);
    return 0;
  }
  v31 = 0;
  IsDevMode = ShieldProvider::GetNameForWarningState(v8, &v31);
  if ( IsDevMode < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        19,
        WPP_154eeafd5d0d31ef67e6778b817bc92a_Traceguids,
        (unsigned int)IsDevMode);
LABEL_12:
    if ( v31 )
      operator delete(v31, v9);
    return (unsigned int)IsDevMode;
  }
  phkResult = 0;
  v10 = RegOpenCurrentUser(0x20006u, &phkResult);
  IsDevMode = v10;
  if ( v10 )
  {
    if ( v10 > 0 )
      IsDevMode = (unsigned __int16)v10 | 0x80070000;
    if ( IsDevMode < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          20,
          WPP_154eeafd5d0d31ef67e6778b817bc92a_Traceguids,
          (unsigned int)IsDevMode);
LABEL_21:
      if ( phkResult )
        RegCloseKey(phkResult);
      goto LABEL_12;
    }
  }
  hKey = 0;
  IsDevMode = CommonUtil::UtilRegCreateKey(
                (CommonUtil *)&hKey,
                (HKEY *)phkResult,
                (HKEY)&stru_1800F5070,
                (const unsigned __int16 *)0x20006,
                0,
                v28,
                (unsigned int)v31);
  if ( IsDevMode < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        21,
        WPP_154eeafd5d0d31ef67e6778b817bc92a_Traceguids,
        (unsigned int)IsDevMode);
LABEL_27:
    if ( hKey )
      RegCloseKey(hKey);
    goto LABEL_21;
  }
  v33 = 0;
  IsDevMode = CommonUtil::UtilRegCreateKey(
                (CommonUtil *)&v33,
                (HKEY *)phkResult,
                (HKEY)&stru_180104F50,
                (const unsigned __int16 *)0x20006,
                0,
                v29,
                (unsigned int)v31);
  if ( IsDevMode < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        22,
        WPP_154eeafd5d0d31ef67e6778b817bc92a_Traceguids,
        (unsigned int)IsDevMode);
    if ( v33 )
      RegCloseKey(v33);
    goto LABEL_27;
  }
  v12 = v31;
  v13 = v33;
  if ( a2 )
  {
    v14 = CommonUtil::UtilRegDeleteValue((CommonUtil *)v33, v31, v11);
  }
  else
  {
    LODWORD(v35) = 0;
    v14 = CommonUtil::UtilRegSetValueInternal(
            (CommonUtil *)v33,
            v31,
            (const unsigned __int16 *)4,
            4u,
            (unsigned __int64)&v35,
            v30);
  }
  v16 = v14;
  if ( v14 >= 0 )
  {
    if ( v13 )
      RegCloseKey(v13);
    if ( hKey )
      RegCloseKey(hKey);
    if ( phkResult )
      RegCloseKey(phkResult);
    if ( v12 )
      operator delete(v12, v15);
    return 0;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      23,
      WPP_154eeafd5d0d31ef67e6778b817bc92a_Traceguids,
      (unsigned int)v14);
  if ( v13 )
    RegCloseKey(v13);
  if ( hKey )
    RegCloseKey(hKey);
  if ( phkResult )
    RegCloseKey(phkResult);
  if ( v12 )
    operator delete(v12, v15);
  return v16;
}

```

## disassembly

```asm
0x1800d0c14  mov     [rsp-18h+arg_0], rbx
0x1800d0c19  mov     [rsp-18h+arg_8], rsi
0x1800d0c1e  push    rbp
0x1800d0c1f  push    rdi
0x1800d0c20  push    r14
0x1800d0c22  mov     rbp, rsp
0x1800d0c25  sub     rsp, 60h
0x1800d0c29  mov     sil, dl
0x1800d0c2c  mov     edi, ecx
0x1800d0c2e  call    ?IsValidWarningState@ShieldProvider@@YA_NW4PillarStatusFlag@@@Z; ShieldProvider::IsValidWarningState(PillarStatusFlag)
0x1800d0c33  xor     r14d, r14d
0x1800d0c36  test    al, al
0x1800d0c38  jnz     short loc_1800D0C76
0x1800d0c3a  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d0c41  lea     rax, WPP_GLOBAL_Control
0x1800d0c48  mov     ebx, 80070057h
0x1800d0c4d  cmp     rcx, rax
0x1800d0c50  jz      short loc_1800D0C6F
0x1800d0c52  test    byte ptr [rcx+1Ch], 1
0x1800d0c56  jz      short loc_1800D0C6F
0x1800d0c58  lea     edx, [r14+12h]
0x1800d0c5c  mov     rcx, [rcx+10h]
0x1800d0c60  lea     r8, WPP_154eeafd5d0d31ef67e6778b817bc92a_Traceguids
0x1800d0c67  mov     r9d, ebx
0x1800d0c6a  call    WPP_SF_d
0x1800d0c6f  mov     eax, ebx
0x1800d0c71  jmp     loc_1800D10CD
0x1800d0c76  call    ?IsPerUserWarningState@ShieldProvider@@YA_NW4PillarStatusFlag@@@Z; ShieldProvider::IsPerUserWarningState(PillarStatusFlag)
0x1800d0c7b  test    al, al
0x1800d0c7d  jz      loc_1800D0F01
0x1800d0c83  lea     rdx, [rbp+var_30]
0x1800d0c87  mov     [rbp+var_30], r14
0x1800d0c8b  call    ShieldProvider__GetNameForWarningState
0x1800d0c90  mov     ebx, eax
0x1800d0c92  test    eax, eax
0x1800d0c94  jns     short loc_1800D0CD7
0x1800d0c96  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d0c9d  lea     rax, WPP_GLOBAL_Control
0x1800d0ca4  cmp     rcx, rax
0x1800d0ca7  jz      short loc_1800D0CC7
0x1800d0ca9  test    byte ptr [rcx+1Ch], 1
0x1800d0cad  jz      short loc_1800D0CC7
0x1800d0caf  mov     rcx, [rcx+10h]
0x1800d0cb3  lea     r8, WPP_154eeafd5d0d31ef67e6778b817bc92a_Traceguids
0x1800d0cba  mov     edx, 13h
0x1800d0cbf  mov     r9d, ebx
0x1800d0cc2  call    WPP_SF_d
0x1800d0cc7  mov     rcx, [rbp+var_30]; void *
0x1800d0ccb  test    rcx, rcx
0x1800d0cce  jz      short loc_1800D0C6F
0x1800d0cd0  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800d0cd5  jmp     short loc_1800D0C6F
0x1800d0cd7  mov     edi, 20006h
0x1800d0cdc  mov     [rbp+phkResult], r14
0x1800d0ce0  mov     ecx, edi; samDesired
0x1800d0ce2  lea     rdx, [rbp+phkResult]; phkResult
0x1800d0ce6  call    cs:__imp_RegOpenCurrentUser
0x1800d0cec  mov     ebx, eax
0x1800d0cee  test    eax, eax
0x1800d0cf0  jz      short loc_1800D0D43
0x1800d0cf2  jle     short loc_1800D0CFD
0x1800d0cf4  movzx   ebx, ax
0x1800d0cf7  or      ebx, 80070000h
0x1800d0cfd  test    ebx, ebx
0x1800d0cff  jns     short loc_1800D0D43
0x1800d0d01  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d0d08  lea     rax, WPP_GLOBAL_Control
0x1800d0d0f  cmp     rcx, rax
0x1800d0d12  jz      short loc_1800D0D32
0x1800d0d14  test    byte ptr [rcx+1Ch], 1
0x1800d0d18  jz      short loc_1800D0D32
0x1800d0d1a  mov     rcx, [rcx+10h]
0x1800d0d1e  lea     r8, WPP_154eeafd5d0d31ef67e6778b817bc92a_Traceguids
0x1800d0d25  mov     edx, 14h
0x1800d0d2a  mov     r9d, ebx
0x1800d0d2d  call    WPP_SF_d
0x1800d0d32  mov     rcx, [rbp+phkResult]; hKey
0x1800d0d36  test    rcx, rcx
0x1800d0d39  jz      short loc_1800D0CC7
0x1800d0d3b  call    cs:__imp_RegCloseKey
0x1800d0d41  jmp     short loc_1800D0CC7
0x1800d0d43  mov     rdx, [rbp+phkResult]; HKEY *
0x1800d0d47  lea     r8, stru_1800F5070; HKEY
0x1800d0d4e  mov     r9d, edi; unsigned __int16 *
0x1800d0d51  mov     [rbp+hKey], r14
0x1800d0d55  lea     rcx, [rbp+hKey]; this
0x1800d0d59  mov     qword ptr [rsp+60h+var_40], r14; unsigned int
0x1800d0d5e  call    ?UtilRegCreateKey@CommonUtil@@YAJPEAPEAUHKEY__@@PEAU2@PEBGKPEAU_SECURITY_ATTRIBUTES@@K@Z; CommonUtil::UtilRegCreateKey(HKEY__ * *,HKEY__ *,ushort const *,ulong,_SECURITY_ATTRIBUTES *,ulong)
0x1800d0d63  mov     ebx, eax
0x1800d0d65  test    eax, eax
0x1800d0d67  jns     short loc_1800D0DAB
0x1800d0d69  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d0d70  lea     rax, WPP_GLOBAL_Control
0x1800d0d77  cmp     rcx, rax
0x1800d0d7a  jz      short loc_1800D0D9A
0x1800d0d7c  test    byte ptr [rcx+1Ch], 1
0x1800d0d80  jz      short loc_1800D0D9A
0x1800d0d82  mov     rcx, [rcx+10h]
0x1800d0d86  lea     r8, WPP_154eeafd5d0d31ef67e6778b817bc92a_Traceguids
0x1800d0d8d  mov     edx, 15h
0x1800d0d92  mov     r9d, ebx
0x1800d0d95  call    WPP_SF_d
0x1800d0d9a  mov     rcx, [rbp+hKey]; hKey
0x1800d0d9e  test    rcx, rcx
0x1800d0da1  jz      short loc_1800D0D32
0x1800d0da3  call    cs:__imp_RegCloseKey
0x1800d0da9  jmp     short loc_1800D0D32
0x1800d0dab  mov     rdx, [rbp+phkResult]; HKEY *
0x1800d0daf  lea     r8, stru_180104F50; HKEY
0x1800d0db6  mov     r9d, edi; unsigned __int16 *
0x1800d0db9  mov     [rbp+var_20], r14
0x1800d0dbd  lea     rcx, [rbp+var_20]; this
0x1800d0dc1  mov     qword ptr [rsp+60h+var_40], r14; unsigned int
0x1800d0dc6  call    ?UtilRegCreateKey@CommonUtil@@YAJPEAPEAUHKEY__@@PEAU2@PEBGKPEAU_SECURITY_ATTRIBUTES@@K@Z; CommonUtil::UtilRegCreateKey(HKEY__ * *,HKEY__ *,ushort const *,ulong,_SECURITY_ATTRIBUTES *,ulong)
0x1800d0dcb  mov     ebx, eax
0x1800d0dcd  test    eax, eax
0x1800d0dcf  jns     short loc_1800D0E13
0x1800d0dd1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d0dd8  lea     rax, WPP_GLOBAL_Control
0x1800d0ddf  cmp     rcx, rax
0x1800d0de2  jz      short loc_1800D0E02
0x1800d0de4  test    byte ptr [rcx+1Ch], 1
0x1800d0de8  jz      short loc_1800D0E02
0x1800d0dea  mov     rcx, [rcx+10h]
0x1800d0dee  lea     r8, WPP_154eeafd5d0d31ef67e6778b817bc92a_Traceguids
0x1800d0df5  mov     edx, 16h
0x1800d0dfa  mov     r9d, ebx
0x1800d0dfd  call    WPP_SF_d
0x1800d0e02  mov     rcx, [rbp+var_20]; hKey
0x1800d0e06  test    rcx, rcx
0x1800d0e09  jz      short loc_1800D0D9A
0x1800d0e0b  call    cs:__imp_RegCloseKey
0x1800d0e11  jmp     short loc_1800D0D9A
0x1800d0e13  mov     rbx, [rbp+var_30]
0x1800d0e17  mov     rdi, [rbp+var_20]
0x1800d0e1b  mov     rdx, rbx; HKEY
0x1800d0e1e  mov     rcx, rdi; this
0x1800d0e21  test    sil, sil
0x1800d0e24  jz      short loc_1800D0E2D
0x1800d0e26  call    ?UtilRegDeleteValue@CommonUtil@@YAJPEAUHKEY__@@PEBG@Z; CommonUtil::UtilRegDeleteValue(HKEY__ *,ushort const *)
0x1800d0e2b  jmp     short loc_1800D0E48
0x1800d0e2d  mov     r8d, 4; unsigned __int16 *
0x1800d0e33  mov     dword ptr [rbp+arg_10], r14d
0x1800d0e37  lea     rax, [rbp+arg_10]
0x1800d0e3b  mov     r9d, r8d; unsigned int
0x1800d0e3e  mov     qword ptr [rsp+60h+var_40], rax; unsigned __int64
0x1800d0e43  call    ?UtilRegSetValueInternal@CommonUtil@@YAJPEAUHKEY__@@PEBGK_KPEBX@Z; CommonUtil::UtilRegSetValueInternal(HKEY__ *,ushort const *,ulong,unsigned __int64,void const *)
0x1800d0e48  mov     esi, eax
0x1800d0e4a  test    eax, eax
0x1800d0e4c  jns     short loc_1800D0EBF
0x1800d0e4e  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d0e55  lea     rax, WPP_GLOBAL_Control
0x1800d0e5c  cmp     rcx, rax
0x1800d0e5f  jz      short loc_1800D0E7F
0x1800d0e61  test    byte ptr [rcx+1Ch], 1
0x1800d0e65  jz      short loc_1800D0E7F
0x1800d0e67  mov     rcx, [rcx+10h]
0x1800d0e6b  lea     r8, WPP_154eeafd5d0d31ef67e6778b817bc92a_Traceguids
0x1800d0e72  mov     edx, 17h
0x1800d0e77  mov     r9d, esi
0x1800d0e7a  call    WPP_SF_d
0x1800d0e7f  test    rdi, rdi
0x1800d0e82  jz      short loc_1800D0E8D
0x1800d0e84  mov     rcx, rdi; hKey
0x1800d0e87  call    cs:__imp_RegCloseKey
0x1800d0e8d  mov     rcx, [rbp+hKey]; hKey
0x1800d0e91  test    rcx, rcx
0x1800d0e94  jz      short loc_1800D0E9C
0x1800d0e96  call    cs:__imp_RegCloseKey
0x1800d0e9c  mov     rcx, [rbp+phkResult]; hKey
0x1800d0ea0  test    rcx, rcx
0x1800d0ea3  jz      short loc_1800D0EAB
0x1800d0ea5  call    cs:__imp_RegCloseKey
0x1800d0eab  test    rbx, rbx
0x1800d0eae  jz      short loc_1800D0EB8
0x1800d0eb0  mov     rcx, rbx; void *
0x1800d0eb3  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800d0eb8  mov     eax, esi
0x1800d0eba  jmp     loc_1800D10CD
0x1800d0ebf  test    rdi, rdi
0x1800d0ec2  jz      short loc_1800D0ECD
0x1800d0ec4  mov     rcx, rdi; hKey
0x1800d0ec7  call    cs:__imp_RegCloseKey
0x1800d0ecd  mov     rcx, [rbp+hKey]; hKey
0x1800d0ed1  test    rcx, rcx
0x1800d0ed4  jz      short loc_1800D0EDC
0x1800d0ed6  call    cs:__imp_RegCloseKey
0x1800d0edc  mov     rcx, [rbp+phkResult]; hKey
0x1800d0ee0  test    rcx, rcx
0x1800d0ee3  jz      short loc_1800D0EEB
0x1800d0ee5  call    cs:__imp_RegCloseKey
0x1800d0eeb  test    rbx, rbx
0x1800d0eee  jz      loc_1800D10CB
0x1800d0ef4  mov     rcx, rbx; void *
0x1800d0ef7  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800d0efc  jmp     loc_1800D10CB
0x1800d0f01  call    ?IsOSWcos@ShieldProvider@@YA_NXZ; ShieldProvider::IsOSWcos(void)
0x1800d0f06  test    al, al
0x1800d0f08  jz      loc_1800D0F90
0x1800d0f0e  lea     rcx, [rbp+arg_10]; this
0x1800d0f12  mov     byte ptr [rbp+arg_10], r14b
0x1800d0f16  call    ?GetIsDevMode@ShieldProvider@@YAJPEA_N@Z; ShieldProvider::GetIsDevMode(bool *)
0x1800d0f1b  mov     ebx, eax
0x1800d0f1d  test    eax, eax
0x1800d0f1f  jns     short loc_1800D0F4C
0x1800d0f21  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d0f28  lea     rax, WPP_GLOBAL_Control
0x1800d0f2f  cmp     rcx, rax
0x1800d0f32  jz      loc_1800D0C6F
0x1800d0f38  test    byte ptr [rcx+1Ch], 1
0x1800d0f3c  jz      loc_1800D0C6F
0x1800d0f42  mov     edx, 18h
0x1800d0f47  jmp     loc_1800D0C5C
0x1800d0f4c  mov     cl, byte ptr [rbp+arg_10]; this
0x1800d0f4f  lea     rdx, aSecurityhealth_4; "SecurityHealthHost.exe"
0x1800d0f56  call    ?ValidateCaller@ShieldProvider@@YAJ_NPEAG@Z; ShieldProvider::ValidateCaller(bool,ushort *)
0x1800d0f5b  mov     ebx, eax
0x1800d0f5d  test    eax, eax
0x1800d0f5f  jns     loc_1800D1096
0x1800d0f65  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d0f6c  lea     rax, WPP_GLOBAL_Control
0x1800d0f73  cmp     rcx, rax
0x1800d0f76  jz      loc_1800D0C6F
0x1800d0f7c  test    byte ptr [rcx+1Ch], 1
0x1800d0f80  jz      loc_1800D0C6F
0x1800d0f86  mov     edx, 19h
0x1800d0f8b  jmp     loc_1800D0C5C
0x1800d0f90  mov     [rbp+phkResult], r14
0x1800d0f94  call    cs:__imp_GetCurrentThread
0x1800d0f9a  xor     r8d, r8d; OpenAsSelf
0x1800d0f9d  lea     r9, [rbp+phkResult]; TokenHandle
0x1800d0fa1  mov     rcx, rax; ThreadHandle
0x1800d0fa4  lea     edx, [r8+8]; DesiredAccess
0x1800d0fa8  call    cs:__imp_OpenThreadToken
0x1800d0fae  test    eax, eax
0x1800d0fb0  jnz     short loc_1800D0FFC
0x1800d0fb2  call    cs:__imp_GetLastError
0x1800d0fb8  mov     ebx, eax
0x1800d0fba  test    eax, eax
0x1800d0fbc  jle     short loc_1800D0FC7
0x1800d0fbe  movzx   ebx, ax
0x1800d0fc1  or      ebx, 80070000h
0x1800d0fc7  test    ebx, ebx
0x1800d0fc9  jns     short loc_1800D0FFC
0x1800d0fcb  test    sil, sil
0x1800d0fce  jz      short loc_1800D0FDC
0x1800d0fd0  cmp     ebx, 800703F0h
0x1800d0fd6  jz      loc_1800D1087
0x1800d0fdc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d0fe3  lea     rax, WPP_GLOBAL_Control
0x1800d0fea  cmp     rcx, rax
0x1800d0fed  jz      short loc_1800D1044
0x1800d0fef  test    byte ptr [rcx+1Ch], 1
0x1800d0ff3  jz      short loc_1800D1044
0x1800d0ff5  mov     edx, 1Ch
0x1800d0ffa  jmp     short loc_1800D1031
0x1800d0ffc  mov     rdx, [rbp+phkResult]; bool *
0x1800d1000  lea     rcx, [rbp+arg_10]; this
0x1800d1004  mov     byte ptr [rbp+arg_10], r14b
0x1800d1008  call    ?UtilCheckTokenMembershipByRid@CommonUtil@@YAJPEA_NPEAXKK@Z; CommonUtil::UtilCheckTokenMembershipByRid(bool *,void *,ulong,ulong)
0x1800d100d  mov     ebx, eax
0x1800d100f  test    eax, eax
0x1800d1011  jns     short loc_1800D105C
0x1800d1013  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d101a  lea     rax, WPP_GLOBAL_Control
0x1800d1021  cmp     rcx, rax
0x1800d1024  jz      short loc_1800D1044
0x1800d1026  test    byte ptr [rcx+1Ch], 1
0x1800d102a  jz      short loc_1800D1044
0x1800d102c  mov     edx, 1Ah
0x1800d1031  mov     rcx, [rcx+10h]
0x1800d1035  lea     r8, WPP_154eeafd5d0d31ef67e6778b817bc92a_Traceguids
0x1800d103c  mov     r9d, ebx
0x1800d103f  call    WPP_SF_d
0x1800d1044  mov     rcx, [rbp+phkResult]; hObject
0x1800d1048  test    rcx, rcx
0x1800d104b  jz      loc_1800D0C6F
0x1800d1051  call    cs:__imp_CloseHandle
0x1800d1057  jmp     loc_1800D0C6F
0x1800d105c  cmp     byte ptr [rbp+arg_10], r14b
0x1800d1060  jnz     short loc_1800D1087
0x1800d1062  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d1069  lea     rax, WPP_GLOBAL_Control
0x1800d1070  mov     ebx, 80070005h
0x1800d1075  cmp     rcx, rax
0x1800d1078  jz      short loc_1800D1044
0x1800d107a  test    byte ptr [rcx+1Ch], 1
0x1800d107e  jz      short loc_1800D1044
0x1800d1080  mov     edx, 1Bh
0x1800d1085  jmp     short loc_1800D1031
0x1800d1087  mov     rcx, [rbp+phkResult]; hObject
0x1800d108b  test    rcx, rcx
0x1800d108e  jz      short loc_1800D1096
0x1800d1090  call    cs:__imp_CloseHandle
0x1800d1096  mov     ecx, edi
0x1800d1098  call    ShieldProvider__GetIndexForDeviceWideWarningDismissalState
0x1800d109d  lea     rdx, ?g_aCSwarningStates@ShieldProvider@@3U?$CSimpleGlobalAtStartup2nd@VCMpCriticalSection@CommonUtil@@@CommonUtil@@A; CommonUtil::CSimpleGlobalAtStartup2nd<CommonUtil::CMpCriticalSection> ShieldProvider::g_aCSwarningStates
0x1800d10a4  mov     ebx, eax
0x1800d10a6  lea     rcx, [rbp+var_18]
0x1800d10aa  call    ??0?$CGenericAutoLock@UCMpCriticalSectionFunctor@CommonUtil@@@CommonUtil@@QEAA@AEBVCMpCriticalSection@1@W4ENUM_LOCK_INITIAL_STATE@01@@Z; CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>(CommonUtil::CMpCriticalSection const &,CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::ENUM_LOCK_INITIAL_STATE)
  ... truncated ...
```
