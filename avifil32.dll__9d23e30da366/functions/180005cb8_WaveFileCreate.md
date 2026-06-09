# WaveFileCreate

- ea: `0x180005cb8`
- end: `0x180005db2`
- name: `WaveFileCreate`
- size: `250`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180008a80`

## callees

- `0x180005cb8`
- `0x180018010`

## import_xrefs

- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x180005d8f`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x180005d8f`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x180005cdd`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x180005cdd`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x180005d86`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x180005d98`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x180005d86`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x180005d98`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x180005cd4`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x180005cd4`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180005da1`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180005da1`

## pseudocode

```c
__int64 __fastcall WaveFileCreate(_QWORD *a1, __int64 a2, __int64 a3)
{
  HGLOBAL v6; // rax
  _QWORD *v7; // rax
  _QWORD *v8; // rbx
  _QWORD *v10; // rcx
  _QWORD *v11; // rax
  int v12; // edi
  HGLOBAL v13; // rax
  HGLOBAL v14; // rax

  v6 = GlobalAlloc(2u, 0x1F0u);
  v7 = GlobalLock(v6);
  v8 = v7;
  if ( !v7 )
    return 2147942414LL;
  v10 = v7 + 2;
  v7[1] = FileVtbl;
  *v7 = &StreamVtbl;
  v7[2] = UnknownVtbl;
  v7[3] = PersistVtbl;
  v11 = v7 + 2;
  if ( a1 )
    v11 = a1;
  v8[4] = v11;
  *((_DWORD *)v8 + 17) = 0;
  v8[5] = 0;
  v8[35] = 0;
  v8[36] = 0;
  v8[38] = 0;
  *((_DWORD *)v8 + 78) = 0;
  v12 = ((__int64 (__fastcall *)(_QWORD *, __int64, __int64))UnknownVtbl[0])(v10, a2, a3);
  if ( v12 < 0 )
  {
    v13 = GlobalHandle(v8);
    GlobalUnlock(v13);
    v14 = GlobalHandle(v8);
    GlobalFree(v14);
  }
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x180005cb8  push    rbx
0x180005cba  push    rbp
0x180005cbb  push    rsi
0x180005cbc  push    rdi
0x180005cbd  sub     rsp, 28h
0x180005cc1  mov     rbp, rdx
0x180005cc4  mov     rdi, rcx
0x180005cc7  mov     edx, 1F0h; dwBytes
0x180005ccc  mov     ecx, 2; uFlags
0x180005cd1  mov     rsi, r8
0x180005cd4  call    cs:__imp_GlobalAlloc
0x180005cda  mov     rcx, rax; hMem
0x180005cdd  call    cs:__imp_GlobalLock
0x180005ce3  mov     rbx, rax
0x180005ce6  test    rax, rax
0x180005ce9  jnz     short loc_180005CF5
0x180005ceb  mov     eax, 8007000Eh
0x180005cf0  jmp     loc_180005DA9
0x180005cf5  lea     rcx, [rbx+10h]
0x180005cf9  test    rdi, rdi
0x180005cfc  lea     rax, FileVtbl
0x180005d03  mov     r8, rsi
0x180005d06  mov     [rbx+8], rax
0x180005d0a  mov     rdx, rbp
0x180005d0d  lea     rax, StreamVtbl
0x180005d14  mov     [rbx], rax
0x180005d17  lea     rax, UnknownVtbl
0x180005d1e  mov     [rcx], rax
0x180005d21  lea     rax, PersistVtbl
0x180005d28  mov     [rbx+18h], rax
0x180005d2c  mov     rax, rcx
0x180005d2f  cmovnz  rax, rdi
0x180005d33  mov     [rbx+20h], rax
0x180005d37  mov     dword ptr [rbx+44h], 0
0x180005d3e  mov     qword ptr [rbx+28h], 0
0x180005d46  mov     qword ptr [rbx+118h], 0
0x180005d51  mov     qword ptr [rbx+120h], 0
0x180005d5c  mov     qword ptr [rbx+130h], 0
0x180005d67  mov     dword ptr [rbx+138h], 0
0x180005d71  mov     rax, cs:UnknownVtbl
0x180005d78  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005d7d  mov     edi, eax
0x180005d7f  test    eax, eax
0x180005d81  jns     short loc_180005DA7
0x180005d83  mov     rcx, rbx; pMem
0x180005d86  call    cs:__imp_GlobalHandle
0x180005d8c  mov     rcx, rax; hMem
0x180005d8f  call    cs:__imp_GlobalUnlock
0x180005d95  mov     rcx, rbx; pMem
0x180005d98  call    cs:__imp_GlobalHandle
0x180005d9e  mov     rcx, rax; hMem
0x180005da1  call    cs:__imp_GlobalFree
0x180005da7  mov     eax, edi
0x180005da9  add     rsp, 28h
0x180005dad  pop     rdi
0x180005dae  pop     rsi
0x180005daf  pop     rbp
0x180005db0  pop     rbx
0x180005db1  retn
```
