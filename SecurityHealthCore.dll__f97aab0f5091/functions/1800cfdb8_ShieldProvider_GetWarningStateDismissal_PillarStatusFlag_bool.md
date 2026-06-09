# ShieldProvider::GetWarningStateDismissal(PillarStatusFlag,bool *)

- ea: `0x1800cfdb8`
- end: `0x1800d00a6`
- name: `?GetWarningStateDismissal@ShieldProvider@@YAJW4PillarStatusFlag@@PEA_N@Z`
- size: `750`
- prototype: ``
- caller_count: `11`
- callee_count: `11`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x18002d1e8`
- `0x180036750`
- `0x18004fc58`
- `0x1800509f8`
- `0x180051800`
- `0x18006f6e0`
- `0x1800b0500`
- `0x1800c6610`
- `0x1800c8b44`
- `0x1800c9520`
- `0x1800d0180`

## callees

- `0x180004ae0`
- `0x18000d7fc`
- `0x18000f02c`
- `0x18000f094`
- `0x1800cf91c`
- `0x1800cfa28`
- `0x1800cfdb8`
- `0x1800d012c`
- `0x1800d015c`
- `0x1800dd3e8`
- `0x1800dd908`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800cfee2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800cff2a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800cff39`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800cff94`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800cffdd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800cffec`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800d0042`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800d0051`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800cfee2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800cff2a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800cff39`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800cff94`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800cffdd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800cffec`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800d0042`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800d0051`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x1800cfe8c`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x1800cfe8c`

## pseudocode

```c
__int64 __fastcall ShieldProvider::GetWarningStateDismissal(__int64 a1, _BYTE *a2)
{
  int NameForWarningState; // ebx
  __int64 v5; // rcx
  const struct std::nothrow_t *v6; // rdx
  LSTATUS v7; // eax
  unsigned int *v8; // r9
  HKEY v9; // rcx
  HKEY v10; // rcx
  HKEY v11; // rbx
  HKEY v12; // rdi
  int ValueDword; // r14d
  __int64 IndexForDeviceWideWarningDismissalState; // rbx
  struct _SECURITY_ATTRIBUTES *v15; // [rsp+28h] [rbp-28h]
  HKEY hKey; // [rsp+30h] [rbp-20h] BYREF
  _BYTE v17[24]; // [rsp+38h] [rbp-18h] BYREF
  int v18; // [rsp+88h] [rbp+38h] BYREF
  HKEY phkResult; // [rsp+90h] [rbp+40h] BYREF
  HKEY v20; // [rsp+98h] [rbp+48h] BYREF

  *a2 = 0;
  if ( !(unsigned __int8)ShieldProvider::IsValidWarningState() )
  {
    NameForWarningState = -2147024809;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 29, WPP_154eeafd5d0d31ef67e6778b817bc92a_Traceguids, 2147942487LL);
    return (unsigned int)NameForWarningState;
  }
  if ( !(unsigned __int8)ShieldProvider::IsPerUserWarningState() )
  {
    IndexForDeviceWideWarningDismissalState = (unsigned int)ShieldProvider::GetIndexForDeviceWideWarningDismissalState(v5);
    CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>(
      v17,
      ShieldProvider::g_aCSwarningStates);
    v17[16] = 0;
    *a2 = *((_BYTE *)qword_18013A630 + IndexForDeviceWideWarningDismissalState);
    CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::~CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>(v17);
    return 0;
  }
  v20 = 0;
  NameForWarningState = ShieldProvider::GetNameForWarningState(v5, &v20);
  if ( NameForWarningState < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
    {
      LOBYTE(v6) = 1;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          30,
          WPP_154eeafd5d0d31ef67e6778b817bc92a_Traceguids,
          (unsigned int)NameForWarningState);
    }
LABEL_11:
    if ( v20 )
      operator delete(v20, v6);
    return (unsigned int)NameForWarningState;
  }
  phkResult = 0;
  v7 = RegOpenCurrentUser(0x20019u, &phkResult);
  NameForWarningState = v7;
  if ( v7 )
  {
    if ( v7 > 0 )
      NameForWarningState = (unsigned __int16)v7 | 0x80070000;
    if ( NameForWarningState < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
      {
        LOBYTE(v6) = 1;
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            31,
            WPP_154eeafd5d0d31ef67e6778b817bc92a_Traceguids,
            (unsigned int)NameForWarningState);
      }
LABEL_20:
      if ( phkResult )
        RegCloseKey(phkResult);
      goto LABEL_11;
    }
  }
  hKey = 0;
  NameForWarningState = CommonUtil::UtilRegCreateKey(
                          (CommonUtil *)&hKey,
                          (HKEY *)phkResult,
                          (const WCHAR *)&stru_180104F50,
                          (const unsigned __int16 *)0x20019,
                          0,
                          v15);
  if ( NameForWarningState == -2147024894 )
  {
    v9 = hKey;
    *a2 = 0;
    if ( v9 )
      RegCloseKey(v9);
    if ( phkResult )
      RegCloseKey(phkResult);
    v10 = v20;
    if ( !v20 )
      return 0;
    goto LABEL_45;
  }
  if ( NameForWarningState < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
    {
      LOBYTE(v6) = 1;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          32,
          WPP_154eeafd5d0d31ef67e6778b817bc92a_Traceguids,
          (unsigned int)NameForWarningState);
    }
    if ( hKey )
      RegCloseKey(hKey);
    goto LABEL_20;
  }
  v11 = v20;
  v12 = hKey;
  v18 = 0;
  ValueDword = CommonUtil::UtilRegGetValueDword((CommonUtil *)hKey, v20, (const unsigned __int16 *)&v18, v8);
  if ( ValueDword >= 0 )
  {
    LOBYTE(v6) = 1;
LABEL_39:
    *a2 = (_BYTE)v6;
    if ( v12 )
      RegCloseKey(v12);
    if ( phkResult )
      RegCloseKey(phkResult);
    if ( !v11 )
      return 0;
    v10 = v11;
LABEL_45:
    operator delete(v10, v6);
    return 0;
  }
  if ( ValueDword == -2147024894 )
  {
    LOBYTE(v6) = 0;
    goto LABEL_39;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    LOBYTE(v6) = 1;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        33,
        WPP_154eeafd5d0d31ef67e6778b817bc92a_Traceguids,
        (unsigned int)ValueDword);
  }
  if ( v12 )
    RegCloseKey(v12);
  if ( phkResult )
    RegCloseKey(phkResult);
  if ( v11 )
    operator delete(v11, v6);
  return (unsigned int)ValueDword;
}

```

## disassembly

```asm
0x1800cfdb8  push    rbp
0x1800cfdba  push    rbx
0x1800cfdbb  push    rsi
0x1800cfdbc  push    rdi
0x1800cfdbd  push    r14
0x1800cfdbf  mov     rbp, rsp
0x1800cfdc2  sub     rsp, 50h
0x1800cfdc6  mov     rsi, rdx
0x1800cfdc9  mov     byte ptr [rdx], 0
0x1800cfdcc  call    ?IsValidWarningState@ShieldProvider@@YA_NW4PillarStatusFlag@@@Z; ShieldProvider::IsValidWarningState(PillarStatusFlag)
0x1800cfdd1  test    al, al
0x1800cfdd3  jnz     short loc_1800CFE13
0x1800cfdd5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800cfddc  lea     rax, WPP_GLOBAL_Control
0x1800cfde3  mov     ebx, 80070057h
0x1800cfde8  cmp     rcx, rax
0x1800cfdeb  jz      short loc_1800CFE0C
0x1800cfded  mov     dl, 1
0x1800cfdef  test    [rcx+1Ch], dl
0x1800cfdf2  jz      short loc_1800CFE0C
0x1800cfdf4  mov     rcx, [rcx+10h]
0x1800cfdf8  lea     r8, WPP_154eeafd5d0d31ef67e6778b817bc92a_Traceguids
0x1800cfdff  mov     edx, 1Dh
0x1800cfe04  mov     r9d, ebx
0x1800cfe07  call    WPP_SF_d
0x1800cfe0c  mov     eax, ebx
0x1800cfe0e  jmp     loc_1800D009B
0x1800cfe13  call    ?IsPerUserWarningState@ShieldProvider@@YA_NW4PillarStatusFlag@@@Z; ShieldProvider::IsPerUserWarningState(PillarStatusFlag)
0x1800cfe18  test    al, al
0x1800cfe1a  jz      loc_1800D0069
0x1800cfe20  lea     rdx, [rbp+arg_18]
0x1800cfe24  mov     [rbp+arg_18], 0
0x1800cfe2c  call    ShieldProvider__GetNameForWarningState
0x1800cfe31  mov     ebx, eax
0x1800cfe33  test    eax, eax
0x1800cfe35  jns     short loc_1800CFE79
0x1800cfe37  mov     rcx, cs:WPP_GLOBAL_Control
0x1800cfe3e  lea     rax, WPP_GLOBAL_Control
0x1800cfe45  cmp     rcx, rax
0x1800cfe48  jz      short loc_1800CFE69
0x1800cfe4a  mov     dl, 1
0x1800cfe4c  test    [rcx+1Ch], dl
0x1800cfe4f  jz      short loc_1800CFE69
0x1800cfe51  mov     rcx, [rcx+10h]
0x1800cfe55  lea     r8, WPP_154eeafd5d0d31ef67e6778b817bc92a_Traceguids
0x1800cfe5c  mov     edx, 1Eh
0x1800cfe61  mov     r9d, ebx
0x1800cfe64  call    WPP_SF_d
0x1800cfe69  mov     rcx, [rbp+arg_18]; void *
0x1800cfe6d  test    rcx, rcx
0x1800cfe70  jz      short loc_1800CFE0C
0x1800cfe72  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800cfe77  jmp     short loc_1800CFE0C
0x1800cfe79  mov     edi, 20019h
0x1800cfe7e  mov     [rbp+phkResult], 0
0x1800cfe86  mov     ecx, edi; samDesired
0x1800cfe88  lea     rdx, [rbp+phkResult]; phkResult
0x1800cfe8c  call    cs:__imp_RegOpenCurrentUser
0x1800cfe92  mov     ebx, eax
0x1800cfe94  test    eax, eax
0x1800cfe96  jz      short loc_1800CFEED
0x1800cfe98  jle     short loc_1800CFEA3
0x1800cfe9a  movzx   ebx, ax
0x1800cfe9d  or      ebx, 80070000h
0x1800cfea3  test    ebx, ebx
0x1800cfea5  jns     short loc_1800CFEED
0x1800cfea7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800cfeae  lea     rax, WPP_GLOBAL_Control
0x1800cfeb5  cmp     rcx, rax
0x1800cfeb8  jz      short loc_1800CFED9
0x1800cfeba  mov     dl, 1
0x1800cfebc  test    [rcx+1Ch], dl
0x1800cfebf  jz      short loc_1800CFED9
0x1800cfec1  mov     rcx, [rcx+10h]
0x1800cfec5  lea     r8, WPP_154eeafd5d0d31ef67e6778b817bc92a_Traceguids
0x1800cfecc  mov     edx, 1Fh
0x1800cfed1  mov     r9d, ebx
0x1800cfed4  call    WPP_SF_d
0x1800cfed9  mov     rcx, [rbp+phkResult]; hKey
0x1800cfedd  test    rcx, rcx
0x1800cfee0  jz      short loc_1800CFE69
0x1800cfee2  call    cs:__imp_RegCloseKey
0x1800cfee8  jmp     loc_1800CFE69
0x1800cfeed  mov     rdx, [rbp+phkResult]; HKEY *
0x1800cfef1  lea     r8, stru_180104F50; HKEY
0x1800cfef8  mov     r9d, edi; unsigned __int16 *
0x1800cfefb  mov     [rbp+hKey], 0
0x1800cff03  lea     rcx, [rbp+hKey]; this
0x1800cff07  mov     qword ptr [rsp+50h+var_30], 0; unsigned int
0x1800cff10  call    ?UtilRegCreateKey@CommonUtil@@YAJPEAPEAUHKEY__@@PEAU2@PEBGKPEAU_SECURITY_ATTRIBUTES@@K@Z; CommonUtil::UtilRegCreateKey(HKEY__ * *,HKEY__ *,ushort const *,ulong,_SECURITY_ATTRIBUTES *,ulong)
0x1800cff15  mov     ebx, eax
0x1800cff17  cmp     eax, 80070002h
0x1800cff1c  jnz     short loc_1800CFF51
0x1800cff1e  mov     rcx, [rbp+hKey]; hKey
0x1800cff22  mov     byte ptr [rsi], 0
0x1800cff25  test    rcx, rcx
0x1800cff28  jz      short loc_1800CFF30
0x1800cff2a  call    cs:__imp_RegCloseKey
0x1800cff30  mov     rcx, [rbp+phkResult]; hKey
0x1800cff34  test    rcx, rcx
0x1800cff37  jz      short loc_1800CFF3F
0x1800cff39  call    cs:__imp_RegCloseKey
0x1800cff3f  mov     rcx, [rbp+arg_18]
0x1800cff43  test    rcx, rcx
0x1800cff46  jz      loc_1800D0099
0x1800cff4c  jmp     loc_1800CFFFE
0x1800cff51  test    ebx, ebx
0x1800cff53  jns     short loc_1800CFF9F
0x1800cff55  mov     rcx, cs:WPP_GLOBAL_Control
0x1800cff5c  lea     rax, WPP_GLOBAL_Control
0x1800cff63  cmp     rcx, rax
0x1800cff66  jz      short loc_1800CFF87
0x1800cff68  mov     dl, 1
0x1800cff6a  test    [rcx+1Ch], dl
0x1800cff6d  jz      short loc_1800CFF87
0x1800cff6f  mov     rcx, [rcx+10h]
0x1800cff73  lea     r8, WPP_154eeafd5d0d31ef67e6778b817bc92a_Traceguids
0x1800cff7a  mov     edx, 20h ; ' '
0x1800cff7f  mov     r9d, ebx
0x1800cff82  call    WPP_SF_d
0x1800cff87  mov     rcx, [rbp+hKey]; hKey
0x1800cff8b  test    rcx, rcx
0x1800cff8e  jz      loc_1800CFED9
0x1800cff94  call    cs:__imp_RegCloseKey
0x1800cff9a  jmp     loc_1800CFED9
0x1800cff9f  mov     rbx, [rbp+arg_18]
0x1800cffa3  lea     r8, [rbp+arg_8]; unsigned __int16 *
0x1800cffa7  mov     rdi, [rbp+hKey]
0x1800cffab  mov     rdx, rbx; HKEY
0x1800cffae  mov     rcx, rdi; this
0x1800cffb1  mov     [rbp+arg_8], 0
0x1800cffb8  call    ?UtilRegGetValueDword@CommonUtil@@YAJPEAUHKEY__@@PEBGPEAK@Z; CommonUtil::UtilRegGetValueDword(HKEY__ *,ushort const *,ulong *)
0x1800cffbd  mov     r14d, eax
0x1800cffc0  test    eax, eax
0x1800cffc2  js      short loc_1800CFFC8
0x1800cffc4  mov     dl, 1
0x1800cffc6  jmp     short loc_1800CFFD3
0x1800cffc8  cmp     r14d, 80070002h
0x1800cffcf  jnz     short loc_1800D0008
0x1800cffd1  xor     dl, dl
0x1800cffd3  mov     [rsi], dl
0x1800cffd5  test    rdi, rdi
0x1800cffd8  jz      short loc_1800CFFE3
0x1800cffda  mov     rcx, rdi; hKey
0x1800cffdd  call    cs:__imp_RegCloseKey
0x1800cffe3  mov     rcx, [rbp+phkResult]; hKey
0x1800cffe7  test    rcx, rcx
0x1800cffea  jz      short loc_1800CFFF2
0x1800cffec  call    cs:__imp_RegCloseKey
0x1800cfff2  test    rbx, rbx
0x1800cfff5  jz      loc_1800D0099
0x1800cfffb  mov     rcx, rbx; void *
0x1800cfffe  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800d0003  jmp     loc_1800D0099
0x1800d0008  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d000f  lea     rax, WPP_GLOBAL_Control
0x1800d0016  cmp     rcx, rax
0x1800d0019  jz      short loc_1800D003A
0x1800d001b  mov     dl, 1
0x1800d001d  test    [rcx+1Ch], dl
0x1800d0020  jz      short loc_1800D003A
0x1800d0022  mov     rcx, [rcx+10h]
0x1800d0026  lea     r8, WPP_154eeafd5d0d31ef67e6778b817bc92a_Traceguids
0x1800d002d  mov     edx, 21h ; '!'
0x1800d0032  mov     r9d, r14d
0x1800d0035  call    WPP_SF_d
0x1800d003a  test    rdi, rdi
0x1800d003d  jz      short loc_1800D0048
0x1800d003f  mov     rcx, rdi; hKey
0x1800d0042  call    cs:__imp_RegCloseKey
0x1800d0048  mov     rcx, [rbp+phkResult]; hKey
0x1800d004c  test    rcx, rcx
0x1800d004f  jz      short loc_1800D0057
0x1800d0051  call    cs:__imp_RegCloseKey
0x1800d0057  test    rbx, rbx
0x1800d005a  jz      short loc_1800D0064
0x1800d005c  mov     rcx, rbx; void *
0x1800d005f  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800d0064  mov     eax, r14d
0x1800d0067  jmp     short loc_1800D009B
0x1800d0069  call    ShieldProvider__GetIndexForDeviceWideWarningDismissalState
0x1800d006e  lea     rdx, ?g_aCSwarningStates@ShieldProvider@@3U?$CSimpleGlobalAtStartup2nd@VCMpCriticalSection@CommonUtil@@@CommonUtil@@A; CommonUtil::CSimpleGlobalAtStartup2nd<CommonUtil::CMpCriticalSection> ShieldProvider::g_aCSwarningStates
0x1800d0075  mov     ebx, eax
0x1800d0077  lea     rcx, [rbp+var_18]
0x1800d007b  call    ??0?$CGenericAutoLock@UCMpCriticalSectionFunctor@CommonUtil@@@CommonUtil@@QEAA@AEBVCMpCriticalSection@1@W4ENUM_LOCK_INITIAL_STATE@01@@Z; CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>(CommonUtil::CMpCriticalSection const &,CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::ENUM_LOCK_INITIAL_STATE)
0x1800d0080  lea     rcx, qword_18013A630
0x1800d0087  mov     [rbp+var_8], 0
0x1800d008b  mov     al, [rbx+rcx]
0x1800d008e  lea     rcx, [rbp+var_18]
0x1800d0092  mov     [rsi], al
0x1800d0094  call    ??1?$CGenericAutoLock@UCMpCriticalSectionFunctor@CommonUtil@@@CommonUtil@@QEAA@XZ; CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::~CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>(void)
0x1800d0099  xor     eax, eax
0x1800d009b  add     rsp, 50h
0x1800d009f  pop     r14
0x1800d00a1  pop     rdi
0x1800d00a2  pop     rsi
0x1800d00a3  pop     rbx
0x1800d00a4  pop     rbp
0x1800d00a5  retn
```
