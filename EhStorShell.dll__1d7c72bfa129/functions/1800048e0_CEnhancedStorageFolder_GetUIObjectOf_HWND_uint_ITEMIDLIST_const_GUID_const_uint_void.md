# CEnhancedStorageFolder::GetUIObjectOf(HWND__ *,uint,_ITEMIDLIST const * *,_GUID const &,uint *,void * *)

- ea: `0x1800048e0`
- end: `0x180004cbb`
- name: `?GetUIObjectOf@CEnhancedStorageFolder@@UEAAJPEAUHWND__@@IPEAPEFBU_ITEMIDLIST@@AEBU_GUID@@PEAIPEAPEAX@Z`
- size: `987`
- prototype: `__int64 __fastcall(CEnhancedStorageFolder *this, HWND, int, const struct _ITEMIDLIST **, const struct _GUID *, unsigned int *, void **)`
- caller_count: `0`
- callee_count: `10`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180003a98`
- `0x18000453c`
- `0x1800048e0`
- `0x180005ab8`
- `0x180005b2c`
- `0x180005c80`
- `0x1800064cc`
- `0x18000684c`
- `0x18000b630`
- `0x18000c010`

## import_xrefs

- `KERNEL32!GetModuleFileNameW` at `0x180004a07`
- `KERNEL32!GetModuleFileNameW` at `0x180004a07`
- `ole32!PropVariantClear` at `0x180004c88`
- `ole32!PropVariantClear` at `0x180004c88`
- `SHELL32!SHCreateDefaultExtractIcon` at `0x180004a64`
- `SHELL32!SHCreateDefaultExtractIcon` at `0x180004a64`
- `PROPSYS!PropVariantToString` at `0x180004bbb`
- `PROPSYS!PropVariantToString` at `0x180004bbb`

## pseudocode

```c
__int64 __fastcall CEnhancedStorageFolder::GetUIObjectOf(
        CEnhancedStorageFolder *this,
        HWND a2,
        int a3,
        const struct _ITEMIDLIST **a4,
        const struct _GUID *a5,
        unsigned int *a6,
        void **a7)
{
  PVOID *v9; // rcx
  __int64 v10; // rax
  __int64 v11; // rax
  HRESULT v12; // ebx
  __int64 IsValid; // rax
  __int64 v14; // r9
  _DWORD *v15; // rdi
  __int64 v16; // r9
  _QWORD *v17; // rcx
  __int64 v18; // rdx
  HRESULT PropertyFromIDList; // eax
  _QWORD *v20; // rcx
  __int64 v21; // rdx
  CContextMenuHandler *v22; // rdi
  __int64 v23; // r8
  __int64 v24; // r9
  int v25; // eax
  void *ppv; // [rsp+20h] [rbp-E0h] BYREF
  PROPVARIANT propvar; // [rsp+28h] [rbp-D8h] BYREF
  WCHAR Filename[264]; // [rsp+40h] [rbp-C0h] BYREF

  v9 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 49, &WPP_6cd5398725ca392462ef447cc6ada768_Traceguids, a4);
    v9 = (PVOID *)WPP_GLOBAL_Control;
  }
  v10 = *(_QWORD *)&a5->Data1 - *(_QWORD *)&GUID_000214e4_0000_0000_c000_000000000046.Data1;
  if ( *(_QWORD *)&a5->Data1 == *(_QWORD *)&GUID_000214e4_0000_0000_c000_000000000046.Data1 )
    v10 = *(_QWORD *)a5->Data4 - *(_QWORD *)GUID_000214e4_0000_0000_c000_000000000046.Data4;
  if ( !v10 )
  {
    if ( v9 != &WPP_GLOBAL_Control && (*((_BYTE *)v9 + 28) & 0x20) != 0 )
    {
      WPP_SF_(v9[2], 50, &WPP_6cd5398725ca392462ef447cc6ada768_Traceguids, a4);
      v9 = (PVOID *)WPP_GLOBAL_Control;
    }
    ppv = 0;
    memset(&propvar, 0, sizeof(propvar));
    if ( !a3 )
    {
      if ( v9 != &WPP_GLOBAL_Control && (*((_BYTE *)v9 + 28) & 2) != 0 )
        WPP_SF_d(v9[2], 51, &WPP_6cd5398725ca392462ef447cc6ada768_Traceguids, 0);
      v12 = -2147024809;
      goto LABEL_62;
    }
    PropertyFromIDList = CItemIDFactory<_ITEMID,1450709556>::GetPropertyFromIDList(*a4, &PKEY_ParsingName, &propvar);
    v12 = PropertyFromIDList;
    if ( PropertyFromIDList >= 0 )
    {
      PropertyFromIDList = PropVariantToString(&propvar, Filename, 0x105u);
      v12 = PropertyFromIDList;
      if ( PropertyFromIDList >= 0 )
      {
        PropertyFromIDList = ATL::CComObject<CContextMenuHandler>::CreateInstance(&ppv);
        v12 = PropertyFromIDList;
        if ( PropertyFromIDList >= 0 )
        {
          v22 = (CContextMenuHandler *)ppv;
          (*(void (__fastcall **)(void *))(*(_QWORD *)ppv + 8LL))(ppv);
          v25 = CContextMenuHandler::InitializeFromName(v22, Filename, v23, v24);
          v12 = v25;
          if ( v25 >= 0 )
          {
            (**(void (__fastcall ***)(CContextMenuHandler *, const struct _GUID *, void **))v22)(v22, a5, a7);
          }
          else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
          {
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              55,
              &WPP_6cd5398725ca392462ef447cc6ada768_Traceguids,
              (unsigned int)v25);
          }
          (*(void (__fastcall **)(CContextMenuHandler *))(*(_QWORD *)v22 + 16LL))(v22);
          goto LABEL_62;
        }
        v20 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        {
LABEL_62:
          PropVariantClear(&propvar);
          return (unsigned int)v12;
        }
        v21 = 54;
      }
      else
      {
        v20 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
          goto LABEL_62;
        v21 = 53;
      }
    }
    else
    {
      v20 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        goto LABEL_62;
      v21 = 52;
    }
    WPP_SF_d(v20[2], v21, &WPP_6cd5398725ca392462ef447cc6ada768_Traceguids, (unsigned int)PropertyFromIDList);
    goto LABEL_62;
  }
  v11 = *(_QWORD *)&a5->Data1 - *(_QWORD *)&GUID_000214fa_0000_0000_c000_000000000046.Data1;
  if ( *(_QWORD *)&a5->Data1 == *(_QWORD *)&GUID_000214fa_0000_0000_c000_000000000046.Data1 )
    v11 = *(_QWORD *)a5->Data4 - *(_QWORD *)GUID_000214fa_0000_0000_c000_000000000046.Data4;
  if ( v11 )
    return (unsigned int)-2147467262;
  if ( v9 != &WPP_GLOBAL_Control && (*((_BYTE *)v9 + 28) & 0x20) != 0 )
  {
    WPP_SF_(v9[2], 56, &WPP_6cd5398725ca392462ef447cc6ada768_Traceguids, a4);
    v9 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( !a3 )
  {
    if ( v9 != &WPP_GLOBAL_Control && (*((_BYTE *)v9 + 28) & 2) != 0 )
      WPP_SF_d(v9[2], 57, &WPP_6cd5398725ca392462ef447cc6ada768_Traceguids, 0);
    return (unsigned int)-2147024809;
  }
  GetModuleFileNameW(hModule, Filename, 0x104u);
  IsValid = CItemIDFactory<_ITEMID,1450709556>::_IsValid(*a4);
  v15 = (_DWORD *)((IsValid + 14) & -(__int64)(IsValid != 0));
  if ( v15 )
  {
    ppv = 0;
    v12 = SHCreateDefaultExtractIcon(&GUID_41ded17d_d6b3_4261_997d_88c60e4b1d58, &ppv);
    if ( v12 >= 0 )
    {
      v12 = (*(__int64 (__fastcall **)(void *, WCHAR *, _QWORD))(*(_QWORD *)ppv + 40LL))(
              ppv,
              Filename,
              (unsigned int)-*v15);
      if ( v12 >= 0 )
      {
        v12 = (**(__int64 (__fastcall ***)(void *, const struct _GUID *, void **))ppv)(ppv, a5, a7);
        goto LABEL_29;
      }
      v17 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        goto LABEL_29;
      v18 = 60;
    }
    else
    {
      v17 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        goto LABEL_29;
      v18 = 59;
    }
    WPP_SF_(v17[2], v18, &WPP_6cd5398725ca392462ef447cc6ada768_Traceguids, v16);
LABEL_29:
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&ppv);
    return (unsigned int)v12;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 58, &WPP_6cd5398725ca392462ef447cc6ada768_Traceguids, v14);
  return (unsigned int)-2147467259;
}

```

## disassembly

```asm
0x1800048e0  mov     [rsp-8+arg_0], rbx
0x1800048e5  mov     [rsp-8+arg_8], rsi
0x1800048ea  push    rbp
0x1800048eb  push    rdi
0x1800048ec  push    r12
0x1800048ee  push    r14
0x1800048f0  push    r15
0x1800048f2  lea     rbp, [rsp-160h]
0x1800048fa  sub     rsp, 260h
0x180004901  mov     rax, cs:__security_cookie
0x180004908  xor     rax, rsp
0x18000490b  mov     [rbp+180h+var_30], rax
0x180004912  mov     rsi, [rbp+180h+arg_20]
0x180004919  mov     rdi, r9
0x18000491c  mov     r14, [rbp+180h+arg_30]
0x180004923  mov     ebx, r8d
0x180004926  mov     rcx, cs:WPP_GLOBAL_Control
0x18000492d  lea     r15, WPP_GLOBAL_Control
0x180004934  lea     r12, WPP_6cd5398725ca392462ef447cc6ada768_Traceguids
0x18000493b  cmp     rcx, r15
0x18000493e  jz      short loc_18000495E
0x180004940  test    byte ptr [rcx+1Ch], 20h
0x180004944  jz      short loc_18000495E
0x180004946  mov     rcx, [rcx+10h]
0x18000494a  mov     edx, 31h ; '1'
0x18000494f  mov     r8, r12
0x180004952  call    WPP_SF_
0x180004957  mov     rcx, cs:WPP_GLOBAL_Control
0x18000495e  mov     rax, [rsi]
0x180004961  sub     rax, qword ptr cs:_GUID_000214e4_0000_0000_c000_000000000046.Data1
0x180004968  jnz     short loc_180004975
0x18000496a  mov     rax, [rsi+8]
0x18000496e  sub     rax, qword ptr cs:_GUID_000214e4_0000_0000_c000_000000000046.Data4
0x180004975  test    rax, rax
0x180004978  jz      loc_180004AF7
0x18000497e  mov     rax, [rsi]
0x180004981  sub     rax, qword ptr cs:_GUID_000214fa_0000_0000_c000_000000000046.Data1
0x180004988  jnz     short loc_180004995
0x18000498a  mov     rax, [rsi+8]
0x18000498e  sub     rax, qword ptr cs:_GUID_000214fa_0000_0000_c000_000000000046.Data4
0x180004995  test    rax, rax
0x180004998  jz      short loc_1800049A4
0x18000499a  mov     ebx, 80004002h
0x18000499f  jmp     loc_180004C8E
0x1800049a4  cmp     rcx, r15
0x1800049a7  jz      short loc_1800049C7
0x1800049a9  test    byte ptr [rcx+1Ch], 20h
0x1800049ad  jz      short loc_1800049C7
0x1800049af  mov     rcx, [rcx+10h]
0x1800049b3  mov     edx, 38h ; '8'
0x1800049b8  mov     r8, r12
0x1800049bb  call    WPP_SF_
0x1800049c0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800049c7  cmp     ebx, 1
0x1800049ca  jnb     short loc_1800049F5
0x1800049cc  cmp     rcx, r15
0x1800049cf  jz      short loc_1800049EB
0x1800049d1  test    byte ptr [rcx+1Ch], 2
0x1800049d5  jz      short loc_1800049EB
0x1800049d7  mov     rcx, [rcx+10h]
0x1800049db  mov     edx, 39h ; '9'
0x1800049e0  mov     r9d, ebx
0x1800049e3  mov     r8, r12
0x1800049e6  call    WPP_SF_d
0x1800049eb  mov     ebx, 80070057h
0x1800049f0  jmp     loc_180004C8E
0x1800049f5  mov     rcx, cs:hModule; hModule
0x1800049fc  lea     rdx, [rsp+280h+Filename]; lpFilename
0x180004a01  mov     r8d, 104h; nSize
0x180004a07  call    cs:__imp_GetModuleFileNameW
0x180004a0d  mov     rcx, [rdi]
0x180004a10  call    ?_IsValid@?$CItemIDFactory@U_ITEMID@@$0FGHIBCDE@@@CAPEFBUCHILDITEMID@1@PEFBU_ITEMIDLIST@@@Z; CItemIDFactory<_ITEMID,1450709556>::_IsValid(_ITEMIDLIST const *)
0x180004a15  lea     rcx, [rax+0Eh]
0x180004a19  neg     rax
0x180004a1c  sbb     rdi, rdi
0x180004a1f  and     rdi, rcx
0x180004a22  jnz     short loc_180004A4F
0x180004a24  mov     rcx, cs:WPP_GLOBAL_Control
0x180004a2b  cmp     rcx, r15
0x180004a2e  jz      short loc_180004A45
0x180004a30  test    byte ptr [rcx+1Ch], 2
0x180004a34  jz      short loc_180004A45
0x180004a36  mov     rcx, [rcx+10h]
0x180004a3a  lea     edx, [rdi+3Ah]
0x180004a3d  mov     r8, r12
0x180004a40  call    WPP_SF_
0x180004a45  mov     ebx, 80004005h
0x180004a4a  jmp     loc_180004C8E
0x180004a4f  lea     rdx, [rsp+280h+ppv]; ppv
0x180004a54  mov     [rsp+280h+ppv], 0
0x180004a5d  lea     rcx, _GUID_41ded17d_d6b3_4261_997d_88c60e4b1d58; riid
0x180004a64  call    cs:__imp_SHCreateDefaultExtractIcon
0x180004a6a  mov     ebx, eax
0x180004a6c  test    eax, eax
0x180004a6e  jns     short loc_180004AA2
0x180004a70  mov     rcx, cs:WPP_GLOBAL_Control
0x180004a77  cmp     rcx, r15
0x180004a7a  jz      short loc_180004A93
0x180004a7c  test    byte ptr [rcx+1Ch], 2
0x180004a80  jz      short loc_180004A93
0x180004a82  mov     edx, 3Bh ; ';'
0x180004a87  mov     rcx, [rcx+10h]
0x180004a8b  mov     r8, r12
0x180004a8e  call    WPP_SF_
0x180004a93  lea     rcx, [rsp+280h+ppv]
0x180004a98  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180004a9d  jmp     loc_180004C8E
0x180004aa2  mov     rcx, [rsp+280h+ppv]
0x180004aa7  lea     rdx, [rsp+280h+Filename]
0x180004aac  mov     r8d, [rdi]
0x180004aaf  neg     r8d
0x180004ab2  mov     rax, [rcx]
0x180004ab5  mov     rax, [rax+28h]
0x180004ab9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004abe  mov     ebx, eax
0x180004ac0  test    eax, eax
0x180004ac2  jns     short loc_180004ADD
0x180004ac4  mov     rcx, cs:WPP_GLOBAL_Control
0x180004acb  cmp     rcx, r15
0x180004ace  jz      short loc_180004A93
0x180004ad0  test    byte ptr [rcx+1Ch], 2
0x180004ad4  jz      short loc_180004A93
0x180004ad6  mov     edx, 3Ch ; '<'
0x180004adb  jmp     short loc_180004A87
0x180004add  mov     rcx, [rsp+280h+ppv]
0x180004ae2  mov     r8, r14
0x180004ae5  mov     rdx, rsi
0x180004ae8  mov     rax, [rcx]
0x180004aeb  mov     rax, [rax]
0x180004aee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004af3  mov     ebx, eax
0x180004af5  jmp     short loc_180004A93
0x180004af7  cmp     rcx, r15
0x180004afa  jz      short loc_180004B1A
0x180004afc  test    byte ptr [rcx+1Ch], 20h
0x180004b00  jz      short loc_180004B1A
0x180004b02  mov     rcx, [rcx+10h]
0x180004b06  mov     edx, 32h ; '2'
0x180004b0b  mov     r8, r12
0x180004b0e  call    WPP_SF_
0x180004b13  mov     rcx, cs:WPP_GLOBAL_Control
0x180004b1a  xor     eax, eax
0x180004b1c  mov     [rsp+280h+ppv], 0
0x180004b25  mov     qword ptr [rsp+280h+propvar+10h], rax
0x180004b2a  xorps   xmm0, xmm0
0x180004b2d  movups  xmmword ptr [rsp+280h+propvar], xmm0
0x180004b32  cmp     ebx, 1
0x180004b35  jnb     short loc_180004B5E
0x180004b37  cmp     rcx, r15
0x180004b3a  jz      short loc_180004B54
0x180004b3c  test    byte ptr [rcx+1Ch], 2
0x180004b40  jz      short loc_180004B54
0x180004b42  mov     rcx, [rcx+10h]
0x180004b46  lea     edx, [rax+33h]
0x180004b49  mov     r9d, ebx
0x180004b4c  mov     r8, r12
0x180004b4f  call    WPP_SF_d
0x180004b54  mov     ebx, 80070057h
0x180004b59  jmp     loc_180004C83
0x180004b5e  mov     rcx, [rdi]
0x180004b61  lea     r8, [rsp+280h+propvar]
0x180004b66  lea     rdx, PKEY_ParsingName
0x180004b6d  call    ?GetPropertyFromIDList@?$CItemIDFactory@U_ITEMID@@$0FGHIBCDE@@@SAJPEFBU_ITEMIDLIST@@AEBU_tagpropertykey@@PEAUtagPROPVARIANT@@@Z; CItemIDFactory<_ITEMID,1450709556>::GetPropertyFromIDList(_ITEMIDLIST const *,_tagpropertykey const &,tagPROPVARIANT *)
0x180004b72  mov     ebx, eax
0x180004b74  test    eax, eax
0x180004b76  jns     short loc_180004BAB
0x180004b78  mov     rcx, cs:WPP_GLOBAL_Control
0x180004b7f  cmp     rcx, r15
0x180004b82  jz      loc_180004C83
0x180004b88  test    byte ptr [rcx+1Ch], 2
0x180004b8c  jz      loc_180004C83
0x180004b92  mov     edx, 34h ; '4'
0x180004b97  mov     rcx, [rcx+10h]
0x180004b9b  mov     r9d, eax
0x180004b9e  mov     r8, r12
0x180004ba1  call    WPP_SF_d
0x180004ba6  jmp     loc_180004C83
0x180004bab  mov     r8d, 105h; cch
0x180004bb1  lea     rdx, [rsp+280h+Filename]; psz
0x180004bb6  lea     rcx, [rsp+280h+propvar]; propvar
0x180004bbb  call    cs:__imp_PropVariantToString
0x180004bc1  mov     ebx, eax
0x180004bc3  test    eax, eax
0x180004bc5  jns     short loc_180004BE8
0x180004bc7  mov     rcx, cs:WPP_GLOBAL_Control
0x180004bce  cmp     rcx, r15
0x180004bd1  jz      loc_180004C83
0x180004bd7  test    byte ptr [rcx+1Ch], 2
0x180004bdb  jz      loc_180004C83
0x180004be1  mov     edx, 35h ; '5'
0x180004be6  jmp     short loc_180004B97
0x180004be8  lea     rcx, [rsp+280h+ppv]
0x180004bed  call    ?CreateInstance@?$CComObject@VCContextMenuHandler@@@ATL@@SAJPEAPEAV12@@Z; ATL::CComObject<CContextMenuHandler>::CreateInstance(ATL::CComObject<CContextMenuHandler> * *)
0x180004bf2  mov     ebx, eax
0x180004bf4  test    eax, eax
0x180004bf6  jns     short loc_180004C11
0x180004bf8  mov     rcx, cs:WPP_GLOBAL_Control
0x180004bff  cmp     rcx, r15
0x180004c02  jz      short loc_180004C83
0x180004c04  test    byte ptr [rcx+1Ch], 2
0x180004c08  jz      short loc_180004C83
0x180004c0a  mov     edx, 36h ; '6'
0x180004c0f  jmp     short loc_180004B97
0x180004c11  mov     rdi, [rsp+280h+ppv]
0x180004c16  mov     rcx, rdi
0x180004c19  mov     rax, [rdi]
0x180004c1c  mov     rax, [rax+8]
0x180004c20  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004c25  lea     rdx, [rsp+280h+Filename]; unsigned __int16 *
0x180004c2a  mov     rcx, rdi; this
0x180004c2d  call    ?InitializeFromName@CContextMenuHandler@@QEAAJPEBG@Z; CContextMenuHandler::InitializeFromName(ushort const *)
0x180004c32  mov     ebx, eax
0x180004c34  test    eax, eax
0x180004c36  jns     short loc_180004C60
0x180004c38  mov     rcx, cs:WPP_GLOBAL_Control
0x180004c3f  cmp     rcx, r15
0x180004c42  jz      short loc_180004C74
0x180004c44  test    byte ptr [rcx+1Ch], 2
0x180004c48  jz      short loc_180004C74
0x180004c4a  mov     rcx, [rcx+10h]
0x180004c4e  mov     edx, 37h ; '7'
0x180004c53  mov     r9d, eax
0x180004c56  mov     r8, r12
0x180004c59  call    WPP_SF_d
0x180004c5e  jmp     short loc_180004C74
0x180004c60  mov     rax, [rdi]
0x180004c63  mov     r8, r14
0x180004c66  mov     rdx, rsi
0x180004c69  mov     rcx, rdi
0x180004c6c  mov     rax, [rax]
0x180004c6f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004c74  mov     rax, [rdi]
0x180004c77  mov     rcx, rdi
0x180004c7a  mov     rax, [rax+10h]
0x180004c7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004c83  lea     rcx, [rsp+280h+propvar]; pvar
0x180004c88  call    cs:__imp_PropVariantClear
0x180004c8e  mov     eax, ebx
0x180004c90  mov     rcx, [rbp+180h+var_30]
0x180004c97  xor     rcx, rsp; StackCookie
0x180004c9a  call    __security_check_cookie
0x180004c9f  lea     r11, [rsp+280h+var_20]
0x180004ca7  mov     rbx, [r11+30h]
0x180004cab  mov     rsi, [r11+38h]
0x180004caf  mov     rsp, r11
0x180004cb2  pop     r15
0x180004cb4  pop     r14
0x180004cb6  pop     r12
0x180004cb8  pop     rdi
0x180004cb9  pop     rbp
0x180004cba  retn
```
