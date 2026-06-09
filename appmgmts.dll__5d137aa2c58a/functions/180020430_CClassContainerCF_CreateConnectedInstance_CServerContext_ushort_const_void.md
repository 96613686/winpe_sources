# CClassContainerCF::CreateConnectedInstance(CServerContext *,ushort const *,void * *)

- ea: `0x180020430`
- end: `0x1800204df`
- name: `?CreateConnectedInstance@CClassContainerCF@@QEAAJPEAVCServerContext@@PEBGPEAPEAX@Z`
- size: `175`
- prototype: `__int64 __fastcall(CClassContainerCF *this, const unsigned __int16 **, const unsigned __int16 *, void **)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18001bde0`

## callees

- `0x18001e8ac`
- `0x180020430`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002045b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002045b`

## pseudocode

```c
__int64 __fastcall CClassContainerCF::CreateConnectedInstance(
        CClassContainerCF *this,
        const unsigned __int16 **a2,
        const unsigned __int16 *a3,
        void **a4)
{
  CClassContainer *v7; // rax
  CClassContainer *v8; // rax
  CClassContainer *v9; // rdi
  int v10; // ebx
  CClassContainer *v11; // rcx
  __int64 v12; // rax
  int v14; // [rsp+30h] [rbp+8h] BYREF
  int v15; // [rsp+34h] [rbp+Ch]

  v15 = HIDWORD(this);
  v14 = 0;
  v7 = (CClassContainer *)LocalAlloc(0, 0x260u);
  if ( v7 && (v8 = CClassContainer::CClassContainer(v7, a2, a3, (unsigned int *)&v14), (v9 = v8) != 0) )
  {
    v10 = v14;
    v11 = v8;
    v12 = *(_QWORD *)v8;
    if ( v14 < 0 )
    {
      (*(void (__fastcall **)(CClassContainer *))(v12 + 8))(v11);
    }
    else
    {
      v10 = (*(__int64 (__fastcall **)(CClassContainer *, GUID *, void **))v12)(v11, &IID_IClassAdmin, a4);
      if ( v10 < 0 )
        v10 = -2147418113;
    }
    (*(void (__fastcall **)(CClassContainer *))(*(_QWORD *)v9 + 16LL))(v9);
  }
  else
  {
    return (unsigned int)-2147024882;
  }
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x180020430  mov     rax, rsp
0x180020433  mov     [rax+10h], rbx
0x180020437  mov     [rax+18h], rsi
0x18002043b  mov     [rax+8], rcx
0x18002043f  push    rdi
0x180020440  sub     rsp, 20h
0x180020444  mov     rdi, rdx
0x180020447  mov     dword ptr [rax+8], 0
0x18002044e  mov     edx, 260h; uBytes
0x180020453  xor     ecx, ecx; uFlags
0x180020455  mov     rsi, r9
0x180020458  mov     rbx, r8
0x18002045b  call    cs:__imp_LocalAlloc
0x180020461  test    rax, rax
0x180020464  jz      short loc_1800204C8
0x180020466  lea     r9, [rsp+28h+arg_0]; int *
0x18002046b  mov     r8, rbx; unsigned __int16 *
0x18002046e  mov     rdx, rdi; struct CServerContext *
0x180020471  mov     rcx, rax; this
0x180020474  call    ??0CClassContainer@@QEAA@PEAVCServerContext@@PEBGPEAJ@Z; CClassContainer::CClassContainer(CServerContext *,ushort const *,long *)
0x180020479  mov     rdi, rax
0x18002047c  test    rax, rax
0x18002047f  jz      short loc_1800204C8
0x180020481  mov     ebx, [rsp+28h+arg_0]
0x180020485  mov     rcx, rdi
0x180020488  mov     rax, [rax]
0x18002048b  test    ebx, ebx
0x18002048d  js      short loc_1800204AE
0x18002048f  mov     rax, [rax]
0x180020492  lea     rdx, IID_IClassAdmin
0x180020499  mov     r8, rsi
0x18002049c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800204a1  mov     ebx, eax
0x1800204a3  test    eax, eax
0x1800204a5  jns     short loc_1800204B7
0x1800204a7  mov     ebx, 8000FFFFh
0x1800204ac  jmp     short loc_1800204B7
0x1800204ae  mov     rax, [rax+8]
0x1800204b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800204b7  mov     rax, [rdi]
0x1800204ba  mov     rcx, rdi
0x1800204bd  mov     rax, [rax+10h]
0x1800204c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800204c6  jmp     short loc_1800204CD
0x1800204c8  mov     ebx, 8007000Eh
0x1800204cd  mov     rsi, [rsp+28h+arg_10]
0x1800204d2  mov     eax, ebx
0x1800204d4  mov     rbx, [rsp+28h+arg_8]
0x1800204d9  add     rsp, 20h
0x1800204dd  pop     rdi
0x1800204de  retn
```
