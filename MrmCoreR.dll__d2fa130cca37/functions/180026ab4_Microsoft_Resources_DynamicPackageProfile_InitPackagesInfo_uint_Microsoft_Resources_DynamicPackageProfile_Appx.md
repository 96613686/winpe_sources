# Microsoft::Resources::DynamicPackageProfile::InitPackagesInfo(uint,Microsoft::Resources::DynamicPackageProfile::AppxPackageInfo * *,Microsoft::Resources::DynamicPackageProfile::AppxPackageInfo * * *,int *)

- ea: `0x180026ab4`
- end: `0x1800270bd`
- name: `?InitPackagesInfo@DynamicPackageProfile@Resources@Microsoft@@IEAAJIPEAPEAVAppxPackageInfo@123@PEAPEAPEAV4123@PEAH@Z`
- size: `1545`
- prototype: `__int64 __fastcall(Microsoft::Resources::DynamicPackageProfile *__hidden this, unsigned int, struct Microsoft::Resources::DynamicPackageProfile::AppxPackageInfo **, struct Microsoft::Resources::DynamicPackageProfile::AppxPackageInfo ***, int *)`
- caller_count: `1`
- callee_count: `14`
- tags: `broker_com_uri`

## callers

- `0x180056724`

## callees

- `0x18001b738`
- `0x18001fe28`
- `0x180024464`
- `0x180026ab4`
- `0x180027270`
- `0x180028510`
- `0x180028ad0`
- `0x18002c8d0`
- `0x18002ec70`
- `0x180030c6c`
- `0x180083978`
- `0x1800862f0`
- `0x180086f7c`
- `0x18008a6a4`

## import_xrefs

- `KERNELBASE!GetCurrentPackageFullName` at `0x180026b3d`
- `KERNELBASE!GetCurrentPackageFullName` at `0x180026b3d`
- `KERNELBASE!GetCurrentPackageInfo2` at `0x180026b7e`
- `KERNELBASE!GetCurrentPackageInfo2` at `0x180026c85`
- `KERNELBASE!GetCurrentPackageInfo2` at `0x180026b7e`
- `KERNELBASE!GetCurrentPackageInfo2` at `0x180026c85`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180026bf1`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180026c54`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180026bf1`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180026c54`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180026bdc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180026c3f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180026f5c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002700e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002703a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800c15ba`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180026bdc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180026c3f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180026f5c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002700e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002703a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800c15ba`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180026f6a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002701c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180027048`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800c15c8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180026f6a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002701c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180027048`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800c15c8`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180026dc9`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180026e41`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180026dc9`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180026e41`

## pseudocode

```c
__int64 __fastcall Microsoft::Resources::DynamicPackageProfile::InitPackagesInfo(
        Microsoft::Resources::DynamicPackageProfile *this,
        unsigned int a2,
        struct Microsoft::Resources::DynamicPackageProfile::AppxPackageInfo **a3,
        struct Microsoft::Resources::DynamicPackageProfile::AppxPackageInfo ***a4,
        int *a5)
{
  unsigned int v7; // r13d
  LPCWCH **v8; // rcx
  __int64 v9; // rdx
  __int64 result; // rax
  int v11; // ebx
  __int64 v12; // rsi
  int v13; // edi
  HANDLE ProcessHeap; // rax
  SIZE_T v15; // r8
  void *v16; // rdi
  __int64 v17; // rsi
  HANDLE v18; // rax
  SIZE_T v19; // r8
  Microsoft::Resources *v20; // rsi
  unsigned int CurrentPackageInfo2; // eax
  void *v22; // rdx
  Microsoft::Resources *v23; // r15
  int v24; // r12d
  Microsoft::Resources::StringResult *v25; // rax
  Microsoft::Resources::StringResult *v26; // r14
  __int64 v27; // rax
  __int64 v28; // rcx
  int v29; // r15d
  unsigned __int16 *v30; // rcx
  __int64 v31; // rax
  int v32; // eax
  int *v33; // r13
  __int64 v34; // r14
  unsigned int v35; // r15d
  _QWORD *v36; // rsi
  unsigned int k; // r13d
  const WCHAR *Ref; // rax
  LPCWCH v39; // r8
  int v40; // eax
  LPCWCH *v41; // r13
  Microsoft::Resources::DynamicPackageProfile::AppxPackageInfo *v42; // rcx
  void *v43; // rbx
  void *v44; // rdx
  unsigned int v45; // edx
  HANDLE v46; // rax
  __int64 v47; // rdx
  unsigned int v48; // edx
  void *v49; // rdx
  unsigned int v50; // edx
  unsigned int v51; // ebx
  void *v52; // rdx
  HANDLE v53; // rax
  __int64 m; // rcx
  HANDLE v55; // rax
  int j; // esi
  int i; // esi
  Microsoft::Resources::DynamicPackageProfile::AppxPackageInfo *v58; // rcx
  HANDLE v59; // rax
  Microsoft::Resources::DynamicPackageProfile::AppxPackageInfo *v60; // rcx
  unsigned int *bIgnoreCase; // [rsp+20h] [rbp-E0h]
  int bIgnoreCasea; // [rsp+20h] [rbp-E0h]
  LPCWCH *v63; // [rsp+30h] [rbp-D0h] BYREF
  int v64; // [rsp+38h] [rbp-C8h] BYREF
  unsigned int v65; // [rsp+3Ch] [rbp-C4h] BYREF
  unsigned int v66; // [rsp+40h] [rbp-C0h] BYREF
  LONG CurrentPackageFullName; // [rsp+44h] [rbp-BCh]
  Microsoft::Resources *v68; // [rsp+48h] [rbp-B8h]
  UINT32 packageFullNameLength; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int v70; // [rsp+54h] [rbp-ACh] BYREF
  int v71; // [rsp+58h] [rbp-A8h]
  Microsoft::Resources::DynamicPackageProfile *v72; // [rsp+60h] [rbp-A0h]
  Microsoft::Resources *v73; // [rsp+68h] [rbp-98h]
  unsigned __int16 *v74; // [rsp+70h] [rbp-90h]
  int *v75; // [rsp+78h] [rbp-88h]
  LPVOID lpMem; // [rsp+80h] [rbp-80h]
  struct Microsoft::Resources::DynamicPackageProfile::AppxPackageInfo ***v77; // [rsp+88h] [rbp-78h]
  WCHAR packageFullName[128]; // [rsp+90h] [rbp-70h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1E8h] [rbp+E8h]

  lpMem = a3;
  v72 = this;
  v7 = 0;
  v75 = a5;
  v64 = 0;
  v65 = 0;
  v77 = a4;
  memset_0(packageFullName, 0, sizeof(packageFullName));
  packageFullNameLength = 128;
  CurrentPackageFullName = 0;
  if ( !*((_BYTE *)this + 164) )
    CurrentPackageFullName = GetCurrentPackageFullName(&packageFullNameLength, packageFullName);
  v8 = &v63;
  v9 = 8;
  do
  {
    *(_BYTE *)v8 = 0;
    v8 = (LPCWCH **)((char *)v8 + 1);
    --v9;
  }
  while ( v9 );
  result = GetCurrentPackageInfo2(a2, 2, &v65);
  if ( (_DWORD)result != 122 )
  {
    if ( !(_DWORD)result )
      return 2147500036LL;
    if ( (int)result > 0 )
      return (unsigned __int16)result | 0x80070000;
    return result;
  }
  v66 = v65;
  v70 = v64;
  v63 = 0;
  if ( !is_mul_ok((unsigned int)v64, 8u) || !(8LL * (unsigned int)v64) )
    goto LABEL_55;
  v63 = 0;
  v11 = -2147024362;
  v12 = 8LL * (unsigned int)v64;
  if ( is_mul_ok((unsigned int)v64, 8u) )
  {
    v13 = 0;
  }
  else
  {
    v12 = -1;
    v13 = -2147024362;
  }
  ProcessHeap = GetProcessHeap();
  v15 = 0;
  if ( v13 >= 0 )
    v15 = v12;
  v16 = HeapAlloc(ProcessHeap, 8u, v15);
  if ( !v16 )
  {
LABEL_55:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x4EB,
      (unsigned int)"onecoreuap\\base\\mrt\\mrm\\src\\clientprofiles.cpp",
      (const char *)0x8007000ELL,
      (int)&v64);
    return 2147942414LL;
  }
  v63 = 0;
  if ( !is_mul_ok(v66, 1u) || !v66 )
    goto LABEL_53;
  v63 = 0;
  v17 = v66;
  if ( is_mul_ok(v66, 1u) )
    v11 = 0;
  else
    v17 = -1;
  v18 = GetProcessHeap();
  v19 = 0;
  if ( v11 >= 0 )
    v19 = v17;
  v68 = (Microsoft::Resources *)HeapAlloc(v18, 8u, v19);
  v20 = v68;
  if ( !v68 )
  {
LABEL_53:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x4F9,
      (unsigned int)"onecoreuap\\base\\mrt\\mrm\\src\\clientprofiles.cpp",
      (const char *)0x8007000ELL,
      (int)&v64);
LABEL_54:
    v46 = GetProcessHeap();
    HeapFree(v46, 0, v16);
    return 2147942414LL;
  }
  bIgnoreCase = &v70;
  CurrentPackageInfo2 = GetCurrentPackageInfo2(a2, 2, &v66);
  if ( CurrentPackageInfo2 )
  {
    v51 = wil::details::in1diag3::Return_Win32(
            retaddr,
            (void *)0x4FC,
            (unsigned int)"onecoreuap\\base\\mrt\\mrm\\src\\clientprofiles.cpp",
            (const char *)CurrentPackageInfo2,
            (unsigned int)&v70);
    Microsoft::Resources::DefFreeMemory(v20, v52);
    v53 = GetProcessHeap();
    HeapFree(v53, 0, v16);
    return v51;
  }
  else
  {
    v23 = v20;
    v73 = v20;
    v24 = 0;
    while ( v7 < v64 )
    {
      v25 = (Microsoft::Resources::StringResult *)Microsoft::Resources::DefObject::operator new[](0x68u);
      v26 = v25;
      if ( !v25 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x507,
          (unsigned int)"onecoreuap\\base\\mrt\\mrm\\src\\clientprofiles.cpp",
          (const char *)0x8007000ELL,
          (int)bIgnoreCase);
        Microsoft::Resources::DefFreeMemory(v20, v44);
        for ( i = 0; i < v24; ++i )
        {
          v60 = (Microsoft::Resources::DynamicPackageProfile::AppxPackageInfo *)*((_QWORD *)v16 + i);
          if ( v60 )
            Microsoft::Resources::DynamicPackageProfile::AppxPackageInfo::`scalar deleting destructor'(v60, v45);
        }
        goto LABEL_54;
      }
      Microsoft::Resources::StringResult::StringResult(v25);
      Microsoft::Resources::StringResult::StringResult((Microsoft::Resources::StringResult *)((char *)v26 + 32));
      Microsoft::Resources::StringResult::StringResult((Microsoft::Resources::StringResult *)((char *)v26 + 64));
      v27 = 80LL * v7;
      v71 = *(_DWORD *)((char *)v23 + v27 + 4);
      v74 = *(unsigned __int16 **)((char *)v23 + v27 + 8);
      v68 = *(Microsoft::Resources **)((char *)v23 + v27 + 48);
      v28 = *(_QWORD *)v26;
      v63 = (LPCWCH *)((char *)v23 + v27 + 16);
      v29 = DefStringResult_SetCopy(v28, *v63);
      if ( v29 < 0 )
      {
        v47 = 783;
        goto LABEL_57;
      }
      v29 = DefStringResult_SetCopy(*((_QWORD *)v26 + 4), v68);
      if ( v29 < 0 )
      {
        v47 = 784;
LABEL_57:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v47,
          (unsigned int)"onecoreuap\\base\\mrt\\mrm\\src\\clientprofiles.cpp",
          (const char *)(unsigned int)v29,
          (int)bIgnoreCase);
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x50A,
          (unsigned int)"onecoreuap\\base\\mrt\\mrm\\src\\clientprofiles.cpp",
          (const char *)(unsigned int)v29,
          bIgnoreCasea);
        Microsoft::Resources::DynamicPackageProfile::AppxPackageInfo::`scalar deleting destructor'(v26, v48);
        Microsoft::Resources::DefFreeMemory(v20, v49);
        for ( j = 0; j < v24; ++j )
        {
          v58 = (Microsoft::Resources::DynamicPackageProfile::AppxPackageInfo *)*((_QWORD *)v16 + j);
          if ( v58 )
            Microsoft::Resources::DynamicPackageProfile::AppxPackageInfo::`scalar deleting destructor'(v58, v50);
        }
        v59 = GetProcessHeap();
        HeapFree(v59, 0, v16);
        return (unsigned int)v29;
      }
      v29 = DefStringResult_SetCopy(*((_QWORD *)v26 + 8), v74);
      if ( v29 < 0 )
      {
        v47 = 785;
        goto LABEL_57;
      }
      v23 = v73;
      v30 = v74;
      v68 = v20;
      *((_DWORD *)v26 + 24) = v71;
      *((_BYTE *)v26 + 100) = Microsoft::Resources::IProfileHelpers::PathIsInSystemWindowsDirectory(v30);
      *((_BYTE *)v26 + 101) = 0;
      if ( !CurrentPackageFullName && *((_DWORD *)v72 + 40) == -1 && !*((_BYTE *)v72 + 164) )
      {
        v32 = CompareStringOrdinal(*v63, -1, packageFullName, -1, 1);
        if ( !(unsigned int)IntToComparison((unsigned int)(v32 - 2)) )
          *((_DWORD *)v72 + 40) = v7;
      }
      v31 = v7;
      ++v24;
      ++v7;
      *((_QWORD *)v16 + v31) = v26;
    }
    v33 = v75;
    v34 = 0;
    v35 = *v75;
    if ( *v75 )
    {
      v36 = lpMem;
      do
      {
        for ( k = v34; k < v24; ++k )
        {
          v63 = (LPCWCH *)k;
          Microsoft::Resources::StringResult::GetRef((Microsoft::Resources::StringResult *)(*((_QWORD *)v16 + k) + 32LL));
          Ref = Microsoft::Resources::StringResult::GetRef((Microsoft::Resources::StringResult *)(v36[v34] + 32LL));
          v40 = CompareStringOrdinal(Ref, -1, v39, -1, 0);
          if ( !(unsigned int)IntToComparison((unsigned int)(v40 - 2)) )
          {
            v41 = v63;
            v42 = (Microsoft::Resources::DynamicPackageProfile::AppxPackageInfo *)*((_QWORD *)v16 + (_QWORD)v63);
            if ( v42 )
              Microsoft::Resources::DynamicPackageProfile::AppxPackageInfo::`scalar deleting destructor'(
                v42,
                (unsigned int)v22);
            *((_QWORD *)v16 + (_QWORD)v41) = *((_QWORD *)v16 + v34);
            *((_QWORD *)v16 + v34) = v36[v34];
            v36[v34] = 0;
            break;
          }
        }
        v34 = (unsigned int)(v34 + 1);
      }
      while ( (unsigned int)v34 < v35 );
      v20 = v68;
      v33 = v75;
    }
    v43 = lpMem;
    if ( lpMem )
    {
      for ( m = 0; (unsigned int)m < v35; m = (unsigned int)(m + 1) )
      {
        if ( *((_QWORD *)lpMem + m) )
          wil::details::in1diag3::_FailFast_Unexpected(
            retaddr,
            (void *)0x53D,
            (unsigned int)"onecoreuap\\base\\mrt\\mrm\\src\\clientprofiles.cpp",
            (const char *)retaddr);
      }
      v55 = GetProcessHeap();
      HeapFree(v55, 0, v43);
    }
    *v77 = (struct Microsoft::Resources::DynamicPackageProfile::AppxPackageInfo **)v16;
    *v33 = v24;
    Microsoft::Resources::DefFreeMemory(v20, v22);
    *((_BYTE *)v72 + 164) = 1;
    return 0;
  }
}

```

## disassembly

```asm
0x180026ab4  push    rbp
0x180026ab6  push    rbx
0x180026ab7  push    rsi
0x180026ab8  push    rdi
0x180026ab9  push    r12
0x180026abb  push    r13
0x180026abd  push    r14
0x180026abf  push    r15
0x180026ac1  lea     rbp, [rsp-0A8h]
0x180026ac9  sub     rsp, 1A8h
0x180026ad0  mov     rax, cs:__security_cookie
0x180026ad7  xor     rax, rsp
0x180026ada  mov     [rbp+0E0h+var_50], rax
0x180026ae1  mov     rax, [rbp+0E0h+arg_20]
0x180026ae8  mov     r14d, edx
0x180026aeb  mov     [rbp+0E0h+lpMem], r8
0x180026aef  mov     rbx, rcx
0x180026af2  mov     [rsp+1E0h+var_180], rcx
0x180026af7  xor     r13d, r13d
0x180026afa  xor     edx, edx; Val
0x180026afc  mov     [rsp+1E0h+var_168], rax
0x180026b01  mov     r8d, 100h; Size
0x180026b07  mov     [rsp+1E0h+var_1A8], r13d
0x180026b0c  lea     rcx, [rbp+0E0h+packageFullName]; void *
0x180026b10  mov     [rsp+1E0h+var_1A4], r13d
0x180026b15  mov     [rbp+0E0h+var_158], r9
0x180026b19  call    memset_0
0x180026b1e  mov     [rsp+1E0h+packageFullNameLength], 80h
0x180026b26  mov     [rsp+1E0h+var_19C], r13d
0x180026b2b  cmp     [rbx+0A4h], r13b
0x180026b32  jnz     short loc_180026B47
0x180026b34  lea     rdx, [rbp+0E0h+packageFullName]; packageFullName
0x180026b38  lea     rcx, [rsp+1E0h+packageFullNameLength]; packageFullNameLength
0x180026b3d  call    cs:__imp_GetCurrentPackageFullName
0x180026b43  mov     [rsp+1E0h+var_19C], eax
0x180026b47  mov     r12d, 8
0x180026b4d  lea     rcx, [rsp+1E0h+var_1B0]
0x180026b52  mov     edx, r12d
0x180026b55  lea     r15d, [r12-7]
0x180026b5a  mov     [rcx], r13b
0x180026b5d  add     rcx, r15
0x180026b60  sub     rdx, r15
0x180026b63  jnz     short loc_180026B5A
0x180026b65  xor     r9d, r9d
0x180026b68  lea     rax, [rsp+1E0h+var_1A8]
0x180026b6d  lea     r8, [rsp+1E0h+var_1A4]
0x180026b72  mov     qword ptr [rsp+1E0h+bIgnoreCase], rax; int
0x180026b77  mov     ecx, r14d
0x180026b7a  lea     edx, [r9+2]
0x180026b7e  call    cs:__imp_GetCurrentPackageInfo2
0x180026b84  cmp     eax, 7Ah ; 'z'
0x180026b87  jnz     loc_180026EE9
0x180026b8d  mov     ecx, [rsp+1E0h+var_1A8]
0x180026b91  mov     eax, [rsp+1E0h+var_1A4]
0x180026b95  mov     r8d, ecx
0x180026b98  mov     [rsp+1E0h+var_1A0], eax
0x180026b9c  mov     rax, r12
0x180026b9f  mul     rcx
0x180026ba2  mov     [rsp+1E0h+var_18C], ecx
0x180026ba6  mov     [rsp+1E0h+var_1B0], r13
0x180026bab  test    rdx, rdx
0x180026bae  jnz     loc_180026F72
0x180026bb4  test    rax, rax
0x180026bb7  jz      loc_180026F72
0x180026bbd  mov     rax, r12
0x180026bc0  mov     [rsp+1E0h+var_1B0], r13
0x180026bc5  mul     r8
0x180026bc8  mov     ebx, 80070216h
0x180026bcd  mov     rsi, rax
0x180026bd0  test    rdx, rdx
0x180026bd3  jnz     loc_18002706A
0x180026bd9  mov     edi, r13d
0x180026bdc  call    cs:__imp_GetProcessHeap
0x180026be2  test    edi, edi
0x180026be4  mov     r8, r13
0x180026be7  mov     edx, r12d; dwFlags
0x180026bea  mov     rcx, rax; hHeap
0x180026bed  cmovns  r8, rsi; dwBytes
0x180026bf1  call    cs:__imp_HeapAlloc
0x180026bf7  mov     rdi, rax
0x180026bfa  test    rax, rax
0x180026bfd  jz      loc_180026F72
0x180026c03  mov     r8d, [rsp+1E0h+var_1A0]
0x180026c08  mov     rax, r15
0x180026c0b  mul     r8
0x180026c0e  mov     [rsp+1E0h+var_1B0], r13
0x180026c13  test    rdx, rdx
0x180026c16  jnz     loc_180026F3E
0x180026c1c  test    rax, rax
0x180026c1f  jz      loc_180026F3E
0x180026c25  mov     rax, r15
0x180026c28  mov     [rsp+1E0h+var_1B0], r13
0x180026c2d  mul     r8
0x180026c30  mov     rsi, rax
0x180026c33  test    rdx, rdx
0x180026c36  jnz     loc_180027075
0x180026c3c  mov     ebx, r13d
0x180026c3f  call    cs:__imp_GetProcessHeap
0x180026c45  test    ebx, ebx
0x180026c47  mov     r8, r13
0x180026c4a  mov     edx, r12d; dwFlags
0x180026c4d  mov     rcx, rax; hHeap
0x180026c50  cmovns  r8, rsi; dwBytes
0x180026c54  call    cs:__imp_HeapAlloc
0x180026c5a  mov     [rsp+1E0h+var_198], rax
0x180026c5f  mov     rsi, rax
0x180026c62  test    rax, rax
0x180026c65  jz      loc_180026F3E
0x180026c6b  lea     rax, [rsp+1E0h+var_18C]
0x180026c70  mov     r9, rsi
0x180026c73  lea     r8, [rsp+1E0h+var_1A0]
0x180026c78  mov     qword ptr [rsp+1E0h+bIgnoreCase], rax; unsigned int
0x180026c7d  mov     edx, 2
0x180026c82  mov     ecx, r14d
0x180026c85  call    cs:__imp_GetCurrentPackageInfo2
0x180026c8b  test    eax, eax
0x180026c8d  jnz     loc_180026FE9
0x180026c93  mov     r15, rsi
0x180026c96  mov     [rsp+1E0h+var_178], rsi
0x180026c9b  mov     r12d, r13d
0x180026c9e  cmp     r13d, [rsp+1E0h+var_1A8]
0x180026ca3  jnb     loc_180026DE9
0x180026ca9  mov     ecx, 68h ; 'h'; unsigned __int64
0x180026cae  call    ??_UDefObject@Resources@Microsoft@@SAPEAX_K@Z; Microsoft::Resources::DefObject::operator new[](unsigned __int64)
0x180026cb3  mov     r14, rax
0x180026cb6  test    rax, rax
0x180026cb9  jz      loc_180026EF4
0x180026cbf  mov     rcx, rax; this
0x180026cc2  call    ??0StringResult@Resources@Microsoft@@QEAA@XZ; Microsoft::Resources::StringResult::StringResult(void)
0x180026cc7  lea     rcx, [r14+20h]; this
0x180026ccb  call    ??0StringResult@Resources@Microsoft@@QEAA@XZ; Microsoft::Resources::StringResult::StringResult(void)
0x180026cd0  lea     rcx, [r14+40h]; this
0x180026cd4  call    ??0StringResult@Resources@Microsoft@@QEAA@XZ; Microsoft::Resources::StringResult::StringResult(void)
0x180026cd9  mov     eax, r13d
0x180026cdc  lea     rax, [rax+rax*4]
0x180026ce0  shl     rax, 4
0x180026ce4  mov     ecx, [rax+r15+4]
0x180026ce9  mov     [rsp+1E0h+var_188], ecx
0x180026ced  mov     rcx, [rax+r15+8]
0x180026cf2  mov     [rsp+1E0h+var_170], rcx
0x180026cf7  mov     rcx, [rax+r15+30h]
0x180026cfc  add     rax, 10h
0x180026d00  add     rax, r15
0x180026d03  mov     [rsp+1E0h+var_198], rcx
0x180026d08  mov     rcx, [r14]
0x180026d0b  mov     [rsp+1E0h+var_1B0], rax
0x180026d10  mov     rdx, [rax]
0x180026d13  call    DefStringResult_SetCopy
0x180026d18  mov     r15d, eax
0x180026d1b  test    eax, eax
0x180026d1d  js      loc_180026F92
0x180026d23  mov     rdx, [rsp+1E0h+var_198]
0x180026d28  mov     rcx, [r14+20h]
0x180026d2c  call    DefStringResult_SetCopy
0x180026d31  mov     r15d, eax
0x180026d34  test    eax, eax
0x180026d36  js      loc_18002707E
0x180026d3c  mov     rdx, [rsp+1E0h+var_170]
0x180026d41  mov     rcx, [r14+40h]
0x180026d45  call    DefStringResult_SetCopy
0x180026d4a  mov     r15d, eax
0x180026d4d  test    eax, eax
0x180026d4f  js      loc_180027029
0x180026d55  mov     eax, [rsp+1E0h+var_188]
0x180026d59  mov     r15, [rsp+1E0h+var_178]
0x180026d5e  mov     rcx, [rsp+1E0h+var_170]; unsigned __int16 *
0x180026d63  mov     [rsp+1E0h+var_178], r15
0x180026d68  mov     [rsp+1E0h+var_198], rsi
0x180026d6d  mov     [r14+60h], eax
0x180026d71  call    ?PathIsInSystemWindowsDirectory@IProfileHelpers@Resources@Microsoft@@SA_NPEBG@Z; Microsoft::Resources::IProfileHelpers::PathIsInSystemWindowsDirectory(ushort const *)
0x180026d76  xor     ecx, ecx
0x180026d78  mov     [r14+64h], al
0x180026d7c  mov     [r14+65h], cl
0x180026d80  cmp     [rsp+1E0h+var_19C], ecx
0x180026d84  jnz     short loc_180026D94
0x180026d86  mov     rax, [rsp+1E0h+var_180]
0x180026d8b  cmp     dword ptr [rax+0A0h], 0FFFFFFFFh
0x180026d92  jz      short loc_180026DA6
0x180026d94  mov     eax, r13d
0x180026d97  inc     r12d
0x180026d9a  inc     r13d
0x180026d9d  mov     [rdi+rax*8], r14
0x180026da1  jmp     loc_180026C9E
0x180026da6  cmp     [rax+0A4h], cl
0x180026dac  jnz     short loc_180026D94
0x180026dae  mov     rcx, [rsp+1E0h+var_1B0]
0x180026db3  lea     r8, [rbp+0E0h+packageFullName]; lpString2
0x180026db7  or      r9d, 0FFFFFFFFh; cchCount2
0x180026dbb  mov     [rsp+1E0h+bIgnoreCase], 1; bIgnoreCase
0x180026dc3  or      edx, r9d; cchCount1
0x180026dc6  mov     rcx, [rcx]; lpString1
0x180026dc9  call    cs:__imp_CompareStringOrdinal
0x180026dcf  lea     ecx, [rax-2]
0x180026dd2  call    _IntToComparison
0x180026dd7  test    eax, eax
0x180026dd9  jnz     short loc_180026D94
0x180026ddb  mov     rax, [rsp+1E0h+var_180]
0x180026de0  mov     [rax+0A0h], r13d
0x180026de7  jmp     short loc_180026D94
0x180026de9  mov     r13, [rsp+1E0h+var_168]
0x180026dee  xor     r14d, r14d
0x180026df1  mov     r15d, [r13+0]
0x180026df5  test    r15d, r15d
0x180026df8  jz      loc_180026E98
0x180026dfe  mov     rsi, [rbp+0E0h+lpMem]
0x180026e02  mov     r13d, r14d
0x180026e05  cmp     r13d, r12d
0x180026e08  jnb     short loc_180026E82
0x180026e0a  mov     eax, r13d
0x180026e0d  mov     [rsp+1E0h+var_1B0], rax
0x180026e12  mov     rcx, [rdi+rax*8]
0x180026e16  add     rcx, 20h ; ' '; this
0x180026e1a  call    ?GetRef@StringResult@Resources@Microsoft@@QEBAPEBGXZ; Microsoft::Resources::StringResult::GetRef(void)
0x180026e1f  mov     rcx, [rsi+r14*8]
0x180026e23  mov     r8, rax
0x180026e26  add     rcx, 20h ; ' '; this
0x180026e2a  call    ?GetRef@StringResult@Resources@Microsoft@@QEBAPEBGXZ; Microsoft::Resources::StringResult::GetRef(void)
0x180026e2f  or      r9d, 0FFFFFFFFh; cchCount2
0x180026e33  mov     [rsp+1E0h+bIgnoreCase], 0; bIgnoreCase
0x180026e3b  or      edx, r9d; cchCount1
0x180026e3e  mov     rcx, rax; lpString1
0x180026e41  call    cs:__imp_CompareStringOrdinal
0x180026e47  lea     ecx, [rax-2]
0x180026e4a  call    _IntToComparison
0x180026e4f  test    eax, eax
0x180026e51  jnz     loc_180026F36
0x180026e57  mov     r13, [rsp+1E0h+var_1B0]
0x180026e5c  mov     rcx, [rdi+r13*8]; this
0x180026e60  test    rcx, rcx
0x180026e63  jz      short loc_180026E6A
0x180026e65  call    ??_GAppxPackageInfo@DynamicPackageProfile@Resources@Microsoft@@QEAAPEAXI@Z; Microsoft::Resources::DynamicPackageProfile::AppxPackageInfo::`scalar deleting destructor'(uint)
0x180026e6a  mov     rax, [rdi+r14*8]
0x180026e6e  mov     [rdi+r13*8], rax
0x180026e72  mov     rax, [rsi+r14*8]
0x180026e76  mov     [rdi+r14*8], rax
0x180026e7a  mov     qword ptr [rsi+r14*8], 0
0x180026e82  inc     r14d
0x180026e85  cmp     r14d, r15d
0x180026e88  jb      loc_180026E02
0x180026e8e  mov     rsi, [rsp+1E0h+var_198]
0x180026e93  mov     r13, [rsp+1E0h+var_168]
0x180026e98  mov     rbx, [rbp+0E0h+lpMem]
0x180026e9c  test    rbx, rbx
0x180026e9f  jnz     loc_180027033
0x180026ea5  mov     rax, [rbp+0E0h+var_158]
0x180026ea9  mov     rcx, rsi; this
0x180026eac  mov     [rax], rdi
0x180026eaf  mov     [r13+0], r12d
0x180026eb3  call    ?DefFreeMemory@Resources@Microsoft@@YAXPEAX@Z; Microsoft::Resources::DefFreeMemory(void *)
0x180026eb8  mov     rax, [rsp+1E0h+var_180]
0x180026ebd  mov     byte ptr [rax+0A4h], 1
0x180026ec4  xor     eax, eax
0x180026ec6  mov     rcx, [rbp+0E0h+var_50]
0x180026ecd  xor     rcx, rsp; StackCookie
0x180026ed0  call    __security_check_cookie
0x180026ed5  add     rsp, 1A8h
0x180026edc  pop     r15
0x180026ede  pop     r14
0x180026ee0  pop     r13
0x180026ee2  pop     r12
0x180026ee4  pop     rdi
0x180026ee5  pop     rsi
0x180026ee6  pop     rbx
0x180026ee7  pop     rbp
0x180026ee8  retn
0x180026ee9  test    eax, eax
0x180026eeb  jnz     short loc_180026F2A
0x180026eed  mov     eax, 80004004h
0x180026ef2  jmp     short loc_180026EC6
0x180026ef4  mov     rcx, [rbp+0E8h]; this
0x180026efb  lea     r8, aOnecoreuapBase_7; "onecoreuap\\base\\mrt\\mrm\\src\\client"...
0x180026f02  mov     r9d, 8007000Eh; char *
0x180026f08  mov     edx, 507h; void *
0x180026f0d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180026f12  mov     rcx, rsi; this
0x180026f15  call    ?DefFreeMemory@Resources@Microsoft@@YAXPEAX@Z; Microsoft::Resources::DefFreeMemory(void *)
0x180026f1a  test    rdi, rdi
0x180026f1d  jnz     loc_180027098
0x180026f23  mov     eax, 8007000Eh
0x180026f28  jmp     short loc_180026EC6
0x180026f2a  jle     short loc_180026EC6
0x180026f2c  movzx   eax, ax
0x180026f2f  or      eax, 80070000h
0x180026f34  jmp     short loc_180026EC6
0x180026f36  inc     r13d
0x180026f39  jmp     loc_180026E05
0x180026f3e  mov     rcx, [rbp+0E8h]; this
0x180026f45  lea     r8, aOnecoreuapBase_7; "onecoreuap\\base\\mrt\\mrm\\src\\client"...
0x180026f4c  mov     r9d, 8007000Eh; char *
0x180026f52  mov     edx, 4F9h; void *
0x180026f57  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180026f5c  call    cs:__imp_GetProcessHeap
0x180026f62  mov     r8, rdi; lpMem
0x180026f65  xor     edx, edx; dwFlags
0x180026f67  mov     rcx, rax; hHeap
0x180026f6a  call    cs:__imp_HeapFree
0x180026f70  jmp     short loc_180026F23
0x180026f72  mov     rcx, [rbp+0E8h]; this
0x180026f79  lea     r8, aOnecoreuapBase_7; "onecoreuap\\base\\mrt\\mrm\\src\\client"...
0x180026f80  mov     r9d, 8007000Eh; char *
  ... truncated ...
```
