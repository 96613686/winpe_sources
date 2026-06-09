# tson::save_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>>(tson::output_archive &,tip2::vector_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>> &)

- ea: `0x1400079c0`
- end: `0x140007a4d`
- name: `??$save_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@@tson@@YAXAEAVoutput_archive@0@AEAV?$vector_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@@tip2@@@Z`
- size: `141`
- prototype: `void __fastcall(tson::output_archive *this, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task`

## callers

- `0x14001b764`

## callees

- `0x14000480c`
- `0x1400079c0`
- `0x14001a7cc`
- `0x14001c010`
- `0x14001c0c0`

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
0x1400079c0  mov     r11, rsp
0x1400079c3  mov     [r11+8], rbx
0x1400079c7  mov     [r11+18h], rbp
0x1400079cb  push    rsi
0x1400079cc  push    rdi
0x1400079cd  push    r14
0x1400079cf  sub     rsp, 40h
0x1400079d3  mov     rax, [rdx+10h]
0x1400079d7  mov     r10, rdx
0x1400079da  lea     rdx, [r11+10h]
0x1400079de  mov     [r11+10h], rax
0x1400079e2  mov     rdi, rcx
0x1400079e5  call    ??$?RUsize_tag@tson@@@output_archive@tson@@QEAAAEAV01@$$QEAUsize_tag@1@@Z; tson::output_archive::operator()<tson::size_tag>(tson::size_tag &&)
0x1400079ea  mov     rax, [r10+10h]
0x1400079ee  mov     rbx, [r10]
0x1400079f1  lea     rsi, [rbx+rax*8]
0x1400079f5  jmp     short loc_140007A35
0x1400079f7  mov     rdx, [rbx]
0x1400079fa  lea     rcx, [rsp+58h+var_38]
0x1400079ff  call    ?make_string_tag@tson@@YA?AUansistring_tag@1@PEBD@Z; tson::make_string_tag(char const *)
0x140007a04  mov     r8b, 17h
0x140007a07  mov     rcx, rdi
0x140007a0a  mov     r14, [rax]
0x140007a0d  mov     rbp, [rax+8]
0x140007a11  test    r14, r14
0x140007a14  setz    dl
0x140007a17  call    ?write_type@output_archive@tson@@AEAA_N_NW4archive_marker@details@2@@Z; tson::output_archive::write_type(bool,tson::details::archive_marker)
0x140007a1c  test    al, al
0x140007a1e  jz      short loc_140007A31
0x140007a20  mov     r9, rbp; unsigned __int64
0x140007a23  mov     r8, r14; void *
0x140007a26  mov     rdx, rbp; unsigned __int64
0x140007a29  mov     rcx, rdi; this
0x140007a2c  call    ?write_string_bytes@output_archive@tson@@AEAAX_KPEAX0@Z; tson::output_archive::write_string_bytes(unsigned __int64,void *,unsigned __int64)
0x140007a31  add     rbx, 8
0x140007a35  cmp     rbx, rsi
0x140007a38  jnz     short loc_1400079F7
0x140007a3a  mov     rbx, [rsp+58h+arg_0]
0x140007a3f  mov     rbp, [rsp+58h+arg_10]
0x140007a44  add     rsp, 40h
0x140007a48  pop     r14
0x140007a4a  pop     rdi
0x140007a4b  pop     rsi
0x140007a4c  retn
```
