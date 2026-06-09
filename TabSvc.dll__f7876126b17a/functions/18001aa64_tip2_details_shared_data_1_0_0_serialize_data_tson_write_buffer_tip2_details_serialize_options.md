# tip2::details::shared_data<1,0,0>::serialize_data(tson::write_buffer &,tip2::details::serialize_options)

- ea: `0x18001aa64`
- end: `0x18001ac3f`
- name: `?serialize_data@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAPEBDAEAVwrite_buffer@tson@@W4serialize_options@23@@Z`
- size: `475`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `12`
- tags: `registry_config, service_task`

## callers

- `0x180019314`
- `0x180028f78`
- `0x1800292b8`

## callees

- `0x18001aa64`
- `0x18001ac48`
- `0x18001ad38`
- `0x18001ae48`
- `0x18001ae88`
- `0x18001af1c`
- `0x18001af4c`
- `0x18001bbe0`
- `0x18001d374`
- `0x18001eee0`
- `0x1800296ac`
- `0x180031010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall tip2::details::shared_data<1,0,0>::serialize_data(
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
      tson::output_archive::process<tson::nvp<tip2::vector_nothrow<wil::StoredFailureInfo> &>,tson::nvp<tip2::vector_nothrow<tip2::test_flag> &>>((tson *)&v19);
    }
    v10 = *a1;
    if ( tip2::details::g_test_interface_exception_guard )
    {
      if ( !(unsigned __int8)tip2::details::g_test_interface_exception_guard(v10, &v19, a3, 0, 0) )
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
0x18001aa64  push    rbp
0x18001aa66  push    rbx
0x18001aa67  push    rsi
0x18001aa68  push    rdi
0x18001aa69  push    r14
0x18001aa6b  lea     rbp, [rsp-20h]
0x18001aa70  sub     rsp, 120h
0x18001aa77  mov     rax, cs:__security_cookie
0x18001aa7e  xor     rax, rsp
0x18001aa81  mov     [rbp+40h+var_30], rax
0x18001aa85  mov     edi, r8d
0x18001aa88  mov     r14, rdx
0x18001aa8b  mov     rbx, rcx
0x18001aa8e  test    r8d, r8d
0x18001aa91  jz      loc_18001AC23
0x18001aa97  lea     rsi, [rcx+21h]
0x18001aa9b  mov     r8b, [rsi]; unsigned __int8
0x18001aa9e  lea     rcx, [rsp+140h+var_D0]; this
0x18001aaa3  call    ??0output_archive@tson@@QEAA@AEAVwrite_buffer@1@E@Z; tson::output_archive::output_archive(tson::write_buffer &,uchar)
0x18001aaa8  test    dil, 4
0x18001aaac  jz      short loc_18001AAD8
0x18001aaae  cmp     byte ptr [rsi], 0
0x18001aab1  jbe     short loc_18001AAD8
0x18001aab3  lea     rax, aVersion; "version"
0x18001aaba  mov     [rsp+140h+var_110], rax
0x18001aabf  mov     [rsp+140h+var_108], 7
0x18001aac4  mov     qword ptr [rsp+140h+var_100], rsi
0x18001aac9  lea     rdx, [rsp+140h+var_110]
0x18001aace  lea     rcx, [rsp+140h+var_D0]
0x18001aad3  call    ??$?RV?$nvp@AEAE@tson@@@output_archive@tson@@QEAAAEAV01@$$QEAV?$nvp@AEAE@1@@Z; tson::output_archive::operator()<tson::nvp<uchar &>>(tson::nvp<uchar &> &&)
0x18001aad8  test    dil, 1
0x18001aadc  jz      loc_18001ABB1
0x18001aae2  test    dword ptr [rbx+14h], 40000h
0x18001aae9  jz      short loc_18001AB35
0x18001aaeb  mov     rdx, [rbx+8]
0x18001aaef  test    rdx, rdx
0x18001aaf2  jnz     short loc_18001AAF8
0x18001aaf4  mov     rdx, [rbx+18h]
0x18001aaf8  lea     rcx, [rsp+140h+var_E8]
0x18001aafd  call    ?make_string_tag@tson@@YA?AUansistring_tag@1@PEBD@Z; tson::make_string_tag(char const *)
0x18001ab02  lea     rcx, aName; "name"
0x18001ab09  mov     [rsp+140h+var_110], rcx
0x18001ab0e  mov     [rsp+140h+var_108], 4
0x18001ab13  movups  xmm0, xmmword ptr [rax]
0x18001ab16  movups  [rsp+140h+var_100], xmm0
0x18001ab1b  movsd   xmm1, qword ptr [rax+10h]
0x18001ab20  movsd   [rsp+140h+var_F0], xmm1
0x18001ab26  lea     rdx, [rsp+140h+var_110]
0x18001ab2b  lea     rcx, [rsp+140h+var_D0]
0x18001ab30  call    ??$?RV?$nvp@Uansistring_tag@tson@@@tson@@@output_archive@tson@@QEAAAEAV01@$$QEAV?$nvp@Uansistring_tag@tson@@@1@@Z; tson::output_archive::operator()<tson::nvp<tson::ansistring_tag>>(tson::nvp<tson::ansistring_tag> &&)
0x18001ab35  lea     rax, aFlags; "flags"
0x18001ab3c  mov     [rsp+140h+var_110], rax
0x18001ab41  mov     [rsp+140h+var_108], 5
0x18001ab46  lea     rax, [rbx+78h]
0x18001ab4a  mov     qword ptr [rsp+140h+var_100], rax
0x18001ab4f  lea     rax, aErrors; "errors"
0x18001ab56  mov     [rsp+140h+var_E8], rax
0x18001ab5b  mov     [rsp+140h+var_E0], 6
0x18001ab60  lea     rax, [rbx+48h]
0x18001ab64  mov     [rsp+140h+var_D8], rax
0x18001ab69  lea     rax, aLog; "log"
0x18001ab70  mov     [rsp+140h+var_D0], rax
0x18001ab75  mov     [rsp+140h+var_C8], 3
0x18001ab7a  lea     rcx, [rsp+140h+var_D0]; this
0x18001ab7f  call    ?startNode@output_archive@tson@@QEAAXXZ; tson::output_archive::startNode(void)
0x18001ab84  lea     rdx, [rbx+60h]
0x18001ab88  lea     rcx, [rsp+140h+var_D0]; this
0x18001ab8d  call    ??$save_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@@tson@@YAXAEAVoutput_archive@0@AEAV?$vector_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@@tip2@@@Z; tson::save_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>>(tson::output_archive &,tip2::vector_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>> &)
0x18001ab92  lea     rcx, [rsp+140h+var_D0]; this
0x18001ab97  call    ?finishNode@output_archive@tson@@QEAAXXZ; tson::output_archive::finishNode(void)
0x18001ab9c  lea     r8, [rsp+140h+var_110]
0x18001aba1  lea     rdx, [rsp+140h+var_E8]
0x18001aba6  lea     rcx, [rsp+140h+var_D0]; this
0x18001abab  call    ??$process@V?$nvp@AEAV?$vector_nothrow@VStoredFailureInfo@wil@@@tip2@@@tson@@V?$nvp@AEAV?$vector_nothrow@Utest_flag@tip2@@@tip2@@@2@@output_archive@tson@@AEAAX$$QEAV?$nvp@AEAV?$vector_nothrow@VStoredFailureInfo@wil@@@tip2@@@1@$$QEAV?$nvp@AEAV?$vector_nothrow@Utest_flag@tip2@@@tip2@@@1@@Z; tson::output_archive::process<tson::nvp<tip2::vector_nothrow<wil::StoredFailureInfo> &>,tson::nvp<tip2::vector_nothrow<tip2::test_flag> &>>(tson::nvp<tip2::vector_nothrow<wil::StoredFailureInfo> &> &&,tson::nvp<tip2::vector_nothrow<tip2::test_flag> &> &&)
0x18001abb0  nop
0x18001abb1  mov     rcx, [rbx]
0x18001abb4  mov     rax, cs:?g_test_interface_exception_guard@details@tip2@@3P6A_NAEAUtest_data_interface@12@PEAVoutput_archive@tson@@W4serialize_options@12@PEAVinput_archive@5@PEBUTipReportingInfo@@@_EEA
0x18001abbb  mov     r8d, edi
0x18001abbe  lea     rdx, [rsp+140h+var_D0]
0x18001abc3  test    rax, rax
0x18001abc6  jz      short loc_18001ABFA
0x18001abc8  mov     [rsp+140h+var_120], 0
0x18001abd1  xor     r9d, r9d
0x18001abd4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001abd9  test    al, al
0x18001abdb  jnz     short loc_18001AC07
0x18001abdd  mov     byte ptr [rbx+0A0h], 3
0x18001abe4  mov     word ptr [rbx+0A2h], 400Ch
0x18001abed  mov     qword ptr [rbx+0A8h], 0
0x18001abf8  jmp     short loc_18001AC07
0x18001abfa  mov     rax, [rcx]
0x18001abfd  mov     rax, [rax+8]
0x18001ac01  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ac06  nop
0x18001ac07  lea     rcx, [rsp+140h+var_D0]; this
0x18001ac0c  call    ?finish@output_archive@tson@@QEAAJXZ; tson::output_archive::finish(void)
0x18001ac11  test    eax, eax
0x18001ac13  js      short loc_18001AC1E
0x18001ac15  mov     rax, [r14+810h]
0x18001ac1c  jmp     short loc_18001AC25
0x18001ac1e  bts     dword ptr [rbx+40h], 14h
0x18001ac23  xor     eax, eax
0x18001ac25  mov     rcx, [rbp+40h+var_30]
0x18001ac29  xor     rcx, rsp; StackCookie
0x18001ac2c  call    __security_check_cookie
0x18001ac31  add     rsp, 120h
0x18001ac38  pop     r14
0x18001ac3a  pop     rdi
0x18001ac3b  pop     rsi
0x18001ac3c  pop     rbx
0x18001ac3d  pop     rbp
0x18001ac3e  retn
```
