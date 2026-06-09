# tip2::details::shared_data<0,0,0>::serialize_data(tson::write_buffer &,tip2::details::serialize_options)

- ea: `0x14001b764`
- end: `0x14001b8f8`
- name: `?serialize_data@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAPEBDAEAVwrite_buffer@tson@@W4serialize_options@23@@Z`
- size: `404`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `12`
- tags: `registry_config, service_task`

## callers

- `0x140019320`
- `0x140019650`
- `0x14001b938`

## callees

- `0x140003620`
- `0x1400048e4`
- `0x1400049a4`
- `0x14000787c`
- `0x1400079c0`
- `0x1400085d0`
- `0x1400199f0`
- `0x140019a5c`
- `0x14001a7cc`
- `0x14001b6fc`
- `0x14001b764`
- `0x14001bae8`

## pseudocode

```c
__int64 __fastcall tip2::details::shared_data<0,0,0>::serialize_data(
        __int64 a1,
        struct tson::write_buffer *a2,
        unsigned int a3)
{
  _BYTE *v6; // rsi
  __int64 v7; // rdx
  __int64 string_tag; // rax
  __int64 v9; // xmm1_8
  const char *v11; // [rsp+20h] [rbp-E0h] BYREF
  char v12; // [rsp+28h] [rbp-D8h]
  __int128 v13; // [rsp+30h] [rbp-D0h]
  __int64 v14; // [rsp+40h] [rbp-C0h]
  const char *v15; // [rsp+48h] [rbp-B8h] BYREF
  char v16; // [rsp+50h] [rbp-B0h]
  __int64 v17; // [rsp+58h] [rbp-A8h]
  const char *v18; // [rsp+60h] [rbp-A0h] BYREF
  char v19; // [rsp+68h] [rbp-98h]

  if ( a3 )
  {
    v6 = (_BYTE *)(a1 + 33);
    tson::output_archive::output_archive((tson::output_archive *)&v18, a2, *(_BYTE *)(a1 + 33));
    if ( (a3 & 4) != 0 && *v6 )
    {
      v12 = 7;
      v11 = "version";
      *(_QWORD *)&v13 = v6;
      tson::output_archive::operator()<tson::nvp<unsigned char &>>(&v18, &v11);
    }
    if ( (a3 & 1) != 0 )
    {
      if ( (*(_DWORD *)(a1 + 20) & 0x40000) != 0 )
      {
        v7 = *(_QWORD *)(a1 + 8);
        if ( !v7 )
          v7 = *(_QWORD *)(a1 + 24);
        string_tag = tson::make_string_tag(&v15, v7);
        v12 = 4;
        v11 = "name";
        v9 = *(_QWORD *)(string_tag + 16);
        v13 = *(_OWORD *)string_tag;
        v14 = v9;
        tson::output_archive::operator()<tson::nvp<tson::ansistring_tag>>(&v18, &v11);
      }
      v12 = 5;
      v11 = "flags";
      v16 = 6;
      *(_QWORD *)&v13 = a1 + 120;
      v15 = "errors";
      v17 = a1 + 72;
      v18 = "log";
      v19 = 3;
      tson::output_archive::startNode((tson::output_archive *)&v18);
      tson::save_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>>(
        (tson::output_archive *)&v18,
        a1 + 96);
      tson::output_archive::finishNode((tson::output_archive *)&v18);
      tson::output_archive::process<tson::nvp<tip2::vector_nothrow<wil::StoredFailureInfo> &>,tson::nvp<tip2::vector_nothrow<tip2::test_flag> &>>((tson::output_archive *)&v18);
    }
    tip2::details::shared_data<0,0,0>::serialize(a1, &v18, a3);
    if ( (int)tson::output_archive::finish((tson::output_archive *)&v18) >= 0 )
      return *((_QWORD *)a2 + 258);
    *(_DWORD *)(a1 + 64) |= 0x100000u;
  }
  return 0;
}

```

## disassembly

```asm
0x14001b764  push    rbp
0x14001b766  push    rbx
0x14001b767  push    rsi
0x14001b768  push    rdi
0x14001b769  push    r14
0x14001b76b  lea     rbp, [rsp-10h]
0x14001b770  sub     rsp, 110h
0x14001b777  mov     rax, cs:__security_cookie
0x14001b77e  xor     rax, rsp
0x14001b781  mov     [rbp+30h+var_30], rax
0x14001b785  mov     edi, r8d
0x14001b788  mov     r14, rdx
0x14001b78b  mov     rbx, rcx
0x14001b78e  test    r8d, r8d
0x14001b791  jz      loc_14001B8DC
0x14001b797  lea     rsi, [rcx+21h]
0x14001b79b  mov     r8b, [rsi]; unsigned __int8
0x14001b79e  lea     rcx, [rsp+130h+var_D0]; this
0x14001b7a3  call    ??0output_archive@tson@@QEAA@AEAVwrite_buffer@1@E@Z; tson::output_archive::output_archive(tson::write_buffer &,uchar)
0x14001b7a8  test    dil, 4
0x14001b7ac  jz      short loc_14001B7D8
0x14001b7ae  cmp     byte ptr [rsi], 0
0x14001b7b1  jbe     short loc_14001B7D8
0x14001b7b3  lea     rax, aVersion; "version"
0x14001b7ba  mov     [rsp+130h+var_108], 7
0x14001b7bf  lea     rdx, [rsp+130h+var_110]
0x14001b7c4  mov     [rsp+130h+var_110], rax
0x14001b7c9  lea     rcx, [rsp+130h+var_D0]
0x14001b7ce  mov     qword ptr [rsp+130h+var_100], rsi
0x14001b7d3  call    ??$?RV?$nvp@AEAE@tson@@@output_archive@tson@@QEAAAEAV01@$$QEAV?$nvp@AEAE@1@@Z; tson::output_archive::operator()<tson::nvp<uchar &>>(tson::nvp<uchar &> &&)
0x14001b7d8  test    dil, 1
0x14001b7dc  jz      loc_14001B8B0
0x14001b7e2  test    dword ptr [rbx+14h], 40000h
0x14001b7e9  jz      short loc_14001B835
0x14001b7eb  mov     rdx, [rbx+8]
0x14001b7ef  test    rdx, rdx
0x14001b7f2  jnz     short loc_14001B7F8
0x14001b7f4  mov     rdx, [rbx+18h]
0x14001b7f8  lea     rcx, [rsp+130h+var_E8]
0x14001b7fd  call    ?make_string_tag@tson@@YA?AUansistring_tag@1@PEBD@Z; tson::make_string_tag(char const *)
0x14001b802  lea     rcx, aName; "name"
0x14001b809  mov     [rsp+130h+var_108], 4
0x14001b80e  mov     [rsp+130h+var_110], rcx
0x14001b813  lea     rdx, [rsp+130h+var_110]
0x14001b818  lea     rcx, [rsp+130h+var_D0]
0x14001b81d  movups  xmm0, xmmword ptr [rax]
0x14001b820  movsd   xmm1, qword ptr [rax+10h]
0x14001b825  movups  [rsp+130h+var_100], xmm0
0x14001b82a  movsd   [rsp+130h+var_F0], xmm1
0x14001b830  call    ??$?RV?$nvp@Uansistring_tag@tson@@@tson@@@output_archive@tson@@QEAAAEAV01@$$QEAV?$nvp@Uansistring_tag@tson@@@1@@Z; tson::output_archive::operator()<tson::nvp<tson::ansistring_tag>>(tson::nvp<tson::ansistring_tag> &&)
0x14001b835  lea     rax, aFlags; "flags"
0x14001b83c  mov     [rsp+130h+var_108], 5
0x14001b841  mov     [rsp+130h+var_110], rax
0x14001b846  lea     rcx, [rsp+130h+var_D0]; this
0x14001b84b  lea     rax, [rbx+78h]
0x14001b84f  mov     [rsp+130h+var_E0], 6
0x14001b854  mov     qword ptr [rsp+130h+var_100], rax
0x14001b859  lea     rax, aErrors; "errors"
0x14001b860  mov     [rsp+130h+var_E8], rax
0x14001b865  lea     rax, [rbx+48h]
0x14001b869  mov     [rsp+130h+var_D8], rax
0x14001b86e  lea     rax, aLog; "log"
0x14001b875  mov     [rsp+130h+var_D0], rax
0x14001b87a  mov     [rsp+130h+var_C8], 3
0x14001b87f  call    ?startNode@output_archive@tson@@QEAAXXZ; tson::output_archive::startNode(void)
0x14001b884  lea     rdx, [rbx+60h]
0x14001b888  lea     rcx, [rsp+130h+var_D0]; this
0x14001b88d  call    ??$save_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@@tson@@YAXAEAVoutput_archive@0@AEAV?$vector_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@@tip2@@@Z; tson::save_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>>(tson::output_archive &,tip2::vector_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>> &)
0x14001b892  lea     rcx, [rsp+130h+var_D0]; this
0x14001b897  call    ?finishNode@output_archive@tson@@QEAAXXZ; tson::output_archive::finishNode(void)
0x14001b89c  lea     r8, [rsp+130h+var_110]
0x14001b8a1  lea     rdx, [rsp+130h+var_E8]
0x14001b8a6  lea     rcx, [rsp+130h+var_D0]; this
0x14001b8ab  call    ??$process@V?$nvp@AEAV?$vector_nothrow@VStoredFailureInfo@wil@@@tip2@@@tson@@V?$nvp@AEAV?$vector_nothrow@Utest_flag@tip2@@@tip2@@@2@@output_archive@tson@@AEAAX$$QEAV?$nvp@AEAV?$vector_nothrow@VStoredFailureInfo@wil@@@tip2@@@1@$$QEAV?$nvp@AEAV?$vector_nothrow@Utest_flag@tip2@@@tip2@@@1@@Z; tson::output_archive::process<tson::nvp<tip2::vector_nothrow<wil::StoredFailureInfo> &>,tson::nvp<tip2::vector_nothrow<tip2::test_flag> &>>(tson::nvp<tip2::vector_nothrow<wil::StoredFailureInfo> &> &&,tson::nvp<tip2::vector_nothrow<tip2::test_flag> &> &&)
0x14001b8b0  mov     r8d, edi
0x14001b8b3  lea     rdx, [rsp+130h+var_D0]
0x14001b8b8  mov     rcx, rbx
0x14001b8bb  call    ?serialize@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAXAEAVoutput_archive@tson@@W4serialize_options@23@@Z; tip2::details::shared_data<0,0,0>::serialize(tson::output_archive &,tip2::details::serialize_options)
0x14001b8c0  lea     rcx, [rsp+130h+var_D0]; this
0x14001b8c5  call    ?finish@output_archive@tson@@QEAAJXZ; tson::output_archive::finish(void)
0x14001b8ca  test    eax, eax
0x14001b8cc  js      short loc_14001B8D7
0x14001b8ce  mov     rax, [r14+810h]
0x14001b8d5  jmp     short loc_14001B8DE
0x14001b8d7  bts     dword ptr [rbx+40h], 14h
0x14001b8dc  xor     eax, eax
0x14001b8de  mov     rcx, [rbp+30h+var_30]
0x14001b8e2  xor     rcx, rsp; StackCookie
0x14001b8e5  call    __security_check_cookie
0x14001b8ea  add     rsp, 110h
0x14001b8f1  pop     r14
0x14001b8f3  pop     rdi
0x14001b8f4  pop     rsi
0x14001b8f5  pop     rbx
0x14001b8f6  pop     rbp
0x14001b8f7  retn
```
