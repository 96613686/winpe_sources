# tson::input_archive::process<tson::nvp<tip2::vector_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>> &>,tson::nvp<tip2::vector_nothrow<wil::StoredFailureInfo> &>,tson::nvp<tip2::vector_nothrow<tip2::test_flag> &>>(tson::nvp<tip2::vector_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>> &> &&,tson::nvp<tip2::vector_nothrow<wil::StoredFailureInfo> &> &&,tson::nvp<tip2::vector_nothrow<tip2::test_flag> &> &&)

- ea: `0x180016bc8`
- end: `0x180016c65`
- name: `??$process@V?$nvp@AEAV?$vector_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@@tip2@@@tson@@V?$nvp@AEAV?$vector_nothrow@VStoredFailureInfo@wil@@@tip2@@@2@V?$nvp@AEAV?$vector_nothrow@Utest_flag@tip2@@@tip2@@@2@@input_archive@tson@@AEAAX$$QEAV?$nvp@AEAV?$vector_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@@tip2@@@1@$$QEAV?$nvp@AEAV?$vector_nothrow@VStoredFailureInfo@wil@@@tip2@@@1@$$QEAV?$nvp@AEAV?$vector_nothrow@Utest_flag@tip2@@@tip2@@@1@@Z`
- size: `157`
- prototype: `void __fastcall(tson *this, __int64, __int64 *, __int64 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task`

## callers

- `0x1800234b8`

## callees

- `0x180015d6c`
- `0x180015e84`
- `0x180015f3c`
- `0x180023dd0`
- `0x180025d28`

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
0x180016bc8  push    rbx
0x180016bca  push    rbp
0x180016bcb  push    rsi
0x180016bcc  push    rdi
0x180016bcd  sub     rsp, 28h
0x180016bd1  mov     r10b, [rdx+8]
0x180016bd5  mov     rsi, r9
0x180016bd8  mov     rax, [rdx]
0x180016bdb  mov     rdi, r8
0x180016bde  mov     [rcx+10h], rax
0x180016be2  mov     rbp, rcx
0x180016be5  mov     [rcx+18h], r10b
0x180016be9  mov     rbx, [rdx+10h]
0x180016bed  call    ?startNode@input_archive@tson@@QEAAXXZ; tson::input_archive::startNode(void)
0x180016bf2  mov     rdx, rbx
0x180016bf5  mov     rcx, rbp; this
0x180016bf8  call    ??$load_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@@tson@@YAXAEAVinput_archive@0@AEAV?$vector_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@@tip2@@@Z; tson::load_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>>(tson::input_archive &,tip2::vector_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>> &)
0x180016bfd  mov     rcx, rbp; this
0x180016c00  call    ?finishNode@input_archive@tson@@QEAAXXZ; tson::input_archive::finishNode(void)
0x180016c05  mov     cl, [rdi+8]
0x180016c08  mov     rax, [rdi]
0x180016c0b  mov     [rbp+18h], cl
0x180016c0e  mov     rcx, rbp; this
0x180016c11  mov     [rbp+10h], rax
0x180016c15  mov     rbx, [rdi+10h]
0x180016c19  call    ?startNode@input_archive@tson@@QEAAXXZ; tson::input_archive::startNode(void)
0x180016c1e  mov     rdx, rbx
0x180016c21  mov     rcx, rbp; this
0x180016c24  call    ??$load_nothrow@VStoredFailureInfo@wil@@@tson@@YAXAEAVinput_archive@0@AEAV?$vector_nothrow@VStoredFailureInfo@wil@@@tip2@@@Z; tson::load_nothrow<wil::StoredFailureInfo>(tson::input_archive &,tip2::vector_nothrow<wil::StoredFailureInfo> &)
0x180016c29  mov     rcx, rbp; this
0x180016c2c  call    ?finishNode@input_archive@tson@@QEAAXXZ; tson::input_archive::finishNode(void)
0x180016c31  mov     cl, [rsi+8]
0x180016c34  mov     rax, [rsi]
0x180016c37  mov     [rbp+18h], cl
0x180016c3a  mov     rcx, rbp; this
0x180016c3d  mov     [rbp+10h], rax
0x180016c41  mov     rbx, [rsi+10h]
0x180016c45  call    ?startNode@input_archive@tson@@QEAAXXZ; tson::input_archive::startNode(void)
0x180016c4a  mov     rdx, rbx
0x180016c4d  mov     rcx, rbp; this
0x180016c50  call    ??$load_nothrow@Utest_flag@tip2@@@tson@@YAXAEAVinput_archive@0@AEAV?$vector_nothrow@Utest_flag@tip2@@@tip2@@@Z; tson::load_nothrow<tip2::test_flag>(tson::input_archive &,tip2::vector_nothrow<tip2::test_flag> &)
0x180016c55  mov     rcx, rbp; this
0x180016c58  add     rsp, 28h
0x180016c5c  pop     rdi
0x180016c5d  pop     rsi
0x180016c5e  pop     rbp
0x180016c5f  pop     rbx
0x180016c60  jmp     ?finishNode@input_archive@tson@@QEAAXXZ; tson::input_archive::finishNode(void)
```
