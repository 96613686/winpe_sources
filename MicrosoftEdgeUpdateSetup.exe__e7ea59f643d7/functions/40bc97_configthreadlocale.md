# __configthreadlocale

- ea: `0x40bc97`
- end: `0x40bcf9`
- name: `__configthreadlocale`
- size: `98`
- prototype: `int __cdecl(int Flag)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x4081b0`

## callees

- `0x40bc97`
- `0x40e819`
- `0x40ec26`
- `0x40ece3`

## pseudocode

```c
int __cdecl _configthreadlocale(int Flag)
{
  _DWORD *v1; // esi
  int v2; // ecx
  int result; // eax
  unsigned int v4; // ecx

  v1 = __acrt_getptd();
  v2 = v1[212];
  result = ((v2 & 2) == 0) + 1;
  if ( Flag == -1 )
  {
    dword_4266A0 = -1;
  }
  else
  {
    switch ( Flag )
    {
      case 0:
        return result;
      case 1:
        v4 = v2 | 2;
        break;
      case 2:
        v4 = v2 & 0xFFFFFFFD;
        break;
      default:
        *_errno() = 22;
        _invalid_parameter_noinfo();
        return -1;
    }
    v1[212] = v4;
  }
  return result;
}

```

## disassembly

```asm
0x40bc97  mov     edi, edi
0x40bc99  push    ebp
0x40bc9a  mov     ebp, esp
0x40bc9c  push    esi
0x40bc9d  call    ___acrt_getptd
0x40bca2  mov     edx, [ebp+Flag]
0x40bca5  mov     esi, eax
0x40bca7  push    0
0x40bca9  pop     eax
0x40bcaa  mov     ecx, [esi+350h]
0x40bcb0  test    cl, 2
0x40bcb3  setz    al
0x40bcb6  inc     eax
0x40bcb7  cmp     edx, 0FFFFFFFFh
0x40bcba  jz      short loc_40BCEF
0x40bcbc  test    edx, edx
0x40bcbe  jz      short loc_40BCF6
0x40bcc0  cmp     edx, 1
0x40bcc3  jz      short loc_40BCE4
0x40bcc5  cmp     edx, 2
0x40bcc8  jz      short loc_40BCDF
0x40bcca  call    __errno
0x40bccf  mov     dword ptr [eax], 16h
0x40bcd5  call    __invalid_parameter_noinfo
0x40bcda  or      eax, 0FFFFFFFFh
0x40bcdd  jmp     short loc_40BCF6
0x40bcdf  and     ecx, 0FFFFFFFDh
0x40bce2  jmp     short loc_40BCE7
0x40bce4  or      ecx, 2
0x40bce7  mov     [esi+350h], ecx
0x40bced  jmp     short loc_40BCF6
0x40bcef  or      dword_4266A0, 0FFFFFFFFh
0x40bcf6  pop     esi
0x40bcf7  pop     ebp
0x40bcf8  retn
```
