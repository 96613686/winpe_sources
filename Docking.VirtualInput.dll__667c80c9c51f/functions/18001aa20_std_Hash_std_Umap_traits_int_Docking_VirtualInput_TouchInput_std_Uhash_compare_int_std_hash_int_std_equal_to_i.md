# std::_Hash<std::_Umap_traits<int,Docking::VirtualInput::TouchInput,std::_Uhash_compare<int,std::hash<int>,std::equal_to<int>>,std::allocator<std::pair<int const,Docking::VirtualInput::TouchInput>>,0>>::_Erase_bucket(std::_List_node<std::pair<int const,Docking::VirtualInput::TouchInput>,void *> *,unsigned __int64)

- ea: `0x18001aa20`
- end: `0x18001aae2`
- name: `?_Erase_bucket@?$_Hash@V?$_Umap_traits@HUTouchInput@VirtualInput@Docking@@V?$_Uhash_compare@HU?$hash@H@std@@U?$equal_to@H@2@@std@@V?$allocator@U?$pair@$$CBHUTouchInput@VirtualInput@Docking@@@std@@@5@$0A@@std@@@std@@IEAAXPEAU?$_List_node@U?$pair@$$CBHUTouchInput@VirtualInput@Docking@@@std@@PEAX@2@_K@Z`
- size: `194`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18001aca0`

## callees

- `0x18001aa20`

## pseudocode

```c
__int64 __fastcall std::_Hash<std::_Umap_traits<int,Docking::VirtualInput::TouchInput,std::_Uhash_compare<int,std::hash<int>,std::equal_to<int>>,std::allocator<std::pair<int const,Docking::VirtualInput::TouchInput>>,0>>::_Erase_bucket(
        __int64 a1,
        _QWORD *a2,
        __int64 a3)
{
  __int64 result; // rax
  _QWORD *v4; // [rsp+0h] [rbp-28h]
  _QWORD *v5; // [rsp+8h] [rbp-20h]
  __int64 v6; // [rsp+10h] [rbp-18h]

  v4 = (_QWORD *)(*(_QWORD *)(a1 + 24) + 16 * a3);
  v5 = v4 + 1;
  if ( (_QWORD *)v4[1] == a2 )
  {
    if ( (_QWORD *)*v4 == a2 )
    {
      v6 = *(_QWORD *)(a1 + 8);
      *v4 = v6;
      result = (__int64)(v4 + 1);
      *v5 = v6;
    }
    else
    {
      result = *(_QWORD *)(a1 + 24) + 16 * a3 + 8;
      *v5 = a2[1];
    }
  }
  else
  {
    result = *(_QWORD *)(a1 + 24) + 16 * a3;
    if ( (_QWORD *)*v4 == a2 )
    {
      result = *(_QWORD *)(a1 + 24) + 16 * a3;
      *v4 = *a2;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18001aa20  mov     [rsp+arg_10], r8
0x18001aa25  mov     [rsp+arg_8], rdx
0x18001aa2a  mov     [rsp+arg_0], rcx
0x18001aa2f  sub     rsp, 28h
0x18001aa33  mov     rax, [rsp+28h+arg_10]
0x18001aa38  shl     rax, 1
0x18001aa3b  mov     rcx, [rsp+28h+arg_0]
0x18001aa40  mov     rcx, [rcx+18h]
0x18001aa44  lea     rax, [rcx+rax*8]
0x18001aa48  mov     [rsp+28h+var_28], rax
0x18001aa4c  mov     rax, [rsp+28h+arg_10]
0x18001aa51  shl     rax, 1
0x18001aa54  mov     rcx, [rsp+28h+arg_0]
0x18001aa59  mov     rcx, [rcx+18h]
0x18001aa5d  lea     rax, [rcx+rax*8+8]
0x18001aa62  mov     [rsp+28h+var_20], rax
0x18001aa67  mov     rax, [rsp+28h+var_20]
0x18001aa6c  mov     rcx, [rsp+28h+arg_8]
0x18001aa71  cmp     [rax], rcx
0x18001aa74  jnz     short loc_18001AAC0
0x18001aa76  mov     rax, [rsp+28h+var_28]
0x18001aa7a  mov     rcx, [rsp+28h+arg_8]
0x18001aa7f  cmp     [rax], rcx
0x18001aa82  jnz     short loc_18001AAAD
0x18001aa84  mov     rax, [rsp+28h+arg_0]
0x18001aa89  mov     rax, [rax+8]
0x18001aa8d  mov     [rsp+28h+var_18], rax
0x18001aa92  mov     rax, [rsp+28h+var_28]
0x18001aa96  mov     rcx, [rsp+28h+var_18]
0x18001aa9b  mov     [rax], rcx
0x18001aa9e  mov     rax, [rsp+28h+var_20]
0x18001aaa3  mov     rcx, [rsp+28h+var_18]
0x18001aaa8  mov     [rax], rcx
0x18001aaab  jmp     short loc_18001AABE
0x18001aaad  mov     rax, [rsp+28h+var_20]
0x18001aab2  mov     rcx, [rsp+28h+arg_8]
0x18001aab7  mov     rcx, [rcx+8]
0x18001aabb  mov     [rax], rcx
0x18001aabe  jmp     short loc_18001AADD
0x18001aac0  mov     rax, [rsp+28h+var_28]
0x18001aac4  mov     rcx, [rsp+28h+arg_8]
0x18001aac9  cmp     [rax], rcx
0x18001aacc  jnz     short loc_18001AADD
0x18001aace  mov     rax, [rsp+28h+var_28]
0x18001aad2  mov     rcx, [rsp+28h+arg_8]
0x18001aad7  mov     rcx, [rcx]
0x18001aada  mov     [rax], rcx
0x18001aadd  add     rsp, 28h
0x18001aae1  retn
```
