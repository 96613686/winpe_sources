# tson::save_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>>(tson::output_archive &,tip2::vector_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>> &)

- ea: `0x180011000`
- end: `0x18001108d`
- name: `??$save_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@@tson@@YAXAEAVoutput_archive@0@AEAV?$vector_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@@tip2@@@Z`
- size: `141`
- prototype: `__int64 __fastcall(tson::output_archive *this)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task`

## callers

- `0x18000c970`

## callees

- `0x18000c59c`
- `0x180011000`
- `0x18001f600`
- `0x1800217dc`
- `0x18002188c`

## pseudocode

```c
void __fastcall tson::save_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>>(
        tson::output_archive *this,
        __int64 a2,
        __int64 a3)
{
  _QWORD *v4; // r9
  _QWORD *v5; // rbx
  __int64 v6; // rsi
  __int64 string_tag; // rax
  void *v8; // r14
  unsigned __int64 v9; // rbp
  _BYTE v10[56]; // [rsp+20h] [rbp-38h] BYREF
  __int64 v11; // [rsp+68h] [rbp+10h] BYREF

  v11 = *(_QWORD *)(a2 + 16);
  tson::output_archive::operator()<tson::size_tag>(this, &v11, a3, a2);
  v5 = (_QWORD *)*v4;
  v6 = *v4 + 8LL * v4[2];
  while ( v5 != (_QWORD *)v6 )
  {
    string_tag = tson::make_string_tag(v10, *v5);
    v8 = *(void **)string_tag;
    v9 = *(_QWORD *)(string_tag + 8);
    if ( tson::output_archive::write_type(this, *(_QWORD *)string_tag == 0, 23) )
      tson::output_archive::write_string_bytes(this, v9, v8, v9);
    ++v5;
  }
}

```

## disassembly

```asm
0x180011000  mov     r11, rsp
0x180011003  mov     [r11+8], rbx
0x180011007  mov     [r11+18h], rbp
0x18001100b  push    rsi
0x18001100c  push    rdi
0x18001100d  push    r14
0x18001100f  sub     rsp, 40h
0x180011013  mov     rax, [rdx+10h]
0x180011017  mov     r9, rdx
0x18001101a  lea     rdx, [r11+10h]
0x18001101e  mov     [r11+10h], rax
0x180011022  mov     rdi, rcx
0x180011025  call    ??$?RUsize_tag@tson@@@output_archive@tson@@QEAAAEAV01@$$QEAUsize_tag@1@@Z; tson::output_archive::operator()<tson::size_tag>(tson::size_tag &&)
0x18001102a  mov     rax, [r9+10h]
0x18001102e  mov     rbx, [r9]
0x180011031  lea     rsi, [rbx+rax*8]
0x180011035  jmp     short loc_180011075
0x180011037  mov     rdx, [rbx]
0x18001103a  lea     rcx, [rsp+58h+var_38]
0x18001103f  call    ?make_string_tag@tson@@YA?AUansistring_tag@1@PEBD@Z; tson::make_string_tag(char const *)
0x180011044  mov     r8b, 17h
0x180011047  mov     rcx, rdi
0x18001104a  mov     r14, [rax]
0x18001104d  mov     rbp, [rax+8]
0x180011051  test    r14, r14
0x180011054  setz    dl
0x180011057  call    ?write_type@output_archive@tson@@AEAA_N_NW4archive_marker@details@2@@Z; tson::output_archive::write_type(bool,tson::details::archive_marker)
0x18001105c  test    al, al
0x18001105e  jz      short loc_180011071
0x180011060  mov     r9, rbp; unsigned __int64
0x180011063  mov     r8, r14; void *
0x180011066  mov     rdx, rbp; unsigned __int64
0x180011069  mov     rcx, rdi; this
0x18001106c  call    ?write_string_bytes@output_archive@tson@@AEAAX_KPEAX0@Z; tson::output_archive::write_string_bytes(unsigned __int64,void *,unsigned __int64)
0x180011071  add     rbx, 8
0x180011075  cmp     rbx, rsi
0x180011078  jnz     short loc_180011037
0x18001107a  mov     rbx, [rsp+58h+arg_0]
0x18001107f  mov     rbp, [rsp+58h+arg_10]
0x180011084  add     rsp, 40h
0x180011088  pop     r14
0x18001108a  pop     rdi
0x18001108b  pop     rsi
0x18001108c  retn
```
