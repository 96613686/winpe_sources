# BfsDeleteFileFromGlobalFileTable

- ea: `0x14000c7e8`
- end: `0x14000ca53`
- name: `BfsDeleteFileFromGlobalFileTable`
- size: `619`
- prototype: `__int64 __fastcall(__int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x14000c344`

## callees

- `0x140001008`
- `0x140001320`
- `0x1400061d0`
- `0x1400071d4`
- `0x14000c4ac`
- `0x14000c7e8`
- `0x14000d6f0`
- `0x140011194`
- `0x140012cd4`
- `0x140013860`

## import_xrefs

- `ntoskrnl!RtlInitEnumerationHashTable` at `0x14000c8b9`
- `ntoskrnl!RtlInitEnumerationHashTable` at `0x14000c8b9`
- `ntoskrnl!RtlEnumerateEntryHashTable` at `0x14000c98c`
- `ntoskrnl!RtlEnumerateEntryHashTable` at `0x14000c98c`
- `ntoskrnl!RtlEndEnumerationHashTable` at `0x14000c9ac`
- `ntoskrnl!RtlEndEnumerationHashTable` at `0x14000c9ac`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000c949`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000c95b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000c978`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000c9e7`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000c949`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000c95b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000c978`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000c9e7`

## pseudocode

```c
__int64 __fastcall BfsDeleteFileFromGlobalFileTable(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 GlobalFileEntry; // rax
  __int64 v6; // rsi
  unsigned int v7; // r8d
  int v8; // ecx
  __int64 v9; // rdx
  __int64 v10; // rdx
  __int64 v11; // rcx
  __int16 v12; // ax
  struct _RTL_DYNAMIC_HASH_TABLE *v13; // rcx
  signed __int64 v14; // rcx
  PVOID v15; // rbx
  int v16; // edi
  int v17; // r8d
  int v18; // r9d
  int v19; // ecx
  PRTL_DYNAMIC_HASH_TABLE_ENTRY v20; // rax
  PVOID *p_Flink; // r14
  int v23[2]; // [rsp+20h] [rbp-79h]
  int v24; // [rsp+20h] [rbp-79h]
  PVOID P; // [rsp+30h] [rbp-69h] BYREF
  __int128 v26; // [rsp+38h] [rbp-61h] BYREF
  __int128 v27; // [rsp+48h] [rbp-51h] BYREF
  struct _RTL_DYNAMIC_HASH_TABLE_ENUMERATOR Enumerator; // [rsp+58h] [rbp-41h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v29; // [rsp+80h] [rbp-19h] BYREF
  PVOID *p_P; // [rsp+A0h] [rbp+7h]
  __int64 v31; // [rsp+A8h] [rbp+Fh]

  memset(&Enumerator, 0, sizeof(Enumerator));
  v26 = 0;
  v27 = 0;
  GlobalFileEntry = BfsGetGlobalFileEntry(&gBfsGlobalFileTable, a3);
  v6 = GlobalFileEntry;
  v7 = *(unsigned __int16 *)(GlobalFileEntry + 64) >> 1;
  if ( v7 )
  {
    v8 = 0;
    v9 = 0;
    while ( *(_WORD *)(*(_QWORD *)(GlobalFileEntry + 72) + 2 * v9) != 92 || ++v8 != 3 )
    {
      v9 = (unsigned int)(v9 + 1);
      if ( (unsigned int)v9 >= v7 )
        goto LABEL_21;
    }
    *((_QWORD *)&v27 + 1) = *(_QWORD *)(GlobalFileEntry + 72);
    LOWORD(v27) = 2 * v9;
    v10 = (unsigned int)(v9 + 1);
    WORD1(v27) = v27;
    v11 = *(_QWORD *)(GlobalFileEntry + 72) + 2 * v10;
    v12 = *(_WORD *)(GlobalFileEntry + 64);
    *((_QWORD *)&v26 + 1) = v11;
    v13 = *(struct _RTL_DYNAMIC_HASH_TABLE **)(v6 + 88);
    LOWORD(v26) = v12 - 2 * v10;
    WORD1(v26) = v26;
    if ( v13 )
    {
      RtlInitEnumerationHashTable(v13, &Enumerator);
      while ( 1 )
      {
        do
        {
          v20 = RtlEnumerateEntryHashTable(*(PRTL_DYNAMIC_HASH_TABLE *)(v6 + 88), &Enumerator);
          p_Flink = (PVOID *)&v20->Linkage.Flink;
          if ( !v20 )
          {
            RtlEndEnumerationHashTable(*(PRTL_DYNAMIC_HASH_TABLE *)(v6 + 88), &Enumerator);
            goto LABEL_17;
          }
          v14 = *(_QWORD *)(v6 + 48);
          P = 0;
        }
        while ( (signed __int64)v20[1].Signature > v14 );
        *(_QWORD *)v23 = v20[1].Linkage.Blink;
        if ( (int)BfsGetPolicyEntry(a1, a2, &gBfsPolicyTable, v20[1].Linkage.Flink) >= 0 )
        {
          v15 = P;
          v16 = BfsDeleteEntry(*((_QWORD *)P + 6), *(unsigned int *)(v6 + 80), &v27, &v26, *(_QWORD *)v23, &P);
          BfsDereferencePolicyEntryEx(v15);
          v19 = 0;
          if ( v16 != -1073741275 )
            v19 = v16;
          if ( v19 < 0 )
            break;
        }
        ExFreePoolWithTag(p_Flink[3], 0);
        ExFreePoolWithTag(p_Flink[4], 0);
        BfsRemoveEntryHashTable(*(_QWORD *)(v6 + 88), p_Flink);
        ExFreePoolWithTag(p_Flink, 0);
      }
      if ( (unsigned int)dword_140019000 > 3 )
      {
        LODWORD(P) = v19;
        p_P = &P;
        v31 = 4;
        tlgWriteTransfer_EtwWriteTransfer(v19, (int)&byte_140016D91, v17, v18, v24, &v29);
      }
    }
    else
    {
LABEL_17:
      BfsRemoveFileEntryFromDeleteList(v6);
      if ( !*(_DWORD *)(*(_QWORD *)(v6 + 88) + 20LL) )
      {
        BfsRemoveEntryHashTable(::P, v6);
        BfsClearGlobalFileEntry(v6);
        ExFreePoolWithTag((PVOID)v6, 0);
      }
    }
  }
  else
  {
LABEL_21:
    BfsRemoveFileEntryFromDeleteList(GlobalFileEntry);
  }
  return 0;
}

```

## disassembly

```asm
0x14000c7e8  push    rbp
0x14000c7ea  push    rbx
0x14000c7eb  push    rsi
0x14000c7ec  push    rdi
0x14000c7ed  push    r12
0x14000c7ef  push    r14
0x14000c7f1  push    r15
0x14000c7f3  lea     rbp, [rsp-27h]
0x14000c7f8  sub     rsp, 0C0h
0x14000c7ff  mov     rax, cs:__security_cookie
0x14000c806  xor     rax, rsp
0x14000c809  mov     [rbp+57h+var_40], rax
0x14000c80d  xorps   xmm0, xmm0
0x14000c810  mov     r12, rdx
0x14000c813  mov     r15, rcx
0x14000c816  xor     eax, eax
0x14000c818  xorps   xmm1, xmm1
0x14000c81b  mov     qword ptr [rbp+57h+Enumerator.BucketIndex], rax
0x14000c81f  mov     rdx, r8
0x14000c822  lea     rcx, gBfsGlobalFileTable
0x14000c829  movups  xmmword ptr [rbp+57h+Enumerator], xmm0
0x14000c82d  movups  xmmword ptr [rbp+57h+Enumerator+10h], xmm0
0x14000c831  movups  [rbp+57h+var_B8], xmm0
0x14000c835  movups  [rbp+57h+var_A8], xmm1
0x14000c839  call    BfsGetGlobalFileEntry
0x14000c83e  mov     rsi, rax
0x14000c841  movzx   r8d, word ptr [rax+40h]
0x14000c846  shr     r8d, 1
0x14000c849  jz      loc_14000CA2A
0x14000c84f  mov     r9, [rax+48h]
0x14000c853  xor     ecx, ecx
0x14000c855  xor     edx, edx
0x14000c857  cmp     word ptr [r9+rdx*2], 5Ch ; '\'
0x14000c85d  jnz     short loc_14000C866
0x14000c85f  inc     ecx
0x14000c861  cmp     ecx, 3
0x14000c864  jz      short loc_14000C876
0x14000c866  inc     edx
0x14000c868  cmp     edx, r8d
0x14000c86b  jb      short loc_14000C857
0x14000c86d  cmp     ecx, 3
0x14000c870  jnz     loc_14000CA2A
0x14000c876  movzx   eax, dx
0x14000c879  mov     qword ptr [rbp+57h+var_A8+8], r9
0x14000c87d  add     ax, ax
0x14000c880  mov     word ptr [rbp+57h+var_A8], ax
0x14000c884  inc     edx
0x14000c886  mov     word ptr [rbp+57h+var_A8+2], ax
0x14000c88a  mov     rax, [rsi+48h]
0x14000c88e  lea     rcx, [rax+rdx*2]
0x14000c892  movzx   eax, word ptr [rsi+40h]
0x14000c896  add     dx, dx
0x14000c899  mov     qword ptr [rbp+57h+var_B8+8], rcx
0x14000c89d  mov     rcx, [rsi+58h]; HashTable
0x14000c8a1  sub     ax, dx
0x14000c8a4  mov     word ptr [rbp+57h+var_B8], ax
0x14000c8a8  mov     word ptr [rbp+57h+var_B8+2], ax
0x14000c8ac  test    rcx, rcx
0x14000c8af  jz      loc_14000C9B8
0x14000c8b5  lea     rdx, [rbp+57h+Enumerator]; Enumerator
0x14000c8b9  call    cs:__imp_RtlInitEnumerationHashTable
0x14000c8c0  nop     dword ptr [rax+rax+00h]
0x14000c8c5  jmp     loc_14000C984
0x14000c8ca  mov     rcx, [rsi+30h]
0x14000c8ce  mov     [rbp+57h+P], 0
0x14000c8d6  cmp     [r14+28h], rcx
0x14000c8da  jg      loc_14000C984
0x14000c8e0  mov     r9, [r14+18h]
0x14000c8e4  lea     rax, [rbp+57h+P]
0x14000c8e8  mov     [rsp+0F0h+var_C8], rax
0x14000c8ed  lea     r8, gBfsPolicyTable
0x14000c8f4  mov     rax, [r14+20h]
0x14000c8f8  mov     rdx, r12
0x14000c8fb  mov     rcx, r15
0x14000c8fe  mov     qword ptr [rsp+0F0h+var_D0], rax; int
0x14000c903  call    BfsGetPolicyEntry
0x14000c908  test    eax, eax
0x14000c90a  js      short loc_14000C943
0x14000c90c  mov     rbx, [rbp+57h+P]
0x14000c910  lea     r9, [rbp+57h+var_B8]
0x14000c914  mov     edx, [rsi+50h]
0x14000c917  lea     r8, [rbp+57h+var_A8]
0x14000c91b  mov     rcx, [rbx+30h]
0x14000c91f  call    BfsDeleteEntry
0x14000c924  xor     edx, edx
0x14000c926  mov     rcx, rbx; P
0x14000c929  mov     edi, eax
0x14000c92b  call    BfsDereferencePolicyEntryEx
0x14000c930  xor     ecx, ecx
0x14000c932  cmp     edi, 0C0000225h
0x14000c938  cmovnz  ecx, edi; int
0x14000c93b  test    ecx, ecx
0x14000c93d  js      loc_14000C9F5
0x14000c943  mov     rcx, [r14+18h]; P
0x14000c947  xor     edx, edx; Tag
0x14000c949  call    cs:__imp_ExFreePoolWithTag
0x14000c950  nop     dword ptr [rax+rax+00h]
0x14000c955  mov     rcx, [r14+20h]; P
0x14000c959  xor     edx, edx; Tag
0x14000c95b  call    cs:__imp_ExFreePoolWithTag
0x14000c962  nop     dword ptr [rax+rax+00h]
0x14000c967  mov     rcx, [rsi+58h]
0x14000c96b  mov     rdx, r14
0x14000c96e  call    BfsRemoveEntryHashTable
0x14000c973  xor     edx, edx; Tag
0x14000c975  mov     rcx, r14; P
0x14000c978  call    cs:__imp_ExFreePoolWithTag
0x14000c97f  nop     dword ptr [rax+rax+00h]
0x14000c984  mov     rcx, [rsi+58h]; HashTable
0x14000c988  lea     rdx, [rbp+57h+Enumerator]; Enumerator
0x14000c98c  call    cs:__imp_RtlEnumerateEntryHashTable
0x14000c993  nop     dword ptr [rax+rax+00h]
0x14000c998  mov     r14, rax
0x14000c99b  test    rax, rax
0x14000c99e  jnz     loc_14000C8CA
0x14000c9a4  mov     rcx, [rsi+58h]; HashTable
0x14000c9a8  lea     rdx, [rbp+57h+Enumerator]; Enumerator
0x14000c9ac  call    cs:__imp_RtlEndEnumerationHashTable
0x14000c9b3  nop     dword ptr [rax+rax+00h]
0x14000c9b8  mov     rcx, rsi
0x14000c9bb  call    BfsRemoveFileEntryFromDeleteList
0x14000c9c0  mov     r10, [rsi+58h]
0x14000c9c4  cmp     dword ptr [r10+14h], 0
0x14000c9c9  jnz     short loc_14000CA32
0x14000c9cb  mov     rcx, cs:P
0x14000c9d2  mov     rdx, rsi
0x14000c9d5  call    BfsRemoveEntryHashTable
0x14000c9da  mov     rcx, rsi
0x14000c9dd  call    BfsClearGlobalFileEntry
0x14000c9e2  xor     edx, edx; Tag
0x14000c9e4  mov     rcx, rsi; P
0x14000c9e7  call    cs:__imp_ExFreePoolWithTag
0x14000c9ee  nop     dword ptr [rax+rax+00h]
0x14000c9f3  jmp     short loc_14000CA32
0x14000c9f5  mov     eax, cs:dword_140019000
0x14000c9fb  cmp     eax, 3
0x14000c9fe  jbe     short loc_14000CA32
0x14000ca00  lea     rax, [rbp+57h+P]
0x14000ca04  mov     dword ptr [rbp+57h+P], ecx
0x14000ca07  mov     [rbp+57h+var_50], rax
0x14000ca0b  lea     rdx, byte_140016D91; int
0x14000ca12  lea     rax, [rbp+57h+var_70]
0x14000ca16  mov     [rbp+57h+var_48], 4
0x14000ca1e  mov     [rsp+0F0h+var_C8], rax; PEVENT_DATA_DESCRIPTOR
0x14000ca23  call    _tlgWriteTransfer_EtwWriteTransfer
0x14000ca28  jmp     short loc_14000CA32
0x14000ca2a  mov     rcx, rsi
0x14000ca2d  call    BfsRemoveFileEntryFromDeleteList
0x14000ca32  xor     eax, eax
0x14000ca34  mov     rcx, [rbp+57h+var_40]
0x14000ca38  xor     rcx, rsp; StackCookie
0x14000ca3b  call    __security_check_cookie
0x14000ca40  add     rsp, 0C0h
0x14000ca47  pop     r15
0x14000ca49  pop     r14
0x14000ca4b  pop     r12
0x14000ca4d  pop     rdi
0x14000ca4e  pop     rsi
0x14000ca4f  pop     rbx
0x14000ca50  pop     rbp
0x14000ca51  retn
```
