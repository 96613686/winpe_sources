# std::vector<std::shared_ptr<CConfigSet>,std::allocator<std::shared_ptr<CConfigSet>>>::_Destroy(std::shared_ptr<CConfigSet> *,std::shared_ptr<CConfigSet> *)

- ea: `0x18000a148`
- end: `0x18000a1bc`
- name: `?_Destroy@?$vector@V?$shared_ptr@VCConfigSet@@@std@@V?$allocator@V?$shared_ptr@VCConfigSet@@@std@@@2@@std@@IEAAXPEAV?$shared_ptr@VCConfigSet@@@2@0@Z`
- size: `116`
- prototype: `__int64 __fastcall(__int64, __int64, __int64)`
- caller_count: `8`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180008f84`
- `0x180008fcc`
- `0x1800095e8`
- `0x180009aa0`
- `0x180009bd0`
- `0x18000a1c4`
- `0x18000db4c`
- `0x18000f704`

## callees

- `0x18000a148`
- `0x180012010`

## pseudocode

```c
__int64 __fastcall std::vector<std::shared_ptr<CConfigSet>>::_Destroy(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 v4; // rdi
  volatile signed __int32 *v5; // rbx
  __int64 result; // rax

  if ( a2 != a3 )
  {
    v4 = a2;
    do
    {
      v5 = *(volatile signed __int32 **)(v4 + 8);
      if ( v5 )
      {
        result = (unsigned int)_InterlockedExchangeAdd(v5 + 2, 0xFFFFFFFF);
        if ( (_DWORD)result == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v5)(v5);
          result = (unsigned int)_InterlockedExchangeAdd(v5 + 3, 0xFFFFFFFF);
          if ( (_DWORD)result == 1 )
            result = (*(__int64 (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v5 + 8LL))(v5);
        }
      }
      v4 += 16;
    }
    while ( v4 != a3 );
  }
  return result;
}

```

## disassembly

```asm
0x18000a148  cmp     rdx, r8
0x18000a14b  jz      short locret_18000A1BB
0x18000a14d  mov     [rsp+arg_0], rbx
0x18000a152  mov     [rsp+arg_8], rsi
0x18000a157  push    rdi
0x18000a158  sub     rsp, 20h
0x18000a15c  mov     rsi, r8
0x18000a15f  mov     rdi, rdx
0x18000a162  mov     rbx, [rdi+8]
0x18000a166  test    rbx, rbx
0x18000a169  jz      short loc_18000A1A3
0x18000a16b  or      eax, 0FFFFFFFFh
0x18000a16e  lock xadd [rbx+8], eax
0x18000a173  cmp     eax, 1
0x18000a176  jnz     short loc_18000A1A3
0x18000a178  mov     rax, [rbx]
0x18000a17b  mov     rcx, rbx
0x18000a17e  mov     rax, [rax]
0x18000a181  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a186  or      eax, 0FFFFFFFFh
0x18000a189  lock xadd [rbx+0Ch], eax
0x18000a18e  cmp     eax, 1
0x18000a191  jnz     short loc_18000A1A3
0x18000a193  mov     rax, [rbx]
0x18000a196  mov     rcx, rbx
0x18000a199  mov     rax, [rax+8]
0x18000a19d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a1a2  nop
0x18000a1a3  add     rdi, 10h
0x18000a1a7  cmp     rdi, rsi
0x18000a1aa  jnz     short loc_18000A162
0x18000a1ac  mov     rbx, [rsp+28h+arg_0]
0x18000a1b1  mov     rsi, [rsp+28h+arg_8]
0x18000a1b6  add     rsp, 20h
0x18000a1ba  pop     rdi
0x18000a1bb  retn
```
