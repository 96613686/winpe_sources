# tip2::details::shared_data<0,0,0>::serialize_data(tson::write_buffer &,tip2::details::serialize_options)

- ea: `0x1800245dc`
- end: `0x180024899`
- name: `?serialize_data@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAPEBDAEAVwrite_buffer@tson@@W4serialize_options@23@@Z`
- size: `701`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `10`
- tags: `registry_config, service_task`

## callers

- `0x180021ecc`
- `0x18002275c`
- `0x1800248a0`

## callees

- `0x180002590`
- `0x18000c5c4`
- `0x18000d660`
- `0x1800125d0`
- `0x180013784`
- `0x18002377c`
- `0x1800245dc`
- `0x180024f48`
- `0x18002515c`
- `0x180033010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall tip2::details::shared_data<0,0,0>::serialize_data(
        __int64 *a1,
        struct tson::write_buffer *a2,
        unsigned int a3)
{
  _BYTE *v6; // rdi
  void *v7; // rax
  void *v8; // r15
  unsigned __int64 v9; // rsi
  tson::write_buffer *v10; // rdi
  __int64 v11; // rcx
  wil::details::in1diag3 *v12; // rcx
  tson::write_buffer *v13; // rax
  _DWORD *v14; // r9
  unsigned __int64 v15; // r8
  const char *v17; // [rsp+30h] [rbp-D0h] BYREF
  char v18; // [rsp+38h] [rbp-C8h]
  _BYTE *v19; // [rsp+40h] [rbp-C0h]
  const char *v20; // [rsp+48h] [rbp-B8h] BYREF
  char v21; // [rsp+50h] [rbp-B0h]
  __int64 *v22; // [rsp+58h] [rbp-A8h]
  const char *v23; // [rsp+60h] [rbp-A0h] BYREF
  char v24; // [rsp+68h] [rbp-98h]
  __int64 *v25; // [rsp+70h] [rbp-90h]
  const char *v26; // [rsp+80h] [rbp-80h] BYREF
  char v27; // [rsp+88h] [rbp-78h]
  char v28; // [rsp+98h] [rbp-68h]
  int v29; // [rsp+108h] [rbp+8h]
  tson::write_buffer *v30; // [rsp+110h] [rbp+10h]

  if ( !a3 )
    return 0;
  v6 = (char *)a1 + 33;
  tson::output_archive::output_archive((tson::output_archive *)&v26, a2, *((_BYTE *)a1 + 33));
  if ( (a3 & 4) != 0 && *v6 )
  {
    v17 = "version";
    v18 = 7;
    v19 = v6;
    tson::output_archive::operator()<tson::nvp<unsigned char &>>(&v26, &v17);
  }
  if ( (a3 & 1) != 0 )
  {
    if ( (*((_DWORD *)a1 + 5) & 0x40000) == 0 )
    {
LABEL_19:
      v17 = "flags";
      v18 = 5;
      v19 = a1 + 15;
      v23 = "errors";
      v24 = 6;
      v25 = a1 + 9;
      v20 = "log";
      v21 = 3;
      v22 = a1 + 12;
      tson::output_archive::process<tson::nvp<tip2::vector_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>> &>,tson::nvp<tip2::vector_nothrow<wil::StoredFailureInfo> &>,tson::nvp<tip2::vector_nothrow<tip2::test_flag> &>>(
        (tson *)&v26,
        (__int64)&v20,
        (__int64 *)&v23,
        (__int64 *)&v17);
      goto LABEL_20;
    }
    v7 = (void *)a1[1];
    if ( v7 )
    {
      v8 = (void *)a1[1];
    }
    else
    {
      v7 = (void *)a1[3];
      v8 = v7;
      if ( !v7 )
      {
        v9 = 0;
        goto LABEL_14;
      }
    }
    v9 = -1;
    do
      ++v9;
    while ( *((_BYTE *)v7 + v9) );
LABEL_14:
    *(_DWORD *)((char *)&v22 + 1) = 0;
    *(_WORD *)((char *)&v22 + 5) = 0;
    HIBYTE(v22) = 0;
    v26 = "name";
    v27 = 4;
    if ( tson::output_archive::write_name((tson::output_archive *)&v26, v8 == 0) )
    {
      v10 = v30;
      if ( *((_QWORD *)v30 + 259) < *((_QWORD *)v30 + 260) || tson::write_buffer::reserve(v30, 1u) )
        *(_BYTE *)(*((_QWORD *)v10 + 259))++ = 23;
      tson::output_archive::write_string_bytes((tson::output_archive *)&v26, v9, v8, v9);
    }
    goto LABEL_19;
  }
LABEL_20:
  v11 = *a1;
  if ( tip2::details::g_test_interface_exception_guard )
  {
    if ( !(unsigned __int8)tip2::details::g_test_interface_exception_guard(v11, &v26, a3, 0, 0) )
    {
      *((_BYTE *)a1 + 160) = 3;
      *((_WORD *)a1 + 81) = 16396;
      a1[21] = 0;
    }
  }
  else
  {
    (*(void (__fastcall **)(__int64, const char **, _QWORD))(*(_QWORD *)v11 + 8LL))(v11, &v26, a3);
  }
  if ( v29 < 0 || v28 )
    goto LABEL_30;
  v13 = v30;
  if ( *((_BYTE *)v30 + 8) )
  {
    *((_QWORD *)v30 + 258) = 0;
    *((_QWORD *)v13 + 259) = 0;
    *((_QWORD *)v13 + 260) = 0;
LABEL_30:
    *((_DWORD *)a1 + 16) |= 0x100000u;
    return 0;
  }
  v14 = (_DWORD *)*((_QWORD *)v30 + 258);
  v15 = (unsigned int)*((_QWORD *)v30 + 259) - (unsigned int)v14;
  if ( v15 > 0xFFFFFF )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v12);
  *v14 = v15 & 0x3F | (4 * (_WORD)v15) & 0x3F00 | ((_DWORD)v15 << 6) & 0x3F000000 | (16 * v15) & 0x3F0000 | 0x80408040;
  return *((_QWORD *)a2 + 258);
}

```

## disassembly

```asm
0x1800245dc  push    rbp
0x1800245de  push    rbx
0x1800245df  push    rsi
0x1800245e0  push    rdi
0x1800245e1  push    r13
0x1800245e3  push    r14
0x1800245e5  push    r15
0x1800245e7  lea     rbp, [rsp-30h]
0x1800245ec  sub     rsp, 130h
0x1800245f3  mov     rax, cs:__security_cookie
0x1800245fa  xor     rax, rsp
0x1800245fd  mov     [rbp+60h+var_40], rax
0x180024601  mov     r14d, r8d
0x180024604  mov     r13, rdx
0x180024607  mov     rbx, rcx
0x18002460a  test    r8d, r8d
0x18002460d  jz      loc_180024873
0x180024613  lea     rdi, [rcx+21h]
0x180024617  mov     r8b, [rdi]; unsigned __int8
0x18002461a  lea     rcx, [rbp+60h+var_E0]; this
0x18002461e  call    ??0output_archive@tson@@QEAA@AEAVwrite_buffer@1@E@Z; tson::output_archive::output_archive(tson::write_buffer &,uchar)
0x180024623  test    r14b, 4
0x180024627  jz      short loc_180024652
0x180024629  cmp     byte ptr [rdi], 0
0x18002462c  jbe     short loc_180024652
0x18002462e  lea     rax, aVersion; "version"
0x180024635  mov     [rsp+160h+var_130], rax
0x18002463a  mov     [rsp+160h+var_128], 7
0x18002463f  mov     [rsp+160h+var_120], rdi
0x180024644  lea     rdx, [rsp+160h+var_130]
0x180024649  lea     rcx, [rbp+60h+var_E0]
0x18002464d  call    ??$?RV?$nvp@AEAE@tson@@@output_archive@tson@@QEAAAEAV01@$$QEAV?$nvp@AEAE@1@@Z; tson::output_archive::operator()<tson::nvp<uchar &>>(tson::nvp<uchar &> &&)
0x180024652  test    r14b, 1
0x180024656  jz      loc_180024774
0x18002465c  test    dword ptr [rbx+14h], 40000h
0x180024663  jz      loc_18002470D
0x180024669  mov     rax, [rbx+8]
0x18002466d  test    rax, rax
0x180024670  jz      short loc_180024677
0x180024672  mov     r15, rax
0x180024675  jmp     short loc_180024683
0x180024677  mov     rax, [rbx+18h]
0x18002467b  mov     r15, rax
0x18002467e  test    rax, rax
0x180024681  jz      short loc_180024692
0x180024683  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180024687  inc     rsi
0x18002468a  cmp     byte ptr [rax+rsi], 0
0x18002468e  jnz     short loc_180024687
0x180024690  jmp     short loc_180024694
0x180024692  xor     esi, esi
0x180024694  xor     eax, eax
0x180024696  mov     [rsp+160h+var_107], eax
0x18002469a  mov     [rsp+160h+var_103], ax
0x18002469f  mov     [rsp+160h+var_101], al
0x1800246a3  lea     rax, aName; "name"
0x1800246aa  mov     [rbp+60h+var_E0], rax
0x1800246ae  mov     [rbp+60h+var_D8], 4
0x1800246b2  test    r15, r15
0x1800246b5  setz    dl; bool
0x1800246b8  lea     rcx, [rbp+60h+var_E0]; this
0x1800246bc  call    ?write_name@output_archive@tson@@AEAA_N_N@Z; tson::output_archive::write_name(bool)
0x1800246c1  test    al, al
0x1800246c3  jz      short loc_18002470D
0x1800246c5  mov     rdi, [rbp+60h+var_50]
0x1800246c9  mov     rax, [rdi+820h]
0x1800246d0  cmp     [rdi+818h], rax
0x1800246d7  jb      short loc_1800246EA
0x1800246d9  mov     edx, 1; unsigned __int64
0x1800246de  mov     rcx, rdi; this
0x1800246e1  call    ?reserve@write_buffer@tson@@AEAA_N_K@Z; tson::write_buffer::reserve(unsigned __int64)
0x1800246e6  test    al, al
0x1800246e8  jz      short loc_1800246FB
0x1800246ea  mov     rax, [rdi+818h]
0x1800246f1  mov     byte ptr [rax], 17h
0x1800246f4  inc     qword ptr [rdi+818h]
0x1800246fb  mov     r9, rsi; unsigned __int64
0x1800246fe  mov     r8, r15; void *
0x180024701  mov     rdx, rsi; unsigned __int64
0x180024704  lea     rcx, [rbp+60h+var_E0]; this
0x180024708  call    ?write_string_bytes@output_archive@tson@@AEAAX_KPEAX0@Z; tson::output_archive::write_string_bytes(unsigned __int64,void *,unsigned __int64)
0x18002470d  lea     rax, aFlags; "flags"
0x180024714  mov     [rsp+160h+var_130], rax
0x180024719  mov     [rsp+160h+var_128], 5
0x18002471e  lea     rax, [rbx+78h]
0x180024722  mov     [rsp+160h+var_120], rax
0x180024727  lea     rax, aErrors; "errors"
0x18002472e  mov     [rsp+160h+var_100], rax
0x180024733  mov     [rsp+160h+var_F8], 6
0x180024738  lea     rax, [rbx+48h]
0x18002473c  mov     [rsp+160h+var_F0], rax
0x180024741  lea     rax, aLog; "log"
0x180024748  mov     [rsp+160h+var_118], rax
0x18002474d  mov     [rsp+160h+var_110], 3
0x180024752  lea     rax, [rbx+60h]
0x180024756  mov     [rsp+58h], rax
0x18002475b  lea     r9, [rsp+160h+var_130]
0x180024760  lea     r8, [rsp+160h+var_100]
0x180024765  lea     rdx, [rsp+160h+var_118]
0x18002476a  lea     rcx, [rbp+60h+var_E0]; this
0x18002476e  call    ??$process@V?$nvp@AEAV?$vector_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@@tip2@@@tson@@V?$nvp@AEAV?$vector_nothrow@VStoredFailureInfo@wil@@@tip2@@@2@V?$nvp@AEAV?$vector_nothrow@Utest_flag@tip2@@@tip2@@@2@@output_archive@tson@@AEAAX$$QEAV?$nvp@AEAV?$vector_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@@tip2@@@1@$$QEAV?$nvp@AEAV?$vector_nothrow@VStoredFailureInfo@wil@@@tip2@@@1@$$QEAV?$nvp@AEAV?$vector_nothrow@Utest_flag@tip2@@@tip2@@@1@@Z; tson::output_archive::process<tson::nvp<tip2::vector_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>> &>,tson::nvp<tip2::vector_nothrow<wil::StoredFailureInfo> &>,tson::nvp<tip2::vector_nothrow<tip2::test_flag> &>>(tson::nvp<tip2::vector_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>> &> &&,tson::nvp<tip2::vector_nothrow<wil::StoredFailureInfo> &> &&,tson::nvp<tip2::vector_nothrow<tip2::test_flag> &> &&)
0x180024773  nop
0x180024774  mov     rcx, [rbx]
0x180024777  mov     rax, cs:?g_test_interface_exception_guard@details@tip2@@3P6A_NAEAUtest_data_interface@12@PEAVoutput_archive@tson@@W4serialize_options@12@PEAVinput_archive@5@PEBUTipReportingInfo@@@_EEA
0x18002477e  mov     r8d, r14d
0x180024781  lea     rdx, [rbp+60h+var_E0]
0x180024785  test    rax, rax
0x180024788  jz      short loc_1800247BC
0x18002478a  mov     [rsp+160h+var_140], 0
0x180024793  xor     r9d, r9d
0x180024796  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002479b  test    al, al
0x18002479d  jnz     short loc_1800247C9
0x18002479f  mov     byte ptr [rbx+0A0h], 3
0x1800247a6  mov     word ptr [rbx+0A2h], 400Ch
0x1800247af  mov     qword ptr [rbx+0A8h], 0
0x1800247ba  jmp     short loc_1800247C9
0x1800247bc  mov     rax, [rcx]
0x1800247bf  mov     rax, [rax+8]
0x1800247c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800247c8  nop
0x1800247c9  cmp     [rbp+60h+var_58], 0
0x1800247cd  jl      loc_18002486E
0x1800247d3  cmp     [rbp+60h+var_C8], 0
0x1800247d7  jnz     loc_18002486E
0x1800247dd  mov     rax, [rbp+60h+var_50]
0x1800247e1  cmp     byte ptr [rax+8], 0
0x1800247e5  jnz     short loc_18002484D
0x1800247e7  mov     r9, [rax+810h]
0x1800247ee  mov     r8, [rax+818h]
0x1800247f5  sub     r8, r9
0x1800247f8  mov     r8d, r8d
0x1800247fb  cmp     r8, 0FFFFFFh
0x180024802  ja      loc_180024893
0x180024808  mov     edx, r8d
0x18002480b  shl     rdx, 4
0x18002480f  and     edx, 3F0000h
0x180024815  mov     ecx, r8d
0x180024818  shl     rcx, 6
0x18002481c  and     ecx, 3F000000h
0x180024822  or      edx, ecx
0x180024824  lea     rcx, ds:0[r8*4]
0x18002482c  and     ecx, 3F00h
0x180024832  or      edx, ecx
0x180024834  and     r8d, 3Fh
0x180024838  or      edx, r8d
0x18002483b  or      edx, 80408040h
0x180024841  mov     [r9], edx
0x180024844  mov     rax, [r13+810h]
0x18002484b  jmp     short loc_180024875
0x18002484d  mov     qword ptr [rax+810h], 0
0x180024858  mov     qword ptr [rax+818h], 0
0x180024863  mov     qword ptr [rax+820h], 0
0x18002486e  bts     dword ptr [rbx+40h], 14h
0x180024873  xor     eax, eax
0x180024875  mov     rcx, [rbp+60h+var_40]
0x180024879  xor     rcx, rsp; StackCookie
0x18002487c  call    __security_check_cookie
0x180024881  add     rsp, 130h
0x180024888  pop     r15
0x18002488a  pop     r14
0x18002488c  pop     r13
0x18002488e  pop     rdi
0x18002488f  pop     rsi
0x180024890  pop     rbx
0x180024891  pop     rbp
0x180024892  retn
0x180024893  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
