# CommonUtil::MpDuplicateBuffer<wchar_t>(wchar_t * *,unsigned __int64,wchar_t const *)

- ea: `0x140003008`
- end: `0x140003052`
- name: `??$MpDuplicateBuffer@_W@CommonUtil@@YAJPEAPEA_W_KPEB_W@Z`
- size: `74`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140003054`

## callees

- `0x140003008`
- `0x140024bcc`
- `0x140025080`

## pseudocode

```c
__int64 __fastcall CommonUtil::MpDuplicateBuffer<wchar_t>(void **a1, __int64 a2, const void *a3)
{
  __int64 result; // rax

  result = CommonUtil::MpNewBuffer<wchar_t>(a1, a2);
  if ( (int)result >= 0 )
  {
    memmove(*a1, a3, 2 * a2);
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x140003008  mov     [rsp+arg_0], rbx
0x14000300d  mov     [rsp+arg_8], rsi
0x140003012  push    rdi
0x140003013  sub     rsp, 20h
0x140003017  mov     rsi, r8
0x14000301a  mov     rbx, rdx
0x14000301d  mov     rdi, rcx
0x140003020  call    ??$MpNewBuffer@_W@CommonUtil@@YAJPEAPEA_W_K@Z; CommonUtil::MpNewBuffer<wchar_t>(wchar_t * *,unsigned __int64)
0x140003025  mov     r9d, eax
0x140003028  shr     r9d, 1Fh
0x14000302c  test    r9b, r9b
0x14000302f  jnz     short loc_140003042
0x140003031  mov     rcx, [rdi]; void *
0x140003034  lea     r8, [rbx+rbx]; Size
0x140003038  mov     rdx, rsi; Src
0x14000303b  call    memmove
0x140003040  xor     eax, eax
0x140003042  mov     rbx, [rsp+28h+arg_0]
0x140003047  mov     rsi, [rsp+28h+arg_8]
0x14000304c  add     rsp, 20h
0x140003050  pop     rdi
0x140003051  retn
```
