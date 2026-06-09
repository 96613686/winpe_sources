# std::shared_ptr<SharedMemory>::_Resetp<SharedMemory,std::default_delete<SharedMemory>>(SharedMemory *,std::default_delete<SharedMemory>)

- ea: `0x18000c8c4`
- end: `0x18000c95c`
- name: `??$_Resetp@VSharedMemory@@U?$default_delete@VSharedMemory@@@std@@@?$shared_ptr@VSharedMemory@@@std@@AEAAXPEAVSharedMemory@@U?$default_delete@VSharedMemory@@@1@@Z`
- size: `152`
- prototype: `unsigned __int64 __fastcall(_QWORD *, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18000c9a8`

## callees

- `0x180002a88`
- `0x18000c8c4`
- `0x180010010`

## pseudocode

```c
unsigned __int64 __fastcall std::shared_ptr<SharedMemory>::_Resetp<SharedMemory,std::default_delete<SharedMemory>>(
        _QWORD *a1,
        __int64 a2)
{
  unsigned __int64 result; // rax
  __int64 v5; // rcx
  _QWORD *v6; // rbx
  volatile signed __int32 *v7; // rdi

  try
  {
    result = (unsigned __int64)operator new(0x20u);
    v6 = (_QWORD *)result;
    if ( result )
    {
      *(_DWORD *)(result + 8) = 1;
      *(_DWORD *)(result + 12) = 1;
      result = (unsigned __int64)&std::_Ref_count_del<SharedMemory,std::default_delete<SharedMemory>>::`vftable';
      *v6 = &std::_Ref_count_del<SharedMemory,std::default_delete<SharedMemory>>::`vftable';
      v6[2] = a2;
    }
    v7 = (volatile signed __int32 *)a1[1];
    if ( v7 )
    {
      result = (unsigned int)_InterlockedExchangeAdd(v7 + 2, 0xFFFFFFFF);
      if ( (_DWORD)result == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v7)(v7);
        result = (unsigned int)_InterlockedExchangeAdd(v7 + 3, 0xFFFFFFFF);
        if ( (_DWORD)result == 1 )
          result = (*(__int64 (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v7 + 8LL))(v7);
      }
    }
    a1[1] = v6;
    *a1 = a2;
  }
  catch ( ... )
  {
    std::default_delete<SharedMemory>::operator()(v5, a2);
    throw;
  }
  return result;
}

```

## disassembly

```asm
0x18000c8c4  mov     [rsp+arg_0], rbx
0x18000c8c9  mov     [rsp+arg_8], rdx
0x18000c8ce  push    rsi
0x18000c8cf  push    rdi
0x18000c8d0  push    r14
0x18000c8d2  sub     rsp, 20h
0x18000c8d6  mov     r14, rdx
0x18000c8d9  mov     rsi, rcx
0x18000c8dc  mov     ecx, 20h ; ' '; Size
0x18000c8e1  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000c8e6  mov     rbx, rax
0x18000c8e9  test    rbx, rbx
0x18000c8ec  jz      short loc_18000C907
0x18000c8ee  mov     eax, 1
0x18000c8f3  mov     [rbx+8], eax
0x18000c8f6  mov     [rbx+0Ch], eax
0x18000c8f9  lea     rax, ??_7?$_Ref_count_del@VSharedMemory@@U?$default_delete@VSharedMemory@@@std@@@std@@6B@; const std::_Ref_count_del<SharedMemory,std::default_delete<SharedMemory>>::`vftable'
0x18000c900  mov     [rbx], rax
0x18000c903  mov     [rbx+10h], r14
0x18000c907  mov     rdi, [rsi+8]
0x18000c90b  test    rdi, rdi
0x18000c90e  jz      short loc_18000C947
0x18000c910  or      eax, 0FFFFFFFFh
0x18000c913  lock xadd [rdi+8], eax
0x18000c918  cmp     eax, 1
0x18000c91b  jnz     short loc_18000C947
0x18000c91d  mov     rax, [rdi]
0x18000c920  mov     rcx, rdi
0x18000c923  mov     rax, [rax]
0x18000c926  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c92b  or      eax, 0FFFFFFFFh
0x18000c92e  lock xadd [rdi+0Ch], eax
0x18000c933  cmp     eax, 1
0x18000c936  jnz     short loc_18000C947
0x18000c938  mov     rax, [rdi]
0x18000c93b  mov     rcx, rdi
0x18000c93e  mov     rax, [rax+8]
0x18000c942  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c947  mov     [rsi+8], rbx
0x18000c94b  mov     [rsi], r14
0x18000c94e  mov     rbx, [rsp+38h+arg_0]
0x18000c953  add     rsp, 20h
0x18000c957  pop     r14
0x18000c959  pop     rdi
0x18000c95a  pop     rsi
0x18000c95b  retn
```
