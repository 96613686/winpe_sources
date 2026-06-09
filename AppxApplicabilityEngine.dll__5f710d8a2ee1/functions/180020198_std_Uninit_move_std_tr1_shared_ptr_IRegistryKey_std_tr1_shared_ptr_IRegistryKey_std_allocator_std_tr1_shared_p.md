# std::_Uninit_move<std::tr1::shared_ptr<IRegistryKey> *,std::tr1::shared_ptr<IRegistryKey> *,std::allocator<std::tr1::shared_ptr<IRegistryKey>>,std::tr1::shared_ptr<IRegistryKey>>(std::tr1::shared_ptr<IRegistryKey> *,std::tr1::shared_ptr<IRegistryKey> *,std::tr1::shared_ptr<IRegistryKey> *,std::allocator<std::tr1::shared_ptr<IRegistryKey>> &,std::tr1::shared_ptr<IRegistryKey> *,std::_Nonscalar_ptr_iterator_tag)

- ea: `0x180020198`
- end: `0x1800201e4`
- name: `??$_Uninit_move@PEAV?$shared_ptr@VIRegistryKey@@@tr1@std@@PEAV123@V?$allocator@V?$shared_ptr@VIRegistryKey@@@tr1@std@@@3@V123@@std@@YAPEAV?$shared_ptr@VIRegistryKey@@@tr1@0@PEAV120@00AEAV?$allocator@V?$shared_ptr@VIRegistryKey@@@tr1@std@@@0@0U_Nonscalar_ptr_iterator_tag@0@@Z`
- size: `76`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18002136c`

## callees

- `0x180020198`
- `0x1800201ec`

## pseudocode

```c
__int64 __fastcall std::_Uninit_move<std::tr1::shared_ptr<IRegistryKey> *,std::tr1::shared_ptr<IRegistryKey> *,std::allocator<std::tr1::shared_ptr<IRegistryKey>>,std::tr1::shared_ptr<IRegistryKey>>(
        __int64 a1,
        __int64 a2,
        __int64 a3)
{
  __int64 v5; // rdx
  __int64 v6; // r9
  __int64 v7; // rdx
  __int64 v8; // r10

  v5 = a1;
  if ( a1 != a2 )
  {
    do
    {
      std::tr1::shared_ptr<IRegistryKey>::shared_ptr<IRegistryKey>(a3, v5);
      a3 = v6 + 16;
      v5 = v7 + 16;
    }
    while ( v5 != v8 );
  }
  return a3;
}

```

## disassembly

```asm
0x180020198  mov     [rsp+arg_18], r9
0x18002019d  mov     [rsp+arg_10], r8
0x1800201a2  sub     rsp, 38h
0x1800201a6  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x1800201af  mov     r9, r8
0x1800201b2  mov     r10, rdx
0x1800201b5  mov     rdx, rcx
0x1800201b8  mov     [rsp+38h+arg_18], r8
0x1800201bd  cmp     rcx, r10
0x1800201c0  jz      short loc_1800201DC
0x1800201c2  mov     rcx, r9
0x1800201c5  call    ??0?$shared_ptr@VIRegistryKey@@@tr1@std@@QEAA@$$QEAV012@@Z; std::tr1::shared_ptr<IRegistryKey>::shared_ptr<IRegistryKey>(std::tr1::shared_ptr<IRegistryKey> &&)
0x1800201ca  add     r9, 10h
0x1800201ce  mov     [rsp+38h+arg_10], r9
0x1800201d3  add     rdx, 10h
0x1800201d7  cmp     rdx, r10
0x1800201da  jnz     short loc_1800201C2
0x1800201dc  mov     rax, r9
0x1800201df  add     rsp, 38h
0x1800201e3  retn
```
