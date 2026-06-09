# CAVIFile::CUnknownImpl::Release(void)

- ea: `0x18000b5c0`
- end: `0x18000b756`
- name: `?Release@CUnknownImpl@CAVIFile@@UEAAKXZ`
- size: `406`
- prototype: `unsigned int __fastcall(CAVIFile::CUnknownImpl *__hidden this)`
- caller_count: `0`
- callee_count: `7`
- tags: `file_ops`

## callees

- `0x180001048`
- `0x1800041c0`
- `0x180008c3c`
- `0x18000b5c0`
- `0x18000b87c`
- `0x180014580`
- `0x1800148c4`

## import_xrefs

- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x18000b682`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x18000b6b3`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x18000b682`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x18000b6b3`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x18000b679`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x18000b68f`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x18000b6aa`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x18000b6c0`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x18000b679`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x18000b68f`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x18000b6aa`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x18000b6c0`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18000b698`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18000b6c9`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18000b698`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18000b6c9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000b5da`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000b5da`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000b707`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000b707`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000b6fe`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000b745`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000b6fe`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000b745`

## pseudocode

```c
__int64 __fastcall CAVIFile::CUnknownImpl::Release(CAVIFile::CUnknownImpl *this)
{
  __int64 v1; // rdi
  struct _RTL_CRITICAL_SECTION *v3; // rbx
  int v4; // ecx
  __int64 i; // rsi
  unsigned __int64 v6; // rax
  void *v7; // rbp
  const void *v8; // rcx
  HGLOBAL v9; // rax
  HGLOBAL v10; // rax
  const void *v11; // rcx
  HGLOBAL v12; // rax
  HGLOBAL v13; // rax
  unsigned int v15; // edi

  v1 = *((_QWORD *)this + 1);
  v3 = (struct _RTL_CRITICAL_SECTION *)(v1 + 1264);
  EnterCriticalSection((LPCRITICAL_SECTION)(v1 + 1264));
  v4 = *((_DWORD *)this + 4);
  --uUseCount;
  *((_DWORD *)this + 4) = v4 - 1;
  if ( v4 == 1 )
  {
    if ( *(_DWORD *)(v1 + 728) )
    {
      *((_DWORD *)this + 4) = 1;
      SaveChanges((struct CAVIFile *)v1, 1);
      --*((_DWORD *)this + 4);
    }
    for ( i = 0; ; i = (unsigned int)(i + 1) )
    {
      v6 = 64;
      if ( *(_DWORD *)(v1 + 104) <= 0x40u )
        v6 = *(unsigned int *)(v1 + 104);
      if ( (unsigned int)i >= v6 )
        break;
      v7 = *(void **)(v1 + 8 * i + 736);
      if ( v7 )
      {
        CAVIStream::~CAVIStream(*(CAVIStream **)(v1 + 8 * i + 736));
        operator delete(v7, 0x580u);
      }
    }
    if ( *(_QWORD *)(v1 + 664) )
    {
      shfileRelease();
      shfileClose(*(LPCVOID *)(v1 + 664));
    }
    v8 = *(const void **)(v1 + 1248);
    if ( v8 )
    {
      v9 = GlobalHandle(v8);
      GlobalUnlock(v9);
      v10 = GlobalHandle(*(LPCVOID *)(v1 + 1248));
      GlobalFree(v10);
    }
    v11 = *(const void **)(v1 + 712);
    if ( v11 )
    {
      v12 = GlobalHandle(v11);
      GlobalUnlock(v12);
      v13 = GlobalHandle(*(LPCVOID *)(v1 + 712));
      GlobalFree(v13);
    }
    if ( *(_QWORD *)(v1 + 1256) )
      EndBuffered();
    *(_QWORD *)(v1 + 664) = 0;
    *(_QWORD *)(v1 + 1248) = 0;
    if ( v1 != -1264 )
      LeaveCriticalSection((LPCRITICAL_SECTION)(v1 + 1264));
    DeleteCriticalSection((LPCRITICAL_SECTION)(v1 + 1264));
    *(_QWORD *)(v1 + 24) = &CAVIFile::CF::`vftable';
    operator delete((void *)v1, 0x518u);
    return 0;
  }
  else
  {
    if ( *(_QWORD *)(v1 + 664) )
      shfileRelease();
    v15 = *((_DWORD *)this + 4);
    if ( v3 )
      LeaveCriticalSection(v3);
    return v15;
  }
}

```

## disassembly

```asm
0x18000b5c0  push    rbx
0x18000b5c2  push    rbp
0x18000b5c3  push    rsi
0x18000b5c4  push    rdi
0x18000b5c5  sub     rsp, 28h
0x18000b5c9  mov     rdi, [rcx+8]
0x18000b5cd  mov     rsi, rcx
0x18000b5d0  lea     rbx, [rdi+4F0h]
0x18000b5d7  mov     rcx, rbx; lpCriticalSection
0x18000b5da  call    cs:__imp_EnterCriticalSection
0x18000b5e0  mov     ecx, [rsi+10h]
0x18000b5e3  or      ebp, 0FFFFFFFFh
0x18000b5e6  add     cs:uUseCount, ebp
0x18000b5ec  lea     eax, [rcx-1]
0x18000b5ef  mov     [rsi+10h], eax
0x18000b5f2  test    eax, eax
0x18000b5f4  jnz     loc_18000B729
0x18000b5fa  cmp     [rdi+2D8h], eax
0x18000b600  jz      short loc_18000B613
0x18000b602  mov     [rsi+10h], ecx
0x18000b605  lea     edx, [rax+1]; int
0x18000b608  mov     rcx, rdi; struct CAVIFile *
0x18000b60b  call    ?SaveChanges@@YAJPEAVCAVIFile@@H@Z; SaveChanges(CAVIFile *,int)
0x18000b610  add     [rsi+10h], ebp
0x18000b613  xor     esi, esi
0x18000b615  cmp     dword ptr [rdi+68h], 40h ; '@'
0x18000b619  mov     eax, 40h ; '@'
0x18000b61e  ja      short loc_18000B623
0x18000b620  mov     eax, [rdi+68h]
0x18000b623  mov     ebp, esi
0x18000b625  cmp     rbp, rax
0x18000b628  jnb     short loc_18000B650
0x18000b62a  mov     rbp, [rdi+rsi*8+2E0h]
0x18000b632  test    rbp, rbp
0x18000b635  jz      short loc_18000B64C
0x18000b637  mov     rcx, rbp; this
0x18000b63a  call    ??1CAVIStream@@QEAA@XZ; CAVIStream::~CAVIStream(void)
0x18000b63f  mov     edx, 580h; unsigned __int64
0x18000b644  mov     rcx, rbp; void *
0x18000b647  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000b64c  inc     esi
0x18000b64e  jmp     short loc_18000B615
0x18000b650  mov     rcx, [rdi+298h]
0x18000b657  test    rcx, rcx
0x18000b65a  jz      short loc_18000B66D
0x18000b65c  call    shfileRelease
0x18000b661  mov     rcx, [rdi+298h]; pMem
0x18000b668  call    shfileClose
0x18000b66d  mov     rcx, [rdi+4E0h]; pMem
0x18000b674  test    rcx, rcx
0x18000b677  jz      short loc_18000B69E
0x18000b679  call    cs:__imp_GlobalHandle
0x18000b67f  mov     rcx, rax; hMem
0x18000b682  call    cs:__imp_GlobalUnlock
0x18000b688  mov     rcx, [rdi+4E0h]; pMem
0x18000b68f  call    cs:__imp_GlobalHandle
0x18000b695  mov     rcx, rax; hMem
0x18000b698  call    cs:__imp_GlobalFree
0x18000b69e  mov     rcx, [rdi+2C8h]; pMem
0x18000b6a5  test    rcx, rcx
0x18000b6a8  jz      short loc_18000B6CF
0x18000b6aa  call    cs:__imp_GlobalHandle
0x18000b6b0  mov     rcx, rax; hMem
0x18000b6b3  call    cs:__imp_GlobalUnlock
0x18000b6b9  mov     rcx, [rdi+2C8h]; pMem
0x18000b6c0  call    cs:__imp_GlobalHandle
0x18000b6c6  mov     rcx, rax; hMem
0x18000b6c9  call    cs:__imp_GlobalFree
0x18000b6cf  mov     rcx, [rdi+4E8h]
0x18000b6d6  test    rcx, rcx
0x18000b6d9  jz      short loc_18000B6E0
0x18000b6db  call    EndBuffered
0x18000b6e0  mov     qword ptr [rdi+298h], 0
0x18000b6eb  mov     qword ptr [rdi+4E0h], 0
0x18000b6f6  test    rbx, rbx
0x18000b6f9  jz      short loc_18000B704
0x18000b6fb  mov     rcx, rbx; lpCriticalSection
0x18000b6fe  call    cs:__imp_LeaveCriticalSection
0x18000b704  mov     rcx, rbx; lpCriticalSection
0x18000b707  call    cs:__imp_DeleteCriticalSection
0x18000b70d  lea     rax, ??_7CF@CAVIFile@@6B@; const CAVIFile::CF::`vftable'
0x18000b714  mov     edx, 518h; unsigned __int64
0x18000b719  mov     rcx, rdi; void *
0x18000b71c  mov     [rdi+18h], rax
0x18000b720  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000b725  xor     eax, eax
0x18000b727  jmp     short loc_18000B74D
0x18000b729  mov     rcx, [rdi+298h]
0x18000b730  test    rcx, rcx
0x18000b733  jz      short loc_18000B73A
0x18000b735  call    shfileRelease
0x18000b73a  mov     edi, [rsi+10h]
0x18000b73d  test    rbx, rbx
0x18000b740  jz      short loc_18000B74B
0x18000b742  mov     rcx, rbx; lpCriticalSection
0x18000b745  call    cs:__imp_LeaveCriticalSection
0x18000b74b  mov     eax, edi
0x18000b74d  add     rsp, 28h
0x18000b751  pop     rdi
0x18000b752  pop     rsi
0x18000b753  pop     rbp
0x18000b754  pop     rbx
0x18000b755  retn
```
