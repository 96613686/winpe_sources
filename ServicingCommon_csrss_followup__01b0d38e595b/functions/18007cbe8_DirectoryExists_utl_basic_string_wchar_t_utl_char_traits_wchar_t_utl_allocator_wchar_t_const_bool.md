# DirectoryExists(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const &,bool &)

- ea: `0x18007cbe8`
- end: `0x18007cddc`
- name: `?DirectoryExists@@YAJAEBV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@AEA_N@Z`
- size: `500`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, authz_impersonation, loader_planting, installer_update`

## callers

- `0x18007e3f0`

## callees

- `0x180018df0`
- `0x18002d2b0`
- `0x180047d5c`
- `0x18006c244`
- `0x18007cbb8`
- `0x18007cbe8`
- `0x18007d794`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18007cca6`
- `KERNEL32!GetLastError` at `0x18007ccbd`
- `KERNEL32!GetLastError` at `0x18007cd4d`
- `KERNEL32!GetLastError` at `0x18007cca6`
- `KERNEL32!GetLastError` at `0x18007ccbd`
- `KERNEL32!GetLastError` at `0x18007cd4d`
- `KERNEL32!CreateFileW` at `0x18007cc69`
- `KERNEL32!CreateFileW` at `0x18007cc69`
- `KERNEL32!GetFileAttributesW` at `0x18007cc95`
- `KERNEL32!GetFileAttributesW` at `0x18007cc95`
- `ntdll!RtlRaiseStatus` at `0x18007cd6e`
- `ntdll!RtlRaiseStatus` at `0x18007cd6e`

## string_xrefs

- `0x18007ccd9`: `onecore\base\servicing\overlayutil\mount.cpp`
- `0x18007cd83`: `onecore\base\servicing\overlayutil\mount.cpp`
- `0x18007cce4`: `DirectoryExists`
- `0x18007cd8e`: `DirectoryExists`

## pseudocode

```c
__int64 __fastcall DirectoryExists(LPCWSTR *a1, _BYTE *a2)
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
        v15[2] = 197;
        v15[0] = "onecore\\base\\servicing\\overlayutil\\mount.cpp";
        v15[1] = "DirectoryExists";
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
    if ( (FileAttributesW & 0x10) != 0 )
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
  v14[2] = 188;
  v14[0] = "onecore\\base\\servicing\\overlayutil\\mount.cpp";
  v14[1] = "DirectoryExists";
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
0x18007cbe8  mov     [rsp-8+arg_10], rbx
0x18007cbed  push    rbp
0x18007cbee  push    rsi
0x18007cbef  push    rdi
0x18007cbf0  lea     rbp, [rsp-47h]
0x18007cbf5  sub     rsp, 0B0h
0x18007cbfc  mov     rax, cs:__security_cookie
0x18007cc03  xor     rax, rsp
0x18007cc06  mov     [rbp+57h+var_20], rax
0x18007cc0a  mov     rsi, rcx
0x18007cc0d  mov     [rbp+57h+var_38], 0
0x18007cc14  lea     rcx, [rbp+57h+var_30]; this
0x18007cc18  mov     byte ptr [rdx], 0
0x18007cc1b  mov     rdi, rdx
0x18007cc1e  mov     [rbp+57h+var_30], 0
0x18007cc26  mov     [rbp+57h+var_28], 0
0x18007cc2a  call    ?Acquire@BackupRestoreVolumePrivilegeAcquisition@RtlSystemUtil@@QEAAJXZ; RtlSystemUtil::BackupRestoreVolumePrivilegeAcquisition::Acquire(void)
0x18007cc2f  mov     ebx, eax
0x18007cc31  test    eax, eax
0x18007cc33  js      loc_18007CDCC
0x18007cc39  mov     rcx, [rsi]; lpFileName
0x18007cc3c  xor     r9d, r9d; lpSecurityAttributes
0x18007cc3f  mov     [rsp+0C0h+hTemplateFile], 0; hTemplateFile
0x18007cc48  mov     edx, 80000000h; dwDesiredAccess
0x18007cc4d  mov     [rsp+0C0h+dwFlagsAndAttributes], 2000000h; dwFlagsAndAttributes
0x18007cc55  mov     [rbp+57h+var_80], 0
0x18007cc5d  lea     r8d, [r9+7]; dwShareMode
0x18007cc61  mov     [rsp+0C0h+dwCreationDisposition], 3; dwCreationDisposition
0x18007cc69  call    cs:__imp_CreateFileW
0x18007cc70  nop     dword ptr [rax+rax+00h]
0x18007cc75  mov     rdx, rax
0x18007cc78  lea     rcx, [rbp+57h+var_80]
0x18007cc7c  call    ?TakeOwnership@?$AutoGenericHandleBase@PEAX$00V?$AutoGenericHandle@PEAX$00$1?CloseWithNtCloseHandle@Detail@Windows@@YAXPEAX@Z@Windows@@@Windows@@QEAAXPEAX@Z; Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&Windows::Detail::CloseWithNtCloseHandle(void *)>>::TakeOwnership(void *)
0x18007cc81  mov     rax, [rbp+57h+var_80]
0x18007cc85  dec     rax
0x18007cc88  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18007cc8c  ja      loc_18007CD4D
0x18007cc92  mov     rcx, [rsi]; lpFileName
0x18007cc95  call    cs:__imp_GetFileAttributesW
0x18007cc9c  nop     dword ptr [rax+rax+00h]
0x18007cca1  cmp     eax, 0FFFFFFFFh
0x18007cca4  jnz     short loc_18007CD12
0x18007cca6  call    cs:__imp_GetLastError
0x18007ccad  nop     dword ptr [rax+rax+00h]
0x18007ccb2  test    eax, eax
0x18007ccb4  jnz     short loc_18007CCBD
0x18007ccb6  mov     eax, 36FDh
0x18007ccbb  jmp     short loc_18007CCD1
0x18007ccbd  call    cs:__imp_GetLastError
0x18007ccc4  nop     dword ptr [rax+rax+00h]
0x18007ccc9  test    eax, eax
0x18007cccb  jz      loc_18007CD69
0x18007ccd1  mov     [rbp+57h+var_68], 0BCh
0x18007ccd9  lea     rcx, aOnecoreBaseSer_0; "onecore\\base\\servicing\\overlayutil\\"...
0x18007cce0  mov     [rbp+57h+var_78], rcx
0x18007cce4  lea     rcx, aDirectoryexist; "DirectoryExists"
0x18007cceb  mov     [rbp+57h+var_70], rcx
0x18007ccef  lea     rcx, aGetlasterror; "GetLastError"
0x18007ccf6  mov     [rbp+57h+var_60], rcx
0x18007ccfa  test    eax, eax
0x18007ccfc  jle     short loc_18007CD06
0x18007ccfe  movzx   eax, ax
0x18007cd01  or      eax, 80070000h
0x18007cd06  mov     r8d, eax
0x18007cd09  lea     rdx, [rbp+57h+var_78]
0x18007cd0d  jmp     loc_18007CDB8
0x18007cd12  test    al, 10h
0x18007cd14  jz      short loc_18007CD19
0x18007cd16  mov     byte ptr [rdi], 1
0x18007cd19  lea     rcx, [rbp+57h+var_80]
0x18007cd1d  call    ?Close@?$AutoGenericHandleBase@PEAX$00V?$AutoGenericHandle@PEAX$00$1?CloseWithNtCloseHandle@Detail@Windows@@YAXPEAX@Z@Windows@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&Windows::Detail::CloseWithNtCloseHandle(void *)>>::Close(void)
0x18007cd22  lea     rcx, [rbp+57h+var_30]; this
0x18007cd26  call    ??1PrivilegeAcquisition@RtlSystemUtil@@QEAA@XZ; RtlSystemUtil::PrivilegeAcquisition::~PrivilegeAcquisition(void)
0x18007cd2b  xor     eax, eax
0x18007cd2d  mov     rcx, [rbp+57h+var_20]
0x18007cd31  xor     rcx, rsp; StackCookie
0x18007cd34  call    __security_check_cookie
0x18007cd39  mov     rbx, [rsp+0C0h+arg_10]
0x18007cd41  add     rsp, 0B0h
0x18007cd48  pop     rdi
0x18007cd49  pop     rsi
0x18007cd4a  pop     rbp
0x18007cd4b  retn
0x18007cd4d  call    cs:__imp_GetLastError
0x18007cd54  nop     dword ptr [rax+rax+00h]
0x18007cd59  mov     r8d, eax
0x18007cd5c  add     eax, 0FFFFFFFEh
0x18007cd5f  cmp     eax, 1
0x18007cd62  jbe     short loc_18007CD19
0x18007cd64  test    r8d, r8d
0x18007cd67  jnz     short loc_18007CD7B
0x18007cd69  mov     ecx, 0C00000E5h; Status
0x18007cd6e  call    cs:__imp_RtlRaiseStatus
0x18007cd75  nop     dword ptr [rax+rax+00h]
0x18007cd7a  int     3; Trap to Debugger
0x18007cd7b  mov     [rbp+57h+var_48], 0C5h
0x18007cd83  lea     rcx, aOnecoreBaseSer_0; "onecore\\base\\servicing\\overlayutil\\"...
0x18007cd8a  mov     [rbp+57h+var_58], rcx
0x18007cd8e  lea     rcx, aDirectoryexist; "DirectoryExists"
0x18007cd95  mov     [rbp+57h+var_50], rcx
0x18007cd99  lea     rax, aLasterr; "__lastErr"
0x18007cda0  mov     [rbp+57h+var_40], rax
0x18007cda4  test    r8d, r8d
0x18007cda7  jle     short loc_18007CDB4
0x18007cda9  movzx   r8d, r8w
0x18007cdad  or      r8d, 80070000h
0x18007cdb4  lea     rdx, [rbp+57h+var_58]
0x18007cdb8  lea     rcx, [rbp+57h+var_38]
0x18007cdbc  call    ?OriginateHResult@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@J@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateHResult(Windows::ErrorHandling::_RTL_CALL_SITE const &,long)
0x18007cdc1  lea     rcx, [rbp+57h+var_80]
0x18007cdc5  mov     ebx, eax
0x18007cdc7  call    ?Close@?$AutoGenericHandleBase@PEAX$00V?$AutoGenericHandle@PEAX$00$1?CloseWithNtCloseHandle@Detail@Windows@@YAXPEAX@Z@Windows@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&Windows::Detail::CloseWithNtCloseHandle(void *)>>::Close(void)
0x18007cdcc  lea     rcx, [rbp+57h+var_30]; this
0x18007cdd0  call    ??1PrivilegeAcquisition@RtlSystemUtil@@QEAA@XZ; RtlSystemUtil::PrivilegeAcquisition::~PrivilegeAcquisition(void)
0x18007cdd5  mov     eax, ebx
0x18007cdd7  jmp     loc_18007CD2D
```
