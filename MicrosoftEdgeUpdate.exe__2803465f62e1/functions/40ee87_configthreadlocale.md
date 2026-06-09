# __configthreadlocale

- ea: `0x40ee87`
- end: `0x40eee9`
- name: `__configthreadlocale`
- size: `98`
- prototype: `int __cdecl(int Flag)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x40b630`

## callees

- `0x40de54`
- `0x40ee87`
- `0x40f9a9`
- `0x40ffa9`

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
    dword_4176A0 = -1;
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
0x40ee87  mov     edi, edi
0x40ee89  push    ebp
0x40ee8a  mov     ebp, esp
0x40ee8c  push    esi
0x40ee8d  call    ___acrt_getptd
0x40ee92  mov     edx, [ebp+Flag]
0x40ee95  mov     esi, eax
0x40ee97  push    0
0x40ee99  pop     eax
0x40ee9a  mov     ecx, [esi+350h]
0x40eea0  test    cl, 2
0x40eea3  setz    al
0x40eea6  inc     eax
0x40eea7  cmp     edx, 0FFFFFFFFh
0x40eeaa  jz      short loc_40EEDF
0x40eeac  test    edx, edx
0x40eeae  jz      short loc_40EEE6
0x40eeb0  cmp     edx, 1
0x40eeb3  jz      short loc_40EED4
0x40eeb5  cmp     edx, 2
0x40eeb8  jz      short loc_40EECF
0x40eeba  call    __errno
0x40eebf  mov     dword ptr [eax], 16h
0x40eec5  call    __invalid_parameter_noinfo
0x40eeca  or      eax, 0FFFFFFFFh
0x40eecd  jmp     short loc_40EEE6
0x40eecf  and     ecx, 0FFFFFFFDh
0x40eed2  jmp     short loc_40EED7
0x40eed4  or      ecx, 2
0x40eed7  mov     [esi+350h], ecx
0x40eedd  jmp     short loc_40EEE6
0x40eedf  or      dword_4176A0, 0FFFFFFFFh
0x40eee6  pop     esi
0x40eee7  pop     ebp
0x40eee8  retn
```
