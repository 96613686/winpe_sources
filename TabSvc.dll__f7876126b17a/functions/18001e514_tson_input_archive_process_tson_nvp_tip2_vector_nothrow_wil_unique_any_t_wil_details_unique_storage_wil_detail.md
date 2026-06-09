# tson::input_archive::process<tson::nvp<tip2::vector_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>> &>,tson::nvp<tip2::vector_nothrow<wil::StoredFailureInfo> &>,tson::nvp<tip2::vector_nothrow<tip2::test_flag> &>>(tson::nvp<tip2::vector_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>> &> &&,tson::nvp<tip2::vector_nothrow<wil::StoredFailureInfo> &> &&,tson::nvp<tip2::vector_nothrow<tip2::test_flag> &> &&)

- ea: `0x18001e514`
- end: `0x18001e5b1`
- name: `??$process@V?$nvp@AEAV?$vector_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@@tip2@@@tson@@V?$nvp@AEAV?$vector_nothrow@VStoredFailureInfo@wil@@@tip2@@@2@V?$nvp@AEAV?$vector_nothrow@Utest_flag@tip2@@@tip2@@@2@@input_archive@tson@@AEAAX$$QEAV?$nvp@AEAV?$vector_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@@tip2@@@1@$$QEAV?$nvp@AEAV?$vector_nothrow@VStoredFailureInfo@wil@@@tip2@@@1@$$QEAV?$nvp@AEAV?$vector_nothrow@Utest_flag@tip2@@@tip2@@@1@@Z`
- size: `157`
- prototype: `void __fastcall(tson *this, __int64, __int64 *, __int64 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task`

## callers

- `0x18001af84`

## callees

- `0x18001decc`
- `0x18001dfe4`
- `0x18001e09c`
- `0x180029760`
- `0x18002abb0`

## pseudocode

```c
void __fastcall tson::input_archive::process<tson::nvp<tip2::vector_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>> &>,tson::nvp<tip2::vector_nothrow<wil::StoredFailureInfo> &>,tson::nvp<tip2::vector_nothrow<tip2::test_flag> &>>(
        tson *this,
        __int64 a2,
        __int64 *a3,
        __int64 *a4)
{
  char v4; // r10
  __int64 *v8; // rbx
  __int64 v9; // rax
  __int64 v10; // rax

  v4 = *(_BYTE *)(a2 + 8);
  *((_QWORD *)this + 2) = *(_QWORD *)a2;
  *((_BYTE *)this + 24) = v4;
  v8 = *(__int64 **)(a2 + 16);
  tson::input_archive::startNode(this);
  tson::load_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>>(
    this,
    v8);
  tson::input_archive::finishNode(this);
  v9 = *a3;
  *((_BYTE *)this + 24) = *((_BYTE *)a3 + 8);
  *((_QWORD *)this + 2) = v9;
  tson::input_archive::startNode(this);
  tson::load_nothrow<wil::StoredFailureInfo>(this);
  tson::input_archive::finishNode(this);
  v10 = *a4;
  *((_BYTE *)this + 24) = *((_BYTE *)a4 + 8);
  *((_QWORD *)this + 2) = v10;
  tson::input_archive::startNode(this);
  tson::load_nothrow<tip2::test_flag>(this);
  tson::input_archive::finishNode(this);
}

```

## disassembly

```asm
0x18001e514  push    rbx
0x18001e516  push    rbp
0x18001e517  push    rsi
0x18001e518  push    rdi
0x18001e519  sub     rsp, 28h
0x18001e51d  mov     r10b, [rdx+8]
0x18001e521  mov     rsi, r9
0x18001e524  mov     rax, [rdx]
0x18001e527  mov     rdi, r8
0x18001e52a  mov     [rcx+10h], rax
0x18001e52e  mov     rbp, rcx
0x18001e531  mov     [rcx+18h], r10b
0x18001e535  mov     rbx, [rdx+10h]
0x18001e539  call    ?startNode@input_archive@tson@@QEAAXXZ; tson::input_archive::startNode(void)
0x18001e53e  mov     rdx, rbx
0x18001e541  mov     rcx, rbp; this
0x18001e544  call    ??$load_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@@tson@@YAXAEAVinput_archive@0@AEAV?$vector_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@@tip2@@@Z; tson::load_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>>(tson::input_archive &,tip2::vector_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>> &)
0x18001e549  mov     rcx, rbp; this
0x18001e54c  call    ?finishNode@input_archive@tson@@QEAAXXZ; tson::input_archive::finishNode(void)
0x18001e551  mov     cl, [rdi+8]
0x18001e554  mov     rax, [rdi]
0x18001e557  mov     [rbp+18h], cl
0x18001e55a  mov     rcx, rbp; this
0x18001e55d  mov     [rbp+10h], rax
0x18001e561  mov     rbx, [rdi+10h]
0x18001e565  call    ?startNode@input_archive@tson@@QEAAXXZ; tson::input_archive::startNode(void)
0x18001e56a  mov     rdx, rbx
0x18001e56d  mov     rcx, rbp; this
0x18001e570  call    ??$load_nothrow@VStoredFailureInfo@wil@@@tson@@YAXAEAVinput_archive@0@AEAV?$vector_nothrow@VStoredFailureInfo@wil@@@tip2@@@Z; tson::load_nothrow<wil::StoredFailureInfo>(tson::input_archive &,tip2::vector_nothrow<wil::StoredFailureInfo> &)
0x18001e575  mov     rcx, rbp; this
0x18001e578  call    ?finishNode@input_archive@tson@@QEAAXXZ; tson::input_archive::finishNode(void)
0x18001e57d  mov     cl, [rsi+8]
0x18001e580  mov     rax, [rsi]
0x18001e583  mov     [rbp+18h], cl
0x18001e586  mov     rcx, rbp; this
0x18001e589  mov     [rbp+10h], rax
0x18001e58d  mov     rbx, [rsi+10h]
0x18001e591  call    ?startNode@input_archive@tson@@QEAAXXZ; tson::input_archive::startNode(void)
0x18001e596  mov     rdx, rbx
0x18001e599  mov     rcx, rbp; this
0x18001e59c  call    ??$load_nothrow@Utest_flag@tip2@@@tson@@YAXAEAVinput_archive@0@AEAV?$vector_nothrow@Utest_flag@tip2@@@tip2@@@Z; tson::load_nothrow<tip2::test_flag>(tson::input_archive &,tip2::vector_nothrow<tip2::test_flag> &)
0x18001e5a1  mov     rcx, rbp; this
0x18001e5a4  add     rsp, 28h
0x18001e5a8  pop     rdi
0x18001e5a9  pop     rsi
0x18001e5aa  pop     rbp
0x18001e5ab  pop     rbx
0x18001e5ac  jmp     ?finishNode@input_archive@tson@@QEAAXXZ; tson::input_archive::finishNode(void)
```
