# CompareSourceElements(std::shared_ptr<CConfigSource const>,std::shared_ptr<CConfigSource const>)

- ea: `0x18000b270`
- end: `0x18000b316`
- name: `?CompareSourceElements@@YAHV?$shared_ptr@$$CBVCConfigSource@@@std@@0@Z`
- size: `166`
- prototype: `_BOOL8 __fastcall(__int64, __int64)`
- caller_count: `4`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000a6e0`
- `0x18000a838`
- `0x18000a9f0`
- `0x18000adac`

## callees

- `0x18000b270`
- `0x180012010`

## pseudocode

```c
_BOOL8 __fastcall CompareSourceElements(__int64 a1, __int64 a2)
{
  BOOL v3; // edi
  volatile signed __int32 *v4; // rbx
  volatile signed __int32 *v5; // rbx

  v3 = **(_DWORD **)a1 < **(_DWORD **)a2;
  v4 = *(volatile signed __int32 **)(a1 + 8);
  if ( v4 )
  {
    if ( _InterlockedExchangeAdd(v4 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v4)(v4);
      if ( _InterlockedExchangeAdd(v4 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v4 + 8LL))(v4);
    }
  }
  v5 = *(volatile signed __int32 **)(a2 + 8);
  if ( v5 )
  {
    if ( _InterlockedExchangeAdd(v5 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v5)(v5);
      if ( _InterlockedExchangeAdd(v5 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v5 + 8LL))(v5);
    }
  }
  return v3;
}

```

## disassembly

```asm
0x18000b270  push    rbx
0x18000b272  push    rbp
0x18000b273  push    rsi
0x18000b274  push    rdi
0x18000b275  sub     rsp, 28h
0x18000b279  mov     rsi, rdx
0x18000b27c  mov     rax, [rcx]
0x18000b27f  mov     r8d, [rax]
0x18000b282  mov     rax, [rdx]
0x18000b285  xor     edi, edi
0x18000b287  cmp     r8d, [rax]
0x18000b28a  setb    dil
0x18000b28e  mov     rbx, [rcx+8]
0x18000b292  or      ebp, 0FFFFFFFFh
0x18000b295  test    rbx, rbx
0x18000b298  jz      short loc_18000B2CE
0x18000b29a  mov     eax, ebp
0x18000b29c  lock xadd [rbx+8], eax
0x18000b2a1  add     eax, ebp
0x18000b2a3  jnz     short loc_18000B2CE
0x18000b2a5  mov     rax, [rbx]
0x18000b2a8  mov     rcx, rbx
0x18000b2ab  mov     rax, [rax]
0x18000b2ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b2b3  mov     eax, ebp
0x18000b2b5  lock xadd [rbx+0Ch], eax
0x18000b2ba  add     eax, ebp
0x18000b2bc  jnz     short loc_18000B2CE
0x18000b2be  mov     rax, [rbx]
0x18000b2c1  mov     rcx, rbx
0x18000b2c4  mov     rax, [rax+8]
0x18000b2c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b2cd  nop
0x18000b2ce  mov     rbx, [rsi+8]
0x18000b2d2  test    rbx, rbx
0x18000b2d5  jz      short loc_18000B30B
0x18000b2d7  mov     eax, ebp
0x18000b2d9  lock xadd [rbx+8], eax
0x18000b2de  add     eax, ebp
0x18000b2e0  jnz     short loc_18000B30B
0x18000b2e2  mov     rax, [rbx]
0x18000b2e5  mov     rcx, rbx
0x18000b2e8  mov     rax, [rax]
0x18000b2eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b2f0  mov     edx, ebp
0x18000b2f2  lock xadd [rbx+0Ch], edx
0x18000b2f7  add     edx, ebp
0x18000b2f9  jnz     short loc_18000B30B
0x18000b2fb  mov     rdx, [rbx]
0x18000b2fe  mov     rcx, rbx
0x18000b301  mov     rax, [rdx+8]
0x18000b305  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b30a  nop
0x18000b30b  mov     eax, edi
0x18000b30d  add     rsp, 28h
0x18000b311  pop     rdi
0x18000b312  pop     rsi
0x18000b313  pop     rbp
0x18000b314  pop     rbx
0x18000b315  retn
```
