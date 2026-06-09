# BipEnergyBudgetRecordTaskStats

- ea: `0x180036740`
- end: `0x18003693c`
- name: `BipEnergyBudgetRecordTaskStats`
- size: `508`
- prototype: `__int64 __usercall@<rax>(struct _BI_LOCK *@<rcx>, char)`
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18000e610`
- `0x180011450`
- `0x18005bed4`

## callees

- `0x180036740`
- `0x18006a8d4`

## import_xrefs

- `ntdll!RtlUpcaseUnicodeChar` at `0x180036807`
- `ntdll!RtlUpcaseUnicodeChar` at `0x180036807`
- `ntdll!RtlGetNextEntryHashTable` at `0x180036907`
- `ntdll!RtlGetNextEntryHashTable` at `0x180036907`
- `ntdll!RtlLookupEntryHashTable` at `0x180036845`
- `ntdll!RtlLookupEntryHashTable` at `0x180036845`
- `ntdll!RtlCompareUnicodeStrings` at `0x180036889`
- `ntdll!RtlCompareUnicodeStrings` at `0x180036889`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180036798`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180036798`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800368d9`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800368d9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003679e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003679e`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180036921`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180036921`

## pseudocode

```c
__int64 __fastcall BipEnergyBudgetRecordTaskStats(struct _BI_LOCK *a1, __int64 a2, unsigned int a3, char a4, char a5)
{
  unsigned int v6; // ebx
  unsigned int v7; // r15d
  __int64 v9; // rsi
  __int64 v10; // rax
  WCHAR *v11; // r13
  __int64 v12; // rbx
  __int64 v13; // rax
  __int64 v14; // r12
  WCHAR *v15; // r14
  WCHAR v16; // ax
  __int64 NextEntryHashTable; // rax
  _QWORD *v18; // rbx
  __int64 v19; // r9
  __int64 v20; // rcx
  __int64 v21; // rdx
  int v22; // edi
  __int64 result; // rax
  int v24; // [rsp+20h] [rbp-68h]
  __int128 v25; // [rsp+30h] [rbp-58h] BYREF
  __int64 v26; // [rsp+40h] [rbp-48h]
  __int64 v27; // [rsp+90h] [rbp+8h]

  v6 = 1 << *((_DWORD *)a1 + 2);
  v7 = 0;
  v9 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index);
  if ( *(_DWORD *)(v9 + 4) >= v6 && IsDebuggerPresent() )
    BipSyncDebugPrintLockBug(a1);
  RtlAcquireSRWLockExclusive(a1);
  *((_DWORD *)a1 + 3) = GetCurrentThreadId();
  *(_DWORD *)(v9 + 8) |= v6;
  *(_DWORD *)(v9 + 4) |= v6;
  v10 = *(_QWORD *)(a2 + 80);
  if ( v10 )
  {
    v11 = (WCHAR *)(v10 + 160);
    v26 = 0;
    v12 = -1;
    v13 = *((_QWORD *)a1 + 2);
    v27 = v13;
    v25 = 0;
    do
      ++v12;
    while ( v11[v12] );
    v14 = qword_1800C4148;
    v15 = v11;
    if ( (_DWORD)v12 )
    {
      do
      {
        v16 = RtlUpcaseUnicodeChar(*v15++);
        v14 = v16 + 39 * v14;
        ++v7;
      }
      while ( v7 < (unsigned int)v12 );
      v13 = v27;
    }
    v26 = 0;
    v25 = 0;
    NextEntryHashTable = RtlLookupEntryHashTable(v13, v14, &v25);
    if ( NextEntryHashTable )
    {
      do
      {
        v18 = (_QWORD *)NextEntryHashTable;
        v19 = -1;
        do
          ++v19;
        while ( v11[v19] );
        v20 = NextEntryHashTable + 40;
        v21 = -1;
        do
          ++v21;
        while ( *(_WORD *)(v20 + 2 * v21) );
        LOBYTE(v24) = 1;
        if ( !(unsigned int)RtlCompareUnicodeStrings(v20, v21, v11, v19, v24) )
          break;
        NextEntryHashTable = RtlGetNextEntryHashTable(v27, &v25);
      }
      while ( NextEntryHashTable );
      v18[49] += a3;
      if ( a4 )
        ++v18[47];
      if ( a5 )
        ++v18[48];
    }
  }
  v22 = ~(1 << *((_DWORD *)a1 + 2));
  *((_DWORD *)a1 + 3) = 0;
  *(_DWORD *)(v9 + 8) &= v22;
  RtlReleaseSRWLockExclusive(a1);
  result = 4;
  *(_DWORD *)(v9 + 4) &= v22;
  return result;
}

```

## disassembly

```asm
0x180036740  mov     [rsp+arg_8], rbx
0x180036745  mov     [rsp+arg_18], r9b
0x18003674a  mov     [rsp+arg_10], r8d
0x18003674f  push    rbp
0x180036750  push    rsi
0x180036751  push    rdi
0x180036752  push    r12
0x180036754  push    r13
0x180036756  push    r14
0x180036758  push    r15
0x18003675a  sub     rsp, 50h
0x18003675e  mov     rax, gs:58h
0x180036767  mov     edi, 1
0x18003676c  mov     r10d, cs:_tls_index
0x180036773  mov     rbp, rcx
0x180036776  mov     ecx, [rcx+8]
0x180036779  mov     ebx, edi
0x18003677b  shl     ebx, cl
0x18003677d  xor     r15d, r15d
0x180036780  mov     r14, rdx
0x180036783  mov     rsi, [rax+r10*8]
0x180036787  mov     eax, 4
0x18003678c  cmp     [rax+rsi], ebx
0x18003678f  jnb     loc_180036921
0x180036795  mov     rcx, rbp
0x180036798  call    cs:__imp_RtlAcquireSRWLockExclusive
0x18003679e  call    cs:__imp_GetCurrentThreadId
0x1800367a4  mov     [rbp+0Ch], eax
0x1800367a7  mov     eax, 8
0x1800367ac  or      [rax+rsi], ebx
0x1800367af  mov     eax, 4
0x1800367b4  or      [rax+rsi], ebx
0x1800367b7  mov     rax, [r14+50h]
0x1800367bb  test    rax, rax
0x1800367be  jz      loc_1800368C3
0x1800367c4  lea     r13, [rax+0A0h]
0x1800367cb  xorps   xmm0, xmm0
0x1800367ce  xor     eax, eax
0x1800367d0  mov     [rsp+88h+var_48], rax
0x1800367d5  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800367d9  mov     rax, [rbp+10h]
0x1800367dd  mov     [rsp+88h+arg_0], rax
0x1800367e5  movups  [rsp+88h+var_58], xmm0
0x1800367ea  inc     rbx
0x1800367ed  cmp     [r13+rbx*2+0], r15w
0x1800367f3  jnz     short loc_1800367EA
0x1800367f5  mov     r12, cs:qword_1800C4148
0x1800367fc  mov     r14, r13
0x1800367ff  test    ebx, ebx
0x180036801  jz      short loc_18003682B
0x180036803  movzx   ecx, word ptr [r14]; Source
0x180036807  call    cs:__imp_RtlUpcaseUnicodeChar
0x18003680d  imul    r12, 27h ; '''
0x180036811  movzx   ecx, ax
0x180036814  lea     r14, [r14+2]
0x180036818  add     r12, rcx
0x18003681b  add     r15d, edi
0x18003681e  cmp     r15d, ebx
0x180036821  jb      short loc_180036803
0x180036823  mov     rax, [rsp+88h+arg_0]
0x18003682b  xor     ecx, ecx
0x18003682d  lea     r8, [rsp+88h+var_58]
0x180036832  mov     [rsp+88h+var_48], rcx
0x180036837  xorps   xmm0, xmm0
0x18003683a  mov     rcx, rax
0x18003683d  mov     rdx, r12
0x180036840  movups  [rsp+88h+var_58], xmm0
0x180036845  call    cs:__imp_RtlLookupEntryHashTable
0x18003684b  xor     r15d, r15d
0x18003684e  test    rax, rax
0x180036851  jz      short loc_1800368C3
0x180036853  mov     r14, [rsp+88h+arg_0]
0x18003685b  or      r12, 0FFFFFFFFFFFFFFFFh
0x18003685f  mov     rbx, rax
0x180036862  mov     r9, r12
0x180036865  inc     r9
0x180036868  cmp     [r13+r9*2+0], r15w
0x18003686e  jnz     short loc_180036865
0x180036870  lea     rcx, [rax+28h]
0x180036874  mov     rdx, r12
0x180036877  inc     rdx
0x18003687a  cmp     [rcx+rdx*2], r15w
0x18003687f  jnz     short loc_180036877
0x180036881  mov     r8, r13
0x180036884  mov     byte ptr [rsp+88h+var_68], dil
0x180036889  call    cs:__imp_RtlCompareUnicodeStrings
0x18003688f  test    eax, eax
0x180036891  jnz     short loc_1800368FF
0x180036893  mov     eax, [rsp+88h+arg_10]
0x18003689a  add     [rbx+188h], rax
0x1800368a1  cmp     [rsp+88h+arg_18], r15b
0x1800368a9  jz      short loc_1800368B2
0x1800368ab  add     [rbx+178h], rdi
0x1800368b2  cmp     [rsp+88h+arg_20], r15b
0x1800368ba  jz      short loc_1800368C3
0x1800368bc  add     [rbx+180h], rdi
0x1800368c3  mov     ecx, [rbp+8]
0x1800368c6  shl     edi, cl
0x1800368c8  mov     rcx, rbp
0x1800368cb  mov     eax, 8
0x1800368d0  not     edi
0x1800368d2  mov     [rbp+0Ch], r15d
0x1800368d6  and     [rax+rsi], edi
0x1800368d9  call    cs:__imp_RtlReleaseSRWLockExclusive
0x1800368df  mov     rbx, [rsp+88h+arg_8]
0x1800368e7  mov     eax, 4
0x1800368ec  and     [rax+rsi], edi
0x1800368ef  add     rsp, 50h
0x1800368f3  pop     r15
0x1800368f5  pop     r14
0x1800368f7  pop     r13
0x1800368f9  pop     r12
0x1800368fb  pop     rdi
0x1800368fc  pop     rsi
0x1800368fd  pop     rbp
0x1800368fe  retn
0x1800368ff  lea     rdx, [rsp+88h+var_58]
0x180036904  mov     rcx, r14
0x180036907  call    cs:__imp_RtlGetNextEntryHashTable
0x18003690d  test    rax, rax
0x180036910  jnz     loc_18003685F
0x180036916  test    rbx, rbx
0x180036919  jnz     loc_180036893
0x18003691f  jmp     short loc_1800368C3
0x180036921  call    cs:__imp_IsDebuggerPresent
0x180036927  test    eax, eax
0x180036929  jz      loc_180036795
0x18003692f  mov     rcx, rbp; struct _BI_LOCK *
0x180036932  call    ?BipSyncDebugPrintLockBug@@YAXPEAU_BI_LOCK@@@Z; BipSyncDebugPrintLockBug(_BI_LOCK *)
0x180036937  jmp     loc_180036795
```
