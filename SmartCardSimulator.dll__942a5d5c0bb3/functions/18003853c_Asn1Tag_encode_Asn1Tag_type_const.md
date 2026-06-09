# Asn1Tag::encode(Asn1Tag::type const &)

- ea: `0x18003853c`
- end: `0x180038803`
- name: `?encode@Asn1Tag@@SA?AV?$tuple@V?$scoped_error@Utag@ntstatus_error@@@errorlib@@V?$vector@EU?$secure_allocator@E@wil@@@std@@U_Nil@tr1@4@U564@U564@U564@U564@U564@U564@U564@@tr1@std@@AEBUtype@1@@Z`
- size: `711`
- prototype: ``
- caller_count: `3`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x1800303cc`
- `0x18003365c`
- `0x180039eac`

## callees

- `0x180008000`
- `0x1800089e8`
- `0x18000a9c4`
- `0x18000c37c`
- `0x18000c484`
- `0x18000efc0`
- `0x18000f1b8`
- `0x18000fb88`
- `0x18001d704`
- `0x18003853c`
- `0x180056a94`
- `0x18005e010`

## string_xrefs

- `0x1800386d3`: `onecore\ds\security\asn1\ntasn1\ntasn1der\derenc.c`
- `0x1800386e7`: `onecore\ds\security\asn1\ntasn1\ntasn1der\derenc.c`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall Asn1Tag::encode(__int64 a1, int *a2)
{
  __int64 v4; // rsi
  __int64 v5; // r9
  __int64 v6; // r8
  __int64 v7; // rcx
  __int64 v8; // rdx
  int v9; // r15d
  unsigned int v10; // edi
  signed int v11; // ebx
  char v12; // r15
  __int64 v13; // rdx
  _BYTE *v14; // rcx
  __int64 v15; // r9
  char i; // al
  __int64 v17; // r9
  _BYTE *v18; // rax
  _BYTE *v19; // rcx
  __int64 v20; // rax
  _QWORD v22[2]; // [rsp+20h] [rbp-59h] BYREF
  __int128 v23; // [rsp+30h] [rbp-49h]
  __int64 v24; // [rsp+40h] [rbp-39h]
  __int64 (__fastcall *v25)(_QWORD *, __int64); // [rsp+48h] [rbp-31h]
  __int128 v26; // [rsp+50h] [rbp-29h]
  __int64 v27; // [rsp+68h] [rbp-11h] BYREF
  __int64 v28; // [rsp+70h] [rbp-9h]
  _BYTE v29[72]; // [rsp+88h] [rbp+Fh] BYREF
  signed int v30; // [rsp+E8h] [rbp+6Fh] BYREF
  unsigned int v31; // [rsp+F0h] [rbp+77h] BYREF
  int v32; // [rsp+F4h] [rbp+7Bh]

  errorlib::scoped_error<ntstatus_error::tag>::scoped_error<ntstatus_error::tag>(&v31);
  std::_Vector_val<unsigned char,wil::secure_allocator<unsigned char>>::_Vector_val<unsigned char,wil::secure_allocator<unsigned char>>(v29);
  v4 = 4;
  std::vector<unsigned char,wil::secure_allocator<unsigned char>>::resize(v29, 4);
  rangelib::make_raw_range<std::vector<unsigned char> const &>(&v27, v29);
  *(_QWORD *)&v23 = 0;
  v6 = v27;
  v22[0] = v27;
  v22[1] = v28 - v27;
  v26 = 0;
  v24 = 0;
  v25 = 0;
  if ( v27 )
  {
    v7 = v28;
    *((_QWORD *)&v23 + 1) = v28;
  }
  else
  {
    v23 = 0;
    v7 = 0;
  }
  v8 = v28;
  if ( !v27 )
    v8 = 0;
  v9 = *a2;
  v10 = v9 & 0x1FFFFFFF;
  if ( v27 )
  {
    v12 = HIBYTE(v9) & 0xE0;
    v13 = v8 - v27;
    if ( v10 <= 0x1E )
    {
      v11 = v13 == 0 ? 0x80090028 : 0;
      v19 = (_BYTE *)(v7 - 1);
      *(_QWORD *)&v23 = v19;
      if ( v13 )
      {
        *v19 = v12 | v10;
        goto LABEL_42;
      }
      v17 = 469;
    }
    else
    {
      v11 = v13 == 0 ? 0x80090028 : 0;
      v14 = (_BYTE *)(v7 - 1);
      *(_QWORD *)&v23 = v14;
      if ( v13 )
      {
        for ( i = v10 & 0x7F; ; i = v10 | 0x80 )
        {
          v10 >>= 7;
          *v14 = i;
          v11 = 0;
          if ( !v10 )
            break;
          if ( v22[0] && (_QWORD)v23 == v22[0] )
          {
            if ( v25 )
              v11 = v25(v22, 1);
            else
              v11 = -2146893784;
          }
          v14 = (_BYTE *)(v23 - 1);
          *(_QWORD *)&v23 = v23 - 1;
          if ( v11 < 0 )
          {
            v15 = 138;
            goto LABEL_29;
          }
        }
        if ( v22[0] && (_QWORD)v23 == v22[0] )
        {
          if ( v25 )
            v11 = v25(v22, 1);
          else
            v11 = -2146893784;
        }
        v18 = (_BYTE *)(v23 - 1);
        *(_QWORD *)&v23 = v23 - 1;
        if ( v11 >= 0 )
        {
          *v18 = v12 | 0x1F;
          goto LABEL_42;
        }
        v17 = 454;
      }
      else
      {
        v15 = 121;
LABEL_29:
        DebugTraceError((unsigned int)v11, v13, "onecore\\ds\\security\\asn1\\ntasn1\\ntasn1der\\derenc.c", v15);
        v17 = 447;
      }
    }
    DebugTraceError((unsigned int)v11, v13, "onecore\\ds\\security\\asn1\\ntasn1\\ntasn1der\\derenc.c", v17);
    goto LABEL_42;
  }
  v11 = 0;
  if ( v10 <= 0x1E )
  {
    v4 = 1;
  }
  else if ( v10 >= 0x80 )
  {
    if ( v10 >= 0x4000 )
    {
      if ( v10 >= 0x200000 )
        v4 = 6LL - (v10 < 0x10000000);
    }
    else
    {
      v4 = 3;
    }
  }
  else
  {
    v4 = 2;
  }
  *(_QWORD *)&v23 = v7 - v4;
LABEL_42:
  v30 = v11;
  errorlib::scoped_error<ntstatus_error::tag>::receive<long>(&v31, &v30, v6, v5);
  v32 = 3;
  if ( (v31 >> 30) - 1 <= 2 )
  {
    std::_Vector_val<unsigned char,wil::secure_allocator<unsigned char>>::_Vector_val<unsigned char,wil::secure_allocator<unsigned char>>(&v27);
    std::tr1::tuple<errorlib::scoped_error<ntstatus_error::tag>,std::vector<unsigned char,wil::secure_allocator<unsigned char>>,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil>::tuple<errorlib::scoped_error<ntstatus_error::tag>,std::vector<unsigned char,wil::secure_allocator<unsigned char>>,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil>(
      a1,
      &v31,
      &v27);
  }
  else
  {
    v20 = std::vector<unsigned char,wil::secure_allocator<unsigned char>>::vector<unsigned char,wil::secure_allocator<unsigned char>>(
            &v27,
            v23,
            *((_QWORD *)&v23 + 1));
    std::tr1::tuple<errorlib::scoped_error<ntstatus_error::tag>,std::vector<unsigned char,wil::secure_allocator<unsigned char>>,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil>::tuple<errorlib::scoped_error<ntstatus_error::tag>,std::vector<unsigned char,wil::secure_allocator<unsigned char>>,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil>(
      a1,
      &v31,
      v20);
  }
  std::vector<unsigned char,wil::secure_allocator<unsigned char>>::_Tidy(&v27);
  std::vector<unsigned char,wil::secure_allocator<unsigned char>>::_Tidy(v29);
  errorlib::scoped_error<winerror_error::tag>::~scoped_error<winerror_error::tag>(&v31);
  return a1;
}

```

## disassembly

```asm
0x18003853c  mov     [rsp-8+arg_0], rbx
0x180038541  push    rbp
0x180038542  push    rsi
0x180038543  push    rdi
0x180038544  push    r12
0x180038546  push    r15
0x180038548  lea     rbp, [rsp-37h]
0x18003854d  sub     rsp, 0B0h
0x180038554  mov     r15, rdx
0x180038557  mov     r12, rcx
0x18003855a  lea     rcx, [rbp+57h+arg_10]
0x18003855e  call    ??0?$scoped_error@Utag@ntstatus_error@@@errorlib@@QEAA@XZ; errorlib::scoped_error<ntstatus_error::tag>::scoped_error<ntstatus_error::tag>(void)
0x180038563  nop
0x180038564  lea     rcx, [rbp+57h+var_48]
0x180038568  call    ??0?$_Vector_val@EU?$secure_allocator@E@wil@@@std@@QEAA@U?$secure_allocator@E@wil@@@Z; std::_Vector_val<uchar,wil::secure_allocator<uchar>>::_Vector_val<uchar,wil::secure_allocator<uchar>>(wil::secure_allocator<uchar>)
0x18003856d  nop
0x18003856e  mov     esi, 4
0x180038573  mov     edx, esi
0x180038575  lea     rcx, [rbp+57h+var_48]
0x180038579  call    ?resize@?$vector@EU?$secure_allocator@E@wil@@@std@@QEAAX_K@Z; std::vector<uchar,wil::secure_allocator<uchar>>::resize(unsigned __int64)
0x18003857e  lea     rdx, [rbp+57h+var_48]
0x180038582  lea     rcx, [rbp+57h+var_68]
0x180038586  call    ??$make_raw_range@AEBV?$vector@EV?$allocator@E@std@@@std@@@rangelib@@YA?AV?$range@PEBE@0@AEBV?$vector@EV?$allocator@E@std@@@std@@@Z; rangelib::make_raw_range<std::vector<uchar> const &>(std::vector<uchar> const &)
0x18003858b  mov     qword ptr [rbp+57h+var_A0], 0
0x180038593  mov     rax, [rbp+57h+var_60]
0x180038597  mov     r8, [rbp+57h+var_68]
0x18003859b  sub     rax, r8
0x18003859e  mov     [rbp+57h+var_B0], r8
0x1800385a2  mov     [rbp+57h+var_A8], rax
0x1800385a6  xorps   xmm0, xmm0
0x1800385a9  movdqa  [rbp+57h+var_80], xmm0
0x1800385ae  mov     [rbp+57h+var_90], 0
0x1800385b6  mov     [rbp+57h+var_88], 0
0x1800385be  test    r8, r8
0x1800385c1  jz      short loc_1800385CD
0x1800385c3  lea     rcx, [rax+r8]
0x1800385c7  mov     qword ptr [rbp+57h+var_A0+8], rcx
0x1800385cb  jmp     short loc_1800385D7
0x1800385cd  movdqa  [rbp+57h+var_A0], xmm0
0x1800385d2  movq    rcx, xmm0
0x1800385d7  lea     rdx, [rax+r8]
0x1800385db  xor     eax, eax
0x1800385dd  test    r8, r8
0x1800385e0  cmovz   rdx, rax
0x1800385e4  mov     r15d, [r15]
0x1800385e7  mov     edi, r15d
0x1800385ea  and     edi, 1FFFFFFFh
0x1800385f0  test    r8, r8
0x1800385f3  jnz     short loc_180038640
0x1800385f5  xor     ebx, ebx
0x1800385f7  cmp     edi, 1Eh
0x1800385fa  jbe     short loc_18003862F
0x1800385fc  cmp     edi, 80h
0x180038602  jnb     short loc_180038609
0x180038604  lea     esi, [rax+2]
0x180038607  jmp     short loc_180038634
0x180038609  cmp     edi, 4000h
0x18003860f  jnb     short loc_180038618
0x180038611  mov     esi, 3
0x180038616  jmp     short loc_180038634
0x180038618  cmp     edi, 200000h
0x18003861e  jb      short loc_180038634
0x180038620  cmp     edi, 10000000h
0x180038626  sbb     rsi, rsi
0x180038629  add     rsi, 6
0x18003862d  jmp     short loc_180038634
0x18003862f  mov     esi, 1
0x180038634  sub     rcx, rsi
0x180038637  mov     qword ptr [rbp+57h+var_A0], rcx
0x18003863b  jmp     loc_18003876D
0x180038640  shr     r15d, 18h
0x180038644  and     r15b, 0E0h
0x180038648  sub     rdx, r8
0x18003864b  cmp     edi, 1Eh
0x18003864e  jbe     loc_180038746
0x180038654  cmp     rdx, 1
0x180038658  sbb     ebx, ebx
0x18003865a  mov     esi, 80090028h
0x18003865f  and     ebx, esi
0x180038661  dec     rcx
0x180038664  mov     qword ptr [rbp+57h+var_A0], rcx
0x180038668  cmp     rdx, 1
0x18003866c  jnb     short loc_180038676
0x18003866e  mov     r9d, 79h ; 'y'
0x180038674  jmp     short loc_1800386D3
0x180038676  mov     al, dil
0x180038679  and     al, 7Fh
0x18003867b  shr     edi, 7
0x18003867e  mov     [rcx], al
0x180038680  xor     ebx, ebx
0x180038682  mov     rcx, [rbp+57h+var_B0]
0x180038686  test    edi, edi
0x180038688  jz      short loc_1800386F7
0x18003868a  test    rcx, rcx
0x18003868d  jz      short loc_1800386B7
0x18003868f  mov     rax, qword ptr [rbp+57h+var_A0]
0x180038693  sub     rax, rcx
0x180038696  cmp     rax, 1
0x18003869a  jnb     short loc_1800386B7
0x18003869c  mov     rax, [rbp+57h+var_88]
0x1800386a0  test    rax, rax
0x1800386a3  jz      short loc_1800386B5
0x1800386a5  lea     edx, [rbx+1]
0x1800386a8  lea     rcx, [rbp+57h+var_B0]
0x1800386ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800386b1  mov     ebx, eax
0x1800386b3  jmp     short loc_1800386B7
0x1800386b5  mov     ebx, esi
0x1800386b7  mov     rcx, qword ptr [rbp+57h+var_A0]
0x1800386bb  dec     rcx
0x1800386be  mov     qword ptr [rbp+57h+var_A0], rcx
0x1800386c2  test    ebx, ebx
0x1800386c4  js      short loc_1800386CD
0x1800386c6  mov     al, dil
0x1800386c9  or      al, 80h
0x1800386cb  jmp     short loc_18003867B
0x1800386cd  mov     r9d, 8Ah
0x1800386d3  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\asn1\\ntasn1\\nt"...
0x1800386da  mov     ecx, ebx
0x1800386dc  call    DebugTraceError
0x1800386e1  mov     r9d, 1BFh
0x1800386e7  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\asn1\\ntasn1\\nt"...
0x1800386ee  mov     ecx, ebx
0x1800386f0  call    DebugTraceError
0x1800386f5  jmp     short loc_18003876D
0x1800386f7  test    rcx, rcx
0x1800386fa  jz      short loc_180038726
0x1800386fc  mov     rax, qword ptr [rbp+57h+var_A0]
0x180038700  sub     rax, rcx
0x180038703  cmp     rax, 1
0x180038707  jnb     short loc_180038726
0x180038709  mov     rax, [rbp+57h+var_88]
0x18003870d  test    rax, rax
0x180038710  jz      short loc_180038724
0x180038712  mov     edx, 1
0x180038717  lea     rcx, [rbp+57h+var_B0]
0x18003871b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038720  mov     ebx, eax
0x180038722  jmp     short loc_180038726
0x180038724  mov     ebx, esi
0x180038726  mov     rax, qword ptr [rbp+57h+var_A0]
0x18003872a  dec     rax
0x18003872d  mov     qword ptr [rbp+57h+var_A0], rax
0x180038731  test    ebx, ebx
0x180038733  jns     short loc_18003873D
0x180038735  mov     r9d, 1C6h
0x18003873b  jmp     short loc_1800386E7
0x18003873d  or      r15b, 1Fh
0x180038741  mov     [rax], r15b
0x180038744  jmp     short loc_18003876D
0x180038746  cmp     rdx, 1
0x18003874a  sbb     ebx, ebx
0x18003874c  and     ebx, 80090028h
0x180038752  dec     rcx
0x180038755  mov     qword ptr [rbp+57h+var_A0], rcx
0x180038759  cmp     rdx, 1
0x18003875d  jnb     short loc_180038767
0x18003875f  mov     r9d, 1D5h
0x180038765  jmp     short loc_1800386E7
0x180038767  or      dil, r15b
0x18003876a  mov     [rcx], dil
0x18003876d  mov     [rbp+57h+arg_8], ebx
0x180038770  lea     rdx, [rbp+57h+arg_8]
0x180038774  lea     rcx, [rbp+57h+arg_10]
0x180038778  call    ??$receive@J@?$scoped_error@Utag@ntstatus_error@@@errorlib@@QEAAAEAV01@$$QEAJ@Z; errorlib::scoped_error<ntstatus_error::tag>::receive<long>(long &&)
0x18003877d  mov     [rbp+57h+arg_14], 3
0x180038784  mov     eax, [rbp+57h+arg_10]
0x180038787  shr     eax, 1Eh
0x18003878a  dec     eax
0x18003878c  lea     rcx, [rbp+57h+var_68]
0x180038790  cmp     eax, 2
0x180038793  jbe     short loc_1800387B5
0x180038795  mov     r8, qword ptr [rbp+57h+var_A0+8]
0x180038799  mov     rdx, qword ptr [rbp+57h+var_A0]
0x18003879d  call    ??$?0PEAE@?$vector@EU?$secure_allocator@E@wil@@@std@@QEAA@PEAE0@Z; std::vector<uchar,wil::secure_allocator<uchar>>::vector<uchar,wil::secure_allocator<uchar>>(uchar *,uchar *)
0x1800387a2  nop
0x1800387a3  mov     r8, rax
0x1800387a6  lea     rdx, [rbp+57h+arg_10]
0x1800387aa  mov     rcx, r12
0x1800387ad  call    ??$?0AEAV?$scoped_error@Utag@ntstatus_error@@@errorlib@@V?$vector@EU?$secure_allocator@E@wil@@@std@@@?$tuple@V?$scoped_error@Utag@ntstatus_error@@@errorlib@@V?$vector@EU?$secure_allocator@E@wil@@@std@@U_Nil@tr1@4@U564@U564@U564@U564@U564@U564@U564@@tr1@std@@QEAA@AEAV?$scoped_error@Utag@ntstatus_error@@@errorlib@@$$QEAV?$vector@EU?$secure_allocator@E@wil@@@2@@Z; std::tr1::tuple<errorlib::scoped_error<ntstatus_error::tag>,std::vector<uchar,wil::secure_allocator<uchar>>,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil>::tuple<errorlib::scoped_error<ntstatus_error::tag>,std::vector<uchar,wil::secure_allocator<uchar>>,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil>(errorlib::scoped_error<ntstatus_error::tag> &,std::vector<uchar,wil::secure_allocator<uchar>> &&)
0x1800387b2  nop
0x1800387b3  jmp     short loc_1800387CC
0x1800387b5  call    ??0?$_Vector_val@EU?$secure_allocator@E@wil@@@std@@QEAA@U?$secure_allocator@E@wil@@@Z; std::_Vector_val<uchar,wil::secure_allocator<uchar>>::_Vector_val<uchar,wil::secure_allocator<uchar>>(wil::secure_allocator<uchar>)
0x1800387ba  nop
0x1800387bb  lea     r8, [rbp+57h+var_68]
0x1800387bf  lea     rdx, [rbp+57h+arg_10]
0x1800387c3  mov     rcx, r12
0x1800387c6  call    ??$?0AEAV?$scoped_error@Utag@ntstatus_error@@@errorlib@@V?$vector@EU?$secure_allocator@E@wil@@@std@@@?$tuple@V?$scoped_error@Utag@ntstatus_error@@@errorlib@@V?$vector@EU?$secure_allocator@E@wil@@@std@@U_Nil@tr1@4@U564@U564@U564@U564@U564@U564@U564@@tr1@std@@QEAA@AEAV?$scoped_error@Utag@ntstatus_error@@@errorlib@@$$QEAV?$vector@EU?$secure_allocator@E@wil@@@2@@Z; std::tr1::tuple<errorlib::scoped_error<ntstatus_error::tag>,std::vector<uchar,wil::secure_allocator<uchar>>,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil>::tuple<errorlib::scoped_error<ntstatus_error::tag>,std::vector<uchar,wil::secure_allocator<uchar>>,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil>(errorlib::scoped_error<ntstatus_error::tag> &,std::vector<uchar,wil::secure_allocator<uchar>> &&)
0x1800387cb  nop
0x1800387cc  lea     rcx, [rbp+57h+var_68]
0x1800387d0  call    ?_Tidy@?$vector@EU?$secure_allocator@E@wil@@@std@@IEAAXXZ; std::vector<uchar,wil::secure_allocator<uchar>>::_Tidy(void)
0x1800387d5  nop
0x1800387d6  lea     rcx, [rbp+57h+var_48]
0x1800387da  call    ?_Tidy@?$vector@EU?$secure_allocator@E@wil@@@std@@IEAAXXZ; std::vector<uchar,wil::secure_allocator<uchar>>::_Tidy(void)
0x1800387df  nop
0x1800387e0  lea     rcx, [rbp+57h+arg_10]
0x1800387e4  call    ??1?$scoped_error@Utag@winerror_error@@@errorlib@@QEAA@XZ; errorlib::scoped_error<winerror_error::tag>::~scoped_error<winerror_error::tag>(void)
0x1800387e9  mov     rax, r12
0x1800387ec  mov     rbx, [rsp+0D0h+arg_0]
0x1800387f4  add     rsp, 0B0h
0x1800387fb  pop     r15
0x1800387fd  pop     r12
0x1800387ff  pop     rdi
0x180038800  pop     rsi
0x180038801  pop     rbp
0x180038802  retn
```
