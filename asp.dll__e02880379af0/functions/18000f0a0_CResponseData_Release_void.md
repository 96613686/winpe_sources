# CResponseData::Release(void)

- ea: `0x18000f0a0`
- end: `0x18000f1bd`
- name: `?Release@CResponseData@@UEAAKXZ`
- size: `285`
- prototype: `unsigned int __fastcall(CResponseData *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x18000f7e0`

## callees

- `0x18000f0a0`
- `0x18000f1d0`
- `0x180010550`

## import_xrefs

- `KERNEL32!HeapFree` at `0x180029f21`
- `KERNEL32!HeapFree` at `0x180029f39`
- `KERNEL32!HeapFree` at `0x180029f54`
- `KERNEL32!HeapFree` at `0x180029f6c`
- `KERNEL32!HeapFree` at `0x180029f8b`
- `KERNEL32!HeapFree` at `0x180029fa7`
- `KERNEL32!HeapFree` at `0x180029f21`
- `KERNEL32!HeapFree` at `0x180029f39`
- `KERNEL32!HeapFree` at `0x180029f54`
- `KERNEL32!HeapFree` at `0x180029f6c`
- `KERNEL32!HeapFree` at `0x180029f8b`
- `KERNEL32!HeapFree` at `0x180029fa7`
- `iisutil!?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z` at `0x18000f13f`
- `iisutil!?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z` at `0x18000f17d`
- `iisutil!?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z` at `0x18000f1af`
- `iisutil!?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z` at `0x18000f13f`
- `iisutil!?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z` at `0x18000f17d`
- `iisutil!?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z` at `0x18000f1af`

## pseudocode

```c
__int64 __fastcall CResponseData::Release(CResponseData *this)
{
  bool v1; // zf
  __int64 result; // rax
  void *v4; // r8
  void *v5; // r8
  void *v6; // r8
  void *v7; // r8
  void *v8; // rdi
  void *v9; // rsi
  CResponseBufferSet *v10; // rdi

  v1 = (*((_DWORD *)this + 71))-- == 1;
  result = *((unsigned int *)this + 71);
  if ( v1 )
  {
    v4 = (void *)*((_QWORD *)this + 14);
    *(_QWORD *)this = &CResponseData::`vftable';
    if ( v4 )
    {
      HeapFree(g_hDenaliHeap, 0, v4);
      *((_QWORD *)this + 14) = 0;
    }
    v5 = (void *)*((_QWORD *)this + 16);
    if ( v5 )
    {
      HeapFree(g_hDenaliHeap, 0, v5);
      *((_QWORD *)this + 16) = 0;
    }
    v6 = (void *)*((_QWORD *)this + 15);
    if ( v6 )
    {
      HeapFree(g_hDenaliHeap, 0, v6);
      *((_QWORD *)this + 15) = 0;
    }
    v7 = (void *)*((_QWORD *)this + 17);
    if ( v7 )
    {
      HeapFree(g_hDenaliHeap, 0, v7);
      *((_QWORD *)this + 17) = 0;
    }
    v8 = (void *)*((_QWORD *)this + 8);
    if ( v8 )
    {
      do
      {
        v9 = (void *)*((_QWORD *)v8 + 4);
        if ( (*(_BYTE *)v8 & 2) != 0 )
        {
          HeapFree(g_hDenaliHeap, 0, *((LPVOID *)v8 + 1));
          *((_QWORD *)v8 + 1) = 0;
        }
        if ( (*(_BYTE *)v8 & 4) != 0 )
        {
          HeapFree(g_hDenaliHeap, 0, *((LPVOID *)v8 + 2));
          *((_QWORD *)v8 + 2) = 0;
        }
        if ( CHTTPHeader::sm_pach )
          ALLOC_CACHE_HANDLER::Free(CHTTPHeader::sm_pach, v8);
        v8 = v9;
      }
      while ( v9 );
    }
    v10 = (CResponseBufferSet *)*((_QWORD *)this + 19);
    *((_QWORD *)this + 9) = 0;
    *((_QWORD *)this + 8) = 0;
    if ( v10 )
    {
      CResponseBufferSet::~CResponseBufferSet(v10);
      if ( CResponseBufferSet::sm_pach )
        ALLOC_CACHE_HANDLER::Free(CResponseBufferSet::sm_pach, v10);
      *((_QWORD *)this + 19) = 0;
    }
    CResponseCookies::~CResponseCookies((CResponseData *)((char *)this + 184));
    if ( CResponseData::sm_pach )
      ALLOC_CACHE_HANDLER::Free(CResponseData::sm_pach, this);
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x18000f0a0  push    rbx
0x18000f0a2  sub     rsp, 20h
0x18000f0a6  add     dword ptr [rcx+11Ch], 0FFFFFFFFh
0x18000f0ad  mov     rbx, rcx
0x18000f0b0  mov     eax, [rcx+11Ch]
0x18000f0b6  jnz     loc_18000F1B7
0x18000f0bc  mov     r8, [rcx+70h]; lpMem
0x18000f0c0  lea     rax, ??_7CResponseData@@6B@; const CResponseData::`vftable'
0x18000f0c7  mov     [rsp+28h+arg_0], rbp
0x18000f0cc  xor     ebp, ebp
0x18000f0ce  mov     [rsp+28h+arg_10], rdi
0x18000f0d3  mov     [rcx], rax
0x18000f0d6  test    r8, r8
0x18000f0d9  jnz     loc_180029F18
0x18000f0df  mov     r8, [rbx+80h]; lpMem
0x18000f0e6  test    r8, r8
0x18000f0e9  jnz     loc_180029F30
0x18000f0ef  mov     r8, [rbx+78h]; lpMem
0x18000f0f3  test    r8, r8
0x18000f0f6  jnz     loc_180029F4B
0x18000f0fc  mov     r8, [rbx+88h]; lpMem
0x18000f103  test    r8, r8
0x18000f106  jnz     loc_180029F63
0x18000f10c  mov     rdi, [rbx+40h]
0x18000f110  test    rdi, rdi
0x18000f113  jz      short loc_18000F152
0x18000f115  mov     [rsp+28h+arg_8], rsi
0x18000f11a  test    byte ptr [rdi], 2
0x18000f11d  mov     rsi, [rdi+20h]
0x18000f121  jnz     loc_180029F7E
0x18000f127  test    byte ptr [rdi], 4
0x18000f12a  jnz     loc_180029F9A
0x18000f130  mov     rcx, cs:?sm_pach@CHTTPHeader@@2PEAVALLOC_CACHE_HANDLER@@EA; ALLOC_CACHE_HANDLER * CHTTPHeader::sm_pach
0x18000f137  test    rcx, rcx
0x18000f13a  jz      short loc_18000F145
0x18000f13c  mov     rdx, rdi
0x18000f13f  call    cs:__imp_?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z; ALLOC_CACHE_HANDLER::Free(void *)
0x18000f145  mov     rdi, rsi
0x18000f148  test    rsi, rsi
0x18000f14b  jnz     short loc_18000F11A
0x18000f14d  mov     rsi, [rsp+28h+arg_8]
0x18000f152  mov     rdi, [rbx+98h]
0x18000f159  mov     [rbx+48h], rbp
0x18000f15d  mov     [rbx+40h], rbp
0x18000f161  test    rdi, rdi
0x18000f164  jz      short loc_18000F18A
0x18000f166  mov     rcx, rdi; this
0x18000f169  call    ??1CResponseBufferSet@@QEAA@XZ; CResponseBufferSet::~CResponseBufferSet(void)
0x18000f16e  mov     rcx, cs:?sm_pach@CResponseBufferSet@@2PEAVALLOC_CACHE_HANDLER@@EA; ALLOC_CACHE_HANDLER * CResponseBufferSet::sm_pach
0x18000f175  test    rcx, rcx
0x18000f178  jz      short loc_18000F183
0x18000f17a  mov     rdx, rdi
0x18000f17d  call    cs:__imp_?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z; ALLOC_CACHE_HANDLER::Free(void *)
0x18000f183  mov     [rbx+98h], rbp
0x18000f18a  lea     rcx, [rbx+0B8h]; this
0x18000f191  call    ??1CResponseCookies@@QEAA@XZ; CResponseCookies::~CResponseCookies(void)
0x18000f196  mov     rcx, cs:?sm_pach@CResponseData@@2PEAVALLOC_CACHE_HANDLER@@EA; ALLOC_CACHE_HANDLER * CResponseData::sm_pach
0x18000f19d  mov     rdi, [rsp+28h+arg_10]
0x18000f1a2  mov     rbp, [rsp+28h+arg_0]
0x18000f1a7  test    rcx, rcx
0x18000f1aa  jz      short loc_18000F1B5
0x18000f1ac  mov     rdx, rbx
0x18000f1af  call    cs:__imp_?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z; ALLOC_CACHE_HANDLER::Free(void *)
0x18000f1b5  xor     eax, eax
0x18000f1b7  add     rsp, 20h
0x18000f1bb  pop     rbx
0x18000f1bc  retn
0x180029f18  mov     rcx, cs:?g_hDenaliHeap@@3PEAXEA; hHeap
0x180029f1f  xor     edx, edx; dwFlags
0x180029f21  call    cs:__imp_HeapFree
0x180029f27  mov     [rbx+70h], rbp
0x180029f2b  jmp     loc_18000F0DF
0x180029f30  mov     rcx, cs:?g_hDenaliHeap@@3PEAXEA; hHeap
0x180029f37  xor     edx, edx; dwFlags
0x180029f39  call    cs:__imp_HeapFree
0x180029f3f  mov     [rbx+80h], rbp
0x180029f46  jmp     loc_18000F0EF
0x180029f4b  mov     rcx, cs:?g_hDenaliHeap@@3PEAXEA; hHeap
0x180029f52  xor     edx, edx; dwFlags
0x180029f54  call    cs:__imp_HeapFree
0x180029f5a  mov     [rbx+78h], rbp
0x180029f5e  jmp     loc_18000F0FC
0x180029f63  mov     rcx, cs:?g_hDenaliHeap@@3PEAXEA; hHeap
0x180029f6a  xor     edx, edx; dwFlags
0x180029f6c  call    cs:__imp_HeapFree
0x180029f72  mov     [rbx+88h], rbp
0x180029f79  jmp     loc_18000F10C
0x180029f7e  mov     r8, [rdi+8]; lpMem
0x180029f82  xor     edx, edx; dwFlags
0x180029f84  mov     rcx, cs:?g_hDenaliHeap@@3PEAXEA; hHeap
0x180029f8b  call    cs:__imp_HeapFree
0x180029f91  mov     [rdi+8], rbp
0x180029f95  jmp     loc_18000F127
0x180029f9a  mov     r8, [rdi+10h]; lpMem
0x180029f9e  xor     edx, edx; dwFlags
0x180029fa0  mov     rcx, cs:?g_hDenaliHeap@@3PEAXEA; hHeap
0x180029fa7  call    cs:__imp_HeapFree
0x180029fad  mov     [rdi+10h], rbp
0x180029fb1  jmp     loc_18000F130
```
