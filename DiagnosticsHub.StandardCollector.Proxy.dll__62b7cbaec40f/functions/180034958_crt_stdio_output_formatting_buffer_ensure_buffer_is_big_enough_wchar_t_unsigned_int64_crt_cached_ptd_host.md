# __crt_stdio_output::formatting_buffer::ensure_buffer_is_big_enough<wchar_t>(unsigned __int64,__crt_cached_ptd_host &)

- ea: `0x180034958`
- end: `0x180034a04`
- name: `??$ensure_buffer_is_big_enough@_W@formatting_buffer@__crt_stdio_output@@QEAA_N_KAEAV__crt_cached_ptd_host@@@Z`
- size: `172`
- prototype: ``
- caller_count: `18`
- callee_count: `3`
- tags: ``

## callers

- `0x18003a2b4`
- `0x18003a4c0`
- `0x18003a6fc`
- `0x18003a908`
- `0x18003ab14`
- `0x18003ad50`
- `0x18003bbdc`
- `0x18003bde8`
- `0x18003c024`
- `0x18003c230`
- `0x18003c43c`
- `0x18003c678`
- `0x18003d504`
- `0x18003d710`
- `0x18003d94c`
- `0x18003db58`
- `0x18003dd64`
- `0x18003dfa0`

## callees

- `0x180008040`
- `0x1800126d0`
- `0x180034958`

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
0x180034958  mov     [rsp+arg_0], rbx
0x18003495d  mov     [rsp+arg_8], rbp
0x180034962  mov     [rsp+arg_10], rsi
0x180034967  push    rdi
0x180034968  sub     rsp, 20h
0x18003496c  mov     rax, 3FFFFFFFFFFFFFFFh
0x180034976  mov     rbp, rcx
0x180034979  cmp     rdx, rax
0x18003497c  jbe     short loc_18003498F
0x18003497e  mov     byte ptr [r8+30h], 1
0x180034983  xor     al, al
0x180034985  mov     dword ptr [r8+2Ch], 0Ch
0x18003498d  jmp     short loc_1800349EF
0x18003498f  xor     edi, edi
0x180034991  lea     rsi, ds:0[rdx*4]
0x180034999  cmp     [rcx+408h], rdi
0x1800349a0  jnz     short loc_1800349AB
0x1800349a2  cmp     rsi, 400h
0x1800349a9  jbe     short loc_1800349B4
0x1800349ab  cmp     rsi, [rcx+400h]
0x1800349b2  ja      short loc_1800349B8
0x1800349b4  mov     al, 1
0x1800349b6  jmp     short loc_1800349EF
0x1800349b8  mov     rcx, rsi; Size
0x1800349bb  call    _malloc_base
0x1800349c0  mov     rbx, rax
0x1800349c3  test    rax, rax
0x1800349c6  jz      short loc_1800349E5
0x1800349c8  mov     rcx, [rbp+408h]; Block
0x1800349cf  call    _free_base
0x1800349d4  mov     [rbp+408h], rbx
0x1800349db  mov     dil, 1
0x1800349de  mov     [rbp+400h], rsi
0x1800349e5  xor     ecx, ecx; Block
0x1800349e7  call    _free_base
0x1800349ec  mov     al, dil
0x1800349ef  mov     rbx, [rsp+28h+arg_0]
0x1800349f4  mov     rbp, [rsp+28h+arg_8]
0x1800349f9  mov     rsi, [rsp+28h+arg_10]
0x1800349fe  add     rsp, 20h
0x180034a02  pop     rdi
0x180034a03  retn
```
