# winrt::Windows::Internal::Shell::implementation::FocusSessionThemeManager::RemoveSession(winrt::guid const &)

- ea: `0x180022f5c`
- end: `0x180023092`
- name: `?RemoveSession@FocusSessionThemeManager@implementation@Shell@Internal@Windows@winrt@@QEAAXAEBUguid@6@@Z`
- size: `310`
- prototype: `void __fastcall(winrt::Windows::Internal::Shell::implementation::FocusSessionThemeManager *__hidden this, const struct winrt::guid *)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180022f30`

## callees

- `0x180003980`
- `0x180008fa8`
- `0x18000dfc0`
- `0x18001ed40`
- `0x18001f304`
- `0x180020460`
- `0x1800207ac`
- `0x180021848`
- `0x1800226ec`
- `0x180022b40`
- `0x180022f5c`
- `0x180024410`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180022f97`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180022f97`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall winrt::Windows::Internal::Shell::implementation::FocusSessionThemeManager::RemoveSession(
        RTL_SRWLOCK *this,
        const struct winrt::guid *a2)
{
  RTL_SRWLOCK *v4; // rbx
  __int64 active; // rax
  __int128 *Ptr; // rbx
  __int128 *v7; // rbp
  char v8; // bl
  RTL_SRWLOCK *v9; // [rsp+30h] [rbp-98h] BYREF
  _BYTE v10[72]; // [rsp+38h] [rbp-90h] BYREF
  __int128 v11; // [rsp+80h] [rbp-48h] BYREF

  v4 = this + 17;
  AcquireSRWLockExclusive(this + 17);
  v9 = v4;
  active = wil::cloud_store::load<Windows::Data::Shell::FocusActiveSessions>(&this[3], v10);
  wil::cloud_store_data<Windows::Data::Shell::FocusActiveSessions>::operator=(&this[8], active);
  wil::cloud_store_data<Windows::Data::Shell::FocusActiveSessions>::~cloud_store_data<Windows::Data::Shell::FocusActiveSessions>(v10);
  Ptr = (__int128 *)this[10].Ptr;
  v7 = (__int128 *)this[11].Ptr;
  while ( Ptr != v7 )
  {
    v11 = *Ptr;
    if ( (unsigned __int8)winrt::Windows::Foundation::GuidHelper::Equals((const struct winrt::guid *)&v11, a2) )
      break;
    Ptr = (__int128 *)((char *)Ptr + 40);
  }
  if ( Ptr == this[11].Ptr )
  {
    v8 = 0;
  }
  else
  {
    std::vector<Windows::Data::Shell::FocusSession>::erase(&this[10], &v11, Ptr);
    wil::cloud_store::save<Windows::Data::Shell::FocusActiveSessions>(&this[3], &v11, &this[8]);
    v8 = 1;
  }
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v9);
  if ( v8 )
  {
    winrt::Windows::Internal::Shell::implementation::FocusSessionThemeManager::OnSessionsChanged((winrt::Windows::Internal::Shell::implementation::FocusSessionThemeManager *)this);
    v9 = 0;
    winrt::Windows::Internal::Shell::implementation::FocusSessionThemeManager::RefreshTimer(
      (winrt::Windows::Internal::Shell::implementation::FocusSessionThemeManager *)this,
      (const struct winrt::Windows::System::Threading::ThreadPoolTimer *)&v9);
    winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(&v9);
  }
}

```

## disassembly

```asm
0x180022f5c  mov     [rsp+arg_8], rbx
0x180022f61  mov     [rsp+arg_10], rbp
0x180022f66  push    rsi
0x180022f67  push    rdi
0x180022f68  push    r12
0x180022f6a  push    r14
0x180022f6c  push    r15
0x180022f6e  sub     rsp, 0A0h
0x180022f75  mov     rax, cs:__security_cookie
0x180022f7c  xor     rax, rsp
0x180022f7f  mov     [rsp+0C8h+var_38], rax
0x180022f87  mov     r12, rdx
0x180022f8a  mov     rdi, rcx
0x180022f8d  lea     rbx, [rcx+88h]
0x180022f94  mov     rcx, rbx; SRWLock
0x180022f97  call    cs:__imp_AcquireSRWLockExclusive
0x180022f9d  mov     [rsp+0C8h+var_98], rbx
0x180022fa2  lea     rdx, [rsp+0C8h+var_90]
0x180022fa7  lea     rcx, [rdi+18h]
0x180022fab  call    ??$load@UFocusActiveSessions@Shell@Data@Windows@@@cloud_store@wil@@QEAA?AV?$cloud_store_data@UFocusActiveSessions@Shell@Data@Windows@@@1@W4cloud_store_load_options@1@PEBD@Z; wil::cloud_store::load<Windows::Data::Shell::FocusActiveSessions>(wil::cloud_store_load_options,char const *)
0x180022fb0  nop
0x180022fb1  mov     rdx, rax
0x180022fb4  lea     rcx, [rdi+40h]
0x180022fb8  call    ??4?$cloud_store_data@UFocusActiveSessions@Shell@Data@Windows@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::cloud_store_data<Windows::Data::Shell::FocusActiveSessions>::operator=(wil::cloud_store_data<Windows::Data::Shell::FocusActiveSessions> &&)
0x180022fbd  nop
0x180022fbe  lea     rcx, [rsp+0C8h+var_90]
0x180022fc3  call    ??1?$cloud_store_data@UFocusActiveSessions@Shell@Data@Windows@@@wil@@QEAA@XZ; wil::cloud_store_data<Windows::Data::Shell::FocusActiveSessions>::~cloud_store_data<Windows::Data::Shell::FocusActiveSessions>(void)
0x180022fc8  mov     rbx, [rdi+50h]
0x180022fcc  mov     rbp, [rdi+58h]
0x180022fd0  jmp     short loc_180022FF6
0x180022fd2  movups  xmm0, xmmword ptr [rbx]
0x180022fd5  movdqa  [rsp+0C8h+var_48], xmm0
0x180022fde  mov     rdx, r12; struct winrt::guid *
0x180022fe1  lea     rcx, [rsp+0C8h+var_48]; struct winrt::guid *
0x180022fe9  call    ?Equals@GuidHelper@Foundation@Windows@winrt@@SA@AEBUguid@4@0@Z; winrt::Windows::Foundation::GuidHelper::Equals(winrt::guid const &,winrt::guid const &)
0x180022fee  test    al, al
0x180022ff0  jnz     short loc_180022FFB
0x180022ff2  add     rbx, 28h ; '('
0x180022ff6  cmp     rbx, rbp
0x180022ff9  jnz     short loc_180022FD2
0x180022ffb  cmp     rbx, [rdi+58h]
0x180022fff  jnz     short loc_180023005
0x180023001  xor     bl, bl
0x180023003  jmp     short loc_180023030
0x180023005  mov     r8, rbx
0x180023008  lea     rdx, [rsp+0C8h+var_48]
0x180023010  lea     rcx, [rdi+50h]
0x180023014  call    ?erase@?$vector@UFocusSession@Shell@Data@Windows@@V?$allocator@UFocusSession@Shell@Data@Windows@@@std@@@std@@QEAA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@UFocusSession@Shell@Data@Windows@@@std@@@std@@@2@V?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@UFocusSession@Shell@Data@Windows@@@std@@@std@@@2@@Z; std::vector<Windows::Data::Shell::FocusSession>::erase(std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<Windows::Data::Shell::FocusSession>>>)
0x180023019  lea     r8, [rdi+40h]
0x18002301d  lea     rdx, [rsp+0C8h+var_48]
0x180023025  lea     rcx, [rdi+18h]
0x180023029  call    ??$save@UFocusActiveSessions@Shell@Data@Windows@@@cloud_store@wil@@QEAA?AVcloud_store_save_result@1@AEBV?$cloud_store_data@UFocusActiveSessions@Shell@Data@Windows@@@1@W4cloud_store_save_options@1@_KPEBD@Z; wil::cloud_store::save<Windows::Data::Shell::FocusActiveSessions>(wil::cloud_store_data<Windows::Data::Shell::FocusActiveSessions> const &,wil::cloud_store_save_options,unsigned __int64,char const *)
0x18002302e  mov     bl, 1
0x180023030  lea     rcx, [rsp+0C8h+var_98]
0x180023035  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18002303a  test    bl, bl
0x18002303c  jz      short loc_180023066
0x18002303e  mov     rcx, rdi; this
0x180023041  call    ?OnSessionsChanged@FocusSessionThemeManager@implementation@Shell@Internal@Windows@winrt@@AEAAXXZ; winrt::Windows::Internal::Shell::implementation::FocusSessionThemeManager::OnSessionsChanged(void)
0x180023046  mov     [rsp+0C8h+var_98], 0
0x18002304f  lea     rdx, [rsp+0C8h+var_98]; struct winrt::Windows::System::Threading::ThreadPoolTimer *
0x180023054  mov     rcx, rdi; this
0x180023057  call    ?RefreshTimer@FocusSessionThemeManager@implementation@Shell@Internal@Windows@winrt@@AEAAXAEBUThreadPoolTimer@Threading@System@56@@Z; winrt::Windows::Internal::Shell::implementation::FocusSessionThemeManager::RefreshTimer(winrt::Windows::System::Threading::ThreadPoolTimer const &)
0x18002305c  lea     rcx, [rsp+0C8h+var_98]
0x180023061  call    ??1?$com_ptr@UIWeakReferenceSource@impl@winrt@@@winrt@@QEAA@XZ; winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(void)
0x180023066  mov     rcx, [rsp+0C8h+var_38]
0x18002306e  xor     rcx, rsp; StackCookie
0x180023071  call    __security_check_cookie
0x180023076  lea     r11, [rsp+0C8h+var_28]
0x18002307e  mov     rbx, [r11+38h]
0x180023082  mov     rbp, [r11+40h]
0x180023086  mov     rsp, r11
0x180023089  pop     r15
0x18002308b  pop     r14
0x18002308d  pop     r12
0x18002308f  pop     rdi
0x180023090  pop     rsi
0x180023091  retn
```
