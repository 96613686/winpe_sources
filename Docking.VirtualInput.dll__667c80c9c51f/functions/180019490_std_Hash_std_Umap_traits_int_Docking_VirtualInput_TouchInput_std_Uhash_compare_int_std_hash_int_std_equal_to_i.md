# std::_Hash<std::_Umap_traits<int,Docking::VirtualInput::TouchInput,std::_Uhash_compare<int,std::hash<int>,std::equal_to<int>>,std::allocator<std::pair<int const,Docking::VirtualInput::TouchInput>>,0>>::_Unchecked_erase(std::_List_node<std::pair<int const,Docking::VirtualInput::TouchInput>,void *> *,std::_List_node<std::pair<int const,Docking::VirtualInput::TouchInput>,void *> * const)

- ea: `0x180019490`
- end: `0x18001979f`
- name: `?_Unchecked_erase@?$_Hash@V?$_Umap_traits@HUTouchInput@VirtualInput@Docking@@V?$_Uhash_compare@HU?$hash@H@std@@U?$equal_to@H@2@@std@@V?$allocator@U?$pair@$$CBHUTouchInput@VirtualInput@Docking@@@std@@@5@$0A@@std@@@std@@AEAAPEAU?$_List_node@U?$pair@$$CBHUTouchInput@VirtualInput@Docking@@@std@@PEAX@2@PEAU32@QEAU32@@Z`
- size: `783`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180019ba0`

## callees

- `0x18000b810`
- `0x180016980`
- `0x180016db0`
- `0x180018870`
- `0x180019490`
- `0x180019b00`

## pseudocode

```c
__int64 __fastcall std::_Hash<std::_Umap_traits<int,Docking::VirtualInput::TouchInput,std::_Uhash_compare<int,std::hash<int>,std::equal_to<int>>,std::allocator<std::pair<int const,Docking::VirtualInput::TouchInput>>,0>>::_Unchecked_erase(
        __int64 a1,
        __int64 a2,
        __int64 a3)
{
  __int64 v4; // rax
  __int64 v5; // rax
  bool v6; // [rsp+22h] [rbp-96h]
  bool v7; // [rsp+24h] [rbp-94h]
  bool v8; // [rsp+25h] [rbp-93h]
  _BYTE v9[16]; // [rsp+28h] [rbp-90h] BYREF
  __int64 v10; // [rsp+38h] [rbp-80h]
  __int64 v11; // [rsp+40h] [rbp-78h]
  __int64 v12; // [rsp+48h] [rbp-70h]
  _QWORD *v13; // [rsp+50h] [rbp-68h]
  _QWORD *v14; // [rsp+58h] [rbp-60h]
  __int64 v15; // [rsp+60h] [rbp-58h]
  __int64 v16; // [rsp+68h] [rbp-50h]
  _QWORD *v17; // [rsp+70h] [rbp-48h]
  _QWORD *v18; // [rsp+78h] [rbp-40h]
  __int64 v19; // [rsp+80h] [rbp-38h]
  __int64 v20; // [rsp+88h] [rbp-30h]
  __int64 v21; // [rsp+90h] [rbp-28h]
  __int64 v22; // [rsp+98h] [rbp-20h]
  __int64 v23; // [rsp+A0h] [rbp-18h]
  __int64 v24; // [rsp+A8h] [rbp-10h]

  if ( a2 == a3 )
    return a3;
  v12 = *(_QWORD *)(a1 + 8);
  v11 = *(_QWORD *)(a1 + 24);
  std::_Hash<std::_Umap_traits<int,Docking::VirtualInput::TouchInput,std::_Uhash_compare<int,std::hash<int>,std::equal_to<int>>,std::allocator<std::pair<int const,Docking::VirtualInput::TouchInput>>,0>>::_Range_eraser::_Range_eraser(
    v9,
    a1 + 8,
    a2);
  v21 = *(_QWORD *)(a2 + 8);
  v4 = Microsoft::WRL::Details::Forward<std::nullptr_t>(v10 + 16);
  v15 = std::_Hash<std::_Umap_traits<int,Docking::VirtualInput::TouchInput,std::_Uhash_compare<int,std::hash<int>,std::equal_to<int>>,std::allocator<std::pair<int const,Docking::VirtualInput::TouchInput>>,0>>::bucket(
          a1,
          v4);
  v13 = (_QWORD *)(v11 + 16 * v15);
  v14 = v13 + 1;
  v6 = *v13 == v10;
  v19 = v13[1];
  while ( 1 )
  {
    v7 = v10 == v19;
    std::_Hash<std::_Umap_traits<int,Docking::VirtualInput::TouchInput,std::_Uhash_compare<int,std::hash<int>,std::equal_to<int>>,std::allocator<std::pair<int const,Docking::VirtualInput::TouchInput>>,0>>::_Range_eraser::_Bump_erased(v9);
    if ( v7 )
      break;
    if ( v10 == a3 )
    {
      if ( v6 )
        *v13 = v10;
      v20 = a3;
      std::_Hash<std::_Umap_traits<int,Docking::VirtualInput::TouchInput,std::_Uhash_compare<int,std::hash<int>,std::equal_to<int>>,std::allocator<std::pair<int const,Docking::VirtualInput::TouchInput>>,0>>::_Range_eraser::~_Range_eraser(v9);
      return v20;
    }
  }
  if ( v6 )
  {
    *v13 = v12;
    *v14 = v12;
  }
  else
  {
    *v14 = v21;
  }
  while ( v10 != a3 )
  {
    v5 = Microsoft::WRL::Details::Forward<std::nullptr_t>(v10 + 16);
    v16 = std::_Hash<std::_Umap_traits<int,Docking::VirtualInput::TouchInput,std::_Uhash_compare<int,std::hash<int>,std::equal_to<int>>,std::allocator<std::pair<int const,Docking::VirtualInput::TouchInput>>,0>>::bucket(
            a1,
            v5);
    v17 = (_QWORD *)(v11 + 16 * v16);
    v18 = v17 + 1;
    v22 = v17[1];
    while ( 1 )
    {
      v8 = v10 == v22;
      std::_Hash<std::_Umap_traits<int,Docking::VirtualInput::TouchInput,std::_Uhash_compare<int,std::hash<int>,std::equal_to<int>>,std::allocator<std::pair<int const,Docking::VirtualInput::TouchInput>>,0>>::_Range_eraser::_Bump_erased(v9);
      if ( v8 )
        break;
      if ( v10 == a3 )
      {
        *v17 = v10;
        v23 = a3;
        std::_Hash<std::_Umap_traits<int,Docking::VirtualInput::TouchInput,std::_Uhash_compare<int,std::hash<int>,std::equal_to<int>>,std::allocator<std::pair<int const,Docking::VirtualInput::TouchInput>>,0>>::_Range_eraser::~_Range_eraser(v9);
        return v23;
      }
    }
    *v17 = v12;
    *v18 = v12;
  }
  v24 = a3;
  std::_Hash<std::_Umap_traits<int,Docking::VirtualInput::TouchInput,std::_Uhash_compare<int,std::hash<int>,std::equal_to<int>>,std::allocator<std::pair<int const,Docking::VirtualInput::TouchInput>>,0>>::_Range_eraser::~_Range_eraser(v9);
  return v24;
}

```

## disassembly

```asm
0x180019490  mov     [rsp+arg_10], r8
0x180019495  mov     [rsp+arg_8], rdx
0x18001949a  mov     [rsp+arg_0], rcx
0x18001949f  sub     rsp, 0B8h
0x1800194a6  mov     rax, [rsp+0B8h+arg_10]
0x1800194ae  cmp     [rsp+0B8h+arg_8], rax
0x1800194b6  jnz     short loc_1800194C5
0x1800194b8  mov     rax, [rsp+0B8h+arg_10]
0x1800194c0  jmp     loc_180019797
0x1800194c5  mov     rax, [rsp+0B8h+arg_0]
0x1800194cd  mov     rax, [rax+8]
0x1800194d1  mov     [rsp+0B8h+var_70], rax
0x1800194d6  mov     rax, [rsp+0B8h+arg_0]
0x1800194de  mov     rax, [rax+18h]
0x1800194e2  mov     [rsp+0B8h+var_78], rax
0x1800194e7  mov     rax, [rsp+0B8h+arg_0]
0x1800194ef  add     rax, 8
0x1800194f3  mov     r8, [rsp+0B8h+arg_8]
0x1800194fb  mov     rdx, rax
0x1800194fe  lea     rcx, [rsp+0B8h+var_90]
0x180019503  call    ??0_Range_eraser@?$_Hash@V?$_Umap_traits@HUTouchInput@VirtualInput@Docking@@V?$_Uhash_compare@HU?$hash@H@std@@U?$equal_to@H@2@@std@@V?$allocator@U?$pair@$$CBHUTouchInput@VirtualInput@Docking@@@std@@@5@$0A@@std@@@std@@QEAA@AEAV?$list@U?$pair@$$CBHUTouchInput@VirtualInput@Docking@@@std@@V?$allocator@U?$pair@$$CBHUTouchInput@VirtualInput@Docking@@@std@@@2@@2@QEAU?$_List_node@U?$pair@$$CBHUTouchInput@VirtualInput@Docking@@@std@@PEAX@2@@Z; std::_Hash<std::_Umap_traits<int,Docking::VirtualInput::TouchInput,std::_Uhash_compare<int,std::hash<int>,std::equal_to<int>>,std::allocator<std::pair<int const,Docking::VirtualInput::TouchInput>>,0>>::_Range_eraser::_Range_eraser(std::list<std::pair<int const,Docking::VirtualInput::TouchInput>> &,std::_List_node<std::pair<int const,Docking::VirtualInput::TouchInput>,void *> * const)
0x180019508  nop
0x180019509  mov     rax, [rsp+0B8h+arg_8]
0x180019511  mov     rax, [rax+8]
0x180019515  mov     [rsp+0B8h+var_28], rax
0x18001951d  mov     rax, [rsp+0B8h+var_80]
0x180019522  add     rax, 10h
0x180019526  mov     rcx, rax
0x180019529  call    ??$Forward@$$T@Details@WRL@Microsoft@@YA$$QEA$$TAEA$$T@Z
0x18001952e  mov     rdx, rax
0x180019531  mov     rcx, [rsp+0B8h+arg_0]
0x180019539  call    ?bucket@?$_Hash@V?$_Umap_traits@HUTouchInput@VirtualInput@Docking@@V?$_Uhash_compare@HU?$hash@H@std@@U?$equal_to@H@2@@std@@V?$allocator@U?$pair@$$CBHUTouchInput@VirtualInput@Docking@@@std@@@5@$0A@@std@@@std@@QEBA_KAEBH@Z; std::_Hash<std::_Umap_traits<int,Docking::VirtualInput::TouchInput,std::_Uhash_compare<int,std::hash<int>,std::equal_to<int>>,std::allocator<std::pair<int const,Docking::VirtualInput::TouchInput>>,0>>::bucket(int const &)
0x18001953e  mov     [rsp+0B8h+var_58], rax
0x180019543  mov     rax, [rsp+0B8h+var_58]
0x180019548  shl     rax, 1
0x18001954b  mov     rcx, [rsp+0B8h+var_78]
0x180019550  lea     rax, [rcx+rax*8]
0x180019554  mov     [rsp+0B8h+var_68], rax
0x180019559  mov     rax, [rsp+0B8h+var_58]
0x18001955e  shl     rax, 1
0x180019561  mov     rcx, [rsp+0B8h+var_78]
0x180019566  lea     rax, [rcx+rax*8+8]
0x18001956b  mov     [rsp+0B8h+var_60], rax
0x180019570  mov     rax, [rsp+0B8h+var_68]
0x180019575  mov     rcx, [rsp+0B8h+var_80]
0x18001957a  cmp     [rax], rcx
0x18001957d  jnz     short loc_180019586
0x18001957f  mov     [rsp+0B8h+var_98], 1
0x180019584  jmp     short loc_18001958B
0x180019586  mov     [rsp+0B8h+var_98], 0
0x18001958b  movzx   eax, [rsp+0B8h+var_98]
0x180019590  mov     [rsp+0B8h+var_96], al
0x180019594  mov     rax, [rsp+0B8h+var_60]
0x180019599  mov     rax, [rax]
0x18001959c  mov     [rsp+0B8h+var_38], rax
0x1800195a4  mov     rax, [rsp+0B8h+var_38]
0x1800195ac  cmp     [rsp+0B8h+var_80], rax
0x1800195b1  jnz     short loc_1800195BA
0x1800195b3  mov     [rsp+0B8h+var_97], 1
0x1800195b8  jmp     short loc_1800195BF
0x1800195ba  mov     [rsp+0B8h+var_97], 0
0x1800195bf  movzx   eax, [rsp+0B8h+var_97]
0x1800195c4  mov     [rsp+0B8h+var_94], al
0x1800195c8  lea     rcx, [rsp+0B8h+var_90]
0x1800195cd  call    ?_Bump_erased@_Range_eraser@?$_Hash@V?$_Umap_traits@HUTouchInput@VirtualInput@Docking@@V?$_Uhash_compare@HU?$hash@H@std@@U?$equal_to@H@2@@std@@V?$allocator@U?$pair@$$CBHUTouchInput@VirtualInput@Docking@@@std@@@5@$0A@@std@@@std@@QEAAXXZ; std::_Hash<std::_Umap_traits<int,Docking::VirtualInput::TouchInput,std::_Uhash_compare<int,std::hash<int>,std::equal_to<int>>,std::allocator<std::pair<int const,Docking::VirtualInput::TouchInput>>,0>>::_Range_eraser::_Bump_erased(void)
0x1800195d2  nop
0x1800195d3  movzx   eax, [rsp+0B8h+var_94]
0x1800195d8  test    eax, eax
0x1800195da  jz      short loc_1800195DE
0x1800195dc  jmp     short loc_18001962F
0x1800195de  mov     rax, [rsp+0B8h+arg_10]
0x1800195e6  cmp     [rsp+0B8h+var_80], rax
0x1800195eb  jnz     short loc_18001962A
0x1800195ed  movzx   eax, [rsp+0B8h+var_96]
0x1800195f2  test    eax, eax
0x1800195f4  jz      short loc_180019603
0x1800195f6  mov     rax, [rsp+0B8h+var_68]
0x1800195fb  mov     rcx, [rsp+0B8h+var_80]
0x180019600  mov     [rax], rcx
0x180019603  mov     rax, [rsp+0B8h+arg_10]
0x18001960b  mov     [rsp+0B8h+var_30], rax
0x180019613  lea     rcx, [rsp+0B8h+var_90]
0x180019618  call    ??1_Range_eraser@?$_Hash@V?$_Umap_traits@HUTouchInput@VirtualInput@Docking@@V?$_Uhash_compare@HU?$hash@H@std@@U?$equal_to@H@2@@std@@V?$allocator@U?$pair@$$CBHUTouchInput@VirtualInput@Docking@@@std@@@5@$0A@@std@@@std@@QEAA@XZ; std::_Hash<std::_Umap_traits<int,Docking::VirtualInput::TouchInput,std::_Uhash_compare<int,std::hash<int>,std::equal_to<int>>,std::allocator<std::pair<int const,Docking::VirtualInput::TouchInput>>,0>>::_Range_eraser::~_Range_eraser(void)
0x18001961d  mov     rax, [rsp+0B8h+var_30]
0x180019625  jmp     loc_180019797
0x18001962a  jmp     loc_1800195A4
0x18001962f  movzx   eax, [rsp+0B8h+var_96]
0x180019634  test    eax, eax
0x180019636  jz      short loc_180019654
0x180019638  mov     rax, [rsp+0B8h+var_68]
0x18001963d  mov     rcx, [rsp+0B8h+var_70]
0x180019642  mov     [rax], rcx
0x180019645  mov     rax, [rsp+0B8h+var_60]
0x18001964a  mov     rcx, [rsp+0B8h+var_70]
0x18001964f  mov     [rax], rcx
0x180019652  jmp     short loc_180019664
0x180019654  mov     rax, [rsp+0B8h+var_60]
0x180019659  mov     rcx, [rsp+0B8h+var_28]
0x180019661  mov     [rax], rcx
0x180019664  mov     rax, [rsp+0B8h+arg_10]
0x18001966c  cmp     [rsp+0B8h+var_80], rax
0x180019671  jz      loc_180019775
0x180019677  mov     rax, [rsp+0B8h+var_80]
0x18001967c  add     rax, 10h
0x180019680  mov     rcx, rax
0x180019683  call    ??$Forward@$$T@Details@WRL@Microsoft@@YA$$QEA$$TAEA$$T@Z
0x180019688  mov     rdx, rax
0x18001968b  mov     rcx, [rsp+0B8h+arg_0]
0x180019693  call    ?bucket@?$_Hash@V?$_Umap_traits@HUTouchInput@VirtualInput@Docking@@V?$_Uhash_compare@HU?$hash@H@std@@U?$equal_to@H@2@@std@@V?$allocator@U?$pair@$$CBHUTouchInput@VirtualInput@Docking@@@std@@@5@$0A@@std@@@std@@QEBA_KAEBH@Z; std::_Hash<std::_Umap_traits<int,Docking::VirtualInput::TouchInput,std::_Uhash_compare<int,std::hash<int>,std::equal_to<int>>,std::allocator<std::pair<int const,Docking::VirtualInput::TouchInput>>,0>>::bucket(int const &)
0x180019698  mov     [rsp+0B8h+var_50], rax
0x18001969d  mov     rax, [rsp+0B8h+var_50]
0x1800196a2  shl     rax, 1
0x1800196a5  mov     rcx, [rsp+0B8h+var_78]
0x1800196aa  lea     rax, [rcx+rax*8]
0x1800196ae  mov     [rsp+0B8h+var_48], rax
0x1800196b3  mov     rax, [rsp+0B8h+var_50]
0x1800196b8  shl     rax, 1
0x1800196bb  mov     rcx, [rsp+0B8h+var_78]
0x1800196c0  lea     rax, [rcx+rax*8+8]
0x1800196c5  mov     [rsp+0B8h+var_40], rax
0x1800196ca  mov     rax, [rsp+0B8h+var_40]
0x1800196cf  mov     rax, [rax]
0x1800196d2  mov     [rsp+0B8h+var_20], rax
0x1800196da  mov     rax, [rsp+0B8h+var_20]
0x1800196e2  cmp     [rsp+0B8h+var_80], rax
0x1800196e7  jnz     short loc_1800196F0
0x1800196e9  mov     [rsp+0B8h+var_95], 1
0x1800196ee  jmp     short loc_1800196F5
0x1800196f0  mov     [rsp+0B8h+var_95], 0
0x1800196f5  movzx   eax, [rsp+0B8h+var_95]
0x1800196fa  mov     [rsp+0B8h+var_93], al
0x1800196fe  lea     rcx, [rsp+0B8h+var_90]
0x180019703  call    ?_Bump_erased@_Range_eraser@?$_Hash@V?$_Umap_traits@HUTouchInput@VirtualInput@Docking@@V?$_Uhash_compare@HU?$hash@H@std@@U?$equal_to@H@2@@std@@V?$allocator@U?$pair@$$CBHUTouchInput@VirtualInput@Docking@@@std@@@5@$0A@@std@@@std@@QEAAXXZ; std::_Hash<std::_Umap_traits<int,Docking::VirtualInput::TouchInput,std::_Uhash_compare<int,std::hash<int>,std::equal_to<int>>,std::allocator<std::pair<int const,Docking::VirtualInput::TouchInput>>,0>>::_Range_eraser::_Bump_erased(void)
0x180019708  nop
0x180019709  movzx   eax, [rsp+0B8h+var_93]
0x18001970e  test    eax, eax
0x180019710  jz      short loc_180019714
0x180019712  jmp     short loc_180019756
0x180019714  mov     rax, [rsp+0B8h+arg_10]
0x18001971c  cmp     [rsp+0B8h+var_80], rax
0x180019721  jnz     short loc_180019754
0x180019723  mov     rax, [rsp+0B8h+var_48]
0x180019728  mov     rcx, [rsp+0B8h+var_80]
0x18001972d  mov     [rax], rcx
0x180019730  mov     rax, [rsp+0B8h+arg_10]
0x180019738  mov     [rsp+0B8h+var_18], rax
0x180019740  lea     rcx, [rsp+0B8h+var_90]
0x180019745  call    ??1_Range_eraser@?$_Hash@V?$_Umap_traits@HUTouchInput@VirtualInput@Docking@@V?$_Uhash_compare@HU?$hash@H@std@@U?$equal_to@H@2@@std@@V?$allocator@U?$pair@$$CBHUTouchInput@VirtualInput@Docking@@@std@@@5@$0A@@std@@@std@@QEAA@XZ; std::_Hash<std::_Umap_traits<int,Docking::VirtualInput::TouchInput,std::_Uhash_compare<int,std::hash<int>,std::equal_to<int>>,std::allocator<std::pair<int const,Docking::VirtualInput::TouchInput>>,0>>::_Range_eraser::~_Range_eraser(void)
0x18001974a  mov     rax, [rsp+0B8h+var_18]
0x180019752  jmp     short loc_180019797
0x180019754  jmp     short loc_1800196DA
0x180019756  mov     rax, [rsp+0B8h+var_48]
0x18001975b  mov     rcx, [rsp+0B8h+var_70]
0x180019760  mov     [rax], rcx
0x180019763  mov     rax, [rsp+0B8h+var_40]
0x180019768  mov     rcx, [rsp+0B8h+var_70]
0x18001976d  mov     [rax], rcx
0x180019770  jmp     loc_180019664
0x180019775  mov     rax, [rsp+0B8h+arg_10]
0x18001977d  mov     [rsp+0B8h+var_10], rax
0x180019785  lea     rcx, [rsp+0B8h+var_90]
0x18001978a  call    ??1_Range_eraser@?$_Hash@V?$_Umap_traits@HUTouchInput@VirtualInput@Docking@@V?$_Uhash_compare@HU?$hash@H@std@@U?$equal_to@H@2@@std@@V?$allocator@U?$pair@$$CBHUTouchInput@VirtualInput@Docking@@@std@@@5@$0A@@std@@@std@@QEAA@XZ; std::_Hash<std::_Umap_traits<int,Docking::VirtualInput::TouchInput,std::_Uhash_compare<int,std::hash<int>,std::equal_to<int>>,std::allocator<std::pair<int const,Docking::VirtualInput::TouchInput>>,0>>::_Range_eraser::~_Range_eraser(void)
0x18001978f  mov     rax, [rsp+0B8h+var_10]
0x180019797  add     rsp, 0B8h
0x18001979e  retn
```
