# tip2::details::shared_data<0,0,0>::serialize_data(tson::write_buffer &,tip2::details::serialize_options)

- ea: `0x18000e47c`
- end: `0x18000e657`
- name: `?serialize_data@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAPEBDAEAVwrite_buffer@tson@@W4serialize_options@23@@Z`
- size: `475`
- prototype: `__int64 __fastcall(__int64 *, struct tson::write_buffer *, unsigned int)`
- caller_count: `3`
- callee_count: `12`
- tags: `registry_config, service_task`

## callers

- `0x18000d5ec`
- `0x180012ec0`
- `0x180013540`

## callees

- `0x180002c00`
- `0x18000a730`
- `0x18000a784`
- `0x18000aaac`
- `0x18000aee8`
- `0x18000b3b0`
- `0x18000d9e0`
- `0x18000da94`
- `0x18000dba4`
- `0x18000e47c`
- `0x18000e698`
- `0x18001c010`

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
        string_tag = tson::make_string_tag(&v16, v7);
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
0x18000e47c  push    rbp
0x18000e47e  push    rbx
0x18000e47f  push    rsi
0x18000e480  push    rdi
0x18000e481  push    r14
0x18000e483  lea     rbp, [rsp-20h]
0x18000e488  sub     rsp, 120h
0x18000e48f  mov     rax, cs:__security_cookie
0x18000e496  xor     rax, rsp
0x18000e499  mov     [rbp+40h+var_30], rax
0x18000e49d  mov     edi, r8d
0x18000e4a0  mov     r14, rdx
0x18000e4a3  mov     rbx, rcx
0x18000e4a6  test    r8d, r8d
0x18000e4a9  jz      loc_18000E63B
0x18000e4af  lea     rsi, [rcx+21h]
0x18000e4b3  mov     r8b, [rsi]; unsigned __int8
0x18000e4b6  lea     rcx, [rsp+140h+var_D0]; this
0x18000e4bb  call    ??0output_archive@tson@@QEAA@AEAVwrite_buffer@1@E@Z; tson::output_archive::output_archive(tson::write_buffer &,uchar)
0x18000e4c0  test    dil, 4
0x18000e4c4  jz      short loc_18000E4F0
0x18000e4c6  cmp     byte ptr [rsi], 0
0x18000e4c9  jbe     short loc_18000E4F0
0x18000e4cb  lea     rax, aVersion; "version"
0x18000e4d2  mov     [rsp+140h+var_110], rax
0x18000e4d7  mov     [rsp+140h+var_108], 7
0x18000e4dc  mov     qword ptr [rsp+140h+var_100], rsi
0x18000e4e1  lea     rdx, [rsp+140h+var_110]
0x18000e4e6  lea     rcx, [rsp+140h+var_D0]
0x18000e4eb  call    ??$?RV?$nvp@AEAE@tson@@@output_archive@tson@@QEAAAEAV01@$$QEAV?$nvp@AEAE@1@@Z; tson::output_archive::operator()<tson::nvp<uchar &>>(tson::nvp<uchar &> &&)
0x18000e4f0  test    dil, 1
0x18000e4f4  jz      loc_18000E5C9
0x18000e4fa  test    dword ptr [rbx+14h], 40000h
0x18000e501  jz      short loc_18000E54D
0x18000e503  mov     rdx, [rbx+8]
0x18000e507  test    rdx, rdx
0x18000e50a  jnz     short loc_18000E510
0x18000e50c  mov     rdx, [rbx+18h]
0x18000e510  lea     rcx, [rsp+140h+var_E8]
0x18000e515  call    ?make_string_tag@tson@@YA?AUansistring_tag@1@PEBD@Z; tson::make_string_tag(char const *)
0x18000e51a  lea     rcx, aName; "name"
0x18000e521  mov     [rsp+140h+var_110], rcx
0x18000e526  mov     [rsp+140h+var_108], 4
0x18000e52b  movups  xmm0, xmmword ptr [rax]
0x18000e52e  movups  [rsp+140h+var_100], xmm0
0x18000e533  movsd   xmm1, qword ptr [rax+10h]
0x18000e538  movsd   [rsp+140h+var_F0], xmm1
0x18000e53e  lea     rdx, [rsp+140h+var_110]
0x18000e543  lea     rcx, [rsp+140h+var_D0]
0x18000e548  call    ??$?RV?$nvp@Uansistring_tag@tson@@@tson@@@output_archive@tson@@QEAAAEAV01@$$QEAV?$nvp@Uansistring_tag@tson@@@1@@Z; tson::output_archive::operator()<tson::nvp<tson::ansistring_tag>>(tson::nvp<tson::ansistring_tag> &&)
0x18000e54d  lea     rax, aFlags; "flags"
0x18000e554  mov     [rsp+140h+var_110], rax
0x18000e559  mov     [rsp+140h+var_108], 5
0x18000e55e  lea     rax, [rbx+78h]
0x18000e562  mov     qword ptr [rsp+140h+var_100], rax
0x18000e567  lea     rax, aErrors; "errors"
0x18000e56e  mov     [rsp+140h+var_E8], rax
0x18000e573  mov     [rsp+140h+var_E0], 6
0x18000e578  lea     rax, [rbx+48h]
0x18000e57c  mov     [rsp+140h+var_D8], rax
0x18000e581  lea     rax, aLog; "log"
0x18000e588  mov     [rsp+140h+var_D0], rax
0x18000e58d  mov     [rsp+140h+var_C8], 3
0x18000e592  lea     rcx, [rsp+140h+var_D0]; this
0x18000e597  call    ?startNode@output_archive@tson@@QEAAXXZ; tson::output_archive::startNode(void)
0x18000e59c  lea     rdx, [rbx+60h]
0x18000e5a0  lea     rcx, [rsp+140h+var_D0]; this
0x18000e5a5  call    ??$save_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@@tson@@YAXAEAVoutput_archive@0@AEAV?$vector_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@@tip2@@@Z; tson::save_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>>(tson::output_archive &,tip2::vector_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>> &)
0x18000e5aa  lea     rcx, [rsp+140h+var_D0]; this
0x18000e5af  call    ?finishNode@output_archive@tson@@QEAAXXZ; tson::output_archive::finishNode(void)
0x18000e5b4  lea     r8, [rsp+140h+var_110]
0x18000e5b9  lea     rdx, [rsp+140h+var_E8]
0x18000e5be  lea     rcx, [rsp+140h+var_D0]; this
0x18000e5c3  call    ??$process@V?$nvp@AEAV?$vector_nothrow@VStoredFailureInfo@wil@@@tip2@@@tson@@V?$nvp@AEAV?$vector_nothrow@Utest_flag@tip2@@@tip2@@@2@@output_archive@tson@@AEAAX$$QEAV?$nvp@AEAV?$vector_nothrow@VStoredFailureInfo@wil@@@tip2@@@1@$$QEAV?$nvp@AEAV?$vector_nothrow@Utest_flag@tip2@@@tip2@@@1@@Z; tson::output_archive::process<tson::nvp<tip2::vector_nothrow<wil::StoredFailureInfo> &>,tson::nvp<tip2::vector_nothrow<tip2::test_flag> &>>(tson::nvp<tip2::vector_nothrow<wil::StoredFailureInfo> &> &&,tson::nvp<tip2::vector_nothrow<tip2::test_flag> &> &&)
0x18000e5c8  nop
0x18000e5c9  mov     rcx, [rbx]
0x18000e5cc  mov     rax, cs:?g_test_interface_exception_guard@details@tip2@@3P6A_NAEAUtest_data_interface@12@PEAVoutput_archive@tson@@W4serialize_options@12@PEAVinput_archive@5@PEBUTipReportingInfo@@@_EEA
0x18000e5d3  mov     r8d, edi
0x18000e5d6  lea     rdx, [rsp+140h+var_D0]
0x18000e5db  test    rax, rax
0x18000e5de  jz      short loc_18000E612
0x18000e5e0  mov     [rsp+140h+var_120], 0
0x18000e5e9  xor     r9d, r9d
0x18000e5ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e5f1  test    al, al
0x18000e5f3  jnz     short loc_18000E61F
0x18000e5f5  mov     byte ptr [rbx+0A0h], 3
0x18000e5fc  mov     word ptr [rbx+0A2h], 400Ch
0x18000e605  mov     qword ptr [rbx+0A8h], 0
0x18000e610  jmp     short loc_18000E61F
0x18000e612  mov     rax, [rcx]
0x18000e615  mov     rax, [rax+8]
0x18000e619  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e61e  nop
0x18000e61f  lea     rcx, [rsp+140h+var_D0]; this
0x18000e624  call    ?finish@output_archive@tson@@QEAAJXZ; tson::output_archive::finish(void)
0x18000e629  test    eax, eax
0x18000e62b  js      short loc_18000E636
0x18000e62d  mov     rax, [r14+810h]
0x18000e634  jmp     short loc_18000E63D
0x18000e636  bts     dword ptr [rbx+40h], 14h
0x18000e63b  xor     eax, eax
0x18000e63d  mov     rcx, [rbp+40h+var_30]
0x18000e641  xor     rcx, rsp; StackCookie
0x18000e644  call    __security_check_cookie
0x18000e649  add     rsp, 120h
0x18000e650  pop     r14
0x18000e652  pop     rdi
0x18000e653  pop     rsi
0x18000e654  pop     rbx
0x18000e655  pop     rbp
0x18000e656  retn
```
