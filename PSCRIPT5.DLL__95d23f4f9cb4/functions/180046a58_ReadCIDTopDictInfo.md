# ReadCIDTopDictInfo

- ea: `0x180046a58`
- end: `0x180046b07`
- name: `ReadCIDTopDictInfo`
- size: `175`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `loader_planting, installer_update`

## callers

- `0x1800487e0`

## callees

- `0x180045a70`
- `0x180046318`
- `0x1800466cc`
- `0x180046a58`
- `0x180046c1c`
- `0x180048b5c`
- `0x18004e048`
- `0x18004e324`
- `0x18004e360`
- `0x180052154`

## pseudocode

```c
__int64 __fastcall ReadCIDTopDictInfo(__int64 a1)
{
  if ( !*(_DWORD *)(a1 + 664) )
    XCF_FatalErrorHandler(a1, 26);
  ReadTableInfo(a1, *(unsigned int *)(a1 + 668), a1 + 7908);
  if ( *(_DWORD *)(a1 + 7816) != 1 )
    return 25;
  XCF_ReadBlock(a1, *(unsigned int *)(a1 + 7820), 3);
  *(_WORD *)(a1 + 14952) = XCF_Read2(a1);
  XCF_Read1(a1);
  if ( *(_WORD *)(a1 + 14952) > 0x100u )
    XCF_FatalErrorHandler(a1, 25);
  ProcessCharset(a1);
  ProcessFDIndex(a1);
  AssignDictionaryDefaults(a1);
  XC_SetUpStandardSubrs(a1);
  return 0;
}

```

## disassembly

```asm
0x180046a58  push    rbx
0x180046a5a  sub     rsp, 20h
0x180046a5e  cmp     dword ptr [rcx+298h], 0
0x180046a65  mov     rbx, rcx
0x180046a68  jz      loc_180046AF1
0x180046a6e  mov     edx, [rcx+29Ch]
0x180046a74  lea     r8, [rcx+1EE4h]
0x180046a7b  call    ReadTableInfo
0x180046a80  cmp     dword ptr [rbx+1E88h], 1
0x180046a87  jz      short loc_180046A94
0x180046a89  mov     eax, 19h
0x180046a8e  add     rsp, 20h
0x180046a92  pop     rbx
0x180046a93  retn
0x180046a94  mov     edx, [rbx+1E8Ch]
0x180046a9a  mov     r8d, 3
0x180046aa0  mov     rcx, rbx
0x180046aa3  call    XCF_ReadBlock
0x180046aa8  mov     rcx, rbx
0x180046aab  call    XCF_Read2
0x180046ab0  mov     rcx, rbx
0x180046ab3  mov     [rbx+3A68h], ax
0x180046aba  call    XCF_Read1
0x180046abf  mov     eax, 100h
0x180046ac4  mov     rcx, rbx
0x180046ac7  cmp     [rbx+3A68h], ax
0x180046ace  ja      short loc_180046AFC
0x180046ad0  call    ProcessCharset
0x180046ad5  mov     rcx, rbx
0x180046ad8  call    ProcessFDIndex
0x180046add  mov     rcx, rbx
0x180046ae0  call    AssignDictionaryDefaults
0x180046ae5  mov     rcx, rbx
0x180046ae8  call    XC_SetUpStandardSubrs
0x180046aed  xor     eax, eax
0x180046aef  jmp     short loc_180046A8E
0x180046af1  mov     edx, 1Ah
0x180046af6  call    XCF_FatalErrorHandler
0x180046afc  mov     edx, 19h
0x180046b01  call    XCF_FatalErrorHandler
```
