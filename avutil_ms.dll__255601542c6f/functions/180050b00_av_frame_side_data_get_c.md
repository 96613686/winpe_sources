# av_frame_side_data_get_c

- ea: `0x180050b00`
- end: `0x180050b21`
- name: `av_frame_side_data_get_c`
- size: `33`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x18003b460`

## callees

- `0x180050b00`

## pseudocode

```c
__int64 __fastcall av_frame_side_data_get_c(__int64 a1, int a2, int a3)
{
  __int64 v3; // rax

  v3 = 0;
  if ( a2 <= 0 )
    return 0;
  while ( **(_DWORD **)(a1 + 8 * v3) != a3 )
  {
    if ( ++v3 >= a2 )
      return 0;
  }
  return *(_QWORD *)(a1 + 8 * v3);
}

```

## disassembly

```asm
0x180050b00  xor     eax, eax
0x180050b02  movsxd  r9, edx
0x180050b05  test    edx, edx
0x180050b07  jle     short loc_180050B1A
0x180050b09  mov     rdx, [rcx+rax*8]
0x180050b0d  cmp     [rdx], r8d
0x180050b10  jz      short loc_180050B1D
0x180050b12  inc     rax
0x180050b15  cmp     rax, r9
0x180050b18  jl      short loc_180050B09
0x180050b1a  xor     eax, eax
0x180050b1c  retn
0x180050b1d  mov     rax, rdx
0x180050b20  retn
```
