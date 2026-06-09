# Microsoft::Windows::Performance::CImageIdEventTraceExtender::CImageIdEventTraceExtender(void)

- ea: `0x18001f32c`
- end: `0x18001fb03`
- name: `??0CImageIdEventTraceExtender@Performance@Windows@Microsoft@@QEAA@XZ`
- size: `2007`
- prototype: `__int64 __fastcall(Microsoft::Windows::Performance::CImageIdEventTraceExtender *__hidden this)`
- caller_count: `1`
- callee_count: `22`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x180023844`

## callees

- `0x180001b90`
- `0x180001bb4`
- `0x180001bf8`
- `0x180011648`
- `0x180015f9c`
- `0x18001618c`
- `0x180016f5c`
- `0x180017000`
- `0x18001994c`
- `0x18001a030`
- `0x18001f28c`
- `0x18001f32c`
- `0x180020678`
- `0x180023010`
- `0x1800232e0`
- `0x1800232f0`
- `0x180023c9c`
- `0x18002428c`
- `0x180024e18`
- `0x180025e80`
- `0x1800279b0`
- `0x180039010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001f7e3`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001f814`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001f7e3`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001f814`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001f429`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001f429`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001f444`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001f444`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemWindowsDirectoryW` at `0x18001f832`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemWindowsDirectoryW` at `0x18001f832`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001fac2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001fac2`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x18001f8bd`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x18001f93d`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x18001f8bd`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x18001f93d`

## string_xrefs

- `0x18001f422`: `ntdll.dll`
- `0x18001f625`: `XPERF_EmbeddedPdbPath`
- `0x18001f669`: `_NT_SYMBOL_PATH`

## pseudocode

```c
// Hidden C++ exception states: #wind=33
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
0x18001f32c  mov     [rsp-8+arg_8], rbx
0x18001f331  mov     [rsp-8+arg_10], rsi
0x18001f336  push    rbp
0x18001f337  push    rdi
0x18001f338  push    r12
0x18001f33a  push    r14
0x18001f33c  push    r15
0x18001f33e  lea     rbp, [rsp-210h]
0x18001f346  sub     rsp, 310h
0x18001f34d  mov     rax, cs:__security_cookie
0x18001f354  xor     rax, rsp
0x18001f357  mov     [rbp+230h+var_30], rax
0x18001f35e  mov     rsi, rcx
0x18001f361  mov     [rbp+230h+var_248], rcx
0x18001f365  xor     r12d, r12d
0x18001f368  mov     [rsp+330h+var_2F0], r12d
0x18001f36d  mov     [rcx+18h], r12d
0x18001f371  mov     [rcx+8], r12
0x18001f375  mov     [rcx+10h], r12
0x18001f379  lea     rax, ??_7CImageIdEventTraceExtender@Performance@Windows@Microsoft@@6B@; const Microsoft::Windows::Performance::CImageIdEventTraceExtender::`vftable'
0x18001f380  mov     [rcx], rax
0x18001f383  mov     [rcx+20h], r12d
0x18001f387  mov     [rcx+28h], r12
0x18001f38b  mov     [rcx+30h], r12d
0x18001f38f  mov     [rcx+38h], r12
0x18001f393  mov     [rcx+40h], r12
0x18001f397  mov     [rcx+48h], r12
0x18001f39b  mov     [rcx+50h], r12
0x18001f39f  mov     [rcx+58h], r12
0x18001f3a3  mov     [rcx+60h], r12
0x18001f3a7  mov     [rcx+68h], r12
0x18001f3ab  xorps   xmm0, xmm0
0x18001f3ae  movups  xmmword ptr [rcx+70h], xmm0
0x18001f3b2  mov     [rcx+80h], r12
0x18001f3b9  lea     ecx, [r12+7]
0x18001f3be  mov     [rsi+88h], rcx
0x18001f3c5  mov     [rsi+70h], r12w
0x18001f3ca  movups  xmmword ptr [rsi+90h], xmm0
0x18001f3d1  mov     [rsi+0A0h], r12
0x18001f3d8  mov     [rsi+0A8h], rcx
0x18001f3df  mov     [rsi+90h], r12w
0x18001f3e7  mov     [rsi+0B0h], r12b
0x18001f3ee  mov     [rsi+0B8h], r12
0x18001f3f5  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x18001f3fc  lea     r14, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x18001f403  mov     rcx, r14
0x18001f406  mov     rax, [rax+18h]
0x18001f40a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f40f  add     rax, 18h
0x18001f413  mov     [rsi+0C0h], rax
0x18001f41a  mov     [rsi+0C8h], r12w
0x18001f422  lea     rcx, ModuleName; "ntdll.dll"
0x18001f429  call    cs:__imp_GetModuleHandleW
0x18001f430  nop     dword ptr [rax+rax+00h]
0x18001f435  test    rax, rax
0x18001f438  jz      short loc_18001F47E
0x18001f43a  lea     rdx, aRtlgetdevicefa; "RtlGetDeviceFamilyInfoEnum"
0x18001f441  mov     rcx, rax; hModule
0x18001f444  call    cs:__imp_GetProcAddress
0x18001f44b  nop     dword ptr [rax+rax+00h]
0x18001f450  test    rax, rax
0x18001f453  jz      short loc_18001F47E
0x18001f455  mov     dword ptr [rsp+330h+var_2F8], r12d
0x18001f45a  xor     r8d, r8d
0x18001f45d  lea     rdx, [rsp+330h+var_2F8]
0x18001f462  xor     ecx, ecx
0x18001f464  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f469  mov     eax, dword ptr [rsp+330h+var_2F8]
0x18001f46d  cmp     eax, 5
0x18001f470  jz      short loc_18001F47A
0x18001f472  add     eax, 0FFFFFFF5h
0x18001f475  cmp     eax, 1
0x18001f478  ja      short loc_18001F47E
0x18001f47a  mov     al, 1
0x18001f47c  jmp     short loc_18001F481
0x18001f47e  mov     al, r12b
0x18001f481  mov     [rsi+0CAh], al
0x18001f487  lea     rdi, [rsi+0D0h]
0x18001f48e  mov     [rsp+330h+var_2E0], rdi
0x18001f493  mov     [rdi], r12
0x18001f496  mov     [rdi+8], r12
0x18001f49a  mov     ecx, 0A0h; Size
0x18001f49f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001f4a4  mov     [rax], rax
0x18001f4a7  mov     [rax+8], rax
0x18001f4ab  mov     [rdi], rax
0x18001f4ae  mov     [rdi+10h], r12
0x18001f4b2  mov     [rdi+18h], r12
0x18001f4b6  mov     ecx, 38h ; '8'; Size
0x18001f4bb  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001f4c0  mov     [rax], rax
0x18001f4c3  mov     [rax+8], rax
0x18001f4c7  mov     [rax+10h], rax
0x18001f4cb  mov     word ptr [rax+18h], 101h
0x18001f4d1  mov     [rdi+10h], rax
0x18001f4d5  mov     [rdi+20h], r12
0x18001f4d9  mov     [rdi+28h], r12
0x18001f4dd  mov     ecx, 30h ; '0'; Size
0x18001f4e2  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001f4e7  mov     [rax], rax
0x18001f4ea  mov     [rax+8], rax
0x18001f4ee  mov     [rax+10h], rax
0x18001f4f2  mov     word ptr [rax+18h], 101h
0x18001f4f8  mov     [rdi+20h], rax
0x18001f4fc  mov     [rdi+30h], r12
0x18001f500  mov     [rdi+38h], r12
0x18001f504  mov     ecx, 28h ; '('; Size
0x18001f509  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001f50e  mov     [rax], rax
0x18001f511  mov     [rax+8], rax
0x18001f515  mov     [rax+10h], rax
0x18001f519  mov     word ptr [rax+18h], 101h
0x18001f51f  mov     [rdi+30h], rax
0x18001f523  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x18001f52a  mov     rcx, r14
0x18001f52d  mov     rax, [rax+18h]
0x18001f531  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f536  add     rax, 18h
0x18001f53a  mov     [rsi+110h], rax
0x18001f541  mov     [rsi+118h], r12
0x18001f548  mov     [rsi+120h], r12d
0x18001f54f  mov     [rsi+128h], r12b
0x18001f556  mov     [rsi+130h], r12
0x18001f55d  mov     [rsi+138h], r12
0x18001f564  mov     [rsi+140h], r12
0x18001f56b  lea     rdi, [rsi+148h]
0x18001f572  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x18001f579  mov     rcx, r14
0x18001f57c  mov     rax, [rax+18h]
0x18001f580  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f585  add     rax, 18h
0x18001f589  mov     [rdi], rax
0x18001f58c  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x18001f593  mov     rcx, r14
0x18001f596  mov     rax, [rax+18h]
0x18001f59a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f59f  add     rax, 18h
0x18001f5a3  mov     [rsi+150h], rax
0x18001f5aa  lea     rbx, [rsi+158h]
0x18001f5b1  mov     [rbx], r12
0x18001f5b4  lea     r14, [rsi+160h]
0x18001f5bb  mov     [r14], r12
0x18001f5be  lea     r15, [rsi+168h]
0x18001f5c5  mov     [r15], r12
0x18001f5c8  mov     [rsi+170h], r12
0x18001f5cf  lea     rcx, [rsi+178h]; this
0x18001f5d6  call    ??0CErrorEvent@Performance@Windows@Microsoft@@QEAA@K@Z; Microsoft::Windows::Performance::CErrorEvent::CErrorEvent(ulong)
0x18001f5db  nop
0x18001f5dc  mov     edx, 2
0x18001f5e1  mov     rcx, rbx
0x18001f5e4  call    ?Allocate@?$CAutoVectorPtr@T_CVDD@@@ATL@@QEAA_N_K@Z; ATL::CAutoVectorPtr<_CVDD>::Allocate(unsigned __int64)
0x18001f5e9  test    al, al
0x18001f5eb  jz      loc_18001FAAC
0x18001f5f1  mov     edx, 2
0x18001f5f6  mov     rcx, r14
0x18001f5f9  call    ?Allocate@?$CAutoVectorPtr@K@ATL@@QEAA_N_K@Z; ATL::CAutoVectorPtr<ulong>::Allocate(unsigned __int64)
0x18001f5fe  test    al, al
0x18001f600  jz      loc_18001FAAC
0x18001f606  mov     edx, 2
0x18001f60b  mov     rcx, r15
0x18001f60e  call    ?Allocate@?$CAutoVectorPtr@_K@ATL@@QEAA_N_K@Z; ATL::CAutoVectorPtr<unsigned __int64>::Allocate(unsigned __int64)
0x18001f613  test    al, al
0x18001f615  jz      loc_18001FAAC
0x18001f61b  mov     dword ptr [rsi+170h], 2
0x18001f625  lea     rdx, aXperfEmbeddedp; "XPERF_EmbeddedPdbPath"
0x18001f62c  mov     rcx, rdi
0x18001f62f  call    ?GetEnvironmentVariableW@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAHPEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::GetEnvironmentVariableW(ushort const *)
0x18001f634  or      r15, 0FFFFFFFFFFFFFFFFh
0x18001f638  test    eax, eax
0x18001f63a  jz      short loc_18001F649
0x18001f63c  mov     rax, [rdi]
0x18001f63f  cmp     [rax-10h], r12d
0x18001f643  jnz     loc_18001F8A8
0x18001f649  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x18001f650  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x18001f657  mov     rax, [rax+18h]
0x18001f65b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f660  add     rax, 18h
0x18001f664  mov     [rsp+330h+var_300], rax
0x18001f669  lea     rdx, aNtSymbolPath; "_NT_SYMBOL_PATH"
0x18001f670  lea     rcx, [rsp+330h+var_300]
0x18001f675  call    ?GetEnvironmentVariableW@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAHPEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::GetEnvironmentVariableW(ushort const *)
0x18001f67a  test    eax, eax
0x18001f67c  jz      loc_18001F820
0x18001f682  xorps   xmm0, xmm0
0x18001f685  movdqu  xmmword ptr [rbp+230h+var_278], xmm0
0x18001f68a  mov     [rbp+230h+var_268], r12
0x18001f68e  mov     [rbp+230h+var_260], r12d
0x18001f692  mov     [rbp+230h+var_258], r12
0x18001f696  mov     [rbp+230h+var_250], 1
0x18001f69d  mov     [rbp+230h+var_280], r12d
0x18001f6a1  lea     rcx, [rbp+230h+var_280]
0x18001f6a5  call    ?Parse@?$CAtlRegExp@VCAtlRECharTraitsW@ATL@@@ATL@@QEAA?AW4REParseError@2@PEBGH@Z; ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::Parse(ushort const *,int)
0x18001f6aa  test    eax, eax
0x18001f6ac  jnz     loc_18001FAB7
0x18001f6b2  mov     [rsp+330h+var_2B8], r12
0x18001f6b7  mov     [rbp+230h+var_2B0], r12
0x18001f6bb  mov     [rbp+230h+Block], r12
0x18001f6bf  xorps   xmm0, xmm0
0x18001f6c2  movdqa  [rbp+230h+var_2A0], xmm0
0x18001f6c7  mov     [rbp+230h+var_290], r12d
0x18001f6cb  mov     [rsp+330h+var_2D0], r12d
0x18001f6d0  mov     [rbp+230h+var_288], r12
0x18001f6d4  mov     ebx, 100h
0x18001f6d9  mov     edx, ebx
0x18001f6db  lea     rcx, [rbp+230h+Block]
0x18001f6df  call    ?GrowBuffer@?$CAtlArray@PEAXV?$CElementTraits@PEAX@ATL@@@ATL@@AEAA_N_K@Z; ATL::CAtlArray<void *,ATL::CElementTraits<void *>>::GrowBuffer(unsigned __int64)
0x18001f6e4  test    al, al
0x18001f6e6  jz      short loc_18001F6F1
0x18001f6e8  call    ?CallConstructors@?$CAtlArray@PEAXV?$CElementTraits@PEAX@ATL@@@ATL@@CAXPEAPEAX_K@Z; ATL::CAtlArray<void *,ATL::CElementTraits<void *>>::CallConstructors(void * *,unsigned __int64)
0x18001f6ed  mov     qword ptr [rbp+230h+var_2A0], rbx
0x18001f6f1  mov     [rsp+330h+var_2C8], r12
0x18001f6f6  mov     [rsp+330h+var_2C0], r12
0x18001f6fb  mov     dword ptr [rsp+330h+var_2F8], r12d
0x18001f700  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x18001f707  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x18001f70e  mov     rax, [rax+18h]
0x18001f712  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f717  add     rax, 18h
0x18001f71b  mov     [rsp+330h+var_2E8], rax
0x18001f720  lea     r9, [rsp+330h+var_2F8]
0x18001f725  lea     rdx, [rsp+330h+var_2E0]
0x18001f72a  lea     rcx, [rsp+330h+var_300]
0x18001f72f  call    ?Tokenize@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEBA?AV12@PEBGAEAH@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Tokenize(ushort const *,int &)
0x18001f734  nop
0x18001f735  mov     rdx, rax
0x18001f738  lea     rcx, [rsp+330h+var_2E8]
0x18001f73d  call    ??4?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::operator=(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x18001f742  mov     rcx, [rax]
0x18001f745  mov     ebx, [rcx-10h]
0x18001f748  mov     rdx, [rsp+330h+var_2E0]
0x18001f74d  add     rdx, 0FFFFFFFFFFFFFFE8h
0x18001f751  mov     eax, r15d
0x18001f754  lock xadd [rdx+10h], eax
0x18001f759  add     eax, r15d
0x18001f75c  test    eax, eax
0x18001f75e  jg      short loc_18001F76F
0x18001f760  mov     rcx, [rdx]
0x18001f763  mov     rax, [rcx]
0x18001f766  mov     rax, [rax+8]
0x18001f76a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f76f  test    ebx, ebx
0x18001f771  jz      short loc_18001F7B2
0x18001f773  xor     r9d, r9d
0x18001f776  lea     r8, [rsp+330h+var_2D0]
0x18001f77b  mov     rdx, [rsp+330h+var_2E8]
0x18001f780  lea     rcx, [rbp+230h+var_280]
0x18001f784  call    ?Match@?$CAtlRegExp@VCAtlRECharTraitsW@ATL@@@ATL@@QEAAHPEBGPEAV?$CAtlREMatchContext@VCAtlRECharTraitsW@ATL@@@2@PEAPEBG@Z; ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::Match(ushort const *,ATL::CAtlREMatchContext<ATL::CAtlRECharTraitsW> *,ushort const * *)
0x18001f789  test    eax, eax
0x18001f78b  jz      short loc_18001F720
0x18001f78d  cmp     [rsp+330h+var_2D0], r12d
0x18001f792  jbe     loc_18001FAE2
0x18001f798  mov     rax, [rbp+230h+var_2B0]
0x18001f79c  mov     r8, [rax+8]
0x18001f7a0  sub     r8, [rax]
0x18001f7a3  sar     r8, 1
0x18001f7a6  mov     rdx, [rax]
0x18001f7a9  mov     rcx, rdi
0x18001f7ac  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x18001f7b1  nop
0x18001f7b2  mov     rdx, [rsp+330h+var_2E8]
0x18001f7b7  add     rdx, 0FFFFFFFFFFFFFFE8h
0x18001f7bb  mov     eax, r15d
0x18001f7be  lock xadd [rdx+10h], eax
0x18001f7c3  add     eax, r15d
0x18001f7c6  test    eax, eax
0x18001f7c8  jg      short loc_18001F7DA
0x18001f7ca  mov     rcx, [rdx]
0x18001f7cd  mov     rax, [rcx]
0x18001f7d0  mov     rax, [rax+8]
0x18001f7d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f7d9  nop
0x18001f7da  mov     rcx, [rbp+230h+Block]; Block
0x18001f7de  test    rcx, rcx
0x18001f7e1  jz      short loc_18001F7EF
0x18001f7e3  call    cs:__imp_free
0x18001f7ea  nop     dword ptr [rax+rax+00h]
0x18001f7ef  mov     rcx, [rbp+230h+var_2B0]; void *
0x18001f7f3  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001f7f8  mov     [rbp+230h+var_2B0], r12
0x18001f7fc  mov     rcx, [rsp+330h+var_2B8]; void *
0x18001f801  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001f806  mov     [rsp+330h+var_2B8], r12
0x18001f80b  mov     rcx, [rbp+230h+var_278]; Block
0x18001f80f  test    rcx, rcx
0x18001f812  jz      short loc_18001F820
0x18001f814  call    cs:__imp_free
0x18001f81b  nop     dword ptr [rax+rax+00h]
0x18001f820  mov     rax, [rdi]
0x18001f823  cmp     [rax-10h], r12d
0x18001f827  jnz     short loc_18001F881
0x18001f829  mov     edx, 105h; uSize
0x18001f82e  lea     rcx, [rbp+230h+Buffer]; lpBuffer
0x18001f832  call    cs:__imp_GetSystemWindowsDirectoryW
0x18001f839  nop     dword ptr [rax+rax+00h]
0x18001f83e  test    eax, eax
0x18001f840  jz      loc_18001FAC2
0x18001f846  lea     rcx, [rbp+230h+Buffer]
0x18001f84a  mov     rax, r15
0x18001f84d  inc     rax
  ... truncated ...
```
