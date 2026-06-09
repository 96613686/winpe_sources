# std::map<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::less<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const>,std::allocator<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>>::~map<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::less<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const>,std::allocator<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>>(void)

- ea: `0x140008820`
- end: `0x140008861`
- name: `??1?$map@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@QEAA@XZ`
- size: `65`
- prototype: `void __fastcall(void **)`
- caller_count: `5`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x140012273`
- `0x140012297`
- `0x140012526`
- `0x140012579`
- `0x1400125af`

## callees

- `0x14000ec30`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x140008854`
- `msvcrt!??3@YAXPEAX@Z` at `0x140008854`

## pseudocode

```c
void __fastcall std::map<std::wstring const,std::wstring>::~map<std::wstring const,std::wstring,std::less<std::wstring const>,std::allocator<std::pair<std::wstring const,std::wstring>>>(
        void **a1)
{
  std::_Tree<std::_Tmap_traits<std::wstring const,std::wstring,std::less<std::wstring const>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::_Erase(
    a1,
    *((_QWORD *)*a1 + 1));
  *((_QWORD *)*a1 + 1) = *a1;
  *(_QWORD *)*a1 = *a1;
  *((_QWORD *)*a1 + 2) = *a1;
  a1[1] = 0;
  operator delete(*a1);
}

```

## disassembly

```asm
0x140008820  push    rbx
0x140008822  sub     rsp, 20h
0x140008826  mov     rbx, rcx
0x140008829  mov     rdx, [rcx]
0x14000882c  mov     rdx, [rdx+8]
0x140008830  call    ?_Erase@?$_Tree@V?$_Tmap_traits@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@$0A@@std@@@std@@IEAAXPEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@PEAX@2@@Z; std::_Tree<std::_Tmap_traits<std::wstring const,std::wstring,std::less<std::wstring const>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::_Erase(std::_Tree_node<std::pair<std::wstring const,std::wstring>,void *> *)
0x140008835  mov     rax, [rbx]
0x140008838  mov     [rax+8], rax
0x14000883c  mov     rax, [rbx]
0x14000883f  mov     [rax], rax
0x140008842  mov     rax, [rbx]
0x140008845  mov     [rax+10h], rax
0x140008849  mov     qword ptr [rbx+8], 0
0x140008851  mov     rcx, [rbx]
0x140008854  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x14000885a  nop
0x14000885b  add     rsp, 20h
0x14000885f  pop     rbx
0x140008860  retn
```
