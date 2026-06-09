# __crt_stdio_output::write_multiple_characters<__crt_stdio_output::string_output_adapter<wchar_t>,char>(__crt_stdio_output::string_output_adapter<wchar_t> const &,char,int,int * const)

- ea: `0x18000c52c`
- end: `0x18000c5a2`
- name: `??$write_multiple_characters@V?$string_output_adapter@_W@__crt_stdio_output@@D@__crt_stdio_output@@YAXAEBV?$string_output_adapter@_W@0@DHQEAH@Z`
- size: `118`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18000cbfc`

## callees

- `0x18000c52c`

## pseudocode

```c
__int64 __fastcall __crt_stdio_output::write_multiple_characters<__crt_stdio_output::string_output_adapter<wchar_t>,char>(
        __int64 *a1,
        char a2,
        int a3,
        int *a4)
{
  int v4; // r10d
  int i; // r11d
  __int64 result; // rax

  if ( a3 > 0 )
  {
    v4 = *a4;
    for ( i = 0; i < a3; ++i )
    {
      result = *(_QWORD *)(*a1 + 8);
      if ( *(_QWORD *)(*a1 + 16) == result )
      {
        if ( *(_BYTE *)(*a1 + 24) )
          ++v4;
        else
          v4 = -1;
        *a4 = v4;
      }
      else
      {
        *a4 = v4 + 1;
        ++*(_QWORD *)(*a1 + 16);
        **(_WORD **)*a1 = a2;
        result = *a1;
        *(_QWORD *)*a1 += 2LL;
        v4 = *a4;
      }
      if ( v4 == -1 )
        break;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18000c52c  test    r8d, r8d
0x18000c52f  jle     short locret_18000C5A1
0x18000c531  mov     [rsp+arg_0], rbx
0x18000c536  mov     [rsp+arg_8], rdi
0x18000c53b  mov     r10d, [r9]
0x18000c53e  mov     rbx, rcx
0x18000c541  movsx   edi, dl
0x18000c544  xor     r11d, r11d
0x18000c547  mov     rdx, [rbx]
0x18000c54a  mov     rax, [rdx+8]
0x18000c54e  cmp     [rdx+10h], rax
0x18000c552  jnz     short loc_18000C568
0x18000c554  cmp     byte ptr [rdx+18h], 0
0x18000c558  jz      short loc_18000C55F
0x18000c55a  inc     r10d
0x18000c55d  jmp     short loc_18000C563
0x18000c55f  or      r10d, 0FFFFFFFFh
0x18000c563  mov     [r9], r10d
0x18000c566  jmp     short loc_18000C589
0x18000c568  lea     eax, [r10+1]
0x18000c56c  mov     [r9], eax
0x18000c56f  mov     rax, [rbx]
0x18000c572  inc     qword ptr [rax+10h]
0x18000c576  mov     rax, [rbx]
0x18000c579  mov     rcx, [rax]
0x18000c57c  mov     [rcx], di
0x18000c57f  mov     rax, [rbx]
0x18000c582  add     qword ptr [rax], 2
0x18000c586  mov     r10d, [r9]
0x18000c589  cmp     r10d, 0FFFFFFFFh
0x18000c58d  jz      short loc_18000C597
0x18000c58f  inc     r11d
0x18000c592  cmp     r11d, r8d
0x18000c595  jl      short loc_18000C547
0x18000c597  mov     rbx, [rsp+arg_0]
0x18000c59c  mov     rdi, [rsp+arg_8]
0x18000c5a1  retn
```
