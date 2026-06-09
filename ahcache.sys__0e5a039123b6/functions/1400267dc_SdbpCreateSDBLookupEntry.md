# SdbpCreateSDBLookupEntry

- ea: `0x1400267dc`
- end: `0x14002696b`
- name: `SdbpCreateSDBLookupEntry`
- size: `399`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x140052234`

## callees

- `0x1400012f0`
- `0x140026660`
- `0x1400267dc`
- `0x14002d39c`
- `0x14003e364`
- `0x14005498c`

## string_xrefs

- `0x1400268b0`: `SdbpCreateSDBLookupEntry`
- `0x140026946`: `SdbpCreateSDBLookupEntry`

## pseudocode

```c
_QWORD *__fastcall SdbpCreateSDBLookupEntry(__int64 a1, int a2, const wchar_t *a3, unsigned int a4)
{
  __int64 SDBLookupEntry; // rax
  __int64 v9; // rcx
  __int64 v10; // rax
  int v11; // r14d
  unsigned __int64 v12; // rdx
  unsigned __int64 v13; // rsi
  unsigned int v14; // eax
  unsigned int v15; // edi
  __int64 v16; // rax
  wchar_t *v17; // rcx
  _QWORD *v18; // r10
  __int64 v19; // rax

  SDBLookupEntry = SdbpFindSDBLookupEntry(a1, a3, a4);
  if ( SDBLookupEntry )
    SdbpRemoveSDBLookupEntry(a1, SDBLookupEntry);
  v10 = -1;
  do
    ++v10;
  while ( a3[v10] );
  v11 = v10 + 1;
  v12 = 2LL * (unsigned int)(v10 + 1);
  if ( v12 > 0xFFFFFFFF || (v13 = 24LL * (unsigned int)(a2 - 1), v13 > 0xFFFFFFFF) )
  {
    AslLogCallPrintf(1, "SdbpCreateSDBLookupEntry", 270, "Invalid sdb lookup buffer request");
    return 0;
  }
  v14 = v13 + v12;
  if ( (int)v13 + (int)v12 < (unsigned int)v12 )
  {
    AslLogCallPrintf(1, "SdbpCreateSDBLookupEntry", 277, "Invalid sdb lookup total buffer request");
    return 0;
  }
  v15 = v14 + 56;
  if ( v14 + 56 < v14 )
  {
    AslLogCallPrintf(1, "SdbpCreateSDBLookupEntry", 282, "Invalid sdb lookup total buffer request");
    return 0;
  }
  v16 = AslAlloc(v9, v15, 1);
  if ( !v16 )
  {
    AslLogCallPrintf(1, "SdbpCreateSDBLookupEntry", 289, "Failed to allocate 0x%lx bytes for sdb lookup buffer", v15);
    return 0;
  }
  v17 = (wchar_t *)(v16 + v13 + 56);
  *(_DWORD *)(v16 + 24) = a4;
  *(_QWORD *)(v16 + 16) = v17;
  *(_DWORD *)(v16 + 28) = a2;
  if ( RtlStringCchCopyW(v17, v11, a3) < 0 )
    return 0;
  v19 = *(_QWORD *)(a1 + 576);
  if ( v19 )
  {
    *v18 = v19;
    v18[1] = *(_QWORD *)(*(_QWORD *)(a1 + 576) + 8LL);
    **(_QWORD **)(*(_QWORD *)(a1 + 576) + 8LL) = v18;
    *(_QWORD *)(*(_QWORD *)(a1 + 576) + 8LL) = v18;
    *(_QWORD *)(a1 + 576) = v18;
  }
  else
  {
    *(_QWORD *)(a1 + 576) = v18;
    v18[1] = v18;
    *v18 = v18;
  }
  return v18;
}

```

## disassembly

```asm
0x1400267dc  push    rbx
0x1400267de  push    rbp
0x1400267df  push    rsi
0x1400267e0  push    rdi
0x1400267e1  push    r12
0x1400267e3  push    r13
0x1400267e5  push    r14
0x1400267e7  push    r15
0x1400267e9  sub     rsp, 38h
0x1400267ed  mov     rbp, r8
0x1400267f0  mov     r15d, edx
0x1400267f3  mov     rdx, rbp
0x1400267f6  mov     r8d, r9d
0x1400267f9  mov     r12d, r9d
0x1400267fc  mov     rbx, rcx
0x1400267ff  call    SdbpFindSDBLookupEntry
0x140026804  xor     r13d, r13d
0x140026807  test    rax, rax
0x14002680a  jz      short loc_140026817
0x14002680c  mov     rdx, rax
0x14002680f  mov     rcx, rbx
0x140026812  call    SdbpRemoveSDBLookupEntry
0x140026817  or      rax, 0FFFFFFFFFFFFFFFFh
0x14002681b  inc     rax
0x14002681e  cmp     [rbp+rax*2+0], r13w
0x140026824  jnz     short loc_14002681B
0x140026826  lea     r14d, [rax+1]
0x14002682a  mov     r8d, 0FFFFFFFFh
0x140026830  mov     edx, r14d
0x140026833  add     rdx, rdx
0x140026836  cmp     rdx, r8
0x140026839  ja      loc_140026939
0x14002683f  lea     eax, [r15-1]
0x140026843  lea     rax, [rax+rax*2]
0x140026847  lea     rsi, ds:0[rax*8]
0x14002684f  cmp     rsi, r8
0x140026852  ja      loc_140026939
0x140026858  lea     eax, [rsi+rdx]
0x14002685b  cmp     eax, edx
0x14002685d  jnb     short loc_140026871
0x14002685f  lea     r9, aInvalidSdbLook_0; "Invalid sdb lookup total buffer request"
0x140026866  mov     r8d, 115h
0x14002686c  jmp     loc_140026946
0x140026871  lea     edi, [rax+38h]
0x140026874  cmp     edi, eax
0x140026876  jnb     short loc_14002688A
0x140026878  lea     r9, aInvalidSdbLook_0; "Invalid sdb lookup total buffer request"
0x14002687f  mov     r8d, 11Ah
0x140026885  jmp     loc_140026946
0x14002688a  mov     edx, edi
0x14002688c  mov     r8d, 1
0x140026892  call    AslAlloc
0x140026897  mov     r10, rax
0x14002689a  test    rax, rax
0x14002689d  jnz     short loc_1400268C4
0x14002689f  lea     r9, aFailedToAlloca_3; "Failed to allocate 0x%lx bytes for sdb "...
0x1400268a6  mov     [rsp+78h+var_58], edi
0x1400268aa  mov     r8d, 121h
0x1400268b0  lea     rdx, aSdbpcreatesdbl; "SdbpCreateSDBLookupEntry"
0x1400268b7  lea     ecx, [rax+1]
0x1400268ba  call    AslLogCallPrintf
0x1400268bf  jmp     loc_140026957
0x1400268c4  lea     rcx, [rsi+38h]
0x1400268c8  movsxd  rdx, r14d; cchDest
0x1400268cb  add     rcx, r10; pszDest
0x1400268ce  mov     [rax+18h], r12d
0x1400268d2  mov     r8, rbp; pszSrc
0x1400268d5  mov     [rax+10h], rcx
0x1400268d9  mov     [rax+1Ch], r15d
0x1400268dd  call    RtlStringCchCopyW
0x1400268e2  test    eax, eax
0x1400268e4  js      short loc_140026957
0x1400268e6  mov     rax, [rbx+240h]
0x1400268ed  test    rax, rax
0x1400268f0  jnz     short loc_140026902
0x1400268f2  mov     [rbx+240h], r10
0x1400268f9  mov     [r10+8], r10
0x1400268fd  mov     [r10], r10
0x140026900  jmp     short loc_140026934
0x140026902  mov     [r10], rax
0x140026905  mov     rax, [rbx+240h]
0x14002690c  mov     rcx, [rax+8]
0x140026910  mov     [r10+8], rcx
0x140026914  mov     rax, [rbx+240h]
0x14002691b  mov     rcx, [rax+8]
0x14002691f  mov     [rcx], r10
0x140026922  mov     rax, [rbx+240h]
0x140026929  mov     [rax+8], r10
0x14002692d  mov     [rbx+240h], r10
0x140026934  mov     rax, r10
0x140026937  jmp     short loc_140026959
0x140026939  lea     r9, aInvalidSdbLook; "Invalid sdb lookup buffer request"
0x140026940  mov     r8d, 10Eh
0x140026946  lea     rdx, aSdbpcreatesdbl; "SdbpCreateSDBLookupEntry"
0x14002694d  mov     ecx, 1
0x140026952  call    AslLogCallPrintf
0x140026957  xor     eax, eax
0x140026959  add     rsp, 38h
0x14002695d  pop     r15
0x14002695f  pop     r14
0x140026961  pop     r13
0x140026963  pop     r12
0x140026965  pop     rdi
0x140026966  pop     rsi
0x140026967  pop     rbp
0x140026968  pop     rbx
0x140026969  retn
```
