# BfsCreateGlobalFileEntry

- ea: `0x14000c434`
- end: `0x14000c652`
- name: `BfsCreateGlobalFileEntry`
- size: `542`
- prototype: `__int64 __fastcall(PCUNICODE_STRING SourceString)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x14000bf64`

## callees

- `0x140001008`
- `0x14000c434`
- `0x140013730`

## import_xrefs

- `ntoskrnl!RtlCreateHashTable` at `0x14000c573`
- `ntoskrnl!RtlCreateHashTable` at `0x14000c573`
- `ntoskrnl!RtlDeleteHashTable` at `0x14000c608`
- `ntoskrnl!RtlDeleteHashTable` at `0x14000c608`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000c58c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000c5dc`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000c5f3`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000c61a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000c58c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000c5dc`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000c5f3`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000c61a`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14000c539`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14000c539`
- `ntoskrnl!ExAllocatePool2` at `0x14000c472`
- `ntoskrnl!ExAllocatePool2` at `0x14000c4ee`
- `ntoskrnl!ExAllocatePool2` at `0x14000c553`
- `ntoskrnl!ExAllocatePool2` at `0x14000c472`
- `ntoskrnl!ExAllocatePool2` at `0x14000c4ee`
- `ntoskrnl!ExAllocatePool2` at `0x14000c553`

## pseudocode

```c
__int64 __fastcall BfsCreateGlobalFileEntry(PCUNICODE_STRING SourceString, int a2, struct _UNICODE_STRING **a3)
{
  __int64 Pool2; // rax
  int v7; // r8d
  int v8; // r9d
  struct _UNICODE_STRING *v9; // rbx
  unsigned int v10; // edi
  __int64 v11; // rax
  int v12; // r8d
  int v13; // r9d
  int v14; // ecx
  __int64 v15; // rax
  PVOID *p_Buffer; // rdi
  PWSTR Buffer; // rcx
  struct _RTL_DYNAMIC_HASH_TABLE *v18; // rcx
  int v20; // [rsp+20h] [rbp-50h]
  int v21; // [rsp+30h] [rbp-40h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v22; // [rsp+38h] [rbp-38h] BYREF
  int *v23; // [rsp+58h] [rbp-18h]
  __int64 v24; // [rsp+60h] [rbp-10h]

  Pool2 = ExAllocatePool2(256, 96, 1735616066);
  v9 = (struct _UNICODE_STRING *)Pool2;
  if ( !Pool2 )
  {
    v10 = -1073741801;
    if ( (unsigned int)dword_140019000 > 3 )
    {
      v21 = -1073741801;
      v23 = &v21;
      v24 = 4;
      tlgWriteTransfer_EtwWriteTransfer(-1073741801, (int)&byte_140016D91, v7, v8, v20, &v22);
    }
    goto LABEL_13;
  }
  *(_DWORD *)(Pool2 + 80) = a2;
  *(_BYTE *)(Pool2 + 40) = 0;
  *(_QWORD *)(Pool2 + 48) = 0;
  v11 = ExAllocatePool2(256, SourceString->Length + 2LL, 1316185666);
  v9[4].Buffer = (PWSTR)v11;
  if ( v11 )
  {
    v9[4].Length = SourceString->Length;
    v9[4].MaximumLength = SourceString->Length + 2;
    RtlCopyUnicodeString(v9 + 4, SourceString);
    v15 = ExAllocatePool2(256, 40, 1416848962);
    p_Buffer = (PVOID *)&v9[5].Buffer;
    v9[5].Buffer = (PWSTR)v15;
    if ( v15 )
    {
      if ( RtlCreateHashTable((PRTL_DYNAMIC_HASH_TABLE *)&v9[5].Buffer, 0, 0) )
      {
        v10 = 0;
        goto LABEL_19;
      }
      ExFreePoolWithTag(*p_Buffer, 0);
      *p_Buffer = 0;
      v10 = -1073741823;
      if ( (unsigned int)dword_140019000 <= 3 )
        goto LABEL_12;
      v21 = -1073741823;
      goto LABEL_11;
    }
  }
  v14 = -1073741801;
  v10 = -1073741801;
  if ( (unsigned int)dword_140019000 > 3 )
  {
    v21 = -1073741801;
LABEL_11:
    v24 = 4;
    v23 = &v21;
    tlgWriteTransfer_EtwWriteTransfer(v14, (int)&byte_140016D91, v12, v13, v20, &v22);
  }
LABEL_12:
  ExFreePoolWithTag(v9, 0);
LABEL_13:
  Buffer = v9[4].Buffer;
  if ( Buffer )
    ExFreePoolWithTag(Buffer, 0);
  v18 = (struct _RTL_DYNAMIC_HASH_TABLE *)v9[5].Buffer;
  if ( v18 )
  {
    RtlDeleteHashTable(v18);
    ExFreePoolWithTag(v9[5].Buffer, 0);
  }
  v9 = 0;
LABEL_19:
  *a3 = v9;
  return v10;
}

```

## disassembly

```asm
0x14000c434  mov     [rsp-28h+arg_8], rbx
0x14000c439  push    rbp
0x14000c43a  push    rsi
0x14000c43b  push    rdi
0x14000c43c  push    r12
0x14000c43e  push    r14
0x14000c440  mov     rbp, rsp
0x14000c443  sub     rsp, 70h
0x14000c447  mov     rax, cs:__security_cookie
0x14000c44e  xor     rax, rsp
0x14000c451  mov     [rbp+var_8], rax
0x14000c455  mov     rsi, r8
0x14000c458  mov     r14d, edx
0x14000c45b  mov     rdi, rcx
0x14000c45e  mov     r12d, 100h
0x14000c464  mov     ecx, r12d
0x14000c467  mov     edx, 60h ; '`'
0x14000c46c  mov     r8d, 67736642h
0x14000c472  call    cs:__imp_ExAllocatePool2
0x14000c479  nop     dword ptr [rax+rax+00h]
0x14000c47e  mov     rbx, rax
0x14000c481  test    rax, rax
0x14000c484  jnz     short loc_14000C4C9
0x14000c486  mov     eax, cs:dword_140019000
0x14000c48c  mov     ecx, 0C0000017h; int
0x14000c491  mov     edi, ecx
0x14000c493  cmp     eax, 3
0x14000c496  jbe     loc_14000C5E8
0x14000c49c  lea     rax, [rbp+var_40]
0x14000c4a0  mov     [rbp+var_40], ecx
0x14000c4a3  mov     [rbp+var_18], rax
0x14000c4a7  lea     rdx, byte_140016D91; int
0x14000c4ae  lea     rax, [rbp+var_38]
0x14000c4b2  mov     [rbp+var_10], 4
0x14000c4ba  mov     [rsp+70h+var_48], rax; PEVENT_DATA_DESCRIPTOR
0x14000c4bf  call    _tlgWriteTransfer_EtwWriteTransfer
0x14000c4c4  jmp     loc_14000C5E8
0x14000c4c9  mov     [rax+50h], r14d
0x14000c4cd  mov     r8d, 4E736642h
0x14000c4d3  mov     byte ptr [rax+28h], 0
0x14000c4d7  mov     r14d, 2
0x14000c4dd  mov     qword ptr [rax+30h], 0
0x14000c4e5  mov     rcx, r12
0x14000c4e8  movzx   edx, word ptr [rdi]
0x14000c4eb  add     rdx, r14
0x14000c4ee  call    cs:__imp_ExAllocatePool2
0x14000c4f5  nop     dword ptr [rax+rax+00h]
0x14000c4fa  mov     [rbx+48h], rax
0x14000c4fe  test    rax, rax
0x14000c501  jnz     short loc_14000C521
0x14000c503  mov     eax, cs:dword_140019000
0x14000c509  mov     ecx, 0C0000017h
0x14000c50e  mov     edi, ecx
0x14000c510  cmp     eax, 3
0x14000c513  jbe     loc_14000C5D7
0x14000c519  mov     [rbp+var_40], ecx
0x14000c51c  jmp     loc_14000C5B2
0x14000c521  movzx   eax, word ptr [rdi]
0x14000c524  lea     rcx, [rbx+40h]; DestinationString
0x14000c528  mov     [rcx], ax
0x14000c52b  mov     rdx, rdi; SourceString
0x14000c52e  movzx   eax, word ptr [rdi]
0x14000c531  add     ax, r14w
0x14000c535  mov     [rbx+42h], ax
0x14000c539  call    cs:__imp_RtlCopyUnicodeString
0x14000c540  nop     dword ptr [rax+rax+00h]
0x14000c545  mov     edx, 28h ; '('
0x14000c54a  mov     r8d, 54736642h
0x14000c550  mov     rcx, r12
0x14000c553  call    cs:__imp_ExAllocatePool2
0x14000c55a  nop     dword ptr [rax+rax+00h]
0x14000c55f  lea     rdi, [rbx+58h]
0x14000c563  mov     [rdi], rax
0x14000c566  test    rax, rax
0x14000c569  jz      short loc_14000C503
0x14000c56b  xor     r8d, r8d; Flags
0x14000c56e  xor     edx, edx; Shift
0x14000c570  mov     rcx, rdi; HashTable
0x14000c573  call    cs:__imp_RtlCreateHashTable
0x14000c57a  nop     dword ptr [rax+rax+00h]
0x14000c57f  test    al, al
0x14000c581  jnz     loc_14000C62A
0x14000c587  mov     rcx, [rdi]; P
0x14000c58a  xor     edx, edx; Tag
0x14000c58c  call    cs:__imp_ExFreePoolWithTag
0x14000c593  nop     dword ptr [rax+rax+00h]
0x14000c598  mov     qword ptr [rdi], 0
0x14000c59f  mov     edi, 0C0000001h
0x14000c5a4  mov     eax, cs:dword_140019000
0x14000c5aa  cmp     eax, 3
0x14000c5ad  jbe     short loc_14000C5D7
0x14000c5af  mov     [rbp+var_40], edi
0x14000c5b2  lea     rax, [rbp+var_40]
0x14000c5b6  mov     [rbp+var_10], 4
0x14000c5be  mov     [rbp+var_18], rax
0x14000c5c2  lea     rdx, byte_140016D91; int
0x14000c5c9  lea     rax, [rbp+var_38]
0x14000c5cd  mov     [rsp+70h+var_48], rax; PEVENT_DATA_DESCRIPTOR
0x14000c5d2  call    _tlgWriteTransfer_EtwWriteTransfer
0x14000c5d7  xor     edx, edx; Tag
0x14000c5d9  mov     rcx, rbx; P
0x14000c5dc  call    cs:__imp_ExFreePoolWithTag
0x14000c5e3  nop     dword ptr [rax+rax+00h]
0x14000c5e8  mov     rcx, [rbx+48h]; P
0x14000c5ec  test    rcx, rcx
0x14000c5ef  jz      short loc_14000C5FF
0x14000c5f1  xor     edx, edx; Tag
0x14000c5f3  call    cs:__imp_ExFreePoolWithTag
0x14000c5fa  nop     dword ptr [rax+rax+00h]
0x14000c5ff  mov     rcx, [rbx+58h]; HashTable
0x14000c603  test    rcx, rcx
0x14000c606  jz      short loc_14000C626
0x14000c608  call    cs:__imp_RtlDeleteHashTable
0x14000c60f  nop     dword ptr [rax+rax+00h]
0x14000c614  mov     rcx, [rbx+58h]; P
0x14000c618  xor     edx, edx; Tag
0x14000c61a  call    cs:__imp_ExFreePoolWithTag
0x14000c621  nop     dword ptr [rax+rax+00h]
0x14000c626  xor     ebx, ebx
0x14000c628  jmp     short loc_14000C62C
0x14000c62a  xor     edi, edi
0x14000c62c  mov     [rsi], rbx
0x14000c62f  mov     eax, edi
0x14000c631  mov     rcx, [rbp+var_8]
0x14000c635  xor     rcx, rsp; StackCookie
0x14000c638  call    __security_check_cookie
0x14000c63d  mov     rbx, [rsp+70h+arg_8]
0x14000c645  add     rsp, 70h
0x14000c649  pop     r14
0x14000c64b  pop     r12
0x14000c64d  pop     rdi
0x14000c64e  pop     rsi
0x14000c64f  pop     rbp
0x14000c650  retn
```
