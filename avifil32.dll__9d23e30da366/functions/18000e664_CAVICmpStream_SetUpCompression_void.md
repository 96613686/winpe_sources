# CAVICmpStream::SetUpCompression(void)

- ea: `0x18000e664`
- end: `0x18000e964`
- name: `?SetUpCompression@CAVICmpStream@@QEAAJXZ`
- size: `768`
- prototype: `__int64 __fastcall(CAVICmpStream *__hidden this)`
- caller_count: `2`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18000dc50`
- `0x18000de80`

## callees

- `0x18000e664`
- `0x180014350`
- `0x180017365`
- `0x180018010`

## import_xrefs

- `MSVFW32!ICSendMessage` at `0x18000e6d4`
- `MSVFW32!ICSendMessage` at `0x18000e728`
- `MSVFW32!ICSendMessage` at `0x18000e760`
- `MSVFW32!ICSendMessage` at `0x18000e785`
- `MSVFW32!ICSendMessage` at `0x18000e844`
- `MSVFW32!ICSendMessage` at `0x18000e922`
- `MSVFW32!ICSendMessage` at `0x18000e6d4`
- `MSVFW32!ICSendMessage` at `0x18000e728`
- `MSVFW32!ICSendMessage` at `0x18000e760`
- `MSVFW32!ICSendMessage` at `0x18000e785`
- `MSVFW32!ICSendMessage` at `0x18000e844`
- `MSVFW32!ICSendMessage` at `0x18000e922`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalReAlloc` at `0x18000e8da`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalReAlloc` at `0x18000e8da`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x18000e8bc`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x18000e8bc`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x18000e6fa`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x18000e7a5`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x18000e818`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x18000e8e3`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x18000e6fa`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x18000e7a5`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x18000e818`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x18000e8e3`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x18000e8b3`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x18000e8c9`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x18000e8b3`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x18000e8c9`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x18000e6f1`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x18000e79c`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x18000e80f`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x18000e6f1`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x18000e79c`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x18000e80f`

## pseudocode

```c
__int64 __fastcall CAVICmpStream::SetUpCompression(CAVICmpStream *this)
{
  PGETFRAME FrameOpen; // rax
  unsigned int v3; // ebx
  DWORD_PTR v4; // rax
  DWORD_PTR v5; // rsi
  LONG_PTR v6; // rax
  HGLOBAL v7; // rax
  LPVOID v8; // rax
  DWORD_PTR v9; // r9
  HIC v10; // rcx
  unsigned int v11; // eax
  HGLOBAL v12; // rax
  void *v13; // rax
  bool v14; // zf
  HGLOBAL v15; // rax
  LPVOID v16; // rax
  __int64 v17; // rcx
  unsigned int *v18; // rcx
  unsigned __int64 v19; // rax
  unsigned int v20; // eax
  unsigned int v21; // esi
  HGLOBAL v22; // rax
  HGLOBAL v23; // rax
  HGLOBAL v24; // rax
  unsigned int *v25; // rax
  DWORD_PTR v26; // r8
  HIC v27; // rcx

  FrameOpen = AVIStreamGetFrameOpen(*((PAVISTREAM *)this + 32), 0);
  *((_QWORD *)this + 33) = FrameOpen;
  if ( !FrameOpen )
    return (unsigned int)-2147205016;
  v3 = 0;
  if ( *((_DWORD *)this + 13) == 541215044 )
    return v3;
  v4 = ((__int64 (__fastcall *)(PGETFRAME, _QWORD))FrameOpen->lpVtbl->GetFrame)(FrameOpen, 0);
  v5 = v4;
  if ( !v4 )
    return (unsigned int)-2147205016;
  LODWORD(v6) = ICSendMessage(*((HIC *)this + 35), 0x4004u, v4, 0);
  if ( (int)v6 < 40 )
  {
    v6 = (unsigned int)v6;
LABEL_25:
    if ( v6 == -2 )
      return (unsigned int)-2147205018;
    else
      return (unsigned int)(v6 != -3) - 2147205017;
  }
  *((_DWORD *)this + 82) = v6;
  v7 = GlobalAlloc(0x2042u, (int)v6);
  v8 = GlobalLock(v7);
  *((_QWORD *)this + 40) = v8;
  if ( !v8 )
    return (unsigned int)-2147205017;
  v6 = ICSendMessage(*((HIC *)this + 35), 0x4004u, v5, (DWORD_PTR)v8);
  if ( (int)v6 < 0 )
    goto LABEL_25;
  v9 = *((_QWORD *)this + 40);
  v10 = (HIC)*((_QWORD *)this + 35);
  *((_DWORD *)this + 27) = *((_DWORD *)this + 25) + *(_DWORD *)(v9 + 4);
  *((_DWORD *)this + 28) = *((_DWORD *)this + 26) + *(_DWORD *)(v9 + 8);
  v6 = ICSendMessage(v10, 0x4007u, v5, v9);
  if ( v6 )
    goto LABEL_25;
  v11 = ICSendMessage(*((HIC *)this + 35), 0x4005u, v5, *((_QWORD *)this + 40));
  v12 = GlobalAlloc(0x2002u, v11 + (__int64)*((int *)this + 82));
  v13 = GlobalLock(v12);
  *((_QWORD *)this + 36) = v13;
  if ( !v13 )
    return (unsigned int)-2147205017;
  memmove_0(v13, *((const void **)this + 40), *((int *)this + 82));
  v14 = *((_DWORD *)this + 87) == 1;
  *((_QWORD *)this + 37) = **((unsigned int **)this + 36)
                         + *((_QWORD *)this + 36)
                         + 4LL * *(unsigned int *)(*((_QWORD *)this + 36) + 32LL);
  if ( !v14 && (*((_BYTE *)this + 356) & 0x20) == 0 )
  {
    v15 = GlobalAlloc(0x2002u, 0x428u);
    v16 = GlobalLock(v15);
    *((_QWORD *)this + 38) = v16;
    if ( !v16 )
      return (unsigned int)-2147205017;
    LODWORD(v6) = ICSendMessage(*((HIC *)this + 35), 0x400Au, *((_QWORD *)this + 40), (DWORD_PTR)v16);
    if ( (int)v6 < 0 )
    {
      v6 = (int)v6;
    }
    else
    {
      v17 = *((_QWORD *)this + 38);
      if ( !*(_DWORD *)(v17 + 20) )
        *(_DWORD *)(v17 + 20) = *(_DWORD *)(v17 + 8)
                              * (((*(_DWORD *)(v17 + 4) * (unsigned int)*(unsigned __int16 *)(v17 + 14) + 31) >> 3)
                               & 0x1FFFFFFC);
      v18 = (unsigned int *)*((_QWORD *)this + 38);
      v19 = 4LL * v18[8];
      if ( v19 > 0xFFFFFFFF )
        return (unsigned int)-2147205017;
      v20 = v18[5] + v19;
      if ( v20 < v18[5] )
        return (unsigned int)-2147205017;
      v21 = *v18 + v20;
      if ( v21 < *v18 )
        return (unsigned int)-2147205017;
      v22 = GlobalHandle(v18);
      GlobalUnlock(v22);
      v23 = GlobalHandle(*((LPCVOID *)this + 38));
      v24 = GlobalReAlloc(v23, v21, 0x2002u);
      v25 = (unsigned int *)GlobalLock(v24);
      *((_QWORD *)this + 38) = v25;
      if ( !v25 )
        return (unsigned int)-2147205017;
      v26 = *((_QWORD *)this + 40);
      v27 = (HIC)*((_QWORD *)this + 35);
      *((_QWORD *)this + 39) = (char *)&v25[v25[8]] + *v25;
      v6 = ICSendMessage(v27, 0x400Cu, v26, (DWORD_PTR)v25);
      if ( !v6 )
        return v3;
    }
    goto LABEL_25;
  }
  return v3;
}

```

## disassembly

```asm
0x18000e664  mov     [rsp+arg_0], rbx
0x18000e669  mov     [rsp+arg_8], rsi
0x18000e66e  push    rdi
0x18000e66f  sub     rsp, 20h
0x18000e673  mov     rdi, rcx
0x18000e676  xor     edx, edx; lpbiWanted
0x18000e678  mov     rcx, [rcx+100h]; pavi
0x18000e67f  call    AVIStreamGetFrameOpen
0x18000e684  mov     [rdi+108h], rax
0x18000e68b  mov     rcx, rax
0x18000e68e  test    rax, rax
0x18000e691  jnz     short loc_18000E69D
0x18000e693  mov     ebx, 80044068h
0x18000e698  jmp     loc_18000E952
0x18000e69d  xor     ebx, ebx
0x18000e69f  cmp     dword ptr [rdi+34h], 20424944h
0x18000e6a6  jz      loc_18000E952
0x18000e6ac  mov     rax, [rax]
0x18000e6af  xor     edx, edx
0x18000e6b1  mov     rax, [rax+18h]
0x18000e6b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e6ba  mov     rsi, rax
0x18000e6bd  test    rax, rax
0x18000e6c0  jz      short loc_18000E693
0x18000e6c2  mov     rcx, [rdi+118h]; hic
0x18000e6c9  xor     r9d, r9d; dw2
0x18000e6cc  mov     r8, rax; dw1
0x18000e6cf  mov     edx, 4004h; msg
0x18000e6d4  call    cs:__imp_ICSendMessage
0x18000e6da  cmp     eax, 28h ; '('
0x18000e6dd  jl      loc_18000E933
0x18000e6e3  movsxd  rdx, eax; dwBytes
0x18000e6e6  mov     ecx, 2042h; uFlags
0x18000e6eb  mov     [rdi+148h], eax
0x18000e6f1  call    cs:__imp_GlobalAlloc
0x18000e6f7  mov     rcx, rax; hMem
0x18000e6fa  call    cs:__imp_GlobalLock
0x18000e700  mov     [rdi+140h], rax
0x18000e707  test    rax, rax
0x18000e70a  jnz     short loc_18000E716
0x18000e70c  mov     ebx, 80044067h
0x18000e711  jmp     loc_18000E952
0x18000e716  mov     rcx, [rdi+118h]; hic
0x18000e71d  mov     r9, rax; dw2
0x18000e720  mov     r8, rsi; dw1
0x18000e723  mov     edx, 4004h; msg
0x18000e728  call    cs:__imp_ICSendMessage
0x18000e72e  test    eax, eax
0x18000e730  js      loc_18000E935
0x18000e736  mov     r9, [rdi+140h]; dw2
0x18000e73d  mov     r8, rsi; dw1
0x18000e740  mov     rcx, [rdi+118h]; hic
0x18000e747  mov     edx, 4007h; msg
0x18000e74c  mov     eax, [r9+4]
0x18000e750  add     eax, [rdi+64h]
0x18000e753  mov     [rdi+6Ch], eax
0x18000e756  mov     eax, [r9+8]
0x18000e75a  add     eax, [rdi+68h]
0x18000e75d  mov     [rdi+70h], eax
0x18000e760  call    cs:__imp_ICSendMessage
0x18000e766  test    rax, rax
0x18000e769  jnz     loc_18000E935
0x18000e76f  mov     r9, [rdi+140h]; dw2
0x18000e776  mov     r8, rsi; dw1
0x18000e779  mov     rcx, [rdi+118h]; hic
0x18000e780  mov     edx, 4005h; msg
0x18000e785  call    cs:__imp_ICSendMessage
0x18000e78b  movsxd  rdx, dword ptr [rdi+148h]
0x18000e792  mov     ecx, eax
0x18000e794  add     rdx, rcx; dwBytes
0x18000e797  mov     ecx, 2002h; uFlags
0x18000e79c  call    cs:__imp_GlobalAlloc
0x18000e7a2  mov     rcx, rax; hMem
0x18000e7a5  call    cs:__imp_GlobalLock
0x18000e7ab  mov     [rdi+120h], rax
0x18000e7b2  test    rax, rax
0x18000e7b5  jz      loc_18000E70C
0x18000e7bb  movsxd  r8, dword ptr [rdi+148h]; Size
0x18000e7c2  mov     rcx, rax; void *
0x18000e7c5  mov     rdx, [rdi+140h]; Src
0x18000e7cc  call    memmove_0
0x18000e7d1  mov     rcx, [rdi+120h]
0x18000e7d8  mov     eax, [rcx]
0x18000e7da  mov     edx, [rcx+20h]
0x18000e7dd  add     rcx, rax
0x18000e7e0  cmp     dword ptr [rdi+15Ch], 1
0x18000e7e7  lea     rax, [rcx+rdx*4]
0x18000e7eb  mov     [rdi+128h], rax
0x18000e7f2  jz      loc_18000E952
0x18000e7f8  test    byte ptr [rdi+164h], 20h
0x18000e7ff  jnz     loc_18000E952
0x18000e805  mov     edx, 428h; dwBytes
0x18000e80a  mov     ecx, 2002h; uFlags
0x18000e80f  call    cs:__imp_GlobalAlloc
0x18000e815  mov     rcx, rax; hMem
0x18000e818  call    cs:__imp_GlobalLock
0x18000e81e  mov     [rdi+130h], rax
0x18000e825  test    rax, rax
0x18000e828  jz      loc_18000E70C
0x18000e82e  mov     r8, [rdi+140h]; dw1
0x18000e835  mov     r9, rax; dw2
0x18000e838  mov     rcx, [rdi+118h]; hic
0x18000e83f  mov     edx, 400Ah; msg
0x18000e844  call    cs:__imp_ICSendMessage
0x18000e84a  test    eax, eax
0x18000e84c  js      loc_18000E92F
0x18000e852  mov     rcx, [rdi+130h]
0x18000e859  cmp     [rcx+14h], ebx
0x18000e85c  jnz     short loc_18000E878
0x18000e85e  movzx   eax, word ptr [rcx+0Eh]
0x18000e862  imul    eax, [rcx+4]
0x18000e866  add     eax, 1Fh
0x18000e869  shr     eax, 3
0x18000e86c  and     eax, 1FFFFFFCh
0x18000e871  imul    eax, [rcx+8]
0x18000e875  mov     [rcx+14h], eax
0x18000e878  mov     rcx, [rdi+130h]; pMem
0x18000e87f  mov     r9d, 0FFFFFFFFh
0x18000e885  mov     eax, [rcx+20h]
0x18000e888  shl     rax, 2
0x18000e88c  cmp     rax, r9
0x18000e88f  ja      loc_18000E70C
0x18000e895  add     eax, [rcx+14h]
0x18000e898  cmp     eax, [rcx+14h]
0x18000e89b  cmovnb  r9d, eax
0x18000e89f  jb      loc_18000E70C
0x18000e8a5  mov     eax, [rcx]
0x18000e8a7  lea     esi, [rax+r9]
0x18000e8ab  cmp     esi, eax
0x18000e8ad  jb      loc_18000E70C
0x18000e8b3  call    cs:__imp_GlobalHandle
0x18000e8b9  mov     rcx, rax; hMem
0x18000e8bc  call    cs:__imp_GlobalUnlock
0x18000e8c2  mov     rcx, [rdi+130h]; pMem
0x18000e8c9  call    cs:__imp_GlobalHandle
0x18000e8cf  mov     edx, esi; dwBytes
0x18000e8d1  mov     r8d, 2002h; uFlags
0x18000e8d7  mov     rcx, rax; hMem
0x18000e8da  call    cs:__imp_GlobalReAlloc
0x18000e8e0  mov     rcx, rax; hMem
0x18000e8e3  call    cs:__imp_GlobalLock
0x18000e8e9  mov     [rdi+130h], rax
0x18000e8f0  mov     r9, rax; dw2
0x18000e8f3  test    rax, rax
0x18000e8f6  jz      loc_18000E70C
0x18000e8fc  mov     ecx, [rax]
0x18000e8fe  mov     edx, [rax+20h]
0x18000e901  add     rcx, rax
0x18000e904  mov     r8, [rdi+140h]; dw1
0x18000e90b  lea     rax, [rcx+rdx*4]
0x18000e90f  mov     rcx, [rdi+118h]; hic
0x18000e916  mov     edx, 400Ch; msg
0x18000e91b  mov     [rdi+138h], rax
0x18000e922  call    cs:__imp_ICSendMessage
0x18000e928  test    rax, rax
0x18000e92b  jz      short loc_18000E952
0x18000e92d  jmp     short loc_18000E935
0x18000e92f  cdqe
0x18000e931  jmp     short loc_18000E935
0x18000e933  mov     eax, eax
0x18000e935  cmp     rax, 0FFFFFFFFFFFFFFFEh
0x18000e939  jnz     short loc_18000E942
0x18000e93b  mov     ebx, 80044066h
0x18000e940  jmp     short loc_18000E952
0x18000e942  xor     ecx, ecx
0x18000e944  mov     ebx, 80044067h
0x18000e949  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000e94d  setnz   cl
0x18000e950  add     ebx, ecx
0x18000e952  mov     rsi, [rsp+28h+arg_8]
0x18000e957  mov     eax, ebx
0x18000e959  mov     rbx, [rsp+28h+arg_0]
0x18000e95e  add     rsp, 20h
0x18000e962  pop     rdi
0x18000e963  retn
```
