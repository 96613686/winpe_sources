# SerializedReadOnlyUserLanguagesRegistrar::SerializedReadOnlyUserLanguagesRegistrar(void *)

- ea: `0x18001ea98`
- end: `0x18001eb58`
- name: `??0SerializedReadOnlyUserLanguagesRegistrar@@QEAA@PEAX@Z`
- size: `192`
- prototype: `SerializedReadOnlyUserLanguagesRegistrar *__fastcall(SerializedReadOnlyUserLanguagesRegistrar *__hidden this, void *)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, registry_config`

## callers

- `0x18000ff6c`

## callees

- `0x18001e844`
- `0x18001ea98`
- `0x1800216d8`
- `0x180021bc4`
- `0x1800227c0`
- `0x180025010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
SerializedReadOnlyUserLanguagesRegistrar *__fastcall SerializedReadOnlyUserLanguagesRegistrar::SerializedReadOnlyUserLanguagesRegistrar(
        SerializedReadOnlyUserLanguagesRegistrar *this,
        void *a2)
{
  __int64 v3; // rax
  __int64 SystemPath; // rax
  int v5; // edx
  int v6; // r8d
  int v7; // r9d
  _QWORD *v8; // rdx
  _BYTE v10[40]; // [rsp+50h] [rbp-21h] BYREF
  _BYTE v11[40]; // [rsp+78h] [rbp+7h] BYREF
  _QWORD v12[3]; // [rsp+A0h] [rbp+2Fh] BYREF
  _QWORD *v13; // [rsp+B8h] [rbp+47h]

  *(_QWORD *)this = &SerializedReadOnlyUserLanguagesRegistrar::`vftable';
  v12[0] = &std::tr1::_Impl_no_alloc1<std::tr1::_Callable_fun<void * (*const)(void *),0>,void *,void *>::`vftable';
  v12[1] = SerializedReadOnlyUserLanguagesRegistrar::Null_PSid_Deleter;
  v13 = v12;
  v3 = std::unique_ptr<void,std::tr1::function<void * (void *)>>::unique_ptr<void,std::tr1::function<void * (void *)>>(
         v10,
         a2,
         v12);
  SystemPath = SerializedRegistryKey::GetSystemPath(v11, v3);
  SerializedRegistryMultiStringValue::SerializedRegistryMultiStringValue((_DWORD)this + 8, v5, v6, v7, SystemPath);
  if ( v13 )
  {
    v8 = v12;
    LOBYTE(v8) = v13 != v12;
    (*(void (__fastcall **)(_QWORD *, _QWORD *))(*v13 + 24LL))(v13, v8);
  }
  return this;
}

```

## disassembly

```asm
0x18001ea98  mov     rax, rsp
0x18001ea9b  push    rbp
0x18001ea9c  lea     rbp, [rax-5Fh]
0x18001eaa0  sub     rsp, 0C0h
0x18001eaa7  mov     [rbp+57h+var_88], 0FFFFFFFFFFFFFFFEh
0x18001eaaf  mov     [rax+18h], rbx
0x18001eab3  mov     rax, cs:__security_cookie
0x18001eaba  xor     rax, rsp
0x18001eabd  mov     [rbp+57h+var_8], rax
0x18001eac1  mov     rbx, rcx
0x18001eac4  mov     [rbp+57h+var_80], rcx
0x18001eac8  lea     rax, ??_7SerializedReadOnlyUserLanguagesRegistrar@@6B@; const SerializedReadOnlyUserLanguagesRegistrar::`vftable'
0x18001eacf  mov     [rcx], rax
0x18001ead2  lea     rax, ??_7?$_Impl_no_alloc1@U?$_Callable_fun@Q6APEAXPEAX@Z$0A@@tr1@std@@PEAXPEAX@tr1@std@@6B@; const std::tr1::_Impl_no_alloc1<std::tr1::_Callable_fun<void * (*const)(void *),0>,void *,void *>::`vftable'
0x18001ead9  mov     [rbp+57h+var_28], rax
0x18001eadd  lea     rax, ?Null_PSid_Deleter@SerializedReadOnlyUserLanguagesRegistrar@@CAPEAXPEAX@Z; SerializedReadOnlyUserLanguagesRegistrar::Null_PSid_Deleter(void *)
0x18001eae4  mov     [rbp+57h+var_20], rax
0x18001eae8  lea     rax, [rbp+57h+var_28]
0x18001eaec  mov     [rbp+57h+var_10], rax
0x18001eaf0  lea     r8, [rbp+57h+var_28]
0x18001eaf4  lea     rcx, [rbp+57h+var_78]
0x18001eaf8  call    ??0?$unique_ptr@XV?$function@$$A6APEAXPEAX@Z@tr1@std@@@std@@QEAA@PEAX$$QEAV?$function@$$A6APEAXPEAX@Z@tr1@1@@Z; std::unique_ptr<void,std::tr1::function<void * (void *)>>::unique_ptr<void,std::tr1::function<void * (void *)>>(void *,std::tr1::function<void * (void *)> &&)
0x18001eafd  mov     rdx, rax
0x18001eb00  lea     rcx, [rbp+57h+var_50]
0x18001eb04  call    ?GetSystemPath@SerializedRegistryKey@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@XV?$function@$$A6APEAXPEAX@Z@tr1@std@@@3@@Z; SerializedRegistryKey::GetSystemPath(std::unique_ptr<void,std::tr1::function<void * (void *)>>)
0x18001eb09  lea     rcx, [rbx+8]
0x18001eb0d  mov     [rsp+20h], rax
0x18001eb12  call    ??0SerializedRegistryMultiStringValue@@QEAA@PEAUHKEY__@@PEBG1V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; SerializedRegistryMultiStringValue::SerializedRegistryMultiStringValue(HKEY__ *,ushort const *,ushort const *,std::wstring)
0x18001eb17  nop
0x18001eb18  mov     rcx, [rbp+57h+var_10]
0x18001eb1c  test    rcx, rcx
0x18001eb1f  jz      short loc_18001EB38
0x18001eb21  mov     rax, [rcx]
0x18001eb24  lea     rdx, [rbp+57h+var_28]
0x18001eb28  cmp     rcx, rdx
0x18001eb2b  setnz   dl
0x18001eb2e  mov     rax, [rax+18h]
0x18001eb32  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001eb37  nop
0x18001eb38  mov     rax, rbx
0x18001eb3b  mov     rcx, [rbp+57h+var_8]
0x18001eb3f  xor     rcx, rsp; StackCookie
0x18001eb42  call    __security_check_cookie
0x18001eb47  mov     rbx, [rsp+0C0h+arg_10]
0x18001eb4f  add     rsp, 0C0h
0x18001eb56  pop     rbp
0x18001eb57  retn
```
