# Windows::IEnumOnOwnedSTLImpl<IEnumString,&__s_GUID const _GUID_00000101_0000_0000_c000_000000000046,ushort *,Windows::CopyFromPairWstringToLpolestr,std::map<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::less<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const>,std::allocator<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>>>::Init(std::map<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::less<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const>,std::allocator<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>> &)

- ea: `0x14000ae40`
- end: `0x14000af38`
- name: `?Init@?$IEnumOnOwnedSTLImpl@UIEnumString@@$1?_GUID_00000101_0000_0000_c000_000000000046@@3U__s_GUID@@BPEAGVCopyFromPairWstringToLpolestr@Windows@@V?$map@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@@Windows@@QEAAJAEAV?$map@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@@Z`
- size: `248`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x140009850`
- `0x14000afe0`

## callees

- `0x140007888`
- `0x14000ae40`
- `0x14000ec30`

## pseudocode

```c
__int64 __fastcall Windows::IEnumOnOwnedSTLImpl<IEnumString,&__s_GUID const _GUID_00000101_0000_0000_c000_000000000046,unsigned short *,Windows::CopyFromPairWstringToLpolestr,std::map<std::wstring const,std::wstring>>::Init(
        __int64 a1,
        _QWORD *a2)
{
  __int64 v3; // rdi
  unsigned int v4; // r14d
  __int64 *v5; // rbx
  _QWORD *v6; // r8
  __int64 **v7; // rdx
  __int64 *i; // rcx
  __int64 j; // rcx
  __int64 *v13; // [rsp+50h] [rbp+18h]

  try
  {
    v3 = a1;
    v4 = 0;
    v5 = (__int64 *)(a1 + 8);
    v13 = (__int64 *)(a1 + 8);
    if ( (_QWORD *)(a1 + 8) != a2 )
    {
      std::_Tree<std::_Tmap_traits<std::wstring const,std::wstring,std::less<std::wstring const>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::_Erase(
        a1 + 8,
        *(__int64 **)(*v5 + 8));
      *(_QWORD *)(*v5 + 8) = *v5;
      *(_QWORD *)*v5 = *v5;
      *(_QWORD *)(*v5 + 16) = *v5;
      v5[1] = 0;
      *(_QWORD *)(*v5 + 8) = std::_Tree<std::_Tmap_traits<std::wstring const,std::wstring,std::less<std::wstring const>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::_Copy_nodes<std::integral_constant<bool,0>>(
                               v5,
                               *(_QWORD *)(*a2 + 8LL),
                               *v5,
                               a1);
      v5[1] = a2[1];
      v6 = (_QWORD *)*v5;
      v7 = *(__int64 ***)(*v5 + 8);
      if ( *((_BYTE *)v7 + 25) )
      {
        *v6 = v6;
        *(_QWORD *)(*v5 + 16) = *v5;
      }
      else
      {
        for ( i = *v7; !*((_BYTE *)i + 25); i = (__int64 *)*i )
          v7 = (__int64 **)i;
        *v6 = v7;
        for ( j = *(_QWORD *)(*v5 + 8); !*(_BYTE *)(*(_QWORD *)(j + 16) + 25LL); j = *(_QWORD *)(j + 16) )
          ;
        *(_QWORD *)(*v5 + 16) = j;
      }
    }
  }
  catch ( std::bad_alloc )
  {
    v3 = a1;
    v4 = -2147024882;
    v5 = v13;
  }
  v3 = a1;
  v4 = 0;
}

```

## disassembly

```asm
0x14000ae40  mov     [rsp+arg_18], rbx
0x14000ae45  mov     [rsp+arg_0], rcx
0x14000ae4a  push    rsi
0x14000ae4b  push    rdi
0x14000ae4c  push    r14
0x14000ae4e  sub     rsp, 20h
0x14000ae52  mov     rsi, rdx
0x14000ae55  mov     rdi, rcx
0x14000ae58  xor     r14d, r14d
0x14000ae5b  lea     rbx, [rcx+8]
0x14000ae5f  mov     [rsp+38h+arg_10], rbx
0x14000ae64  cmp     rbx, rdx
0x14000ae67  jz      loc_14000AF0C
0x14000ae6d  mov     rdx, [rbx]
0x14000ae70  mov     rdx, [rdx+8]
0x14000ae74  mov     rcx, rbx
0x14000ae77  call    ?_Erase@?$_Tree@V?$_Tmap_traits@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@$0A@@std@@@std@@IEAAXPEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@PEAX@2@@Z; std::_Tree<std::_Tmap_traits<std::wstring const,std::wstring,std::less<std::wstring const>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::_Erase(std::_Tree_node<std::pair<std::wstring const,std::wstring>,void *> *)
0x14000ae7c  mov     rax, [rbx]
0x14000ae7f  mov     [rax+8], rax
0x14000ae83  mov     rax, [rbx]
0x14000ae86  mov     [rax], rax
0x14000ae89  mov     rax, [rbx]
0x14000ae8c  mov     [rax+10h], rax
0x14000ae90  mov     [rbx+8], r14
0x14000ae94  mov     rdx, [rsi]
0x14000ae97  mov     r9b, byte ptr [rsp+38h+arg_0]
0x14000ae9c  mov     r8, [rbx]
0x14000ae9f  mov     rdx, [rdx+8]
0x14000aea3  mov     rcx, rbx
0x14000aea6  call    ??$_Copy_nodes@U?$integral_constant@_N$0A@@std@@@?$_Tree@V?$_Tmap_traits@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@$0A@@std@@@std@@IEAAPEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@PEAX@1@PEAU21@0U?$integral_constant@_N$0A@@1@@Z; std::_Tree<std::_Tmap_traits<std::wstring const,std::wstring,std::less<std::wstring const>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::_Copy_nodes<std::integral_constant<bool,0>>(std::_Tree_node<std::pair<std::wstring const,std::wstring>,void *> *,std::_Tree_node<std::pair<std::wstring const,std::wstring>,void *> *,std::integral_constant<bool,0>)
0x14000aeab  mov     rcx, rax
0x14000aeae  mov     rax, [rbx]
0x14000aeb1  mov     [rax+8], rcx
0x14000aeb5  mov     rax, [rsi+8]
0x14000aeb9  mov     [rbx+8], rax
0x14000aebd  mov     r8, [rbx]
0x14000aec0  mov     rdx, [r8+8]
0x14000aec4  cmp     [rdx+19h], r14b
0x14000aec8  jnz     short loc_14000AF02
0x14000aeca  mov     rcx, [rdx]
0x14000aecd  cmp     [rcx+19h], r14b
0x14000aed1  jnz     short loc_14000AEE2
0x14000aed3  mov     rdx, rcx
0x14000aed6  mov     rax, [rcx]
0x14000aed9  mov     rcx, rax
0x14000aedc  cmp     byte ptr [rax+19h], 0
0x14000aee0  jz      short loc_14000AED3
0x14000aee2  mov     [r8], rdx
0x14000aee5  mov     rdx, [rbx]
0x14000aee8  mov     rcx, [rdx+8]
0x14000aeec  jmp     short loc_14000AEF2
0x14000aeee  mov     rcx, [rcx+10h]
0x14000aef2  mov     rax, [rcx+10h]
0x14000aef6  cmp     byte ptr [rax+19h], 0
0x14000aefa  jz      short loc_14000AEEE
0x14000aefc  mov     [rdx+10h], rcx
0x14000af00  jmp     short loc_14000AF0C
0x14000af02  mov     [r8], r8
0x14000af05  mov     rax, [rbx]
0x14000af08  mov     [rax+10h], rax
0x14000af0c  jmp     short loc_14000AF1D
0x14000af0e  mov     rdi, [rsp+38h+arg_0]
0x14000af13  mov     r14d, [rsp+38h+arg_8]
0x14000af18  mov     rbx, [rsp+38h+arg_10]
0x14000af1d  mov     rcx, [rbx]
0x14000af20  mov     rdx, [rcx]
0x14000af23  mov     [rdi+18h], rdx
0x14000af27  mov     eax, r14d
0x14000af2a  mov     rbx, [rsp+38h+arg_18]
0x14000af2f  add     rsp, 20h
0x14000af33  pop     r14
0x14000af35  pop     rdi
0x14000af36  pop     rsi
0x14000af37  retn
```
