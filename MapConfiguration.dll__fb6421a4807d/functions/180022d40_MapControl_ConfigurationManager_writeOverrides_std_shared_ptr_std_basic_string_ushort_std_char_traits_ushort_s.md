# MapControl::ConfigurationManager::writeOverrides(std::shared_ptr<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>> const &)

- ea: `0x180022d40`
- end: `0x180022ea7`
- name: `?writeOverrides@ConfigurationManager@MapControl@@AEAAXAEBV?$shared_ptr@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@Z`
- size: `359`
- prototype: `void __fastcall(__int64, __int64 *)`
- caller_count: `0`
- callee_count: `15`
- tags: `file_ops, registry_config, broker_com_uri`

## callees

- `0x1800094a0`
- `0x18000c2f8`
- `0x18000c354`
- `0x18000c850`
- `0x180013da8`
- `0x180014cd8`
- `0x18001badc`
- `0x18001bb2c`
- `0x18001bb6c`
- `0x18001d298`
- `0x180022114`
- `0x180022d40`
- `0x180029980`
- `0x180029b2c`
- `0x180043010`

## string_xrefs

- `0x180022d6e`: `overrides.json`
- `0x180022dac`: `overrides.json`

## pseudocode

```c
void __fastcall MapControl::ConfigurationManager::writeOverrides(__int64 a1, __int64 *a2)
{
  __int64 v3; // rsi
  unsigned int v4; // ebx
  __int64 v5; // rcx
  __int64 v6; // rdi
  __int64 v7; // rbx
  struct Pal::Infrastructure *Instance; // rax
  int v9; // edx
  int v10; // r9d
  __int64 v11; // r10
  _BYTE v12[8]; // [rsp+40h] [rbp-59h] BYREF
  _BYTE *v13; // [rsp+48h] [rbp-51h] BYREF
  __int64 (__fastcall *v14)(); // [rsp+50h] [rbp-49h] BYREF
  __int64 v15; // [rsp+58h] [rbp-41h] BYREF
  std::_Ref_count_base *v16; // [rsp+60h] [rbp-39h]
  _QWORD v17[2]; // [rsp+68h] [rbp-31h] BYREF
  char v18; // [rsp+78h] [rbp-21h]
  _QWORD v19[3]; // [rsp+90h] [rbp-9h] BYREF
  char v20; // [rsp+A8h] [rbp+Fh]
  _QWORD *v21; // [rsp+C8h] [rbp+2Fh]

  v3 = a1;
  v4 = *(_DWORD *)(a1 + 400);
  std::wstring::wstring(v17, L"overrides.json");
  Pal::IO::deleteFile(v17, v4);
  std::wstring::_Tidy_deallocate(v17);
  LODWORD(v3) = *(_DWORD *)(v3 + 400);
  v5 = *a2;
  v6 = 2LL * *(_QWORD *)(*a2 + 16);
  v7 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v5);
  std::wstring::wstring(v17, L"overrides.json");
  Instance = Pal::Infrastructure::getInstance();
  (*(void (__fastcall **)(_QWORD, __int64 *, _QWORD *, __int64, __int64, _DWORD))(**((_QWORD **)Instance + 1) + 24LL))(
    *((_QWORD *)Instance + 1),
    &v15,
    v17,
    v7,
    v6,
    v3);
  std::wstring::_Tidy_deallocate(v17);
  Pal::ManualResetEvent::ManualResetEvent((Pal::ManualResetEvent *)v12);
  v13 = v12;
  v14 = MapControl::ConfigurationManager::fileWriteComplete;
  std::_Compressed_pair<void (*)(Pal::AsyncOperation<unsigned __int64> const &,Pal::ManualResetEvent *),std::tuple<std::_Ph<1>,Pal::ManualResetEvent *>,0>::_Compressed_pair<void (*)(Pal::AsyncOperation<unsigned __int64> const &,Pal::ManualResetEvent *),std::tuple<std::_Ph<1>,Pal::ManualResetEvent *>,0>(
    (unsigned int)v17,
    v9,
    (unsigned int)&v14,
    v10,
    (__int64)&v13);
  v19[0] = &std::_Func_impl_no_alloc<std::_Binder<std::_Unforced,void (*)(Pal::AsyncOperation<unsigned __int64> const &,Pal::ManualResetEvent *),std::_Ph<1> const &,Pal::ManualResetEvent *>,void,Pal::AsyncOperation<unsigned __int64> &>::`vftable';
  v19[1] = v17[0];
  v19[2] = v17[1];
  v20 = v18;
  v21 = v19;
  Pal::AsyncOperation<unsigned __int64>::setCallback(v11, v19);
  std::_Func_class<void,>::_Tidy(v19);
  Pal::ManualResetEvent::wait((Pal::ManualResetEvent *)v12);
  std::unique_ptr<Pal::ManualResetEventImplWindows>::~unique_ptr<Pal::ManualResetEventImplWindows>(v12);
  if ( v16 )
    std::_Ref_count_base::_Decref(v16);
}

```

## disassembly

```asm
0x180022d40  mov     [rsp-8+arg_10], rbx
0x180022d45  push    rbp
0x180022d46  push    rsi
0x180022d47  push    rdi
0x180022d48  lea     rbp, [rsp-47h]
0x180022d4d  sub     rsp, 0E0h
0x180022d54  mov     rax, cs:__security_cookie
0x180022d5b  xor     rax, rsp
0x180022d5e  mov     [rbp+57h+var_20], rax
0x180022d62  mov     rdi, rdx
0x180022d65  mov     rsi, rcx
0x180022d68  mov     ebx, [rcx+190h]
0x180022d6e  lea     rdx, aOverridesJson; "overrides.json"
0x180022d75  lea     rcx, [rbp+57h+var_88]
0x180022d79  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180022d7e  nop
0x180022d7f  mov     edx, ebx
0x180022d81  lea     rcx, [rbp+57h+var_88]
0x180022d85  call    ?deleteFile@IO@Pal@@SAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4FileLocation@2@@Z; Pal::IO::deleteFile(std::wstring const &,Pal::FileLocation)
0x180022d8a  nop
0x180022d8b  lea     rcx, [rbp+57h+var_88]
0x180022d8f  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180022d94  mov     esi, [rsi+190h]
0x180022d9a  mov     rcx, [rdi]
0x180022d9d  mov     rdi, [rcx+10h]
0x180022da1  add     rdi, rdi
0x180022da4  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180022da9  mov     rbx, rax
0x180022dac  lea     rdx, aOverridesJson; "overrides.json"
0x180022db3  lea     rcx, [rbp+57h+var_88]
0x180022db7  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180022dbc  nop
0x180022dbd  call    ?getInstance@Infrastructure@Pal@@CAAEAV12@XZ; Pal::Infrastructure::getInstance(void)
0x180022dc2  mov     rcx, [rax+8]
0x180022dc6  mov     rdx, [rcx]
0x180022dc9  mov     rax, [rdx+18h]
0x180022dcd  mov     [rsp+0F0h+var_C8], esi
0x180022dd1  mov     [rsp+0F0h+var_D0], rdi
0x180022dd6  mov     r9, rbx
0x180022dd9  lea     r8, [rbp+57h+var_88]
0x180022ddd  lea     rdx, [rbp+57h+var_98]
0x180022de1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022de6  nop
0x180022de7  lea     rcx, [rbp+57h+var_88]
0x180022deb  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180022df0  lea     rcx, [rbp+57h+var_B0]; this
0x180022df4  call    ??0ManualResetEvent@Pal@@QEAA@XZ; Pal::ManualResetEvent::ManualResetEvent(void)
0x180022df9  nop
0x180022dfa  mov     r10, [rbp+57h+var_98]
0x180022dfe  lea     rax, [rbp+57h+var_B0]
0x180022e02  mov     [rbp+57h+var_A8], rax
0x180022e06  lea     rax, ?fileWriteComplete@ConfigurationManager@MapControl@@CAXAEBV?$AsyncOperation@_K@Pal@@PEAVManualResetEvent@4@@Z; MapControl::ConfigurationManager::fileWriteComplete(Pal::AsyncOperation<unsigned __int64> const &,Pal::ManualResetEvent *)
0x180022e0d  mov     [rbp+57h+var_A0], rax
0x180022e11  lea     rax, [rbp+57h+var_A8]
0x180022e15  mov     [rsp+0F0h+var_D0], rax
0x180022e1a  lea     r8, [rbp+57h+var_A0]
0x180022e1e  lea     rcx, [rbp+57h+var_88]
0x180022e22  call    ??$?0P6AXAEBV?$AsyncOperation@_K@Pal@@PEAVManualResetEvent@1@@ZAEBU?$_Ph@$00@std@@PEAV21@@?$_Compressed_pair@P6AXAEBV?$AsyncOperation@_K@Pal@@PEAVManualResetEvent@2@@ZV?$tuple@U?$_Ph@$00@std@@PEAVManualResetEvent@Pal@@@std@@$0A@@std@@QEAA@U_One_then_variadic_args_t@1@$$QEAP6AXAEBV?$AsyncOperation@_K@Pal@@PEAVManualResetEvent@4@@ZAEBU?$_Ph@$00@1@$$QEAPEAV54@@Z; std::_Compressed_pair<void (*)(Pal::AsyncOperation<unsigned __int64> const &,Pal::ManualResetEvent *),std::tuple<std::_Ph<1>,Pal::ManualResetEvent *>,0>::_Compressed_pair<void (*)(Pal::AsyncOperation<unsigned __int64> const &,Pal::ManualResetEvent *),std::tuple<std::_Ph<1>,Pal::ManualResetEvent *>,0>(std::_One_then_variadic_args_t,void (*&&)(Pal::AsyncOperation<unsigned __int64> const &,Pal::ManualResetEvent *),std::_Ph<1> const &,Pal::ManualResetEvent * &&)
0x180022e27  lea     r11, ??_7?$_Func_impl_no_alloc@V?$_Binder@U_Unforced@std@@P6AXAEBV?$AsyncOperation@_K@Pal@@PEAVManualResetEvent@4@@ZAEBU?$_Ph@$00@2@PEAV54@@std@@XAEAV?$AsyncOperation@_K@Pal@@@std@@6B@; const std::_Func_impl_no_alloc<std::_Binder<std::_Unforced,void (*)(Pal::AsyncOperation<unsigned __int64> const &,Pal::ManualResetEvent *),std::_Ph<1> const &,Pal::ManualResetEvent *>,void,Pal::AsyncOperation<unsigned __int64> &>::`vftable'
0x180022e2e  mov     [rbp+57h+var_60], r11
0x180022e32  mov     rax, [rbp+57h+var_88]
0x180022e36  mov     [rbp+57h+var_58], rax
0x180022e3a  mov     rax, [rbp+57h+var_80]
0x180022e3e  mov     [rbp+57h+var_50], rax
0x180022e42  mov     al, [rbp+57h+var_78]
0x180022e45  mov     [rbp+57h+var_48], al
0x180022e48  lea     rax, [rbp+57h+var_60]
0x180022e4c  mov     [rbp+57h+var_28], rax
0x180022e50  lea     rdx, [rbp+57h+var_60]
0x180022e54  mov     rcx, r10
0x180022e57  call    ?setCallback@?$AsyncOperation@_K@Pal@@QEAAXAEBV?$function@$$A6AXAEAV?$AsyncOperation@_K@Pal@@@Z@std@@@Z; Pal::AsyncOperation<unsigned __int64>::setCallback(std::function<void (Pal::AsyncOperation<unsigned __int64> &)> const &)
0x180022e5c  nop
0x180022e5d  lea     rcx, [rbp+57h+var_60]
0x180022e61  call    ?_Tidy@?$_Func_class@X$$V@std@@IEAAXXZ; std::_Func_class<void,>::_Tidy(void)
0x180022e66  lea     rcx, [rbp+57h+var_B0]; this
0x180022e6a  call    ?wait@ManualResetEvent@Pal@@QEAAXXZ; Pal::ManualResetEvent::wait(void)
0x180022e6f  nop
0x180022e70  lea     rcx, [rbp+57h+var_B0]
0x180022e74  call    ??1?$unique_ptr@VManualResetEventImplWindows@Pal@@U?$default_delete@VManualResetEventImplWindows@Pal@@@std@@@std@@QEAA@XZ; std::unique_ptr<Pal::ManualResetEventImplWindows>::~unique_ptr<Pal::ManualResetEventImplWindows>(void)
0x180022e79  nop
0x180022e7a  mov     rcx, [rbp+57h+var_90]; this
0x180022e7e  test    rcx, rcx
0x180022e81  jz      short loc_180022E88
0x180022e83  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180022e88  mov     rcx, [rbp+57h+var_20]
0x180022e8c  xor     rcx, rsp; StackCookie
0x180022e8f  call    __security_check_cookie
0x180022e94  mov     rbx, [rsp+0F0h+arg_10]
0x180022e9c  add     rsp, 0E0h
0x180022ea3  pop     rdi
0x180022ea4  pop     rsi
0x180022ea5  pop     rbp
0x180022ea6  retn
```
