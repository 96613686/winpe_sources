# BfeFindSidEntry

- ea: `0x180036870`
- end: `0x180036917`
- name: `BfeFindSidEntry`
- size: `167`
- prototype: `__int64 __fastcall(PSID Sid2)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180066a78`

## callees

- `0x180036870`
- `0x180036920`
- `0x180058b30`

## import_xrefs

- `ntdll!RtlEqualSid` at `0x1800368d7`
- `ntdll!RtlEqualSid` at `0x1800368d7`
- `ntdll!RtlLookupEntryHashTable` at `0x1800368c2`
- `ntdll!RtlLookupEntryHashTable` at `0x1800368c2`
- `ntdll!RtlGetNextEntryHashTable` at `0x1800368ed`
- `ntdll!RtlGetNextEntryHashTable` at `0x1800368ed`

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
  for ( i = RtlLookupEntryHashTable(&qword_1800F2668[262], v4, &v8);
        ;
        i = RtlGetNextEntryHashTable(&qword_1800F2668[262], &v8) )
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
0x180036870  mov     [rsp+arg_10], rbx
0x180036875  mov     [rsp+arg_18], rsi
0x18003687a  push    rdi
0x18003687b  sub     rsp, 40h
0x18003687f  mov     rax, cs:__security_cookie
0x180036886  xor     rax, rsp
0x180036889  mov     [rsp+48h+var_10], rax
0x18003688e  xorps   xmm0, xmm0
0x180036891  xor     eax, eax
0x180036893  movups  [rsp+48h+var_28], xmm0
0x180036898  mov     [rsp+48h+var_18], rax
0x18003689d  mov     rdi, rdx
0x1800368a0  mov     rsi, rcx
0x1800368a3  call    BfeComputeSidSignature
0x1800368a8  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1800368ac  lea     r8, [rsp+48h+var_28]
0x1800368b1  test    rax, rax
0x1800368b4  cmovz   rax, rcx
0x1800368b8  lea     rcx, qword_1800F2668+830h
0x1800368bf  mov     rdx, rax
0x1800368c2  call    cs:__imp_RtlLookupEntryHashTable
0x1800368c8  mov     rbx, rax
0x1800368cb  test    rax, rax
0x1800368ce  jz      short loc_1800368F8
0x1800368d0  mov     rcx, [rax+18h]; Sid1
0x1800368d4  mov     rdx, rsi; Sid2
0x1800368d7  call    cs:__imp_RtlEqualSid
0x1800368dd  test    al, al
0x1800368df  jnz     short loc_1800368F5
0x1800368e1  lea     rdx, [rsp+48h+var_28]
0x1800368e6  lea     rcx, qword_1800F2668+830h
0x1800368ed  call    cs:__imp_RtlGetNextEntryHashTable
0x1800368f3  jmp     short loc_1800368C8
0x1800368f5  mov     [rdi], rbx
0x1800368f8  xor     eax, eax
0x1800368fa  mov     rcx, [rsp+48h+var_10]
0x1800368ff  xor     rcx, rsp; StackCookie
0x180036902  call    __security_check_cookie
0x180036907  mov     rbx, [rsp+48h+arg_10]
0x18003690c  mov     rsi, [rsp+48h+arg_18]
0x180036911  add     rsp, 40h
0x180036915  pop     rdi
0x180036916  retn
```
