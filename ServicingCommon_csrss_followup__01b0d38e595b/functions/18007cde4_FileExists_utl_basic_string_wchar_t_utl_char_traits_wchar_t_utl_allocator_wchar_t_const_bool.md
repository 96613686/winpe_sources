# FileExists(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const &,bool &)

- ea: `0x18007cde4`
- end: `0x18007cfd8`
- name: `?FileExists@@YAJAEBV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@AEA_N@Z`
- size: `500`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, authz_impersonation, loader_planting, installer_update`

## callers

- `0x18007eb20`

## callees

- `0x180018df0`
- `0x18002d2b0`
- `0x180047d5c`
- `0x18006c244`
- `0x18007cbb8`
- `0x18007cde4`
- `0x18007d794`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18007cea2`
- `KERNEL32!GetLastError` at `0x18007ceb9`
- `KERNEL32!GetLastError` at `0x18007cf49`
- `KERNEL32!GetLastError` at `0x18007cea2`
- `KERNEL32!GetLastError` at `0x18007ceb9`
- `KERNEL32!GetLastError` at `0x18007cf49`
- `KERNEL32!CreateFileW` at `0x18007ce65`
- `KERNEL32!CreateFileW` at `0x18007ce65`
- `KERNEL32!GetFileAttributesW` at `0x18007ce91`
- `KERNEL32!GetFileAttributesW` at `0x18007ce91`
- `ntdll!RtlRaiseStatus` at `0x18007cf6a`
- `ntdll!RtlRaiseStatus` at `0x18007cf6a`

## string_xrefs

- `0x18007ced5`: `onecore\base\servicing\overlayutil\mount.cpp`
- `0x18007cf7f`: `onecore\base\servicing\overlayutil\mount.cpp`

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
    goto LABEL_20;
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
        goto LABEL_19;
      }
      goto LABEL_15;
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
LABEL_15:
    RtlRaiseStatus(-1073741595);
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
LABEL_19:
  v4 = Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateHResult(
         &v16,
         v10,
         v9);
  Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&void Windows::Detail::CloseWithNtCloseHandle(void *)>>::Close(&v13);
LABEL_20:
  RtlSystemUtil::PrivilegeAcquisition::~PrivilegeAcquisition((RtlSystemUtil::PrivilegeAcquisition *)&v17);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18007cde4  mov     [rsp-8+arg_10], rbx
0x18007cde9  push    rbp
0x18007cdea  push    rsi
0x18007cdeb  push    rdi
0x18007cdec  lea     rbp, [rsp-47h]
0x18007cdf1  sub     rsp, 0B0h
0x18007cdf8  mov     rax, cs:__security_cookie
0x18007cdff  xor     rax, rsp
0x18007ce02  mov     [rbp+57h+var_20], rax
0x18007ce06  mov     rsi, rcx
0x18007ce09  mov     [rbp+57h+var_38], 0
0x18007ce10  lea     rcx, [rbp+57h+var_30]; this
0x18007ce14  mov     byte ptr [rdx], 0
0x18007ce17  mov     rdi, rdx
0x18007ce1a  mov     [rbp+57h+var_30], 0
0x18007ce22  mov     [rbp+57h+var_28], 0
0x18007ce26  call    ?Acquire@BackupRestoreVolumePrivilegeAcquisition@RtlSystemUtil@@QEAAJXZ; RtlSystemUtil::BackupRestoreVolumePrivilegeAcquisition::Acquire(void)
0x18007ce2b  mov     ebx, eax
0x18007ce2d  test    eax, eax
0x18007ce2f  js      loc_18007CFC8
0x18007ce35  mov     rcx, [rsi]; lpFileName
0x18007ce38  xor     r9d, r9d; lpSecurityAttributes
0x18007ce3b  mov     [rsp+0C0h+hTemplateFile], 0; hTemplateFile
0x18007ce44  mov     edx, 80000000h; dwDesiredAccess
0x18007ce49  mov     [rsp+0C0h+dwFlagsAndAttributes], 2000000h; dwFlagsAndAttributes
0x18007ce51  mov     [rbp+57h+var_80], 0
0x18007ce59  lea     r8d, [r9+7]; dwShareMode
0x18007ce5d  mov     [rsp+0C0h+dwCreationDisposition], 3; dwCreationDisposition
0x18007ce65  call    cs:__imp_CreateFileW
0x18007ce6c  nop     dword ptr [rax+rax+00h]
0x18007ce71  mov     rdx, rax
0x18007ce74  lea     rcx, [rbp+57h+var_80]
0x18007ce78  call    ?TakeOwnership@?$AutoGenericHandleBase@PEAX$00V?$AutoGenericHandle@PEAX$00$1?CloseWithNtCloseHandle@Detail@Windows@@YAXPEAX@Z@Windows@@@Windows@@QEAAXPEAX@Z; Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&Windows::Detail::CloseWithNtCloseHandle(void *)>>::TakeOwnership(void *)
0x18007ce7d  mov     rax, [rbp+57h+var_80]
0x18007ce81  dec     rax
0x18007ce84  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18007ce88  ja      loc_18007CF49
0x18007ce8e  mov     rcx, [rsi]; lpFileName
0x18007ce91  call    cs:__imp_GetFileAttributesW
0x18007ce98  nop     dword ptr [rax+rax+00h]
0x18007ce9d  cmp     eax, 0FFFFFFFFh
0x18007cea0  jnz     short loc_18007CF0E
0x18007cea2  call    cs:__imp_GetLastError
0x18007cea9  nop     dword ptr [rax+rax+00h]
0x18007ceae  test    eax, eax
0x18007ceb0  jnz     short loc_18007CEB9
0x18007ceb2  mov     eax, 36FDh
0x18007ceb7  jmp     short loc_18007CECD
0x18007ceb9  call    cs:__imp_GetLastError
0x18007cec0  nop     dword ptr [rax+rax+00h]
0x18007cec5  test    eax, eax
0x18007cec7  jz      loc_18007CF65
0x18007cecd  mov     [rbp+57h+var_68], 90h
0x18007ced5  lea     rcx, aOnecoreBaseSer_0; "onecore\\base\\servicing\\overlayutil\\"...
0x18007cedc  mov     [rbp+57h+var_78], rcx
0x18007cee0  lea     rcx, aFileexists; "FileExists"
0x18007cee7  mov     [rbp+57h+var_70], rcx
0x18007ceeb  lea     rcx, aGetlasterror; "GetLastError"
0x18007cef2  mov     [rbp+57h+var_60], rcx
0x18007cef6  test    eax, eax
0x18007cef8  jle     short loc_18007CF02
0x18007cefa  movzx   eax, ax
0x18007cefd  or      eax, 80070000h
0x18007cf02  mov     r8d, eax
0x18007cf05  lea     rdx, [rbp+57h+var_78]
0x18007cf09  jmp     loc_18007CFB4
0x18007cf0e  test    al, 10h
0x18007cf10  jnz     short loc_18007CF15
0x18007cf12  mov     byte ptr [rdi], 1
0x18007cf15  lea     rcx, [rbp+57h+var_80]
0x18007cf19  call    ?Close@?$AutoGenericHandleBase@PEAX$00V?$AutoGenericHandle@PEAX$00$1?CloseWithNtCloseHandle@Detail@Windows@@YAXPEAX@Z@Windows@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&Windows::Detail::CloseWithNtCloseHandle(void *)>>::Close(void)
0x18007cf1e  lea     rcx, [rbp+57h+var_30]; this
0x18007cf22  call    ??1PrivilegeAcquisition@RtlSystemUtil@@QEAA@XZ; RtlSystemUtil::PrivilegeAcquisition::~PrivilegeAcquisition(void)
0x18007cf27  xor     eax, eax
0x18007cf29  mov     rcx, [rbp+57h+var_20]
0x18007cf2d  xor     rcx, rsp; StackCookie
0x18007cf30  call    __security_check_cookie
0x18007cf35  mov     rbx, [rsp+0C0h+arg_10]
0x18007cf3d  add     rsp, 0B0h
0x18007cf44  pop     rdi
0x18007cf45  pop     rsi
0x18007cf46  pop     rbp
0x18007cf47  retn
0x18007cf49  call    cs:__imp_GetLastError
0x18007cf50  nop     dword ptr [rax+rax+00h]
0x18007cf55  mov     r8d, eax
0x18007cf58  add     eax, 0FFFFFFFEh
0x18007cf5b  cmp     eax, 1
0x18007cf5e  jbe     short loc_18007CF15
0x18007cf60  test    r8d, r8d
0x18007cf63  jnz     short loc_18007CF77
0x18007cf65  mov     ecx, 0C00000E5h; Status
0x18007cf6a  call    cs:__imp_RtlRaiseStatus
0x18007cf71  nop     dword ptr [rax+rax+00h]
0x18007cf76  int     3; Trap to Debugger
0x18007cf77  mov     [rbp+57h+var_48], 99h
0x18007cf7f  lea     rcx, aOnecoreBaseSer_0; "onecore\\base\\servicing\\overlayutil\\"...
0x18007cf86  mov     [rbp+57h+var_58], rcx
0x18007cf8a  lea     rcx, aFileexists; "FileExists"
0x18007cf91  mov     [rbp+57h+var_50], rcx
0x18007cf95  lea     rax, aLasterr; "__lastErr"
0x18007cf9c  mov     [rbp+57h+var_40], rax
0x18007cfa0  test    r8d, r8d
0x18007cfa3  jle     short loc_18007CFB0
0x18007cfa5  movzx   r8d, r8w
0x18007cfa9  or      r8d, 80070000h
0x18007cfb0  lea     rdx, [rbp+57h+var_58]
0x18007cfb4  lea     rcx, [rbp+57h+var_38]
0x18007cfb8  call    ?OriginateHResult@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@J@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateHResult(Windows::ErrorHandling::_RTL_CALL_SITE const &,long)
0x18007cfbd  lea     rcx, [rbp+57h+var_80]
0x18007cfc1  mov     ebx, eax
0x18007cfc3  call    ?Close@?$AutoGenericHandleBase@PEAX$00V?$AutoGenericHandle@PEAX$00$1?CloseWithNtCloseHandle@Detail@Windows@@YAXPEAX@Z@Windows@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&Windows::Detail::CloseWithNtCloseHandle(void *)>>::Close(void)
0x18007cfc8  lea     rcx, [rbp+57h+var_30]; this
0x18007cfcc  call    ??1PrivilegeAcquisition@RtlSystemUtil@@QEAA@XZ; RtlSystemUtil::PrivilegeAcquisition::~PrivilegeAcquisition(void)
0x18007cfd1  mov     eax, ebx
0x18007cfd3  jmp     loc_18007CF29
```
