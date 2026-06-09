# __crt_stdio_input::input_processor<char,__crt_stdio_input::string_input_adapter<char>>::write_integer(unsigned __int64)

- ea: `0x180023b40`
- end: `0x180023bb8`
- name: `?write_integer@?$input_processor@DV?$string_input_adapter@D@__crt_stdio_input@@@__crt_stdio_input@@AEAA_N_K@Z`
- size: `120`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x180022480`
- `0x1800227ac`

## callees

- `0x18000be9c`
- `0x18000bfbc`
- `0x180022204`
- `0x180023b40`

## pseudocode

```c
char __fastcall __crt_stdio_input::input_processor<char,__crt_stdio_input::string_input_adapter<char>>::write_integer(
        __int64 a1,
        __int64 a2)
{
  _QWORD *v3; // rbx
  __int64 v5; // rax
  __int64 v6; // rax
  __int64 v7; // rax

  *(_QWORD *)(a1 + 128) += 8LL;
  v3 = *(_QWORD **)(*(_QWORD *)(a1 + 128) - 8LL);
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
0x180023b40  mov     [rsp+arg_0], rbx
0x180023b45  push    rdi
0x180023b46  sub     rsp, 20h
0x180023b4a  add     qword ptr [rcx+80h], 8
0x180023b52  mov     rdi, rdx
0x180023b55  mov     rax, [rcx+80h]
0x180023b5c  mov     rbx, [rax-8]
0x180023b60  test    rbx, rbx
0x180023b63  jnz     short loc_180023B79
0x180023b65  call    _errno
0x180023b6a  mov     dword ptr [rax], 16h
0x180023b70  call    _invalid_parameter_noinfo
0x180023b75  xor     al, al
0x180023b77  jmp     short loc_180023BAD
0x180023b79  add     rcx, 20h ; ' '
0x180023b7d  call    ?length@?$format_string_parser@_W@__crt_stdio_input@@QEBA_KXZ; __crt_stdio_input::format_string_parser<wchar_t>::length(void)
0x180023b82  sub     rax, 1
0x180023b86  jz      short loc_180023BA8
0x180023b88  sub     rax, 1
0x180023b8c  jz      short loc_180023BA3
0x180023b8e  sub     rax, 2
0x180023b92  jz      short loc_180023B9F
0x180023b94  cmp     rax, 4
0x180023b98  jnz     short loc_180023B75
0x180023b9a  mov     [rbx], rdi
0x180023b9d  jmp     short loc_180023BAB
0x180023b9f  mov     [rbx], edi
0x180023ba1  jmp     short loc_180023BAB
0x180023ba3  mov     [rbx], di
0x180023ba6  jmp     short loc_180023BAB
0x180023ba8  mov     [rbx], dil
0x180023bab  mov     al, 1
0x180023bad  mov     rbx, [rsp+28h+arg_0]
0x180023bb2  add     rsp, 20h
0x180023bb6  pop     rdi
0x180023bb7  retn
```
