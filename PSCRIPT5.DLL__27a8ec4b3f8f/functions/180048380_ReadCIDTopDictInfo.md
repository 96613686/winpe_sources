# ReadCIDTopDictInfo

- ea: `0x180048380`
- end: `0x180048430`
- name: `ReadCIDTopDictInfo`
- size: `176`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `10`
- tags: `loader_planting, installer_update`

## callers

- `0x18004a050`

## callees

- `0x180047390`
- `0x180047c38`
- `0x180047ff4`
- `0x180048380`
- `0x180048544`
- `0x18004a3cc`
- `0x18004f8e4`
- `0x18004fbc4`
- `0x18004fc04`
- `0x180053ad4`

## pseudocode

```c
__int64 __fastcall ReadCIDTopDictInfo(__int64 a1)
{
  if ( !*(_DWORD *)(a1 + 664) )
    XCF_FatalErrorHandler((_JBTYPE *)a1, 26);
  ReadTableInfo(a1, *(unsigned int *)(a1 + 668), (_DWORD *)(a1 + 7908));
  if ( *(_DWORD *)(a1 + 7816) != 1 )
    return 25;
  XCF_ReadBlock(a1, *(unsigned int *)(a1 + 7820), 3);
  *(_WORD *)(a1 + 14952) = XCF_Read2((_JBTYPE *)a1);
  XCF_Read1((_JBTYPE *)a1);
  if ( *(_WORD *)(a1 + 14952) > 0x100u )
    XCF_FatalErrorHandler((_JBTYPE *)a1, 25);
  ProcessCharset(a1);
  ProcessFDIndex(a1);
  AssignDictionaryDefaults(a1);
  XC_SetUpStandardSubrs(a1);
  return 0;
}

```

## disassembly

```asm
0x180048380  push    rbx
0x180048382  sub     rsp, 20h
0x180048386  cmp     dword ptr [rcx+298h], 0
0x18004838d  mov     rbx, rcx
0x180048390  jz      loc_18004841A
0x180048396  mov     edx, [rcx+29Ch]
0x18004839c  lea     r8, [rcx+1EE4h]
0x1800483a3  call    ReadTableInfo
0x1800483a8  cmp     dword ptr [rbx+1E88h], 1
0x1800483af  jz      short loc_1800483BD
0x1800483b1  mov     eax, 19h
0x1800483b6  add     rsp, 20h
0x1800483ba  pop     rbx
0x1800483bb  retn
0x1800483bd  mov     edx, [rbx+1E8Ch]
0x1800483c3  mov     r8d, 3
0x1800483c9  mov     rcx, rbx
0x1800483cc  call    XCF_ReadBlock
0x1800483d1  mov     rcx, rbx
0x1800483d4  call    XCF_Read2
0x1800483d9  mov     rcx, rbx
0x1800483dc  mov     [rbx+3A68h], ax
0x1800483e3  call    XCF_Read1
0x1800483e8  mov     eax, 100h
0x1800483ed  mov     rcx, rbx
0x1800483f0  cmp     [rbx+3A68h], ax
0x1800483f7  ja      short loc_180048425
0x1800483f9  call    ProcessCharset
0x1800483fe  mov     rcx, rbx
0x180048401  call    ProcessFDIndex
0x180048406  mov     rcx, rbx
0x180048409  call    AssignDictionaryDefaults
0x18004840e  mov     rcx, rbx
0x180048411  call    XC_SetUpStandardSubrs
0x180048416  xor     eax, eax
0x180048418  jmp     short loc_1800483B6
0x18004841a  mov     edx, 1Ah
0x18004841f  call    XCF_FatalErrorHandler
0x180048425  mov     edx, 19h
0x18004842a  call    XCF_FatalErrorHandler
```
