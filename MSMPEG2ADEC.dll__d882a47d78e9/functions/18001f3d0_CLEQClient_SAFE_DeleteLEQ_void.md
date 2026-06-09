# CLEQClient::SAFE_DeleteLEQ(void)

- ea: `0x18001f3d0`
- end: `0x18001f42f`
- name: `?SAFE_DeleteLEQ@CLEQClient@@AEAAJXZ`
- size: `95`
- prototype: `__int64 __fastcall(CLEQClient *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18001f1a0`

## callees

- `0x18001f3d0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__aligned_free` at `0x18001f3ff`
- `api-ms-win-crt-private-l1-1-0!_o__aligned_free` at `0x18001f40e`
- `api-ms-win-crt-private-l1-1-0!_o__aligned_free` at `0x18001f3ff`
- `api-ms-win-crt-private-l1-1-0!_o__aligned_free` at `0x18001f40e`
- `mfperfhelper!__imp_ippsFFTFree_R_32f` at `0x18001f3ec`
- `mfperfhelper!__imp_ippsFFTFree_R_32f` at `0x18001f3ec`

## pseudocode

```c
__int64 __fastcall CLEQClient::SAFE_DeleteLEQ(void **this)
{
  void *v1; // rdi

  v1 = *this;
  if ( *this )
  {
    ippsFFTFree_R_32f(*((_QWORD *)v1 + 29));
    _aligned_free(*((void **)v1 + 30));
    _aligned_free(*this);
    *this = 0;
  }
  return 0;
}

```

## disassembly

```asm
0x18001f3d0  mov     [rsp+arg_0], rbx
0x18001f3d5  push    rdi
0x18001f3d6  sub     rsp, 20h
0x18001f3da  mov     rdi, [rcx]
0x18001f3dd  mov     rbx, rcx
0x18001f3e0  test    rdi, rdi
0x18001f3e3  jz      short loc_18001F421
0x18001f3e5  mov     rcx, [rdi+0E8h]
0x18001f3ec  call    cs:__imp_ippsFFTFree_R_32f
0x18001f3f3  nop     dword ptr [rax+rax+00h]
0x18001f3f8  mov     rcx, [rdi+0F0h]; Block
0x18001f3ff  call    cs:__imp__aligned_free
0x18001f406  nop     dword ptr [rax+rax+00h]
0x18001f40b  mov     rcx, [rbx]; Block
0x18001f40e  call    cs:__imp__aligned_free
0x18001f415  nop     dword ptr [rax+rax+00h]
0x18001f41a  mov     qword ptr [rbx], 0
0x18001f421  mov     rbx, [rsp+28h+arg_0]
0x18001f426  xor     eax, eax
0x18001f428  add     rsp, 20h
0x18001f42c  pop     rdi
0x18001f42d  retn
```
