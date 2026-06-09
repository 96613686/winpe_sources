# std::_Tree<std::_Tmap_traits<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::less<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const>,std::allocator<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>,0>>::_Destroy_if_not_nil(std::_Tree_node<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,void *> *)

- ea: `0x14000eb8c`
- end: `0x14000ebf2`
- name: `?_Destroy_if_not_nil@?$_Tree@V?$_Tmap_traits@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@$0A@@std@@@std@@IEAAXPEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@PEAX@2@@Z`
- size: `102`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `3`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x14000791c`
- `0x1400121be`
- `0x1400121e7`

## callees

- `0x14000eb8c`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x14000eba0`
- `msvcrt!??3@YAXPEAX@Z` at `0x14000ebc7`
- `msvcrt!??3@YAXPEAX@Z` at `0x14000eba0`
- `msvcrt!??3@YAXPEAX@Z` at `0x14000ebc7`
- `msvcrt!??3@YAXPEAX@Z` at `0x14000ebeb`

## pseudocode

```c
void __fastcall std::_Tree<std::_Tmap_traits<std::wstring const,std::wstring,std::less<std::wstring const>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::_Destroy_if_not_nil(
        __int64 a1,
        __int64 a2)
{
  if ( *(_QWORD *)(a2 + 88) >= 8u )
    operator delete(*(void **)(a2 + 64));
  *(_QWORD *)(a2 + 88) = 7;
  *(_QWORD *)(a2 + 80) = 0;
  *(_WORD *)(a2 + 64) = 0;
  if ( *(_QWORD *)(a2 + 56) >= 8u )
    operator delete(*(void **)(a2 + 32));
  *(_QWORD *)(a2 + 56) = 7;
  *(_QWORD *)(a2 + 48) = 0;
  *(_WORD *)(a2 + 32) = 0;
  operator delete((void *)a2);
}

```

## disassembly

```asm
0x14000eb8c  push    rbx
0x14000eb8e  sub     rsp, 20h
0x14000eb92  cmp     qword ptr [rdx+58h], 8
0x14000eb97  mov     rbx, rdx
0x14000eb9a  jb      short loc_14000EBA6
0x14000eb9c  mov     rcx, [rdx+40h]
0x14000eba0  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x14000eba6  xor     eax, eax
0x14000eba8  mov     qword ptr [rbx+58h], 7
0x14000ebb0  mov     qword ptr [rbx+50h], 0
0x14000ebb8  mov     [rbx+40h], ax
0x14000ebbc  cmp     qword ptr [rbx+38h], 8
0x14000ebc1  jb      short loc_14000EBCD
0x14000ebc3  mov     rcx, [rbx+20h]
0x14000ebc7  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x14000ebcd  xor     eax, eax
0x14000ebcf  mov     qword ptr [rbx+38h], 7
0x14000ebd7  mov     qword ptr [rbx+30h], 0
0x14000ebdf  mov     rcx, rbx
0x14000ebe2  mov     [rbx+20h], ax
0x14000ebe6  add     rsp, 20h
0x14000ebea  pop     rbx
0x14000ebeb  jmp     cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
```
