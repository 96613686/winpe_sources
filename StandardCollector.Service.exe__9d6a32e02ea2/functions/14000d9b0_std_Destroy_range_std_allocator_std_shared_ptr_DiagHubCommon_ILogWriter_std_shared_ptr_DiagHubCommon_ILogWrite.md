# std::_Destroy_range<std::allocator<std::shared_ptr<DiagHubCommon::ILogWriter>>>(std::shared_ptr<DiagHubCommon::ILogWriter> *,std::shared_ptr<DiagHubCommon::ILogWriter> * const,std::allocator<std::shared_ptr<DiagHubCommon::ILogWriter>> &)

- ea: `0x14000d9b0`
- end: `0x14000da25`
- name: `??$_Destroy_range@V?$allocator@V?$shared_ptr@VILogWriter@DiagHubCommon@@@std@@@std@@@std@@YAXPEAV?$shared_ptr@VILogWriter@DiagHubCommon@@@0@QEAV10@AEAV?$allocator@V?$shared_ptr@VILogWriter@DiagHubCommon@@@std@@@0@@Z`
- size: `117`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `6`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x14000b824`
- `0x14000d104`
- `0x14000d484`
- `0x14000da28`
- `0x14000dec8`
- `0x14000dff0`

## callees

- `0x14000d9b0`
- `0x140014c70`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
__int64 __fastcall std::_Destroy_range<std::allocator<std::shared_ptr<DiagHubCommon::ILogWriter>>>(
        __int64 a1,
        __int64 a2)
{
  __int64 v3; // rdi
  volatile signed __int32 *v4; // rbx
  __int64 result; // rax

  if ( a1 != a2 )
  {
    v3 = a1;
    do
    {
      v4 = *(volatile signed __int32 **)(v3 + 8);
      if ( v4 )
      {
        result = (unsigned int)_InterlockedExchangeAdd(v4 + 2, 0xFFFFFFFF);
        if ( (_DWORD)result == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v4)(v4);
          result = (unsigned int)_InterlockedExchangeAdd(v4 + 3, 0xFFFFFFFF);
          if ( (_DWORD)result == 1 )
            result = (*(__int64 (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v4 + 8LL))(v4);
        }
      }
      v3 += 16;
    }
    while ( v3 != a2 );
  }
  return result;
}

```

## disassembly

```asm
0x14000d9b0  cmp     rcx, rdx
0x14000d9b3  jz      short locret_14000DA24
0x14000d9b5  mov     [rsp+arg_0], rbx
0x14000d9ba  mov     [rsp+arg_8], rsi
0x14000d9bf  push    rdi
0x14000d9c0  sub     rsp, 20h
0x14000d9c4  mov     rsi, rdx
0x14000d9c7  mov     rdi, rcx
0x14000d9ca  mov     rbx, [rdi+8]
0x14000d9ce  test    rbx, rbx
0x14000d9d1  jz      short loc_14000DA0C
0x14000d9d3  or      eax, 0FFFFFFFFh
0x14000d9d6  lock xadd [rbx+8], eax
0x14000d9db  cmp     eax, 1
0x14000d9de  jnz     short loc_14000DA0C
0x14000d9e0  mov     rax, [rbx]
0x14000d9e3  mov     rcx, rbx
0x14000d9e6  mov     rax, [rax]
0x14000d9e9  call    cs:__guard_dispatch_icall_fptr
0x14000d9ef  or      eax, 0FFFFFFFFh
0x14000d9f2  lock xadd [rbx+0Ch], eax
0x14000d9f7  cmp     eax, 1
0x14000d9fa  jnz     short loc_14000DA0C
0x14000d9fc  mov     rax, [rbx]
0x14000d9ff  mov     rcx, rbx
0x14000da02  mov     rax, [rax+8]
0x14000da06  call    cs:__guard_dispatch_icall_fptr
0x14000da0c  add     rdi, 10h
0x14000da10  cmp     rdi, rsi
0x14000da13  jnz     short loc_14000D9CA
0x14000da15  mov     rbx, [rsp+28h+arg_0]
0x14000da1a  mov     rsi, [rsp+28h+arg_8]
0x14000da1f  add     rsp, 20h
0x14000da23  pop     rdi
0x14000da24  retn
```
