# CACMCmpStream::Create(__int64,__int64)

- ea: `0x1800155d0`
- end: `0x1800156dc`
- name: `?Create@CACMCmpStream@@UEAAJ_J0@Z`
- size: `268`
- prototype: `__int64 __fastcall(CACMCmpStream *__hidden this, __int64, __int64)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x1800155d0`
- `0x180017365`
- `0x180018010`

## import_xrefs

- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x180015675`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x180015675`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x18001566c`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x18001566c`
- `MSACM32!acmGetVersion` at `0x180015616`
- `MSACM32!acmGetVersion` at `0x180015616`

## pseudocode

```c
__int64 __fastcall CACMCmpStream::Create(CACMCmpStream *this, __int64 a2, __int64 a3)
{
  bool v6; // zf
  unsigned int v7; // ebx
  _WORD *v8; // rcx
  unsigned int v9; // edx
  unsigned __int64 v10; // r8
  HGLOBAL v11; // rax
  void *v12; // rax

  (*(void (__fastcall **)(__int64, char *, __int64))(*(_QWORD *)a2 + 32LL))(a2, (char *)this + 20, 204);
  v6 = *((_DWORD *)this + 5) == 1935963489;
  *((_DWORD *)this + 6) = 0;
  if ( v6 && acmGetVersion() >= 0x2000000 )
  {
    if ( !a3 || (v8 = *(_WORD **)(a3 + 24)) == 0 )
    {
      *((_DWORD *)this + 66) = 0;
      *((_QWORD *)this + 32) = 0;
      goto LABEL_16;
    }
    v9 = 16;
    if ( *v8 == 1 )
      v10 = 16;
    else
      v10 = (unsigned __int16)v8[8] + 18LL;
    if ( *(unsigned int *)(a3 + 32) >= v10 )
    {
      if ( *v8 != 1 )
        v9 = (unsigned __int16)v8[8] + 18;
      *((_DWORD *)this + 66) = v9;
      v11 = GlobalAlloc(2u, v9);
      v12 = GlobalLock(v11);
      *((_QWORD *)this + 32) = v12;
      if ( !v12 )
        return (unsigned int)-2147205017;
      memmove_0(v12, *(const void **)(a3 + 24), *((int *)this + 66));
LABEL_16:
      v7 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)a2 + 8LL))(a2);
      *((_QWORD *)this + 28) = a2;
      return v7;
    }
  }
  return (unsigned int)-2147205016;
}

```

## disassembly

```asm
0x1800155d0  push    rbx
0x1800155d2  push    rsi
0x1800155d3  push    rdi
0x1800155d4  push    r14
0x1800155d6  sub     rsp, 28h
0x1800155da  mov     rax, [rdx]
0x1800155dd  mov     r14, rdx
0x1800155e0  mov     rsi, r8
0x1800155e3  lea     rdx, [rcx+14h]
0x1800155e7  mov     rdi, rcx
0x1800155ea  mov     r8d, 0CCh
0x1800155f0  mov     rcx, r14
0x1800155f3  mov     rax, [rax+20h]
0x1800155f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800155fc  cmp     dword ptr [rdi+14h], 73647561h
0x180015603  mov     dword ptr [rdi+18h], 0
0x18001560a  jz      short loc_180015616
0x18001560c  mov     ebx, 80044068h
0x180015611  jmp     loc_1800156D0
0x180015616  call    cs:__imp_acmGetVersion
0x18001561c  cmp     eax, 2000000h
0x180015621  jb      short loc_18001560C
0x180015623  test    rsi, rsi
0x180015626  jz      short loc_1800156A3
0x180015628  mov     rcx, [rsi+18h]
0x18001562c  test    rcx, rcx
0x18001562f  jz      short loc_1800156A3
0x180015631  cmp     word ptr [rcx], 1
0x180015635  mov     edx, 10h
0x18001563a  jnz     short loc_180015641
0x18001563c  mov     r8d, edx
0x18001563f  jmp     short loc_18001564A
0x180015641  movzx   r8d, word ptr [rcx+10h]
0x180015646  add     r8, 12h
0x18001564a  mov     eax, [rsi+20h]
0x18001564d  cmp     rax, r8
0x180015650  jb      short loc_18001560C
0x180015652  cmp     word ptr [rcx], 1
0x180015656  jz      short loc_18001565F
0x180015658  movzx   edx, word ptr [rcx+10h]
0x18001565c  add     edx, 12h
0x18001565f  mov     [rdi+108h], edx
0x180015665  mov     ecx, 2; uFlags
0x18001566a  mov     edx, edx; dwBytes
0x18001566c  call    cs:__imp_GlobalAlloc
0x180015672  mov     rcx, rax; hMem
0x180015675  call    cs:__imp_GlobalLock
0x18001567b  mov     [rdi+100h], rax
0x180015682  test    rax, rax
0x180015685  jnz     short loc_18001568E
0x180015687  mov     ebx, 80044067h
0x18001568c  jmp     short loc_1800156D0
0x18001568e  movsxd  r8, dword ptr [rdi+108h]; Size
0x180015695  mov     rcx, rax; void *
0x180015698  mov     rdx, [rsi+18h]; Src
0x18001569c  call    memmove_0
0x1800156a1  jmp     short loc_1800156B8
0x1800156a3  mov     dword ptr [rdi+108h], 0
0x1800156ad  mov     qword ptr [rdi+100h], 0
0x1800156b8  mov     rcx, [r14]
0x1800156bb  xor     ebx, ebx
0x1800156bd  mov     rax, [rcx+8]
0x1800156c1  mov     rcx, r14
0x1800156c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800156c9  mov     [rdi+0E0h], r14
0x1800156d0  mov     eax, ebx
0x1800156d2  add     rsp, 28h
0x1800156d6  pop     r14
0x1800156d8  pop     rdi
0x1800156d9  pop     rsi
0x1800156da  pop     rbx
0x1800156db  retn
```
