# __crt_stdio_output::formatting_buffer::ensure_buffer_is_big_enough<char>(unsigned __int64,__crt_cached_ptd_host &)

- ea: `0x14000c850`
- end: `0x14000c8f8`
- name: `??$ensure_buffer_is_big_enough@D@formatting_buffer@__crt_stdio_output@@QEAA_N_KAEAV__crt_cached_ptd_host@@@Z`
- size: `168`
- prototype: ``
- caller_count: `5`
- callee_count: `3`
- tags: ``

## callers

- `0x14000d404`
- `0x14000d814`
- `0x14000dc24`
- `0x14000fd18`
- `0x14000ff74`

## callees

- `0x14000c850`
- `0x140013e10`
- `0x140013e70`

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
0x14000c850  mov     [rsp+arg_0], rbx
0x14000c855  mov     [rsp+arg_8], rbp
0x14000c85a  mov     [rsp+arg_10], rsi
0x14000c85f  push    rdi
0x14000c860  sub     rsp, 20h
0x14000c864  mov     rax, 7FFFFFFFFFFFFFFFh
0x14000c86e  mov     rbp, rcx
0x14000c871  cmp     rdx, rax
0x14000c874  jbe     short loc_14000C887
0x14000c876  mov     byte ptr [r8+30h], 1
0x14000c87b  xor     al, al
0x14000c87d  mov     dword ptr [r8+2Ch], 0Ch
0x14000c885  jmp     short loc_14000C8E3
0x14000c887  xor     edi, edi
0x14000c889  lea     rsi, [rdx+rdx]
0x14000c88d  cmp     [rcx+408h], rdi
0x14000c894  jnz     short loc_14000C89F
0x14000c896  cmp     rsi, 400h
0x14000c89d  jbe     short loc_14000C8A8
0x14000c89f  cmp     rsi, [rcx+400h]
0x14000c8a6  ja      short loc_14000C8AC
0x14000c8a8  mov     al, 1
0x14000c8aa  jmp     short loc_14000C8E3
0x14000c8ac  mov     rcx, rsi; Size
0x14000c8af  call    _malloc_base
0x14000c8b4  mov     rbx, rax
0x14000c8b7  test    rax, rax
0x14000c8ba  jz      short loc_14000C8D9
0x14000c8bc  mov     rcx, [rbp+408h]; Block
0x14000c8c3  call    _free_base
0x14000c8c8  mov     [rbp+408h], rbx
0x14000c8cf  mov     dil, 1
0x14000c8d2  mov     [rbp+400h], rsi
0x14000c8d9  xor     ecx, ecx; Block
0x14000c8db  call    _free_base
0x14000c8e0  mov     al, dil
0x14000c8e3  mov     rbx, [rsp+28h+arg_0]
0x14000c8e8  mov     rbp, [rsp+28h+arg_8]
0x14000c8ed  mov     rsi, [rsp+28h+arg_10]
0x14000c8f2  add     rsp, 20h
0x14000c8f6  pop     rdi
0x14000c8f7  retn
```
