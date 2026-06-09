# CPerformanceStructureManipulator<_WMI_PERFORMANCE,_WMI_PERFORMANCE,_WMI_PERF_NAMESPACE>::CreateStructure(ulong)

- ea: `0x14000b070`
- end: `0x14000b0c2`
- name: `?CreateStructure@?$CPerformanceStructureManipulator@U_WMI_PERFORMANCE@@U1@U_WMI_PERF_NAMESPACE@@@@CAPEAU_WMI_PERFORMANCE@@K@Z`
- size: `82`
- prototype: `_DWORD *()`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x14000b2e4`

## callees

- `0x140001a6f`
- `0x14000b070`

## import_xrefs

- `msvcrt!malloc` at `0x14000b081`
- `msvcrt!malloc` at `0x14000b081`

## pseudocode

```c
_DWORD *CPerformanceStructureManipulator<_WMI_PERFORMANCE,_WMI_PERFORMANCE,_WMI_PERF_NAMESPACE>::CreateStructure()
{
  _DWORD *v0; // rax
  _DWORD *v1; // rbx

  v0 = malloc(0x10u);
  v1 = v0;
  if ( v0 )
  {
    memset_0(v0, 0, 0x10u);
    v1[3] = 16;
    *v1 = 16;
    v1[2] = 0;
  }
  return v1;
}

```

## disassembly

```asm
0x14000b070  mov     [rsp+arg_0], rbx
0x14000b075  push    rdi
0x14000b076  sub     rsp, 20h
0x14000b07a  mov     edi, 10h
0x14000b07f  mov     ecx, edi; Size
0x14000b081  call    cs:__imp_malloc
0x14000b087  mov     rbx, rax
0x14000b08a  mov     [rsp+28h+arg_8], rax
0x14000b08f  test    rax, rax
0x14000b092  jz      short loc_14000B0AD
0x14000b094  mov     r8d, edi; Size
0x14000b097  xor     edx, edx; Val
0x14000b099  mov     rcx, rax; void *
0x14000b09c  call    memset_0
0x14000b0a1  mov     [rbx+0Ch], edi
0x14000b0a4  mov     [rbx], edi
0x14000b0a6  mov     dword ptr [rbx+8], 0
0x14000b0ad  jmp     short loc_14000B0B4
0x14000b0af  mov     rbx, [rsp+28h+arg_8]
0x14000b0b4  mov     rax, rbx
0x14000b0b7  mov     rbx, [rsp+28h+arg_0]
0x14000b0bc  add     rsp, 20h
0x14000b0c0  pop     rdi
0x14000b0c1  retn
```
