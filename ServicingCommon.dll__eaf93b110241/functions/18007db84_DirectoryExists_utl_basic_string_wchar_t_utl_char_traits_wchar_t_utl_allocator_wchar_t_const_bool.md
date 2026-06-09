# DirectoryExists(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const &,bool &)

- ea: `0x18007db84`
- end: `0x18007dd71`
- name: `?DirectoryExists@@YAJAEBV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@AEA_N@Z`
- size: `493`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, authz_impersonation, installer_update`

## callers

- `0x18007f370`

## callees

- `0x18000ea3c`
- `0x18001fd10`
- `0x1800293a0`
- `0x180044bcc`
- `0x18006c360`
- `0x18007db54`
- `0x18007db84`
- `0x18007e720`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18007dc42`
- `KERNEL32!GetLastError` at `0x18007dc59`
- `KERNEL32!GetLastError` at `0x18007dce9`
- `KERNEL32!GetLastError` at `0x18007dc42`
- `KERNEL32!GetLastError` at `0x18007dc59`
- `KERNEL32!GetLastError` at `0x18007dce9`
- `KERNEL32!CreateFileW` at `0x18007dc05`
- `KERNEL32!CreateFileW` at `0x18007dc05`
- `KERNEL32!GetFileAttributesW` at `0x18007dc31`
- `KERNEL32!GetFileAttributesW` at `0x18007dc31`

## string_xrefs

- `0x18007dc75`: `onecore\base\servicing\overlayutil\mount.cpp`
- `0x18007dd0d`: `onecore\base\servicing\overlayutil\mount.cpp`
- `0x18007dc80`: `DirectoryExists`
- `0x18007dd18`: `DirectoryExists`

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
        v15[2] = 197;
        v15[0] = "onecore\\base\\servicing\\overlayutil\\mount.cpp";
        v15[1] = "DirectoryExists";
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
    if ( (FileAttributesW & 0x10) != 0 )
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
    JUMPOUT(0x18007DD70LL);
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
0x18007db84  mov     [rsp-8+arg_10], rbx
0x18007db89  push    rbp
0x18007db8a  push    rsi
0x18007db8b  push    rdi
0x18007db8c  lea     rbp, [rsp-47h]
0x18007db91  sub     rsp, 0B0h
0x18007db98  mov     rax, cs:__security_cookie
0x18007db9f  xor     rax, rsp
0x18007dba2  mov     [rbp+57h+var_20], rax
0x18007dba6  mov     rsi, rcx
0x18007dba9  mov     [rbp+57h+var_38], 0
0x18007dbb0  lea     rcx, [rbp+57h+var_30]; this
0x18007dbb4  mov     byte ptr [rdx], 0
0x18007dbb7  mov     rdi, rdx
0x18007dbba  mov     [rbp+57h+var_30], 0
0x18007dbc2  mov     [rbp+57h+var_28], 0
0x18007dbc6  call    ?Acquire@BackupRestoreVolumePrivilegeAcquisition@RtlSystemUtil@@QEAAJXZ; RtlSystemUtil::BackupRestoreVolumePrivilegeAcquisition::Acquire(void)
0x18007dbcb  mov     ebx, eax
0x18007dbcd  test    eax, eax
0x18007dbcf  js      loc_18007DD56
0x18007dbd5  mov     rcx, [rsi]; lpFileName
0x18007dbd8  xor     r9d, r9d; lpSecurityAttributes
0x18007dbdb  mov     [rsp+0C0h+hTemplateFile], 0; hTemplateFile
0x18007dbe4  mov     edx, 80000000h; dwDesiredAccess
0x18007dbe9  mov     [rsp+0C0h+dwFlagsAndAttributes], 2000000h; dwFlagsAndAttributes
0x18007dbf1  mov     [rbp+57h+var_80], 0
0x18007dbf9  lea     r8d, [r9+7]; dwShareMode
0x18007dbfd  mov     [rsp+0C0h+dwCreationDisposition], 3; dwCreationDisposition
0x18007dc05  call    cs:__imp_CreateFileW
0x18007dc0c  nop     dword ptr [rax+rax+00h]
0x18007dc11  mov     rdx, rax
0x18007dc14  lea     rcx, [rbp+57h+var_80]
0x18007dc18  call    ?TakeOwnership@?$AutoGenericHandleBase@PEAX$00V?$AutoGenericHandle@PEAX$00$1?CloseWithNtCloseHandle@Detail@Windows@@YAXPEAX@Z@Windows@@@Windows@@QEAAXPEAX@Z; Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&Windows::Detail::CloseWithNtCloseHandle(void *)>>::TakeOwnership(void *)
0x18007dc1d  mov     rax, [rbp+57h+var_80]
0x18007dc21  dec     rax
0x18007dc24  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18007dc28  ja      loc_18007DCE9
0x18007dc2e  mov     rcx, [rsi]; lpFileName
0x18007dc31  call    cs:__imp_GetFileAttributesW
0x18007dc38  nop     dword ptr [rax+rax+00h]
0x18007dc3d  cmp     eax, 0FFFFFFFFh
0x18007dc40  jnz     short loc_18007DCAE
0x18007dc42  call    cs:__imp_GetLastError
0x18007dc49  nop     dword ptr [rax+rax+00h]
0x18007dc4e  test    eax, eax
0x18007dc50  jnz     short loc_18007DC59
0x18007dc52  mov     eax, 36FDh
0x18007dc57  jmp     short loc_18007DC6D
0x18007dc59  call    cs:__imp_GetLastError
0x18007dc60  nop     dword ptr [rax+rax+00h]
0x18007dc65  test    eax, eax
0x18007dc67  jz      loc_18007DD66
0x18007dc6d  mov     [rbp+57h+var_68], 0BCh
0x18007dc75  lea     rcx, aOnecoreBaseSer_0; "onecore\\base\\servicing\\overlayutil\\"...
0x18007dc7c  mov     [rbp+57h+var_78], rcx
0x18007dc80  lea     rcx, aDirectoryexist; "DirectoryExists"
0x18007dc87  mov     [rbp+57h+var_70], rcx
0x18007dc8b  lea     rcx, aGetlasterror; "GetLastError"
0x18007dc92  mov     [rbp+57h+var_60], rcx
0x18007dc96  test    eax, eax
0x18007dc98  jle     short loc_18007DCA2
0x18007dc9a  movzx   eax, ax
0x18007dc9d  or      eax, 80070000h
0x18007dca2  mov     r8d, eax
0x18007dca5  lea     rdx, [rbp+57h+var_78]
0x18007dca9  jmp     loc_18007DD42
0x18007dcae  test    al, 10h
0x18007dcb0  jz      short loc_18007DCB5
0x18007dcb2  mov     byte ptr [rdi], 1
0x18007dcb5  lea     rcx, [rbp+57h+var_80]
0x18007dcb9  call    ?Close@?$AutoGenericHandleBase@PEAX$00V?$AutoGenericHandle@PEAX$00$1?CloseWithNtCloseHandle@Detail@Windows@@YAXPEAX@Z@Windows@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&Windows::Detail::CloseWithNtCloseHandle(void *)>>::Close(void)
0x18007dcbe  lea     rcx, [rbp+57h+var_30]; this
0x18007dcc2  call    ??1PrivilegeAcquisition@RtlSystemUtil@@QEAA@XZ; RtlSystemUtil::PrivilegeAcquisition::~PrivilegeAcquisition(void)
0x18007dcc7  xor     eax, eax
0x18007dcc9  mov     rcx, [rbp+57h+var_20]
0x18007dccd  xor     rcx, rsp; StackCookie
0x18007dcd0  call    __security_check_cookie
0x18007dcd5  mov     rbx, [rsp+0C0h+arg_10]
0x18007dcdd  add     rsp, 0B0h
0x18007dce4  pop     rdi
0x18007dce5  pop     rsi
0x18007dce6  pop     rbp
0x18007dce7  retn
0x18007dce9  call    cs:__imp_GetLastError
0x18007dcf0  nop     dword ptr [rax+rax+00h]
0x18007dcf5  mov     r8d, eax
0x18007dcf8  add     eax, 0FFFFFFFEh
0x18007dcfb  cmp     eax, 1
0x18007dcfe  jbe     short loc_18007DCB5
0x18007dd00  test    r8d, r8d
0x18007dd03  jz      short loc_18007DD66
0x18007dd05  mov     [rbp+57h+var_48], 0C5h
0x18007dd0d  lea     rcx, aOnecoreBaseSer_0; "onecore\\base\\servicing\\overlayutil\\"...
0x18007dd14  mov     [rbp+57h+var_58], rcx
0x18007dd18  lea     rcx, aDirectoryexist; "DirectoryExists"
0x18007dd1f  mov     [rbp+57h+var_50], rcx
0x18007dd23  lea     rax, aLasterr; "__lastErr"
0x18007dd2a  mov     [rbp+57h+var_40], rax
0x18007dd2e  test    r8d, r8d
0x18007dd31  jle     short loc_18007DD3E
0x18007dd33  movzx   r8d, r8w
0x18007dd37  or      r8d, 80070000h
0x18007dd3e  lea     rdx, [rbp+57h+var_58]
0x18007dd42  lea     rcx, [rbp+57h+var_38]
0x18007dd46  call    ?OriginateHResult@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@J@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateHResult(Windows::ErrorHandling::_RTL_CALL_SITE const &,long)
0x18007dd4b  lea     rcx, [rbp+57h+var_80]
0x18007dd4f  mov     ebx, eax
0x18007dd51  call    ?Close@?$AutoGenericHandleBase@PEAX$00V?$AutoGenericHandle@PEAX$00$1?CloseWithNtCloseHandle@Detail@Windows@@YAXPEAX@Z@Windows@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&Windows::Detail::CloseWithNtCloseHandle(void *)>>::Close(void)
0x18007dd56  lea     rcx, [rbp+57h+var_30]; this
0x18007dd5a  call    ??1PrivilegeAcquisition@RtlSystemUtil@@QEAA@XZ; RtlSystemUtil::PrivilegeAcquisition::~PrivilegeAcquisition(void)
0x18007dd5f  mov     eax, ebx
0x18007dd61  jmp     loc_18007DCC9
0x18007dd66  mov     ecx, 0C00000E5h; int
0x18007dd6b  call    ?INTERNAL_ERROR_ACTION@@YAXJ@Z; INTERNAL_ERROR_ACTION(long)
```
