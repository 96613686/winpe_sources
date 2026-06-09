# CRsopAppContext::MoveAppContextState(CRsopAppContext *)

- ea: `0x1800119c4`
- end: `0x180011ab8`
- name: `?MoveAppContextState@CRsopAppContext@@QEAAJPEAV1@@Z`
- size: `244`
- prototype: `__int64 __fastcall(CRsopAppContext *__hidden this, struct CRsopAppContext *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18000df00`

## callees

- `0x180002b14`
- `0x1800119c4`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800119df`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180011a37`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800119df`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180011a37`

## pseudocode

```c
__int64 __fastcall CRsopAppContext::MoveAppContextState(CRsopAppContext *this, struct CRsopAppContext *a2)
{
  unsigned __int16 *v4; // rax
  unsigned int v5; // edx
  __int64 v6; // rcx
  __int64 v7; // rax
  __int64 result; // rax

  if ( !*((_QWORD *)a2 + 11)
    || (LocalFree(*((HLOCAL *)this + 11)),
        v4 = StringDuplicate(*((const unsigned __int16 **)a2 + 11)),
        (*((_QWORD *)this + 11) = v4) != 0) )
  {
    v6 = *((_QWORD *)a2 + 1);
    *((_QWORD *)this + 1) = v6;
    if ( v6 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 8LL))(v6);
    *((_DWORD *)this + 8) = *((_DWORD *)a2 + 8);
    *((_DWORD *)this + 9) = *((_DWORD *)a2 + 9);
    *((_QWORD *)this + 5) = *((_QWORD *)a2 + 5);
    *((_QWORD *)a2 + 5) = 0;
    LocalFree(*((HLOCAL *)this + 2));
    v5 = 0;
    *((_QWORD *)this + 2) = *((_QWORD *)a2 + 2);
    v7 = *(_QWORD *)a2;
    *((_QWORD *)a2 + 2) = 0;
    *(_QWORD *)this = v7;
    *((_QWORD *)this + 3) = *((_QWORD *)a2 + 3);
    *((_QWORD *)this + 9) = *((_QWORD *)a2 + 9);
    *((_QWORD *)a2 + 9) = 0;
  }
  else
  {
    v5 = -2147024882;
  }
  *((_DWORD *)this + 20) = *((_DWORD *)a2 + 20);
  *((_DWORD *)this + 21) = *((_DWORD *)a2 + 21);
  result = v5;
  *((_DWORD *)this + 24) = *((_DWORD *)a2 + 24);
  *((_DWORD *)this + 25) = *((_DWORD *)a2 + 25);
  *((_DWORD *)this + 26) = *((_DWORD *)a2 + 26);
  *((_DWORD *)this + 27) = *((_DWORD *)a2 + 27);
  *((_DWORD *)this + 28) = *((_DWORD *)a2 + 28);
  *((_QWORD *)this + 15) = *((_QWORD *)a2 + 15);
  *((_DWORD *)this + 32) = *((_DWORD *)a2 + 32);
  return result;
}

```

## disassembly

```asm
0x1800119c4  mov     [rsp+arg_0], rbx
0x1800119c9  push    rdi
0x1800119ca  sub     rsp, 20h
0x1800119ce  cmp     qword ptr [rdx+58h], 0
0x1800119d3  mov     rbx, rdx
0x1800119d6  mov     rdi, rcx
0x1800119d9  jz      short loc_1800119FE
0x1800119db  mov     rcx, [rcx+58h]; hMem
0x1800119df  call    cs:__imp_LocalFree
0x1800119e5  mov     rcx, [rbx+58h]; unsigned __int16 *
0x1800119e9  call    ?StringDuplicate@@YAPEAGPEBG@Z; StringDuplicate(ushort const *)
0x1800119ee  mov     [rdi+58h], rax
0x1800119f2  test    rax, rax
0x1800119f5  jnz     short loc_1800119FE
0x1800119f7  mov     edx, 8007000Eh
0x1800119fc  jmp     short loc_180011A6D
0x1800119fe  mov     rcx, [rbx+8]
0x180011a02  mov     [rdi+8], rcx
0x180011a06  test    rcx, rcx
0x180011a09  jz      short loc_180011A17
0x180011a0b  mov     rax, [rcx]
0x180011a0e  mov     rax, [rax+8]
0x180011a12  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011a17  mov     eax, [rbx+20h]
0x180011a1a  mov     [rdi+20h], eax
0x180011a1d  mov     eax, [rbx+24h]
0x180011a20  mov     [rdi+24h], eax
0x180011a23  mov     rax, [rbx+28h]
0x180011a27  mov     [rdi+28h], rax
0x180011a2b  mov     qword ptr [rbx+28h], 0
0x180011a33  mov     rcx, [rdi+10h]; hMem
0x180011a37  call    cs:__imp_LocalFree
0x180011a3d  mov     rax, [rbx+10h]
0x180011a41  xor     edx, edx
0x180011a43  mov     [rdi+10h], rax
0x180011a47  mov     rax, [rbx]
0x180011a4a  mov     qword ptr [rbx+10h], 0
0x180011a52  mov     [rdi], rax
0x180011a55  mov     rax, [rbx+18h]
0x180011a59  mov     [rdi+18h], rax
0x180011a5d  mov     rax, [rbx+48h]
0x180011a61  mov     [rdi+48h], rax
0x180011a65  mov     qword ptr [rbx+48h], 0
0x180011a6d  mov     eax, [rbx+50h]
0x180011a70  mov     [rdi+50h], eax
0x180011a73  mov     eax, [rbx+54h]
0x180011a76  mov     [rdi+54h], eax
0x180011a79  mov     eax, edx
0x180011a7b  mov     ecx, [rbx+60h]
0x180011a7e  mov     [rdi+60h], ecx
0x180011a81  mov     ecx, [rbx+64h]
0x180011a84  mov     [rdi+64h], ecx
0x180011a87  mov     ecx, [rbx+68h]
0x180011a8a  mov     [rdi+68h], ecx
0x180011a8d  mov     ecx, [rbx+6Ch]
0x180011a90  mov     [rdi+6Ch], ecx
0x180011a93  mov     ecx, [rbx+70h]
0x180011a96  mov     [rdi+70h], ecx
0x180011a99  mov     rcx, [rbx+78h]
0x180011a9d  mov     [rdi+78h], rcx
0x180011aa1  mov     ecx, [rbx+80h]
0x180011aa7  mov     rbx, [rsp+28h+arg_0]
0x180011aac  mov     [rdi+80h], ecx
0x180011ab2  add     rsp, 20h
0x180011ab6  pop     rdi
0x180011ab7  retn
```
