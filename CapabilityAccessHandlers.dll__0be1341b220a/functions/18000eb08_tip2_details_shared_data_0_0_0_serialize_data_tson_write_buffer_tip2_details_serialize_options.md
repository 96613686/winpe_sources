# tip2::details::shared_data<0,0,0>::serialize_data(tson::write_buffer &,tip2::details::serialize_options)

- ea: `0x18000eb08`
- end: `0x18000ece3`
- name: `?serialize_data@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAPEBDAEAVwrite_buffer@tson@@W4serialize_options@23@@Z`
- size: `475`
- prototype: `__int64 __fastcall(__int64 *, struct tson::write_buffer *, unsigned int)`
- caller_count: `3`
- callee_count: `12`
- tags: `registry_config, service_task`

## callers

- `0x18000d3ec`
- `0x18000daac`
- `0x18000ed24`

## callees

- `0x180004c70`
- `0x18000a64c`
- `0x18000a6a0`
- `0x18000a97c`
- `0x18000ac78`
- `0x18000b13c`
- `0x18000de08`
- `0x18000df0c`
- `0x18000e01c`
- `0x18000eb08`
- `0x18000ef58`
- `0x180014010`

## pseudocode

```c
__int64 __fastcall tip2::details::shared_data<0,0,0>::serialize_data(
        __int64 *a1,
        struct tson::write_buffer *a2,
        unsigned int a3)
{
  _BYTE *v6; // rsi
  __int64 v7; // rdx
  __int64 string_tag; // rax
  __int64 v9; // r8
  __int64 v10; // rcx
  const char *v12; // [rsp+30h] [rbp-D0h] BYREF
  char v13; // [rsp+38h] [rbp-C8h]
  __int128 v14; // [rsp+40h] [rbp-C0h]
  __int64 v15; // [rsp+50h] [rbp-B0h]
  const char *v16; // [rsp+58h] [rbp-A8h] BYREF
  char v17; // [rsp+60h] [rbp-A0h]
  __int64 *v18; // [rsp+68h] [rbp-98h]
  const char *v19; // [rsp+70h] [rbp-90h] BYREF
  char v20; // [rsp+78h] [rbp-88h]

  if ( a3 )
  {
    v6 = (char *)a1 + 33;
    tson::output_archive::output_archive((tson::output_archive *)&v19, a2, *((_BYTE *)a1 + 33));
    if ( (a3 & 4) != 0 && *v6 )
    {
      v12 = "version";
      v13 = 7;
      *(_QWORD *)&v14 = v6;
      tson::output_archive::operator()<tson::nvp<unsigned char &>>(&v19, &v12);
    }
    if ( (a3 & 1) != 0 )
    {
      if ( (*((_DWORD *)a1 + 5) & 0x40000) != 0 )
      {
        v7 = a1[1];
        if ( !v7 )
          v7 = a1[3];
        string_tag = tson::make_string_tag((__int64)&v16, v7);
        v12 = "name";
        v13 = 4;
        v14 = *(_OWORD *)string_tag;
        v15 = *(_QWORD *)(string_tag + 16);
        tson::output_archive::operator()<tson::nvp<tson::ansistring_tag>>(&v19, &v12);
      }
      v12 = "flags";
      v13 = 5;
      *(_QWORD *)&v14 = a1 + 15;
      v16 = "errors";
      v17 = 6;
      v18 = a1 + 9;
      v19 = "log";
      v20 = 3;
      tson::output_archive::startNode((tson::output_archive *)&v19);
      tson::save_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>>(
        (tson::output_archive *)&v19,
        (__int64)(a1 + 12),
        v9);
      tson::output_archive::finishNode((tson::output_archive *)&v19);
      tson::output_archive::process<tson::nvp<tip2::vector_nothrow<wil::StoredFailureInfo> &>,tson::nvp<tip2::vector_nothrow<tip2::test_flag> &>>((tson::output_archive *)&v19);
    }
    v10 = *a1;
    if ( tip2::details::g_test_interface_exception_guard )
    {
      if ( !(unsigned __int8)((__int64 (__fastcall *)(__int64, const char **, _QWORD, _QWORD, _QWORD))tip2::details::g_test_interface_exception_guard)(
                               v10,
                               &v19,
                               a3,
                               0,
                               0) )
      {
        *((_BYTE *)a1 + 160) = 3;
        *((_WORD *)a1 + 81) = 16396;
        a1[21] = 0;
      }
    }
    else
    {
      (*(void (__fastcall **)(__int64, const char **, _QWORD))(*(_QWORD *)v10 + 8LL))(v10, &v19, a3);
    }
    if ( (int)tson::output_archive::finish((tson::output_archive *)&v19) >= 0 )
      return *((_QWORD *)a2 + 258);
    *((_DWORD *)a1 + 16) |= 0x100000u;
  }
  return 0;
}

```

## disassembly

```asm
0x18000eb08  push    rbp
0x18000eb0a  push    rbx
0x18000eb0b  push    rsi
0x18000eb0c  push    rdi
0x18000eb0d  push    r14
0x18000eb0f  lea     rbp, [rsp-20h]
0x18000eb14  sub     rsp, 120h
0x18000eb1b  mov     rax, cs:__security_cookie
0x18000eb22  xor     rax, rsp
0x18000eb25  mov     [rbp+40h+var_30], rax
0x18000eb29  mov     edi, r8d
0x18000eb2c  mov     r14, rdx
0x18000eb2f  mov     rbx, rcx
0x18000eb32  test    r8d, r8d
0x18000eb35  jz      loc_18000ECC7
0x18000eb3b  lea     rsi, [rcx+21h]
0x18000eb3f  mov     r8b, [rsi]; unsigned __int8
0x18000eb42  lea     rcx, [rsp+140h+var_D0]; this
0x18000eb47  call    ??0output_archive@tson@@QEAA@AEAVwrite_buffer@1@E@Z; tson::output_archive::output_archive(tson::write_buffer &,uchar)
0x18000eb4c  test    dil, 4
0x18000eb50  jz      short loc_18000EB7C
0x18000eb52  cmp     byte ptr [rsi], 0
0x18000eb55  jbe     short loc_18000EB7C
0x18000eb57  lea     rax, aVersion; "version"
0x18000eb5e  mov     [rsp+140h+var_110], rax
0x18000eb63  mov     [rsp+140h+var_108], 7
0x18000eb68  mov     qword ptr [rsp+140h+var_100], rsi
0x18000eb6d  lea     rdx, [rsp+140h+var_110]
0x18000eb72  lea     rcx, [rsp+140h+var_D0]
0x18000eb77  call    ??$?RV?$nvp@AEAE@tson@@@output_archive@tson@@QEAAAEAV01@$$QEAV?$nvp@AEAE@1@@Z; tson::output_archive::operator()<tson::nvp<uchar &>>(tson::nvp<uchar &> &&)
0x18000eb7c  test    dil, 1
0x18000eb80  jz      loc_18000EC55
0x18000eb86  test    dword ptr [rbx+14h], 40000h
0x18000eb8d  jz      short loc_18000EBD9
0x18000eb8f  mov     rdx, [rbx+8]
0x18000eb93  test    rdx, rdx
0x18000eb96  jnz     short loc_18000EB9C
0x18000eb98  mov     rdx, [rbx+18h]
0x18000eb9c  lea     rcx, [rsp+140h+var_E8]
0x18000eba1  call    ?make_string_tag@tson@@YA?AUansistring_tag@1@PEBD@Z; tson::make_string_tag(char const *)
0x18000eba6  lea     rcx, aName; "name"
0x18000ebad  mov     [rsp+140h+var_110], rcx
0x18000ebb2  mov     [rsp+140h+var_108], 4
0x18000ebb7  movups  xmm0, xmmword ptr [rax]
0x18000ebba  movups  [rsp+140h+var_100], xmm0
0x18000ebbf  movsd   xmm1, qword ptr [rax+10h]
0x18000ebc4  movsd   [rsp+140h+var_F0], xmm1
0x18000ebca  lea     rdx, [rsp+140h+var_110]
0x18000ebcf  lea     rcx, [rsp+140h+var_D0]
0x18000ebd4  call    ??$?RV?$nvp@Uansistring_tag@tson@@@tson@@@output_archive@tson@@QEAAAEAV01@$$QEAV?$nvp@Uansistring_tag@tson@@@1@@Z; tson::output_archive::operator()<tson::nvp<tson::ansistring_tag>>(tson::nvp<tson::ansistring_tag> &&)
0x18000ebd9  lea     rax, aFlags; "flags"
0x18000ebe0  mov     [rsp+140h+var_110], rax
0x18000ebe5  mov     [rsp+140h+var_108], 5
0x18000ebea  lea     rax, [rbx+78h]
0x18000ebee  mov     qword ptr [rsp+140h+var_100], rax
0x18000ebf3  lea     rax, aErrors; "errors"
0x18000ebfa  mov     [rsp+140h+var_E8], rax
0x18000ebff  mov     [rsp+140h+var_E0], 6
0x18000ec04  lea     rax, [rbx+48h]
0x18000ec08  mov     [rsp+140h+var_D8], rax
0x18000ec0d  lea     rax, aLog; "log"
0x18000ec14  mov     [rsp+140h+var_D0], rax
0x18000ec19  mov     [rsp+140h+var_C8], 3
0x18000ec1e  lea     rcx, [rsp+140h+var_D0]; this
0x18000ec23  call    ?startNode@output_archive@tson@@QEAAXXZ; tson::output_archive::startNode(void)
0x18000ec28  lea     rdx, [rbx+60h]
0x18000ec2c  lea     rcx, [rsp+140h+var_D0]; this
0x18000ec31  call    ??$save_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@@tson@@YAXAEAVoutput_archive@0@AEAV?$vector_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@@tip2@@@Z; tson::save_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>>(tson::output_archive &,tip2::vector_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>> &)
0x18000ec36  lea     rcx, [rsp+140h+var_D0]; this
0x18000ec3b  call    ?finishNode@output_archive@tson@@QEAAXXZ; tson::output_archive::finishNode(void)
0x18000ec40  lea     r8, [rsp+140h+var_110]
0x18000ec45  lea     rdx, [rsp+140h+var_E8]
0x18000ec4a  lea     rcx, [rsp+140h+var_D0]; this
0x18000ec4f  call    ??$process@V?$nvp@AEAV?$vector_nothrow@VStoredFailureInfo@wil@@@tip2@@@tson@@V?$nvp@AEAV?$vector_nothrow@Utest_flag@tip2@@@tip2@@@2@@output_archive@tson@@AEAAX$$QEAV?$nvp@AEAV?$vector_nothrow@VStoredFailureInfo@wil@@@tip2@@@1@$$QEAV?$nvp@AEAV?$vector_nothrow@Utest_flag@tip2@@@tip2@@@1@@Z; tson::output_archive::process<tson::nvp<tip2::vector_nothrow<wil::StoredFailureInfo> &>,tson::nvp<tip2::vector_nothrow<tip2::test_flag> &>>(tson::nvp<tip2::vector_nothrow<wil::StoredFailureInfo> &> &&,tson::nvp<tip2::vector_nothrow<tip2::test_flag> &> &&)
0x18000ec54  nop
0x18000ec55  mov     rcx, [rbx]
0x18000ec58  mov     rax, cs:?g_test_interface_exception_guard@details@tip2@@3P6A_NAEAUtest_data_interface@12@PEAVoutput_archive@tson@@W4serialize_options@12@PEAVinput_archive@5@PEBUTipReportingInfo@@@_EEA
0x18000ec5f  mov     r8d, edi
0x18000ec62  lea     rdx, [rsp+140h+var_D0]
0x18000ec67  test    rax, rax
0x18000ec6a  jz      short loc_18000EC9E
0x18000ec6c  mov     [rsp+140h+var_120], 0
0x18000ec75  xor     r9d, r9d
0x18000ec78  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ec7d  test    al, al
0x18000ec7f  jnz     short loc_18000ECAB
0x18000ec81  mov     byte ptr [rbx+0A0h], 3
0x18000ec88  mov     word ptr [rbx+0A2h], 400Ch
0x18000ec91  mov     qword ptr [rbx+0A8h], 0
0x18000ec9c  jmp     short loc_18000ECAB
0x18000ec9e  mov     rax, [rcx]
0x18000eca1  mov     rax, [rax+8]
0x18000eca5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ecaa  nop
0x18000ecab  lea     rcx, [rsp+140h+var_D0]; this
0x18000ecb0  call    ?finish@output_archive@tson@@QEAAJXZ; tson::output_archive::finish(void)
0x18000ecb5  test    eax, eax
0x18000ecb7  js      short loc_18000ECC2
0x18000ecb9  mov     rax, [r14+810h]
0x18000ecc0  jmp     short loc_18000ECC9
0x18000ecc2  bts     dword ptr [rbx+40h], 14h
0x18000ecc7  xor     eax, eax
0x18000ecc9  mov     rcx, [rbp+40h+var_30]
0x18000eccd  xor     rcx, rsp; StackCookie
0x18000ecd0  call    __security_check_cookie
0x18000ecd5  add     rsp, 120h
0x18000ecdc  pop     r14
0x18000ecde  pop     rdi
0x18000ecdf  pop     rsi
0x18000ece0  pop     rbx
0x18000ece1  pop     rbp
0x18000ece2  retn
```
