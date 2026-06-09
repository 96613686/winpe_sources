# std::vector<std::unique_ptr<ushort,release::Deleter<release::aifree_tag>>,std::allocator<std::unique_ptr<ushort,release::Deleter<release::aifree_tag>>>>::~vector<std::unique_ptr<ushort,release::Deleter<release::aifree_tag>>,std::allocator<std::unique_ptr<ushort,release::Deleter<release::aifree_tag>>>>(void)

- ea: `0x140002894`
- end: `0x1400028da`
- name: `??1?$vector@V?$unique_ptr@GU?$Deleter@Uaifree_tag@release@@@release@@@std@@V?$allocator@V?$unique_ptr@GU?$Deleter@Uaifree_tag@release@@@release@@@std@@@2@@std@@QEAA@XZ`
- size: `70`
- prototype: `void __fastcall(std::_Container_base0 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x140013d67`

## callees

- `0x14000157c`
- `0x140002894`
- `0x140006880`

## import_xrefs

- `msvcp110_win!?_Orphan_all@_Container_base0@std@@QEAAXXZ` at `0x1400028a3`
- `msvcp110_win!?_Orphan_all@_Container_base0@std@@QEAAXXZ` at `0x1400028a3`

## pseudocode

```c
void __fastcall std::vector<std::unique_ptr<unsigned short,release::Deleter<release::aifree_tag>>>::~vector<std::unique_ptr<unsigned short,release::Deleter<release::aifree_tag>>>(
        std::_Container_base0 *a1)
{
  __int64 v2; // rcx

  if ( *(_QWORD *)a1 )
  {
    std::_Container_base0::_Orphan_all(a1);
    std::vector<std::unique_ptr<unsigned short,release::Deleter<release::aifree_tag>>>::_Destroy(
      v2,
      *(_QWORD *)a1,
      *((_QWORD *)a1 + 1));
    operator delete(*(void **)a1);
    *(_QWORD *)a1 = 0;
    *((_QWORD *)a1 + 1) = 0;
    *((_QWORD *)a1 + 2) = 0;
  }
}

```

## disassembly

```asm
0x140002894  push    rbx
0x140002896  sub     rsp, 20h
0x14000289a  mov     rbx, rcx
0x14000289d  cmp     qword ptr [rcx], 0
0x1400028a1  jz      short loc_1400028D4
0x1400028a3  call    cs:__imp_?_Orphan_all@_Container_base0@std@@QEAAXXZ; std::_Container_base0::_Orphan_all(void)
0x1400028a9  mov     r8, [rbx+8]
0x1400028ad  mov     rdx, [rbx]
0x1400028b0  call    ?_Destroy@?$vector@V?$unique_ptr@GU?$Deleter@Uaifree_tag@release@@@release@@@std@@V?$allocator@V?$unique_ptr@GU?$Deleter@Uaifree_tag@release@@@release@@@std@@@2@@std@@IEAAXPEAV?$unique_ptr@GU?$Deleter@Uaifree_tag@release@@@release@@@2@0@Z; std::vector<std::unique_ptr<ushort,release::Deleter<release::aifree_tag>>>::_Destroy(std::unique_ptr<ushort,release::Deleter<release::aifree_tag>> *,std::unique_ptr<ushort,release::Deleter<release::aifree_tag>> *)
0x1400028b5  mov     rcx, [rbx]; Block
0x1400028b8  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1400028bd  mov     qword ptr [rbx], 0
0x1400028c4  mov     qword ptr [rbx+8], 0
0x1400028cc  mov     qword ptr [rbx+10h], 0
0x1400028d4  add     rsp, 20h
0x1400028d8  pop     rbx
0x1400028d9  retn
```
