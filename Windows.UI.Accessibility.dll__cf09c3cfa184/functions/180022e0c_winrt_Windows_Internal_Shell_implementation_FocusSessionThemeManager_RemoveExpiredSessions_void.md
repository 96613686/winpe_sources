# winrt::Windows::Internal::Shell::implementation::FocusSessionThemeManager::RemoveExpiredSessions(void)

- ea: `0x180022e0c`
- end: `0x180022f22`
- name: `?RemoveExpiredSessions@FocusSessionThemeManager@implementation@Shell@Internal@Windows@winrt@@AEAAXXZ`
- size: `278`
- prototype: `void __fastcall(winrt::Windows::Internal::Shell::implementation::FocusSessionThemeManager *__hidden this)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config`

## callers

- `0x180022b40`

## callees

- `0x180008be8`
- `0x180008fa8`
- `0x1800092b0`
- `0x18001b894`
- `0x18001ed40`
- `0x18001f304`
- `0x180020460`
- `0x1800207ac`
- `0x1800226ec`
- `0x180022e0c`
- `0x180024410`
- `0x180024718`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180022e35`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180022e35`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180022ec8`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180022ec8`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall winrt::Windows::Internal::Shell::implementation::FocusSessionThemeManager::RemoveExpiredSessions(
        RTL_SRWLOCK *this)
{
  RTL_SRWLOCK *v2; // r14
  __int64 active; // rax
  char v4; // r12
  _QWORD *i; // rbx
  __int64 v6; // rdi
  _BYTE v7[16]; // [rsp+30h] [rbp-39h] BYREF
  _BYTE v8[128]; // [rsp+40h] [rbp-29h] BYREF
  char v9; // [rsp+D0h] [rbp+67h] BYREF
  RTL_SRWLOCK *v10; // [rsp+D8h] [rbp+6Fh] BYREF
  char v11; // [rsp+E0h] [rbp+77h] BYREF

  v2 = this + 17;
  AcquireSRWLockExclusive(this + 17);
  v10 = v2;
  active = wil::cloud_store::load<Windows::Data::Shell::FocusActiveSessions>(&this[3], v8);
  wil::cloud_store_data<Windows::Data::Shell::FocusActiveSessions>::operator=(&this[8], active);
  wil::cloud_store_data<Windows::Data::Shell::FocusActiveSessions>::~cloud_store_data<Windows::Data::Shell::FocusActiveSessions>(v8);
  v4 = 0;
  for ( i = this[10].Ptr; i != this[11].Ptr; i += 5 )
  {
    v6 = i[4];
    if ( *(_QWORD *)winrt::clock::now(&v9) >= v6 )
    {
      std::vector<Windows::Data::Shell::FocusSession>::erase(&this[10], &v11, i);
      i -= 5;
      v4 = 1;
    }
  }
  if ( v4 )
  {
    wil::cloud_store::save<Windows::Data::Shell::FocusActiveSessions>(&this[3], v7, &this[8]);
    if ( v2 )
    {
      wil::last_error_context::last_error_context((wil::last_error_context *)&v9);
      ReleaseSRWLockExclusive(v2);
      wil::last_error_context::~last_error_context((wil::last_error_context *)&v9);
    }
    v10 = 0;
    winrt::Windows::Internal::Shell::implementation::FocusSessionThemeManager::OnSessionsChanged((winrt::Windows::Internal::Shell::implementation::FocusSessionThemeManager *)this);
    if ( this[10].Ptr == this[11].Ptr )
    {
      v9 = 1;
      winrt::Windows::Internal::Shell::implementation::FocusSessionTelemetry::FocusDeactivated<bool>(&v9);
    }
  }
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v10);
}

```

## disassembly

```asm
0x180022e0c  mov     [rsp-8+arg_18], rbx
0x180022e11  push    rbp
0x180022e12  push    rsi
0x180022e13  push    rdi
0x180022e14  push    r12
0x180022e16  push    r13
0x180022e18  push    r14
0x180022e1a  push    r15
0x180022e1c  lea     rbp, [rsp-27h]
0x180022e21  sub     rsp, 90h
0x180022e28  mov     r15, rcx
0x180022e2b  lea     r14, [rcx+88h]
0x180022e32  mov     rcx, r14; SRWLock
0x180022e35  call    cs:__imp_AcquireSRWLockExclusive
0x180022e3b  mov     [rbp+57h+arg_8], r14
0x180022e3f  lea     rdx, [rbp+57h+var_80]
0x180022e43  lea     rcx, [r15+18h]
0x180022e47  call    ??$load@UFocusActiveSessions@Shell@Data@Windows@@@cloud_store@wil@@QEAA?AV?$cloud_store_data@UFocusActiveSessions@Shell@Data@Windows@@@1@W4cloud_store_load_options@1@PEBD@Z; wil::cloud_store::load<Windows::Data::Shell::FocusActiveSessions>(wil::cloud_store_load_options,char const *)
0x180022e4c  nop
0x180022e4d  lea     rcx, [r15+40h]
0x180022e51  mov     rdx, rax
0x180022e54  call    ??4?$cloud_store_data@UFocusActiveSessions@Shell@Data@Windows@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::cloud_store_data<Windows::Data::Shell::FocusActiveSessions>::operator=(wil::cloud_store_data<Windows::Data::Shell::FocusActiveSessions> &&)
0x180022e59  nop
0x180022e5a  lea     rcx, [rbp+57h+var_80]
0x180022e5e  call    ??1?$cloud_store_data@UFocusActiveSessions@Shell@Data@Windows@@@wil@@QEAA@XZ; wil::cloud_store_data<Windows::Data::Shell::FocusActiveSessions>::~cloud_store_data<Windows::Data::Shell::FocusActiveSessions>(void)
0x180022e63  lea     rsi, [r15+50h]
0x180022e67  xor     r12b, r12b
0x180022e6a  mov     rbx, [rsi]
0x180022e6d  cmp     rbx, [rsi+8]
0x180022e71  jz      short loc_180022EA1
0x180022e73  mov     rdi, [rbx+20h]
0x180022e77  lea     rcx, [rbp+57h+arg_0]
0x180022e7b  call    ?now@clock@winrt@@SA?AV?$time_point@Uclock@winrt@@V?$duration@_JU?$ratio@$00$0JIJGIA@@std@@@chrono@std@@@chrono@std@@XZ; winrt::clock::now(void)
0x180022e80  cmp     [rax], rdi
0x180022e83  jl      short loc_180022E9B
0x180022e85  mov     r8, rbx
0x180022e88  lea     rdx, [rbp+57h+arg_10]
0x180022e8c  mov     rcx, rsi
0x180022e8f  call    ?erase@?$vector@UFocusSession@Shell@Data@Windows@@V?$allocator@UFocusSession@Shell@Data@Windows@@@std@@@std@@QEAA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@UFocusSession@Shell@Data@Windows@@@std@@@std@@@2@V?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@UFocusSession@Shell@Data@Windows@@@std@@@std@@@2@@Z; std::vector<Windows::Data::Shell::FocusSession>::erase(std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<Windows::Data::Shell::FocusSession>>>)
0x180022e94  sub     rbx, 28h ; '('
0x180022e98  mov     r12b, 1
0x180022e9b  add     rbx, 28h ; '('
0x180022e9f  jmp     short loc_180022E6D
0x180022ea1  test    r12b, r12b
0x180022ea4  jz      short loc_180022EFE
0x180022ea6  lea     r8, [r15+40h]
0x180022eaa  lea     rdx, [rbp+57h+var_90]
0x180022eae  lea     rcx, [r15+18h]
0x180022eb2  call    ??$save@UFocusActiveSessions@Shell@Data@Windows@@@cloud_store@wil@@QEAA?AVcloud_store_save_result@1@AEBV?$cloud_store_data@UFocusActiveSessions@Shell@Data@Windows@@@1@W4cloud_store_save_options@1@_KPEBD@Z; wil::cloud_store::save<Windows::Data::Shell::FocusActiveSessions>(wil::cloud_store_data<Windows::Data::Shell::FocusActiveSessions> const &,wil::cloud_store_save_options,unsigned __int64,char const *)
0x180022eb7  test    r14, r14
0x180022eba  jz      short loc_180022ED7
0x180022ebc  lea     rcx, [rbp+57h+arg_0]; this
0x180022ec0  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180022ec5  mov     rcx, r14; SRWLock
0x180022ec8  call    cs:__imp_ReleaseSRWLockExclusive
0x180022ece  lea     rcx, [rbp+57h+arg_0]; this
0x180022ed2  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180022ed7  mov     [rbp+57h+arg_8], 0
0x180022edf  mov     rcx, r15; this
0x180022ee2  call    ?OnSessionsChanged@FocusSessionThemeManager@implementation@Shell@Internal@Windows@winrt@@AEAAXXZ; winrt::Windows::Internal::Shell::implementation::FocusSessionThemeManager::OnSessionsChanged(void)
0x180022ee7  mov     rax, [rsi+8]
0x180022eeb  cmp     [rsi], rax
0x180022eee  jnz     short loc_180022EFE
0x180022ef0  mov     [rbp+57h+arg_0], 1
0x180022ef4  lea     rcx, [rbp+57h+arg_0]
0x180022ef8  call    ??$FocusDeactivated@_N@FocusSessionTelemetry@implementation@Shell@Internal@Windows@winrt@@SAX$$QEA_N@Z; winrt::Windows::Internal::Shell::implementation::FocusSessionTelemetry::FocusDeactivated<bool>(bool &&)
0x180022efd  nop
0x180022efe  lea     rcx, [rbp+57h+arg_8]
0x180022f02  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180022f07  mov     rbx, [rsp+0C0h+arg_18]
0x180022f0f  add     rsp, 90h
0x180022f16  pop     r15
0x180022f18  pop     r14
0x180022f1a  pop     r13
0x180022f1c  pop     r12
0x180022f1e  pop     rdi
0x180022f1f  pop     rsi
0x180022f20  pop     rbp
0x180022f21  retn
```
