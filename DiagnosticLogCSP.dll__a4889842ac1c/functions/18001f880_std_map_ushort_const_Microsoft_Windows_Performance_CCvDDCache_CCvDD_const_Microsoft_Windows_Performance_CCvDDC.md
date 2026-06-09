# std::map<ushort const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>::operator[](ushort const * &&)

- ea: `0x18001f880`
- end: `0x18001f974`
- name: `??A?$map@PEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@UlessLPCWSTR_ci@2345@V?$allocator@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@@std@@QEAAAEAPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@$$QEAPEBG@Z`
- size: `244`
- prototype: `__int64 __fastcall(__int64 *, _QWORD *)`
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18001f9e4`
- `0x18001fdf8`

## callees

- `0x180001b84`
- `0x180010b08`
- `0x180010d94`
- `0x18001f880`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18001f8b4`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18001f8e4`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18001f8b4`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18001f8e4`

## pseudocode

```c
__int64 __fastcall std::map<unsigned short const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<unsigned short const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>::operator[](
        __int64 *a1,
        _QWORD *a2)
{
  __int64 inserted; // rdi
  __int64 *v5; // r15
  unsigned int v6; // ebp
  __int64 v7; // rbx
  __int64 v8; // rbx
  __int64 *v9; // rax
  __int64 *v11; // [rsp+20h] [rbp-48h] BYREF
  __int64 v12; // [rsp+28h] [rbp-40h]

  inserted = *a1;
  v5 = *(__int64 **)(*a1 + 8);
  v6 = 0;
  v7 = (__int64)v5;
  if ( !*((_BYTE *)v5 + 25) )
  {
    do
    {
      v5 = (__int64 *)v7;
      if ( (int)_o__wcsicmp(*(_QWORD *)(v7 + 32), *a2) >= 0 )
      {
        v6 = 1;
        inserted = v7;
        v7 = *(_QWORD *)v7;
      }
      else
      {
        v6 = 0;
        v7 = *(_QWORD *)(v7 + 16);
      }
    }
    while ( !*(_BYTE *)(v7 + 25) );
  }
  if ( *(_BYTE *)(inserted + 25) || (int)_o__wcsicmp(*a2, *(_QWORD *)(inserted + 32)) < 0 )
  {
    if ( a1[1] == 0x555555555555555LL )
      std::_Throw_tree_length_error();
    v8 = *a1;
    v11 = a1;
    v12 = 0;
    v9 = (__int64 *)operator new(0x30u);
    v9[4] = *a2;
    v9[5] = 0;
    *v9 = v8;
    v9[1] = v8;
    v9[2] = v8;
    *((_WORD *)v9 + 12) = 0;
    v11 = v5;
    v12 = v6;
    inserted = std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64 const,ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>>::_Insert_node(
                 a1,
                 &v11);
  }
  return inserted + 40;
}

```

## disassembly

```asm
0x18001f880  push    rbx
0x18001f882  push    rbp
0x18001f883  push    rsi
0x18001f884  push    rdi
0x18001f885  push    r13
0x18001f887  push    r14
0x18001f889  push    r15
0x18001f88b  sub     rsp, 30h
0x18001f88f  mov     r14, rdx
0x18001f892  mov     rsi, rcx
0x18001f895  mov     rdi, [rcx]
0x18001f898  mov     r15, [rdi+8]
0x18001f89c  xor     ebp, ebp
0x18001f89e  xor     r13d, r13d
0x18001f8a1  mov     rbx, r15
0x18001f8a4  cmp     [r15+19h], bpl
0x18001f8a8  jnz     short loc_18001F8D7
0x18001f8aa  mov     r15, rbx
0x18001f8ad  mov     rdx, [r14]
0x18001f8b0  mov     rcx, [rbx+20h]
0x18001f8b4  call    cs:__imp__o__wcsicmp
0x18001f8ba  test    eax, eax
0x18001f8bc  jns     short loc_18001F8C6
0x18001f8be  xor     ebp, ebp
0x18001f8c0  mov     rbx, [rbx+10h]
0x18001f8c4  jmp     short loc_18001F8D1
0x18001f8c6  mov     ebp, 1
0x18001f8cb  mov     rdi, rbx
0x18001f8ce  mov     rbx, [rbx]
0x18001f8d1  cmp     [rbx+19h], r13b
0x18001f8d5  jz      short loc_18001F8AA
0x18001f8d7  cmp     [rdi+19h], r13b
0x18001f8db  jnz     short loc_18001F8EE
0x18001f8dd  mov     rdx, [rdi+20h]
0x18001f8e1  mov     rcx, [r14]
0x18001f8e4  call    cs:__imp__o__wcsicmp
0x18001f8ea  test    eax, eax
0x18001f8ec  jns     short loc_18001F95B
0x18001f8ee  mov     rax, 555555555555555h
0x18001f8f8  cmp     [rsi+8], rax
0x18001f8fc  jz      short loc_18001F96E
0x18001f8fe  mov     rbx, [rsi]
0x18001f901  mov     [rsp+68h+var_48], rsi
0x18001f906  mov     [rsp+68h+var_40], 0
0x18001f90f  mov     ecx, 30h ; '0'; Size
0x18001f914  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001f919  nop
0x18001f91a  mov     rcx, [r14]
0x18001f91d  mov     [rax+20h], rcx
0x18001f921  mov     qword ptr [rax+28h], 0
0x18001f929  mov     [rax], rbx
0x18001f92c  mov     [rax+8], rbx
0x18001f930  mov     [rax+10h], rbx
0x18001f934  mov     word ptr [rax+18h], 0
0x18001f93a  mov     [rsp+68h+var_48], r15
0x18001f93f  mov     dword ptr [rsp+68h+var_40], ebp
0x18001f943  mov     dword ptr [rsp+68h+var_40+4], r13d
0x18001f948  mov     r8, rax
0x18001f94b  lea     rdx, [rsp+68h+var_48]
0x18001f950  mov     rcx, rsi
0x18001f953  call    ?_Insert_node@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CB_KV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@std@@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CB_KV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@std@@PEAX@2@U?$_Tree_id@PEAU?$_Tree_node@U?$pair@$$CB_KV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@std@@PEAX@std@@@2@QEAU32@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64 const,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>>::_Insert_node(std::_Tree_id<std::_Tree_node<std::pair<unsigned __int64 const,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,void *> *>,std::_Tree_node<std::pair<unsigned __int64 const,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,void *> * const)
0x18001f958  mov     rdi, rax
0x18001f95b  lea     rax, [rdi+28h]
0x18001f95f  add     rsp, 30h
0x18001f963  pop     r15
0x18001f965  pop     r14
0x18001f967  pop     r13
0x18001f969  pop     rdi
0x18001f96a  pop     rsi
0x18001f96b  pop     rbp
0x18001f96c  pop     rbx
0x18001f96d  retn
0x18001f96e  call    ?_Throw_tree_length_error@std@@YAXXZ; std::_Throw_tree_length_error(void)
```
