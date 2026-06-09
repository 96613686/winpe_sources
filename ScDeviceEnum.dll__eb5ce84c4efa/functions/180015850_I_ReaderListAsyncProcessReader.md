# I_ReaderListAsyncProcessReader

- ea: `0x180015850`
- end: `0x180015c09`
- name: `I_ReaderListAsyncProcessReader`
- size: `953`
- prototype: `__int64 __fastcall(__int64, __int64, int, const void *, SIZE_T dwBytes)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x18001b00c`

## callees

- `0x180001f26`
- `0x180007178`
- `0x1800071d4`
- `0x180015850`
- `0x18001ca98`
- `0x18001cc6c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180015ac2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180015ad4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180015aeb`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180015b99`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180015ac2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180015ad4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180015aeb`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180015b99`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800158c4`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180015965`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800159f6`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180015a5c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800158c4`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180015965`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800159f6`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180015a5c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015b35`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015b35`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x180015ba7`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x180015ba7`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x180015b2a`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x180015b2a`

## pseudocode

```c
__int64 __fastcall I_ReaderListAsyncProcessReader(__int64 a1, __int64 a2, int a3, const void *a4, SIZE_T dwBytes)
{
  DWORD LastError; // ebx
  __int64 v9; // rcx
  LPVOID *v10; // r14
  PVOID v11; // rcx
  void *v12; // rbp
  __int64 v13; // r8
  wchar_t *v14; // rax
  __int64 v15; // rcx
  _QWORD *v16; // rcx
  __int64 v17; // rdx
  const wchar_t *v18; // r8
  __int64 v19; // rdx
  HANDLE v20; // rcx
  void *v21; // rax
  __int64 v22; // rcx
  _QWORD *v23; // rax
  __int64 v24; // rcx
  void *v25; // rdi
  struct _TP_WORK *ThreadpoolWork; // rax
  __int64 v27; // rcx

  WppTraceIndent(a1, 0);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 208, &WPP_173052b9a503333cb537dada0074ae31_Traceguids, WPP_pszIndent);
  }
  LastError = 8;
  v10 = (LPVOID *)HeapAlloc(hHeap, 8u, 0xF8u);
  if ( !v10 )
  {
    WppTraceIndent(v9, 2);
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_s(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        209,
        &WPP_173052b9a503333cb537dada0074ae31_Traceguids,
        WPP_pszIndent);
    }
    goto LABEL_46;
  }
  v12 = 0;
  if ( !*(_QWORD *)a2 )
  {
    LastError = 87;
LABEL_34:
    if ( *v10 )
      HeapFree(hHeap, 0, *v10);
    HeapFree(hHeap, 0, v10);
    if ( v12 )
      HeapFree(hHeap, 0, v12);
    goto LABEL_46;
  }
  v13 = -1;
  do
    ++v13;
  while ( *(_WORD *)(*(_QWORD *)a2 + 2 * v13) );
  v14 = (wchar_t *)HeapAlloc(hHeap, 8u, 2 * v13 + 2);
  *v10 = v14;
  if ( !v14 )
  {
    WppTraceIndent(v15, 2);
    v16 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_34;
    }
    v17 = 210;
    goto LABEL_33;
  }
  v18 = *(const wchar_t **)a2;
  v19 = -1;
  do
    ++v19;
  while ( v18[v19] );
  if ( StringCchCopyW(v14, v19 + 1, v18) < 0 )
  {
    LastError = 122;
    goto LABEL_34;
  }
  v20 = hHeap;
  *((_DWORD *)v10 + 3) = *(_DWORD *)(a2 + 12);
  v21 = HeapAlloc(v20, 8u, (unsigned int)dwBytes);
  v12 = v21;
  if ( !v21 )
  {
    WppTraceIndent(v22, 2);
    v16 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_34;
    }
    v17 = 211;
    goto LABEL_33;
  }
  memcpy_0(v21, a4, (unsigned int)dwBytes);
  v23 = HeapAlloc(hHeap, 8u, 0x28u);
  v25 = v23;
  if ( !v23 )
  {
    WppTraceIndent(v24, 2);
    v16 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_34;
    }
    v17 = 212;
LABEL_33:
    WPP_SF_s(v16[2], v17, &WPP_173052b9a503333cb537dada0074ae31_Traceguids, WPP_pszIndent);
    goto LABEL_34;
  }
  *v23 = a1;
  v23[1] = v10;
  *((_DWORD *)v23 + 4) = a3;
  v23[3] = v12;
  *((_DWORD *)v23 + 8) = dwBytes;
  _InterlockedIncrement((volatile signed __int32 *)(a1 + 384));
  ThreadpoolWork = CreateThreadpoolWork(I_ReaderListReaderProcessingWorker, v23, (PTP_CALLBACK_ENVIRON)(a1 + 272));
  if ( ThreadpoolWork )
  {
    LastError = 0;
    SubmitThreadpoolWork(ThreadpoolWork);
  }
  else
  {
    LastError = GetLastError();
    WppTraceIndent(v27, 2);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
    {
      WPP_SF_sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        213,
        (unsigned int)&WPP_173052b9a503333cb537dada0074ae31_Traceguids,
        WPP_pszIndent,
        LastError);
    }
    _InterlockedDecrement((volatile signed __int32 *)(a1 + 384));
    HeapFree(hHeap, 0, v25);
  }
LABEL_46:
  WppTraceIndent(v11, 1);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      214,
      (unsigned int)&WPP_173052b9a503333cb537dada0074ae31_Traceguids,
      WPP_pszIndent,
      LastError);
  }
  return LastError;
}

```

## disassembly

```asm
0x180015850  mov     [rsp+Src], r9
0x180015855  push    rbx
0x180015856  push    rbp
0x180015857  push    rsi
0x180015858  push    rdi
0x180015859  push    r12
0x18001585b  push    r13
0x18001585d  push    r14
0x18001585f  push    r15
0x180015861  sub     rsp, 38h
0x180015865  mov     r15, rdx
0x180015868  mov     r13d, r8d
0x18001586b  xor     edx, edx
0x18001586d  mov     rsi, rcx
0x180015870  call    WppTraceIndent
0x180015875  mov     rcx, cs:WPP_GLOBAL_Control
0x18001587c  lea     rax, WPP_GLOBAL_Control
0x180015883  cmp     rcx, rax
0x180015886  jz      short loc_1800158B0
0x180015888  test    byte ptr [rcx+1Ch], 2
0x18001588c  jz      short loc_1800158B0
0x18001588e  cmp     byte ptr [rcx+19h], 5
0x180015892  jb      short loc_1800158B0
0x180015894  mov     r9, cs:WPP_pszIndent
0x18001589b  lea     r8, WPP_173052b9a503333cb537dada0074ae31_Traceguids
0x1800158a2  mov     rcx, [rcx+10h]
0x1800158a6  mov     edx, 0D0h
0x1800158ab  call    WPP_SF_s
0x1800158b0  mov     rcx, cs:hHeap; hHeap
0x1800158b7  mov     ebx, 8
0x1800158bc  mov     edx, ebx; dwFlags
0x1800158be  mov     r8d, 0F8h; dwBytes
0x1800158c4  call    cs:__imp_HeapAlloc
0x1800158ca  xor     r12d, r12d
0x1800158cd  mov     r14, rax
0x1800158d0  test    rax, rax
0x1800158d3  jnz     short loc_180015929
0x1800158d5  lea     edx, [rbx-6]
0x1800158d8  call    WppTraceIndent
0x1800158dd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800158e4  lea     r15, WPP_GLOBAL_Control
0x1800158eb  cmp     rcx, r15
0x1800158ee  jz      loc_180015BB4
0x1800158f4  test    byte ptr [rcx+1Ch], 1
0x1800158f8  jz      loc_180015BB4
0x1800158fe  cmp     byte ptr [rcx+19h], 2
0x180015902  jb      loc_180015BB4
0x180015908  mov     r9, cs:WPP_pszIndent
0x18001590f  lea     r8, WPP_173052b9a503333cb537dada0074ae31_Traceguids
0x180015916  mov     rcx, [rcx+10h]
0x18001591a  mov     edx, 0D1h
0x18001591f  call    WPP_SF_s
0x180015924  jmp     loc_180015BB4
0x180015929  mov     rax, [r15]
0x18001592c  mov     rbp, r12
0x18001592f  mov     rdi, r12
0x180015932  test    rax, rax
0x180015935  jnz     short loc_180015946
0x180015937  lea     ebx, [rax+57h]
0x18001593a  lea     r15, WPP_GLOBAL_Control
0x180015941  jmp     loc_180015AB1
0x180015946  or      r8, 0FFFFFFFFFFFFFFFFh
0x18001594a  inc     r8
0x18001594d  cmp     [rax+r8*2], r12w
0x180015952  jnz     short loc_18001594A
0x180015954  mov     rcx, cs:hHeap; hHeap
0x18001595b  lea     r8, ds:2[r8*2]; dwBytes
0x180015963  mov     edx, ebx; dwFlags
0x180015965  call    cs:__imp_HeapAlloc
0x18001596b  mov     [r14], rax
0x18001596e  test    rax, rax
0x180015971  jnz     short loc_1800159B0
0x180015973  lea     edx, [rax+2]
0x180015976  call    WppTraceIndent
0x18001597b  mov     rcx, cs:WPP_GLOBAL_Control
0x180015982  lea     r15, WPP_GLOBAL_Control
0x180015989  cmp     rcx, r15
0x18001598c  jz      loc_180015AB1
0x180015992  test    byte ptr [rcx+1Ch], 1
0x180015996  jz      loc_180015AB1
0x18001599c  cmp     byte ptr [rcx+19h], 2
0x1800159a0  jb      loc_180015AB1
0x1800159a6  mov     edx, 0D2h
0x1800159ab  jmp     loc_180015A9A
0x1800159b0  mov     r8, [r15]; pszSrc
0x1800159b3  or      rdx, 0FFFFFFFFFFFFFFFFh
0x1800159b7  inc     rdx
0x1800159ba  cmp     [r8+rdx*2], r12w
0x1800159bf  jnz     short loc_1800159B7
0x1800159c1  inc     rdx; cchDest
0x1800159c4  mov     rcx, rax; pszDest
0x1800159c7  call    StringCchCopyW
0x1800159cc  test    eax, eax
0x1800159ce  jns     short loc_1800159DA
0x1800159d0  mov     ebx, 7Ah ; 'z'
0x1800159d5  jmp     loc_18001593A
0x1800159da  mov     eax, [r15+0Ch]
0x1800159de  mov     edx, ebx; dwFlags
0x1800159e0  mov     r15d, dword ptr [rsp+78h+dwBytes]
0x1800159e8  mov     rcx, cs:hHeap; hHeap
0x1800159ef  mov     r8d, r15d; dwBytes
0x1800159f2  mov     [r14+0Ch], eax
0x1800159f6  call    cs:__imp_HeapAlloc
0x1800159fc  mov     rbp, rax
0x1800159ff  test    rax, rax
0x180015a02  jnz     short loc_180015A3A
0x180015a04  lea     edx, [rax+2]
0x180015a07  call    WppTraceIndent
0x180015a0c  mov     rcx, cs:WPP_GLOBAL_Control
0x180015a13  lea     r15, WPP_GLOBAL_Control
0x180015a1a  cmp     rcx, r15
0x180015a1d  jz      loc_180015AB1
0x180015a23  test    byte ptr [rcx+1Ch], 1
0x180015a27  jz      loc_180015AB1
0x180015a2d  cmp     byte ptr [rcx+19h], 2
0x180015a31  jb      short loc_180015AB1
0x180015a33  mov     edx, 0D3h
0x180015a38  jmp     short loc_180015A9A
0x180015a3a  mov     rdx, [rsp+78h+Src]; Src
0x180015a42  mov     r8, r15; Size
0x180015a45  mov     rcx, rbp; void *
0x180015a48  call    memcpy_0
0x180015a4d  mov     rcx, cs:hHeap; hHeap
0x180015a54  mov     r8d, 28h ; '('; dwBytes
0x180015a5a  mov     edx, ebx; dwFlags
0x180015a5c  call    cs:__imp_HeapAlloc
0x180015a62  mov     rdi, rax
0x180015a65  test    rax, rax
0x180015a68  jnz     loc_180015AFF
0x180015a6e  lea     edx, [rax+2]
0x180015a71  call    WppTraceIndent
0x180015a76  mov     rcx, cs:WPP_GLOBAL_Control
0x180015a7d  lea     r15, WPP_GLOBAL_Control
0x180015a84  cmp     rcx, r15
0x180015a87  jz      short loc_180015AB1
0x180015a89  test    byte ptr [rcx+1Ch], 1
0x180015a8d  jz      short loc_180015AB1
0x180015a8f  cmp     byte ptr [rcx+19h], 2
0x180015a93  jb      short loc_180015AB1
0x180015a95  mov     edx, 0D4h
0x180015a9a  mov     r9, cs:WPP_pszIndent
0x180015aa1  lea     r8, WPP_173052b9a503333cb537dada0074ae31_Traceguids
0x180015aa8  mov     rcx, [rcx+10h]
0x180015aac  call    WPP_SF_s
0x180015ab1  mov     r8, [r14]; lpMem
0x180015ab4  test    r8, r8
0x180015ab7  jz      short loc_180015AC8
0x180015ab9  mov     rcx, cs:hHeap; hHeap
0x180015ac0  xor     edx, edx; dwFlags
0x180015ac2  call    cs:__imp_HeapFree
0x180015ac8  mov     rcx, cs:hHeap; hHeap
0x180015acf  mov     r8, r14; lpMem
0x180015ad2  xor     edx, edx; dwFlags
0x180015ad4  call    cs:__imp_HeapFree
0x180015ada  test    rbp, rbp
0x180015add  jz      short loc_180015AF1
0x180015adf  mov     rcx, cs:hHeap; hHeap
0x180015ae6  mov     r8, rbp; lpMem
0x180015ae9  xor     edx, edx; dwFlags
0x180015aeb  call    cs:__imp_HeapFree
0x180015af1  test    rdi, rdi
0x180015af4  jz      loc_180015BB4
0x180015afa  jmp     loc_180015B8D
0x180015aff  mov     [rax], rsi
0x180015b02  mov     [rax+8], r14
0x180015b06  mov     [rax+10h], r13d
0x180015b0a  mov     [rax+18h], rbp
0x180015b0e  mov     [rax+20h], r15d
0x180015b12  lock inc dword ptr [rsi+180h]
0x180015b19  lea     r8, [rsi+110h]; pcbe
0x180015b20  mov     rdx, rax; pv
0x180015b23  lea     rcx, I_ReaderListReaderProcessingWorker; pfnwk
0x180015b2a  call    cs:__imp_CreateThreadpoolWork
0x180015b30  test    rax, rax
0x180015b33  jnz     short loc_180015BA1
0x180015b35  call    cs:__imp_GetLastError
0x180015b3b  mov     edx, 2
0x180015b40  mov     ebx, eax
0x180015b42  call    WppTraceIndent
0x180015b47  mov     rcx, cs:WPP_GLOBAL_Control
0x180015b4e  lea     r15, WPP_GLOBAL_Control
0x180015b55  cmp     rcx, r15
0x180015b58  jz      short loc_180015B86
0x180015b5a  test    byte ptr [rcx+1Ch], 1
0x180015b5e  jz      short loc_180015B86
0x180015b60  cmp     byte ptr [rcx+19h], 3
0x180015b64  jb      short loc_180015B86
0x180015b66  mov     r9, cs:WPP_pszIndent
0x180015b6d  lea     r8, WPP_173052b9a503333cb537dada0074ae31_Traceguids
0x180015b74  mov     rcx, [rcx+10h]
0x180015b78  mov     edx, 0D5h
0x180015b7d  mov     [rsp+78h+var_58], ebx
0x180015b81  call    WPP_SF_sd
0x180015b86  lock dec dword ptr [rsi+180h]
0x180015b8d  mov     rcx, cs:hHeap; hHeap
0x180015b94  mov     r8, rdi; lpMem
0x180015b97  xor     edx, edx; dwFlags
0x180015b99  call    cs:__imp_HeapFree
0x180015b9f  jmp     short loc_180015BB4
0x180015ba1  mov     rcx, rax; pwk
0x180015ba4  mov     ebx, r12d
0x180015ba7  call    cs:__imp_SubmitThreadpoolWork
0x180015bad  lea     r15, WPP_GLOBAL_Control
0x180015bb4  mov     edx, 1
0x180015bb9  call    WppTraceIndent
0x180015bbe  mov     rcx, cs:WPP_GLOBAL_Control
0x180015bc5  cmp     rcx, r15
0x180015bc8  jz      short loc_180015BF6
0x180015bca  test    byte ptr [rcx+1Ch], 2
0x180015bce  jz      short loc_180015BF6
0x180015bd0  cmp     byte ptr [rcx+19h], 5
0x180015bd4  jb      short loc_180015BF6
0x180015bd6  mov     r9, cs:WPP_pszIndent
0x180015bdd  lea     r8, WPP_173052b9a503333cb537dada0074ae31_Traceguids
0x180015be4  mov     rcx, [rcx+10h]
0x180015be8  mov     edx, 0D6h
0x180015bed  mov     [rsp+78h+var_58], ebx
0x180015bf1  call    WPP_SF_sd
0x180015bf6  mov     eax, ebx
0x180015bf8  add     rsp, 38h
0x180015bfc  pop     r15
0x180015bfe  pop     r14
0x180015c00  pop     r13
0x180015c02  pop     r12
0x180015c04  pop     rdi
0x180015c05  pop     rsi
0x180015c06  pop     rbp
0x180015c07  pop     rbx
0x180015c08  retn
```
