# Common::DirectoryTreeWalker::Walk(ushort const *,uint)

- ea: `0x180018ffc`
- end: `0x1800194d1`
- name: `?Walk@DirectoryTreeWalker@Common@@QEAAJPEBGI@Z`
- size: `1237`
- prototype: `__int64 __fastcall(__int64 **this, const unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x1800194d8`

## callees

- `0x18000be00`
- `0x18000be3c`
- `0x180018968`
- `0x180018a28`
- `0x180018aac`
- `0x180018b90`
- `0x180018cc4`
- `0x180018ef0`
- `0x180018ffc`
- `0x18001b30a`
- `0x18001b340`
- `0x18001c010`

## pseudocode

```c
__int64 __fastcall Common::DirectoryTreeWalker::Walk(__int64 **this, const unsigned __int16 *a2, int a3)
{
  unsigned int v5; // ebx
  int v7; // r14d
  __int64 *v8; // rcx
  __int64 *v9; // rdx
  __int64 (__fastcall *v10)(__int64, __int64, __int64 *, struct _WIN32_FIND_DATAW *); // rax
  unsigned int v11; // eax
  Common::DirectoryTreeWalker *i; // rcx
  unsigned int Handle; // edi
  PVOID v14; // rcx
  void *v15; // r12
  struct _WIN32_FIND_DATAW *v16; // rbx
  unsigned __int16 *v17; // r8
  unsigned __int64 v18; // rdx
  __int64 *v19; // rcx
  __int64 *v20; // rax
  unsigned int v21; // eax
  unsigned __int64 v22; // rdx
  __int64 *v23; // rbx
  int v24; // r15d
  __int64 *v25; // rcx
  __int64 *v26; // rdx
  struct _WIN32_FIND_DATAW *v27; // rbx
  __int64 (__fastcall *v28)(__int64, __int64, __int64 *, struct _WIN32_FIND_DATAW *); // rax
  unsigned __int16 *v29; // r8
  unsigned __int64 v30; // rdx
  __int64 *v31; // rcx
  __int64 *v32; // rax
  __int64 *v33; // rdx
  int v34; // [rsp+30h] [rbp-D0h] BYREF
  PVOID P; // [rsp+38h] [rbp-C8h] BYREF
  int v36; // [rsp+40h] [rbp-C0h]
  void *v37[3]; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v38; // [rsp+60h] [rbp-A0h] BYREF
  __int64 *v39; // [rsp+68h] [rbp-98h]
  __int64 *v40; // [rsp+70h] [rbp-90h]
  struct _WIN32_FIND_DATAW v41; // [rsp+80h] [rbp-80h] BYREF

  v37[1] = this[9];
  v37[2] = this[6];
  v37[0] = 0;
  P = 0;
  v5 = Common::DirectoryTreeWalker::InitializePath((Common::DirectoryTreeWalker *)this, a2);
  if ( v5 )
    goto LABEL_2;
  *((_DWORD *)this + 8) = a3;
  v7 = 0;
  v36 = a3 & 2;
  if ( (a3 & 2) != 0 && (a3 & 1) == 0 )
  {
    memset_0(&v41, 0, sizeof(v41));
    v8 = this[6];
    v9 = this[1];
    v39 = this[9];
    v10 = (__int64 (__fastcall *)(__int64, __int64, __int64 *, struct _WIN32_FIND_DATAW *))this[7];
    v38 = 0;
    v40 = v8;
    v11 = v10((__int64)v8, (__int64)v9, &v38, &v41);
    v5 = v11;
    if ( v11 - 2 > 1 )
    {
      v34 = 0;
      if ( v11
        || (v5 = Common::DirectoryTreeWalker::Visit(
                   (Common::DirectoryTreeWalker *)this,
                   (unsigned __int64)this[2],
                   (unsigned __int16 *)this[1],
                   &v41,
                   &v34)) != 0 )
      {
        anonymous_namespace_::FindFileHandle::Close(&v38);
LABEL_2:
        Common::GlobalHeap::Free(0);
        anonymous_namespace_::FindFileHandle::Close(v37);
        return v5;
      }
      if ( v34 )
        v7 = v34;
    }
    anonymous_namespace_::FindFileHandle::Close(&v38);
  }
  Handle = Common::DirectoryTreeWalker::GetFirstFindHandle(
             (Common::DirectoryTreeWalker *)this,
             v37,
             (struct _WIN32_FIND_DATAW **)&P);
  if ( Handle )
  {
    v14 = P;
  }
  else
  {
    while ( 1 )
    {
      v15 = v37[0];
      v16 = (struct _WIN32_FIND_DATAW *)P;
LABEL_16:
      if ( !Common::DirectoryTreeWalker::IsDirAndShouldBeWalked(i, v16) )
        break;
      if ( v16->cFileName[0] == 46 && (!v16->cFileName[1] || v16->cFileName[1] == 46 && !v16->cFileName[2]) )
        goto LABEL_38;
      Handle = Common::DirectoryTreeWalker::AppendNameToDirPath((Common::DirectoryTreeWalker *)this, v16->cFileName);
      if ( Handle )
        goto LABEL_33;
      if ( v36 )
      {
        v17 = (unsigned __int16 *)this[1];
        v18 = (unsigned __int64)this[2];
        v34 = 0;
        Handle = Common::DirectoryTreeWalker::Visit((Common::DirectoryTreeWalker *)this, v18, v17, v16, &v34);
        if ( Handle )
          goto LABEL_33;
        if ( v34 && v34 != 3 && !v7 )
          v7 = v34;
      }
      P = 0;
      Common::GlobalHeap::Alloc(0x18u, &P);
      v19 = (__int64 *)P;
      if ( !P )
      {
        Handle = 14;
        goto LABEL_33;
      }
      v20 = *this;
      *((_QWORD *)P + 1) = v15;
      *v19 = (__int64)v20;
      v19[2] = (__int64)v16;
      *this = v19;
      P = 0;
      v37[0] = 0;
      v21 = Common::DirectoryTreeWalker::GetFirstFindHandle(
              (Common::DirectoryTreeWalker *)this,
              v37,
              (struct _WIN32_FIND_DATAW **)&P);
      Handle = v21;
      if ( v21 == 2 )
      {
        v16 = (struct _WIN32_FIND_DATAW *)P;
        Handle = 18;
        goto LABEL_43;
      }
      if ( v21 )
      {
        v16 = (struct _WIN32_FIND_DATAW *)P;
        if ( v21 == 3 )
          goto LABEL_43;
        goto LABEL_33;
      }
    }
    v22 = (unsigned __int64)this[2];
    v34 = 0;
    Handle = Common::DirectoryTreeWalker::Visit(
               (Common::DirectoryTreeWalker *)this,
               v22,
               (unsigned __int16 *)this[1],
               v16,
               &v34);
    if ( Handle )
    {
LABEL_33:
      v14 = v16;
      goto LABEL_34;
    }
    Handle = v34;
LABEL_38:
    if ( Handle )
    {
      if ( Handle == 18 )
        goto LABEL_43;
      if ( Handle == 3 )
        goto LABEL_15;
      if ( !v7 )
        v7 = Handle;
LABEL_74:
      if ( Handle != 3 )
        Handle = ((__int64 (__fastcall *)(__int64 *, void *, struct _WIN32_FIND_DATAW *))this[8])(this[6], v15, v16);
      goto LABEL_15;
    }
    while ( 1 )
    {
      if ( Handle != 18 )
        goto LABEL_74;
LABEL_15:
      if ( !Handle )
        goto LABEL_16;
LABEL_43:
      Common::GlobalHeap::Free(v16);
      anonymous_namespace_::FindFileHandle::Close(v37);
      if ( Handle != 18 && Handle != 3 )
        goto LABEL_81;
      v23 = *this;
      if ( *this )
      {
        v24 = 0;
      }
      else
      {
        v24 = 1;
        if ( (a3 & 3) != 0 )
          break;
      }
      memset_0(&v41, 0, sizeof(v41));
      if ( v24 )
      {
        v25 = this[6];
        v26 = this[1];
        v27 = 0;
        v39 = this[9];
        v28 = (__int64 (__fastcall *)(__int64, __int64, __int64 *, struct _WIN32_FIND_DATAW *))this[7];
        v38 = 0;
        v40 = v25;
        Handle = v28((__int64)v25, (__int64)v26, &v38, &v41);
        if ( Handle - 2 > 1 )
        {
          if ( Handle )
          {
            anonymous_namespace_::FindFileHandle::Close(&v38);
            goto LABEL_81;
          }
          v27 = &v41;
        }
        anonymous_namespace_::FindFileHandle::Close(&v38);
      }
      else
      {
        v27 = v23 ? (struct _WIN32_FIND_DATAW *)v23[2] : 0LL;
      }
      if ( Handle - 2 <= 1 || v36 )
      {
        Handle = 0;
      }
      else
      {
        v29 = (unsigned __int16 *)this[1];
        v30 = (unsigned __int64)this[2];
        v34 = 0;
        Handle = Common::DirectoryTreeWalker::Visit((Common::DirectoryTreeWalker *)this, v30, v29, v27, &v34);
        if ( Handle )
          goto LABEL_81;
        Handle = v34;
        if ( v34 && v34 != 3 && !v7 )
          v7 = v34;
      }
      if ( v24 )
        break;
      v31 = *this;
      v15 = (void *)(*this)[1];
      v32 = (__int64 *)**this;
      v16 = (struct _WIN32_FIND_DATAW *)(*this)[2];
      v37[0] = v15;
      *this = v32;
      Common::GlobalHeap::Free(v31);
      for ( i = (Common::DirectoryTreeWalker *)((char *)this[2] - 1); i; i = (Common::DirectoryTreeWalker *)((char *)i - 1) )
      {
        v33 = this[1];
        if ( *((_WORD *)v33 + (_QWORD)i) == 92 )
        {
          *((_WORD *)v33 + (_QWORD)i) = 0;
          break;
        }
      }
      this[2] = (__int64 *)i;
    }
    if ( v7 )
    {
      Common::GlobalHeap::Free(0);
      Handle = v7;
      goto LABEL_35;
    }
    if ( Handle == 18 || Handle == 3 )
      Handle = 0;
LABEL_81:
    v14 = 0;
  }
LABEL_34:
  Common::GlobalHeap::Free(v14);
LABEL_35:
  anonymous_namespace_::FindFileHandle::Close(v37);
  return Handle;
}

```

## disassembly

```asm
0x180018ffc  mov     [rsp-8+arg_10], rbx
0x180019001  push    rbp
0x180019002  push    rsi
0x180019003  push    rdi
0x180019004  push    r12
0x180019006  push    r13
0x180019008  push    r14
0x18001900a  push    r15
0x18001900c  lea     rbp, [rsp-1E0h]
0x180019014  sub     rsp, 2E0h
0x18001901b  mov     rax, cs:__security_cookie
0x180019022  xor     rax, rsp
0x180019025  mov     [rbp+210h+var_40], rax
0x18001902c  mov     rax, [rcx+48h]
0x180019030  xor     r12d, r12d
0x180019033  mov     [rsp+310h+var_2C0], rax
0x180019038  mov     r13d, r8d
0x18001903b  mov     rax, [rcx+30h]
0x18001903f  mov     rsi, rcx
0x180019042  mov     [rsp+310h+var_2B8], rax
0x180019047  mov     [rsp+310h+var_2C8], r12
0x18001904c  mov     [rsp+310h+P], r12
0x180019051  call    ?InitializePath@DirectoryTreeWalker@Common@@AEAAJPEBG@Z; Common::DirectoryTreeWalker::InitializePath(ushort const *)
0x180019056  mov     ebx, eax
0x180019058  test    eax, eax
0x18001905a  jz      short loc_180019074
0x18001905c  xor     ecx, ecx; P
0x18001905e  call    ?Free@GlobalHeap@Common@@SAXPEAX@Z; Common::GlobalHeap::Free(void *)
0x180019063  lea     rcx, [rsp+310h+var_2C8]
0x180019068  call    _anonymous_namespace___FindFileHandle__Close
0x18001906d  mov     eax, ebx
0x18001906f  jmp     loc_1800192A9
0x180019074  mov     eax, r13d
0x180019077  mov     [rsi+20h], r13d
0x18001907b  and     eax, 2
0x18001907e  mov     r14d, r12d
0x180019081  mov     [rsp+310h+var_2D0], eax
0x180019085  jz      loc_18001912D
0x18001908b  test    r13b, 1
0x18001908f  jnz     loc_18001912D
0x180019095  xor     edx, edx; Val
0x180019097  lea     rcx, [rbp+210h+var_290]; void *
0x18001909b  mov     r8d, 250h; Size
0x1800190a1  call    memset_0
0x1800190a6  mov     rax, [rsi+48h]
0x1800190aa  lea     r9, [rbp+210h+var_290]
0x1800190ae  mov     rcx, [rsi+30h]
0x1800190b2  lea     r8, [rsp+310h+var_2B0]
0x1800190b7  mov     rdx, [rsi+8]
0x1800190bb  mov     [rsp+310h+var_2A8], rax
0x1800190c0  mov     rax, [rsi+38h]
0x1800190c4  mov     [rsp+310h+var_2B0], r12
0x1800190c9  mov     [rsp+310h+var_2A0], rcx
0x1800190ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800190d3  mov     ebx, eax
0x1800190d5  lea     ecx, [rax-2]
0x1800190d8  cmp     ecx, 1
0x1800190db  jbe     short loc_180019123
0x1800190dd  mov     [rsp+310h+var_2E0], r12d
0x1800190e2  test    eax, eax
0x1800190e4  jz      short loc_1800190F5
0x1800190e6  lea     rcx, [rsp+310h+var_2B0]
0x1800190eb  call    _anonymous_namespace___FindFileHandle__Close
0x1800190f0  jmp     loc_18001905C
0x1800190f5  mov     r8, [rsi+8]; unsigned __int16 *
0x1800190f9  lea     rax, [rsp+310h+var_2E0]
0x1800190fe  mov     rdx, [rsi+10h]; unsigned __int64
0x180019102  lea     r9, [rbp+210h+var_290]; struct _WIN32_FIND_DATAW *
0x180019106  mov     rcx, rsi; this
0x180019109  mov     [rsp+310h+var_2F0], rax; int *
0x18001910e  call    ?Visit@DirectoryTreeWalker@Common@@AEAAJ_KPEAGPEBU_WIN32_FIND_DATAW@@PEAJ@Z; Common::DirectoryTreeWalker::Visit(unsigned __int64,ushort *,_WIN32_FIND_DATAW const *,long *)
0x180019113  mov     ebx, eax
0x180019115  test    eax, eax
0x180019117  jnz     short loc_1800190E6
0x180019119  mov     eax, [rsp+310h+var_2E0]
0x18001911d  test    eax, eax
0x18001911f  cmovnz  r14d, eax
0x180019123  lea     rcx, [rsp+310h+var_2B0]
0x180019128  call    _anonymous_namespace___FindFileHandle__Close
0x18001912d  lea     r8, [rsp+310h+P]; struct _WIN32_FIND_DATAW **
0x180019132  mov     rcx, rsi; this
0x180019135  lea     rdx, [rsp+310h+var_2C8]; void **
0x18001913a  call    ?GetFirstFindHandle@DirectoryTreeWalker@Common@@AEAAJPEAPEAXPEAPEAU_WIN32_FIND_DATAW@@@Z; Common::DirectoryTreeWalker::GetFirstFindHandle(void * *,_WIN32_FIND_DATAW * *)
0x18001913f  mov     edi, eax
0x180019141  test    eax, eax
0x180019143  jz      short loc_18001914F
0x180019145  mov     rcx, [rsp+310h+P]
0x18001914a  jmp     loc_180019298
0x18001914f  mov     r15d, r12d
0x180019152  mov     r12, [rsp+310h+var_2C8]
0x180019157  mov     rbx, [rsp+310h+P]
0x18001915c  test    r15d, r15d
0x18001915f  jz      short loc_180019184
0x180019161  mov     rcx, [rsi+30h]
0x180019165  mov     r8, rbx
0x180019168  mov     rax, [rsi+40h]
0x18001916c  mov     rdx, r12
0x18001916f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019174  mov     edi, eax
0x180019176  xor     r8d, r8d
0x180019179  test    edi, edi
0x18001917b  jnz     loc_180019329
0x180019181  mov     r15d, r8d
0x180019184  mov     rdx, rbx; struct _WIN32_FIND_DATAW *
0x180019187  call    ?IsDirAndShouldBeWalked@DirectoryTreeWalker@Common@@AEBA_NAEBU_WIN32_FIND_DATAW@@@Z; Common::DirectoryTreeWalker::IsDirAndShouldBeWalked(_WIN32_FIND_DATAW const &)
0x18001918c  xor     r8d, r8d
0x18001918f  test    al, al
0x180019191  jz      loc_1800192D3
0x180019197  lea     rdx, [rbx+2Ch]; unsigned __int16 *
0x18001919b  cmp     word ptr [rdx], 2Eh ; '.'
0x18001919f  jnz     short loc_1800191BE
0x1800191a1  cmp     [rdx+2], r8w
0x1800191a6  jz      loc_180019302
0x1800191ac  cmp     word ptr [rdx+2], 2Eh ; '.'
0x1800191b1  jnz     short loc_1800191BE
0x1800191b3  cmp     [rdx+4], r8w
0x1800191b8  jz      loc_180019302
0x1800191be  mov     rcx, rsi; this
0x1800191c1  call    ?AppendNameToDirPath@DirectoryTreeWalker@Common@@AEAAJPEBG@Z; Common::DirectoryTreeWalker::AppendNameToDirPath(ushort const *)
0x1800191c6  mov     edi, eax
0x1800191c8  test    eax, eax
0x1800191ca  jnz     loc_180019295
0x1800191d0  cmp     [rsp+310h+var_2D0], eax
0x1800191d4  jz      short loc_180019215
0x1800191d6  mov     r8, [rsi+8]; unsigned __int16 *
0x1800191da  mov     r9, rbx; struct _WIN32_FIND_DATAW *
0x1800191dd  mov     rdx, [rsi+10h]; unsigned __int64
0x1800191e1  mov     rcx, rsi; this
0x1800191e4  mov     [rsp+310h+var_2E0], eax
0x1800191e8  lea     rax, [rsp+310h+var_2E0]
0x1800191ed  mov     [rsp+310h+var_2F0], rax; int *
0x1800191f2  call    ?Visit@DirectoryTreeWalker@Common@@AEAAJ_KPEAGPEBU_WIN32_FIND_DATAW@@PEAJ@Z; Common::DirectoryTreeWalker::Visit(unsigned __int64,ushort *,_WIN32_FIND_DATAW const *,long *)
0x1800191f7  mov     edi, eax
0x1800191f9  test    eax, eax
0x1800191fb  jnz     loc_180019295
0x180019201  mov     eax, [rsp+310h+var_2E0]
0x180019205  test    eax, eax
0x180019207  jz      short loc_180019215
0x180019209  cmp     eax, 3
0x18001920c  jz      short loc_180019215
0x18001920e  test    r14d, r14d
0x180019211  cmovz   r14d, eax
0x180019215  lea     rdx, [rsp+310h+P]; void **
0x18001921a  mov     [rsp+310h+P], 0
0x180019223  mov     ecx, 18h; unsigned __int64
0x180019228  call    ?Alloc@GlobalHeap@Common@@SAJ_KPEAPEAX@Z; Common::GlobalHeap::Alloc(unsigned __int64,void * *)
0x18001922d  mov     rcx, [rsp+310h+P]
0x180019232  test    rcx, rcx
0x180019235  jz      loc_1800194A7
0x18001923b  mov     rax, [rsi]
0x18001923e  lea     r8, [rsp+310h+P]; struct _WIN32_FIND_DATAW **
0x180019243  mov     [rcx+8], r12
0x180019247  lea     rdx, [rsp+310h+var_2C8]; void **
0x18001924c  mov     [rcx], rax
0x18001924f  xor     r12d, r12d
0x180019252  mov     [rcx+10h], rbx
0x180019256  mov     [rsi], rcx
0x180019259  mov     rcx, rsi; this
0x18001925c  mov     [rsp+310h+P], r12
0x180019261  mov     [rsp+310h+var_2C8], r12
0x180019266  call    ?GetFirstFindHandle@DirectoryTreeWalker@Common@@AEAAJPEAPEAXPEAPEAU_WIN32_FIND_DATAW@@@Z; Common::DirectoryTreeWalker::GetFirstFindHandle(void * *,_WIN32_FIND_DATAW * *)
0x18001926b  mov     edi, eax
0x18001926d  cmp     eax, 2
0x180019270  jnz     short loc_18001927F
0x180019272  mov     rbx, [rsp+310h+P]
0x180019277  lea     edi, [rax+10h]
0x18001927a  jmp     loc_18001932C
0x18001927f  test    eax, eax
0x180019281  jz      loc_180019152
0x180019287  mov     rbx, [rsp+310h+P]
0x18001928c  cmp     eax, 3
0x18001928f  jz      loc_18001932C
0x180019295  mov     rcx, rbx; P
0x180019298  call    ?Free@GlobalHeap@Common@@SAXPEAX@Z; Common::GlobalHeap::Free(void *)
0x18001929d  lea     rcx, [rsp+310h+var_2C8]
0x1800192a2  call    _anonymous_namespace___FindFileHandle__Close
0x1800192a7  mov     eax, edi
0x1800192a9  mov     rcx, [rbp+210h+var_40]
0x1800192b0  xor     rcx, rsp; StackCookie
0x1800192b3  call    __security_check_cookie
0x1800192b8  mov     rbx, [rsp+310h+arg_10]
0x1800192c0  add     rsp, 2E0h
0x1800192c7  pop     r15
0x1800192c9  pop     r14
0x1800192cb  pop     r13
0x1800192cd  pop     r12
0x1800192cf  pop     rdi
0x1800192d0  pop     rsi
0x1800192d1  pop     rbp
0x1800192d2  retn
0x1800192d3  mov     rdx, [rsi+10h]; unsigned __int64
0x1800192d7  lea     rax, [rsp+310h+var_2E0]
0x1800192dc  mov     [rsp+310h+var_2E0], r8d
0x1800192e1  mov     r9, rbx; struct _WIN32_FIND_DATAW *
0x1800192e4  mov     r8, [rsi+8]; unsigned __int16 *
0x1800192e8  mov     rcx, rsi; this
0x1800192eb  mov     [rsp+310h+var_2F0], rax; int *
0x1800192f0  call    ?Visit@DirectoryTreeWalker@Common@@AEAAJ_KPEAGPEBU_WIN32_FIND_DATAW@@PEAJ@Z; Common::DirectoryTreeWalker::Visit(unsigned __int64,ushort *,_WIN32_FIND_DATAW const *,long *)
0x1800192f5  xor     r8d, r8d
0x1800192f8  mov     edi, eax
0x1800192fa  test    eax, eax
0x1800192fc  jnz     short loc_180019295
0x1800192fe  mov     edi, [rsp+310h+var_2E0]
0x180019302  test    edi, edi
0x180019304  jz      loc_180019490
0x18001930a  cmp     edi, 12h
0x18001930d  jz      short loc_180019329
0x18001930f  cmp     edi, 3
0x180019312  jz      loc_180019179
0x180019318  test    r14d, r14d
0x18001931b  jnz     loc_180019499
0x180019321  mov     r14d, edi
0x180019324  jmp     loc_180019499
0x180019329  xor     r12d, r12d
0x18001932c  mov     rcx, rbx; P
0x18001932f  call    ?Free@GlobalHeap@Common@@SAXPEAX@Z; Common::GlobalHeap::Free(void *)
0x180019334  lea     rcx, [rsp+310h+var_2C8]
0x180019339  call    _anonymous_namespace___FindFileHandle__Close
0x18001933e  cmp     edi, 12h
0x180019341  jz      short loc_18001934C
0x180019343  cmp     edi, 3
0x180019346  jnz     loc_1800194CA
0x18001934c  mov     rbx, [rsi]
0x18001934f  test    rbx, rbx
0x180019352  jnz     short loc_180019376
0x180019354  lea     r15d, [rbx+1]
0x180019358  test    r13b, 3
0x18001935c  jz      short loc_180019379
0x18001935e  test    r14d, r14d
0x180019361  jz      loc_1800194BD
0x180019367  xor     ecx, ecx; P
0x180019369  call    ?Free@GlobalHeap@Common@@SAXPEAX@Z; Common::GlobalHeap::Free(void *)
0x18001936e  mov     edi, r14d
0x180019371  jmp     loc_18001929D
0x180019376  mov     r15d, r12d
0x180019379  xor     edx, edx; Val
0x18001937b  lea     rcx, [rbp+210h+var_290]; void *
0x18001937f  mov     r8d, 250h; Size
0x180019385  call    memset_0
0x18001938a  test    r15d, r15d
0x18001938d  jz      short loc_1800193E1
0x18001938f  mov     rax, [rsi+48h]
0x180019393  lea     r9, [rbp+210h+var_290]
0x180019397  mov     rcx, [rsi+30h]
0x18001939b  lea     r8, [rsp+310h+var_2B0]
0x1800193a0  mov     rdx, [rsi+8]
0x1800193a4  mov     rbx, r12
0x1800193a7  mov     [rsp+310h+var_2A8], rax
0x1800193ac  mov     rax, [rsi+38h]
0x1800193b0  mov     [rsp+310h+var_2B0], r12
0x1800193b5  mov     [rsp+310h+var_2A0], rcx
0x1800193ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800193bf  mov     edi, eax
0x1800193c1  add     eax, 0FFFFFFFEh
0x1800193c4  cmp     eax, 1
0x1800193c7  jbe     short loc_1800193D5
0x1800193c9  test    edi, edi
0x1800193cb  jnz     loc_1800194B1
0x1800193d1  lea     rbx, [rbp+210h+var_290]
0x1800193d5  lea     rcx, [rsp+310h+var_2B0]
0x1800193da  call    _anonymous_namespace___FindFileHandle__Close
0x1800193df  jmp     short loc_1800193EF
0x1800193e1  test    rbx, rbx
0x1800193e4  jnz     short loc_1800193EB
0x1800193e6  mov     rbx, r12
0x1800193e9  jmp     short loc_1800193EF
0x1800193eb  mov     rbx, [rbx+10h]
0x1800193ef  lea     eax, [rdi-2]
0x1800193f2  cmp     eax, 1
0x1800193f5  jbe     short loc_180019441
0x1800193f7  cmp     [rsp+310h+var_2D0], r12d
0x1800193fc  jnz     short loc_180019441
0x1800193fe  mov     r8, [rsi+8]; unsigned __int16 *
0x180019402  lea     rax, [rsp+310h+var_2E0]
0x180019407  mov     rdx, [rsi+10h]; unsigned __int64
0x18001940b  mov     r9, rbx; struct _WIN32_FIND_DATAW *
0x18001940e  mov     rcx, rsi; this
0x180019411  mov     [rsp+310h+var_2F0], rax; int *
0x180019416  mov     [rsp+310h+var_2E0], r12d
0x18001941b  call    ?Visit@DirectoryTreeWalker@Common@@AEAAJ_KPEAGPEBU_WIN32_FIND_DATAW@@PEAJ@Z; Common::DirectoryTreeWalker::Visit(unsigned __int64,ushort *,_WIN32_FIND_DATAW const *,long *)
0x180019420  mov     edi, eax
0x180019422  test    eax, eax
0x180019424  jnz     loc_1800194CA
0x18001942a  mov     edi, [rsp+310h+var_2E0]
0x18001942e  test    edi, edi
0x180019430  jz      short loc_180019444
0x180019432  cmp     edi, 3
0x180019435  jz      short loc_180019444
0x180019437  test    r14d, r14d
0x18001943a  jnz     short loc_180019444
0x18001943c  mov     r14d, edi
0x18001943f  jmp     short loc_180019444
0x180019441  mov     edi, r12d
0x180019444  test    r15d, r15d
0x180019447  jnz     loc_18001935E
0x18001944d  mov     rcx, [rsi]; P
0x180019450  mov     r12, [rcx+8]
0x180019454  mov     rax, [rcx]
0x180019457  mov     rbx, [rcx+10h]
0x18001945b  mov     [rsp+310h+var_2C8], r12
  ... truncated ...
```
