# ReplaceOOPBitmaps(HMENU__ *,uint,uint,uint,void * const *,ulong const *,std::vector<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HBITMAP__ *,int (*)(void *),&DeleteObject(void *),wistd::integral_constant<unsigned __int64,0>,HBITMAP__ *,HBITMAP__ *,0,std::nullptr_t>>>,std::allocator<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HBITMAP__ *,int (*)(void *),&DeleteObject(void *),wistd::integral_constant<unsigned __int64,0>,HBITMAP__ *,HBITMAP__ *,0,std::nullptr_t>>>>> *)

- ea: `0x180002670`
- end: `0x18000294d`
- name: `?ReplaceOOPBitmaps@@YAXPEAUHMENU__@@IIIPEBQEAXPEBKPEAV?$vector@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHBITMAP__@@P6AHPEAX@Z$1?DeleteObject@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@V?$allocator@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHBITMAP__@@P6AHPEAX@Z$1?DeleteObject@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@std@@@std@@@Z`
- size: `733`
- prototype: `__int64 __fastcall(int, int, int, int, __int64, unsigned int *, __int64)`
- caller_count: `2`
- callee_count: `11`
- tags: `registry_config`

## callers

- `0x180002670`
- `0x18000a500`

## callees

- `0x180002670`
- `0x180002b5c`
- `0x180003760`
- `0x1800037e4`
- `0x1800054d8`
- `0x180005540`
- `0x1800056ac`
- `0x18000578c`
- `0x180007a90`
- `0x180009dfc`
- `0x180009e40`

## import_xrefs

- `ext-ms-win-ntuser-menu-l1-1-0!GetMenuItemInfoA` at `0x18000275f`
- `ext-ms-win-ntuser-menu-l1-1-0!GetMenuItemInfoA` at `0x18000275f`
- `ext-ms-win-ntuser-menu-l1-1-0!GetMenuItemCount` at `0x180002705`
- `ext-ms-win-ntuser-menu-l1-1-0!GetMenuItemCount` at `0x1800028ec`
- `ext-ms-win-ntuser-menu-l1-1-0!GetMenuItemCount` at `0x180002705`
- `ext-ms-win-ntuser-menu-l1-1-0!GetMenuItemCount` at `0x1800028ec`
- `ext-ms-win-ntuser-menu-l1-1-0!SetMenuItemInfoA` at `0x1800028ca`
- `ext-ms-win-ntuser-menu-l1-1-0!SetMenuItemInfoA` at `0x1800028ca`
- `ext-ms-win-rtcore-ntuser-dc-access-l1-1-0!GetDC` at `0x1800026e6`
- `ext-ms-win-rtcore-ntuser-dc-access-l1-1-0!GetDC` at `0x1800026e6`
- `ext-ms-win-gdi-dc-create-l1-1-0!DeleteDC` at `0x180002910`
- `ext-ms-win-rtcore-gdi-object-l1-1-0!DeleteObject` at `0x1800028e1`
- `ext-ms-win-rtcore-gdi-object-l1-1-0!DeleteObject` at `0x1800028e1`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
BOOL __fastcall ReplaceOOPBitmaps(
        HMENU a1,
        UINT a2,
        UINT a3,
        unsigned int a4,
        __int64 a5,
        unsigned int *a6,
        __int64 a7)
{
  unsigned int v10; // r8d
  HDC DC; // rbx
  unsigned int v12; // r8d
  const char *v13; // r9
  signed int i; // edi
  unsigned int v15; // r8d
  const char *v16; // r9
  HBITMAP v17; // rax
  HBITMAP v18; // rax
  HBITMAP v19; // rax
  unsigned int v20; // r8d
  const char *v21; // r9
  int v23; // [rsp+20h] [rbp-91h]
  unsigned int v24; // [rsp+40h] [rbp-71h] BYREF
  HGDIOBJ ho[3]; // [rsp+48h] [rbp-69h] BYREF
  struct tagMENUITEMINFOA mii; // [rsp+60h] [rbp-51h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+47h]

  if ( !(unsigned __int8)IsGetDCPresent()
    || !(unsigned __int8)IsDeleteDCPresent()
    || !(unsigned __int8)IsGetMenuItemInfoWPresent()
    || !(unsigned __int8)IsGetMenuItemInfoWPresent()
    || !(unsigned __int8)IsGetMenuItemInfoWPresent()
    || !(unsigned __int8)IsGetDIBitsPresent() )
  {
    wil::details::in1diag3::Throw_Hr(retaddr, (void *)0x6C, v10, (const char *)0x80004001LL, v23);
  }
  DC = GetDC(0);
  ho[1] = DC;
  if ( !DC )
    wil::details::in1diag3::_Throw_GetLastError(retaddr, (void *)0x70, v12, v13);
  for ( i = 0; i < GetMenuItemCount(a1); ++i )
  {
    memset(&mii.fType, 0, 72);
    mii.cbSize = 80;
    mii.fMask = 142;
    if ( !GetMenuItemInfoA(a1, i, 1, &mii) )
      wil::details::in1diag3::_Throw_GetLastError(retaddr, (void *)0x79, v15, v16);
    if ( mii.wID >= a2 && mii.wID <= a3 )
    {
      if ( mii.hSubMenu )
        ReplaceOOPBitmaps((int)mii.hSubMenu, a2, a3, a4, a5, a6, a7);
      mii.cbSize = 80;
      mii.fMask = 136;
      v24 = 0;
      ho[0] = 0;
      if ( mii.hbmpItem )
      {
        if ( FindFileMappingIndexForHBITMAP(a4, a6, (unsigned int)mii.hbmpItem, &v24) )
        {
          v17 = RecreateSingleBitMap(DC, *(HANDLE *)(a5 + 8LL * v24));
          mii.hbmpItem = v17;
          if ( v17 )
          {
            wil::details::unique_storage<wil::details::resource_policy<HBITMAP__ *,int (*)(void *),&int DeleteObject(void *),wistd::integral_constant<unsigned __int64,0>,HBITMAP__ *,HBITMAP__ *,0,std::nullptr_t>>::reset(
              ho,
              v17);
            std::vector<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HBITMAP__ *,int (*)(void *),&int DeleteObject(void *),wistd::integral_constant<unsigned __int64,0>,HBITMAP__ *,HBITMAP__ *,0,std::nullptr_t>>>>::push_back(
              a7,
              ho);
          }
        }
      }
      if ( mii.hbmpChecked )
      {
        if ( FindFileMappingIndexForHBITMAP(a4, a6, (unsigned int)mii.hbmpChecked, &v24) )
        {
          v18 = RecreateSingleBitMap(DC, *(HANDLE *)(a5 + 8LL * v24));
          mii.hbmpChecked = v18;
          if ( v18 )
          {
            wil::details::unique_storage<wil::details::resource_policy<HBITMAP__ *,int (*)(void *),&int DeleteObject(void *),wistd::integral_constant<unsigned __int64,0>,HBITMAP__ *,HBITMAP__ *,0,std::nullptr_t>>::reset(
              ho,
              v18);
            std::vector<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HBITMAP__ *,int (*)(void *),&int DeleteObject(void *),wistd::integral_constant<unsigned __int64,0>,HBITMAP__ *,HBITMAP__ *,0,std::nullptr_t>>>>::push_back(
              a7,
              ho);
          }
        }
      }
      if ( mii.hbmpUnchecked )
      {
        if ( FindFileMappingIndexForHBITMAP(a4, a6, (unsigned int)mii.hbmpUnchecked, &v24) )
        {
          v19 = RecreateSingleBitMap(DC, *(HANDLE *)(a5 + 8LL * v24));
          mii.hbmpUnchecked = v19;
          if ( v19 )
          {
            wil::details::unique_storage<wil::details::resource_policy<HBITMAP__ *,int (*)(void *),&int DeleteObject(void *),wistd::integral_constant<unsigned __int64,0>,HBITMAP__ *,HBITMAP__ *,0,std::nullptr_t>>::reset(
              ho,
              v19);
            std::vector<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HBITMAP__ *,int (*)(void *),&int DeleteObject(void *),wistd::integral_constant<unsigned __int64,0>,HBITMAP__ *,HBITMAP__ *,0,std::nullptr_t>>>>::push_back(
              a7,
              ho);
          }
        }
      }
      if ( !SetMenuItemInfoA(a1, i, 1, &mii) )
        wil::details::in1diag3::_Throw_GetLastError(retaddr, (void *)0xAA, v20, v21);
      if ( ho[0] )
        DeleteObject(ho[0]);
    }
  }
  return DeleteDC(DC);
}

```

## disassembly

```asm
0x180002670  mov     [rsp-8+arg_18], r9d
0x180002675  push    rbp
0x180002676  push    rbx
0x180002677  push    rsi
0x180002678  push    rdi
0x180002679  push    r12
0x18000267b  push    r13
0x18000267d  push    r14
0x18000267f  push    r15
0x180002681  lea     rbp, [rsp-7]
0x180002686  sub     rsp, 0B8h
0x18000268d  mov     r14d, r8d
0x180002690  mov     r15d, edx
0x180002693  mov     rsi, rcx
0x180002696  call    IsGetDCPresent
0x18000269b  test    al, al
0x18000269d  jz      loc_180002938
0x1800026a3  call    IsDeleteDCPresent
0x1800026a8  test    al, al
0x1800026aa  jz      loc_180002938
0x1800026b0  call    IsGetMenuItemInfoWPresent
0x1800026b5  test    al, al
0x1800026b7  jz      loc_180002938
0x1800026bd  call    IsGetMenuItemInfoWPresent
0x1800026c2  test    al, al
0x1800026c4  jz      loc_180002938
0x1800026ca  call    IsGetMenuItemInfoWPresent
0x1800026cf  test    al, al
0x1800026d1  jz      loc_180002938
0x1800026d7  call    IsGetDIBitsPresent
0x1800026dc  test    al, al
0x1800026de  jz      loc_180002938
0x1800026e4  xor     ecx, ecx; hWnd
0x1800026e6  call    cs:__imp_GetDC
0x1800026ec  mov     rbx, rax
0x1800026ef  mov     [rbp+3Fh+var_A0], rax
0x1800026f3  mov     rcx, [rbp+47h]; this
0x1800026f7  test    rax, rax
0x1800026fa  jz      loc_18000292D
0x180002700  xor     edi, edi
0x180002702  mov     rcx, rsi; hMenu
0x180002705  call    cs:__imp_GetMenuItemCount
0x18000270b  test    eax, eax
0x18000270d  jle     loc_1800028FA
0x180002713  mov     r12, [rbp+3Fh+arg_30]
0x180002717  mov     r13, [rbp+3Fh+arg_20]
0x18000271b  nop     dword ptr [rax+rax+00h]
0x180002720  mov     qword ptr [rbp+3Fh+mii.fType], 0
0x180002728  xorps   xmm0, xmm0
0x18000272b  movdqa  xmmword ptr [rbp+3Fh+mii.wID], xmm0
0x180002730  xorps   xmm1, xmm1
0x180002733  movdqa  xmmword ptr [rbp+3Fh+mii.hbmpChecked], xmm1
0x180002738  movdqa  xmmword ptr [rbp+3Fh+mii.dwItemData], xmm0
0x18000273d  movdqa  xmmword ptr [rbp+3Fh+mii.cch], xmm1
0x180002742  mov     [rbp+3Fh+mii.cbSize], 50h ; 'P'
0x180002749  mov     [rbp+3Fh+mii.fMask], 8Eh
0x180002750  lea     r9, [rbp+3Fh+mii]; lpmii
0x180002754  mov     r8d, 1; fByPosition
0x18000275a  mov     edx, edi; item
0x18000275c  mov     rcx, rsi; hmenu
0x18000275f  call    cs:__imp_GetMenuItemInfoA
0x180002765  mov     rcx, [rbp+47h]; this
0x180002769  test    eax, eax
0x18000276b  jz      loc_180002922
0x180002771  mov     eax, [rbp+3Fh+mii.wID]
0x180002774  cmp     eax, r15d
0x180002777  jb      loc_1800028E7
0x18000277d  cmp     eax, r14d
0x180002780  ja      loc_1800028E7
0x180002786  mov     rcx, [rbp+3Fh+mii.hSubMenu]; int
0x18000278a  test    rcx, rcx
0x18000278d  jz      short loc_1800027B1
0x18000278f  mov     [rsp+0F0h+var_C0], r12; __int64
0x180002794  mov     rax, [rbp+3Fh+arg_28]
0x180002798  mov     [rsp+0F0h+var_C8], rax; unsigned int *
0x18000279d  mov     [rsp+0F0h+var_D0], r13; int
0x1800027a2  mov     r9d, [rbp+3Fh+arg_18]; int
0x1800027a6  mov     r8d, r14d; int
0x1800027a9  mov     edx, r15d; int
0x1800027ac  call    ?ReplaceOOPBitmaps@@YAXPEAUHMENU__@@IIIPEBQEAXPEBKPEAV?$vector@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHBITMAP__@@P6AHPEAX@Z$1?DeleteObject@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@V?$allocator@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHBITMAP__@@P6AHPEAX@Z$1?DeleteObject@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@std@@@std@@@Z
0x1800027b1  mov     [rbp+3Fh+mii.cbSize], 50h ; 'P'
0x1800027b8  mov     [rbp+3Fh+mii.fMask], 88h
0x1800027bf  xor     eax, eax
0x1800027c1  mov     [rbp+3Fh+var_B0], eax
0x1800027c4  mov     [rbp+3Fh+ho], rax
0x1800027c8  mov     rax, [rbp+3Fh+mii.hbmpItem]
0x1800027cc  test    rax, rax
0x1800027cf  jz      short loc_180002819
0x1800027d1  lea     r9, [rbp+3Fh+var_B0]; unsigned int *
0x1800027d5  mov     r8d, eax; unsigned int
0x1800027d8  mov     rdx, [rbp+3Fh+arg_28]; unsigned int *
0x1800027dc  mov     ecx, [rbp+3Fh+arg_18]; unsigned int
0x1800027df  call    ?FindFileMappingIndexForHBITMAP@@YA_NIPEBKKPEAI@Z
0x1800027e4  test    al, al
0x1800027e6  jz      short loc_180002819
0x1800027e8  mov     edx, [rbp+3Fh+var_B0]
0x1800027eb  mov     rdx, [r13+rdx*8+0]; hFileMappingObject
0x1800027f0  mov     rcx, rbx; hdc
0x1800027f3  call    ?RecreateSingleBitMap@@YAPEAUHBITMAP__@@PEAUHDC__@@PEAX@Z
0x1800027f8  mov     [rbp+3Fh+mii.hbmpItem], rax
0x1800027fc  test    rax, rax
0x1800027ff  jz      short loc_180002819
0x180002801  mov     rdx, rax
0x180002804  lea     rcx, [rbp+3Fh+ho]
0x180002808  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHBITMAP__@@P6AHPEAX@Z$1?DeleteObject@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHBITMAP__@@@Z
0x18000280d  lea     rdx, [rbp+3Fh+ho]
0x180002811  mov     rcx, r12
0x180002814  call    ?push_back@?$vector@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHBITMAP__@@P6AHPEAX@Z$1?DeleteObject@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@V?$allocator@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHBITMAP__@@P6AHPEAX@Z$1?DeleteObject@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@std@@@std@@QEAAX$$QEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHBITMAP__@@P6AHPEAX@Z$1?DeleteObject@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@Z
0x180002819  mov     rax, [rbp+3Fh+mii.hbmpChecked]
0x18000281d  test    rax, rax
0x180002820  jz      short loc_18000286A
0x180002822  lea     r9, [rbp+3Fh+var_B0]; unsigned int *
0x180002826  mov     r8d, eax; unsigned int
0x180002829  mov     rdx, [rbp+3Fh+arg_28]; unsigned int *
0x18000282d  mov     ecx, [rbp+3Fh+arg_18]; unsigned int
0x180002830  call    ?FindFileMappingIndexForHBITMAP@@YA_NIPEBKKPEAI@Z
0x180002835  test    al, al
0x180002837  jz      short loc_18000286A
0x180002839  mov     edx, [rbp+3Fh+var_B0]
0x18000283c  mov     rdx, [r13+rdx*8+0]; hFileMappingObject
0x180002841  mov     rcx, rbx; hdc
0x180002844  call    ?RecreateSingleBitMap@@YAPEAUHBITMAP__@@PEAUHDC__@@PEAX@Z
0x180002849  mov     [rbp+3Fh+mii.hbmpChecked], rax
0x18000284d  test    rax, rax
0x180002850  jz      short loc_18000286A
0x180002852  mov     rdx, rax
0x180002855  lea     rcx, [rbp+3Fh+ho]
0x180002859  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHBITMAP__@@P6AHPEAX@Z$1?DeleteObject@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHBITMAP__@@@Z
0x18000285e  lea     rdx, [rbp+3Fh+ho]
0x180002862  mov     rcx, r12
0x180002865  call    ?push_back@?$vector@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHBITMAP__@@P6AHPEAX@Z$1?DeleteObject@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@V?$allocator@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHBITMAP__@@P6AHPEAX@Z$1?DeleteObject@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@std@@@std@@QEAAX$$QEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHBITMAP__@@P6AHPEAX@Z$1?DeleteObject@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@Z
0x18000286a  mov     rax, [rbp+3Fh+mii.hbmpUnchecked]
0x18000286e  test    rax, rax
0x180002871  jz      short loc_1800028BB
0x180002873  lea     r9, [rbp+3Fh+var_B0]; unsigned int *
0x180002877  mov     r8d, eax; unsigned int
0x18000287a  mov     rdx, [rbp+3Fh+arg_28]; unsigned int *
0x18000287e  mov     ecx, [rbp+3Fh+arg_18]; unsigned int
0x180002881  call    ?FindFileMappingIndexForHBITMAP@@YA_NIPEBKKPEAI@Z
0x180002886  test    al, al
0x180002888  jz      short loc_1800028BB
0x18000288a  mov     edx, [rbp+3Fh+var_B0]
0x18000288d  mov     rdx, [r13+rdx*8+0]; hFileMappingObject
0x180002892  mov     rcx, rbx; hdc
0x180002895  call    ?RecreateSingleBitMap@@YAPEAUHBITMAP__@@PEAUHDC__@@PEAX@Z
0x18000289a  mov     [rbp+3Fh+mii.hbmpUnchecked], rax
0x18000289e  test    rax, rax
0x1800028a1  jz      short loc_1800028BB
0x1800028a3  mov     rdx, rax
0x1800028a6  lea     rcx, [rbp+3Fh+ho]
0x1800028aa  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHBITMAP__@@P6AHPEAX@Z$1?DeleteObject@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHBITMAP__@@@Z
0x1800028af  lea     rdx, [rbp+3Fh+ho]
0x1800028b3  mov     rcx, r12
0x1800028b6  call    ?push_back@?$vector@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHBITMAP__@@P6AHPEAX@Z$1?DeleteObject@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@V?$allocator@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHBITMAP__@@P6AHPEAX@Z$1?DeleteObject@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@std@@@std@@QEAAX$$QEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHBITMAP__@@P6AHPEAX@Z$1?DeleteObject@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@Z
0x1800028bb  lea     r9, [rbp+3Fh+mii]; lpmii
0x1800028bf  mov     r8d, 1; fByPositon
0x1800028c5  mov     edx, edi; item
0x1800028c7  mov     rcx, rsi; hmenu
0x1800028ca  call    cs:__imp_SetMenuItemInfoA
0x1800028d0  mov     rcx, [rbp+47h]; this
0x1800028d4  test    eax, eax
0x1800028d6  jz      short loc_180002917
0x1800028d8  mov     rcx, [rbp+3Fh+ho]; ho
0x1800028dc  test    rcx, rcx
0x1800028df  jz      short loc_1800028E7
0x1800028e1  call    cs:__imp_DeleteObject
0x1800028e7  inc     edi
0x1800028e9  mov     rcx, rsi; hMenu
0x1800028ec  call    cs:__imp_GetMenuItemCount
0x1800028f2  cmp     edi, eax
0x1800028f4  jl      loc_180002720
0x1800028fa  mov     rcx, rbx
0x1800028fd  add     rsp, 0B8h
0x180002904  pop     r15
0x180002906  pop     r14
0x180002908  pop     r13
0x18000290a  pop     r12
0x18000290c  pop     rdi
0x18000290d  pop     rsi
0x18000290e  pop     rbx
0x18000290f  pop     rbp
0x180002910  jmp     cs:__imp_DeleteDC
0x180002917  mov     edx, 0AAh; void *
0x18000291c  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z
0x180002922  mov     edx, 79h ; 'y'; void *
0x180002927  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z
0x18000292d  mov     edx, 70h ; 'p'; void *
0x180002932  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z
0x180002938  mov     rcx, [rbp+47h]; this
0x18000293c  mov     edx, 6Ch ; 'l'; void *
0x180002941  mov     r9d, 80004001h; char *
0x180002947  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z
```
