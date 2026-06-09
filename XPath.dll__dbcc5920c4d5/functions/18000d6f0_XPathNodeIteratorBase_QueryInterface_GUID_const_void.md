# XPathNodeIteratorBase::QueryInterface(_GUID const &,void * *)

- ea: `0x18000d6f0`
- end: `0x18000d764`
- name: `?QueryInterface@XPathNodeIteratorBase@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `116`
- prototype: `__int64 __fastcall(XPathNodeIteratorBase *__hidden this, const struct _GUID *, void **)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180005440`
- `0x18000d690`

## callees

- `0x180005390`
- `0x18000d6f0`
- `0x180012010`

## pseudocode

```c
__int64 __fastcall XPathNodeIteratorBase::QueryInterface(
        struct ISupportErrorInfo *this,
        struct _GUID *a2,
        struct ISupportErrorInfo **a3)
{
  __int64 v4; // rax
  __int64 v5; // rax

  if ( !a3 )
    return 2147942487LL;
  v4 = *(_QWORD *)&a2->Data1 - *(_QWORD *)&IID_IUnknown.Data1;
  if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&IID_IUnknown.Data1 )
    v4 = *(_QWORD *)a2->Data4 - *(_QWORD *)IID_IUnknown.Data4;
  if ( !v4 )
    goto LABEL_9;
  v5 = *(_QWORD *)&a2->Data1 - *(_QWORD *)&IID_IXPathNodeIterator.Data1;
  if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&IID_IXPathNodeIterator.Data1 )
    v5 = *(_QWORD *)a2->Data4 - *(_QWORD *)IID_IXPathNodeIterator.Data4;
  if ( !v5 )
LABEL_9:
    *a3 = this;
  if ( !*a3 )
    return SimpleIUnknownImpl<IXPathExpression>::QueryInterface(this + 1, a2, a3);
  ((void (__fastcall *)(struct ISupportErrorInfo *))this->lpVtbl->AddRef)(this);
  return 0;
}

```

## disassembly

```asm
0x18000d6f0  sub     rsp, 28h
0x18000d6f4  test    r8, r8
0x18000d6f7  jnz     short loc_18000D703
0x18000d6f9  mov     eax, 80070057h
0x18000d6fe  add     rsp, 28h
0x18000d702  retn
0x18000d703  mov     rax, [rdx]
0x18000d706  sub     rax, qword ptr cs:IID_IUnknown.Data1
0x18000d70d  jnz     short loc_18000D71A
0x18000d70f  mov     rax, [rdx+8]
0x18000d713  sub     rax, qword ptr cs:IID_IUnknown.Data4
0x18000d71a  test    rax, rax
0x18000d71d  jz      short loc_18000D73B
0x18000d71f  mov     rax, [rdx]
0x18000d722  sub     rax, qword ptr cs:IID_IXPathNodeIterator.Data1
0x18000d729  jnz     short loc_18000D736
0x18000d72b  mov     rax, [rdx+8]
0x18000d72f  sub     rax, qword ptr cs:IID_IXPathNodeIterator.Data4
0x18000d736  test    rax, rax
0x18000d739  jnz     short loc_18000D73E
0x18000d73b  mov     [r8], rcx
0x18000d73e  cmp     qword ptr [r8], 0
0x18000d742  jz      short loc_18000D757
0x18000d744  mov     rax, [rcx]
0x18000d747  mov     rax, [rax+8]
0x18000d74b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d750  xor     eax, eax
0x18000d752  add     rsp, 28h
0x18000d756  retn
0x18000d757  add     rcx, 8
0x18000d75b  add     rsp, 28h
0x18000d75f  jmp     ?QueryInterface@?$SimpleIUnknownImpl@UIXPathExpression@@@@UEAAJAEBU_GUID@@PEAPEAX@Z; SimpleIUnknownImpl<IXPathExpression>::QueryInterface(_GUID const &,void * *)
```
