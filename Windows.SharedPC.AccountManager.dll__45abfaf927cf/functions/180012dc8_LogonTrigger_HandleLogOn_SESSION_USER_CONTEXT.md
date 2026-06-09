# LogonTrigger::HandleLogOn(_SESSION_USER_CONTEXT)

- ea: `0x180012dc8`
- end: `0x180012f5d`
- name: `?HandleLogOn@LogonTrigger@@QEAAXU_SESSION_USER_CONTEXT@@@Z`
- size: `405`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `17`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1800114d0`

## callees

- `0x180003530`
- `0x18000a5c4`
- `0x18000ccd4`
- `0x18000cd50`
- `0x180011be0`
- `0x180012030`
- `0x180012294`
- `0x1800123d4`
- `0x1800125c4`
- `0x1800126ac`
- `0x18001295c`
- `0x180012dc8`
- `0x180013040`
- `0x180013628`
- `0x1800136d4`
- `0x180013c28`
- `0x180013dcc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180012e6a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180012e6a`

## string_xrefs

- `0x180012efe`: `shellcommon\shell\sharedpc\accountmanager\lib\service\logontrigger.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall LogonTrigger::HandleLogOn(RTL_SRWLOCK *a1, __int128 *a2)
{
  __int64 StringSidFromSessionUser; // rax
  _DWORD *Ptr; // rcx
  __int64 v6; // rcx
  PVOID v7; // rdx
  const unsigned __int16 *v8; // rax
  int updated; // eax
  const char *v10; // r9
  int v11[4]; // [rsp+20h] [rbp-1C8h] BYREF
  __int128 v12; // [rsp+30h] [rbp-1B8h] BYREF
  _BYTE v13[32]; // [rsp+40h] [rbp-1A8h] BYREF
  _BYTE v14[32]; // [rsp+60h] [rbp-188h] BYREF
  _QWORD v15[42]; // [rsp+80h] [rbp-168h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1E8h] [rbp+0h]

  wil::ActivityBase<SharedPCAccountManagerLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<SharedPCAccountManagerLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(
    (__int64)v15,
    (__int64)"HandleLogOn");
  v15[0] = &SharedPCAccountManagerTelemetry::HandleLogOn::`vftable';
  SharedPCAccountManagerTelemetry::HandleLogOn::StartActivity((SharedPCAccountManagerTelemetry::HandleLogOn *)v15);
  std::wstring::wstring(v13);
  v12 = *a2;
  *(_OWORD *)v11 = v12;
  try
  {
    StringSidFromSessionUser = LogonTrigger::GetStringSidFromSessionUser((__int64)v14, (__int64)v11);
    std::wstring::operator=(v13, StringSidFromSessionUser);
    std::wstring::_Tidy_deallocate((__int64)v14);
    AcquireSRWLockExclusive(a1 + 5);
    *(_QWORD *)v11 = a1 + 5;
    Ptr = a1[8].Ptr;
    if ( Ptr == a1[9].Ptr )
      goto LABEL_21;
    do
    {
      if ( Ptr[2] == *((_DWORD *)a2 + 2) && *(_QWORD *)Ptr == *(_QWORD *)a2 )
        break;
      Ptr += 12;
    }
    while ( Ptr != a1[9].Ptr );
    if ( Ptr == a1[9].Ptr )
    {
LABEL_21:
      if ( !IsWCOSSpecialAccount((const struct _SESSION_USER_CONTEXT *)a2) )
      {
        v7 = a1[9].Ptr;
        if ( v7 == a1[10].Ptr )
        {
          std::vector<SessionUserInfo>::_Emplace_reallocate<SessionUserInfo const &>(&a1[8], v7, &v12);
        }
        else
        {
          std::_Default_allocator_traits<std::allocator<SessionUserInfo>>::construct<SessionUserInfo,SessionUserInfo const &>(
            v6,
            v7,
            &v12);
          a1[9].Ptr = (char *)a1[9].Ptr + 48;
        }
      }
    }
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>((RTL_SRWLOCK **)v11);
    v8 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr();
    updated = LogonTrigger::UpdateUserAccessTime((LogonTrigger *)a1, v8);
    if ( updated < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x4B,
        (int)"shellcommon\\shell\\sharedpc\\accountmanager\\lib\\service\\logontrigger.cpp",
        (const char *)(unsigned int)updated,
        v11[0]);
    wil::ActivityBase<SharedPCAccountManagerLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(v15);
    std::wstring::_Tidy_deallocate((__int64)v13);
    SharedPCAccountManagerTelemetry::HandleLogOn::~HandleLogOn((SharedPCAccountManagerTelemetry::HandleLogOn *)v15);
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtException(
      retaddr,
      (void *)0x4E,
      (unsigned int)"shellcommon\\shell\\sharedpc\\accountmanager\\lib\\service\\logontrigger.cpp",
      v10);
  }
}

```

## disassembly

```asm
0x180012dc8  mov     [rsp+arg_10], rbx
0x180012dcd  mov     [rsp+arg_18], rsi
0x180012dd2  push    rdi
0x180012dd3  sub     rsp, 1E0h
0x180012dda  mov     rax, cs:__security_cookie
0x180012de1  xor     rax, rsp
0x180012de4  mov     [rsp+1E8h+var_18], rax
0x180012dec  mov     rdi, rdx
0x180012def  mov     rsi, rcx
0x180012df2  lea     rdx, aHandlelogon; "HandleLogOn"
0x180012df9  lea     rcx, [rsp+1E8h+var_168]
0x180012e01  call    ??0?$ActivityBase@VSharedPCAccountManagerLogging@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<SharedPCAccountManagerLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<SharedPCAccountManagerLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x180012e06  lea     rax, ??_7HandleLogOn@SharedPCAccountManagerTelemetry@@6B@; const SharedPCAccountManagerTelemetry::HandleLogOn::`vftable'
0x180012e0d  mov     [rsp+1E8h+var_168], rax
0x180012e15  lea     rcx, [rsp+1E8h+var_168]; this
0x180012e1d  call    ?StartActivity@HandleLogOn@SharedPCAccountManagerTelemetry@@QEAAXXZ; SharedPCAccountManagerTelemetry::HandleLogOn::StartActivity(void)
0x180012e22  nop
0x180012e23  lea     rcx, [rsp+1E8h+var_1A8]
0x180012e28  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180012e2d  nop
0x180012e2e  movaps  xmm1, xmmword ptr [rdi]
0x180012e31  movdqu  [rsp+1E8h+var_1B8], xmm1
0x180012e37  movdqa  xmmword ptr [rsp+1E8h+var_1C8], xmm1
0x180012e3d  lea     rdx, [rsp+1E8h+var_1C8]
0x180012e42  lea     rcx, [rsp+1E8h+var_188]
0x180012e47  call    ?GetStringSidFromSessionUser@LogonTrigger@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_SESSION_USER_CONTEXT@@@Z; LogonTrigger::GetStringSidFromSessionUser(_SESSION_USER_CONTEXT)
0x180012e4c  mov     rdx, rax
0x180012e4f  lea     rcx, [rsp+1E8h+var_1A8]
0x180012e54  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180012e59  lea     rcx, [rsp+1E8h+var_188]
0x180012e5e  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180012e63  lea     rbx, [rsi+28h]
0x180012e67  mov     rcx, rbx; SRWLock
0x180012e6a  call    cs:__imp_AcquireSRWLockExclusive
0x180012e70  mov     qword ptr [rsp+1E8h+var_1C8], rbx; int
0x180012e75  mov     rcx, [rsi+40h]
0x180012e79  cmp     rcx, [rsi+48h]
0x180012e7d  jz      short loc_180012E9F
0x180012e7f  mov     edx, [rdi+8]
0x180012e82  cmp     [rcx+8], edx
0x180012e85  jnz     short loc_180012E8F
0x180012e87  mov     rax, [rdi]
0x180012e8a  cmp     [rcx], rax
0x180012e8d  jz      short loc_180012E99
0x180012e8f  add     rcx, 30h ; '0'
0x180012e93  cmp     rcx, [rsi+48h]
0x180012e97  jnz     short loc_180012E82
0x180012e99  cmp     rcx, [rsi+48h]
0x180012e9d  jnz     short loc_180012ED0
0x180012e9f  mov     rcx, rdi; struct _SESSION_USER_CONTEXT *
0x180012ea2  call    ?IsWCOSSpecialAccount@@YA_NAEBU_SESSION_USER_CONTEXT@@@Z; IsWCOSSpecialAccount(_SESSION_USER_CONTEXT const &)
0x180012ea7  test    al, al
0x180012ea9  jnz     short loc_180012ED0
0x180012eab  mov     rdx, [rsi+48h]
0x180012eaf  lea     r8, [rsp+1E8h+var_1B8]
0x180012eb4  cmp     rdx, [rsi+50h]
0x180012eb8  jz      short loc_180012EC6
0x180012eba  call    ??$construct@USessionUserInfo@@AEBU1@@?$_Default_allocator_traits@V?$allocator@USessionUserInfo@@@std@@@std@@SAXAEAV?$allocator@USessionUserInfo@@@1@QEAUSessionUserInfo@@AEBU3@@Z; std::_Default_allocator_traits<std::allocator<SessionUserInfo>>::construct<SessionUserInfo,SessionUserInfo const &>(std::allocator<SessionUserInfo> &,SessionUserInfo * const,SessionUserInfo const &)
0x180012ebf  add     qword ptr [rsi+48h], 30h ; '0'
0x180012ec4  jmp     short loc_180012ED0
0x180012ec6  lea     rcx, [rsi+40h]
0x180012eca  call    ??$_Emplace_reallocate@AEBUSessionUserInfo@@@?$vector@USessionUserInfo@@V?$allocator@USessionUserInfo@@@std@@@std@@AEAAPEAUSessionUserInfo@@QEAU2@AEBU2@@Z; std::vector<SessionUserInfo>::_Emplace_reallocate<SessionUserInfo const &>(SessionUserInfo * const,SessionUserInfo const &)
0x180012ecf  nop
0x180012ed0  lea     rcx, [rsp+1E8h+var_1C8]
0x180012ed5  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180012eda  lea     rcx, [rsp+1E8h+var_1A8]
0x180012edf  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180012ee4  mov     rdx, rax; unsigned __int16 *
0x180012ee7  mov     rcx, rsi; this
0x180012eea  call    ?UpdateUserAccessTime@LogonTrigger@@QEAAJPEBG@Z; LogonTrigger::UpdateUserAccessTime(ushort const *)
0x180012eef  mov     rcx, [rsp+1E8h]; this
0x180012ef7  test    eax, eax
0x180012ef9  jns     short loc_180012F0F
0x180012efb  mov     r9d, eax; char *
0x180012efe  lea     r8, aShellcommonShe_11; "shellcommon\\shell\\sharedpc\\accountma"...
0x180012f05  mov     edx, 4Bh ; 'K'; void *
0x180012f0a  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180012f0f  lea     rcx, [rsp+1E8h+var_168]
0x180012f17  call    ?Stop@?$ActivityBase@VSharedPCAccountManagerLogging@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<SharedPCAccountManagerLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x180012f1c  nop
0x180012f1d  lea     rcx, [rsp+1E8h+var_1A8]
0x180012f22  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180012f27  nop
0x180012f28  lea     rcx, [rsp+1E8h+var_168]; this
0x180012f30  call    ??1HandleLogOn@SharedPCAccountManagerTelemetry@@QEAA@XZ; SharedPCAccountManagerTelemetry::HandleLogOn::~HandleLogOn(void)
0x180012f35  nop
0x180012f36  jmp     short $+2
0x180012f38  mov     rcx, [rsp+1E8h+var_18]
0x180012f40  xor     rcx, rsp; StackCookie
0x180012f43  call    __security_check_cookie
0x180012f48  lea     r11, [rsp+1E8h+var_8]
0x180012f50  mov     rbx, [r11+20h]
0x180012f54  mov     rsi, [r11+28h]
0x180012f58  mov     rsp, r11
0x180012f5b  pop     rdi
0x180012f5c  retn
```
