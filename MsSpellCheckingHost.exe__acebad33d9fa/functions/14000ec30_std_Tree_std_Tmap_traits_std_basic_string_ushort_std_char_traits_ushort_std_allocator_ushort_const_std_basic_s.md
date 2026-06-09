# std::_Tree<std::_Tmap_traits<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::less<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const>,std::allocator<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>,0>>::_Erase(std::_Tree_node<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,void *> *)

- ea: `0x14000ec30`
- end: `0x14000eccd`
- name: `?_Erase@?$_Tree@V?$_Tmap_traits@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@$0A@@std@@@std@@IEAAXPEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@PEAX@2@@Z`
- size: `157`
- prototype: `void __fastcall(__int64, __int64 *)`
- caller_count: `7`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x140008564`
- `0x140008820`
- `0x14000ae40`
- `0x14000afe0`
- `0x14000ec30`
- `0x140010d08`
- `0x140012194`

## callees

- `0x14000ec30`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x14000ec68`
- `msvcrt!??3@YAXPEAX@Z` at `0x14000ec8f`
- `msvcrt!??3@YAXPEAX@Z` at `0x14000ecae`
- `msvcrt!??3@YAXPEAX@Z` at `0x14000ec68`
- `msvcrt!??3@YAXPEAX@Z` at `0x14000ec8f`
- `msvcrt!??3@YAXPEAX@Z` at `0x14000ecae`

## pseudocode

```c
void __fastcall std::_Tree<std::_Tmap_traits<std::wstring const,std::wstring,std::less<std::wstring const>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::_Erase(
        __int64 a1,
        __int64 *a2)
{
  __int64 *v2; // rbx
  __int64 *i; // rdi

  v2 = a2;
  for ( i = a2; !*((_BYTE *)i + 25); v2 = i )
  {
    std::_Tree<std::_Tmap_traits<std::wstring const,std::wstring,std::less<std::wstring const>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::_Erase(
      a1,
      i[2]);
    i = (__int64 *)*i;
    if ( (unsigned __int64)v2[11] >= 8 )
      operator delete((void *)v2[8]);
    v2[11] = 7;
    v2[10] = 0;
    *((_WORD *)v2 + 32) = 0;
    if ( (unsigned __int64)v2[7] >= 8 )
      operator delete((void *)v2[4]);
    v2[7] = 7;
    v2[6] = 0;
    *((_WORD *)v2 + 16) = 0;
    operator delete(v2);
  }
}

```

## disassembly

```asm
0x14000ec30  mov     [rsp+arg_0], rbx
0x14000ec35  mov     [rsp+arg_8], rsi
0x14000ec3a  push    rdi
0x14000ec3b  sub     rsp, 20h
0x14000ec3f  cmp     byte ptr [rdx+19h], 0
0x14000ec43  mov     rbx, rdx
0x14000ec46  mov     rsi, rcx
0x14000ec49  mov     rdi, rdx
0x14000ec4c  jnz     short loc_14000ECBD
0x14000ec4e  mov     rdx, [rdi+10h]
0x14000ec52  mov     rcx, rsi
0x14000ec55  call    ?_Erase@?$_Tree@V?$_Tmap_traits@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@$0A@@std@@@std@@IEAAXPEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@PEAX@2@@Z; std::_Tree<std::_Tmap_traits<std::wstring const,std::wstring,std::less<std::wstring const>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::_Erase(std::_Tree_node<std::pair<std::wstring const,std::wstring>,void *> *)
0x14000ec5a  cmp     qword ptr [rbx+58h], 8
0x14000ec5f  mov     rdi, [rdi]
0x14000ec62  jb      short loc_14000EC6E
0x14000ec64  mov     rcx, [rbx+40h]
0x14000ec68  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x14000ec6e  xor     eax, eax
0x14000ec70  mov     qword ptr [rbx+58h], 7
0x14000ec78  mov     qword ptr [rbx+50h], 0
0x14000ec80  mov     [rbx+40h], ax
0x14000ec84  cmp     qword ptr [rbx+38h], 8
0x14000ec89  jb      short loc_14000EC95
0x14000ec8b  mov     rcx, [rbx+20h]
0x14000ec8f  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x14000ec95  xor     eax, eax
0x14000ec97  mov     qword ptr [rbx+38h], 7
0x14000ec9f  mov     qword ptr [rbx+30h], 0
0x14000eca7  mov     rcx, rbx
0x14000ecaa  mov     [rbx+20h], ax
0x14000ecae  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x14000ecb4  cmp     byte ptr [rdi+19h], 0
0x14000ecb8  mov     rbx, rdi
0x14000ecbb  jz      short loc_14000EC4E
0x14000ecbd  mov     rbx, [rsp+28h+arg_0]
0x14000ecc2  mov     rsi, [rsp+28h+arg_8]
0x14000ecc7  add     rsp, 20h
0x14000eccb  pop     rdi
0x14000eccc  retn
```
