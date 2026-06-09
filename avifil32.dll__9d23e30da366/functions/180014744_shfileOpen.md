# shfileOpen

- ea: `0x180014744`
- end: `0x180014878`
- name: `shfileOpen`
- size: `308`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName)`
- caller_count: `2`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x180005f34`
- `0x180009ef0`

## callees

- `0x180001008`
- `0x180001048`
- `0x180014744`
- `0x180016350`
- `0x18001637c`
- `0x180016738`

## import_xrefs

- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x180014843`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x180014843`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x18001476c`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x18001476c`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x18001483a`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x18001484c`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x18001483a`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x18001484c`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x180014763`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x180014763`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180014855`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180014855`
- `WINMM!mmioOpenW` at `0x180014828`
- `WINMM!mmioOpenW` at `0x180014828`

## pseudocode

```c
_DWORD *__fastcall shfileOpen(WCHAR *lpFileName, __int64 a2, DWORD a3)
{
  HGLOBAL v5; // rax
  _DWORD *v6; // rax
  _DWORD *v7; // rbx
  _QWORD *v9; // rax
  _QWORD *v10; // rdi
  CFileBuffer *v11; // rsi
  __int64 v12; // rbp
  void *v13; // rdi
  HMMIO v14; // rax
  HGLOBAL v15; // rax
  HGLOBAL v16; // rax

  v5 = GlobalAlloc(0x2040u, 0x18u);
  v6 = GlobalLock(v5);
  v7 = v6;
  if ( !v6 )
    return 0;
  *((_QWORD *)v6 + 1) = 0;
  if ( (a3 & 0x1000) == 0 )
    goto LABEL_18;
  v9 = operator new(0x190u);
  v10 = v9;
  if ( v9 )
  {
    v11 = (CFileBuffer *)(v9 + 1);
    v12 = 4;
    do
    {
      CFileBuffer::CFileBuffer(v11);
      v11 = (CFileBuffer *)((char *)v11 + 88);
      --v12;
    }
    while ( v12 );
    *(_QWORD *)((char *)v10 + 372) = 0;
    v10[48] = -1;
  }
  else
  {
    v10 = 0;
  }
  *((_QWORD *)v7 + 2) = v10;
  if ( !v10 || !(unsigned int)CFileStream::Open((CFileStream *)v10, lpFileName, a3 & 3, a3 & 0x1000) )
  {
LABEL_18:
    v13 = (void *)*((_QWORD *)v7 + 2);
    if ( v13 )
    {
      CFileStream::~CFileStream(*((CFileStream **)v7 + 2));
      operator delete(v13, 0x190u);
    }
    *((_QWORD *)v7 + 2) = 0;
    v14 = mmioOpenW(lpFileName, 0, a3);
    *((_QWORD *)v7 + 1) = v14;
    if ( !v14 )
    {
      v15 = GlobalHandle(v7);
      GlobalUnlock(v15);
      v16 = GlobalHandle(v7);
      GlobalFree(v16);
      return 0;
    }
  }
  *v7 = 1;
  return v7;
}

```

## disassembly

```asm
0x180014744  push    rbx
0x180014746  push    rbp
0x180014747  push    rsi
0x180014748  push    rdi
0x180014749  push    r12
0x18001474b  push    r14
0x18001474d  push    r15
0x18001474f  sub     rsp, 20h
0x180014753  mov     r12, rcx
0x180014756  mov     edx, 18h; dwBytes
0x18001475b  mov     ecx, 2040h; uFlags
0x180014760  mov     r15d, r8d
0x180014763  call    cs:__imp_GlobalAlloc
0x180014769  mov     rcx, rax; hMem
0x18001476c  call    cs:__imp_GlobalLock
0x180014772  mov     rbx, rax
0x180014775  test    rax, rax
0x180014778  jnz     short loc_180014781
0x18001477a  xor     eax, eax
0x18001477c  jmp     loc_180014869
0x180014781  mov     r14d, r15d
0x180014784  mov     qword ptr [rax+8], 0
0x18001478c  and     r14d, 1000h
0x180014793  jz      short loc_1800147FA
0x180014795  mov     ecx, 190h; Size
0x18001479a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001479f  mov     rdi, rax
0x1800147a2  test    rax, rax
0x1800147a5  jz      short loc_1800147D6
0x1800147a7  lea     rsi, [rax+8]
0x1800147ab  mov     ebp, 4
0x1800147b0  mov     rcx, rsi; this
0x1800147b3  call    ??0CFileBuffer@@QEAA@XZ; CFileBuffer::CFileBuffer(void)
0x1800147b8  add     rsi, 58h ; 'X'
0x1800147bc  sub     rbp, 1
0x1800147c0  jnz     short loc_1800147B0
0x1800147c2  mov     [rdi+174h], rbp
0x1800147c9  mov     qword ptr [rdi+180h], 0FFFFFFFFFFFFFFFFh
0x1800147d4  jmp     short loc_1800147D8
0x1800147d6  xor     edi, edi
0x1800147d8  mov     [rbx+10h], rdi
0x1800147dc  test    rdi, rdi
0x1800147df  jz      short loc_1800147FA
0x1800147e1  mov     r8d, r15d
0x1800147e4  mov     r9d, r14d; int
0x1800147e7  and     r8d, 3; int
0x1800147eb  mov     rdx, r12; lpFileName
0x1800147ee  mov     rcx, rdi; this
0x1800147f1  call    ?Open@CFileStream@@QEAAHPEAGHH@Z; CFileStream::Open(ushort *,int,int)
0x1800147f6  test    eax, eax
0x1800147f8  jnz     short loc_180014860
0x1800147fa  mov     rdi, [rbx+10h]
0x1800147fe  test    rdi, rdi
0x180014801  jz      short loc_180014818
0x180014803  mov     rcx, rdi; this
0x180014806  call    ??1CFileStream@@QEAA@XZ; CFileStream::~CFileStream(void)
0x18001480b  mov     edx, 190h; unsigned __int64
0x180014810  mov     rcx, rdi; void *
0x180014813  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180014818  mov     r8d, r15d; fdwOpen
0x18001481b  mov     qword ptr [rbx+10h], 0
0x180014823  xor     edx, edx; pmmioinfo
0x180014825  mov     rcx, r12; pszFileName
0x180014828  call    cs:__imp_mmioOpenW
0x18001482e  mov     [rbx+8], rax
0x180014832  test    rax, rax
0x180014835  jnz     short loc_180014860
0x180014837  mov     rcx, rbx; pMem
0x18001483a  call    cs:__imp_GlobalHandle
0x180014840  mov     rcx, rax; hMem
0x180014843  call    cs:__imp_GlobalUnlock
0x180014849  mov     rcx, rbx; pMem
0x18001484c  call    cs:__imp_GlobalHandle
0x180014852  mov     rcx, rax; hMem
0x180014855  call    cs:__imp_GlobalFree
0x18001485b  jmp     loc_18001477A
0x180014860  mov     dword ptr [rbx], 1
0x180014866  mov     rax, rbx
0x180014869  add     rsp, 20h
0x18001486d  pop     r15
0x18001486f  pop     r14
0x180014871  pop     r12
0x180014873  pop     rdi
0x180014874  pop     rsi
0x180014875  pop     rbp
0x180014876  pop     rbx
0x180014877  retn
```
