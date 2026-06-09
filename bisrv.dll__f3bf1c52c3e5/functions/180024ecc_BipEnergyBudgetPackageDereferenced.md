# BipEnergyBudgetPackageDereferenced

- ea: `0x180024ecc`
- end: `0x1800250ca`
- name: `BipEnergyBudgetPackageDereferenced`
- size: `510`
- prototype: ``
- caller_count: `4`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180023b00`
- `0x18004b890`
- `0x180058b20`
- `0x18008170c`

## callees

- `0x180023bf0`
- `0x180024ecc`
- `0x1800250d0`
- `0x1800257fc`

## import_xrefs

- `ntdll!RtlUpcaseUnicodeChar` at `0x180024f1e`
- `ntdll!RtlUpcaseUnicodeChar` at `0x180024f1e`
- `ntdll!RtlGetNextEntryHashTable` at `0x180024fa3`
- `ntdll!RtlGetNextEntryHashTable` at `0x180024fa3`
- `ntdll!RtlLookupEntryHashTable` at `0x180024f52`
- `ntdll!RtlLookupEntryHashTable` at `0x180024f52`
- `ntdll!RtlCompareUnicodeStrings` at `0x180024f91`
- `ntdll!RtlCompareUnicodeStrings` at `0x180024ff0`
- `ntdll!RtlCompareUnicodeStrings` at `0x180024f91`
- `ntdll!RtlCompareUnicodeStrings` at `0x180024ff0`
- `ntdll!RtlFreeHeap` at `0x18002506a`
- `ntdll!RtlFreeHeap` at `0x180025088`
- `ntdll!RtlFreeHeap` at `0x18002506a`
- `ntdll!RtlFreeHeap` at `0x180025088`
- `ntdll!RtlEqualSid` at `0x180025009`
- `ntdll!RtlEqualSid` at `0x180025009`

## pseudocode

```c
__int64 __fastcall BipEnergyBudgetPackageDereferenced(__int64 a1, __int64 a2)
{
  __int64 v2; // r12
  __int64 v3; // r14
  __int64 v4; // rbx
  __int64 v7; // rbp
  WCHAR *v8; // rdi
  unsigned int i; // esi
  WCHAR v10; // ax
  __int64 result; // rax
  __int64 v12; // rdi
  __int64 v13; // r9
  __int64 v14; // rcx
  __int64 v15; // rdx
  void *v16; // rbp
  PSID *j; // rbx
  PSID *v18; // rcx
  PSID **v19; // rax
  PSID v20; // r8
  int v21; // [rsp+20h] [rbp-78h]
  __int128 v22; // [rsp+30h] [rbp-68h] BYREF
  __int64 v23; // [rsp+40h] [rbp-58h]

  v2 = *(_QWORD *)(a1 + 16);
  v3 = a2 + 160;
  v22 = 0;
  v23 = 0;
  v4 = -1;
  do
    ++v4;
  while ( *(_WORD *)(v3 + 2 * v4) );
  v7 = qword_1800C4148;
  v8 = (WCHAR *)(a2 + 160);
  for ( i = 0; i < (unsigned int)v4; ++i )
  {
    v10 = RtlUpcaseUnicodeChar(*v8++);
    v7 = v10 + 39 * v7;
  }
  v23 = 0;
  v22 = 0;
  result = RtlLookupEntryHashTable(v2, v7, &v22);
  if ( result )
  {
    do
    {
      v12 = result;
      v13 = -1;
      do
        ++v13;
      while ( *(_WORD *)(v3 + 2 * v13) );
      v14 = result + 40;
      v15 = -1;
      do
        ++v15;
      while ( *(_WORD *)(v14 + 2 * v15) );
      LOBYTE(v21) = 1;
      if ( !(unsigned int)RtlCompareUnicodeStrings(v14, v15, v3, v13, v21) )
        break;
      result = RtlGetNextEntryHashTable(v2, &v22);
    }
    while ( result );
    v16 = *(void **)(a2 + 24);
    for ( j = *(PSID **)(v12 + 352); j != (PSID *)(v12 + 352); j = (PSID *)*j )
    {
      LOBYTE(v21) = 1;
      if ( !(unsigned int)RtlCompareUnicodeStrings(j + 34, 65, a2 + 416, 65, v21) && RtlEqualSid(j[51], v16) )
      {
        if ( j )
        {
          if ( *(_DWORD *)(v12 + 296) == 1
            && *(_BYTE *)(v12 + 372)
            && !*(_DWORD *)(v12 + 368)
            && *((char *)j + 468) >= 0 )
          {
            BipPackageImportanceUpdateScoreForPackage(a1, j);
          }
          --*(_DWORD *)(v12 + 296);
          v18 = (PSID *)*j;
          if ( *((PSID **)*j + 1) != j || (v19 = (PSID **)j[1], *v19 != j) )
            __fastfail(3u);
          *v19 = v18;
          v18[1] = v19;
          v20 = j[51];
          if ( v20 )
            RtlFreeHeap(BipHeap, 0, v20);
          BipUsageHistoryCleanup(j + 54);
          RtlFreeHeap(BipHeap, 0, j);
        }
        return BipEnergyBudgetCacheImportanceScoreForBudget(a1, v12);
      }
    }
    return BipEnergyBudgetCacheImportanceScoreForBudget(a1, v12);
  }
  return result;
}

```

## disassembly

```asm
0x180024ecc  push    rbx
0x180024ece  push    rbp
0x180024ecf  push    rsi
0x180024ed0  push    rdi
0x180024ed1  push    r12
0x180024ed3  push    r13
0x180024ed5  push    r14
0x180024ed7  push    r15
0x180024ed9  sub     rsp, 58h
0x180024edd  mov     r12, [rcx+10h]
0x180024ee1  lea     r14, [rdx+0A0h]
0x180024ee8  xor     eax, eax
0x180024eea  xorps   xmm0, xmm0
0x180024eed  movups  [rsp+98h+var_68], xmm0
0x180024ef2  mov     [rsp+98h+var_58], rax
0x180024ef7  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180024efb  mov     r13, rdx
0x180024efe  mov     r15, rcx
0x180024f01  inc     rbx
0x180024f04  cmp     [r14+rbx*2], ax
0x180024f09  jnz     short loc_180024F01
0x180024f0b  mov     rbp, cs:qword_1800C4148
0x180024f12  mov     rdi, r14
0x180024f15  mov     esi, eax
0x180024f17  test    ebx, ebx
0x180024f19  jz      short loc_180024F38
0x180024f1b  movzx   ecx, word ptr [rdi]; Source
0x180024f1e  call    cs:__imp_RtlUpcaseUnicodeChar
0x180024f24  imul    rbp, 27h ; '''
0x180024f28  movzx   ecx, ax
0x180024f2b  lea     rdi, [rdi+2]
0x180024f2f  add     rbp, rcx
0x180024f32  inc     esi
0x180024f34  cmp     esi, ebx
0x180024f36  jb      short loc_180024F1B
0x180024f38  xorps   xmm0, xmm0
0x180024f3b  lea     r8, [rsp+98h+var_68]
0x180024f40  xor     eax, eax
0x180024f42  mov     rdx, rbp
0x180024f45  mov     rcx, r12
0x180024f48  mov     [rsp+98h+var_58], rax
0x180024f4d  movups  [rsp+98h+var_68], xmm0
0x180024f52  call    cs:__imp_RtlLookupEntryHashTable
0x180024f58  xor     r10d, r10d
0x180024f5b  test    rax, rax
0x180024f5e  jz      loc_180025099
0x180024f64  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180024f68  mov     rdi, rax
0x180024f6b  mov     r9, rbx
0x180024f6e  inc     r9
0x180024f71  cmp     [r14+r9*2], r10w
0x180024f76  jnz     short loc_180024F6E
0x180024f78  lea     rcx, [rax+28h]
0x180024f7c  mov     rdx, rbx
0x180024f7f  inc     rdx
0x180024f82  cmp     [rcx+rdx*2], r10w
0x180024f87  jnz     short loc_180024F7F
0x180024f89  mov     r8, r14
0x180024f8c  mov     byte ptr [rsp+98h+var_78], 1
0x180024f91  call    cs:__imp_RtlCompareUnicodeStrings
0x180024f97  test    eax, eax
0x180024f99  jz      short loc_180024FBA
0x180024f9b  lea     rdx, [rsp+98h+var_68]
0x180024fa0  mov     rcx, r12
0x180024fa3  call    cs:__imp_RtlGetNextEntryHashTable
0x180024fa9  xor     r10d, r10d
0x180024fac  test    rax, rax
0x180024faf  jnz     short loc_180024F68
0x180024fb1  test    rdi, rdi
0x180024fb4  jz      loc_180025099
0x180024fba  mov     rbp, [r13+18h]
0x180024fbe  lea     rsi, [rdi+160h]
0x180024fc5  mov     rbx, [rsi]
0x180024fc8  mov     r14d, 41h ; 'A'
0x180024fce  cmp     rbx, rsi
0x180024fd1  jz      loc_18002508E
0x180024fd7  lea     r8, [r13+1A0h]
0x180024fde  mov     byte ptr [rsp+98h+var_78], 1
0x180024fe3  lea     rcx, [rbx+110h]
0x180024fea  mov     r9, r14
0x180024fed  mov     rdx, r14
0x180024ff0  call    cs:__imp_RtlCompareUnicodeStrings
0x180024ff6  test    eax, eax
0x180024ff8  jz      short loc_180024FFF
0x180024ffa  mov     rbx, [rbx]
0x180024ffd  jmp     short loc_180024FCE
0x180024fff  mov     rcx, [rbx+198h]; Sid1
0x180025006  mov     rdx, rbp; Sid2
0x180025009  call    cs:__imp_RtlEqualSid
0x18002500f  xor     r10d, r10d
0x180025012  test    al, al
0x180025014  jz      short loc_180024FFA
0x180025016  test    rbx, rbx
0x180025019  jz      short loc_18002508E
0x18002501b  cmp     dword ptr [rdi+128h], 1
0x180025022  jnz     short loc_180025036
0x180025024  cmp     [rdi+174h], r10b
0x18002502b  jz      short loc_180025036
0x18002502d  cmp     [rdi+170h], r10d
0x180025034  jz      short loc_1800250AA
0x180025036  dec     dword ptr [rdi+128h]
0x18002503c  mov     rcx, [rbx]
0x18002503f  cmp     [rcx+8], rbx
0x180025043  jnz     short loc_1800250C3
0x180025045  mov     rax, [rbx+8]
0x180025049  cmp     [rax], rbx
0x18002504c  jnz     short loc_1800250C3
0x18002504e  mov     [rax], rcx
0x180025051  mov     [rcx+8], rax
0x180025055  mov     r8, [rbx+198h]; P
0x18002505c  test    r8, r8
0x18002505f  jz      short loc_180025070
0x180025061  mov     rcx, cs:BipHeap; HeapHandle
0x180025068  xor     edx, edx; Flags
0x18002506a  call    cs:__imp_RtlFreeHeap
0x180025070  lea     rcx, [rbx+1B0h]
0x180025077  call    BipUsageHistoryCleanup
0x18002507c  mov     rcx, cs:BipHeap; HeapHandle
0x180025083  mov     r8, rbx; P
0x180025086  xor     edx, edx; Flags
0x180025088  call    cs:__imp_RtlFreeHeap
0x18002508e  mov     rdx, rdi
0x180025091  mov     rcx, r15
0x180025094  call    BipEnergyBudgetCacheImportanceScoreForBudget
0x180025099  add     rsp, 58h
0x18002509d  pop     r15
0x18002509f  pop     r14
0x1800250a1  pop     r13
0x1800250a3  pop     r12
0x1800250a5  pop     rdi
0x1800250a6  pop     rsi
0x1800250a7  pop     rbp
0x1800250a8  pop     rbx
0x1800250a9  retn
0x1800250aa  cmp     [rbx+1D4h], r10b
0x1800250b1  jl      short loc_180025036
0x1800250b3  mov     rdx, rbx
0x1800250b6  mov     rcx, r15
0x1800250b9  call    BipPackageImportanceUpdateScoreForPackage
0x1800250be  jmp     loc_180025036
0x1800250c3  mov     ecx, 3
0x1800250c8  int     29h; Win8: RtlFailFast(ecx)
```
