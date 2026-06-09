# __crt_stdio_input::input_processor<wchar_t,__crt_stdio_input::string_input_adapter<wchar_t>>::write_integer(unsigned __int64)

- ea: `0x180023bb8`
- end: `0x180023c2a`
- name: `?write_integer@?$input_processor@_WV?$string_input_adapter@_W@__crt_stdio_input@@@__crt_stdio_input@@AEAA_N_K@Z`
- size: `114`
- prototype: `char __fastcall(__int64, __int64)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x1800225a0`
- `0x180022864`

## callees

- `0x18000be9c`
- `0x18000bfbc`
- `0x180022204`
- `0x180023bb8`

## pseudocode

```c
char __fastcall __crt_stdio_input::input_processor<wchar_t,__crt_stdio_input::string_input_adapter<wchar_t>>::write_integer(
        __int64 a1,
        __int64 a2)
{
  _QWORD *v3; // rbx
  __int64 v5; // rax
  __int64 v6; // rax
  __int64 v7; // rax

  *(_QWORD *)(a1 + 104) += 8LL;
  v3 = *(_QWORD **)(*(_QWORD *)(a1 + 104) - 8LL);
  if ( !v3 )
  {
    *errno() = 22;
    invalid_parameter_noinfo();
    return 0;
  }
  v5 = __crt_stdio_input::format_string_parser<wchar_t>::length(a1 + 32) - 1;
  if ( v5 )
  {
    v6 = v5 - 1;
    if ( v6 )
    {
      v7 = v6 - 2;
      if ( v7 )
      {
        if ( v7 != 4 )
          return 0;
        *v3 = a2;
      }
      else
      {
        *(_DWORD *)v3 = a2;
      }
    }
    else
    {
      *(_WORD *)v3 = a2;
    }
  }
  else
  {
    *(_BYTE *)v3 = a2;
  }
  return 1;
}

```

## disassembly

```asm
0x180023bb8  mov     [rsp+arg_0], rbx
0x180023bbd  push    rdi
0x180023bbe  sub     rsp, 20h
0x180023bc2  add     qword ptr [rcx+68h], 8
0x180023bc7  mov     rdi, rdx
0x180023bca  mov     rax, [rcx+68h]
0x180023bce  mov     rbx, [rax-8]
0x180023bd2  test    rbx, rbx
0x180023bd5  jnz     short loc_180023BEB
0x180023bd7  call    _errno
0x180023bdc  mov     dword ptr [rax], 16h
0x180023be2  call    _invalid_parameter_noinfo
0x180023be7  xor     al, al
0x180023be9  jmp     short loc_180023C1F
0x180023beb  add     rcx, 20h ; ' '
0x180023bef  call    ?length@?$format_string_parser@_W@__crt_stdio_input@@QEBA_KXZ; __crt_stdio_input::format_string_parser<wchar_t>::length(void)
0x180023bf4  sub     rax, 1
0x180023bf8  jz      short loc_180023C1A
0x180023bfa  sub     rax, 1
0x180023bfe  jz      short loc_180023C15
0x180023c00  sub     rax, 2
0x180023c04  jz      short loc_180023C11
0x180023c06  cmp     rax, 4
0x180023c0a  jnz     short loc_180023BE7
0x180023c0c  mov     [rbx], rdi
0x180023c0f  jmp     short loc_180023C1D
0x180023c11  mov     [rbx], edi
0x180023c13  jmp     short loc_180023C1D
0x180023c15  mov     [rbx], di
0x180023c18  jmp     short loc_180023C1D
0x180023c1a  mov     [rbx], dil
0x180023c1d  mov     al, 1
0x180023c1f  mov     rbx, [rsp+28h+arg_0]
0x180023c24  add     rsp, 20h
0x180023c28  pop     rdi
0x180023c29  retn
```
