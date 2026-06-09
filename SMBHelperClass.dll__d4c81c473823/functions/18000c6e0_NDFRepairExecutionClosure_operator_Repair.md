# NDFRepairExecutionClosure::operator()(Repair * &)

- ea: `0x18000c6e0`
- end: `0x18000c736`
- name: `??RNDFRepairExecutionClosure@@UEAAHAEAPEAVRepair@@@Z`
- size: `86`
- prototype: `__int64 __fastcall(__int64, __int64 *)`
- caller_count: `0`
- callee_count: `2`
- tags: `installer_update`

## callees

- `0x18000c6e0`
- `0x180012010`

## pseudocode

```c
__int64 __fastcall NDFRepairExecutionClosure::operator()(__int64 a1, __int64 *a2)
{
  __int64 v3; // rcx
  __m128i v4; // xmm0
  _QWORD *v5; // rdx
  __int64 result; // rax

  v3 = *a2;
  v4 = *(__m128i *)(*a2 + 40);
  v5 = *(_QWORD **)(a1 + 8);
  if ( v4.m128i_i64[0] != *v5 )
    return 1;
  if ( _mm_srli_si128(v4, 8).m128i_u64[0] != v5[1] )
    return 1;
  result = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v3 + 16LL))(v3, *(_QWORD *)(a1 + 32));
  if ( (_DWORD)result )
    return 1;
  *(_DWORD *)(a1 + 40) = 1;
  return result;
}

```

## disassembly

```asm
0x18000c6e0  push    rbx
0x18000c6e2  sub     rsp, 20h
0x18000c6e6  mov     rbx, rcx
0x18000c6e9  mov     rcx, [rdx]
0x18000c6ec  movups  xmm0, xmmword ptr [rcx+28h]
0x18000c6f0  mov     rdx, [rbx+8]
0x18000c6f4  movq    rax, xmm0
0x18000c6f9  cmp     rax, [rdx]
0x18000c6fc  jnz     short loc_18000C72B
0x18000c6fe  psrldq  xmm0, 8
0x18000c703  movq    rax, xmm0
0x18000c708  cmp     rax, [rdx+8]
0x18000c70c  jnz     short loc_18000C72B
0x18000c70e  mov     rax, [rcx]
0x18000c711  mov     rdx, [rbx+20h]
0x18000c715  mov     rax, [rax+10h]
0x18000c719  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c71e  test    eax, eax
0x18000c720  jnz     short loc_18000C72B
0x18000c722  mov     dword ptr [rbx+28h], 1
0x18000c729  jmp     short loc_18000C730
0x18000c72b  mov     eax, 1
0x18000c730  add     rsp, 20h
0x18000c734  pop     rbx
0x18000c735  retn
```
