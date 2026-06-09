# ElementNode::AppendIdentifyingPredicate(ConfigTreeBase *,STRU &)

- ea: `0x18000ab84`
- end: `0x18000ac4a`
- name: `?AppendIdentifyingPredicate@ElementNode@@IEAAXPEAVConfigTreeBase@@AEAVSTRU@@@Z`
- size: `198`
- prototype: `void __fastcall(ElementNode *__hidden this, struct ConfigTreeBase *, struct STRU *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18000b7a0`

## callees

- `0x18000ab38`
- `0x18000ab84`
- `0x18000c09c`
- `0x180012f3c`

## pseudocode

```c
void __fastcall ElementNode::AppendIdentifyingPredicate(
        ElementNode *this,
        struct ConfigTreeBase *a2,
        struct STRU *a3,
        unsigned int a4)
{
  int v7; // eax
  unsigned int v8; // r9d
  int v9; // eax
  int pExceptionObject; // [rsp+78h] [rbp+20h] BYREF

  v7 = STRU::Append(a3, L"[", 0, a4);
  if ( v7 < 0 )
  {
    pExceptionObject = v7;
    throw (long *)&pExceptionObject;
  }
  if ( !(unsigned __int8)PropertyCollection::TryAppendPredicateWithSelectProperties(
                           (ElementNode *)((char *)this + 88),
                           a2,
                           this,
                           a3,
                           (bool (*)(struct PropertyNode *))PropertyCollection::IsCollectionKeyProperty)
    && !(unsigned __int8)PropertyCollection::TryAppendPredicateWithSelectProperties(
                           (ElementNode *)((char *)this + 88),
                           a2,
                           this,
                           a3,
                           0) )
  {
    STRU::Append(a3, L"1", 0, v8);
  }
  v9 = STRU::Append(a3, L"]", 0, v8);
  if ( v9 < 0 )
  {
    pExceptionObject = v9;
    throw (long *)&pExceptionObject;
  }
}

```

## disassembly

```asm
0x18000ab84  push    rbx
0x18000ab86  push    rbp
0x18000ab87  push    rsi
0x18000ab88  push    rdi
0x18000ab89  sub     rsp, 38h
0x18000ab8d  mov     rbx, r8
0x18000ab90  mov     rsi, rdx
0x18000ab93  mov     rdi, rcx
0x18000ab96  lea     rdx, asc_1800185F4; "["
0x18000ab9d  mov     rcx, rbx; this
0x18000aba0  xor     r8d, r8d; unsigned int
0x18000aba3  call    ?Append@STRU@@QEAAJPEBGKK@Z; STRU::Append(ushort const *,ulong,ulong)
0x18000aba8  test    eax, eax
0x18000abaa  jns     short loc_18000ABC2
0x18000abac  lea     rdx, _TI1J; pThrowInfo
0x18000abb3  mov     [rsp+58h+pExceptionObject], eax
0x18000abb7  lea     rcx, [rsp+58h+pExceptionObject]; pExceptionObject
0x18000abbc  call    _CxxThrowException_0
0x18000abc2  lea     rax, ?IsCollectionKeyProperty@PropertyCollection@@CA_NPEAVPropertyNode@@@Z; PropertyCollection::IsCollectionKeyProperty(PropertyNode *)
0x18000abc9  mov     r9, rbx; struct STRU *
0x18000abcc  mov     r8, rdi; struct ElementNode *
0x18000abcf  mov     [rsp+58h+var_38], rax; bool (*)(struct PropertyNode *)
0x18000abd4  mov     rdx, rsi; struct ConfigTreeBase *
0x18000abd7  lea     rcx, [rdi+58h]; this
0x18000abdb  call    ?TryAppendPredicateWithSelectProperties@PropertyCollection@@AEAA_NPEAVConfigTreeBase@@PEAVElementNode@@AEAVSTRU@@P6A_NPEAVPropertyNode@@@Z@Z; PropertyCollection::TryAppendPredicateWithSelectProperties(ConfigTreeBase *,ElementNode *,STRU &,bool (*)(PropertyNode *))
0x18000abe0  test    al, al
0x18000abe2  jnz     short loc_18000AC15
0x18000abe4  mov     r9, rbx; struct STRU *
0x18000abe7  mov     [rsp+58h+var_38], 0; bool (*)(struct PropertyNode *)
0x18000abf0  mov     r8, rdi; struct ElementNode *
0x18000abf3  lea     rcx, [rdi+58h]; this
0x18000abf7  mov     rdx, rsi; struct ConfigTreeBase *
0x18000abfa  call    ?TryAppendPredicateWithSelectProperties@PropertyCollection@@AEAA_NPEAVConfigTreeBase@@PEAVElementNode@@AEAVSTRU@@P6A_NPEAVPropertyNode@@@Z@Z; PropertyCollection::TryAppendPredicateWithSelectProperties(ConfigTreeBase *,ElementNode *,STRU &,bool (*)(PropertyNode *))
0x18000abff  test    al, al
0x18000ac01  jnz     short loc_18000AC15
0x18000ac03  xor     r8d, r8d; unsigned int
0x18000ac06  lea     rdx, a1; "1"
0x18000ac0d  mov     rcx, rbx; this
0x18000ac10  call    ?Append@STRU@@QEAAJPEBGKK@Z; STRU::Append(ushort const *,ulong,ulong)
0x18000ac15  xor     r8d, r8d; unsigned int
0x18000ac18  lea     rdx, asc_1800185F8; "]"
0x18000ac1f  mov     rcx, rbx; this
0x18000ac22  call    ?Append@STRU@@QEAAJPEBGKK@Z; STRU::Append(ushort const *,ulong,ulong)
0x18000ac27  test    eax, eax
0x18000ac29  jns     short loc_18000AC41
0x18000ac2b  lea     rdx, _TI1J; pThrowInfo
0x18000ac32  mov     [rsp+58h+pExceptionObject], eax
0x18000ac36  lea     rcx, [rsp+58h+pExceptionObject]; pExceptionObject
0x18000ac3b  call    _CxxThrowException_0
0x18000ac41  add     rsp, 38h
0x18000ac45  pop     rdi
0x18000ac46  pop     rsi
0x18000ac47  pop     rbp
0x18000ac48  pop     rbx
0x18000ac49  retn
```
