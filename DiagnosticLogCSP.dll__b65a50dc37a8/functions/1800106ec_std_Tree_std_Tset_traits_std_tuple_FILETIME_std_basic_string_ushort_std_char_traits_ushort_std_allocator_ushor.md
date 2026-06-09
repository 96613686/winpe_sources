# std::_Tree<std::_Tset_traits<std::tuple<_FILETIME,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,FileTimeComparer,std::allocator<std::tuple<_FILETIME,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>,0>>::~_Tree<std::_Tset_traits<std::tuple<_FILETIME,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,FileTimeComparer,std::allocator<std::tuple<_FILETIME,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>,0>>(void)

- ea: `0x1800106ec`
- end: `0x180010754`
- name: `??1?$_Tree@V?$_Tset_traits@V?$tuple@U_FILETIME@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@UFileTimeComparer@@V?$allocator@V?$tuple@U_FILETIME@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@2@$0A@@std@@@std@@QEAA@XZ`
- size: `104`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180010798`
- `0x180010ed4`

## callees

- `0x180001bf8`
- `0x18000a924`
- `0x18001045c`
- `0x1800106ec`

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
    operator delete(v3);
  }
  operator delete(*a1);
}

```

## disassembly

```asm
0x1800106ec  mov     [rsp+arg_0], rbx
0x1800106f1  mov     [rsp+arg_8], rsi
0x1800106f6  push    rdi
0x1800106f7  sub     rsp, 20h
0x1800106fb  mov     rax, [rcx]
0x1800106fe  mov     rsi, rcx
0x180010701  mov     rdi, [rax+8]
0x180010705  jmp     short loc_180010732
0x180010707  mov     r8, [rdi+10h]
0x18001070b  mov     rdx, rsi
0x18001070e  mov     rcx, rsi
0x180010711  call    ??$_Erase_tree@V?$allocator@U?$_Tree_node@V?$tuple@U_FILETIME@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@V?$tuple@U_FILETIME@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@V?$tuple@U_FILETIME@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@PEAX@std@@@1@PEAU?$_Tree_node@V?$tuple@U_FILETIME@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@PEAX@1@@Z; std::_Tree_val<std::_Tree_simple_types<std::tuple<_FILETIME,std::wstring>>>::_Erase_tree<std::allocator<std::_Tree_node<std::tuple<_FILETIME,std::wstring>,void *>>>(std::allocator<std::_Tree_node<std::tuple<_FILETIME,std::wstring>,void *>> &,std::_Tree_node<std::tuple<_FILETIME,std::wstring>,void *> *)
0x180010716  mov     rbx, rdi
0x180010719  mov     rdi, [rdi]
0x18001071c  lea     rcx, [rbx+20h]
0x180010720  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180010725  mov     edx, 48h ; 'H'; unsigned __int64
0x18001072a  mov     rcx, rbx; void *
0x18001072d  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180010732  cmp     byte ptr [rdi+19h], 0
0x180010736  jz      short loc_180010707
0x180010738  mov     rcx, [rsi]; void *
0x18001073b  mov     edx, 48h ; 'H'; unsigned __int64
0x180010740  mov     rbx, [rsp+28h+arg_0]
0x180010745  mov     rsi, [rsp+28h+arg_8]
0x18001074a  add     rsp, 20h
0x18001074e  pop     rdi
0x18001074f  jmp     ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
```
