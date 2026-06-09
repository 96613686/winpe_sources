# UnLinkFromIFOBJList

- ea: `0x18000180c`
- end: `0x18000188b`
- name: `UnLinkFromIFOBJList`
- size: `127`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `3`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x1800014b0`
- `0x1800018a0`
- `0x180006e70`

## callees

- `0x18000180c`

## pseudocode

```c
__int64 __fastcall UnLinkFromIFOBJList(__int64 a1, _QWORD *a2)
{
  __int64 v2; // r8
  _QWORD *v3; // r8

  if ( a2[5] != a1 )
    return 5;
  if ( a2 == *(_QWORD **)(a1 + 8) )
  {
    v2 = *a2;
    if ( *a2 )
    {
      if ( *(_QWORD *)(v2 + 40) != a1 )
        v2 = 0;
      *(_QWORD *)(a1 + 8) = v2;
    }
    else
    {
      *(_QWORD *)(a1 + 8) = 0;
    }
  }
  if ( *a2 )
    *(_QWORD *)(*a2 + 48LL) = a2[6];
  v3 = (_QWORD *)a2[6];
  if ( v3 )
    *v3 = *a2;
  if ( (_QWORD *)IFObjList == a2 )
    IFObjList = *a2;
  a2[6] = 0;
  --cTotalEpEntries;
  *a2 = 0;
  a2[5] = 0;
  --*(_DWORD *)(a1 + 4);
  return 0;
}

```

## disassembly

```asm
0x18000180c  cmp     [rdx+28h], rcx
0x180001810  jnz     short loc_180001879
0x180001812  xor     r9d, r9d
0x180001815  cmp     rdx, [rcx+8]
0x180001819  jnz     short loc_18000182F
0x18000181b  mov     r8, [rdx]
0x18000181e  test    r8, r8
0x180001821  jz      short loc_180001873
0x180001823  cmp     [r8+28h], rcx
0x180001827  cmovnz  r8, r9
0x18000182b  mov     [rcx+8], r8
0x18000182f  mov     r8, [rdx]
0x180001832  test    r8, r8
0x180001835  jz      short loc_18000183F
0x180001837  mov     rax, [rdx+30h]
0x18000183b  mov     [r8+30h], rax
0x18000183f  mov     r8, [rdx+30h]
0x180001843  test    r8, r8
0x180001846  jnz     short loc_18000186B
0x180001848  cmp     cs:IFObjList, rdx
0x18000184f  jz      short loc_18000187F
0x180001851  or      eax, 0FFFFFFFFh
0x180001854  mov     [rdx+30h], r9
0x180001858  add     cs:cTotalEpEntries, eax
0x18000185e  mov     [rdx], r9
0x180001861  mov     [rdx+28h], r9
0x180001865  add     [rcx+4], eax
0x180001868  xor     eax, eax
0x18000186a  retn
0x18000186b  mov     rax, [rdx]
0x18000186e  mov     [r8], rax
0x180001871  jmp     short loc_180001848
0x180001873  mov     [rcx+8], r9
0x180001877  jmp     short loc_18000182F
0x180001879  mov     eax, 5
0x18000187e  retn
0x18000187f  mov     rax, [rdx]
0x180001882  mov     cs:IFObjList, rax
0x180001889  jmp     short loc_180001851
```
