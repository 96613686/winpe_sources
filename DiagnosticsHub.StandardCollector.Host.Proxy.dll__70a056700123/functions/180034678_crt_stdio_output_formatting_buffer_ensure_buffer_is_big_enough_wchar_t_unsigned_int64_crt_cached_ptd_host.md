# __crt_stdio_output::formatting_buffer::ensure_buffer_is_big_enough<wchar_t>(unsigned __int64,__crt_cached_ptd_host &)

- ea: `0x180034678`
- end: `0x180034724`
- name: `??$ensure_buffer_is_big_enough@_W@formatting_buffer@__crt_stdio_output@@QEAA_N_KAEAV__crt_cached_ptd_host@@@Z`
- size: `172`
- prototype: ``
- caller_count: `18`
- callee_count: `3`
- tags: ``

## callers

- `0x180039fd4`
- `0x18003a1e0`
- `0x18003a41c`
- `0x18003a628`
- `0x18003a834`
- `0x18003aa70`
- `0x18003b8fc`
- `0x18003bb08`
- `0x18003bd44`
- `0x18003bf50`
- `0x18003c15c`
- `0x18003c398`
- `0x18003d224`
- `0x18003d430`
- `0x18003d66c`
- `0x18003d878`
- `0x18003da84`
- `0x18003dcc0`

## callees

- `0x1800078e0`
- `0x180011f70`
- `0x180034678`

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
0x180034678  mov     [rsp+arg_0], rbx
0x18003467d  mov     [rsp+arg_8], rbp
0x180034682  mov     [rsp+arg_10], rsi
0x180034687  push    rdi
0x180034688  sub     rsp, 20h
0x18003468c  mov     rax, 3FFFFFFFFFFFFFFFh
0x180034696  mov     rbp, rcx
0x180034699  cmp     rdx, rax
0x18003469c  jbe     short loc_1800346AF
0x18003469e  mov     byte ptr [r8+30h], 1
0x1800346a3  xor     al, al
0x1800346a5  mov     dword ptr [r8+2Ch], 0Ch
0x1800346ad  jmp     short loc_18003470F
0x1800346af  xor     edi, edi
0x1800346b1  lea     rsi, ds:0[rdx*4]
0x1800346b9  cmp     [rcx+408h], rdi
0x1800346c0  jnz     short loc_1800346CB
0x1800346c2  cmp     rsi, 400h
0x1800346c9  jbe     short loc_1800346D4
0x1800346cb  cmp     rsi, [rcx+400h]
0x1800346d2  ja      short loc_1800346D8
0x1800346d4  mov     al, 1
0x1800346d6  jmp     short loc_18003470F
0x1800346d8  mov     rcx, rsi; Size
0x1800346db  call    _malloc_base
0x1800346e0  mov     rbx, rax
0x1800346e3  test    rax, rax
0x1800346e6  jz      short loc_180034705
0x1800346e8  mov     rcx, [rbp+408h]; Block
0x1800346ef  call    _free_base
0x1800346f4  mov     [rbp+408h], rbx
0x1800346fb  mov     dil, 1
0x1800346fe  mov     [rbp+400h], rsi
0x180034705  xor     ecx, ecx; Block
0x180034707  call    _free_base
0x18003470c  mov     al, dil
0x18003470f  mov     rbx, [rsp+28h+arg_0]
0x180034714  mov     rbp, [rsp+28h+arg_8]
0x180034719  mov     rsi, [rsp+28h+arg_10]
0x18003471e  add     rsp, 20h
0x180034722  pop     rdi
0x180034723  retn
```
