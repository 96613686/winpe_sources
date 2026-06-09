# tip2::details::shared_data<1,0,0>::serialize_data(tson::write_buffer &,tip2::details::serialize_options)

- ea: `0x180025900`
- end: `0x180025a94`
- name: `?serialize_data@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAPEBDAEAVwrite_buffer@tson@@W4serialize_options@23@@Z`
- size: `404`
- prototype: ``
- caller_count: `3`
- callee_count: `12`
- tags: `registry_config, service_task`

## callers

- `0x180023708`
- `0x180023a04`
- `0x180025af0`

## callees

- `0x180003560`
- `0x18000974c`
- `0x180009c80`
- `0x180016c6c`
- `0x180017998`
- `0x18001ac68`
- `0x180023d64`
- `0x180023e20`
- `0x1800246fc`
- `0x18002589c`
- `0x180025900`
- `0x180025d50`

## pseudocode

```c
__int64 __fastcall tip2::details::shared_data<1,0,0>::serialize_data(
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
    tip2::details::shared_data<1,0,0>::serialize(a1, &v18, a3);
    if ( (int)tson::output_archive::finish((tson::output_archive *)&v18) >= 0 )
      return *((_QWORD *)a2 + 258);
    *(_DWORD *)(a1 + 64) |= 0x100000u;
  }
  return 0;
}

```

## disassembly

```asm
0x180025900  push    rbp
0x180025902  push    rbx
0x180025903  push    rsi
0x180025904  push    rdi
0x180025905  push    r14
0x180025907  lea     rbp, [rsp-10h]
0x18002590c  sub     rsp, 110h
0x180025913  mov     rax, cs:__security_cookie
0x18002591a  xor     rax, rsp
0x18002591d  mov     [rbp+30h+var_30], rax
0x180025921  mov     edi, r8d
0x180025924  mov     r14, rdx
0x180025927  mov     rbx, rcx
0x18002592a  test    r8d, r8d
0x18002592d  jz      loc_180025A78
0x180025933  lea     rsi, [rcx+21h]
0x180025937  mov     r8b, [rsi]; unsigned __int8
0x18002593a  lea     rcx, [rsp+130h+var_D0]; this
0x18002593f  call    ??0output_archive@tson@@QEAA@AEAVwrite_buffer@1@E@Z; tson::output_archive::output_archive(tson::write_buffer &,uchar)
0x180025944  test    dil, 4
0x180025948  jz      short loc_180025974
0x18002594a  cmp     byte ptr [rsi], 0
0x18002594d  jbe     short loc_180025974
0x18002594f  lea     rax, aVersion; "version"
0x180025956  mov     [rsp+130h+var_108], 7
0x18002595b  lea     rdx, [rsp+130h+var_110]
0x180025960  mov     [rsp+130h+var_110], rax
0x180025965  lea     rcx, [rsp+130h+var_D0]
0x18002596a  mov     qword ptr [rsp+130h+var_100], rsi
0x18002596f  call    ??$?RV?$nvp@AEAE@tson@@@output_archive@tson@@QEAAAEAV01@$$QEAV?$nvp@AEAE@1@@Z; tson::output_archive::operator()<tson::nvp<uchar &>>(tson::nvp<uchar &> &&)
0x180025974  test    dil, 1
0x180025978  jz      loc_180025A4C
0x18002597e  test    dword ptr [rbx+14h], 40000h
0x180025985  jz      short loc_1800259D1
0x180025987  mov     rdx, [rbx+8]
0x18002598b  test    rdx, rdx
0x18002598e  jnz     short loc_180025994
0x180025990  mov     rdx, [rbx+18h]
0x180025994  lea     rcx, [rsp+130h+var_E8]
0x180025999  call    ?make_string_tag@tson@@YA?AUansistring_tag@1@PEBD@Z; tson::make_string_tag(char const *)
0x18002599e  lea     rcx, aName; "name"
0x1800259a5  mov     [rsp+130h+var_108], 4
0x1800259aa  mov     [rsp+130h+var_110], rcx
0x1800259af  lea     rdx, [rsp+130h+var_110]
0x1800259b4  lea     rcx, [rsp+130h+var_D0]
0x1800259b9  movups  xmm0, xmmword ptr [rax]
0x1800259bc  movsd   xmm1, qword ptr [rax+10h]
0x1800259c1  movups  [rsp+130h+var_100], xmm0
0x1800259c6  movsd   [rsp+130h+var_F0], xmm1
0x1800259cc  call    ??$?RV?$nvp@Uansistring_tag@tson@@@tson@@@output_archive@tson@@QEAAAEAV01@$$QEAV?$nvp@Uansistring_tag@tson@@@1@@Z; tson::output_archive::operator()<tson::nvp<tson::ansistring_tag>>(tson::nvp<tson::ansistring_tag> &&)
0x1800259d1  lea     rax, aFlags; "flags"
0x1800259d8  mov     [rsp+130h+var_108], 5
0x1800259dd  mov     [rsp+130h+var_110], rax
0x1800259e2  lea     rcx, [rsp+130h+var_D0]; this
0x1800259e7  lea     rax, [rbx+78h]
0x1800259eb  mov     [rsp+130h+var_E0], 6
0x1800259f0  mov     qword ptr [rsp+130h+var_100], rax
0x1800259f5  lea     rax, aErrors; "errors"
0x1800259fc  mov     [rsp+130h+var_E8], rax
0x180025a01  lea     rax, [rbx+48h]
0x180025a05  mov     [rsp+130h+var_D8], rax
0x180025a0a  lea     rax, aLog; "log"
0x180025a11  mov     [rsp+130h+var_D0], rax
0x180025a16  mov     [rsp+130h+var_C8], 3
0x180025a1b  call    ?startNode@output_archive@tson@@QEAAXXZ; tson::output_archive::startNode(void)
0x180025a20  lea     rdx, [rbx+60h]
0x180025a24  lea     rcx, [rsp+130h+var_D0]; this
0x180025a29  call    ??$save_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@@tson@@YAXAEAVoutput_archive@0@AEAV?$vector_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@@tip2@@@Z; tson::save_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>>(tson::output_archive &,tip2::vector_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>> &)
0x180025a2e  lea     rcx, [rsp+130h+var_D0]; this
0x180025a33  call    ?finishNode@output_archive@tson@@QEAAXXZ; tson::output_archive::finishNode(void)
0x180025a38  lea     r8, [rsp+130h+var_110]
0x180025a3d  lea     rdx, [rsp+130h+var_E8]
0x180025a42  lea     rcx, [rsp+130h+var_D0]; this
0x180025a47  call    ??$process@V?$nvp@AEAV?$vector_nothrow@VStoredFailureInfo@wil@@@tip2@@@tson@@V?$nvp@AEAV?$vector_nothrow@Utest_flag@tip2@@@tip2@@@2@@output_archive@tson@@AEAAX$$QEAV?$nvp@AEAV?$vector_nothrow@VStoredFailureInfo@wil@@@tip2@@@1@$$QEAV?$nvp@AEAV?$vector_nothrow@Utest_flag@tip2@@@tip2@@@1@@Z; tson::output_archive::process<tson::nvp<tip2::vector_nothrow<wil::StoredFailureInfo> &>,tson::nvp<tip2::vector_nothrow<tip2::test_flag> &>>(tson::nvp<tip2::vector_nothrow<wil::StoredFailureInfo> &> &&,tson::nvp<tip2::vector_nothrow<tip2::test_flag> &> &&)
0x180025a4c  mov     r8d, edi
0x180025a4f  lea     rdx, [rsp+130h+var_D0]
0x180025a54  mov     rcx, rbx
0x180025a57  call    ?serialize@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAXAEAVoutput_archive@tson@@W4serialize_options@23@@Z; tip2::details::shared_data<1,0,0>::serialize(tson::output_archive &,tip2::details::serialize_options)
0x180025a5c  lea     rcx, [rsp+130h+var_D0]; this
0x180025a61  call    ?finish@output_archive@tson@@QEAAJXZ; tson::output_archive::finish(void)
0x180025a66  test    eax, eax
0x180025a68  js      short loc_180025A73
0x180025a6a  mov     rax, [r14+810h]
0x180025a71  jmp     short loc_180025A7A
0x180025a73  bts     dword ptr [rbx+40h], 14h
0x180025a78  xor     eax, eax
0x180025a7a  mov     rcx, [rbp+30h+var_30]
0x180025a7e  xor     rcx, rsp; StackCookie
0x180025a81  call    __security_check_cookie
0x180025a86  add     rsp, 110h
0x180025a8d  pop     r14
0x180025a8f  pop     rdi
0x180025a90  pop     rsi
0x180025a91  pop     rbx
0x180025a92  pop     rbp
0x180025a93  retn
```
