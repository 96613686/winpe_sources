# StrMap::Find(ushort const *,ulong *)

- ea: `0x18001a0c8`
- end: `0x18001a14d`
- name: `?Find@StrMap@@QEBAPEAXPEBGPEAK@Z`
- size: `133`
- prototype: `void *__fastcall(StrMap *__hidden this, const unsigned __int16 *, unsigned int *)`
- caller_count: `15`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180007e04`
- `0x1800085a0`
- `0x18000bf50`
- `0x180019e14`
- `0x18001a154`
- `0x18001a184`
- `0x18001a25c`
- `0x18001b3ec`
- `0x18001b4e4`
- `0x18001b568`
- `0x18001b5ac`
- `0x18001b62c`
- `0x18001b6c4`
- `0x18001bc54`
- `0x18001bc84`

## callees

- `0x18001a0c8`
- `0x18001bb28`

## import_xrefs

- `msvcrt!bsearch` at `0x18001a11d`
- `msvcrt!bsearch` at `0x18001a11d`

## pseudocode

```c
_QWORD *__fastcall StrMap::Find(StrMap *this, const unsigned __int16 *a2, unsigned int *a3)
{
  size_t v6; // r8
  const void *v7; // rdx
  _QWORD *result; // rax
  _QWORD Key[3]; // [rsp+30h] [rbp-18h] BYREF

  if ( a3 )
    *a3 = 0;
  StrMap::Sort(this);
  v6 = *((int *)this + 2);
  v7 = *(const void **)this;
  Key[0] = a2;
  Key[1] = 0;
  result = bsearch(Key, v7, v6, 0x10u, (_CoreCrtNonSecureSearchSortCompareFunction)StrMap::Compare);
  if ( result )
  {
    if ( a3 )
      *a3 = ((__int64)result - *(_QWORD *)this) >> 4;
    return (_QWORD *)result[1];
  }
  return result;
}

```

## disassembly

```asm
0x18001a0c8  mov     [rsp+arg_0], rbx
0x18001a0cd  mov     [rsp+arg_8], rsi
0x18001a0d2  push    rdi
0x18001a0d3  sub     rsp, 40h
0x18001a0d7  mov     rbx, r8
0x18001a0da  mov     rsi, rdx
0x18001a0dd  mov     rdi, rcx
0x18001a0e0  test    r8, r8
0x18001a0e3  jz      short loc_18001A0EC
0x18001a0e5  mov     dword ptr [r8], 0
0x18001a0ec  call    ?Sort@StrMap@@IEBAXXZ; StrMap::Sort(void)
0x18001a0f1  movsxd  r8, dword ptr [rdi+8]; NumOfElements
0x18001a0f5  lea     rax, ?Compare@StrMap@@KAHPEBX0@Z; StrMap::Compare(void const *,void const *)
0x18001a0fc  mov     rdx, [rdi]; Base
0x18001a0ff  lea     rcx, [rsp+48h+Key]; Key
0x18001a104  mov     r9d, 10h; SizeOfElements
0x18001a10a  mov     [rsp+48h+CompareFunction], rax; CompareFunction
0x18001a10f  mov     [rsp+48h+Key], rsi
0x18001a114  mov     [rsp+48h+var_10], 0
0x18001a11d  call    cs:__imp_bsearch
0x18001a123  test    rax, rax
0x18001a126  jz      short loc_18001A13D
0x18001a128  test    rbx, rbx
0x18001a12b  jz      short loc_18001A139
0x18001a12d  mov     rcx, rax
0x18001a130  sub     rcx, [rdi]
0x18001a133  sar     rcx, 4
0x18001a137  mov     [rbx], ecx
0x18001a139  mov     rax, [rax+8]
0x18001a13d  mov     rbx, [rsp+48h+arg_0]
0x18001a142  mov     rsi, [rsp+48h+arg_8]
0x18001a147  add     rsp, 40h
0x18001a14b  pop     rdi
0x18001a14c  retn
```
