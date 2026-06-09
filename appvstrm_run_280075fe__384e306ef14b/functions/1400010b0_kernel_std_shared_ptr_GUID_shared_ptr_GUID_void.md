# kernel_std::shared_ptr<_GUID>::~shared_ptr<_GUID>(void)

- ea: `0x1400010b0`
- end: `0x1400010fe`
- name: `??1?$shared_ptr@U_GUID@@@kernel_std@@QEAA@XZ`
- size: `78`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x14000984c`
- `0x14000bfe4`
- `0x14000d5a8`

## callees

- `0x1400010b0`
- `0x140015b30`

## pseudocode

```c
__int64 __fastcall kernel_std::shared_ptr<_GUID>::~shared_ptr<_GUID>(__int64 a1)
{
  volatile signed __int32 *v1; // rbx
  __int64 result; // rax

  v1 = *(volatile signed __int32 **)(a1 + 8);
  if ( v1 )
  {
    result = (unsigned int)_InterlockedExchangeAdd(v1 + 2, 0xFFFFFFFF);
    if ( (_DWORD)result == 1 )
    {
      (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v1 + 8LL))(v1);
      result = (unsigned int)_InterlockedExchangeAdd(v1 + 3, 0xFFFFFFFF);
      if ( (_DWORD)result == 1 )
        return (*(__int64 (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v1 + 16LL))(v1);
    }
  }
  return result;
}

```

## disassembly

```asm
0x1400010b0  push    rbx
0x1400010b2  sub     rsp, 20h
0x1400010b6  mov     rbx, [rcx+8]
0x1400010ba  test    rbx, rbx
0x1400010bd  jz      short loc_1400010F7
0x1400010bf  or      eax, 0FFFFFFFFh
0x1400010c2  lock xadd [rbx+8], eax
0x1400010c7  cmp     eax, 1
0x1400010ca  jnz     short loc_1400010F7
0x1400010cc  mov     rax, [rbx]
0x1400010cf  mov     rcx, rbx
0x1400010d2  mov     rax, [rax+8]
0x1400010d6  call    _guard_dispatch_icall
0x1400010db  or      eax, 0FFFFFFFFh
0x1400010de  lock xadd [rbx+0Ch], eax
0x1400010e3  cmp     eax, 1
0x1400010e6  jnz     short loc_1400010F7
0x1400010e8  mov     rax, [rbx]
0x1400010eb  mov     rcx, rbx
0x1400010ee  mov     rax, [rax+10h]
0x1400010f2  call    _guard_dispatch_icall
0x1400010f7  add     rsp, 20h
0x1400010fb  pop     rbx
0x1400010fc  retn
```
