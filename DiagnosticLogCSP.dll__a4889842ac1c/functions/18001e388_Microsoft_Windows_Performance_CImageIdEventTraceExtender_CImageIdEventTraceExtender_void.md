# Microsoft::Windows::Performance::CImageIdEventTraceExtender::CImageIdEventTraceExtender(void)

- ea: `0x18001e388`
- end: `0x18001eb2e`
- name: `??0CImageIdEventTraceExtender@Performance@Windows@Microsoft@@QEAA@XZ`
- size: `1958`
- prototype: `Microsoft::Windows::Performance::CImageIdEventTraceExtender *__fastcall(Microsoft::Windows::Performance::CImageIdEventTraceExtender *this)`
- caller_count: `1`
- callee_count: `22`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x1800228a4`

## callees

- `0x180001b60`
- `0x180001b84`
- `0x180001bc8`
- `0x180010db8`
- `0x18001543c`
- `0x18001562c`
- `0x18001639c`
- `0x180016440`
- `0x180018bd8`
- `0x180019260`
- `0x18001e2ec`
- `0x18001e388`
- `0x18001f65c`
- `0x1800220cc`
- `0x180022394`
- `0x1800223a4`
- `0x180022c40`
- `0x1800231dc`
- `0x180023c6c`
- `0x180024d20`
- `0x1800267d0`
- `0x180037010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001e833`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001e85e`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001e833`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001e85e`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001e485`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001e485`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001e49a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001e49a`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemWindowsDirectoryW` at `0x18001e876`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemWindowsDirectoryW` at `0x18001e876`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001eaf3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001eaf3`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x18001e8fb`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x18001e975`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x18001e8fb`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x18001e975`

## string_xrefs

- `0x18001e47e`: `ntdll.dll`
- `0x18001e675`: `XPERF_EmbeddedPdbPath`
- `0x18001e6b9`: `_NT_SYMBOL_PATH`

## pseudocode

```c
// Hidden C++ exception states: #wind=4 #try_helpers=2
Microsoft::Windows::Performance::CImageIdEventTraceExtender *__fastcall Microsoft::Windows::Performance::CImageIdEventTraceExtender::CImageIdEventTraceExtender(
        Microsoft::Windows::Performance::CImageIdEventTraceExtender *this)
{
  HMODULE ModuleHandleW; // rax
  FARPROC ProcAddress; // rax
  bool v4; // al
  _QWORD *v5; // rax
  _QWORD *v6; // rax
  _QWORD *v7; // rax
  _QWORD *v8; // rax
  LPCWSTR *v9; // rdi
  unsigned int v10; // edx
  __int64 v11; // r8
  __int64 v12; // rax
  int v13; // ebx
  char *v14; // rdx
  _QWORD *v15; // rdx
  unsigned __int64 v16; // rdx
  unsigned __int64 v17; // rax
  _QWORD *v18; // rdx
  DWORD FullPathNameW; // eax
  DWORD v20; // r14d
  __int64 v21; // rax
  WCHAR *v22; // rbx
  __int64 v24; // rax
  __int64 v25; // rcx
  __int64 v26; // rcx
  _QWORD *v27; // rdx
  signed int LastError; // eax
  __int64 v29; // [rsp+30h] [rbp-D0h] BYREF
  WCHAR *v30; // [rsp+38h] [rbp-C8h] BYREF
  int v31; // [rsp+40h] [rbp-C0h]
  __int64 v32; // [rsp+48h] [rbp-B8h] BYREF
  volatile signed __int32 *v33; // [rsp+50h] [rbp-B0h] BYREF
  int v34; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v35; // [rsp+68h] [rbp-98h]
  __int64 v36; // [rsp+70h] [rbp-90h]
  void *v37; // [rsp+78h] [rbp-88h]
  void *v38; // [rsp+80h] [rbp-80h]
  void *Block; // [rsp+88h] [rbp-78h] BYREF
  __int128 v40; // [rsp+90h] [rbp-70h]
  int v41; // [rsp+A0h] [rbp-60h]
  __int64 v42; // [rsp+A8h] [rbp-58h]
  int v43; // [rsp+B0h] [rbp-50h] BYREF
  void *v44[2]; // [rsp+B8h] [rbp-48h]
  __int64 v45; // [rsp+C8h] [rbp-38h]
  int v46; // [rsp+D0h] [rbp-30h]
  __int64 v47; // [rsp+D8h] [rbp-28h]
  int v48; // [rsp+E0h] [rbp-20h]
  Microsoft::Windows::Performance::CImageIdEventTraceExtender *v49; // [rsp+E8h] [rbp-18h]
  WCHAR Buffer[264]; // [rsp+F0h] [rbp-10h] BYREF

  v49 = this;
  v31 = 0;
  *((_DWORD *)this + 6) = 0;
  *((_QWORD *)this + 1) = 0;
  *((_QWORD *)this + 2) = 0;
  *(_QWORD *)this = &Microsoft::Windows::Performance::CImageIdEventTraceExtender::`vftable';
  *((_DWORD *)this + 8) = 0;
  *((_QWORD *)this + 5) = 0;
  *((_DWORD *)this + 12) = 0;
  *((_QWORD *)this + 7) = 0;
  *((_QWORD *)this + 8) = 0;
  *((_QWORD *)this + 9) = 0;
  *((_QWORD *)this + 10) = 0;
  *((_QWORD *)this + 11) = 0;
  *((_QWORD *)this + 12) = 0;
  *((_QWORD *)this + 13) = 0;
  *((_OWORD *)this + 7) = 0;
  *((_QWORD *)this + 16) = 0;
  *((_QWORD *)this + 17) = 7;
  *((_WORD *)this + 56) = 0;
  *((_OWORD *)this + 9) = 0;
  *((_QWORD *)this + 20) = 0;
  *((_QWORD *)this + 21) = 7;
  *((_WORD *)this + 72) = 0;
  *((_BYTE *)this + 176) = 0;
  *((_QWORD *)this + 23) = 0;
  *((_QWORD *)this + 24) = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
  *((_WORD *)this + 100) = 0;
  ModuleHandleW = GetModuleHandleW(L"ntdll.dll");
  v4 = 0;
  if ( ModuleHandleW )
  {
    ProcAddress = GetProcAddress(ModuleHandleW, "RtlGetDeviceFamilyInfoEnum");
    if ( ProcAddress )
    {
      LODWORD(v30) = 0;
      ((void (__fastcall *)(_QWORD, WCHAR **, _QWORD))ProcAddress)(0, &v30, 0);
      if ( (_DWORD)v30 == 5 || (unsigned int)((_DWORD)v30 - 11) <= 1 )
        v4 = 1;
    }
  }
  *((_BYTE *)this + 202) = v4;
  v33 = (volatile signed __int32 *)((char *)this + 208);
  *((_QWORD *)this + 26) = 0;
  *((_QWORD *)this + 27) = 0;
  v5 = operator new(0xA0u);
  *v5 = v5;
  v5[1] = v5;
  *((_QWORD *)this + 26) = v5;
  *((_QWORD *)this + 28) = 0;
  *((_QWORD *)this + 29) = 0;
  v6 = operator new(0x38u);
  *v6 = v6;
  v6[1] = v6;
  v6[2] = v6;
  *((_WORD *)v6 + 12) = 257;
  *((_QWORD *)this + 28) = v6;
  *((_QWORD *)this + 30) = 0;
  *((_QWORD *)this + 31) = 0;
  v7 = operator new(0x30u);
  *v7 = v7;
  v7[1] = v7;
  v7[2] = v7;
  *((_WORD *)v7 + 12) = 257;
  *((_QWORD *)this + 30) = v7;
  *((_QWORD *)this + 32) = 0;
  *((_QWORD *)this + 33) = 0;
  v8 = operator new(0x28u);
  *v8 = v8;
  v8[1] = v8;
  v8[2] = v8;
  *((_WORD *)v8 + 12) = 257;
  *((_QWORD *)this + 32) = v8;
  *((_QWORD *)this + 34) = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
  *((_QWORD *)this + 35) = 0;
  *((_DWORD *)this + 72) = 0;
  *((_BYTE *)this + 296) = 0;
  *((_QWORD *)this + 38) = 0;
  *((_QWORD *)this + 39) = 0;
  *((_QWORD *)this + 40) = 0;
  v9 = (LPCWSTR *)((char *)this + 328);
  *((_QWORD *)this + 41) = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
  *((_QWORD *)this + 42) = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
  *((_QWORD *)this + 43) = 0;
  *((_QWORD *)this + 44) = 0;
  *((_QWORD *)this + 45) = 0;
  *((_QWORD *)this + 46) = 0;
  Microsoft::Windows::Performance::CErrorEvent::CErrorEvent(
    (Microsoft::Windows::Performance::CImageIdEventTraceExtender *)((char *)this + 376),
    v10);
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
    || !*((_DWORD *)*v9 - 4) )
  {
    v29 = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
    if ( (unsigned int)ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::GetEnvironmentVariableW(
                         &v29,
                         L"_NT_SYMBOL_PATH") )
    {
      *(_OWORD *)v44 = 0;
      v45 = 0;
      v46 = 0;
      v47 = 0;
      v48 = 1;
      v43 = 0;
      if ( (unsigned int)ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::Parse(&v43) )
        ATL::AtlThrowImpl(-2147024882);
      v37 = 0;
      v38 = 0;
      Block = 0;
      v40 = 0;
      v41 = 0;
      v34 = 0;
      v42 = 0;
      if ( (unsigned __int8)ATL::CAtlArray<void *,ATL::CElementTraits<void *>>::GrowBuffer(&Block, 256) )
      {
        ATL::CAtlArray<void *,ATL::CElementTraits<void *>>::CallConstructors();
        *(_QWORD *)&v40 = 256;
      }
      v35 = 0;
      v36 = 0;
      LODWORD(v30) = 0;
      v32 = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
      while ( 1 )
      {
        v12 = ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Tokenize(
                &v29,
                &v33,
                v11,
                &v30);
        v13 = *(_DWORD *)(*(_QWORD *)ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::operator=(
                                       &v32,
                                       v12)
                        - 16LL);
        v14 = (char *)(v33 - 6);
        if ( _InterlockedDecrement(v33 - 2) <= 0 )
          (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v14 + 8LL))(*(_QWORD *)v14);
        if ( !v13 )
          break;
        if ( (unsigned int)ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::Match(&v43, v32, &v34, 0) )
        {
          if ( !v34 )
            ATL::AtlThrowImpl(-2147467259);
          ATL::CSimpleStringT<unsigned short,0>::SetString(
            (char *)this + 328,
            *(_QWORD *)v38,
            (__int64)(*((_QWORD *)v38 + 1) - *(_QWORD *)v38) >> 1);
          break;
        }
      }
      v15 = (_QWORD *)(v32 - 24);
      if ( _InterlockedDecrement((volatile signed __int32 *)(v32 - 24 + 16)) <= 0 )
        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v15 + 8LL))(*v15);
      if ( Block )
        free(Block);
      operator delete(v38, (unsigned __int64)v15);
      v38 = 0;
      operator delete(v37, v16);
      v37 = 0;
      if ( v44[0] )
        free(v44[0]);
    }
    if ( !*((_DWORD *)*v9 - 4) )
    {
      if ( !GetSystemWindowsDirectoryW(Buffer, 0x105u) )
      {
        LastError = GetLastError();
        if ( LastError > 0 )
          LastError = (unsigned __int16)LastError | 0x80070000;
        ATL::AtlThrowImpl(LastError);
      }
      v17 = -1;
      do
        ++v17;
      while ( Buffer[v17] );
      if ( v17 < 2 || Buffer[1] != 58 )
        ATL::AtlThrowImpl(-2147418113);
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Format(
        (char *)this + 328,
        L"%wc:\\Symbols",
        Buffer[0]);
    }
    v18 = (_QWORD *)(v29 - 24);
    if ( _InterlockedDecrement((volatile signed __int32 *)(v29 - 24 + 16)) <= 0 )
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v18 + 8LL))(*v18);
  }
  if ( *((_DWORD *)*v9 - 4) )
  {
    FullPathNameW = GetFullPathNameW(*v9, 0, 0, 0);
    if ( FullPathNameW )
    {
      v20 = FullPathNameW + 1;
      v21 = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr);
      v22 = (WCHAR *)(v21 + 24);
      v30 = (WCHAR *)(v21 + 24);
      if ( (((*(_DWORD *)(v21 + 12) - v20) | (1 - *(_DWORD *)(v21 + 16))) & 0x80000000) != 0 )
      {
        ATL::CSimpleStringT<unsigned short,0>::PrepareWrite2(&v30, v20);
        v22 = v30;
      }
      if ( *((int *)v22 - 2) > 1 )
      {
        ATL::CSimpleStringT<unsigned short,0>::Fork(&v30, *((unsigned int *)v22 - 4));
        v22 = v30;
      }
      if ( !GetFullPathNameW(*v9, v20, v22, 0) )
        goto LABEL_45;
      if ( v22 )
      {
        v24 = -1;
        do
          ++v24;
        while ( v22[v24] );
        if ( (int)v24 < 0 )
          goto LABEL_62;
      }
      else
      {
        LODWORD(v24) = 0;
      }
      if ( (int)v24 <= *((_DWORD *)v22 - 3) )
      {
        *((_DWORD *)v22 - 4) = v24;
        v22[(unsigned int)v24] = 0;
        if ( *((int *)v22 - 4) >= 0 )
        {
          if ( *v22 != 92 )
          {
            v25 = *((_QWORD *)v22 - 3);
            if ( !v25 || (v26 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v25 + 32LL))(v25)) == 0 )
              v26 = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[4])(&ATL::g_strmgr);
            if ( !v26 )
              ATL::AtlThrowImpl(-2147467259);
            v29 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v26 + 24LL))(v26) + 24;
            v31 = 1;
            ATL::CSimpleStringT<unsigned short,0>::Concatenate(
              (unsigned int)&v29,
              (unsigned int)L"\\\\?\\",
              4,
              (_DWORD)v22,
              *((_DWORD *)v22 - 4));
            ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::operator=(
              (char *)this + 328,
              &v29);
            v27 = (_QWORD *)(v29 - 24);
            if ( _InterlockedDecrement((volatile signed __int32 *)(v29 - 24 + 16)) <= 0 )
              (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v27 + 8LL))(*v27);
          }
LABEL_45:
          if ( _InterlockedDecrement((volatile signed __int32 *)v22 - 2) <= 0 )
            (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v22 - 3) + 8LL))(*((_QWORD *)v22 - 3));
          return this;
        }
      }
LABEL_62:
      ATL::AtlThrowImpl(-2147024809);
    }
  }
  return this;
}

```

## disassembly

```asm
0x18001e388  mov     [rsp-8+arg_8], rbx
0x18001e38d  mov     [rsp-8+arg_10], rsi
0x18001e392  push    rbp
0x18001e393  push    rdi
0x18001e394  push    r12
0x18001e396  push    r14
0x18001e398  push    r15
0x18001e39a  lea     rbp, [rsp-210h]
0x18001e3a2  sub     rsp, 310h
0x18001e3a9  mov     rax, cs:__security_cookie
0x18001e3b0  xor     rax, rsp
0x18001e3b3  mov     [rbp+230h+var_30], rax
0x18001e3ba  mov     rsi, rcx
0x18001e3bd  mov     [rbp+230h+var_248], rcx
0x18001e3c1  xor     r12d, r12d
0x18001e3c4  mov     [rsp+330h+var_2F0], r12d
0x18001e3c9  mov     [rcx+18h], r12d
0x18001e3cd  mov     [rcx+8], r12
0x18001e3d1  mov     [rcx+10h], r12
0x18001e3d5  lea     rax, ??_7CImageIdEventTraceExtender@Performance@Windows@Microsoft@@6B@; const Microsoft::Windows::Performance::CImageIdEventTraceExtender::`vftable'
0x18001e3dc  mov     [rcx], rax
0x18001e3df  mov     [rcx+20h], r12d
0x18001e3e3  mov     [rcx+28h], r12
0x18001e3e7  mov     [rcx+30h], r12d
0x18001e3eb  mov     [rcx+38h], r12
0x18001e3ef  mov     [rcx+40h], r12
0x18001e3f3  mov     [rcx+48h], r12
0x18001e3f7  mov     [rcx+50h], r12
0x18001e3fb  mov     [rcx+58h], r12
0x18001e3ff  mov     [rcx+60h], r12
0x18001e403  mov     [rcx+68h], r12
0x18001e407  xorps   xmm0, xmm0
0x18001e40a  movups  xmmword ptr [rcx+70h], xmm0
0x18001e40e  mov     [rcx+80h], r12
0x18001e415  lea     ecx, [r12+7]
0x18001e41a  mov     [rsi+88h], rcx
0x18001e421  mov     [rsi+70h], r12w
0x18001e426  movups  xmmword ptr [rsi+90h], xmm0
0x18001e42d  mov     [rsi+0A0h], r12
0x18001e434  mov     [rsi+0A8h], rcx
0x18001e43b  mov     [rsi+90h], r12w
0x18001e443  mov     [rsi+0B0h], r12b
0x18001e44a  mov     [rsi+0B8h], r12
0x18001e451  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x18001e458  lea     r14, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x18001e45f  mov     rcx, r14
0x18001e462  mov     rax, [rax+18h]
0x18001e466  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e46b  add     rax, 18h
0x18001e46f  mov     [rsi+0C0h], rax
0x18001e476  mov     [rsi+0C8h], r12w
0x18001e47e  lea     rcx, ModuleName; "ntdll.dll"
0x18001e485  call    cs:__imp_GetModuleHandleW
0x18001e48b  test    rax, rax
0x18001e48e  jz      short loc_18001E4CE
0x18001e490  lea     rdx, aRtlgetdevicefa; "RtlGetDeviceFamilyInfoEnum"
0x18001e497  mov     rcx, rax; hModule
0x18001e49a  call    cs:__imp_GetProcAddress
0x18001e4a0  test    rax, rax
0x18001e4a3  jz      short loc_18001E4CE
0x18001e4a5  mov     dword ptr [rsp+330h+var_2F8], r12d
0x18001e4aa  xor     r8d, r8d
0x18001e4ad  lea     rdx, [rsp+330h+var_2F8]
0x18001e4b2  xor     ecx, ecx
0x18001e4b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e4b9  mov     eax, dword ptr [rsp+330h+var_2F8]
0x18001e4bd  cmp     eax, 5
0x18001e4c0  jz      short loc_18001E4CA
0x18001e4c2  add     eax, 0FFFFFFF5h
0x18001e4c5  cmp     eax, 1
0x18001e4c8  ja      short loc_18001E4CE
0x18001e4ca  mov     al, 1
0x18001e4cc  jmp     short loc_18001E4D1
0x18001e4ce  mov     al, r12b
0x18001e4d1  mov     [rsi+0CAh], al
0x18001e4d7  lea     rdi, [rsi+0D0h]
0x18001e4de  mov     [rsp+330h+var_2E0], rdi
0x18001e4e3  mov     [rdi], r12
0x18001e4e6  mov     [rdi+8], r12
0x18001e4ea  mov     ecx, 0A0h; Size
0x18001e4ef  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001e4f4  mov     [rax], rax
0x18001e4f7  mov     [rax+8], rax
0x18001e4fb  mov     [rdi], rax
0x18001e4fe  mov     [rdi+10h], r12
0x18001e502  mov     [rdi+18h], r12
0x18001e506  mov     ecx, 38h ; '8'; Size
0x18001e50b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001e510  mov     [rax], rax
0x18001e513  mov     [rax+8], rax
0x18001e517  mov     [rax+10h], rax
0x18001e51b  mov     word ptr [rax+18h], 101h
0x18001e521  mov     [rdi+10h], rax
0x18001e525  mov     [rdi+20h], r12
0x18001e529  mov     [rdi+28h], r12
0x18001e52d  mov     ecx, 30h ; '0'; Size
0x18001e532  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001e537  mov     [rax], rax
0x18001e53a  mov     [rax+8], rax
0x18001e53e  mov     [rax+10h], rax
0x18001e542  mov     word ptr [rax+18h], 101h
0x18001e548  mov     [rdi+20h], rax
0x18001e54c  mov     [rdi+30h], r12
0x18001e550  mov     [rdi+38h], r12
0x18001e554  mov     ecx, 28h ; '('; Size
0x18001e559  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001e55e  mov     [rax], rax
0x18001e561  mov     [rax+8], rax
0x18001e565  mov     [rax+10h], rax
0x18001e569  mov     word ptr [rax+18h], 101h
0x18001e56f  mov     [rdi+30h], rax
0x18001e573  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x18001e57a  mov     rcx, r14
0x18001e57d  mov     rax, [rax+18h]
0x18001e581  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e586  add     rax, 18h
0x18001e58a  mov     [rsi+110h], rax
0x18001e591  mov     [rsi+118h], r12
0x18001e598  mov     [rsi+120h], r12d
0x18001e59f  mov     [rsi+128h], r12b
0x18001e5a6  mov     [rsi+130h], r12
0x18001e5ad  mov     [rsi+138h], r12
0x18001e5b4  mov     [rsi+140h], r12
0x18001e5bb  lea     rdi, [rsi+148h]
0x18001e5c2  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x18001e5c9  mov     rcx, r14
0x18001e5cc  mov     rax, [rax+18h]
0x18001e5d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e5d5  add     rax, 18h
0x18001e5d9  mov     [rdi], rax
0x18001e5dc  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x18001e5e3  mov     rcx, r14
0x18001e5e6  mov     rax, [rax+18h]
0x18001e5ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e5ef  add     rax, 18h
0x18001e5f3  mov     [rsi+150h], rax
0x18001e5fa  lea     rbx, [rsi+158h]
0x18001e601  mov     [rbx], r12
0x18001e604  lea     r14, [rsi+160h]
0x18001e60b  mov     [r14], r12
0x18001e60e  lea     r15, [rsi+168h]
0x18001e615  mov     [r15], r12
0x18001e618  mov     [rsi+170h], r12
0x18001e61f  lea     rcx, [rsi+178h]; this
0x18001e626  call    ??0CErrorEvent@Performance@Windows@Microsoft@@QEAA@K@Z; Microsoft::Windows::Performance::CErrorEvent::CErrorEvent(ulong)
0x18001e62b  nop
0x18001e62c  mov     edx, 2
0x18001e631  mov     rcx, rbx
0x18001e634  call    ?Allocate@?$CAutoVectorPtr@T_CVDD@@@ATL@@QEAA_N_K@Z; ATL::CAutoVectorPtr<_CVDD>::Allocate(unsigned __int64)
0x18001e639  test    al, al
0x18001e63b  jz      loc_18001EADD
0x18001e641  mov     edx, 2
0x18001e646  mov     rcx, r14
0x18001e649  call    ?Allocate@?$CAutoVectorPtr@K@ATL@@QEAA_N_K@Z; ATL::CAutoVectorPtr<ulong>::Allocate(unsigned __int64)
0x18001e64e  test    al, al
0x18001e650  jz      loc_18001EADD
0x18001e656  mov     edx, 2
0x18001e65b  mov     rcx, r15
0x18001e65e  call    ?Allocate@?$CAutoVectorPtr@_K@ATL@@QEAA_N_K@Z; ATL::CAutoVectorPtr<unsigned __int64>::Allocate(unsigned __int64)
0x18001e663  test    al, al
0x18001e665  jz      loc_18001EADD
0x18001e66b  mov     dword ptr [rsi+170h], 2
0x18001e675  lea     rdx, aXperfEmbeddedp; "XPERF_EmbeddedPdbPath"
0x18001e67c  mov     rcx, rdi
0x18001e67f  call    ?GetEnvironmentVariableW@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAHPEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::GetEnvironmentVariableW(ushort const *)
0x18001e684  or      r15, 0FFFFFFFFFFFFFFFFh
0x18001e688  test    eax, eax
0x18001e68a  jz      short loc_18001E699
0x18001e68c  mov     rax, [rdi]
0x18001e68f  cmp     [rax-10h], r12d
0x18001e693  jnz     loc_18001E8E6
0x18001e699  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x18001e6a0  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x18001e6a7  mov     rax, [rax+18h]
0x18001e6ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e6b0  add     rax, 18h
0x18001e6b4  mov     [rsp+330h+var_300], rax
0x18001e6b9  lea     rdx, aNtSymbolPath; "_NT_SYMBOL_PATH"
0x18001e6c0  lea     rcx, [rsp+330h+var_300]
0x18001e6c5  call    ?GetEnvironmentVariableW@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAHPEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::GetEnvironmentVariableW(ushort const *)
0x18001e6ca  test    eax, eax
0x18001e6cc  jz      loc_18001E864
0x18001e6d2  xorps   xmm0, xmm0
0x18001e6d5  movdqu  xmmword ptr [rbp+230h+var_278], xmm0
0x18001e6da  mov     [rbp+230h+var_268], r12
0x18001e6de  mov     [rbp+230h+var_260], r12d
0x18001e6e2  mov     [rbp+230h+var_258], r12
0x18001e6e6  mov     [rbp+230h+var_250], 1
0x18001e6ed  mov     [rbp+230h+var_280], r12d
0x18001e6f1  lea     rcx, [rbp+230h+var_280]
0x18001e6f5  call    ?Parse@?$CAtlRegExp@VCAtlRECharTraitsW@ATL@@@ATL@@QEAA?AW4REParseError@2@PEBGH@Z; ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::Parse(ushort const *,int)
0x18001e6fa  test    eax, eax
0x18001e6fc  jnz     loc_18001EAE8
0x18001e702  mov     [rsp+330h+var_2B8], r12
0x18001e707  mov     [rbp+230h+var_2B0], r12
0x18001e70b  mov     [rbp+230h+Block], r12
0x18001e70f  xorps   xmm0, xmm0
0x18001e712  movdqa  [rbp+230h+var_2A0], xmm0
0x18001e717  mov     [rbp+230h+var_290], r12d
0x18001e71b  mov     [rsp+330h+var_2D0], r12d
0x18001e720  mov     [rbp+230h+var_288], r12
0x18001e724  mov     ebx, 100h
0x18001e729  mov     edx, ebx
0x18001e72b  lea     rcx, [rbp+230h+Block]
0x18001e72f  call    ?GrowBuffer@?$CAtlArray@PEAXV?$CElementTraits@PEAX@ATL@@@ATL@@AEAA_N_K@Z; ATL::CAtlArray<void *,ATL::CElementTraits<void *>>::GrowBuffer(unsigned __int64)
0x18001e734  test    al, al
0x18001e736  jz      short loc_18001E741
0x18001e738  call    ?CallConstructors@?$CAtlArray@PEAXV?$CElementTraits@PEAX@ATL@@@ATL@@CAXPEAPEAX_K@Z; ATL::CAtlArray<void *,ATL::CElementTraits<void *>>::CallConstructors(void * *,unsigned __int64)
0x18001e73d  mov     qword ptr [rbp+230h+var_2A0], rbx
0x18001e741  mov     [rsp+330h+var_2C8], r12
0x18001e746  mov     [rsp+330h+var_2C0], r12
0x18001e74b  mov     dword ptr [rsp+330h+var_2F8], r12d
0x18001e750  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x18001e757  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x18001e75e  mov     rax, [rax+18h]
0x18001e762  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e767  add     rax, 18h
0x18001e76b  mov     [rsp+330h+var_2E8], rax
0x18001e770  lea     r9, [rsp+330h+var_2F8]
0x18001e775  lea     rdx, [rsp+330h+var_2E0]
0x18001e77a  lea     rcx, [rsp+330h+var_300]
0x18001e77f  call    ?Tokenize@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEBA?AV12@PEBGAEAH@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Tokenize(ushort const *,int &)
0x18001e784  nop
0x18001e785  mov     rdx, rax
0x18001e788  lea     rcx, [rsp+330h+var_2E8]
0x18001e78d  call    ??4?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::operator=(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x18001e792  mov     rcx, [rax]
0x18001e795  mov     ebx, [rcx-10h]
0x18001e798  mov     rdx, [rsp+330h+var_2E0]
0x18001e79d  add     rdx, 0FFFFFFFFFFFFFFE8h
0x18001e7a1  mov     eax, r15d
0x18001e7a4  lock xadd [rdx+10h], eax
0x18001e7a9  add     eax, r15d
0x18001e7ac  test    eax, eax
0x18001e7ae  jg      short loc_18001E7BF
0x18001e7b0  mov     rcx, [rdx]
0x18001e7b3  mov     rax, [rcx]
0x18001e7b6  mov     rax, [rax+8]
0x18001e7ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e7bf  test    ebx, ebx
0x18001e7c1  jz      short loc_18001E802
0x18001e7c3  xor     r9d, r9d
0x18001e7c6  lea     r8, [rsp+330h+var_2D0]
0x18001e7cb  mov     rdx, [rsp+330h+var_2E8]
0x18001e7d0  lea     rcx, [rbp+230h+var_280]
0x18001e7d4  call    ?Match@?$CAtlRegExp@VCAtlRECharTraitsW@ATL@@@ATL@@QEAAHPEBGPEAV?$CAtlREMatchContext@VCAtlRECharTraitsW@ATL@@@2@PEAPEBG@Z; ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::Match(ushort const *,ATL::CAtlREMatchContext<ATL::CAtlRECharTraitsW> *,ushort const * *)
0x18001e7d9  test    eax, eax
0x18001e7db  jz      short loc_18001E770
0x18001e7dd  cmp     [rsp+330h+var_2D0], r12d
0x18001e7e2  jbe     loc_18001EB0D
0x18001e7e8  mov     rax, [rbp+230h+var_2B0]
0x18001e7ec  mov     r8, [rax+8]
0x18001e7f0  sub     r8, [rax]
0x18001e7f3  sar     r8, 1
0x18001e7f6  mov     rdx, [rax]
0x18001e7f9  mov     rcx, rdi
0x18001e7fc  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x18001e801  nop
0x18001e802  mov     rdx, [rsp+330h+var_2E8]
0x18001e807  add     rdx, 0FFFFFFFFFFFFFFE8h
0x18001e80b  mov     eax, r15d
0x18001e80e  lock xadd [rdx+10h], eax
0x18001e813  add     eax, r15d
0x18001e816  test    eax, eax
0x18001e818  jg      short loc_18001E82A
0x18001e81a  mov     rcx, [rdx]
0x18001e81d  mov     rax, [rcx]
0x18001e820  mov     rax, [rax+8]
0x18001e824  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e829  nop
0x18001e82a  mov     rcx, [rbp+230h+Block]; Block
0x18001e82e  test    rcx, rcx
0x18001e831  jz      short loc_18001E839
0x18001e833  call    cs:__imp_free
0x18001e839  mov     rcx, [rbp+230h+var_2B0]; void *
0x18001e83d  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001e842  mov     [rbp+230h+var_2B0], r12
0x18001e846  mov     rcx, [rsp+330h+var_2B8]; void *
0x18001e84b  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001e850  mov     [rsp+330h+var_2B8], r12
0x18001e855  mov     rcx, [rbp+230h+var_278]; Block
0x18001e859  test    rcx, rcx
0x18001e85c  jz      short loc_18001E864
0x18001e85e  call    cs:__imp_free
0x18001e864  mov     rax, [rdi]
0x18001e867  cmp     [rax-10h], r12d
0x18001e86b  jnz     short loc_18001E8BF
0x18001e86d  mov     edx, 105h; uSize
0x18001e872  lea     rcx, [rbp+230h+Buffer]; lpBuffer
0x18001e876  call    cs:__imp_GetSystemWindowsDirectoryW
0x18001e87c  test    eax, eax
0x18001e87e  jz      loc_18001EAF3
0x18001e884  lea     rcx, [rbp+230h+Buffer]
0x18001e888  mov     rax, r15
0x18001e88b  inc     rax
0x18001e88e  cmp     [rcx+rax*2], r12w
0x18001e893  jnz     short loc_18001E88B
0x18001e895  cmp     rax, 2
0x18001e899  jb      loc_18001EB18
0x18001e89f  cmp     [rbp+230h+var_23E], 3Ah ; ':'
  ... truncated ...
```
