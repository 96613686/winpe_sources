# CComBase::NDRelease(void)

- ea: `0x180025970`
- end: `0x1800259a3`
- name: `?NDRelease@CComBase@@UEAAKXZ`
- size: `51`
- prototype: `unsigned int __fastcall(CComBase *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180025970`
- `0x180046010`

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
0x180025970  sub     rsp, 28h
0x180025974  or      eax, 0FFFFFFFFh
0x180025977  lock xadd [rcx+10h], eax
0x18002597c  sub     eax, 1
0x18002597f  jz      short loc_180025986
0x180025981  add     rsp, 28h
0x180025985  retn
0x180025986  mov     eax, [rcx+10h]
0x180025989  mov     edx, 1
0x18002598e  add     eax, edx
0x180025990  mov     [rcx+10h], eax
0x180025993  mov     rax, [rcx]
0x180025996  mov     rax, [rax+18h]
0x18002599a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002599f  xor     eax, eax
0x1800259a1  jmp     short loc_180025981
```
