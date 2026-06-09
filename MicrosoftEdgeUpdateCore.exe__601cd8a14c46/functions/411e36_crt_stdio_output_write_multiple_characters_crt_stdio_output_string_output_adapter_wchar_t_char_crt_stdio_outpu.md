# __crt_stdio_output::write_multiple_characters<__crt_stdio_output::string_output_adapter<wchar_t>,char>(__crt_stdio_output::string_output_adapter<wchar_t> const &,char,int,int * const)

- ea: `0x411e36`
- end: `0x411e67`
- name: `??$write_multiple_characters@V?$string_output_adapter@_W@__crt_stdio_output@@D@__crt_stdio_output@@YAXABV?$string_output_adapter@_W@0@DHQAH@Z`
- size: `49`
- prototype: `int __cdecl(int, char, int, _DWORD *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x4125d5`

## callees

- `0x411e36`
- `0x412e0a`

## pseudocode

```c
int __cdecl __crt_stdio_output::write_multiple_characters<__crt_stdio_output::string_output_adapter<wchar_t>,char>(
        int a1,
        char a2,
        int a3,
        _DWORD *a4)
{
  int i; // esi
  int result; // eax

  for ( i = 0; i < a3; ++i )
  {
    result = __crt_stdio_output::string_output_adapter<wchar_t>::write_character(a2, a4);
    if ( *a4 == -1 )
      break;
  }
  return result;
}

```

## disassembly

```asm
0x411e36  mov     edi, edi
0x411e38  push    ebp
0x411e39  mov     ebp, esp
0x411e3b  push    esi
0x411e3c  xor     esi, esi
0x411e3e  cmp     [ebp+arg_8], esi
0x411e41  jle     short loc_411E64
0x411e43  push    ebx
0x411e44  movsx   bx, [ebp+arg_4]
0x411e49  push    edi
0x411e4a  mov     edi, [ebp+arg_C]
0x411e4d  mov     ecx, [ebp+arg_0]
0x411e50  push    edi
0x411e51  push    ebx
0x411e52  call    ?write_character@?$string_output_adapter@_W@__crt_stdio_output@@QBE_N_WQAH@Z
0x411e57  cmp     dword ptr [edi], 0FFFFFFFFh
0x411e5a  jz      short loc_411E62
0x411e5c  inc     esi
0x411e5d  cmp     esi, [ebp+arg_8]
0x411e60  jl      short loc_411E4D
0x411e62  pop     edi
0x411e63  pop     ebx
0x411e64  pop     esi
0x411e65  pop     ebp
0x411e66  retn
```
