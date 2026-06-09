# CEditStream::Copy(long *,long *,IAVIStream * *)

- ea: `0x180011594`
- end: `0x18001191b`
- name: `?Copy@CEditStream@@UEAAJPEAJ0PEAPEAUIAVIStream@@@Z`
- size: `903`
- prototype: `__int64 __fastcall(CEditStream *__hidden this, int *, int *, struct IAVIStream **)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops`

## callers

- `0x180011580`

## callees

- `0x180008350`
- `0x180010eec`
- `0x180011594`
- `0x180011f9c`
- `0x180012844`
- `0x180012e88`
- `0x180017365`
- `0x180018010`

## pseudocode

```c
__int64 __fastcall CEditStream::Copy(CEditStream *this, int *a2, int *a3, struct IAVIStream **a4)
{
  CEditStream *v4; // r14
  IAVIStream *v9; // rcx
  LONG v10; // edi
  int v11; // eax
  int v12; // ecx
  int v13; // edx
  int v15; // edi
  int v16; // r15d
  struct CEditStream *v17; // rax
  struct CEditStream *v18; // rbx
  __int64 v19; // r12
  struct IAVIStream *v20; // rcx
  int v21; // esi
  int v22; // r15d
  __int64 *v23; // r13
  __int64 v24; // r14
  struct IAVIStream *v25; // rcx
  int v26; // r8d
  __int64 v27; // rdx
  __int64 v28; // r8
  __int64 v29; // rax
  __int64 v30; // rcx
  __int64 v31; // rcx
  __int64 v32; // rcx
  bool v33; // zf
  int v34; // [rsp+30h] [rbp-20h]
  int v35; // [rsp+34h] [rbp-1Ch] BYREF
  int v36; // [rsp+38h] [rbp-18h] BYREF
  struct IAVIStream *v37; // [rsp+40h] [rbp-10h] BYREF
  struct IAVIStream *v38; // [rsp+48h] [rbp-8h] BYREF
  int v40; // [rsp+98h] [rbp+48h] BYREF
  int v41; // [rsp+A0h] [rbp+50h] BYREF

  v4 = (CEditStream *)((char *)this - 288);
  v37 = 0;
  v35 = 0;
  v36 = 0;
  v41 = 0;
  if ( this == (CEditStream *)288 )
    v9 = 0;
  else
    v9 = (IAVIStream *)((char *)this + *(int *)(*(_QWORD *)v4 + 4LL) - 288);
  v10 = AVIStreamLength(v9);
  v40 = v10;
  v11 = *a2;
  if ( *a2 < 0 )
  {
    *a2 = 0;
    v11 = 0;
  }
  v12 = *a3;
  if ( *a3 < 0 )
  {
    v12 = v10 - v11;
    *a3 = v10 - v11;
  }
  v13 = *a2;
  if ( *a2 <= v10 )
  {
    if ( v13 + v12 <= v10 )
    {
      v15 = v12;
    }
    else
    {
      v15 = v10 - v13;
      *a3 = v15;
    }
    v16 = *a2;
    v34 = v15;
    v17 = CEditStream::NewEditStream(0);
    v18 = v17;
    if ( !v17 )
    {
      *a4 = 0;
      return 2147762279LL;
    }
    *a4 = (struct IAVIStream *)((char *)v17 + *(int *)(*(_QWORD *)v17 + 4LL));
    memmove_0((char *)v17 + 12, (char *)v4 + 12, 0xCCu);
    if ( v15 <= 0 )
    {
      v15 = *((_DWORD *)v18 + 10) + *((_DWORD *)v18 + 11) - v16;
      v34 = v15;
    }
    CEditStream::ResolveEdits(v4, v16, &v37, &v40, &v35, 0);
    CEditStream::ResolveEdits(v4, v16 + v15, &v38, &v36, &v41, 1);
    v19 = v35;
    if ( v35 == v41 )
    {
      v20 = v37;
      **((_QWORD **)v18 + 29) = v37;
      if ( v20 )
        ((void (__fastcall *)(struct IAVIStream *))v20->lpVtbl->AddRef)(v20);
      *(_DWORD *)(*((_QWORD *)v18 + 29) + 8LL) = v40;
      *(_DWORD *)(*((_QWORD *)v18 + 29) + 12LL) = v15;
    }
    else
    {
      if ( v35 > v41 || v35 < 0 )
        return 2147762280LL;
      v21 = v41 - v35;
      CEditStream::AllocEditSpace(v18, 1, v41 - v35);
      v22 = 0;
      if ( v21 >= 0 )
      {
        v23 = (__int64 *)((char *)this - 56);
        do
        {
          v24 = 56LL * v22;
          if ( v22 )
          {
            v27 = *v23;
            v28 = *((_QWORD *)v18 + 29);
            if ( v22 >= v21 )
            {
              v31 = 56LL * v41;
              *(_OWORD *)(v24 + v28) = *(_OWORD *)(v31 + v27);
              *(_OWORD *)(v24 + v28 + 16) = *(_OWORD *)(v31 + v27 + 16);
              *(_OWORD *)(v24 + v28 + 32) = *(_OWORD *)(v31 + v27 + 32);
              *(_QWORD *)(v24 + v28 + 48) = *(_QWORD *)(v31 + v27 + 48);
              v32 = *(_QWORD *)(v24 + *((_QWORD *)v18 + 29));
              if ( v32 )
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v32 + 8LL))(v32);
              *(_DWORD *)(v24 + *((_QWORD *)v18 + 29) + 12) = v36 - *(_DWORD *)(v24 + *((_QWORD *)v18 + 29) + 8);
            }
            else
            {
              v29 = 56LL * (v22 + (int)v19);
              *(_OWORD *)(v24 + v28) = *(_OWORD *)(v29 + v27);
              *(_OWORD *)(v24 + v28 + 16) = *(_OWORD *)(v29 + v27 + 16);
              *(_OWORD *)(v24 + v28 + 32) = *(_OWORD *)(v29 + v27 + 32);
              *(_QWORD *)(v24 + v28 + 48) = *(_QWORD *)(v29 + v27 + 48);
              v30 = *(_QWORD *)(v24 + *((_QWORD *)v18 + 29));
              if ( v30 )
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 8LL))(v30);
            }
          }
          else
          {
            v25 = v37;
            *(_QWORD *)(v24 + *((_QWORD *)v18 + 29)) = v37;
            if ( v25 )
              ((void (__fastcall *)(struct IAVIStream *))v25->lpVtbl->AddRef)(v25);
            v23 = (__int64 *)((char *)this - 56);
            v26 = v40;
            *(_DWORD *)(v24 + *((_QWORD *)v18 + 29) + 8) = v40;
            *(_DWORD *)(v24 + *((_QWORD *)v18 + 29) + 12) = *(_DWORD *)(56 * v19 + *((_QWORD *)this - 7) + 8)
                                                          + *(_DWORD *)(56 * v19 + *((_QWORD *)this - 7) + 12)
                                                          - v26;
          }
          ++v22;
        }
        while ( v22 <= v21 );
        v15 = v34;
      }
      CEditStream::PossiblyRemoveEdit(v18, v21);
      CEditStream::PossiblyRemoveEdit(v18, 0);
    }
    if ( (*(unsigned int (__fastcall **)(_QWORD, _QWORD, __int64))(***((_QWORD ***)v18 + 29) + 40LL))(
           **((_QWORD **)v18 + 29),
           *(unsigned int *)(*((_QWORD *)v18 + 29) + 8LL),
           20) != *(_DWORD *)(*((_QWORD *)v18 + 29) + 8LL) )
      *((_DWORD *)v18 + 56) = 1;
    v33 = *((_DWORD *)v18 + 56) == 0;
    *((_DWORD *)v18 + 10) = 0;
    *((_DWORD *)v18 + 11) = v15;
    *((_QWORD *)v18 + 10) = 0;
    if ( !v33 )
      *((_DWORD *)v18 + 4) = 0;
    return 0;
  }
  else
  {
    if ( a4 )
      *a4 = 0;
    return 2147762282LL;
  }
}

```

## disassembly

```asm
0x180011594  mov     [rsp-38h+arg_18], rbx
0x180011599  mov     [rsp-38h+arg_0], rcx
0x18001159e  push    rbp
0x18001159f  push    rsi
0x1800115a0  push    rdi
0x1800115a1  push    r12
0x1800115a3  push    r13
0x1800115a5  push    r14
0x1800115a7  push    r15
0x1800115a9  mov     rbp, rsp
0x1800115ac  sub     rsp, 50h
0x1800115b0  xor     r12d, r12d
0x1800115b3  lea     r14, [rcx-120h]
0x1800115ba  mov     [rbp+var_10], r12
0x1800115be  mov     rsi, r9
0x1800115c1  mov     [rbp+var_1C], r12d
0x1800115c5  mov     r15, r8
0x1800115c8  mov     [rbp+var_18], r12d
0x1800115cc  mov     rbx, rdx
0x1800115cf  mov     [rbp+arg_10], r12d
0x1800115d3  mov     r13, rcx
0x1800115d6  test    r14, r14
0x1800115d9  jnz     short loc_1800115E0
0x1800115db  mov     ecx, r12d
0x1800115de  jmp     short loc_1800115F1
0x1800115e0  mov     rax, [r14]
0x1800115e3  movsxd  rcx, dword ptr [rax+4]
0x1800115e7  add     rcx, 0FFFFFFFFFFFFFEE0h
0x1800115ee  add     rcx, r13; pavi
0x1800115f1  call    AVIStreamLength
0x1800115f6  mov     edi, eax
0x1800115f8  mov     [rbp+arg_8], eax
0x1800115fb  mov     eax, [rbx]
0x1800115fd  test    eax, eax
0x1800115ff  jns     short loc_180011607
0x180011601  mov     [rbx], r12d
0x180011604  mov     eax, r12d
0x180011607  mov     ecx, [r15]
0x18001160a  test    ecx, ecx
0x18001160c  jns     short loc_180011615
0x18001160e  mov     ecx, edi
0x180011610  sub     ecx, eax
0x180011612  mov     [r15], ecx
0x180011615  mov     edx, [rbx]
0x180011617  cmp     edx, edi
0x180011619  jle     short loc_18001162D
0x18001161b  test    rsi, rsi
0x18001161e  jz      short loc_180011623
0x180011620  mov     [rsi], r12
0x180011623  mov     eax, 8004406Ah
0x180011628  jmp     loc_180011903
0x18001162d  lea     eax, [rdx+rcx]
0x180011630  cmp     eax, edi
0x180011632  jle     short loc_18001163B
0x180011634  sub     edi, edx
0x180011636  mov     [r15], edi
0x180011639  jmp     short loc_18001163D
0x18001163b  mov     edi, ecx
0x18001163d  mov     r15d, [rbx]
0x180011640  xor     ecx, ecx; struct IAVIStream *
0x180011642  mov     [rbp+var_20], edi
0x180011645  call    ?NewEditStream@CEditStream@@SAPEAV1@PEAUIAVIStream@@@Z; CEditStream::NewEditStream(IAVIStream *)
0x18001164a  mov     rbx, rax
0x18001164d  test    rax, rax
0x180011650  jnz     short loc_18001165F
0x180011652  mov     [rsi], r12
0x180011655  mov     eax, 80044067h
0x18001165a  jmp     loc_180011903
0x18001165f  mov     rax, [rax]
0x180011662  lea     rdx, [r14+0Ch]; Src
0x180011666  mov     r8d, 0CCh; Size
0x18001166c  movsxd  rcx, dword ptr [rax+4]
0x180011670  add     rcx, rbx
0x180011673  mov     [rsi], rcx
0x180011676  lea     rcx, [rbx+0Ch]; void *
0x18001167a  call    memmove_0
0x18001167f  test    edi, edi
0x180011681  jg      short loc_18001168F
0x180011683  mov     edi, [rbx+2Ch]
0x180011686  add     edi, [rbx+28h]
0x180011689  sub     edi, r15d
0x18001168c  mov     [rbp+var_20], edi
0x18001168f  lea     rax, [rbp+var_1C]
0x180011693  mov     [rsp+50h+var_28], r12d; int
0x180011698  lea     r9, [rbp+arg_8]; int *
0x18001169c  mov     [rsp+50h+var_30], rax; int *
0x1800116a1  lea     r8, [rbp+var_10]; struct IAVIStream **
0x1800116a5  mov     edx, r15d; int
0x1800116a8  mov     rcx, r14; this
0x1800116ab  call    ?ResolveEdits@CEditStream@@AEAAJJPEAPEAUIAVIStream@@PEAJ1H@Z; CEditStream::ResolveEdits(long,IAVIStream * *,long *,long *,int)
0x1800116b0  lea     rax, [rbp+arg_10]
0x1800116b4  mov     [rsp+50h+var_28], 1; int
0x1800116bc  lea     edx, [r15+rdi]; int
0x1800116c0  mov     [rsp+50h+var_30], rax; int *
0x1800116c5  lea     r9, [rbp+var_18]; int *
0x1800116c9  mov     rcx, r14; this
0x1800116cc  lea     r8, [rbp+var_8]; struct IAVIStream **
0x1800116d0  call    ?ResolveEdits@CEditStream@@AEAAJJPEAPEAUIAVIStream@@PEAJ1H@Z; CEditStream::ResolveEdits(long,IAVIStream * *,long *,long *,int)
0x1800116d5  movsxd  r12, [rbp+var_1C]
0x1800116d9  mov     eax, [rbp+arg_10]
0x1800116dc  cmp     r12d, eax
0x1800116df  jnz     short loc_18001171C
0x1800116e1  mov     rcx, [rbp+var_10]
0x1800116e5  mov     rax, [rbx+0E8h]
0x1800116ec  mov     [rax], rcx
0x1800116ef  test    rcx, rcx
0x1800116f2  jz      short loc_180011700
0x1800116f4  mov     rax, [rcx]
0x1800116f7  mov     rax, [rax+8]
0x1800116fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011700  mov     rcx, [rbx+0E8h]
0x180011707  mov     eax, [rbp+arg_8]
0x18001170a  mov     [rcx+8], eax
0x18001170d  mov     rax, [rbx+0E8h]
0x180011714  mov     [rax+0Ch], edi
0x180011717  jmp     loc_1800118A3
0x18001171c  jg      loc_1800118FE
0x180011722  test    r12d, r12d
0x180011725  js      loc_1800118FE
0x18001172b  mov     esi, eax
0x18001172d  mov     edx, 1; int
0x180011732  sub     esi, r12d
0x180011735  mov     rcx, rbx; this
0x180011738  mov     r8d, esi; int
0x18001173b  call    ?AllocEditSpace@CEditStream@@AEAAJJJ@Z; CEditStream::AllocEditSpace(long,long)
0x180011740  xor     r15d, r15d
0x180011743  test    esi, esi
0x180011745  js      loc_18001188F
0x18001174b  mov     rdi, [rbp+arg_0]
0x18001174f  add     r13, 0FFFFFFFFFFFFFFC8h
0x180011753  movsxd  rax, r15d
0x180011756  imul    r14, rax, 38h ; '8'
0x18001175a  test    r15d, r15d
0x18001175d  jnz     short loc_1800117B7
0x18001175f  mov     rcx, [rbp+var_10]
0x180011763  mov     rax, [rbx+0E8h]
0x18001176a  mov     [r14+rax], rcx
0x18001176e  test    rcx, rcx
0x180011771  jz      short loc_18001177F
0x180011773  mov     rax, [rcx]
0x180011776  mov     rax, [rax+8]
0x18001177a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001177f  mov     rax, [rbx+0E8h]
0x180011786  lea     r13, [rdi-38h]
0x18001178a  mov     r8d, [rbp+arg_8]
0x18001178e  imul    rcx, r12, 38h ; '8'
0x180011792  mov     [r14+rax+8], r8d
0x180011797  mov     rax, [rdi-38h]
0x18001179b  mov     edx, [rcx+rax+0Ch]
0x18001179f  add     edx, [rcx+rax+8]
0x1800117a3  mov     rax, [rbx+0E8h]
0x1800117aa  sub     edx, r8d
0x1800117ad  mov     [r14+rax+0Ch], edx
0x1800117b2  jmp     loc_180011880
0x1800117b7  mov     rdx, [r13+0]
0x1800117bb  mov     r8, [rbx+0E8h]
0x1800117c2  cmp     r15d, esi
0x1800117c5  jge     short loc_18001181C
0x1800117c7  lea     eax, [r15+r12]
0x1800117cb  movsxd  rcx, eax
0x1800117ce  imul    rax, rcx, 38h ; '8'
0x1800117d2  movups  xmm0, xmmword ptr [rax+rdx]
0x1800117d6  movups  xmmword ptr [r14+r8], xmm0
0x1800117db  movups  xmm1, xmmword ptr [rax+rdx+10h]
0x1800117e0  movups  xmmword ptr [r14+r8+10h], xmm1
0x1800117e6  movups  xmm0, xmmword ptr [rax+rdx+20h]
0x1800117eb  movups  xmmword ptr [r14+r8+20h], xmm0
0x1800117f1  movsd   xmm1, qword ptr [rax+rdx+30h]
0x1800117f7  movsd   qword ptr [r14+r8+30h], xmm1
0x1800117fe  mov     rax, [rbx+0E8h]
0x180011805  mov     rcx, [r14+rax]
0x180011809  test    rcx, rcx
0x18001180c  jz      short loc_180011880
0x18001180e  mov     rax, [rcx]
0x180011811  mov     rax, [rax+8]
0x180011815  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001181a  jmp     short loc_180011880
0x18001181c  movsxd  rax, [rbp+arg_10]
0x180011820  imul    rcx, rax, 38h ; '8'
0x180011824  movups  xmm0, xmmword ptr [rcx+rdx]
0x180011828  movups  xmmword ptr [r14+r8], xmm0
0x18001182d  movups  xmm1, xmmword ptr [rcx+rdx+10h]
0x180011832  movups  xmmword ptr [r14+r8+10h], xmm1
0x180011838  movups  xmm0, xmmword ptr [rcx+rdx+20h]
0x18001183d  movups  xmmword ptr [r14+r8+20h], xmm0
0x180011843  movsd   xmm1, qword ptr [rcx+rdx+30h]
0x180011849  movsd   qword ptr [r14+r8+30h], xmm1
0x180011850  mov     rax, [rbx+0E8h]
0x180011857  mov     rcx, [r14+rax]
0x18001185b  test    rcx, rcx
0x18001185e  jz      short loc_18001186C
0x180011860  mov     rax, [rcx]
0x180011863  mov     rax, [rax+8]
0x180011867  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001186c  mov     rcx, [rbx+0E8h]
0x180011873  mov     eax, [rbp+var_18]
0x180011876  sub     eax, [r14+rcx+8]
0x18001187b  mov     [r14+rcx+0Ch], eax
0x180011880  inc     r15d
0x180011883  cmp     r15d, esi
0x180011886  jle     loc_180011753
0x18001188c  mov     edi, [rbp+var_20]
0x18001188f  mov     edx, esi; int
0x180011891  mov     rcx, rbx; this
0x180011894  call    ?PossiblyRemoveEdit@CEditStream@@AEAAJJ@Z; CEditStream::PossiblyRemoveEdit(long)
0x180011899  xor     edx, edx; int
0x18001189b  mov     rcx, rbx; this
0x18001189e  call    ?PossiblyRemoveEdit@CEditStream@@AEAAJJ@Z; CEditStream::PossiblyRemoveEdit(long)
0x1800118a3  mov     rdx, [rbx+0E8h]
0x1800118aa  mov     r8d, 14h
0x1800118b0  mov     rcx, [rdx]
0x1800118b3  mov     edx, [rdx+8]
0x1800118b6  mov     rax, [rcx]
0x1800118b9  mov     rax, [rax+28h]
0x1800118bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800118c2  mov     rcx, [rbx+0E8h]
0x1800118c9  cmp     eax, [rcx+8]
0x1800118cc  jz      short loc_1800118D8
0x1800118ce  mov     dword ptr [rbx+0E0h], 1
0x1800118d8  cmp     dword ptr [rbx+0E0h], 0
0x1800118df  mov     dword ptr [rbx+28h], 0
0x1800118e6  mov     [rbx+2Ch], edi
0x1800118e9  mov     qword ptr [rbx+50h], 0
0x1800118f1  jz      short loc_1800118FA
0x1800118f3  mov     dword ptr [rbx+10h], 0
0x1800118fa  xor     eax, eax
0x1800118fc  jmp     short loc_180011903
0x1800118fe  mov     eax, 80044068h
0x180011903  mov     rbx, [rsp+50h+arg_18]
0x18001190b  add     rsp, 50h
0x18001190f  pop     r15
0x180011911  pop     r14
0x180011913  pop     r13
0x180011915  pop     r12
0x180011917  pop     rdi
0x180011918  pop     rsi
0x180011919  pop     rbp
0x18001191a  retn
```
