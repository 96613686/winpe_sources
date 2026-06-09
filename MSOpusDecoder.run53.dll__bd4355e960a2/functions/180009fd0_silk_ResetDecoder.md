# silk_ResetDecoder

- ea: `0x180009fd0`
- end: `0x18000a018`
- name: `silk_ResetDecoder`
- size: `72`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x1800022f0`
- `0x180003620`
- `0x180003840`

## callees

- `0x180009fd0`
- `0x1800139b0`

## pseudocode

```c
__int64 __fastcall silk_ResetDecoder(__int64 a1)
{
  __int64 i; // rbx
  __int64 result; // rax

  for ( i = 0; i != 2; ++i )
    result = silk_init_decoder(a1 + 4296 * i);
  *(_QWORD *)(a1 + 8592) = 0;
  *(_DWORD *)(a1 + 8600) = 0;
  *(_DWORD *)(a1 + 8612) = 0;
  return result;
}

```

## disassembly

```asm
0x180009fd0  mov     [rsp+arg_0], rbx
0x180009fd5  push    rdi
0x180009fd6  sub     rsp, 20h
0x180009fda  mov     rdi, rcx
0x180009fdd  xor     ebx, ebx
0x180009fdf  nop
0x180009fe0  imul    rcx, rbx, 10C8h
0x180009fe7  add     rcx, rdi
0x180009fea  call    silk_init_decoder
0x180009fef  inc     rbx
0x180009ff2  cmp     rbx, 2
0x180009ff6  jnz     short loc_180009FE0
0x180009ff8  mov     rbx, [rsp+28h+arg_0]
0x180009ffd  xor     ecx, ecx
0x180009fff  mov     [rdi+2190h], rcx
0x18000a006  mov     [rdi+2198h], ecx
0x18000a00c  mov     [rdi+21A4h], ecx
0x18000a012  add     rsp, 20h
0x18000a016  pop     rdi
0x18000a017  retn
```
