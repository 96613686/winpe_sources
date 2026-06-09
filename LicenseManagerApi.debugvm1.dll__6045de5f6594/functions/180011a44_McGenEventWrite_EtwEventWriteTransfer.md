# McGenEventWrite_EtwEventWriteTransfer

- ea: `0x180011a44`
- end: `0x180011a91`
- name: `McGenEventWrite_EtwEventWriteTransfer`
- size: `77`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180011720`
- `0x180011a98`

## callees

- `0x180011a44`

## import_xrefs

- `ntdll!EtwEventWriteTransfer` at `0x180011a86`
- `ntdll!EtwEventWriteTransfer` at `0x180011a86`

## pseudocode

```c
__int64 __fastcall McGenEventWrite_EtwEventWriteTransfer(_QWORD *a1, __int64 a2, __int64 a3, int a4, __int64 a5)
{
  unsigned __int16 *v5; // r8
  int v6; // r10d

  v5 = (unsigned __int16 *)a1[1];
  if ( v5 )
  {
    *(_QWORD *)a5 = v5;
    v6 = 2;
    LODWORD(v5) = *v5;
  }
  else
  {
    *(_QWORD *)a5 = 0;
    v6 = 0;
  }
  *(_DWORD *)(a5 + 8) = (_DWORD)v5;
  *(_DWORD *)(a5 + 12) = v6;
  return EtwEventWriteTransfer(*a1, a2, 0, 0, a4, a5);
}

```

## disassembly

```asm
0x180011a44  sub     rsp, 38h
0x180011a48  mov     r8, [rcx+8]
0x180011a4c  mov     rax, [rsp+38h+arg_20]
0x180011a51  test    r8, r8
0x180011a54  jnz     short loc_180011A5E
0x180011a56  mov     [rax], r8
0x180011a59  xor     r10d, r10d
0x180011a5c  jmp     short loc_180011A6B
0x180011a5e  mov     [rax], r8
0x180011a61  mov     r10d, 2
0x180011a67  movzx   r8d, word ptr [r8]
0x180011a6b  mov     [rax+8], r8d
0x180011a6f  xor     r8d, r8d
0x180011a72  mov     [rsp+38h+var_10], rax
0x180011a77  mov     [rax+0Ch], r10d
0x180011a7b  mov     rcx, [rcx]
0x180011a7e  mov     [rsp+38h+var_18], r9d
0x180011a83  xor     r9d, r9d
0x180011a86  call    cs:__imp_EtwEventWriteTransfer
0x180011a8c  add     rsp, 38h
0x180011a90  retn
```
