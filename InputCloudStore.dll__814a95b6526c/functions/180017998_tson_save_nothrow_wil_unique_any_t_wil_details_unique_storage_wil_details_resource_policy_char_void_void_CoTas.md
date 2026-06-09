# tson::save_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>>(tson::output_archive &,tip2::vector_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>> &)

- ea: `0x180017998`
- end: `0x180017a25`
- name: `??$save_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@@tson@@YAXAEAVoutput_archive@0@AEAV?$vector_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@@tip2@@@Z`
- size: `141`
- prototype: `void __fastcall(tson::output_archive *this, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task`

## callers

- `0x180025900`

## callees

- `0x1800095a0`
- `0x180017998`
- `0x1800246fc`
- `0x180026338`
- `0x1800263e8`

## pseudocode

```c
void __fastcall tson::save_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>>(
        tson::output_archive *this,
        __int64 a2)
{
  _QWORD *v3; // r10
  _QWORD *v4; // rbx
  __int64 v5; // rsi
  __int64 string_tag; // rax
  __int64 v7; // r8
  void *v8; // r14
  unsigned __int64 v9; // rbp
  __int64 v10; // rdx
  _BYTE v11[56]; // [rsp+20h] [rbp-38h] BYREF
  __int64 v12; // [rsp+68h] [rbp+10h] BYREF

  v12 = *(_QWORD *)(a2 + 16);
  tson::output_archive::operator()<tson::size_tag>(this, &v12);
  v4 = (_QWORD *)*v3;
  v5 = *v3 + 8LL * v3[2];
  while ( v4 != (_QWORD *)v5 )
  {
    string_tag = tson::make_string_tag(v11, *v4);
    LOBYTE(v7) = 23;
    v8 = *(void **)string_tag;
    v9 = *(_QWORD *)(string_tag + 8);
    LOBYTE(v10) = *(_QWORD *)string_tag == 0;
    if ( (unsigned __int8)tson::output_archive::write_type(this, v10, v7) )
      tson::output_archive::write_string_bytes(this, v9, v8, v9);
    ++v4;
  }
}

```

## disassembly

```asm
0x180017998  mov     r11, rsp
0x18001799b  mov     [r11+8], rbx
0x18001799f  mov     [r11+18h], rbp
0x1800179a3  push    rsi
0x1800179a4  push    rdi
0x1800179a5  push    r14
0x1800179a7  sub     rsp, 40h
0x1800179ab  mov     rax, [rdx+10h]
0x1800179af  mov     r10, rdx
0x1800179b2  lea     rdx, [r11+10h]
0x1800179b6  mov     [r11+10h], rax
0x1800179ba  mov     rdi, rcx
0x1800179bd  call    ??$?RUsize_tag@tson@@@output_archive@tson@@QEAAAEAV01@$$QEAUsize_tag@1@@Z; tson::output_archive::operator()<tson::size_tag>(tson::size_tag &&)
0x1800179c2  mov     rax, [r10+10h]
0x1800179c6  mov     rbx, [r10]
0x1800179c9  lea     rsi, [rbx+rax*8]
0x1800179cd  jmp     short loc_180017A0D
0x1800179cf  mov     rdx, [rbx]
0x1800179d2  lea     rcx, [rsp+58h+var_38]
0x1800179d7  call    ?make_string_tag@tson@@YA?AUansistring_tag@1@PEBD@Z; tson::make_string_tag(char const *)
0x1800179dc  mov     r8b, 17h
0x1800179df  mov     rcx, rdi
0x1800179e2  mov     r14, [rax]
0x1800179e5  mov     rbp, [rax+8]
0x1800179e9  test    r14, r14
0x1800179ec  setz    dl
0x1800179ef  call    ?write_type@output_archive@tson@@AEAA_N_NW4archive_marker@details@2@@Z; tson::output_archive::write_type(bool,tson::details::archive_marker)
0x1800179f4  test    al, al
0x1800179f6  jz      short loc_180017A09
0x1800179f8  mov     r9, rbp; unsigned __int64
0x1800179fb  mov     r8, r14; void *
0x1800179fe  mov     rdx, rbp; unsigned __int64
0x180017a01  mov     rcx, rdi; this
0x180017a04  call    ?write_string_bytes@output_archive@tson@@AEAAX_KPEAX0@Z; tson::output_archive::write_string_bytes(unsigned __int64,void *,unsigned __int64)
0x180017a09  add     rbx, 8
0x180017a0d  cmp     rbx, rsi
0x180017a10  jnz     short loc_1800179CF
0x180017a12  mov     rbx, [rsp+58h+arg_0]
0x180017a17  mov     rbp, [rsp+58h+arg_10]
0x180017a1c  add     rsp, 40h
0x180017a20  pop     r14
0x180017a22  pop     rdi
0x180017a23  pop     rsi
0x180017a24  retn
```
