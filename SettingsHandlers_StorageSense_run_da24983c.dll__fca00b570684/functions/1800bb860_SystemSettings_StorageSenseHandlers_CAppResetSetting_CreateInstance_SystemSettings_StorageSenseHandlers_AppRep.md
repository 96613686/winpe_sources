# SystemSettings::StorageSenseHandlers::CAppResetSetting::CreateInstance(SystemSettings::StorageSenseHandlers::AppRepairType,Microsoft::WRL::ComPtr<SystemSettings::StorageSenseHandlers::CAppTileData>,SystemSettings::StorageSenseHandlers::CAppResetSetting * *)

- ea: `0x1800bb860`
- end: `0x1800bba4c`
- name: `?CreateInstance@CAppResetSetting@StorageSenseHandlers@SystemSettings@@SAJW4AppRepairType@23@V?$ComPtr@VCAppTileData@StorageSenseHandlers@SystemSettings@@@WRL@Microsoft@@PEAPEAV123@@Z`
- size: `492`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x1800bc410`

## callees

- `0x18000733c`
- `0x18000c964`
- `0x18000e6cc`
- `0x180010ecc`
- `0x1800a79dc`
- `0x1800a7c4c`
- `0x1800a8a88`
- `0x1800a8cb4`
- `0x1800bb210`
- `0x1800bb860`
- `0x1800bdbe4`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800bb9b5`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800bb9d3`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800bb9b5`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800bb9d3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800bb8fa`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800bb93f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800bb8fa`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800bb93f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800bb996`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800bb996`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall SystemSettings::StorageSenseHandlers::CAppResetSetting::CreateInstance(
        int a1,
        SystemSettings::StorageSenseHandlers::CAppTileData **a2,
        __int64 *a3)
{
  SystemSettings::StorageSenseHandlers::CAppResetSetting *v6; // rax
  __int64 v7; // rbx
  __int64 v8; // rsi
  unsigned int v9; // ebx
  __int64 v10; // r9
  __int64 v11; // rdx
  SystemSettings::StorageSenseHandlers::CAppTileData *v12; // rdi
  int PackageFullName; // eax
  SystemSettings::StorageSenseHandlers::CAppTileData *v14; // rbx
  const WCHAR *StringRawBuffer; // rbx
  BOOL bIgnoreCase; // [rsp+20h] [rbp-48h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]
  __int64 v19; // [rsp+80h] [rbp+18h] BYREF
  SystemSettings::StorageSenseHandlers::CAppResetSetting *v20; // [rsp+88h] [rbp+20h] BYREF

  *a3 = 0;
  v19 = 0;
  v6 = (SystemSettings::StorageSenseHandlers::CAppResetSetting *)operator new(
                                                                   0x100u,
                                                                   (const struct std::nothrow_t *)&std::nothrow);
  v20 = v6;
  if ( v6 )
  {
    v7 = SystemSettings::StorageSenseHandlers::CAppResetSetting::CAppResetSetting(v6);
    v19 = v7;
    v20 = 0;
    v8 = v7;
  }
  else
  {
    v7 = 0;
    v8 = 0;
  }
  Microsoft::WRL::Details::MakeAllocator<Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_1dabfb557c6ca53c8eb192beb0706936_ &>>::~MakeAllocator<Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_1dabfb557c6ca53c8eb192beb0706936_ &>>(&v20);
  if ( !v7 )
  {
    v9 = -2147024882;
    v10 = 2147942414LL;
    v11 = 434;
LABEL_9:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v11,
      (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\storagesense\\lib\\appadvancedinfo.cpp",
      (const char *)v10,
      bIgnoreCase);
    goto LABEL_21;
  }
  v12 = *a2;
  WindowsDeleteString(*(HSTRING *)(v8 + 224));
  *(_QWORD *)(v8 + 224) = 0;
  PackageFullName = SystemSettings::StorageSenseHandlers::CAppTileData::GetPackageFullName(v12, (HSTRING *)(v8 + 224));
  v9 = PackageFullName;
  if ( PackageFullName < 0 )
  {
    v11 = 435;
LABEL_8:
    v10 = (unsigned int)PackageFullName;
    goto LABEL_9;
  }
  v14 = *a2;
  WindowsDeleteString(*(HSTRING *)(v8 + 216));
  *(_QWORD *)(v8 + 216) = 0;
  PackageFullName = SystemSettings::StorageSenseHandlers::CAppTileData::GetPackageFamilyName(v14, (HSTRING *)(v8 + 216));
  v9 = PackageFullName;
  if ( PackageFullName < 0 )
  {
    v11 = 436;
    goto LABEL_8;
  }
  *(_DWORD *)(v8 + 248) = a1;
  *(_WORD *)(v8 + 232) = 0;
  *(_WORD *)(v8 + 235) = 1;
  *(_DWORD *)(v8 + 240) = 0;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_56489269>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_56489269>::GetImpl'::`2'::impl) )
  {
    StringRawBuffer = WindowsGetStringRawBuffer(*(HSTRING *)(v8 + 216), 0);
    if ( CompareStringOrdinal(StringRawBuffer, -1, L"MicrosoftWindows.Client.AIX_cw5n1h2txyewy", -1, 1) == 2
      || CompareStringOrdinal(StringRawBuffer, -1, L"MicrosoftWindows.Client.CoreAI_cw5n1h2txyewy", -1, 1) == 2 )
    {
      *(_BYTE *)(v8 + 235) = 0;
    }
  }
  if ( (int)SystemSettings::StorageSenseHandlers::CAppTileData::GetIsCentennial(*a2, (bool *)(v8 + 234)) < 0 )
    *(_BYTE *)(v8 + 234) = 0;
  if ( (int)SystemSettings::StorageSenseHandlers::CAppTileData::GetIsLanguagePack(*a2, (unsigned __int8 *)(v8 + 244)) < 0 )
    *(_BYTE *)(v8 + 244) = 0;
  v19 = 0;
  *a3 = v8;
  v9 = 0;
LABEL_21:
  Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v19);
  Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(a2);
  return v9;
}

```

## disassembly

```asm
0x1800bb860  mov     rax, rsp
0x1800bb863  mov     [rax+10h], rdx
0x1800bb867  push    rbx
0x1800bb868  push    rbp
0x1800bb869  push    rsi
0x1800bb86a  push    rdi
0x1800bb86b  push    r12
0x1800bb86d  push    r14
0x1800bb86f  push    r15
0x1800bb871  sub     rsp, 30h
0x1800bb875  mov     r15, r8
0x1800bb878  mov     r14, rdx
0x1800bb87b  mov     ebp, ecx
0x1800bb87d  xor     r12d, r12d
0x1800bb880  mov     [r8], r12
0x1800bb883  mov     [rax+18h], r12
0x1800bb887  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800bb88e  mov     ecx, 100h; unsigned __int64
0x1800bb893  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800bb898  mov     [rsp+68h+arg_18], rax
0x1800bb8a0  test    rax, rax
0x1800bb8a3  jz      short loc_1800BB8C5
0x1800bb8a5  mov     rcx, rax; this
0x1800bb8a8  call    ??0CAppResetSetting@StorageSenseHandlers@SystemSettings@@QEAA@XZ; SystemSettings::StorageSenseHandlers::CAppResetSetting::CAppResetSetting(void)
0x1800bb8ad  mov     rbx, rax
0x1800bb8b0  mov     [rsp+68h+arg_10], rax
0x1800bb8b8  mov     [rsp+68h+arg_18], r12
0x1800bb8c0  mov     rsi, rax
0x1800bb8c3  jmp     short loc_1800BB8CB
0x1800bb8c5  mov     rbx, r12
0x1800bb8c8  mov     rsi, r12
0x1800bb8cb  lea     rcx, [rsp+68h+arg_18]
0x1800bb8d3  call    ??1?$MakeAllocator@V?$CTaskWrapper@AEAV_lambda_1dabfb557c6ca53c8eb192beb0706936_@@@ComTaskPool@Internal@Windows@@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::MakeAllocator<Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_1dabfb557c6ca53c8eb192beb0706936_ &>>::~MakeAllocator<Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_1dabfb557c6ca53c8eb192beb0706936_ &>>(void)
0x1800bb8d8  nop
0x1800bb8d9  test    rbx, rbx
0x1800bb8dc  jnz     short loc_1800BB8ED
0x1800bb8de  mov     ebx, 8007000Eh
0x1800bb8e3  mov     r9d, ebx
0x1800bb8e6  mov     edx, 1B2h
0x1800bb8eb  jmp     short loc_1800BB91C
0x1800bb8ed  mov     rdi, [r14]
0x1800bb8f0  lea     rbx, [rsi+0E0h]
0x1800bb8f7  mov     rcx, [rbx]; string
0x1800bb8fa  call    cs:__imp_WindowsDeleteString
0x1800bb900  mov     [rbx], r12
0x1800bb903  mov     rdx, rbx; HSTRING *
0x1800bb906  mov     rcx, rdi; this
0x1800bb909  call    ?GetPackageFullName@CAppTileData@StorageSenseHandlers@SystemSettings@@QEAAJPEAPEAUHSTRING__@@@Z; SystemSettings::StorageSenseHandlers::CAppTileData::GetPackageFullName(HSTRING__ * *)
0x1800bb90e  mov     ebx, eax
0x1800bb910  test    eax, eax
0x1800bb912  jns     short loc_1800BB932
0x1800bb914  mov     edx, 1B3h; void *
0x1800bb919  mov     r9d, eax; char *
0x1800bb91c  mov     rcx, [rsp+68h]; this
0x1800bb921  lea     r8, aOnecoreuapShel_28; "onecoreuap\\shell\\coresettinghandlers"...
0x1800bb928  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800bb92d  jmp     loc_1800BBA25
0x1800bb932  mov     rbx, [r14]
0x1800bb935  lea     rdi, [rsi+0D8h]
0x1800bb93c  mov     rcx, [rdi]; string
0x1800bb93f  call    cs:__imp_WindowsDeleteString
0x1800bb945  mov     [rdi], r12
0x1800bb948  mov     rdx, rdi; HSTRING *
0x1800bb94b  mov     rcx, rbx; this
0x1800bb94e  call    ?GetPackageFamilyName@CAppTileData@StorageSenseHandlers@SystemSettings@@QEAAJPEAPEAUHSTRING__@@@Z; SystemSettings::StorageSenseHandlers::CAppTileData::GetPackageFamilyName(HSTRING__ * *)
0x1800bb953  mov     ebx, eax
0x1800bb955  test    eax, eax
0x1800bb957  jns     short loc_1800BB960
0x1800bb959  mov     edx, 1B4h
0x1800bb95e  jmp     short loc_1800BB919
0x1800bb960  mov     [rsi+0F8h], ebp
0x1800bb966  mov     [rsi+0E8h], r12w
0x1800bb96e  mov     ebp, 1
0x1800bb973  mov     [rsi+0EBh], bp
0x1800bb97a  mov     [rsi+0F0h], r12d
0x1800bb981  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_56489269@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_56489269@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_56489269> `wil::Feature<__WilFeatureTraits_Feature_56489269>::GetImpl(void)'::`2'::impl
0x1800bb988  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_56489269@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_56489269>::__private_IsEnabled(void)
0x1800bb98d  test    al, al
0x1800bb98f  jz      short loc_1800BB9E5
0x1800bb991  xor     edx, edx; length
0x1800bb993  mov     rcx, [rdi]; string
0x1800bb996  call    cs:__imp_WindowsGetStringRawBuffer
0x1800bb99c  mov     rbx, rax
0x1800bb99f  mov     [rsp+68h+bIgnoreCase], ebp; bIgnoreCase
0x1800bb9a3  or      edi, 0FFFFFFFFh
0x1800bb9a6  mov     r9d, edi; cchCount2
0x1800bb9a9  lea     r8, aMicrosoftwindo_1; "MicrosoftWindows.Client.AIX_cw5n1h2txye"...
0x1800bb9b0  mov     edx, edi; cchCount1
0x1800bb9b2  mov     rcx, rax; lpString1
0x1800bb9b5  call    cs:__imp_CompareStringOrdinal
0x1800bb9bb  cmp     eax, 2
0x1800bb9be  jz      short loc_1800BB9DE
0x1800bb9c0  mov     [rsp+68h+bIgnoreCase], ebp; bIgnoreCase
0x1800bb9c4  mov     r9d, edi; cchCount2
0x1800bb9c7  lea     r8, aMicrosoftwindo_11; "MicrosoftWindows.Client.CoreAI_cw5n1h2t"...
0x1800bb9ce  mov     edx, edi; cchCount1
0x1800bb9d0  mov     rcx, rbx; lpString1
0x1800bb9d3  call    cs:__imp_CompareStringOrdinal
0x1800bb9d9  cmp     eax, 2
0x1800bb9dc  jnz     short loc_1800BB9E5
0x1800bb9de  mov     [rsi+0EBh], r12b
0x1800bb9e5  lea     rbx, [rsi+0EAh]
0x1800bb9ec  mov     rdx, rbx; bool *
0x1800bb9ef  mov     rcx, [r14]; this
0x1800bb9f2  call    ?GetIsCentennial@CAppTileData@StorageSenseHandlers@SystemSettings@@QEAAJPEA_N@Z; SystemSettings::StorageSenseHandlers::CAppTileData::GetIsCentennial(bool *)
0x1800bb9f7  test    eax, eax
0x1800bb9f9  jns     short loc_1800BB9FE
0x1800bb9fb  mov     [rbx], r12b
0x1800bb9fe  lea     rbx, [rsi+0F4h]
0x1800bba05  mov     rdx, rbx; unsigned __int8 *
0x1800bba08  mov     rcx, [r14]; this
0x1800bba0b  call    ?GetIsLanguagePack@CAppTileData@StorageSenseHandlers@SystemSettings@@QEAAJPEAE@Z; SystemSettings::StorageSenseHandlers::CAppTileData::GetIsLanguagePack(uchar *)
0x1800bba10  test    eax, eax
0x1800bba12  jns     short loc_1800BBA17
0x1800bba14  mov     [rbx], r12b
0x1800bba17  mov     [rsp+68h+arg_10], r12
0x1800bba1f  mov     [r15], rsi
0x1800bba22  mov     ebx, r12d
0x1800bba25  lea     rcx, [rsp+68h+arg_10]
0x1800bba2d  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x1800bba32  nop
0x1800bba33  mov     rcx, r14
0x1800bba36  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x1800bba3b  mov     eax, ebx
0x1800bba3d  add     rsp, 30h
0x1800bba41  pop     r15
0x1800bba43  pop     r14
0x1800bba45  pop     r12
0x1800bba47  pop     rdi
0x1800bba48  pop     rsi
0x1800bba49  pop     rbp
0x1800bba4a  pop     rbx
0x1800bba4b  retn
```
