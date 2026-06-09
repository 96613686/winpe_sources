# __crt_stdio_output::formatting_buffer::ensure_buffer_is_big_enough<char>(unsigned __int64,__crt_cached_ptd_host &)

- ea: `0x140061a40`
- end: `0x140061ae8`
- name: `??$ensure_buffer_is_big_enough@D@formatting_buffer@__crt_stdio_output@@QEAA_N_KAEAV__crt_cached_ptd_host@@@Z`
- size: `168`
- prototype: `char __fastcall(__int64, unsigned __int64, __int64)`
- caller_count: `5`
- callee_count: `3`
- tags: ``

## callers

- `0x1400625f4`
- `0x140062a04`
- `0x140062e14`
- `0x14006552c`
- `0x140065788`

## callees

- `0x140061a40`
- `0x140072280`
- `0x1400722e0`

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
0x140061a40  mov     [rsp+arg_0], rbx
0x140061a45  mov     [rsp+arg_8], rbp
0x140061a4a  mov     [rsp+arg_10], rsi
0x140061a4f  push    rdi
0x140061a50  sub     rsp, 20h
0x140061a54  mov     rax, 7FFFFFFFFFFFFFFFh
0x140061a5e  mov     rbp, rcx
0x140061a61  cmp     rdx, rax
0x140061a64  jbe     short loc_140061A77
0x140061a66  mov     byte ptr [r8+30h], 1
0x140061a6b  xor     al, al
0x140061a6d  mov     dword ptr [r8+2Ch], 0Ch
0x140061a75  jmp     short loc_140061AD3
0x140061a77  xor     edi, edi
0x140061a79  lea     rsi, [rdx+rdx]
0x140061a7d  cmp     [rcx+408h], rdi
0x140061a84  jnz     short loc_140061A8F
0x140061a86  cmp     rsi, 400h
0x140061a8d  jbe     short loc_140061A98
0x140061a8f  cmp     rsi, [rcx+400h]
0x140061a96  ja      short loc_140061A9C
0x140061a98  mov     al, 1
0x140061a9a  jmp     short loc_140061AD3
0x140061a9c  mov     rcx, rsi; Size
0x140061a9f  call    _malloc_base
0x140061aa4  mov     rbx, rax
0x140061aa7  test    rax, rax
0x140061aaa  jz      short loc_140061AC9
0x140061aac  mov     rcx, [rbp+408h]; Block
0x140061ab3  call    _free_base
0x140061ab8  mov     [rbp+408h], rbx
0x140061abf  mov     dil, 1
0x140061ac2  mov     [rbp+400h], rsi
0x140061ac9  xor     ecx, ecx; Block
0x140061acb  call    _free_base
0x140061ad0  mov     al, dil
0x140061ad3  mov     rbx, [rsp+28h+arg_0]
0x140061ad8  mov     rbp, [rsp+28h+arg_8]
0x140061add  mov     rsi, [rsp+28h+arg_10]
0x140061ae2  add     rsp, 20h
0x140061ae6  pop     rdi
0x140061ae7  retn
```
