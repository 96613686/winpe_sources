# std::vector<Microsoft::WRL::ComPtr<IFilterRule>,std::allocator<Microsoft::WRL::ComPtr<IFilterRule>>>::_Tidy(void)

- ea: `0x1800192b0`
- end: `0x180019325`
- name: `?_Tidy@?$vector@V?$ComPtr@UIFilterRule@@@WRL@Microsoft@@V?$allocator@V?$ComPtr@UIFilterRule@@@WRL@Microsoft@@@std@@@std@@IEAAXXZ`
- size: `117`
- prototype: `void __fastcall(__int64)`
- caller_count: `4`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800171dc`
- `0x1800175a0`
- `0x180017840`
- `0x18002317b`

## callees

- `0x1800192b0`
- `0x180024010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x1800192f8`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800192f8`

## pseudocode

```c
void __fastcall std::vector<Microsoft::WRL::ComPtr<IFilterRule>>::_Tidy(__int64 a1)
{
  __int64 *v2; // rbx
  __int64 *v3; // rsi
  __int64 v4; // rcx

  v2 = *(__int64 **)a1;
  if ( *(_QWORD *)a1 )
  {
    v3 = *(__int64 **)(a1 + 8);
    while ( v2 != v3 )
    {
      v4 = *v2;
      if ( *v2 )
      {
        *v2 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
      }
      ++v2;
    }
    operator delete(*(void **)a1);
    *(_QWORD *)a1 = 0;
    *(_QWORD *)(a1 + 8) = 0;
    *(_QWORD *)(a1 + 16) = 0;
  }
}

```

## disassembly

```asm
0x1800192b0  mov     [rsp+arg_0], rbx
0x1800192b5  mov     [rsp+arg_8], rsi
0x1800192ba  push    rdi
0x1800192bb  sub     rsp, 20h
0x1800192bf  mov     rdi, rcx
0x1800192c2  mov     rbx, [rcx]
0x1800192c5  test    rbx, rbx
0x1800192c8  jz      short loc_180019315
0x1800192ca  mov     rsi, [rcx+8]
0x1800192ce  jmp     short loc_1800192F0
0x1800192d0  mov     rcx, [rbx]
0x1800192d3  test    rcx, rcx
0x1800192d6  jz      short loc_1800192EC
0x1800192d8  mov     qword ptr [rbx], 0
0x1800192df  mov     rax, [rcx]
0x1800192e2  mov     rax, [rax+10h]
0x1800192e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800192eb  nop
0x1800192ec  add     rbx, 8
0x1800192f0  cmp     rbx, rsi
0x1800192f3  jnz     short loc_1800192D0
0x1800192f5  mov     rcx, [rdi]
0x1800192f8  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800192fe  mov     qword ptr [rdi], 0
0x180019305  mov     qword ptr [rdi+8], 0
0x18001930d  mov     qword ptr [rdi+10h], 0
0x180019315  mov     rbx, [rsp+28h+arg_0]
0x18001931a  mov     rsi, [rsp+28h+arg_8]
0x18001931f  add     rsp, 20h
0x180019323  pop     rdi
0x180019324  retn
```
