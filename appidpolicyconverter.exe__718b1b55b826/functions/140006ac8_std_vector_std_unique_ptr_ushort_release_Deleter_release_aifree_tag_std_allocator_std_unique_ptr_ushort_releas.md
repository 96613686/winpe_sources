# std::vector<std::unique_ptr<ushort,release::Deleter<release::aifree_tag>>,std::allocator<std::unique_ptr<ushort,release::Deleter<release::aifree_tag>>>>::_Reallocate(unsigned __int64)

- ea: `0x140006ac8`
- end: `0x140006b6d`
- name: `?_Reallocate@?$vector@V?$unique_ptr@GU?$Deleter@Uaifree_tag@release@@@release@@@std@@V?$allocator@V?$unique_ptr@GU?$Deleter@Uaifree_tag@release@@@release@@@std@@@2@@std@@IEAAX_K@Z`
- size: `165`
- prototype: `__int64 *__fastcall(__int64 **, unsigned __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x140006d30`

## callees

- `0x140001530`
- `0x14000157c`
- `0x1400026bc`
- `0x140006880`
- `0x140006ac8`

## import_xrefs

- `msvcp110_win!?_Xbad_alloc@std@@YAXXZ` at `0x140006b0d`
- `msvcp110_win!?_Xbad_alloc@std@@YAXXZ` at `0x140006b0d`
- `msvcp110_win!?_Orphan_all@_Container_base0@std@@QEAAXXZ` at `0x140006b4a`
- `msvcp110_win!?_Orphan_all@_Container_base0@std@@QEAAXXZ` at `0x140006b4a`

## pseudocode

```c
__int64 *__fastcall std::vector<std::unique_ptr<unsigned short,release::Deleter<release::aifree_tag>>>::_Reallocate(
        __int64 **a1,
        unsigned __int64 a2)
{
  __int64 *v4; // rbx
  __int64 v5; // rcx
  __int64 v6; // r14
  __int64 *result; // rax

  v4 = 0;
  if ( a2 )
  {
    if ( a2 > 0x1FFFFFFFFFFFFFFFLL || (v4 = (__int64 *)operator new(8 * a2)) == 0 )
      std::_Xbad_alloc();
  }
  std::_Uninit_move<std::unique_ptr<unsigned short,release::Deleter<release::aifree_tag>> *,std::unique_ptr<unsigned short,release::Deleter<release::aifree_tag>> *,std::allocator<std::unique_ptr<unsigned short,release::Deleter<release::aifree_tag>>>,std::unique_ptr<unsigned short,release::Deleter<release::aifree_tag>>>(
    *a1,
    a1[1],
    v4);
  v6 = a1[1] - *a1;
  if ( *a1 )
  {
    std::vector<std::unique_ptr<unsigned short,release::Deleter<release::aifree_tag>>>::_Destroy(v5, *a1, a1[1]);
    operator delete(*a1);
  }
  std::_Container_base0::_Orphan_all((std::_Container_base0 *)a1);
  a1[2] = &v4[a2];
  result = &v4[v6];
  a1[1] = result;
  *a1 = v4;
  return result;
}

```

## disassembly

```asm
0x140006ac8  push    rbx
0x140006aca  push    rsi
0x140006acb  push    rdi
0x140006acc  push    r14
0x140006ace  sub     rsp, 38h
0x140006ad2  mov     rsi, rdx
0x140006ad5  mov     rdi, rcx
0x140006ad8  xor     ebx, ebx
0x140006ada  mov     [rsp+58h+arg_8], rbx
0x140006adf  test    rdx, rdx
0x140006ae2  jz      short loc_140006B14
0x140006ae4  mov     rax, 1FFFFFFFFFFFFFFFh
0x140006aee  cmp     rdx, rax
0x140006af1  ja      short loc_140006B0D
0x140006af3  lea     rcx, ds:0[rdx*8]; Size
0x140006afb  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140006b00  mov     rbx, rax
0x140006b03  mov     [rsp+58h+arg_8], rax
0x140006b08  test    rax, rax
0x140006b0b  jnz     short loc_140006B14
0x140006b0d  call    cs:__imp_?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
0x140006b13  nop
0x140006b14  mov     r8, rbx
0x140006b17  mov     rdx, [rdi+8]
0x140006b1b  mov     rcx, [rdi]
0x140006b1e  call    ??$_Uninit_move@PEAV?$unique_ptr@GU?$Deleter@Uaifree_tag@release@@@release@@@std@@PEAV12@V?$allocator@V?$unique_ptr@GU?$Deleter@Uaifree_tag@release@@@release@@@std@@@2@V12@@std@@YAPEAV?$unique_ptr@GU?$Deleter@Uaifree_tag@release@@@release@@@0@PEAV10@00AEAU?$_Wrap_alloc@V?$allocator@V?$unique_ptr@GU?$Deleter@Uaifree_tag@release@@@release@@@std@@@std@@@0@0U_Nonscalar_ptr_iterator_tag@0@@Z; std::_Uninit_move<std::unique_ptr<ushort,release::Deleter<release::aifree_tag>> *,std::unique_ptr<ushort,release::Deleter<release::aifree_tag>> *,std::allocator<std::unique_ptr<ushort,release::Deleter<release::aifree_tag>>>,std::unique_ptr<ushort,release::Deleter<release::aifree_tag>>>(std::unique_ptr<ushort,release::Deleter<release::aifree_tag>> *,std::unique_ptr<ushort,release::Deleter<release::aifree_tag>> *,std::unique_ptr<ushort,release::Deleter<release::aifree_tag>> *,std::_Wrap_alloc<std::allocator<std::unique_ptr<ushort,release::Deleter<release::aifree_tag>>>> &,std::unique_ptr<ushort,release::Deleter<release::aifree_tag>> *,std::_Nonscalar_ptr_iterator_tag)
0x140006b23  nop
0x140006b24  mov     rdx, [rdi]
0x140006b27  mov     r8, [rdi+8]
0x140006b2b  mov     r14, r8
0x140006b2e  sub     r14, rdx
0x140006b31  sar     r14, 3
0x140006b35  test    rdx, rdx
0x140006b38  jz      short loc_140006B47
0x140006b3a  call    ?_Destroy@?$vector@V?$unique_ptr@GU?$Deleter@Uaifree_tag@release@@@release@@@std@@V?$allocator@V?$unique_ptr@GU?$Deleter@Uaifree_tag@release@@@release@@@std@@@2@@std@@IEAAXPEAV?$unique_ptr@GU?$Deleter@Uaifree_tag@release@@@release@@@2@0@Z; std::vector<std::unique_ptr<ushort,release::Deleter<release::aifree_tag>>>::_Destroy(std::unique_ptr<ushort,release::Deleter<release::aifree_tag>> *,std::unique_ptr<ushort,release::Deleter<release::aifree_tag>> *)
0x140006b3f  mov     rcx, [rdi]; Block
0x140006b42  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140006b47  mov     rcx, rdi
0x140006b4a  call    cs:__imp_?_Orphan_all@_Container_base0@std@@QEAAXXZ; std::_Container_base0::_Orphan_all(void)
0x140006b50  lea     rax, [rbx+rsi*8]
0x140006b54  mov     [rdi+10h], rax
0x140006b58  lea     rax, [rbx+r14*8]
0x140006b5c  mov     [rdi+8], rax
0x140006b60  mov     [rdi], rbx
0x140006b63  add     rsp, 38h
0x140006b67  pop     r14
0x140006b69  pop     rdi
0x140006b6a  pop     rsi
0x140006b6b  pop     rbx
0x140006b6c  retn
```
