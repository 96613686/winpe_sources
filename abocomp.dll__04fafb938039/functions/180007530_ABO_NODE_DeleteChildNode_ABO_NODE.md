# ABO_NODE::DeleteChildNode(ABO_NODE *)

- ea: `0x180007530`
- end: `0x1800075c4`
- name: `?DeleteChildNode@ABO_NODE@@QEAAJPEAV1@@Z`
- size: `148`
- prototype: `__int64 __fastcall(ABO_NODE *__hidden this, struct ABO_NODE *)`
- caller_count: `4`
- callee_count: `5`
- tags: ``

## callers

- `0x180007724`
- `0x18000c560`
- `0x18000ce90`
- `0x18000f110`

## callees

- `0x18000473c`
- `0x180005e94`
- `0x180007530`
- `0x180007670`
- `0x1800076d4`

## import_xrefs

- `iisutil!?DeleteRecord@CLKRHashTable@@QEAA?AW4LK_RETCODE@@PEBX@Z` at `0x180007596`
- `iisutil!?DeleteRecord@CLKRHashTable@@QEAA?AW4LK_RETCODE@@PEBX@Z` at `0x180007596`

## pseudocode

```c
__int64 __fastcall ABO_NODE::DeleteChildNode(ABO_NODE *this, struct ABO_NODE *a2)
{
  int v3; // ebx
  ARRAY_LIST *v4; // r14
  __int64 v5; // rsi
  __int64 v6; // rcx
  struct ABO_NODE *v7; // rdi
  __int64 v8; // rcx

  if ( a2 )
  {
    if ( !*((_DWORD *)this + 10) )
      return (unsigned int)-2147024893;
    v4 = (ABO_NODE *)((char *)this + 32);
    v5 = 0;
    v6 = *((_QWORD *)this + 4);
    do
    {
      v7 = *(struct ABO_NODE **)(v6 + 8 * v5);
      if ( v7 == a2 )
        break;
      v7 = 0;
      v5 = (unsigned int)(v5 + 1);
    }
    while ( (unsigned int)v5 < *((_DWORD *)this + 10) );
    if ( v7 )
    {
      ABO_NODE::ReferenceAboNode(v7);
      v3 = ABO_NODE::DeleteNode(v7);
      if ( v3 >= 0 )
      {
        v8 = *((_QWORD *)this + 6);
        if ( v8 )
          CLKRHashTable::DeleteRecord(v8, *(_QWORD *)(*(_QWORD *)v4 + 8 * v5));
        v3 = ARRAY_LIST::DeleteEntry(v4, v5);
      }
      ABO_NODE::DereferenceAboNode(v7);
    }
    else
    {
      return (unsigned int)-2147024893;
    }
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180007530  push    rbx
0x180007532  push    rbp
0x180007533  push    rsi
0x180007534  push    rdi
0x180007535  push    r14
0x180007537  sub     rsp, 20h
0x18000753b  mov     rbp, rcx
0x18000753e  test    rdx, rdx
0x180007541  jnz     short loc_18000754A
0x180007543  mov     ebx, 80070057h
0x180007548  jmp     short loc_1800075B7
0x18000754a  cmp     dword ptr [rcx+28h], 0
0x18000754e  jbe     short loc_1800075B2
0x180007550  lea     r14, [rcx+20h]
0x180007554  xor     esi, esi
0x180007556  mov     rcx, [r14]
0x180007559  mov     rdi, [rcx+rsi*8]
0x18000755d  cmp     rdi, rdx
0x180007560  jz      short loc_18000756B
0x180007562  xor     edi, edi
0x180007564  inc     esi
0x180007566  cmp     esi, [rbp+28h]
0x180007569  jb      short loc_180007559
0x18000756b  test    rdi, rdi
0x18000756e  jz      short loc_1800075B2
0x180007570  mov     rcx, rdi; this
0x180007573  call    ?ReferenceAboNode@ABO_NODE@@QEAAXXZ; ABO_NODE::ReferenceAboNode(void)
0x180007578  mov     rcx, rdi; this
0x18000757b  call    ?DeleteNode@ABO_NODE@@QEAAJXZ; ABO_NODE::DeleteNode(void)
0x180007580  mov     ebx, eax
0x180007582  test    eax, eax
0x180007584  js      short loc_1800075A8
0x180007586  mov     rcx, [rbp+30h]
0x18000758a  test    rcx, rcx
0x18000758d  jz      short loc_18000759C
0x18000758f  mov     rdx, [r14]
0x180007592  mov     rdx, [rdx+rsi*8]
0x180007596  call    cs:__imp_?DeleteRecord@CLKRHashTable@@QEAA?AW4LK_RETCODE@@PEBX@Z; CLKRHashTable::DeleteRecord(void const *)
0x18000759c  mov     edx, esi; unsigned int
0x18000759e  mov     rcx, r14; this
0x1800075a1  call    ?DeleteEntry@ARRAY_LIST@@QEAAJK@Z; ARRAY_LIST::DeleteEntry(ulong)
0x1800075a6  mov     ebx, eax
0x1800075a8  mov     rcx, rdi; this
0x1800075ab  call    ?DereferenceAboNode@ABO_NODE@@QEAAXXZ; ABO_NODE::DereferenceAboNode(void)
0x1800075b0  jmp     short loc_1800075B7
0x1800075b2  mov     ebx, 80070003h
0x1800075b7  mov     eax, ebx
0x1800075b9  add     rsp, 20h
0x1800075bd  pop     r14
0x1800075bf  pop     rdi
0x1800075c0  pop     rsi
0x1800075c1  pop     rbp
0x1800075c2  pop     rbx
0x1800075c3  retn
```
