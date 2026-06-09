# __crt_stdio_output::formatting_buffer::ensure_buffer_is_big_enough<char>(unsigned __int64,__crt_cached_ptd_host &)

- ea: `0x14000b2d0`
- end: `0x14000b378`
- name: `??$ensure_buffer_is_big_enough@D@formatting_buffer@__crt_stdio_output@@QEAA_N_KAEAV__crt_cached_ptd_host@@@Z`
- size: `168`
- prototype: `char __fastcall(__int64, unsigned __int64, __int64)`
- caller_count: `5`
- callee_count: `3`
- tags: ``

## callers

- `0x14000be90`
- `0x14000c2a0`
- `0x14000c6b0`
- `0x14000e9ec`
- `0x14000ec40`

## callees

- `0x14000b2d0`
- `0x1400107c4`
- `0x140012040`

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
0x14000b2d0  mov     [rsp+arg_0], rbx
0x14000b2d5  mov     [rsp+arg_8], rbp
0x14000b2da  mov     [rsp+arg_10], rsi
0x14000b2df  push    rdi
0x14000b2e0  sub     rsp, 20h
0x14000b2e4  mov     rax, 7FFFFFFFFFFFFFFFh
0x14000b2ee  mov     rbp, rcx
0x14000b2f1  cmp     rdx, rax
0x14000b2f4  jbe     short loc_14000B307
0x14000b2f6  mov     byte ptr [r8+30h], 1
0x14000b2fb  xor     al, al
0x14000b2fd  mov     dword ptr [r8+2Ch], 0Ch
0x14000b305  jmp     short loc_14000B363
0x14000b307  xor     edi, edi
0x14000b309  lea     rsi, [rdx+rdx]
0x14000b30d  cmp     [rcx+408h], rdi
0x14000b314  jnz     short loc_14000B31F
0x14000b316  cmp     rsi, 400h
0x14000b31d  jbe     short loc_14000B328
0x14000b31f  cmp     rsi, [rcx+400h]
0x14000b326  ja      short loc_14000B32C
0x14000b328  mov     al, 1
0x14000b32a  jmp     short loc_14000B363
0x14000b32c  mov     rcx, rsi; Size
0x14000b32f  call    _malloc_base
0x14000b334  mov     rbx, rax
0x14000b337  test    rax, rax
0x14000b33a  jz      short loc_14000B359
0x14000b33c  mov     rcx, [rbp+408h]; Block
0x14000b343  call    _free_base
0x14000b348  mov     [rbp+408h], rbx
0x14000b34f  mov     dil, 1
0x14000b352  mov     [rbp+400h], rsi
0x14000b359  xor     ecx, ecx; Block
0x14000b35b  call    _free_base
0x14000b360  mov     al, dil
0x14000b363  mov     rbx, [rsp+28h+arg_0]
0x14000b368  mov     rbp, [rsp+28h+arg_8]
0x14000b36d  mov     rsi, [rsp+28h+arg_10]
0x14000b372  add     rsp, 20h
0x14000b376  pop     rdi
0x14000b377  retn
```
