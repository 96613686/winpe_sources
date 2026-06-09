# XPathNavigatorInternal::MoveNavigatorAndUpdateState(ushort const *,ushort const *,long (IXPathNavigator::*)(ushort const *,ushort const *))

- ea: `0x18000e6a8`
- end: `0x18000e6e0`
- name: `?MoveNavigatorAndUpdateState@XPathNavigatorInternal@@AEAAJPEBG0P8IXPathNavigator@@EAAJ00@Z@Z`
- size: `56`
- prototype: `__int64 __fastcall(XPathNavigatorInternal *this)`
- caller_count: `8`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x18000cf20`
- `0x18000cf80`
- `0x18000d030`
- `0x18000d1c0`
- `0x18000d200`
- `0x18000d2a0`
- `0x18000d300`
- `0x18000d5a4`

## callees

- `0x18000e6a8`
- `0x18000e72c`
- `0x180012010`

## pseudocode

```c
__int64 __fastcall XPathNavigatorInternal::MoveNavigatorAndUpdateState(
        XPathNavigatorInternal *this,
        __int64 a2,
        __int64 a3,
        __int64 (__fastcall *a4)(_QWORD))
{
  __int64 result; // rax
  unsigned int v6; // ebx
  int updated; // eax

  result = a4(*(_QWORD *)this);
  v6 = result;
  if ( !(_DWORD)result )
  {
    updated = XPathNavigatorInternal::UpdateState(this);
    if ( updated < 0 )
      return (unsigned int)updated;
    return v6;
  }
  return result;
}

```

## disassembly

```asm
0x18000e6a8  mov     [rsp+arg_0], rbx
0x18000e6ad  push    rdi
0x18000e6ae  sub     rsp, 20h
0x18000e6b2  mov     rdi, rcx
0x18000e6b5  mov     rax, r9
0x18000e6b8  mov     rcx, [rcx]
0x18000e6bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e6c0  mov     ebx, eax
0x18000e6c2  test    eax, eax
0x18000e6c4  jnz     short loc_18000E6D5
0x18000e6c6  mov     rcx, rdi; this
0x18000e6c9  call    ?UpdateState@XPathNavigatorInternal@@AEAAJXZ; XPathNavigatorInternal::UpdateState(void)
0x18000e6ce  test    eax, eax
0x18000e6d0  cmovs   ebx, eax
0x18000e6d3  mov     eax, ebx
0x18000e6d5  mov     rbx, [rsp+28h+arg_0]
0x18000e6da  add     rsp, 20h
0x18000e6de  pop     rdi
0x18000e6df  retn
```
