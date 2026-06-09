# tson::load_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>>(tson::input_archive &,tip2::vector_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>> &)

- ea: `0x18001dfe4`
- end: `0x18001e093`
- name: `??$load_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@@tson@@YAXAEAVinput_archive@0@AEAV?$vector_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@@tip2@@@Z`
- size: `175`
- prototype: `__int64 __fastcall(tson::input_archive *this, __int64 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task`

## callers

- `0x18001e514`

## callees

- `0x180018f48`
- `0x180018fc4`
- `0x18001b2d4`
- `0x18001d1d4`
- `0x18001dfe4`
- `0x180029fc4`

## pseudocode

```c
__int64 __fastcall tson::load_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>>(
        tson::input_archive *this,
        __int64 *a2)
{
  __int64 result; // rax
  __int64 v5; // rbx
  unsigned __int64 v6; // rax
  __int64 v7; // rdx
  __int64 v8; // rdx
  __int64 v9; // rax
  __int64 v10; // rcx
  __int64 v11; // [rsp+40h] [rbp+18h] BYREF

  v11 = 0;
  tson::input_archive::operator()<tson::size_tag &>(this, &v11);
  result = tip2::vector_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>>::clear(a2);
  v5 = v11;
  while ( v5 )
  {
    v11 = 0;
    --v5;
    tson::input_archive::read_cotaskmem_string<tson::ansistring_tag,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>>(this);
    v6 = a2[1];
    if ( a2[2] < v6 )
      goto LABEL_6;
    v7 = 2 * v6;
    if ( !v6 )
      v7 = 10;
    if ( (unsigned __int8)tip2::vector_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>>::reserve(
                            a2,
                            v7) )
    {
LABEL_6:
      v8 = a2[2];
      v9 = v11;
      v10 = *a2;
      v11 = 0;
      *(_QWORD *)(v10 + 8 * v8) = v9;
      ++a2[2];
    }
    result = wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v11);
  }
  return result;
}

```

## disassembly

```asm
0x18001dfe4  mov     rax, rsp
0x18001dfe7  mov     [rax+8], rbx
0x18001dfeb  mov     [rax+10h], rsi
0x18001dfef  push    rdi
0x18001dff0  sub     rsp, 20h
0x18001dff4  mov     rdi, rdx
0x18001dff7  mov     qword ptr [rax+18h], 0
0x18001dfff  lea     rdx, [rax+18h]
0x18001e003  mov     rsi, rcx
0x18001e006  call    ??$?RAEAUsize_tag@tson@@@input_archive@tson@@QEAAAEAV01@AEAUsize_tag@1@@Z; tson::input_archive::operator()<tson::size_tag &>(tson::size_tag &)
0x18001e00b  mov     rcx, rdi
0x18001e00e  call    ?clear@?$vector_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@@tip2@@QEAAXXZ; tip2::vector_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>>::clear(void)
0x18001e013  mov     rbx, [rsp+28h+arg_10]
0x18001e018  jmp     short loc_18001E07E
0x18001e01a  lea     rdx, [rsp+28h+arg_10]
0x18001e01f  mov     [rsp+28h+arg_10], 0
0x18001e028  mov     rcx, rsi; this
0x18001e02b  dec     rbx
0x18001e02e  call    ??$read_cotaskmem_string@Uansistring_tag@tson@@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@@input_archive@tson@@AEAAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@@Z; tson::input_archive::read_cotaskmem_string<tson::ansistring_tag,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>> &)
0x18001e033  mov     rax, [rdi+8]
0x18001e037  cmp     [rdi+10h], rax
0x18001e03b  jb      short loc_18001E057
0x18001e03d  lea     rdx, [rax+rax]
0x18001e041  test    rax, rax
0x18001e044  jnz     short loc_18001E04B
0x18001e046  mov     edx, 0Ah
0x18001e04b  mov     rcx, rdi
0x18001e04e  call    ?reserve@?$vector_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@@tip2@@QEAA_N_K@Z; tip2::vector_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>>::reserve(unsigned __int64)
0x18001e053  test    al, al
0x18001e055  jz      short loc_18001E074
0x18001e057  mov     rdx, [rdi+10h]
0x18001e05b  mov     rax, [rsp+28h+arg_10]
0x18001e060  mov     rcx, [rdi]
0x18001e063  mov     [rsp+28h+arg_10], 0
0x18001e06c  mov     [rcx+rdx*8], rax
0x18001e070  inc     qword ptr [rdi+10h]
0x18001e074  lea     rcx, [rsp+28h+arg_10]
0x18001e079  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18001e07e  test    rbx, rbx
0x18001e081  jnz     short loc_18001E01A
0x18001e083  mov     rbx, [rsp+28h+arg_0]
0x18001e088  mov     rsi, [rsp+28h+arg_8]
0x18001e08d  add     rsp, 20h
0x18001e091  pop     rdi
0x18001e092  retn
```
