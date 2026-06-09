# RemoveFilterHashTableEntry

- ea: `0x14000ab5c`
- end: `0x14000ac3f`
- name: `RemoveFilterHashTableEntry`
- size: `227`
- prototype: `char __fastcall(void *, __int64, _QWORD *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x14000b280`

## callees

- `0x140001118`
- `0x14000164c`
- `0x140001a70`
- `0x14000aa30`
- `0x14000ab5c`

## string_xrefs

- `0x14000ab7d`: `UevFilter.RemoveHandleFromHashTable: Entry\n`
- `0x14000ac17`: `UevFilter.RemoveHandleFromHashTable: Exit\n`

## pseudocode

```c
char __fastcall RemoveFilterHashTableEntry(void *a1, __int64 a2, _QWORD *a3)
{
  unsigned int (__fastcall **v3)(__int64); // rdi
  char v6; // si
  __int64 v7; // r8
  unsigned int (__fastcall *v8)(__int64); // rax
  __int64 v9; // r14
  _QWORD *v10; // rcx
  unsigned int (__fastcall *v11)(__int64); // rdx
  PVOID P; // [rsp+40h] [rbp+8h] BYREF
  unsigned int (__fastcall *v14)(__int64); // [rsp+50h] [rbp+18h] BYREF

  P = a1;
  v3 = (unsigned int (__fastcall **)(__int64))::P;
  v6 = 0;
  DbgTrace(2, "UevFilter.RemoveHandleFromHashTable: Entry\n", (__int64)a3);
  if ( a3 )
    *a3 = 0;
  if ( v3 )
  {
    v8 = *v3;
    P = 0;
    v14 = 0;
    v9 = v8(a2);
    if ( FindTableEntryInFilterHashTable(v3, a2, (unsigned int (__fastcall **)(__int64))&P, &v14) )
    {
      v10 = P;
      if ( P )
      {
        v11 = v14;
        if ( v14 )
          *(_QWORD *)v14 = *(_QWORD *)P;
        else
          v3[v9 + 3] = 0;
        if ( a3 )
          *a3 = v10[2];
        FreeGenericBuffer(v10, (__int64)v11, v7);
        v6 = 1;
      }
    }
  }
  DbgTrace(2, "UevFilter.RemoveHandleFromHashTable: Exit\n", v7);
  return v6;
}

```

## disassembly

```asm
0x14000ab5c  mov     [rsp+arg_8], rbx
0x14000ab61  mov     [rsp+arg_18], rbp
0x14000ab66  mov     [rsp+P], rcx
0x14000ab6b  push    rsi
0x14000ab6c  push    rdi
0x14000ab6d  push    r14
0x14000ab6f  sub     rsp, 20h
0x14000ab73  mov     rdi, cs:P
0x14000ab7a  mov     rbp, rdx
0x14000ab7d  lea     rdx, aUevfilterRemov_0; "UevFilter.RemoveHandleFromHashTable: En"...
0x14000ab84  mov     ecx, 2
0x14000ab89  mov     rbx, r8
0x14000ab8c  xor     sil, sil
0x14000ab8f  call    DbgTrace
0x14000ab94  test    rbx, rbx
0x14000ab97  jz      short loc_14000ABA0
0x14000ab99  mov     qword ptr [rbx], 0
0x14000aba0  test    rdi, rdi
0x14000aba3  jz      short loc_14000AC17
0x14000aba5  mov     rax, [rdi]
0x14000aba8  mov     rcx, rbp
0x14000abab  mov     [rsp+38h+P], 0
0x14000abb4  mov     [rsp+38h+arg_10], 0
0x14000abbd  call    _guard_dispatch_icall
0x14000abc2  lea     r9, [rsp+38h+arg_10]
0x14000abc7  mov     r14d, eax
0x14000abca  lea     r8, [rsp+38h+P]
0x14000abcf  mov     rdx, rbp
0x14000abd2  mov     rcx, rdi
0x14000abd5  call    FindTableEntryInFilterHashTable
0x14000abda  test    al, al
0x14000abdc  jz      short loc_14000AC17
0x14000abde  mov     rcx, [rsp+38h+P]; P
0x14000abe3  test    rcx, rcx
0x14000abe6  jz      short loc_14000AC17
0x14000abe8  mov     rdx, [rsp+38h+arg_10]
0x14000abed  test    rdx, rdx
0x14000abf0  jz      short loc_14000ABFA
0x14000abf2  mov     rax, [rcx]
0x14000abf5  mov     [rdx], rax
0x14000abf8  jmp     short loc_14000AC03
0x14000abfa  mov     qword ptr [rdi+r14*8+18h], 0
0x14000ac03  test    rbx, rbx
0x14000ac06  jz      short loc_14000AC0F
0x14000ac08  mov     rax, [rcx+10h]
0x14000ac0c  mov     [rbx], rax
0x14000ac0f  call    FreeGenericBuffer
0x14000ac14  mov     sil, 1
0x14000ac17  lea     rdx, aUevfilterRemov; "UevFilter.RemoveHandleFromHashTable: Ex"...
0x14000ac1e  mov     ecx, 2
0x14000ac23  call    DbgTrace
0x14000ac28  mov     rbx, [rsp+38h+arg_8]
0x14000ac2d  mov     al, sil
0x14000ac30  mov     rbp, [rsp+38h+arg_18]
0x14000ac35  add     rsp, 20h
0x14000ac39  pop     r14
0x14000ac3b  pop     rdi
0x14000ac3c  pop     rsi
0x14000ac3d  retn
```
