# Microsoft::Windows::Performance::CImageIdEventTraceExtender::CImageIdEventTraceExtender(void)

- ea: `0x18000d770`
- end: `0x18000df0e`
- name: `??0CImageIdEventTraceExtender@Performance@Windows@Microsoft@@QEAA@XZ`
- size: `1950`
- prototype: `Microsoft::Windows::Performance::CImageIdEventTraceExtender *__fastcall(Microsoft::Windows::Performance::CImageIdEventTraceExtender *this)`
- caller_count: `1`
- callee_count: `22`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x180011c74`

## callees

- `0x180001870`
- `0x180001894`
- `0x1800018a0`
- `0x180003bb8`
- `0x18000439c`
- `0x18000458c`
- `0x180005304`
- `0x1800053a8`
- `0x180007724`
- `0x180007da8`
- `0x18000d6d4`
- `0x18000d770`
- `0x18000ea38`
- `0x1800114bc`
- `0x180011764`
- `0x180011774`
- `0x180012058`
- `0x1800125f8`
- `0x180013088`
- `0x180013e40`
- `0x18001578c`
- `0x18002a010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000dc1a`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000dc47`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000dc1a`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000dc47`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ded3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ded3`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemWindowsDirectoryW` at `0x18000dc5f`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemWindowsDirectoryW` at `0x18000dc5f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000d868`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000d868`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000d87d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000d87d`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x18000dce4`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x18000dd5e`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x18000dce4`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x18000dd5e`

## string_xrefs

- `0x18000d861`: `ntdll.dll`
- `0x18000da58`: `XPERF_EmbeddedPdbPath`
- `0x18000da9c`: `_NT_SYMBOL_PATH`

## pseudocode

```c
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
  unsigned __int64 v16; // rax
  _QWORD *v17; // rdx
  DWORD FullPathNameW; // eax
  DWORD v19; // r14d
  __int64 v20; // rax
  WCHAR *v21; // rbx
  __int64 v23; // rax
  __int64 v24; // rcx
  __int64 v25; // rcx
  _QWORD *v26; // rdx
  signed int LastError; // eax
  __int64 v28; // [rsp+30h] [rbp-D0h] BYREF
  WCHAR *v29; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v30; // [rsp+40h] [rbp-C0h] BYREF
  volatile signed __int32 *v31; // [rsp+48h] [rbp-B8h] BYREF
  int v32; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v33; // [rsp+58h] [rbp-A8h]
  __int64 v34; // [rsp+60h] [rbp-A0h]
  void *v35; // [rsp+68h] [rbp-98h]
  void *v36; // [rsp+70h] [rbp-90h]
  void *Block; // [rsp+78h] [rbp-88h] BYREF
  __int128 v38; // [rsp+80h] [rbp-80h]
  int v39; // [rsp+90h] [rbp-70h]
  __int64 v40; // [rsp+98h] [rbp-68h]
  int v41; // [rsp+A0h] [rbp-60h] BYREF
  void *v42[2]; // [rsp+A8h] [rbp-58h]
  __int64 v43; // [rsp+B8h] [rbp-48h]
  int v44; // [rsp+C0h] [rbp-40h]
  __int64 v45; // [rsp+C8h] [rbp-38h]
  int v46; // [rsp+D0h] [rbp-30h]
  Microsoft::Windows::Performance::CImageIdEventTraceExtender *v47; // [rsp+D8h] [rbp-28h]
  WCHAR Buffer[264]; // [rsp+E0h] [rbp-20h] BYREF

  v47 = this;
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
      LODWORD(v29) = 0;
      ((void (__fastcall *)(_QWORD, WCHAR **, _QWORD))ProcAddress)(0, &v29, 0);
      if ( (_DWORD)v29 == 5 || (unsigned int)((_DWORD)v29 - 11) <= 1 )
        v4 = 1;
    }
  }
  *((_BYTE *)this + 202) = v4;
  v31 = (volatile signed __int32 *)((char *)this + 208);
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
    v28 = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
    if ( (unsigned int)ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::GetEnvironmentVariableW(
                         &v28,
                         L"_NT_SYMBOL_PATH") )
    {
      *(_OWORD *)v42 = 0;
      v43 = 0;
      v44 = 0;
      v45 = 0;
      v46 = 1;
      v41 = 0;
      if ( (unsigned int)ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::Parse(&v41) )
        ATL::AtlThrowImpl(-2147024882);
      v35 = 0;
      v36 = 0;
      Block = 0;
      v38 = 0;
      v39 = 0;
      v32 = 0;
      v40 = 0;
      if ( (unsigned __int8)ATL::CAtlArray<void *,ATL::CElementTraits<void *>>::GrowBuffer(&Block, 256) )
      {
        ATL::CAtlArray<void *,ATL::CElementTraits<void *>>::CallConstructors();
        *(_QWORD *)&v38 = 256;
      }
      v33 = 0;
      v34 = 0;
      LODWORD(v29) = 0;
      v30 = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
      while ( 1 )
      {
        v12 = ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Tokenize(
                &v28,
                &v31,
                v11,
                &v29);
        v13 = *(_DWORD *)(*(_QWORD *)ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::operator=(
                                       &v30,
                                       v12)
                        - 16LL);
        v14 = (char *)(v31 - 6);
        if ( _InterlockedDecrement(v31 - 2) <= 0 )
          (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v14 + 8LL))(*(_QWORD *)v14);
        if ( !v13 )
          break;
        if ( (unsigned int)ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::Match(&v41, v30, &v32, 0) )
        {
          if ( !v32 )
            ATL::AtlThrowImpl(-2147467259);
          ATL::CSimpleStringT<unsigned short,0>::SetString(
            (char *)this + 328,
            *(_QWORD *)v36,
            (__int64)(*((_QWORD *)v36 + 1) - *(_QWORD *)v36) >> 1);
          break;
        }
      }
      v15 = (_QWORD *)(v30 - 24);
      if ( _InterlockedDecrement((volatile signed __int32 *)(v30 - 24 + 16)) <= 0 )
        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v15 + 8LL))(*v15);
      if ( Block )
        free(Block);
      operator delete(v36);
      v36 = 0;
      operator delete(v35);
      v35 = 0;
      if ( v42[0] )
        free(v42[0]);
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
      v16 = -1;
      do
        ++v16;
      while ( Buffer[v16] );
      if ( v16 < 2 || Buffer[1] != 58 )
        ATL::AtlThrowImpl(-2147418113);
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Format(
        (char *)this + 328,
        L"%wc:\\Symbols",
        Buffer[0]);
    }
    v17 = (_QWORD *)(v28 - 24);
    if ( _InterlockedDecrement((volatile signed __int32 *)(v28 - 24 + 16)) <= 0 )
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v17 + 8LL))(*v17);
  }
  if ( *((_DWORD *)*v9 - 4) )
  {
    FullPathNameW = GetFullPathNameW(*v9, 0, 0, 0);
    if ( FullPathNameW )
    {
      v19 = FullPathNameW + 1;
      v20 = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr);
      v21 = (WCHAR *)(v20 + 24);
      v29 = (WCHAR *)(v20 + 24);
      if ( (((*(_DWORD *)(v20 + 12) - v19) | (1 - *(_DWORD *)(v20 + 16))) & 0x80000000) != 0 )
      {
        ATL::CSimpleStringT<unsigned short,0>::PrepareWrite2(&v29, v19);
        v21 = v29;
      }
      if ( *((int *)v21 - 2) > 1 )
      {
        ATL::CSimpleStringT<unsigned short,0>::Fork(&v29, *((unsigned int *)v21 - 4));
        v21 = v29;
      }
      if ( !GetFullPathNameW(*v9, v19, v21, 0) )
        goto LABEL_45;
      if ( v21 )
      {
        v23 = -1;
        do
          ++v23;
        while ( v21[v23] );
        if ( (int)v23 < 0 )
          goto LABEL_61;
      }
      else
      {
        LODWORD(v23) = 0;
      }
      if ( (int)v23 <= *((_DWORD *)v21 - 3) )
      {
        *((_DWORD *)v21 - 4) = v23;
        v21[(unsigned int)v23] = 0;
        if ( *((int *)v21 - 4) >= 0 )
        {
          if ( *v21 != 92 )
          {
            v24 = *((_QWORD *)v21 - 3);
            if ( !v24 || (v25 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v24 + 32LL))(v24)) == 0 )
            {
              v25 = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[4])(&ATL::g_strmgr);
              if ( !v25 )
                ATL::AtlThrowImpl(-2147467259);
            }
            v28 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v25 + 24LL))(v25) + 24;
            ATL::CSimpleStringT<unsigned short,0>::Concatenate(
              (unsigned int)&v28,
              (unsigned int)L"\\\\?\\",
              4,
              (_DWORD)v21,
              *((_DWORD *)v21 - 4));
            ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::operator=(
              (char *)this + 328,
              &v28);
            v26 = (_QWORD *)(v28 - 24);
            if ( _InterlockedDecrement((volatile signed __int32 *)(v28 - 24 + 16)) <= 0 )
              (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v26 + 8LL))(*v26);
          }
LABEL_45:
          if ( _InterlockedDecrement((volatile signed __int32 *)v21 - 2) <= 0 )
            (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v21 - 3) + 8LL))(*((_QWORD *)v21 - 3));
          return this;
        }
      }
LABEL_61:
      ATL::AtlThrowImpl(-2147024809);
    }
  }
  return this;
}

```

## disassembly

```asm
0x18000d770  mov     [rsp-8+arg_8], rbx
0x18000d775  mov     [rsp-8+arg_10], rsi
0x18000d77a  push    rbp
0x18000d77b  push    rdi
0x18000d77c  push    r12
0x18000d77e  push    r14
0x18000d780  push    r15
0x18000d782  lea     rbp, [rsp-200h]
0x18000d78a  sub     rsp, 300h
0x18000d791  mov     rax, cs:__security_cookie
0x18000d798  xor     rax, rsp
0x18000d79b  mov     [rbp+220h+var_30], rax
0x18000d7a2  mov     rsi, rcx
0x18000d7a5  mov     [rbp+220h+var_248], rcx
0x18000d7a9  xor     r12d, r12d
0x18000d7ac  mov     [rcx+18h], r12d
0x18000d7b0  mov     [rcx+8], r12
0x18000d7b4  mov     [rcx+10h], r12
0x18000d7b8  lea     rax, ??_7CImageIdEventTraceExtender@Performance@Windows@Microsoft@@6B@; const Microsoft::Windows::Performance::CImageIdEventTraceExtender::`vftable'
0x18000d7bf  mov     [rcx], rax
0x18000d7c2  mov     [rcx+20h], r12d
0x18000d7c6  mov     [rcx+28h], r12
0x18000d7ca  mov     [rcx+30h], r12d
0x18000d7ce  mov     [rcx+38h], r12
0x18000d7d2  mov     [rcx+40h], r12
0x18000d7d6  mov     [rcx+48h], r12
0x18000d7da  mov     [rcx+50h], r12
0x18000d7de  mov     [rcx+58h], r12
0x18000d7e2  mov     [rcx+60h], r12
0x18000d7e6  mov     [rcx+68h], r12
0x18000d7ea  xorps   xmm0, xmm0
0x18000d7ed  movups  xmmword ptr [rcx+70h], xmm0
0x18000d7f1  mov     [rcx+80h], r12
0x18000d7f8  lea     ecx, [r12+7]
0x18000d7fd  mov     [rsi+88h], rcx
0x18000d804  mov     [rsi+70h], r12w
0x18000d809  movups  xmmword ptr [rsi+90h], xmm0
0x18000d810  mov     [rsi+0A0h], r12
0x18000d817  mov     [rsi+0A8h], rcx
0x18000d81e  mov     [rsi+90h], r12w
0x18000d826  mov     [rsi+0B0h], r12b
0x18000d82d  mov     [rsi+0B8h], r12
0x18000d834  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x18000d83b  lea     r14, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x18000d842  mov     rcx, r14
0x18000d845  mov     rax, [rax+18h]
0x18000d849  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d84e  add     rax, 18h
0x18000d852  mov     [rsi+0C0h], rax
0x18000d859  mov     [rsi+0C8h], r12w
0x18000d861  lea     rcx, LibFileName; "ntdll.dll"
0x18000d868  call    cs:__imp_GetModuleHandleW
0x18000d86e  test    rax, rax
0x18000d871  jz      short loc_18000D8B1
0x18000d873  lea     rdx, aRtlgetdevicefa; "RtlGetDeviceFamilyInfoEnum"
0x18000d87a  mov     rcx, rax; hModule
0x18000d87d  call    cs:__imp_GetProcAddress
0x18000d883  test    rax, rax
0x18000d886  jz      short loc_18000D8B1
0x18000d888  mov     dword ptr [rsp+320h+var_2E8], r12d
0x18000d88d  xor     r8d, r8d
0x18000d890  lea     rdx, [rsp+320h+var_2E8]
0x18000d895  xor     ecx, ecx
0x18000d897  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d89c  mov     eax, dword ptr [rsp+320h+var_2E8]
0x18000d8a0  cmp     eax, 5
0x18000d8a3  jz      short loc_18000D8AD
0x18000d8a5  add     eax, 0FFFFFFF5h
0x18000d8a8  cmp     eax, 1
0x18000d8ab  ja      short loc_18000D8B1
0x18000d8ad  mov     al, 1
0x18000d8af  jmp     short loc_18000D8B4
0x18000d8b1  mov     al, r12b
0x18000d8b4  mov     [rsi+0CAh], al
0x18000d8ba  lea     rdi, [rsi+0D0h]
0x18000d8c1  mov     [rsp+320h+var_2D8], rdi
0x18000d8c6  mov     [rdi], r12
0x18000d8c9  mov     [rdi+8], r12
0x18000d8cd  mov     ecx, 0A0h; Size
0x18000d8d2  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000d8d7  mov     [rax], rax
0x18000d8da  mov     [rax+8], rax
0x18000d8de  mov     [rdi], rax
0x18000d8e1  mov     [rdi+10h], r12
0x18000d8e5  mov     [rdi+18h], r12
0x18000d8e9  mov     ecx, 38h ; '8'; Size
0x18000d8ee  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000d8f3  mov     [rax], rax
0x18000d8f6  mov     [rax+8], rax
0x18000d8fa  mov     [rax+10h], rax
0x18000d8fe  mov     word ptr [rax+18h], 101h
0x18000d904  mov     [rdi+10h], rax
0x18000d908  mov     [rdi+20h], r12
0x18000d90c  mov     [rdi+28h], r12
0x18000d910  mov     ecx, 30h ; '0'; Size
0x18000d915  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000d91a  mov     [rax], rax
0x18000d91d  mov     [rax+8], rax
0x18000d921  mov     [rax+10h], rax
0x18000d925  mov     word ptr [rax+18h], 101h
0x18000d92b  mov     [rdi+20h], rax
0x18000d92f  mov     [rdi+30h], r12
0x18000d933  mov     [rdi+38h], r12
0x18000d937  mov     ecx, 28h ; '('; Size
0x18000d93c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000d941  mov     [rax], rax
0x18000d944  mov     [rax+8], rax
0x18000d948  mov     [rax+10h], rax
0x18000d94c  mov     word ptr [rax+18h], 101h
0x18000d952  mov     [rdi+30h], rax
0x18000d956  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x18000d95d  mov     rcx, r14
0x18000d960  mov     rax, [rax+18h]
0x18000d964  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d969  add     rax, 18h
0x18000d96d  mov     [rsi+110h], rax
0x18000d974  mov     [rsi+118h], r12
0x18000d97b  mov     [rsi+120h], r12d
0x18000d982  mov     [rsi+128h], r12b
0x18000d989  mov     [rsi+130h], r12
0x18000d990  mov     [rsi+138h], r12
0x18000d997  mov     [rsi+140h], r12
0x18000d99e  lea     rdi, [rsi+148h]
0x18000d9a5  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x18000d9ac  mov     rcx, r14
0x18000d9af  mov     rax, [rax+18h]
0x18000d9b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d9b8  add     rax, 18h
0x18000d9bc  mov     [rdi], rax
0x18000d9bf  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x18000d9c6  mov     rcx, r14
0x18000d9c9  mov     rax, [rax+18h]
0x18000d9cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d9d2  add     rax, 18h
0x18000d9d6  mov     [rsi+150h], rax
0x18000d9dd  lea     rbx, [rsi+158h]
0x18000d9e4  mov     [rbx], r12
0x18000d9e7  lea     r14, [rsi+160h]
0x18000d9ee  mov     [r14], r12
0x18000d9f1  lea     r15, [rsi+168h]
0x18000d9f8  mov     [r15], r12
0x18000d9fb  mov     [rsi+170h], r12
0x18000da02  lea     rcx, [rsi+178h]; this
0x18000da09  call    ??0CErrorEvent@Performance@Windows@Microsoft@@QEAA@K@Z; Microsoft::Windows::Performance::CErrorEvent::CErrorEvent(ulong)
0x18000da0e  nop
0x18000da0f  mov     edx, 2
0x18000da14  mov     rcx, rbx
0x18000da17  call    ?Allocate@?$CAutoVectorPtr@T_CVDD@@@ATL@@QEAA_N_K@Z; ATL::CAutoVectorPtr<_CVDD>::Allocate(unsigned __int64)
0x18000da1c  test    al, al
0x18000da1e  jz      loc_18000DEBD
0x18000da24  mov     edx, 2
0x18000da29  mov     rcx, r14
0x18000da2c  call    ?Allocate@?$CAutoVectorPtr@K@ATL@@QEAA_N_K@Z; ATL::CAutoVectorPtr<ulong>::Allocate(unsigned __int64)
0x18000da31  test    al, al
0x18000da33  jz      loc_18000DEBD
0x18000da39  mov     edx, 2
0x18000da3e  mov     rcx, r15
0x18000da41  call    ?Allocate@?$CAutoVectorPtr@_K@ATL@@QEAA_N_K@Z; ATL::CAutoVectorPtr<unsigned __int64>::Allocate(unsigned __int64)
0x18000da46  test    al, al
0x18000da48  jz      loc_18000DEBD
0x18000da4e  mov     dword ptr [rsi+170h], 2
0x18000da58  lea     rdx, aXperfEmbeddedp; "XPERF_EmbeddedPdbPath"
0x18000da5f  mov     rcx, rdi
0x18000da62  call    ?GetEnvironmentVariableW@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAHPEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::GetEnvironmentVariableW(ushort const *)
0x18000da67  or      r15, 0FFFFFFFFFFFFFFFFh
0x18000da6b  test    eax, eax
0x18000da6d  jz      short loc_18000DA7C
0x18000da6f  mov     rax, [rdi]
0x18000da72  cmp     [rax-10h], r12d
0x18000da76  jnz     loc_18000DCCF
0x18000da7c  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x18000da83  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x18000da8a  mov     rax, [rax+18h]
0x18000da8e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000da93  add     rax, 18h
0x18000da97  mov     [rsp+320h+var_2F0], rax
0x18000da9c  lea     rdx, aNtSymbolPath; "_NT_SYMBOL_PATH"
0x18000daa3  lea     rcx, [rsp+320h+var_2F0]
0x18000daa8  call    ?GetEnvironmentVariableW@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAHPEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::GetEnvironmentVariableW(ushort const *)
0x18000daad  test    eax, eax
0x18000daaf  jz      loc_18000DC4D
0x18000dab5  xorps   xmm0, xmm0
0x18000dab8  movdqu  xmmword ptr [rbp+220h+var_278], xmm0
0x18000dabd  mov     [rbp+220h+var_268], r12
0x18000dac1  mov     [rbp+220h+var_260], r12d
0x18000dac5  mov     [rbp+220h+var_258], r12
0x18000dac9  mov     [rbp+220h+var_250], 1
0x18000dad0  mov     [rbp+220h+var_280], r12d
0x18000dad4  lea     rcx, [rbp+220h+var_280]
0x18000dad8  call    ?Parse@?$CAtlRegExp@VCAtlRECharTraitsW@ATL@@@ATL@@QEAA?AW4REParseError@2@PEBGH@Z; ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::Parse(ushort const *,int)
0x18000dadd  test    eax, eax
0x18000dadf  jnz     loc_18000DEC8
0x18000dae5  mov     [rsp+320h+var_2B8], r12
0x18000daea  mov     [rsp+320h+var_2B0], r12
0x18000daef  mov     [rsp+320h+Block], r12
0x18000daf4  xorps   xmm0, xmm0
0x18000daf7  movdqa  [rbp+220h+var_2A0], xmm0
0x18000dafc  mov     [rbp+220h+var_290], r12d
0x18000db00  mov     [rsp+320h+var_2D0], r12d
0x18000db05  mov     [rbp+220h+var_288], r12
0x18000db09  mov     ebx, 100h
0x18000db0e  mov     edx, ebx
0x18000db10  lea     rcx, [rsp+320h+Block]
0x18000db15  call    ?GrowBuffer@?$CAtlArray@PEAXV?$CElementTraits@PEAX@ATL@@@ATL@@AEAA_N_K@Z; ATL::CAtlArray<void *,ATL::CElementTraits<void *>>::GrowBuffer(unsigned __int64)
0x18000db1a  test    al, al
0x18000db1c  jz      short loc_18000DB27
0x18000db1e  call    ?CallConstructors@?$CAtlArray@PEAXV?$CElementTraits@PEAX@ATL@@@ATL@@CAXPEAPEAX_K@Z; ATL::CAtlArray<void *,ATL::CElementTraits<void *>>::CallConstructors(void * *,unsigned __int64)
0x18000db23  mov     qword ptr [rbp+220h+var_2A0], rbx
0x18000db27  mov     [rsp+320h+var_2C8], r12
0x18000db2c  mov     [rsp+320h+var_2C0], r12
0x18000db31  mov     dword ptr [rsp+320h+var_2E8], r12d
0x18000db36  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x18000db3d  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x18000db44  mov     rax, [rax+18h]
0x18000db48  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000db4d  add     rax, 18h
0x18000db51  mov     [rsp+320h+var_2E0], rax
0x18000db56  lea     r9, [rsp+320h+var_2E8]
0x18000db5b  lea     rdx, [rsp+320h+var_2D8]
0x18000db60  lea     rcx, [rsp+320h+var_2F0]
0x18000db65  call    ?Tokenize@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEBA?AV12@PEBGAEAH@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Tokenize(ushort const *,int &)
0x18000db6a  mov     rdx, rax
0x18000db6d  lea     rcx, [rsp+320h+var_2E0]
0x18000db72  call    ??4?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::operator=(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x18000db77  mov     rcx, [rax]
0x18000db7a  mov     ebx, [rcx-10h]
0x18000db7d  mov     rdx, [rsp+320h+var_2D8]
0x18000db82  add     rdx, 0FFFFFFFFFFFFFFE8h
0x18000db86  mov     eax, r15d
0x18000db89  lock xadd [rdx+10h], eax
0x18000db8e  add     eax, r15d
0x18000db91  test    eax, eax
0x18000db93  jg      short loc_18000DBA4
0x18000db95  mov     rcx, [rdx]
0x18000db98  mov     rax, [rcx]
0x18000db9b  mov     rax, [rax+8]
0x18000db9f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dba4  test    ebx, ebx
0x18000dba6  jz      short loc_18000DBE8
0x18000dba8  xor     r9d, r9d
0x18000dbab  lea     r8, [rsp+320h+var_2D0]
0x18000dbb0  mov     rdx, [rsp+320h+var_2E0]
0x18000dbb5  lea     rcx, [rbp+220h+var_280]
0x18000dbb9  call    ?Match@?$CAtlRegExp@VCAtlRECharTraitsW@ATL@@@ATL@@QEAAHPEBGPEAV?$CAtlREMatchContext@VCAtlRECharTraitsW@ATL@@@2@PEAPEBG@Z; ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::Match(ushort const *,ATL::CAtlREMatchContext<ATL::CAtlRECharTraitsW> *,ushort const * *)
0x18000dbbe  test    eax, eax
0x18000dbc0  jz      short loc_18000DB56
0x18000dbc2  cmp     [rsp+320h+var_2D0], r12d
0x18000dbc7  jbe     loc_18000DEED
0x18000dbcd  mov     rax, [rsp+320h+var_2B0]
0x18000dbd2  mov     r8, [rax+8]
0x18000dbd6  sub     r8, [rax]
0x18000dbd9  sar     r8, 1
0x18000dbdc  mov     rdx, [rax]
0x18000dbdf  mov     rcx, rdi
0x18000dbe2  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x18000dbe7  nop
0x18000dbe8  mov     rdx, [rsp+320h+var_2E0]
0x18000dbed  add     rdx, 0FFFFFFFFFFFFFFE8h
0x18000dbf1  mov     eax, r15d
0x18000dbf4  lock xadd [rdx+10h], eax
0x18000dbf9  add     eax, r15d
0x18000dbfc  test    eax, eax
0x18000dbfe  jg      short loc_18000DC10
0x18000dc00  mov     rcx, [rdx]
0x18000dc03  mov     rax, [rcx]
0x18000dc06  mov     rax, [rax+8]
0x18000dc0a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dc0f  nop
0x18000dc10  mov     rcx, [rsp+320h+Block]; Block
0x18000dc15  test    rcx, rcx
0x18000dc18  jz      short loc_18000DC20
0x18000dc1a  call    cs:__imp_free
0x18000dc20  mov     rcx, [rsp+320h+var_2B0]; Block
0x18000dc25  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000dc2a  mov     [rsp+320h+var_2B0], r12
0x18000dc2f  mov     rcx, [rsp+320h+var_2B8]; Block
0x18000dc34  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000dc39  mov     [rsp+320h+var_2B8], r12
0x18000dc3e  mov     rcx, [rbp+220h+var_278]; Block
0x18000dc42  test    rcx, rcx
0x18000dc45  jz      short loc_18000DC4D
0x18000dc47  call    cs:__imp_free
0x18000dc4d  mov     rax, [rdi]
0x18000dc50  cmp     [rax-10h], r12d
0x18000dc54  jnz     short loc_18000DCA8
0x18000dc56  mov     edx, 105h; uSize
0x18000dc5b  lea     rcx, [rbp+220h+Buffer]; lpBuffer
0x18000dc5f  call    cs:__imp_GetSystemWindowsDirectoryW
0x18000dc65  test    eax, eax
0x18000dc67  jz      loc_18000DED3
0x18000dc6d  lea     rcx, [rbp+220h+Buffer]
0x18000dc71  mov     rax, r15
0x18000dc74  inc     rax
0x18000dc77  cmp     [rcx+rax*2], r12w
0x18000dc7c  jnz     short loc_18000DC74
0x18000dc7e  cmp     rax, 2
0x18000dc82  jb      loc_18000DEF8
0x18000dc88  cmp     [rbp+220h+var_23E], 3Ah ; ':'
0x18000dc8d  jnz     loc_18000DEF8
0x18000dc93  movzx   r8d, [rbp+220h+Buffer]
  ... truncated ...
```
