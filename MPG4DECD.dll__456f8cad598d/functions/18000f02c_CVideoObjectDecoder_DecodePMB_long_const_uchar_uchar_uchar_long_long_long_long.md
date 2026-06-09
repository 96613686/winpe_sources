# CVideoObjectDecoder::DecodePMB(long const *,uchar *,uchar *,uchar *,long,long,long,long)

- ea: `0x18000f02c`
- end: `0x18000f4ef`
- name: `?DecodePMB@CVideoObjectDecoder@@AEAAJPEBJPEAE11JJJJ@Z`
- size: `1219`
- prototype: `__int64 __fastcall(CVideoObjectDecoder *__hidden this, const int *, unsigned __int8 *, unsigned __int8 *, unsigned __int8 *, int, int, int, int)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x1800106c0`
- `0x180011040`
- `0x180011aa8`

## callees

- `0x18000f02c`
- `0x180022010`

## pseudocode

```c
__int64 __fastcall CVideoObjectDecoder::DecodePMB(
        CVideoObjectDecoder *this,
        const int *a2,
        unsigned __int8 *a3,
        unsigned __int8 *a4,
        unsigned __int8 *a5,
        int a6,
        int a7,
        int a8,
        int a9)
{
  char *v9; // r14
  __int64 v10; // r13
  int v12; // ecx
  __int64 v14; // r12
  BOOL v15; // ebp
  BOOL v16; // esi
  __int64 result; // rax
  unsigned __int8 *v18; // r15
  __int64 v19; // r12
  __int64 v20; // rax
  unsigned __int8 *v21; // r15
  __int64 v22; // r13
  __int64 v23; // r12
  __int64 v24; // rax
  const int *v25; // r13
  int v26; // edx
  BOOL v27; // esi
  BOOL v28; // ebp
  __int64 v29; // r15
  __int64 v30; // r15
  __int64 v31; // [rsp+90h] [rbp+8h]
  __int64 v32; // [rsp+90h] [rbp+8h]
  __int64 v33; // [rsp+90h] [rbp+8h]
  __int64 v35; // [rsp+98h] [rbp+10h]

  v9 = (char *)this + 1616;
  v10 = *((_QWORD *)this + 439);
  v12 = *((_DWORD *)this + 84);
  v31 = v10;
  v14 = *((_QWORD *)this + 29) + ((__int64)a6 >> 1) + v12 * ((a7 >> 1) + 32);
  v15 = (a6 & 1) == 0;
  v16 = (a7 & 1) == 0;
  if ( *a2 )
  {
    result = (*((__int64 (__fastcall **)(CVideoObjectDecoder *, __int64))this + 457))(this, v10);
    if ( (_DWORD)result )
      return result;
    (*((void (__fastcall **)(char *, __int64, _QWORD))this + 450))(v9, 8, *((unsigned int *)this + 916));
    (*((void (__fastcall **)(unsigned __int8 *, char *, __int64, _QWORD, BOOL, BOOL))this + 455))(
      a3,
      v9,
      v14 + 32,
      *((unsigned int *)this + 84),
      v15,
      v16);
  }
  else
  {
    (*((void (__fastcall **)(__int64, __int64, unsigned __int8 *, __int64, int, int, bool, bool, int))this + 456))(
      1,
      1,
      a3,
      v14 + 32,
      v12,
      v12,
      (a6 & 1) == 0,
      (a7 & 1) == 0,
      8);
  }
  v18 = a3 + 8;
  v19 = v14 + 40;
  if ( a2[1] )
  {
    result = (*((__int64 (__fastcall **)(CVideoObjectDecoder *, __int64))this + 457))(this, v10);
    if ( (_DWORD)result )
      return result;
    (*((void (__fastcall **)(char *, __int64, _QWORD))this + 450))(v9, 8, *((unsigned int *)this + 916));
    (*((void (__fastcall **)(unsigned __int8 *, char *, __int64, _QWORD, BOOL, BOOL))this + 455))(
      v18,
      v9,
      v19,
      *((unsigned int *)this + 84),
      v15,
      v16);
  }
  else
  {
    (*((void (__fastcall **)(__int64, __int64, unsigned __int8 *, __int64, _DWORD, _DWORD, BOOL, BOOL, int))this + 456))(
      1,
      1,
      v18,
      v19,
      *((_DWORD *)this + 84),
      *((_DWORD *)this + 84),
      v15,
      v16,
      8);
  }
  v20 = *((int *)this + 924);
  v21 = &v18[v20];
  v22 = v20 + v19;
  if ( a2[2] )
  {
    v23 = v31;
    result = (*((__int64 (__fastcall **)(CVideoObjectDecoder *, __int64))this + 457))(this, v31);
    if ( (_DWORD)result )
      return result;
    (*((void (__fastcall **)(char *, __int64, _QWORD))this + 450))(v9, 8, *((unsigned int *)this + 916));
    (*((void (__fastcall **)(unsigned __int8 *, char *, __int64, _QWORD, BOOL, BOOL))this + 455))(
      v21,
      v9,
      v22,
      *((unsigned int *)this + 84),
      v15,
      v16);
  }
  else
  {
    (*((void (__fastcall **)(__int64, __int64, unsigned __int8 *, __int64, _DWORD, _DWORD, BOOL, BOOL, int))this + 456))(
      1,
      1,
      v21,
      v22,
      *((_DWORD *)this + 84),
      *((_DWORD *)this + 84),
      v15,
      v16,
      8);
    v23 = v31;
  }
  v24 = v22 + 8;
  v25 = a2;
  v32 = v24;
  if ( a2[3] )
  {
    result = (*((__int64 (__fastcall **)(CVideoObjectDecoder *, __int64))this + 457))(this, v23);
    if ( (_DWORD)result )
      return result;
    (*((void (__fastcall **)(char *, __int64, _QWORD))this + 450))(v9, 8, *((unsigned int *)this + 916));
    (*((void (__fastcall **)(unsigned __int8 *, char *, __int64, _QWORD, BOOL, BOOL))this + 455))(
      v21 + 8,
      v9,
      v32,
      *((unsigned int *)this + 84),
      v15,
      v16);
  }
  else
  {
    (*((void (__fastcall **)(__int64, __int64, unsigned __int8 *, __int64, _DWORD, _DWORD, BOOL, BOOL, int))this + 456))(
      1,
      1,
      v21 + 8,
      v24,
      *((_DWORD *)this + 84),
      *((_DWORD *)this + 84),
      v15,
      v16,
      8);
  }
  v26 = *((_DWORD *)this + 85);
  v27 = (a8 & 1) == 0;
  v28 = (a9 & 1) == 0;
  v29 = (a8 >> 1) + 16 + v26 * ((a9 >> 1) + 16);
  v33 = *((_QWORD *)this + 31);
  v35 = v29 + *((_QWORD *)this + 30);
  if ( v25[4] )
  {
    result = (*((__int64 (__fastcall **)(CVideoObjectDecoder *, __int64))this + 457))(this, v23);
    if ( (_DWORD)result )
      return result;
    (*((void (__fastcall **)(char *, __int64, _QWORD))this + 450))(v9, 8, *((unsigned int *)this + 916));
    (*((void (__fastcall **)(unsigned __int8 *, char *, __int64, _QWORD, BOOL, BOOL))this + 455))(
      a4,
      v9,
      v35,
      *((unsigned int *)this + 85),
      v27,
      v28);
  }
  else
  {
    (*((void (__fastcall **)(__int64, __int64, unsigned __int8 *, __int64, int, int, bool, bool, int))this + 456))(
      1,
      1,
      a4,
      v29 + *((_QWORD *)this + 30),
      v26,
      v26,
      (a8 & 1) == 0,
      (a9 & 1) == 0,
      8);
  }
  v30 = v33 + v29;
  if ( v25[5] )
  {
    result = (*((__int64 (__fastcall **)(CVideoObjectDecoder *, __int64))this + 457))(this, v23);
    if ( (_DWORD)result )
      return result;
    (*((void (__fastcall **)(char *, __int64, _QWORD))this + 450))(v9, 8, *((unsigned int *)this + 916));
    (*((void (__fastcall **)(unsigned __int8 *, char *, __int64, _QWORD, BOOL, BOOL))this + 455))(
      a5,
      v9,
      v30,
      *((unsigned int *)this + 85),
      v27,
      v28);
  }
  else
  {
    (*((void (__fastcall **)(__int64, __int64, unsigned __int8 *, __int64, _DWORD, _DWORD, BOOL, BOOL, int))this + 456))(
      1,
      1,
      a5,
      v30,
      *((_DWORD *)this + 85),
      *((_DWORD *)this + 85),
      v27,
      v28,
      8);
  }
  return 0;
}

```

## disassembly

```asm
0x18000f02c  mov     [rsp+arg_10], rbx
0x18000f031  mov     [rsp+arg_18], r9
0x18000f036  mov     [rsp+arg_8], rdx
0x18000f03b  push    rbp
0x18000f03c  push    rsi
0x18000f03d  push    rdi
0x18000f03e  push    r12
0x18000f040  push    r13
0x18000f042  push    r14
0x18000f044  push    r15
0x18000f046  sub     rsp, 50h
0x18000f04a  mov     esi, [rsp+88h+arg_30]
0x18000f051  lea     r14, [rcx+650h]
0x18000f058  mov     r13, [rcx+0DB8h]
0x18000f05f  mov     eax, esi
0x18000f061  movsxd  rbp, [rsp+88h+arg_28]
0x18000f069  mov     rbx, rcx
0x18000f06c  mov     ecx, [rcx+150h]
0x18000f072  not     esi
0x18000f074  sar     eax, 1
0x18000f076  mov     r15, r8
0x18000f079  add     eax, 20h ; ' '
0x18000f07c  mov     [rsp+88h+arg_0], r13
0x18000f084  imul    eax, ecx
0x18000f087  movsxd  r12, eax
0x18000f08a  mov     rax, rbp
0x18000f08d  sar     rax, 1
0x18000f090  not     ebp
0x18000f092  add     r12, rax
0x18000f095  mov     eax, 1
0x18000f09a  add     r12, [rbx+0E8h]
0x18000f0a1  and     ebp, eax
0x18000f0a3  and     esi, eax
0x18000f0a5  cmp     dword ptr [rdx], 0
0x18000f0a8  jz      short loc_18000F107
0x18000f0aa  mov     rax, [rbx+0E48h]
0x18000f0b1  mov     rdx, r13
0x18000f0b4  mov     rcx, rbx
0x18000f0b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f0bc  test    eax, eax
0x18000f0be  jnz     loc_18000F4D7
0x18000f0c4  mov     r8d, [rbx+0E50h]
0x18000f0cb  lea     edi, [rax+8]
0x18000f0ce  mov     rax, [rbx+0E10h]
0x18000f0d5  mov     edx, edi
0x18000f0d7  mov     rcx, r14
0x18000f0da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f0df  mov     r9d, [rbx+150h]
0x18000f0e6  lea     r8, [r12+20h]
0x18000f0eb  mov     rax, [rbx+0E38h]
0x18000f0f2  mov     rdx, r14
0x18000f0f5  mov     rcx, r15
0x18000f0f8  mov     [rsp+88h+var_60], esi
0x18000f0fc  mov     [rsp+88h+var_68], ebp
0x18000f100  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f105  jmp     short loc_18000F135
0x18000f107  mov     edx, eax
0x18000f109  lea     r9, [r12+20h]
0x18000f10e  mov     edi, 8
0x18000f113  mov     [rsp+88h+var_48], edi
0x18000f117  mov     [rsp+88h+var_50], esi
0x18000f11b  mov     [rsp+88h+var_58], ebp
0x18000f11f  mov     [rsp+88h+var_60], ecx
0x18000f123  mov     [rsp+88h+var_68], ecx
0x18000f127  mov     ecx, eax
0x18000f129  mov     rax, [rbx+0E40h]
0x18000f130  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f135  mov     rax, [rsp+88h+arg_8]
0x18000f13d  add     r15, 8
0x18000f141  add     r12, 28h ; '('
0x18000f145  cmp     dword ptr [rax+4], 0
0x18000f149  jz      short loc_18000F1A3
0x18000f14b  mov     rax, [rbx+0E48h]
0x18000f152  mov     rdx, r13
0x18000f155  mov     rcx, rbx
0x18000f158  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f15d  test    eax, eax
0x18000f15f  jnz     loc_18000F4D7
0x18000f165  mov     r8d, [rbx+0E50h]
0x18000f16c  mov     edx, edi
0x18000f16e  mov     rax, [rbx+0E10h]
0x18000f175  mov     rcx, r14
0x18000f178  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f17d  mov     r9d, [rbx+150h]
0x18000f184  mov     r8, r12
0x18000f187  mov     rax, [rbx+0E38h]
0x18000f18e  mov     rdx, r14
0x18000f191  mov     rcx, r15
0x18000f194  mov     [rsp+88h+var_60], esi
0x18000f198  mov     [rsp+88h+var_68], ebp
0x18000f19c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f1a1  jmp     short loc_18000F1D6
0x18000f1a3  mov     ecx, [rbx+150h]
0x18000f1a9  mov     r9, r12
0x18000f1ac  mov     rax, [rbx+0E40h]
0x18000f1b3  mov     r8, r15
0x18000f1b6  mov     [rsp+88h+var_48], edi
0x18000f1ba  mov     [rsp+88h+var_50], esi
0x18000f1be  mov     [rsp+88h+var_58], ebp
0x18000f1c2  mov     [rsp+88h+var_60], ecx
0x18000f1c6  mov     [rsp+88h+var_68], ecx
0x18000f1ca  mov     ecx, 1
0x18000f1cf  mov     edx, ecx
0x18000f1d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f1d6  movsxd  rax, dword ptr [rbx+0E70h]
0x18000f1dd  add     r15, rax
0x18000f1e0  lea     r13, [rax+r12]
0x18000f1e4  mov     rax, [rsp+88h+arg_8]
0x18000f1ec  cmp     dword ptr [rax+8], 0
0x18000f1f0  jz      short loc_18000F252
0x18000f1f2  mov     r12, [rsp+88h+arg_0]
0x18000f1fa  mov     rcx, rbx
0x18000f1fd  mov     rax, [rbx+0E48h]
0x18000f204  mov     rdx, r12
0x18000f207  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f20c  test    eax, eax
0x18000f20e  jnz     loc_18000F4D7
0x18000f214  mov     r8d, [rbx+0E50h]
0x18000f21b  mov     edx, edi
0x18000f21d  mov     rax, [rbx+0E10h]
0x18000f224  mov     rcx, r14
0x18000f227  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f22c  mov     r9d, [rbx+150h]
0x18000f233  mov     r8, r13
0x18000f236  mov     rax, [rbx+0E38h]
0x18000f23d  mov     rdx, r14
0x18000f240  mov     rcx, r15
0x18000f243  mov     [rsp+88h+var_60], esi
0x18000f247  mov     [rsp+88h+var_68], ebp
0x18000f24b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f250  jmp     short loc_18000F28F
0x18000f252  mov     ecx, [rbx+150h]
0x18000f258  mov     eax, 1
0x18000f25d  mov     [rsp+88h+var_48], edi
0x18000f261  mov     edx, eax
0x18000f263  mov     [rsp+88h+var_50], esi
0x18000f267  mov     r9, r13
0x18000f26a  mov     [rsp+88h+var_58], ebp
0x18000f26e  mov     r8, r15
0x18000f271  mov     [rsp+88h+var_60], ecx
0x18000f275  mov     [rsp+88h+var_68], ecx
0x18000f279  mov     ecx, eax
0x18000f27b  mov     rax, [rbx+0E40h]
0x18000f282  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f287  mov     r12, [rsp+88h+arg_0]
0x18000f28f  lea     rax, [r13+8]
0x18000f293  mov     r13, [rsp+88h+arg_8]
0x18000f29b  mov     [rsp+88h+arg_0], rax
0x18000f2a3  cmp     dword ptr [r13+0Ch], 0
0x18000f2a8  jz      short loc_18000F308
0x18000f2aa  mov     rax, [rbx+0E48h]
0x18000f2b1  mov     rdx, r12
0x18000f2b4  mov     rcx, rbx
0x18000f2b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f2bc  test    eax, eax
0x18000f2be  jnz     loc_18000F4D7
0x18000f2c4  mov     r8d, [rbx+0E50h]
0x18000f2cb  mov     edx, edi
0x18000f2cd  mov     rax, [rbx+0E10h]
0x18000f2d4  mov     rcx, r14
0x18000f2d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f2dc  mov     r9d, [rbx+150h]
0x18000f2e3  lea     rcx, [r15+8]
0x18000f2e7  mov     r8, [rsp+88h+arg_0]
0x18000f2ef  mov     rdx, r14
0x18000f2f2  mov     rax, [rbx+0E38h]
0x18000f2f9  mov     [rsp+88h+var_60], esi
0x18000f2fd  mov     [rsp+88h+var_68], ebp
0x18000f301  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f306  jmp     short loc_18000F33E
0x18000f308  mov     ecx, [rbx+150h]
0x18000f30e  lea     r8, [r15+8]
0x18000f312  mov     [rsp+88h+var_48], edi
0x18000f316  mov     r9, rax
0x18000f319  mov     [rsp+88h+var_50], esi
0x18000f31d  mov     eax, 1
0x18000f322  mov     [rsp+88h+var_58], ebp
0x18000f326  mov     edx, eax
0x18000f328  mov     [rsp+88h+var_60], ecx
0x18000f32c  mov     [rsp+88h+var_68], ecx
0x18000f330  mov     ecx, eax
0x18000f332  mov     rax, [rbx+0E40h]
0x18000f339  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f33e  mov     eax, [rsp+88h+arg_40]
0x18000f345  mov     r10d, 1
0x18000f34b  mov     ecx, [rsp+88h+arg_38]
0x18000f352  mov     ebp, eax
0x18000f354  mov     edx, [rbx+154h]
0x18000f35a  mov     esi, ecx
0x18000f35c  sar     eax, 1
0x18000f35e  not     esi
0x18000f360  add     eax, 10h
0x18000f363  sar     ecx, 1
0x18000f365  imul    eax, edx
0x18000f368  add     ecx, 10h
0x18000f36b  not     ebp
0x18000f36d  and     esi, r10d
0x18000f370  and     ebp, r10d
0x18000f373  add     eax, ecx
0x18000f375  mov     rcx, [rbx+0F8h]
0x18000f37c  movsxd  r15, eax
0x18000f37f  mov     rax, [rbx+0F0h]
0x18000f386  add     rax, r15
0x18000f389  mov     [rsp+88h+arg_0], rcx
0x18000f391  cmp     dword ptr [r13+10h], 0
0x18000f396  mov     [rsp+88h+arg_8], rax
0x18000f39e  jz      short loc_18000F402
0x18000f3a0  mov     rax, [rbx+0E48h]
0x18000f3a7  mov     rdx, r12
0x18000f3aa  mov     rcx, rbx
0x18000f3ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f3b2  test    eax, eax
0x18000f3b4  jnz     loc_18000F4D7
0x18000f3ba  mov     r8d, [rbx+0E50h]
0x18000f3c1  mov     edx, edi
0x18000f3c3  mov     rax, [rbx+0E10h]
0x18000f3ca  mov     rcx, r14
0x18000f3cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f3d2  mov     r9d, [rbx+154h]
0x18000f3d9  mov     rdx, r14
0x18000f3dc  mov     r8, [rsp+88h+arg_8]
0x18000f3e4  mov     rcx, [rsp+88h+arg_18]
0x18000f3ec  mov     rax, [rbx+0E38h]
0x18000f3f3  mov     [rsp+88h+var_60], ebp
0x18000f3f7  mov     [rsp+88h+var_68], esi
0x18000f3fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f400  jmp     short loc_18000F433
0x18000f402  mov     r8, [rsp+88h+arg_18]
0x18000f40a  mov     r9, rax
0x18000f40d  mov     rax, [rbx+0E40h]
0x18000f414  mov     ecx, r10d
0x18000f417  mov     [rsp+88h+var_48], edi
0x18000f41b  mov     [rsp+88h+var_50], ebp
0x18000f41f  mov     [rsp+88h+var_58], esi
0x18000f423  mov     [rsp+88h+var_60], edx
0x18000f427  mov     [rsp+88h+var_68], edx
0x18000f42b  mov     edx, r10d
0x18000f42e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f433  add     r15, [rsp+88h+arg_0]
0x18000f43b  cmp     dword ptr [r13+14h], 0
0x18000f440  jz      short loc_18000F49B
0x18000f442  mov     rax, [rbx+0E48h]
0x18000f449  mov     rdx, r12
0x18000f44c  mov     rcx, rbx
0x18000f44f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f454  test    eax, eax
0x18000f456  jnz     short loc_18000F4D7
0x18000f458  mov     r8d, [rbx+0E50h]
0x18000f45f  mov     edx, edi
0x18000f461  mov     rax, [rbx+0E10h]
0x18000f468  mov     rcx, r14
0x18000f46b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f470  mov     r9d, [rbx+154h]
0x18000f477  mov     r8, r15
0x18000f47a  mov     rcx, [rsp+88h+arg_20]
0x18000f482  mov     rdx, r14
0x18000f485  mov     rax, [rbx+0E38h]
0x18000f48c  mov     [rsp+88h+var_60], ebp
0x18000f490  mov     [rsp+88h+var_68], esi
0x18000f494  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f499  jmp     short loc_18000F4D5
0x18000f49b  mov     edx, [rbx+154h]
0x18000f4a1  mov     eax, 1
0x18000f4a6  mov     r8, [rsp+88h+arg_20]
0x18000f4ae  mov     ecx, eax
0x18000f4b0  mov     [rsp+88h+var_48], edi
0x18000f4b4  mov     r9, r15
0x18000f4b7  mov     [rsp+88h+var_50], ebp
0x18000f4bb  mov     [rsp+88h+var_58], esi
0x18000f4bf  mov     [rsp+88h+var_60], edx
0x18000f4c3  mov     [rsp+88h+var_68], edx
0x18000f4c7  mov     edx, eax
0x18000f4c9  mov     rax, [rbx+0E40h]
0x18000f4d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f4d5  xor     eax, eax
0x18000f4d7  mov     rbx, [rsp+88h+arg_10]
0x18000f4df  add     rsp, 50h
0x18000f4e3  pop     r15
0x18000f4e5  pop     r14
0x18000f4e7  pop     r13
0x18000f4e9  pop     r12
0x18000f4eb  pop     rdi
0x18000f4ec  pop     rsi
0x18000f4ed  pop     rbp
0x18000f4ee  retn
```
