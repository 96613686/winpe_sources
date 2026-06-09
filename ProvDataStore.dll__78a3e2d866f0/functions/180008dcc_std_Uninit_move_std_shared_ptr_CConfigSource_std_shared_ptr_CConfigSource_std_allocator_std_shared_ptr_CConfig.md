# std::_Uninit_move<std::shared_ptr<CConfigSource> *,std::shared_ptr<CConfigSource> *,std::allocator<std::shared_ptr<CConfigSource>>,std::shared_ptr<CConfigSource>>(std::shared_ptr<CConfigSource> *,std::shared_ptr<CConfigSource> *,std::shared_ptr<CConfigSource> *,std::_Wrap_alloc<std::allocator<std::shared_ptr<CConfigSource>>> &,std::shared_ptr<CConfigSource> *,std::_Nonscalar_ptr_iterator_tag)

- ea: `0x180008dcc`
- end: `0x180008e28`
- name: `??$_Uninit_move@PEAV?$shared_ptr@VCConfigSource@@@std@@PEAV12@V?$allocator@V?$shared_ptr@VCConfigSource@@@std@@@2@V12@@std@@YAPEAV?$shared_ptr@VCConfigSource@@@0@PEAV10@00AEAU?$_Wrap_alloc@V?$allocator@V?$shared_ptr@VCConfigSource@@@std@@@std@@@0@0U_Nonscalar_ptr_iterator_tag@0@@Z`
- size: `92`
- prototype: `__int64 *__fastcall(__int64 *, __int64 *, __int64 *)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x18000a1c4`

## callees

- `0x180008dcc`

## pseudocode

```c
__int64 *__fastcall std::_Uninit_move<std::shared_ptr<CConfigSource> *,std::shared_ptr<CConfigSource> *,std::allocator<std::shared_ptr<CConfigSource>>,std::shared_ptr<CConfigSource>>(
        __int64 *a1,
        __int64 *a2,
        __int64 *a3)
{
  __int64 *i; // r9
  __int64 v4; // rcx

  for ( i = a1; i != a2; i += 2 )
  {
    *a3 = 0;
    a3[1] = 0;
    if ( a3 != i )
    {
      a3[1] = i[1];
      i[1] = 0;
      v4 = *a3;
      *a3 = *i;
      *i = v4;
    }
    a3 += 2;
  }
  return a3;
}

```

## disassembly

```asm
0x180008dcc  mov     [rsp+arg_18], r9
0x180008dd1  mov     [rsp+arg_10], r8
0x180008dd6  sub     rsp, 28h
0x180008dda  mov     r9, rcx
0x180008ddd  mov     [rsp+28h+arg_18], r8
0x180008de2  cmp     rcx, rdx
0x180008de5  jz      short loc_180008E20
0x180008de7  xor     r10d, r10d
0x180008dea  mov     [r8], r10
0x180008ded  mov     [r8+8], r10
0x180008df1  cmp     r8, r9
0x180008df4  jz      short loc_180008E0E
0x180008df6  mov     rax, [r9+8]
0x180008dfa  mov     [r8+8], rax
0x180008dfe  mov     [r9+8], r10
0x180008e02  mov     rcx, [r8]
0x180008e05  mov     rax, [r9]
0x180008e08  mov     [r8], rax
0x180008e0b  mov     [r9], rcx
0x180008e0e  add     r8, 10h
0x180008e12  mov     [rsp+28h+arg_10], r8
0x180008e17  add     r9, 10h
0x180008e1b  cmp     r9, rdx
0x180008e1e  jnz     short loc_180008DEA
0x180008e20  mov     rax, r8
0x180008e23  add     rsp, 28h
0x180008e27  retn
```
