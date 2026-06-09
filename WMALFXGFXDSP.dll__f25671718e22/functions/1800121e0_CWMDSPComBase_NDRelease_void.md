# CWMDSPComBase::NDRelease(void)

- ea: `0x1800121e0`
- end: `0x180012213`
- name: `?NDRelease@CWMDSPComBase@@UEAAKXZ`
- size: `51`
- prototype: `unsigned int __fastcall(CWMDSPComBase *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x1800121e0`
- `0x180086010`

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
0x1800121e0  sub     rsp, 28h
0x1800121e4  or      eax, 0FFFFFFFFh
0x1800121e7  lock xadd [rcx+10h], eax
0x1800121ec  sub     eax, 1
0x1800121ef  jz      short loc_1800121F6
0x1800121f1  add     rsp, 28h
0x1800121f5  retn
0x1800121f6  mov     eax, [rcx+10h]
0x1800121f9  mov     edx, 1
0x1800121fe  add     eax, edx
0x180012200  mov     [rcx+10h], eax
0x180012203  mov     rax, [rcx]
0x180012206  mov     rax, [rax+18h]
0x18001220a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001220f  xor     eax, eax
0x180012211  jmp     short loc_1800121F1
```
