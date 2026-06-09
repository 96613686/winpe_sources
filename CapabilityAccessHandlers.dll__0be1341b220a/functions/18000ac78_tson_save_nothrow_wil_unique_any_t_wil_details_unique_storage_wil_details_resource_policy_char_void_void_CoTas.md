# tson::save_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>>(tson::output_archive &,tip2::vector_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>> &)

- ea: `0x18000ac78`
- end: `0x18000ad05`
- name: `??$save_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@@tson@@YAXAEAVoutput_archive@0@AEAV?$vector_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@@tip2@@@Z`
- size: `141`
- prototype: `void __fastcall(tson::output_archive *this, __int64, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task`

## callers

- `0x18000eb08`

## callees

- `0x18000a5fc`
- `0x18000ac78`
- `0x18000e01c`
- `0x18000f2a8`
- `0x18000f358`

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
  __int64 v8; // r8
  void *v9; // r14
  unsigned __int64 v10; // rbp
  __int64 v11; // rdx
  _BYTE v12[56]; // [rsp+20h] [rbp-38h] BYREF
  __int64 v13; // [rsp+68h] [rbp+10h] BYREF

  v13 = *(_QWORD *)(a2 + 16);
  tson::output_archive::operator()<tson::size_tag>(this, &v13, a3, a2);
  v5 = (_QWORD *)*v4;
  v6 = *v4 + 8LL * v4[2];
  while ( v5 != (_QWORD *)v6 )
  {
    string_tag = tson::make_string_tag(v12, *v5);
    LOBYTE(v8) = 23;
    v9 = *(void **)string_tag;
    v10 = *(_QWORD *)(string_tag + 8);
    LOBYTE(v11) = *(_QWORD *)string_tag == 0;
    if ( (unsigned __int8)tson::output_archive::write_type(this, v11, v8) )
      tson::output_archive::write_string_bytes(this, v10, v9, v10);
    ++v5;
  }
}

```

## disassembly

```asm
0x18000ac78  mov     r11, rsp
0x18000ac7b  mov     [r11+8], rbx
0x18000ac7f  mov     [r11+18h], rbp
0x18000ac83  push    rsi
0x18000ac84  push    rdi
0x18000ac85  push    r14
0x18000ac87  sub     rsp, 40h
0x18000ac8b  mov     rax, [rdx+10h]
0x18000ac8f  mov     r9, rdx
0x18000ac92  lea     rdx, [r11+10h]
0x18000ac96  mov     [r11+10h], rax
0x18000ac9a  mov     rdi, rcx
0x18000ac9d  call    ??$?RUsize_tag@tson@@@output_archive@tson@@QEAAAEAV01@$$QEAUsize_tag@1@@Z; tson::output_archive::operator()<tson::size_tag>(tson::size_tag &&)
0x18000aca2  mov     rax, [r9+10h]
0x18000aca6  mov     rbx, [r9]
0x18000aca9  lea     rsi, [rbx+rax*8]
0x18000acad  jmp     short loc_18000ACED
0x18000acaf  mov     rdx, [rbx]
0x18000acb2  lea     rcx, [rsp+58h+var_38]
0x18000acb7  call    ?make_string_tag@tson@@YA?AUansistring_tag@1@PEBD@Z; tson::make_string_tag(char const *)
0x18000acbc  mov     r8b, 17h
0x18000acbf  mov     rcx, rdi
0x18000acc2  mov     r14, [rax]
0x18000acc5  mov     rbp, [rax+8]
0x18000acc9  test    r14, r14
0x18000accc  setz    dl
0x18000accf  call    ?write_type@output_archive@tson@@AEAA_N_NW4archive_marker@details@2@@Z; tson::output_archive::write_type(bool,tson::details::archive_marker)
0x18000acd4  test    al, al
0x18000acd6  jz      short loc_18000ACE9
0x18000acd8  mov     r9, rbp; unsigned __int64
0x18000acdb  mov     r8, r14; void *
0x18000acde  mov     rdx, rbp; unsigned __int64
0x18000ace1  mov     rcx, rdi; this
0x18000ace4  call    ?write_string_bytes@output_archive@tson@@AEAAX_KPEAX0@Z; tson::output_archive::write_string_bytes(unsigned __int64,void *,unsigned __int64)
0x18000ace9  add     rbx, 8
0x18000aced  cmp     rbx, rsi
0x18000acf0  jnz     short loc_18000ACAF
0x18000acf2  mov     rbx, [rsp+58h+arg_0]
0x18000acf7  mov     rbp, [rsp+58h+arg_10]
0x18000acfc  add     rsp, 40h
0x18000ad00  pop     r14
0x18000ad02  pop     rdi
0x18000ad03  pop     rsi
0x18000ad04  retn
```
