# WpnUserService::OnStopping(int)

- ea: `0x18000a450`
- end: `0x18000a58f`
- name: `?OnStopping@WpnUserService@@UEAAJH@Z`
- size: `319`
- prototype: `__int64 __fastcall(WpnUserService *this)`
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x180002bc0`
- `0x18000a450`
- `0x18000cad4`
- `0x18000ce58`
- `0x18000e554`
- `0x180012010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18000a479`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18000a479`
- `ntdll!RtlPublishWnfStateData` at `0x18000a4c3`
- `ntdll!RtlPublishWnfStateData` at `0x18000a501`
- `ntdll!RtlPublishWnfStateData` at `0x18000a4c3`
- `ntdll!RtlPublishWnfStateData` at `0x18000a501`
- `combase!__imp_CoReleaseSharedService` at `0x18000a55e`
- `combase!__imp_CoReleaseSharedService` at `0x18000a55e`

## string_xrefs

- `0x18000a4d8`: `onecoreuap\base\diagnosis\platform\notifications\servicehost\userservice\dll\wpnuserservice.cpp`
- `0x18000a516`: `onecoreuap\base\diagnosis\platform\notifications\servicehost\userservice\dll\wpnuserservice.cpp`

## pseudocode

```c
__int64 __fastcall WpnUserService::OnStopping(WpnUserService *this)
{
  unsigned int v2; // eax
  int v3; // eax
  int v4; // eax
  __int64 v5; // rcx
  int v7; // [rsp+30h] [rbp-28h] BYREF
  GUID pguid; // [rsp+38h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  pguid = 0;
  v2 = CoCreateGuid(&pguid);
  LogIfStopSrvFailedAndReturnHr(v2, (char *)this + 8, 4);
  if ( *((_QWORD *)this + 24) )
  {
    v7 = 0;
    v3 = RtlPublishWnfStateData(WNF_WPN_USER_PLATFORM_READY, 0, &v7, 4) | 0x10000000;
    if ( v3 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0xD1,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\servicehost\\userservice\\dll\\wpnuserservice.cpp",
        (const char *)(unsigned int)v3,
        0);
    v4 = RtlPublishWnfStateData(WNF_WPN_USER_IN_SESSION_PLATFORM_READY, 0, 0, 0) | 0x10000000;
    if ( v4 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0xD4,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\servicehost\\userservice\\dll\\wpnuserservice.cpp",
        (const char *)(unsigned int)v4,
        0);
    WpnUserService::_ComCleanupWork(this);
    v5 = *((_QWORD *)this + 24);
    if ( v5 )
    {
      *((_QWORD *)this + 24) = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
    }
    if ( *((_DWORD *)this + 51) )
      CoReleaseSharedService();
  }
  LogIfStopSrvFailedAndReturnHr(0, (char *)this + 8, 5);
  return 0;
}

```

## disassembly

```asm
0x18000a450  mov     [rsp+arg_8], rbx
0x18000a455  push    rdi
0x18000a456  sub     rsp, 50h
0x18000a45a  mov     rax, cs:__security_cookie
0x18000a461  xor     rax, rsp
0x18000a464  mov     [rsp+58h+var_10], rax
0x18000a469  mov     rbx, rcx
0x18000a46c  xorps   xmm0, xmm0
0x18000a46f  movups  xmmword ptr [rsp+58h+pguid.Data1], xmm0
0x18000a474  lea     rcx, [rsp+58h+pguid]; pguid
0x18000a479  call    cs:__imp_CoCreateGuid
0x18000a47f  mov     r8d, 4
0x18000a485  lea     rdx, [rbx+8]
0x18000a489  mov     ecx, eax
0x18000a48b  call    ?LogIfStopSrvFailedAndReturnHr@@YAJJPEBGW4StopServiceFailureReason@@@Z; LogIfStopSrvFailedAndReturnHr(long,ushort const *,StopServiceFailureReason)
0x18000a490  cmp     qword ptr [rbx+0C0h], 0
0x18000a498  jz      loc_18000A564
0x18000a49e  mov     [rsp+58h+var_28], 0
0x18000a4a6  mov     qword ptr [rsp+58h+var_38], 0; int
0x18000a4af  mov     r9d, 4
0x18000a4b5  lea     r8, [rsp+58h+var_28]
0x18000a4ba  xor     edx, edx
0x18000a4bc  mov     rcx, cs:WNF_WPN_USER_PLATFORM_READY
0x18000a4c3  call    cs:__imp_RtlPublishWnfStateData
0x18000a4c9  or      eax, 10000000h
0x18000a4ce  mov     rcx, [rsp+58h]; this
0x18000a4d3  jge     short loc_18000A4E9
0x18000a4d5  mov     r9d, eax; char *
0x18000a4d8  lea     r8, aOnecoreuapBase; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18000a4df  mov     edx, 0D1h; void *
0x18000a4e4  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18000a4e9  mov     qword ptr [rsp+58h+var_38], 0; int
0x18000a4f2  xor     r9d, r9d
0x18000a4f5  xor     r8d, r8d
0x18000a4f8  xor     edx, edx
0x18000a4fa  mov     rcx, cs:WNF_WPN_USER_IN_SESSION_PLATFORM_READY
0x18000a501  call    cs:__imp_RtlPublishWnfStateData
0x18000a507  or      eax, 10000000h
0x18000a50c  mov     rcx, [rsp+58h]; this
0x18000a511  jge     short loc_18000A527
0x18000a513  mov     r9d, eax; char *
0x18000a516  lea     r8, aOnecoreuapBase; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18000a51d  mov     edx, 0D4h; void *
0x18000a522  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18000a527  mov     rcx, rbx; this
0x18000a52a  call    ?_ComCleanupWork@WpnUserService@@AEAAXXZ; WpnUserService::_ComCleanupWork(void)
0x18000a52f  nop
0x18000a530  mov     rcx, [rbx+0C0h]
0x18000a537  test    rcx, rcx
0x18000a53a  jz      short loc_18000A554
0x18000a53c  mov     qword ptr [rbx+0C0h], 0
0x18000a547  mov     rax, [rcx]
0x18000a54a  mov     rax, [rax+10h]
0x18000a54e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a553  nop
0x18000a554  mov     ecx, [rbx+0CCh]
0x18000a55a  test    ecx, ecx
0x18000a55c  jz      short loc_18000A564
0x18000a55e  call    cs:__imp_CoReleaseSharedService
0x18000a564  mov     r8d, 5
0x18000a56a  lea     rdx, [rbx+8]
0x18000a56e  xor     ecx, ecx
0x18000a570  call    ?LogIfStopSrvFailedAndReturnHr@@YAJJPEBGW4StopServiceFailureReason@@@Z; LogIfStopSrvFailedAndReturnHr(long,ushort const *,StopServiceFailureReason)
0x18000a575  xor     eax, eax
0x18000a577  mov     rcx, [rsp+58h+var_10]
0x18000a57c  xor     rcx, rsp; StackCookie
0x18000a57f  call    __security_check_cookie
0x18000a584  mov     rbx, [rsp+58h+arg_8]
0x18000a589  add     rsp, 50h
0x18000a58d  pop     rdi
0x18000a58e  retn
```
