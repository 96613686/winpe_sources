# Kerb3961::RFC4121CipherSuite<1,1,2>::CommonWrapEncrypted(Kerb3961::MutableBinary const &,Kerb3961::ReadOnlyBinary const &,unsigned __int64,uint,Kerb3961::ReadOnlyBinary const &,bool,bool,unsigned __int64 *)

- ea: `0x180019950`
- end: `0x180019c9c`
- name: `?CommonWrapEncrypted@?$RFC4121CipherSuite@$00$00$01@Kerb3961@@EEAA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@2@AEBUMutableBinary@2@AEBUReadOnlyBinary@2@_KI1_N3PEA_K@Z`
- size: `844`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180001d64`
- `0x180002c34`
- `0x180002c4c`
- `0x180002c64`
- `0x180002fc0`
- `0x180004118`
- `0x1800101b8`
- `0x180019950`
- `0x18001d360`
- `0x18001e010`

## pseudocode

```c
__int64 __fastcall Kerb3961::RFC4121CipherSuite<1,1,2>::CommonWrapEncrypted(
        __int64 *a1,
        __int64 a2,
        void **a3,
        _QWORD *a4,
        unsigned __int64 a5,
        int a6,
        __int64 a7,
        unsigned __int8 a8,
        char a9,
        __int64 *a10)
{
  __int64 v14; // rax
  __int64 v15; // r15
  __int16 v16; // ax
  char v17; // al
  int v18; // r8d
  __int64 v19; // r9
  int v20; // ebx
  int v21; // r8d
  int v22; // ebx
  __int64 v23; // rax
  __int64 (__fastcall *v24)(__int64 *, __int64 *, char **, char **, void **, _QWORD *, __int64 *); // rax
  __int64 v25; // rbx
  int v26; // r8d
  void *v27; // rcx
  int v28; // eax
  int v29; // ebx
  __int64 v30; // rax
  __int64 v31; // r9
  __int64 v33; // [rsp+40h] [rbp-C0h] BYREF
  void *v34; // [rsp+48h] [rbp-B8h]
  char *v35; // [rsp+50h] [rbp-B0h]
  char *v36[2]; // [rsp+58h] [rbp-A8h] BYREF
  char *v37; // [rsp+68h] [rbp-98h]
  __int16 v38; // [rsp+70h] [rbp-90h] BYREF
  char v39; // [rsp+72h] [rbp-8Eh]
  char v40; // [rsp+73h] [rbp-8Dh]
  __int16 v41; // [rsp+74h] [rbp-8Ch]
  __int16 v42; // [rsp+76h] [rbp-8Ah]
  unsigned __int64 v43; // [rsp+78h] [rbp-88h]
  char *v44[2]; // [rsp+88h] [rbp-78h] BYREF
  char *v45; // [rsp+98h] [rbp-68h]
  __int64 v46; // [rsp+A0h] [rbp-60h] BYREF
  __int16 *v47; // [rsp+A8h] [rbp-58h]
  __int64 v48; // [rsp+B0h] [rbp-50h] BYREF
  void *v49; // [rsp+B8h] [rbp-48h]
  __int128 v50; // [rsp+C0h] [rbp-40h]
  __int128 v51; // [rsp+D0h] [rbp-30h]
  __int128 v52; // [rsp+E0h] [rbp-20h]
  __int128 v53; // [rsp+F0h] [rbp-10h] BYREF
  void *Src; // [rsp+108h] [rbp+8h]
  __int128 v55; // [rsp+110h] [rbp+10h]
  __int128 v56; // [rsp+120h] [rbp+20h]

  if ( a6 )
  {
    Kerb3961::Logging::Verify::ConditionFailed((Kerb3961::Logging::Verify *)"QOP == 0", (const char *)a2);
    *(_QWORD *)a2 = 0;
    *(_QWORD *)(a2 + 8) = 0;
    *(_DWORD *)(a2 + 16) = -1073741811;
  }
  else
  {
    v14 = (*(__int64 (__fastcall **)(__int64 *, __int64))(*a1 + 384))(a1, (__int64)*a3 + 16);
    v15 = v14;
    if ( a10 )
      *a10 = v14;
    v40 = -1;
    v38 = 1029;
    v42 = 0;
    if ( *a4 || !*a3 )
      v16 = 4096;
    else
      v16 = __ROR2__(v14, 8);
    v41 = v16;
    v43 = _byteswap_uint64(a5);
    v17 = 2;
    if ( !a8 )
      v17 = 3;
    v39 = v17;
    if ( a9 )
      v39 = v17 | 4;
    v46 = 16;
    v47 = &v38;
    (*(void (__fastcall **)(__int64 *, char **, __int64, __int64, int))(*a1 + 168))(a1, v36, a7, 2LL * a8 + 22, 1);
    v20 = (int)v37;
    if ( (int)v37 >= 0 )
    {
      LOBYTE(v19) = 1;
      (*(void (__fastcall **)(__int64 *, char **, char **, __int64))(*a1 + 184))(a1, v44, v36, v19);
      v22 = (int)v45;
      if ( (int)v45 >= 0 )
      {
        v23 = *a1;
        v33 = 0;
        v24 = *(__int64 (__fastcall **)(__int64 *, __int64 *, char **, char **, void **, _QWORD *, __int64 *))(v23 + 368);
        v34 = 0;
        LODWORD(v35) = -1073741823;
        v25 = v24(a1, &v48, v36, v44, a3, a4, &v46);
        v33 = *(_QWORD *)v25;
        v27 = *(void **)(v25 + 8);
        *(_QWORD *)v25 = 0;
        v34 = v27;
        v28 = *(_DWORD *)(v25 + 16);
        *(_QWORD *)(v25 + 8) = 0;
        LODWORD(v35) = v28;
        *(_DWORD *)(v25 + 16) = -1073741823;
        if ( v49 )
          operator delete(v49, 0);
        v29 = (int)v35;
        if ( (int)v35 >= 0 )
        {
          v30 = (*(__int64 (__fastcall **)(__int64 *))(*a1 + 392))(a1);
          v31 = v33 - (_QWORD)*a3;
          v49 = *a3;
          v48 = v30;
          *(_QWORD *)&v50 = v15 & -(__int64)(a10 != 0);
          *((_QWORD *)&v50 + 1) = v31 - v30 - v50;
          v42 = __ROR2__(WORD4(v50), 8);
          Kerb3961::Split<4>(&v53, &v33, &v48);
          memcpy_0(a3[1], Src, (size_t)*a3);
          v49 = v47;
          v48 = v46;
          v50 = v56;
          v51 = v53;
          v52 = v55;
          Kerb3961::Concatenate<4>(a2, &v48);
        }
        else
        {
          Kerb3961::Logging::Verify::StatusFailed(
            (Kerb3961::Logging::Verify *)"encryption",
            (const char *)(unsigned int)v35,
            v26);
          *(_QWORD *)a2 = 0;
          *(_QWORD *)(a2 + 8) = 0;
          *(_DWORD *)(a2 + 16) = v29;
        }
        if ( v34 )
          operator delete(v34, 0);
      }
      else
      {
        Kerb3961::Logging::Verify::StatusFailed(
          (Kerb3961::Logging::Verify *)"state",
          (const char *)(unsigned int)v45,
          v21);
        *(_QWORD *)a2 = 0;
        *(_QWORD *)(a2 + 8) = 0;
        *(_DWORD *)(a2 + 16) = v22;
      }
      if ( v44[1] )
         Kerb3961::EncryptionAlgorithm::`vcall'{176,{flat}}(v44[0]);
    }
    else
    {
      Kerb3961::Logging::Verify::StatusFailed(
        (Kerb3961::Logging::Verify *)"specificKey",
        (const char *)(unsigned int)v37,
        v18);
      *(_QWORD *)a2 = 0;
      *(_QWORD *)(a2 + 8) = 0;
      *(_DWORD *)(a2 + 16) = v20;
    }
    if ( v36[1] )
       Kerb3961::EncryptionAlgorithm::`vcall'{160,{flat}}(v36[0]);
  }
  return a2;
}

```

## disassembly

```asm
0x180019950  push    rbp
0x180019952  push    rbx
0x180019953  push    rsi
0x180019954  push    rdi
0x180019955  push    r12
0x180019957  push    r13
0x180019959  push    r14
0x18001995b  push    r15
0x18001995d  lea     rbp, [rsp-38h]
0x180019962  sub     rsp, 138h
0x180019969  mov     rbx, [rbp+70h+arg_30]
0x180019970  xor     r15d, r15d
0x180019973  mov     r13, r9
0x180019976  mov     r12, [rbp+70h+arg_48]
0x18001997d  mov     r14, r8
0x180019980  mov     rdi, rdx
0x180019983  mov     rsi, rcx
0x180019986  cmp     [rbp+70h+arg_28], r15d
0x18001998d  jz      short loc_1800199AE
0x18001998f  lea     rcx, aQop0; "QOP == 0"
0x180019996  call    ?ConditionFailed@Verify@Logging@Kerb3961@@YAXPEBD@Z; Kerb3961::Logging::Verify::ConditionFailed(char const *)
0x18001999b  mov     [rdi], r15
0x18001999e  mov     [rdi+8], r15
0x1800199a2  mov     dword ptr [rdi+10h], 0C000000Dh
0x1800199a9  jmp     loc_180019C85
0x1800199ae  mov     rax, [rcx]
0x1800199b1  mov     rdx, [r8]
0x1800199b4  add     rdx, 10h
0x1800199b8  mov     rax, [rax+180h]
0x1800199bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800199c4  xor     r8d, r8d
0x1800199c7  mov     r15, rax
0x1800199ca  test    r12, r12
0x1800199cd  jz      short loc_1800199D3
0x1800199cf  mov     [r12], rax
0x1800199d3  mov     eax, 405h
0x1800199d8  mov     [rsp+170h+var_FD], 0FFh
0x1800199dd  mov     [rsp+170h+var_100], ax
0x1800199e2  mov     [rsp+170h+var_FA], r8w
0x1800199e8  cmp     [r13+0], r8
0x1800199ec  jnz     short loc_1800199FD
0x1800199ee  cmp     [r14], r8
0x1800199f1  jz      short loc_1800199FD
0x1800199f3  movzx   eax, r15w
0x1800199f7  ror     ax, 8
0x1800199fb  jmp     short loc_180019A02
0x1800199fd  mov     eax, 1000h
0x180019a02  movzx   ecx, [rbp+70h+arg_38]
0x180019a09  mov     edx, 3
0x180019a0e  mov     [rsp+170h+var_FC], ax
0x180019a13  test    cl, cl
0x180019a15  mov     rax, [rbp+70h+arg_20]
0x180019a1c  bswap   rax
0x180019a1f  mov     [rsp+170h+var_F8], rax
0x180019a24  mov     al, 2
0x180019a26  movzx   eax, al
0x180019a29  cmovz   eax, edx
0x180019a2c  mov     [rsp+170h+var_FE], al
0x180019a30  cmp     [rbp+70h+arg_40], r8b
0x180019a37  jz      short loc_180019A3F
0x180019a39  or      al, 4
0x180019a3b  mov     [rsp+170h+var_FE], al
0x180019a3f  lea     rax, [rsp+170h+var_100]
0x180019a44  mov     [rbp+70h+var_D0], 10h
0x180019a4c  mov     [rbp+70h+var_C8], rax
0x180019a50  lea     r9, ds:16h[rcx*2]
0x180019a58  mov     rax, [rsi]
0x180019a5b  lea     rdx, [rsp+170h+var_118]
0x180019a60  mov     r8, rbx
0x180019a63  mov     dword ptr [rsp+170h+var_150], 1
0x180019a6b  mov     rcx, rsi
0x180019a6e  mov     rax, [rax+0A8h]
0x180019a75  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019a7a  mov     ebx, dword ptr [rsp+170h+var_108]
0x180019a7e  test    ebx, ebx
0x180019a80  jns     short loc_180019AA7
0x180019a82  mov     edx, ebx; char *
0x180019a84  lea     rcx, aSpecifickey; "specificKey"
0x180019a8b  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x180019a90  mov     qword ptr [rdi], 0
0x180019a97  mov     qword ptr [rdi+8], 0
0x180019a9f  mov     [rdi+10h], ebx
0x180019aa2  jmp     loc_180019C71
0x180019aa7  mov     rax, [rsi]
0x180019aaa  lea     r8, [rsp+170h+var_118]
0x180019aaf  mov     r9b, 1
0x180019ab2  lea     rdx, [rbp+70h+var_E8]
0x180019ab6  mov     rcx, rsi
0x180019ab9  mov     rax, [rax+0B8h]
0x180019ac0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019ac5  mov     ebx, dword ptr [rbp+70h+var_D8]
0x180019ac8  test    ebx, ebx
0x180019aca  jns     short loc_180019AF1
0x180019acc  mov     edx, ebx; char *
0x180019ace  lea     rcx, aState; "state"
0x180019ad5  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x180019ada  mov     qword ptr [rdi], 0
0x180019ae1  mov     qword ptr [rdi+8], 0
0x180019ae9  mov     [rdi+10h], ebx
0x180019aec  jmp     loc_180019C5F
0x180019af1  mov     rax, [rsi]
0x180019af4  lea     rcx, [rbp+70h+var_D0]
0x180019af8  mov     [rsp+170h+var_140], rcx
0x180019afd  lea     r9, [rbp+70h+var_E8]
0x180019b01  mov     [rsp+170h+var_148], r13
0x180019b06  lea     r8, [rsp+170h+var_118]
0x180019b0b  lea     rdx, [rbp+70h+var_C0]
0x180019b0f  mov     [rsp+170h+var_130], 0
0x180019b18  mov     rax, [rax+170h]
0x180019b1f  mov     rcx, rsi
0x180019b22  mov     [rsp+170h+var_128], 0
0x180019b2b  mov     dword ptr [rsp+170h+var_120], 0C0000001h
0x180019b33  mov     [rsp+170h+var_150], r14
0x180019b38  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019b3d  mov     rcx, [rsp+170h+var_128]; void *
0x180019b42  xor     r13d, r13d
0x180019b45  mov     rbx, rax
0x180019b48  test    rcx, rcx
0x180019b4b  jz      short loc_180019B54
0x180019b4d  xor     edx, edx; struct std::nothrow_t *
0x180019b4f  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180019b54  mov     rcx, [rbx]
0x180019b57  mov     [rsp+170h+var_130], rcx
0x180019b5c  mov     rcx, [rbx+8]
0x180019b60  mov     [rbx], r13
0x180019b63  mov     [rsp+170h+var_128], rcx
0x180019b68  mov     eax, [rbx+10h]
0x180019b6b  mov     [rbx+8], r13
0x180019b6f  mov     dword ptr [rsp+170h+var_120], eax
0x180019b73  mov     dword ptr [rbx+10h], 0C0000001h
0x180019b7a  mov     rcx, [rbp+70h+var_B8]; void *
0x180019b7e  test    rcx, rcx
0x180019b81  jz      short loc_180019B8A
0x180019b83  xor     edx, edx; struct std::nothrow_t *
0x180019b85  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180019b8a  mov     ebx, dword ptr [rsp+170h+var_120]
0x180019b8e  test    ebx, ebx
0x180019b90  jns     short loc_180019BAF
0x180019b92  mov     edx, ebx; char *
0x180019b94  lea     rcx, aEncryption; "encryption"
0x180019b9b  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x180019ba0  mov     [rdi], r13
0x180019ba3  mov     [rdi+8], r13
0x180019ba7  mov     [rdi+10h], ebx
0x180019baa  jmp     loc_180019C4E
0x180019baf  mov     rax, [rsi]
0x180019bb2  neg     r12
0x180019bb5  mov     rcx, rsi
0x180019bb8  sbb     rbx, rbx
0x180019bbb  and     rbx, r15
0x180019bbe  mov     rax, [rax+188h]
0x180019bc5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019bca  mov     r8, [r14]
0x180019bcd  lea     rcx, [rbp+70h+var_80]
0x180019bd1  mov     r9, [rsp+170h+var_130]
0x180019bd6  sub     r9, r8
0x180019bd9  mov     [rbp+70h+var_B8], r8
0x180019bdd  sub     r9, rax
0x180019be0  mov     [rbp+70h+var_C0], rax
0x180019be4  sub     r9, rbx
0x180019be7  mov     qword ptr [rbp+70h+var_B0], rbx
0x180019beb  movzx   edx, r9w
0x180019bef  mov     qword ptr [rbp+70h+var_B0+8], r9
0x180019bf3  ror     dx, 8
0x180019bf7  lea     r8, [rbp+70h+var_C0]
0x180019bfb  mov     [rsp+170h+var_FA], dx
0x180019c00  lea     rdx, [rsp+170h+var_130]
0x180019c05  call    ??$Split@$03@Kerb3961@@YA?AU?$array@$$CBUMutableBinary@Kerb3961@@$03@utl@@AEBUMutableBinary@0@U?$array@_K$03@2@@Z; Kerb3961::Split<4>(Kerb3961::MutableBinary const &,utl::array<unsigned __int64,4>)
0x180019c0a  mov     r8, [r14]; Size
0x180019c0d  mov     rdx, [rbp+70h+Src]; Src
0x180019c11  mov     rcx, [r14+8]; void *
0x180019c15  call    memcpy_0
0x180019c1a  mov     rcx, [rbp+70h+var_C8]
0x180019c1e  lea     rdx, [rbp+70h+var_C0]
0x180019c22  mov     rax, [rbp+70h+var_D0]
0x180019c26  movaps  xmm0, [rbp+70h+var_50]
0x180019c2a  movaps  xmm1, [rbp+70h+var_80]
0x180019c2e  movaps  xmm2, [rbp+70h+var_60]
0x180019c32  mov     [rbp+70h+var_B8], rcx
0x180019c36  mov     rcx, rdi
0x180019c39  mov     [rbp+70h+var_C0], rax
0x180019c3d  movaps  [rbp+70h+var_B0], xmm0
0x180019c41  movaps  [rbp+70h+var_A0], xmm1
0x180019c45  movaps  [rbp+70h+var_90], xmm2
0x180019c49  call    ??$Concatenate@$03@Kerb3961@@YA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@0@U?$array@$$CBUReadOnlyBinary@Kerb3961@@$03@utl@@@Z; Kerb3961::Concatenate<4>(utl::array<Kerb3961::ReadOnlyBinary const,4>)
0x180019c4e  mov     rcx, [rsp+170h+var_128]; void *
0x180019c53  test    rcx, rcx
0x180019c56  jz      short loc_180019C5F
0x180019c58  xor     edx, edx; struct std::nothrow_t *
0x180019c5a  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180019c5f  mov     rdx, [rbp+70h+var_E0]
0x180019c63  test    rdx, rdx
0x180019c66  jz      short loc_180019C71
0x180019c68  mov     rcx, [rbp+70h+var_E8]
0x180019c6c  call    ??_9EncryptionAlgorithm@Kerb3961@@$BLA@AA; [thunk]: Kerb3961::EncryptionAlgorithm::`vcall'{176,{flat}}
0x180019c71  mov     rdx, [rsp+170h+var_110]
0x180019c76  test    rdx, rdx
0x180019c79  jz      short loc_180019C85
0x180019c7b  mov     rcx, [rsp+170h+var_118]
0x180019c80  call    ??_9EncryptionAlgorithm@Kerb3961@@$BKA@AA; [thunk]: Kerb3961::EncryptionAlgorithm::`vcall'{160,{flat}}
0x180019c85  mov     rax, rdi
0x180019c88  add     rsp, 138h
0x180019c8f  pop     r15
0x180019c91  pop     r14
0x180019c93  pop     r13
0x180019c95  pop     r12
0x180019c97  pop     rdi
0x180019c98  pop     rsi
0x180019c99  pop     rbx
0x180019c9a  pop     rbp
0x180019c9b  retn
```
