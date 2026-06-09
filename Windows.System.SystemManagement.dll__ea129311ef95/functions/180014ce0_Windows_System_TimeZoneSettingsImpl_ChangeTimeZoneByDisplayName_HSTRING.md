# Windows::System::TimeZoneSettingsImpl::ChangeTimeZoneByDisplayName(HSTRING__ *)

- ea: `0x180014ce0`
- end: `0x180014e7b`
- name: `?ChangeTimeZoneByDisplayName@TimeZoneSettingsImpl@System@Windows@@UEAAJPEAUHSTRING__@@@Z`
- size: `411`
- prototype: `__int64 __fastcall(Windows::System::TimeZoneSettingsImpl *__hidden this, HSTRING)`
- caller_count: `0`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callees

- `0x180002dc0`
- `0x18000d0a4`
- `0x18000ed24`
- `0x18000f824`
- `0x1800146a0`
- `0x180014ce0`
- `0x180016d38`
- `0x18001c6a8`
- `0x18002b010`

## import_xrefs

- `ntdll!RtlAcquirePrivilege` at `0x180014dd8`
- `ntdll!RtlAcquirePrivilege` at `0x180014dd8`
- `ntdll!RtlReleasePrivilege` at `0x180014e1b`
- `ntdll!RtlReleasePrivilege` at `0x180014e1b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014df5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014df5`
- `api-ms-win-core-timezone-l1-1-0!SetDynamicTimeZoneInformation` at `0x180014deb`
- `api-ms-win-core-timezone-l1-1-0!SetDynamicTimeZoneInformation` at `0x180014deb`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::System::TimeZoneSettingsImpl::ChangeTimeZoneByDisplayName(
        Windows::System::TimeZoneSettingsImpl *this,
        HSTRING a2)
{
  int HasSystemManagementCapability; // ebx
  const DYNAMIC_TIME_ZONE_INFORMATION *v5; // rdi
  NTSTATUS v6; // eax
  signed int LastError; // eax
  int v9; // [rsp+20h] [rbp-E0h]
  unsigned __int8 v10; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v11[3]; // [rsp+31h] [rbp-CFh] BYREF
  unsigned int v12; // [rsp+34h] [rbp-CCh] BYREF
  ULONG Privilege; // [rsp+38h] [rbp-C8h] BYREF
  PVOID ReturnedState; // [rsp+40h] [rbp-C0h] BYREF
  _QWORD v15[42]; // [rsp+50h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1C8h] [rbp+C8h]

  v12 = 0;
  v11[0] = 0;
  ReturnedState = 0;
  Privilege = 34;
  v10 = 0;
  wil::ActivityBase<Windows::System::SysAdminTraceLoggingProvider,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<Windows::System::SysAdminTraceLoggingProvider,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>(
    v15,
    "ChangeTimeZoneByDisplayNameActivity");
  v15[0] = &Windows::System::SysAdminTraceLoggingProvider::ChangeTimeZoneByDisplayNameActivity::`vftable';
  Windows::System::SysAdminTraceLoggingProvider::ChangeTimeZoneByDisplayNameActivity::StartActivity((Windows::System::SysAdminTraceLoggingProvider::ChangeTimeZoneByDisplayNameActivity *)v15);
  HasSystemManagementCapability = Windows::System::SystemManagementUtil::HasSystemManagementCapability(&v10);
  if ( HasSystemManagementCapability >= 0 )
  {
    if ( v10 )
    {
      HasSystemManagementCapability = (*(__int64 (__fastcall **)(_QWORD, HSTRING, unsigned int *, _BYTE *))(**((_QWORD **)this + 8) + 72LL))(
                                        *((_QWORD *)this + 8),
                                        a2,
                                        &v12,
                                        v11);
      if ( HasSystemManagementCapability >= 0 )
      {
        if ( !v11[0] || v12 == -1 )
        {
          HasSystemManagementCapability = -2147024809;
        }
        else
        {
          v5 = *(const DYNAMIC_TIME_ZONE_INFORMATION **)(*((_QWORD *)this + 9) + 8LL * v12);
          if ( v5 )
          {
            v6 = RtlAcquirePrivilege(&Privilege, 1u, 0, &ReturnedState);
            HasSystemManagementCapability = v6 | 0x10000000;
            if ( v6 >= 0 && !SetDynamicTimeZoneInformation(v5) )
            {
              LastError = GetLastError();
              HasSystemManagementCapability = LastError;
              if ( LastError > 0 )
                HasSystemManagementCapability = (unsigned __int16)LastError | 0x80070000;
            }
          }
          else
          {
            HasSystemManagementCapability = -2147418113;
          }
        }
      }
    }
    else
    {
      HasSystemManagementCapability = -2147024891;
    }
  }
  if ( ReturnedState )
    RtlReleasePrivilege(ReturnedState);
  if ( HasSystemManagementCapability < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0xE3,
      (unsigned int)"onecoreuap\\windows\\iot\\winrt\\sysadmin\\lib\\timezonesettings\\timezonesettingsimpl.cpp",
      (const char *)(unsigned int)HasSystemManagementCapability,
      v9);
  wil::ActivityBase<Windows::System::SysAdminTraceLoggingProvider,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(
    v15,
    (unsigned int)HasSystemManagementCapability);
  Windows::System::SysAdminTraceLoggingProvider::ChangeTimeZoneByDisplayNameActivity::~ChangeTimeZoneByDisplayNameActivity((Windows::System::SysAdminTraceLoggingProvider::ChangeTimeZoneByDisplayNameActivity *)v15);
  return (unsigned int)HasSystemManagementCapability;
}

```

## disassembly

```asm
0x180014ce0  mov     [rsp-8+arg_10], rbx
0x180014ce5  push    rbp
0x180014ce6  push    rsi
0x180014ce7  push    rdi
0x180014ce8  lea     rbp, [rsp-0B0h]
0x180014cf0  sub     rsp, 1B0h
0x180014cf7  mov     rax, cs:__security_cookie
0x180014cfe  xor     rax, rsp
0x180014d01  mov     [rbp+0C0h+var_20], rax
0x180014d08  mov     rsi, rdx
0x180014d0b  mov     rdi, rcx
0x180014d0e  mov     [rsp+1C0h+var_18C], 0
0x180014d16  mov     [rsp+1C0h+var_18F], 0
0x180014d1b  mov     [rsp+1C0h+ReturnedState], 0
0x180014d24  mov     [rsp+1C0h+Privilege], 22h ; '"'
0x180014d2c  mov     [rsp+1C0h+var_190], 0
0x180014d31  lea     rdx, aChangetimezone; "ChangeTimeZoneByDisplayNameActivity"
0x180014d38  lea     rcx, [rsp+1C0h+var_170]
0x180014d3d  call    ??0?$ActivityBase@VSysAdminTraceLoggingProvider@System@Windows@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<Windows::System::SysAdminTraceLoggingProvider,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<Windows::System::SysAdminTraceLoggingProvider,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x180014d42  lea     rax, ??_7ChangeTimeZoneByDisplayNameActivity@SysAdminTraceLoggingProvider@System@Windows@@6B@; const Windows::System::SysAdminTraceLoggingProvider::ChangeTimeZoneByDisplayNameActivity::`vftable'
0x180014d49  mov     [rsp+1C0h+var_170], rax
0x180014d4e  lea     rcx, [rsp+1C0h+var_170]; this
0x180014d53  call    ?StartActivity@ChangeTimeZoneByDisplayNameActivity@SysAdminTraceLoggingProvider@System@Windows@@QEAAXXZ; Windows::System::SysAdminTraceLoggingProvider::ChangeTimeZoneByDisplayNameActivity::StartActivity(void)
0x180014d58  nop
0x180014d59  lea     rcx, [rsp+1C0h+var_190]; unsigned __int8 *
0x180014d5e  call    ?HasSystemManagementCapability@SystemManagementUtil@System@Windows@@SAJPEAE@Z; Windows::System::SystemManagementUtil::HasSystemManagementCapability(uchar *)
0x180014d63  mov     ebx, eax
0x180014d65  test    eax, eax
0x180014d67  js      loc_180014E11
0x180014d6d  cmp     [rsp+1C0h+var_190], 0
0x180014d72  jnz     short loc_180014D7E
0x180014d74  mov     ebx, 80070005h
0x180014d79  jmp     loc_180014E11
0x180014d7e  mov     rcx, [rdi+40h]
0x180014d82  mov     rax, [rcx]
0x180014d85  lea     r9, [rsp+1C0h+var_18F]
0x180014d8a  lea     r8, [rsp+1C0h+var_18C]
0x180014d8f  mov     rdx, rsi
0x180014d92  mov     rax, [rax+48h]
0x180014d96  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014d9b  mov     ebx, eax
0x180014d9d  test    eax, eax
0x180014d9f  js      short loc_180014E11
0x180014da1  cmp     [rsp+1C0h+var_18F], 0
0x180014da6  jz      short loc_180014E0C
0x180014da8  cmp     [rsp+1C0h+var_18C], 0FFFFFFFFh
0x180014dad  jz      short loc_180014E0C
0x180014daf  mov     ecx, [rsp+1C0h+var_18C]
0x180014db3  mov     rax, [rdi+48h]
0x180014db7  mov     rdi, [rax+rcx*8]
0x180014dbb  test    rdi, rdi
0x180014dbe  jnz     short loc_180014DC7
0x180014dc0  mov     ebx, 8000FFFFh
0x180014dc5  jmp     short loc_180014E11
0x180014dc7  lea     r9, [rsp+1C0h+ReturnedState]; ReturnedState
0x180014dcc  xor     r8d, r8d; Flags
0x180014dcf  lea     edx, [r8+1]; NumPriv
0x180014dd3  lea     rcx, [rsp+1C0h+Privilege]; Privilege
0x180014dd8  call    cs:__imp_RtlAcquirePrivilege
0x180014dde  mov     ebx, eax
0x180014de0  or      ebx, 10000000h
0x180014de6  jl      short loc_180014E11
0x180014de8  mov     rcx, rdi; lpTimeZoneInformation
0x180014deb  call    cs:__imp_SetDynamicTimeZoneInformation
0x180014df1  test    eax, eax
0x180014df3  jnz     short loc_180014E11
0x180014df5  call    cs:__imp_GetLastError
0x180014dfb  mov     ebx, eax
0x180014dfd  test    eax, eax
0x180014dff  jle     short loc_180014E11
0x180014e01  movzx   ebx, ax
0x180014e04  or      ebx, 80070000h
0x180014e0a  jmp     short loc_180014E11
0x180014e0c  mov     ebx, 80070057h
0x180014e11  mov     rcx, [rsp+1C0h+ReturnedState]; ReturnedState
0x180014e16  test    rcx, rcx
0x180014e19  jz      short loc_180014E21
0x180014e1b  call    cs:__imp_RtlReleasePrivilege
0x180014e21  mov     rcx, [rbp+0C8h]; this
0x180014e28  test    ebx, ebx
0x180014e2a  jns     short loc_180014E40
0x180014e2c  mov     r9d, ebx; char *
0x180014e2f  lea     r8, aOnecoreuapWind_3; "onecoreuap\\windows\\iot\\winrt\\sysadm"...
0x180014e36  mov     edx, 0E3h; void *
0x180014e3b  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180014e40  mov     edx, ebx
0x180014e42  lea     rcx, [rsp+1C0h+var_170]
0x180014e47  call    ?Stop@?$ActivityBase@VSysAdminTraceLoggingProvider@System@Windows@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<Windows::System::SysAdminTraceLoggingProvider,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x180014e4c  nop
0x180014e4d  lea     rcx, [rsp+1C0h+var_170]; this
0x180014e52  call    ??1ChangeTimeZoneByDisplayNameActivity@SysAdminTraceLoggingProvider@System@Windows@@QEAA@XZ; Windows::System::SysAdminTraceLoggingProvider::ChangeTimeZoneByDisplayNameActivity::~ChangeTimeZoneByDisplayNameActivity(void)
0x180014e57  mov     eax, ebx
0x180014e59  mov     rcx, [rbp+0C0h+var_20]
0x180014e60  xor     rcx, rsp; StackCookie
0x180014e63  call    __security_check_cookie
0x180014e68  mov     rbx, [rsp+1C0h+arg_10]
0x180014e70  add     rsp, 1B0h
0x180014e77  pop     rdi
0x180014e78  pop     rsi
0x180014e79  pop     rbp
0x180014e7a  retn
```
