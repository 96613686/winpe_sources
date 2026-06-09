# ReadOnlyUserLanguages::ReadOnlyUserLanguages(void *)

- ea: `0x18001e964`
- end: `0x18001ea90`
- name: `??0ReadOnlyUserLanguages@@QEAA@PEAX@Z`
- size: `300`
- prototype: `ReadOnlyUserLanguages *__fastcall(ReadOnlyUserLanguages *this, void *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x18000fb54`

## callees

- `0x18000d8f8`
- `0x180011a64`
- `0x18001e804`
- `0x18001e964`
- `0x18001eb60`
- `0x18001ebec`
- `0x180020220`
- `0x1800227c0`
- `0x180025010`

## pseudocode

```c
ReadOnlyUserLanguages *__fastcall ReadOnlyUserLanguages::ReadOnlyUserLanguages(ReadOnlyUserLanguages *this, void *a2)
{
  _QWORD *v4; // rbx
  __int64 v5; // rdx
  _QWORD *v6; // rdx
  _QWORD *v7; // rbx
  RegistryKey *v8; // rax
  unsigned int v10; // [rsp+28h] [rbp-59h]
  unsigned int v11; // [rsp+30h] [rbp-51h]
  _QWORD v12[3]; // [rsp+70h] [rbp-11h] BYREF
  _QWORD *v13; // [rsp+88h] [rbp+7h]
  _BYTE v14[40]; // [rsp+90h] [rbp+Fh] BYREF

  v12[0] = &std::tr1::_Impl_no_alloc1<std::tr1::_Callable_fun<void (*const)(IUserLanguagesRegistrar *),0>,void,IUserLanguagesRegistrar *>::`vftable';
  v12[1] = UserLanguages::IUserLanguagesRegistrarNullDeleter;
  v13 = v12;
  v4 = (_QWORD *)((char *)this + 40);
  v5 = std::unique_ptr<IUserLanguagesRegistrar,std::tr1::function<void (IUserLanguagesRegistrar *)>>::unique_ptr<IUserLanguagesRegistrar,std::tr1::function<void (IUserLanguagesRegistrar *)>>(
         v14,
         (char *)this + 40,
         v12);
  UserLanguages::UserLanguages(this, v5);
  std::unique_ptr<void,std::tr1::function<void * (void *)>>::~unique_ptr<void,std::tr1::function<void * (void *)>>(v14);
  if ( v13 )
  {
    v6 = v12;
    LOBYTE(v6) = v13 != v12;
    (*(void (__fastcall **)(_QWORD *, _QWORD *))(*v13 + 24LL))(v13, v6);
  }
  *v4 = &SerializedReadOnlyUserLanguagesRegistrar::`vftable';
  v7 = v4 + 1;
  *v7 = &UserLanguageRegistryValue::`vftable';
  v8 = (RegistryKey *)operator new(0x50u);
  if ( v8 )
    v8 = RegistryKey::RegistryKey(v8, a2, HKEY_CURRENT_USER, L"Control Panel\\International\\User Profile", v10, v11);
  v7[1] = v8;
  std::wstring::wstring((__int64)(v7 + 2), (__int64)L"Languages");
  *v7 = &UserLanguageRegistryValue::`vftable';
  return this;
}

```

## disassembly

```asm
0x18001e964  mov     rax, rsp
0x18001e967  push    rbp
0x18001e968  push    rsi
0x18001e969  push    rdi
0x18001e96a  lea     rbp, [rax-5Fh]
0x18001e96e  sub     rsp, 0C0h
0x18001e975  mov     [rbp+57h+var_A0], 0FFFFFFFFFFFFFFFEh
0x18001e97d  mov     [rax+18h], rbx
0x18001e981  mov     rax, cs:__security_cookie
0x18001e988  xor     rax, rsp
0x18001e98b  mov     [rbp+57h+var_20], rax
0x18001e98f  mov     rsi, rdx
0x18001e992  mov     rdi, rcx
0x18001e995  mov     [rbp+57h+var_90], rcx
0x18001e999  lea     rax, ??_7?$_Impl_no_alloc1@U?$_Callable_fun@Q6AXPEAVIUserLanguagesRegistrar@@@Z$0A@@tr1@std@@XPEAVIUserLanguagesRegistrar@@@tr1@std@@6B@; const std::tr1::_Impl_no_alloc1<std::tr1::_Callable_fun<void (*const)(IUserLanguagesRegistrar *),0>,void,IUserLanguagesRegistrar *>::`vftable'
0x18001e9a0  mov     [rbp+57h+var_68], rax
0x18001e9a4  lea     rax, ?IUserLanguagesRegistrarNullDeleter@UserLanguages@@SAXPEAVIUserLanguagesRegistrar@@@Z; UserLanguages::IUserLanguagesRegistrarNullDeleter(IUserLanguagesRegistrar *)
0x18001e9ab  mov     [rbp+57h+var_60], rax
0x18001e9af  lea     rax, [rbp+57h+var_68]
0x18001e9b3  mov     [rbp+57h+var_50], rax
0x18001e9b7  lea     rbx, [rcx+28h]
0x18001e9bb  lea     r8, [rbp+57h+var_68]
0x18001e9bf  mov     rdx, rbx
0x18001e9c2  lea     rcx, [rbp+57h+var_48]
0x18001e9c6  call    ??0?$unique_ptr@VIUserLanguagesRegistrar@@V?$function@$$A6AXPEAVIUserLanguagesRegistrar@@@Z@tr1@std@@@std@@QEAA@PEAVIUserLanguagesRegistrar@@$$QEAV?$function@$$A6AXPEAVIUserLanguagesRegistrar@@@Z@tr1@1@@Z; std::unique_ptr<IUserLanguagesRegistrar,std::tr1::function<void (IUserLanguagesRegistrar *)>>::unique_ptr<IUserLanguagesRegistrar,std::tr1::function<void (IUserLanguagesRegistrar *)>>(IUserLanguagesRegistrar *,std::tr1::function<void (IUserLanguagesRegistrar *)> &&)
0x18001e9cb  nop
0x18001e9cc  mov     rdx, rax
0x18001e9cf  mov     rcx, rdi
0x18001e9d2  call    ??0UserLanguages@@QEAA@$$QEAV?$unique_ptr@VIUserLanguagesRegistrar@@V?$function@$$A6AXPEAVIUserLanguagesRegistrar@@@Z@tr1@std@@@std@@@Z; UserLanguages::UserLanguages(std::unique_ptr<IUserLanguagesRegistrar,std::tr1::function<void (IUserLanguagesRegistrar *)>> &&)
0x18001e9d7  nop
0x18001e9d8  lea     rcx, [rbp+57h+var_48]
0x18001e9dc  call    ??1?$unique_ptr@XV?$function@$$A6APEAXPEAX@Z@tr1@std@@@std@@QEAA@XZ; std::unique_ptr<void,std::tr1::function<void * (void *)>>::~unique_ptr<void,std::tr1::function<void * (void *)>>(void)
0x18001e9e1  nop
0x18001e9e2  mov     rcx, [rbp+57h+var_50]
0x18001e9e6  test    rcx, rcx
0x18001e9e9  jz      short loc_18001EA02
0x18001e9eb  mov     rax, [rcx]
0x18001e9ee  lea     rdx, [rbp+57h+var_68]
0x18001e9f2  cmp     rcx, rdx
0x18001e9f5  setnz   dl
0x18001e9f8  mov     rax, [rax+18h]
0x18001e9fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ea01  nop
0x18001ea02  mov     [rbp+57h+var_80], rbx
0x18001ea06  lea     rax, ??_7SerializedReadOnlyUserLanguagesRegistrar@@6B@; const SerializedReadOnlyUserLanguagesRegistrar::`vftable'
0x18001ea0d  mov     [rbx], rax
0x18001ea10  add     rbx, 8
0x18001ea14  mov     [rbp+57h+var_78], rbx
0x18001ea18  lea     rax, ??_7UserLanguageRegistryValue@@6B@; const UserLanguageRegistryValue::`vftable'
0x18001ea1f  mov     [rbx], rax
0x18001ea22  mov     ecx, 50h ; 'P'; Size
0x18001ea27  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001ea2c  mov     [rbp+57h+var_70], rax
0x18001ea30  test    rax, rax
0x18001ea33  jz      short loc_18001EA4F
0x18001ea35  lea     r9, ?USER_LANGUAGES_REGKEY_NAME@Internal@Windows@@3QBGB; "Control Panel\\International\\User Prof"...
0x18001ea3c  mov     r8, 0FFFFFFFF80000001h; hKey
0x18001ea43  mov     rdx, rsi; void *
0x18001ea46  mov     rcx, rax; this
0x18001ea49  call    ??0RegistryKey@@QEAA@PEAXPEAUHKEY__@@PEBGKK@Z; RegistryKey::RegistryKey(void *,HKEY__ *,ushort const *,ulong,ulong)
0x18001ea4e  nop
0x18001ea4f  mov     [rbx+8], rax
0x18001ea53  lea     rcx, [rbx+10h]
0x18001ea57  lea     rdx, ?USER_LANGUAGES_REGKEY_VALUE@Internal@Windows@@3QBGB; "Languages"
0x18001ea5e  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x18001ea63  nop
0x18001ea64  lea     rax, ??_7UserLanguageRegistryValue@@6B@; const UserLanguageRegistryValue::`vftable'
0x18001ea6b  mov     [rbx], rax
0x18001ea6e  mov     rax, rdi
0x18001ea71  mov     rcx, [rbp+57h+var_20]
0x18001ea75  xor     rcx, rsp; StackCookie
0x18001ea78  call    __security_check_cookie
0x18001ea7d  mov     rbx, [rsp+0D0h+arg_10]
0x18001ea85  add     rsp, 0C0h
0x18001ea8c  pop     rdi
0x18001ea8d  pop     rsi
0x18001ea8e  pop     rbp
0x18001ea8f  retn
```
