# __crt_stdio_output::formatting_buffer::ensure_buffer_is_big_enough<char>(unsigned __int64,__crt_cached_ptd_host &)

- ea: `0x14001001c`
- end: `0x1400100c4`
- name: `??$ensure_buffer_is_big_enough@D@formatting_buffer@__crt_stdio_output@@QEAA_N_KAEAV__crt_cached_ptd_host@@@Z`
- size: `168`
- prototype: `char __fastcall(__int64, unsigned __int64, __int64)`
- caller_count: `5`
- callee_count: `3`
- tags: ``

## callers

- `0x140010bd0`
- `0x140010fe0`
- `0x1400113f0`
- `0x140013808`
- `0x140013a64`

## callees

- `0x14001001c`
- `0x140019930`
- `0x140019990`

## pseudocode

```c
char __fastcall __crt_stdio_output::formatting_buffer::ensure_buffer_is_big_enough<char>(
        __int64 a1,
        unsigned __int64 a2,
        __int64 a3)
{
  char result; // al
  char v5; // di
  unsigned __int64 v6; // rsi
  void *v7; // rbx

  if ( a2 <= 0x7FFFFFFFFFFFFFFFLL )
  {
    v5 = 0;
    v6 = 2 * a2;
    if ( (*(_QWORD *)(a1 + 1032) || v6 > 0x400) && v6 > *(_QWORD *)(a1 + 1024) )
    {
      v7 = malloc_base(2 * a2);
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
0x14001001c  mov     [rsp+arg_0], rbx
0x140010021  mov     [rsp+arg_8], rbp
0x140010026  mov     [rsp+arg_10], rsi
0x14001002b  push    rdi
0x14001002c  sub     rsp, 20h
0x140010030  mov     rax, 7FFFFFFFFFFFFFFFh
0x14001003a  mov     rbp, rcx
0x14001003d  cmp     rdx, rax
0x140010040  jbe     short loc_140010053
0x140010042  mov     byte ptr [r8+30h], 1
0x140010047  xor     al, al
0x140010049  mov     dword ptr [r8+2Ch], 0Ch
0x140010051  jmp     short loc_1400100AF
0x140010053  xor     edi, edi
0x140010055  lea     rsi, [rdx+rdx]
0x140010059  cmp     [rcx+408h], rdi
0x140010060  jnz     short loc_14001006B
0x140010062  cmp     rsi, 400h
0x140010069  jbe     short loc_140010074
0x14001006b  cmp     rsi, [rcx+400h]
0x140010072  ja      short loc_140010078
0x140010074  mov     al, 1
0x140010076  jmp     short loc_1400100AF
0x140010078  mov     rcx, rsi; Size
0x14001007b  call    _malloc_base
0x140010080  mov     rbx, rax
0x140010083  test    rax, rax
0x140010086  jz      short loc_1400100A5
0x140010088  mov     rcx, [rbp+408h]; Block
0x14001008f  call    _free_base
0x140010094  mov     [rbp+408h], rbx
0x14001009b  mov     dil, 1
0x14001009e  mov     [rbp+400h], rsi
0x1400100a5  xor     ecx, ecx; Block
0x1400100a7  call    _free_base
0x1400100ac  mov     al, dil
0x1400100af  mov     rbx, [rsp+28h+arg_0]
0x1400100b4  mov     rbp, [rsp+28h+arg_8]
0x1400100b9  mov     rsi, [rsp+28h+arg_10]
0x1400100be  add     rsp, 20h
0x1400100c2  pop     rdi
0x1400100c3  retn
```
