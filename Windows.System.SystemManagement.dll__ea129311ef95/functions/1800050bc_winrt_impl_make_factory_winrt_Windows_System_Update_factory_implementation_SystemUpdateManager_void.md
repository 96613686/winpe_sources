# winrt::impl::make_factory<winrt::Windows::System::Update::factory_implementation::SystemUpdateManager>(void)

- ea: `0x1800050bc`
- end: `0x180005210`
- name: `??$make_factory@USystemUpdateManager@factory_implementation@Update@System@Windows@winrt@@@impl@winrt@@YA?AUIActivationFactory@Foundation@Windows@1@XZ`
- size: `340`
- prototype: `_QWORD *__fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `12`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180009bb4`

## callees

- `0x180002de4`
- `0x18000399c`
- `0x180003aac`
- `0x180003ab8`
- `0x1800050bc`
- `0x180005a1c`
- `0x180008c0c`
- `0x180008de4`
- `0x180008efc`
- `0x180009918`
- `0x18001eff4`
- `0x18002b010`

## string_xrefs

- `0x1800050e2`: `Windows.System.Update.SystemUpdateManager`

## pseudocode

```c
_QWORD *__fastcall winrt::impl::make_factory<winrt::Windows::System::Update::factory_implementation::SystemUpdateManager>(
        _QWORD *a1)
{
  __int64 v2; // rdi
  _QWORD *v3; // rbx
  _QWORD *v4; // rbx
  unsigned int v5; // eax
  __int64 v7; // [rsp+38h] [rbp-21h] BYREF
  _QWORD v8[2]; // [rsp+40h] [rbp-19h] BYREF
  int v9; // [rsp+50h] [rbp-9h] BYREF
  __int128 v10; // [rsp+58h] [rbp-1h]
  _QWORD v11[9]; // [rsp+68h] [rbp+Fh] BYREF
  char v12; // [rsp+C8h] [rbp+6Fh] BYREF
  char v13; // [rsp+D0h] [rbp+77h] BYREF
  __int64 v14; // [rsp+D8h] [rbp+7Fh] BYREF

  winrt::impl::get_static_lifetime_map(&v7);
  winrt::param::hstring::create_string_reference(
    (winrt::param::hstring *)v11,
    L"Windows.System.Update.SystemUpdateManager",
    0x29u);
  v14 = 0;
  v2 = v7;
  (*(void (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v7 + 48LL))(v7, v11[0], &v14);
  if ( v14 )
  {
    *a1 = v14;
  }
  else
  {
    v3 = operator new(0x58u);
    memset_0(v3, 0, 0x58u);
    winrt::Windows::System::Update::factory_implementation::SystemUpdateManager::SystemUpdateManager((winrt::Windows::System::Update::factory_implementation::SystemUpdateManager *)v3);
    *v3 = &winrt::Windows::System::Update::factory_implementation::SystemUpdateManager::`vftable';
    v4 = v3 + 2;
    v8[0] = v4;
    v8[1] = &`winrt::impl::make_factory<winrt::Windows::System::Update::factory_implementation::SystemUpdateManager>'::`7'::lock;
    WINRT_IMPL_AcquireSRWLockExclusive(&`winrt::impl::make_factory<winrt::Windows::System::Update::factory_implementation::SystemUpdateManager>'::`7'::lock);
    (*(void (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v2 + 48LL))(v2, v11[0], &v14);
    if ( v14 )
    {
      *a1 = v14;
    }
    else
    {
      v12 = 0;
      v9 = 0;
      v10 = 0;
      v5 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD *, char *))(*(_QWORD *)v2 + 80LL))(v2, v11[0], v4, &v12);
      winrt::check_hresult(&v13, v5, &v9);
      v8[0] = 0;
      *a1 = v4;
    }
    ReleaseSRWLockExclusive_0(&`winrt::impl::make_factory<winrt::Windows::System::Update::factory_implementation::SystemUpdateManager>'::`7'::lock);
    _lambda_12ef4a55c56a96ec7ad58335194b061f_::~_lambda_12ef4a55c56a96ec7ad58335194b061f_((_lambda_12ef4a55c56a96ec7ad58335194b061f_ *)v8);
  }
  if ( v2 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v7);
  return a1;
}

```

## disassembly

```asm
0x1800050bc  push    rbp
0x1800050be  push    rbx
0x1800050bf  push    rsi
0x1800050c0  push    rdi
0x1800050c1  push    r14
0x1800050c3  lea     rbp, [rsp-37h]
0x1800050c8  sub     rsp, 90h
0x1800050cf  mov     rsi, rcx
0x1800050d2  lea     rcx, [rbp+57h+var_78]
0x1800050d6  call    ?get_static_lifetime_map@impl@winrt@@YA?AU?$com_ptr@UIStaticLifetimeCollection@impl@winrt@@@2@XZ; winrt::impl::get_static_lifetime_map(void)
0x1800050db  nop
0x1800050dc  mov     r8d, 29h ; ')'; unsigned __int64
0x1800050e2  lea     rdx, aWindowsSystemU_3; "Windows.System.Update.SystemUpdateManag"...
0x1800050e9  lea     rcx, [rbp+57h+var_48]; this
0x1800050ed  call    ?create_string_reference@hstring@param@winrt@@AEAAXQEBG_K@Z; winrt::param::hstring::create_string_reference(ushort const * const,unsigned __int64)
0x1800050f2  mov     [rbp+57h+arg_18], 0
0x1800050fa  mov     rdi, [rbp+57h+var_78]
0x1800050fe  mov     rax, [rdi]
0x180005101  lea     r8, [rbp+57h+arg_18]
0x180005105  mov     rdx, [rbp+57h+var_48]
0x180005109  mov     rcx, rdi
0x18000510c  mov     rax, [rax+30h]
0x180005110  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005115  mov     rax, [rbp+57h+arg_18]
0x180005119  test    rax, rax
0x18000511c  jz      short loc_180005126
0x18000511e  mov     [rsi], rax
0x180005121  jmp     loc_1800051F1
0x180005126  mov     r14d, 58h ; 'X'
0x18000512c  mov     ecx, r14d; Size
0x18000512f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180005134  mov     rbx, rax
0x180005137  mov     r8d, r14d; Size
0x18000513a  xor     edx, edx; Val
0x18000513c  mov     rcx, rax; void *
0x18000513f  call    memset_0
0x180005144  mov     rcx, rbx; this
0x180005147  call    ??0SystemUpdateManager@factory_implementation@Update@System@Windows@winrt@@QEAA@XZ; winrt::Windows::System::Update::factory_implementation::SystemUpdateManager::SystemUpdateManager(void)
0x18000514c  lea     rax, ??_7SystemUpdateManager@factory_implementation@Update@System@Windows@winrt@@6B@; const winrt::Windows::System::Update::factory_implementation::SystemUpdateManager::`vftable'
0x180005153  mov     [rbx], rax
0x180005156  add     rbx, 10h
0x18000515a  mov     [rbp+57h+var_70], rbx
0x18000515e  lea     r14, ?lock@?6???$make_factory@USystemUpdateManager@factory_implementation@Update@System@Windows@winrt@@@impl@winrt@@YA?AUIActivationFactory@Foundation@Windows@2@XZ@4Uslim_mutex@2@A; winrt::slim_mutex `winrt::impl::make_factory<winrt::Windows::System::Update::factory_implementation::SystemUpdateManager>(void)'::`7'::lock
0x180005165  mov     [rbp+57h+var_68], r14
0x180005169  mov     rcx, r14; SRWLock
0x18000516c  call    WINRT_IMPL_AcquireSRWLockExclusive
0x180005171  nop
0x180005172  mov     rax, [rdi]
0x180005175  lea     r8, [rbp+57h+arg_18]
0x180005179  mov     rdx, [rbp+57h+var_48]
0x18000517d  mov     rcx, rdi
0x180005180  mov     rax, [rax+30h]
0x180005184  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005189  mov     rax, [rbp+57h+arg_18]
0x18000518d  test    rax, rax
0x180005190  jz      short loc_180005197
0x180005192  mov     [rsi], rax
0x180005195  jmp     short loc_1800051DE
0x180005197  mov     [rbp+57h+arg_8], 0
0x18000519b  mov     [rbp+57h+var_60], 0
0x1800051a2  xorps   xmm0, xmm0
0x1800051a5  movdqu  [rbp+57h+var_58], xmm0
0x1800051aa  mov     rax, [rdi]
0x1800051ad  lea     r9, [rbp+57h+arg_8]
0x1800051b1  mov     r8, rbx
0x1800051b4  mov     rdx, [rbp+57h+var_48]
0x1800051b8  mov     rcx, rdi
0x1800051bb  mov     rax, [rax+50h]
0x1800051bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800051c4  lea     r8, [rbp+57h+var_60]
0x1800051c8  mov     edx, eax
0x1800051ca  lea     rcx, [rbp+57h+arg_10]
0x1800051ce  call    ?check_hresult@winrt@@YA?AUhresult@1@U21@AEBUslim_source_location@impl@1@@Z; winrt::check_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x1800051d3  mov     [rbp+57h+var_70], 0
0x1800051db  mov     [rsi], rbx
0x1800051de  mov     rcx, r14; SRWLock
0x1800051e1  call    ReleaseSRWLockExclusive_0
0x1800051e6  nop
0x1800051e7  lea     rcx, [rbp+57h+var_70]; this
0x1800051eb  call    ??1_lambda_12ef4a55c56a96ec7ad58335194b061f_@@QEAA@XZ; _lambda_12ef4a55c56a96ec7ad58335194b061f_::~_lambda_12ef4a55c56a96ec7ad58335194b061f_(void)
0x1800051f0  nop
0x1800051f1  test    rdi, rdi
0x1800051f4  jz      short loc_1800051FF
0x1800051f6  lea     rcx, [rbp+57h+var_78]
0x1800051fa  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x1800051ff  mov     rax, rsi
0x180005202  add     rsp, 90h
0x180005209  pop     r14
0x18000520b  pop     rdi
0x18000520c  pop     rsi
0x18000520d  pop     rbx
0x18000520e  pop     rbp
0x18000520f  retn
```
