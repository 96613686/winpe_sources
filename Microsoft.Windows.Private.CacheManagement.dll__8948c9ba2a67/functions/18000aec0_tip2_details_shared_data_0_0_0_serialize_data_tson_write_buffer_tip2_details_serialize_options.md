# tip2::details::shared_data<0,0,0>::serialize_data(tson::write_buffer &,tip2::details::serialize_options)

- ea: `0x18000aec0`
- end: `0x18000b318`
- name: `?serialize_data@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAPEBDAEAVwrite_buffer@tson@@W4serialize_options@23@@Z`
- size: `1112`
- prototype: `__int64 __fastcall(__int64 *, tson::write_buffer *, __int64)`
- caller_count: `3`
- callee_count: `10`
- tags: ``

## callers

- `0x18000a770`
- `0x18000a930`
- `0x18000b7c0`

## callees

- `0x180002b50`
- `0x18000aec0`
- `0x18000d3b0`
- `0x18000d6b0`
- `0x18000d8d0`
- `0x18000dac0`
- `0x18000de10`
- `0x18000de80`
- `0x1800181b0`
- `0x18001cdf0`

## pseudocode

```c
__int64 __fastcall tip2::details::shared_data<0,0,0>::serialize_data(__int64 *a1, tson::write_buffer *a2, __int64 a3)
{
  unsigned int v3; // r12d
  tson::write_buffer *v4; // r13
  char v6; // di
  tson::write_buffer *v7; // rbx
  char v8; // di
  tson::write_buffer *v9; // rbx
  _BYTE *v10; // rdi
  _BYTE *v11; // rax
  unsigned __int64 v12; // rbx
  __int64 v13; // r8
  __int64 v14; // rcx
  unsigned __int64 v15; // rax
  __int64 v16; // rdx
  int v17; // ecx
  void **v18; // rsi
  void **i; // r15
  _BYTE *v20; // rdi
  unsigned __int64 v21; // rbx
  __int64 v22; // rcx
  wil::details::in1diag3 *v23; // rcx
  tson::write_buffer *v24; // rax
  _DWORD *v25; // r8
  unsigned __int64 v26; // rdx
  _OWORD v28[8]; // [rsp+60h] [rbp-A0h] BYREF
  __int128 v29; // [rsp+E0h] [rbp-20h]
  tson::write_buffer *v30; // [rsp+F0h] [rbp-10h]

  v3 = a3;
  v4 = a2;
  if ( !(_DWORD)a3 )
    return 0;
  memset(v28, 0, sizeof(v28));
  v29 = 0;
  v6 = *((_BYTE *)a1 + 33);
  memset((char *)&v28[1] + 12, 0, 100);
  *(_QWORD *)&v29 = 0;
  DWORD2(v29) = 0;
  v30 = a2;
  if ( *((_QWORD *)a2 + 259) < *((_QWORD *)a2 + 260) || tson::write_buffer::reserve(a2, 1u) )
    *(_BYTE *)(*((_QWORD *)v4 + 259))++ = 0x80;
  v7 = v30;
  if ( *((_QWORD *)v30 + 259) < *((_QWORD *)v30 + 260) || tson::write_buffer::reserve(v30, 1u) )
  {
    **((_BYTE **)v30 + 259) = v6;
    ++*((_QWORD *)v7 + 259);
  }
  if ( (unsigned __int64)v29 >= 0x19 )
  {
    BYTE8(v28[1]) = 1;
  }
  else
  {
    *((_DWORD *)&v28[1] + v29 + 3) = 1;
    *(_QWORD *)&v29 = v29 + 1;
  }
  if ( (v3 & 4) != 0 )
  {
    v8 = *((_BYTE *)a1 + 33);
    if ( v8 )
    {
      *(_QWORD *)&v28[0] = "version";
      BYTE8(v28[0]) = 7;
      LOBYTE(a3) = 12;
      if ( (unsigned __int8)tson::output_archive::write_type(v28, 0, a3) )
      {
        v9 = v30;
        if ( *((_QWORD *)v30 + 259) < *((_QWORD *)v30 + 260) || tson::write_buffer::reserve(v30, 1u) )
          *(_BYTE *)(*((_QWORD *)v9 + 259))++ = v8;
      }
    }
  }
  if ( (v3 & 1) != 0 )
  {
    if ( (*((_DWORD *)a1 + 5) & 0x40000) == 0 )
    {
LABEL_28:
      *(_QWORD *)&v28[0] = "log";
      BYTE8(v28[0]) = 3;
      tson::output_archive::write_name((tson::output_archive *)v28, 0);
      v14 = v29;
      if ( (unsigned __int64)v29 >= 0x19 )
      {
        BYTE8(v28[1]) = 1;
      }
      else
      {
        *((_DWORD *)&v28[1] + v29 + 3) = 0;
        v14 = v29 + 1;
        *(_QWORD *)&v29 = v29 + 1;
      }
      v15 = a1[14];
      if ( v14 )
      {
        v16 = (__int64)&v28[1] + 4 * v14 + 8;
      }
      else
      {
        BYTE8(v28[1]) = 1;
        v16 = (__int64)&v28[1] + 12;
      }
      *(_DWORD *)v16 = 2;
      if ( v15 > 0xFFFF )
      {
        v17 = DWORD2(v29);
        v16 = 2147483659LL;
        if ( (SDWORD2(v29) & 0x80000000) == 0 )
          v17 = -2147483637;
        DWORD2(v29) = v17;
      }
      WORD5(v28[0]) = v15;
      v18 = (void **)a1[12];
      for ( i = &v18[a1[14]]; v18 != i; ++v18 )
      {
        v20 = *v18;
        if ( *v18 )
        {
          v21 = -1;
          do
            ++v21;
          while ( v20[v21] );
        }
        else
        {
          v21 = 0;
        }
        LOBYTE(v16) = v20 == 0;
        LOBYTE(v13) = 23;
        if ( (unsigned __int8)tson::output_archive::write_type(v28, v16, v13) )
          tson::output_archive::write_string_bytes((tson::output_archive *)v28, v21, v20, v21);
      }
      tson::output_archive::finishNode((tson::output_archive *)v28);
      tson::output_archive::process<tson::nvp<tip2::vector_nothrow<wil::StoredFailureInfo> &>,tson::nvp<tip2::vector_nothrow<tip2::test_flag> &>>((tson *)v28);
      goto LABEL_48;
    }
    v10 = (_BYTE *)a1[1];
    if ( v10 )
    {
      v11 = (_BYTE *)a1[1];
    }
    else
    {
      v10 = (_BYTE *)a1[3];
      v11 = v10;
      if ( !v10 )
      {
        v12 = 0;
        goto LABEL_26;
      }
    }
    v12 = -1;
    do
      ++v12;
    while ( v10[v12] );
LABEL_26:
    *(_QWORD *)&v28[0] = "name";
    BYTE8(v28[0]) = 4;
    LOBYTE(a2) = v11 == 0;
    LOBYTE(a3) = 23;
    if ( (unsigned __int8)tson::output_archive::write_type(v28, a2, a3) )
      tson::output_archive::write_string_bytes((tson::output_archive *)v28, v12, v10, v12);
    goto LABEL_28;
  }
LABEL_48:
  v22 = *a1;
  if ( tip2::details::g_test_interface_exception_guard )
  {
    if ( !(unsigned __int8)tip2::details::g_test_interface_exception_guard(v22, v28, v3, 0, 0) )
    {
      *((_BYTE *)a1 + 160) = 3;
      *((_WORD *)a1 + 81) = 16396;
      a1[21] = 0;
    }
  }
  else
  {
    (*(void (__fastcall **)(__int64, _OWORD *, _QWORD))(*(_QWORD *)v22 + 8LL))(v22, v28, v3);
  }
  if ( SDWORD2(v29) < 0 || BYTE8(v28[1]) )
    goto LABEL_58;
  v24 = v30;
  if ( *((_BYTE *)v30 + 8) )
  {
    *((_QWORD *)v30 + 258) = 0;
    *((_QWORD *)v24 + 259) = 0;
    *((_QWORD *)v24 + 260) = 0;
LABEL_58:
    *((_DWORD *)a1 + 16) |= 0x100000u;
    return 0;
  }
  v25 = (_DWORD *)*((_QWORD *)v30 + 258);
  v26 = (unsigned int)*((_QWORD *)v30 + 259) - (unsigned int)v25;
  if ( v26 > 0xFFFFFF )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v23);
  *v25 = v26 & 0x3F | (16 * v26) & 0x3F0000 | (4 * (_WORD)v26) & 0x3F00 | ((_DWORD)v26 << 6) & 0x3F000000 | 0x80408040;
  return *((_QWORD *)v4 + 258);
}

```

## disassembly

```asm
0x18000aec0  mov     [rsp-8+arg_8], rbx
0x18000aec5  push    rbp
0x18000aec6  push    rsi
0x18000aec7  push    rdi
0x18000aec8  push    r12
0x18000aeca  push    r13
0x18000aecc  push    r14
0x18000aece  push    r15
0x18000aed0  lea     rbp, [rsp-10h]
0x18000aed5  sub     rsp, 110h
0x18000aedc  mov     rax, cs:__security_cookie
0x18000aee3  xor     rax, rsp
0x18000aee6  mov     [rbp+40h+var_40], rax
0x18000aeea  mov     r12d, r8d
0x18000aeed  mov     r13, rdx
0x18000aef0  mov     r14, rcx
0x18000aef3  test    r8d, r8d
0x18000aef6  jz      loc_18000B2E9
0x18000aefc  xorps   xmm0, xmm0
0x18000aeff  xor     eax, eax
0x18000af01  movups  [rsp+140h+var_E0], xmm0
0x18000af06  movups  [rsp+140h+var_D0], xmm0
0x18000af0b  movups  [rbp+40h+var_C0], xmm0
0x18000af0f  movups  [rbp+40h+var_B0], xmm0
0x18000af13  movups  [rbp+40h+var_A0], xmm0
0x18000af17  movups  [rbp+40h+var_90], xmm0
0x18000af1b  movups  [rbp+40h+var_80], xmm0
0x18000af1f  movups  [rbp+40h+var_70], xmm0
0x18000af23  movups  [rbp+40h+var_60], xmm0
0x18000af27  movzx   edi, byte ptr [rcx+21h]
0x18000af2b  movups  [rsp+140h+var_D0+0Ch], xmm0
0x18000af30  movups  [rbp+40h+var_C0+0Ch], xmm0
0x18000af34  movups  [rbp+40h+var_B0+0Ch], xmm0
0x18000af38  movups  [rbp+40h+var_A0+0Ch], xmm0
0x18000af3c  movups  [rbp+40h+var_90+0Ch], xmm0
0x18000af40  movups  [rbp+40h+var_80+0Ch], xmm0
0x18000af44  mov     dword ptr [rbp+40h+var_70+0Ch], eax
0x18000af47  xor     esi, esi
0x18000af49  mov     qword ptr [rbp+40h+var_60], rsi
0x18000af4d  mov     dword ptr [rbp+40h+var_60+8], esi
0x18000af50  mov     [rbp+40h+var_50], rdx
0x18000af54  mov     rax, [rdx+820h]
0x18000af5b  cmp     [rdx+818h], rax
0x18000af62  jb      short loc_18000AF75
0x18000af64  mov     edx, 1; unsigned __int64
0x18000af69  mov     rcx, r13; this
0x18000af6c  call    ?reserve@write_buffer@tson@@AEAA_N_K@Z; tson::write_buffer::reserve(unsigned __int64)
0x18000af71  test    al, al
0x18000af73  jz      short loc_18000AF86
0x18000af75  mov     rax, [r13+818h]
0x18000af7c  mov     byte ptr [rax], 80h
0x18000af7f  inc     qword ptr [r13+818h]
0x18000af86  mov     rbx, [rbp+40h+var_50]
0x18000af8a  mov     rax, [rbx+820h]
0x18000af91  cmp     [rbx+818h], rax
0x18000af98  jb      short loc_18000AFAB
0x18000af9a  mov     edx, 1; unsigned __int64
0x18000af9f  mov     rcx, rbx; this
0x18000afa2  call    ?reserve@write_buffer@tson@@AEAA_N_K@Z; tson::write_buffer::reserve(unsigned __int64)
0x18000afa7  test    al, al
0x18000afa9  jz      short loc_18000AFBC
0x18000afab  mov     rax, [rbx+818h]
0x18000afb2  mov     [rax], dil
0x18000afb5  inc     qword ptr [rbx+818h]
0x18000afbc  mov     rax, qword ptr [rbp+40h+var_60]
0x18000afc0  cmp     rax, 19h
0x18000afc4  jnb     short loc_18000AFD4
0x18000afc6  mov     dword ptr [rsp+rax*4+140h+var_D0+0Ch], 1
0x18000afce  inc     qword ptr [rbp+40h+var_60]
0x18000afd2  jmp     short loc_18000AFD9
0x18000afd4  mov     byte ptr [rsp+140h+var_D0+8], 1
0x18000afd9  test    r12b, 4
0x18000afdd  jz      short loc_18000B043
0x18000afdf  movzx   edi, byte ptr [r14+21h]
0x18000afe4  test    dil, dil
0x18000afe7  jz      short loc_18000B043
0x18000afe9  lea     rax, aVersion; "version"
0x18000aff0  mov     qword ptr [rsp+140h+var_E0], rax
0x18000aff5  mov     byte ptr [rsp+140h+var_E0+8], 7
0x18000affa  mov     r8b, 0Ch
0x18000affd  xor     edx, edx
0x18000afff  lea     rcx, [rsp+140h+var_E0]
0x18000b004  call    ?write_type@output_archive@tson@@AEAA_N_NW4archive_marker@details@2@@Z; tson::output_archive::write_type(bool,tson::details::archive_marker)
0x18000b009  test    al, al
0x18000b00b  jz      short loc_18000B043
0x18000b00d  mov     rbx, [rbp+40h+var_50]
0x18000b011  mov     rax, [rbx+820h]
0x18000b018  cmp     [rbx+818h], rax
0x18000b01f  jb      short loc_18000B032
0x18000b021  mov     edx, 1; unsigned __int64
0x18000b026  mov     rcx, rbx; this
0x18000b029  call    ?reserve@write_buffer@tson@@AEAA_N_K@Z; tson::write_buffer::reserve(unsigned __int64)
0x18000b02e  test    al, al
0x18000b030  jz      short loc_18000B043
0x18000b032  mov     rax, [rbx+818h]
0x18000b039  mov     [rax], dil
0x18000b03c  inc     qword ptr [rbx+818h]
0x18000b043  test    r12b, 1
0x18000b047  jz      loc_18000B200
0x18000b04d  test    dword ptr [r14+14h], 40000h
0x18000b055  jz      short loc_18000B0C9
0x18000b057  mov     rdi, [r14+8]
0x18000b05b  test    rdi, rdi
0x18000b05e  jz      short loc_18000B065
0x18000b060  mov     rax, rdi
0x18000b063  jmp     short loc_18000B071
0x18000b065  mov     rdi, [r14+18h]
0x18000b069  mov     rax, rdi
0x18000b06c  test    rdi, rdi
0x18000b06f  jz      short loc_18000B08B
0x18000b071  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x18000b078  nop     dword ptr [rax+rax+00000000h]
0x18000b080  inc     rbx
0x18000b083  cmp     [rdi+rbx], sil
0x18000b087  jnz     short loc_18000B080
0x18000b089  jmp     short loc_18000B08E
0x18000b08b  mov     rbx, rsi
0x18000b08e  lea     rcx, aName_0; "name"
0x18000b095  mov     qword ptr [rsp+140h+var_E0], rcx
0x18000b09a  mov     byte ptr [rsp+140h+var_E0+8], 4
0x18000b09f  test    rax, rax
0x18000b0a2  setz    dl
0x18000b0a5  mov     r8b, 17h
0x18000b0a8  lea     rcx, [rsp+140h+var_E0]
0x18000b0ad  call    ?write_type@output_archive@tson@@AEAA_N_NW4archive_marker@details@2@@Z; tson::output_archive::write_type(bool,tson::details::archive_marker)
0x18000b0b2  test    al, al
0x18000b0b4  jz      short loc_18000B0C9
0x18000b0b6  mov     r9, rbx; unsigned __int64
0x18000b0b9  mov     r8, rdi; void *
0x18000b0bc  mov     rdx, rbx; unsigned __int64
0x18000b0bf  lea     rcx, [rsp+140h+var_E0]; this
0x18000b0c4  call    ?write_string_bytes@output_archive@tson@@AEAAX_KPEAX0@Z; tson::output_archive::write_string_bytes(unsigned __int64,void *,unsigned __int64)
0x18000b0c9  lea     rax, aFlags; "flags"
0x18000b0d0  mov     [rsp+140h+var_110], rax
0x18000b0d5  mov     [rsp+140h+var_108], 5
0x18000b0da  lea     rax, [r14+78h]
0x18000b0de  mov     [rsp+140h+var_100], rax
0x18000b0e3  lea     rax, aErrors; "errors"
0x18000b0ea  mov     [rsp+140h+var_F8], rax
0x18000b0ef  mov     [rsp+140h+var_F0], 6
0x18000b0f4  lea     rax, [r14+48h]
0x18000b0f8  mov     [rsp+140h+var_E8], rax
0x18000b0fd  lea     rax, aLog; "log"
0x18000b104  mov     qword ptr [rsp+140h+var_E0], rax
0x18000b109  mov     byte ptr [rsp+140h+var_E0+8], 3
0x18000b10e  xor     edx, edx; bool
0x18000b110  lea     rcx, [rsp+140h+var_E0]; this
0x18000b115  call    ?write_name@output_archive@tson@@AEAA_N_N@Z; tson::output_archive::write_name(bool)
0x18000b11a  mov     rcx, qword ptr [rbp+40h+var_60]
0x18000b11e  cmp     rcx, 19h
0x18000b122  jnb     short loc_18000B135
0x18000b124  mov     dword ptr [rsp+rcx*4+140h+var_D0+0Ch], esi
0x18000b128  mov     rcx, qword ptr [rbp+40h+var_60]
0x18000b12c  inc     rcx
0x18000b12f  mov     qword ptr [rbp+40h+var_60], rcx
0x18000b133  jmp     short loc_18000B13A
0x18000b135  mov     byte ptr [rsp+140h+var_D0+8], 1
0x18000b13a  mov     rax, [r14+70h]
0x18000b13e  test    rcx, rcx
0x18000b141  jz      short loc_18000B14E
0x18000b143  lea     rdx, [rsp+140h+var_D0+8]
0x18000b148  lea     rdx, [rdx+rcx*4]
0x18000b14c  jmp     short loc_18000B158
0x18000b14e  mov     byte ptr [rsp+140h+var_D0+8], 1
0x18000b153  lea     rdx, [rsp+140h+var_D0+0Ch]
0x18000b158  mov     dword ptr [rdx], 2
0x18000b15e  cmp     rax, 0FFFFh
0x18000b164  jbe     short loc_18000B176
0x18000b166  mov     ecx, dword ptr [rbp+40h+var_60+8]
0x18000b169  mov     edx, 8000000Bh
0x18000b16e  test    ecx, ecx
0x18000b170  cmovns  ecx, edx
0x18000b173  mov     dword ptr [rbp+40h+var_60+8], ecx
0x18000b176  mov     word ptr [rsp+140h+var_E0+0Ah], ax
0x18000b17b  mov     rsi, [r14+60h]
0x18000b17f  mov     rax, [r14+70h]
0x18000b183  lea     r15, [rsi+rax*8]
0x18000b187  cmp     rsi, r15
0x18000b18a  jz      short loc_18000B1E0
0x18000b18c  nop     dword ptr [rax+00h]
0x18000b190  mov     rdi, [rsi]
0x18000b193  test    rdi, rdi
0x18000b196  jz      short loc_18000B1AB
0x18000b198  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x18000b19f  nop
0x18000b1a0  inc     rbx
0x18000b1a3  cmp     byte ptr [rdi+rbx], 0
0x18000b1a7  jnz     short loc_18000B1A0
0x18000b1a9  jmp     short loc_18000B1AD
0x18000b1ab  xor     ebx, ebx
0x18000b1ad  test    rdi, rdi
0x18000b1b0  setz    dl
0x18000b1b3  mov     r8b, 17h
0x18000b1b6  lea     rcx, [rsp+140h+var_E0]
0x18000b1bb  call    ?write_type@output_archive@tson@@AEAA_N_NW4archive_marker@details@2@@Z; tson::output_archive::write_type(bool,tson::details::archive_marker)
0x18000b1c0  test    al, al
0x18000b1c2  jz      short loc_18000B1D7
0x18000b1c4  mov     r9, rbx; unsigned __int64
0x18000b1c7  mov     r8, rdi; void *
0x18000b1ca  mov     rdx, rbx; unsigned __int64
0x18000b1cd  lea     rcx, [rsp+140h+var_E0]; this
0x18000b1d2  call    ?write_string_bytes@output_archive@tson@@AEAAX_KPEAX0@Z; tson::output_archive::write_string_bytes(unsigned __int64,void *,unsigned __int64)
0x18000b1d7  add     rsi, 8
0x18000b1db  cmp     rsi, r15
0x18000b1de  jnz     short loc_18000B190
0x18000b1e0  lea     rcx, [rsp+140h+var_E0]; this
0x18000b1e5  call    ?finishNode@output_archive@tson@@QEAAXXZ; tson::output_archive::finishNode(void)
0x18000b1ea  lea     r8, [rsp+140h+var_110]
0x18000b1ef  lea     rdx, [rsp+140h+var_F8]
0x18000b1f4  lea     rcx, [rsp+140h+var_E0]; this
0x18000b1f9  call    ??$process@V?$nvp@AEAV?$vector_nothrow@VStoredFailureInfo@wil@@@tip2@@@tson@@V?$nvp@AEAV?$vector_nothrow@Utest_flag@tip2@@@tip2@@@2@@output_archive@tson@@AEAAX$$QEAV?$nvp@AEAV?$vector_nothrow@VStoredFailureInfo@wil@@@tip2@@@1@$$QEAV?$nvp@AEAV?$vector_nothrow@Utest_flag@tip2@@@tip2@@@1@@Z; tson::output_archive::process<tson::nvp<tip2::vector_nothrow<wil::StoredFailureInfo> &>,tson::nvp<tip2::vector_nothrow<tip2::test_flag> &>>(tson::nvp<tip2::vector_nothrow<wil::StoredFailureInfo> &> &&,tson::nvp<tip2::vector_nothrow<tip2::test_flag> &> &&)
0x18000b1fe  xor     esi, esi
0x18000b200  mov     rcx, [r14]
0x18000b203  mov     rax, cs:?g_test_interface_exception_guard@details@tip2@@3P6A_NAEAUtest_data_interface@12@PEAVoutput_archive@tson@@W4serialize_options@12@PEAVinput_archive@5@PEBUTipReportingInfo@@@_EEA
0x18000b20a  mov     r8d, r12d
0x18000b20d  lea     rdx, [rsp+140h+var_E0]
0x18000b212  test    rax, rax
0x18000b215  jz      short loc_18000B244
0x18000b217  mov     [rsp+140h+var_120], rsi
0x18000b21c  xor     r9d, r9d
0x18000b21f  call    cs:__guard_dispatch_icall_fptr
0x18000b225  test    al, al
0x18000b227  jnz     short loc_18000B252
0x18000b229  mov     byte ptr [r14+0A0h], 3
0x18000b231  mov     word ptr [r14+0A2h], 400Ch
0x18000b23b  mov     [r14+0A8h], rsi
0x18000b242  jmp     short loc_18000B252
0x18000b244  mov     rax, [rcx]
0x18000b247  mov     rax, [rax+8]
0x18000b24b  call    cs:__guard_dispatch_icall_fptr
0x18000b251  nop
0x18000b252  cmp     dword ptr [rbp+40h+var_60+8], 0
0x18000b256  jl      loc_18000B2E1
0x18000b25c  cmp     byte ptr [rsp+140h+var_D0+8], 0
0x18000b261  jnz     short loc_18000B2E1
0x18000b263  mov     rax, [rbp+40h+var_50]
0x18000b267  cmp     byte ptr [rax+8], 0
0x18000b26b  jnz     short loc_18000B2CC
0x18000b26d  mov     r8, [rax+810h]
0x18000b274  mov     rdx, [rax+818h]
0x18000b27b  sub     rdx, r8
0x18000b27e  mov     edx, edx
0x18000b280  cmp     rdx, 0FFFFFFh
0x18000b287  ja      loc_18000B312
0x18000b28d  mov     ecx, edx
0x18000b28f  shl     rcx, 6
0x18000b293  and     ecx, 3F000000h
0x18000b299  lea     rax, ds:0[rdx*4]
0x18000b2a1  and     eax, 3F00h
0x18000b2a6  or      ecx, eax
0x18000b2a8  mov     eax, edx
0x18000b2aa  shl     rax, 4
0x18000b2ae  and     eax, 3F0000h
0x18000b2b3  or      ecx, eax
0x18000b2b5  and     edx, 3Fh
0x18000b2b8  or      ecx, edx
0x18000b2ba  or      ecx, 80408040h
0x18000b2c0  mov     [r8], ecx
0x18000b2c3  mov     rax, [r13+810h]
0x18000b2ca  jmp     short loc_18000B2EB
0x18000b2cc  mov     [rax+810h], rsi
0x18000b2d3  mov     [rax+818h], rsi
0x18000b2da  mov     [rax+820h], rsi
0x18000b2e1  or      dword ptr [r14+40h], 100000h
0x18000b2e9  xor     eax, eax
0x18000b2eb  mov     rcx, [rbp+40h+var_40]
0x18000b2ef  xor     rcx, rsp; StackCookie
0x18000b2f2  call    __security_check_cookie
0x18000b2f7  mov     rbx, [rsp+140h+arg_8]
0x18000b2ff  add     rsp, 110h
0x18000b306  pop     r15
0x18000b308  pop     r14
0x18000b30a  pop     r13
0x18000b30c  pop     r12
0x18000b30e  pop     rdi
0x18000b30f  pop     rsi
0x18000b310  pop     rbp
0x18000b311  retn
0x18000b312  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
