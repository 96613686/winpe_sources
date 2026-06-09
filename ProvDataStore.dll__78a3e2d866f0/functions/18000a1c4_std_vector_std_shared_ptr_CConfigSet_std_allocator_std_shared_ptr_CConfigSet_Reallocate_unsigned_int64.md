# std::vector<std::shared_ptr<CConfigSet>,std::allocator<std::shared_ptr<CConfigSet>>>::_Reallocate(unsigned __int64)

- ea: `0x18000a1c4`
- end: `0x18000a261`
- name: `?_Reallocate@?$vector@V?$shared_ptr@VCConfigSet@@@std@@V?$allocator@V?$shared_ptr@VCConfigSet@@@std@@@2@@std@@IEAAX_K@Z`
- size: `157`
- prototype: `__int64 *__fastcall(__int64, unsigned __int64)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops, registry_config`

## callers

- `0x18000a268`
- `0x18000f790`

## callees

- `0x1800018f4`
- `0x180008dcc`
- `0x18000a148`
- `0x18000a1c4`

## import_xrefs

- `msvcp110_win!?_Xbad_alloc@std@@YAXXZ` at `0x18000a201`
- `msvcp110_win!?_Xbad_alloc@std@@YAXXZ` at `0x18000a201`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000a23b`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000a23b`

## pseudocode

```c
__int64 *__fastcall std::vector<std::shared_ptr<CConfigSet>>::_Reallocate(__int64 a1, unsigned __int64 a2)
{
  __int64 v3; // rdi
  __int64 *v4; // rbx
  __int64 v5; // rcx
  __int64 v6; // rsi
  __int64 *result; // rax
  __int64 *v8; // [rsp+68h] [rbp+10h]

  if ( a2 )
  {
    if ( a2 > 0xFFFFFFFFFFFFFFFLL || (v3 = 2 * a2, v4 = (__int64 *)operator new(16 * a2), (v8 = v4) == 0) )
    {
      std::_Xbad_alloc();
      __debugbreak();
    }
  }
  else
  {
    v4 = 0;
    v8 = 0;
    v3 = 0;
  }
  try
  {
    std::_Uninit_move<std::shared_ptr<CConfigSource> *,std::shared_ptr<CConfigSource> *,std::allocator<std::shared_ptr<CConfigSource>>,std::shared_ptr<CConfigSource>>(
      *(__int64 **)a1,
      *(__int64 **)(a1 + 8),
      v4);
  }
  catch ( ... )
  {
    std::_Wrap_alloc<std::allocator<unsigned char>>::deallocate(v5, v8);
    throw;
  }
  v6 = *(_QWORD *)(a1 + 8) - *(_QWORD *)a1;
  if ( *(_QWORD *)a1 )
  {
    std::vector<std::shared_ptr<CConfigSet>>::_Destroy(v5, *(_QWORD *)a1, *(_QWORD *)(a1 + 8));
    operator delete(*(void **)a1);
  }
  result = &v4[v3];
  *(_QWORD *)(a1 + 16) = &v4[v3];
  *(_QWORD *)(a1 + 8) = (char *)v4 + (v6 & 0xFFFFFFFFFFFFFFF0uLL);
  *(_QWORD *)a1 = v4;
  return result;
}

```

## disassembly

```asm
0x18000a1c4  push    rbx
0x18000a1c6  push    rsi
0x18000a1c7  push    rdi
0x18000a1c8  push    r14
0x18000a1ca  sub     rsp, 38h
0x18000a1ce  mov     rdi, rdx
0x18000a1d1  mov     r14, rcx
0x18000a1d4  test    rdx, rdx
0x18000a1d7  jz      short loc_18000A208
0x18000a1d9  mov     rax, 0FFFFFFFFFFFFFFFh
0x18000a1e3  cmp     rdx, rax
0x18000a1e6  ja      short loc_18000A201
0x18000a1e8  shl     rdi, 4
0x18000a1ec  mov     rcx, rdi; Size
0x18000a1ef  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000a1f4  mov     rbx, rax
0x18000a1f7  mov     [rsp+58h+arg_8], rax
0x18000a1fc  test    rax, rax
0x18000a1ff  jnz     short loc_18000A211
0x18000a201  call    cs:__imp_?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
0x18000a207  int     3; Trap to Debugger
0x18000a208  xor     ebx, ebx
0x18000a20a  mov     [rsp+58h+arg_8], rbx
0x18000a20f  xor     edi, edi
0x18000a211  mov     r8, rbx
0x18000a214  mov     rdx, [r14+8]
0x18000a218  mov     rcx, [r14]
0x18000a21b  call    ??$_Uninit_move@PEAV?$shared_ptr@VCConfigSource@@@std@@PEAV12@V?$allocator@V?$shared_ptr@VCConfigSource@@@std@@@2@V12@@std@@YAPEAV?$shared_ptr@VCConfigSource@@@0@PEAV10@00AEAU?$_Wrap_alloc@V?$allocator@V?$shared_ptr@VCConfigSource@@@std@@@std@@@0@0U_Nonscalar_ptr_iterator_tag@0@@Z; std::_Uninit_move<std::shared_ptr<CConfigSource> *,std::shared_ptr<CConfigSource> *,std::allocator<std::shared_ptr<CConfigSource>>,std::shared_ptr<CConfigSource>>(std::shared_ptr<CConfigSource> *,std::shared_ptr<CConfigSource> *,std::shared_ptr<CConfigSource> *,std::_Wrap_alloc<std::allocator<std::shared_ptr<CConfigSource>>> &,std::shared_ptr<CConfigSource> *,std::_Nonscalar_ptr_iterator_tag)
0x18000a220  nop
0x18000a221  mov     rdx, [r14]
0x18000a224  mov     r8, [r14+8]
0x18000a228  mov     rsi, r8
0x18000a22b  sub     rsi, rdx
0x18000a22e  test    rdx, rdx
0x18000a231  jz      short loc_18000A241
0x18000a233  call    ?_Destroy@?$vector@V?$shared_ptr@VCConfigSet@@@std@@V?$allocator@V?$shared_ptr@VCConfigSet@@@std@@@2@@std@@IEAAXPEAV?$shared_ptr@VCConfigSet@@@2@0@Z; std::vector<std::shared_ptr<CConfigSet>>::_Destroy(std::shared_ptr<CConfigSet> *,std::shared_ptr<CConfigSet> *)
0x18000a238  mov     rcx, [r14]
0x18000a23b  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000a241  lea     rax, [rdi+rbx]
0x18000a245  mov     [r14+10h], rax
0x18000a249  and     rsi, 0FFFFFFFFFFFFFFF0h
0x18000a24d  add     rsi, rbx
0x18000a250  mov     [r14+8], rsi
0x18000a254  mov     [r14], rbx
0x18000a257  add     rsp, 38h
0x18000a25b  pop     r14
0x18000a25d  pop     rdi
0x18000a25e  pop     rsi
0x18000a25f  pop     rbx
0x18000a260  retn
```
