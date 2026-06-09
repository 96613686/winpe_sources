# FileExists(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const &,bool &)

- ea: `0x18007dd78`
- end: `0x18007df65`
- name: `?FileExists@@YAJAEBV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@AEA_N@Z`
- size: `493`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, authz_impersonation, installer_update`

## callers

- `0x18007faa0`

## callees

- `0x18000ea3c`
- `0x18001fd10`
- `0x1800293a0`
- `0x180044bcc`
- `0x18006c360`
- `0x18007db54`
- `0x18007dd78`
- `0x18007e720`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18007de36`
- `KERNEL32!GetLastError` at `0x18007de4d`
- `KERNEL32!GetLastError` at `0x18007dedd`
- `KERNEL32!GetLastError` at `0x18007de36`
- `KERNEL32!GetLastError` at `0x18007de4d`
- `KERNEL32!GetLastError` at `0x18007dedd`
- `KERNEL32!CreateFileW` at `0x18007ddf9`
- `KERNEL32!CreateFileW` at `0x18007ddf9`
- `KERNEL32!GetFileAttributesW` at `0x18007de25`
- `KERNEL32!GetFileAttributesW` at `0x18007de25`

## string_xrefs

- `0x18007de69`: `onecore\base\servicing\overlayutil\mount.cpp`
- `0x18007df01`: `onecore\base\servicing\overlayutil\mount.cpp`

## pseudocode

```c
__int64 __fastcall FileExists(LPCWSTR *a1, _BYTE *a2)
{
  int v4; // ebx
  const WCHAR *v5; // rcx
  HANDLE FileW; // rax
  DWORD FileAttributesW; // eax
  signed int v8; // eax
  __int64 v9; // r8
  _QWORD *v10; // rdx
  signed int LastError; // eax
  __int64 v13; // [rsp+40h] [rbp-29h] BYREF
  _QWORD v14[4]; // [rsp+48h] [rbp-21h] BYREF
  _QWORD v15[4]; // [rsp+68h] [rbp-1h] BYREF
  int v16; // [rsp+88h] [rbp+1Fh] BYREF
  __int64 v17; // [rsp+90h] [rbp+27h] BYREF
  char v18; // [rsp+98h] [rbp+2Fh]

  v16 = 0;
  *a2 = 0;
  v17 = 0;
  v18 = 0;
  v4 = RtlSystemUtil::BackupRestoreVolumePrivilegeAcquisition::Acquire((RtlSystemUtil::BackupRestoreVolumePrivilegeAcquisition *)&v17);
  if ( v4 < 0 )
    goto LABEL_19;
  v5 = *a1;
  v13 = 0;
  FileW = CreateFileW(v5, 0x80000000, 7u, 0, 3u, 0x2000000u, 0);
  Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&void Windows::Detail::CloseWithNtCloseHandle(void *)>>::TakeOwnership(
    &v13,
    FileW);
  if ( (unsigned __int64)(v13 - 1) > 0xFFFFFFFFFFFFFFFDuLL )
  {
    LastError = GetLastError();
    v9 = (unsigned int)LastError;
    if ( (unsigned int)(LastError - 2) > 1 )
    {
      if ( LastError )
      {
        v15[2] = 153;
        v15[0] = "onecore\\base\\servicing\\overlayutil\\mount.cpp";
        v15[1] = "FileExists";
        v15[3] = "__lastErr";
        if ( LastError > 0 )
          v9 = (unsigned __int16)LastError | 0x80070000;
        v10 = v15;
        goto LABEL_18;
      }
      goto LABEL_20;
    }
LABEL_12:
    Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&void Windows::Detail::CloseWithNtCloseHandle(void *)>>::Close(&v13);
    RtlSystemUtil::PrivilegeAcquisition::~PrivilegeAcquisition((RtlSystemUtil::PrivilegeAcquisition *)&v17);
    return 0;
  }
  FileAttributesW = GetFileAttributesW(*a1);
  if ( FileAttributesW != -1 )
  {
    if ( (FileAttributesW & 0x10) == 0 )
      *a2 = 1;
    goto LABEL_12;
  }
  if ( GetLastError() )
  {
    v8 = GetLastError();
    if ( v8 )
      goto LABEL_7;
LABEL_20:
    INTERNAL_ERROR_ACTION(-1073741595);
    JUMPOUT(0x18007DF64LL);
  }
  v8 = 14077;
LABEL_7:
  v14[2] = 144;
  v14[0] = "onecore\\base\\servicing\\overlayutil\\mount.cpp";
  v14[1] = "FileExists";
  v14[3] = "GetLastError";
  if ( v8 > 0 )
    v8 = (unsigned __int16)v8 | 0x80070000;
  v9 = (unsigned int)v8;
  v10 = v14;
LABEL_18:
  v4 = Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateHResult(
         &v16,
         v10,
         v9);
  Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&void Windows::Detail::CloseWithNtCloseHandle(void *)>>::Close(&v13);
LABEL_19:
  RtlSystemUtil::PrivilegeAcquisition::~PrivilegeAcquisition((RtlSystemUtil::PrivilegeAcquisition *)&v17);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18007dd78  mov     [rsp-8+arg_10], rbx
0x18007dd7d  push    rbp
0x18007dd7e  push    rsi
0x18007dd7f  push    rdi
0x18007dd80  lea     rbp, [rsp-47h]
0x18007dd85  sub     rsp, 0B0h
0x18007dd8c  mov     rax, cs:__security_cookie
0x18007dd93  xor     rax, rsp
0x18007dd96  mov     [rbp+57h+var_20], rax
0x18007dd9a  mov     rsi, rcx
0x18007dd9d  mov     [rbp+57h+var_38], 0
0x18007dda4  lea     rcx, [rbp+57h+var_30]; this
0x18007dda8  mov     byte ptr [rdx], 0
0x18007ddab  mov     rdi, rdx
0x18007ddae  mov     [rbp+57h+var_30], 0
0x18007ddb6  mov     [rbp+57h+var_28], 0
0x18007ddba  call    ?Acquire@BackupRestoreVolumePrivilegeAcquisition@RtlSystemUtil@@QEAAJXZ; RtlSystemUtil::BackupRestoreVolumePrivilegeAcquisition::Acquire(void)
0x18007ddbf  mov     ebx, eax
0x18007ddc1  test    eax, eax
0x18007ddc3  js      loc_18007DF4A
0x18007ddc9  mov     rcx, [rsi]; lpFileName
0x18007ddcc  xor     r9d, r9d; lpSecurityAttributes
0x18007ddcf  mov     [rsp+0C0h+hTemplateFile], 0; hTemplateFile
0x18007ddd8  mov     edx, 80000000h; dwDesiredAccess
0x18007dddd  mov     [rsp+0C0h+dwFlagsAndAttributes], 2000000h; dwFlagsAndAttributes
0x18007dde5  mov     [rbp+57h+var_80], 0
0x18007dded  lea     r8d, [r9+7]; dwShareMode
0x18007ddf1  mov     [rsp+0C0h+dwCreationDisposition], 3; dwCreationDisposition
0x18007ddf9  call    cs:__imp_CreateFileW
0x18007de00  nop     dword ptr [rax+rax+00h]
0x18007de05  mov     rdx, rax
0x18007de08  lea     rcx, [rbp+57h+var_80]
0x18007de0c  call    ?TakeOwnership@?$AutoGenericHandleBase@PEAX$00V?$AutoGenericHandle@PEAX$00$1?CloseWithNtCloseHandle@Detail@Windows@@YAXPEAX@Z@Windows@@@Windows@@QEAAXPEAX@Z; Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&Windows::Detail::CloseWithNtCloseHandle(void *)>>::TakeOwnership(void *)
0x18007de11  mov     rax, [rbp+57h+var_80]
0x18007de15  dec     rax
0x18007de18  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18007de1c  ja      loc_18007DEDD
0x18007de22  mov     rcx, [rsi]; lpFileName
0x18007de25  call    cs:__imp_GetFileAttributesW
0x18007de2c  nop     dword ptr [rax+rax+00h]
0x18007de31  cmp     eax, 0FFFFFFFFh
0x18007de34  jnz     short loc_18007DEA2
0x18007de36  call    cs:__imp_GetLastError
0x18007de3d  nop     dword ptr [rax+rax+00h]
0x18007de42  test    eax, eax
0x18007de44  jnz     short loc_18007DE4D
0x18007de46  mov     eax, 36FDh
0x18007de4b  jmp     short loc_18007DE61
0x18007de4d  call    cs:__imp_GetLastError
0x18007de54  nop     dword ptr [rax+rax+00h]
0x18007de59  test    eax, eax
0x18007de5b  jz      loc_18007DF5A
0x18007de61  mov     [rbp+57h+var_68], 90h
0x18007de69  lea     rcx, aOnecoreBaseSer_0; "onecore\\base\\servicing\\overlayutil\\"...
0x18007de70  mov     [rbp+57h+var_78], rcx
0x18007de74  lea     rcx, aFileexists; "FileExists"
0x18007de7b  mov     [rbp+57h+var_70], rcx
0x18007de7f  lea     rcx, aGetlasterror; "GetLastError"
0x18007de86  mov     [rbp+57h+var_60], rcx
0x18007de8a  test    eax, eax
0x18007de8c  jle     short loc_18007DE96
0x18007de8e  movzx   eax, ax
0x18007de91  or      eax, 80070000h
0x18007de96  mov     r8d, eax
0x18007de99  lea     rdx, [rbp+57h+var_78]
0x18007de9d  jmp     loc_18007DF36
0x18007dea2  test    al, 10h
0x18007dea4  jnz     short loc_18007DEA9
0x18007dea6  mov     byte ptr [rdi], 1
0x18007dea9  lea     rcx, [rbp+57h+var_80]
0x18007dead  call    ?Close@?$AutoGenericHandleBase@PEAX$00V?$AutoGenericHandle@PEAX$00$1?CloseWithNtCloseHandle@Detail@Windows@@YAXPEAX@Z@Windows@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&Windows::Detail::CloseWithNtCloseHandle(void *)>>::Close(void)
0x18007deb2  lea     rcx, [rbp+57h+var_30]; this
0x18007deb6  call    ??1PrivilegeAcquisition@RtlSystemUtil@@QEAA@XZ; RtlSystemUtil::PrivilegeAcquisition::~PrivilegeAcquisition(void)
0x18007debb  xor     eax, eax
0x18007debd  mov     rcx, [rbp+57h+var_20]
0x18007dec1  xor     rcx, rsp; StackCookie
0x18007dec4  call    __security_check_cookie
0x18007dec9  mov     rbx, [rsp+0C0h+arg_10]
0x18007ded1  add     rsp, 0B0h
0x18007ded8  pop     rdi
0x18007ded9  pop     rsi
0x18007deda  pop     rbp
0x18007dedb  retn
0x18007dedd  call    cs:__imp_GetLastError
0x18007dee4  nop     dword ptr [rax+rax+00h]
0x18007dee9  mov     r8d, eax
0x18007deec  add     eax, 0FFFFFFFEh
0x18007deef  cmp     eax, 1
0x18007def2  jbe     short loc_18007DEA9
0x18007def4  test    r8d, r8d
0x18007def7  jz      short loc_18007DF5A
0x18007def9  mov     [rbp+57h+var_48], 99h
0x18007df01  lea     rcx, aOnecoreBaseSer_0; "onecore\\base\\servicing\\overlayutil\\"...
0x18007df08  mov     [rbp+57h+var_58], rcx
0x18007df0c  lea     rcx, aFileexists; "FileExists"
0x18007df13  mov     [rbp+57h+var_50], rcx
0x18007df17  lea     rax, aLasterr; "__lastErr"
0x18007df1e  mov     [rbp+57h+var_40], rax
0x18007df22  test    r8d, r8d
0x18007df25  jle     short loc_18007DF32
0x18007df27  movzx   r8d, r8w
0x18007df2b  or      r8d, 80070000h
0x18007df32  lea     rdx, [rbp+57h+var_58]
0x18007df36  lea     rcx, [rbp+57h+var_38]
0x18007df3a  call    ?OriginateHResult@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@J@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateHResult(Windows::ErrorHandling::_RTL_CALL_SITE const &,long)
0x18007df3f  lea     rcx, [rbp+57h+var_80]
0x18007df43  mov     ebx, eax
0x18007df45  call    ?Close@?$AutoGenericHandleBase@PEAX$00V?$AutoGenericHandle@PEAX$00$1?CloseWithNtCloseHandle@Detail@Windows@@YAXPEAX@Z@Windows@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&Windows::Detail::CloseWithNtCloseHandle(void *)>>::Close(void)
0x18007df4a  lea     rcx, [rbp+57h+var_30]; this
0x18007df4e  call    ??1PrivilegeAcquisition@RtlSystemUtil@@QEAA@XZ; RtlSystemUtil::PrivilegeAcquisition::~PrivilegeAcquisition(void)
0x18007df53  mov     eax, ebx
0x18007df55  jmp     loc_18007DEBD
0x18007df5a  mov     ecx, 0C00000E5h; int
0x18007df5f  call    ?INTERNAL_ERROR_ACTION@@YAXJ@Z; INTERNAL_ERROR_ACTION(long)
```
