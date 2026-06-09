# tip2::details::shared_data<1,0,0>::deserialize_data(TestInfo_ODR_guard::TestInfo const &)

- ea: `0x18001af84`
- end: `0x18001b29e`
- name: `?deserialize_data@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAXAEBUTestInfo@TestInfo_ODR_guard@@@Z`
- size: `794`
- prototype: `void __fastcall(__int64 *, __int64)`
- caller_count: `3`
- callee_count: `10`
- tags: `registry_config, service_task`

## callers

- `0x180028cbc`
- `0x180028d90`
- `0x180028f78`

## callees

- `0x18001af84`
- `0x18001b2a4`
- `0x18001bbe0`
- `0x18001c684`
- `0x18001dea4`
- `0x18001e514`
- `0x180028e48`
- `0x18002a94c`
- `0x18002ac94`
- `0x180031010`

## pseudocode

```c
void __fastcall tip2::details::shared_data<1,0,0>::deserialize_data(__int64 *a1, __int64 a2)
{
  int *v4; // r8
  unsigned int v5; // ecx
  __int64 *v6; // r14
  unsigned __int16 v7; // ax
  unsigned __int64 v8; // r8
  int *v9; // rcx
  __int64 v10; // rcx
  unsigned __int8 v11[8]; // [rsp+30h] [rbp-D0h] BYREF
  const char *v12; // [rsp+38h] [rbp-C8h] BYREF
  char v13; // [rsp+40h] [rbp-C0h]
  __int64 *v14; // [rsp+48h] [rbp-B8h]
  int *v15; // [rsp+50h] [rbp-B0h] BYREF
  int *v16; // [rsp+58h] [rbp-A8h]
  int *v17; // [rsp+60h] [rbp-A0h]
  char v18; // [rsp+68h] [rbp-98h]
  const char *v19; // [rsp+70h] [rbp-90h] BYREF
  char v20; // [rsp+78h] [rbp-88h]
  __int64 *v21; // [rsp+80h] [rbp-80h]
  const char *v22; // [rsp+88h] [rbp-78h] BYREF
  char v23; // [rsp+90h] [rbp-70h]
  __int64 *v24; // [rsp+98h] [rbp-68h]
  int **v25; // [rsp+A0h] [rbp-60h] BYREF
  int v26; // [rsp+A8h] [rbp-58h]
  const char *v27; // [rsp+B0h] [rbp-50h]
  __int16 v28; // [rsp+B8h] [rbp-48h]
  char v29; // [rsp+C0h] [rbp-40h]
  _DWORD v30[25]; // [rsp+C4h] [rbp-3Ch] BYREF
  unsigned __int64 v31; // [rsp+128h] [rbp+28h]

  if ( (*(_DWORD *)(a2 + 20) & 0x1000) == 0 )
    goto LABEL_35;
  v4 = *(int **)(a2 + 24);
  v15 = v4;
  v16 = v4;
  v17 = v4;
  v18 = 0;
  if ( v4
    && *(_BYTE *)v4
    && *((_BYTE *)v4 + 1)
    && *((_BYTE *)v4 + 2)
    && *((_BYTE *)v4 + 3)
    && !*((_BYTE *)v4 + 4)
    && (*v4 & 0xC0C0C0C0) == 0x80408040 )
  {
    v5 = *v4;
    v16 = (int *)((char *)v4 + 5);
    v17 = (int *)((char *)v4
                + (v5 & 0x3F | ((v5 & 0x3F00 | ((v5 & 0x3F0000 | (unsigned __int64)((v5 >> 2) & 0xFC00000)) >> 2)) >> 2)));
  }
  else
  {
    v18 = 1;
  }
  v6 = a1 + 1;
  v25 = &v15;
  v26 = 0;
  v27 = 0;
  v28 = 0;
  v29 = 0;
  memset_0(v30, 0, sizeof(v30));
  v31 = 0;
  tson::input_archive::consume_expected_marker((tson::read_buffer **)&v25);
  tson::input_archive::consume_expected_marker((tson::read_buffer **)&v25);
  if ( v31 >= 0x19 )
    v29 = 1;
  else
    v30[v31++] = 0;
  if ( (*((_DWORD *)a1 + 5) & 0x40000) != 0 )
  {
    if ( a1[3] )
    {
      v27 = "name";
      LOBYTE(v28) = 4;
      if ( tson::input_archive::search((tson::input_archive *)&v25) )
      {
        tson::input_archive::consume_expected_marker((tson::read_buffer **)&v25);
        v11[0] = 0;
        tson::read_buffer::consume<unsigned char>((__int64)v25, v11);
        if ( v11[0] > 1u )
        {
          v7 = tson::input_archive::upgrade_string_size((tson::input_archive *)&v25, v11[0]);
          v8 = (unsigned __int64)v25[1] + (unsigned __int16)(v7 - 1);
          if ( v8 > (unsigned __int64)v25[2] )
            *((_BYTE *)v25 + 24) = 1;
          else
            v25[1] = (int *)v8;
        }
      }
    }
    else
    {
      v12 = "name";
      v13 = 4;
      v14 = a1 + 1;
      tson::input_archive::operator()<tson::nvp<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>> &>>(
        (__int64)&v25,
        (__int64)&v12);
      if ( *v6 )
        a1[3] = *v6;
    }
  }
  v12 = "flags";
  v13 = 5;
  v14 = a1 + 15;
  v19 = "errors";
  v20 = 6;
  v21 = a1 + 9;
  v22 = "log";
  v23 = 3;
  v24 = a1 + 12;
  tson::input_archive::process<tson::nvp<tip2::vector_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>> &>,tson::nvp<tip2::vector_nothrow<wil::StoredFailureInfo> &>,tson::nvp<tip2::vector_nothrow<tip2::test_flag> &>>(
    (tson *)&v25,
    (__int64)&v22,
    (__int64 *)&v19,
    (__int64 *)&v12);
  v9 = v25[1];
  if ( v9 >= v25[2] )
    goto LABEL_26;
  if ( *(_BYTE *)v9 == 8 )
  {
    tson::input_archive::consume_expected_marker((tson::read_buffer **)&v25);
  }
  else
  {
LABEL_26:
    v10 = *a1;
    if ( tip2::details::g_test_interface_exception_guard )
    {
      if ( !(unsigned __int8)tip2::details::g_test_interface_exception_guard(v10, 0, 0, &v25, 0)
        && !*((_BYTE *)a1 + 160) )
      {
        *((_BYTE *)a1 + 160) = 3;
        *((_WORD *)a1 + 81) = 16397;
        a1[21] = 0;
      }
    }
    else
    {
      (*(void (__fastcall **)(__int64, int ***))(*(_QWORD *)v10 + 16LL))(v10, &v25);
    }
  }
  if ( v26 < 0 || *((_BYTE *)v25 + 24) || v29 )
LABEL_35:
    *((_DWORD *)a1 + 16) |= 0x80000u;
  else
    *((_DWORD *)a1 + 46) = *(_DWORD *)(a2 + 16);
}

```

## disassembly

```asm
0x18001af84  mov     [rsp-8+arg_8], rbx
0x18001af89  mov     [rsp-8+arg_10], rsi
0x18001af8e  push    rbp
0x18001af8f  push    rdi
0x18001af90  push    r12
0x18001af92  push    r14
0x18001af94  push    r15
0x18001af96  lea     rbp, [rsp-40h]
0x18001af9b  sub     rsp, 140h
0x18001afa2  mov     rax, cs:__security_cookie
0x18001afa9  xor     rax, rsp
0x18001afac  mov     [rbp+60h+var_30], rax
0x18001afb0  mov     rsi, rdx
0x18001afb3  mov     rdi, rcx
0x18001afb6  test    dword ptr [rdx+14h], 1000h
0x18001afbd  jz      loc_18001B271
0x18001afc3  mov     r8, [rdx+18h]
0x18001afc7  mov     [rsp+160h+var_110], r8
0x18001afcc  mov     [rsp+160h+var_108], r8
0x18001afd1  mov     [rsp+160h+var_100], r8
0x18001afd6  xor     r15d, r15d
0x18001afd9  mov     [rsp+160h+var_F8], r15b
0x18001afde  lea     r12d, [r15+1]
0x18001afe2  test    r8, r8
0x18001afe5  jz      short loc_18001B057
0x18001afe7  cmp     [r8], r15b
0x18001afea  jz      short loc_18001B057
0x18001afec  cmp     [r8+1], r15b
0x18001aff0  jz      short loc_18001B057
0x18001aff2  cmp     [r8+2], r15b
0x18001aff6  jz      short loc_18001B057
0x18001aff8  cmp     [r8+3], r15b
0x18001affc  jz      short loc_18001B057
0x18001affe  cmp     [r8+4], r15b
0x18001b002  jnz     short loc_18001B057
0x18001b004  mov     eax, [r8]
0x18001b007  and     eax, 0C0C0C0C0h
0x18001b00c  cmp     eax, 80408040h
0x18001b011  jnz     short loc_18001B057
0x18001b013  mov     ecx, [r8]
0x18001b016  lea     rax, [r8+5]
0x18001b01a  mov     [rsp+160h+var_108], rax
0x18001b01f  mov     edx, ecx
0x18001b021  shr     rdx, 2
0x18001b025  and     edx, 0FC00000h
0x18001b02b  mov     eax, ecx
0x18001b02d  and     eax, 3F0000h
0x18001b032  or      rdx, rax
0x18001b035  shr     rdx, 2
0x18001b039  mov     eax, ecx
0x18001b03b  and     eax, 3F00h
0x18001b040  or      rdx, rax
0x18001b043  shr     rdx, 2
0x18001b047  and     ecx, 3Fh
0x18001b04a  or      rdx, rcx
0x18001b04d  add     rdx, r8
0x18001b050  mov     [rsp+160h+var_100], rdx
0x18001b055  jmp     short loc_18001B05C
0x18001b057  mov     [rsp+160h+var_F8], r12b
0x18001b05c  lea     r14, [rdi+8]
0x18001b060  mov     bl, [r14+19h]
0x18001b064  lea     rax, [rsp+160h+var_110]
0x18001b069  mov     [rbp+60h+var_C0], rax
0x18001b06d  mov     [rbp+60h+var_B8], r15d
0x18001b071  mov     [rbp+60h+var_B0], r15
0x18001b075  mov     [rbp+60h+var_A8], r15w
0x18001b07a  mov     [rbp+60h+var_A0], r15b
0x18001b07e  xor     edx, edx; Val
0x18001b080  lea     r8d, [rdx+64h]; Size
0x18001b084  lea     rcx, [rbp+60h+var_9C]; void *
0x18001b088  call    memset_0
0x18001b08d  mov     [rbp+60h+var_38], r15
0x18001b091  mov     r8d, 80070309h
0x18001b097  mov     dl, 80h
0x18001b099  lea     rcx, [rbp+60h+var_C0]
0x18001b09d  call    ?consume_expected_marker@input_archive@tson@@AEAA_NW4archive_marker@details@2@J@Z; tson::input_archive::consume_expected_marker(tson::details::archive_marker,long)
0x18001b0a2  mov     dl, bl
0x18001b0a4  lea     rcx, [rbp+60h+var_C0]
0x18001b0a8  call    ?consume_expected_marker@input_archive@tson@@AEAA_NW4archive_marker@details@2@J@Z; tson::input_archive::consume_expected_marker(tson::details::archive_marker,long)
0x18001b0ad  mov     r8, [rbp+60h+var_38]
0x18001b0b1  cmp     r8, 19h
0x18001b0b5  jnb     short loc_18001B0C2
0x18001b0b7  mov     [rbp+r8*4+60h+var_9C], r15d
0x18001b0bc  add     [rbp+60h+var_38], r12
0x18001b0c0  jmp     short loc_18001B0C6
0x18001b0c2  mov     [rbp+60h+var_A0], r12b
0x18001b0c6  mov     ebx, 8007065Dh
0x18001b0cb  test    dword ptr [rdi+14h], 40000h
0x18001b0d2  jz      loc_18001B174
0x18001b0d8  lea     rax, aName; "name"
0x18001b0df  lea     rcx, [rbp+60h+var_C0]; this
0x18001b0e3  cmp     [rdi+18h], r15
0x18001b0e7  jnz     short loc_18001B110
0x18001b0e9  mov     [rsp+160h+var_128], rax
0x18001b0ee  mov     [rsp+160h+var_120], 4
0x18001b0f3  mov     [rsp+160h+var_118], r14
0x18001b0f8  lea     rdx, [rsp+160h+var_128]
0x18001b0fd  call    ??$?RV?$nvp@AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@@tson@@@input_archive@tson@@QEAAAEAV01@$$QEAV?$nvp@AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@@1@@Z; tson::input_archive::operator()<tson::nvp<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>> &>>(tson::nvp<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>> &> &&)
0x18001b102  mov     rax, [r14]
0x18001b105  test    rax, rax
0x18001b108  jz      short loc_18001B174
0x18001b10a  mov     [rdi+18h], rax
0x18001b10e  jmp     short loc_18001B174
0x18001b110  mov     [rbp+60h+var_B0], rax
0x18001b114  mov     byte ptr [rbp+60h+var_A8], 4
0x18001b118  call    ?search@input_archive@tson@@AEAA_NXZ; tson::input_archive::search(void)
0x18001b11d  test    al, al
0x18001b11f  jz      short loc_18001B174
0x18001b121  mov     r8d, ebx
0x18001b124  mov     dl, 17h
0x18001b126  lea     rcx, [rbp+60h+var_C0]
0x18001b12a  call    ?consume_expected_marker@input_archive@tson@@AEAA_NW4archive_marker@details@2@J@Z; tson::input_archive::consume_expected_marker(tson::details::archive_marker,long)
0x18001b12f  mov     [rsp+160h+var_130], r15b
0x18001b134  lea     rdx, [rsp+160h+var_130]
0x18001b139  mov     rcx, [rbp+60h+var_C0]
0x18001b13d  call    ??$consume@E@read_buffer@tson@@QEAA_NAEAE@Z; tson::read_buffer::consume<uchar>(uchar &)
0x18001b142  mov     dl, [rsp+160h+var_130]; unsigned __int8
0x18001b146  cmp     dl, r12b
0x18001b149  jbe     short loc_18001B174
0x18001b14b  lea     rcx, [rbp+60h+var_C0]; this
0x18001b14f  call    ?upgrade_string_size@input_archive@tson@@AEAAGE@Z; tson::input_archive::upgrade_string_size(uchar)
0x18001b154  sub     ax, r12w
0x18001b158  movzx   r8d, ax
0x18001b15c  mov     rdx, [rbp+60h+var_C0]
0x18001b160  add     r8, [rdx+8]
0x18001b164  cmp     r8, [rdx+10h]
0x18001b168  ja      short loc_18001B170
0x18001b16a  mov     [rdx+8], r8
0x18001b16e  jmp     short loc_18001B174
0x18001b170  mov     [rdx+18h], r12b
0x18001b174  lea     rax, aFlags; "flags"
0x18001b17b  mov     [rsp+160h+var_128], rax
0x18001b180  mov     [rsp+160h+var_120], 5
0x18001b185  lea     rax, [rdi+78h]
0x18001b189  mov     [rsp+160h+var_118], rax
0x18001b18e  lea     rax, aErrors; "errors"
0x18001b195  mov     [rsp+160h+var_F0], rax
0x18001b19a  mov     [rsp+160h+var_E8], 6
0x18001b19f  lea     rax, [rdi+48h]
0x18001b1a3  mov     [rbp+60h+var_E0], rax
0x18001b1a7  lea     rax, aLog; "log"
0x18001b1ae  mov     [rbp+60h+var_D8], rax
0x18001b1b2  mov     [rbp+60h+var_D0], 3
0x18001b1b6  lea     rax, [rdi+60h]
0x18001b1ba  mov     [rbp+60h+var_C8], rax
0x18001b1be  lea     r9, [rsp+160h+var_128]
0x18001b1c3  lea     r8, [rsp+160h+var_F0]
0x18001b1c8  lea     rdx, [rbp+60h+var_D8]
0x18001b1cc  lea     rcx, [rbp+60h+var_C0]; this
0x18001b1d0  call    ??$process@V?$nvp@AEAV?$vector_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@@tip2@@@tson@@V?$nvp@AEAV?$vector_nothrow@VStoredFailureInfo@wil@@@tip2@@@2@V?$nvp@AEAV?$vector_nothrow@Utest_flag@tip2@@@tip2@@@2@@input_archive@tson@@AEAAX$$QEAV?$nvp@AEAV?$vector_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@@tip2@@@1@$$QEAV?$nvp@AEAV?$vector_nothrow@VStoredFailureInfo@wil@@@tip2@@@1@$$QEAV?$nvp@AEAV?$vector_nothrow@Utest_flag@tip2@@@tip2@@@1@@Z; tson::input_archive::process<tson::nvp<tip2::vector_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>> &>,tson::nvp<tip2::vector_nothrow<wil::StoredFailureInfo> &>,tson::nvp<tip2::vector_nothrow<tip2::test_flag> &>>(tson::nvp<tip2::vector_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>> &> &&,tson::nvp<tip2::vector_nothrow<wil::StoredFailureInfo> &> &&,tson::nvp<tip2::vector_nothrow<tip2::test_flag> &> &&)
0x18001b1d5  mov     rax, [rbp+60h+var_C0]
0x18001b1d9  mov     rcx, [rax+8]
0x18001b1dd  cmp     rcx, [rax+10h]
0x18001b1e1  jnb     short loc_18001B1F7
0x18001b1e3  mov     dl, 8
0x18001b1e5  cmp     [rcx], dl
0x18001b1e7  jnz     short loc_18001B1F7
0x18001b1e9  mov     r8d, ebx
0x18001b1ec  lea     rcx, [rbp+60h+var_C0]
0x18001b1f0  call    ?consume_expected_marker@input_archive@tson@@AEAA_NW4archive_marker@details@2@J@Z; tson::input_archive::consume_expected_marker(tson::details::archive_marker,long)
0x18001b1f5  jmp     short loc_18001B250
0x18001b1f7  mov     rcx, [rdi]
0x18001b1fa  mov     rax, cs:?g_test_interface_exception_guard@details@tip2@@3P6A_NAEAUtest_data_interface@12@PEAVoutput_archive@tson@@W4serialize_options@12@PEAVinput_archive@5@PEBUTipReportingInfo@@@_EEA
0x18001b201  test    rax, rax
0x18001b204  jz      short loc_18001B23F
0x18001b206  mov     [rsp+160h+var_140], r15
0x18001b20b  lea     r9, [rbp+60h+var_C0]
0x18001b20f  xor     r8d, r8d
0x18001b212  xor     edx, edx
0x18001b214  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b219  test    al, al
0x18001b21b  jnz     short loc_18001B250
0x18001b21d  cmp     [rdi+0A0h], r15b
0x18001b224  jnz     short loc_18001B250
0x18001b226  mov     byte ptr [rdi+0A0h], 3
0x18001b22d  mov     word ptr [rdi+0A2h], 400Dh
0x18001b236  mov     [rdi+0A8h], r15
0x18001b23d  jmp     short loc_18001B250
0x18001b23f  mov     rax, [rcx]
0x18001b242  lea     rdx, [rbp+60h+var_C0]
0x18001b246  mov     rax, [rax+10h]
0x18001b24a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b24f  nop
0x18001b250  cmp     [rbp+60h+var_B8], r15d
0x18001b254  jl      short loc_18001B271
0x18001b256  mov     rax, [rbp+60h+var_C0]
0x18001b25a  cmp     [rax+18h], r15b
0x18001b25e  jnz     short loc_18001B271
0x18001b260  cmp     [rbp+60h+var_A0], r15b
0x18001b264  jnz     short loc_18001B271
0x18001b266  mov     eax, [rsi+10h]
0x18001b269  mov     [rdi+0B8h], eax
0x18001b26f  jmp     short loc_18001B276
0x18001b271  bts     dword ptr [rdi+40h], 13h
0x18001b276  mov     rcx, [rbp+60h+var_30]
0x18001b27a  xor     rcx, rsp; StackCookie
0x18001b27d  call    __security_check_cookie
0x18001b282  lea     r11, [rsp+160h+var_20]
0x18001b28a  mov     rbx, [r11+38h]
0x18001b28e  mov     rsi, [r11+40h]
0x18001b292  mov     rsp, r11
0x18001b295  pop     r15
0x18001b297  pop     r14
0x18001b299  pop     r12
0x18001b29b  pop     rdi
0x18001b29c  pop     rbp
0x18001b29d  retn
```
