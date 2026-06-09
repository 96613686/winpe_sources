# std::vector<APPID_PLUGIN_,std::allocator<APPID_PLUGIN_>>::_Reallocate(unsigned __int64)

- ea: `0x14000696c`
- end: `0x140006a1c`
- name: `?_Reallocate@?$vector@UAPPID_PLUGIN_@@V?$allocator@UAPPID_PLUGIN_@@@std@@@std@@IEAAX_K@Z`
- size: `176`
- prototype: `__int64 __fastcall(__int64 *, unsigned __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, loader_planting`

## callers

- `0x140006c10`

## callees

- `0x140001530`
- `0x14000157c`
- `0x140002644`
- `0x14000696c`

## import_xrefs

- `msvcp110_win!?_Xbad_alloc@std@@YAXXZ` at `0x1400069b1`
- `msvcp110_win!?_Xbad_alloc@std@@YAXXZ` at `0x1400069b1`
- `msvcp110_win!?_Orphan_all@_Container_base0@std@@QEAAXXZ` at `0x1400069f1`
- `msvcp110_win!?_Orphan_all@_Container_base0@std@@QEAAXXZ` at `0x1400069f1`

## pseudocode

```c
__int64 __fastcall std::vector<APPID_PLUGIN_>::_Reallocate(__int64 *a1, unsigned __int64 a2)
{
  void *v4; // rbx
  unsigned __int64 v5; // r14
  __int64 result; // rax
  void *v7; // [rsp+68h] [rbp+10h]

  v4 = 0;
  v7 = 0;
  if ( a2 )
  {
    if ( a2 > 0x71C71C71C71C71CLL || (v4 = operator new(36 * a2), (v7 = v4) == 0) )
      std::_Xbad_alloc();
  }
  try
  {
    std::_Uninit_move<APPID_PLUGIN_ *,APPID_PLUGIN_ *,std::allocator<APPID_PLUGIN_>,APPID_PLUGIN_>(
      *a1,
      a1[1],
      (__int64)v4);
  }
  catch ( ... )
  {
    operator delete(v7);
    throw;
  }
  v5 = 0x8E38E38E38E38E39uLL * ((a1[1] - *a1) >> 2);
  if ( *a1 )
    operator delete((void *)*a1);
  std::_Container_base0::_Orphan_all((std::_Container_base0 *)a1);
  a1[2] = (__int64)v4 + 36 * a2;
  result = 9 * v5;
  a1[1] = (__int64)v4 + 36 * v5;
  *a1 = (__int64)v4;
  return result;
}

```

## disassembly

```asm
0x14000696c  push    rbx
0x14000696e  push    rsi
0x14000696f  push    rdi
0x140006970  push    r14
0x140006972  sub     rsp, 38h
0x140006976  mov     rdi, rdx
0x140006979  mov     rsi, rcx
0x14000697c  xor     ebx, ebx
0x14000697e  mov     [rsp+58h+arg_8], rbx
0x140006983  test    rdx, rdx
0x140006986  jz      short loc_1400069B8
0x140006988  mov     rax, 71C71C71C71C71Ch
0x140006992  cmp     rdx, rax
0x140006995  ja      short loc_1400069B1
0x140006997  lea     rcx, [rdx+rdx*8]
0x14000699b  shl     rcx, 2; Size
0x14000699f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1400069a4  mov     rbx, rax
0x1400069a7  mov     [rsp+58h+arg_8], rax
0x1400069ac  test    rax, rax
0x1400069af  jnz     short loc_1400069B8
0x1400069b1  call    cs:__imp_?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
0x1400069b7  nop
0x1400069b8  mov     r8, rbx
0x1400069bb  mov     rdx, [rsi+8]
0x1400069bf  mov     rcx, [rsi]
0x1400069c2  call    ??$_Uninit_move@PEAUAPPID_PLUGIN_@@PEAU1@V?$allocator@UAPPID_PLUGIN_@@@std@@U1@@std@@YAPEAUAPPID_PLUGIN_@@PEAU1@00AEAU?$_Wrap_alloc@V?$allocator@UAPPID_PLUGIN_@@@std@@@0@0U_Nonscalar_ptr_iterator_tag@0@@Z; std::_Uninit_move<APPID_PLUGIN_ *,APPID_PLUGIN_ *,std::allocator<APPID_PLUGIN_>,APPID_PLUGIN_>(APPID_PLUGIN_ *,APPID_PLUGIN_ *,APPID_PLUGIN_ *,std::_Wrap_alloc<std::allocator<APPID_PLUGIN_>> &,APPID_PLUGIN_ *,std::_Nonscalar_ptr_iterator_tag)
0x1400069c7  nop
0x1400069c8  mov     rcx, [rsi]; Block
0x1400069cb  mov     r14, [rsi+8]
0x1400069cf  sub     r14, rcx
0x1400069d2  sar     r14, 2
0x1400069d6  mov     rax, 8E38E38E38E38E39h
0x1400069e0  imul    r14, rax
0x1400069e4  test    rcx, rcx
0x1400069e7  jz      short loc_1400069EE
0x1400069e9  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1400069ee  mov     rcx, rsi
0x1400069f1  call    cs:__imp_?_Orphan_all@_Container_base0@std@@QEAAXXZ; std::_Container_base0::_Orphan_all(void)
0x1400069f7  lea     rax, [rdi+rdi*8]
0x1400069fb  lea     rcx, [rbx+rax*4]
0x1400069ff  mov     [rsi+10h], rcx
0x140006a03  lea     rax, [r14+r14*8]
0x140006a07  lea     rcx, [rbx+rax*4]
0x140006a0b  mov     [rsi+8], rcx
0x140006a0f  mov     [rsi], rbx
0x140006a12  add     rsp, 38h
0x140006a16  pop     r14
0x140006a18  pop     rdi
0x140006a19  pop     rsi
0x140006a1a  pop     rbx
0x140006a1b  retn
```
