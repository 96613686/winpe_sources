# GetFinalPath(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const &,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &)

- ea: `0x18007cfe0`
- end: `0x18007d461`
- name: `?GetFinalPath@@YAJAEBV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@AEAV12@@Z`
- size: `1153`
- prototype: ``
- caller_count: `1`
- callee_count: `16`
- tags: `file_ops, reparse_path, authz_impersonation, registry_config, loader_planting, installer_update`

## callers

- `0x18007e5c0`

## callees

- `0x180018df0`
- `0x18001f1d8`
- `0x18001f840`
- `0x18002d2b0`
- `0x180030ba8`
- `0x180047d5c`
- `0x18006c244`
- `0x18007c9fc`
- `0x18007cb18`
- `0x18007cbb8`
- `0x18007cfe0`
- `0x18007d794`
- `0x18007df88`
- `0x18007e064`
- `0x18007e08c`
- `0x18007e288`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18007d178`
- `KERNEL32!GetLastError` at `0x18007d1d5`
- `KERNEL32!GetLastError` at `0x18007d252`
- `KERNEL32!GetLastError` at `0x18007d269`
- `KERNEL32!GetLastError` at `0x18007d31e`
- `KERNEL32!GetLastError` at `0x18007d37a`
- `KERNEL32!GetLastError` at `0x18007d178`
- `KERNEL32!GetLastError` at `0x18007d1d5`
- `KERNEL32!GetLastError` at `0x18007d252`
- `KERNEL32!GetLastError` at `0x18007d269`
- `KERNEL32!GetLastError` at `0x18007d31e`
- `KERNEL32!GetLastError` at `0x18007d37a`
- `KERNEL32!CreateFileW` at `0x18007d14a`
- `KERNEL32!CreateFileW` at `0x18007d14a`
- `KERNEL32!GetFinalPathNameByHandleW` at `0x18007d240`
- `KERNEL32!GetFinalPathNameByHandleW` at `0x18007d30e`
- `KERNEL32!GetFinalPathNameByHandleW` at `0x18007d240`
- `KERNEL32!GetFinalPathNameByHandleW` at `0x18007d30e`
- `ntdll!RtlRaiseStatus` at `0x18007d38f`
- `ntdll!RtlRaiseStatus` at `0x18007d38f`

## string_xrefs

- `0x18007d059`: `GetFinalPath`
- `0x18007d0b8`: `GetFinalPath`
- `0x18007d1bd`: `GetFinalPath`
- `0x18007d1fc`: `GetFinalPath`
- `0x18007d290`: `GetFinalPath`
- `0x18007d2ea`: `GetFinalPath`
- `0x18007d346`: `GetFinalPath`
- `0x18007d3c5`: `GetFinalPath`
- `0x18007d03d`: `onecore\base\servicing\overlayutil\mount.cpp`
- `0x18007d09c`: `onecore\base\servicing\overlayutil\mount.cpp`
- `0x18007d1a3`: `onecore\base\servicing\overlayutil\mount.cpp`
- `0x18007d1f1`: `onecore\base\servicing\overlayutil\mount.cpp`
- `0x18007d285`: `onecore\base\servicing\overlayutil\mount.cpp`
- `0x18007d2d0`: `onecore\base\servicing\overlayutil\mount.cpp`
- `0x18007d33b`: `onecore\base\servicing\overlayutil\mount.cpp`
- `0x18007d3ab`: `onecore\base\servicing\overlayutil\mount.cpp`
- `0x18007d0b1`: `TempPath.resize(NewLength)`
- `0x18007d052`: `Path.length() > 0`
- `0x18007d1b6`: `TempPath.assign(Path)`
- `0x18007d2e3`: `LocalFinalPath`
- `0x18007d29b`: `ReqPathLength != 0`
- `0x18007d351`: `ReqPathLength != 0`
- `0x18007d3be`: `FinalPath.assign(LocalFinalPath.get())`

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
  HANDLE hFile; // [rsp+40h] [rbp-C0h] BYREF
  _QWORD v22[4]; // [rsp+48h] [rbp-B8h] BYREF
  _QWORD v23[4]; // [rsp+68h] [rbp-98h] BYREF
  _QWORD v24[4]; // [rsp+88h] [rbp-78h] BYREF
  _QWORD v25[4]; // [rsp+A8h] [rbp-58h] BYREF
  _QWORD v26[4]; // [rsp+C8h] [rbp-38h] BYREF
  _QWORD v27[4]; // [rsp+E8h] [rbp-18h] BYREF
  _QWORD v28[4]; // [rsp+108h] [rbp+8h] BYREF
  _QWORD v29[4]; // [rsp+128h] [rbp+28h] BYREF
  int v30; // [rsp+148h] [rbp+48h] BYREF
  LPWSTR lpszFilePath; // [rsp+150h] [rbp+50h] BYREF
  __int64 v32; // [rsp+158h] [rbp+58h] BYREF
  char v33; // [rsp+160h] [rbp+60h]
  wchar_t *Buffer[2]; // [rsp+168h] [rbp+68h] BYREF
  _WORD v35[8]; // [rsp+178h] [rbp+78h] BYREF

  v30 = 0;
  Buffer[0] = v35;
  Buffer[1] = v35;
  v35[0] = 0;
  v4 = a1[1] - *a1;
  if ( !v4 )
  {
    v22[2] = 24;
    v22[0] = "onecore\\base\\servicing\\overlayutil\\mount.cpp";
    v22[3] = "Path.length() > 0";
    v22[1] = "GetFinalPath";
    v5 = Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateInvalidParameter_NullPointer(
           &v30,
           v22);
LABEL_7:
    v9 = v5;
LABEL_43:
    utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::_Uninit(Buffer);
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
      v24[2] = 40;
      v24[0] = "onecore\\base\\servicing\\overlayutil\\mount.cpp";
      v24[3] = "TempPath.assign(Path)";
      v24[1] = "GetFinalPath";
      v8 = v24;
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
      v23[2] = 30;
      v23[0] = "onecore\\base\\servicing\\overlayutil\\mount.cpp";
      v23[3] = "TempPath.resize(NewLength)";
      v23[1] = "GetFinalPath";
      v8 = v23;
LABEL_6:
      v5 = Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateNtStatus(
             &v30,
             v8,
             3221225495LL);
      goto LABEL_7;
    }
    swprintf_s(Buffer[0], v7, L"%ws\\", *a1);
  }
  v32 = 0;
  v33 = 0;
  v9 = RtlSystemUtil::BackupRestoreVolumePrivilegeAcquisition::Acquire((RtlSystemUtil::BackupRestoreVolumePrivilegeAcquisition *)&v32);
  if ( v9 < 0 )
  {
LABEL_42:
    RtlSystemUtil::PrivilegeAcquisition::~PrivilegeAcquisition((RtlSystemUtil::PrivilegeAcquisition *)&v32);
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
      v25[2] = 57;
      v25[0] = "onecore\\base\\servicing\\overlayutil\\mount.cpp";
      v25[1] = "GetFinalPath";
      v25[3] = "File.IsValid()";
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      v13 = v25;
LABEL_19:
      v9 = Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateHResult(
             &v30,
             v13,
             (unsigned int)LastError);
LABEL_41:
      Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&void Windows::Detail::CloseWithNtCloseHandle(void *)>>::Close(&hFile);
      goto LABEL_42;
    }
    LastError = GetLastError();
    if ( LastError )
      goto LABEL_16;
LABEL_36:
    RtlRaiseStatus(-1073741595);
  }
  FinalPathNameByHandleW = GetFinalPathNameByHandleW(hFile, 0, 0, 0);
  v15 = FinalPathNameByHandleW;
  if ( !FinalPathNameByHandleW )
  {
    if ( GetLastError() )
    {
      LastError = GetLastError();
      if ( !LastError )
        goto LABEL_36;
    }
    else
    {
      LastError = 14077;
    }
    v26[2] = 61;
    v26[0] = "onecore\\base\\servicing\\overlayutil\\mount.cpp";
    v26[1] = "GetFinalPath";
    v26[3] = "ReqPathLength != 0";
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v13 = v26;
    goto LABEL_19;
  }
  utl::make_unique<wchar_t [0],0>(&lpszFilePath, FinalPathNameByHandleW);
  v16 = lpszFilePath;
  if ( !lpszFilePath )
  {
    v27[2] = 64;
    v27[0] = "onecore\\base\\servicing\\overlayutil\\mount.cpp";
    v27[3] = "LocalFinalPath";
    v27[1] = "GetFinalPath";
    v17 = v27;
LABEL_39:
    v19 = Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateNtStatus(
            &v30,
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
        goto LABEL_36;
    }
    else
    {
      v18 = 14077;
    }
    v28[2] = 72;
    v28[0] = "onecore\\base\\servicing\\overlayutil\\mount.cpp";
    v28[1] = "GetFinalPath";
    v28[3] = "ReqPathLength != 0";
    if ( v18 > 0 )
      v18 = (unsigned __int16)v18 | 0x80070000;
    v19 = Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateHResult(
            &v30,
            v28,
            (unsigned int)v18);
LABEL_40:
    v9 = v19;
    utl::unique_ptr<OVERLAY_CIM_CONFIGURATION [0],utl::default_delete<OVERLAY_CIM_CONFIGURATION [0]>>::~unique_ptr<OVERLAY_CIM_CONFIGURATION [0],utl::default_delete<OVERLAY_CIM_CONFIGURATION [0]>>(&lpszFilePath);
    goto LABEL_41;
  }
  if ( !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(a2, v16) )
  {
    v29[2] = 74;
    v29[0] = "onecore\\base\\servicing\\overlayutil\\mount.cpp";
    v29[3] = "FinalPath.assign(LocalFinalPath.get())";
    v29[1] = "GetFinalPath";
    v17 = v29;
    goto LABEL_39;
  }
  utl::unique_ptr<OVERLAY_CIM_CONFIGURATION [0],utl::default_delete<OVERLAY_CIM_CONFIGURATION [0]>>::~unique_ptr<OVERLAY_CIM_CONFIGURATION [0],utl::default_delete<OVERLAY_CIM_CONFIGURATION [0]>>(&lpszFilePath);
  Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&void Windows::Detail::CloseWithNtCloseHandle(void *)>>::Close(&hFile);
  RtlSystemUtil::PrivilegeAcquisition::~PrivilegeAcquisition((RtlSystemUtil::PrivilegeAcquisition *)&v32);
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::_Uninit(Buffer);
  return 0;
}

```

## disassembly

```asm
0x18007cfe0  mov     [rsp-8+arg_10], rbx
0x18007cfe5  mov     [rsp-8+arg_18], rsi
0x18007cfea  push    rbp
0x18007cfeb  push    rdi
0x18007cfec  push    r14
0x18007cfee  lea     rbp, [rsp-90h]
0x18007cff6  sub     rsp, 190h
0x18007cffd  mov     rax, cs:__security_cookie
0x18007d004  xor     rax, rsp
0x18007d007  mov     [rbp+0A0h+var_18], rax
0x18007d00e  lea     rax, [rbp+0A0h+var_28]
0x18007d012  mov     [rbp+0A0h+var_58], 0
0x18007d019  mov     [rbp+0A0h+Buffer], rax
0x18007d01d  mov     r14, rdx
0x18007d020  lea     rax, [rbp+0A0h+var_28]
0x18007d024  mov     rdi, rcx
0x18007d027  mov     [rbp+0A0h+var_30], rax
0x18007d02b  xor     eax, eax
0x18007d02d  mov     [rbp+0A0h+var_28], ax
0x18007d031  mov     rax, [rcx+8]
0x18007d035  mov     r8, rax
0x18007d038  sub     r8, [rcx]
0x18007d03b  jnz     short loc_18007D07A
0x18007d03d  lea     rcx, aOnecoreBaseSer_0; "onecore\\base\\servicing\\overlayutil\\"...
0x18007d044  mov     [rsp+1A0h+var_148], 18h
0x18007d04d  mov     [rsp+1A0h+var_158], rcx
0x18007d052  lea     rax, aPathLength0; "Path.length() > 0"
0x18007d059  lea     rcx, aGetfinalpath; "GetFinalPath"
0x18007d060  mov     [rsp+1A0h+var_140], rax
0x18007d065  mov     [rsp+1A0h+var_150], rcx
0x18007d06a  lea     rdx, [rsp+1A0h+var_158]
0x18007d06f  lea     rcx, [rbp+0A0h+var_58]
0x18007d073  call    ?OriginateInvalidParameter_NullPointer@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateInvalidParameter_NullPointer(Windows::ErrorHandling::_RTL_CALL_SITE const &)
0x18007d078  jmp     short loc_18007D0DC
0x18007d07a  sar     r8, 1
0x18007d07d  cmp     word ptr [rax-2], 5Ch ; '\'
0x18007d082  jz      loc_18007D18F
0x18007d088  lea     rbx, [r8+2]
0x18007d08c  mov     rdx, rbx
0x18007d08f  lea     rcx, [rbp+0A0h+Buffer]
0x18007d093  call    ?resize@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_N_K_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::resize(unsigned __int64,wchar_t)
0x18007d098  test    al, al
0x18007d09a  jnz     short loc_18007D0E3
0x18007d09c  lea     rcx, aOnecoreBaseSer_0; "onecore\\base\\servicing\\overlayutil\\"...
0x18007d0a3  mov     [rsp+1A0h+var_128], 1Eh
0x18007d0ac  mov     [rsp+1A0h+var_138], rcx
0x18007d0b1  lea     rax, aTemppathResize; "TempPath.resize(NewLength)"
0x18007d0b8  lea     rcx, aGetfinalpath; "GetFinalPath"
0x18007d0bf  mov     [rbp+0A0h+var_120], rax
0x18007d0c3  mov     [rsp+1A0h+var_130], rcx
0x18007d0c8  lea     rdx, [rsp+1A0h+var_138]
0x18007d0cd  mov     r8d, 0C0000017h
0x18007d0d3  lea     rcx, [rbp+0A0h+var_58]
0x18007d0d7  call    ?OriginateNtStatus@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@J@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateNtStatus(Windows::ErrorHandling::_RTL_CALL_SITE const &,long)
0x18007d0dc  mov     ebx, eax
0x18007d0de  jmp     loc_18007D405
0x18007d0e3  mov     r9, [rdi]
0x18007d0e6  lea     r8, aWs_0; "%ws\\"
0x18007d0ed  mov     rcx, [rbp+0A0h+Buffer]; Buffer
0x18007d0f1  mov     rdx, rbx; BufferCount
0x18007d0f4  call    swprintf_s
0x18007d0f9  lea     rcx, [rbp+0A0h+var_48]; this
0x18007d0fd  mov     [rbp+0A0h+var_48], 0
0x18007d105  mov     [rbp+0A0h+var_40], 0
0x18007d109  call    ?Acquire@BackupRestoreVolumePrivilegeAcquisition@RtlSystemUtil@@QEAAJXZ; RtlSystemUtil::BackupRestoreVolumePrivilegeAcquisition::Acquire(void)
0x18007d10e  mov     ebx, eax
0x18007d110  test    eax, eax
0x18007d112  js      loc_18007D3FC
0x18007d118  mov     rcx, [rbp+0A0h+Buffer]; lpFileName
0x18007d11c  xor     r9d, r9d; lpSecurityAttributes
0x18007d11f  mov     [rsp+1A0h+hTemplateFile], 0; hTemplateFile
0x18007d128  mov     edx, 80000000h; dwDesiredAccess
0x18007d12d  mov     [rsp+1A0h+dwFlagsAndAttributes], 2000000h; dwFlagsAndAttributes
0x18007d135  mov     [rsp+1A0h+hFile], 0
0x18007d13e  lea     r8d, [r9+7]; dwShareMode
0x18007d142  mov     [rsp+1A0h+dwCreationDisposition], 3; dwCreationDisposition
0x18007d14a  call    cs:__imp_CreateFileW
0x18007d151  nop     dword ptr [rax+rax+00h]
0x18007d156  mov     rdx, rax
0x18007d159  lea     rcx, [rsp+1A0h+hFile]
0x18007d15e  call    ?TakeOwnership@?$AutoGenericHandleBase@PEAX$00V?$AutoGenericHandle@PEAX$00$1?CloseWithNtCloseHandle@Detail@Windows@@YAXPEAX@Z@Windows@@@Windows@@QEAAXPEAX@Z; Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&Windows::Detail::CloseWithNtCloseHandle(void *)>>::TakeOwnership(void *)
0x18007d163  mov     rdi, [rsp+1A0h+hFile]
0x18007d168  lea     rax, [rdi+1]
0x18007d16c  test    rax, 0FFFFFFFFFFFFFFFEh
0x18007d172  jnz     loc_18007D235
0x18007d178  call    cs:__imp_GetLastError
0x18007d17f  nop     dword ptr [rax+rax+00h]
0x18007d184  test    eax, eax
0x18007d186  jnz     short loc_18007D1D5
0x18007d188  mov     eax, 36FDh
0x18007d18d  jmp     short loc_18007D1E9
0x18007d18f  mov     rdx, [rcx]
0x18007d192  lea     rcx, [rbp+0A0h+Buffer]
0x18007d196  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(wchar_t const *,unsigned __int64)
0x18007d19b  test    al, al
0x18007d19d  jnz     loc_18007D0F9
0x18007d1a3  lea     rcx, aOnecoreBaseSer_0; "onecore\\base\\servicing\\overlayutil\\"...
0x18007d1aa  mov     [rbp+0A0h+var_108], 28h ; '('
0x18007d1b2  mov     [rbp+0A0h+var_118], rcx
0x18007d1b6  lea     rax, aTemppathAssign; "TempPath.assign(Path)"
0x18007d1bd  lea     rcx, aGetfinalpath; "GetFinalPath"
0x18007d1c4  mov     [rbp+0A0h+var_100], rax
0x18007d1c8  mov     [rbp+0A0h+var_110], rcx
0x18007d1cc  lea     rdx, [rbp+0A0h+var_118]
0x18007d1d0  jmp     loc_18007D0CD
0x18007d1d5  call    cs:__imp_GetLastError
0x18007d1dc  nop     dword ptr [rax+rax+00h]
0x18007d1e1  test    eax, eax
0x18007d1e3  jz      loc_18007D38A
0x18007d1e9  mov     [rbp+0A0h+var_E8], 39h ; '9'
0x18007d1f1  lea     rcx, aOnecoreBaseSer_0; "onecore\\base\\servicing\\overlayutil\\"...
0x18007d1f8  mov     [rbp+0A0h+var_F8], rcx
0x18007d1fc  lea     rcx, aGetfinalpath; "GetFinalPath"
0x18007d203  mov     [rbp+0A0h+var_F0], rcx
0x18007d207  lea     rcx, aFileIsvalid; "File.IsValid()"
0x18007d20e  mov     [rbp+0A0h+var_E0], rcx
0x18007d212  test    eax, eax
0x18007d214  jle     short loc_18007D21E
0x18007d216  movzx   eax, ax
0x18007d219  or      eax, 80070000h
0x18007d21e  lea     rdx, [rbp+0A0h+var_F8]
0x18007d222  mov     r8d, eax
0x18007d225  lea     rcx, [rbp+0A0h+var_58]
0x18007d229  call    ?OriginateHResult@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@J@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateHResult(Windows::ErrorHandling::_RTL_CALL_SITE const &,long)
0x18007d22e  mov     ebx, eax
0x18007d230  jmp     loc_18007D3F2
0x18007d235  xor     r9d, r9d; dwFlags
0x18007d238  xor     r8d, r8d; cchFilePath
0x18007d23b  xor     edx, edx; lpszFilePath
0x18007d23d  mov     rcx, rdi; hFile
0x18007d240  call    cs:__imp_GetFinalPathNameByHandleW
0x18007d247  nop     dword ptr [rax+rax+00h]
0x18007d24c  mov     esi, eax
0x18007d24e  test    eax, eax
0x18007d250  jnz     short loc_18007D2BB
0x18007d252  call    cs:__imp_GetLastError
0x18007d259  nop     dword ptr [rax+rax+00h]
0x18007d25e  test    eax, eax
0x18007d260  jnz     short loc_18007D269
0x18007d262  mov     eax, 36FDh
0x18007d267  jmp     short loc_18007D27D
0x18007d269  call    cs:__imp_GetLastError
0x18007d270  nop     dword ptr [rax+rax+00h]
0x18007d275  test    eax, eax
0x18007d277  jz      loc_18007D38A
0x18007d27d  mov     [rbp+0A0h+var_C8], 3Dh ; '='
0x18007d285  lea     rcx, aOnecoreBaseSer_0; "onecore\\base\\servicing\\overlayutil\\"...
0x18007d28c  mov     [rbp+0A0h+var_D8], rcx
0x18007d290  lea     rcx, aGetfinalpath; "GetFinalPath"
0x18007d297  mov     [rbp+0A0h+var_D0], rcx
0x18007d29b  lea     rcx, aReqpathlength0; "ReqPathLength != 0"
0x18007d2a2  mov     [rbp+0A0h+var_C0], rcx
0x18007d2a6  test    eax, eax
0x18007d2a8  jle     short loc_18007D2B2
0x18007d2aa  movzx   eax, ax
0x18007d2ad  or      eax, 80070000h
0x18007d2b2  lea     rdx, [rbp+0A0h+var_D8]
0x18007d2b6  jmp     loc_18007D222
0x18007d2bb  mov     rdx, rsi
0x18007d2be  lea     rcx, [rbp+0A0h+lpszFilePath]
0x18007d2c2  call    ??$make_unique@$$BY0A@_W$0A@@utl@@YA?AV?$unique_ptr@$$BY0A@_WU?$default_delete@$$BY0A@_W@utl@@@0@_K@Z; utl::make_unique<wchar_t [0],0>(unsigned __int64)
0x18007d2c7  mov     rbx, [rbp+0A0h+lpszFilePath]
0x18007d2cb  test    rbx, rbx
0x18007d2ce  jnz     short loc_18007D302
0x18007d2d0  lea     rcx, aOnecoreBaseSer_0; "onecore\\base\\servicing\\overlayutil\\"...
0x18007d2d7  mov     [rbp+0A0h+var_A8], 40h ; '@'
0x18007d2df  mov     [rbp+0A0h+var_B8], rcx
0x18007d2e3  lea     rax, aLocalfinalpath; "LocalFinalPath"
0x18007d2ea  lea     rcx, aGetfinalpath; "GetFinalPath"
0x18007d2f1  mov     [rbp+0A0h+var_A0], rax
0x18007d2f5  mov     [rbp+0A0h+var_B0], rcx
0x18007d2f9  lea     rdx, [rbp+0A0h+var_B8]
0x18007d2fd  jmp     loc_18007D3D8
0x18007d302  xor     r9d, r9d; dwFlags
0x18007d305  mov     r8d, esi; cchFilePath
0x18007d308  mov     rdx, rbx; lpszFilePath
0x18007d30b  mov     rcx, rdi; hFile
0x18007d30e  call    cs:__imp_GetFinalPathNameByHandleW
0x18007d315  nop     dword ptr [rax+rax+00h]
0x18007d31a  test    eax, eax
0x18007d31c  jnz     short loc_18007D39C
0x18007d31e  call    cs:__imp_GetLastError
0x18007d325  nop     dword ptr [rax+rax+00h]
0x18007d32a  test    eax, eax
0x18007d32c  jnz     short loc_18007D37A
0x18007d32e  mov     eax, 36FDh
0x18007d333  mov     [rbp+0A0h+var_88], 48h ; 'H'
0x18007d33b  lea     rcx, aOnecoreBaseSer_0; "onecore\\base\\servicing\\overlayutil\\"...
0x18007d342  mov     [rbp+0A0h+var_98], rcx
0x18007d346  lea     rcx, aGetfinalpath; "GetFinalPath"
0x18007d34d  mov     [rbp+0A0h+var_90], rcx
0x18007d351  lea     rcx, aReqpathlength0; "ReqPathLength != 0"
0x18007d358  mov     [rbp+0A0h+var_80], rcx
0x18007d35c  test    eax, eax
0x18007d35e  jle     short loc_18007D368
0x18007d360  movzx   eax, ax
0x18007d363  or      eax, 80070000h
0x18007d368  mov     r8d, eax
0x18007d36b  lea     rdx, [rbp+0A0h+var_98]
0x18007d36f  lea     rcx, [rbp+0A0h+var_58]
0x18007d373  call    ?OriginateHResult@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@J@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateHResult(Windows::ErrorHandling::_RTL_CALL_SITE const &,long)
0x18007d378  jmp     short loc_18007D3E7
0x18007d37a  call    cs:__imp_GetLastError
0x18007d381  nop     dword ptr [rax+rax+00h]
0x18007d386  test    eax, eax
0x18007d388  jnz     short loc_18007D333
0x18007d38a  mov     ecx, 0C00000E5h; Status
0x18007d38f  call    cs:__imp_RtlRaiseStatus
0x18007d396  nop     dword ptr [rax+rax+00h]
0x18007d39b  int     3; Trap to Debugger
0x18007d39c  mov     rdx, rbx
0x18007d39f  mov     rcx, r14
0x18007d3a2  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(wchar_t const *)
0x18007d3a7  test    al, al
0x18007d3a9  jnz     short loc_18007D412
0x18007d3ab  lea     rcx, aOnecoreBaseSer_0; "onecore\\base\\servicing\\overlayutil\\"...
0x18007d3b2  mov     [rbp+0A0h+var_68], 4Ah ; 'J'
0x18007d3ba  mov     [rbp+0A0h+var_78], rcx
0x18007d3be  lea     rax, aFinalpathAssig; "FinalPath.assign(LocalFinalPath.get())"
0x18007d3c5  lea     rcx, aGetfinalpath; "GetFinalPath"
0x18007d3cc  mov     [rbp+0A0h+var_60], rax
0x18007d3d0  mov     [rbp+0A0h+var_70], rcx
0x18007d3d4  lea     rdx, [rbp+0A0h+var_78]
0x18007d3d8  mov     r8d, 0C0000017h
0x18007d3de  lea     rcx, [rbp+0A0h+var_58]
0x18007d3e2  call    ?OriginateNtStatus@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@J@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateNtStatus(Windows::ErrorHandling::_RTL_CALL_SITE const &,long)
0x18007d3e7  lea     rcx, [rbp+0A0h+lpszFilePath]
0x18007d3eb  mov     ebx, eax
0x18007d3ed  call    ??1?$unique_ptr@$$BY0A@UOVERLAY_CIM_CONFIGURATION@@U?$default_delete@$$BY0A@UOVERLAY_CIM_CONFIGURATION@@@utl@@@utl@@QEAA@XZ; utl::unique_ptr<OVERLAY_CIM_CONFIGURATION [0],utl::default_delete<OVERLAY_CIM_CONFIGURATION [0]>>::~unique_ptr<OVERLAY_CIM_CONFIGURATION [0],utl::default_delete<OVERLAY_CIM_CONFIGURATION [0]>>(void)
0x18007d3f2  lea     rcx, [rsp+1A0h+hFile]
0x18007d3f7  call    ?Close@?$AutoGenericHandleBase@PEAX$00V?$AutoGenericHandle@PEAX$00$1?CloseWithNtCloseHandle@Detail@Windows@@YAXPEAX@Z@Windows@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&Windows::Detail::CloseWithNtCloseHandle(void *)>>::Close(void)
0x18007d3fc  lea     rcx, [rbp+0A0h+var_48]; this
0x18007d400  call    ??1PrivilegeAcquisition@RtlSystemUtil@@QEAA@XZ; RtlSystemUtil::PrivilegeAcquisition::~PrivilegeAcquisition(void)
0x18007d405  lea     rcx, [rbp+0A0h+Buffer]
0x18007d409  call    ?_Uninit@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@AEAAXXZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::_Uninit(void)
0x18007d40e  mov     eax, ebx
0x18007d410  jmp     short loc_18007D439
0x18007d412  lea     rcx, [rbp+0A0h+lpszFilePath]
0x18007d416  call    ??1?$unique_ptr@$$BY0A@UOVERLAY_CIM_CONFIGURATION@@U?$default_delete@$$BY0A@UOVERLAY_CIM_CONFIGURATION@@@utl@@@utl@@QEAA@XZ; utl::unique_ptr<OVERLAY_CIM_CONFIGURATION [0],utl::default_delete<OVERLAY_CIM_CONFIGURATION [0]>>::~unique_ptr<OVERLAY_CIM_CONFIGURATION [0],utl::default_delete<OVERLAY_CIM_CONFIGURATION [0]>>(void)
0x18007d41b  lea     rcx, [rsp+1A0h+hFile]
0x18007d420  call    ?Close@?$AutoGenericHandleBase@PEAX$00V?$AutoGenericHandle@PEAX$00$1?CloseWithNtCloseHandle@Detail@Windows@@YAXPEAX@Z@Windows@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&Windows::Detail::CloseWithNtCloseHandle(void *)>>::Close(void)
0x18007d425  lea     rcx, [rbp+0A0h+var_48]; this
0x18007d429  call    ??1PrivilegeAcquisition@RtlSystemUtil@@QEAA@XZ; RtlSystemUtil::PrivilegeAcquisition::~PrivilegeAcquisition(void)
0x18007d42e  lea     rcx, [rbp+0A0h+Buffer]
0x18007d432  call    ?_Uninit@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@AEAAXXZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::_Uninit(void)
0x18007d437  xor     eax, eax
0x18007d439  mov     rcx, [rbp+0A0h+var_18]
0x18007d440  xor     rcx, rsp; StackCookie
0x18007d443  call    __security_check_cookie
0x18007d448  lea     r11, [rsp+1A0h+var_10]
0x18007d450  mov     rbx, [r11+30h]
0x18007d454  mov     rsi, [r11+38h]
0x18007d458  mov     rsp, r11
0x18007d45b  pop     r14
0x18007d45d  pop     rdi
0x18007d45e  pop     rbp
0x18007d45f  retn
```
