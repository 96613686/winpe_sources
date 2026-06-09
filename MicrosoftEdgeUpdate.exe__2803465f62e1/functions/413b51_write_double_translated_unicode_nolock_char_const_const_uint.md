# write_double_translated_unicode_nolock(char const * const,uint)

- ea: `0x413b51`
- end: `0x413bb9`
- name: `?write_double_translated_unicode_nolock@@YA?AUwrite_result@?A0x17268360@@QBDI@Z`
- size: `104`
- prototype: `DWORD *__cdecl(DWORD *, unsigned int, int)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x414012`

## callees

- `0x413b51`
- `0x41468a`

## import_xrefs

- `KERNEL32!GetLastError` at `0x413baa`
- `KERNEL32!GetLastError` at `0x413baa`

## pseudocode

```c
DWORD *__cdecl write_double_translated_unicode_nolock(DWORD *a1, unsigned int a2, int a3)
{
  wchar_t *v3; // edi
  int v4; // ebx

  *a1 = 0;
  a1[1] = 0;
  a1[2] = 0;
  v3 = (wchar_t *)a2;
  if ( a2 < a2 + a3 )
  {
    while ( 1 )
    {
      v4 = *v3;
      if ( _putwch_nolock(*v3) != (_WORD)v4 )
        break;
      a1[1] += 2;
      if ( v4 == 10 )
      {
        if ( _putwch_nolock(0xDu) != 13 )
          break;
        ++a1[1];
        ++a1[2];
      }
      if ( (unsigned int)++v3 >= a2 + a3 )
        return a1;
    }
    *a1 = GetLastError();
  }
  return a1;
}

```

## disassembly

```asm
0x413b51  mov     edi, edi
0x413b53  push    ebp
0x413b54  mov     ebp, esp
0x413b56  push    ecx
0x413b57  push    ebx
0x413b58  push    esi
0x413b59  mov     esi, [ebp+arg_0]
0x413b5c  xor     eax, eax
0x413b5e  push    edi
0x413b5f  mov     edi, esi
0x413b61  stosd
0x413b62  stosd
0x413b63  stosd
0x413b64  mov     edi, [ebp+arg_4]
0x413b67  mov     eax, [ebp+arg_8]
0x413b6a  add     eax, edi
0x413b6c  mov     [ebp+var_4], eax
0x413b6f  cmp     edi, eax
0x413b71  jnb     short loc_413BB2
0x413b73  movzx   ebx, word ptr [edi]
0x413b76  push    ebx; Character
0x413b77  call    __putwch_nolock
0x413b7c  pop     ecx
0x413b7d  cmp     ax, bx
0x413b80  jnz     short loc_413BAA
0x413b82  add     dword ptr [esi+4], 2
0x413b86  cmp     ebx, 0Ah
0x413b89  jnz     short loc_413BA0
0x413b8b  push    0Dh
0x413b8d  pop     ebx
0x413b8e  push    ebx; Character
0x413b8f  call    __putwch_nolock
0x413b94  pop     ecx
0x413b95  cmp     ax, bx
0x413b98  jnz     short loc_413BAA
0x413b9a  inc     dword ptr [esi+4]
0x413b9d  inc     dword ptr [esi+8]
0x413ba0  add     edi, 2
0x413ba3  cmp     edi, [ebp+var_4]
0x413ba6  jb      short loc_413B73
0x413ba8  jmp     short loc_413BB2
0x413baa  call    ds:GetLastError
0x413bb0  mov     [esi], eax
0x413bb2  pop     edi
0x413bb3  mov     eax, esi
0x413bb5  pop     esi
0x413bb6  pop     ebx
0x413bb7  leave
0x413bb8  retn
```
