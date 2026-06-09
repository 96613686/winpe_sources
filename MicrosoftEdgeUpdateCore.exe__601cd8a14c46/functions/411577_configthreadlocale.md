# __configthreadlocale

- ea: `0x411577`
- end: `0x4115d9`
- name: `__configthreadlocale`
- size: `98`
- prototype: `int __cdecl(int Flag)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x40d4f0`

## callees

- `0x410369`
- `0x410443`
- `0x411577`
- `0x413a39`

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
    dword_43D758 = -1;
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
0x411577  mov     edi, edi
0x411579  push    ebp
0x41157a  mov     ebp, esp
0x41157c  push    esi
0x41157d  call    ___acrt_getptd
0x411582  mov     edx, [ebp+Flag]
0x411585  mov     esi, eax
0x411587  push    0
0x411589  pop     eax
0x41158a  mov     ecx, [esi+350h]
0x411590  test    cl, 2
0x411593  setz    al
0x411596  inc     eax
0x411597  cmp     edx, 0FFFFFFFFh
0x41159a  jz      short loc_4115CF
0x41159c  test    edx, edx
0x41159e  jz      short loc_4115D6
0x4115a0  cmp     edx, 1
0x4115a3  jz      short loc_4115C4
0x4115a5  cmp     edx, 2
0x4115a8  jz      short loc_4115BF
0x4115aa  call    __errno
0x4115af  mov     dword ptr [eax], 16h
0x4115b5  call    __invalid_parameter_noinfo
0x4115ba  or      eax, 0FFFFFFFFh
0x4115bd  jmp     short loc_4115D6
0x4115bf  and     ecx, 0FFFFFFFDh
0x4115c2  jmp     short loc_4115C7
0x4115c4  or      ecx, 2
0x4115c7  mov     [esi+350h], ecx
0x4115cd  jmp     short loc_4115D6
0x4115cf  or      dword_43D758, 0FFFFFFFFh
0x4115d6  pop     esi
0x4115d7  pop     ebp
0x4115d8  retn
```
