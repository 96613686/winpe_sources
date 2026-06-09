# XPathNavigatorInternal::InitializeAsValidPosition(IXPathNavigator *)

- ea: `0x18000e5ac`
- end: `0x18000e5da`
- name: `?InitializeAsValidPosition@XPathNavigatorInternal@@QEAAJPEAUIXPathNavigator@@@Z`
- size: `46`
- prototype: `__int64 __fastcall(XPathNavigatorInternal *__hidden this, struct IXPathNavigator *)`
- caller_count: `2`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180002dc0`
- `0x18000b170`

## callees

- `0x180004b84`
- `0x18000e5ac`
- `0x18000e72c`

## pseudocode

```c
__int64 __fastcall XPathNavigatorInternal::InitializeAsValidPosition(XPathNavigatorInternal *this, struct IUnknown *a2)
{
  int updated; // ecx
  __int64 result; // rax

  *((_BYTE *)this + 16) = 1;
  if ( *(struct IUnknown **)this != a2 )
    ATL::AtlComPtrAssign((struct IUnknown **)this, a2);
  updated = XPathNavigatorInternal::UpdateState(this);
  result = 0;
  if ( updated < 0 )
    return (unsigned int)updated;
  return result;
}

```

## disassembly

```asm
0x18000e5ac  push    rbx
0x18000e5ae  sub     rsp, 20h
0x18000e5b2  mov     byte ptr [rcx+10h], 1
0x18000e5b6  mov     rbx, rcx
0x18000e5b9  cmp     [rcx], rdx
0x18000e5bc  jz      short loc_18000E5C3
0x18000e5be  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x18000e5c3  mov     rcx, rbx; this
0x18000e5c6  call    ?UpdateState@XPathNavigatorInternal@@AEAAJXZ; XPathNavigatorInternal::UpdateState(void)
0x18000e5cb  mov     ecx, eax
0x18000e5cd  xor     eax, eax
0x18000e5cf  test    ecx, ecx
0x18000e5d1  cmovs   eax, ecx
0x18000e5d4  add     rsp, 20h
0x18000e5d8  pop     rbx
0x18000e5d9  retn
```
