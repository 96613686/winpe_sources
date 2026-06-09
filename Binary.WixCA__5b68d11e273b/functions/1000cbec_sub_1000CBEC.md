# sub_1000CBEC

- ea: `0x1000cbec`
- end: `0x1000cc46`
- name: `sub_1000CBEC`
- size: `90`
- prototype: `int __stdcall(int, OLECHAR *psz, int)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x1000c9b7`
- `0x1000ca52`

## callees

- `0x1000ad15`
- `0x1000cbec`

## import_xrefs

- `OLEAUT32!SysAllocString` at `0x1000cc01`
- `OLEAUT32!SysAllocString` at `0x1000cc01`
- `OLEAUT32!SysFreeString` at `0x1000cc31`
- `OLEAUT32!SysFreeString` at `0x1000cc31`

## string_xrefs

- `0x1000cc15`: `d:\a\_work\1\s\src\libs\dutil\xmlutil.cpp`

## pseudocode

```c
int __stdcall sub_1000CBEC(int a1, OLECHAR *psz, int a3)
{
  OLECHAR *v3; // edi
  int v4; // esi

  if ( !a3 || !a1 )
    return -2147024809;
  v3 = SysAllocString(psz);
  if ( v3 )
  {
    v4 = (*(int (__stdcall **)(int, OLECHAR *, int))(*(_DWORD *)a1 + 188))(a1, v3, a3);
    SysFreeString(v3);
  }
  else
  {
    v4 = -2147024882;
    nullsub_1("d:\\a\\_work\\1\\s\\src\\libs\\dutil\\xmlutil.cpp", 102, -2147024882);
  }
  return v4;
}

```

## disassembly

```asm
0x1000cbec  push    ebp
0x1000cbed  mov     ebp, esp
0x1000cbef  cmp     [ebp+arg_8], 0
0x1000cbf3  push    esi
0x1000cbf4  jz      short loc_1000CC3C
0x1000cbf6  mov     esi, [ebp+arg_0]
0x1000cbf9  test    esi, esi
0x1000cbfb  jz      short loc_1000CC3C
0x1000cbfd  push    edi
0x1000cbfe  push    [ebp+psz]; psz
0x1000cc01  call    ds:SysAllocString
0x1000cc07  mov     edi, eax
0x1000cc09  test    edi, edi
0x1000cc0b  jnz     short loc_1000CC21
0x1000cc0d  mov     esi, 8007000Eh
0x1000cc12  push    esi
0x1000cc13  push    66h ; 'f'
0x1000cc15  push    offset aDAWork1SSrcLib_7; "d:\\a\\_work\\1\\s\\src\\libs\\dutil\\x"...
0x1000cc1a  call    nullsub_1
0x1000cc1f  jmp     short loc_1000CC37
0x1000cc21  push    [ebp+arg_8]
0x1000cc24  mov     eax, [esi]
0x1000cc26  push    edi
0x1000cc27  push    esi
0x1000cc28  call    dword ptr [eax+0BCh]
0x1000cc2e  mov     esi, eax
0x1000cc30  push    edi; bstrString
0x1000cc31  call    ds:SysFreeString
0x1000cc37  mov     eax, esi
0x1000cc39  pop     edi
0x1000cc3a  jmp     short loc_1000CC41
0x1000cc3c  mov     eax, 80070057h
0x1000cc41  pop     esi
0x1000cc42  pop     ebp
0x1000cc43  retn    0Ch
```
