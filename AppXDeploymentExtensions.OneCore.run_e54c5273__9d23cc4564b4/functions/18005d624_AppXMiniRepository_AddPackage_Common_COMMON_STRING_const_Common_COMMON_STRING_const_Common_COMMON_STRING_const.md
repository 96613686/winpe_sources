# AppXMiniRepository::AddPackage(Common::COMMON_STRING const *,Common::COMMON_STRING const *,Common::COMMON_STRING const *,int,void * const,_SID_AND_ATTRIBUTES * const,ulong,AppXApplicationData const *,ulong,unsigned __int64,unsigned __int64)

- ea: `0x18005d624`
- end: `0x18005deb0`
- name: `?AddPackage@AppXMiniRepository@@QEAAJPEBUCOMMON_STRING@Common@@00HQEAXQEAU_SID_AND_ATTRIBUTES@@KPEBVAppXApplicationData@@K_K4@Z`
- size: `2188`
- prototype: `__int64 __fastcall(AppXMiniRepository *this, const struct Common::COMMON_STRING *, void **, const struct Common::COMMON_STRING *, int, PSID Sid, Common *, int, const struct AppXApplicationData *, unsigned int, unsigned __int64, unsigned __int64)`
- caller_count: `1`
- callee_count: `16`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18005d210`

## callees

- `0x18000e6e0`
- `0x1800138e0`
- `0x18005d624`
- `0x18005deb8`
- `0x18005ded4`
- `0x18005def0`
- `0x18005e090`
- `0x18005e5ec`
- `0x18005e938`
- `0x18005e98c`
- `0x1800603c0`
- `0x180098bf4`
- `0x1800a219c`
- `0x1800f0700`
- `0x1800f17a4`
- `0x1800f18d7`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005dc26`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005dc31`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005dc3c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005dc47`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005dca4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005dd01`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005ddbc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005ddc4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005ddcf`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005ddda`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005dde5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005dc26`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005dc31`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005dc3c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005dc47`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005dca4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005dd01`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005ddbc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005ddc4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005ddcf`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005ddda`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005dde5`
- `ntdll!RtlValidSid` at `0x18005d774`
- `ntdll!RtlValidSid` at `0x18005d774`
- `ntdll!RtlLengthSid` at `0x18005d762`
- `ntdll!RtlLengthSid` at `0x18005d7c3`
- `ntdll!RtlLengthSid` at `0x18005d762`
- `ntdll!RtlLengthSid` at `0x18005d7c3`

## string_xrefs

- `0x18005d7db`: `PackageSid`
- `0x18005d8eb`: `CapabilitySids`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall AppXMiniRepository::AddPackage(
        AppXMiniRepository *this,
        const struct Common::COMMON_STRING *a2,
        void **a3,
        const struct Common::COMMON_STRING *a4,
        int a5,
        PSID Sid,
        Common *a7,
        int a8,
        const struct AppXApplicationData *a9,
        unsigned int a10,
        unsigned __int64 a11,
        unsigned __int64 a12)
{
  void **v13; // r14
  unsigned int v16; // ebx
  void *v17; // rdx
  HKEY v18; // rcx
  unsigned __int64 v19; // r13
  __int64 v20; // rdx
  __int64 v21; // r9
  void *v22; // rdx
  void *v24; // rdx
  PSID v25; // r15
  int v26; // eax
  int v27; // eax
  ULONG cbData; // eax
  LSTATUS v29; // eax
  __int64 v30; // r8
  const unsigned __int16 *v31; // rdx
  const BYTE *v32; // rcx
  DWORD v33; // eax
  LSTATUS v34; // eax
  const BYTE *v35; // rcx
  DWORD v36; // eax
  LSTATUS v37; // eax
  LSTATUS v38; // eax
  LSTATUS v39; // eax
  const BYTE *v40; // rcx
  DWORD v41; // eax
  LSTATUS v42; // eax
  LSTATUS v43; // eax
  LSTATUS v44; // eax
  LSTATUS v45; // eax
  int PerApplicationData; // eax
  void *v47; // rdx
  unsigned __int64 v48; // rdx
  void *v49; // rdx
  HKEY v50; // rcx
  void *v51; // rdx
  int v52; // eax
  void *v53; // rdx
  unsigned __int64 v54; // rdx
  void *v55; // rdx
  HKEY v56; // rcx
  unsigned __int64 v57; // r9
  __int64 v58; // rdx
  int v59; // eax
  unsigned __int64 v60; // rdx
  void *v61; // rdx
  unsigned __int64 v62; // rdx
  void *v63; // rdx
  unsigned __int64 v64; // rdx
  void *v65; // rdx
  unsigned __int64 v66; // rdx
  void *v67; // rdx
  int v68; // eax
  int lpData; // [rsp+20h] [rbp-38h]
  int lpDataa; // [rsp+20h] [rbp-38h]
  int lpDatab; // [rsp+20h] [rbp-38h]
  int lpDatac; // [rsp+20h] [rbp-38h]
  int lpDatad; // [rsp+20h] [rbp-38h]
  int lpDatae; // [rsp+20h] [rbp-38h]
  BYTE Data[8]; // [rsp+30h] [rbp-28h] BYREF
  void *v76[2]; // [rsp+38h] [rbp-20h] BYREF
  int v77; // [rsp+48h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+40h]
  HKEY hKey; // [rsp+A0h] [rbp+48h] BYREF

  v13 = a3;
  hKey = 0;
  a7 = 0;
  if ( !*((_DWORD *)this + 8) )
  {
    v16 = -2147024891;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x29C,
      (unsigned int)"onecore\\base\\appmodel\\appxminirepository\\lib\\appxminirepository.cpp",
      (const char *)0x80070005LL,
      lpData);
    Common::AutoPtrSidRtlFreeSid(a7, v17);
    v18 = hKey;
    if ( (unsigned __int64)hKey - 1 > 0xFFFFFFFFFFFFFFFDuLL )
      return v16;
    goto LABEL_100;
  }
  if ( !a2 || !*(_DWORD *)a2 )
  {
    v16 = -2147024809;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x29F,
      (unsigned int)"onecore\\base\\appmodel\\appxminirepository\\lib\\appxminirepository.cpp",
      (const char *)0x80070057LL,
      lpData);
    Common::AutoPtrSidRtlFreeSid(a7, v24);
    v18 = hKey;
    if ( (unsigned __int64)hKey - 1 > 0xFFFFFFFFFFFFFFFDuLL )
      return v16;
    goto LABEL_100;
  }
  if ( !a3 || !*(_DWORD *)a3 )
  {
    v20 = 672;
    goto LABEL_13;
  }
  if ( !a4 || !*(_DWORD *)a4 )
  {
    v20 = 673;
    goto LABEL_13;
  }
  v19 = a11;
  if ( a11 < a12 )
  {
    v20 = 674;
LABEL_13:
    v16 = -2147024809;
    v21 = 2147942487LL;
LABEL_14:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v20,
      (unsigned int)"onecore\\base\\appmodel\\appxminirepository\\lib\\appxminirepository.cpp",
      (const char *)v21,
      lpData);
LABEL_15:
    Common::AutoPtrSidRtlFreeSid(a7, v22);
    Common::RegistryKey::~RegistryKey((Common::RegistryKey *)&hKey);
    return v16;
  }
  v25 = Sid;
  if ( !Sid )
  {
    v20 = 675;
    goto LABEL_13;
  }
  if ( RtlLengthSid(Sid) > 0x44 || !RtlValidSid(v25) )
  {
    v16 = -2147023559;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2A5,
      (unsigned int)"onecore\\base\\appmodel\\appxminirepository\\lib\\appxminirepository.cpp",
      (const char *)0x80070539LL,
      lpData);
    Common::AutoPtrSidRtlFreeSid(a7, v51);
    v18 = hKey;
    if ( (unsigned __int64)hKey - 1 > 0xFFFFFFFFFFFFFFFDuLL )
      return v16;
    goto LABEL_100;
  }
  if ( !a5 )
  {
    v52 = PackageSid::PackageSidToPackageCapabilitySid(v25, (PSID *)&a7);
    v16 = v52;
    if ( v52 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2BC,
        (unsigned int)"onecore\\base\\appmodel\\appxminirepository\\lib\\appxminirepository.cpp",
        (const char *)(unsigned int)v52,
        lpData);
      Common::AutoPtrSidRtlFreeSid(a7, v53);
      v18 = hKey;
      if ( (unsigned __int64)hKey - 1 > 0xFFFFFFFFFFFFFFFDuLL )
        return v16;
LABEL_100:
      RegCloseKey(v18);
      return v16;
    }
  }
  v26 = AppXMiniRepository::ValidatePerApplicationData(a9, a10);
  v16 = v26;
  if ( v26 < 0 )
  {
    v21 = (unsigned int)v26;
    v20 = 703;
    goto LABEL_14;
  }
  v27 = AppXMiniRepository::CreatePackageRootKey(this, a2, &hKey);
  v16 = v27;
  if ( v27 < 0 )
  {
    v21 = (unsigned int)v27;
    v20 = 706;
    goto LABEL_14;
  }
  cbData = RtlLengthSid(v25);
  v29 = RegSetValueExW_0(hKey, L"PackageSid", 0, 3u, (const BYTE *)v25, cbData);
  v16 = v29;
  if ( v29 > 0 )
    v16 = (unsigned __int16)v29 | 0x80070000;
  if ( (v16 & 0x80000000) != 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2CC,
      (unsigned int)"onecore\\base\\appmodel\\appxminirepository\\lib\\appxminirepository.cpp",
      (const char *)v16,
      lpDataa);
LABEL_121:
    AppXMiniRepository::RemovePackage(this, a2);
    goto LABEL_15;
  }
  *(_OWORD *)v76 = 0;
  v77 = 0;
  v30 = (unsigned int)(*(_DWORD *)v13 - 1);
  v31 = (const unsigned __int16 *)v13[1];
  if ( v31[v30] == 92 )
  {
    v59 = Common::StringBuffer::SetValue((Common::StringBuffer *)v76, v31, v30);
    v16 = v59;
    if ( v59 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2D3,
        (unsigned int)"onecore\\base\\appmodel\\appxminirepository\\lib\\appxminirepository.cpp",
        (const char *)(unsigned int)v59,
        lpDataa);
      if ( v76[1] )
        operator delete(v76[1], v60);
      AppXMiniRepository::RemovePackage(this, a2);
      Common::AutoPtrSidRtlFreeSid(a7, v61);
      v56 = hKey;
      if ( (unsigned __int64)hKey - 1 > 0xFFFFFFFFFFFFFFFDuLL )
        return v16;
LABEL_109:
      RegCloseKey(v56);
      return v16;
    }
    v13 = v76;
  }
  v32 = (const BYTE *)v13[1];
  if ( v32 )
    v33 = 2 * *(_DWORD *)v13 + 2;
  else
    v33 = 0;
  v34 = RegSetValueExW_0(hKey, L"PackageRootFolder", 0, 1u, v32, v33);
  v16 = v34;
  if ( v34 > 0 )
    v16 = (unsigned __int16)v34 | 0x80070000;
  if ( (v16 & 0x80000000) != 0 )
  {
    v57 = v16;
    v58 = 731;
    goto LABEL_120;
  }
  v35 = (const BYTE *)*((_QWORD *)a4 + 1);
  if ( v35 )
    v36 = 2 * *(_DWORD *)a4 + 2;
  else
    v36 = 0;
  v37 = RegSetValueExW_0(hKey, L"DisplayName", 0, 1u, v35, v36);
  v16 = v37;
  if ( v37 > 0 )
    v16 = (unsigned __int16)v37 | 0x80070000;
  if ( (v16 & 0x80000000) != 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2DE,
      (unsigned int)"onecore\\base\\appmodel\\appxminirepository\\lib\\appxminirepository.cpp",
      (const char *)v16,
      lpDatab);
    if ( v76[1] )
      operator delete(v76[1], v64);
    AppXMiniRepository::RemovePackage(this, a2);
    Common::AutoPtrSidRtlFreeSid(a7, v65);
    v56 = hKey;
    if ( (unsigned __int64)hKey - 1 > 0xFFFFFFFFFFFFFFFDuLL )
      return v16;
    goto LABEL_109;
  }
  v38 = RegDeleteValueW_0(hKey, L"CapabilityCount");
  v16 = v38;
  if ( v38 > 0 )
    v16 = (unsigned __int16)v38 | 0x80070000;
  if ( (int)(v16 + 0x80000000) >= 0 && v16 != -2147024894 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2E2,
      (unsigned int)"onecore\\base\\appmodel\\appxminirepository\\lib\\appxminirepository.cpp",
      (const char *)v16,
      lpDatab);
    if ( v76[1] )
      operator delete(v76[1], v54);
    AppXMiniRepository::RemovePackage(this, a2);
    Common::AutoPtrSidRtlFreeSid(a7, v55);
    v56 = hKey;
    if ( (unsigned __int64)hKey - 1 > 0xFFFFFFFFFFFFFFFDuLL )
      return v16;
    goto LABEL_109;
  }
  v39 = RegDeleteValueW_0(hKey, L"CapabilitySids");
  v16 = v39;
  if ( v39 > 0 )
    v16 = (unsigned __int16)v39 | 0x80070000;
  if ( ((v16 + 0x80000000) & 0x80000000) == 0 && v16 != -2147024894 )
  {
    v57 = v16;
    v58 = 741;
LABEL_120:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v58,
      (unsigned int)"onecore\\base\\appmodel\\appxminirepository\\lib\\appxminirepository.cpp",
      (const char *)v57,
      lpDatab);
    Common::StringBuffer::~StringBuffer((Common::StringBuffer *)v76);
    goto LABEL_121;
  }
  v40 = (const BYTE *)*((_QWORD *)a2 + 1);
  if ( v40 )
    v41 = 2 * *(_DWORD *)a2 + 2;
  else
    v41 = 0;
  v42 = RegSetValueExW_0(hKey, L"PackageID", 0, 1u, v40, v41);
  v16 = v42;
  if ( v42 > 0 )
    v16 = (unsigned __int16)v42 | 0x80070000;
  if ( (v16 & 0x80000000) != 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2E8,
      (unsigned int)"onecore\\base\\appmodel\\appxminirepository\\lib\\appxminirepository.cpp",
      (const char *)v16,
      lpDatac);
    if ( v76[1] )
      operator delete(v76[1], v62);
    AppXMiniRepository::RemovePackage(this, a2);
    Common::AutoPtrSidRtlFreeSid(a7, v63);
    v56 = hKey;
    if ( (unsigned __int64)hKey - 1 > 0xFFFFFFFFFFFFFFFDuLL )
      return v16;
    goto LABEL_109;
  }
  *(_QWORD *)Data = v19;
  v43 = RegSetValueExW_0(hKey, L"OSMaxVersionTested", 0, 0xBu, Data, 8u);
  v16 = v43;
  if ( v43 > 0 )
    v16 = (unsigned __int16)v43 | 0x80070000;
  if ( (v16 & 0x80000000) != 0 )
  {
    v57 = v16;
    v58 = 745;
    goto LABEL_120;
  }
  *(_QWORD *)Data = a12;
  v44 = RegSetValueExW_0(hKey, L"OSMinVersion", 0, 0xBu, Data, 8u);
  v16 = v44;
  if ( v44 > 0 )
    v16 = (unsigned __int16)v44 | 0x80070000;
  if ( (v16 & 0x80000000) != 0 )
  {
    v57 = v16;
    v58 = 746;
    goto LABEL_120;
  }
  a8 = 0;
  v45 = RegSetValueExW_0(hKey, L"CapabilityCount", 0, 4u, (const BYTE *)&a8, 4u);
  v16 = v45;
  if ( v45 > 0 )
    v16 = (unsigned __int16)v45 | 0x80070000;
  if ( (v16 & 0x80000000) != 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x19C,
      (unsigned int)"onecore\\base\\appmodel\\appxminirepository\\lib\\appxminirepository.cpp",
      (const char *)v16,
      lpDatad);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2EC,
      (unsigned int)"onecore\\base\\appmodel\\appxminirepository\\lib\\appxminirepository.cpp",
      (const char *)v16,
      lpDatae);
    if ( v76[1] )
      operator delete(v76[1], v66);
    AppXMiniRepository::RemovePackage(this, a2);
    Common::AutoPtrSidRtlFreeSid(a7, v67);
    v50 = hKey;
    if ( (unsigned __int64)hKey - 1 > 0xFFFFFFFFFFFFFFFDuLL )
      return v16;
LABEL_108:
    RegCloseKey(v50);
    return v16;
  }
  PerApplicationData = AppXMiniRepository::CreatePerApplicationData((struct Common::RegistryKey *)&hKey, a9, a10);
  v16 = PerApplicationData;
  if ( PerApplicationData < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2ED,
      (unsigned int)"onecore\\base\\appmodel\\appxminirepository\\lib\\appxminirepository.cpp",
      (const char *)(unsigned int)PerApplicationData,
      lpDatad);
    if ( v76[1] )
      operator delete(v76[1], v48);
    AppXMiniRepository::RemovePackage(this, a2);
    Common::AutoPtrSidRtlFreeSid(a7, v49);
    v50 = hKey;
    if ( (unsigned __int64)hKey - 1 > 0xFFFFFFFFFFFFFFFDuLL )
      return v16;
    goto LABEL_108;
  }
  if ( a5 )
  {
    a8 = 1;
    v68 = Common::RegistryKey::SetValue((Common::RegistryKey *)&hKey, L"Framework", &a8, 4u, 4u);
    v16 = v68;
    if ( v68 < 0 )
    {
      v57 = (unsigned int)v68;
      v58 = 753;
      goto LABEL_120;
    }
  }
  if ( v76[1] )
    operator delete(v76[1], (unsigned __int64)v47);
  Common::AutoPtrSidRtlFreeSid(a7, v47);
  if ( (unsigned __int64)hKey - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
    RegCloseKey(hKey);
  return 0;
}

```

## disassembly

```asm
0x18005d624  push    rbp
0x18005d626  push    rbx
0x18005d627  push    rsi
0x18005d628  push    rdi
0x18005d629  push    r12
0x18005d62b  push    r13
0x18005d62d  push    r14
0x18005d62f  push    r15
0x18005d631  mov     rbp, rsp
0x18005d634  sub     rsp, 58h
0x18005d638  mov     r12, r9
0x18005d63b  mov     r14, r8
0x18005d63e  mov     rdi, rdx
0x18005d641  mov     rsi, rcx
0x18005d644  xor     ebx, ebx
0x18005d646  mov     [rbp+hKey], rbx
0x18005d64a  mov     [rbp+arg_30], rbx
0x18005d64e  cmp     [rcx+20h], ebx
0x18005d651  jnz     short loc_18005D68E
0x18005d653  mov     rcx, [rbp+40h]; this
0x18005d657  mov     ebx, 80070005h
0x18005d65c  mov     r9d, ebx; char *
0x18005d65f  lea     r8, aOnecoreBaseApp_48; "onecore\\base\\appmodel\\appxminireposi"...
0x18005d666  mov     edx, 29Ch; void *
0x18005d66b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005d670  mov     rcx, [rbp+arg_30]; this
0x18005d674  call    ?AutoPtrSidRtlFreeSid@Common@@YAXPEAX@Z; Common::AutoPtrSidRtlFreeSid(void *)
0x18005d679  nop
0x18005d67a  mov     rcx, [rbp+hKey]; hKey
0x18005d67e  lea     rdx, [rcx-1]
0x18005d682  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x18005d686  jbe     loc_18005DD01
0x18005d68c  jmp     short loc_18005D6FD
0x18005d68e  test    rdi, rdi
0x18005d691  jz      short loc_18005D710
0x18005d693  cmp     [rdx], ebx
0x18005d695  jz      short loc_18005D710
0x18005d697  test    r14, r14
0x18005d69a  jz      loc_18005D74B
0x18005d6a0  cmp     [r8], ebx
0x18005d6a3  jz      loc_18005D74B
0x18005d6a9  test    r12, r12
0x18005d6ac  jz      short loc_18005D6CE
0x18005d6ae  cmp     [r9], ebx
0x18005d6b1  jz      short loc_18005D6CE
0x18005d6b3  mov     r13, [rbp+arg_50]
0x18005d6ba  cmp     r13, [rbp+arg_58]
0x18005d6c1  jnb     loc_18005D752
0x18005d6c7  mov     edx, 2A2h
0x18005d6cc  jmp     short loc_18005D6D3
0x18005d6ce  mov     edx, 2A1h; void *
0x18005d6d3  mov     ebx, 80070057h
0x18005d6d8  mov     r9d, ebx; char *
0x18005d6db  lea     r8, aOnecoreBaseApp_48; "onecore\\base\\appmodel\\appxminireposi"...
0x18005d6e2  mov     rcx, [rbp+40h]; this
0x18005d6e6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005d6eb  mov     rcx, [rbp+arg_30]; this
0x18005d6ef  call    ?AutoPtrSidRtlFreeSid@Common@@YAXPEAX@Z; Common::AutoPtrSidRtlFreeSid(void *)
0x18005d6f4  lea     rcx, [rbp+hKey]; this
0x18005d6f8  call    ??1RegistryKey@Common@@QEAA@XZ; Common::RegistryKey::~RegistryKey(void)
0x18005d6fd  mov     eax, ebx
0x18005d6ff  add     rsp, 58h
0x18005d703  pop     r15
0x18005d705  pop     r14
0x18005d707  pop     r13
0x18005d709  pop     r12
0x18005d70b  pop     rdi
0x18005d70c  pop     rsi
0x18005d70d  pop     rbx
0x18005d70e  pop     rbp
0x18005d70f  retn
0x18005d710  mov     rcx, [rbp+40h]; this
0x18005d714  mov     ebx, 80070057h
0x18005d719  mov     r9d, ebx; char *
0x18005d71c  lea     r8, aOnecoreBaseApp_48; "onecore\\base\\appmodel\\appxminireposi"...
0x18005d723  mov     edx, 29Fh; void *
0x18005d728  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005d72d  mov     rcx, [rbp+arg_30]; this
0x18005d731  call    ?AutoPtrSidRtlFreeSid@Common@@YAXPEAX@Z; Common::AutoPtrSidRtlFreeSid(void *)
0x18005d736  nop
0x18005d737  mov     rcx, [rbp+hKey]; hKey
0x18005d73b  lea     rax, [rcx-1]
0x18005d73f  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18005d743  jbe     loc_18005DCA4
0x18005d749  jmp     short loc_18005D6FD
0x18005d74b  mov     edx, 2A0h
0x18005d750  jmp     short loc_18005D6D3
0x18005d752  mov     r15, [rbp+Sid]
0x18005d756  test    r15, r15
0x18005d759  jz      loc_18005DDF0
0x18005d75f  mov     rcx, r15; Sid
0x18005d762  call    cs:__imp_RtlLengthSid
0x18005d768  cmp     eax, 44h ; 'D'
0x18005d76b  ja      loc_18005DAA2
0x18005d771  mov     rcx, r15; Sid
0x18005d774  call    cs:__imp_RtlValidSid
0x18005d77a  test    al, al
0x18005d77c  jz      loc_18005DAA2
0x18005d782  cmp     [rbp+arg_20], ebx
0x18005d785  jz      loc_18005DAE0
0x18005d78b  mov     edx, [rbp+arg_48]; unsigned int
0x18005d791  mov     rcx, [rbp+arg_40]; struct AppXApplicationData *
0x18005d798  call    ?ValidatePerApplicationData@AppXMiniRepository@@CAJPEBVAppXApplicationData@@K@Z; AppXMiniRepository::ValidatePerApplicationData(AppXApplicationData const *,ulong)
0x18005d79d  mov     ebx, eax
0x18005d79f  test    eax, eax
0x18005d7a1  js      loc_18005DDFA
0x18005d7a7  lea     r8, [rbp+hKey]; struct Common::RegistryKey *
0x18005d7ab  mov     rdx, rdi; struct Common::COMMON_STRING *
0x18005d7ae  mov     rcx, rsi; this
0x18005d7b1  call    ?CreatePackageRootKey@AppXMiniRepository@@QEAAJPEBUCOMMON_STRING@Common@@AEAVRegistryKey@3@@Z; AppXMiniRepository::CreatePackageRootKey(Common::COMMON_STRING const *,Common::RegistryKey &)
0x18005d7b6  mov     ebx, eax
0x18005d7b8  test    eax, eax
0x18005d7ba  js      loc_18005DE07
0x18005d7c0  mov     rcx, r15; Sid
0x18005d7c3  call    cs:__imp_RtlLengthSid
0x18005d7c9  mov     [rsp+58h+cbData], eax; cbData
0x18005d7cd  mov     [rsp+58h+lpData], r15; int
0x18005d7d2  mov     r9d, 3; dwType
0x18005d7d8  xor     r8d, r8d; Reserved
0x18005d7db  lea     rdx, aPackagesid; "PackageSid"
0x18005d7e2  mov     rcx, [rbp+hKey]; hKey
0x18005d7e6  call    RegSetValueExW_0
0x18005d7eb  mov     ebx, eax
0x18005d7ed  xor     r15d, r15d
0x18005d7f0  test    eax, eax
0x18005d7f2  jle     short loc_18005D7FD
0x18005d7f4  movzx   ebx, ax
0x18005d7f7  or      ebx, 80070000h
0x18005d7fd  test    ebx, ebx
0x18005d7ff  js      loc_18005DE14
0x18005d805  xorps   xmm0, xmm0
0x18005d808  movups  xmmword ptr [rbp+var_20], xmm0
0x18005d80c  mov     [rbp+var_10], r15d
0x18005d810  mov     r8d, [r14]
0x18005d813  dec     r8d; unsigned int
0x18005d816  mov     rdx, [r14+8]; unsigned __int16 *
0x18005d81a  cmp     word ptr [rdx+r8*2], 5Ch ; '\'
0x18005d820  jz      loc_18005DC0E
0x18005d826  mov     rcx, [r14+8]
0x18005d82a  test    rcx, rcx
0x18005d82d  jnz     loc_18005DB2F
0x18005d833  mov     eax, r15d
0x18005d836  mov     [rsp+58h+cbData], eax; cbData
0x18005d83a  mov     [rsp+58h+lpData], rcx; lpData
0x18005d83f  mov     r14d, 1
0x18005d845  mov     r9d, r14d; dwType
0x18005d848  xor     r8d, r8d; Reserved
0x18005d84b  lea     rdx, aPackagerootfol; "PackageRootFolder"
0x18005d852  mov     rcx, [rbp+hKey]; hKey
0x18005d856  call    RegSetValueExW_0
0x18005d85b  mov     ebx, eax
0x18005d85d  test    eax, eax
0x18005d85f  jle     short loc_18005D86A
0x18005d861  movzx   ebx, ax
0x18005d864  or      ebx, 80070000h
0x18005d86a  test    ebx, ebx
0x18005d86c  js      loc_18005DE2E
0x18005d872  mov     rcx, [r12+8]
0x18005d877  test    rcx, rcx
0x18005d87a  jnz     loc_18005DB3E
0x18005d880  mov     eax, r15d
0x18005d883  mov     [rsp+58h+cbData], eax; cbData
0x18005d887  mov     [rsp+58h+lpData], rcx; int
0x18005d88c  mov     r9d, r14d; dwType
0x18005d88f  xor     r8d, r8d; Reserved
0x18005d892  lea     rdx, aDisplayname; "DisplayName"
0x18005d899  mov     rcx, [rbp+hKey]; hKey
0x18005d89d  call    RegSetValueExW_0
0x18005d8a2  mov     ebx, eax
0x18005d8a4  mov     r12d, 80070000h
0x18005d8aa  test    eax, eax
0x18005d8ac  jle     short loc_18005D8B4
0x18005d8ae  movzx   ebx, ax
0x18005d8b1  or      ebx, r12d
0x18005d8b4  test    ebx, ebx
0x18005d8b6  js      loc_18005DD0C
0x18005d8bc  lea     rdx, aCapabilitycoun; "CapabilityCount"
0x18005d8c3  mov     rcx, [rbp+hKey]; hKey
0x18005d8c7  call    RegDeleteValueW_0
0x18005d8cc  mov     ebx, eax
0x18005d8ce  test    eax, eax
0x18005d8d0  jle     short loc_18005D8D8
0x18005d8d2  movzx   ebx, ax
0x18005d8d5  or      ebx, r12d
0x18005d8d8  mov     r14d, 80000000h
0x18005d8de  lea     eax, [rbx+r14]
0x18005d8e2  test    r14d, eax
0x18005d8e5  jz      loc_18005DB97
0x18005d8eb  lea     rdx, aCapabilitysids; "CapabilitySids"
0x18005d8f2  mov     rcx, [rbp+hKey]; hKey
0x18005d8f6  call    RegDeleteValueW_0
0x18005d8fb  mov     ebx, eax
0x18005d8fd  test    eax, eax
0x18005d8ff  jle     short loc_18005D907
0x18005d901  movzx   ebx, ax
0x18005d904  or      ebx, r12d
0x18005d907  lea     eax, [rbx+r14]
0x18005d90b  test    r14d, eax
0x18005d90e  jz      loc_18005DBF5
0x18005d914  mov     rcx, [rdi+8]
0x18005d918  test    rcx, rcx
0x18005d91b  jnz     loc_18005DB4E
0x18005d921  mov     eax, r15d
0x18005d924  mov     [rsp+58h+cbData], eax; cbData
0x18005d928  mov     [rsp+58h+lpData], rcx; int
0x18005d92d  mov     r9d, 1; dwType
0x18005d933  xor     r8d, r8d; Reserved
0x18005d936  lea     rdx, aPackageid; "PackageID"
0x18005d93d  mov     rcx, [rbp+hKey]; hKey
0x18005d941  call    RegSetValueExW_0
0x18005d946  mov     ebx, eax
0x18005d948  test    eax, eax
0x18005d94a  jle     short loc_18005D952
0x18005d94c  movzx   ebx, ax
0x18005d94f  or      ebx, r12d
0x18005d952  test    ebx, ebx
0x18005d954  js      loc_18005DCAF
0x18005d95a  mov     qword ptr [rbp+Data], r13
0x18005d95e  mov     r14d, 8
0x18005d964  mov     [rsp+58h+cbData], r14d; cbData
0x18005d969  lea     rax, [rbp+Data]
0x18005d96d  mov     [rsp+58h+lpData], rax; lpData
0x18005d972  lea     r13d, [r14+3]
0x18005d976  mov     r9d, r13d; dwType
0x18005d979  xor     r8d, r8d; Reserved
0x18005d97c  lea     rdx, aOsmaxversionte; "OSMaxVersionTested"
0x18005d983  mov     rcx, [rbp+hKey]; hKey
0x18005d987  call    RegSetValueExW_0
0x18005d98c  mov     ebx, eax
0x18005d98e  test    eax, eax
0x18005d990  jle     short loc_18005D998
0x18005d992  movzx   ebx, ax
0x18005d995  or      ebx, r12d
0x18005d998  test    ebx, ebx
0x18005d99a  js      loc_18005DE38
0x18005d9a0  mov     rax, [rbp+arg_58]
0x18005d9a7  mov     qword ptr [rbp+Data], rax
0x18005d9ab  mov     [rsp+58h+cbData], r14d; cbData
0x18005d9b0  lea     rax, [rbp+Data]
0x18005d9b4  mov     [rsp+58h+lpData], rax; lpData
0x18005d9b9  mov     r9d, r13d; dwType
0x18005d9bc  xor     r8d, r8d; Reserved
0x18005d9bf  lea     rdx, aOsminversion; "OSMinVersion"
0x18005d9c6  mov     rcx, [rbp+hKey]; hKey
0x18005d9ca  call    RegSetValueExW_0
0x18005d9cf  mov     ebx, eax
0x18005d9d1  test    eax, eax
0x18005d9d3  jle     short loc_18005D9DB
0x18005d9d5  movzx   ebx, ax
0x18005d9d8  or      ebx, r12d
0x18005d9db  test    ebx, ebx
0x18005d9dd  js      loc_18005DE42
0x18005d9e3  mov     [rbp+arg_38], r15d
0x18005d9ea  mov     r14d, 4
0x18005d9f0  mov     [rsp+58h+cbData], r14d; cbData
0x18005d9f5  lea     rax, [rbp+arg_38]
0x18005d9fc  mov     [rsp+58h+lpData], rax; int
0x18005da01  mov     r9d, r14d; dwType
0x18005da04  xor     r8d, r8d; Reserved
0x18005da07  lea     rdx, aCapabilitycoun; "CapabilityCount"
0x18005da0e  mov     rcx, [rbp+hKey]; hKey
0x18005da12  call    RegSetValueExW_0
0x18005da17  mov     ebx, eax
0x18005da19  test    eax, eax
0x18005da1b  jle     short loc_18005DA23
0x18005da1d  movzx   ebx, ax
0x18005da20  or      ebx, r12d
0x18005da23  mov     rcx, [rbp+40h]; this
0x18005da27  test    ebx, ebx
0x18005da29  js      loc_18005DD5A
0x18005da2f  mov     r8d, [rbp+arg_48]; unsigned int
0x18005da36  mov     rdx, [rbp+arg_40]; struct AppXApplicationData *
0x18005da3d  lea     rcx, [rbp+hKey]; this
0x18005da41  call    ?CreatePerApplicationData@AppXMiniRepository@@CAJAEAVRegistryKey@Common@@PEBVAppXApplicationData@@K@Z; AppXMiniRepository::CreatePerApplicationData(Common::RegistryKey &,AppXApplicationData const *,ulong)
0x18005da46  mov     ebx, eax
0x18005da48  test    eax, eax
0x18005da4a  jns     loc_18005DB5C
0x18005da50  mov     rcx, [rbp+40h]; this
0x18005da54  mov     r9d, eax; char *
0x18005da57  lea     r8, aOnecoreBaseApp_48; "onecore\\base\\appmodel\\appxminireposi"...
0x18005da5e  mov     edx, 2EDh; void *
0x18005da63  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005da68  mov     rcx, [rbp+var_20+8]; void *
0x18005da6c  test    rcx, rcx
0x18005da6f  jz      short loc_18005DA76
0x18005da71  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18005da76  mov     rdx, rdi; struct Common::COMMON_STRING *
0x18005da79  mov     rcx, rsi; this
0x18005da7c  call    ?RemovePackage@AppXMiniRepository@@QEAAJPEBUCOMMON_STRING@Common@@@Z; AppXMiniRepository::RemovePackage(Common::COMMON_STRING const *)
0x18005da81  mov     rcx, [rbp+arg_30]; this
0x18005da85  call    ?AutoPtrSidRtlFreeSid@Common@@YAXPEAX@Z; Common::AutoPtrSidRtlFreeSid(void *)
0x18005da8a  nop
0x18005da8b  mov     rcx, [rbp+hKey]; hKey
0x18005da8f  lea     rax, [rcx-1]
0x18005da93  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18005da97  jbe     loc_18005DC26
0x18005da9d  jmp     loc_18005D6FD
0x18005daa2  mov     rcx, [rbp+40h]; this
0x18005daa6  mov     ebx, 80070539h
0x18005daab  mov     r9d, ebx; char *
  ... truncated ...
```
