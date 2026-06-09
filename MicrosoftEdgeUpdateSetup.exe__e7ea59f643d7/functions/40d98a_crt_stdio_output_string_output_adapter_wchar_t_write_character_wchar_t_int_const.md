# __crt_stdio_output::string_output_adapter<wchar_t>::write_character(wchar_t,int * const)

- ea: `0x40d98a`
- end: `0x40d9cf`
- name: `?write_character@?$string_output_adapter@_W@__crt_stdio_output@@QBE_N_WQAH@Z`
- size: `69`
- prototype: `char __thiscall(int *this, __int16, _DWORD *)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x40c9a3`
- `0x40cf9b`
- `0x40d9cf`

## callees

- `0x40d98a`

## pseudocode

```c
char __thiscall __crt_stdio_output::string_output_adapter<wchar_t>::write_character(int *this, __int16 a2, _DWORD *a3)
{
  int v4; // ecx

  v4 = *this;
  if ( *(_DWORD *)(v4 + 8) == *(_DWORD *)(v4 + 4) )
  {
    if ( *(_BYTE *)(v4 + 12) )
      ++*a3;
    else
      *a3 = -1;
    return *(_BYTE *)(*this + 12);
  }
  else
  {
    ++*a3;
    ++*(_DWORD *)(*this + 8);
    **(_WORD **)*this = a2;
    *(_DWORD *)*this += 2;
    return 1;
  }
}

```

## disassembly

```asm
0x40d98a  mov     edi, edi
0x40d98c  push    ebp
0x40d98d  mov     ebp, esp
0x40d98f  mov     edx, ecx
0x40d991  mov     ecx, [edx]
0x40d993  mov     eax, [ecx+8]
0x40d996  cmp     eax, [ecx+4]
0x40d999  mov     eax, [ebp+arg_4]
0x40d99c  jnz     short loc_40D9B2
0x40d99e  cmp     byte ptr [ecx+0Ch], 0
0x40d9a2  jz      short loc_40D9A8
0x40d9a4  inc     dword ptr [eax]
0x40d9a6  jmp     short loc_40D9AB
0x40d9a8  or      dword ptr [eax], 0FFFFFFFFh
0x40d9ab  mov     eax, [edx]
0x40d9ad  mov     al, [eax+0Ch]
0x40d9b0  jmp     short loc_40D9CB
0x40d9b2  inc     dword ptr [eax]
0x40d9b4  mov     eax, [edx]
0x40d9b6  inc     dword ptr [eax+8]
0x40d9b9  mov     eax, [edx]
0x40d9bb  mov     ecx, [eax]
0x40d9bd  mov     ax, [ebp+arg_0]
0x40d9c1  mov     [ecx], ax
0x40d9c4  mov     eax, [edx]
0x40d9c6  add     dword ptr [eax], 2
0x40d9c9  mov     al, 1
0x40d9cb  pop     ebp
0x40d9cc  retn    8
```
