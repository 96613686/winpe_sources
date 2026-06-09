# SystemSettings::StorageSenseHandlers::CAppTerminateSetting::CreateInstance(Microsoft::WRL::ComPtr<SystemSettings::StorageSenseHandlers::CAppTileData>,SystemSettings::StorageSenseHandlers::CAppTerminateSetting * *)

- ea: `0x1800ca24c`
- end: `0x1800ca458`
- name: `?CreateInstance@CAppTerminateSetting@StorageSenseHandlers@SystemSettings@@SAJV?$ComPtr@VCAppTileData@StorageSenseHandlers@SystemSettings@@@WRL@Microsoft@@PEAPEAV123@@Z`
- size: `524`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800bc410`

## callees

- `0x180008ad4`
- `0x18000c964`
- `0x18000e6cc`
- `0x180034cd8`
- `0x1800a7c4c`
- `0x1800a8a88`
- `0x1800a8cb4`
- `0x1800a8ee4`
- `0x1800bdbe4`
- `0x1800c85bc`
- `0x1800ca24c`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800ca3df`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800ca40a`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800ca3df`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800ca40a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ca2a0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ca369`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ca3a6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ca420`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ca2a0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ca369`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ca3a6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ca420`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800ca322`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800ca3bc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800ca3f0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800ca322`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800ca3bc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800ca3f0`
- `ext-ms-win-appmodel-activation-l1-1-1!GetPackageExecutionContextForPackageByFullName` at `0x1800ca332`
- `ext-ms-win-appmodel-activation-l1-1-1!GetPackageExecutionContextForPackageByFullName` at `0x1800ca332`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall SystemSettings::StorageSenseHandlers::CAppTerminateSetting::CreateInstance(
        SystemSettings::StorageSenseHandlers::CAppTileData **a1,
        _QWORD *a2)
{
  __int64 v4; // rdi
  unsigned int v5; // ebx
  __int64 v6; // r9
  __int64 v7; // rdx
  SystemSettings::StorageSenseHandlers::CAppTileData *v8; // rbx
  HSTRING *v9; // r14
  int PackageFullName; // eax
  int IsLanguagePack; // eax
  PCWSTR v12; // rax
  SystemSettings::StorageSenseHandlers::CAppTileData *v13; // rbx
  int PackageFamilyName; // eax
  const WCHAR *StringRawBuffer; // rax
  const WCHAR *v16; // rax
  BOOL bIgnoreCase; // [rsp+20h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+28h]
  HSTRING string; // [rsp+68h] [rbp+38h] BYREF
  __int64 v21; // [rsp+70h] [rbp+40h] BYREF

  *a2 = 0;
  Microsoft::WRL::Details::Make<SystemSettings::StorageSenseHandlers::CAppTerminateSetting,>(&v21);
  v4 = v21;
  if ( v21 )
  {
    v8 = *a1;
    v9 = (HSTRING *)(v21 + 216);
    WindowsDeleteString(*(HSTRING *)(v21 + 216));
    *v9 = 0;
    PackageFullName = SystemSettings::StorageSenseHandlers::CAppTileData::GetPackageFullName(v8, (HSTRING *)(v4 + 216));
    v5 = PackageFullName;
    if ( PackageFullName >= 0 )
    {
      IsLanguagePack = SystemSettings::StorageSenseHandlers::CAppTileData::GetIsLanguagePack(
                         *a1,
                         (unsigned __int8 *)(v4 + 224));
      if ( IsLanguagePack < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0xC0,
          (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\storagesense\\lib\\appsetting.cpp",
          (const char *)(unsigned int)IsLanguagePack,
          bIgnoreCase);
      *(_DWORD *)(v4 + 228) = SystemSettings::StorageSenseHandlers::CAppTileData::GetPackageType(*a1);
      if ( !(unsigned __int8)IsGetPackageExecutionContextForPackageByFullNamePresent()
        || (v12 = WindowsGetStringRawBuffer(*v9, 0),
            PackageFullName = GetPackageExecutionContextForPackageByFullName(v12, v4 + 232),
            v5 = PackageFullName,
            PackageFullName >= 0) )
      {
        if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_56489269>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_56489269>::GetImpl'::`2'::impl) )
        {
          string = 0;
          v13 = *a1;
          WindowsDeleteString(0);
          string = 0;
          PackageFamilyName = SystemSettings::StorageSenseHandlers::CAppTileData::GetPackageFamilyName(v13, &string);
          v5 = PackageFamilyName;
          if ( PackageFamilyName < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0xCC,
              (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\storagesense\\lib\\appsetting.cpp",
              (const char *)(unsigned int)PackageFamilyName,
              bIgnoreCase);
            WindowsDeleteString(string);
            string = 0;
            goto LABEL_20;
          }
          StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
          if ( CompareStringOrdinal(StringRawBuffer, -1, L"MicrosoftWindows.Client.AIX_cw5n1h2txyewy", -1, 1) == 2
            || (v16 = WindowsGetStringRawBuffer(string, 0),
                CompareStringOrdinal(v16, -1, L"MicrosoftWindows.Client.CoreAI_cw5n1h2txyewy", -1, 1) == 2) )
          {
            *(_BYTE *)(v4 + 225) = 0;
          }
          WindowsDeleteString(string);
        }
        v21 = 0;
        *a2 = v4;
        v5 = 0;
        goto LABEL_20;
      }
      v7 = 198;
    }
    else
    {
      v7 = 191;
    }
    v6 = (unsigned int)PackageFullName;
  }
  else
  {
    v5 = -2147024882;
    v6 = 2147942414LL;
    v7 = 190;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v7,
    (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\storagesense\\lib\\appsetting.cpp",
    (const char *)v6,
    bIgnoreCase);
LABEL_20:
  Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v21);
  Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(a1);
  return v5;
}

```

## disassembly

```asm
0x1800ca24c  mov     [rsp-28h+arg_18], rbx
0x1800ca251  mov     [rsp-28h+arg_0], rcx
0x1800ca256  push    rbp
0x1800ca257  push    rsi
0x1800ca258  push    rdi
0x1800ca259  push    r14
0x1800ca25b  push    r15
0x1800ca25d  mov     rbp, rsp
0x1800ca260  sub     rsp, 30h
0x1800ca264  mov     r15, rdx
0x1800ca267  mov     rsi, rcx
0x1800ca26a  mov     qword ptr [rdx], 0
0x1800ca271  lea     rcx, [rbp+arg_10]
0x1800ca275  call    ??$Make@VCAppTerminateSetting@StorageSenseHandlers@SystemSettings@@$$V@Details@WRL@Microsoft@@YA?AV?$ComPtr@VCAppTerminateSetting@StorageSenseHandlers@SystemSettings@@@12@XZ; Microsoft::WRL::Details::Make<SystemSettings::StorageSenseHandlers::CAppTerminateSetting,>(void)
0x1800ca27a  nop
0x1800ca27b  mov     rdi, [rbp+arg_10]
0x1800ca27f  test    rdi, rdi
0x1800ca282  jnz     short loc_1800CA293
0x1800ca284  mov     ebx, 8007000Eh
0x1800ca289  mov     r9d, ebx
0x1800ca28c  mov     edx, 0BEh
0x1800ca291  jmp     short loc_1800CA2C6
0x1800ca293  mov     rbx, [rsi]
0x1800ca296  lea     r14, [rdi+0D8h]
0x1800ca29d  mov     rcx, [r14]; string
0x1800ca2a0  call    cs:__imp_WindowsDeleteString
0x1800ca2a6  mov     qword ptr [r14], 0
0x1800ca2ad  mov     rdx, r14; HSTRING *
0x1800ca2b0  mov     rcx, rbx; this
0x1800ca2b3  call    ?GetPackageFullName@CAppTileData@StorageSenseHandlers@SystemSettings@@QEAAJPEAPEAUHSTRING__@@@Z; SystemSettings::StorageSenseHandlers::CAppTileData::GetPackageFullName(HSTRING__ * *)
0x1800ca2b8  mov     ebx, eax
0x1800ca2ba  test    eax, eax
0x1800ca2bc  jns     short loc_1800CA2DB
0x1800ca2be  mov     edx, 0BFh; void *
0x1800ca2c3  mov     r9d, eax; char *
0x1800ca2c6  mov     rcx, [rbp+28h]; this
0x1800ca2ca  lea     r8, aOnecoreuapShel_27; "onecoreuap\\shell\\coresettinghandlers"...
0x1800ca2d1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ca2d6  jmp     loc_1800CA433
0x1800ca2db  lea     rdx, [rdi+0E0h]; unsigned __int8 *
0x1800ca2e2  mov     rcx, [rsi]; this
0x1800ca2e5  call    ?GetIsLanguagePack@CAppTileData@StorageSenseHandlers@SystemSettings@@QEAAJPEAE@Z; SystemSettings::StorageSenseHandlers::CAppTileData::GetIsLanguagePack(uchar *)
0x1800ca2ea  mov     rcx, [rbp+28h]; this
0x1800ca2ee  test    eax, eax
0x1800ca2f0  jns     short loc_1800CA306
0x1800ca2f2  mov     r9d, eax; char *
0x1800ca2f5  lea     r8, aOnecoreuapShel_27; "onecoreuap\\shell\\coresettinghandlers"...
0x1800ca2fc  mov     edx, 0C0h; void *
0x1800ca301  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800ca306  mov     rcx, [rsi]
0x1800ca309  call    ?GetPackageType@CAppTileData@StorageSenseHandlers@SystemSettings@@QEAA?AW4PackageType@StateRepository@Internal@Windows@@XZ; SystemSettings::StorageSenseHandlers::CAppTileData::GetPackageType(void)
0x1800ca30e  mov     [rdi+0E4h], eax
0x1800ca314  call    IsGetPackageExecutionContextForPackageByFullNamePresent
0x1800ca319  test    al, al
0x1800ca31b  jz      short loc_1800CA348
0x1800ca31d  xor     edx, edx; length
0x1800ca31f  mov     rcx, [r14]; string
0x1800ca322  call    cs:__imp_WindowsGetStringRawBuffer
0x1800ca328  lea     rdx, [rdi+0E8h]
0x1800ca32f  mov     rcx, rax
0x1800ca332  call    cs:__imp_GetPackageExecutionContextForPackageByFullName
0x1800ca338  mov     ebx, eax
0x1800ca33a  test    eax, eax
0x1800ca33c  jns     short loc_1800CA348
0x1800ca33e  mov     edx, 0C6h
0x1800ca343  jmp     loc_1800CA2C3
0x1800ca348  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_56489269@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_56489269@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_56489269> `wil::Feature<__WilFeatureTraits_Feature_56489269>::GetImpl(void)'::`2'::impl
0x1800ca34f  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_56489269@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_56489269>::__private_IsEnabled(void)
0x1800ca354  test    al, al
0x1800ca356  jz      loc_1800CA426
0x1800ca35c  mov     [rbp+string], 0
0x1800ca364  mov     rbx, [rsi]
0x1800ca367  xor     ecx, ecx; string
0x1800ca369  call    cs:__imp_WindowsDeleteString
0x1800ca36f  mov     [rbp+string], 0
0x1800ca377  lea     rdx, [rbp+string]; HSTRING *
0x1800ca37b  mov     rcx, rbx; this
0x1800ca37e  call    ?GetPackageFamilyName@CAppTileData@StorageSenseHandlers@SystemSettings@@QEAAJPEAPEAUHSTRING__@@@Z; SystemSettings::StorageSenseHandlers::CAppTileData::GetPackageFamilyName(HSTRING__ * *)
0x1800ca383  mov     ebx, eax
0x1800ca385  test    eax, eax
0x1800ca387  jns     short loc_1800CA3B6
0x1800ca389  mov     rcx, [rbp+28h]; this
0x1800ca38d  mov     r9d, eax; char *
0x1800ca390  lea     r8, aOnecoreuapShel_27; "onecoreuap\\shell\\coresettinghandlers"...
0x1800ca397  mov     edx, 0CCh; void *
0x1800ca39c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ca3a1  nop
0x1800ca3a2  mov     rcx, [rbp+string]; string
0x1800ca3a6  call    cs:__imp_WindowsDeleteString
0x1800ca3ac  mov     [rbp+string], 0
0x1800ca3b4  jmp     short loc_1800CA433
0x1800ca3b6  xor     edx, edx; length
0x1800ca3b8  mov     rcx, [rbp+string]; string
0x1800ca3bc  call    cs:__imp_WindowsGetStringRawBuffer
0x1800ca3c2  mov     r14d, 1
0x1800ca3c8  mov     [rsp+30h+bIgnoreCase], r14d; bIgnoreCase
0x1800ca3cd  or      ebx, 0FFFFFFFFh
0x1800ca3d0  mov     r9d, ebx; cchCount2
0x1800ca3d3  lea     r8, aMicrosoftwindo_1; "MicrosoftWindows.Client.AIX_cw5n1h2txye"...
0x1800ca3da  mov     edx, ebx; cchCount1
0x1800ca3dc  mov     rcx, rax; lpString1
0x1800ca3df  call    cs:__imp_CompareStringOrdinal
0x1800ca3e5  cmp     eax, 2
0x1800ca3e8  jz      short loc_1800CA415
0x1800ca3ea  xor     edx, edx; length
0x1800ca3ec  mov     rcx, [rbp+string]; string
0x1800ca3f0  call    cs:__imp_WindowsGetStringRawBuffer
0x1800ca3f6  mov     [rsp+30h+bIgnoreCase], r14d; bIgnoreCase
0x1800ca3fb  mov     r9d, ebx; cchCount2
0x1800ca3fe  lea     r8, aMicrosoftwindo_11; "MicrosoftWindows.Client.CoreAI_cw5n1h2t"...
0x1800ca405  mov     edx, ebx; cchCount1
0x1800ca407  mov     rcx, rax; lpString1
0x1800ca40a  call    cs:__imp_CompareStringOrdinal
0x1800ca410  cmp     eax, 2
0x1800ca413  jnz     short loc_1800CA41C
0x1800ca415  mov     byte ptr [rdi+0E1h], 0
0x1800ca41c  mov     rcx, [rbp+string]; string
0x1800ca420  call    cs:__imp_WindowsDeleteString
0x1800ca426  mov     [rbp+arg_10], 0
0x1800ca42e  mov     [r15], rdi
0x1800ca431  xor     ebx, ebx
0x1800ca433  lea     rcx, [rbp+arg_10]
0x1800ca437  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x1800ca43c  nop
0x1800ca43d  mov     rcx, rsi
0x1800ca440  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x1800ca445  mov     eax, ebx
0x1800ca447  mov     rbx, [rsp+30h+arg_18]
0x1800ca44c  add     rsp, 30h
0x1800ca450  pop     r15
0x1800ca452  pop     r14
0x1800ca454  pop     rdi
0x1800ca455  pop     rsi
0x1800ca456  pop     rbp
0x1800ca457  retn
```
