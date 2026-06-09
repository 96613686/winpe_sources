# EnLinkOnIFOBJList

- ea: `0x180002610`
- end: `0x1800026aa`
- name: `EnLinkOnIFOBJList`
- size: `154`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800018a0`

## callees

- `0x180002610`

## pseudocode

```c
__int64 __fastcall EnLinkOnIFOBJList(__int64 a1, _QWORD *a2)
{
  __int64 v3; // rax
  __int64 v4; // rax
  _QWORD *v5; // rdx
  _QWORD *v6; // rax
  __int64 result; // rax
  _QWORD *v8; // rax

  *a2 = *(_QWORD *)(a1 + 8);
  v3 = *(_QWORD *)(a1 + 8);
  if ( v3 )
  {
    a2[6] = *(_QWORD *)(v3 + 48);
    *(_QWORD *)(*(_QWORD *)(a1 + 8) + 48LL) = a2;
    v8 = (_QWORD *)a2[6];
    if ( v8 )
      *v8 = a2;
  }
  else
  {
    a2[6] = 0;
  }
  v4 = *(_QWORD *)(a1 + 8);
  if ( v4 )
  {
    if ( v4 != IFObjList )
      goto LABEL_8;
LABEL_10:
    IFObjList = (__int64)a2;
    goto LABEL_8;
  }
  v5 = (_QWORD *)IFObjList;
  if ( !IFObjList )
    goto LABEL_10;
  v6 = *(_QWORD **)IFObjList;
  if ( *(_QWORD *)IFObjList )
  {
    do
    {
      v5 = v6;
      v6 = (_QWORD *)*v6;
    }
    while ( v6 );
  }
  *v5 = a2;
  a2[6] = v5;
LABEL_8:
  ++cTotalEpEntries;
  result = 0;
  *(_QWORD *)(a1 + 8) = a2;
  a2[5] = a1;
  ++*(_DWORD *)(a1 + 4);
  return result;
}

```

## disassembly

```asm
0x180002610  mov     rax, [rcx+8]
0x180002614  mov     r9, rdx
0x180002617  mov     [rdx], rax
0x18000261a  mov     r8, rcx
0x18000261d  mov     rax, [rcx+8]
0x180002621  test    rax, rax
0x180002624  jnz     short loc_18000268C
0x180002626  mov     [rdx+30h], rax
0x18000262a  mov     rax, [rcx+8]
0x18000262e  test    rax, rax
0x180002631  jnz     short loc_18000267A
0x180002633  mov     rdx, cs:IFObjList
0x18000263a  test    rdx, rdx
0x18000263d  jz      short loc_180002683
0x18000263f  mov     rax, [rdx]
0x180002642  test    rax, rax
0x180002645  jz      short loc_18000265E
0x180002647  nop     word ptr [rax+rax+00000000h]
0x180002650  mov     rcx, [rax]
0x180002653  mov     rdx, rax
0x180002656  mov     rax, rcx
0x180002659  test    rcx, rcx
0x18000265c  jnz     short loc_180002650
0x18000265e  mov     [rdx], r9
0x180002661  mov     [r9+30h], rdx
0x180002665  inc     cs:cTotalEpEntries
0x18000266b  xor     eax, eax
0x18000266d  mov     [r8+8], r9
0x180002671  mov     [r9+28h], r8
0x180002675  inc     dword ptr [r8+4]
0x180002679  retn
0x18000267a  cmp     rax, cs:IFObjList
0x180002681  jnz     short loc_180002665
0x180002683  mov     cs:IFObjList, r9
0x18000268a  jmp     short loc_180002665
0x18000268c  mov     rax, [rax+30h]
0x180002690  mov     [rdx+30h], rax
0x180002694  mov     rax, [rcx+8]
0x180002698  mov     [rax+30h], r9
0x18000269c  mov     rax, [rdx+30h]
0x1800026a0  test    rax, rax
0x1800026a3  jz      short loc_18000262A
0x1800026a5  mov     [rax], r9
0x1800026a8  jmp     short loc_18000262A
```
