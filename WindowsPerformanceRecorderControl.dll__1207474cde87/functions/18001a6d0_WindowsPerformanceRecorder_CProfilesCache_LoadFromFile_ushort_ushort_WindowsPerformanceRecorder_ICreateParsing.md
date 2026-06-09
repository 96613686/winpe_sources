# WindowsPerformanceRecorder::CProfilesCache::LoadFromFile(ushort *,ushort *,WindowsPerformanceRecorder::ICreateParsingErrorInfo *,WindowsPerformanceRecorder::CBaseProfileElement::CElementType,WindowsPerformanceRecorder::CBaseProfileElement * *)

- ea: `0x18001a6d0`
- end: `0x18001a8c2`
- name: `?LoadFromFile@CProfilesCache@WindowsPerformanceRecorder@@QEAAJPEAG0PEAUICreateParsingErrorInfo@2@W4CElementType@CBaseProfileElement@2@PEAPEAV52@@Z`
- size: `498`
- prototype: ``
- caller_count: `2`
- callee_count: `13`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180023090`
- `0x18006b9c0`

## callees

- `0x180008330`
- `0x18000eeb0`
- `0x180018d84`
- `0x18001930c`
- `0x18001a6d0`
- `0x18001c458`
- `0x1800218a8`
- `0x180022634`
- `0x180043378`
- `0x18004b46c`
- `0x18007073c`
- `0x1800709b0`
- `0x18008c010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18001a705`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18001a705`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18001a883`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18001a883`

## string_xrefs

- `0x18001a77d`: `WPRControlMinimalBuiltinProfiles.xml`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall WindowsPerformanceRecorder::CProfilesCache::LoadFromFile(
        __int64 a1,
        __int64 a2,
        unsigned __int16 *a3,
        struct IUnknown *a4,
        unsigned int a5,
        __int64 a6)
{
  HRESULT v10; // r13d
  char v11; // r12
  __int64 v12; // r8
  unsigned __int16 *v13; // rbx
  const unsigned __int16 *v14; // rdx
  int ProfileFromFileOrString; // eax
  unsigned int BaseProfileElementFromFile; // r14d
  __int64 v17; // rdi
  __int64 v19; // [rsp+30h] [rbp-78h] BYREF
  unsigned __int16 *v20; // [rsp+38h] [rbp-70h] BYREF
  _QWORD v21[2]; // [rsp+40h] [rbp-68h] BYREF
  ATL::CAtlException *v22; // [rsp+50h] [rbp-58h] BYREF
  void **v23; // [rsp+58h] [rbp-50h] BYREF
  HRESULT v24; // [rsp+60h] [rbp-48h]

  v21[1] = -2;
  v23 = &WindowsPerformanceRecorder::Impl::CAutoComInit::`vftable';
  v10 = CoInitializeEx(0, 0);
  v24 = v10;
  v21[0] = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
  v20 = (unsigned __int16 *)(((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24);
  v11 = 0;
  try
  {
    ATL::CSimpleStringT<unsigned short,0>::SetString(v21, a2);
    ATL::CSimpleStringT<unsigned short,0>::SetString(&v20, a3);
    v13 = v20;
    if ( !*((_DWORD *)v20 - 4) )
    {
      v14 = L"WPRControlMinimalBuiltinProfiles.xml";
      if ( !WindowsPerformanceRecorder::CProfilesCache::sc_fUseMinimalBuiltInProfiles )
        v14 = (const unsigned __int16 *)&WindowsPerformanceRecorder::CProfilesCache::sc_WPRControlBuiltInProfileFileName;
      ATL::CSimpleStringT<unsigned short,0>::SetString(&v20, v14);
      v11 = 1;
      v13 = v20;
    }
  }
  catch ( ATL::CAtlException *v22 )
  {
    LODWORD(v19) = *(_DWORD *)v22;
    WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo((WindowsPerformanceRecorder::Status::CSessionInfo *)&v20);
    WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo((WindowsPerformanceRecorder::Status::CSessionInfo *)v21);
    WindowsPerformanceRecorder::Impl::CAutoComInit::~CAutoComInit((WindowsPerformanceRecorder::Impl::CAutoComInit *)&v23);
    return (unsigned int)v19;
  }
  *(_BYTE *)(a1 + 56) = 0;
  if ( *(struct IUnknown **)(a1 + 48) != a4 )
    ATL::AtlComPtrAssign((struct IUnknown **)(a1 + 48), a4);
  v19 = 0;
  LOBYTE(v12) = v11;
  if ( ((int)WindowsPerformanceRecorder::CProfilesCache::GetProfileElementsFromCache(a1, v13, v12, &v19) < 0
     || v19 == *(_QWORD *)(a1 + 8))
    && (!v11
      ? (ProfileFromFileOrString = WindowsPerformanceRecorder::CProfilesCache::LoadProfileFromFileOrString(
                                     (char ***)a1,
                                     a3,
                                     1))
      : (ProfileFromFileOrString = WindowsPerformanceRecorder::CProfilesCache::LoadBuiltInProfileFile(
                                     (WindowsPerformanceRecorder::CProfilesCache *)a1,
                                     v13)),
        BaseProfileElementFromFile = ProfileFromFileOrString,
        ProfileFromFileOrString < 0) )
  {
    WindowsPerformanceRecorder::CProfilesCache::RemoveProfileElementsCollectionFromCache(
      (WindowsPerformanceRecorder::CProfilesCache *)a1,
      v13);
    v17 = v21[0];
  }
  else
  {
    v17 = v21[0];
    BaseProfileElementFromFile = WindowsPerformanceRecorder::CProfilesCache::GetBaseProfileElementFromFile(
                                   a1,
                                   v21[0] & -(__int64)(*(_DWORD *)(v21[0] - 16LL) != 0),
                                   v13,
                                   a5,
                                   v11,
                                   a6);
  }
  ATL::CComPtrBase<WindowsPerformanceRecorder::ICreateParsingErrorInfo>::Release(a1 + 48);
  *(_BYTE *)(a1 + 56) = 0;
  ATL::CStringData::Release((ATL::CStringData *)(v13 - 12));
  ATL::CStringData::Release((ATL::CStringData *)(v17 - 24));
  if ( v10 >= 0 )
    CoUninitialize();
  return BaseProfileElementFromFile;
}

```

## disassembly

```asm
0x18001a6d0  push    rbx
0x18001a6d2  push    rsi
0x18001a6d3  push    rdi
0x18001a6d4  push    r12
0x18001a6d6  push    r13
0x18001a6d8  push    r14
0x18001a6da  push    r15
0x18001a6dc  sub     rsp, 70h
0x18001a6e0  mov     [rsp+0A8h+var_60], 0FFFFFFFFFFFFFFFEh
0x18001a6e9  mov     rdi, r9
0x18001a6ec  mov     r14, r8
0x18001a6ef  mov     rbx, rdx
0x18001a6f2  mov     rsi, rcx
0x18001a6f5  lea     rax, ??_7CAutoComInit@Impl@WindowsPerformanceRecorder@@6B@; const WindowsPerformanceRecorder::Impl::CAutoComInit::`vftable'
0x18001a6fc  mov     [rsp+0A8h+var_50], rax
0x18001a701  xor     edx, edx; dwCoInit
0x18001a703  xor     ecx, ecx; pvReserved
0x18001a705  call    cs:__imp_CoInitializeEx
0x18001a70b  mov     r13d, eax
0x18001a70e  mov     [rsp+0A8h+var_48], eax
0x18001a712  mov     r8, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x18001a719  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x18001a720  mov     rax, [r8+18h]
0x18001a724  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a729  add     rax, 18h
0x18001a72d  mov     [rsp+0A8h+var_68], rax
0x18001a732  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x18001a739  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x18001a740  mov     rax, [rax+18h]
0x18001a744  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a749  add     rax, 18h
0x18001a74d  mov     [rsp+0A8h+var_70], rax
0x18001a752  xor     r15d, r15d
0x18001a755  mov     r12b, r15b
0x18001a758  mov     rdx, rbx
0x18001a75b  lea     rcx, [rsp+0A8h+var_68]
0x18001a760  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBG@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *)
0x18001a765  mov     rdx, r14
0x18001a768  lea     rcx, [rsp+0A8h+var_70]
0x18001a76d  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBG@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *)
0x18001a772  mov     rbx, [rsp+0A8h+var_70]
0x18001a777  cmp     [rbx-10h], r15d
0x18001a77b  jnz     short loc_18001A7A8
0x18001a77d  lea     rdx, ?sc_WPRControlMinimalBuiltInProfileFileName@CProfilesCache@WindowsPerformanceRecorder@@0QBGB; "WPRControlMinimalBuiltinProfiles.xml"
0x18001a784  lea     rax, ?sc_WPRControlBuiltInProfileFileName@CProfilesCache@WindowsPerformanceRecorder@@0QBGB; ushort const near * const WindowsPerformanceRecorder::CProfilesCache::sc_WPRControlBuiltInProfileFileName
0x18001a78b  cmp     cs:?sc_fUseMinimalBuiltInProfiles@CProfilesCache@WindowsPerformanceRecorder@@0_NA, r15b; bool WindowsPerformanceRecorder::CProfilesCache::sc_fUseMinimalBuiltInProfiles
0x18001a792  cmovz   rdx, rax
0x18001a796  lea     rcx, [rsp+0A8h+var_70]
0x18001a79b  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBG@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *)
0x18001a7a0  mov     r12b, 1
0x18001a7a3  mov     rbx, [rsp+0A8h+var_70]
0x18001a7a8  mov     [rsi+38h], r15b
0x18001a7ac  lea     r15, [rsi+30h]
0x18001a7b0  cmp     [r15], rdi
0x18001a7b3  jz      short loc_18001A7C0
0x18001a7b5  mov     rdx, rdi; struct IUnknown *
0x18001a7b8  mov     rcx, r15; struct IUnknown **
0x18001a7bb  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x18001a7c0  mov     [rsp+0A8h+var_78], 0
0x18001a7c9  lea     r9, [rsp+0A8h+var_78]
0x18001a7ce  mov     r8b, r12b
0x18001a7d1  mov     rdx, rbx
0x18001a7d4  mov     rcx, rsi
0x18001a7d7  call    ?GetProfileElementsFromCache@CProfilesCache@WindowsPerformanceRecorder@@AEAAJPEBG_NAEAV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBUCFileKey@Impl@WindowsPerformanceRecorder@@PEAUCBaseProfileElementCollection@CBaseProfileElement@3@@std@@@std@@@std@@@std@@@Z; WindowsPerformanceRecorder::CProfilesCache::GetProfileElementsFromCache(ushort const *,bool,std::_Tree_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<WindowsPerformanceRecorder::Impl::CFileKey const,WindowsPerformanceRecorder::CBaseProfileElement::CBaseProfileElementCollection *>>>> &)
0x18001a7dc  test    eax, eax
0x18001a7de  js      short loc_18001A7F0
0x18001a7e0  mov     rax, [rsi+8]
0x18001a7e4  cmp     [rsp+0A8h+var_78], rax
0x18001a7e9  setnz   al
0x18001a7ec  test    al, al
0x18001a7ee  jnz     short loc_18001A814
0x18001a7f0  mov     rcx, rsi; this
0x18001a7f3  test    r12b, r12b
0x18001a7f6  jz      short loc_18001A802
0x18001a7f8  mov     rdx, rbx; unsigned __int16 *
0x18001a7fb  call    ?LoadBuiltInProfileFile@CProfilesCache@WindowsPerformanceRecorder@@AEAAJPEBG@Z; WindowsPerformanceRecorder::CProfilesCache::LoadBuiltInProfileFile(ushort const *)
0x18001a800  jmp     short loc_18001A80D
0x18001a802  mov     r8b, 1; bool
0x18001a805  mov     rdx, r14; unsigned __int16 *
0x18001a808  call    ?LoadProfileFromFileOrString@CProfilesCache@WindowsPerformanceRecorder@@AEAAJPEAG_N@Z; WindowsPerformanceRecorder::CProfilesCache::LoadProfileFromFileOrString(ushort *,bool)
0x18001a80d  mov     r14d, eax
0x18001a810  test    eax, eax
0x18001a812  js      short loc_18001A84E
0x18001a814  mov     rdi, [rsp+0A8h+var_68]
0x18001a819  mov     eax, [rdi-10h]
0x18001a81c  neg     eax
0x18001a81e  sbb     rdx, rdx
0x18001a821  and     rdx, rdi
0x18001a824  mov     rax, [rsp+0A8h+arg_28]
0x18001a82c  mov     [rsp+0A8h+var_80], rax
0x18001a831  mov     [rsp+0A8h+var_88], r12b
0x18001a836  mov     r9d, [rsp+0A8h+arg_20]
0x18001a83e  mov     r8, rbx
0x18001a841  mov     rcx, rsi
0x18001a844  call    ?GetBaseProfileElementFromFile@CProfilesCache@WindowsPerformanceRecorder@@AEAAJPEBG0W4CElementType@CBaseProfileElement@2@_NPEAPEAV42@@Z; WindowsPerformanceRecorder::CProfilesCache::GetBaseProfileElementFromFile(ushort const *,ushort const *,WindowsPerformanceRecorder::CBaseProfileElement::CElementType,bool,WindowsPerformanceRecorder::CBaseProfileElement * *)
0x18001a849  mov     r14d, eax
0x18001a84c  jmp     short loc_18001A85E
0x18001a84e  mov     rdx, rbx; unsigned __int16 *
0x18001a851  mov     rcx, rsi; this
0x18001a854  call    ?RemoveProfileElementsCollectionFromCache@CProfilesCache@WindowsPerformanceRecorder@@QEAAJPEBG@Z; WindowsPerformanceRecorder::CProfilesCache::RemoveProfileElementsCollectionFromCache(ushort const *)
0x18001a859  mov     rdi, [rsp+0A8h+var_68]
0x18001a85e  mov     rcx, r15
0x18001a861  call    ?Release@?$CComPtrBase@UICreateParsingErrorInfo@WindowsPerformanceRecorder@@@ATL@@QEAAXXZ; ATL::CComPtrBase<WindowsPerformanceRecorder::ICreateParsingErrorInfo>::Release(void)
0x18001a866  mov     byte ptr [rsi+38h], 0
0x18001a86a  lea     rcx, [rbx-18h]; this
0x18001a86e  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18001a873  nop
0x18001a874  lea     rcx, [rdi-18h]; this
0x18001a878  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18001a87d  nop
0x18001a87e  test    r13d, r13d
0x18001a881  js      short loc_18001A889
0x18001a883  call    cs:__imp_CoUninitialize
0x18001a889  mov     eax, r14d
0x18001a88c  jmp     short loc_18001A8B2
0x18001a88e  lea     rcx, [rsp+0A8h+var_70]; this
0x18001a893  call    ??1CSessionInfo@Status@WindowsPerformanceRecorder@@QEAA@XZ; WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo(void)
0x18001a898  nop
0x18001a899  lea     rcx, [rsp+0A8h+var_68]; this
0x18001a89e  call    ??1CSessionInfo@Status@WindowsPerformanceRecorder@@QEAA@XZ; WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo(void)
0x18001a8a3  nop
0x18001a8a4  lea     rcx, [rsp+0A8h+var_50]; this
0x18001a8a9  call    ??1CAutoComInit@Impl@WindowsPerformanceRecorder@@UEAA@XZ; WindowsPerformanceRecorder::Impl::CAutoComInit::~CAutoComInit(void)
0x18001a8ae  mov     eax, dword ptr [rsp+0A8h+var_78]
0x18001a8b2  add     rsp, 70h
0x18001a8b6  pop     r15
0x18001a8b8  pop     r14
0x18001a8ba  pop     r13
0x18001a8bc  pop     r12
0x18001a8be  pop     rdi
0x18001a8bf  pop     rsi
0x18001a8c0  pop     rbx
0x18001a8c1  retn
```
