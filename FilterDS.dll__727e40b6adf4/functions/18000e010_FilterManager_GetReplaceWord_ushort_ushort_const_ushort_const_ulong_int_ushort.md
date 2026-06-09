# FilterManager::GetReplaceWord(ushort *,ushort const *,ushort const *,ulong,int *,ushort * *)

- ea: `0x18000e010`
- end: `0x18000e0a0`
- name: `?GetReplaceWord@FilterManager@@UEAAXPEAGPEBG1KPEAHPEAPEAG@Z`
- size: `144`
- prototype: `void __fastcall(FilterManager *this, unsigned __int16 *, char *, const unsigned __int16 *, unsigned int, int *, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x18000dd08`
- `0x18000e010`
- `0x18000e21c`

## pseudocode

```c
void __fastcall FilterManager::GetReplaceWord(
        FilterManager *this,
        unsigned __int16 *a2,
        char *a3,
        const unsigned __int16 *a4,
        unsigned int a5,
        int *a6,
        unsigned __int16 **a7)
{
  int *v7; // rdi
  unsigned __int16 ***v8; // rbx
  unsigned __int16 **v9; // rsi
  __int64 v13; // rcx

  v7 = a6;
  v8 = (unsigned __int16 ***)((char *)this + 16);
  v9 = a7;
  LOBYTE(a6) = 1;
  *v7 = 0;
  *v9 = 0;
  std::_Hash<std::_Umap_traits<enum FilterType,std::unique_ptr<std::vector<std::unique_ptr<FilterAgent>>>,std::_Uhash_compare<enum FilterType,std::hash<enum FilterType>,std::equal_to<enum FilterType>>,std::allocator<std::pair<enum FilterType const,std::unique_ptr<std::vector<std::unique_ptr<FilterAgent>>>>>,0>>::find(
    (__int64 *)this + 2,
    (__int64 **)&a7,
    (char *)&a6);
  if ( a7 != *v8 )
    FilterManager::GetReplaceByType(v13, (FilterAgent ****)a7 + 3, a2, a3, (__int64)a4, a5, v7, v9);
}

```

## disassembly

```asm
0x18000e010  mov     rax, rsp
0x18000e013  push    rbx
0x18000e014  push    rbp
0x18000e015  push    rsi
0x18000e016  push    rdi
0x18000e017  push    r14
0x18000e019  push    r15
0x18000e01b  sub     rsp, 48h
0x18000e01f  mov     rdi, [rsp+78h+arg_28]
0x18000e027  lea     rbx, [rcx+10h]
0x18000e02b  mov     rsi, [rsp+78h+arg_30]
0x18000e033  mov     r14, r8
0x18000e036  mov     r15, rdx
0x18000e039  mov     byte ptr [rax+30h], 1
0x18000e03d  lea     r8, [rax+30h]
0x18000e041  mov     rcx, rbx
0x18000e044  mov     dword ptr [rdi], 0
0x18000e04a  lea     rdx, [rax+38h]
0x18000e04e  mov     qword ptr [rsi], 0
0x18000e055  mov     rbp, r9
0x18000e058  call    ?find@?$_Hash@V?$_Umap_traits@W4FilterType@@V?$unique_ptr@V?$vector@V?$unique_ptr@VFilterAgent@@U?$default_delete@VFilterAgent@@@std@@@std@@V?$allocator@V?$unique_ptr@VFilterAgent@@U?$default_delete@VFilterAgent@@@std@@@std@@@2@@std@@U?$default_delete@V?$vector@V?$unique_ptr@VFilterAgent@@U?$default_delete@VFilterAgent@@@std@@@std@@V?$allocator@V?$unique_ptr@VFilterAgent@@U?$default_delete@VFilterAgent@@@std@@@std@@@2@@std@@@2@@std@@V?$_Uhash_compare@W4FilterType@@U?$hash@W4FilterType@@@std@@U?$equal_to@W4FilterType@@@3@@3@V?$allocator@U?$pair@$$CBW4FilterType@@V?$unique_ptr@V?$vector@V?$unique_ptr@VFilterAgent@@U?$default_delete@VFilterAgent@@@std@@@std@@V?$allocator@V?$unique_ptr@VFilterAgent@@U?$default_delete@VFilterAgent@@@std@@@std@@@2@@std@@U?$default_delete@V?$vector@V?$unique_ptr@VFilterAgent@@U?$default_delete@VFilterAgent@@@std@@@std@@V?$allocator@V?$unique_ptr@VFilterAgent@@U?$default_delete@VFilterAgent@@@std@@@std@@@2@@std@@@2@@std@@@std@@@3@$0A@@std@@@std@@QEAA?AV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBW4FilterType@@V?$unique_ptr@V?$vector@V?$unique_ptr@VFilterAgent@@U?$default_delete@VFilterAgent@@@std@@@std@@V?$allocator@V?$unique_ptr@VFilterAgent@@U?$default_delete@VFilterAgent@@@std@@@std@@@2@@std@@U?$default_delete@V?$vector@V?$unique_ptr@VFilterAgent@@U?$default_delete@VFilterAgent@@@std@@@std@@V?$allocator@V?$unique_ptr@VFilterAgent@@U?$default_delete@VFilterAgent@@@std@@@std@@@2@@std@@@2@@std@@@std@@@std@@@std@@@2@AEBW4FilterType@@@Z; std::_Hash<std::_Umap_traits<FilterType,std::unique_ptr<std::vector<std::unique_ptr<FilterAgent>>>,std::_Uhash_compare<FilterType,std::hash<FilterType>,std::equal_to<FilterType>>,std::allocator<std::pair<FilterType const,std::unique_ptr<std::vector<std::unique_ptr<FilterAgent>>>>>,0>>::find(FilterType const &)
0x18000e05d  mov     rdx, [rsp+78h+arg_30]
0x18000e065  cmp     rdx, [rbx]
0x18000e068  jz      short loc_18000E093
0x18000e06a  mov     eax, [rsp+78h+arg_20]
0x18000e071  add     rdx, 18h
0x18000e075  mov     [rsp+78h+var_40], rsi
0x18000e07a  mov     r9, r14
0x18000e07d  mov     [rsp+78h+var_48], rdi
0x18000e082  mov     r8, r15
0x18000e085  mov     [rsp+78h+var_50], eax
0x18000e089  mov     [rsp+78h+var_58], rbp
0x18000e08e  call    ?GetReplaceByType@FilterManager@@IEAAXAEBV?$unique_ptr@V?$vector@V?$unique_ptr@VFilterAgent@@U?$default_delete@VFilterAgent@@@std@@@std@@V?$allocator@V?$unique_ptr@VFilterAgent@@U?$default_delete@VFilterAgent@@@std@@@std@@@2@@std@@U?$default_delete@V?$vector@V?$unique_ptr@VFilterAgent@@U?$default_delete@VFilterAgent@@@std@@@std@@V?$allocator@V?$unique_ptr@VFilterAgent@@U?$default_delete@VFilterAgent@@@std@@@std@@@2@@std@@@2@@std@@PEAGPEBG2KPEAHPEAPEAG@Z; FilterManager::GetReplaceByType(std::unique_ptr<std::vector<std::unique_ptr<FilterAgent>>> const &,ushort *,ushort const *,ushort const *,ulong,int *,ushort * *)
0x18000e093  add     rsp, 48h
0x18000e097  pop     r15
0x18000e099  pop     r14
0x18000e09b  pop     rdi
0x18000e09c  pop     rsi
0x18000e09d  pop     rbp
0x18000e09e  pop     rbx
0x18000e09f  retn
```
