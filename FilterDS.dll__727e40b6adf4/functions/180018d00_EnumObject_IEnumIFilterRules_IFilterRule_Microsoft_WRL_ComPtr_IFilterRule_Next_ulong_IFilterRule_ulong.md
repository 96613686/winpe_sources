# EnumObject<IEnumIFilterRules,IFilterRule *,Microsoft::WRL::ComPtr<IFilterRule>>::Next(ulong,IFilterRule * *,ulong *)

- ea: `0x180018d00`
- end: `0x180018d82`
- name: `?Next@?$EnumObject@UIEnumIFilterRules@@PEAUIFilterRule@@V?$ComPtr@UIFilterRule@@@WRL@Microsoft@@@@UEAAJKPEAPEAUIFilterRule@@PEAK@Z`
- size: `130`
- prototype: `_BOOL8 __fastcall(__int64, unsigned int, _QWORD *, unsigned int *)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180018d00`
- `0x180024010`

## pseudocode

```c
_BOOL8 __fastcall EnumObject<IEnumIFilterRules,IFilterRule *,Microsoft::WRL::ComPtr<IFilterRule>>::Next(
        __int64 a1,
        unsigned int a2,
        _QWORD *a3,
        unsigned int *a4)
{
  unsigned int i; // ebx
  __int64 v9; // r12
  unsigned __int64 v10; // rbp
  __int64 v11; // rcx

  for ( i = 0; i < a2; ++i )
  {
    v9 = *(_QWORD *)(a1 + 16);
    v10 = *(unsigned int *)(a1 + 40);
    if ( v10 >= (*(_QWORD *)(a1 + 24) - v9) >> 3 )
      break;
    _mm_lfence();
    v11 = *(_QWORD *)(v9 + 8 * v10);
    if ( v11 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 8LL))(v11);
    *a3 = *(_QWORD *)(v9 + 8 * v10);
    ++*(_DWORD *)(a1 + 40);
    ++a3;
  }
  if ( a4 )
    *a4 = i;
  return i != a2;
}

```

## disassembly

```asm
0x180018d00  push    rbx
0x180018d02  push    rbp
0x180018d03  push    rsi
0x180018d04  push    rdi
0x180018d05  push    r12
0x180018d07  push    r14
0x180018d09  push    r15
0x180018d0b  sub     rsp, 20h
0x180018d0f  mov     r14, r9
0x180018d12  mov     r15, r8
0x180018d15  mov     esi, edx
0x180018d17  mov     rdi, rcx
0x180018d1a  xor     ebx, ebx
0x180018d1c  test    edx, edx
0x180018d1e  jz      short loc_180018D64
0x180018d20  mov     r12, [rdi+10h]
0x180018d24  mov     ebp, [rdi+28h]
0x180018d27  mov     rax, [rdi+18h]
0x180018d2b  sub     rax, r12
0x180018d2e  sar     rax, 3
0x180018d32  cmp     rbp, rax
0x180018d35  jnb     short loc_180018D64
0x180018d37  lfence
0x180018d3a  mov     rcx, [r12+rbp*8]
0x180018d3e  test    rcx, rcx
0x180018d41  jz      short loc_180018D50
0x180018d43  mov     rax, [rcx]
0x180018d46  mov     rax, [rax+8]
0x180018d4a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018d4f  nop
0x180018d50  mov     rax, [r12+rbp*8]
0x180018d54  mov     [r15], rax
0x180018d57  inc     dword ptr [rdi+28h]
0x180018d5a  add     r15, 8
0x180018d5e  inc     ebx
0x180018d60  cmp     ebx, esi
0x180018d62  jb      short loc_180018D20
0x180018d64  test    r14, r14
0x180018d67  jz      short loc_180018D6C
0x180018d69  mov     [r14], ebx
0x180018d6c  xor     eax, eax
0x180018d6e  cmp     ebx, esi
0x180018d70  setnz   al
0x180018d73  add     rsp, 20h
0x180018d77  pop     r15
0x180018d79  pop     r14
0x180018d7b  pop     r12
0x180018d7d  pop     rdi
0x180018d7e  pop     rsi
0x180018d7f  pop     rbp
0x180018d80  pop     rbx
0x180018d81  retn
```
