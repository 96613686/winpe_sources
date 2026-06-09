# CGermanSegmentationHandler::DoesCompoundWordVerifyAux(CWordNode *,ILspWordLatticeWalker *,int,Speller::CSpellerDataStorage *,ushort * const,unsigned __int64,bool &,bool &)

- ea: `0x180098848`
- end: `0x180098d71`
- name: `?DoesCompoundWordVerifyAux@CGermanSegmentationHandler@@SA_NPEAVCWordNode@@PEAUILspWordLatticeWalker@@HPEAVCSpellerDataStorage@Speller@@QEAG_KAEA_N5@Z`
- size: `1321`
- prototype: `bool __fastcall(struct CWordNode *, struct ILspWordLatticeWalker *, int, struct Speller::CSpellerDataStorage *, unsigned __int16 *const, unsigned __int64, bool *, bool *)`
- caller_count: `2`
- callee_count: `15`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18003bd7c`
- `0x180098848`

## callees

- `0x180003d38`
- `0x180009690`
- `0x18000b1a0`
- `0x180016258`
- `0x1800162e4`
- `0x18002be20`
- `0x180035640`
- `0x18003ed6c`
- `0x18006d468`
- `0x18008e690`
- `0x180092f58`
- `0x180098848`
- `0x180098f8c`
- `0x18009e300`
- `0x1800b0010`

## pseudocode

```c
bool __fastcall CGermanSegmentationHandler::DoesCompoundWordVerifyAux(
        struct CWordNode *a1,
        struct ILspWordLatticeWalker *a2,
        unsigned int a3,
        struct Speller::CSpellerDataStorage *a4,
        unsigned __int16 *const a5,
        unsigned __int64 a6,
        bool *a7,
        bool *a8)
{
  __int64 *v8; // rbx
  __int64 v12; // rbx
  bool DoesCompoundWordVerifyAux; // r14
  __int64 v14; // rsi
  __int64 v15; // rdi
  __int64 v16; // rax
  __int64 v17; // rsi
  __int64 v18; // rax
  struct CWordNode *v19; // rdi
  __int64 v20; // rdx
  __int64 v21; // rbx
  struct Speller::CSpellerDataStorage *v22; // r8
  __int64 v23; // rbx
  unsigned int v24; // edx
  unsigned __int64 v25; // r8
  const unsigned __int16 *v26; // rax
  unsigned int v27; // edx
  unsigned int i; // edx
  unsigned int j; // edx
  const unsigned __int16 *v30; // rax
  unsigned int v31; // edx
  __int64 v32; // r8
  unsigned int k; // edx
  __int64 v34; // rcx
  __int64 v35; // rcx
  unsigned __int64 v36; // rbx
  const unsigned __int16 *v37; // rax
  __int64 v38; // rdx
  int v39; // edx
  unsigned __int64 v40; // r8
  __int64 v41; // r8
  unsigned __int64 v42; // rbx
  const unsigned __int16 *v43; // rax
  unsigned __int64 v46; // [rsp+48h] [rbp-150h]
  __int64 v47; // [rsp+58h] [rbp-140h]
  _BYTE pExceptionObject[72]; // [rsp+68h] [rbp-130h] BYREF
  unsigned __int16 v49[72]; // [rsp+B0h] [rbp-E8h] BYREF
  const void *retaddr; // [rsp+198h] [rbp+0h]

  v8 = (__int64 *)((char *)a4 + 104);
  v46 = (unsigned int)Speller::CWordCollection::IndexOf(
                        (struct Speller::CSpellerDataStorage *)((char *)a4 + 104),
                        *((_DWORD *)a1 + 4),
                        *(_DWORD *)((char *)a1 + *(int *)(*((_QWORD *)a1 + 1) + 4LL) + 80));
  if ( v46 >= v8[1] )
  {
    CNLException::CNLException((CNLException *)pExceptionObject, 2147942487LL, retaddr);
    throw (CNLException *)pExceptionObject;
  }
  v12 = *v8;
  DoesCompoundWordVerifyAux = 0;
  v14 = *((_QWORD *)a1 + 2);
  v15 = *(_QWORD *)((char *)a1 + *(int *)(*((_QWORD *)a1 + 1) + 4LL) + 80);
  if ( (*(unsigned __int8 (__fastcall **)(struct ILspWordLatticeWalker *, _QWORD))(*(_QWORD *)a2 + 40LL))(a2, 0) )
  {
    v16 = v14 - 1;
    v17 = v12 + (v46 << 7);
    v47 = v15 + v16;
    while ( 1 )
    {
      while ( 1 )
      {
LABEL_5:
        v18 = (*(__int64 (__fastcall **)(struct ILspWordLatticeWalker *))(*(_QWORD *)a2 + 32LL))(a2);
        v19 = (struct CWordNode *)v18;
        if ( !v18 )
        {
LABEL_59:
          (*(void (__fastcall **)(struct ILspWordLatticeWalker *, _QWORD))(*(_QWORD *)a2 + 48LL))(a2, 0);
          return DoesCompoundWordVerifyAux;
        }
        v20 = *(int *)(*(_QWORD *)(v18 + 8) + 4LL);
        if ( (*(_DWORD *)(v20 + v18 + 8) & 0xF8000000) == 0x38000000
          && ((*(_DWORD *)(v20 + v18 + 36) & 0x100) == 0 || *(_DWORD *)(v17 + 76) == 6) )
        {
          break;
        }
LABEL_47:
        if ( DoesCompoundWordVerifyAux )
          goto LABEL_59;
      }
      if ( *(_QWORD *)(v18 + 16) + *(_QWORD *)(v20 + v18 + 80) - 1LL != v47 )
        goto LABEL_49;
      v21 = v20 + v18;
      if ( (*(_DWORD *)(v20 + v18 + 16) & 0x800) != 0
        || LSP::LexEntryData::IsRestrictedInMask((LSP::LexEntryData *)(v21 + 16), a3) )
      {
        goto LABEL_49;
      }
      if ( LSP::LexEntryData::IsInDialectMask((LSP::LexEntryData *)(v21 + 16), a3) )
        goto LABEL_15;
      v22 = a4;
      v23 = *((_QWORD *)a4 + 4);
      if ( *(_QWORD *)(v23 + 16) - *(_QWORD *)((char *)a1 + *(int *)(*((_QWORD *)a1 + 1) + 4LL) + 80) != *((_QWORD *)a1 + 2) )
        break;
LABEL_50:
      v38 = *(int *)(*((_QWORD *)v19 + 1) + 4LL);
      if ( *((_QWORD *)v19 + 2) + *(_QWORD *)((char *)v19 + v38 + 80) - 1LL >= v47 )
        goto LABEL_47;
      v39 = *(_DWORD *)((char *)v19 + v38 + 16);
      if ( ((v39 & 0x400) == 0 || (a3 & 1) == 0)
        && ((v39 & 0x1000) == 0 || (a3 & 2) == 0)
        && ((v39 & 0x2000) == 0 || (a3 & 4) == 0)
        && ((v39 & 0x4000) == 0 || (a3 & 8) == 0) )
      {
        goto LABEL_47;
      }
      DoesCompoundWordVerifyAux = CGermanSegmentationHandler::DoesCompoundWordVerifyAux(
                                    a1,
                                    a2,
                                    a3,
                                    v22,
                                    a5,
                                    0x41u,
                                    a7,
                                    a8);
      if ( DoesCompoundWordVerifyAux )
      {
        if ( (*(_DWORD *)((_BYTE *)v19 + *(int *)(*((_QWORD *)v19 + 1) + 4LL) + 36) & 0x200) == 0
          || !CGermanSegmentationHandler::FindNormForms(v19, a5, v40, a7) )
        {
          v41 = *(int *)(*((_QWORD *)v19 + 1) + 4LL);
          v42 = *(_QWORD *)((char *)v19 + v41 + 80);
          v43 = LSP::CName::ToString((struct CWordNode *)((char *)v19 + v41 + 48));
          StringCchCopyNW(v49, 0x41u, v43, v42);
          StringCchCatW(v49, 0x41u, a5);
          StringCchCopyW(a5, 0x41u, v49);
        }
        goto LABEL_59;
      }
    }
    if ( CText::GetText(*(CText **)(v23 + 168))[*((_QWORD *)a1 + 2)
                                              + *(_QWORD *)(v23 + 8)
                                              + *(_QWORD *)((char *)a1 + *(int *)(*((_QWORD *)a1 + 1) + 4LL) + 80)] == 45 )
    {
LABEL_15:
      v24 = 0;
      v25 = *(int *)(*((_QWORD *)v19 + 1) + 4LL);
      while ( 1 )
      {
        if ( v24 >= 4 )
          goto LABEL_43;
        if ( (unsigned int)(unsigned __int8)(*(_DWORD *)((char *)v19 + v25 + 20) >> (8 * v24)) - 1 <= 0x3F )
          break;
        ++v24;
      }
      v26 = LSP::CName::ToString((struct CWordNode *)((char *)a1 + *(int *)(*((_QWORD *)a1 + 1) + 4LL) + 48));
      if ( (unsigned int)CMN_IsCharUpperW(*v26) )
      {
LABEL_43:
        if ( (*(_DWORD *)((_BYTE *)v19 + *(int *)(*((_QWORD *)v19 + 1) + 4LL) + 36) & 0x200) == 0
          || !CGermanSegmentationHandler::FindNormForms(v19, a5, v25, a7) )
        {
          v35 = *(int *)(*((_QWORD *)v19 + 1) + 4LL);
          v36 = *(_QWORD *)((char *)v19 + v35 + 80);
          v37 = LSP::CName::ToString((struct CWordNode *)((char *)v19 + v35 + 48));
          StringCchCopyNW(a5, 0x41u, v37, v36);
        }
        DoesCompoundWordVerifyAux = 1;
        goto LABEL_47;
      }
      v27 = 0;
      v25 = *(int *)(*((_QWORD *)v19 + 1) + 4LL);
      while ( v27 < 4 )
      {
        if ( (unsigned int)(unsigned __int8)(*(_DWORD *)((char *)v19 + v25 + 20) >> (8 * v27)) - 65 <= 0x3F )
          goto LABEL_43;
        ++v27;
      }
      for ( i = 0; i < 4; ++i )
      {
        if ( (unsigned int)(unsigned __int8)(*(_DWORD *)((char *)v19 + v25 + 20) >> (8 * i)) - 129 <= 0x1F )
          goto LABEL_43;
      }
      for ( j = 0; j < 4; ++j )
      {
        if ( (unsigned int)(unsigned __int8)(*(_DWORD *)((char *)v19 + v25 + 20) >> (8 * j)) - 1 <= 0x3F )
        {
          v30 = LSP::CName::ToString((struct CWordNode *)((char *)a1 + *(int *)(*((_QWORD *)a1 + 1) + 4LL) + 48));
          if ( !(unsigned int)CMN_IsCharUpperW(*v30) )
          {
            v31 = 0;
            v32 = *(int *)(*((_QWORD *)v19 + 1) + 4LL);
            while ( v31 < 4 )
            {
              if ( (unsigned int)(unsigned __int8)(*(_DWORD *)((char *)v19 + v32 + 20) >> (8 * v31)) - 65 <= 0x3F )
                goto LABEL_47;
              ++v31;
            }
            for ( k = 0; k < 4; ++k )
            {
              if ( (unsigned int)(unsigned __int8)(*(_DWORD *)((char *)v19 + v32 + 20) >> (8 * k)) - 129 <= 0x1F )
                goto LABEL_47;
            }
            if ( !*a7 )
            {
              v34 = *(int *)(*((_QWORD *)a1 + 1) + 4LL);
              *(_DWORD *)((char *)a1 + v34 + 36) |= 0x40u;
              DoesCompoundWordVerifyAux = 0;
              goto LABEL_5;
            }
          }
          goto LABEL_47;
        }
      }
      goto LABEL_47;
    }
LABEL_49:
    v22 = a4;
    goto LABEL_50;
  }
  return DoesCompoundWordVerifyAux;
}

```

## disassembly

```asm
0x180098848  push    rbx
0x18009884a  push    rbp
0x18009884b  push    rsi
0x18009884c  push    rdi
0x18009884d  push    r12
0x18009884f  push    r13
0x180098851  push    r14
0x180098853  push    r15
0x180098855  sub     rsp, 158h
0x18009885c  mov     rax, cs:__security_cookie
0x180098863  xor     rax, rsp
0x180098866  mov     [rsp+198h+var_58], rax
0x18009886e  mov     rax, [rsp+198h+arg_30]
0x180098876  lea     rbx, [r9+68h]
0x18009887a  mov     r13, [rsp+198h+arg_20]
0x180098882  mov     r12d, r8d
0x180098885  mov     [rsp+198h+var_148], rax
0x18009888a  mov     r15, rdx
0x18009888d  mov     rax, [rsp+198h+arg_38]
0x180098895  mov     rbp, rcx
0x180098898  mov     edx, [rcx+10h]; unsigned int
0x18009889b  mov     [rsp+198h+var_138], rax
0x1800988a0  mov     rax, [rcx+8]
0x1800988a4  mov     [rsp+198h+var_158], r9
0x1800988a9  movsxd  r8, dword ptr [rax+4]
0x1800988ad  mov     r8d, [r8+rcx+50h]; unsigned int
0x1800988b2  mov     rcx, rbx; this
0x1800988b5  call    ?IndexOf@CWordCollection@Speller@@QEAAHII@Z; Speller::CWordCollection::IndexOf(uint,uint)
0x1800988ba  mov     esi, eax
0x1800988bc  mov     [rsp+198h+var_150], rsi
0x1800988c1  cmp     rsi, [rbx+8]
0x1800988c5  jb      short loc_1800988F0
0x1800988c7  mov     r8, [rsp+198h]; void *
0x1800988cf  lea     rcx, [rsp+198h+pExceptionObject]; this
0x1800988d4  mov     edx, 80070057h; int
0x1800988d9  call    ??0CNLException@@QEAA@JPEBX@Z; CNLException::CNLException(long,void const *)
0x1800988de  lea     rdx, _TI2?AVCNLException@@; pThrowInfo
0x1800988e5  lea     rcx, [rsp+198h+pExceptionObject]; pExceptionObject
0x1800988ea  call    _CxxThrowException_0
0x1800988f0  mov     rax, [rbp+8]
0x1800988f4  xor     edx, edx
0x1800988f6  mov     rbx, [rbx]
0x1800988f9  xor     r14b, r14b
0x1800988fc  mov     rsi, [rbp+10h]
0x180098900  movsxd  rcx, dword ptr [rax+4]
0x180098904  mov     rax, [r15]
0x180098907  mov     rdi, [rcx+rbp+50h]
0x18009890c  mov     rcx, r15
0x18009890f  mov     rax, [rax+28h]
0x180098913  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180098918  test    al, al
0x18009891a  jz      loc_180098D4A
0x180098920  mov     rax, [rsp+198h+var_150]
0x180098925  shl     rax, 7
0x180098929  add     rax, rbx
0x18009892c  mov     [rsp+198h+var_150], rax
0x180098931  lea     rax, [rsi-1]
0x180098935  mov     rsi, [rsp+198h+var_150]
0x18009893a  add     rax, rdi
0x18009893d  mov     [rsp+198h+var_140], rax
0x180098942  mov     rax, [r15]
0x180098945  mov     rcx, r15
0x180098948  mov     rax, [rax+20h]
0x18009894c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180098951  mov     rdi, rax
0x180098954  test    rax, rax
0x180098957  jz      loc_180098D39
0x18009895d  mov     rax, [rax+8]
0x180098961  movsxd  rdx, dword ptr [rax+4]
0x180098965  mov     eax, [rdx+rdi+8]
0x180098969  and     eax, 0F8000000h
0x18009896e  cmp     eax, 38000000h
0x180098973  jnz     loc_180098C06
0x180098979  test    dword ptr [rdx+rdi+24h], 100h
0x180098981  jz      short loc_18009898D
0x180098983  cmp     dword ptr [rsi+4Ch], 6
0x180098987  jnz     loc_180098C06
0x18009898d  mov     rcx, [rdx+rdi+50h]
0x180098992  dec     rcx
0x180098995  add     rcx, [rdi+10h]
0x180098999  cmp     rcx, [rsp+198h+var_140]
0x18009899e  jnz     loc_180098C14
0x1800989a4  lea     rbx, [rdx+rdi]
0x1800989a8  test    dword ptr [rbx+10h], 800h
0x1800989af  jnz     loc_180098C14
0x1800989b5  mov     edx, r12d; unsigned int
0x1800989b8  lea     rcx, [rbx+10h]; this
0x1800989bc  call    ?IsRestrictedInMask@LexEntryData@LSP@@QEBA_NI@Z; LSP::LexEntryData::IsRestrictedInMask(uint)
0x1800989c1  test    al, al
0x1800989c3  jnz     loc_180098C14
0x1800989c9  mov     edx, r12d; unsigned int
0x1800989cc  lea     rcx, [rbx+10h]; this
0x1800989d0  call    ?IsInDialectMask@LexEntryData@LSP@@QEBA_NI@Z; LSP::LexEntryData::IsInDialectMask(uint)
0x1800989d5  test    al, al
0x1800989d7  jnz     short loc_180098A2D
0x1800989d9  mov     rax, [rbp+8]
0x1800989dd  mov     r8, [rsp+198h+var_158]
0x1800989e2  movsxd  rcx, dword ptr [rax+4]
0x1800989e6  mov     rbx, [r8+20h]
0x1800989ea  mov     rax, [rbx+10h]
0x1800989ee  sub     rax, [rcx+rbp+50h]
0x1800989f3  cmp     rax, [rbp+10h]
0x1800989f7  jz      loc_180098C19
0x1800989fd  mov     rcx, [rbx+0A8h]; this
0x180098a04  call    ?GetText@CText@@QEAAPEBGXZ; CText::GetText(void)
0x180098a09  mov     r8, rax
0x180098a0c  mov     rax, [rbp+8]
0x180098a10  movsxd  rcx, dword ptr [rax+4]
0x180098a14  mov     rdx, [rcx+rbp+50h]
0x180098a19  add     rdx, [rbx+8]
0x180098a1d  add     rdx, [rbp+10h]
0x180098a21  cmp     word ptr [r8+rdx*2], 2Dh ; '-'
0x180098a27  jnz     loc_180098C14
0x180098a2d  mov     rax, [rdi+8]
0x180098a31  xor     edx, edx
0x180098a33  movsxd  r8, dword ptr [rax+4]; unsigned __int64
0x180098a37  lea     ebx, [rdx+4]
0x180098a3a  cmp     edx, ebx
0x180098a3c  jnb     loc_180098BB1
0x180098a42  test    edx, edx
0x180098a44  js      short loc_180098A5E
0x180098a46  mov     eax, [r8+rdi+14h]
0x180098a4b  lea     ecx, ds:0[rdx*8]
0x180098a52  shr     eax, cl
0x180098a54  movzx   ecx, al
0x180098a57  dec     ecx
0x180098a59  cmp     ecx, 3Fh ; '?'
0x180098a5c  jbe     short loc_180098A62
0x180098a5e  inc     edx
0x180098a60  jmp     short loc_180098A3A
0x180098a62  mov     rax, [rbp+8]
0x180098a66  movsxd  rcx, dword ptr [rax+4]
0x180098a6a  add     rcx, 30h ; '0'
0x180098a6e  add     rcx, rbp; this
0x180098a71  call    ?ToString@CName@LSP@@QEBAPEBGXZ; LSP::CName::ToString(void)
0x180098a76  movzx   ecx, word ptr [rax]
0x180098a79  call    CMN_IsCharUpperW
0x180098a7e  test    eax, eax
0x180098a80  jnz     loc_180098BB1
0x180098a86  mov     rax, [rdi+8]
0x180098a8a  xor     edx, edx
0x180098a8c  movsxd  r8, dword ptr [rax+4]
0x180098a90  cmp     edx, ebx
0x180098a92  jnb     short loc_180098AB9
0x180098a94  test    edx, edx
0x180098a96  js      short loc_180098AB5
0x180098a98  mov     eax, [r8+rdi+14h]
0x180098a9d  lea     ecx, ds:0[rdx*8]
0x180098aa4  shr     eax, cl
0x180098aa6  movzx   ecx, al
0x180098aa9  sub     ecx, 41h ; 'A'
0x180098aac  cmp     ecx, 3Fh ; '?'
0x180098aaf  jbe     loc_180098BB1
0x180098ab5  inc     edx
0x180098ab7  jmp     short loc_180098A90
0x180098ab9  xor     edx, edx
0x180098abb  cmp     edx, ebx
0x180098abd  jnb     short loc_180098AE7
0x180098abf  test    edx, edx
0x180098ac1  js      short loc_180098AE3
0x180098ac3  mov     eax, [r8+rdi+14h]
0x180098ac8  lea     ecx, ds:0[rdx*8]
0x180098acf  shr     eax, cl
0x180098ad1  movzx   ecx, al
0x180098ad4  sub     ecx, 81h
0x180098ada  cmp     ecx, 1Fh
0x180098add  jbe     loc_180098BB1
0x180098ae3  inc     edx
0x180098ae5  jmp     short loc_180098ABB
0x180098ae7  xor     edx, edx
0x180098ae9  cmp     edx, ebx
0x180098aeb  jnb     loc_180098C06
0x180098af1  test    edx, edx
0x180098af3  js      short loc_180098B0D
0x180098af5  mov     eax, [r8+rdi+14h]
0x180098afa  lea     ecx, ds:0[rdx*8]
0x180098b01  shr     eax, cl
0x180098b03  movzx   ecx, al
0x180098b06  dec     ecx
0x180098b08  cmp     ecx, 3Fh ; '?'
0x180098b0b  jbe     short loc_180098B11
0x180098b0d  inc     edx
0x180098b0f  jmp     short loc_180098AE9
0x180098b11  mov     rax, [rbp+8]
0x180098b15  movsxd  rcx, dword ptr [rax+4]
0x180098b19  add     rcx, 30h ; '0'
0x180098b1d  add     rcx, rbp; this
0x180098b20  call    ?ToString@CName@LSP@@QEBAPEBGXZ; LSP::CName::ToString(void)
0x180098b25  movzx   ecx, word ptr [rax]
0x180098b28  call    CMN_IsCharUpperW
0x180098b2d  test    eax, eax
0x180098b2f  jnz     loc_180098C06
0x180098b35  mov     rax, [rdi+8]
0x180098b39  xor     edx, edx
0x180098b3b  movsxd  r8, dword ptr [rax+4]
0x180098b3f  cmp     edx, ebx
0x180098b41  jnb     short loc_180098B68
0x180098b43  test    edx, edx
0x180098b45  js      short loc_180098B64
0x180098b47  mov     eax, [r8+rdi+14h]
0x180098b4c  lea     ecx, ds:0[rdx*8]
0x180098b53  shr     eax, cl
0x180098b55  movzx   ecx, al
0x180098b58  sub     ecx, 41h ; 'A'
0x180098b5b  cmp     ecx, 3Fh ; '?'
0x180098b5e  jbe     loc_180098C06
0x180098b64  inc     edx
0x180098b66  jmp     short loc_180098B3F
0x180098b68  xor     edx, edx
0x180098b6a  cmp     edx, ebx
0x180098b6c  jnb     short loc_180098B92
0x180098b6e  test    edx, edx
0x180098b70  js      short loc_180098B8E
0x180098b72  mov     eax, [r8+rdi+14h]
0x180098b77  lea     ecx, ds:0[rdx*8]
0x180098b7e  shr     eax, cl
0x180098b80  movzx   ecx, al
0x180098b83  sub     ecx, 81h
0x180098b89  cmp     ecx, 1Fh
0x180098b8c  jbe     short loc_180098C06
0x180098b8e  inc     edx
0x180098b90  jmp     short loc_180098B6A
0x180098b92  mov     rbx, [rsp+198h+var_148]
0x180098b97  cmp     byte ptr [rbx], 0
0x180098b9a  jnz     short loc_180098C06
0x180098b9c  mov     rax, [rbp+8]
0x180098ba0  movsxd  rcx, dword ptr [rax+4]
0x180098ba4  or      dword ptr [rcx+rbp+24h], 40h
0x180098ba9  xor     r14b, r14b
0x180098bac  jmp     loc_180098942
0x180098bb1  mov     rax, [rdi+8]
0x180098bb5  movsxd  rcx, dword ptr [rax+4]
0x180098bb9  test    dword ptr [rcx+rdi+24h], 200h
0x180098bc1  jz      short loc_180098BD7
0x180098bc3  mov     r9, [rsp+198h+var_148]; bool *
0x180098bc8  mov     rdx, r13; unsigned __int16 *
0x180098bcb  mov     rcx, rdi; struct CWordNode *
0x180098bce  call    ?FindNormForms@CGermanSegmentationHandler@@SA_NPEAVCWordNode@@QEAG_KAEA_N@Z; CGermanSegmentationHandler::FindNormForms(CWordNode *,ushort * const,unsigned __int64,bool &)
0x180098bd3  test    al, al
0x180098bd5  jnz     short loc_180098C03
0x180098bd7  mov     rax, [rdi+8]
0x180098bdb  movsxd  rcx, dword ptr [rax+4]
0x180098bdf  mov     rbx, [rcx+rdi+50h]
0x180098be4  add     rcx, 30h ; '0'
0x180098be8  add     rcx, rdi; this
0x180098beb  call    ?ToString@CName@LSP@@QEBAPEBGXZ; LSP::CName::ToString(void)
0x180098bf0  mov     r9, rbx; unsigned __int64
0x180098bf3  mov     r8, rax; unsigned __int16 *
0x180098bf6  mov     edx, 41h ; 'A'; unsigned __int64
0x180098bfb  mov     rcx, r13; unsigned __int16 *
0x180098bfe  call    ?StringCchCopyNW@@YAJPEAG_KPEBG1@Z; StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x180098c03  mov     r14b, 1
0x180098c06  test    r14b, r14b
0x180098c09  jz      loc_180098942
0x180098c0f  jmp     loc_180098D39
0x180098c14  mov     r8, [rsp+198h+var_158]
0x180098c19  mov     rax, [rdi+8]
0x180098c1d  movsxd  rdx, dword ptr [rax+4]
0x180098c21  mov     rcx, [rdx+rdi+50h]
0x180098c26  dec     rcx
0x180098c29  add     rcx, [rdi+10h]
0x180098c2d  cmp     rcx, [rsp+198h+var_140]
0x180098c32  jge     short loc_180098C06
0x180098c34  mov     edx, [rdx+rdi+10h]
0x180098c38  bt      edx, 0Ah
0x180098c3c  setb    cl
0x180098c3f  test    r12b, 1
0x180098c43  setnz   al
0x180098c46  test    al, cl
0x180098c48  jnz     short loc_180098C80
0x180098c4a  bt      edx, 0Ch
0x180098c4e  setb    cl
0x180098c51  test    r12b, 2
0x180098c55  setnz   al
0x180098c58  test    al, cl
0x180098c5a  jnz     short loc_180098C80
0x180098c5c  bt      edx, 0Dh
0x180098c60  setb    cl
0x180098c63  test    r12b, 4
0x180098c67  setnz   al
0x180098c6a  test    al, cl
0x180098c6c  jnz     short loc_180098C80
0x180098c6e  bt      edx, 0Eh
0x180098c72  setb    cl
0x180098c75  test    r12b, 8
0x180098c79  setnz   al
0x180098c7c  test    al, cl
0x180098c7e  jz      short loc_180098C06
0x180098c80  mov     rax, [rsp+198h+var_138]
0x180098c85  mov     r9, r8; struct Speller::CSpellerDataStorage *
0x180098c88  mov     rbx, [rsp+198h+var_148]
0x180098c8d  mov     r8d, r12d; int
0x180098c90  mov     [rsp+198h+var_160], rax; bool *
0x180098c95  mov     rdx, r15; struct ILspWordLatticeWalker *
0x180098c98  mov     [rsp+198h+var_168], rbx; bool *
0x180098c9d  mov     rcx, rbp; struct CWordNode *
0x180098ca0  mov     [rsp+198h+var_170], 41h ; 'A'; unsigned __int64
0x180098ca9  mov     [rsp+198h+var_178], r13; unsigned __int16 *
0x180098cae  call    ?DoesCompoundWordVerifyAux@CGermanSegmentationHandler@@SA_NPEAVCWordNode@@PEAUILspWordLatticeWalker@@HPEAVCSpellerDataStorage@Speller@@QEAG_KAEA_N5@Z; CGermanSegmentationHandler::DoesCompoundWordVerifyAux(CWordNode *,ILspWordLatticeWalker *,int,Speller::CSpellerDataStorage *,ushort * const,unsigned __int64,bool &,bool &)
0x180098cb3  mov     r14b, al
  ... truncated ...
```
