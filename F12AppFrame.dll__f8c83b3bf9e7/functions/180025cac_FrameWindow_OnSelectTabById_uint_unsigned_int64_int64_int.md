# FrameWindow::OnSelectTabById(uint,unsigned __int64,__int64,int &)

- ea: `0x180025cac`
- end: `0x180026113`
- name: `?OnSelectTabById@FrameWindow@@QEAA_JI_K_JAEAH@Z`
- size: `1127`
- prototype: `__int64 __fastcall(FrameWindow *__hidden this, unsigned int, unsigned __int64, __int64, int *)`
- caller_count: `4`
- callee_count: `16`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800257e0`
- `0x18002874c`
- `0x180028978`
- `0x18002b910`

## callees

- `0x18000193c`
- `0x1800031a4`
- `0x180003858`
- `0x180003880`
- `0x1800039ec`
- `0x18001e894`
- `0x180020528`
- `0x180021e24`
- `0x180022f44`
- `0x180025cac`
- `0x1800269a4`
- `0x180028d38`
- `0x1800299c8`
- `0x18002c6c4`
- `0x18002f988`
- `0x180035010`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x180025e99`
- `ADVAPI32!RegCloseKey` at `0x180025e99`
- `ADVAPI32!RegSetValueExW` at `0x180025e8b`
- `ADVAPI32!RegSetValueExW` at `0x180025e8b`
- `OLEAUT32!__imp_SysAllocString` at `0x180025f46`
- `OLEAUT32!__imp_SysAllocString` at `0x180025f46`
- `OLEAUT32!__imp_VariantClear` at `0x180025f34`
- `OLEAUT32!__imp_VariantClear` at `0x180025f9b`
- `OLEAUT32!__imp_VariantClear` at `0x180025ff5`
- `OLEAUT32!__imp_VariantClear` at `0x180025f34`
- `OLEAUT32!__imp_VariantClear` at `0x180025f9b`
- `OLEAUT32!__imp_VariantClear` at `0x180025ff5`
- `OLEAUT32!__imp_VariantCopy` at `0x180025f6f`
- `OLEAUT32!__imp_VariantCopy` at `0x180025fc9`
- `OLEAUT32!__imp_VariantCopy` at `0x180025f6f`
- `OLEAUT32!__imp_VariantCopy` at `0x180025fc9`

## string_xrefs

- `0x180025e7d`: `lastselectedpluginid`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall FrameWindow::OnSelectTabById(FrameWindow *this, __int64 a2, unsigned int a3, int a4)
{
  unsigned int v6; // r11d
  __int64 v7; // rdx
  int v8; // edi
  signed int v9; // edx
  int TabFromId; // eax
  int v12; // edi
  struct ATL::CRegKey *v13; // rdx
  HKEY v14; // rcx
  HKEY v15; // rdi
  bool v16; // zf
  __int64 v17; // rcx
  VARIANTARG *v18; // rdi
  HRESULT v19; // eax
  VARIANTARG *v20; // rdi
  HRESULT v21; // eax
  VARIANTARG **v22; // rax
  VARIANTARG *v23; // r8
  VARIANTARG *v24; // rdx
  VARIANTARG *v25; // rcx
  int *v26; // rdx
  VARIANTARG *pvargDest[2]; // [rsp+30h] [rbp-30h] BYREF
  VARIANTARG *v28; // [rsp+40h] [rbp-20h]
  VARIANTARG hKey; // [rsp+48h] [rbp-18h] BYREF
  int *Data; // [rsp+90h] [rbp+30h] BYREF
  unsigned int v31; // [rsp+98h] [rbp+38h] BYREF
  VARIANTARG **v32; // [rsp+A0h] [rbp+40h] BYREF
  VARIANTARG ***v33; // [rsp+A8h] [rbp+48h]

  v31 = a3;
  if ( a3 == *((_DWORD *)this + 138) )
    return 0;
  if ( !(unsigned __int8)FrameWindow::WasShowToolStartFired(this, a3) )
  {
    switch ( v6 )
    {
      case 1u:
        v7 = 931;
        goto LABEL_19;
      case 2u:
        v7 = 933;
        goto LABEL_19;
      case 3u:
        v7 = 935;
        goto LABEL_19;
      case 4u:
        v7 = 937;
        goto LABEL_19;
      case 5u:
        v7 = 941;
        goto LABEL_19;
      case 6u:
        v7 = 943;
        goto LABEL_19;
      case 8u:
        v7 = 939;
        goto LABEL_19;
      case 9u:
        v7 = 927;
LABEL_19:
        (*(void (__fastcall **)(_QWORD, __int64, _QWORD))(**((_QWORD **)this + 71) + 48LL))(
          *((_QWORD *)this + 71),
          v7,
          0);
        v6 = v31;
        break;
    }
  }
  v8 = 0;
  if ( !(unsigned __int8)FrameWindow::IsPluginLoaded(this, v6) )
  {
    TabFromId = FrameWindow::CreateTabFromId((__int64)this, v9);
    v8 = TabFromId;
    if ( TabFromId )
    {
      if ( TabFromId != -2147483622 )
        return -1;
    }
  }
  *(_BYTE *)(*(_QWORD *)std::map<enum PluginId,std::shared_ptr<BrowserToolThreadInfo>>::operator[](
                          (__int64 *)this + 56,
                          (int *)&v31)
           + 26LL) = 1;
  if ( !v8 && v31 != 8 )
  {
    (*(void (__fastcall **)(_QWORD, _QWORD, _QWORD))(**((_QWORD **)this + 89) + 56LL))(
      *((_QWORD *)this + 89),
      *((unsigned int *)this + 138),
      *((unsigned __int8 *)this + 432));
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 89) + 24LL))(*((_QWORD *)this + 89));
    (*(void (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD))(**((_QWORD **)this + 89) + 48LL))(
      *((_QWORD *)this + 89),
      *((unsigned int *)this + 138),
      *((unsigned __int8 *)this + 435),
      *((unsigned __int8 *)this + 441));
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 89) + 32LL))(*((_QWORD *)this + 89));
    v12 = v31;
    *((_DWORD *)this + 138) = v31;
    memset(&hKey, 0, sizeof(hKey));
    if ( F12::CreateOrOpenF12RegRoot((HKEY *)&hKey, v13) )
    {
      v14 = *(HKEY *)&hKey.vt;
      if ( *(_QWORD *)&hKey.vt )
        goto LABEL_31;
    }
    else
    {
      LODWORD(Data) = v12;
      v15 = *(HKEY *)&hKey.vt;
      RegSetValueExW(*(HKEY *)&hKey.vt, L"lastselectedpluginid", 0, 4u, (const BYTE *)&Data, 4u);
      if ( v15 )
      {
        v14 = v15;
LABEL_31:
        RegCloseKey(v14);
      }
    }
    if ( *((_QWORD *)this + 67) >= 0x14u )
    {
      v16 = (*((_QWORD *)this + 67))-- == 1;
      if ( v16 )
        *((_QWORD *)this + 66) = 0;
      else
        ++*((_QWORD *)this + 66);
    }
    if ( a4 )
    {
      v17 = *((_QWORD *)this + 67);
      while ( (unsigned __int64)--v17 > *((_QWORD *)this + 83) )
      {
        v16 = (*((_QWORD *)this + 67))-- == 1;
        if ( v16 )
          *((_QWORD *)this + 66) = 0;
      }
      std::deque<enum PluginId>::push_back((char *)this + 504, &v31);
      *((_QWORD *)this + 83) = *((_QWORD *)this + 67) - 1LL;
    }
    *(_OWORD *)pvargDest = 0;
    v28 = 0;
    hKey.vt = 0;
    VariantClear(&hKey);
    hKey.vt = 8;
    hKey.llVal = (LONGLONG)SysAllocString(L"tabSelected");
    if ( !hKey.llVal )
    {
      hKey.vt = 10;
      hKey.lVal = -2147024882;
      ATL::AtlThrowImpl(-2147024882);
    }
    v18 = pvargDest[1];
    if ( pvargDest[1] == v28 )
    {
      std::vector<ATL::CComVariant>::_Emplace_reallocate<ATL::CComVariant>(
        (const VARIANTARG **)pvargDest,
        pvargDest[1],
        &hKey);
    }
    else
    {
      pvargDest[1]->vt = 0;
      v19 = VariantCopy(v18, &hKey);
      if ( v19 < 0 )
      {
        v18->vt = 10;
        v18->lVal = v19;
        ATL::AtlThrowImpl(v19);
      }
      ++pvargDest[1];
    }
    VariantClear(&hKey);
    hKey.vt = 3;
    hKey.lVal = *((_DWORD *)this + 138);
    v20 = pvargDest[1];
    if ( pvargDest[1] == v28 )
    {
      std::vector<ATL::CComVariant>::_Emplace_reallocate<ATL::CComVariant>(
        (const VARIANTARG **)pvargDest,
        pvargDest[1],
        &hKey);
    }
    else
    {
      pvargDest[1]->vt = 0;
      v21 = VariantCopy(v20, &hKey);
      if ( v21 < 0 )
      {
        v20->vt = 10;
        v20->lVal = v21;
        ATL::AtlThrowImpl(v21);
      }
      ++pvargDest[1];
    }
    VariantClear(&hKey);
    v33 = &v32;
    v22 = (VARIANTARG **)operator new(0x18u);
    v23 = v28;
    v28 = 0;
    v24 = pvargDest[1];
    pvargDest[1] = 0;
    v25 = pvargDest[0];
    pvargDest[0] = 0;
    *v22 = v25;
    v22[1] = v24;
    v22[2] = v23;
    v32 = v22;
    Data = (int *)(((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24);
    if ( !ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CheckImplicitLoad(
            (wchar_t **)&Data,
            0) )
      ATL::CSimpleStringT<unsigned short,0>::Empty(&Data);
    FrameWindow::PostPluginMessage(this, 0, &Data, &v32);
    v26 = Data - 6;
    if ( _InterlockedExchangeAdd(Data - 2, 0xFFFFFFFF) <= 1 )
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v26 + 8LL))(*(_QWORD *)v26);
    if ( (unsigned __int8)FrameWindow::IsPluginLoaded(this, *((unsigned int *)this + 138)) )
      FrameWindow::ShowSelectedTool(this);
    std::vector<ATL::CComVariant>::~vector<ATL::CComVariant>((__int64)pvargDest);
  }
  return 0;
}

```

## disassembly

```asm
0x180025cac  mov     [rsp-28h+arg_8], edx
0x180025cb0  push    rbp
0x180025cb1  push    rbx
0x180025cb2  push    rsi
0x180025cb3  push    rdi
0x180025cb4  push    r15
0x180025cb6  mov     rbp, rsp
0x180025cb9  sub     rsp, 60h
0x180025cbd  mov     rsi, r9
0x180025cc0  mov     r11, r8
0x180025cc3  mov     rbx, rcx
0x180025cc6  mov     [rbp+arg_8], r11d
0x180025cca  cmp     r8d, [rcx+228h]
0x180025cd1  jz      loc_1800260D3
0x180025cd7  mov     edx, r11d
0x180025cda  call    ?WasShowToolStartFired@FrameWindow@@AEBA_NW4PluginId@@@Z; FrameWindow::WasShowToolStartFired(PluginId)
0x180025cdf  test    al, al
0x180025ce1  jnz     short loc_180025D5E
0x180025ce3  mov     ecx, r11d
0x180025ce6  sub     ecx, 1
0x180025ce9  jz      short loc_180025D3F
0x180025ceb  sub     ecx, 1
0x180025cee  jz      short loc_180025D38
0x180025cf0  sub     ecx, 1
0x180025cf3  jz      short loc_180025D31
0x180025cf5  sub     ecx, 1
0x180025cf8  jz      short loc_180025D2A
0x180025cfa  sub     ecx, 1
0x180025cfd  jz      short loc_180025D23
0x180025cff  sub     ecx, 1
0x180025d02  jz      short loc_180025D1C
0x180025d04  sub     ecx, 2
0x180025d07  jz      short loc_180025D15
0x180025d09  cmp     ecx, 1
0x180025d0c  jnz     short loc_180025D5E
0x180025d0e  mov     edx, 39Fh
0x180025d13  jmp     short loc_180025D44
0x180025d15  mov     edx, 3ABh
0x180025d1a  jmp     short loc_180025D44
0x180025d1c  mov     edx, 3AFh
0x180025d21  jmp     short loc_180025D44
0x180025d23  mov     edx, 3ADh
0x180025d28  jmp     short loc_180025D44
0x180025d2a  mov     edx, 3A9h
0x180025d2f  jmp     short loc_180025D44
0x180025d31  mov     edx, 3A7h
0x180025d36  jmp     short loc_180025D44
0x180025d38  mov     edx, 3A5h
0x180025d3d  jmp     short loc_180025D44
0x180025d3f  mov     edx, 3A3h
0x180025d44  mov     rcx, [rbx+238h]
0x180025d4b  mov     rax, [rcx]
0x180025d4e  xor     r8d, r8d
0x180025d51  mov     rax, [rax+30h]
0x180025d55  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025d5a  mov     r11d, [rbp+arg_8]
0x180025d5e  xor     edi, edi
0x180025d60  mov     edx, r11d
0x180025d63  mov     rcx, rbx
0x180025d66  call    ?IsPluginLoaded@FrameWindow@@AEBA_NW4PluginId@@@Z; FrameWindow::IsPluginLoaded(PluginId)
0x180025d6b  test    al, al
0x180025d6d  jnz     short loc_180025D8D
0x180025d6f  mov     rcx, rbx
0x180025d72  call    ?CreateTabFromId@FrameWindow@@AEAAJW4PluginId@@@Z; FrameWindow::CreateTabFromId(PluginId)
0x180025d77  mov     edi, eax
0x180025d79  test    eax, eax
0x180025d7b  jz      short loc_180025D8D
0x180025d7d  cmp     eax, 8000001Ah
0x180025d82  jz      short loc_180025D8D
0x180025d84  or      rax, 0FFFFFFFFFFFFFFFFh
0x180025d88  jmp     loc_1800260D5
0x180025d8d  lea     rcx, [rbx+1C0h]
0x180025d94  lea     rdx, [rbp+arg_8]
0x180025d98  call    ??A?$map@W4PluginId@@V?$shared_ptr@UBrowserToolThreadInfo@@@std@@U?$less@W4PluginId@@@3@V?$allocator@U?$pair@$$CBW4PluginId@@V?$shared_ptr@UBrowserToolThreadInfo@@@std@@@std@@@3@@std@@QEAAAEAV?$shared_ptr@UBrowserToolThreadInfo@@@1@AEBW4PluginId@@@Z; std::map<PluginId,std::shared_ptr<BrowserToolThreadInfo>>::operator[](PluginId const &)
0x180025d9d  mov     rcx, [rax]
0x180025da0  mov     byte ptr [rcx+1Ah], 1
0x180025da4  test    edi, edi
0x180025da6  jnz     loc_1800260D3
0x180025dac  lea     r15d, [rdi+8]
0x180025db0  cmp     [rbp+arg_8], r15d
0x180025db4  jz      loc_1800260D3
0x180025dba  mov     rcx, [rbx+2C8h]
0x180025dc1  mov     rax, [rcx]
0x180025dc4  movzx   r8d, byte ptr [rbx+1B0h]
0x180025dcc  mov     edx, [rbx+228h]
0x180025dd2  mov     rax, [rax+38h]
0x180025dd6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025ddb  mov     rcx, [rbx+2C8h]
0x180025de2  mov     rax, [rcx]
0x180025de5  mov     rax, [rax+18h]
0x180025de9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025dee  mov     rcx, [rbx+2C8h]
0x180025df5  mov     rax, [rcx]
0x180025df8  movzx   r9d, byte ptr [rbx+1B9h]
0x180025e00  movzx   r8d, byte ptr [rbx+1B3h]
0x180025e08  mov     edx, [rbx+228h]
0x180025e0e  mov     rax, [rax+30h]
0x180025e12  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025e17  mov     rcx, [rbx+2C8h]
0x180025e1e  mov     rax, [rcx]
0x180025e21  mov     rax, [rax+20h]
0x180025e25  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025e2a  mov     edi, [rbp+arg_8]
0x180025e2d  mov     [rbx+228h], edi
0x180025e33  mov     [rbp+hKey], 0
0x180025e3b  mov     [rbp+var_10], 0
0x180025e43  mov     [rbp+var_8], 0
0x180025e4b  lea     rcx, [rbp+hKey]; this
0x180025e4f  call    ?CreateOrOpenF12RegRoot@F12@@YAJAEAVCRegKey@ATL@@@Z; F12::CreateOrOpenF12RegRoot(ATL::CRegKey &)
0x180025e54  test    eax, eax
0x180025e56  jz      short loc_180025E63
0x180025e58  mov     rcx, [rbp+hKey]
0x180025e5c  test    rcx, rcx
0x180025e5f  jz      short loc_180025E9F
0x180025e61  jmp     short loc_180025E99
0x180025e63  mov     dword ptr [rbp+Data], edi
0x180025e66  mov     r9d, 4; dwType
0x180025e6c  mov     [rsp+60h+cbData], r9d; cbData
0x180025e71  lea     rax, [rbp+Data]
0x180025e75  mov     [rsp+60h+lpData], rax; lpData
0x180025e7a  xor     r8d, r8d; Reserved
0x180025e7d  lea     rdx, aLastselectedpl; "lastselectedpluginid"
0x180025e84  mov     rdi, [rbp+hKey]
0x180025e88  mov     rcx, rdi; hKey
0x180025e8b  call    cs:__imp_RegSetValueExW
0x180025e91  test    rdi, rdi
0x180025e94  jz      short loc_180025E9F
0x180025e96  mov     rcx, rdi; hKey
0x180025e99  call    cs:__imp_RegCloseKey
0x180025e9f  cmp     qword ptr [rbx+218h], 14h
0x180025ea7  jb      short loc_180025EC7
0x180025ea9  sub     qword ptr [rbx+218h], 1
0x180025eb1  jnz     short loc_180025EC0
0x180025eb3  mov     qword ptr [rbx+210h], 0
0x180025ebe  jmp     short loc_180025EC7
0x180025ec0  inc     qword ptr [rbx+210h]
0x180025ec7  test    esi, esi
0x180025ec9  jz      short loc_180025F1A
0x180025ecb  mov     rcx, [rbx+218h]
0x180025ed2  dec     rcx
0x180025ed5  cmp     rcx, [rbx+298h]
0x180025edc  jbe     short loc_180025EF5
0x180025ede  sub     qword ptr [rbx+218h], 1
0x180025ee6  jnz     short loc_180025ED2
0x180025ee8  mov     qword ptr [rbx+210h], 0
0x180025ef3  jmp     short loc_180025ED2
0x180025ef5  mov     eax, 1F8h
0x180025efa  mov     rcx, rbx
0x180025efd  add     rcx, rax
0x180025f00  lea     rdx, [rbp+arg_8]
0x180025f04  call    ?push_back@?$deque@W4PluginId@@V?$allocator@W4PluginId@@@std@@@std@@QEAAXAEBW4PluginId@@@Z; std::deque<PluginId>::push_back(PluginId const &)
0x180025f09  mov     rax, [rbx+218h]
0x180025f10  dec     rax
0x180025f13  mov     [rbx+298h], rax
0x180025f1a  xorps   xmm0, xmm0
0x180025f1d  movdqu  xmmword ptr [rbp+pvargDest], xmm0
0x180025f22  mov     [rbp+var_20], 0
0x180025f2a  xor     eax, eax
0x180025f2c  mov     word ptr [rbp+hKey], ax
0x180025f30  lea     rcx, [rbp+hKey]; pvarg
0x180025f34  call    cs:__imp_VariantClear
0x180025f3a  mov     word ptr [rbp+hKey], r15w
0x180025f3f  lea     rcx, aTabselected; "tabSelected"
0x180025f46  call    cs:__imp_SysAllocString
0x180025f4c  mov     [rbp+var_10], rax
0x180025f50  test    rax, rax
0x180025f53  jz      loc_1800260EE
0x180025f59  mov     rdi, [rbp+pvargDest+8]
0x180025f5d  cmp     rdi, [rbp+var_20]
0x180025f61  jz      short loc_180025F86
0x180025f63  xor     eax, eax
0x180025f65  mov     [rdi], ax
0x180025f68  lea     rdx, [rbp+hKey]; pvargSrc
0x180025f6c  mov     rcx, rdi; pvargDest
0x180025f6f  call    cs:__imp_VariantCopy
0x180025f75  mov     ecx, eax; int
0x180025f77  test    eax, eax
0x180025f79  js      loc_180026105
0x180025f7f  add     [rbp+pvargDest+8], 18h
0x180025f84  jmp     short loc_180025F97
0x180025f86  lea     r8, [rbp+hKey]
0x180025f8a  mov     rdx, rdi
0x180025f8d  lea     rcx, [rbp+pvargDest]
0x180025f91  call    ??$_Emplace_reallocate@VCComVariant@ATL@@@?$vector@VCComVariant@ATL@@V?$allocator@VCComVariant@ATL@@@std@@@std@@AEAAPEAVCComVariant@ATL@@QEAV23@$$QEAV23@@Z; std::vector<ATL::CComVariant>::_Emplace_reallocate<ATL::CComVariant>(ATL::CComVariant * const,ATL::CComVariant &&)
0x180025f96  nop
0x180025f97  lea     rcx, [rbp+hKey]; pvarg
0x180025f9b  call    cs:__imp_VariantClear
0x180025fa1  mov     eax, 3
0x180025fa6  mov     word ptr [rbp+hKey], ax
0x180025faa  mov     eax, [rbx+228h]
0x180025fb0  mov     dword ptr [rbp+var_10], eax
0x180025fb3  mov     rdi, [rbp+pvargDest+8]
0x180025fb7  cmp     rdi, [rbp+var_20]
0x180025fbb  jz      short loc_180025FE0
0x180025fbd  xor     eax, eax
0x180025fbf  mov     [rdi], ax
0x180025fc2  lea     rdx, [rbp+hKey]; pvargSrc
0x180025fc6  mov     rcx, rdi; pvargDest
0x180025fc9  call    cs:__imp_VariantCopy
0x180025fcf  mov     ecx, eax; int
0x180025fd1  test    eax, eax
0x180025fd3  js      loc_1800260E0
0x180025fd9  add     [rbp+pvargDest+8], 18h
0x180025fde  jmp     short loc_180025FF1
0x180025fe0  lea     r8, [rbp+hKey]
0x180025fe4  mov     rdx, rdi
0x180025fe7  lea     rcx, [rbp+pvargDest]
0x180025feb  call    ??$_Emplace_reallocate@VCComVariant@ATL@@@?$vector@VCComVariant@ATL@@V?$allocator@VCComVariant@ATL@@@std@@@std@@AEAAPEAVCComVariant@ATL@@QEAV23@$$QEAV23@@Z; std::vector<ATL::CComVariant>::_Emplace_reallocate<ATL::CComVariant>(ATL::CComVariant * const,ATL::CComVariant &&)
0x180025ff0  nop
0x180025ff1  lea     rcx, [rbp+hKey]; pvarg
0x180025ff5  call    cs:__imp_VariantClear
0x180025ffb  lea     rax, [rbp+arg_10]
0x180025fff  mov     [rbp+arg_18], rax
0x180026003  mov     ecx, 18h; Size
0x180026008  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002600d  mov     r8, [rbp+var_20]
0x180026011  mov     [rbp+var_20], 0
0x180026019  mov     rdx, [rbp+pvargDest+8]
0x18002601d  mov     [rbp+pvargDest+8], 0
0x180026025  mov     rcx, [rbp+pvargDest]
0x180026029  mov     [rbp+pvargDest], 0
0x180026031  mov     [rax], rcx
0x180026034  mov     [rax+8], rdx
0x180026038  mov     [rax+10h], r8
0x18002603c  mov     [rbp+arg_10], rax
0x180026040  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x180026047  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x18002604e  mov     rax, [rax+18h]
0x180026052  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026057  add     rax, 18h
0x18002605b  mov     [rbp+Data], rax
0x18002605f  xor     edx, edx
0x180026061  lea     rcx, [rbp+Data]
0x180026065  call    ?CheckImplicitLoad@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@AEAA_NPEBX@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CheckImplicitLoad(void const *)
0x18002606a  test    al, al
0x18002606c  jnz     short loc_180026078
0x18002606e  lea     rcx, [rbp+Data]
0x180026072  call    ?Empty@?$CSimpleStringT@G$0A@@ATL@@QEAAXXZ; ATL::CSimpleStringT<ushort,0>::Empty(void)
0x180026077  nop
0x180026078  lea     r9, [rbp+arg_10]
0x18002607c  lea     r8, [rbp+Data]
0x180026080  xor     edx, edx
0x180026082  mov     rcx, rbx
0x180026085  call    ?PostPluginMessage@FrameWindow@@AEAAXW4PluginId@@AEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$unique_ptr@V?$vector@VCComVariant@ATL@@V?$allocator@VCComVariant@ATL@@@std@@@std@@U?$default_delete@V?$vector@VCComVariant@ATL@@V?$allocator@VCComVariant@ATL@@@std@@@std@@@2@@std@@@Z; FrameWindow::PostPluginMessage(PluginId,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,std::unique_ptr<std::vector<ATL::CComVariant>>)
0x18002608a  nop
0x18002608b  mov     rdx, [rbp+Data]
0x18002608f  add     rdx, 0FFFFFFFFFFFFFFE8h
0x180026093  or      eax, 0FFFFFFFFh
0x180026096  lock xadd [rdx+10h], eax
0x18002609b  sub     eax, 1
0x18002609e  jg      short loc_1800260AF
0x1800260a0  mov     rcx, [rdx]
0x1800260a3  mov     rax, [rcx]
0x1800260a6  mov     rax, [rax+8]
0x1800260aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800260af  mov     edx, [rbx+228h]
0x1800260b5  mov     rcx, rbx
0x1800260b8  call    ?IsPluginLoaded@FrameWindow@@AEBA_NW4PluginId@@@Z; FrameWindow::IsPluginLoaded(PluginId)
0x1800260bd  test    al, al
0x1800260bf  jz      short loc_1800260CA
0x1800260c1  mov     rcx, rbx; this
0x1800260c4  call    ?ShowSelectedTool@FrameWindow@@AEAAJXZ; FrameWindow::ShowSelectedTool(void)
0x1800260c9  nop
0x1800260ca  lea     rcx, [rbp+pvargDest]
0x1800260ce  call    ??1?$vector@VCComVariant@ATL@@V?$allocator@VCComVariant@ATL@@@std@@@std@@QEAA@XZ; std::vector<ATL::CComVariant>::~vector<ATL::CComVariant>(void)
0x1800260d3  xor     eax, eax
0x1800260d5  add     rsp, 60h
0x1800260d9  pop     r15
0x1800260db  pop     rdi
0x1800260dc  pop     rsi
0x1800260dd  pop     rbx
0x1800260de  pop     rbp
0x1800260df  retn
0x1800260e0  mov     word ptr [rdi], 0Ah
0x1800260e5  mov     [rdi+8], ecx
0x1800260e8  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x1800260ee  mov     eax, 0Ah
0x1800260f3  mov     word ptr [rbp+hKey], ax
0x1800260f7  mov     ecx, 8007000Eh; int
0x1800260fc  mov     dword ptr [rbp+var_10], ecx
0x1800260ff  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180026105  mov     word ptr [rdi], 0Ah
0x18002610a  mov     [rdi+8], ecx
0x18002610d  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
