# ShellEaselDropTarget::RotateImages(void)

- ea: `0x1800496ec`
- end: `0x180049c54`
- name: `?RotateImages@ShellEaselDropTarget@@AEAAXXZ`
- size: `1384`
- prototype: `void __fastcall(ShellEaselDropTarget *__hidden this)`
- caller_count: `1`
- callee_count: `14`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x180047070`

## callees

- `0x1800037d8`
- `0x180004908`
- `0x180004e88`
- `0x18000cb74`
- `0x180029cfc`
- `0x18003110c`
- `0x180040de0`
- `0x180046c28`
- `0x180047b9c`
- `0x1800496ec`
- `0x18004a698`
- `0x18004a9c4`
- `0x18004ad90`
- `0x180080010`

## import_xrefs

- `KERNEL32!CompareStringOrdinal` at `0x18004997e`
- `KERNEL32!CompareStringOrdinal` at `0x18004997e`
- `KERNEL32!WaitForSingleObject` at `0x180049a2e`
- `KERNEL32!WaitForSingleObject` at `0x180049a2e`
- `KERNEL32!ReleaseMutex` at `0x180049a53`
- `KERNEL32!ReleaseMutex` at `0x180049a53`
- `KERNEL32!CloseHandle` at `0x180049a5c`
- `KERNEL32!CloseHandle` at `0x180049a5c`
- `ole32!CoTaskMemFree` at `0x180049906`
- `ole32!CoTaskMemFree` at `0x180049906`
- `ole32!CoCreateInstance` at `0x1800497c0`
- `ole32!CoCreateInstance` at `0x1800497c0`
- `SHELL32!SHCreateShellItemArrayFromDataObject` at `0x180049719`
- `SHELL32!SHCreateShellItemArrayFromDataObject` at `0x180049719`
- `SHELL32!SHChangeNotify` at `0x180049b92`
- `SHELL32!SHChangeNotify` at `0x180049bd5`
- `SHELL32!SHChangeNotify` at `0x180049bef`
- `SHELL32!SHChangeNotify` at `0x180049b92`
- `SHELL32!SHChangeNotify` at `0x180049bd5`
- `SHELL32!SHChangeNotify` at `0x180049bef`
- `SHELL32!__imp_ILFree` at `0x180049bdf`
- `SHELL32!__imp_ILFree` at `0x180049bdf`
- `SHLWAPI!PathFindExtensionW` at `0x18004995a`
- `SHLWAPI!PathFindExtensionW` at `0x18004995a`
- `SHLWAPI!__imp_ShellMessageBoxW` at `0x180049af1`
- `SHLWAPI!__imp_ShellMessageBoxW` at `0x180049af1`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x180049725`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18004974a`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18004975d`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x180049789`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x1800497cc`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x180049ba2`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x180049c44`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x180049c4d`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x180049725`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18004974a`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18004975d`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x180049789`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x1800497cc`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x180049ba2`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x180049c44`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x180049c4d`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
void __fastcall ShellEaselDropTarget::RotateImages(IDataObject **this)
{
  HRESULT v2; // eax
  int v3; // edx
  int v4; // eax
  int v5; // edx
  unsigned int v6; // esi
  int v7; // edx
  int v8; // r15d
  HRESULT v9; // eax
  int v10; // edx
  LPVOID v11; // rdi
  void (__fastcall *v12)(LPVOID, __int64, _QWORD, _QWORD, _QWORD); // rbx
  _QWORD *v13; // rax
  LPVOID v14; // rdi
  void (__fastcall *v15)(LPVOID, _QWORD); // rbx
  _QWORD *v16; // rax
  unsigned int v17; // r14d
  int v18; // eax
  int v19; // edx
  int v20; // eax
  int v21; // edx
  LPVOID v22; // rbx
  __int64 v23; // rax
  const unsigned __int16 **v24; // rax
  unsigned int v25; // r14d
  LPVOID v26; // rbx
  LPCWSTR *v27; // rax
  const WCHAR *ExtensionW; // rax
  LPVOID v29; // rbx
  void (__fastcall *v30)(LPVOID, __int64, _QWORD); // rdi
  _QWORD *v31; // rax
  const unsigned __int16 **v32; // rax
  int v33; // eax
  int v34; // edx
  HANDLE v35; // rbx
  enum WICBitmapTransformOptions v36; // r8d
  bool *v37; // r9
  __int64 v38; // rdx
  int v39; // r15d
  ShellEaselDropTarget *v40; // rcx
  LPVOID v41; // rbx
  void (__fastcall *v42)(LPVOID, __int64, _QWORD); // rdi
  _QWORD *v43; // rax
  unsigned __int16 v44; // ax
  void (__fastcall *v45)(LPVOID, __int64, _QWORD, _QWORD, _QWORD); // rdi
  _QWORD *v46; // rax
  bool v47; // cf
  bool v48; // zf
  LPCVOID *v49; // rax
  const unsigned __int16 **v50; // rax
  unsigned int v51; // ebx
  const unsigned __int16 **v52; // rax
  HANDLE hHandle; // [rsp+30h] [rbp-48h] BYREF
  _BYTE v54[8]; // [rsp+38h] [rbp-40h] BYREF
  _BYTE v55[8]; // [rsp+40h] [rbp-38h] BYREF
  _QWORD v56[3]; // [rsp+48h] [rbp-30h] BYREF
  int v57; // [rsp+60h] [rbp-18h]
  unsigned int v58; // [rsp+C0h] [rbp+48h] BYREF
  LPVOID v59; // [rsp+C8h] [rbp+50h] BYREF
  void *ppv; // [rsp+D0h] [rbp+58h] BYREF
  LPVOID pv; // [rsp+D8h] [rbp+60h] BYREF

  ppv = 0;
  v2 = SHCreateShellItemArrayFromDataObject(this[11], &GUID_b63ea76d_1f85_456f_a19c_48159efa858b, &ppv);
  if ( v2 < 0 )
  {
    Base::Throw((Base *)(unsigned int)v2, v3);
    __debugbreak();
  }
  v58 = 0;
  v4 = (*(__int64 (__fastcall **)(void *, unsigned int *))(*(_QWORD *)ppv + 56LL))(ppv, &v58);
  if ( v4 < 0 )
  {
    Base::Throw((Base *)(unsigned int)v4, v5);
    __debugbreak();
  }
  v6 = v58;
  if ( !v58 )
  {
    Base::Throw((Base *)0x8000FFFFLL, v5);
    __debugbreak();
  }
  memset(v56, 0, sizeof(v56));
  v57 = 0;
  if ( !(unsigned __int8)ATL::CAtlArray<Base::Path,ATL::CElementTraits<Base::Path>>::SetCount(v56, v58) )
  {
    Base::Throw((Base *)0x8007000ELL, v7);
    __debugbreak();
  }
  v59 = 0;
  v8 = 1;
  if ( v6 > 1 )
  {
    v9 = CoCreateInstance(&CLSID_ProgressDialog, 0, 3u, &GUID_ebbc7c04_315e_11d2_b62f_006097df5bd4, &v59);
    if ( v9 < 0 )
    {
      Base::Throw((Base *)(unsigned int)v9, v10);
      __debugbreak();
    }
    v11 = v59;
    v12 = *(void (__fastcall **)(LPVOID, __int64, _QWORD, _QWORD, _QWORD))(*(_QWORD *)v59 + 80LL);
    v13 = (_QWORD *)Base::ResourceString::ResourceString((Base::ResourceString *)&pv, 0xBD2u);
    v12(v11, 1, *v13, 0, 0);
    Base::String::~String((Base::String *)&pv);
    v14 = v59;
    v15 = *(void (__fastcall **)(LPVOID, _QWORD))(*(_QWORD *)v59 + 40LL);
    v16 = (_QWORD *)Base::ResourceString::ResourceString(
                      (Base::ResourceString *)&pv,
                      (unsigned int)(*((_DWORD *)this + 20) != 4) + 3024);
    v15(v14, *v16);
    Base::String::~String((Base::String *)&pv);
    (*(void (__fastcall **)(LPVOID, _QWORD, _QWORD, __int64, _QWORD))(*(_QWORD *)v59 + 24LL))(v59, 0, 0, 2, 0);
    (*(void (__fastcall **)(LPVOID, __int64, _QWORD))(*(_QWORD *)v59 + 64LL))(v59, 1, v6);
  }
  v17 = 0;
  do
  {
    hHandle = 0;
    v18 = (*(__int64 (__fastcall **)(void *, _QWORD, HANDLE *))(*(_QWORD *)ppv + 64LL))(ppv, v17, &hHandle);
    if ( v18 < 0 )
      goto LABEL_51;
    pv = 0;
    v20 = (*(__int64 (__fastcall **)(HANDLE, __int64, LPVOID *))(*(_QWORD *)hHandle + 40LL))(hHandle, 2147647488LL, &pv);
    if ( v20 < 0 )
    {
      Base::Throw((Base *)(unsigned int)v20, v21);
LABEL_51:
      Base::Throw((Base *)(unsigned int)v18, v19);
      JUMPOUT(0x180049C53LL);
    }
    v22 = pv;
    v23 = ATL::CAtlArray<unsigned __int64,ATL::CElementTraits<unsigned __int64>>::operator[](v56, v17);
    ATL::CSimpleStringT<unsigned short,0>::SetString(v23, v22);
    v24 = (const unsigned __int16 **)ATL::CAtlArray<unsigned __int64,ATL::CElementTraits<unsigned __int64>>::operator[](
                                       v56,
                                       v17);
    SuspendResumeParent(*v24, 1);
    CoTaskMemFree(pv);
    pv = 0;
    ATL::CComPtrBase<IFreeThreadedItemContainer>::~CComPtrBase<IFreeThreadedItemContainer>(&hHandle);
    ++v17;
  }
  while ( v17 < v6 );
  v25 = 0;
  v26 = v59;
  while ( !v26 || !(*(unsigned int (__fastcall **)(LPVOID))(*(_QWORD *)v26 + 56LL))(v26) )
  {
    v8 = v25;
    v27 = (LPCWSTR *)ATL::CAtlArray<unsigned __int64,ATL::CElementTraits<unsigned __int64>>::operator[](v56, v25);
    ExtensionW = PathFindExtensionW(*v27);
    if ( ExtensionW && CompareStringOrdinal(ExtensionW, -1, L".gif", -1, 1) == 2 )
      goto LABEL_35;
    v29 = v59;
    if ( v59 )
    {
      v30 = *(void (__fastcall **)(LPVOID, __int64, _QWORD))(*(_QWORD *)v59 + 80LL);
      v31 = (_QWORD *)ATL::CAtlArray<unsigned __int64,ATL::CElementTraits<unsigned __int64>>::operator[](v56, v25);
      v30(v29, 2, *v31);
      (*(void (__fastcall **)(LPVOID, _QWORD, _QWORD))(*(_QWORD *)v59 + 64LL))(v59, v25 + 1, v6);
    }
    hHandle = 0;
    v32 = (const unsigned __int16 **)ATL::CAtlArray<unsigned __int64,ATL::CElementTraits<unsigned __int64>>::operator[](
                                       v56,
                                       v25);
    if ( (int)CreateMutexForRotate(*v32, &hHandle) < 0 )
      goto LABEL_35;
    pv = 0;
    v33 = (*(__int64 (__fastcall **)(void *, _QWORD, LPVOID *))(*(_QWORD *)ppv + 64LL))(ppv, v25, &pv);
    if ( v33 < 0 )
    {
      Base::Throw((Base *)(unsigned int)v33, v34);
      goto LABEL_44;
    }
    v35 = hHandle;
    WaitForSingleObject(hHandle, 0xFFFFFFFF);
    v38 = 1;
    if ( *((_DWORD *)this + 20) != 4 )
      v38 = 3;
    v39 = CodecUtil::SaveImageWithRotation((CodecUtil *)pv, (struct IShellItem *)v38, v36, v37);
    ReleaseMutex(v35);
    CloseHandle(v35);
    ATL::CComPtrBase<IFreeThreadedItemContainer>::~CComPtrBase<IFreeThreadedItemContainer>(&pv);
    if ( v39 >= 0 )
    {
LABEL_35:
      v8 = 1;
    }
    else
    {
      v41 = v59;
      if ( v59 )
      {
        v42 = *(void (__fastcall **)(LPVOID, __int64, _QWORD))(*(_QWORD *)v59 + 80LL);
        v43 = (_QWORD *)Base::ResourceString::ResourceString((Base::ResourceString *)v54, 0xBD3u);
        v42(v41, 1, *v43);
        Base::String::~String((Base::String *)v54);
      }
      v44 = ShellEaselDropTarget::TranslateRotateFailure(v40, v39);
      v8 = 1;
      if ( ShellMessageBoxW(hModule, 0, (LPCWSTR)v44, (LPCWSTR)0xBD4, (v6 - v25 > 1) + 16) == 2 )
        v25 = v6 - 1;
      v26 = v59;
      if ( !v59 )
        goto LABEL_37;
      v45 = *(void (__fastcall **)(LPVOID, __int64, _QWORD, _QWORD, _QWORD))(*(_QWORD *)v59 + 80LL);
      v46 = (_QWORD *)Base::ResourceString::ResourceString((Base::ResourceString *)v55, 0xBD2u);
      v45(v26, 1, *v46, 0, 0);
      Base::String::~String((Base::String *)v55);
    }
    v26 = v59;
LABEL_37:
    if ( ++v25 >= v6 )
      goto LABEL_38;
  }
  v26 = v59;
LABEL_38:
  if ( v26 )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v26 + 32LL))(v26);
  LODWORD(v29) = 4096;
  v47 = v6 == 0;
  v48 = v6 == 1;
  if ( v6 == 1 )
  {
    v49 = (LPCVOID *)ATL::CAtlArray<unsigned __int64,ATL::CElementTraits<unsigned __int64>>::operator[](v56, 0);
    SHChangeNotify(0x2000, 5u, *v49, 0);
    goto LABEL_47;
  }
LABEL_44:
  if ( !v47 && !v48 )
  {
    pv = 0;
    v50 = (const unsigned __int16 **)ATL::CAtlArray<unsigned __int64,ATL::CElementTraits<unsigned __int64>>::operator[](
                                       v56,
                                       0);
    if ( (int)GetSimpleParent(*v50, (struct _ITEMIDLIST **)&pv) >= 0 )
    {
      SHChangeNotify((LONG)v29, 0, pv, 0);
      ILFree((LPITEMIDLIST)pv);
    }
  }
LABEL_47:
  SHChangeNotify(0, (UINT)v29, 0, 0);
  v51 = 0;
  do
  {
    v52 = (const unsigned __int16 **)ATL::CAtlArray<unsigned __int64,ATL::CElementTraits<unsigned __int64>>::operator[](
                                       v56,
                                       v51);
    SuspendResumeParent(*v52, 0);
    v51 += v8;
  }
  while ( v51 < v6 );
  ATL::CComPtrBase<IFreeThreadedItemContainer>::~CComPtrBase<IFreeThreadedItemContainer>(&v59);
  ATL::CAtlArray<Base::Path,ATL::CElementTraits<Base::Path>>::~CAtlArray<Base::Path,ATL::CElementTraits<Base::Path>>(v56);
  ATL::CComPtrBase<IFreeThreadedItemContainer>::~CComPtrBase<IFreeThreadedItemContainer>(&ppv);
}

```

## disassembly

```asm
0x1800496ec  push    rbp
0x1800496ee  push    rbx
0x1800496ef  push    rsi
0x1800496f0  push    rdi
0x1800496f1  push    r12
0x1800496f3  push    r13
0x1800496f5  push    r14
0x1800496f7  push    r15
0x1800496f9  mov     rbp, rsp
0x1800496fc  sub     rsp, 78h
0x180049700  mov     r13, rcx
0x180049703  xor     r12d, r12d
0x180049706  mov     [rbp+ppv], r12
0x18004970a  lea     r8, [rbp+ppv]; ppv
0x18004970e  lea     rdx, _GUID_b63ea76d_1f85_456f_a19c_48159efa858b; riid
0x180049715  mov     rcx, [rcx+58h]; pdo
0x180049719  call    cs:__imp_SHCreateShellItemArrayFromDataObject
0x18004971f  test    eax, eax
0x180049721  jns     short loc_18004972C
0x180049723  mov     ecx, eax
0x180049725  call    cs:__imp_?Throw@Base@@YAXJ@Z; Base::Throw(long)
0x18004972b  int     3; Trap to Debugger
0x18004972c  mov     [rbp+arg_0], r12d
0x180049730  mov     rcx, [rbp+ppv]
0x180049734  mov     rax, [rcx]
0x180049737  lea     rdx, [rbp+arg_0]
0x18004973b  mov     rax, [rax+38h]
0x18004973f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049744  test    eax, eax
0x180049746  jns     short loc_180049751
0x180049748  mov     ecx, eax
0x18004974a  call    cs:__imp_?Throw@Base@@YAXJ@Z; Base::Throw(long)
0x180049750  int     3; Trap to Debugger
0x180049751  mov     esi, [rbp+arg_0]
0x180049754  test    esi, esi
0x180049756  jnz     short loc_180049764
0x180049758  mov     ecx, 8000FFFFh
0x18004975d  call    cs:__imp_?Throw@Base@@YAXJ@Z; Base::Throw(long)
0x180049763  int     3; Trap to Debugger
0x180049764  mov     [rbp+var_30], r12
0x180049768  mov     [rbp+var_28], r12
0x18004976c  mov     [rbp+var_20], r12
0x180049770  mov     [rbp+var_18], r12d
0x180049774  mov     rdx, rsi
0x180049777  lea     rcx, [rbp+var_30]
0x18004977b  call    ?SetCount@?$CAtlArray@VPath@Base@@V?$CElementTraits@VPath@Base@@@ATL@@@ATL@@QEAA_N_KH@Z; ATL::CAtlArray<Base::Path,ATL::CElementTraits<Base::Path>>::SetCount(unsigned __int64,int)
0x180049780  test    al, al
0x180049782  jnz     short loc_180049790
0x180049784  mov     ecx, 8007000Eh
0x180049789  call    cs:__imp_?Throw@Base@@YAXJ@Z; Base::Throw(long)
0x18004978f  int     3; Trap to Debugger
0x180049790  mov     [rbp+arg_8], r12
0x180049794  mov     r15d, 1
0x18004979a  cmp     esi, r15d
0x18004979d  jbe     loc_180049884
0x1800497a3  lea     rax, [rbp+arg_8]
0x1800497a7  mov     qword ptr [rsp+78h+bIgnoreCase], rax; ppv
0x1800497ac  lea     r9, _GUID_ebbc7c04_315e_11d2_b62f_006097df5bd4; riid
0x1800497b3  xor     edx, edx; pUnkOuter
0x1800497b5  lea     r8d, [r15+2]; dwClsContext
0x1800497b9  lea     rcx, CLSID_ProgressDialog; rclsid
0x1800497c0  call    cs:__imp_CoCreateInstance
0x1800497c6  test    eax, eax
0x1800497c8  jns     short loc_1800497D3
0x1800497ca  mov     ecx, eax
0x1800497cc  call    cs:__imp_?Throw@Base@@YAXJ@Z; Base::Throw(long)
0x1800497d2  int     3; Trap to Debugger
0x1800497d3  mov     rdi, [rbp+arg_8]
0x1800497d7  mov     rax, [rdi]
0x1800497da  mov     rbx, [rax+50h]
0x1800497de  mov     edx, 0BD2h; unsigned int
0x1800497e3  lea     rcx, [rbp+pv]; this
0x1800497e7  call    ??0ResourceString@Base@@QEAA@I@Z; Base::ResourceString::ResourceString(uint)
0x1800497ec  nop
0x1800497ed  mov     qword ptr [rsp+78h+bIgnoreCase], r12
0x1800497f2  xor     r9d, r9d
0x1800497f5  mov     r8, [rax]
0x1800497f8  mov     edx, r15d
0x1800497fb  mov     rcx, rdi
0x1800497fe  mov     rax, rbx
0x180049801  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049806  nop
0x180049807  lea     rcx, [rbp+pv]; this
0x18004980b  call    ??1String@Base@@QEAA@XZ; Base::String::~String(void)
0x180049810  mov     rdi, [rbp+arg_8]
0x180049814  mov     rax, [rdi]
0x180049817  mov     rbx, [rax+28h]
0x18004981b  mov     edx, r12d
0x18004981e  cmp     dword ptr [r13+50h], 4
0x180049823  setnz   dl
0x180049826  add     edx, 0BD0h; unsigned int
0x18004982c  lea     rcx, [rbp+pv]; this
0x180049830  call    ??0ResourceString@Base@@QEAA@I@Z; Base::ResourceString::ResourceString(uint)
0x180049835  nop
0x180049836  mov     rdx, [rax]
0x180049839  mov     rcx, rdi
0x18004983c  mov     rax, rbx
0x18004983f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049844  nop
0x180049845  lea     rcx, [rbp+pv]; this
0x180049849  call    ??1String@Base@@QEAA@XZ; Base::String::~String(void)
0x18004984e  mov     rcx, [rbp+arg_8]
0x180049852  mov     rax, [rcx]
0x180049855  mov     qword ptr [rsp+78h+bIgnoreCase], r12
0x18004985a  mov     r9d, 2
0x180049860  xor     r8d, r8d
0x180049863  xor     edx, edx
0x180049865  mov     rax, [rax+18h]
0x180049869  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004986e  mov     rcx, [rbp+arg_8]
0x180049872  mov     rax, [rcx]
0x180049875  mov     r8d, esi
0x180049878  mov     edx, r15d
0x18004987b  mov     rax, [rax+40h]
0x18004987f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049884  mov     r14d, r12d
0x180049887  mov     [rbp+hHandle], r12
0x18004988b  mov     rcx, [rbp+ppv]
0x18004988f  mov     rax, [rcx]
0x180049892  lea     r8, [rbp+hHandle]
0x180049896  mov     edx, r14d
0x180049899  mov     rax, [rax+40h]
0x18004989d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800498a2  test    eax, eax
0x1800498a4  js      loc_180049C4B
0x1800498aa  mov     [rbp+pv], r12
0x1800498ae  mov     rcx, [rbp+hHandle]
0x1800498b2  mov     rax, [rcx]
0x1800498b5  lea     r8, [rbp+pv]
0x1800498b9  mov     edx, 80028000h
0x1800498be  mov     rax, [rax+28h]
0x1800498c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800498c7  test    eax, eax
0x1800498c9  js      loc_180049C42
0x1800498cf  mov     rbx, [rbp+pv]
0x1800498d3  mov     edx, r14d
0x1800498d6  lea     rcx, [rbp+var_30]
0x1800498da  call    ??A?$CAtlArray@_KV?$CElementTraits@_K@ATL@@@ATL@@QEAAAEA_K_K@Z; ATL::CAtlArray<unsigned __int64,ATL::CElementTraits<unsigned __int64>>::operator[](unsigned __int64)
0x1800498df  mov     rdx, rbx
0x1800498e2  mov     rcx, rax
0x1800498e5  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBG@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *)
0x1800498ea  mov     edx, r14d
0x1800498ed  lea     rcx, [rbp+var_30]
0x1800498f1  call    ??A?$CAtlArray@_KV?$CElementTraits@_K@ATL@@@ATL@@QEAAAEA_K_K@Z; ATL::CAtlArray<unsigned __int64,ATL::CElementTraits<unsigned __int64>>::operator[](unsigned __int64)
0x1800498f6  mov     edx, r15d; int
0x1800498f9  mov     rcx, [rax]; unsigned __int16 *
0x1800498fc  call    ?SuspendResumeParent@@YAXPEBGH@Z; SuspendResumeParent(ushort const *,int)
0x180049901  nop
0x180049902  mov     rcx, [rbp+pv]; pv
0x180049906  call    cs:__imp_CoTaskMemFree
0x18004990c  mov     [rbp+pv], r12
0x180049910  lea     rcx, [rbp+hHandle]
0x180049914  call    ??1?$CComPtrBase@UIFreeThreadedItemContainer@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IFreeThreadedItemContainer>::~CComPtrBase<IFreeThreadedItemContainer>(void)
0x180049919  add     r14d, r15d
0x18004991c  cmp     r14d, esi
0x18004991f  jb      loc_180049887
0x180049925  mov     r14d, r12d
0x180049928  mov     rbx, [rbp+arg_8]
0x18004992c  test    rbx, rbx
0x18004992f  jz      short loc_180049948
0x180049931  mov     rax, [rbx]
0x180049934  mov     rcx, rbx
0x180049937  mov     rax, [rax+38h]
0x18004993b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049940  test    eax, eax
0x180049942  jnz     loc_180049B9A
0x180049948  mov     r15d, r14d
0x18004994b  mov     edx, r14d
0x18004994e  lea     rcx, [rbp+var_30]
0x180049952  call    ??A?$CAtlArray@_KV?$CElementTraits@_K@ATL@@@ATL@@QEAAAEA_K_K@Z; ATL::CAtlArray<unsigned __int64,ATL::CElementTraits<unsigned __int64>>::operator[](unsigned __int64)
0x180049957  mov     rcx, [rax]; pszPath
0x18004995a  call    cs:__imp_PathFindExtensionW
0x180049960  test    rax, rax
0x180049963  jz      short loc_18004998D
0x180049965  mov     [rsp+78h+bIgnoreCase], 1; bIgnoreCase
0x18004996d  or      r9d, 0FFFFFFFFh; cchCount2
0x180049971  lea     r8, aGif_0; ".gif"
0x180049978  or      edx, r9d; cchCount1
0x18004997b  mov     rcx, rax; lpString1
0x18004997e  call    cs:__imp_CompareStringOrdinal
0x180049984  cmp     eax, 2
0x180049987  jz      loc_180049B44
0x18004998d  mov     rbx, [rbp+arg_8]
0x180049991  test    rbx, rbx
0x180049994  jz      short loc_1800499DD
0x180049996  mov     rax, [rbx]
0x180049999  mov     rdi, [rax+50h]
0x18004999d  mov     rdx, r15
0x1800499a0  lea     rcx, [rbp+var_30]
0x1800499a4  call    ??A?$CAtlArray@_KV?$CElementTraits@_K@ATL@@@ATL@@QEAAAEA_K_K@Z; ATL::CAtlArray<unsigned __int64,ATL::CElementTraits<unsigned __int64>>::operator[](unsigned __int64)
0x1800499a9  mov     qword ptr [rsp+78h+bIgnoreCase], r12
0x1800499ae  mov     r9d, 1
0x1800499b4  mov     r8, [rax]
0x1800499b7  lea     edx, [r9+1]
0x1800499bb  mov     rcx, rbx
0x1800499be  mov     rax, rdi
0x1800499c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800499c6  mov     rcx, [rbp+arg_8]
0x1800499ca  mov     rax, [rcx]
0x1800499cd  lea     edx, [r14+1]
0x1800499d1  mov     r8d, esi
0x1800499d4  mov     rax, [rax+40h]
0x1800499d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800499dd  mov     [rbp+hHandle], r12
0x1800499e1  mov     rdx, r15
0x1800499e4  lea     rcx, [rbp+var_30]
0x1800499e8  call    ??A?$CAtlArray@_KV?$CElementTraits@_K@ATL@@@ATL@@QEAAAEA_K_K@Z; ATL::CAtlArray<unsigned __int64,ATL::CElementTraits<unsigned __int64>>::operator[](unsigned __int64)
0x1800499ed  lea     rdx, [rbp+hHandle]; void **
0x1800499f1  mov     rcx, [rax]; unsigned __int16 *
0x1800499f4  call    ?CreateMutexForRotate@@YAJPEBGPEAPEAX@Z; CreateMutexForRotate(ushort const *,void * *)
0x1800499f9  test    eax, eax
0x1800499fb  js      loc_180049B44
0x180049a01  mov     [rbp+pv], r12
0x180049a05  mov     rcx, [rbp+ppv]
0x180049a09  mov     rax, [rcx]
0x180049a0c  lea     r8, [rbp+pv]
0x180049a10  mov     edx, r14d
0x180049a13  mov     rax, [rax+40h]
0x180049a17  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049a1c  test    eax, eax
0x180049a1e  js      loc_180049BA0
0x180049a24  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180049a27  mov     rbx, [rbp+hHandle]
0x180049a2b  mov     rcx, rbx; hHandle
0x180049a2e  call    cs:__imp_WaitForSingleObject
0x180049a34  mov     edx, 1
0x180049a39  cmp     dword ptr [r13+50h], 4
0x180049a3e  lea     eax, [rdx+2]
0x180049a41  cmovnz  edx, eax; struct IShellItem *
0x180049a44  mov     rcx, [rbp+pv]; this
0x180049a48  call    ?SaveImageWithRotation@CodecUtil@@YAJPEAUIShellItem@@W4WICBitmapTransformOptions@@PEA_N@Z; CodecUtil::SaveImageWithRotation(IShellItem *,WICBitmapTransformOptions,bool *)
0x180049a4d  mov     r15d, eax
0x180049a50  mov     rcx, rbx; hMutex
0x180049a53  call    cs:__imp_ReleaseMutex
0x180049a59  mov     rcx, rbx; hObject
0x180049a5c  call    cs:__imp_CloseHandle
0x180049a62  nop
0x180049a63  lea     rcx, [rbp+pv]
0x180049a67  call    ??1?$CComPtrBase@UIFreeThreadedItemContainer@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IFreeThreadedItemContainer>::~CComPtrBase<IFreeThreadedItemContainer>(void)
0x180049a6c  test    r15d, r15d
0x180049a6f  jns     loc_180049B44
0x180049a75  mov     rbx, [rbp+arg_8]
0x180049a79  test    rbx, rbx
0x180049a7c  jz      short loc_180049AB8
0x180049a7e  mov     rax, [rbx]
0x180049a81  mov     rdi, [rax+50h]
0x180049a85  mov     edx, 0BD3h; unsigned int
0x180049a8a  lea     rcx, [rbp+var_40]; this
0x180049a8e  call    ??0ResourceString@Base@@QEAA@I@Z; Base::ResourceString::ResourceString(uint)
0x180049a93  nop
0x180049a94  mov     qword ptr [rsp+78h+bIgnoreCase], r12
0x180049a99  xor     r9d, r9d
0x180049a9c  mov     r8, [rax]
0x180049a9f  lea     edx, [r9+1]
0x180049aa3  mov     rcx, rbx
0x180049aa6  mov     rax, rdi
0x180049aa9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049aae  nop
0x180049aaf  lea     rcx, [rbp+var_40]; this
0x180049ab3  call    ??1String@Base@@QEAA@XZ; Base::String::~String(void)
0x180049ab8  mov     edx, r15d; int
0x180049abb  call    ?TranslateRotateFailure@ShellEaselDropTarget@@AEAAIJ@Z; ShellEaselDropTarget::TranslateRotateFailure(long)
0x180049ac0  mov     edx, esi
0x180049ac2  sub     edx, r14d
0x180049ac5  mov     r9d, r12d
0x180049ac8  mov     r15d, 1
0x180049ace  cmp     edx, r15d
0x180049ad1  setnbe  r9b
0x180049ad5  add     r9d, 10h
0x180049ad9  movzx   r8d, ax; lpcText
0x180049add  mov     [rsp+78h+bIgnoreCase], r9d; fuStyle
0x180049ae2  xor     edx, edx; hWnd
0x180049ae4  mov     r9d, 0BD4h; lpcTitle
0x180049aea  mov     rcx, cs:hModule; hAppInst
0x180049af1  call    cs:__imp_ShellMessageBoxW
0x180049af7  cmp     eax, 2
0x180049afa  jnz     short loc_180049B00
0x180049afc  lea     r14d, [rsi-1]
0x180049b00  mov     rbx, [rbp+arg_8]
0x180049b04  test    rbx, rbx
0x180049b07  jz      short loc_180049B4E
0x180049b09  mov     rax, [rbx]
0x180049b0c  mov     rdi, [rax+50h]
0x180049b10  mov     edx, 0BD2h; unsigned int
0x180049b15  lea     rcx, [rbp+var_38]; this
0x180049b19  call    ??0ResourceString@Base@@QEAA@I@Z; Base::ResourceString::ResourceString(uint)
0x180049b1e  nop
0x180049b1f  mov     qword ptr [rsp+78h+bIgnoreCase], r12
0x180049b24  xor     r9d, r9d
0x180049b27  mov     r8, [rax]
0x180049b2a  mov     edx, r15d
0x180049b2d  mov     rcx, rbx
0x180049b30  mov     rax, rdi
0x180049b33  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049b38  nop
0x180049b39  lea     rcx, [rbp+var_38]; this
0x180049b3d  call    ??1String@Base@@QEAA@XZ; Base::String::~String(void)
0x180049b42  jmp     short loc_180049B4A
0x180049b44  mov     r15d, 1
0x180049b4a  mov     rbx, [rbp+arg_8]
  ... truncated ...
```
