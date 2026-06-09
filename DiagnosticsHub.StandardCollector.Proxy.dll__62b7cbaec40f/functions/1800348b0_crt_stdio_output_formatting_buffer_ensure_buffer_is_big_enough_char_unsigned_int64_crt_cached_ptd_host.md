# __crt_stdio_output::formatting_buffer::ensure_buffer_is_big_enough<char>(unsigned __int64,__crt_cached_ptd_host &)

- ea: `0x1800348b0`
- end: `0x180034958`
- name: `??$ensure_buffer_is_big_enough@D@formatting_buffer@__crt_stdio_output@@QEAA_N_KAEAV__crt_cached_ptd_host@@@Z`
- size: `168`
- prototype: ``
- caller_count: `30`
- callee_count: `3`
- tags: ``

## callers

- `0x180039634`
- `0x180039838`
- `0x180039a70`
- `0x180039c74`
- `0x180039e78`
- `0x18003a0b0`
- `0x18003af5c`
- `0x18003b160`
- `0x18003b398`
- `0x18003b59c`
- `0x18003b7a0`
- `0x18003b9d8`
- `0x18003c884`
- `0x18003ca88`
- `0x18003ccc0`
- `0x18003cec4`
- `0x18003d0c8`
- `0x18003d300`
- `0x18004e170`
- `0x18004e3cc`
- `0x18004e648`
- `0x18004e8a4`
- `0x18004eb00`
- `0x18004ed7c`
- `0x18004efd8`
- `0x18004f254`
- `0x18004f4f0`
- `0x18004f76c`
- `0x18004f9e8`
- `0x18004fc84`

## callees

- `0x180008040`
- `0x1800126d0`
- `0x1800348b0`

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
0x1800348b0  mov     [rsp+arg_0], rbx
0x1800348b5  mov     [rsp+arg_8], rbp
0x1800348ba  mov     [rsp+arg_10], rsi
0x1800348bf  push    rdi
0x1800348c0  sub     rsp, 20h
0x1800348c4  mov     rax, 7FFFFFFFFFFFFFFFh
0x1800348ce  mov     rbp, rcx
0x1800348d1  cmp     rdx, rax
0x1800348d4  jbe     short loc_1800348E7
0x1800348d6  mov     byte ptr [r8+30h], 1
0x1800348db  xor     al, al
0x1800348dd  mov     dword ptr [r8+2Ch], 0Ch
0x1800348e5  jmp     short loc_180034943
0x1800348e7  xor     edi, edi
0x1800348e9  lea     rsi, [rdx+rdx]
0x1800348ed  cmp     [rcx+408h], rdi
0x1800348f4  jnz     short loc_1800348FF
0x1800348f6  cmp     rsi, 400h
0x1800348fd  jbe     short loc_180034908
0x1800348ff  cmp     rsi, [rcx+400h]
0x180034906  ja      short loc_18003490C
0x180034908  mov     al, 1
0x18003490a  jmp     short loc_180034943
0x18003490c  mov     rcx, rsi; Size
0x18003490f  call    _malloc_base
0x180034914  mov     rbx, rax
0x180034917  test    rax, rax
0x18003491a  jz      short loc_180034939
0x18003491c  mov     rcx, [rbp+408h]; Block
0x180034923  call    _free_base
0x180034928  mov     [rbp+408h], rbx
0x18003492f  mov     dil, 1
0x180034932  mov     [rbp+400h], rsi
0x180034939  xor     ecx, ecx; Block
0x18003493b  call    _free_base
0x180034940  mov     al, dil
0x180034943  mov     rbx, [rsp+28h+arg_0]
0x180034948  mov     rbp, [rsp+28h+arg_8]
0x18003494d  mov     rsi, [rsp+28h+arg_10]
0x180034952  add     rsp, 20h
0x180034956  pop     rdi
0x180034957  retn
```
