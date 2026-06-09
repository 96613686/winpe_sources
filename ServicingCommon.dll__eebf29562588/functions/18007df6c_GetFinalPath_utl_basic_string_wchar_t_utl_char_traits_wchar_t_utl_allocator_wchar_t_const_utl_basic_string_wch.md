# GetFinalPath(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const &,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &)

- ea: `0x18007df6c`
- end: `0x18007e3ec`
- name: `?GetFinalPath@@YAJAEBV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@AEAV12@@Z`
- size: `1152`
- prototype: ``
- caller_count: `1`
- callee_count: `17`
- tags: `file_ops, reparse_path, authz_impersonation, registry_config, installer_update`

## callers

- `0x18007f540`

## callees

- `0x18000ea3c`
- `0x18001f4ac`
- `0x18001f5d4`
- `0x18001fd10`
- `0x1800293a0`
- `0x18002cc98`
- `0x180044bcc`
- `0x18006c360`
- `0x18007d998`
- `0x18007dab4`
- `0x18007db54`
- `0x18007df6c`
- `0x18007e720`
- `0x18007ef14`
- `0x18007eff0`
- `0x18007f018`
- `0x18007f214`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18007e104`
- `KERNEL32!GetLastError` at `0x18007e161`
- `KERNEL32!GetLastError` at `0x18007e1de`
- `KERNEL32!GetLastError` at `0x18007e1f5`
- `KERNEL32!GetLastError` at `0x18007e2aa`
- `KERNEL32!GetLastError` at `0x18007e306`
- `KERNEL32!GetLastError` at `0x18007e104`
- `KERNEL32!GetLastError` at `0x18007e161`
- `KERNEL32!GetLastError` at `0x18007e1de`
- `KERNEL32!GetLastError` at `0x18007e1f5`
- `KERNEL32!GetLastError` at `0x18007e2aa`
- `KERNEL32!GetLastError` at `0x18007e306`
- `KERNEL32!CreateFileW` at `0x18007e0d6`
- `KERNEL32!CreateFileW` at `0x18007e0d6`
- `KERNEL32!GetFinalPathNameByHandleW` at `0x18007e1cc`
- `KERNEL32!GetFinalPathNameByHandleW` at `0x18007e29a`
- `KERNEL32!GetFinalPathNameByHandleW` at `0x18007e1cc`
- `KERNEL32!GetFinalPathNameByHandleW` at `0x18007e29a`

## string_xrefs

- `0x18007dfc9`: `onecore\base\servicing\overlayutil\mount.cpp`
- `0x18007e028`: `onecore\base\servicing\overlayutil\mount.cpp`
- `0x18007e12f`: `onecore\base\servicing\overlayutil\mount.cpp`
- `0x18007e17d`: `onecore\base\servicing\overlayutil\mount.cpp`
- `0x18007e211`: `onecore\base\servicing\overlayutil\mount.cpp`
- `0x18007e25c`: `onecore\base\servicing\overlayutil\mount.cpp`
- `0x18007e2c7`: `onecore\base\servicing\overlayutil\mount.cpp`
- `0x18007e32b`: `onecore\base\servicing\overlayutil\mount.cpp`
- `0x18007dfde`: `Path.length() > 0`
- `0x18007dfe5`: `GetFinalPath`
- `0x18007e044`: `GetFinalPath`
- `0x18007e149`: `GetFinalPath`
- `0x18007e188`: `GetFinalPath`
- `0x18007e21c`: `GetFinalPath`
- `0x18007e276`: `GetFinalPath`
- `0x18007e2d2`: `GetFinalPath`
- `0x18007e345`: `GetFinalPath`
- `0x18007e03d`: `TempPath.resize(NewLength)`
- `0x18007e142`: `TempPath.assign(Path)`
- `0x18007e227`: `ReqPathLength != 0`
- `0x18007e2dd`: `ReqPathLength != 0`
- `0x18007e33e`: `FinalPath.assign(LocalFinalPath.get())`
- `0x18007e26f`: `LocalFinalPath`

## pseudocode

```c
__int64 __fastcall GetFinalPath(_QWORD *a1, __int64 a2)
{
  __int64 v4; // r8
  int v5; // eax
  __int64 v6; // r8
  size_t v7; // rbx
  _QWORD *v8; // rdx
  int v9; // ebx
  HANDLE FileW; // rax
  HANDLE v11; // rdi
  signed int LastError; // eax
  _QWORD *v13; // rdx
  DWORD FinalPathNameByHandleW; // eax
  DWORD v15; // esi
  LPWSTR v16; // rbx
  _QWORD *v17; // rdx
  signed int v18; // eax
  int v19; // eax
  const struct std::nothrow_t *v20; // rdx
  const struct std::nothrow_t *v21; // rdx
  HANDLE hFile; // [rsp+40h] [rbp-C0h] BYREF
  _QWORD v24[4]; // [rsp+48h] [rbp-B8h] BYREF
  _QWORD v25[4]; // [rsp+68h] [rbp-98h] BYREF
  _QWORD v26[4]; // [rsp+88h] [rbp-78h] BYREF
  _QWORD v27[4]; // [rsp+A8h] [rbp-58h] BYREF
  _QWORD v28[4]; // [rsp+C8h] [rbp-38h] BYREF
  _QWORD v29[4]; // [rsp+E8h] [rbp-18h] BYREF
  _QWORD v30[4]; // [rsp+108h] [rbp+8h] BYREF
  _QWORD v31[4]; // [rsp+128h] [rbp+28h] BYREF
  int v32; // [rsp+148h] [rbp+48h] BYREF
  LPWSTR lpszFilePath; // [rsp+150h] [rbp+50h] BYREF
  __int64 v34; // [rsp+158h] [rbp+58h] BYREF
  char v35; // [rsp+160h] [rbp+60h]
  wchar_t *Buffer[2]; // [rsp+168h] [rbp+68h] BYREF
  _WORD v37[8]; // [rsp+178h] [rbp+78h] BYREF

  v32 = 0;
  Buffer[0] = v37;
  Buffer[1] = v37;
  v37[0] = 0;
  v4 = a1[1] - *a1;
  if ( !v4 )
  {
    v24[2] = 24;
    v24[0] = "onecore\\base\\servicing\\overlayutil\\mount.cpp";
    v24[3] = "Path.length() > 0";
    v24[1] = "GetFinalPath";
    v5 = Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateInvalidParameter_NullPointer(
           &v32,
           v24);
LABEL_7:
    v9 = v5;
LABEL_43:
    utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::_Uninit((void **)Buffer);
    return (unsigned int)v9;
  }
  v6 = v4 >> 1;
  if ( *(_WORD *)(a1[1] - 2LL) == 92 )
  {
    if ( !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(
                             Buffer,
                             *a1,
                             v6) )
    {
      v26[2] = 40;
      v26[0] = "onecore\\base\\servicing\\overlayutil\\mount.cpp";
      v26[3] = "TempPath.assign(Path)";
      v26[1] = "GetFinalPath";
      v8 = v26;
      goto LABEL_6;
    }
  }
  else
  {
    v7 = v6 + 2;
    if ( !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::resize(
                             Buffer,
                             v6 + 2) )
    {
      v25[2] = 30;
      v25[0] = "onecore\\base\\servicing\\overlayutil\\mount.cpp";
      v25[3] = "TempPath.resize(NewLength)";
      v25[1] = "GetFinalPath";
      v8 = v25;
LABEL_6:
      v5 = Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateNtStatus(
             &v32,
             v8,
             3221225495LL);
      goto LABEL_7;
    }
    swprintf_s(Buffer[0], v7, L"%ws\\", *a1);
  }
  v34 = 0;
  v35 = 0;
  v9 = RtlSystemUtil::BackupRestoreVolumePrivilegeAcquisition::Acquire((RtlSystemUtil::BackupRestoreVolumePrivilegeAcquisition *)&v34);
  if ( v9 < 0 )
  {
LABEL_42:
    RtlSystemUtil::PrivilegeAcquisition::~PrivilegeAcquisition((RtlSystemUtil::PrivilegeAcquisition *)&v34);
    goto LABEL_43;
  }
  hFile = 0;
  FileW = CreateFileW(Buffer[0], 0x80000000, 7u, 0, 3u, 0x2000000u, 0);
  Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&void Windows::Detail::CloseWithNtCloseHandle(void *)>>::TakeOwnership(
    &hFile,
    FileW);
  v11 = hFile;
  if ( (((unsigned __int64)hFile + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
  {
    if ( !GetLastError() )
    {
      LastError = 14077;
LABEL_16:
      v27[2] = 57;
      v27[0] = "onecore\\base\\servicing\\overlayutil\\mount.cpp";
      v27[1] = "GetFinalPath";
      v27[3] = "File.IsValid()";
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      v13 = v27;
LABEL_19:
      v9 = Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateHResult(
             &v32,
             v13,
             (unsigned int)LastError);
LABEL_41:
      Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&void Windows::Detail::CloseWithNtCloseHandle(void *)>>::Close(&hFile);
      goto LABEL_42;
    }
    LastError = GetLastError();
    if ( LastError )
      goto LABEL_16;
LABEL_45:
    INTERNAL_ERROR_ACTION(-1073741595);
    JUMPOUT(0x18007E3EBLL);
  }
  FinalPathNameByHandleW = GetFinalPathNameByHandleW(hFile, 0, 0, 0);
  v15 = FinalPathNameByHandleW;
  if ( !FinalPathNameByHandleW )
  {
    if ( GetLastError() )
    {
      LastError = GetLastError();
      if ( !LastError )
        goto LABEL_45;
    }
    else
    {
      LastError = 14077;
    }
    v28[2] = 61;
    v28[0] = "onecore\\base\\servicing\\overlayutil\\mount.cpp";
    v28[1] = "GetFinalPath";
    v28[3] = "ReqPathLength != 0";
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v13 = v28;
    goto LABEL_19;
  }
  utl::make_unique<wchar_t [0],0>(&lpszFilePath, FinalPathNameByHandleW);
  v16 = lpszFilePath;
  if ( !lpszFilePath )
  {
    v29[2] = 64;
    v29[0] = "onecore\\base\\servicing\\overlayutil\\mount.cpp";
    v29[3] = "LocalFinalPath";
    v29[1] = "GetFinalPath";
    v17 = v29;
LABEL_39:
    v19 = Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateNtStatus(
            &v32,
            v17,
            3221225495LL);
    goto LABEL_40;
  }
  if ( !GetFinalPathNameByHandleW(v11, lpszFilePath, v15, 0) )
  {
    if ( GetLastError() )
    {
      v18 = GetLastError();
      if ( !v18 )
        goto LABEL_45;
    }
    else
    {
      v18 = 14077;
    }
    v30[2] = 72;
    v30[0] = "onecore\\base\\servicing\\overlayutil\\mount.cpp";
    v30[1] = "GetFinalPath";
    v30[3] = "ReqPathLength != 0";
    if ( v18 > 0 )
      v18 = (unsigned __int16)v18 | 0x80070000;
    v19 = Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateHResult(
            &v32,
            v30,
            (unsigned int)v18);
LABEL_40:
    v9 = v19;
    utl::unique_ptr<OVERLAY_CIM_CONFIGURATION [0],utl::default_delete<OVERLAY_CIM_CONFIGURATION [0]>>::~unique_ptr<OVERLAY_CIM_CONFIGURATION [0],utl::default_delete<OVERLAY_CIM_CONFIGURATION [0]>>(
      (void **)&lpszFilePath,
      v20);
    goto LABEL_41;
  }
  if ( !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(a2, v16) )
  {
    v31[2] = 74;
    v31[0] = "onecore\\base\\servicing\\overlayutil\\mount.cpp";
    v31[3] = "FinalPath.assign(LocalFinalPath.get())";
    v31[1] = "GetFinalPath";
    v17 = v31;
    goto LABEL_39;
  }
  utl::unique_ptr<OVERLAY_CIM_CONFIGURATION [0],utl::default_delete<OVERLAY_CIM_CONFIGURATION [0]>>::~unique_ptr<OVERLAY_CIM_CONFIGURATION [0],utl::default_delete<OVERLAY_CIM_CONFIGURATION [0]>>(
    (void **)&lpszFilePath,
    v21);
  Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&void Windows::Detail::CloseWithNtCloseHandle(void *)>>::Close(&hFile);
  RtlSystemUtil::PrivilegeAcquisition::~PrivilegeAcquisition((RtlSystemUtil::PrivilegeAcquisition *)&v34);
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::_Uninit((void **)Buffer);
  return 0;
}

```

## disassembly

```asm
0x18007df6c  mov     [rsp-8+arg_10], rbx
0x18007df71  mov     [rsp-8+arg_18], rsi
0x18007df76  push    rbp
0x18007df77  push    rdi
0x18007df78  push    r14
0x18007df7a  lea     rbp, [rsp-90h]
0x18007df82  sub     rsp, 190h
0x18007df89  mov     rax, cs:__security_cookie
0x18007df90  xor     rax, rsp
0x18007df93  mov     [rbp+0A0h+var_18], rax
0x18007df9a  lea     rax, [rbp+0A0h+var_28]
0x18007df9e  mov     [rbp+0A0h+var_58], 0
0x18007dfa5  mov     [rbp+0A0h+Buffer], rax
0x18007dfa9  mov     r14, rdx
0x18007dfac  lea     rax, [rbp+0A0h+var_28]
0x18007dfb0  mov     rdi, rcx
0x18007dfb3  mov     [rbp+0A0h+var_30], rax
0x18007dfb7  xor     eax, eax
0x18007dfb9  mov     [rbp+0A0h+var_28], ax
0x18007dfbd  mov     rax, [rcx+8]
0x18007dfc1  mov     r8, rax
0x18007dfc4  sub     r8, [rcx]
0x18007dfc7  jnz     short loc_18007E006
0x18007dfc9  lea     rcx, aOnecoreBaseSer_0; "onecore\\base\\servicing\\overlayutil\\"...
0x18007dfd0  mov     [rsp+1A0h+var_148], 18h
0x18007dfd9  mov     [rsp+1A0h+var_158], rcx
0x18007dfde  lea     rax, aPathLength0; "Path.length() > 0"
0x18007dfe5  lea     rcx, aGetfinalpath; "GetFinalPath"
0x18007dfec  mov     [rsp+1A0h+var_140], rax
0x18007dff1  mov     [rsp+1A0h+var_150], rcx
0x18007dff6  lea     rdx, [rsp+1A0h+var_158]
0x18007dffb  lea     rcx, [rbp+0A0h+var_58]
0x18007dfff  call    ?OriginateInvalidParameter_NullPointer@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateInvalidParameter_NullPointer(Windows::ErrorHandling::_RTL_CALL_SITE const &)
0x18007e004  jmp     short loc_18007E068
0x18007e006  sar     r8, 1
0x18007e009  cmp     word ptr [rax-2], 5Ch ; '\'
0x18007e00e  jz      loc_18007E11B
0x18007e014  lea     rbx, [r8+2]
0x18007e018  mov     rdx, rbx
0x18007e01b  lea     rcx, [rbp+0A0h+Buffer]
0x18007e01f  call    ?resize@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_N_K_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::resize(unsigned __int64,wchar_t)
0x18007e024  test    al, al
0x18007e026  jnz     short loc_18007E06F
0x18007e028  lea     rcx, aOnecoreBaseSer_0; "onecore\\base\\servicing\\overlayutil\\"...
0x18007e02f  mov     [rsp+1A0h+var_128], 1Eh
0x18007e038  mov     [rsp+1A0h+var_138], rcx
0x18007e03d  lea     rax, aTemppathResize; "TempPath.resize(NewLength)"
0x18007e044  lea     rcx, aGetfinalpath; "GetFinalPath"
0x18007e04b  mov     [rbp+0A0h+var_120], rax
0x18007e04f  mov     [rsp+1A0h+var_130], rcx
0x18007e054  lea     rdx, [rsp+1A0h+var_138]
0x18007e059  mov     r8d, 0C0000017h
0x18007e05f  lea     rcx, [rbp+0A0h+var_58]
0x18007e063  call    ?OriginateNtStatus@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@J@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateNtStatus(Windows::ErrorHandling::_RTL_CALL_SITE const &,long)
0x18007e068  mov     ebx, eax
0x18007e06a  jmp     loc_18007E385
0x18007e06f  mov     r9, [rdi]
0x18007e072  lea     r8, aWs_0; "%ws\\"
0x18007e079  mov     rcx, [rbp+0A0h+Buffer]; Buffer
0x18007e07d  mov     rdx, rbx; BufferCount
0x18007e080  call    swprintf_s
0x18007e085  lea     rcx, [rbp+0A0h+var_48]; this
0x18007e089  mov     [rbp+0A0h+var_48], 0
0x18007e091  mov     [rbp+0A0h+var_40], 0
0x18007e095  call    ?Acquire@BackupRestoreVolumePrivilegeAcquisition@RtlSystemUtil@@QEAAJXZ; RtlSystemUtil::BackupRestoreVolumePrivilegeAcquisition::Acquire(void)
0x18007e09a  mov     ebx, eax
0x18007e09c  test    eax, eax
0x18007e09e  js      loc_18007E37C
0x18007e0a4  mov     rcx, [rbp+0A0h+Buffer]; lpFileName
0x18007e0a8  xor     r9d, r9d; lpSecurityAttributes
0x18007e0ab  mov     [rsp+1A0h+hTemplateFile], 0; hTemplateFile
0x18007e0b4  mov     edx, 80000000h; dwDesiredAccess
0x18007e0b9  mov     [rsp+1A0h+dwFlagsAndAttributes], 2000000h; dwFlagsAndAttributes
0x18007e0c1  mov     [rsp+1A0h+hFile], 0
0x18007e0ca  lea     r8d, [r9+7]; dwShareMode
0x18007e0ce  mov     [rsp+1A0h+dwCreationDisposition], 3; dwCreationDisposition
0x18007e0d6  call    cs:__imp_CreateFileW
0x18007e0dd  nop     dword ptr [rax+rax+00h]
0x18007e0e2  mov     rdx, rax
0x18007e0e5  lea     rcx, [rsp+1A0h+hFile]
0x18007e0ea  call    ?TakeOwnership@?$AutoGenericHandleBase@PEAX$00V?$AutoGenericHandle@PEAX$00$1?CloseWithNtCloseHandle@Detail@Windows@@YAXPEAX@Z@Windows@@@Windows@@QEAAXPEAX@Z; Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&Windows::Detail::CloseWithNtCloseHandle(void *)>>::TakeOwnership(void *)
0x18007e0ef  mov     rdi, [rsp+1A0h+hFile]
0x18007e0f4  lea     rax, [rdi+1]
0x18007e0f8  test    rax, 0FFFFFFFFFFFFFFFEh
0x18007e0fe  jnz     loc_18007E1C1
0x18007e104  call    cs:__imp_GetLastError
0x18007e10b  nop     dword ptr [rax+rax+00h]
0x18007e110  test    eax, eax
0x18007e112  jnz     short loc_18007E161
0x18007e114  mov     eax, 36FDh
0x18007e119  jmp     short loc_18007E175
0x18007e11b  mov     rdx, [rcx]
0x18007e11e  lea     rcx, [rbp+0A0h+Buffer]
0x18007e122  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(wchar_t const *,unsigned __int64)
0x18007e127  test    al, al
0x18007e129  jnz     loc_18007E085
0x18007e12f  lea     rcx, aOnecoreBaseSer_0; "onecore\\base\\servicing\\overlayutil\\"...
0x18007e136  mov     [rbp+0A0h+var_108], 28h ; '('
0x18007e13e  mov     [rbp+0A0h+var_118], rcx
0x18007e142  lea     rax, aTemppathAssign; "TempPath.assign(Path)"
0x18007e149  lea     rcx, aGetfinalpath; "GetFinalPath"
0x18007e150  mov     [rbp+0A0h+var_100], rax
0x18007e154  mov     [rbp+0A0h+var_110], rcx
0x18007e158  lea     rdx, [rbp+0A0h+var_118]
0x18007e15c  jmp     loc_18007E059
0x18007e161  call    cs:__imp_GetLastError
0x18007e168  nop     dword ptr [rax+rax+00h]
0x18007e16d  test    eax, eax
0x18007e16f  jz      loc_18007E3E1
0x18007e175  mov     [rbp+0A0h+var_E8], 39h ; '9'
0x18007e17d  lea     rcx, aOnecoreBaseSer_0; "onecore\\base\\servicing\\overlayutil\\"...
0x18007e184  mov     [rbp+0A0h+var_F8], rcx
0x18007e188  lea     rcx, aGetfinalpath; "GetFinalPath"
0x18007e18f  mov     [rbp+0A0h+var_F0], rcx
0x18007e193  lea     rcx, aFileIsvalid; "File.IsValid()"
0x18007e19a  mov     [rbp+0A0h+var_E0], rcx
0x18007e19e  test    eax, eax
0x18007e1a0  jle     short loc_18007E1AA
0x18007e1a2  movzx   eax, ax
0x18007e1a5  or      eax, 80070000h
0x18007e1aa  lea     rdx, [rbp+0A0h+var_F8]
0x18007e1ae  mov     r8d, eax
0x18007e1b1  lea     rcx, [rbp+0A0h+var_58]
0x18007e1b5  call    ?OriginateHResult@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@J@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateHResult(Windows::ErrorHandling::_RTL_CALL_SITE const &,long)
0x18007e1ba  mov     ebx, eax
0x18007e1bc  jmp     loc_18007E372
0x18007e1c1  xor     r9d, r9d; dwFlags
0x18007e1c4  xor     r8d, r8d; cchFilePath
0x18007e1c7  xor     edx, edx; lpszFilePath
0x18007e1c9  mov     rcx, rdi; hFile
0x18007e1cc  call    cs:__imp_GetFinalPathNameByHandleW
0x18007e1d3  nop     dword ptr [rax+rax+00h]
0x18007e1d8  mov     esi, eax
0x18007e1da  test    eax, eax
0x18007e1dc  jnz     short loc_18007E247
0x18007e1de  call    cs:__imp_GetLastError
0x18007e1e5  nop     dword ptr [rax+rax+00h]
0x18007e1ea  test    eax, eax
0x18007e1ec  jnz     short loc_18007E1F5
0x18007e1ee  mov     eax, 36FDh
0x18007e1f3  jmp     short loc_18007E209
0x18007e1f5  call    cs:__imp_GetLastError
0x18007e1fc  nop     dword ptr [rax+rax+00h]
0x18007e201  test    eax, eax
0x18007e203  jz      loc_18007E3E1
0x18007e209  mov     [rbp+0A0h+var_C8], 3Dh ; '='
0x18007e211  lea     rcx, aOnecoreBaseSer_0; "onecore\\base\\servicing\\overlayutil\\"...
0x18007e218  mov     [rbp+0A0h+var_D8], rcx
0x18007e21c  lea     rcx, aGetfinalpath; "GetFinalPath"
0x18007e223  mov     [rbp+0A0h+var_D0], rcx
0x18007e227  lea     rcx, aReqpathlength0; "ReqPathLength != 0"
0x18007e22e  mov     [rbp+0A0h+var_C0], rcx
0x18007e232  test    eax, eax
0x18007e234  jle     short loc_18007E23E
0x18007e236  movzx   eax, ax
0x18007e239  or      eax, 80070000h
0x18007e23e  lea     rdx, [rbp+0A0h+var_D8]
0x18007e242  jmp     loc_18007E1AE
0x18007e247  mov     rdx, rsi
0x18007e24a  lea     rcx, [rbp+0A0h+lpszFilePath]
0x18007e24e  call    ??$make_unique@$$BY0A@_W$0A@@utl@@YA?AV?$unique_ptr@$$BY0A@_WU?$default_delete@$$BY0A@_W@utl@@@0@_K@Z; utl::make_unique<wchar_t [0],0>(unsigned __int64)
0x18007e253  mov     rbx, [rbp+0A0h+lpszFilePath]
0x18007e257  test    rbx, rbx
0x18007e25a  jnz     short loc_18007E28E
0x18007e25c  lea     rcx, aOnecoreBaseSer_0; "onecore\\base\\servicing\\overlayutil\\"...
0x18007e263  mov     [rbp+0A0h+var_A8], 40h ; '@'
0x18007e26b  mov     [rbp+0A0h+var_B8], rcx
0x18007e26f  lea     rax, aLocalfinalpath; "LocalFinalPath"
0x18007e276  lea     rcx, aGetfinalpath; "GetFinalPath"
0x18007e27d  mov     [rbp+0A0h+var_A0], rax
0x18007e281  mov     [rbp+0A0h+var_B0], rcx
0x18007e285  lea     rdx, [rbp+0A0h+var_B8]
0x18007e289  jmp     loc_18007E358
0x18007e28e  xor     r9d, r9d; dwFlags
0x18007e291  mov     r8d, esi; cchFilePath
0x18007e294  mov     rdx, rbx; lpszFilePath
0x18007e297  mov     rcx, rdi; hFile
0x18007e29a  call    cs:__imp_GetFinalPathNameByHandleW
0x18007e2a1  nop     dword ptr [rax+rax+00h]
0x18007e2a6  test    eax, eax
0x18007e2a8  jnz     short loc_18007E31C
0x18007e2aa  call    cs:__imp_GetLastError
0x18007e2b1  nop     dword ptr [rax+rax+00h]
0x18007e2b6  test    eax, eax
0x18007e2b8  jnz     short loc_18007E306
0x18007e2ba  mov     eax, 36FDh
0x18007e2bf  mov     [rbp+0A0h+var_88], 48h ; 'H'
0x18007e2c7  lea     rcx, aOnecoreBaseSer_0; "onecore\\base\\servicing\\overlayutil\\"...
0x18007e2ce  mov     [rbp+0A0h+var_98], rcx
0x18007e2d2  lea     rcx, aGetfinalpath; "GetFinalPath"
0x18007e2d9  mov     [rbp+0A0h+var_90], rcx
0x18007e2dd  lea     rcx, aReqpathlength0; "ReqPathLength != 0"
0x18007e2e4  mov     [rbp+0A0h+var_80], rcx
0x18007e2e8  test    eax, eax
0x18007e2ea  jle     short loc_18007E2F4
0x18007e2ec  movzx   eax, ax
0x18007e2ef  or      eax, 80070000h
0x18007e2f4  mov     r8d, eax
0x18007e2f7  lea     rdx, [rbp+0A0h+var_98]
0x18007e2fb  lea     rcx, [rbp+0A0h+var_58]
0x18007e2ff  call    ?OriginateHResult@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@J@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateHResult(Windows::ErrorHandling::_RTL_CALL_SITE const &,long)
0x18007e304  jmp     short loc_18007E367
0x18007e306  call    cs:__imp_GetLastError
0x18007e30d  nop     dword ptr [rax+rax+00h]
0x18007e312  test    eax, eax
0x18007e314  jz      loc_18007E3E1
0x18007e31a  jmp     short loc_18007E2BF
0x18007e31c  mov     rdx, rbx
0x18007e31f  mov     rcx, r14
0x18007e322  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(wchar_t const *)
0x18007e327  test    al, al
0x18007e329  jnz     short loc_18007E392
0x18007e32b  lea     rcx, aOnecoreBaseSer_0; "onecore\\base\\servicing\\overlayutil\\"...
0x18007e332  mov     [rbp+0A0h+var_68], 4Ah ; 'J'
0x18007e33a  mov     [rbp+0A0h+var_78], rcx
0x18007e33e  lea     rax, aFinalpathAssig; "FinalPath.assign(LocalFinalPath.get())"
0x18007e345  lea     rcx, aGetfinalpath; "GetFinalPath"
0x18007e34c  mov     [rbp+0A0h+var_60], rax
0x18007e350  mov     [rbp+0A0h+var_70], rcx
0x18007e354  lea     rdx, [rbp+0A0h+var_78]
0x18007e358  mov     r8d, 0C0000017h
0x18007e35e  lea     rcx, [rbp+0A0h+var_58]
0x18007e362  call    ?OriginateNtStatus@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@J@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateNtStatus(Windows::ErrorHandling::_RTL_CALL_SITE const &,long)
0x18007e367  lea     rcx, [rbp+0A0h+lpszFilePath]
0x18007e36b  mov     ebx, eax
0x18007e36d  call    ??1?$unique_ptr@$$BY0A@UOVERLAY_CIM_CONFIGURATION@@U?$default_delete@$$BY0A@UOVERLAY_CIM_CONFIGURATION@@@utl@@@utl@@QEAA@XZ; utl::unique_ptr<OVERLAY_CIM_CONFIGURATION [0],utl::default_delete<OVERLAY_CIM_CONFIGURATION [0]>>::~unique_ptr<OVERLAY_CIM_CONFIGURATION [0],utl::default_delete<OVERLAY_CIM_CONFIGURATION [0]>>(void)
0x18007e372  lea     rcx, [rsp+1A0h+hFile]
0x18007e377  call    ?Close@?$AutoGenericHandleBase@PEAX$00V?$AutoGenericHandle@PEAX$00$1?CloseWithNtCloseHandle@Detail@Windows@@YAXPEAX@Z@Windows@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&Windows::Detail::CloseWithNtCloseHandle(void *)>>::Close(void)
0x18007e37c  lea     rcx, [rbp+0A0h+var_48]; this
0x18007e380  call    ??1PrivilegeAcquisition@RtlSystemUtil@@QEAA@XZ; RtlSystemUtil::PrivilegeAcquisition::~PrivilegeAcquisition(void)
0x18007e385  lea     rcx, [rbp+0A0h+Buffer]
0x18007e389  call    ?_Uninit@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@AEAAXXZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::_Uninit(void)
0x18007e38e  mov     eax, ebx
0x18007e390  jmp     short loc_18007E3B9
0x18007e392  lea     rcx, [rbp+0A0h+lpszFilePath]
0x18007e396  call    ??1?$unique_ptr@$$BY0A@UOVERLAY_CIM_CONFIGURATION@@U?$default_delete@$$BY0A@UOVERLAY_CIM_CONFIGURATION@@@utl@@@utl@@QEAA@XZ; utl::unique_ptr<OVERLAY_CIM_CONFIGURATION [0],utl::default_delete<OVERLAY_CIM_CONFIGURATION [0]>>::~unique_ptr<OVERLAY_CIM_CONFIGURATION [0],utl::default_delete<OVERLAY_CIM_CONFIGURATION [0]>>(void)
0x18007e39b  lea     rcx, [rsp+1A0h+hFile]
0x18007e3a0  call    ?Close@?$AutoGenericHandleBase@PEAX$00V?$AutoGenericHandle@PEAX$00$1?CloseWithNtCloseHandle@Detail@Windows@@YAXPEAX@Z@Windows@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&Windows::Detail::CloseWithNtCloseHandle(void *)>>::Close(void)
0x18007e3a5  lea     rcx, [rbp+0A0h+var_48]; this
0x18007e3a9  call    ??1PrivilegeAcquisition@RtlSystemUtil@@QEAA@XZ; RtlSystemUtil::PrivilegeAcquisition::~PrivilegeAcquisition(void)
0x18007e3ae  lea     rcx, [rbp+0A0h+Buffer]
0x18007e3b2  call    ?_Uninit@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@AEAAXXZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::_Uninit(void)
0x18007e3b7  xor     eax, eax
0x18007e3b9  mov     rcx, [rbp+0A0h+var_18]
0x18007e3c0  xor     rcx, rsp; StackCookie
0x18007e3c3  call    __security_check_cookie
0x18007e3c8  lea     r11, [rsp+1A0h+var_10]
0x18007e3d0  mov     rbx, [r11+30h]
0x18007e3d4  mov     rsi, [r11+38h]
0x18007e3d8  mov     rsp, r11
0x18007e3db  pop     r14
0x18007e3dd  pop     rdi
0x18007e3de  pop     rbp
0x18007e3df  retn
0x18007e3e1  mov     ecx, 0C00000E5h; int
0x18007e3e6  call    ?INTERNAL_ERROR_ACTION@@YAXJ@Z; INTERNAL_ERROR_ACTION(long)
```
