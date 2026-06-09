# __crt_stdio_output::write_multiple_characters<__crt_stdio_output::string_output_adapter<wchar_t>,char>(__crt_stdio_output::string_output_adapter<wchar_t> const &,char,int,int * const)

- ea: `0x40c9a3`
- end: `0x40c9d4`
- name: `??$write_multiple_characters@V?$string_output_adapter@_W@__crt_stdio_output@@D@__crt_stdio_output@@YAXABV?$string_output_adapter@_W@0@DHQAH@Z`
- size: `49`
- prototype: `int __cdecl(int, char, int, _DWORD *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x40d155`

## callees

- `0x40c9a3`
- `0x40d98a`

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
0x40c9a3  mov     edi, edi
0x40c9a5  push    ebp
0x40c9a6  mov     ebp, esp
0x40c9a8  push    esi
0x40c9a9  xor     esi, esi
0x40c9ab  cmp     [ebp+arg_8], esi
0x40c9ae  jle     short loc_40C9D1
0x40c9b0  push    ebx
0x40c9b1  movsx   bx, [ebp+arg_4]
0x40c9b6  push    edi
0x40c9b7  mov     edi, [ebp+arg_C]
0x40c9ba  mov     ecx, [ebp+arg_0]
0x40c9bd  push    edi
0x40c9be  push    ebx
0x40c9bf  call    ?write_character@?$string_output_adapter@_W@__crt_stdio_output@@QBE_N_WQAH@Z
0x40c9c4  cmp     dword ptr [edi], 0FFFFFFFFh
0x40c9c7  jz      short loc_40C9CF
0x40c9c9  inc     esi
0x40c9ca  cmp     esi, [ebp+arg_8]
0x40c9cd  jl      short loc_40C9BA
0x40c9cf  pop     edi
0x40c9d0  pop     ebx
0x40c9d1  pop     esi
0x40c9d2  pop     ebp
0x40c9d3  retn
```
