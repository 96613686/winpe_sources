# __crt_stdio_input::skip_whitespace<__crt_stdio_input::string_input_adapter,char>(__crt_stdio_input::string_input_adapter<char> &,__crt_locale_pointers * const)

- ea: `0x18001f908`
- end: `0x18001f95b`
- name: `??$skip_whitespace@Vstring_input_adapter@__crt_stdio_input@@D@__crt_stdio_input@@YAHAEAV?$string_input_adapter@D@0@QEAU__crt_locale_pointers@@@Z`
- size: `83`
- prototype: `__int64 __fastcall(__int64, __crt_locale_pointers *)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x1800226c4`
- `0x1800227ac`
- `0x1800229a8`
- `0x180022b20`

## callees

- `0x18000fcac`
- `0x18001f908`

## pseudocode

```c
__int64 __fastcall __crt_stdio_input::skip_whitespace<__crt_stdio_input::string_input_adapter,char>(
        __int64 a1,
        __crt_locale_pointers *a2)
{
  unsigned __int8 *v4; // rax
  unsigned int v5; // ebx

  while ( 1 )
  {
    v4 = *(unsigned __int8 **)(a1 + 16);
    if ( v4 == *(unsigned __int8 **)(a1 + 8) )
      break;
    v5 = *v4;
    *(_QWORD *)(a1 + 16) = v4 + 1;
    if ( !ischartype_l(v5, 8, a2) )
      return v5;
  }
  return (unsigned int)-1;
}

```

## disassembly

```asm
0x18001f908  mov     [rsp+arg_0], rbx
0x18001f90d  mov     [rsp+arg_8], rsi
0x18001f912  push    rdi
0x18001f913  sub     rsp, 20h
0x18001f917  mov     rsi, rdx
0x18001f91a  mov     rdi, rcx
0x18001f91d  mov     rax, [rdi+10h]
0x18001f921  cmp     rax, [rdi+8]
0x18001f925  jz      short loc_18001F946
0x18001f927  movzx   ebx, byte ptr [rax]
0x18001f92a  mov     r8, rsi; Locale
0x18001f92d  inc     rax
0x18001f930  mov     ecx, ebx; C
0x18001f932  mov     edx, 8; Mask
0x18001f937  mov     [rdi+10h], rax
0x18001f93b  call    _ischartype_l
0x18001f940  test    eax, eax
0x18001f942  jz      short loc_18001F949
0x18001f944  jmp     short loc_18001F91D
0x18001f946  or      ebx, 0FFFFFFFFh
0x18001f949  mov     rsi, [rsp+28h+arg_8]
0x18001f94e  mov     eax, ebx
0x18001f950  mov     rbx, [rsp+28h+arg_0]
0x18001f955  add     rsp, 20h
0x18001f959  pop     rdi
0x18001f95a  retn
```
