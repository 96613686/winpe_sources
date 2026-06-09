# CComBase::NDRelease(void)

- ea: `0x18000cba0`
- end: `0x18000cbd3`
- name: `?NDRelease@CComBase@@UEAAKXZ`
- size: `51`
- prototype: `unsigned int __fastcall(CComBase *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x18000cba0`
- `0x180012010`

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
0x18000cba0  sub     rsp, 28h
0x18000cba4  or      eax, 0FFFFFFFFh
0x18000cba7  lock xadd [rcx+10h], eax
0x18000cbac  sub     eax, 1
0x18000cbaf  jz      short loc_18000CBB6
0x18000cbb1  add     rsp, 28h
0x18000cbb5  retn
0x18000cbb6  mov     eax, [rcx+10h]
0x18000cbb9  mov     edx, 1
0x18000cbbe  add     eax, edx
0x18000cbc0  mov     [rcx+10h], eax
0x18000cbc3  mov     rax, [rcx]
0x18000cbc6  mov     rax, [rax+18h]
0x18000cbca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cbcf  xor     eax, eax
0x18000cbd1  jmp     short loc_18000CBB1
```
