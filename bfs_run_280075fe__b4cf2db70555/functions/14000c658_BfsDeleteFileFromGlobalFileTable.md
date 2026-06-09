# BfsDeleteFileFromGlobalFileTable

- ea: `0x14000c658`
- end: `0x14000c8c3`
- name: `BfsDeleteFileFromGlobalFileTable`
- size: `619`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x14000c1b4`

## callees

- `0x140001008`
- `0x140001320`
- `0x140006040`
- `0x140007044`
- `0x14000c31c`
- `0x14000c658`
- `0x14000d55c`
- `0x140010ffc`
- `0x140012b9c`
- `0x140013730`

## import_xrefs

- `ntoskrnl!RtlInitEnumerationHashTable` at `0x14000c729`
- `ntoskrnl!RtlInitEnumerationHashTable` at `0x14000c729`
- `ntoskrnl!RtlEnumerateEntryHashTable` at `0x14000c7fc`
- `ntoskrnl!RtlEnumerateEntryHashTable` at `0x14000c7fc`
- `ntoskrnl!RtlEndEnumerationHashTable` at `0x14000c81c`
- `ntoskrnl!RtlEndEnumerationHashTable` at `0x14000c81c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000c7b9`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000c7cb`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000c7e8`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000c857`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000c7b9`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000c7cb`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000c7e8`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000c857`

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
  unsigned int v16; // edi
  __int64 v17; // r8
  __int64 v18; // r9
  __int64 v19; // rcx
  PRTL_DYNAMIC_HASH_TABLE_ENTRY v20; // rax
  struct _RTL_DYNAMIC_HASH_TABLE_ENTRY *v21; // r14
  int v23; // [rsp+20h] [rbp-79h]
  PVOID P; // [rsp+30h] [rbp-69h] BYREF
  __int128 v25; // [rsp+38h] [rbp-61h] BYREF
  UNICODE_STRING v26; // [rsp+48h] [rbp-51h] BYREF
  struct _RTL_DYNAMIC_HASH_TABLE_ENUMERATOR Enumerator; // [rsp+58h] [rbp-41h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v28; // [rsp+80h] [rbp-19h] BYREF
  PVOID *p_P; // [rsp+A0h] [rbp+7h]
  __int64 v30; // [rsp+A8h] [rbp+Fh]

  memset(&Enumerator, 0, sizeof(Enumerator));
  v25 = 0;
  v26 = 0;
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
    v26.Buffer = *(PWSTR *)(GlobalFileEntry + 72);
    v26.Length = 2 * v9;
    v10 = (unsigned int)(v9 + 1);
    v26.MaximumLength = v26.Length;
    v11 = *(_QWORD *)(GlobalFileEntry + 72) + 2 * v10;
    v12 = *(_WORD *)(GlobalFileEntry + 64);
    *((_QWORD *)&v25 + 1) = v11;
    v13 = *(struct _RTL_DYNAMIC_HASH_TABLE **)(v6 + 88);
    LOWORD(v25) = v12 - 2 * v10;
    WORD1(v25) = v25;
    if ( v13 )
    {
      RtlInitEnumerationHashTable(v13, &Enumerator);
      while ( 1 )
      {
        do
        {
          v20 = RtlEnumerateEntryHashTable(*(PRTL_DYNAMIC_HASH_TABLE *)(v6 + 88), &Enumerator);
          v21 = v20;
          if ( !v20 )
          {
            RtlEndEnumerationHashTable(*(PRTL_DYNAMIC_HASH_TABLE *)(v6 + 88), &Enumerator);
            goto LABEL_17;
          }
          v14 = *(_QWORD *)(v6 + 48);
          P = 0;
        }
        while ( (signed __int64)v20[1].Signature > v14 );
        if ( (int)BfsGetPolicyEntry(
                    a1,
                    a2,
                    (__int64)&gBfsPolicyTable,
                    v20[1].Linkage.Flink,
                    v20[1].Linkage.Blink,
                    (__int64 *)&P) >= 0 )
        {
          v15 = P;
          v16 = BfsDeleteEntry(*((_QWORD *)P + 6), *(_DWORD *)(v6 + 80), &v26, &v25);
          BfsDereferencePolicyEntryEx(v15);
          v19 = 0;
          if ( v16 != -1073741275 )
            v19 = v16;
          if ( (int)v19 < 0 )
            break;
        }
        ExFreePoolWithTag(v21[1].Linkage.Flink, 0);
        ExFreePoolWithTag(v21[1].Linkage.Blink, 0);
        BfsRemoveEntryHashTable(*(struct _RTL_DYNAMIC_HASH_TABLE **)(v6 + 88), v21);
        ExFreePoolWithTag(v21, 0);
      }
      if ( (unsigned int)dword_140019000 > 3 )
      {
        LODWORD(P) = v19;
        p_P = &P;
        v30 = 4;
        tlgWriteTransfer_EtwWriteTransfer(v19, (unsigned __int8 *)&byte_140016D91, v17, v18, v23, &v28);
      }
    }
    else
    {
LABEL_17:
      BfsRemoveFileEntryFromDeleteList(v6);
      if ( !*(_DWORD *)(*(_QWORD *)(v6 + 88) + 20LL) )
      {
        BfsRemoveEntryHashTable(::P, (struct _RTL_DYNAMIC_HASH_TABLE_ENTRY *)v6);
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
0x14000c658  push    rbp
0x14000c65a  push    rbx
0x14000c65b  push    rsi
0x14000c65c  push    rdi
0x14000c65d  push    r12
0x14000c65f  push    r14
0x14000c661  push    r15
0x14000c663  lea     rbp, [rsp-27h]
0x14000c668  sub     rsp, 0C0h
0x14000c66f  mov     rax, cs:__security_cookie
0x14000c676  xor     rax, rsp
0x14000c679  mov     [rbp+57h+var_40], rax
0x14000c67d  xorps   xmm0, xmm0
0x14000c680  mov     r12, rdx
0x14000c683  mov     r15, rcx
0x14000c686  xor     eax, eax
0x14000c688  xorps   xmm1, xmm1
0x14000c68b  mov     qword ptr [rbp+57h+Enumerator.BucketIndex], rax
0x14000c68f  mov     rdx, r8
0x14000c692  lea     rcx, gBfsGlobalFileTable
0x14000c699  movups  xmmword ptr [rbp+57h+Enumerator], xmm0
0x14000c69d  movups  xmmword ptr [rbp+57h+Enumerator+10h], xmm0
0x14000c6a1  movups  [rbp+57h+var_B8], xmm0
0x14000c6a5  movups  [rbp+57h+var_A8], xmm1
0x14000c6a9  call    BfsGetGlobalFileEntry
0x14000c6ae  mov     rsi, rax
0x14000c6b1  movzx   r8d, word ptr [rax+40h]
0x14000c6b6  shr     r8d, 1
0x14000c6b9  jz      loc_14000C89A
0x14000c6bf  mov     r9, [rax+48h]
0x14000c6c3  xor     ecx, ecx
0x14000c6c5  xor     edx, edx
0x14000c6c7  cmp     word ptr [r9+rdx*2], 5Ch ; '\'
0x14000c6cd  jnz     short loc_14000C6D6
0x14000c6cf  inc     ecx
0x14000c6d1  cmp     ecx, 3
0x14000c6d4  jz      short loc_14000C6E6
0x14000c6d6  inc     edx
0x14000c6d8  cmp     edx, r8d
0x14000c6db  jb      short loc_14000C6C7
0x14000c6dd  cmp     ecx, 3
0x14000c6e0  jnz     loc_14000C89A
0x14000c6e6  movzx   eax, dx
0x14000c6e9  mov     qword ptr [rbp+57h+var_A8+8], r9
0x14000c6ed  add     ax, ax
0x14000c6f0  mov     word ptr [rbp+57h+var_A8], ax
0x14000c6f4  inc     edx
0x14000c6f6  mov     word ptr [rbp+57h+var_A8+2], ax
0x14000c6fa  mov     rax, [rsi+48h]
0x14000c6fe  lea     rcx, [rax+rdx*2]
0x14000c702  movzx   eax, word ptr [rsi+40h]
0x14000c706  add     dx, dx
0x14000c709  mov     qword ptr [rbp+57h+var_B8+8], rcx
0x14000c70d  mov     rcx, [rsi+58h]; HashTable
0x14000c711  sub     ax, dx
0x14000c714  mov     word ptr [rbp+57h+var_B8], ax
0x14000c718  mov     word ptr [rbp+57h+var_B8+2], ax
0x14000c71c  test    rcx, rcx
0x14000c71f  jz      loc_14000C828
0x14000c725  lea     rdx, [rbp+57h+Enumerator]; Enumerator
0x14000c729  call    cs:__imp_RtlInitEnumerationHashTable
0x14000c730  nop     dword ptr [rax+rax+00h]
0x14000c735  jmp     loc_14000C7F4
0x14000c73a  mov     rcx, [rsi+30h]
0x14000c73e  mov     [rbp+57h+P], 0
0x14000c746  cmp     [r14+28h], rcx
0x14000c74a  jg      loc_14000C7F4
0x14000c750  mov     r9, [r14+18h]
0x14000c754  lea     rax, [rbp+57h+P]
0x14000c758  mov     [rsp+0F0h+var_C8], rax
0x14000c75d  lea     r8, gBfsPolicyTable
0x14000c764  mov     rax, [r14+20h]
0x14000c768  mov     rdx, r12
0x14000c76b  mov     rcx, r15
0x14000c76e  mov     qword ptr [rsp+0F0h+var_D0], rax; int
0x14000c773  call    BfsGetPolicyEntry
0x14000c778  test    eax, eax
0x14000c77a  js      short loc_14000C7B3
0x14000c77c  mov     rbx, [rbp+57h+P]
0x14000c780  lea     r9, [rbp+57h+var_B8]
0x14000c784  mov     edx, [rsi+50h]
0x14000c787  lea     r8, [rbp+57h+var_A8]
0x14000c78b  mov     rcx, [rbx+30h]
0x14000c78f  call    BfsDeleteEntry
0x14000c794  xor     edx, edx
0x14000c796  mov     rcx, rbx; P
0x14000c799  mov     edi, eax
0x14000c79b  call    BfsDereferencePolicyEntryEx
0x14000c7a0  xor     ecx, ecx
0x14000c7a2  cmp     edi, 0C0000225h
0x14000c7a8  cmovnz  ecx, edi; int
0x14000c7ab  test    ecx, ecx
0x14000c7ad  js      loc_14000C865
0x14000c7b3  mov     rcx, [r14+18h]; P
0x14000c7b7  xor     edx, edx; Tag
0x14000c7b9  call    cs:__imp_ExFreePoolWithTag
0x14000c7c0  nop     dword ptr [rax+rax+00h]
0x14000c7c5  mov     rcx, [r14+20h]; P
0x14000c7c9  xor     edx, edx; Tag
0x14000c7cb  call    cs:__imp_ExFreePoolWithTag
0x14000c7d2  nop     dword ptr [rax+rax+00h]
0x14000c7d7  mov     rcx, [rsi+58h]
0x14000c7db  mov     rdx, r14
0x14000c7de  call    BfsRemoveEntryHashTable
0x14000c7e3  xor     edx, edx; Tag
0x14000c7e5  mov     rcx, r14; P
0x14000c7e8  call    cs:__imp_ExFreePoolWithTag
0x14000c7ef  nop     dword ptr [rax+rax+00h]
0x14000c7f4  mov     rcx, [rsi+58h]; HashTable
0x14000c7f8  lea     rdx, [rbp+57h+Enumerator]; Enumerator
0x14000c7fc  call    cs:__imp_RtlEnumerateEntryHashTable
0x14000c803  nop     dword ptr [rax+rax+00h]
0x14000c808  mov     r14, rax
0x14000c80b  test    rax, rax
0x14000c80e  jnz     loc_14000C73A
0x14000c814  mov     rcx, [rsi+58h]; HashTable
0x14000c818  lea     rdx, [rbp+57h+Enumerator]; Enumerator
0x14000c81c  call    cs:__imp_RtlEndEnumerationHashTable
0x14000c823  nop     dword ptr [rax+rax+00h]
0x14000c828  mov     rcx, rsi
0x14000c82b  call    BfsRemoveFileEntryFromDeleteList
0x14000c830  mov     r10, [rsi+58h]
0x14000c834  cmp     dword ptr [r10+14h], 0
0x14000c839  jnz     short loc_14000C8A2
0x14000c83b  mov     rcx, cs:P
0x14000c842  mov     rdx, rsi
0x14000c845  call    BfsRemoveEntryHashTable
0x14000c84a  mov     rcx, rsi
0x14000c84d  call    BfsClearGlobalFileEntry
0x14000c852  xor     edx, edx; Tag
0x14000c854  mov     rcx, rsi; P
0x14000c857  call    cs:__imp_ExFreePoolWithTag
0x14000c85e  nop     dword ptr [rax+rax+00h]
0x14000c863  jmp     short loc_14000C8A2
0x14000c865  mov     eax, cs:dword_140019000
0x14000c86b  cmp     eax, 3
0x14000c86e  jbe     short loc_14000C8A2
0x14000c870  lea     rax, [rbp+57h+P]
0x14000c874  mov     dword ptr [rbp+57h+P], ecx
0x14000c877  mov     [rbp+57h+var_50], rax
0x14000c87b  lea     rdx, byte_140016D91; int
0x14000c882  lea     rax, [rbp+57h+var_70]
0x14000c886  mov     [rbp+57h+var_48], 4
0x14000c88e  mov     [rsp+0F0h+var_C8], rax; PEVENT_DATA_DESCRIPTOR
0x14000c893  call    _tlgWriteTransfer_EtwWriteTransfer
0x14000c898  jmp     short loc_14000C8A2
0x14000c89a  mov     rcx, rsi
0x14000c89d  call    BfsRemoveFileEntryFromDeleteList
0x14000c8a2  xor     eax, eax
0x14000c8a4  mov     rcx, [rbp+57h+var_40]
0x14000c8a8  xor     rcx, rsp; StackCookie
0x14000c8ab  call    __security_check_cookie
0x14000c8b0  add     rsp, 0C0h
0x14000c8b7  pop     r15
0x14000c8b9  pop     r14
0x14000c8bb  pop     r12
0x14000c8bd  pop     rdi
0x14000c8be  pop     rsi
0x14000c8bf  pop     rbx
0x14000c8c0  pop     rbp
0x14000c8c1  retn
```
