# ShellEasel::DoCommandSaveAs(void)

- ea: `0x18002df38`
- end: `0x18002e20f`
- name: `?DoCommandSaveAs@ShellEasel@@AEAAXXZ`
- size: `727`
- prototype: `void __fastcall(ShellEasel *__hidden this)`
- caller_count: `1`
- callee_count: `20`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180046df0`

## callees

- `0x1800041a4`
- `0x180004908`
- `0x180025f90`
- `0x180026724`
- `0x180029cfc`
- `0x18002d058`
- `0x18002df38`
- `0x18002e5a8`
- `0x18002e6bc`
- `0x18002ec48`
- `0x18002ecc8`
- `0x18002ed0c`
- `0x18002ef10`
- `0x18002f49c`
- `0x180039910`
- `0x180040264`
- `0x1800457f0`
- `0x18004a000`
- `0x18004b0d4`
- `0x180080010`

## import_xrefs

- `USER32!GetActiveWindow` at `0x18002df88`
- `USER32!GetActiveWindow` at `0x18002df88`
- `SHELL32!SHGetSpecialFolderPathW` at `0x18002e0b6`
- `SHELL32!SHGetSpecialFolderPathW` at `0x18002e0b6`
- `SHLWAPI!PathRemoveExtensionW` at `0x18002dfda`
- `SHLWAPI!PathRemoveExtensionW` at `0x18002dfda`
- `SHLWAPI!PathFindExtensionW` at `0x18002e02f`
- `SHLWAPI!PathFindExtensionW` at `0x18002e02f`
- `PhotoBase!?GetBaseStringManager@String@Base@@SAAEAVCAtlStringMgr@ATL@@XZ` at `0x18002df50`
- `PhotoBase!?GetBaseStringManager@String@Base@@SAAEAVCAtlStringMgr@ATL@@XZ` at `0x18002e076`
- `PhotoBase!?GetBaseStringManager@String@Base@@SAAEAVCAtlStringMgr@ATL@@XZ` at `0x18002e136`
- `PhotoBase!?GetBaseStringManager@String@Base@@SAAEAVCAtlStringMgr@ATL@@XZ` at `0x18002df50`
- `PhotoBase!?GetBaseStringManager@String@Base@@SAAEAVCAtlStringMgr@ATL@@XZ` at `0x18002e076`
- `PhotoBase!?GetBaseStringManager@String@Base@@SAAEAVCAtlStringMgr@ATL@@XZ` at `0x18002e136`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18002e18d`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18002e18d`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall ShellEasel::DoCommandSaveAs(ShellEasel *this)
{
  __int64 BaseStringManager; // rax
  struct Path *v3; // rax
  LPWSTR *v4; // rdi
  int v5; // edx
  __int64 v6; // r8
  unsigned __int16 *v7; // rax
  const unsigned __int16 *ExtensionW; // rax
  __int64 v9; // rax
  __int64 v10; // r8
  WCHAR *v11; // rdx
  __int64 v12; // r8
  LPWSTR v13; // rax
  __int64 v14; // rax
  __int64 v15; // rcx
  int v16; // eax
  int v17; // edx
  struct IWICBitmapEncoderInfo *v18; // rbx
  const unsigned __int16 **appended; // rax
  __int64 v20; // [rsp+20h] [rbp-A9h] BYREF
  _QWORD v21[3]; // [rsp+28h] [rbp-A1h] BYREF
  int v22; // [rsp+40h] [rbp-89h]
  int v23; // [rsp+50h] [rbp-79h] BYREF
  _BYTE v24[4]; // [rsp+54h] [rbp-75h] BYREF
  HWND ActiveWindow; // [rsp+58h] [rbp-71h]
  __int64 v26; // [rsp+68h] [rbp-61h]
  int FilterStringForSave; // [rsp+7Ch] [rbp-4Dh]
  unsigned __int16 *v28; // [rsp+80h] [rbp-49h]
  int v29; // [rsp+88h] [rbp-41h]
  LPWSTR v30; // [rsp+A0h] [rbp-29h]
  int v31; // [rsp+B0h] [rbp-19h]
  __int64 v32; // [rsp+B8h] [rbp-11h]
  LPWSTR v33; // [rsp+130h] [rbp+67h] BYREF
  unsigned __int16 *v34; // [rsp+138h] [rbp+6Fh] BYREF
  __int64 v35; // [rsp+140h] [rbp+77h] BYREF
  LPCWSTR pszPath; // [rsp+148h] [rbp+7Fh] BYREF

  BaseStringManager = Base::String::GetBaseStringManager();
  ATL::CSimpleStringT<unsigned short,0>::CSimpleStringT<unsigned short,0>(&pszPath, BaseStringManager);
  ShellEasel::GetCurrentSelection(this, (struct Path *)&pszPath);
  memset_0(v24, 0, 0x94u);
  v23 = 152;
  ActiveWindow = GetActiveWindow();
  Base::String::String((Base::String *)&v34, (const struct Base::String *)&pszPath);
  v3 = Base::Path::StripPath((Base::Path *)&v34);
  v4 = (LPWSTR *)v3;
  v5 = *(_DWORD *)(*(_QWORD *)v3 - 12LL) - 260;
  if ( (v5 | (1 - *(_DWORD *)(*(_QWORD *)v3 - 8LL))) < 0 )
    ATL::CSimpleStringT<unsigned short,0>::PrepareWrite2(
      v3,
      260,
      v5 | (unsigned int)(1 - *(_DWORD *)(*(_QWORD *)v3 - 8LL)));
  PathRemoveExtensionW(*v4);
  ATL::CSimpleStringT<unsigned short,0>::ReleaseBuffer(v4, 0xFFFFFFFFLL);
  Base::Path::AppendExtraNull((Base::Path *)v4);
  v7 = v34;
  if ( ((*((_DWORD *)v34 - 3) - 260) | (1 - *((_DWORD *)v34 - 2))) < 0 )
  {
    ATL::CSimpleStringT<unsigned short,0>::PrepareWrite2(&v34, 260, v6);
    v7 = v34;
  }
  v28 = v7;
  ATL::CSimpleStringT<unsigned short,0>::ReleaseBuffer(&v34, 0xFFFFFFFFLL);
  ExtensionW = PathFindExtensionW(pszPath);
  Base::Path::Path((Base::Path *)&v35, ExtensionW);
  Base::Path::AppendExtraNull((Base::Path *)&v35);
  v29 = 260 - *(_DWORD *)(v35 - 16);
  v32 = ATL::CSimpleStringT<unsigned short,0>::GetBuffer(&v35) + 2;
  ATL::CSimpleStringT<unsigned short,0>::ReleaseBuffer(&v35, 0xFFFFFFFFLL);
  v9 = Base::String::GetBaseStringManager();
  ATL::CSimpleStringT<unsigned short,0>::CSimpleStringT<unsigned short,0>(&v33, v9);
  v11 = v33;
  if ( ((*((_DWORD *)v33 - 3) - 260) | (1 - *((_DWORD *)v33 - 2))) < 0 )
  {
    ATL::CSimpleStringT<unsigned short,0>::PrepareWrite2(&v33, 260, v10);
    v11 = v33;
  }
  SHGetSpecialFolderPathW(0, v11, 39, 0);
  ATL::CSimpleStringT<unsigned short,0>::ReleaseBuffer(&v33, 0xFFFFFFFFLL);
  v13 = v33;
  if ( ((*((_DWORD *)v33 - 3) - 260) | (1 - *((_DWORD *)v33 - 2))) < 0 )
  {
    ATL::CSimpleStringT<unsigned short,0>::PrepareWrite2(&v33, 260, v12);
    v13 = v33;
  }
  v30 = v13;
  ATL::CSimpleStringT<unsigned short,0>::ReleaseBuffer(&v33, 0xFFFFFFFFLL);
  v29 = 260;
  v31 = 2050;
  memset(v21, 0, sizeof(v21));
  v22 = 0;
  CodecUtil::CodecEncDecHelper::GetImageEncoders((char *)this + 168, v21);
  PurgeEncodersThatDontHaveSaveAsTypeNames(v21);
  v14 = Base::String::GetBaseStringManager();
  ATL::CSimpleStringT<unsigned short,0>::CSimpleStringT<unsigned short,0>(&v20, v14);
  FilterStringForSave = ShellEasel::GetFilterStringForSave(v15, v21, v32, &v20);
  v26 = v20;
  if ( (unsigned int)IsolationAwareGetSaveFileNameW(&v23) )
  {
    v16 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 15) + 112LL))(*((_QWORD *)this + 15));
    if ( v16 < 0 )
    {
      Base::Throw((Base *)(unsigned int)v16, v17);
      __debugbreak();
    }
    v18 = *(struct IWICBitmapEncoderInfo **)ATL::CAtlArray<unsigned __int64,ATL::CElementTraits<unsigned __int64>>::operator[](
                                              v21,
                                              (unsigned int)(FilterStringForSave - 1));
    appended = (const unsigned __int16 **)Base::Path::AppendExtraNull((Base::Path *)&pszPath);
    ShellEasel::SaveTheFile((LPVOID *)this, *appended, v28, v18);
  }
  Base::String::~String((Base::String *)&v20);
  ATL::CAtlArray<ATL::CComQIPtr<IShellItem,&__s_GUID const _GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe>,ATL::CComQIPtrElementTraits<IShellItem,&__s_GUID const _GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe>>::~CAtlArray<ATL::CComQIPtr<IShellItem,&__s_GUID const _GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe>,ATL::CComQIPtrElementTraits<IShellItem,&__s_GUID const _GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe>>(v21);
  Base::String::~String((Base::String *)&v33);
  Base::String::~String((Base::String *)&v35);
  Base::String::~String((Base::String *)&v34);
  Base::String::~String((Base::String *)&pszPath);
}

```

## disassembly

```asm
0x18002df38  push    rbp
0x18002df3a  push    rbx
0x18002df3b  push    rsi
0x18002df3c  push    rdi
0x18002df3d  push    r14
0x18002df3f  push    r15
0x18002df41  lea     rbp, [rsp-2Fh]
0x18002df46  sub     rsp, 0F8h
0x18002df4d  mov     rsi, rcx
0x18002df50  call    cs:__imp_?GetBaseStringManager@String@Base@@SAAEAVCAtlStringMgr@ATL@@XZ; Base::String::GetBaseStringManager(void)
0x18002df56  nop
0x18002df57  mov     rdx, rax
0x18002df5a  lea     rcx, [rbp+57h+pszPath]
0x18002df5e  call    ??0?$CSimpleStringT@G$0A@@ATL@@QEAA@PEAUIAtlStringMgr@1@@Z; ATL::CSimpleStringT<ushort,0>::CSimpleStringT<ushort,0>(ATL::IAtlStringMgr *)
0x18002df63  nop
0x18002df64  lea     rdx, [rbp+57h+pszPath]; struct Path *
0x18002df68  mov     rcx, rsi; this
0x18002df6b  call    ?GetCurrentSelection@ShellEasel@@AEAAXPEAVPath@Base@@@Z; ShellEasel::GetCurrentSelection(Base::Path *)
0x18002df70  xor     edx, edx; Val
0x18002df72  mov     r8d, 94h; Size
0x18002df78  lea     rcx, [rbp+57h+var_CC]; void *
0x18002df7c  call    memset_0
0x18002df81  mov     [rbp+57h+var_D0], 98h
0x18002df88  call    cs:__imp_GetActiveWindow
0x18002df8e  mov     [rbp+57h+var_C8], rax
0x18002df92  lea     rdx, [rbp+57h+pszPath]; struct Base::String *
0x18002df96  lea     rcx, [rbp+57h+arg_8]; this
0x18002df9a  call    ??0String@Base@@QEAA@AEBV01@@Z; Base::String::String(Base::String const &)
0x18002df9f  nop
0x18002dfa0  lea     rcx, [rbp+57h+arg_8]; this
0x18002dfa4  call    ?StripPath@Path@Base@@QEAAAEAV12@XZ; Base::Path::StripPath(void)
0x18002dfa9  mov     rdi, rax
0x18002dfac  mov     rcx, [rax]
0x18002dfaf  mov     ebx, 1
0x18002dfb4  mov     r8d, ebx
0x18002dfb7  sub     r8d, [rcx-8]
0x18002dfbb  mov     edx, [rcx-0Ch]
0x18002dfbe  mov     r14d, 104h
0x18002dfc4  sub     edx, r14d
0x18002dfc7  or      r8d, edx
0x18002dfca  jge     short loc_18002DFD7
0x18002dfcc  mov     edx, r14d
0x18002dfcf  mov     rcx, rax
0x18002dfd2  call    ?PrepareWrite2@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::PrepareWrite2(int)
0x18002dfd7  mov     rcx, [rdi]; pszPath
0x18002dfda  call    cs:__imp_PathRemoveExtensionW
0x18002dfe0  or      r15d, 0FFFFFFFFh
0x18002dfe4  mov     edx, r15d
0x18002dfe7  mov     rcx, rdi
0x18002dfea  call    ?ReleaseBuffer@?$CSimpleStringT@G$0A@@ATL@@QEAAXH@Z; ATL::CSimpleStringT<ushort,0>::ReleaseBuffer(int)
0x18002dfef  mov     rcx, rdi; this
0x18002dff2  call    ?AppendExtraNull@Path@Base@@QEAAAEAV12@XZ; Base::Path::AppendExtraNull(void)
0x18002dff7  mov     rax, [rbp+57h+arg_8]
0x18002dffb  mov     edx, ebx
0x18002dffd  sub     edx, [rax-8]
0x18002e000  mov     ecx, [rax-0Ch]
0x18002e003  sub     ecx, r14d
0x18002e006  or      edx, ecx
0x18002e008  jge     short loc_18002E01A
0x18002e00a  mov     edx, r14d
0x18002e00d  lea     rcx, [rbp+57h+arg_8]
0x18002e011  call    ?PrepareWrite2@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::PrepareWrite2(int)
0x18002e016  mov     rax, [rbp+57h+arg_8]
0x18002e01a  mov     [rbp+57h+var_A0], rax
0x18002e01e  mov     edx, r15d
0x18002e021  lea     rcx, [rbp+57h+arg_8]
0x18002e025  call    ?ReleaseBuffer@?$CSimpleStringT@G$0A@@ATL@@QEAAXH@Z; ATL::CSimpleStringT<ushort,0>::ReleaseBuffer(int)
0x18002e02a  nop
0x18002e02b  mov     rcx, [rbp+57h+pszPath]; pszPath
0x18002e02f  call    cs:__imp_PathFindExtensionW
0x18002e035  mov     rdx, rax; unsigned __int16 *
0x18002e038  lea     rcx, [rbp+57h+arg_10]; this
0x18002e03c  call    ??0Path@Base@@QEAA@PEBG@Z; Base::Path::Path(ushort const *)
0x18002e041  nop
0x18002e042  lea     rcx, [rbp+57h+arg_10]; this
0x18002e046  call    ?AppendExtraNull@Path@Base@@QEAAAEAV12@XZ; Base::Path::AppendExtraNull(void)
0x18002e04b  mov     ecx, r14d
0x18002e04e  mov     rax, [rbp+57h+arg_10]
0x18002e052  sub     ecx, [rax-10h]
0x18002e055  mov     [rbp+57h+var_98], ecx
0x18002e058  lea     rcx, [rbp+57h+arg_10]
0x18002e05c  call    ?GetBuffer@?$CSimpleStringT@G$0A@@ATL@@QEAAPEAGXZ; ATL::CSimpleStringT<ushort,0>::GetBuffer(void)
0x18002e061  add     rax, 2
0x18002e065  mov     [rbp+57h+var_68], rax
0x18002e069  mov     edx, r15d
0x18002e06c  lea     rcx, [rbp+57h+arg_10]
0x18002e070  call    ?ReleaseBuffer@?$CSimpleStringT@G$0A@@ATL@@QEAAXH@Z; ATL::CSimpleStringT<ushort,0>::ReleaseBuffer(int)
0x18002e075  nop
0x18002e076  call    cs:__imp_?GetBaseStringManager@String@Base@@SAAEAVCAtlStringMgr@ATL@@XZ; Base::String::GetBaseStringManager(void)
0x18002e07c  nop
0x18002e07d  mov     rdx, rax
0x18002e080  lea     rcx, [rbp+57h+arg_0]
0x18002e084  call    ??0?$CSimpleStringT@G$0A@@ATL@@QEAA@PEAUIAtlStringMgr@1@@Z; ATL::CSimpleStringT<ushort,0>::CSimpleStringT<ushort,0>(ATL::IAtlStringMgr *)
0x18002e089  nop
0x18002e08a  mov     rdx, [rbp+57h+arg_0]
0x18002e08e  mov     ecx, ebx
0x18002e090  sub     ecx, [rdx-8]
0x18002e093  mov     eax, [rdx-0Ch]
0x18002e096  sub     eax, r14d
0x18002e099  or      ecx, eax
0x18002e09b  jge     short loc_18002E0AD
0x18002e09d  mov     edx, r14d
0x18002e0a0  lea     rcx, [rbp+57h+arg_0]
0x18002e0a4  call    ?PrepareWrite2@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::PrepareWrite2(int)
0x18002e0a9  mov     rdx, [rbp+57h+arg_0]; pszPath
0x18002e0ad  xor     r9d, r9d; fCreate
0x18002e0b0  xor     ecx, ecx; hwnd
0x18002e0b2  lea     r8d, [r9+27h]; csidl
0x18002e0b6  call    cs:__imp_SHGetSpecialFolderPathW
0x18002e0bc  mov     edx, r15d
0x18002e0bf  lea     rcx, [rbp+57h+arg_0]
0x18002e0c3  call    ?ReleaseBuffer@?$CSimpleStringT@G$0A@@ATL@@QEAAXH@Z; ATL::CSimpleStringT<ushort,0>::ReleaseBuffer(int)
0x18002e0c8  mov     rax, [rbp+57h+arg_0]
0x18002e0cc  sub     ebx, [rax-8]
0x18002e0cf  mov     ecx, [rax-0Ch]
0x18002e0d2  sub     ecx, r14d
0x18002e0d5  or      ebx, ecx
0x18002e0d7  jge     short loc_18002E0E9
0x18002e0d9  mov     edx, r14d
0x18002e0dc  lea     rcx, [rbp+57h+arg_0]
0x18002e0e0  call    ?PrepareWrite2@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::PrepareWrite2(int)
0x18002e0e5  mov     rax, [rbp+57h+arg_0]
0x18002e0e9  mov     [rbp+57h+var_80], rax
0x18002e0ed  mov     edx, r15d
0x18002e0f0  lea     rcx, [rbp+57h+arg_0]
0x18002e0f4  call    ?ReleaseBuffer@?$CSimpleStringT@G$0A@@ATL@@QEAAXH@Z; ATL::CSimpleStringT<ushort,0>::ReleaseBuffer(int)
0x18002e0f9  nop
0x18002e0fa  mov     [rbp+57h+var_98], r14d
0x18002e0fe  mov     [rbp+57h+var_70], 802h
0x18002e105  xor     ebx, ebx
0x18002e107  mov     [rsp+120h+var_F8], rbx
0x18002e10c  mov     [rsp+120h+var_F0], rbx
0x18002e111  mov     [rsp+120h+var_E8], rbx
0x18002e116  mov     [rsp+120h+var_E0], ebx
0x18002e11a  lea     rcx, [rsi+0A8h]
0x18002e121  lea     rdx, [rsp+120h+var_F8]
0x18002e126  call    ?GetImageEncoders@CodecEncDecHelper@CodecUtil@@QEAAXAEAV?$CInterfaceArray@UIWICBitmapEncoderInfo@@$1?_GUID_94c9b4ee_a09f_4f92_8a1e_4a9bce7e76fb@@3U__s_GUID@@B@ATL@@@Z; CodecUtil::CodecEncDecHelper::GetImageEncoders(ATL::CInterfaceArray<IWICBitmapEncoderInfo,&__s_GUID const _GUID_94c9b4ee_a09f_4f92_8a1e_4a9bce7e76fb> &)
0x18002e12b  lea     rcx, [rsp+120h+var_F8]
0x18002e130  call    PurgeEncodersThatDontHaveSaveAsTypeNames
0x18002e135  nop
0x18002e136  call    cs:__imp_?GetBaseStringManager@String@Base@@SAAEAVCAtlStringMgr@ATL@@XZ; Base::String::GetBaseStringManager(void)
0x18002e13c  nop
0x18002e13d  mov     rdx, rax
0x18002e140  lea     rcx, [rsp+120h+var_100]
0x18002e145  call    ??0?$CSimpleStringT@G$0A@@ATL@@QEAA@PEAUIAtlStringMgr@1@@Z; ATL::CSimpleStringT<ushort,0>::CSimpleStringT<ushort,0>(ATL::IAtlStringMgr *)
0x18002e14a  nop
0x18002e14b  lea     r9, [rsp+120h+var_100]
0x18002e150  mov     r8, [rbp+57h+var_68]
0x18002e154  lea     rdx, [rsp+120h+var_F8]
0x18002e159  call    ?GetFilterStringForSave@ShellEasel@@AEAAIAEAV?$CInterfaceArray@UIWICBitmapEncoderInfo@@$1?_GUID_94c9b4ee_a09f_4f92_8a1e_4a9bce7e76fb@@3U__s_GUID@@B@ATL@@PEBGAEAVString@Base@@@Z; ShellEasel::GetFilterStringForSave(ATL::CInterfaceArray<IWICBitmapEncoderInfo,&__s_GUID const _GUID_94c9b4ee_a09f_4f92_8a1e_4a9bce7e76fb> &,ushort const *,Base::String &)
0x18002e15e  mov     [rbp+57h+var_A4], eax
0x18002e161  mov     rax, [rsp+120h+var_100]
0x18002e166  mov     [rbp+57h+var_B8], rax
0x18002e16a  lea     rcx, [rbp+57h+var_D0]
0x18002e16e  call    IsolationAwareGetSaveFileNameW
0x18002e173  test    eax, eax
0x18002e175  jz      short loc_18002E1C2
0x18002e177  mov     rcx, [rsi+78h]
0x18002e17b  mov     rax, [rcx]
0x18002e17e  mov     rax, [rax+70h]
0x18002e182  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e187  test    eax, eax
0x18002e189  jns     short loc_18002E194
0x18002e18b  mov     ecx, eax
0x18002e18d  call    cs:__imp_?Throw@Base@@YAXJ@Z; Base::Throw(long)
0x18002e193  int     3; Trap to Debugger
0x18002e194  mov     edx, [rbp+57h+var_A4]
0x18002e197  dec     edx
0x18002e199  lea     rcx, [rsp+120h+var_F8]
0x18002e19e  call    ??A?$CAtlArray@_KV?$CElementTraits@_K@ATL@@@ATL@@QEAAAEA_K_K@Z; ATL::CAtlArray<unsigned __int64,ATL::CElementTraits<unsigned __int64>>::operator[](unsigned __int64)
0x18002e1a3  mov     rbx, [rax]
0x18002e1a6  lea     rcx, [rbp+57h+pszPath]; this
0x18002e1aa  call    ?AppendExtraNull@Path@Base@@QEAAAEAV12@XZ; Base::Path::AppendExtraNull(void)
0x18002e1af  mov     r9, rbx; struct IWICBitmapEncoderInfo *
0x18002e1b2  mov     r8, [rbp+57h+var_A0]; unsigned __int16 *
0x18002e1b6  mov     rdx, [rax]; unsigned __int16 *
0x18002e1b9  mov     rcx, rsi; this
0x18002e1bc  call    ?SaveTheFile@ShellEasel@@AEAAXPEBG0PEAUIWICBitmapEncoderInfo@@@Z; ShellEasel::SaveTheFile(ushort const *,ushort const *,IWICBitmapEncoderInfo *)
0x18002e1c1  nop
0x18002e1c2  lea     rcx, [rsp+120h+var_100]; this
0x18002e1c7  call    ??1String@Base@@QEAA@XZ; Base::String::~String(void)
0x18002e1cc  nop
0x18002e1cd  lea     rcx, [rsp+120h+var_F8]
0x18002e1d2  call    ??1?$CAtlArray@V?$CComQIPtr@UIShellItem@@$1?_GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe@@3U__s_GUID@@B@ATL@@V?$CComQIPtrElementTraits@UIShellItem@@$1?_GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe@@3U__s_GUID@@B@2@@ATL@@QEAA@XZ; ATL::CAtlArray<ATL::CComQIPtr<IShellItem,&__s_GUID const _GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe>,ATL::CComQIPtrElementTraits<IShellItem,&__s_GUID const _GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe>>::~CAtlArray<ATL::CComQIPtr<IShellItem,&__s_GUID const _GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe>,ATL::CComQIPtrElementTraits<IShellItem,&__s_GUID const _GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe>>(void)
0x18002e1d7  nop
0x18002e1d8  lea     rcx, [rbp+57h+arg_0]; this
0x18002e1dc  call    ??1String@Base@@QEAA@XZ; Base::String::~String(void)
0x18002e1e1  nop
0x18002e1e2  lea     rcx, [rbp+57h+arg_10]; this
0x18002e1e6  call    ??1String@Base@@QEAA@XZ; Base::String::~String(void)
0x18002e1eb  nop
0x18002e1ec  lea     rcx, [rbp+57h+arg_8]; this
0x18002e1f0  call    ??1String@Base@@QEAA@XZ; Base::String::~String(void)
0x18002e1f5  nop
0x18002e1f6  lea     rcx, [rbp+57h+pszPath]; this
0x18002e1fa  call    ??1String@Base@@QEAA@XZ; Base::String::~String(void)
0x18002e1ff  add     rsp, 0F8h
0x18002e206  pop     r15
0x18002e208  pop     r14
0x18002e20a  pop     rdi
0x18002e20b  pop     rsi
0x18002e20c  pop     rbx
0x18002e20d  pop     rbp
0x18002e20e  retn
```
