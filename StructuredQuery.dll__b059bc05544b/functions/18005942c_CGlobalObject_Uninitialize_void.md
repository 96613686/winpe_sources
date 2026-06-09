# CGlobalObject::Uninitialize(void)

- ea: `0x18005942c`
- end: `0x180059494`
- name: `?Uninitialize@CGlobalObject@@QEAAXXZ`
- size: `104`
- prototype: `void __fastcall(CGlobalObject *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180049370`

## callees

- `0x18005942c`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180059478`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180059478`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18005943c`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180059489`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18005943c`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180059489`
- `api-ms-win-core-processthreads-l1-1-0!TlsFree` at `0x18005944d`
- `api-ms-win-core-processthreads-l1-1-0!TlsFree` at `0x18005944d`

## pseudocode

```c
void __fastcall CGlobalObject::Uninitialize(CGlobalObject *this)
{
  CGlobalObject *fPending; // [rsp+30h] [rbp+8h] BYREF

  fPending = this;
  DeleteCriticalSection(&stru_1800B1318);
  if ( dwTlsIndex != -1 )
  {
    TlsFree(dwTlsIndex);
    dwTlsIndex = -1;
  }
  LODWORD(fPending) = 0;
  if ( InitOnceBeginInitialize(&InitOnce, 1u, (PBOOL)&fPending, 0) )
    DeleteCriticalSection(&CriticalSection);
}

```

## disassembly

```asm
0x18005942c  mov     [rsp+fPending], rcx
0x180059431  sub     rsp, 28h
0x180059435  lea     rcx, stru_1800B1318; lpCriticalSection
0x18005943c  call    cs:__imp_DeleteCriticalSection
0x180059442  mov     ecx, cs:dwTlsIndex; dwTlsIndex
0x180059448  cmp     ecx, 0FFFFFFFFh
0x18005944b  jz      short loc_18005945D
0x18005944d  call    cs:__imp_TlsFree
0x180059453  mov     cs:dwTlsIndex, 0FFFFFFFFh
0x18005945d  xor     r9d, r9d; lpContext
0x180059460  mov     dword ptr [rsp+28h+fPending], 0
0x180059468  lea     r8, [rsp+28h+fPending]; fPending
0x18005946d  lea     rcx, InitOnce; lpInitOnce
0x180059474  lea     edx, [r9+1]; dwFlags
0x180059478  call    cs:__imp_InitOnceBeginInitialize
0x18005947e  test    eax, eax
0x180059480  jz      short loc_18005948F
0x180059482  lea     rcx, CriticalSection; lpCriticalSection
0x180059489  call    cs:__imp_DeleteCriticalSection
0x18005948f  add     rsp, 28h
0x180059493  retn
```
