# CWMDSPComBase::NDRelease(void)

- ea: `0x180008400`
- end: `0x180008431`
- name: `?NDRelease@CWMDSPComBase@@UEAAKXZ`
- size: `49`
- prototype: `unsigned int __fastcall(CWMDSPComBase *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180008400`
- `0x180085010`

## pseudocode

```c
__int64 __fastcall CWMDSPComBase::NDRelease(CWMDSPComBase *this)
{
  __int64 result; // rax

  result = (unsigned int)_InterlockedDecrement((volatile signed __int32 *)this + 4);
  if ( !(_DWORD)result )
  {
    ++*((_DWORD *)this + 4);
    (*(void (__fastcall **)(CWMDSPComBase *))(*(_QWORD *)this + 24LL))(this);
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x180008400  sub     rsp, 28h
0x180008404  or      eax, 0FFFFFFFFh
0x180008407  lock xadd [rcx+10h], eax
0x18000840c  sub     eax, 1
0x18000840f  jnz     short loc_18000842C
0x180008411  mov     eax, [rcx+10h]
0x180008414  mov     edx, 1
0x180008419  add     eax, edx
0x18000841b  mov     [rcx+10h], eax
0x18000841e  mov     rax, [rcx]
0x180008421  mov     rax, [rax+18h]
0x180008425  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000842a  xor     eax, eax
0x18000842c  add     rsp, 28h
0x180008430  retn
```
