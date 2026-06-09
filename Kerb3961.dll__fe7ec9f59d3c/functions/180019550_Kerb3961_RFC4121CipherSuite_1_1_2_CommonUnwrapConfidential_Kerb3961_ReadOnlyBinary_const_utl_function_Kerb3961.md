# Kerb3961::RFC4121CipherSuite<1,1,2>::CommonUnwrapConfidential(Kerb3961::ReadOnlyBinary const &,utl::function<Kerb3961::ReturnType<Kerb3961::OwnedBinary,&Kerb3961::SingleGetter<Kerb3961::OwnedBinary,16>(Kerb3961::OwnedBinary const &),&Kerb3961::SingleSetter<Kerb3961::OwnedBinary,16>(Kerb3961::OwnedBinary &)> (Kerb3961::ReadOnlyBinary const &)> const &,Kerb3961::ReadOnlyBinary const &)

- ea: `0x180019550`
- end: `0x18001993f`
- name: `?CommonUnwrapConfidential@?$RFC4121CipherSuite@$00$00$01@Kerb3961@@AEAA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@2@AEBUReadOnlyBinary@2@AEBV?$function@$$A6A?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@Kerb3961@@AEBUReadOnlyBinary@2@@Z@utl@@0@Z`
- size: `1007`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180019250`

## callees

- `0x180001d40`
- `0x180001d64`
- `0x180002c34`
- `0x180002c4c`
- `0x180002c64`
- `0x180002fc0`
- `0x180004750`
- `0x1800047e4`
- `0x180006ee0`
- `0x180010124`
- `0x180019550`
- `0x18001e010`

## pseudocode

```c
__int64 __fastcall Kerb3961::RFC4121CipherSuite<1,1,2>::CommonUnwrapConfidential(
        __int64 a1,
        __int64 a2,
        __int64 *a3,
        __int64 a4,
        __int64 a5)
{
  __int64 v5; // rax
  __int16 v10; // r14
  unsigned __int16 v11; // dx
  unsigned __int64 v12; // rcx
  int v13; // edi
  __int64 *v14; // rdx
  __int64 v15; // r14
  char v16; // di
  int v17; // r8d
  int v18; // esi
  int v19; // r8d
  int v20; // esi
  signed __int64 v21; // r13
  char *v22; // r14
  const char *v23; // rdx
  __int64 v24; // rsi
  int v25; // r8d
  void *v26; // rax
  int v27; // esi
  char *v28; // rcx
  unsigned __int64 v29; // rsi
  char v30; // r8
  __int64 v31; // rax
  unsigned __int64 v33; // [rsp+40h] [rbp-C0h] BYREF
  void *v34; // [rsp+48h] [rbp-B8h]
  char *v35; // [rsp+50h] [rbp-B0h]
  char *v36[2]; // [rsp+58h] [rbp-A8h] BYREF
  char *v37; // [rsp+68h] [rbp-98h]
  unsigned __int64 v38; // [rsp+70h] [rbp-90h] BYREF
  void *v39; // [rsp+78h] [rbp-88h]
  int v40; // [rsp+80h] [rbp-80h]
  char *v41[2]; // [rsp+88h] [rbp-78h] BYREF
  char *v42; // [rsp+98h] [rbp-68h]
  unsigned __int64 v43; // [rsp+A0h] [rbp-60h] BYREF
  void *v44; // [rsp+A8h] [rbp-58h]
  char *v45; // [rsp+B0h] [rbp-50h]
  __int64 v46; // [rsp+C0h] [rbp-40h]
  unsigned __int64 v47; // [rsp+C8h] [rbp-38h]
  unsigned __int64 v48; // [rsp+D0h] [rbp-30h]
  _QWORD v49[2]; // [rsp+E0h] [rbp-20h] BYREF
  char v50[16]; // [rsp+F0h] [rbp-10h] BYREF
  _BYTE v51[16]; // [rsp+100h] [rbp+0h] BYREF
  char v52[16]; // [rsp+110h] [rbp+10h] BYREF
  _QWORD v53[2]; // [rsp+120h] [rbp+20h] BYREF

  v5 = a3[1];
  v10 = *(_WORD *)(v5 + 6);
  v38 = 0;
  v39 = 0;
  v40 = -1073741823;
  if ( v10 )
  {
    v11 = __ROR2__(*(_WORD *)(v5 + 6), 8);
    if ( v11 == 28 && *(_WORD *)(v5 + 4) )
      v11 = __ROR2__(*(_WORD *)(v5 + 4), 8) + 28;
    v12 = *a3 - 16;
    v46 = 16;
    v47 = v11 % v12;
    v48 = v12 - v47;
    Kerb3961::Split<3>((Kerb3961::ReadOnlyBinary *)v51);
    Kerb3961::Concatenate(&v43, v51, v53, v52);
    v13 = (int)v45;
    v38 = v43;
    v39 = v44;
    v40 = (int)v45;
    if ( (int)v45 < 0 )
    {
      Kerb3961::Logging::Verify::StatusFailed(
        (Kerb3961::Logging::Verify *)"unrotatedBuffer",
        (const char *)(unsigned int)v45,
        0);
      *(_QWORD *)a2 = 0;
      *(_QWORD *)(a2 + 8) = 0;
      *(_DWORD *)(a2 + 16) = v13;
      goto LABEL_37;
    }
    *((_WORD *)v44 + 3) = 0;
  }
  v46 = 16;
  v14 = (__int64 *)&v38;
  if ( !v10 )
    v14 = a3;
  v15 = v14[1];
  v47 = *v14 - 16;
  Kerb3961::Split<2>((Kerb3961::ReadOnlyBinary *)v49);
  v16 = 1;
  (*(void (__fastcall **)(__int64, char **, __int64, __int64, int))(*(_QWORD *)a1 + 168LL))(
    a1,
    v36,
    a5,
    2LL * ((*(_BYTE *)(v15 + 2) & 1) == 0) + 22,
    1);
  v18 = (int)v37;
  if ( (int)v37 >= 0 )
  {
    (*(void (__fastcall **)(__int64, char **, char **, _QWORD))(*(_QWORD *)a1 + 184LL))(a1, v41, v36, 0);
    v20 = (int)v42;
    if ( (int)v42 < 0 )
    {
      Kerb3961::Logging::Verify::StatusFailed(
        (Kerb3961::Logging::Verify *)"state",
        (const char *)(unsigned int)v42,
        v19);
      *(_QWORD *)a2 = 0;
      *(_QWORD *)(a2 + 8) = 0;
      *(_DWORD *)(a2 + 16) = v20;
      goto LABEL_33;
    }
    v21 = (unsigned __int16)__ROR2__(*(_WORD *)(v15 + 4), 8);
    v33 = 0;
    v34 = 0;
    LODWORD(v35) = 0;
    v22 = (char *)(v21 + 16);
    v24 = (*(__int64 (__fastcall **)(__int64, unsigned __int64 *, char **, char **, char *, __int64, signed __int64))(*(_QWORD *)a1 + 376LL))(
            a1,
            &v43,
            v36,
            v41,
            v50,
            a4,
            v21 + 16);
    v33 = *(_QWORD *)v24;
    v26 = *(void **)(v24 + 8);
    *(_QWORD *)v24 = 0;
    v34 = v26;
    LODWORD(v26) = *(_DWORD *)(v24 + 16);
    *(_QWORD *)(v24 + 8) = 0;
    LODWORD(v35) = (_DWORD)v26;
    *(_DWORD *)(v24 + 16) = -1073741823;
    if ( v44 )
      operator delete(v44, 0);
    v27 = (int)v35;
    if ( (int)v35 >= 0 )
    {
      if ( v33 >= (unsigned __int64)v22 )
      {
        v29 = v33 - (_QWORD)v22;
        v44 = (void *)v21;
        v43 = v33 - (_QWORD)v22;
        v45 = (char *)16;
        Kerb3961::Split<3>(v51, &v33, &v43);
        if ( v49[0] != v53[0] )
          goto LABEL_29;
        if ( v49[0] )
        {
          if ( v49[0] > 0xFFFFFFFF )
            goto LABEL_29;
          v30 = 0;
          LODWORD(v23) = 0;
          do
          {
            v31 = (unsigned int)v23;
            v23 = (const char *)(unsigned int)((_DWORD)v23 + 1);
            v30 |= *(_BYTE *)(v49[1] + v31) ^ *(_BYTE *)(v53[1] + v31);
          }
          while ( (unsigned int)v23 < LODWORD(v49[0]) );
          if ( v30 )
LABEL_29:
            v16 = 0;
        }
        if ( v16 )
        {
          *(_DWORD *)(a2 + 16) = (_DWORD)v35;
          *(_QWORD *)(a2 + 8) = v34;
          LODWORD(v35) = -1073741823;
          *(_QWORD *)a2 = v29;
          v33 = 0;
          v34 = 0;
LABEL_33:
          if ( v41[1] )
             Kerb3961::EncryptionAlgorithm::`vcall'{176,{flat}}(v41[0]);
          goto LABEL_35;
        }
        v28 = "SecureEqualBuffer(headerBuffer, decryptedHeader)";
      }
      else
      {
        v28 = "decryption.length >= trailerSize";
      }
      Kerb3961::Logging::Verify::ConditionFailed((Kerb3961::Logging::Verify *)v28, v23);
      *(_QWORD *)a2 = 0;
      *(_QWORD *)(a2 + 8) = 0;
      *(_DWORD *)(a2 + 16) = -2146893041;
    }
    else
    {
      Kerb3961::Logging::Verify::StatusFailed(
        (Kerb3961::Logging::Verify *)"decryption",
        (const char *)(unsigned int)v35,
        v25);
      *(_QWORD *)a2 = 0;
      *(_QWORD *)(a2 + 8) = 0;
      *(_DWORD *)(a2 + 16) = v27;
    }
    if ( v34 )
      operator delete(v34, 0);
    goto LABEL_33;
  }
  Kerb3961::Logging::Verify::StatusFailed(
    (Kerb3961::Logging::Verify *)"specificKey",
    (const char *)(unsigned int)v37,
    v17);
  *(_QWORD *)a2 = 0;
  *(_QWORD *)(a2 + 8) = 0;
  *(_DWORD *)(a2 + 16) = v18;
LABEL_35:
  if ( v36[1] )
     Kerb3961::EncryptionAlgorithm::`vcall'{160,{flat}}(v36[0]);
LABEL_37:
  if ( v39 )
    operator delete(v39, 0);
  return a2;
}

```

## disassembly

```asm
0x180019550  push    rbp
0x180019552  push    rbx
0x180019553  push    rsi
0x180019554  push    rdi
0x180019555  push    r12
0x180019557  push    r13
0x180019559  push    r14
0x18001955b  push    r15
0x18001955d  lea     rbp, [rsp-48h]
0x180019562  sub     rsp, 148h
0x180019569  mov     rax, cs:__security_cookie
0x180019570  xor     rax, rsp
0x180019573  mov     [rbp+80h+var_50], rax
0x180019577  mov     rax, [r8+8]
0x18001957b  mov     rsi, r8
0x18001957e  mov     r13, [rbp+80h+arg_20]
0x180019585  xor     r8d, r8d
0x180019588  mov     r12, r9
0x18001958b  mov     rbx, rdx
0x18001958e  mov     r15, rcx
0x180019591  movzx   r14d, word ptr [rax+6]
0x180019596  mov     [rsp+180h+var_110], r8
0x18001959b  mov     [rsp+180h+var_108], r8
0x1800195a0  mov     [rbp+80h+var_100], 0C0000001h
0x1800195a7  test    r14w, r14w
0x1800195ab  jz      loc_180019671
0x1800195b1  movzx   edx, word ptr [rax+6]
0x1800195b5  ror     dx, 8
0x1800195b9  cmp     dx, 1Ch
0x1800195bd  jnz     short loc_1800195D2
0x1800195bf  cmp     [rax+4], r8w
0x1800195c4  jz      short loc_1800195D2
0x1800195c6  movzx   edx, word ptr [rax+4]
0x1800195ca  ror     dx, 8
0x1800195ce  add     dx, 1Ch
0x1800195d2  mov     rcx, [rsi]
0x1800195d5  lea     r8, [rbp+80h+var_C0]
0x1800195d9  movzx   eax, dx
0x1800195dc  add     rcx, 0FFFFFFFFFFFFFFF0h
0x1800195e0  xor     edx, edx
0x1800195e2  mov     [rbp+80h+var_C0], 10h
0x1800195ea  div     rcx
0x1800195ed  sub     rcx, rdx
0x1800195f0  mov     [rbp+80h+var_B8], rdx
0x1800195f4  mov     [rbp+80h+var_B0], rcx
0x1800195f8  mov     rdx, rsi
0x1800195fb  lea     rcx, [rbp+80h+var_80]; this
0x1800195ff  call    ??$Split@$02@Kerb3961@@YA?BU?$array@$$CBUReadOnlyBinary@Kerb3961@@$02@utl@@AEBUReadOnlyBinary@0@U?$array@_K$02@2@@Z; Kerb3961::Split<3>(Kerb3961::ReadOnlyBinary const &,utl::array<unsigned __int64,3>)
0x180019604  lea     r9, [rbp+80h+var_70]
0x180019608  lea     r8, [rbp+80h+var_60]
0x18001960c  lea     rdx, [rbp+80h+var_80]
0x180019610  lea     rcx, [rbp+80h+var_E0]
0x180019614  call    ?Concatenate@Kerb3961@@YA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@1@AEBUReadOnlyBinary@1@00@Z; Kerb3961::Concatenate(Kerb3961::ReadOnlyBinary const &,Kerb3961::ReadOnlyBinary const &,Kerb3961::ReadOnlyBinary const &)
0x180019619  mov     rcx, [rsp+180h+var_108]; void *
0x18001961e  xor     r8d, r8d
0x180019621  test    rcx, rcx
0x180019624  jz      short loc_180019630
0x180019626  xor     edx, edx; struct std::nothrow_t *
0x180019628  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18001962d  xor     r8d, r8d; int
0x180019630  mov     rdi, [rbp+80h+var_D0]
0x180019634  mov     rax, [rbp+80h+var_E0]
0x180019638  mov     rcx, [rbp+80h+var_D8]
0x18001963c  mov     [rsp+180h+var_110], rax
0x180019641  mov     [rsp+180h+var_108], rcx
0x180019646  mov     [rbp+80h+var_100], edi
0x180019649  test    edi, edi
0x18001964b  jns     short loc_18001966C
0x18001964d  mov     edx, edi; char *
0x18001964f  lea     rcx, aUnrotatedbuffe; "unrotatedBuffer"
0x180019656  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x18001965b  xor     eax, eax
0x18001965d  mov     [rbx], rax
0x180019660  mov     [rbx+8], rax
0x180019664  mov     [rbx+10h], edi
0x180019667  jmp     loc_18001990B
0x18001966c  mov     [rcx+6], r8w
0x180019671  test    r14w, r14w
0x180019675  mov     [rbp+80h+var_C0], 10h
0x18001967d  lea     rdx, [rsp+180h+var_110]
0x180019682  cmovz   rdx, rsi
0x180019686  lea     r8, [rbp+80h+var_C0]
0x18001968a  lea     rcx, [rbp+80h+var_A0]; this
0x18001968e  mov     rax, [rdx]
0x180019691  mov     r14, [rdx+8]
0x180019695  sub     rax, 10h
0x180019699  mov     [rbp+80h+var_B8], rax
0x18001969d  call    ??$Split@$01@Kerb3961@@YA?BU?$array@$$CBUReadOnlyBinary@Kerb3961@@$01@utl@@AEBUReadOnlyBinary@0@U?$array@_K$01@2@@Z; Kerb3961::Split<2>(Kerb3961::ReadOnlyBinary const &,utl::array<unsigned __int64,2>)
0x1800196a2  mov     r9b, [r14+2]
0x1800196a6  lea     rdx, [rsp+180h+var_128]
0x1800196ab  mov     rax, [r15]
0x1800196ae  not     r9b
0x1800196b1  mov     edi, 1
0x1800196b6  mov     r8, r13
0x1800196b9  and     r9, rdi
0x1800196bc  mov     dword ptr [rsp+180h+var_160], edi
0x1800196c0  mov     rcx, r15
0x1800196c3  mov     rax, [rax+0A8h]
0x1800196ca  lea     r9, ds:16h[r9*2]
0x1800196d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800196d7  mov     esi, dword ptr [rsp+180h+var_118]
0x1800196db  xor     r13d, r13d
0x1800196de  test    esi, esi
0x1800196e0  jns     short loc_1800196FF
0x1800196e2  mov     edx, esi; char *
0x1800196e4  lea     rcx, aSpecifickey; "specificKey"
0x1800196eb  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x1800196f0  mov     [rbx], r13
0x1800196f3  mov     [rbx+8], r13
0x1800196f7  mov     [rbx+10h], esi
0x1800196fa  jmp     loc_1800198F7
0x1800196ff  mov     rax, [r15]
0x180019702  lea     r8, [rsp+180h+var_128]
0x180019707  xor     r9d, r9d
0x18001970a  lea     rdx, [rbp+80h+var_F8]
0x18001970e  mov     rcx, r15
0x180019711  mov     rax, [rax+0B8h]
0x180019718  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001971d  mov     esi, dword ptr [rbp+80h+var_E8]
0x180019720  test    esi, esi
0x180019722  jns     short loc_180019741
0x180019724  mov     edx, esi; char *
0x180019726  lea     rcx, aState; "state"
0x18001972d  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x180019732  mov     [rbx], r13
0x180019735  mov     [rbx+8], r13
0x180019739  mov     [rbx+10h], esi
0x18001973c  jmp     loc_1800198E5
0x180019741  movzx   eax, word ptr [r14+4]
0x180019746  lea     rcx, [rbp+80h+var_90]
0x18001974a  ror     ax, 8
0x18001974e  lea     r9, [rbp+80h+var_F8]
0x180019752  movzx   r13d, ax
0x180019756  lea     r8, [rsp+180h+var_128]
0x18001975b  xor     eax, eax
0x18001975d  lea     rdx, [rbp+80h+var_E0]
0x180019761  mov     [rsp+180h+var_140], rax
0x180019766  mov     [rsp+180h+var_138], rax
0x18001976b  mov     dword ptr [rsp+180h+var_130], eax
0x18001976f  lea     r14, [r13+10h]
0x180019773  mov     rax, [r15]
0x180019776  mov     [rsp+180h+var_150], r14
0x18001977b  mov     [rsp+180h+var_158], r12
0x180019780  mov     [rsp+180h+var_160], rcx
0x180019785  mov     rcx, r15
0x180019788  mov     rax, [rax+178h]
0x18001978f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019794  mov     rcx, [rsp+180h+var_138]; void *
0x180019799  xor     r15d, r15d
0x18001979c  mov     rsi, rax
0x18001979f  test    rcx, rcx
0x1800197a2  jz      short loc_1800197AB
0x1800197a4  xor     edx, edx; struct std::nothrow_t *
0x1800197a6  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800197ab  mov     rax, [rsi]
0x1800197ae  mov     r12d, 0C0000001h
0x1800197b4  mov     [rsp+180h+var_140], rax
0x1800197b9  mov     rax, [rsi+8]
0x1800197bd  mov     [rsi], r15
0x1800197c0  mov     [rsp+180h+var_138], rax
0x1800197c5  mov     eax, [rsi+10h]
0x1800197c8  mov     [rsi+8], r15
0x1800197cc  mov     dword ptr [rsp+180h+var_130], eax
0x1800197d0  mov     [rsi+10h], r12d
0x1800197d4  mov     rcx, [rbp+80h+var_D8]; void *
0x1800197d8  test    rcx, rcx
0x1800197db  jz      short loc_1800197E4
0x1800197dd  xor     edx, edx; struct std::nothrow_t *
0x1800197df  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800197e4  mov     esi, dword ptr [rsp+180h+var_130]
0x1800197e8  test    esi, esi
0x1800197ea  jns     short loc_18001981E
0x1800197ec  mov     edx, esi; char *
0x1800197ee  lea     rcx, aDecryption; "decryption"
0x1800197f5  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x1800197fa  mov     [rbx], r15
0x1800197fd  mov     [rbx+8], r15
0x180019801  mov     [rbx+10h], esi
0x180019804  mov     rcx, [rsp+180h+var_138]; void *
0x180019809  test    rcx, rcx
0x18001980c  jz      loc_1800198E5
0x180019812  xor     edx, edx; struct std::nothrow_t *
0x180019814  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180019819  jmp     loc_1800198E5
0x18001981e  mov     rsi, [rsp+180h+var_140]
0x180019823  cmp     rsi, r14
0x180019826  jnb     short loc_180019844
0x180019828  lea     rcx, aDecryptionLeng; "decryption.length >= trailerSize"
0x18001982f  call    ?ConditionFailed@Verify@Logging@Kerb3961@@YAXPEBD@Z; Kerb3961::Logging::Verify::ConditionFailed(char const *)
0x180019834  mov     [rbx], r15
0x180019837  mov     [rbx+8], r15
0x18001983b  mov     dword ptr [rbx+10h], 8009030Fh
0x180019842  jmp     short loc_180019804
0x180019844  sub     rsi, r14
0x180019847  mov     [rbp+80h+var_D8], r13
0x18001984b  lea     r8, [rbp+80h+var_E0]
0x18001984f  mov     [rbp+80h+var_E0], rsi
0x180019853  lea     rdx, [rsp+180h+var_140]
0x180019858  mov     [rbp+80h+var_D0], 10h
0x180019860  lea     rcx, [rbp+80h+var_80]
0x180019864  call    ??$Split@$02@Kerb3961@@YA?AU?$array@$$CBUMutableBinary@Kerb3961@@$02@utl@@AEBUMutableBinary@0@U?$array@_K$02@2@@Z; Kerb3961::Split<3>(Kerb3961::MutableBinary const &,utl::array<unsigned __int64,3>)
0x180019869  mov     rax, [rbp+80h+var_A0]
0x18001986d  cmp     rax, [rbp+80h+var_60]
0x180019871  jnz     short loc_1800198AF
0x180019873  test    rax, rax
0x180019876  jz      short loc_1800198B2
0x180019878  mov     ecx, 0FFFFFFFFh
0x18001987d  cmp     rax, rcx
0x180019880  ja      short loc_1800198AF
0x180019882  mov     r9, [rbp+80h+var_98]
0x180019886  mov     r8b, r15b
0x180019889  mov     r10, [rbp+80h+var_58]
0x18001988d  mov     edx, r15d
0x180019890  test    eax, eax
0x180019892  jz      short loc_1800198B2
0x180019894  mov     eax, edx
0x180019896  add     edx, edi
0x180019898  mov     cl, [r10+rax]
0x18001989c  mov     al, [r9+rax]
0x1800198a0  xor     cl, al
0x1800198a2  or      r8b, cl
0x1800198a5  cmp     edx, dword ptr [rbp+80h+var_A0]
0x1800198a8  jb      short loc_180019894
0x1800198aa  test    r8b, r8b
0x1800198ad  jz      short loc_1800198B2
0x1800198af  mov     dil, r15b
0x1800198b2  test    dil, dil
0x1800198b5  jnz     short loc_1800198C3
0x1800198b7  lea     rcx, aSecureequalbuf_4; "SecureEqualBuffer(headerBuffer, decrypt"...
0x1800198be  jmp     loc_18001982F
0x1800198c3  mov     eax, dword ptr [rsp+180h+var_130]
0x1800198c7  mov     [rbx+10h], eax
0x1800198ca  mov     rax, [rsp+180h+var_138]
0x1800198cf  mov     [rbx+8], rax
0x1800198d3  mov     dword ptr [rsp+180h+var_130], r12d
0x1800198d8  mov     [rbx], rsi
0x1800198db  mov     [rsp+180h+var_140], r15
0x1800198e0  mov     [rsp+180h+var_138], r15
0x1800198e5  mov     rdx, [rbp+80h+var_F0]
0x1800198e9  test    rdx, rdx
0x1800198ec  jz      short loc_1800198F7
0x1800198ee  mov     rcx, [rbp+80h+var_F8]
0x1800198f2  call    ??_9EncryptionAlgorithm@Kerb3961@@$BLA@AA; [thunk]: Kerb3961::EncryptionAlgorithm::`vcall'{176,{flat}}
0x1800198f7  mov     rdx, [rsp+180h+var_120]
0x1800198fc  test    rdx, rdx
0x1800198ff  jz      short loc_18001990B
0x180019901  mov     rcx, [rsp+180h+var_128]
0x180019906  call    ??_9EncryptionAlgorithm@Kerb3961@@$BKA@AA; [thunk]: Kerb3961::EncryptionAlgorithm::`vcall'{160,{flat}}
0x18001990b  mov     rcx, [rsp+180h+var_108]; void *
0x180019910  test    rcx, rcx
0x180019913  jz      short loc_18001991C
0x180019915  xor     edx, edx; struct std::nothrow_t *
0x180019917  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18001991c  mov     rax, rbx
0x18001991f  mov     rcx, [rbp+80h+var_50]
0x180019923  xor     rcx, rsp; StackCookie
0x180019926  call    __security_check_cookie
0x18001992b  add     rsp, 148h
0x180019932  pop     r15
0x180019934  pop     r14
0x180019936  pop     r13
0x180019938  pop     r12
0x18001993a  pop     rdi
0x18001993b  pop     rsi
0x18001993c  pop     rbx
0x18001993d  pop     rbp
0x18001993e  retn
```
