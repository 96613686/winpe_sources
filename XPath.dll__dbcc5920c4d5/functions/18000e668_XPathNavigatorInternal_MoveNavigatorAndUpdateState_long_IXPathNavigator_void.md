# XPathNavigatorInternal::MoveNavigatorAndUpdateState(long (IXPathNavigator::*)(void))

- ea: `0x18000e668`
- end: `0x18000e6a0`
- name: `?MoveNavigatorAndUpdateState@XPathNavigatorInternal@@AEAAJP8IXPathNavigator@@EAAJXZ@Z`
- size: `56`
- prototype: `__int64 __fastcall(XPathNavigatorInternal *this)`
- caller_count: `5`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x18000d030`
- `0x18000d140`
- `0x18000d190`
- `0x18000d2d0`
- `0x18000d5a4`

## callees

- `0x18000e668`
- `0x18000e72c`
- `0x180012010`

## pseudocode

```c
__int64 __fastcall XPathNavigatorInternal::MoveNavigatorAndUpdateState(
        XPathNavigatorInternal *this,
        __int64 (__fastcall *a2)(_QWORD))
{
  __int64 result; // rax
  unsigned int v4; // ebx
  int updated; // eax

  result = a2(*(_QWORD *)this);
  v4 = result;
  if ( !(_DWORD)result )
  {
    updated = XPathNavigatorInternal::UpdateState(this);
    if ( updated < 0 )
      return (unsigned int)updated;
    return v4;
  }
  return result;
}

```

## disassembly

```asm
0x18000e668  mov     [rsp+arg_0], rbx
0x18000e66d  push    rdi
0x18000e66e  sub     rsp, 20h
0x18000e672  mov     rdi, rcx
0x18000e675  mov     rax, rdx
0x18000e678  mov     rcx, [rcx]
0x18000e67b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e680  mov     ebx, eax
0x18000e682  test    eax, eax
0x18000e684  jnz     short loc_18000E695
0x18000e686  mov     rcx, rdi; this
0x18000e689  call    ?UpdateState@XPathNavigatorInternal@@AEAAJXZ; XPathNavigatorInternal::UpdateState(void)
0x18000e68e  test    eax, eax
0x18000e690  cmovs   ebx, eax
0x18000e693  mov     eax, ebx
0x18000e695  mov     rbx, [rsp+28h+arg_0]
0x18000e69a  add     rsp, 20h
0x18000e69e  pop     rdi
0x18000e69f  retn
```
