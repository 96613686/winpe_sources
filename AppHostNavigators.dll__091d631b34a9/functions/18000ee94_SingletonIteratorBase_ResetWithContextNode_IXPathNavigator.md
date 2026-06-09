# SingletonIteratorBase::ResetWithContextNode(IXPathNavigator *)

- ea: `0x18000ee94`
- end: `0x18000eee8`
- name: `?ResetWithContextNode@SingletonIteratorBase@@IEAAJPEAUIXPathNavigator@@@Z`
- size: `84`
- prototype: `__int64 __fastcall(SingletonIteratorBase *__hidden this, struct IXPathNavigator *)`
- caller_count: `3`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000eac0`
- `0x18000ebb0`
- `0x18000ec40`

## callees

- `0x180007aac`
- `0x18000ee94`
- `0x180014010`

## pseudocode

```c
__int64 __fastcall SingletonIteratorBase::ResetWithContextNode(SingletonIteratorBase *this, struct IXPathNavigator *a2)
{
  char *v2; // rbx
  int v4; // eax
  unsigned int v5; // ecx

  v2 = (char *)this + 24;
  *((_BYTE *)this + 16) = 0;
  if ( *((_QWORD *)this + 3) )
    ATL::AtlComPtrAssign((struct IUnknown **)this + 3, 0);
  if ( !a2 )
    return 0;
  v4 = (*(__int64 (__fastcall **)(struct IXPathNavigator *, char *))(*(_QWORD *)a2 + 88LL))(a2, v2);
  v5 = 0;
  if ( v4 < 0 )
    return (unsigned int)v4;
  return v5;
}

```

## disassembly

```asm
0x18000ee94  mov     [rsp+arg_0], rbx
0x18000ee99  push    rdi
0x18000ee9a  sub     rsp, 20h
0x18000ee9e  lea     rbx, [rcx+18h]
0x18000eea2  mov     byte ptr [rcx+10h], 0
0x18000eea6  cmp     qword ptr [rbx], 0
0x18000eeaa  mov     rdi, rdx
0x18000eead  jz      short loc_18000EEB9
0x18000eeaf  xor     edx, edx; struct IUnknown *
0x18000eeb1  mov     rcx, rbx; struct IUnknown **
0x18000eeb4  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x18000eeb9  test    rdi, rdi
0x18000eebc  jz      short loc_18000EEDB
0x18000eebe  mov     rax, [rdi]
0x18000eec1  mov     rdx, rbx
0x18000eec4  mov     rcx, rdi
0x18000eec7  mov     rax, [rax+58h]
0x18000eecb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000eed0  xor     ecx, ecx
0x18000eed2  test    eax, eax
0x18000eed4  cmovs   ecx, eax
0x18000eed7  mov     eax, ecx
0x18000eed9  jmp     short loc_18000EEDD
0x18000eedb  xor     eax, eax
0x18000eedd  mov     rbx, [rsp+28h+arg_0]
0x18000eee2  add     rsp, 20h
0x18000eee6  pop     rdi
0x18000eee7  retn
```
