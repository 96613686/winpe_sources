# GetCellByDebugCellID(void *,tagDebugCellID)

- ea: `0x1800095b0`
- end: `0x180009606`
- name: `?GetCellByDebugCellID@@YAPEAUtagDebugCellUnion@@PEAXUtagDebugCellID@@@Z`
- size: `86`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180007600`
- `0x1800096c0`

## callees

- `0x1800095b0`

## pseudocode

```c
__int64 __fastcall GetCellByDebugCellID(__int64 *a1, int a2)
{
  __int64 v2; // r8
  __int64 v3; // r9
  __int64 v4; // r8
  __int64 v5; // rcx

  v2 = *a1;
  v3 = 0;
  while ( *(_DWORD *)(v2 + 28) != (unsigned __int16)a2 )
  {
    v4 = *(_QWORD *)(v2 + 40);
    if ( !v4 )
      return v3;
    v2 = v4 - 40;
  }
  if ( HIWORD(a2) > 1u )
  {
    v5 = *(_QWORD *)(v2 + 32);
    if ( v5 + 32 * (unsigned __int64)HIWORD(a2) <= (unsigned __int64)(unsigned int)(*(_DWORD *)(v2 + 24)
                                                                                  * dword_180013B9C)
                                                 + v5
                                                 - 32 )
      return v5 + 32LL * HIWORD(a2);
  }
  return v3;
}

```

## disassembly

```asm
0x1800095b0  mov     r8, [rcx]
0x1800095b3  xor     r9d, r9d
0x1800095b6  mov     [rsp+arg_8], edx
0x1800095ba  movzx   eax, dx
0x1800095bd  cmp     [r8+1Ch], eax
0x1800095c1  jz      short loc_1800095D2
0x1800095c3  mov     r8, [r8+28h]
0x1800095c7  test    r8, r8
0x1800095ca  jz      short loc_180009602
0x1800095cc  add     r8, 0FFFFFFFFFFFFFFD8h
0x1800095d0  jmp     short loc_1800095BA
0x1800095d2  movzx   eax, word ptr [rsp+arg_8+2]
0x1800095d7  cmp     eax, 1
0x1800095da  jbe     short loc_180009602
0x1800095dc  mov     rcx, [r8+20h]
0x1800095e0  mov     edx, eax
0x1800095e2  mov     eax, cs:dword_180013B9C
0x1800095e8  imul    eax, [r8+18h]
0x1800095ed  shl     rdx, 5
0x1800095f1  add     rdx, rcx
0x1800095f4  add     rcx, 0FFFFFFFFFFFFFFE0h
0x1800095f8  add     rcx, rax
0x1800095fb  cmp     rdx, rcx
0x1800095fe  cmovbe  r9, rdx
0x180009602  mov     rax, r9
0x180009605  retn
```
