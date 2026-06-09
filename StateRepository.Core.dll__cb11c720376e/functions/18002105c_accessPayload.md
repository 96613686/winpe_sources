# accessPayload

- ea: `0x18002105c`
- end: `0x180021423`
- name: `accessPayload`
- size: `967`
- prototype: `__int64 __fastcall(__int64, unsigned int, signed int, char *, int)`
- caller_count: `7`
- callee_count: `12`
- tags: ``

## callers

- `0x18001fe60`
- `0x1800209e8`
- `0x18005fc6c`
- `0x1800621d0`
- `0x1800695a4`
- `0x180082090`
- `0x1800820c0`

## callees

- `0x18000c440`
- `0x1800201c0`
- `0x18002105c`
- `0x180021758`
- `0x180024dd8`
- `0x180047008`
- `0x18004a0bc`
- `0x18004d170`
- `0x180060134`
- `0x180062b88`
- `0x18006910e`
- `0x18009a010`

## pseudocode

```c
__int64 __fastcall accessPayload(__int64 a1, unsigned int a2, signed int a3, char *a4, int a5)
{
  __int64 v5; // rbp
  __int64 v8; // rdi
  unsigned int *v10; // r13
  __int64 v11; // rdx
  unsigned int v12; // ebx
  unsigned __int64 v13; // rcx
  unsigned __int64 v14; // rax
  unsigned int v15; // r15d
  unsigned int v16; // edi
  int v17; // ebx
  __int64 v18; // rax
  int v19; // r9d
  unsigned int v20; // ebx
  unsigned int v21; // ebp
  bool v22; // zf
  unsigned __int32 v23; // ebp
  __int64 v24; // r8
  __int64 v25; // rcx
  signed int v26; // r13d
  char *v27; // rdx
  int v28; // ebx
  __int64 v30; // r10
  unsigned int *v31; // rdx
  __int64 v32; // rcx
  int v33; // eax
  __int64 v34; // rax
  __int64 v35; // rax
  __int64 v36; // rdx
  unsigned int OverflowPage; // eax
  int v38; // [rsp+30h] [rbp-58h]
  unsigned int v39; // [rsp+34h] [rbp-54h]
  unsigned int *v40; // [rsp+38h] [rbp-50h]
  unsigned __int64 v41; // [rsp+40h] [rbp-48h]
  __int64 v42; // [rsp+90h] [rbp+8h] BYREF
  __int64 v43; // [rsp+A8h] [rbp+20h] BYREF

  v5 = *(_QWORD *)(a1 + 136);
  v8 = a2;
  if ( *(_WORD *)(a1 + 86) >= *(_WORD *)(v5 + 24) )
  {
    v36 = 75764;
    return sqlite3ReportError(11, v36, "database corruption");
  }
  v10 = *(unsigned int **)(a1 + 32);
  v40 = v10;
  getCellInfo();
  v11 = *(_QWORD *)(a1 + 56);
  v12 = *(unsigned __int16 *)(a1 + 68);
  v13 = v11 - *(_QWORD *)(v5 + 80);
  v14 = v10[14] - v12;
  v42 = v11;
  if ( v13 > v14 )
  {
    v36 = 75779;
    return sqlite3ReportError(11, v36, "database corruption");
  }
  v41 = (unsigned __int64)a4;
  if ( (unsigned int)v8 < v12 )
  {
    if ( (int)v8 + a3 <= v12 )
      v17 = a3;
    else
      v17 = v12 - v8;
    v15 = copyPayload((void *)(v11 + v8), a4, *(_QWORD *)(v5 + 112));
    if ( v15 )
      return v15;
    v11 = v42;
    a3 -= v17;
    v16 = 0;
    a4 += v17;
  }
  else
  {
    v15 = 0;
    v16 = v8 - v12;
  }
  if ( !a3 )
    return v15;
  v18 = *(unsigned __int16 *)(a1 + 68);
  v19 = 0;
  v20 = v10[14] - 4;
  v38 = 0;
  v39 = v20;
  v21 = *(_DWORD *)(v18 + v11);
  HIDWORD(v11) = 0;
  v22 = (*(_BYTE *)(a1 + 1) & 4) == 0;
  v23 = _byteswap_ulong(v21);
  LODWORD(v42) = v23;
  if ( !v22 )
  {
    v24 = *(_QWORD *)(a1 + 16);
    v25 = v16 / v20;
    if ( *(_DWORD *)(v24 + 4 * v25) )
    {
      v19 = v16 / v20;
      v38 = v16 / v20;
      v16 %= v20;
      v23 = *(_DWORD *)(v24 + 4LL * (int)v25);
      LODWORD(v42) = v23;
    }
LABEL_13:
    while ( v23 )
    {
      if ( v23 > v10[16] )
      {
        v36 = 75850;
        return sqlite3ReportError(11, v36, "database corruption");
      }
      *(_DWORD *)(*(_QWORD *)(a1 + 16) + 4LL * v19) = v23;
      if ( v16 >= v20 )
      {
        if ( *(_DWORD *)(*(_QWORD *)(a1 + 16) + 4LL * v19 + 4) )
        {
          v23 = *(_DWORD *)(*(_QWORD *)(a1 + 16) + 4LL * v19 + 4);
          LODWORD(v42) = v23;
        }
        else
        {
          OverflowPage = getOverflowPage(v10, v23, 0, &v42);
          v23 = v42;
          v15 = OverflowPage;
        }
        v16 -= v20;
      }
      else
      {
        if ( v16 + a3 > v20 )
          v26 = v20 - v16;
        else
          v26 = a3;
        if ( a5
          || v16
          || !(unsigned int)sqlite3PagerDirectReadOk(*(_QWORD *)v40, v23)
          || (v27 = a4 - 4, (unsigned __int64)(a4 - 4) < v41) )
        {
          v30 = *(_QWORD *)v40;
          v43 = 0;
          v15 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *, _QWORD))(v30 + 272))(
                  v30,
                  v23,
                  &v43,
                  a5 == 0 ? 2 : 0);
          if ( !v15 )
          {
            v31 = *(unsigned int **)(v43 + 8);
            v23 = _byteswap_ulong(*v31);
            LODWORD(v42) = v23;
            v15 = copyPayload((char *)v31 + v16 + 4, a4, v43);
            sqlite3PagerUnref(v43);
            v16 = 0;
          }
        }
        else
        {
          v28 = *(_DWORD *)v27;
          v15 = (*(__int64 (__fastcall **)(_QWORD, char *, _QWORD, unsigned __int64))(**(_QWORD **)(*(_QWORD *)v40 + 72LL)
                                                                                    + 16LL))(
                  *(_QWORD *)(*(_QWORD *)v40 + 72LL),
                  v27,
                  (unsigned int)(v26 + 4),
                  v40[13] * (unsigned __int64)(v23 - 1));
          v23 = _byteswap_ulong(*((_DWORD *)a4 - 1));
          *((_DWORD *)a4 - 1) = v28;
          v20 = v39;
          LODWORD(v42) = v23;
        }
        a3 -= v26;
        if ( !a3 )
          return v15;
        v35 = v26;
        v10 = v40;
        a4 += v35;
      }
      if ( v15 )
        return v15;
      v19 = ++v38;
    }
    v36 = 75934;
    return sqlite3ReportError(11, v36, "database corruption");
  }
  v32 = *(_QWORD *)(a1 + 16);
  LODWORD(v11) = (v20 + *(_DWORD *)(a1 + 64) - (_DWORD)v18 - 1) % v20;
  LODWORD(v43) = (v20 + *(_DWORD *)(a1 + 64) - (_DWORD)v18 - 1) / v20;
  if ( v32 )
  {
    v33 = sqlite3MallocSize(v32, v11);
    if ( 4 * (int)v43 <= v33 )
    {
LABEL_29:
      memset_0(*(void **)(a1 + 16), 0, 4LL * (int)v43);
      *(_BYTE *)(a1 + 1) |= 4u;
      v19 = 0;
      goto LABEL_13;
    }
  }
  if ( !(unsigned int)sqlite3FaultSim(413, v11) )
  {
    v34 = sqlite3Realloc(*(_QWORD *)(a1 + 16), 8LL * (_DWORD)v43);
    if ( v34 )
    {
      *(_QWORD *)(a1 + 16) = v34;
      goto LABEL_29;
    }
  }
  return 7;
}

```

## disassembly

```asm
0x18002105c  mov     [rsp+arg_8], rbx
0x180021061  push    rbp
0x180021062  push    rsi
0x180021063  push    rdi
0x180021064  push    r12
0x180021066  push    r13
0x180021068  push    r14
0x18002106a  push    r15
0x18002106c  sub     rsp, 50h
0x180021070  mov     rbp, [rcx+88h]
0x180021077  mov     r12, r9
0x18002107a  mov     r14d, r8d
0x18002107d  mov     edi, edx
0x18002107f  mov     rsi, rcx
0x180021082  movzx   eax, word ptr [rbp+18h]
0x180021086  cmp     [rcx+56h], ax
0x18002108a  jnb     loc_18002138B
0x180021090  mov     r13, [rcx+20h]
0x180021094  mov     [rsp+88h+var_50], r13
0x180021099  call    getCellInfo
0x18002109e  mov     rdx, [rsi+38h]
0x1800210a2  mov     eax, [r13+38h]
0x1800210a6  mov     rcx, rdx
0x1800210a9  movzx   ebx, word ptr [rsi+44h]
0x1800210ad  sub     rcx, [rbp+50h]
0x1800210b1  sub     eax, ebx
0x1800210b3  mov     [rsp+88h+arg_0], rdx
0x1800210bb  cmp     rcx, rax
0x1800210be  ja      loc_1800213AD
0x1800210c4  mov     [rsp+88h+var_48], r12
0x1800210c9  cmp     edi, ebx
0x1800210cb  jb      short loc_1800210D4
0x1800210cd  xor     r15d, r15d
0x1800210d0  sub     edi, ebx
0x1800210d2  jmp     short loc_180021120
0x1800210d4  lea     eax, [rdi+r14]
0x1800210d8  cmp     eax, ebx
0x1800210da  jbe     loc_1800213B4
0x1800210e0  sub     ebx, edi
0x1800210e2  mov     rax, [rbp+70h]
0x1800210e6  lea     rcx, [rdx+rdi]; Src
0x1800210ea  mov     r9d, [rsp+88h+arg_20]
0x1800210f2  mov     rdx, r12; void *
0x1800210f5  mov     r8d, ebx
0x1800210f8  mov     [rsp+88h+var_68], rax; __int64
0x1800210fd  call    copyPayload
0x180021102  mov     r15d, eax
0x180021105  test    eax, eax
0x180021107  jnz     loc_180021218
0x18002110d  mov     rdx, [rsp+88h+arg_0]
0x180021115  sub     r14d, ebx
0x180021118  xor     edi, edi
0x18002111a  movsxd  rax, ebx
0x18002111d  add     r12, rax
0x180021120  test    r14d, r14d
0x180021123  jz      loc_180021218
0x180021129  movzx   eax, word ptr [rsi+44h]
0x18002112d  xor     r9d, r9d
0x180021130  mov     ebx, [r13+38h]
0x180021134  add     ebx, 0FFFFFFFCh
0x180021137  mov     [rsp+88h+var_58], r9d
0x18002113c  mov     [rsp+88h+var_54], ebx
0x180021140  mov     ebp, [rax+rdx]
0x180021143  xor     edx, edx
0x180021145  test    byte ptr [rsi+1], 4
0x180021149  bswap   ebp
0x18002114b  mov     dword ptr [rsp+88h+arg_0], ebp
0x180021152  jz      loc_1800212C1
0x180021158  mov     r8, [rsi+10h]
0x18002115c  mov     eax, edi
0x18002115e  div     ebx
0x180021160  mov     ecx, eax
0x180021162  cmp     [r8+rax*4], r9d
0x180021166  jnz     loc_180021349
0x18002116c  test    ebp, ebp
0x18002116e  jz      loc_180021415
0x180021174  cmp     ebp, [r13+40h]
0x180021178  ja      loc_18002140E
0x18002117e  mov     rax, [rsi+10h]
0x180021182  movsxd  rcx, r9d
0x180021185  mov     [rax+rcx*4], ebp
0x180021188  cmp     edi, ebx
0x18002118a  jnb     loc_1800213C6
0x180021190  lea     eax, [rdi+r14]
0x180021194  cmp     eax, ebx
0x180021196  ja      loc_180021403
0x18002119c  mov     r13d, r14d
0x18002119f  cmp     [rsp+88h+arg_20], 0
0x1800211a7  mov     r15, [rsp+88h+var_50]
0x1800211ac  jnz     loc_180021233
0x1800211b2  test    edi, edi
0x1800211b4  jnz     short loc_180021233
0x1800211b6  mov     rcx, [r15]
0x1800211b9  mov     edx, ebp
0x1800211bb  call    sqlite3PagerDirectReadOk
0x1800211c0  test    eax, eax
0x1800211c2  jz      short loc_180021233
0x1800211c4  lea     rdx, [r12-4]
0x1800211c9  cmp     rdx, [rsp+88h+var_48]
0x1800211ce  jb      short loc_180021233
0x1800211d0  mov     rax, [r15]
0x1800211d3  lea     r9d, [rbp-1]
0x1800211d7  mov     ebx, [rdx]
0x1800211d9  lea     r8d, [r13+4]
0x1800211dd  mov     rcx, [rax+48h]
0x1800211e1  mov     eax, [r15+34h]
0x1800211e5  imul    r9, rax
0x1800211e9  mov     r10, [rcx]
0x1800211ec  mov     rax, [r10+10h]
0x1800211f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800211f5  mov     ebp, [r12-4]
0x1800211fa  mov     r15d, eax
0x1800211fd  bswap   ebp
0x1800211ff  mov     [r12-4], ebx
0x180021204  mov     ebx, [rsp+88h+var_54]
0x180021208  mov     dword ptr [rsp+88h+arg_0], ebp
0x18002120f  sub     r14d, r13d
0x180021212  jnz     loc_180021365
0x180021218  mov     eax, r15d
0x18002121b  mov     rbx, [rsp+88h+arg_8]
0x180021223  add     rsp, 50h
0x180021227  pop     r15
0x180021229  pop     r14
0x18002122b  pop     r13
0x18002122d  pop     r12
0x18002122f  pop     rdi
0x180021230  pop     rsi
0x180021231  pop     rbp
0x180021232  retn
0x180021233  mov     r10, [r15]
0x180021236  lea     r8, [rsp+88h+arg_18]
0x18002123e  mov     eax, [rsp+88h+arg_20]
0x180021245  mov     edx, ebp
0x180021247  neg     eax
0x180021249  mov     [rsp+88h+arg_18], 0
0x180021255  mov     rcx, r10
0x180021258  mov     rax, [r10+110h]
0x18002125f  sbb     r9d, r9d
0x180021262  not     r9d
0x180021265  and     r9d, 2
0x180021269  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002126e  mov     r15d, eax
0x180021271  test    eax, eax
0x180021273  jnz     short loc_18002120F
0x180021275  mov     r8, [rsp+88h+arg_18]
0x18002127d  lea     ecx, [rdi+4]
0x180021280  mov     r9d, [rsp+88h+arg_20]
0x180021288  mov     [rsp+88h+var_68], r8; __int64
0x18002128d  mov     rdx, [r8+8]
0x180021291  mov     r8d, r13d
0x180021294  add     rcx, rdx; Src
0x180021297  mov     ebp, [rdx]
0x180021299  mov     rdx, r12; void *
0x18002129c  bswap   ebp
0x18002129e  mov     dword ptr [rsp+88h+arg_0], ebp
0x1800212a5  call    copyPayload
0x1800212aa  mov     rcx, [rsp+88h+arg_18]
0x1800212b2  mov     r15d, eax
0x1800212b5  call    sqlite3PagerUnref
0x1800212ba  xor     edi, edi
0x1800212bc  jmp     loc_18002120F
0x1800212c1  mov     ecx, [rsi+40h]
0x1800212c4  sub     ecx, eax
0x1800212c6  lea     eax, [rcx-1]
0x1800212c9  mov     rcx, [rsi+10h]
0x1800212cd  add     eax, ebx
0x1800212cf  div     ebx
0x1800212d1  mov     dword ptr [rsp+88h+arg_18], eax
0x1800212d8  test    rcx, rcx
0x1800212db  jz      short loc_180021313
0x1800212dd  call    sqlite3MallocSize
0x1800212e2  mov     ecx, dword ptr [rsp+88h+arg_18]
0x1800212e9  shl     ecx, 2
0x1800212ec  cmp     ecx, eax
0x1800212ee  jg      short loc_180021313
0x1800212f0  movsxd  r8, dword ptr [rsp+88h+arg_18]
0x1800212f8  xor     edx, edx; Val
0x1800212fa  mov     rcx, [rsi+10h]; void *
0x1800212fe  shl     r8, 2; Size
0x180021302  call    memset_0
0x180021307  or      byte ptr [rsi+1], 4
0x18002130b  xor     r9d, r9d
0x18002130e  jmp     loc_18002116C
0x180021313  mov     ecx, 19Dh
0x180021318  call    sqlite3FaultSim
0x18002131d  test    eax, eax
0x18002131f  jnz     loc_1800213BC
0x180021325  mov     eax, dword ptr [rsp+88h+arg_18]
0x18002132c  mov     rcx, [rsi+10h]
0x180021330  add     eax, eax
0x180021332  movsxd  rdx, eax
0x180021335  shl     rdx, 2
0x180021339  call    sqlite3Realloc
0x18002133e  test    rax, rax
0x180021341  jz      short loc_1800213BC
0x180021343  mov     [rsi+10h], rax
0x180021347  jmp     short loc_1800212F0
0x180021349  movsxd  rax, ecx
0x18002134c  mov     r9d, ecx
0x18002134f  mov     [rsp+88h+var_58], ecx
0x180021353  mov     edi, edx
0x180021355  mov     ebp, [r8+rax*4]
0x180021359  mov     dword ptr [rsp+88h+arg_0], ebp
0x180021360  jmp     loc_18002116C
0x180021365  movsxd  rax, r13d
0x180021368  mov     r13, [rsp+88h+var_50]
0x18002136d  add     r12, rax
0x180021370  test    r15d, r15d
0x180021373  jnz     loc_180021218
0x180021379  mov     r9d, [rsp+88h+var_58]
0x18002137e  inc     r9d
0x180021381  mov     [rsp+88h+var_58], r9d
0x180021386  jmp     loc_18002116C
0x18002138b  mov     edx, 127F4h
0x180021390  jmp     short loc_180021397
0x180021392  mov     edx, 1289Eh
0x180021397  lea     r8, aDatabaseCorrup; "database corruption"
0x18002139e  mov     ecx, 0Bh
0x1800213a3  call    sqlite3ReportError
0x1800213a8  jmp     loc_18002121B
0x1800213ad  mov     edx, 12803h
0x1800213b2  jmp     short loc_180021397
0x1800213b4  mov     ebx, r14d
0x1800213b7  jmp     loc_1800210E2
0x1800213bc  mov     eax, 7
0x1800213c1  jmp     loc_18002121B
0x1800213c6  mov     rax, [rsi+10h]
0x1800213ca  mov     edx, [rax+rcx*4+4]
0x1800213ce  test    edx, edx
0x1800213d0  jz      short loc_1800213DD
0x1800213d2  mov     ebp, edx
0x1800213d4  mov     dword ptr [rsp+88h+arg_0], edx
0x1800213db  jmp     short loc_1800213FC
0x1800213dd  lea     r9, [rsp+88h+arg_0]
0x1800213e5  xor     r8d, r8d
0x1800213e8  mov     edx, ebp
0x1800213ea  mov     rcx, r13
0x1800213ed  call    getOverflowPage
0x1800213f2  mov     ebp, dword ptr [rsp+88h+arg_0]
0x1800213f9  mov     r15d, eax
0x1800213fc  sub     edi, ebx
0x1800213fe  jmp     loc_180021370
0x180021403  mov     r13d, ebx
0x180021406  sub     r13d, edi
0x180021409  jmp     loc_18002119F
0x18002140e  mov     edx, 1284Ah
0x180021413  jmp     short loc_180021397
0x180021415  test    r14d, r14d
0x180021418  jz      loc_180021218
0x18002141e  jmp     loc_180021392
```
