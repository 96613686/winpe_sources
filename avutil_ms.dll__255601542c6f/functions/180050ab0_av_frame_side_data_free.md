# av_frame_side_data_free

- ea: `0x180050ab0`
- end: `0x180050afd`
- name: `av_frame_side_data_free`
- size: `77`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x18003ba10`
- `0x18003bd20`
- `0x18003bfe0`

## callees

- `0x1800449d0`
- `0x180050ab0`
- `0x180050d58`

## pseudocode

```c
__int64 __fastcall av_frame_side_data_free(_QWORD *a1, _DWORD *a2)
{
  int i; // ebx

  for ( i = 0; i < *a2; ++i )
    sub_180050D58(*a1 + 8LL * i);
  *a2 = 0;
  return av_freep(a1);
}

```

## disassembly

```asm
0x180050ab0  mov     [rsp+arg_0], rbx
0x180050ab5  mov     [rsp+arg_8], rsi
0x180050aba  push    rdi
0x180050abb  sub     rsp, 20h
0x180050abf  xor     ebx, ebx
0x180050ac1  mov     rdi, rdx
0x180050ac4  mov     rsi, rcx
0x180050ac7  cmp     [rdx], ebx
0x180050ac9  jle     short loc_180050AE0
0x180050acb  mov     rax, [rsi]
0x180050ace  movsxd  r8, ebx
0x180050ad1  lea     rcx, [rax+r8*8]
0x180050ad5  call    sub_180050D58
0x180050ada  inc     ebx
0x180050adc  cmp     ebx, [rdi]
0x180050ade  jl      short loc_180050ACB
0x180050ae0  mov     rcx, rsi
0x180050ae3  mov     dword ptr [rdi], 0
0x180050ae9  mov     rbx, [rsp+28h+arg_0]
0x180050aee  mov     rsi, [rsp+28h+arg_8]
0x180050af3  add     rsp, 20h
0x180050af7  pop     rdi
0x180050af8  jmp     av_freep
```
