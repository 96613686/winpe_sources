# __crt_stdio_input::skip_whitespace<__crt_stdio_input::string_input_adapter,wchar_t>(__crt_stdio_input::string_input_adapter<wchar_t> &,__crt_locale_pointers * const)

- ea: `0x18001f95c`
- end: `0x18001f9b5`
- name: `??$skip_whitespace@Vstring_input_adapter@__crt_stdio_input@@_W@__crt_stdio_input@@YAGAEAV?$string_input_adapter@_W@0@QEAU__crt_locale_pointers@@@Z`
- size: `89`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x180022734`
- `0x180022864`
- `0x180022a60`
- `0x180022bac`

## callees

- `0x180014730`
- `0x18001f95c`

## pseudocode

```c
__int64 __fastcall __crt_stdio_input::skip_whitespace<__crt_stdio_input::string_input_adapter,wchar_t>(__int64 a1)
{
  wint_t *v2; // rax
  wint_t v3; // bx

  while ( 1 )
  {
    v2 = *(wint_t **)(a1 + 16);
    if ( v2 == *(wint_t **)(a1 + 8) )
      break;
    v3 = *v2;
    *(_QWORD *)(a1 + 16) = v2 + 1;
    if ( v3 == 0xFFFF || !iswctype(v3, 8u) )
      return v3;
  }
  return (wint_t)-1;
}

```

## disassembly

```asm
0x18001f95c  mov     [rsp+arg_0], rbx
0x18001f961  mov     [rsp+arg_8], rsi
0x18001f966  push    rdi
0x18001f967  sub     rsp, 20h
0x18001f96b  mov     rdi, rcx
0x18001f96e  mov     esi, 0FFFFh
0x18001f973  mov     rax, [rdi+10h]
0x18001f977  cmp     rax, [rdi+8]
0x18001f97b  jz      short loc_18001F9A0
0x18001f97d  movzx   ebx, word ptr [rax]
0x18001f980  add     rax, 2
0x18001f984  mov     [rdi+10h], rax
0x18001f988  cmp     bx, si
0x18001f98b  jz      short loc_18001F9A2
0x18001f98d  mov     edx, 8; Type
0x18001f992  movzx   ecx, bx; C
0x18001f995  call    iswctype
0x18001f99a  test    eax, eax
0x18001f99c  jz      short loc_18001F9A2
0x18001f99e  jmp     short loc_18001F973
0x18001f9a0  mov     ebx, esi
0x18001f9a2  mov     rsi, [rsp+28h+arg_8]
0x18001f9a7  movzx   eax, bx
0x18001f9aa  mov     rbx, [rsp+28h+arg_0]
0x18001f9af  add     rsp, 20h
0x18001f9b3  pop     rdi
0x18001f9b4  retn
```
