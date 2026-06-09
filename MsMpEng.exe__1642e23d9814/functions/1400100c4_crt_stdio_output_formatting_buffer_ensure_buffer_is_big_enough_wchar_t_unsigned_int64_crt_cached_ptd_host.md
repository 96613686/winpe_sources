# __crt_stdio_output::formatting_buffer::ensure_buffer_is_big_enough<wchar_t>(unsigned __int64,__crt_cached_ptd_host &)

- ea: `0x1400100c4`
- end: `0x140010170`
- name: `??$ensure_buffer_is_big_enough@_W@formatting_buffer@__crt_stdio_output@@QEAA_N_KAEAV__crt_cached_ptd_host@@@Z`
- size: `172`
- prototype: `char __fastcall(__int64, unsigned __int64, __int64)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x140010dd4`
- `0x1400111e4`
- `0x1400115f4`

## callees

- `0x1400100c4`
- `0x140019930`
- `0x140019990`

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
0x1400100c4  mov     [rsp+arg_0], rbx
0x1400100c9  mov     [rsp+arg_8], rbp
0x1400100ce  mov     [rsp+arg_10], rsi
0x1400100d3  push    rdi
0x1400100d4  sub     rsp, 20h
0x1400100d8  mov     rax, 3FFFFFFFFFFFFFFFh
0x1400100e2  mov     rbp, rcx
0x1400100e5  cmp     rdx, rax
0x1400100e8  jbe     short loc_1400100FB
0x1400100ea  mov     byte ptr [r8+30h], 1
0x1400100ef  xor     al, al
0x1400100f1  mov     dword ptr [r8+2Ch], 0Ch
0x1400100f9  jmp     short loc_14001015B
0x1400100fb  xor     edi, edi
0x1400100fd  lea     rsi, ds:0[rdx*4]
0x140010105  cmp     [rcx+408h], rdi
0x14001010c  jnz     short loc_140010117
0x14001010e  cmp     rsi, 400h
0x140010115  jbe     short loc_140010120
0x140010117  cmp     rsi, [rcx+400h]
0x14001011e  ja      short loc_140010124
0x140010120  mov     al, 1
0x140010122  jmp     short loc_14001015B
0x140010124  mov     rcx, rsi; Size
0x140010127  call    _malloc_base
0x14001012c  mov     rbx, rax
0x14001012f  test    rax, rax
0x140010132  jz      short loc_140010151
0x140010134  mov     rcx, [rbp+408h]; Block
0x14001013b  call    _free_base
0x140010140  mov     [rbp+408h], rbx
0x140010147  mov     dil, 1
0x14001014a  mov     [rbp+400h], rsi
0x140010151  xor     ecx, ecx; Block
0x140010153  call    _free_base
0x140010158  mov     al, dil
0x14001015b  mov     rbx, [rsp+28h+arg_0]
0x140010160  mov     rbp, [rsp+28h+arg_8]
0x140010165  mov     rsi, [rsp+28h+arg_10]
0x14001016a  add     rsp, 20h
0x14001016e  pop     rdi
0x14001016f  retn
```
