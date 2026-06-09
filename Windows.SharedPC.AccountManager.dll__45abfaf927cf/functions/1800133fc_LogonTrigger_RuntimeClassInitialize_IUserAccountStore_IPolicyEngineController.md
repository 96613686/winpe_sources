# LogonTrigger::RuntimeClassInitialize(IUserAccountStore *,IPolicyEngineController *)

- ea: `0x1800133fc`
- end: `0x180013575`
- name: `?RuntimeClassInitialize@LogonTrigger@@QEAAJPEAUIUserAccountStore@@PEAUIPolicyEngineController@@@Z`
- size: `377`
- prototype: `__int64 __fastcall(LogonTrigger *__hidden this, struct IUserAccountStore *, struct IPolicyEngineController *)`
- caller_count: `1`
- callee_count: `16`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18000edd4`

## callees

- `0x180003530`
- `0x180005120`
- `0x18000a104`
- `0x18000ccd4`
- `0x18000cd50`
- `0x180011be0`
- `0x180012030`
- `0x1800123d4`
- `0x180012658`
- `0x1800126ac`
- `0x180012784`
- `0x18001295c`
- `0x1800133fc`
- `0x180013c28`
- `0x180013dcc`
- `0x180026010`

## string_xrefs

- `0x180013508`: `shellcommon\shell\sharedpc\accountmanager\lib\service\logontrigger.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3 #try_helpers=1
__int64 __fastcall LogonTrigger::RuntimeClassInitialize(
        LogonTrigger *this,
        struct IUserAccountStore *a2,
        struct IPolicyEngineController *a3)
{
  _QWORD *v5; // rcx
  __int128 *v6; // rbx
  __int128 *v7; // r14
  __int64 StringSidFromSessionUser; // rax
  __int64 v9; // rcx
  __int64 v10; // rdx
  const unsigned __int16 *v11; // rax
  int updated; // eax
  int v14[4]; // [rsp+20h] [rbp-98h] BYREF
  _QWORD v15[3]; // [rsp+30h] [rbp-88h] BYREF
  __int128 v16; // [rsp+48h] [rbp-70h] BYREF
  _BYTE v17[32]; // [rsp+58h] [rbp-60h] BYREF
  _BYTE v18[32]; // [rsp+78h] [rbp-40h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+0h]

  Microsoft::WRL::ComPtr<IUserAccountStore>::operator=((__int64 *)this + 6, (__int64)a2);
  if ( *((struct IPolicyEngineController **)this + 7) != a3 )
  {
    if ( a3 )
      (*(void (__fastcall **)(struct IPolicyEngineController *))(*(_QWORD *)a3 + 8LL))(a3);
    *(_QWORD *)v14 = *((_QWORD *)this + 7);
    *((_QWORD *)this + 7) = a3;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v14);
  }
  LogonTrigger::GetCurrentSessionUsers(v15);
  v5 = (_QWORD *)v15[0];
  v6 = (__int128 *)v15[0];
  v7 = (__int128 *)v15[1];
  while ( v6 != v7 )
  {
    std::wstring::wstring(v17);
    v16 = *v6;
    *(_OWORD *)v14 = v16;
    StringSidFromSessionUser = LogonTrigger::GetStringSidFromSessionUser((__int64)v18, (__int64)v14);
    std::wstring::operator=(v17, StringSidFromSessionUser);
    std::wstring::_Tidy_deallocate((__int64)v18);
    v10 = *((_QWORD *)this + 9);
    if ( v10 == *((_QWORD *)this + 10) )
    {
      std::vector<SessionUserInfo>::_Emplace_reallocate<SessionUserInfo const &>((char *)this + 64, v10, &v16);
    }
    else
    {
      std::_Default_allocator_traits<std::allocator<SessionUserInfo>>::construct<SessionUserInfo,SessionUserInfo const &>(
        v9,
        v10,
        &v16);
      *((_QWORD *)this + 9) += 48LL;
    }
    v11 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr();
    updated = LogonTrigger::UpdateUserAccessTime(this, v11);
    if ( updated < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x25,
        (int)"shellcommon\\shell\\sharedpc\\accountmanager\\lib\\service\\logontrigger.cpp",
        (const char *)(unsigned int)updated,
        v14[0]);
    std::wstring::_Tidy_deallocate((__int64)v17);
    ++v6;
    v5 = (_QWORD *)v15[0];
  }
  if ( v5 )
    std::_Deallocate<16>(v5, (v15[2] - (_QWORD)v5) & 0xFFFFFFFFFFFFFFF0uLL);
  return 0;
}

```

## disassembly

```asm
0x1800133fc  mov     [rsp+arg_10], rbx
0x180013401  push    rsi
0x180013402  push    rdi
0x180013403  push    r14
0x180013405  sub     rsp, 0A0h
0x18001340c  mov     rax, cs:__security_cookie
0x180013413  xor     rax, rsp
0x180013416  mov     [rsp+0B8h+var_20], rax
0x18001341e  mov     rbx, r8
0x180013421  mov     rdi, rcx
0x180013424  add     rcx, 30h ; '0'
0x180013428  call    ??4?$ComPtr@UIUserAccountStore@@@WRL@Microsoft@@QEAAAEAV012@PEAUIUserAccountStore@@@Z; Microsoft::WRL::ComPtr<IUserAccountStore>::operator=(IUserAccountStore *)
0x18001342d  cmp     [rdi+38h], rbx
0x180013431  jz      short loc_18001345F
0x180013433  test    rbx, rbx
0x180013436  jz      short loc_180013448
0x180013438  mov     rax, [rbx]
0x18001343b  mov     rcx, rbx
0x18001343e  mov     rax, [rax+8]
0x180013442  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013447  nop
0x180013448  mov     rax, [rdi+38h]
0x18001344c  mov     qword ptr [rsp+0B8h+var_98], rax
0x180013451  mov     [rdi+38h], rbx
0x180013455  lea     rcx, [rsp+0B8h+var_98]
0x18001345a  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001345f  lea     rcx, [rsp+0B8h+var_88]
0x180013464  call    ?GetCurrentSessionUsers@LogonTrigger@@SA?AV?$vector@U_SESSION_USER_CONTEXT@@V?$allocator@U_SESSION_USER_CONTEXT@@@std@@@std@@XZ; LogonTrigger::GetCurrentSessionUsers(void)
0x180013469  nop
0x18001346a  mov     rcx, [rsp+0B8h+var_88]
0x18001346f  mov     rbx, rcx
0x180013472  mov     r14, [rsp+0B8h+var_80]
0x180013477  cmp     rbx, r14
0x18001347a  jz      loc_180013532
0x180013480  lea     rcx, [rsp+0B8h+var_60]
0x180013485  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18001348a  nop
0x18001348b  movups  xmm1, xmmword ptr [rbx]
0x18001348e  movdqu  [rsp+0B8h+var_70], xmm1
0x180013494  movdqu  xmmword ptr [rsp+0B8h+var_98], xmm1; int
0x18001349a  lea     rdx, [rsp+0B8h+var_98]
0x18001349f  lea     rcx, [rsp+0B8h+var_40]
0x1800134a4  call    ?GetStringSidFromSessionUser@LogonTrigger@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_SESSION_USER_CONTEXT@@@Z; LogonTrigger::GetStringSidFromSessionUser(_SESSION_USER_CONTEXT)
0x1800134a9  mov     rdx, rax
0x1800134ac  lea     rcx, [rsp+0B8h+var_60]
0x1800134b1  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1800134b6  lea     rcx, [rsp+0B8h+var_40]
0x1800134bb  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800134c0  mov     rdx, [rdi+48h]
0x1800134c4  lea     r8, [rsp+0B8h+var_70]
0x1800134c9  cmp     rdx, [rdi+50h]
0x1800134cd  jz      short loc_1800134DB
0x1800134cf  call    ??$construct@USessionUserInfo@@AEBU1@@?$_Default_allocator_traits@V?$allocator@USessionUserInfo@@@std@@@std@@SAXAEAV?$allocator@USessionUserInfo@@@1@QEAUSessionUserInfo@@AEBU3@@Z; std::_Default_allocator_traits<std::allocator<SessionUserInfo>>::construct<SessionUserInfo,SessionUserInfo const &>(std::allocator<SessionUserInfo> &,SessionUserInfo * const,SessionUserInfo const &)
0x1800134d4  add     qword ptr [rdi+48h], 30h ; '0'
0x1800134d9  jmp     short loc_1800134E4
0x1800134db  lea     rcx, [rdi+40h]
0x1800134df  call    ??$_Emplace_reallocate@AEBUSessionUserInfo@@@?$vector@USessionUserInfo@@V?$allocator@USessionUserInfo@@@std@@@std@@AEAAPEAUSessionUserInfo@@QEAU2@AEBU2@@Z; std::vector<SessionUserInfo>::_Emplace_reallocate<SessionUserInfo const &>(SessionUserInfo * const,SessionUserInfo const &)
0x1800134e4  lea     rcx, [rsp+0B8h+var_60]
0x1800134e9  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800134ee  mov     rdx, rax; unsigned __int16 *
0x1800134f1  mov     rcx, rdi; this
0x1800134f4  call    ?UpdateUserAccessTime@LogonTrigger@@QEAAJPEBG@Z; LogonTrigger::UpdateUserAccessTime(ushort const *)
0x1800134f9  mov     rcx, [rsp+0B8h]; this
0x180013501  test    eax, eax
0x180013503  jns     short loc_18001351A
0x180013505  mov     r9d, eax; char *
0x180013508  lea     r8, aShellcommonShe_11; "shellcommon\\shell\\sharedpc\\accountma"...
0x18001350f  mov     edx, 25h ; '%'; void *
0x180013514  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18001351a  lea     rcx, [rsp+0B8h+var_60]
0x18001351f  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180013524  add     rbx, 10h
0x180013528  mov     rcx, [rsp+0B8h+var_88]
0x18001352d  jmp     loc_180013477
0x180013532  test    rcx, rcx
0x180013535  jz      short loc_180013548
0x180013537  mov     rdx, [rsp+0B8h+var_78]
0x18001353c  sub     rdx, rcx
0x18001353f  and     rdx, 0FFFFFFFFFFFFFFF0h
0x180013543  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180013548  xor     eax, eax
0x18001354a  jmp     short loc_180013550
0x18001354c  mov     eax, [rsp+0B8h+var_98]
0x180013550  mov     rcx, [rsp+0B8h+var_20]
0x180013558  xor     rcx, rsp; StackCookie
0x18001355b  call    __security_check_cookie
0x180013560  mov     rbx, [rsp+0B8h+arg_10]
0x180013568  add     rsp, 0A0h
0x18001356f  pop     r14
0x180013571  pop     rdi
0x180013572  pop     rsi
0x180013573  retn
```
