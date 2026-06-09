# __crt_stdio_output::formatting_buffer::ensure_buffer_is_big_enough<wchar_t>(unsigned __int64,__crt_cached_ptd_host &)

- ea: `0x14000b378`
- end: `0x14000b424`
- name: `??$ensure_buffer_is_big_enough@_W@formatting_buffer@__crt_stdio_output@@QEAA_N_KAEAV__crt_cached_ptd_host@@@Z`
- size: `172`
- prototype: `char __fastcall(__int64, unsigned __int64, __int64)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x14000c094`
- `0x14000c4a4`
- `0x14000c8b4`

## callees

- `0x14000b378`
- `0x1400107c4`
- `0x140012040`

## pseudocode

```c
char __fastcall __crt_stdio_output::formatting_buffer::ensure_buffer_is_big_enough<wchar_t>(
        __int64 a1,
        unsigned __int64 a2,
        __int64 a3)
{
  char result; // al
  char v5; // di
  unsigned __int64 v6; // rsi
  void *v7; // rbx

  if ( a2 <= 0x3FFFFFFFFFFFFFFFLL )
  {
    v5 = 0;
    v6 = 4 * a2;
    if ( (*(_QWORD *)(a1 + 1032) || v6 > 0x400) && v6 > *(_QWORD *)(a1 + 1024) )
    {
      v7 = malloc_base(4 * a2);
      if ( v7 )
      {
        free_base(*(void **)(a1 + 1032));
        *(_QWORD *)(a1 + 1032) = v7;
        v5 = 1;
        *(_QWORD *)(a1 + 1024) = v6;
      }
      free_base(0);
      return v5;
    }
    else
    {
      return 1;
    }
  }
  else
  {
    *(_BYTE *)(a3 + 48) = 1;
    result = 0;
    *(_DWORD *)(a3 + 44) = 12;
  }
  return result;
}

```

## disassembly

```asm
0x14000b378  mov     [rsp+arg_0], rbx
0x14000b37d  mov     [rsp+arg_8], rbp
0x14000b382  mov     [rsp+arg_10], rsi
0x14000b387  push    rdi
0x14000b388  sub     rsp, 20h
0x14000b38c  mov     rax, 3FFFFFFFFFFFFFFFh
0x14000b396  mov     rbp, rcx
0x14000b399  cmp     rdx, rax
0x14000b39c  jbe     short loc_14000B3AF
0x14000b39e  mov     byte ptr [r8+30h], 1
0x14000b3a3  xor     al, al
0x14000b3a5  mov     dword ptr [r8+2Ch], 0Ch
0x14000b3ad  jmp     short loc_14000B40F
0x14000b3af  xor     edi, edi
0x14000b3b1  lea     rsi, ds:0[rdx*4]
0x14000b3b9  cmp     [rcx+408h], rdi
0x14000b3c0  jnz     short loc_14000B3CB
0x14000b3c2  cmp     rsi, 400h
0x14000b3c9  jbe     short loc_14000B3D4
0x14000b3cb  cmp     rsi, [rcx+400h]
0x14000b3d2  ja      short loc_14000B3D8
0x14000b3d4  mov     al, 1
0x14000b3d6  jmp     short loc_14000B40F
0x14000b3d8  mov     rcx, rsi; Size
0x14000b3db  call    _malloc_base
0x14000b3e0  mov     rbx, rax
0x14000b3e3  test    rax, rax
0x14000b3e6  jz      short loc_14000B405
0x14000b3e8  mov     rcx, [rbp+408h]; Block
0x14000b3ef  call    _free_base
0x14000b3f4  mov     [rbp+408h], rbx
0x14000b3fb  mov     dil, 1
0x14000b3fe  mov     [rbp+400h], rsi
0x14000b405  xor     ecx, ecx; Block
0x14000b407  call    _free_base
0x14000b40c  mov     al, dil
0x14000b40f  mov     rbx, [rsp+28h+arg_0]
0x14000b414  mov     rbp, [rsp+28h+arg_8]
0x14000b419  mov     rsi, [rsp+28h+arg_10]
0x14000b41e  add     rsp, 20h
0x14000b422  pop     rdi
0x14000b423  retn
```
