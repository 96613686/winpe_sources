# XPathNavigatorInternal::UpdateState(void)

- ea: `0x18000e72c`
- end: `0x18000e774`
- name: `?UpdateState@XPathNavigatorInternal@@AEAAJXZ`
- size: `72`
- prototype: `__int64 __fastcall(XPathNavigatorInternal *__hidden this)`
- caller_count: `4`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x18000e5ac`
- `0x18000e668`
- `0x18000e6a8`
- `0x18000e6e8`

## callees

- `0x18000e72c`
- `0x180012010`

## pseudocode

```c
__int64 __fastcall XPathNavigatorInternal::UpdateState(XPathNavigatorInternal *this)
{
  _DWORD *v1; // rdx
  __int64 v3; // rcx
  __int64 result; // rax
  int v5; // eax
  unsigned int v6; // ecx

  v1 = (_DWORD *)((char *)this + 12);
  v3 = *(_QWORD *)this;
  *v1 = 7;
  result = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v3 + 40LL))(v3);
  if ( (int)result >= 0 )
  {
    v5 = (*(__int64 (__fastcall **)(_QWORD, char *))(**(_QWORD **)this + 32LL))(*(_QWORD *)this, (char *)this + 8);
    v6 = 0;
    if ( v5 < 0 )
      return (unsigned int)v5;
    return v6;
  }
  return result;
}

```

## disassembly

```asm
0x18000e72c  push    rbx
0x18000e72e  sub     rsp, 20h
0x18000e732  lea     rdx, [rcx+0Ch]
0x18000e736  mov     rbx, rcx
0x18000e739  mov     rcx, [rcx]
0x18000e73c  mov     dword ptr [rdx], 7
0x18000e742  mov     rax, [rcx]
0x18000e745  mov     rax, [rax+28h]
0x18000e749  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e74e  test    eax, eax
0x18000e750  js      short loc_18000E76E
0x18000e752  mov     rcx, [rbx]
0x18000e755  lea     rdx, [rbx+8]
0x18000e759  mov     rax, [rcx]
0x18000e75c  mov     rax, [rax+20h]
0x18000e760  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e765  xor     ecx, ecx
0x18000e767  test    eax, eax
0x18000e769  cmovs   ecx, eax
0x18000e76c  mov     eax, ecx
0x18000e76e  add     rsp, 20h
0x18000e772  pop     rbx
0x18000e773  retn
```
