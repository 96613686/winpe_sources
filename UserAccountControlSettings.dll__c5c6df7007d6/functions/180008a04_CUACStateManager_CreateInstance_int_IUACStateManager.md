# CUACStateManager_CreateInstance(int,IUACStateManager * *)

- ea: `0x180008a04`
- end: `0x180008a9d`
- name: `?CUACStateManager_CreateInstance@@YAJHPEAPEAUIUACStateManager@@@Z`
- size: `153`
- prototype: `__int64 __fastcall(int, struct IUACStateManager **)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18000751c`

## callees

- `0x180001a04`
- `0x180008a04`
- `0x18000c010`

## import_xrefs

- `KERNEL32!CheckElevationEnabled` at `0x180008a52`
- `KERNEL32!CheckElevationEnabled` at `0x180008a52`

## pseudocode

```c
__int64 __fastcall CUACStateManager_CreateInstance(int a1, struct IUACStateManager **a2)
{
  unsigned int v4; // edi
  _DWORD *v5; // rbx
  int v6; // eax
  int v7; // ecx

  *a2 = 0;
  v4 = -2147024882;
  v5 = operator new(0x18u);
  if ( v5 )
  {
    v5[2] = 1;
    *(_QWORD *)v5 = &CUACStateManager::`vftable';
    v5[5] = 0;
    *((_BYTE *)v5 + 12) = 0;
    v5[4] = a1;
    v6 = CheckElevationEnabled();
    v7 = -2147024896;
    if ( v6 <= 0 )
      v7 = v6;
    *((_BYTE *)v5 + 12) = v7 >= 0;
    v4 = (**(__int64 (__fastcall ***)(void *, GUID *, struct IUACStateManager **))v5)(
           v5,
           &GUID_a462ea40_8db6_41ed_afb8_6b565d70e2dc,
           a2);
    (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v5 + 16LL))(v5);
  }
  return v4;
}

```

## disassembly

```asm
0x180008a04  push    rbx
0x180008a06  push    rbp
0x180008a07  push    rsi
0x180008a08  push    rdi
0x180008a09  sub     rsp, 28h
0x180008a0d  mov     ebp, ecx
0x180008a0f  mov     qword ptr [rdx], 0
0x180008a16  mov     ecx, 18h; Size
0x180008a1b  mov     rsi, rdx
0x180008a1e  mov     edi, 8007000Eh
0x180008a23  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180008a28  mov     rbx, rax
0x180008a2b  test    rax, rax
0x180008a2e  jz      short loc_180008A92
0x180008a30  lea     rax, ??_7CUACStateManager@@6B@; const CUACStateManager::`vftable'
0x180008a37  mov     dword ptr [rbx+8], 1
0x180008a3e  lea     rcx, [rbx+14h]
0x180008a42  mov     [rbx], rax
0x180008a45  mov     dword ptr [rcx], 0
0x180008a4b  mov     byte ptr [rbx+0Ch], 0
0x180008a4f  mov     [rbx+10h], ebp
0x180008a52  call    cs:__imp_CheckElevationEnabled
0x180008a58  lea     ecx, [rdi-0Eh]
0x180008a5b  mov     r8, rsi
0x180008a5e  test    eax, eax
0x180008a60  lea     rdx, _GUID_a462ea40_8db6_41ed_afb8_6b565d70e2dc
0x180008a67  cmovle  ecx, eax
0x180008a6a  shr     ecx, 1Fh
0x180008a6d  xor     cl, 1
0x180008a70  mov     [rbx+0Ch], cl
0x180008a73  mov     rcx, rbx
0x180008a76  mov     rax, [rbx]
0x180008a79  mov     rax, [rax]
0x180008a7c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008a81  mov     rcx, [rbx]
0x180008a84  mov     edi, eax
0x180008a86  mov     rax, [rcx+10h]
0x180008a8a  mov     rcx, rbx
0x180008a8d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008a92  mov     eax, edi
0x180008a94  add     rsp, 28h
0x180008a98  pop     rdi
0x180008a99  pop     rsi
0x180008a9a  pop     rbp
0x180008a9b  pop     rbx
0x180008a9c  retn
```
