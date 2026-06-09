# DataObject::encode(DataObject::type const &)

- ea: `0x18001a8dc`
- end: `0x18001ad72`
- name: `?encode@DataObject@@SA?AV?$tuple@V?$scoped_error@Utag@ntstatus_error@@@errorlib@@V?$vector@EU?$secure_allocator@E@wil@@@std@@U_Nil@tr1@4@U564@U564@U564@U564@U564@U564@U564@@tr1@std@@AEBUtype@1@@Z`
- size: `1174`
- prototype: `__int64 __fastcall(__int64, int *)`
- caller_count: `13`
- callee_count: `14`
- tags: `broker_com_uri`

## callers

- `0x1800152c8`
- `0x18001ad78`
- `0x18003365c`
- `0x18004189c`
- `0x180047800`
- `0x1800496c4`
- `0x1800501b8`
- `0x180050240`
- `0x1800502c8`
- `0x180050834`
- `0x1800509c8`
- `0x180050b5c`
- `0x180050cf0`

## callees

- `0x180007b18`
- `0x180008000`
- `0x1800089e8`
- `0x18000a9c4`
- `0x18000c37c`
- `0x18000c484`
- `0x18000efc0`
- `0x18000f1b8`
- `0x18000fb88`
- `0x18001a8dc`
- `0x18001d704`
- `0x180056a94`
- `0x1800586ba`
- `0x18005e010`

## string_xrefs

- `0x18001a989`: `onecore\ds\security\asn1\ntasn1\ntasn1der\derenc.c`
- `0x18001abc8`: `onecore\ds\security\asn1\ntasn1\ntasn1der\derenc.c`
- `0x18001abdc`: `onecore\ds\security\asn1\ntasn1\ntasn1der\derenc.c`

## pseudocode

```c
__int64 __fastcall DataObject::encode(__int64 a1, int *a2)
{
  int v4; // r14d
  unsigned __int64 v5; // rdx
  __int64 v6; // r12
  __int64 v7; // rcx
  __int64 v8; // rsi
  __int64 v9; // r9
  unsigned __int64 v10; // r8
  unsigned int v11; // ebx
  __int64 v12; // r9
  __int64 v13; // rcx
  unsigned __int64 v14; // rax
  _BYTE *v15; // rcx
  _BYTE *v16; // rcx
  __int64 v17; // r9
  __int64 v18; // r8
  unsigned int v19; // edi
  int v20; // ebx
  char v21; // r14
  __int64 v22; // rdx
  __int64 v23; // rax
  _BYTE *v24; // rdx
  __int64 v25; // r9
  _BYTE *v26; // rcx
  __int64 v27; // r9
  _BYTE *v28; // rax
  __int64 v29; // rbx
  __int64 v30; // rax
  _QWORD v32[2]; // [rsp+20h] [rbp-79h] BYREF
  __int128 v33; // [rsp+30h] [rbp-69h]
  __int64 v34; // [rsp+40h] [rbp-59h]
  __int64 (__fastcall *v35)(_QWORD *, __int64); // [rsp+48h] [rbp-51h]
  __int128 v36; // [rsp+50h] [rbp-49h]
  void *v37[4]; // [rsp+60h] [rbp-39h] BYREF
  __int64 v38; // [rsp+80h] [rbp-19h] BYREF
  __int64 v39; // [rsp+88h] [rbp-11h]
  _BYTE v40[88]; // [rsp+98h] [rbp-1h] BYREF
  unsigned int v41; // [rsp+108h] [rbp+6Fh] BYREF
  unsigned int v42; // [rsp+110h] [rbp+77h] BYREF
  int v43; // [rsp+114h] [rbp+7Bh]

  errorlib::scoped_error<ntstatus_error::tag>::scoped_error<ntstatus_error::tag>(&v42);
  std::_Vector_val<unsigned char,wil::secure_allocator<unsigned char>>::_Vector_val<unsigned char,wil::secure_allocator<unsigned char>>(v40);
  std::vector<unsigned char,wil::secure_allocator<unsigned char>>::resize(
    v40,
    *((_QWORD *)a2 + 2) - *((_QWORD *)a2 + 1) + 16LL);
  rangelib::make_raw_range<std::vector<unsigned char> const &>(&v38, v40);
  *(_QWORD *)&v33 = 0;
  v4 = *a2;
  v5 = *((_QWORD *)a2 + 2) - *((_QWORD *)a2 + 1);
  v6 = v38;
  v32[0] = v38;
  v32[1] = v39 - v5 - v38;
  v36 = 0;
  v34 = 0;
  v35 = 0;
  if ( v38 )
  {
    v7 = v39 - v5;
    *(_QWORD *)&v33 = v39 - v5;
    *((_QWORD *)&v33 + 1) = v39 - v5;
  }
  else
  {
    v33 = 0;
    v7 = 0;
  }
  v8 = 4;
  v9 = 2148073512LL;
  if ( v5 >= 0x80 )
  {
    if ( v5 >= 0x100 )
    {
      if ( v5 >= 0x10000 )
      {
        if ( v5 >= 0x1000000 )
        {
          v10 = 5;
          if ( v5 > 0xFFFFFFFF )
          {
            v11 = -2146881276;
            v12 = 294;
            v13 = 2148086020LL;
LABEL_16:
            DebugTraceError(v13, v5, "onecore\\ds\\security\\asn1\\ntasn1\\ntasn1der\\derenc.c", v12);
            goto LABEL_26;
          }
        }
        else
        {
          v10 = 4;
        }
      }
      else
      {
        v10 = 3;
      }
    }
    else
    {
      v10 = 2;
    }
  }
  else
  {
    v10 = 1;
  }
  if ( !v38 )
  {
    v11 = 0;
    *(_QWORD *)&v33 = v7 - v10;
    goto LABEL_26;
  }
  v14 = v7 - v38;
  if ( v5 >= 0x80 )
  {
    v11 = v14 < v10 ? 0x80090028 : 0;
    v16 = (_BYTE *)(v7 - v10);
    *(_QWORD *)&v33 = v16;
    if ( v10 > v14 )
    {
      v12 = 333;
      goto LABEL_20;
    }
    for ( *v16 = --v10 | 0x80; v10; --v10 )
    {
      *(_BYTE *)(v33 + v10) = v5;
      v5 >>= 8;
    }
  }
  else
  {
    v11 = v7 == v38 ? 0x80090028 : 0;
    v15 = (_BYTE *)(v7 - 1);
    *(_QWORD *)&v33 = v15;
    if ( !v14 )
    {
      v12 = 318;
LABEL_20:
      v13 = v11;
      goto LABEL_16;
    }
    *v15 = v5;
  }
LABEL_26:
  v41 = v11;
  errorlib::scoped_error<ntstatus_error::tag>::receive<long>(&v42, &v41, v10, v9);
  v43 = 3;
  v18 = 1;
  if ( (v42 >> 30) - 1 <= 2 )
  {
    std::_Vector_val<unsigned char,wil::secure_allocator<unsigned char>>::_Vector_val<unsigned char,wil::secure_allocator<unsigned char>>(v37);
    std::tr1::tuple<errorlib::scoped_error<ntstatus_error::tag>,std::vector<unsigned char,wil::secure_allocator<unsigned char>>,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil>::tuple<errorlib::scoped_error<ntstatus_error::tag>,std::vector<unsigned char,wil::secure_allocator<unsigned char>>,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil>(
      a1,
      &v42,
      v37);
    goto LABEL_75;
  }
  v19 = v4 & 0x1FFFFFFF;
  v20 = 0;
  if ( !v32[0] )
  {
    if ( v19 <= 0x1E )
    {
      v8 = 1;
    }
    else if ( v19 >= 0x80 )
    {
      if ( v19 >= 0x4000 )
      {
        if ( v19 >= 0x200000 )
          v8 = 6LL - (v19 < 0x10000000);
      }
      else
      {
        v8 = 3;
      }
    }
    else
    {
      v8 = 2;
    }
    *(_QWORD *)&v33 = v33 - v8;
    goto LABEL_71;
  }
  v21 = HIBYTE(v4) & 0xE0;
  v22 = v33;
  v23 = v33 - v32[0];
  if ( v19 <= 0x1E )
  {
    if ( !v23 )
    {
      if ( v35 )
      {
        v20 = v35(v32, 1);
        v22 = v33;
      }
      else
      {
        v20 = -2146893784;
      }
    }
    v24 = (_BYTE *)(v22 - 1);
    *(_QWORD *)&v33 = v24;
    if ( v20 < 0 )
    {
      v27 = 469;
      goto LABEL_55;
    }
    *v24 = v21 | v19;
  }
  else
  {
    if ( !v23 )
    {
      if ( v35 )
      {
        v20 = v35(v32, 1);
        v22 = v33;
        v18 = 1;
      }
      else
      {
        v20 = -2146893784;
      }
    }
    v24 = (_BYTE *)(v22 - 1);
    *(_QWORD *)&v33 = v24;
    if ( v20 < 0 )
    {
      v25 = 121;
LABEL_54:
      DebugTraceError((unsigned int)v20, v24, "onecore\\ds\\security\\asn1\\ntasn1\\ntasn1der\\derenc.c", v25);
      v27 = 447;
      goto LABEL_55;
    }
    *v24 = v19 & 0x7F;
    while ( 1 )
    {
      v19 >>= 7;
      v20 = 0;
      if ( !v19 )
        break;
      if ( v32[0] && (_QWORD)v33 == v32[0] )
      {
        if ( v35 )
          v20 = v35(v32, 1);
        else
          v20 = -2146893784;
      }
      v26 = (_BYTE *)(v33 - 1);
      *(_QWORD *)&v33 = v33 - 1;
      if ( v20 < 0 )
      {
        v25 = 138;
        goto LABEL_54;
      }
      *v26 = v19 | 0x80;
      v18 = 1;
    }
    if ( v32[0] && (_QWORD)v33 == v32[0] )
    {
      if ( v35 )
        v20 = v35(v32, 1);
      else
        v20 = -2146893784;
    }
    v28 = (_BYTE *)(v33 - 1);
    *(_QWORD *)&v33 = v33 - 1;
    if ( v20 < 0 )
    {
      v27 = 454;
LABEL_55:
      DebugTraceError((unsigned int)v20, v24, "onecore\\ds\\security\\asn1\\ntasn1\\ntasn1der\\derenc.c", v27);
      goto LABEL_71;
    }
    *v28 = v21 | 0x1F;
  }
LABEL_71:
  v41 = v20;
  errorlib::scoped_error<ntstatus_error::tag>::receive<long>(&v42, &v41, v18, v17);
  v43 = 3;
  if ( (v42 >> 30) - 1 <= 2 )
  {
    std::_Vector_val<unsigned char,wil::secure_allocator<unsigned char>>::_Vector_val<unsigned char,wil::secure_allocator<unsigned char>>(v37);
    std::tr1::tuple<errorlib::scoped_error<ntstatus_error::tag>,std::vector<unsigned char,wil::secure_allocator<unsigned char>>,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil>::tuple<errorlib::scoped_error<ntstatus_error::tag>,std::vector<unsigned char,wil::secure_allocator<unsigned char>>,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil>(
      a1,
      &v42,
      v37);
  }
  else
  {
    rangelib::make_range<rangelib::range<unsigned char *> &>(
      v37,
      &v38,
      v39 + *((_QWORD *)a2 + 1) - *((_QWORD *)a2 + 2) - v6,
      0);
    v29 = v33;
    memmove_0(v37[0], *((const void **)a2 + 1), *((_QWORD *)a2 + 2) - *((_QWORD *)a2 + 1));
    v30 = std::vector<unsigned char,wil::secure_allocator<unsigned char>>::vector<unsigned char,wil::secure_allocator<unsigned char>>(
            v37,
            v29,
            v37[1]);
    std::tr1::tuple<errorlib::scoped_error<ntstatus_error::tag>,std::vector<unsigned char,wil::secure_allocator<unsigned char>>,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil>::tuple<errorlib::scoped_error<ntstatus_error::tag>,std::vector<unsigned char,wil::secure_allocator<unsigned char>>,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil>(
      a1,
      &v42,
      v30);
  }
LABEL_75:
  std::vector<unsigned char,wil::secure_allocator<unsigned char>>::_Tidy(v37);
  std::vector<unsigned char,wil::secure_allocator<unsigned char>>::_Tidy(v40);
  errorlib::scoped_error<winerror_error::tag>::~scoped_error<winerror_error::tag>(&v42);
  return a1;
}

```

## disassembly

```asm
0x18001a8dc  mov     [rsp-8+arg_0], rbx
0x18001a8e1  push    rbp
0x18001a8e2  push    rsi
0x18001a8e3  push    rdi
0x18001a8e4  push    r12
0x18001a8e6  push    r13
0x18001a8e8  push    r14
0x18001a8ea  push    r15
0x18001a8ec  lea     rbp, [rsp-27h]
0x18001a8f1  sub     rsp, 0C0h
0x18001a8f8  mov     r13, rdx
0x18001a8fb  mov     r15, rcx
0x18001a8fe  xor     edi, edi
0x18001a900  lea     rcx, [rbp+57h+arg_10]
0x18001a904  call    ??0?$scoped_error@Utag@ntstatus_error@@@errorlib@@QEAA@XZ; errorlib::scoped_error<ntstatus_error::tag>::scoped_error<ntstatus_error::tag>(void)
0x18001a909  nop
0x18001a90a  lea     rcx, [rbp+57h+var_58]
0x18001a90e  call    ??0?$_Vector_val@EU?$secure_allocator@E@wil@@@std@@QEAA@U?$secure_allocator@E@wil@@@Z; std::_Vector_val<uchar,wil::secure_allocator<uchar>>::_Vector_val<uchar,wil::secure_allocator<uchar>>(wil::secure_allocator<uchar>)
0x18001a913  nop
0x18001a914  mov     rdx, [r13+10h]
0x18001a918  sub     rdx, [r13+8]
0x18001a91c  add     rdx, 10h
0x18001a920  lea     rcx, [rbp+57h+var_58]
0x18001a924  call    ?resize@?$vector@EU?$secure_allocator@E@wil@@@std@@QEAAX_K@Z; std::vector<uchar,wil::secure_allocator<uchar>>::resize(unsigned __int64)
0x18001a929  lea     rdx, [rbp+57h+var_58]
0x18001a92d  lea     rcx, [rbp+57h+var_70]
0x18001a931  call    ??$make_raw_range@AEBV?$vector@EV?$allocator@E@std@@@std@@@rangelib@@YA?AV?$range@PEBE@0@AEBV?$vector@EV?$allocator@E@std@@@std@@@Z; rangelib::make_raw_range<std::vector<uchar> const &>(std::vector<uchar> const &)
0x18001a936  mov     qword ptr [rbp+57h+var_C0], rdi
0x18001a93a  mov     r14d, [r13+0]
0x18001a93e  mov     rdx, [r13+10h]
0x18001a942  sub     rdx, [r13+8]
0x18001a946  mov     rax, [rbp+57h+var_68]
0x18001a94a  sub     rax, rdx
0x18001a94d  mov     r12, [rbp+57h+var_70]
0x18001a951  sub     rax, r12
0x18001a954  mov     [rbp+57h+var_D0], r12
0x18001a958  mov     [rbp+57h+var_C8], rax
0x18001a95c  xorps   xmm0, xmm0
0x18001a95f  movdqa  [rbp+57h+var_A0], xmm0
0x18001a964  mov     [rbp+57h+var_B0], rdi
0x18001a968  mov     [rbp+57h+var_A8], rdi
0x18001a96c  test    r12, r12
0x18001a96f  jz      short loc_18001A97F
0x18001a971  lea     rcx, [rax+r12]
0x18001a975  mov     qword ptr [rbp+57h+var_C0], rcx
0x18001a979  mov     qword ptr [rbp+57h+var_C0+8], rcx
0x18001a97d  jmp     short loc_18001A989
0x18001a97f  movdqa  [rbp+57h+var_C0], xmm0
0x18001a984  movq    rcx, xmm0
0x18001a989  lea     r10, aOnecoreDsSecur; "onecore\\ds\\security\\asn1\\ntasn1\\nt"...
0x18001a990  mov     esi, 4
0x18001a995  mov     r9d, 80090028h
0x18001a99b  lea     r11d, [rsi+7Ch]
0x18001a99f  cmp     rdx, r11
0x18001a9a2  jnb     short loc_18001A9BB
0x18001a9a4  lea     r8d, [rsi-3]
0x18001a9a8  test    r12, r12
0x18001a9ab  jnz     short loc_18001AA15
0x18001a9ad  mov     ebx, edi
0x18001a9af  sub     rcx, r8
0x18001a9b2  mov     qword ptr [rbp+57h+var_C0], rcx
0x18001a9b6  jmp     loc_18001AA82
0x18001a9bb  cmp     rdx, 100h
0x18001a9c2  jnb     short loc_18001A9CC
0x18001a9c4  mov     r8d, 2
0x18001a9ca  jmp     short loc_18001A9A8
0x18001a9cc  cmp     rdx, 10000h
0x18001a9d3  jnb     short loc_18001A9DD
0x18001a9d5  mov     r8d, 3
0x18001a9db  jmp     short loc_18001A9A8
0x18001a9dd  cmp     rdx, 1000000h
0x18001a9e4  jnb     short loc_18001A9EB
0x18001a9e6  mov     r8, rsi
0x18001a9e9  jmp     short loc_18001A9A8
0x18001a9eb  mov     eax, 0FFFFFFFFh
0x18001a9f0  mov     r8d, 5
0x18001a9f6  cmp     rdx, rax
0x18001a9f9  jbe     short loc_18001A9A8
0x18001a9fb  mov     ebx, 80093104h
0x18001aa00  mov     r9d, 126h
0x18001aa06  mov     ecx, 80093104h
0x18001aa0b  mov     r8, r10
0x18001aa0e  call    DebugTraceError
0x18001aa13  jmp     short loc_18001AA82
0x18001aa15  mov     rax, rcx
0x18001aa18  sub     rax, r12
0x18001aa1b  cmp     rdx, r11
0x18001aa1e  jnb     short loc_18001AA44
0x18001aa20  cmp     rax, 1
0x18001aa24  sbb     ebx, ebx
0x18001aa26  and     ebx, r9d
0x18001aa29  dec     rcx
0x18001aa2c  mov     qword ptr [rbp+57h+var_C0], rcx
0x18001aa30  cmp     rax, 1
0x18001aa34  jnb     short loc_18001AA40
0x18001aa36  mov     r9d, 13Eh
0x18001aa3c  mov     ecx, ebx
0x18001aa3e  jmp     short loc_18001AA0B
0x18001aa40  mov     [rcx], dl
0x18001aa42  jmp     short loc_18001AA82
0x18001aa44  cmp     rax, r8
0x18001aa47  sbb     ebx, ebx
0x18001aa49  and     ebx, r9d
0x18001aa4c  sub     rcx, r8
0x18001aa4f  mov     qword ptr [rbp+57h+var_C0], rcx
0x18001aa53  cmp     r8, rax
0x18001aa56  jbe     short loc_18001AA60
0x18001aa58  mov     r9d, 14Dh
0x18001aa5e  jmp     short loc_18001AA3C
0x18001aa60  dec     r8
0x18001aa63  mov     al, r8b
0x18001aa66  or      al, r11b
0x18001aa69  mov     [rcx], al
0x18001aa6b  test    r8, r8
0x18001aa6e  jz      short loc_18001AA82
0x18001aa70  mov     rax, qword ptr [rbp+57h+var_C0]
0x18001aa74  mov     [rax+r8], dl
0x18001aa78  shr     rdx, 8
0x18001aa7c  sub     r8, 1
0x18001aa80  jnz     short loc_18001AA70
0x18001aa82  mov     [rbp+57h+arg_8], ebx
0x18001aa85  lea     rdx, [rbp+57h+arg_8]
0x18001aa89  lea     rcx, [rbp+57h+arg_10]
0x18001aa8d  call    ??$receive@J@?$scoped_error@Utag@ntstatus_error@@@errorlib@@QEAAAEAV01@$$QEAJ@Z; errorlib::scoped_error<ntstatus_error::tag>::receive<long>(long &&)
0x18001aa92  mov     edx, 3
0x18001aa97  mov     [rbp+57h+arg_14], edx
0x18001aa9a  mov     eax, [rbp+57h+arg_10]
0x18001aa9d  shr     eax, 1Eh
0x18001aaa0  lea     r8d, [rdx-2]
0x18001aaa4  sub     eax, r8d
0x18001aaa7  cmp     eax, 2
0x18001aaaa  jbe     loc_18001AD1C
0x18001aab0  mov     edi, r14d
0x18001aab3  and     edi, 1FFFFFFFh
0x18001aab9  mov     rcx, [rbp+57h+var_D0]
0x18001aabd  xor     ebx, ebx
0x18001aabf  test    rcx, rcx
0x18001aac2  jnz     short loc_18001AB06
0x18001aac4  cmp     edi, 1Eh
0x18001aac7  jbe     short loc_18001AAFA
0x18001aac9  cmp     edi, 80h
0x18001aacf  jnb     short loc_18001AAD6
0x18001aad1  lea     esi, [rdx-1]
0x18001aad4  jmp     short loc_18001AAFD
0x18001aad6  cmp     edi, 4000h
0x18001aadc  jnb     short loc_18001AAE3
0x18001aade  mov     rsi, rdx
0x18001aae1  jmp     short loc_18001AAFD
0x18001aae3  cmp     edi, 200000h
0x18001aae9  jb      short loc_18001AAFD
0x18001aaeb  cmp     edi, 10000000h
0x18001aaf1  sbb     rsi, rsi
0x18001aaf4  add     rsi, 6
0x18001aaf8  jmp     short loc_18001AAFD
0x18001aafa  mov     rsi, r8
0x18001aafd  sub     qword ptr [rbp+57h+var_C0], rsi
0x18001ab01  jmp     loc_18001AC81
0x18001ab06  shr     r14d, 18h
0x18001ab0a  and     r14b, 0E0h
0x18001ab0e  mov     rdx, qword ptr [rbp+57h+var_C0]
0x18001ab12  mov     rax, rdx
0x18001ab15  sub     rax, rcx
0x18001ab18  cmp     edi, 1Eh
0x18001ab1b  jbe     loc_18001AC3E
0x18001ab21  cmp     rax, r8
0x18001ab24  jnb     short loc_18001AB4E
0x18001ab26  mov     rax, [rbp+57h+var_A8]
0x18001ab2a  test    rax, rax
0x18001ab2d  jz      short loc_18001AB49
0x18001ab2f  mov     rdx, r8
0x18001ab32  lea     rcx, [rbp+57h+var_D0]
0x18001ab36  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ab3b  mov     ebx, eax
0x18001ab3d  mov     rdx, qword ptr [rbp+57h+var_C0]
0x18001ab41  mov     r8d, 1
0x18001ab47  jmp     short loc_18001AB4E
0x18001ab49  mov     ebx, 80090028h
0x18001ab4e  dec     rdx
0x18001ab51  mov     qword ptr [rbp+57h+var_C0], rdx
0x18001ab55  test    ebx, ebx
0x18001ab57  jns     short loc_18001AB61
0x18001ab59  mov     r9d, 79h ; 'y'
0x18001ab5f  jmp     short loc_18001ABC8
0x18001ab61  mov     al, dil
0x18001ab64  and     al, 7Fh
0x18001ab66  mov     [rdx], al
0x18001ab68  shr     edi, 7
0x18001ab6b  xor     ebx, ebx
0x18001ab6d  mov     rcx, [rbp+57h+var_D0]
0x18001ab71  test    edi, edi
0x18001ab73  jz      short loc_18001ABEF
0x18001ab75  test    rcx, rcx
0x18001ab78  jz      short loc_18001ABA4
0x18001ab7a  mov     rax, qword ptr [rbp+57h+var_C0]
0x18001ab7e  sub     rax, rcx
0x18001ab81  cmp     rax, r8
0x18001ab84  jnb     short loc_18001ABA4
0x18001ab86  mov     rax, [rbp+57h+var_A8]
0x18001ab8a  test    rax, rax
0x18001ab8d  jz      short loc_18001AB9F
0x18001ab8f  mov     rdx, r8
0x18001ab92  lea     rcx, [rbp+57h+var_D0]
0x18001ab96  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ab9b  mov     ebx, eax
0x18001ab9d  jmp     short loc_18001ABA4
0x18001ab9f  mov     ebx, 80090028h
0x18001aba4  mov     rcx, qword ptr [rbp+57h+var_C0]
0x18001aba8  dec     rcx
0x18001abab  mov     qword ptr [rbp+57h+var_C0], rcx
0x18001abaf  test    ebx, ebx
0x18001abb1  js      short loc_18001ABC2
0x18001abb3  mov     al, dil
0x18001abb6  or      al, 80h
0x18001abb8  mov     [rcx], al
0x18001abba  mov     r8d, 1
0x18001abc0  jmp     short loc_18001AB68
0x18001abc2  mov     r9d, 8Ah
0x18001abc8  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\asn1\\ntasn1\\nt"...
0x18001abcf  mov     ecx, ebx
0x18001abd1  call    DebugTraceError
0x18001abd6  mov     r9d, 1BFh
0x18001abdc  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\asn1\\ntasn1\\nt"...
0x18001abe3  mov     ecx, ebx
0x18001abe5  call    DebugTraceError
0x18001abea  jmp     loc_18001AC81
0x18001abef  test    rcx, rcx
0x18001abf2  jz      short loc_18001AC1E
0x18001abf4  mov     rax, qword ptr [rbp+57h+var_C0]
0x18001abf8  sub     rax, rcx
0x18001abfb  cmp     rax, r8
0x18001abfe  jnb     short loc_18001AC1E
0x18001ac00  mov     rax, [rbp+57h+var_A8]
0x18001ac04  test    rax, rax
0x18001ac07  jz      short loc_18001AC19
0x18001ac09  mov     rdx, r8
0x18001ac0c  lea     rcx, [rbp+57h+var_D0]
0x18001ac10  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ac15  mov     ebx, eax
0x18001ac17  jmp     short loc_18001AC1E
0x18001ac19  mov     ebx, 80090028h
0x18001ac1e  mov     rax, qword ptr [rbp+57h+var_C0]
0x18001ac22  dec     rax
0x18001ac25  mov     qword ptr [rbp+57h+var_C0], rax
0x18001ac29  test    ebx, ebx
0x18001ac2b  jns     short loc_18001AC35
0x18001ac2d  mov     r9d, 1C6h
0x18001ac33  jmp     short loc_18001ABDC
0x18001ac35  or      r14b, 1Fh
0x18001ac39  mov     [rax], r14b
0x18001ac3c  jmp     short loc_18001AC81
0x18001ac3e  cmp     rax, r8
0x18001ac41  jnb     short loc_18001AC65
0x18001ac43  mov     rax, [rbp+57h+var_A8]
0x18001ac47  test    rax, rax
0x18001ac4a  jz      short loc_18001AC60
0x18001ac4c  mov     rdx, r8
0x18001ac4f  lea     rcx, [rbp+57h+var_D0]
0x18001ac53  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ac58  mov     ebx, eax
0x18001ac5a  mov     rdx, qword ptr [rbp+57h+var_C0]
0x18001ac5e  jmp     short loc_18001AC65
0x18001ac60  mov     ebx, 80090028h
0x18001ac65  dec     rdx
0x18001ac68  mov     qword ptr [rbp+57h+var_C0], rdx
0x18001ac6c  test    ebx, ebx
0x18001ac6e  jns     short loc_18001AC7B
0x18001ac70  mov     r9d, 1D5h
0x18001ac76  jmp     loc_18001ABDC
0x18001ac7b  or      dil, r14b
0x18001ac7e  mov     [rdx], dil
0x18001ac81  mov     [rbp+57h+arg_8], ebx
0x18001ac84  lea     rdx, [rbp+57h+arg_8]
0x18001ac88  lea     rcx, [rbp+57h+arg_10]
0x18001ac8c  call    ??$receive@J@?$scoped_error@Utag@ntstatus_error@@@errorlib@@QEAAAEAV01@$$QEAJ@Z; errorlib::scoped_error<ntstatus_error::tag>::receive<long>(long &&)
0x18001ac91  mov     [rbp+57h+arg_14], 3
0x18001ac98  mov     eax, [rbp+57h+arg_10]
0x18001ac9b  shr     eax, 1Eh
0x18001ac9e  dec     eax
0x18001aca0  cmp     eax, 2
0x18001aca3  jbe     short loc_18001ACFF
0x18001aca5  mov     r8, [r13+8]
0x18001aca9  sub     r8, [r13+10h]
0x18001acad  sub     r8, r12
0x18001acb0  add     r8, [rbp+57h+var_68]
0x18001acb4  xor     r9d, r9d
0x18001acb7  lea     rdx, [rbp+57h+var_70]
0x18001acbb  lea     rcx, [rbp+57h+var_90]
0x18001acbf  call    ??$make_range@AEAV?$range@PEAE@rangelib@@@rangelib@@YA?AV?$range@PEAE@0@AEAV10@_J1@Z; rangelib::make_range<rangelib::range<uchar *> &>(rangelib::range<uchar *> &,__int64,__int64)
0x18001acc4  mov     rbx, qword ptr [rbp+57h+var_C0]
0x18001acc8  mov     rdx, [r13+8]; Src
0x18001accc  mov     r8, [r13+10h]
0x18001acd0  sub     r8, rdx; Size
0x18001acd3  mov     rcx, [rbp+57h+var_90]; void *
0x18001acd7  call    memmove_0
0x18001acdc  mov     r8, [rbp+57h+var_88]
0x18001ace0  mov     rdx, rbx
0x18001ace3  lea     rcx, [rbp+57h+var_90]
0x18001ace7  call    ??$?0PEAE@?$vector@EU?$secure_allocator@E@wil@@@std@@QEAA@PEAE0@Z; std::vector<uchar,wil::secure_allocator<uchar>>::vector<uchar,wil::secure_allocator<uchar>>(uchar *,uchar *)
0x18001acec  nop
0x18001aced  mov     r8, rax
  ... truncated ...
```
