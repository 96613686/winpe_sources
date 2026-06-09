# AppxAllUserStore::EnlistAllUserApplicationPackageOnUserStore(AppxAllUserStore::SetupPhase,ushort const *,Common::RegistryKey *,Common::RegistryKey *,bool,bool,Common::Array<Common::StringBuffer,Common::ContainerOperations<Common::StringBuffer,Common::StringBuffer>,Common::NoKey,Common::ContainerOperations<Common::NoKey,Common::StringBuffer>,Common::ArrayOperations<Common::StringBuffer,Common::NoKey>> *,Common::Array<AppxAllUserStore::_MainPackageInfo,Common::ContainerOperations<AppxAllUserStore::_MainPackageInfo,AppxAllUserStore::_MainPackageInfo>,Common::NoKey,Common::ContainerOperations<Common::NoKey,AppxAllUserStore::_MainPackageInfo>,Common::ArrayOperations<AppxAllUserStore::_MainPackageInfo,Common::NoKey>> *)

- ea: `0x18000af10`
- end: `0x18000b57a`
- name: `?EnlistAllUserApplicationPackageOnUserStore@AppxAllUserStore@@YAJW4SetupPhase@1@PEBGPEAVRegistryKey@Common@@2_N3PEAV?$Array@VStringBuffer@Common@@V?$ContainerOperations@VStringBuffer@Common@@V12@@2@VNoKey@2@V?$ContainerOperations@VNoKey@Common@@VStringBuffer@2@@2@V?$ArrayOperations@VStringBuffer@Common@@VNoKey@2@@2@@4@PEAV?$Array@U_MainPackageInfo@AppxAllUserStore@@V?$ContainerOperations@U_MainPackageInfo@AppxAllUserStore@@U12@@Common@@VNoKey@4@V?$ContainerOperations@VNoKey@Common@@U_MainPackageInfo@AppxAllUserStore@@@4@V?$ArrayOperations@U_MainPackageInfo@AppxAllUserStore@@VNoKey@Common@@@4@@4@@Z`
- size: `1642`
- prototype: ``
- caller_count: `2`
- callee_count: `17`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180038560`
- `0x1800396d4`

## callees

- `0x180004968`
- `0x180007610`
- `0x180007a10`
- `0x180008550`
- `0x18000a600`
- `0x18000ae14`
- `0x18000ae80`
- `0x18000af10`
- `0x18000b580`
- `0x18000bf10`
- `0x18000c594`
- `0x180017f50`
- `0x180018248`
- `0x18001a604`
- `0x180049044`
- `0x18004c97e`
- `0x18004c9d0`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x18000af7b`
- `ntdll!RtlAllocateHeap` at `0x18000b0d5`
- `ntdll!RtlAllocateHeap` at `0x18000af7b`
- `ntdll!RtlAllocateHeap` at `0x18000b0d5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000b3d6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000b3f1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000b419`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000b421`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000b469`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000b474`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000b3d6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000b3f1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000b419`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000b421`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000b469`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000b474`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000b34d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000b4aa`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000b34d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000b4aa`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000b15a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000b1c5`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000b15a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000b1c5`

## string_xrefs

- `0x18000b027`: `onecore\base\appmodel\common\widestring.cpp`
- `0x18000b2b2`: `onecore\admin\appmodel\common\packagefullnameutilities.cpp`
- `0x18000b2d7`: `onecore\admin\appmodel\common\packagefullnameutilities.cpp`
- `0x18000b532`: `onecore\base\appmodel\common\registrykey.cpp`
- `0x18000b48b`: `NumberOfAttempts`

## pseudocode

```c
__int64 __fastcall AppxAllUserStore::EnlistAllUserApplicationPackageOnUserStore(
        int a1,
        WCHAR *a2,
        HKEY *a3,
        HKEY *a4,
        char a5,
        char a6,
        __int64 a7,
        _QWORD *a8)
{
  PVOID ProcessHeap; // rcx
  __int64 v12; // rdx
  Common::StringBuffer *Heap; // rsi
  unsigned int v14; // eax
  unsigned int v15; // edx
  const unsigned __int16 *v16; // rdx
  unsigned int v17; // r8d
  unsigned __int16 *v18; // rax
  __int64 v19; // rcx
  int v20; // ebx
  __int64 v21; // rcx
  unsigned __int64 v22; // rax
  unsigned __int64 v23; // rbx
  unsigned __int64 v24; // rax
  void *v25; // rax
  SIZE_T v26; // r8
  PVOID v27; // rax
  PVOID v28; // rdi
  _QWORD *v29; // rax
  REGSAM v30; // edi
  REGSAM v31; // r9d
  LSTATUS v32; // eax
  unsigned int v33; // ebx
  HKEY v34; // rcx
  LSTATUS v35; // eax
  bool *v36; // r9
  int v37; // eax
  int v38; // eax
  HKEY v39; // rcx
  int v41; // eax
  LSTATUS Value; // eax
  bool v43; // sf
  char v44; // bl
  LSTATUS v45; // eax
  bool v46; // sf
  unsigned int phkResult; // [rsp+20h] [rbp-E0h]
  int phkResulta; // [rsp+20h] [rbp-E0h]
  int phkResultb; // [rsp+20h] [rbp-E0h]
  int phkResultc; // [rsp+20h] [rbp-E0h]
  int phkResultd; // [rsp+20h] [rbp-E0h]
  unsigned __int16 v52; // [rsp+50h] [rbp-B0h] BYREF
  HKEY lpcbData; // [rsp+58h] [rbp-A8h] BYREF
  BYTE v54[4]; // [rsp+60h] [rbp-A0h] BYREF
  HKEY hKey; // [rsp+68h] [rbp-98h] BYREF
  BYTE Data[4]; // [rsp+70h] [rbp-90h] BYREF
  int v57; // [rsp+74h] [rbp-8Ch]
  _QWORD *v58; // [rsp+78h] [rbp-88h]
  _BYTE v59[4]; // [rsp+80h] [rbp-80h] BYREF
  Common *v60; // [rsp+84h] [rbp-7Ch]
  __int64 v61; // [rsp+90h] [rbp-70h]
  __int64 v62; // [rsp+A0h] [rbp-60h]
  __int64 v63; // [rsp+A8h] [rbp-58h]
  unsigned __int16 Src[128]; // [rsp+170h] [rbp+70h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2C8h] [rbp+1C8h]

  v57 = a1;
  ProcessHeap = ReservedForLocalUse::g_heap;
  v58 = a8;
  if ( !ReservedForLocalUse::g_heap )
  {
    ProcessHeap = NtCurrentPeb()->ProcessHeap;
    ReservedForLocalUse::g_heap = ProcessHeap;
  }
  Heap = (Common::StringBuffer *)RtlAllocateHeap(ProcessHeap, 0, 0x18u);
  if ( !Heap )
    return 2147942414LL;
  *(_DWORD *)v54 = 240;
  *((_QWORD *)Heap + 2) = 0;
  *(_OWORD *)Heap = 0;
  v14 = ARI::Identity::Convert<unsigned short,unsigned short *,unsigned short const *,PACKAGE_ID>::PackageIdBasicFromFullName(
          a2,
          v12,
          (unsigned int *)v54,
          (__int64)v59);
  if ( v14 )
  {
    v41 = wil::details::in1diag3::Return_Win32(
            retaddr,
            (void *)0x22,
            (unsigned int)"onecore\\admin\\appmodel\\common\\packagefullnameutilities.cpp",
            (const char *)v14,
            phkResult);
    v20 = v41;
    if ( v41 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x32,
        (unsigned int)"onecore\\admin\\appmodel\\common\\packagefullnameutilities.cpp",
        (const char *)(unsigned int)v41,
        phkResult);
LABEL_49:
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x746,
        (int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\logonutilities.cpp",
        (const char *)(unsigned int)v20);
      Common::StringBuffer::`scalar deleting destructor'(Heap, 1);
      return (unsigned int)v20;
    }
  }
  v16 = Common::ProcessorArchitectureFormatString((Common *)(unsigned int)v60, v15);
  if ( !v16 )
    wil::details::in1diag3::_FailFast_Hr(retaddr, 0, v17, (const char *)0x80070057LL, phkResult);
  StringCchPrintfW(Src, 0x80u, L"%s_%s_%s_%s", v61, v16, v62, v63);
  v18 = Src;
  v19 = 1073741822;
  while ( *v18 )
  {
    ++v18;
    if ( !--v19 )
    {
      v20 = -2147024809;
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x249,
        (int)"onecore\\base\\appmodel\\common\\widestring.cpp",
        (const char *)0x80070057LL);
      goto LABEL_11;
    }
  }
  v20 = Common::StringBuffer::SetValue(Heap, Src, 1073741822 - (int)v19);
LABEL_11:
  if ( v20 < 0 )
    goto LABEL_49;
  v21 = *(_QWORD *)(a7 + 16);
  v22 = *(_QWORD *)(a7 + 8);
  v23 = v21 + 1;
  if ( v21 + 1 > v22 )
  {
    if ( v22 == 0x3FFFFFFF )
    {
      v33 = -2147483637;
    }
    else
    {
      if ( v22 )
        v24 = ((3 * v22) >> 1) + 1;
      else
        v24 = 16;
      if ( v23 <= v24 )
        v23 = v24;
      if ( v23 > 0x3FFFFFFF )
        v23 = 0x3FFFFFFF;
      v25 = ReservedForLocalUse::GetHeap((ReservedForLocalUse *)0x3FFFFFFF);
      v27 = RtlAllocateHeap(v25, 0, v26);
      v28 = v27;
      if ( v27 )
      {
        if ( *(_QWORD *)a7 )
        {
          memmove_0(v27, *(const void **)a7, 8LL * *(_QWORD *)(a7 + 16));
          Common::GlobalHeap::Free(*(void **)a7);
        }
        v21 = *(_QWORD *)(a7 + 16);
        *(_QWORD *)a7 = v28;
        *(_QWORD *)(a7 + 8) = v23;
        goto LABEL_25;
      }
      v33 = -2147024882;
    }
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x747,
      (int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\logonutilities.cpp",
      (const char *)v33);
    Common::StringBuffer::`scalar deleting destructor'(Heap, 1);
    return v33;
  }
LABEL_25:
  v29 = *(_QWORD **)a7;
  v30 = 131097;
  hKey = 0;
  v29[v21] = Heap;
  ++*(_QWORD *)(a7 + 16);
  if ( a4 )
  {
    v31 = 131097;
    if ( !a6 )
      v31 = 983071;
    v32 = RegOpenKeyExW(*a4, a2, 0, v31, &hKey);
    v33 = v32;
    if ( v32 > 0 )
      v33 = (unsigned __int16)v32 | 0x80070000;
    if ( (int)v33 <= -2147024895 || v33 + 2147024892 <= 0x7FF8FFFB )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xAD,
        (unsigned int)"onecore\\base\\appmodel\\common\\registrykey.cpp",
        (const char *)v33,
        phkResulta);
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x6EB,
        (unsigned int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\logonutilities.cpp",
        (const char *)v33,
        phkResultd);
      Common::RegistryKey::~RegistryKey(&hKey);
      goto LABEL_45;
    }
    a4 = 0;
    if ( (unsigned __int64)hKey - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
    {
      *(_DWORD *)Data = 0;
      *(_DWORD *)v54 = 0;
      LODWORD(lpcbData) = 4;
      Value = RegQueryValueExW(hKey, L"LastReturnValue", 0, 0, Data, (LPDWORD)&lpcbData);
      v43 = Value < 0;
      if ( Value > 0 )
        v43 = 1;
      if ( v43 )
        goto LABEL_61;
      if ( *(_DWORD *)Data )
      {
        LODWORD(lpcbData) = 4;
        v45 = RegQueryValueExW(hKey, L"NumberOfAttempts", 0, 0, v54, (LPDWORD)&lpcbData);
        v46 = v45 < 0;
        if ( v45 > 0 )
          v46 = 1;
        if ( v46 || *(_DWORD *)Data && *(_DWORD *)v54 < 0xAu )
          goto LABEL_61;
      }
      v44 = 0;
      if ( a5 )
LABEL_61:
        v44 = 1;
      if ( (unsigned __int64)hKey - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
        RegCloseKey(hKey);
      hKey = 0;
      if ( !v44 )
        goto LABEL_58;
    }
  }
  v34 = *a3;
  lpcbData = (HKEY)a4;
  if ( !a6 )
    v30 = 983071;
  v35 = RegOpenKeyExW(v34, a2, 0, v30, &lpcbData);
  v33 = v35;
  if ( v35 > 0 )
    v33 = (unsigned __int16)v35 | 0x80070000;
  if ( (v33 & 0x80000000) != 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x71E,
      (unsigned int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\logonutilities.cpp",
      (const char *)v33,
      phkResultb);
    if ( (unsigned __int64)lpcbData - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
      RegCloseKey(lpcbData);
    v39 = hKey;
    if ( (unsigned __int64)hKey - 1 > 0xFFFFFFFFFFFFFFFDuLL )
      goto LABEL_45;
LABEL_67:
    RegCloseKey(v39);
LABEL_45:
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x755,
      (int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\logonutilities.cpp",
      (const char *)v33);
    return v33;
  }
  LOBYTE(v52) = 1;
  v37 = AppxAllUserStore::CheckKeyForEnablement(&lpcbData, (struct Common::RegistryKey *)a2, &v52, v36);
  if ( v37 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x721,
      (int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\logonutilities.cpp",
      (const char *)(unsigned int)v37);
  if ( (_BYTE)v52 )
  {
    v38 = AppxAllUserStore::AddPackageToDynamicPackageArray(
            v57,
            (Common::Deployment *)a2,
            (struct Common::StringBuffer *)&lpcbData,
            0,
            0,
            0,
            (int)a4,
            (__int64)a4,
            v58);
    v33 = v38;
    if ( v38 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x72E,
        (unsigned int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\logonutilities.cpp",
        (const char *)(unsigned int)v38,
        phkResultc);
      if ( (unsigned __int64)lpcbData - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
        RegCloseKey(lpcbData);
      v39 = hKey;
      if ( (unsigned __int64)hKey - 1 > 0xFFFFFFFFFFFFFFFDuLL )
        goto LABEL_45;
      goto LABEL_67;
    }
  }
  if ( (unsigned __int64)lpcbData - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
    RegCloseKey(lpcbData);
LABEL_58:
  if ( (unsigned __int64)hKey - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
    RegCloseKey(hKey);
  return 0;
}

```

## disassembly

```asm
0x18000af10  push    rbp
0x18000af12  push    rsi
0x18000af13  push    r12
0x18000af15  push    r13
0x18000af17  push    r14
0x18000af19  push    r15
0x18000af1b  lea     rbp, [rsp-198h]
0x18000af23  sub     rsp, 298h
0x18000af2a  mov     rax, cs:__security_cookie
0x18000af31  xor     rax, rsp
0x18000af34  mov     [rbp+1C0h+var_50], rax
0x18000af3b  mov     rax, [rbp+1C0h+arg_38]
0x18000af42  mov     r15, r9
0x18000af45  mov     r14, [rbp+1C0h+arg_30]
0x18000af4c  mov     r13, r8
0x18000af4f  mov     [rsp+2C0h+var_24C], ecx
0x18000af53  mov     r12, rdx
0x18000af56  mov     rcx, cs:?g_heap@ReservedForLocalUse@@3PEAXEA; HeapHandle
0x18000af5d  mov     [rsp+2C0h+var_248], rax
0x18000af62  test    rcx, rcx
0x18000af65  jz      loc_18000B097
0x18000af6b  xor     edx, edx; Flags
0x18000af6d  mov     [rsp+2C0h+var_30], rbx
0x18000af75  mov     r8d, 18h; Size
0x18000af7b  call    cs:__imp_RtlAllocateHeap
0x18000af81  mov     rsi, rax
0x18000af84  test    rax, rax
0x18000af87  jz      loc_18000B570
0x18000af8d  xor     eax, eax
0x18000af8f  mov     dword ptr [rsp+2C0h+var_260], 0F0h
0x18000af97  xorps   xmm0, xmm0
0x18000af9a  mov     [rsi+10h], rax
0x18000af9e  lea     r9, [rbp+1C0h+var_240]
0x18000afa2  mov     rcx, r12; lpString1
0x18000afa5  lea     r8, [rsp+2C0h+var_260]
0x18000afaa  movups  xmmword ptr [rsi], xmm0
0x18000afad  call    ?PackageIdBasicFromFullName@?$Convert@GPEAGPEBGUPACKAGE_ID@@@Identity@ARI@@SAJPEBGIPEAIPEAE@Z; ARI::Identity::Convert<ushort,ushort *,ushort const *,PACKAGE_ID>::PackageIdBasicFromFullName(ushort const *,uint,uint *,uchar *)
0x18000afb2  test    eax, eax
0x18000afb4  jnz     loc_18000B2AB
0x18000afba  mov     ecx, dword ptr [rbp+1C0h+var_23C]; this
0x18000afbd  call    ?ProcessorArchitectureFormatString@Common@@YAPEBGI@Z; Common::ProcessorArchitectureFormatString(uint)
0x18000afc2  mov     rdx, rax; void *
0x18000afc5  test    rax, rax
0x18000afc8  jz      loc_18000B4DF
0x18000afce  mov     rax, [rbp+1C0h+var_218]
0x18000afd2  lea     r8, aSSSS; "%s_%s_%s_%s"
0x18000afd9  mov     r9, [rbp+1C0h+var_230]
0x18000afdd  lea     rcx, [rbp+1C0h+Src]; unsigned __int16 *
0x18000afe1  mov     [rsp+2C0h+var_290], rax
0x18000afe6  mov     rax, [rbp+1C0h+var_220]
0x18000afea  mov     [rsp+2C0h+lpcbData], rax
0x18000afef  mov     [rsp+2C0h+phkResult], rdx; int
0x18000aff4  mov     edx, 80h; unsigned __int64
0x18000aff9  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000affe  mov     r8d, 3FFFFFFEh
0x18000b004  lea     rax, [rbp+1C0h+Src]
0x18000b008  mov     ecx, r8d
0x18000b00b  nop     dword ptr [rax+rax+00h]
0x18000b010  cmp     word ptr [rax], 0
0x18000b014  jz      short loc_18000B042
0x18000b016  add     rax, 2
0x18000b01a  sub     rcx, 1
0x18000b01e  jnz     short loc_18000B010
0x18000b020  mov     rcx, [rbp+1C8h]; this
0x18000b027  lea     r8, aOnecoreBaseApp_14; "onecore\\base\\appmodel\\common\\widest"...
0x18000b02e  mov     ebx, 80070057h
0x18000b033  mov     edx, 249h; void *
0x18000b038  mov     r9d, ebx; char *
0x18000b03b  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18000b040  jmp     short loc_18000B053
0x18000b042  sub     r8d, ecx; unsigned int
0x18000b045  lea     rdx, [rbp+1C0h+Src]; Src
0x18000b049  mov     rcx, rsi; this
0x18000b04c  call    ?SetValue@StringBuffer@Common@@QEAAJPEBGK@Z; Common::StringBuffer::SetValue(ushort const *,ulong)
0x18000b051  mov     ebx, eax
0x18000b053  test    ebx, ebx
0x18000b055  js      loc_18000B2EB
0x18000b05b  mov     rcx, [r14+10h]
0x18000b05f  mov     rax, [r14+8]
0x18000b063  mov     [rsp+2C0h+var_38], rdi
0x18000b06b  lea     rbx, [rcx+1]
0x18000b06f  cmp     rbx, rax
0x18000b072  jbe     loc_18000B112
0x18000b078  mov     ecx, 3FFFFFFFh; this
0x18000b07d  cmp     rax, rcx
0x18000b080  jz      loc_18000B4F2
0x18000b086  test    rax, rax
0x18000b089  jz      short loc_18000B0B0
0x18000b08b  lea     rax, [rax+rax*2]
0x18000b08f  shr     rax, 1
0x18000b092  inc     rax
0x18000b095  jmp     short loc_18000B0B5
0x18000b097  mov     rax, gs:60h
0x18000b0a0  mov     rcx, [rax+30h]
0x18000b0a4  mov     cs:?g_heap@ReservedForLocalUse@@3PEAXEA, rcx; void * ReservedForLocalUse::g_heap
0x18000b0ab  jmp     loc_18000AF6B
0x18000b0b0  mov     eax, 10h
0x18000b0b5  cmp     rbx, rax
0x18000b0b8  cmovbe  rbx, rax
0x18000b0bc  cmp     rbx, rcx
0x18000b0bf  cmova   rbx, rcx
0x18000b0c3  lea     r8, ds:0[rbx*8]
0x18000b0cb  call    ?GetHeap@ReservedForLocalUse@@YAPEAXXZ; ReservedForLocalUse::GetHeap(void)
0x18000b0d0  mov     rcx, rax; HeapHandle
0x18000b0d3  xor     edx, edx; Flags
0x18000b0d5  call    cs:__imp_RtlAllocateHeap
0x18000b0db  mov     rdi, rax
0x18000b0de  test    rax, rax
0x18000b0e1  jz      loc_18000B4F9
0x18000b0e7  mov     rdx, [r14]; Src
0x18000b0ea  test    rdx, rdx
0x18000b0ed  jz      short loc_18000B107
0x18000b0ef  mov     r8, [r14+10h]
0x18000b0f3  mov     rcx, rax; void *
0x18000b0f6  shl     r8, 3; Size
0x18000b0fa  call    memmove_0
0x18000b0ff  mov     rcx, [r14]; void *
0x18000b102  call    ?Free@GlobalHeap@Common@@SAXPEAX@Z; Common::GlobalHeap::Free(void *)
0x18000b107  mov     rcx, [r14+10h]
0x18000b10b  mov     [r14], rdi
0x18000b10e  mov     [r14+8], rbx
0x18000b112  mov     rax, [r14]
0x18000b115  mov     edi, 20019h
0x18000b11a  mov     [rsp+2C0h+hKey], 0
0x18000b123  mov     [rax+rcx*8], rsi
0x18000b127  inc     qword ptr [r14+10h]
0x18000b12b  mov     r14d, 0F001Fh
0x18000b131  movzx   esi, [rbp+1C0h+arg_28]
0x18000b138  test    r15, r15
0x18000b13b  jz      short loc_18000B1A2
0x18000b13d  mov     rcx, [r15]; hKey
0x18000b140  lea     rax, [rsp+2C0h+hKey]
0x18000b145  mov     r9d, edi
0x18000b148  mov     [rsp+2C0h+phkResult], rax; int
0x18000b14d  test    sil, sil
0x18000b150  mov     rdx, r12; lpSubKey
0x18000b153  cmovz   r9d, r14d; samDesired
0x18000b157  xor     r8d, r8d; ulOptions
0x18000b15a  call    cs:__imp_RegOpenKeyExW
0x18000b160  mov     ebx, eax
0x18000b162  test    eax, eax
0x18000b164  jle     short loc_18000B16F
0x18000b166  movzx   ebx, ax
0x18000b169  or      ebx, 80070000h
0x18000b16f  cmp     ebx, 80070001h
0x18000b175  jle     loc_18000B52B
0x18000b17b  lea     eax, [rbx+7FF8FFFCh]
0x18000b181  cmp     eax, 7FF8FFFBh
0x18000b186  jbe     loc_18000B52B
0x18000b18c  mov     rcx, [rsp+2C0h+hKey]; hKey
0x18000b191  xor     r15d, r15d
0x18000b194  lea     rax, [rcx-1]
0x18000b198  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000b19c  jbe     loc_18000B31A
0x18000b1a2  mov     rcx, [r13+0]; hKey
0x18000b1a6  lea     rax, [rsp+2C0h+var_268]
0x18000b1ab  test    sil, sil
0x18000b1ae  mov     [rsp+2C0h+var_268], r15
0x18000b1b3  mov     rdx, r12; lpSubKey
0x18000b1b6  mov     [rsp+2C0h+phkResult], rax; int
0x18000b1bb  cmovz   edi, r14d
0x18000b1bf  xor     r8d, r8d; ulOptions
0x18000b1c2  mov     r9d, edi; samDesired
0x18000b1c5  call    cs:__imp_RegOpenKeyExW
0x18000b1cb  mov     ebx, eax
0x18000b1cd  test    eax, eax
0x18000b1cf  jle     short loc_18000B1DA
0x18000b1d1  movzx   ebx, ax
0x18000b1d4  or      ebx, 80070000h
0x18000b1da  test    ebx, ebx
0x18000b1dc  js      loc_18000B42C
0x18000b1e2  lea     r8, [rsp+2C0h+var_270]; unsigned __int16 *
0x18000b1e7  mov     byte ptr [rsp+2C0h+var_270], 1
0x18000b1ec  mov     rdx, r12; struct Common::RegistryKey *
0x18000b1ef  lea     rcx, [rsp+2C0h+var_268]; this
0x18000b1f4  call    ?CheckKeyForEnablement@AppxAllUserStore@@YAJPEAVRegistryKey@Common@@PEBGAEA_N@Z; AppxAllUserStore::CheckKeyForEnablement(Common::RegistryKey *,ushort const *,bool &)
0x18000b1f9  test    eax, eax
0x18000b1fb  js      loc_18000B3F9
0x18000b201  cmp     byte ptr [rsp+2C0h+var_270], 0
0x18000b206  jz      loc_18000B3E2
0x18000b20c  mov     rax, [rsp+2C0h+var_248]
0x18000b211  lea     r8, [rsp+2C0h+var_268]
0x18000b216  mov     ecx, [rsp+2C0h+var_24C]
0x18000b21a  xor     r9d, r9d
0x18000b21d  mov     [rsp+2C0h+var_280], rax
0x18000b222  mov     rdx, r12
0x18000b225  mov     [rsp+2C0h+var_288], r15
0x18000b22a  mov     [rsp+2C0h+var_290], r15
0x18000b22f  mov     byte ptr [rsp+2C0h+lpcbData], 0
0x18000b234  mov     byte ptr [rsp+2C0h+phkResult], 0; int
0x18000b239  call    ?AddPackageToDynamicPackageArray@AppxAllUserStore@@YAJW4SetupPhase@1@PEBGPEAVRegistryKey@Common@@_N3311PEAV?$Array@U_MainPackageInfo@AppxAllUserStore@@V?$ContainerOperations@U_MainPackageInfo@AppxAllUserStore@@U12@@Common@@VNoKey@4@V?$ContainerOperations@VNoKey@Common@@U_MainPackageInfo@AppxAllUserStore@@@4@V?$ArrayOperations@U_MainPackageInfo@AppxAllUserStore@@VNoKey@Common@@@4@@4@@Z; AppxAllUserStore::AddPackageToDynamicPackageArray(AppxAllUserStore::SetupPhase,ushort const *,Common::RegistryKey *,bool,bool,bool,ushort const *,ushort const *,Common::Array<AppxAllUserStore::_MainPackageInfo,Common::ContainerOperations<AppxAllUserStore::_MainPackageInfo,AppxAllUserStore::_MainPackageInfo>,Common::NoKey,Common::ContainerOperations<Common::NoKey,AppxAllUserStore::_MainPackageInfo>,Common::ArrayOperations<AppxAllUserStore::_MainPackageInfo,Common::NoKey>> *)
0x18000b23e  mov     ebx, eax
0x18000b240  test    eax, eax
0x18000b242  jns     loc_18000B3E2
0x18000b248  mov     rcx, [rbp+1C8h]; this
0x18000b24f  lea     r8, aOnecoreAdminAp_8; "onecore\\admin\\appmodel\\appxalluserst"...
0x18000b256  mov     r9d, eax; char *
0x18000b259  mov     edx, 72Eh; void *
0x18000b25e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000b263  mov     rcx, [rsp+2C0h+var_268]; hKey
0x18000b268  lea     rax, [rcx-1]
0x18000b26c  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000b270  jbe     loc_18000B421
0x18000b276  mov     rcx, [rsp+2C0h+hKey]
0x18000b27b  lea     rax, [rcx-1]
0x18000b27f  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000b283  jbe     loc_18000B469
0x18000b289  mov     rcx, [rbp+1C8h]; this
0x18000b290  lea     r8, aOnecoreAdminAp_8; "onecore\\admin\\appmodel\\appxalluserst"...
0x18000b297  mov     r9d, ebx; char *
0x18000b29a  mov     edx, 755h; void *
0x18000b29f  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18000b2a4  mov     eax, ebx
0x18000b2a6  jmp     loc_18000B3A5
0x18000b2ab  mov     rcx, [rbp+1C8h]; this
0x18000b2b2  lea     r8, aOnecoreAdminAp_7; "onecore\\admin\\appmodel\\common\\packa"...
0x18000b2b9  mov     r9d, eax; char *
0x18000b2bc  mov     edx, 22h ; '"'; void *
0x18000b2c1  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18000b2c6  mov     ebx, eax
0x18000b2c8  test    eax, eax
0x18000b2ca  jns     loc_18000AFBA
0x18000b2d0  mov     rcx, [rbp+1C8h]; this
0x18000b2d7  lea     r8, aOnecoreAdminAp_7; "onecore\\admin\\appmodel\\common\\packa"...
0x18000b2de  mov     r9d, eax; char *
0x18000b2e1  mov     edx, 32h ; '2'; void *
0x18000b2e6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000b2eb  mov     rcx, [rbp+1C8h]; this
0x18000b2f2  lea     r8, aOnecoreAdminAp_8; "onecore\\admin\\appmodel\\appxalluserst"...
0x18000b2f9  mov     r9d, ebx; char *
0x18000b2fc  mov     edx, 746h; void *
0x18000b301  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18000b306  mov     edx, 1; unsigned int
0x18000b30b  mov     rcx, rsi; this
0x18000b30e  call    ??_GStringBuffer@Common@@QEAAPEAXI@Z; Common::StringBuffer::`scalar deleting destructor'(uint)
0x18000b313  mov     eax, ebx
0x18000b315  jmp     loc_18000B3AD
0x18000b31a  lea     rax, [rsp+2C0h+var_268]
0x18000b31f  mov     dword ptr [rsp+2C0h+Data], r15d
0x18000b324  mov     [rsp+2C0h+lpcbData], rax; lpcbData
0x18000b329  lea     rdx, ValueName; "LastReturnValue"
0x18000b330  lea     rax, [rsp+2C0h+Data]
0x18000b335  mov     dword ptr [rsp+2C0h+var_260], r15d
0x18000b33a  xor     r9d, r9d; lpType
0x18000b33d  mov     [rsp+2C0h+phkResult], rax; lpData
0x18000b342  xor     r8d, r8d; lpReserved
0x18000b345  mov     dword ptr [rsp+2C0h+var_268], 4
0x18000b34d  call    cs:__imp_RegQueryValueExW
0x18000b353  test    eax, eax
0x18000b355  jle     short loc_18000B361
0x18000b357  movzx   eax, ax
0x18000b35a  or      eax, 80070000h
0x18000b35f  test    eax, eax
0x18000b361  js      short loc_18000B3DE
0x18000b363  cmp     dword ptr [rsp+2C0h+Data], r15d
0x18000b368  jnz     loc_18000B47C
0x18000b36e  xor     bl, bl
0x18000b370  cmp     [rbp+1C0h+arg_20], bl
0x18000b376  jnz     short loc_18000B3DE
0x18000b378  mov     rcx, [rsp+2C0h+hKey]; hKey
0x18000b37d  lea     rax, [rcx-1]
0x18000b381  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000b385  jbe     short loc_18000B3D6
0x18000b387  mov     [rsp+2C0h+hKey], r15
0x18000b38c  test    bl, bl
0x18000b38e  jnz     loc_18000B1A2
0x18000b394  mov     rcx, [rsp+2C0h+hKey]; hKey
0x18000b399  lea     rax, [rcx-1]
0x18000b39d  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000b3a1  jbe     short loc_18000B419
0x18000b3a3  xor     eax, eax
0x18000b3a5  mov     rdi, [rsp+2C0h+var_38]
0x18000b3ad  mov     rbx, [rsp+2C0h+var_30]
0x18000b3b5  mov     rcx, [rbp+1C0h+var_50]
0x18000b3bc  xor     rcx, rsp; StackCookie
0x18000b3bf  call    __security_check_cookie
0x18000b3c4  add     rsp, 298h
0x18000b3cb  pop     r15
0x18000b3cd  pop     r14
0x18000b3cf  pop     r13
0x18000b3d1  pop     r12
0x18000b3d3  pop     rsi
0x18000b3d4  pop     rbp
0x18000b3d5  retn
0x18000b3d6  call    cs:__imp_RegCloseKey
0x18000b3dc  jmp     short loc_18000B387
0x18000b3de  mov     bl, 1
0x18000b3e0  jmp     short loc_18000B378
0x18000b3e2  mov     rcx, [rsp+2C0h+var_268]; hKey
0x18000b3e7  lea     rax, [rcx-1]
0x18000b3eb  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000b3ef  ja      short loc_18000B394
0x18000b3f1  call    cs:__imp_RegCloseKey
0x18000b3f7  jmp     short loc_18000B394
0x18000b3f9  mov     rcx, [rbp+1C8h]; this
0x18000b400  lea     r8, aOnecoreAdminAp_8; "onecore\\admin\\appmodel\\appxalluserst"...
0x18000b407  mov     r9d, eax; char *
0x18000b40a  mov     edx, 721h; void *
0x18000b40f  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18000b414  jmp     loc_18000B201
  ... truncated ...
```
