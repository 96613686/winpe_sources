# CComBase::NDRelease(void)

- ea: `0x180008990`
- end: `0x1800089c3`
- name: `?NDRelease@CComBase@@UEAAKXZ`
- size: `51`
- prototype: `unsigned int __fastcall(CComBase *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180008990`
- `0x180085010`

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
0x180008990  sub     rsp, 28h
0x180008994  or      eax, 0FFFFFFFFh
0x180008997  lock xadd [rcx+10h], eax
0x18000899c  sub     eax, 1
0x18000899f  jz      short loc_1800089A6
0x1800089a1  add     rsp, 28h
0x1800089a5  retn
0x1800089a6  mov     eax, [rcx+10h]
0x1800089a9  mov     edx, 1
0x1800089ae  add     eax, edx
0x1800089b0  mov     [rcx+10h], eax
0x1800089b3  mov     rax, [rcx]
0x1800089b6  mov     rax, [rax+18h]
0x1800089ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800089bf  xor     eax, eax
0x1800089c1  jmp     short loc_1800089A1
```
