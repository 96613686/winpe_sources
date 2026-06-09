# CComBase::NDRelease(void)

- ea: `0x180009170`
- end: `0x1800091a1`
- name: `?NDRelease@CComBase@@UEAAKXZ`
- size: `49`
- prototype: `unsigned int __fastcall(CComBase *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180009170`
- `0x180022010`

## pseudocode

```c
__int64 __fastcall CComBase::NDRelease(CComBase *this)
{
  __int64 result; // rax

  result = (unsigned int)_InterlockedDecrement((volatile signed __int32 *)this + 4);
  if ( !(_DWORD)result )
  {
    ++*((_DWORD *)this + 4);
    (*(void (__fastcall **)(CComBase *))(*(_QWORD *)this + 24LL))(this);
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x180009170  sub     rsp, 28h
0x180009174  or      eax, 0FFFFFFFFh
0x180009177  lock xadd [rcx+10h], eax
0x18000917c  sub     eax, 1
0x18000917f  jnz     short loc_18000919C
0x180009181  mov     eax, [rcx+10h]
0x180009184  mov     edx, 1
0x180009189  add     eax, edx
0x18000918b  mov     [rcx+10h], eax
0x18000918e  mov     rax, [rcx]
0x180009191  mov     rax, [rax+18h]
0x180009195  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000919a  xor     eax, eax
0x18000919c  add     rsp, 28h
0x1800091a0  retn
```
