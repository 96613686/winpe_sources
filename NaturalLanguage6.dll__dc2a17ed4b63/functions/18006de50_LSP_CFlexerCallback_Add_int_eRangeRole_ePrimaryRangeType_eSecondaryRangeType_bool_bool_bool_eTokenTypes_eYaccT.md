# LSP::CFlexerCallback::Add(int,eRangeRole,ePrimaryRangeType,eSecondaryRangeType,bool,bool,bool,eTokenTypes,eYaccToken)

- ea: `0x18006de50`
- end: `0x18006e19a`
- name: `?Add@CFlexerCallback@LSP@@UEAAPEAVCWordNode@@HW4eRangeRole@@W4ePrimaryRangeType@@W4eSecondaryRangeType@@_N33W4eTokenTypes@@W4eYaccToken@@@Z`
- size: `842`
- prototype: `__int64 __fastcall(__int64, unsigned int, unsigned int, int, int, char, char, char, int, char)`
- caller_count: `0`
- callee_count: `8`
- tags: `reparse_path`

## callees

- `0x18002a918`
- `0x18002bc50`
- `0x180035640`
- `0x18003754c`
- `0x18003ed6c`
- `0x18005dbdc`
- `0x18006de50`
- `0x1800b0010`

## pseudocode

```c
__int64 __fastcall LSP::CFlexerCallback::Add(
        __int64 a1,
        unsigned int a2,
        unsigned int a3,
        int a4,
        int a5,
        char a6,
        char a7,
        char a8,
        int a9,
        char a10)
{
  unsigned __int64 v10; // rbx
  unsigned __int64 v13; // r14
  __int64 v14; // r15
  int v15; // r13d
  int v16; // ebp
  CSentence *v17; // rcx
  __int64 v18; // r9
  CSentence *v19; // rcx
  unsigned __int64 v20; // rax
  __int64 v21; // r10
  __int64 v22; // rdi
  __int64 (__fastcall *v23)(__int64, __int128 *, unsigned __int64, unsigned __int64, unsigned __int64, int, _DWORD, int, char); // rbx
  __int64 v24; // rax
  __int64 v25; // rax
  __int64 v26; // rdi
  __int64 v27; // rcx
  __int64 v28; // rcx
  __int64 v29; // rcx
  __int64 v30; // rcx
  int v31; // edx
  __int64 v32; // rcx
  struct CZoneHeap *v33; // rbp
  struct CNodeProperties *v34; // rbx
  __int64 v35; // rax
  unsigned __int64 v37; // [rsp+50h] [rbp-A8h]
  __int128 v38; // [rsp+60h] [rbp-98h] BYREF
  char v39[16]; // [rsp+70h] [rbp-88h] BYREF
  _BYTE pExceptionObject[120]; // [rsp+80h] [rbp-78h] BYREF
  const void *retaddr; // [rsp+F8h] [rbp+0h]
  unsigned __int64 v42; // [rsp+100h] [rbp+8h]

  v10 = (int)a2;
  if ( !*(_QWORD *)(a1 + 56) )
    (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)a1 + 8LL))(a1, 1);
  v13 = v10;
  if ( a6 )
  {
    v14 = *(_QWORD *)(a1 + 64);
    v13 = *(_QWORD *)(a1 + 56) + v10 - v14;
  }
  else
  {
    v14 = *(_QWORD *)(a1 + 56);
  }
  v15 = 4;
  if ( a3 < 2 )
  {
    v15 = 3;
  }
  else
  {
    if ( a3 == 9 )
    {
      v16 = 20;
      v15 = 7;
      goto LABEL_13;
    }
    if ( a3 == 12 )
    {
      v16 = 33;
      goto LABEL_13;
    }
  }
  v16 = a9;
LABEL_13:
  v17 = *(CSentence **)(a1 + 16);
  if ( *(_BYTE *)(a1 + 88) )
  {
    v37 = CSentence::OriginalIndex(v17, v14 + *((_QWORD *)v17 + 1) - 1LL);
    v20 = CSentence::OriginalIndex(v19, v13 + v14 + v18 - 1);
    v42 = v20 - v21;
  }
  else
  {
    v42 = v13;
    v37 = v14 + *((_QWORD *)v17 + 1) - 1LL;
  }
  v22 = *(_QWORD *)(a1 + 24);
  v23 = *(__int64 (__fastcall **)(__int64, __int128 *, unsigned __int64, unsigned __int64, unsigned __int64, int, _DWORD, int, char))(*(_QWORD *)v22 + 24LL);
  v24 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 8) + 288LL))(*(_QWORD *)(a1 + 8));
  v38 = *(_OWORD *)(*(__int64 (__fastcall **)(__int64, char *, unsigned __int64, unsigned __int64))(*(_QWORD *)v24 + 40LL))(
                     v24,
                     v39,
                     v37,
                     v42);
  v25 = v23(v22, &v38, v37, v42, v42, v16, 0, v15, a8);
  v26 = v25;
  if ( !v25 )
  {
    CNLException::CNLException((CNLException *)pExceptionObject, 2147500037LL, retaddr);
    throw (CNLException *)pExceptionObject;
  }
  *(_QWORD *)(a1 + 80) = v25;
  *(_BYTE *)(*(int *)(*(_QWORD *)(v25 + 8) + 4LL) + v25 + 12) = a10;
  if ( v16 != 3 )
  {
    v27 = *(int *)(*(_QWORD *)(v25 + 8) + 4LL);
    *(_DWORD *)(v27 + v25 + 12) ^= (*(_DWORD *)(v27 + v25 + 12) ^ (v16 << 16)) & 0x3F0000;
  }
  if ( a3 != 1 )
  {
    if ( a3 || a4 || a5 )
    {
      v28 = *(int *)(*(_QWORD *)(v25 + 8) + 4LL);
      *(_DWORD *)(v28 + v25 + 8) &= 0x7FFFFFFu;
      *(_DWORD *)(v28 + v25 + 8) |= a3 << 27;
      *(_BYTE *)(*(int *)(*(_QWORD *)(v25 + 8) + 4LL) + v25 + 9) = a4;
      v29 = *(int *)(*(_QWORD *)(v25 + 8) + 4LL);
      *(_DWORD *)(v29 + v25 + 8) ^= (*(_DWORD *)(v29 + v25 + 8) ^ (a5 << 16)) & 0x7FF0000;
      v30 = *(int *)(*(_QWORD *)(v25 + 8) + 4LL);
      *(_DWORD *)(v30 + v25 + 8) &= 0xFFFFFF0F;
      *(_DWORD *)(v30 + v25 + 8) |= 16 * v15;
    }
    v31 = *(_DWORD *)(a1 + 72);
    if ( v31 )
    {
      v32 = *(int *)(*(_QWORD *)(v25 + 8) + 4LL);
      *(_DWORD *)(v32 + v25 + 8) ^= (*(_DWORD *)(v32 + v25 + 8) ^ (16 * v31)) & 0xF0;
    }
  }
  v33 = (struct CZoneHeap *)(*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 24) + 112LL))(*(_QWORD *)(a1 + 24));
  if ( *(_BYTE *)(a1 + 88)
    && CSentence::IsNormalized(*(CSentence **)(a1 + 16), v14 + *(_QWORD *)(*(_QWORD *)(a1 + 16) + 8LL) - 1LL, v13) )
  {
    v34 = CMorphNode::NewProperties((CMorphNode *)(v26 + *(int *)(*(_QWORD *)(v26 + 8) + 4LL) + 8LL), v33);
    v35 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 16) + 64LL))(*(_QWORD *)(a1 + 16));
    CNodeProperties::AddNormalizedString(
      v34,
      *(_QWORD *)(*(_QWORD *)(a1 + 16) + 168LL),
      v33,
      v35 - 2 + 2 * v14,
      v13,
      242);
  }
  if ( a7 )
    (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)a1 + 8LL))(a1, a2);
  return v26;
}

```

## disassembly

```asm
0x18006de50  mov     [rsp+arg_10], rbx
0x18006de55  mov     [rsp+arg_18], r9d
0x18006de5a  mov     [rsp+arg_8], edx
0x18006de5e  push    rbp
0x18006de5f  push    rsi
0x18006de60  push    rdi
0x18006de61  push    r12
0x18006de63  push    r13
0x18006de65  push    r14
0x18006de67  push    r15
0x18006de69  sub     rsp, 0C0h
0x18006de70  xor     edi, edi
0x18006de72  movsxd  rbx, edx
0x18006de75  mov     r12d, r8d
0x18006de78  mov     rsi, rcx
0x18006de7b  cmp     [rcx+38h], rdi
0x18006de7f  jnz     short loc_18006DE90
0x18006de81  mov     rax, [rcx]
0x18006de84  lea     edx, [rdi+1]
0x18006de87  mov     rax, [rax+8]
0x18006de8b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006de90  mov     r14, rbx
0x18006de93  cmp     [rsp+0F8h+arg_28], dil
0x18006de9b  jz      short loc_18006DEAA
0x18006de9d  mov     r15, [rsi+40h]
0x18006dea1  sub     r14, r15
0x18006dea4  add     r14, [rsi+38h]
0x18006dea8  jmp     short loc_18006DEAE
0x18006deaa  mov     r15, [rsi+38h]
0x18006deae  mov     r13d, 4
0x18006deb4  mov     ecx, r12d
0x18006deb7  test    r12d, r12d
0x18006deba  jz      short loc_18006DEDB
0x18006debc  sub     ecx, 1
0x18006debf  jz      short loc_18006DEDB
0x18006dec1  sub     ecx, 8
0x18006dec4  jz      short loc_18006DED0
0x18006dec6  cmp     ecx, 3
0x18006dec9  jnz     short loc_18006DEE1
0x18006decb  lea     ebp, [rcx+1Eh]
0x18006dece  jmp     short loc_18006DEE8
0x18006ded0  mov     ebp, 14h
0x18006ded5  lea     r13d, [rbp-0Dh]
0x18006ded9  jmp     short loc_18006DEE8
0x18006dedb  mov     r13d, 3
0x18006dee1  mov     ebp, [rsp+0F8h+arg_40]
0x18006dee8  mov     rcx, [rsi+10h]; this
0x18006deec  cmp     [rsi+58h], dil
0x18006def0  jz      short loc_18006DF26
0x18006def2  mov     r9, [rcx+8]
0x18006def6  lea     rdx, [r9-1]
0x18006defa  add     rdx, r15; unsigned __int64
0x18006defd  call    ?OriginalIndex@CSentence@@QEBA_K_K@Z; CSentence::OriginalIndex(unsigned __int64)
0x18006df02  lea     rdx, [r9-1]
0x18006df06  mov     [rsp+0F8h+var_A8], rax
0x18006df0b  add     rdx, r15
0x18006df0e  mov     r10, rax
0x18006df11  add     rdx, r14; unsigned __int64
0x18006df14  call    ?OriginalIndex@CSentence@@QEBA_K_K@Z; CSentence::OriginalIndex(unsigned __int64)
0x18006df19  sub     rax, r10
0x18006df1c  mov     [rsp+0F8h+arg_0], rax
0x18006df24  jmp     short loc_18006DF3D
0x18006df26  mov     rax, [rcx+8]
0x18006df2a  dec     rax
0x18006df2d  mov     [rsp+0F8h+arg_0], r14
0x18006df35  add     rax, r15
0x18006df38  mov     [rsp+0F8h+var_A8], rax
0x18006df3d  mov     rdi, [rsi+18h]
0x18006df41  mov     rcx, [rsi+8]
0x18006df45  mov     rax, [rdi]
0x18006df48  mov     rbx, [rax+18h]
0x18006df4c  mov     rax, [rcx]
0x18006df4f  mov     rax, [rax+120h]
0x18006df56  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006df5b  mov     r9, [rsp+0F8h+arg_0]
0x18006df63  lea     rdx, [rsp+0F8h+var_88]
0x18006df68  mov     r8, [rsp+0F8h+var_A8]
0x18006df6d  mov     r10, rax
0x18006df70  mov     rcx, [rax]
0x18006df73  mov     rax, [rcx+28h]
0x18006df77  mov     rcx, r10
0x18006df7a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006df7f  mov     dl, [rsp+0F8h+arg_38]
0x18006df86  mov     rcx, rdi
0x18006df89  mov     r8, [rsp+0F8h+var_A8]
0x18006df8e  mov     [rsp+0F8h+var_B8], dl
0x18006df92  lea     rdx, [rsp+0F8h+var_98]
0x18006df97  movups  xmm0, xmmword ptr [rax]
0x18006df9a  mov     rax, [rsp+0F8h+arg_0]
0x18006dfa2  mov     [rsp+0F8h+var_C0], r13d
0x18006dfa7  mov     r9, rax
0x18006dfaa  mov     [rsp+0F8h+var_C8], 0
0x18006dfb2  mov     [rsp+0F8h+var_D0], ebp
0x18006dfb6  mov     [rsp+0F8h+var_D8], rax
0x18006dfbb  mov     rax, rbx
0x18006dfbe  movdqu  [rsp+0F8h+var_98], xmm0
0x18006dfc4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006dfc9  mov     rdi, rax
0x18006dfcc  test    rax, rax
0x18006dfcf  jnz     short loc_18006E000
0x18006dfd1  mov     r8, [rsp+0F8h]; void *
0x18006dfd9  lea     rcx, [rsp+0F8h+pExceptionObject]; this
0x18006dfe1  mov     edx, 80004005h; int
0x18006dfe6  call    ??0CNLException@@QEAA@JPEBX@Z; CNLException::CNLException(long,void const *)
0x18006dfeb  lea     rdx, _TI2?AVCNLException@@; pThrowInfo
0x18006dff2  lea     rcx, [rsp+0F8h+pExceptionObject]; pExceptionObject
0x18006dffa  call    _CxxThrowException_0
0x18006e000  mov     dl, [rsp+0F8h+arg_48]
0x18006e007  mov     [rsi+50h], rdi
0x18006e00b  mov     rax, [rax+8]
0x18006e00f  movsxd  rcx, dword ptr [rax+4]
0x18006e013  mov     [rcx+rdi+0Ch], dl
0x18006e017  cmp     ebp, 3
0x18006e01a  jz      short loc_18006E035
0x18006e01c  mov     rax, [rdi+8]
0x18006e020  shl     ebp, 10h
0x18006e023  movsxd  rcx, dword ptr [rax+4]
0x18006e027  xor     ebp, [rcx+rdi+0Ch]
0x18006e02b  and     ebp, 3F0000h
0x18006e031  xor     [rcx+rdi+0Ch], ebp
0x18006e035  cmp     r12d, 1
0x18006e039  jz      loc_18006E0D4
0x18006e03f  mov     edx, [rsp+0F8h+arg_20]
0x18006e046  mov     r8d, [rsp+0F8h+arg_18]
0x18006e04e  test    r12d, r12d
0x18006e051  jnz     short loc_18006E05C
0x18006e053  test    r8d, r8d
0x18006e056  jnz     short loc_18006E05C
0x18006e058  test    edx, edx
0x18006e05a  jz      short loc_18006E0B4
0x18006e05c  mov     rax, [rdi+8]
0x18006e060  shl     edx, 10h
0x18006e063  shl     r12d, 1Bh
0x18006e067  shl     r13d, 4
0x18006e06b  movsxd  rcx, dword ptr [rax+4]
0x18006e06f  and     dword ptr [rcx+rdi+8], 7FFFFFFh
0x18006e077  or      [rcx+rdi+8], r12d
0x18006e07c  mov     rax, [rdi+8]
0x18006e080  movsxd  rcx, dword ptr [rax+4]
0x18006e084  mov     [rcx+rdi+9], r8b
0x18006e089  mov     rax, [rdi+8]
0x18006e08d  movsxd  rcx, dword ptr [rax+4]
0x18006e091  xor     edx, [rcx+rdi+8]
0x18006e095  and     edx, 7FF0000h
0x18006e09b  xor     [rcx+rdi+8], edx
0x18006e09f  mov     rax, [rdi+8]
0x18006e0a3  movsxd  rcx, dword ptr [rax+4]
0x18006e0a7  and     dword ptr [rcx+rdi+8], 0FFFFFF0Fh
0x18006e0af  or      [rcx+rdi+8], r13d
0x18006e0b4  mov     edx, [rsi+48h]
0x18006e0b7  test    edx, edx
0x18006e0b9  jz      short loc_18006E0D4
0x18006e0bb  mov     rax, [rdi+8]
0x18006e0bf  shl     edx, 4
0x18006e0c2  movsxd  rcx, dword ptr [rax+4]
0x18006e0c6  xor     edx, [rcx+rdi+8]
0x18006e0ca  and     edx, 0F0h
0x18006e0d0  xor     [rcx+rdi+8], edx
0x18006e0d4  mov     rcx, [rsi+18h]
0x18006e0d8  mov     rax, [rcx]
0x18006e0db  mov     rax, [rax+70h]
0x18006e0df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006e0e4  cmp     byte ptr [rsi+58h], 0
0x18006e0e8  mov     rbp, rax
0x18006e0eb  jz      short loc_18006E15C
0x18006e0ed  mov     rcx, [rsi+10h]; this
0x18006e0f1  mov     r8, r14; unsigned __int64
0x18006e0f4  mov     rdx, [rcx+8]
0x18006e0f8  dec     rdx
0x18006e0fb  add     rdx, r15; unsigned __int64
0x18006e0fe  call    ?IsNormalized@CSentence@@QEBA_N_K0@Z; CSentence::IsNormalized(unsigned __int64,unsigned __int64)
0x18006e103  test    al, al
0x18006e105  jz      short loc_18006E15C
0x18006e107  mov     rcx, [rdi+8]
0x18006e10b  mov     rdx, rbp; struct CZoneHeap *
0x18006e10e  movsxd  rcx, dword ptr [rcx+4]
0x18006e112  add     rcx, 8
0x18006e116  add     rcx, rdi; this
0x18006e119  call    ?NewProperties@CMorphNode@@QEAAPEAVCNodeProperties@@AEAVCZoneHeap@@@Z; CMorphNode::NewProperties(CZoneHeap &)
0x18006e11e  mov     rcx, [rsi+10h]
0x18006e122  mov     rbx, rax
0x18006e125  mov     rdx, [rcx]
0x18006e128  mov     rax, [rdx+40h]
0x18006e12c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006e131  mov     rdx, [rsi+10h]
0x18006e135  mov     r8, rbp
0x18006e138  mov     [rsp+0F8h+var_D0], 0F2h
0x18006e140  mov     rcx, rbx
0x18006e143  mov     [rsp+0F8h+var_D8], r14
0x18006e148  lea     r9, [rax-2]
0x18006e14c  mov     rdx, [rdx+0A8h]
0x18006e153  lea     r9, [r9+r15*2]
0x18006e157  call    ?AddNormalizedString@CNodeProperties@@QEAAPEAVCNodeProperty@@PEAVCText@@AEAVCZoneHeap@@PEBG_KW4EMorphUnit@CMorphBits@@@Z; CNodeProperties::AddNormalizedString(CText *,CZoneHeap &,ushort const *,unsigned __int64,CMorphBits::EMorphUnit)
0x18006e15c  cmp     [rsp+0F8h+arg_30], 0
0x18006e164  jz      short loc_18006E17C
0x18006e166  mov     rax, [rsi]
0x18006e169  mov     rcx, rsi
0x18006e16c  mov     edx, [rsp+0F8h+arg_8]
0x18006e173  mov     rax, [rax+8]
0x18006e177  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006e17c  mov     rbx, [rsp+0F8h+arg_10]
0x18006e184  mov     rax, rdi
0x18006e187  add     rsp, 0C0h
0x18006e18e  pop     r15
0x18006e190  pop     r14
0x18006e192  pop     r13
0x18006e194  pop     r12
0x18006e196  pop     rdi
0x18006e197  pop     rsi
0x18006e198  pop     rbp
0x18006e199  retn
```
