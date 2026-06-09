# CEditStream::Release(void)

- ea: `0x180012dc8`
- end: `0x180012e82`
- name: `?Release@CEditStream@@UEAAKXZ`
- size: `186`
- prototype: `unsigned int __fastcall(CEditStream *__hidden this)`
- caller_count: `3`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x180012d70`
- `0x180012d90`
- `0x180012db0`

## callees

- `0x180001048`
- `0x180012dc8`
- `0x180018010`

## import_xrefs

- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x180012e2b`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x180012e2b`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x180012e22`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x180012e34`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x180012e22`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x180012e34`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180012e3d`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180012e3d`

## pseudocode

```c
__int64 __fastcall CEditStream::Release(CEditStream *this)
{
  bool v1; // zf
  __int64 result; // rax
  int v4; // esi
  LPCVOID *i; // rdi
  __int64 v6; // rcx
  HGLOBAL v7; // rax
  HGLOBAL v8; // rax
  __int64 v9; // rcx

  v1 = (*((_DWORD *)this - 66))-- == 1;
  result = *((unsigned int *)this - 66);
  if ( v1 )
  {
    v4 = 0;
    for ( i = (LPCVOID *)((char *)this - 40); v4 < *((_DWORD *)this - 14); ++v4 )
    {
      v6 = *((_QWORD *)*i + 7 * v4);
      if ( v6 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
    }
    v7 = GlobalHandle(*((LPCVOID *)this - 5));
    GlobalUnlock(v7);
    v8 = GlobalHandle(*i);
    GlobalFree(v8);
    v9 = *((_QWORD *)this - 4);
    *i = 0;
    if ( v9 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
    operator delete((char *)this - 272);
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x180012dc8  mov     [rsp+arg_0], rbx
0x180012dcd  mov     [rsp+arg_8], rsi
0x180012dd2  push    rdi
0x180012dd3  sub     rsp, 20h
0x180012dd7  add     dword ptr [rcx-108h], 0FFFFFFFFh
0x180012dde  mov     rbx, rcx
0x180012de1  mov     eax, [rcx-108h]
0x180012de7  jnz     loc_180012E72
0x180012ded  xor     esi, esi
0x180012def  lea     rdi, [rcx-28h]
0x180012df3  cmp     [rcx-38h], esi
0x180012df6  jle     short loc_180012E1E
0x180012df8  movsxd  rax, esi
0x180012dfb  imul    rcx, rax, 38h ; '8'
0x180012dff  mov     rax, [rdi]
0x180012e02  mov     rcx, [rcx+rax]
0x180012e06  test    rcx, rcx
0x180012e09  jz      short loc_180012E17
0x180012e0b  mov     rax, [rcx]
0x180012e0e  mov     rax, [rax+10h]
0x180012e12  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012e17  inc     esi
0x180012e19  cmp     esi, [rbx-38h]
0x180012e1c  jl      short loc_180012DF8
0x180012e1e  mov     rcx, [rbx-28h]; pMem
0x180012e22  call    cs:__imp_GlobalHandle
0x180012e28  mov     rcx, rax; hMem
0x180012e2b  call    cs:__imp_GlobalUnlock
0x180012e31  mov     rcx, [rdi]; pMem
0x180012e34  call    cs:__imp_GlobalHandle
0x180012e3a  mov     rcx, rax; hMem
0x180012e3d  call    cs:__imp_GlobalFree
0x180012e43  mov     rcx, [rbx-20h]
0x180012e47  mov     qword ptr [rdi], 0
0x180012e4e  test    rcx, rcx
0x180012e51  jz      short loc_180012E5F
0x180012e53  mov     rax, [rcx]
0x180012e56  mov     rax, [rax+10h]
0x180012e5a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012e5f  mov     edx, 138h; unsigned __int64
0x180012e64  lea     rcx, [rbx-110h]; void *
0x180012e6b  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180012e70  xor     eax, eax
0x180012e72  mov     rbx, [rsp+28h+arg_0]
0x180012e77  mov     rsi, [rsp+28h+arg_8]
0x180012e7c  add     rsp, 20h
0x180012e80  pop     rdi
0x180012e81  retn
```
