# SystemSettings::StorageSenseHandlers::UnusedApplicationItem::LoadLastUsedTimestamp(void * const &)

- ea: `0x180076b1c`
- end: `0x180076d59`
- name: `?LoadLastUsedTimestamp@UnusedApplicationItem@StorageSenseHandlers@SystemSettings@@QEAAJAEBQEAX@Z`
- size: `573`
- prototype: `__int64 __fastcall(SystemSettings::StorageSenseHandlers::UnusedApplicationItem *__hidden this, void *const *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18007890c`

## callees

- `0x180006e50`
- `0x180012374`
- `0x1800401cc`
- `0x18006ae84`
- `0x180076b1c`
- `0x1800a8a88`
- `0x1800b3504`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180076b5b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180076b5b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180076bb5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180076bb5`
- `api-ms-win-ham-apphistory-l1-1-0!HamQueryPackageUsageInfo` at `0x180076bf3`
- `api-ms-win-ham-apphistory-l1-1-0!HamQueryPackageUsageInfo` at `0x180076bf3`
- `api-ms-win-ham-apphistory-l1-1-0!HamQueryApplicationUsageInfo` at `0x180076c0f`
- `api-ms-win-ham-apphistory-l1-1-0!HamQueryApplicationUsageInfo` at `0x180076c0f`

## string_xrefs

- `0x180076b79`: `CleanupRecommendations`
- `0x180076c50`: `CleanupRecommendations`
- `0x180076b9a`: `onecoreuap\shell\coresettinghandlers\storagesense\lib\recommenderengine.cpp`

## pseudocode

```c
__int64 __fastcall SystemSettings::StorageSenseHandlers::UnusedApplicationItem::LoadLastUsedTimestamp(
        SystemSettings::StorageSenseHandlers::UnusedApplicationItem *this,
        void *const *a2)
{
  HSTRING *v2; // rsi
  SystemSettings::StorageSenseHandlers::CAppTileData *v5; // rbx
  int PackageFamilyName; // ebx
  int v8; // ecx
  int ApplicationUsageInfo; // eax
  int v10; // ebx
  struct _SYSTEMTIME *v11; // r8
  unsigned int InstallDate; // r10d
  PCWSTR StringRawBuffer; // [rsp+30h] [rbp-30h] BYREF
  _OWORD v14[2]; // [rsp+38h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+18h]

  v2 = (HSTRING *)((char *)this + 416);
  if ( !*((_QWORD *)this + 52) )
  {
    v5 = (SystemSettings::StorageSenseHandlers::CAppTileData *)*((_QWORD *)this + 30);
    WindowsDeleteString(0);
    *v2 = 0;
    PackageFamilyName = SystemSettings::StorageSenseHandlers::CAppTileData::GetPackageFamilyName(v5, v2);
    if ( PackageFamilyName < 0 )
    {
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        (void *)0x3BB,
        (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\storagesense\\lib\\recommenderengine.cpp",
        (const char *)(unsigned int)PackageFamilyName,
        (int)"%hs",
        "CleanupRecommendations");
      return (unsigned int)PackageFamilyName;
    }
  }
  StringRawBuffer = WindowsGetStringRawBuffer(*v2, 0);
  memset(v14, 0, sizeof(v14));
  CleanupRecommendationsLogger::ExecutionInfo<unsigned short const * &>(
    (wchar_t *)L"Querying Host Activity Manager (HAM) for app: %s",
    &StringRawBuffer);
  v8 = *(_DWORD *)(*((_QWORD *)this + 30) + 48LL);
  if ( v8 )
  {
    if ( v8 != 1 )
    {
      CleanupRecommendationsLogger::ExecutionInfo<unsigned short const * &>(
        (wchar_t *)L"Failed to query HAM for app: %s",
        &StringRawBuffer);
      return 2147942450LL;
    }
    ApplicationUsageInfo = HamQueryApplicationUsageInfo(StringRawBuffer, *a2, v14);
  }
  else
  {
    ApplicationUsageInfo = HamQueryPackageUsageInfo(StringRawBuffer, *a2, v14);
  }
  v10 = ApplicationUsageInfo;
  CleanupRecommendationsLogger::ExecutionInfo<unsigned short const * &>(
    (wchar_t *)L"Succeeded querying HAM for app: %s",
    &StringRawBuffer);
  if ( v10 >= 0 )
  {
    StringRawBuffer = (PCWSTR)*((_QWORD *)&v14[0] + 1);
    *((_BYTE *)this + 376) = 1;
    PackageFamilyName = SystemSettings::StorageSenseHandlers::RecommenderEngineUtils::FileTimeToLocalSystemTime(
                          (SystemSettings::StorageSenseHandlers::RecommenderEngineUtils *)&StringRawBuffer,
                          (const struct _FILETIME *)((char *)this + 378),
                          v11);
    if ( PackageFamilyName < 0 )
    {
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        (void *)0x3DE,
        (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\storagesense\\lib\\recommenderengine.cpp",
        (const char *)(unsigned int)PackageFamilyName,
        (int)"%hs",
        "CleanupRecommendations");
      return (unsigned int)PackageFamilyName;
    }
    *(_QWORD *)((char *)this + 386) = 0;
    return 0;
  }
  if ( v10 != -1073283070 )
    return (unsigned int)(v10 | 0x10000000);
  InstallDate = SystemSettings::StorageSenseHandlers::CPackageSizeSetting::GetInstallDate(this);
  if ( InstallDate )
  {
    *((_BYTE *)this + 376) = 0;
    *((_WORD *)this + 192) = InstallDate % 0x64;
    *((_WORD *)this + 190) = InstallDate / 0x64 % 0x64;
    *((_WORD *)this + 189) = InstallDate / 0x2710 % 0x2710;
    return 0;
  }
  return 2147950722LL;
}

```

## disassembly

```asm
0x180076b1c  mov     [rsp-18h+arg_10], rbx
0x180076b21  mov     [rsp-18h+arg_18], rsi
0x180076b26  push    rbp
0x180076b27  push    rdi
0x180076b28  push    r14
0x180076b2a  mov     rbp, rsp
0x180076b2d  sub     rsp, 60h
0x180076b31  mov     rax, cs:__security_cookie
0x180076b38  xor     rax, rsp
0x180076b3b  mov     [rbp+var_8], rax
0x180076b3f  lea     rsi, [rcx+1A0h]
0x180076b46  mov     r14, rdx
0x180076b49  cmp     qword ptr [rsi], 0
0x180076b4d  mov     rdi, rcx
0x180076b50  jnz     short loc_180076BB0
0x180076b52  mov     rbx, [rcx+0F0h]
0x180076b59  xor     ecx, ecx; string
0x180076b5b  call    cs:__imp_WindowsDeleteString
0x180076b61  mov     rdx, rsi; HSTRING *
0x180076b64  mov     qword ptr [rsi], 0
0x180076b6b  mov     rcx, rbx; this
0x180076b6e  call    ?GetPackageFamilyName@CAppTileData@StorageSenseHandlers@SystemSettings@@QEAAJPEAPEAUHSTRING__@@@Z; SystemSettings::StorageSenseHandlers::CAppTileData::GetPackageFamilyName(HSTRING__ * *)
0x180076b73  mov     ebx, eax
0x180076b75  test    eax, eax
0x180076b77  jns     short loc_180076BB0
0x180076b79  lea     rdx, aCleanuprecomme; "CleanupRecommendations"
0x180076b80  mov     [rsp+60h+var_38], rdx; char *
0x180076b85  lea     rdx, aHs; "%hs"
0x180076b8c  mov     qword ptr [rsp+60h+var_40], rdx; int
0x180076b91  mov     edx, 3BBh; void *
0x180076b96  mov     rcx, [rbp+18h]; this
0x180076b9a  lea     r8, aOnecoreuapShel_26; "onecoreuap\\shell\\coresettinghandlers"...
0x180076ba1  mov     r9d, ebx; char *
0x180076ba4  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180076ba9  mov     eax, ebx
0x180076bab  jmp     loc_180076D38
0x180076bb0  mov     rcx, [rsi]; string
0x180076bb3  xor     edx, edx; length
0x180076bb5  call    cs:__imp_WindowsGetStringRawBuffer
0x180076bbb  xorps   xmm0, xmm0
0x180076bbe  lea     rdx, [rbp+var_30]
0x180076bc2  lea     rcx, aQueryingHostAc; "Querying Host Activity Manager (HAM) fo"...
0x180076bc9  mov     [rbp+var_30], rax
0x180076bcd  movups  [rbp+var_28], xmm0
0x180076bd1  movups  [rbp+var_18], xmm0
0x180076bd5  call    ??$ExecutionInfo@AEAPEBG@CleanupRecommendationsLogger@@SAXPEBGAEAPEBG@Z; CleanupRecommendationsLogger::ExecutionInfo<ushort const * &>(ushort const *,ushort const * &)
0x180076bda  mov     rax, [rdi+0F0h]
0x180076be1  mov     ecx, [rax+30h]
0x180076be4  test    ecx, ecx
0x180076be6  jnz     short loc_180076BFB
0x180076be8  mov     rdx, [r14]
0x180076beb  lea     r8, [rbp+var_28]
0x180076bef  mov     rcx, [rbp+var_30]
0x180076bf3  call    cs:__imp_HamQueryPackageUsageInfo
0x180076bf9  jmp     short loc_180076C15
0x180076bfb  cmp     ecx, 1
0x180076bfe  jnz     loc_180076D23
0x180076c04  mov     rdx, [r14]
0x180076c07  lea     r8, [rbp+var_28]
0x180076c0b  mov     rcx, [rbp+var_30]
0x180076c0f  call    cs:__imp_HamQueryApplicationUsageInfo
0x180076c15  lea     rdx, [rbp+var_30]
0x180076c19  mov     ebx, eax
0x180076c1b  lea     rcx, aSucceededQuery; "Succeeded querying HAM for app: %s"
0x180076c22  call    ??$ExecutionInfo@AEAPEBG@CleanupRecommendationsLogger@@SAXPEBGAEAPEBG@Z; CleanupRecommendationsLogger::ExecutionInfo<ushort const * &>(ushort const *,ushort const * &)
0x180076c27  test    ebx, ebx
0x180076c29  js      short loc_180076C80
0x180076c2b  mov     rax, qword ptr [rbp+var_28+8]
0x180076c2f  lea     rdx, [rdi+17Ah]; struct _FILETIME *
0x180076c36  lea     rcx, [rbp+var_30]; this
0x180076c3a  mov     [rbp+var_30], rax
0x180076c3e  mov     byte ptr [rdi+178h], 1
0x180076c45  call    ?FileTimeToLocalSystemTime@RecommenderEngineUtils@StorageSenseHandlers@SystemSettings@@YAJPEBU_FILETIME@@PEAU_SYSTEMTIME@@@Z; SystemSettings::StorageSenseHandlers::RecommenderEngineUtils::FileTimeToLocalSystemTime(_FILETIME const *,_SYSTEMTIME *)
0x180076c4a  mov     ebx, eax
0x180076c4c  test    eax, eax
0x180076c4e  jns     short loc_180076C72
0x180076c50  lea     rdx, aCleanuprecomme; "CleanupRecommendations"
0x180076c57  mov     [rsp+60h+var_38], rdx
0x180076c5c  lea     rdx, aHs; "%hs"
0x180076c63  mov     qword ptr [rsp+60h+var_40], rdx
0x180076c68  mov     edx, 3DEh
0x180076c6d  jmp     loc_180076B96
0x180076c72  xor     eax, eax
0x180076c74  mov     [rdi+182h], rax
0x180076c7b  jmp     loc_180076D0F
0x180076c80  cmp     ebx, 0C0070002h
0x180076c86  jnz     loc_180076D1A
0x180076c8c  mov     rcx, rdi; this
0x180076c8f  call    ?GetInstallDate@CPackageSizeSetting@StorageSenseHandlers@SystemSettings@@QEAAIXZ; SystemSettings::StorageSenseHandlers::CPackageSizeSetting::GetInstallDate(void)
0x180076c94  mov     r10d, eax
0x180076c97  test    eax, eax
0x180076c99  jz      short loc_180076D13
0x180076c9b  mov     r11d, 51EB851Fh
0x180076ca1  mov     byte ptr [rdi+178h], 0
0x180076ca8  mov     eax, r11d
0x180076cab  mul     r10d
0x180076cae  mov     eax, r11d
0x180076cb1  mov     r9d, edx
0x180076cb4  shr     r9d, 5
0x180076cb8  mul     r9d
0x180076cbb  movzx   ecx, r9w
0x180076cbf  imul    r8d, ecx, 64h ; 'd'
0x180076cc3  movzx   ecx, r10w
0x180076cc7  shr     edx, 5
0x180076cca  movzx   eax, dx
0x180076ccd  sub     cx, r8w
0x180076cd1  mov     r8d, 0D1B71759h
0x180076cd7  mov     [rdi+180h], cx
0x180076cde  imul    ecx, eax, 64h ; 'd'
0x180076ce1  mov     eax, r8d
0x180076ce4  mul     r10d
0x180076ce7  sub     r9w, cx
0x180076ceb  mov     eax, r8d
0x180076cee  mov     ecx, edx
0x180076cf0  mov     [rdi+17Ch], r9w
0x180076cf8  shr     ecx, 0Dh
0x180076cfb  mul     ecx
0x180076cfd  shr     edx, 0Dh
0x180076d00  imul    eax, edx, 2710h
0x180076d06  sub     ecx, eax
0x180076d08  mov     [rdi+17Ah], cx
0x180076d0f  xor     eax, eax
0x180076d11  jmp     short loc_180076D38
0x180076d13  mov     eax, 80072082h
0x180076d18  jmp     short loc_180076D38
0x180076d1a  bts     ebx, 1Ch
0x180076d1e  jmp     loc_180076BA9
0x180076d23  lea     rdx, [rbp+var_30]
0x180076d27  lea     rcx, aFailedToQueryH; "Failed to query HAM for app: %s"
0x180076d2e  call    ??$ExecutionInfo@AEAPEBG@CleanupRecommendationsLogger@@SAXPEBGAEAPEBG@Z; CleanupRecommendationsLogger::ExecutionInfo<ushort const * &>(ushort const *,ushort const * &)
0x180076d33  mov     eax, 80070032h
0x180076d38  mov     rcx, [rbp+var_8]
0x180076d3c  xor     rcx, rsp; StackCookie
0x180076d3f  call    __security_check_cookie
0x180076d44  lea     r11, [rsp+60h+var_s0]
0x180076d49  mov     rbx, [r11+30h]
0x180076d4d  mov     rsi, [r11+38h]
0x180076d51  mov     rsp, r11
0x180076d54  pop     r14
0x180076d56  pop     rdi
0x180076d57  pop     rbp
0x180076d58  retn
```
