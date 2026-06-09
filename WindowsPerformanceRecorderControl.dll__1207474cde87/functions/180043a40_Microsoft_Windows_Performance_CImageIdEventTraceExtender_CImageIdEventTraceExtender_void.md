# Microsoft::Windows::Performance::CImageIdEventTraceExtender::CImageIdEventTraceExtender(void)

- ea: `0x180043a40`
- end: `0x180043f0a`
- name: `??0CImageIdEventTraceExtender@Performance@Windows@Microsoft@@QEAA@XZ`
- size: `1226`
- prototype: `Microsoft::Windows::Performance::CImageIdEventTraceExtender *__fastcall(Microsoft::Windows::Performance::CImageIdEventTraceExtender *this)`
- caller_count: `1`
- callee_count: `33`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180077d14`

## callees

- `0x180008330`
- `0x1800102a0`
- `0x1800103c0`
- `0x1800131a0`
- `0x180016480`
- `0x18001719c`
- `0x18001c820`
- `0x18001d8fc`
- `0x180021018`
- `0x1800263c0`
- `0x180026410`
- `0x18002a6b4`
- `0x18002c3b0`
- `0x180035760`
- `0x1800359c8`
- `0x180043a40`
- `0x180044210`
- `0x18004aaa4`
- `0x18004b4c0`
- `0x18004d838`
- `0x18004ece0`
- `0x18005a604`
- `0x1800772f0`
- `0x18007740c`
- `0x1800774cc`
- `0x1800774ec`
- `0x180077c98`
- `0x180078048`
- `0x180078280`
- `0x180078c40`
- `0x180079ed4`
- `0x180079f98`
- `0x18008c010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleW` at `0x180043ad7`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleW` at `0x180043ad7`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180043aec`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180043aec`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180043d90`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180043d90`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x180043e04`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x180043e41`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x180043e04`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x180043e41`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemWindowsDirectoryW` at `0x180043d86`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemWindowsDirectoryW` at `0x180043d86`

## string_xrefs

- `0x180043ad0`: `ntdll.dll`
- `0x180043c3d`: `XPERF_EmbeddedPdbPath`
- `0x180043c68`: `_NT_SYMBOL_PATH`

## pseudocode

```c
Microsoft::Windows::Performance::CImageIdEventTraceExtender *__fastcall Microsoft::Windows::Performance::CImageIdEventTraceExtender::CImageIdEventTraceExtender(
        Microsoft::Windows::Performance::CImageIdEventTraceExtender *this)
{
  HMODULE ModuleHandleW; // rax
  FARPROC ProcAddress; // rax
  bool v4; // al
  LPCWSTR *v5; // r14
  unsigned int v6; // edx
  __int64 v7; // rdx
  __int64 v8; // rbx
  int v9; // edi
  __int64 v10; // rdx
  signed int LastError; // eax
  unsigned __int64 v12; // rax
  DWORD FullPathNameW; // eax
  DWORD v14; // ebx
  WCHAR *v15; // rax
  __int64 Manager; // rdx
  __int64 v18; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v19[8]; // [rsp+38h] [rbp-C8h] BYREF
  int v20; // [rsp+40h] [rbp-C0h]
  __int64 v21; // [rsp+48h] [rbp-B8h] BYREF
  __int128 v22; // [rsp+50h] [rbp-B0h] BYREF
  int v23; // [rsp+60h] [rbp-A0h] BYREF
  __int128 v24; // [rsp+68h] [rbp-98h] BYREF
  __int64 v25; // [rsp+78h] [rbp-88h]
  int v26; // [rsp+80h] [rbp-80h]
  __int64 v27; // [rsp+88h] [rbp-78h]
  int v28; // [rsp+90h] [rbp-70h]
  __int64 v29; // [rsp+98h] [rbp-68h]
  Microsoft::Windows::Performance::CImageIdEventTraceExtender *v30; // [rsp+A0h] [rbp-60h]
  _BYTE v31[80]; // [rsp+B0h] [rbp-50h] BYREF
  WCHAR Buffer[264]; // [rsp+100h] [rbp+0h] BYREF

  v29 = -2;
  v30 = this;
  v20 = 0;
  *((_DWORD *)this + 6) = 0;
  *((_QWORD *)this + 1) = 0;
  *((_QWORD *)this + 2) = 0;
  *(_QWORD *)this = &Microsoft::Windows::Performance::CImageIdEventTraceExtender::`vftable';
  *((_DWORD *)this + 8) = 0;
  *((_QWORD *)this + 5) = 0;
  *((_DWORD *)this + 12) = 0;
  *((_QWORD *)this + 7) = 0;
  Performance::NtImagePathDecoder::CLocalNtImagePathDecoder::CLocalNtImagePathDecoder((Microsoft::Windows::Performance::CImageIdEventTraceExtender *)((char *)this + 64));
  *((_QWORD *)this + 23) = 0;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>((char *)this + 192);
  *((_WORD *)this + 100) = 0;
  ModuleHandleW = GetModuleHandleW(L"ntdll.dll");
  v4 = 0;
  if ( ModuleHandleW )
  {
    ProcAddress = GetProcAddress(ModuleHandleW, "RtlGetDeviceFamilyInfoEnum");
    if ( ProcAddress )
    {
      LODWORD(v18) = 0;
      ((void (__fastcall *)(_QWORD, __int64 *, _QWORD))ProcAddress)(0, &v18, 0);
      if ( (_DWORD)v18 == 5 || (unsigned int)(v18 - 11) <= 1 )
        v4 = 1;
    }
  }
  *((_BYTE *)this + 202) = v4;
  *(_QWORD *)&v22 = (char *)this + 208;
  *((_QWORD *)this + 26) = 0;
  *((_QWORD *)this + 27) = 0;
  std::list<Microsoft::Windows::Performance::CCvDDCache::CCvDD>::_Alloc_sentinel_and_proxy((char *)this + 208);
  *((_QWORD *)this + 28) = 0;
  *((_QWORD *)this + 29) = 0;
  std::_Tree<std::_Tmap_traits<WindowsPerformanceRecorder::Impl::CFileKey,WindowsPerformanceRecorder::CBaseProfileElement::CBaseProfileElementCollection *,std::less<WindowsPerformanceRecorder::Impl::CFileKey>,std::allocator<std::pair<WindowsPerformanceRecorder::Impl::CFileKey const,WindowsPerformanceRecorder::CBaseProfileElement::CBaseProfileElementCollection *>>,0>>::_Alloc_sentinel_and_proxy();
  std::map<unsigned short const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<unsigned short const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>::map<unsigned short const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<unsigned short const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>((char *)this + 240);
  *((_QWORD *)this + 32) = 0;
  *((_QWORD *)this + 33) = 0;
  std::_Tree<std::_Tset_traits<WindowsPerformanceRecorder::CTraceMergePropertyElement::CCustomEvent const *,std::less<WindowsPerformanceRecorder::CTraceMergePropertyElement::CCustomEvent const *>,std::allocator<WindowsPerformanceRecorder::CTraceMergePropertyElement::CCustomEvent const *>,0>>::_Alloc_sentinel_and_proxy();
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>((char *)this + 272);
  *((_QWORD *)this + 35) = 0;
  *((_DWORD *)this + 72) = 0;
  *((_BYTE *)this + 296) = 0;
  *((_QWORD *)this + 38) = 0;
  *((_QWORD *)this + 39) = 0;
  *((_QWORD *)this + 40) = 0;
  v5 = (LPCWSTR *)((char *)this + 328);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>((char *)this + 328);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>((char *)this + 336);
  *((_QWORD *)this + 43) = 0;
  *((_QWORD *)this + 44) = 0;
  *((_QWORD *)this + 45) = 0;
  *((_QWORD *)this + 46) = 0;
  Microsoft::Windows::Performance::CErrorEvent::CErrorEvent(
    (Microsoft::Windows::Performance::CImageIdEventTraceExtender *)((char *)this + 376),
    v6);
  if ( !(unsigned __int8)ATL::CAutoVectorPtr<_CVDD>::Allocate((char *)this + 344, 2)
    || !(unsigned __int8)ATL::CAutoVectorPtr<unsigned long>::Allocate((char *)this + 352, 2)
    || !(unsigned __int8)ATL::CAutoVectorPtr<unsigned __int64>::Allocate((char *)this + 360, 2) )
  {
    ATL::AtlThrowImpl(-2147024882);
  }
  *((_DWORD *)this + 92) = 2;
  if ( !(unsigned int)ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::GetEnvironmentVariableW(
                        (char *)this + 328,
                        L"XPERF_EmbeddedPdbPath")
    || !*((_DWORD *)*v5 - 4) )
  {
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(v19);
    if ( (unsigned int)ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::GetEnvironmentVariableW(
                         v19,
                         L"_NT_SYMBOL_PATH") )
    {
      v24 = 0;
      v25 = 0;
      v26 = 0;
      v27 = 0;
      v28 = 1;
      v23 = 0;
      if ( (unsigned int)ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::Parse(&v23) )
        ATL::AtlThrowImpl(-2147024882);
      ATL::CAtlREMatchContext<ATL::CAtlRECharTraitsW>::CAtlREMatchContext<ATL::CAtlRECharTraitsW>(v31);
      LODWORD(v18) = 0;
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(&v21);
      while ( 1 )
      {
        v7 = ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Tokenize(
               v19,
               &v22);
        ATL::CSimpleStringT<unsigned short,0>::operator=(&v21, v7);
        v8 = v21;
        v9 = *(_DWORD *)(v21 - 16);
        WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo((WindowsPerformanceRecorder::Status::CSessionInfo *)&v22);
        if ( !v9 )
          break;
        if ( (unsigned int)ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::Match(&v23, v8, v31, 0) )
        {
          v22 = 0;
          ATL::CAtlREMatchContext<ATL::CAtlRECharTraitsW>::GetMatch(v31, v10, &v22);
          ATL::CSimpleStringT<unsigned short,0>::SetString(
            (__int64 *)this + 41,
            (const void *)v22,
            (__int64)(*((_QWORD *)&v22 + 1) - v22) >> 1);
          break;
        }
      }
      WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo((WindowsPerformanceRecorder::Status::CSessionInfo *)&v21);
      ATL::CAtlREMatchContext<ATL::CAtlRECharTraitsW>::~CAtlREMatchContext<ATL::CAtlRECharTraitsW>(v31);
      ATL::CAtlArray<ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::INSTRUCTION,ATL::CElementTraits<ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::INSTRUCTION>>::~CAtlArray<ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::INSTRUCTION,ATL::CElementTraits<ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::INSTRUCTION>>(&v24);
    }
    if ( !*((_DWORD *)*v5 - 4) )
    {
      if ( !GetSystemWindowsDirectoryW(Buffer, 0x105u) )
      {
        LastError = GetLastError();
        if ( LastError > 0 )
          LastError = (unsigned __int16)LastError | 0x80070000;
        ATL::AtlThrowImpl(LastError);
      }
      v12 = -1;
      do
        ++v12;
      while ( Buffer[v12] );
      if ( v12 < 2 || Buffer[1] != 58 )
        ATL::AtlThrowImpl(-2147418113);
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Format(
        (char *)this + 328,
        L"%wc:\\Symbols",
        Buffer[0]);
    }
    WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo((WindowsPerformanceRecorder::Status::CSessionInfo *)v19);
  }
  if ( *((_DWORD *)*v5 - 4) )
  {
    FullPathNameW = GetFullPathNameW(*v5, 0, 0, 0);
    if ( FullPathNameW )
    {
      v14 = FullPathNameW + 1;
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(&v18);
      ATL::CSimpleStringT<unsigned short,0>::PrepareWrite(&v18, v14);
      v15 = (WCHAR *)ATL::CSimpleStringT<unsigned short,0>::GetBuffer(&v18);
      if ( GetFullPathNameW(*v5, v14, v15, 0) )
      {
        ATL::CSimpleStringT<unsigned short,0>::ReleaseBuffer(&v18);
        if ( (unsigned __int16)ATL::CSimpleStringT<unsigned short,0>::GetAt(&v18) != 92 )
        {
          Manager = ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::GetManager(&v18);
          ATL::CSimpleStringT<unsigned short,0>::CSimpleStringT<unsigned short,0>(v19, Manager);
          v20 = 1;
          ATL::CSimpleStringT<unsigned short,0>::Concatenate(v19, L"\\\\?\\", 4);
          ATL::CSimpleStringT<unsigned short,0>::operator=((char *)this + 328, v19);
          WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo((WindowsPerformanceRecorder::Status::CSessionInfo *)v19);
        }
      }
      WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo((WindowsPerformanceRecorder::Status::CSessionInfo *)&v18);
    }
  }
  return this;
}

```

## disassembly

```asm
0x180043a40  push    rbp
0x180043a42  push    rbx
0x180043a43  push    rsi
0x180043a44  push    rdi
0x180043a45  push    r12
0x180043a47  push    r13
0x180043a49  push    r14
0x180043a4b  push    r15
0x180043a4d  lea     rbp, [rsp-228h]
0x180043a55  sub     rsp, 328h
0x180043a5c  mov     [rbp+260h+var_2C8], 0FFFFFFFFFFFFFFFEh
0x180043a64  mov     rax, cs:__security_cookie
0x180043a6b  xor     rax, rsp
0x180043a6e  mov     [rbp+260h+var_50], rax
0x180043a75  mov     rsi, rcx
0x180043a78  mov     [rbp+260h+var_2C0], rcx
0x180043a7c  xor     r12d, r12d
0x180043a7f  mov     [rsp+360h+var_320], r12d
0x180043a84  mov     [rcx+18h], r12d
0x180043a88  mov     [rcx+8], r12
0x180043a8c  mov     [rcx+10h], r12
0x180043a90  lea     rax, ??_7CImageIdEventTraceExtender@Performance@Windows@Microsoft@@6B@; const Microsoft::Windows::Performance::CImageIdEventTraceExtender::`vftable'
0x180043a97  mov     [rcx], rax
0x180043a9a  mov     [rcx+20h], r12d
0x180043a9e  mov     [rcx+28h], r12
0x180043aa2  mov     [rcx+30h], r12d
0x180043aa6  mov     [rcx+38h], r12
0x180043aaa  add     rcx, 40h ; '@'; this
0x180043aae  call    ??0CLocalNtImagePathDecoder@NtImagePathDecoder@Performance@@QEAA@XZ; Performance::NtImagePathDecoder::CLocalNtImagePathDecoder::CLocalNtImagePathDecoder(void)
0x180043ab3  nop
0x180043ab4  mov     [rsi+0B8h], r12
0x180043abb  lea     rcx, [rsi+0C0h]; void *
0x180043ac2  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x180043ac7  nop
0x180043ac8  mov     [rsi+0C8h], r12w
0x180043ad0  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x180043ad7  call    cs:__imp_GetModuleHandleW
0x180043add  test    rax, rax
0x180043ae0  jz      short loc_180043B20
0x180043ae2  lea     rdx, aRtlgetdevicefa; "RtlGetDeviceFamilyInfoEnum"
0x180043ae9  mov     rcx, rax; hModule
0x180043aec  call    cs:__imp_GetProcAddress
0x180043af2  test    rax, rax
0x180043af5  jz      short loc_180043B20
0x180043af7  mov     dword ptr [rsp+360h+var_330], r12d
0x180043afc  xor     r8d, r8d
0x180043aff  lea     rdx, [rsp+360h+var_330]
0x180043b04  xor     ecx, ecx
0x180043b06  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043b0b  mov     eax, dword ptr [rsp+360h+var_330]
0x180043b0f  cmp     eax, 5
0x180043b12  jz      short loc_180043B1C
0x180043b14  add     eax, 0FFFFFFF5h
0x180043b17  cmp     eax, 1
0x180043b1a  ja      short loc_180043B20
0x180043b1c  mov     al, 1
0x180043b1e  jmp     short loc_180043B23
0x180043b20  mov     al, r12b
0x180043b23  mov     [rsi+0CAh], al
0x180043b29  lea     rbx, [rsi+0D0h]
0x180043b30  mov     qword ptr [rsp+360h+var_310], rbx
0x180043b35  mov     [rbx], r12
0x180043b38  mov     [rbx+8], r12
0x180043b3c  mov     rcx, rbx
0x180043b3f  call    ?_Alloc_sentinel_and_proxy@?$list@UCCvDD@CCvDDCache@Performance@Windows@Microsoft@@V?$allocator@UCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@AEAAXXZ; std::list<Microsoft::Windows::Performance::CCvDDCache::CCvDD>::_Alloc_sentinel_and_proxy(void)
0x180043b44  nop
0x180043b45  lea     rcx, [rbx+10h]
0x180043b49  mov     [rcx], r12
0x180043b4c  mov     [rcx+8], r12
0x180043b50  call    ?_Alloc_sentinel_and_proxy@?$_Tree@V?$_Tmap_traits@UCFileKey@Impl@WindowsPerformanceRecorder@@PEAUCBaseProfileElementCollection@CBaseProfileElement@3@U?$less@UCFileKey@Impl@WindowsPerformanceRecorder@@@std@@V?$allocator@U?$pair@$$CBUCFileKey@Impl@WindowsPerformanceRecorder@@PEAUCBaseProfileElementCollection@CBaseProfileElement@3@@std@@@7@$0A@@std@@@std@@IEAAXXZ; std::_Tree<std::_Tmap_traits<WindowsPerformanceRecorder::Impl::CFileKey,WindowsPerformanceRecorder::CBaseProfileElement::CBaseProfileElementCollection *,std::less<WindowsPerformanceRecorder::Impl::CFileKey>,std::allocator<std::pair<WindowsPerformanceRecorder::Impl::CFileKey const,WindowsPerformanceRecorder::CBaseProfileElement::CBaseProfileElementCollection *>>,0>>::_Alloc_sentinel_and_proxy(void)
0x180043b55  nop
0x180043b56  lea     rcx, [rbx+20h]
0x180043b5a  call    ??0?$map@PEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@UlessLPCWSTR_ci@2345@V?$allocator@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@@std@@QEAA@XZ; std::map<ushort const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>::map<ushort const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>(void)
0x180043b5f  nop
0x180043b60  lea     rcx, [rbx+30h]
0x180043b64  mov     [rcx], r12
0x180043b67  mov     [rcx+8], r12
0x180043b6b  call    ?_Alloc_sentinel_and_proxy@?$_Tree@V?$_Tset_traits@PEBUCCustomEvent@CTraceMergePropertyElement@WindowsPerformanceRecorder@@U?$less@PEBUCCustomEvent@CTraceMergePropertyElement@WindowsPerformanceRecorder@@@std@@V?$allocator@PEBUCCustomEvent@CTraceMergePropertyElement@WindowsPerformanceRecorder@@@5@$0A@@std@@@std@@IEAAXXZ; std::_Tree<std::_Tset_traits<WindowsPerformanceRecorder::CTraceMergePropertyElement::CCustomEvent const *,std::less<WindowsPerformanceRecorder::CTraceMergePropertyElement::CCustomEvent const *>,std::allocator<WindowsPerformanceRecorder::CTraceMergePropertyElement::CCustomEvent const *>,0>>::_Alloc_sentinel_and_proxy(void)
0x180043b70  nop
0x180043b71  lea     rcx, [rsi+110h]; void *
0x180043b78  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x180043b7d  nop
0x180043b7e  mov     [rsi+118h], r12
0x180043b85  mov     [rsi+120h], r12d
0x180043b8c  mov     [rsi+128h], r12b
0x180043b93  mov     [rsi+130h], r12
0x180043b9a  mov     [rsi+138h], r12
0x180043ba1  mov     [rsi+140h], r12
0x180043ba8  lea     r14, [rsi+148h]
0x180043baf  mov     rcx, r14; void *
0x180043bb2  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x180043bb7  nop
0x180043bb8  lea     rcx, [rsi+150h]; void *
0x180043bbf  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x180043bc4  nop
0x180043bc5  lea     rbx, [rsi+158h]
0x180043bcc  mov     [rbx], r12
0x180043bcf  lea     rdi, [rsi+160h]
0x180043bd6  mov     [rdi], r12
0x180043bd9  lea     r15, [rsi+168h]
0x180043be0  mov     [r15], r12
0x180043be3  mov     [rsi+170h], r12
0x180043bea  lea     rcx, [rsi+178h]; this
0x180043bf1  call    ??0CErrorEvent@Performance@Windows@Microsoft@@QEAA@K@Z; Microsoft::Windows::Performance::CErrorEvent::CErrorEvent(ulong)
0x180043bf6  nop
0x180043bf7  mov     r13d, 2
0x180043bfd  mov     edx, r13d
0x180043c00  mov     rcx, rbx
0x180043c03  call    ?Allocate@?$CAutoVectorPtr@T_CVDD@@@ATL@@QEAA_N_K@Z; ATL::CAutoVectorPtr<_CVDD>::Allocate(unsigned __int64)
0x180043c08  test    al, al
0x180043c0a  jz      loc_180043EFF
0x180043c10  mov     edx, r13d
0x180043c13  mov     rcx, rdi
0x180043c16  call    ?Allocate@?$CAutoVectorPtr@K@ATL@@QEAA_N_K@Z; ATL::CAutoVectorPtr<ulong>::Allocate(unsigned __int64)
0x180043c1b  test    al, al
0x180043c1d  jz      loc_180043EFF
0x180043c23  mov     edx, r13d
0x180043c26  mov     rcx, r15
0x180043c29  call    ?Allocate@?$CAutoVectorPtr@_K@ATL@@QEAA_N_K@Z; ATL::CAutoVectorPtr<unsigned __int64>::Allocate(unsigned __int64)
0x180043c2e  test    al, al
0x180043c30  jz      loc_180043EFF
0x180043c36  mov     [rsi+170h], r13d
0x180043c3d  lea     rdx, aXperfEmbeddedp; "XPERF_EmbeddedPdbPath"
0x180043c44  mov     rcx, r14
0x180043c47  call    ?GetEnvironmentVariableW@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAHPEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::GetEnvironmentVariableW(ushort const *)
0x180043c4c  test    eax, eax
0x180043c4e  jz      short loc_180043C5D
0x180043c50  mov     rax, [r14]
0x180043c53  cmp     [rax-10h], r12d
0x180043c57  jnz     loc_180043DEF
0x180043c5d  lea     rcx, [rsp+360h+var_328]; void *
0x180043c62  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x180043c67  nop
0x180043c68  lea     rdx, aNtSymbolPath; "_NT_SYMBOL_PATH"
0x180043c6f  lea     rcx, [rsp+360h+var_328]
0x180043c74  call    ?GetEnvironmentVariableW@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAHPEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::GetEnvironmentVariableW(ushort const *)
0x180043c79  test    eax, eax
0x180043c7b  jz      loc_180043D74
0x180043c81  xorps   xmm0, xmm0
0x180043c84  movdqu  [rsp+360h+var_2F8], xmm0
0x180043c8a  mov     [rsp+360h+var_2E8], r12
0x180043c8f  mov     [rbp+260h+var_2E0], r12d
0x180043c93  mov     [rbp+260h+var_2D8], r12
0x180043c97  mov     [rbp+260h+var_2D0], 1
0x180043c9e  mov     [rsp+360h+var_300], r12d
0x180043ca3  lea     rcx, [rsp+360h+var_300]
0x180043ca8  call    ?Parse@?$CAtlRegExp@VCAtlRECharTraitsW@ATL@@@ATL@@QEAA?AW4REParseError@2@PEBGH@Z; ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::Parse(ushort const *,int)
0x180043cad  test    eax, eax
0x180043caf  jz      short loc_180043CBC
0x180043cb1  mov     ecx, 8007000Eh; int
0x180043cb6  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180043cbc  lea     rcx, [rbp+260h+var_2B0]
0x180043cc0  call    ??0?$CAtlREMatchContext@VCAtlRECharTraitsW@ATL@@@ATL@@QEAA@_K@Z; ATL::CAtlREMatchContext<ATL::CAtlRECharTraitsW>::CAtlREMatchContext<ATL::CAtlRECharTraitsW>(unsigned __int64)
0x180043cc5  nop
0x180043cc6  mov     dword ptr [rsp+360h+var_330], r12d
0x180043ccb  lea     rcx, [rsp+360h+var_318]; void *
0x180043cd0  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x180043cd5  nop
0x180043cd6  lea     r9, [rsp+360h+var_330]
0x180043cdb  lea     rdx, [rsp+360h+var_310]; void *
0x180043ce0  lea     rcx, [rsp+360h+var_328]; void *
0x180043ce5  call    ?Tokenize@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEBA?AV12@PEBGAEAH@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Tokenize(ushort const *,int &)
0x180043cea  nop
0x180043ceb  mov     rdx, rax
0x180043cee  lea     rcx, [rsp+360h+var_318]
0x180043cf3  call    ??4?$CSimpleStringT@G$0A@@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CSimpleStringT<ushort,0>::operator=(ATL::CSimpleStringT<ushort,0> const &)
0x180043cf8  mov     rbx, [rsp+360h+var_318]
0x180043cfd  mov     edi, [rbx-10h]
0x180043d00  lea     rcx, [rsp+360h+var_310]; this
0x180043d05  call    ??1CSessionInfo@Status@WindowsPerformanceRecorder@@QEAA@XZ; WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo(void)
0x180043d0a  test    edi, edi
0x180043d0c  jz      short loc_180043D55
0x180043d0e  xor     r9d, r9d
0x180043d11  lea     r8, [rbp+260h+var_2B0]
0x180043d15  mov     rdx, rbx
0x180043d18  lea     rcx, [rsp+360h+var_300]
0x180043d1d  call    ?Match@?$CAtlRegExp@VCAtlRECharTraitsW@ATL@@@ATL@@QEAAHPEBGPEAV?$CAtlREMatchContext@VCAtlRECharTraitsW@ATL@@@2@PEAPEBG@Z; ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::Match(ushort const *,ATL::CAtlREMatchContext<ATL::CAtlRECharTraitsW> *,ushort const * *)
0x180043d22  test    eax, eax
0x180043d24  jz      short loc_180043CD6
0x180043d26  xorps   xmm0, xmm0
0x180043d29  movups  [rsp+360h+var_310], xmm0
0x180043d2e  lea     r8, [rsp+360h+var_310]
0x180043d33  lea     rcx, [rbp+260h+var_2B0]
0x180043d37  call    ?GetMatch@?$CAtlREMatchContext@VCAtlRECharTraitsW@ATL@@@ATL@@QEAAXIPEAUMatchGroup@12@@Z; ATL::CAtlREMatchContext<ATL::CAtlRECharTraitsW>::GetMatch(uint,ATL::CAtlREMatchContext<ATL::CAtlRECharTraitsW>::MatchGroup *)
0x180043d3c  mov     r8, qword ptr [rsp+360h+var_310+8]
0x180043d41  mov     rdx, qword ptr [rsp+360h+var_310]
0x180043d46  sub     r8, rdx
0x180043d49  sar     r8, 1
0x180043d4c  mov     rcx, r14
0x180043d4f  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x180043d54  nop
0x180043d55  lea     rcx, [rsp+360h+var_318]; this
0x180043d5a  call    ??1CSessionInfo@Status@WindowsPerformanceRecorder@@QEAA@XZ; WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo(void)
0x180043d5f  nop
0x180043d60  lea     rcx, [rbp+260h+var_2B0]
0x180043d64  call    ??1?$CAtlREMatchContext@VCAtlRECharTraitsW@ATL@@@ATL@@QEAA@XZ; ATL::CAtlREMatchContext<ATL::CAtlRECharTraitsW>::~CAtlREMatchContext<ATL::CAtlRECharTraitsW>(void)
0x180043d69  nop
0x180043d6a  lea     rcx, [rsp+360h+var_2F8]
0x180043d6f  call    ??1?$CAtlArray@UINSTRUCTION@?$CAtlRegExp@VCAtlRECharTraitsW@ATL@@@ATL@@V?$CElementTraits@UINSTRUCTION@?$CAtlRegExp@VCAtlRECharTraitsW@ATL@@@ATL@@@3@@ATL@@QEAA@XZ; ATL::CAtlArray<ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::INSTRUCTION,ATL::CElementTraits<ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::INSTRUCTION>>::~CAtlArray<ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::INSTRUCTION,ATL::CElementTraits<ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::INSTRUCTION>>(void)
0x180043d74  mov     rax, [r14]
0x180043d77  cmp     [rax-10h], r12d
0x180043d7b  jnz     short loc_180043DE5
0x180043d7d  mov     edx, 105h; uSize
0x180043d82  lea     rcx, [rbp+260h+Buffer]; lpBuffer
0x180043d86  call    cs:__imp_GetSystemWindowsDirectoryW
0x180043d8c  test    eax, eax
0x180043d8e  jnz     short loc_180043DAA
0x180043d90  call    cs:__imp_GetLastError
0x180043d96  test    eax, eax
0x180043d98  jle     short loc_180043DA2
0x180043d9a  movzx   eax, ax
0x180043d9d  or      eax, 80070000h
0x180043da2  mov     ecx, eax; int
0x180043da4  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180043daa  lea     rcx, [rbp+260h+Buffer]
0x180043dae  or      rax, 0FFFFFFFFFFFFFFFFh
0x180043db2  inc     rax
0x180043db5  cmp     [rcx+rax*2], r12w
0x180043dba  jnz     short loc_180043DB2
0x180043dbc  cmp     rax, r13
0x180043dbf  jb      loc_180043EF4
0x180043dc5  cmp     [rbp+260h+var_25E], 3Ah ; ':'
0x180043dca  jnz     loc_180043EF4
0x180043dd0  movzx   r8d, [rbp+260h+Buffer]
0x180043dd5  lea     rdx, aWcSymbols; "%wc:\\Symbols"
0x180043ddc  mov     rcx, r14
0x180043ddf  call    ?Format@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Format(ushort const *,...)
0x180043de4  nop
0x180043de5  lea     rcx, [rsp+360h+var_328]; this
0x180043dea  call    ??1CSessionInfo@Status@WindowsPerformanceRecorder@@QEAA@XZ; WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo(void)
0x180043def  mov     rcx, [r14]; lpFileName
0x180043df2  cmp     [rcx-10h], r12d
0x180043df6  jz      loc_180043ECE
0x180043dfc  xor     r9d, r9d; lpFilePart
0x180043dff  xor     r8d, r8d; lpBuffer
0x180043e02  xor     edx, edx; nBufferLength
0x180043e04  call    cs:__imp_GetFullPathNameW
0x180043e0a  test    eax, eax
0x180043e0c  jz      loc_180043ECE
0x180043e12  lea     ebx, [rax+1]
0x180043e15  lea     rcx, [rsp+360h+var_330]; void *
0x180043e1a  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x180043e1f  nop
0x180043e20  mov     edx, ebx
0x180043e22  lea     rcx, [rsp+360h+var_330]
0x180043e27  call    ?PrepareWrite@?$CSimpleStringT@G$0A@@ATL@@AEAAPEAGH@Z; ATL::CSimpleStringT<ushort,0>::PrepareWrite(int)
0x180043e2c  lea     rcx, [rsp+360h+var_330]
0x180043e31  call    ?GetBuffer@?$CSimpleStringT@G$0A@@ATL@@QEAAPEAGXZ; ATL::CSimpleStringT<ushort,0>::GetBuffer(void)
0x180043e36  xor     r9d, r9d; lpFilePart
0x180043e39  mov     r8, rax; lpBuffer
0x180043e3c  mov     edx, ebx; nBufferLength
0x180043e3e  mov     rcx, [r14]; lpFileName
0x180043e41  call    cs:__imp_GetFullPathNameW
0x180043e47  test    eax, eax
0x180043e49  jz      short loc_180043EC3
0x180043e4b  lea     rcx, [rsp+360h+var_330]
0x180043e50  call    ?ReleaseBuffer@?$CSimpleStringT@G$0A@@ATL@@QEAAXH@Z; ATL::CSimpleStringT<ushort,0>::ReleaseBuffer(int)
0x180043e55  lea     rcx, [rsp+360h+var_330]
0x180043e5a  call    ?GetAt@?$CSimpleStringT@G$0A@@ATL@@QEBAGH@Z; ATL::CSimpleStringT<ushort,0>::GetAt(int)
0x180043e5f  cmp     ax, 5Ch ; '\'
0x180043e63  jz      short loc_180043EC3
0x180043e65  lea     rcx, [rsp+360h+var_330]
0x180043e6a  call    ?GetManager@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEBAPEAUIAtlStringMgr@2@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::GetManager(void)
0x180043e6f  nop
0x180043e70  mov     rdx, rax
0x180043e73  lea     rcx, [rsp+360h+var_328]
0x180043e78  call    ??0?$CSimpleStringT@G$0A@@ATL@@QEAA@PEAUIAtlStringMgr@1@@Z; ATL::CSimpleStringT<ushort,0>::CSimpleStringT<ushort,0>(ATL::IAtlStringMgr *)
0x180043e7d  nop
0x180043e7e  mov     [rsp+360h+var_320], 1
0x180043e86  mov     r9, [rsp+360h+var_330]
0x180043e8b  mov     eax, [r9-10h]
0x180043e8f  mov     [rsp+360h+var_340], eax
0x180043e93  mov     r8d, 4
0x180043e99  lea     rdx, asc_180099DB8; "\\\\?\\"
0x180043ea0  lea     rcx, [rsp+360h+var_328]
0x180043ea5  call    ?Concatenate@?$CSimpleStringT@G$0A@@ATL@@KAXAEAV12@PEBGH1H@Z; ATL::CSimpleStringT<ushort,0>::Concatenate(ATL::CSimpleStringT<ushort,0> &,ushort const *,int,ushort const *,int)
0x180043eaa  lea     rdx, [rsp+360h+var_328]
0x180043eaf  mov     rcx, r14
0x180043eb2  call    ??4?$CSimpleStringT@G$0A@@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CSimpleStringT<ushort,0>::operator=(ATL::CSimpleStringT<ushort,0> const &)
0x180043eb7  nop
0x180043eb8  lea     rcx, [rsp+360h+var_328]; this
0x180043ebd  call    ??1CSessionInfo@Status@WindowsPerformanceRecorder@@QEAA@XZ; WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo(void)
0x180043ec2  nop
0x180043ec3  lea     rcx, [rsp+360h+var_330]; this
0x180043ec8  call    ??1CSessionInfo@Status@WindowsPerformanceRecorder@@QEAA@XZ; WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo(void)
0x180043ecd  nop
0x180043ece  mov     rax, rsi
0x180043ed1  mov     rcx, [rbp+260h+var_50]
0x180043ed8  xor     rcx, rsp; StackCookie
0x180043edb  call    __security_check_cookie
0x180043ee0  add     rsp, 328h
0x180043ee7  pop     r15
0x180043ee9  pop     r14
0x180043eeb  pop     r13
0x180043eed  pop     r12
0x180043eef  pop     rdi
0x180043ef0  pop     rsi
0x180043ef1  pop     rbx
0x180043ef2  pop     rbp
0x180043ef3  retn
  ... truncated ...
```
