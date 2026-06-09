# write_double_translated_unicode_nolock(char const * const,uint)

- ea: `0x1001e0c4`
- end: `0x1001e12e`
- name: `?write_double_translated_unicode_nolock@@YA?AUwrite_result@?A0x17268360@@QBDI@Z`
- size: `106`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1001e585`

## callees

- `0x1001e0c4`
- `0x1001edbd`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1001e11d`
- `KERNEL32!GetLastError` at `0x1001e11d`

## pseudocode

```c
DWORD *__cdecl write_double_translated_unicode_nolock(DWORD *a1, unsigned int a2, int a3)
{
  __int16 *v3; // edi
  int v4; // ebx

  *a1 = 0;
  a1[1] = 0;
  a1[2] = 0;
  v3 = (__int16 *)a2;
  if ( a2 < a2 + a3 )
  {
    while ( 1 )
    {
      v4 = (unsigned __int16)*v3;
      if ( (unsigned __int16)sub_1001EDBD(*v3) != (_WORD)v4 )
        break;
      a1[1] += 2;
      if ( v4 == 10 )
      {
        if ( (unsigned __int16)sub_1001EDBD(13) != 13 )
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
0x1001e0c4  mov     edi, edi
0x1001e0c6  push    ebp
0x1001e0c7  mov     ebp, esp
0x1001e0c9  push    ecx
0x1001e0ca  push    ebx
0x1001e0cb  push    esi
0x1001e0cc  mov     esi, [ebp+arg_0]
0x1001e0cf  xor     eax, eax
0x1001e0d1  push    edi
0x1001e0d2  mov     edi, esi
0x1001e0d4  stosd
0x1001e0d5  stosd
0x1001e0d6  stosd
0x1001e0d7  mov     edi, [ebp+arg_4]
0x1001e0da  mov     eax, [ebp+arg_8]
0x1001e0dd  add     eax, edi
0x1001e0df  mov     [ebp+var_4], eax
0x1001e0e2  cmp     edi, eax
0x1001e0e4  jnb     short loc_1001E125
0x1001e0e6  movzx   ebx, word ptr [edi]
0x1001e0e9  push    ebx; Buffer
0x1001e0ea  call    sub_1001EDBD
0x1001e0ef  pop     ecx
0x1001e0f0  cmp     ax, bx
0x1001e0f3  jnz     short loc_1001E11D
0x1001e0f5  add     dword ptr [esi+4], 2
0x1001e0f9  cmp     ebx, 0Ah
0x1001e0fc  jnz     short loc_1001E113
0x1001e0fe  push    0Dh
0x1001e100  pop     ebx
0x1001e101  push    ebx; Buffer
0x1001e102  call    sub_1001EDBD
0x1001e107  pop     ecx
0x1001e108  cmp     ax, bx
0x1001e10b  jnz     short loc_1001E11D
0x1001e10d  inc     dword ptr [esi+4]
0x1001e110  inc     dword ptr [esi+8]
0x1001e113  add     edi, 2
0x1001e116  cmp     edi, [ebp+var_4]
0x1001e119  jb      short loc_1001E0E6
0x1001e11b  jmp     short loc_1001E125
0x1001e11d  call    ds:GetLastError
0x1001e123  mov     [esi], eax
0x1001e125  pop     edi
0x1001e126  mov     eax, esi
0x1001e128  pop     esi
0x1001e129  pop     ebx
0x1001e12a  mov     esp, ebp
0x1001e12c  pop     ebp
0x1001e12d  retn
```
