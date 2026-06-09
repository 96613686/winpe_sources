# std::map<ushort const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>::operator[](ushort const * &&)

- ea: `0x1800208a0`
- end: `0x1800209a1`
- name: `??A?$map@PEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@UlessLPCWSTR_ci@2345@V?$allocator@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@@std@@QEAAAEAPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@$$QEAPEBG@Z`
- size: `257`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180020a14`
- `0x180020e38`

## callees

- `0x180001bb4`
- `0x18001138c`
- `0x180011618`
- `0x1800208a0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800208d4`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18002090a`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800208d4`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18002090a`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
0x1800208a0  push    rbx
0x1800208a2  push    rbp
0x1800208a3  push    rsi
0x1800208a4  push    rdi
0x1800208a5  push    r13
0x1800208a7  push    r14
0x1800208a9  push    r15
0x1800208ab  sub     rsp, 30h
0x1800208af  mov     r14, rdx
0x1800208b2  mov     rsi, rcx
0x1800208b5  mov     rdi, [rcx]
0x1800208b8  mov     r15, [rdi+8]
0x1800208bc  xor     ebp, ebp
0x1800208be  xor     r13d, r13d
0x1800208c1  mov     rbx, r15
0x1800208c4  cmp     [r15+19h], bpl
0x1800208c8  jnz     short loc_1800208FD
0x1800208ca  mov     r15, rbx
0x1800208cd  mov     rdx, [r14]
0x1800208d0  mov     rcx, [rbx+20h]
0x1800208d4  call    cs:__imp__o__wcsicmp
0x1800208db  nop     dword ptr [rax+rax+00h]
0x1800208e0  test    eax, eax
0x1800208e2  jns     short loc_1800208EC
0x1800208e4  xor     ebp, ebp
0x1800208e6  mov     rbx, [rbx+10h]
0x1800208ea  jmp     short loc_1800208F7
0x1800208ec  mov     ebp, 1
0x1800208f1  mov     rdi, rbx
0x1800208f4  mov     rbx, [rbx]
0x1800208f7  cmp     [rbx+19h], r13b
0x1800208fb  jz      short loc_1800208CA
0x1800208fd  cmp     [rdi+19h], r13b
0x180020901  jnz     short loc_18002091A
0x180020903  mov     rdx, [rdi+20h]
0x180020907  mov     rcx, [r14]
0x18002090a  call    cs:__imp__o__wcsicmp
0x180020911  nop     dword ptr [rax+rax+00h]
0x180020916  test    eax, eax
0x180020918  jns     short loc_180020987
0x18002091a  mov     rax, 555555555555555h
0x180020924  cmp     [rsi+8], rax
0x180020928  jz      short loc_18002099B
0x18002092a  mov     rbx, [rsi]
0x18002092d  mov     [rsp+68h+var_48], rsi
0x180020932  mov     [rsp+68h+var_40], 0
0x18002093b  mov     ecx, 30h ; '0'; Size
0x180020940  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180020945  nop
0x180020946  mov     rcx, [r14]
0x180020949  mov     [rax+20h], rcx
0x18002094d  mov     qword ptr [rax+28h], 0
0x180020955  mov     [rax], rbx
0x180020958  mov     [rax+8], rbx
0x18002095c  mov     [rax+10h], rbx
0x180020960  mov     word ptr [rax+18h], 0
0x180020966  mov     [rsp+68h+var_48], r15
0x18002096b  mov     dword ptr [rsp+68h+var_40], ebp
0x18002096f  mov     dword ptr [rsp+68h+var_40+4], r13d
0x180020974  mov     r8, rax
0x180020977  lea     rdx, [rsp+68h+var_48]
0x18002097c  mov     rcx, rsi
0x18002097f  call    ?_Insert_node@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CB_KV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@std@@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CB_KV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@std@@PEAX@2@U?$_Tree_id@PEAU?$_Tree_node@U?$pair@$$CB_KV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@std@@PEAX@std@@@2@QEAU32@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64 const,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>>::_Insert_node(std::_Tree_id<std::_Tree_node<std::pair<unsigned __int64 const,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,void *> *>,std::_Tree_node<std::pair<unsigned __int64 const,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,void *> * const)
0x180020984  mov     rdi, rax
0x180020987  lea     rax, [rdi+28h]
0x18002098b  add     rsp, 30h
0x18002098f  pop     r15
0x180020991  pop     r14
0x180020993  pop     r13
0x180020995  pop     rdi
0x180020996  pop     rsi
0x180020997  pop     rbp
0x180020998  pop     rbx
0x180020999  retn
0x18002099b  call    ?_Throw_tree_length_error@std@@YAXXZ; std::_Throw_tree_length_error(void)
```
