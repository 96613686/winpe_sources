# CAVIFile::Create(IUnknown *,_GUID const &,void * *)

- ea: `0x180008db8`
- end: `0x180008f12`
- name: `?Create@CAVIFile@@SAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `346`
- prototype: `__int64 __fastcall(struct IUnknown *, const struct _GUID *, void **)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x180008a80`

## callees

- `0x180001008`
- `0x180001048`
- `0x180001d0c`
- `0x180008db8`
- `0x180018010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180008ec2`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180008ec2`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180008ee5`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180008ee5`

## pseudocode

```c
__int64 __fastcall CAVIFile::Create(struct IUnknown *a1, const struct _GUID *a2, void **a3)
{
  char *v6; // rax
  char *v7; // rbx
  struct IUnknown *v8; // rax
  int v9; // edi

  v6 = (char *)operator new(0x518u);
  v7 = v6;
  if ( !v6 )
    return 2147942414LL;
  *((_QWORD *)v6 + 1) = v6;
  *(_QWORD *)v6 = &CAVIFile::CUnknownImpl::`vftable';
  *((_DWORD *)v6 + 4) = 0;
  *((_QWORD *)v6 + 5) = &CAVIFile::CPersistStorageImpl::`vftable';
  *((_QWORD *)v6 + 3) = &CAVIFile::CF::`vftable';
  *((_QWORD *)v6 + 7) = &CAVIFile::CPersistFileImpl::`vftable';
  *((_QWORD *)v6 + 4) = v6;
  *((_WORD *)v6 + 70) = 0;
  *((_DWORD *)v6 + 169) = 0;
  *((_DWORD *)v6 + 176) = 0;
  *((_DWORD *)v6 + 182) = 0;
  *((_QWORD *)v6 + 89) = 0;
  *((_DWORD *)v6 + 180) = 0;
  *((_QWORD *)v6 + 6) = v6;
  *((_QWORD *)v6 + 8) = v6;
  *((_QWORD *)v6 + 83) = 0;
  *((_OWORD *)v6 + 5) = 0;
  *((_OWORD *)v6 + 6) = 0;
  *((_OWORD *)v6 + 7) = 0;
  *((_QWORD *)v6 + 16) = 0;
  memset_0(v6 + 736, 0, 0x200u);
  *((_DWORD *)v7 + 26) = 0;
  *((_DWORD *)v7 + 34) = 0;
  *((_QWORD *)v7 + 156) = 0;
  v8 = (struct IUnknown *)v7;
  if ( a1 )
    v8 = a1;
  *((_QWORD *)v7 + 157) = 0;
  *((_QWORD *)v7 + 9) = v8;
  InitializeCriticalSection((LPCRITICAL_SECTION)(v7 + 1264));
  v9 = (**(__int64 (__fastcall ***)(void *, const struct _GUID *, void **))v7)(v7, a2, a3);
  if ( v9 < 0 )
  {
    DeleteCriticalSection((LPCRITICAL_SECTION)(v7 + 1264));
    *((_QWORD *)v7 + 3) = &CAVIFile::CF::`vftable';
    operator delete(v7, 0x518u);
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180008db8  push    rbx
0x180008dba  push    rbp
0x180008dbb  push    rsi
0x180008dbc  push    rdi
0x180008dbd  push    r13
0x180008dbf  push    r14
0x180008dc1  sub     rsp, 28h
0x180008dc5  mov     rdi, rcx
0x180008dc8  mov     rbp, r8
0x180008dcb  mov     ecx, 518h; Size
0x180008dd0  mov     r14, rdx
0x180008dd3  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180008dd8  mov     rbx, rax
0x180008ddb  test    rax, rax
0x180008dde  jz      loc_180008F00
0x180008de4  mov     [rbx+8], rbx
0x180008de8  lea     rax, ??_7CUnknownImpl@CAVIFile@@6B@; const CAVIFile::CUnknownImpl::`vftable'
0x180008def  mov     [rbx], rax
0x180008df2  lea     r13, ??_7CF@CAVIFile@@6B@; const CAVIFile::CF::`vftable'
0x180008df9  mov     dword ptr [rbx+10h], 0
0x180008e00  lea     rax, ??_7CPersistStorageImpl@CAVIFile@@6B@; const CAVIFile::CPersistStorageImpl::`vftable'
0x180008e07  mov     [rbx+28h], rax
0x180008e0b  lea     rcx, [rbx+2E0h]; void *
0x180008e12  lea     rax, ??_7CPersistFileImpl@CAVIFile@@6B@; const CAVIFile::CPersistFileImpl::`vftable'
0x180008e19  mov     [rbx+18h], r13
0x180008e1d  mov     [rbx+38h], rax
0x180008e21  xorps   xmm0, xmm0
0x180008e24  xor     eax, eax
0x180008e26  mov     [rbx+20h], rbx
0x180008e2a  mov     [rbx+8Ch], ax
0x180008e31  xor     edx, edx; Val
0x180008e33  mov     [rbx+2A4h], eax
0x180008e39  mov     r8d, 200h; Size
0x180008e3f  mov     [rbx+2C0h], eax
0x180008e45  mov     [rbx+2D8h], eax
0x180008e4b  mov     [rbx+2C8h], rax
0x180008e52  mov     [rbx+2D0h], eax
0x180008e58  mov     [rbx+30h], rbx
0x180008e5c  mov     [rbx+40h], rbx
0x180008e60  mov     qword ptr [rbx+298h], 0
0x180008e6b  movups  xmmword ptr [rbx+50h], xmm0
0x180008e6f  movups  xmmword ptr [rbx+60h], xmm0
0x180008e73  movups  xmmword ptr [rbx+70h], xmm0
0x180008e77  mov     [rbx+80h], rax
0x180008e7e  call    memset_0
0x180008e83  mov     dword ptr [rbx+68h], 0
0x180008e8a  lea     rsi, [rbx+4F0h]
0x180008e91  mov     dword ptr [rbx+88h], 0
0x180008e9b  test    rdi, rdi
0x180008e9e  mov     qword ptr [rbx+4E0h], 0
0x180008ea9  mov     rax, rbx
0x180008eac  cmovnz  rax, rdi
0x180008eb0  mov     qword ptr [rbx+4E8h], 0
0x180008ebb  mov     rcx, rsi; lpCriticalSection
0x180008ebe  mov     [rbx+48h], rax
0x180008ec2  call    cs:__imp_InitializeCriticalSection
0x180008ec8  mov     rax, [rbx]
0x180008ecb  mov     r8, rbp
0x180008ece  mov     rdx, r14
0x180008ed1  mov     rcx, rbx
0x180008ed4  mov     rax, [rax]
0x180008ed7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008edc  mov     edi, eax
0x180008ede  test    eax, eax
0x180008ee0  jns     short loc_180008EFC
0x180008ee2  mov     rcx, rsi; lpCriticalSection
0x180008ee5  call    cs:__imp_DeleteCriticalSection
0x180008eeb  mov     edx, 518h; unsigned __int64
0x180008ef0  mov     [rbx+18h], r13
0x180008ef4  mov     rcx, rbx; void *
0x180008ef7  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180008efc  mov     eax, edi
0x180008efe  jmp     short loc_180008F05
0x180008f00  mov     eax, 8007000Eh
0x180008f05  add     rsp, 28h
0x180008f09  pop     r14
0x180008f0b  pop     r13
0x180008f0d  pop     rdi
0x180008f0e  pop     rsi
0x180008f0f  pop     rbp
0x180008f10  pop     rbx
0x180008f11  retn
```
