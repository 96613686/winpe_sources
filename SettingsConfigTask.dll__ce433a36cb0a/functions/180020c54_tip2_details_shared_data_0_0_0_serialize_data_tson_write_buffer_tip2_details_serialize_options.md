# tip2::details::shared_data<0,0,0>::serialize_data(tson::write_buffer &,tip2::details::serialize_options)

- ea: `0x180020c54`
- end: `0x180020e14`
- name: `?serialize_data@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAPEBDAEAVwrite_buffer@tson@@W4serialize_options@23@@Z`
- size: `448`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `9`
- tags: `registry_config, service_task`

## callers

- `0x18001dfc0`
- `0x18001e6f8`
- `0x180020f74`

## callees

- `0x1800021d0`
- `0x18000c6c0`
- `0x18000c970`
- `0x18000caa0`
- `0x180012218`
- `0x18001eac4`
- `0x18001f600`
- `0x180020c54`
- `0x180024010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall tip2::details::shared_data<0,0,0>::serialize_data(
        __int64 *a1,
        struct tson::write_buffer *a2,
        unsigned int a3)
{
  _BYTE *v6; // rsi
  __int64 v7; // rdx
  __int64 string_tag; // rax
  __int64 v9; // rcx
  const char *v11; // [rsp+30h] [rbp-D0h] BYREF
  char v12; // [rsp+38h] [rbp-C8h]
  _BYTE *v13; // [rsp+40h] [rbp-C0h]
  const char *v14; // [rsp+48h] [rbp-B8h] BYREF
  char v15; // [rsp+50h] [rbp-B0h]
  __int128 v16; // [rsp+58h] [rbp-A8h]
  __int64 v17; // [rsp+68h] [rbp-98h]
  const char *v18; // [rsp+70h] [rbp-90h] BYREF
  char v19; // [rsp+78h] [rbp-88h]
  __int64 *v20; // [rsp+80h] [rbp-80h]
  _BYTE v21[160]; // [rsp+90h] [rbp-70h] BYREF

  if ( a3 )
  {
    v6 = (char *)a1 + 33;
    tson::output_archive::output_archive((tson::output_archive *)v21, a2, *((_BYTE *)a1 + 33));
    if ( (a3 & 4) != 0 && *v6 )
    {
      v11 = "version";
      v12 = 7;
      v13 = v6;
      tson::output_archive::operator()<tson::nvp<unsigned char &>>(v21, &v11);
    }
    if ( (a3 & 1) != 0 )
    {
      if ( (*((_DWORD *)a1 + 5) & 0x40000) != 0 )
      {
        v7 = a1[1];
        if ( !v7 )
          v7 = a1[3];
        string_tag = tson::make_string_tag(&v18, v7);
        v14 = "name";
        v15 = 4;
        v16 = *(_OWORD *)string_tag;
        v17 = *(_QWORD *)(string_tag + 16);
        tson::output_archive::operator()<tson::nvp<tson::ansistring_tag>>(v21, &v14);
      }
      v11 = "flags";
      v12 = 5;
      v13 = a1 + 15;
      v14 = "errors";
      v15 = 6;
      *(_QWORD *)&v16 = a1 + 9;
      v18 = "log";
      v19 = 3;
      v20 = a1 + 12;
      tson::output_archive::operator()<tson::nvp<tip2::vector_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>> &>,tson::nvp<tip2::vector_nothrow<wil::StoredFailureInfo> &>,tson::nvp<tip2::vector_nothrow<tip2::test_flag> &>>(
        (tson::output_archive *)v21,
        (__int64)&v18);
    }
    v9 = *a1;
    if ( tip2::details::g_test_interface_exception_guard )
    {
      if ( !(unsigned __int8)tip2::details::g_test_interface_exception_guard(v9, v21, a3, 0, 0) )
      {
        *((_BYTE *)a1 + 160) = 3;
        *((_WORD *)a1 + 81) = 16396;
        a1[21] = 0;
      }
    }
    else
    {
      (*(void (__fastcall **)(__int64, _BYTE *, _QWORD))(*(_QWORD *)v9 + 8LL))(v9, v21, a3);
    }
    if ( (int)tson::output_archive::finish((tson::output_archive *)v21) >= 0 )
      return *((_QWORD *)a2 + 258);
    *((_DWORD *)a1 + 16) |= 0x100000u;
  }
  return 0;
}

```

## disassembly

```asm
0x180020c54  push    rbp
0x180020c56  push    rbx
0x180020c57  push    rsi
0x180020c58  push    rdi
0x180020c59  push    r14
0x180020c5b  lea     rbp, [rsp-40h]
0x180020c60  sub     rsp, 140h
0x180020c67  mov     rax, cs:__security_cookie
0x180020c6e  xor     rax, rsp
0x180020c71  mov     [rbp+60h+var_30], rax
0x180020c75  mov     edi, r8d
0x180020c78  mov     r14, rdx
0x180020c7b  mov     rbx, rcx
0x180020c7e  test    r8d, r8d
0x180020c81  jz      loc_180020DF8
0x180020c87  lea     rsi, [rcx+21h]
0x180020c8b  mov     r8b, [rsi]; unsigned __int8
0x180020c8e  lea     rcx, [rbp+60h+var_D0]; this
0x180020c92  call    ??0output_archive@tson@@QEAA@AEAVwrite_buffer@1@E@Z; tson::output_archive::output_archive(tson::write_buffer &,uchar)
0x180020c97  test    dil, 4
0x180020c9b  jz      short loc_180020CC6
0x180020c9d  cmp     byte ptr [rsi], 0
0x180020ca0  jbe     short loc_180020CC6
0x180020ca2  lea     rax, aVersion; "version"
0x180020ca9  mov     [rsp+160h+var_130], rax
0x180020cae  mov     [rsp+160h+var_128], 7
0x180020cb3  mov     [rsp+160h+var_120], rsi
0x180020cb8  lea     rdx, [rsp+160h+var_130]
0x180020cbd  lea     rcx, [rbp+60h+var_D0]
0x180020cc1  call    ??$?RV?$nvp@AEAE@tson@@@output_archive@tson@@QEAAAEAV01@$$QEAV?$nvp@AEAE@1@@Z; tson::output_archive::operator()<tson::nvp<uchar &>>(tson::nvp<uchar &> &&)
0x180020cc6  test    dil, 1
0x180020cca  jz      loc_180020D88
0x180020cd0  test    dword ptr [rbx+14h], 40000h
0x180020cd7  jz      short loc_180020D22
0x180020cd9  mov     rdx, [rbx+8]
0x180020cdd  test    rdx, rdx
0x180020ce0  jnz     short loc_180020CE6
0x180020ce2  mov     rdx, [rbx+18h]
0x180020ce6  lea     rcx, [rsp+160h+var_F0]
0x180020ceb  call    ?make_string_tag@tson@@YA?AUansistring_tag@1@PEBD@Z; tson::make_string_tag(char const *)
0x180020cf0  lea     rcx, aName; "name"
0x180020cf7  mov     [rsp+160h+var_118], rcx
0x180020cfc  mov     [rsp+160h+var_110], 4
0x180020d01  movups  xmm0, xmmword ptr [rax]
0x180020d04  movups  [rsp+160h+var_108], xmm0
0x180020d09  movsd   xmm1, qword ptr [rax+10h]
0x180020d0e  movsd   [rsp+160h+var_F8], xmm1
0x180020d14  lea     rdx, [rsp+160h+var_118]
0x180020d19  lea     rcx, [rbp+60h+var_D0]
0x180020d1d  call    ??$?RV?$nvp@Uansistring_tag@tson@@@tson@@@output_archive@tson@@QEAAAEAV01@$$QEAV?$nvp@Uansistring_tag@tson@@@1@@Z; tson::output_archive::operator()<tson::nvp<tson::ansistring_tag>>(tson::nvp<tson::ansistring_tag> &&)
0x180020d22  lea     rax, aFlags; "flags"
0x180020d29  mov     [rsp+160h+var_130], rax
0x180020d2e  mov     [rsp+160h+var_128], 5
0x180020d33  lea     rax, [rbx+78h]
0x180020d37  mov     [rsp+160h+var_120], rax
0x180020d3c  lea     rax, aErrors; "errors"
0x180020d43  mov     [rsp+160h+var_118], rax
0x180020d48  mov     [rsp+160h+var_110], 6
0x180020d4d  lea     rax, [rbx+48h]
0x180020d51  mov     qword ptr [rsp+160h+var_108], rax
0x180020d56  lea     rax, aLog; "log"
0x180020d5d  mov     [rsp+160h+var_F0], rax
0x180020d62  mov     [rsp+160h+var_E8], 3
0x180020d67  lea     rax, [rbx+60h]
0x180020d6b  mov     [rbp+60h+var_E0], rax
0x180020d6f  lea     r9, [rsp+160h+var_130]
0x180020d74  lea     r8, [rsp+160h+var_118]
0x180020d79  lea     rdx, [rsp+160h+var_F0]
0x180020d7e  lea     rcx, [rbp+60h+var_D0]; this
0x180020d82  call    ??$?RV?$nvp@AEAV?$vector_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@@tip2@@@tson@@V?$nvp@AEAV?$vector_nothrow@VStoredFailureInfo@wil@@@tip2@@@1@V?$nvp@AEAV?$vector_nothrow@Utest_flag@tip2@@@tip2@@@1@@output_archive@tson@@QEAAAEAV01@$$QEAV?$nvp@AEAV?$vector_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@@tip2@@@1@$$QEAV?$nvp@AEAV?$vector_nothrow@VStoredFailureInfo@wil@@@tip2@@@1@$$QEAV?$nvp@AEAV?$vector_nothrow@Utest_flag@tip2@@@tip2@@@1@@Z; tson::output_archive::operator()<tson::nvp<tip2::vector_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>> &>,tson::nvp<tip2::vector_nothrow<wil::StoredFailureInfo> &>,tson::nvp<tip2::vector_nothrow<tip2::test_flag> &>>(tson::nvp<tip2::vector_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>> &> &&,tson::nvp<tip2::vector_nothrow<wil::StoredFailureInfo> &> &&,tson::nvp<tip2::vector_nothrow<tip2::test_flag> &> &&)
0x180020d87  nop
0x180020d88  mov     rcx, [rbx]
0x180020d8b  mov     rax, cs:?g_test_interface_exception_guard@details@tip2@@3P6A_NAEAUtest_data_interface@12@PEAVoutput_archive@tson@@W4serialize_options@12@PEAVinput_archive@5@PEBUTipReportingInfo@@@_EEA
0x180020d92  mov     r8d, edi
0x180020d95  lea     rdx, [rbp+60h+var_D0]
0x180020d99  test    rax, rax
0x180020d9c  jz      short loc_180020DD0
0x180020d9e  mov     [rsp+160h+var_140], 0
0x180020da7  xor     r9d, r9d
0x180020daa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020daf  test    al, al
0x180020db1  jnz     short loc_180020DDD
0x180020db3  mov     byte ptr [rbx+0A0h], 3
0x180020dba  mov     word ptr [rbx+0A2h], 400Ch
0x180020dc3  mov     qword ptr [rbx+0A8h], 0
0x180020dce  jmp     short loc_180020DDD
0x180020dd0  mov     rax, [rcx]
0x180020dd3  mov     rax, [rax+8]
0x180020dd7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020ddc  nop
0x180020ddd  lea     rcx, [rbp+60h+var_D0]; this
0x180020de1  call    ?finish@output_archive@tson@@QEAAJXZ; tson::output_archive::finish(void)
0x180020de6  test    eax, eax
0x180020de8  js      short loc_180020DF3
0x180020dea  mov     rax, [r14+810h]
0x180020df1  jmp     short loc_180020DFA
0x180020df3  bts     dword ptr [rbx+40h], 14h
0x180020df8  xor     eax, eax
0x180020dfa  mov     rcx, [rbp+60h+var_30]
0x180020dfe  xor     rcx, rsp; StackCookie
0x180020e01  call    __security_check_cookie
0x180020e06  add     rsp, 140h
0x180020e0d  pop     r14
0x180020e0f  pop     rdi
0x180020e10  pop     rsi
0x180020e11  pop     rbx
0x180020e12  pop     rbp
0x180020e13  retn
```
