# BfeFindSidEntry

- ea: `0x180035574`
- end: `0x18003562e`
- name: `BfeFindSidEntry`
- size: `186`
- prototype: `__int64 __fastcall(PSID Sid2)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180068f68`

## callees

- `0x180035574`
- `0x180035634`
- `0x18005aa60`

## import_xrefs

- `ntdll!RtlEqualSid` at `0x1800355e1`
- `ntdll!RtlEqualSid` at `0x1800355e1`
- `ntdll!RtlLookupEntryHashTable` at `0x1800355c6`
- `ntdll!RtlLookupEntryHashTable` at `0x1800355c6`
- `ntdll!RtlGetNextEntryHashTable` at `0x1800355fd`
- `ntdll!RtlGetNextEntryHashTable` at `0x1800355fd`

## pseudocode

```c
__int64 __fastcall BfeFindSidEntry(PSID Sid2, __int64 *a2)
{
  __int64 v4; // rax
  __int64 i; // rax
  __int64 v6; // rbx
  __int128 v8; // [rsp+20h] [rbp-28h] BYREF
  __int64 v9; // [rsp+30h] [rbp-18h]

  v8 = 0;
  v9 = 0;
  v4 = BfeComputeSidSignature(Sid2);
  if ( !v4 )
    v4 = -1;
  for ( i = RtlLookupEntryHashTable(qword_1800F5EB8, v4, &v8); ; i = RtlGetNextEntryHashTable(qword_1800F5EB8, &v8) )
  {
    v6 = i;
    if ( !i )
      break;
    if ( RtlEqualSid(*(PSID *)(i + 24), Sid2) )
    {
      *a2 = v6;
      return 0;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180035574  mov     [rsp+arg_10], rbx
0x180035579  mov     [rsp+arg_18], rsi
0x18003557e  push    rdi
0x18003557f  sub     rsp, 40h
0x180035583  mov     rax, cs:__security_cookie
0x18003558a  xor     rax, rsp
0x18003558d  mov     [rsp+48h+var_10], rax
0x180035592  xorps   xmm0, xmm0
0x180035595  xor     eax, eax
0x180035597  movups  [rsp+48h+var_28], xmm0
0x18003559c  mov     [rsp+48h+var_18], rax
0x1800355a1  mov     rdi, rdx
0x1800355a4  mov     rsi, rcx
0x1800355a7  call    BfeComputeSidSignature
0x1800355ac  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1800355b0  lea     r8, [rsp+48h+var_28]
0x1800355b5  test    rax, rax
0x1800355b8  cmovz   rax, rcx
0x1800355bc  lea     rcx, qword_1800F5EB8
0x1800355c3  mov     rdx, rax
0x1800355c6  call    cs:__imp_RtlLookupEntryHashTable
0x1800355cd  nop     dword ptr [rax+rax+00h]
0x1800355d2  mov     rbx, rax
0x1800355d5  test    rax, rax
0x1800355d8  jz      short loc_18003560E
0x1800355da  mov     rcx, [rax+18h]; Sid1
0x1800355de  mov     rdx, rsi; Sid2
0x1800355e1  call    cs:__imp_RtlEqualSid
0x1800355e8  nop     dword ptr [rax+rax+00h]
0x1800355ed  test    al, al
0x1800355ef  jnz     short loc_18003560B
0x1800355f1  lea     rdx, [rsp+48h+var_28]
0x1800355f6  lea     rcx, qword_1800F5EB8
0x1800355fd  call    cs:__imp_RtlGetNextEntryHashTable
0x180035604  nop     dword ptr [rax+rax+00h]
0x180035609  jmp     short loc_1800355D2
0x18003560b  mov     [rdi], rbx
0x18003560e  xor     eax, eax
0x180035610  mov     rcx, [rsp+48h+var_10]
0x180035615  xor     rcx, rsp; StackCookie
0x180035618  call    __security_check_cookie
0x18003561d  mov     rbx, [rsp+48h+arg_10]
0x180035622  mov     rsi, [rsp+48h+arg_18]
0x180035627  add     rsp, 40h
0x18003562b  pop     rdi
0x18003562c  retn
```
