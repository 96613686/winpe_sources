# __crt_stdio_output::string_output_adapter<wchar_t>::write_character(wchar_t,int * const)

- ea: `0x412e0a`
- end: `0x412e4f`
- name: `?write_character@?$string_output_adapter@_W@__crt_stdio_output@@QBE_N_WQAH@Z`
- size: `69`
- prototype: `char __thiscall(int *this, __int16, _DWORD *)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x411e36`
- `0x41241b`
- `0x412e4f`

## callees

- `0x412e0a`

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
0x412e0a  mov     edi, edi
0x412e0c  push    ebp
0x412e0d  mov     ebp, esp
0x412e0f  mov     edx, ecx
0x412e11  mov     ecx, [edx]
0x412e13  mov     eax, [ecx+8]
0x412e16  cmp     eax, [ecx+4]
0x412e19  mov     eax, [ebp+arg_4]
0x412e1c  jnz     short loc_412E32
0x412e1e  cmp     byte ptr [ecx+0Ch], 0
0x412e22  jz      short loc_412E28
0x412e24  inc     dword ptr [eax]
0x412e26  jmp     short loc_412E2B
0x412e28  or      dword ptr [eax], 0FFFFFFFFh
0x412e2b  mov     eax, [edx]
0x412e2d  mov     al, [eax+0Ch]
0x412e30  jmp     short loc_412E4B
0x412e32  inc     dword ptr [eax]
0x412e34  mov     eax, [edx]
0x412e36  inc     dword ptr [eax+8]
0x412e39  mov     eax, [edx]
0x412e3b  mov     ecx, [eax]
0x412e3d  mov     ax, [ebp+arg_0]
0x412e41  mov     [ecx], ax
0x412e44  mov     eax, [edx]
0x412e46  add     dword ptr [eax], 2
0x412e49  mov     al, 1
0x412e4b  pop     ebp
0x412e4c  retn    8
```
