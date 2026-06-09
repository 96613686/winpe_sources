# __crt_stdio_output::formatting_buffer::ensure_buffer_is_big_enough<char>(unsigned __int64,__crt_cached_ptd_host &)

- ea: `0x1800345d0`
- end: `0x180034678`
- name: `??$ensure_buffer_is_big_enough@D@formatting_buffer@__crt_stdio_output@@QEAA_N_KAEAV__crt_cached_ptd_host@@@Z`
- size: `168`
- prototype: ``
- caller_count: `30`
- callee_count: `3`
- tags: ``

## callers

- `0x180039354`
- `0x180039558`
- `0x180039790`
- `0x180039994`
- `0x180039b98`
- `0x180039dd0`
- `0x18003ac7c`
- `0x18003ae80`
- `0x18003b0b8`
- `0x18003b2bc`
- `0x18003b4c0`
- `0x18003b6f8`
- `0x18003c5a4`
- `0x18003c7a8`
- `0x18003c9e0`
- `0x18003cbe4`
- `0x18003cde8`
- `0x18003d020`
- `0x18004de90`
- `0x18004e0ec`
- `0x18004e368`
- `0x18004e5c4`
- `0x18004e820`
- `0x18004ea9c`
- `0x18004ecf8`
- `0x18004ef74`
- `0x18004f210`
- `0x18004f48c`
- `0x18004f708`
- `0x18004f9a4`

## callees

- `0x1800078e0`
- `0x180011f70`
- `0x1800345d0`

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
0x1800345d0  mov     [rsp+arg_0], rbx
0x1800345d5  mov     [rsp+arg_8], rbp
0x1800345da  mov     [rsp+arg_10], rsi
0x1800345df  push    rdi
0x1800345e0  sub     rsp, 20h
0x1800345e4  mov     rax, 7FFFFFFFFFFFFFFFh
0x1800345ee  mov     rbp, rcx
0x1800345f1  cmp     rdx, rax
0x1800345f4  jbe     short loc_180034607
0x1800345f6  mov     byte ptr [r8+30h], 1
0x1800345fb  xor     al, al
0x1800345fd  mov     dword ptr [r8+2Ch], 0Ch
0x180034605  jmp     short loc_180034663
0x180034607  xor     edi, edi
0x180034609  lea     rsi, [rdx+rdx]
0x18003460d  cmp     [rcx+408h], rdi
0x180034614  jnz     short loc_18003461F
0x180034616  cmp     rsi, 400h
0x18003461d  jbe     short loc_180034628
0x18003461f  cmp     rsi, [rcx+400h]
0x180034626  ja      short loc_18003462C
0x180034628  mov     al, 1
0x18003462a  jmp     short loc_180034663
0x18003462c  mov     rcx, rsi; Size
0x18003462f  call    _malloc_base
0x180034634  mov     rbx, rax
0x180034637  test    rax, rax
0x18003463a  jz      short loc_180034659
0x18003463c  mov     rcx, [rbp+408h]; Block
0x180034643  call    _free_base
0x180034648  mov     [rbp+408h], rbx
0x18003464f  mov     dil, 1
0x180034652  mov     [rbp+400h], rsi
0x180034659  xor     ecx, ecx; Block
0x18003465b  call    _free_base
0x180034660  mov     al, dil
0x180034663  mov     rbx, [rsp+28h+arg_0]
0x180034668  mov     rbp, [rsp+28h+arg_8]
0x18003466d  mov     rsi, [rsp+28h+arg_10]
0x180034672  add     rsp, 20h
0x180034676  pop     rdi
0x180034677  retn
```
