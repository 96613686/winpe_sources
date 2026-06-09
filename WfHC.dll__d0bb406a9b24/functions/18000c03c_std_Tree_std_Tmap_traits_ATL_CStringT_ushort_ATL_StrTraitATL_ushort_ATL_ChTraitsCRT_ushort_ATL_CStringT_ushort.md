# std::_Tree<std::_Tmap_traits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,std::less<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,std::allocator<std::pair<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>,1>>::_Erase(std::_Tree_node<std::pair<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,void *> *)

- ea: `0x18000c03c`
- end: `0x18000c0d3`
- name: `?_Erase@?$_Tree@V?$_Tmap_traits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V12@U?$less@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@std@@V?$allocator@U?$pair@$$CBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V12@@std@@@4@$00@std@@@std@@IEAAXPEAU?$_Tree_node@U?$pair@$$CBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V12@@std@@PEAX@2@@Z`
- size: `151`
- prototype: `void __fastcall(__int64, _QWORD *)`
- caller_count: `4`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x180005e60`
- `0x18000a884`
- `0x18000a954`
- `0x18000c03c`

## callees

- `0x18000c03c`
- `0x18000e010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18000c0b4`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000c0b4`

## pseudocode

```c
void __fastcall std::_Tree<std::_Tmap_traits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,std::less<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>,std::allocator<std::pair<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>> const,ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>,1>>::_Erase(
        __int64 a1,
        _QWORD *a2)
{
  _QWORD *v2; // rbx
  _QWORD *i; // rdi
  volatile signed __int32 *v5; // rdx
  volatile signed __int32 *v6; // rdx

  v2 = a2;
  for ( i = a2; !*((_BYTE *)i + 25); v2 = i )
  {
    std::_Tree<std::_Tmap_traits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,std::less<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>,std::allocator<std::pair<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>> const,ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>,1>>::_Erase(
      a1,
      i[2]);
    i = (_QWORD *)*i;
    v5 = (volatile signed __int32 *)(v2[5] - 24LL);
    if ( _InterlockedExchangeAdd(v5 + 4, 0xFFFFFFFF) <= 1 )
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v5 + 8LL))(*(_QWORD *)v5);
    v6 = (volatile signed __int32 *)(v2[4] - 24LL);
    if ( _InterlockedExchangeAdd(v6 + 4, 0xFFFFFFFF) <= 1 )
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v6 + 8LL))(*(_QWORD *)v6);
    operator delete(v2);
  }
}

```

## disassembly

```asm
0x18000c03c  mov     [rsp+arg_0], rbx
0x18000c041  mov     [rsp+arg_8], rsi
0x18000c046  push    rdi
0x18000c047  sub     rsp, 20h
0x18000c04b  cmp     byte ptr [rdx+19h], 0
0x18000c04f  mov     rbx, rdx
0x18000c052  mov     rsi, rcx
0x18000c055  mov     rdi, rdx
0x18000c058  jnz     short loc_18000C0C3
0x18000c05a  mov     rdx, [rdi+10h]
0x18000c05e  mov     rcx, rsi
0x18000c061  call    ?_Erase@?$_Tree@V?$_Tmap_traits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V12@U?$less@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@std@@V?$allocator@U?$pair@$$CBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V12@@std@@@4@$00@std@@@std@@IEAAXPEAU?$_Tree_node@U?$pair@$$CBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V12@@std@@PEAX@2@@Z; std::_Tree<std::_Tmap_traits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,std::less<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,std::allocator<std::pair<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>,1>>::_Erase(std::_Tree_node<std::pair<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,void *> *)
0x18000c066  mov     rdx, [rbx+28h]
0x18000c06a  mov     rdi, [rdi]
0x18000c06d  add     rdx, 0FFFFFFFFFFFFFFE8h
0x18000c071  or      eax, 0FFFFFFFFh
0x18000c074  lock xadd [rdx+10h], eax
0x18000c079  sub     eax, 1
0x18000c07c  jg      short loc_18000C08D
0x18000c07e  mov     rcx, [rdx]
0x18000c081  mov     rax, [rcx]
0x18000c084  mov     rax, [rax+8]
0x18000c088  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c08d  mov     rdx, [rbx+20h]
0x18000c091  add     rdx, 0FFFFFFFFFFFFFFE8h
0x18000c095  or      eax, 0FFFFFFFFh
0x18000c098  lock xadd [rdx+10h], eax
0x18000c09d  sub     eax, 1
0x18000c0a0  jg      short loc_18000C0B1
0x18000c0a2  mov     rcx, [rdx]
0x18000c0a5  mov     rax, [rcx]
0x18000c0a8  mov     rax, [rax+8]
0x18000c0ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c0b1  mov     rcx, rbx
0x18000c0b4  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000c0ba  cmp     byte ptr [rdi+19h], 0
0x18000c0be  mov     rbx, rdi
0x18000c0c1  jz      short loc_18000C05A
0x18000c0c3  mov     rbx, [rsp+28h+arg_0]
0x18000c0c8  mov     rsi, [rsp+28h+arg_8]
0x18000c0cd  add     rsp, 20h
0x18000c0d1  pop     rdi
0x18000c0d2  retn
```
