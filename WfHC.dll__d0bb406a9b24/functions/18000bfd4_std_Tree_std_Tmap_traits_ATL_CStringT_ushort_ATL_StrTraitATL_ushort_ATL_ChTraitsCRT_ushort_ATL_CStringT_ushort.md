# std::_Tree<std::_Tmap_traits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,std::less<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,std::allocator<std::pair<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>,1>>::_Destroy_if_not_nil(std::_Tree_node<std::pair<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,void *> *)

- ea: `0x18000bfd4`
- end: `0x18000c034`
- name: `?_Destroy_if_not_nil@?$_Tree@V?$_Tmap_traits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V12@U?$less@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@std@@V?$allocator@U?$pair@$$CBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V12@@std@@@4@$00@std@@@std@@IEAAXPEAU?$_Tree_node@U?$pair@$$CBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V12@@std@@PEAX@2@@Z`
- size: `96`
- prototype: `void __fastcall(__int64, _QWORD *)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x18000a394`
- `0x18000cbaa`

## callees

- `0x18000bfd4`
- `0x18000e010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18000c02d`

## pseudocode

```c
void __fastcall std::_Tree<std::_Tmap_traits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,std::less<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>,std::allocator<std::pair<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>> const,ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>,1>>::_Destroy_if_not_nil(
        __int64 a1,
        _QWORD *a2)
{
  volatile signed __int32 *v3; // rdx
  volatile signed __int32 *v4; // rdx

  v3 = (volatile signed __int32 *)(a2[5] - 24LL);
  if ( _InterlockedExchangeAdd(v3 + 4, 0xFFFFFFFF) <= 1 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v3 + 8LL))(*(_QWORD *)v3);
  v4 = (volatile signed __int32 *)(a2[4] - 24LL);
  if ( _InterlockedExchangeAdd(v4 + 4, 0xFFFFFFFF) <= 1 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v4 + 8LL))(*(_QWORD *)v4);
  operator delete(a2);
}

```

## disassembly

```asm
0x18000bfd4  push    rbx
0x18000bfd6  sub     rsp, 20h
0x18000bfda  mov     rbx, rdx
0x18000bfdd  mov     rdx, [rdx+28h]
0x18000bfe1  add     rdx, 0FFFFFFFFFFFFFFE8h
0x18000bfe5  or      eax, 0FFFFFFFFh
0x18000bfe8  lock xadd [rdx+10h], eax
0x18000bfed  sub     eax, 1
0x18000bff0  jg      short loc_18000C001
0x18000bff2  mov     rcx, [rdx]
0x18000bff5  mov     rax, [rcx]
0x18000bff8  mov     rax, [rax+8]
0x18000bffc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c001  mov     rdx, [rbx+20h]
0x18000c005  add     rdx, 0FFFFFFFFFFFFFFE8h
0x18000c009  or      eax, 0FFFFFFFFh
0x18000c00c  lock xadd [rdx+10h], eax
0x18000c011  sub     eax, 1
0x18000c014  jg      short loc_18000C025
0x18000c016  mov     rcx, [rdx]
0x18000c019  mov     rax, [rcx]
0x18000c01c  mov     rax, [rax+8]
0x18000c020  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c025  mov     rcx, rbx
0x18000c028  add     rsp, 20h
0x18000c02c  pop     rbx
0x18000c02d  jmp     cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
```
