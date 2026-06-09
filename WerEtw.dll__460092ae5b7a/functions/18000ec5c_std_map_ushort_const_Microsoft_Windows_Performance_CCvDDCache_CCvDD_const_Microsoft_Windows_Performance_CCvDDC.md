# std::map<ushort const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>::operator[](ushort const * &&)

- ea: `0x18000ec5c`
- end: `0x18000ed50`
- name: `??A?$map@PEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@UlessLPCWSTR_ci@2345@V?$allocator@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@@std@@QEAAAEAPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@$$QEAPEBG@Z`
- size: `244`
- prototype: `__int64 __fastcall(__int64 *, _QWORD *)`
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18000edc4`
- `0x18000f1d8`

## callees

- `0x1800018a0`
- `0x18000ec5c`
- `0x180015920`
- `0x180015b50`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18000ec90`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18000ecc0`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18000ec90`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18000ecc0`

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
                 &v11,
                 v9);
  }
  return inserted + 40;
}

```

## disassembly

```asm
0x18000ec5c  push    rbx
0x18000ec5e  push    rbp
0x18000ec5f  push    rsi
0x18000ec60  push    rdi
0x18000ec61  push    r13
0x18000ec63  push    r14
0x18000ec65  push    r15
0x18000ec67  sub     rsp, 30h
0x18000ec6b  mov     r14, rdx
0x18000ec6e  mov     rsi, rcx
0x18000ec71  mov     rdi, [rcx]
0x18000ec74  mov     r15, [rdi+8]
0x18000ec78  xor     ebp, ebp
0x18000ec7a  xor     r13d, r13d
0x18000ec7d  mov     rbx, r15
0x18000ec80  cmp     [r15+19h], bpl
0x18000ec84  jnz     short loc_18000ECB3
0x18000ec86  mov     r15, rbx
0x18000ec89  mov     rdx, [r14]
0x18000ec8c  mov     rcx, [rbx+20h]
0x18000ec90  call    cs:__imp__o__wcsicmp
0x18000ec96  test    eax, eax
0x18000ec98  jns     short loc_18000ECA2
0x18000ec9a  xor     ebp, ebp
0x18000ec9c  mov     rbx, [rbx+10h]
0x18000eca0  jmp     short loc_18000ECAD
0x18000eca2  mov     ebp, 1
0x18000eca7  mov     rdi, rbx
0x18000ecaa  mov     rbx, [rbx]
0x18000ecad  cmp     [rbx+19h], r13b
0x18000ecb1  jz      short loc_18000EC86
0x18000ecb3  cmp     [rdi+19h], r13b
0x18000ecb7  jnz     short loc_18000ECCA
0x18000ecb9  mov     rdx, [rdi+20h]
0x18000ecbd  mov     rcx, [r14]
0x18000ecc0  call    cs:__imp__o__wcsicmp
0x18000ecc6  test    eax, eax
0x18000ecc8  jns     short loc_18000ED37
0x18000ecca  mov     rax, 555555555555555h
0x18000ecd4  cmp     [rsi+8], rax
0x18000ecd8  jz      short loc_18000ED4A
0x18000ecda  mov     rbx, [rsi]
0x18000ecdd  mov     [rsp+68h+var_48], rsi
0x18000ece2  mov     [rsp+68h+var_40], 0
0x18000eceb  mov     ecx, 30h ; '0'; Size
0x18000ecf0  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000ecf5  nop
0x18000ecf6  mov     rcx, [r14]
0x18000ecf9  mov     [rax+20h], rcx
0x18000ecfd  mov     qword ptr [rax+28h], 0
0x18000ed05  mov     [rax], rbx
0x18000ed08  mov     [rax+8], rbx
0x18000ed0c  mov     [rax+10h], rbx
0x18000ed10  mov     word ptr [rax+18h], 0
0x18000ed16  mov     [rsp+68h+var_48], r15
0x18000ed1b  mov     dword ptr [rsp+68h+var_40], ebp
0x18000ed1f  mov     dword ptr [rsp+68h+var_40+4], r13d
0x18000ed24  mov     r8, rax
0x18000ed27  lea     rdx, [rsp+68h+var_48]
0x18000ed2c  mov     rcx, rsi
0x18000ed2f  call    ?_Insert_node@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CB_KV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@std@@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CB_KV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@std@@PEAX@2@U?$_Tree_id@PEAU?$_Tree_node@U?$pair@$$CB_KV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@std@@PEAX@std@@@2@QEAU32@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64 const,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>>::_Insert_node(std::_Tree_id<std::_Tree_node<std::pair<unsigned __int64 const,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,void *> *>,std::_Tree_node<std::pair<unsigned __int64 const,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,void *> * const)
0x18000ed34  mov     rdi, rax
0x18000ed37  lea     rax, [rdi+28h]
0x18000ed3b  add     rsp, 30h
0x18000ed3f  pop     r15
0x18000ed41  pop     r14
0x18000ed43  pop     r13
0x18000ed45  pop     rdi
0x18000ed46  pop     rsi
0x18000ed47  pop     rbp
0x18000ed48  pop     rbx
0x18000ed49  retn
0x18000ed4a  call    ?_Throw_tree_length_error@std@@YAXXZ; std::_Throw_tree_length_error(void)
```
