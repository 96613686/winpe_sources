# std::_Tree<std::_Tset_traits<std::tuple<_FILETIME,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,FileTimeComparer,std::allocator<std::tuple<_FILETIME,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>,0>>::~_Tree<std::_Tset_traits<std::tuple<_FILETIME,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,FileTimeComparer,std::allocator<std::tuple<_FILETIME,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>,0>>(void)

- ea: `0x18000fedc`
- end: `0x18000ff44`
- name: `??1?$_Tree@V?$_Tset_traits@V?$tuple@U_FILETIME@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@UFileTimeComparer@@V?$allocator@V?$tuple@U_FILETIME@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@2@$0A@@std@@@std@@QEAA@XZ`
- size: `104`
- prototype: `void __fastcall(void **)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18000ff88`
- `0x180010678`

## callees

- `0x180001bc8`
- `0x18000a600`
- `0x18000fc4c`
- `0x18000fedc`

## pseudocode

```c
void __fastcall std::_Tree<std::_Tset_traits<std::tuple<_FILETIME,std::wstring>,FileTimeComparer,std::allocator<std::tuple<_FILETIME,std::wstring>>,0>>::~_Tree<std::_Tset_traits<std::tuple<_FILETIME,std::wstring>,FileTimeComparer,std::allocator<std::tuple<_FILETIME,std::wstring>>,0>>(
        void **a1)
{
  char *v2; // rdi
  char *v3; // rbx

  v2 = (char *)*((_QWORD *)*a1 + 1);
  while ( !v2[25] )
  {
    std::_Tree_val<std::_Tree_simple_types<std::tuple<_FILETIME,std::wstring>>>::_Erase_tree<std::allocator<std::_Tree_node<std::tuple<_FILETIME,std::wstring>,void *>>>(
      a1,
      a1,
      *((_QWORD *)v2 + 2));
    v3 = v2;
    v2 = *(char **)v2;
    std::wstring::~wstring(v3 + 32);
    operator delete(v3, 0x48u);
  }
  operator delete(*a1, 0x48u);
}

```

## disassembly

```asm
0x18000fedc  mov     [rsp+arg_0], rbx
0x18000fee1  mov     [rsp+arg_8], rsi
0x18000fee6  push    rdi
0x18000fee7  sub     rsp, 20h
0x18000feeb  mov     rax, [rcx]
0x18000feee  mov     rsi, rcx
0x18000fef1  mov     rdi, [rax+8]
0x18000fef5  jmp     short loc_18000FF22
0x18000fef7  mov     r8, [rdi+10h]
0x18000fefb  mov     rdx, rsi
0x18000fefe  mov     rcx, rsi
0x18000ff01  call    ??$_Erase_tree@V?$allocator@U?$_Tree_node@V?$tuple@U_FILETIME@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@V?$tuple@U_FILETIME@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@V?$tuple@U_FILETIME@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@PEAX@std@@@1@PEAU?$_Tree_node@V?$tuple@U_FILETIME@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@PEAX@1@@Z; std::_Tree_val<std::_Tree_simple_types<std::tuple<_FILETIME,std::wstring>>>::_Erase_tree<std::allocator<std::_Tree_node<std::tuple<_FILETIME,std::wstring>,void *>>>(std::allocator<std::_Tree_node<std::tuple<_FILETIME,std::wstring>,void *>> &,std::_Tree_node<std::tuple<_FILETIME,std::wstring>,void *> *)
0x18000ff06  mov     rbx, rdi
0x18000ff09  mov     rdi, [rdi]
0x18000ff0c  lea     rcx, [rbx+20h]
0x18000ff10  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000ff15  mov     edx, 48h ; 'H'; unsigned __int64
0x18000ff1a  mov     rcx, rbx; void *
0x18000ff1d  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000ff22  cmp     byte ptr [rdi+19h], 0
0x18000ff26  jz      short loc_18000FEF7
0x18000ff28  mov     rcx, [rsi]; void *
0x18000ff2b  mov     edx, 48h ; 'H'; unsigned __int64
0x18000ff30  mov     rbx, [rsp+28h+arg_0]
0x18000ff35  mov     rsi, [rsp+28h+arg_8]
0x18000ff3a  add     rsp, 20h
0x18000ff3e  pop     rdi
0x18000ff3f  jmp     ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
```
