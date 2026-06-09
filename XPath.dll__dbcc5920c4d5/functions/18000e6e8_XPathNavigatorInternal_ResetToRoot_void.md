# XPathNavigatorInternal::ResetToRoot(void)

- ea: `0x18000e6e8`
- end: `0x18000e726`
- name: `?ResetToRoot@XPathNavigatorInternal@@QEAAJXZ`
- size: `62`
- prototype: `__int64 __fastcall(XPathNavigatorInternal *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x180005124`
- `0x18000d7f0`

## callees

- `0x18000e6e8`
- `0x18000e72c`
- `0x180012010`

## pseudocode

```c
__int64 __fastcall XPathNavigatorInternal::ResetToRoot(XPathNavigatorInternal *this)
{
  __int64 i; // rcx
  __int64 result; // rax

  for ( i = *(_QWORD *)this; ; i = *(_QWORD *)this )
  {
    result = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)i + 160LL))(i);
    if ( (int)result < 0 )
      break;
    if ( (_DWORD)result )
    {
      result = XPathNavigatorInternal::UpdateState(this);
      if ( (int)result >= 0 )
      {
        *((_BYTE *)this + 16) = 1;
        return 0;
      }
      return result;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18000e6e8  push    rbx
0x18000e6ea  sub     rsp, 20h
0x18000e6ee  mov     rbx, rcx
0x18000e6f1  mov     rcx, [rcx]
0x18000e6f4  mov     rax, [rcx]
0x18000e6f7  mov     rax, [rax+0A0h]
0x18000e6fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e703  test    eax, eax
0x18000e705  js      short loc_18000E720
0x18000e707  jnz     short loc_18000E70E
0x18000e709  mov     rcx, [rbx]
0x18000e70c  jmp     short loc_18000E6F4
0x18000e70e  mov     rcx, rbx; this
0x18000e711  call    ?UpdateState@XPathNavigatorInternal@@AEAAJXZ; XPathNavigatorInternal::UpdateState(void)
0x18000e716  test    eax, eax
0x18000e718  js      short loc_18000E720
0x18000e71a  mov     byte ptr [rbx+10h], 1
0x18000e71e  xor     eax, eax
0x18000e720  add     rsp, 20h
0x18000e724  pop     rbx
0x18000e725  retn
```
