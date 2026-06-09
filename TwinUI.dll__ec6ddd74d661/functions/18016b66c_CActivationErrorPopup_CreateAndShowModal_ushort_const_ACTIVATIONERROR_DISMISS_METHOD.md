# CActivationErrorPopup::CreateAndShowModal(ushort const *,ACTIVATIONERROR_DISMISS_METHOD *)

- ea: `0x18016b66c`
- end: `0x18016b8a5`
- name: `?CreateAndShowModal@CActivationErrorPopup@@QEAAJPEBGPEAW4ACTIVATIONERROR_DISMISS_METHOD@@@Z`
- size: `569`
- prototype: `__int64 __fastcall(CActivationErrorPopup *__hidden this, const unsigned __int16 *, enum ACTIVATIONERROR_DISMISS_METHOD *)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18016da40`

## callees

- `0x18000e2b0`
- `0x180041f54`
- `0x1800febe4`
- `0x180167194`
- `0x180167244`
- `0x18016aba0`
- `0x18016b66c`
- `0x18016d4e8`
- `0x18016d538`
- `0x18016d570`
- `0x18016d78c`
- `0x180170098`
- `0x180172e44`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18016b750`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18016b750`
- `Wldp!__imp_?WldpTraceLoggingWDACBlockDialogShown@@YAXPEBGJU_GUID@@0@Z` at `0x18016b7dd`
- `Wldp!__imp_?WldpTraceLoggingWDACBlockDialogShown@@YAXPEBGJU_GUID@@0@Z` at `0x18016b7dd`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsFileSpecW` at `0x18016b6a8`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsFileSpecW` at `0x18016b855`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsFileSpecW` at `0x18016b6a8`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsFileSpecW` at `0x18016b855`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x18016b6bb`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x18016b785`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x18016b868`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x18016b6bb`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x18016b785`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x18016b868`

## string_xrefs

- `0x18016b744`: `Microsoft.GamingServices_8wekyb3d8bbwe!GamingServices`
- `0x18016b768`: `GamingServices`

## pseudocode

```c
__int64 __fastcall CActivationErrorPopup::CreateAndShowModal(
        CActivationErrorPopup *this,
        WCHAR *a2,
        enum ACTIVATIONERROR_DISMISS_METHOD *a3)
{
  LPWSTR FileNameW; // rax
  __int64 v7; // rdx
  int v8; // ecx
  unsigned __int16 **v9; // r8
  LPWSTR v10; // rax
  __int64 v11; // rdx
  struct _GUID v12; // xmm0
  int v13; // edx
  int v14; // esi
  __int64 v15; // rax
  LPWSTR v16; // rax
  __int64 v17; // rcx
  struct _GUID v19; // [rsp+30h] [rbp-28h] BYREF
  LPWSTR v20; // [rsp+60h] [rbp+8h] BYREF
  LPWSTR v21; // [rsp+68h] [rbp+10h] BYREF

  *(_DWORD *)a3 = 0;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_ActivationErrorDialogsRejuv>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_ActivationErrorDialogsRejuv>::GetImpl'::`2'::impl) )
  {
    FileNameW = 0;
    if ( a2 )
    {
      if ( PathIsFileSpecW(a2) )
        FileNameW = a2;
      else
        FileNameW = PathFindFileNameW(a2);
    }
    v7 = *((_QWORD *)this + 3);
    v21 = FileNameW;
    LODWORD(v20) = *(_DWORD *)(v7 + 116);
    ActivationErrorTelemetry::ActivationErrorDialogLaunch<int,long const &,unsigned short const *>(&v20, v7, &v21);
  }
  if ( a2 )
  {
    if ( IsCodeIntegrityError(**((_DWORD **)this + 3)) || IsNightsWatchDesktopError(v8) )
    {
      if ( IsRunningWdagContainer() )
        v10 = PathFindFileNameW(a2);
      else
        v10 = a2;
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Initialize(
        (char *)this + 32,
        v10,
        -1);
      if ( IsCodeIntegrityError(**((_DWORD **)this + 3)) && !IsNightsWatchUIEnabled() )
      {
        v11 = *((_QWORD *)this + 3);
        v12 = *(struct _GUID *)(v11 + 100);
        LODWORD(v11) = *(_DWORD *)v11;
        v19 = v12;
        WldpTraceLoggingWDACBlockDialogShown(a2, v11, &v19, &pszDefault);
      }
    }
    else
    {
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free((char *)this + 32);
      *((_QWORD *)this + 5) = -1;
      *((_QWORD *)this + 6) = -1;
      ImmersiveAppHelpers::GetNormalDisplayNameFromAppId(a2, (const unsigned __int16 *)this + 16, v9);
      if ( !*((_QWORD *)this + 4)
        && CompareStringOrdinal(a2, -1, L"Microsoft.GamingServices_8wekyb3d8bbwe!GamingServices", -1, 1) == 2 )
      {
        Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Initialize(
          (char *)this + 32,
          L"GamingServices",
          -1);
      }
    }
  }
  v14 = CActivationErrorPopup::CreateAndShowAlert(this, a2);
  if ( v14 >= 0 )
  {
    *(_DWORD *)a3 = *((_DWORD *)this + 14);
    if ( (Microsoft_Windows_Immersive_ShellEnableBits & 8) != 0 )
      McTemplateU0zqjq_EventWriteTransfer(
        *((_QWORD *)this + 3) + 100,
        v13,
        (_DWORD)a2,
        **((_DWORD **)this + 3),
        *((_QWORD *)this + 3) + 100LL,
        *((_DWORD *)this + 14));
    v15 = *((_QWORD *)this + 3);
    v14 = *(_DWORD *)(v15 + 88);
    if ( !v14 || *((_DWORD *)this + 14) != 2 )
    {
      v14 = *(_DWORD *)(v15 + 92);
      if ( !v14 || *((_DWORD *)this + 14) != 3 )
        v14 = 2556505;
    }
  }
  v16 = 0;
  if ( a2 )
  {
    if ( PathIsFileSpecW(a2) )
      v16 = a2;
    else
      v16 = PathFindFileNameW(a2);
  }
  v17 = *((_QWORD *)this + 3);
  v20 = v16;
  ActivationErrorTelemetry::ActivationBlocked<long const &,enum ACTIVATIONERROR_DISMISS_METHOD &,unsigned short const *>(
    v17,
    a3,
    &v20);
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x18016b66c  mov     [rsp+arg_10], rbx
0x18016b671  mov     [rsp+arg_18], rbp
0x18016b676  push    rsi
0x18016b677  push    rdi
0x18016b678  push    r14
0x18016b67a  sub     rsp, 40h
0x18016b67e  mov     r14, r8
0x18016b681  mov     dword ptr [r8], 0
0x18016b688  mov     rbx, rdx
0x18016b68b  mov     rdi, rcx
0x18016b68e  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ActivationErrorDialogsRejuv@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ActivationErrorDialogsRejuv@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ActivationErrorDialogsRejuv> `wil::Feature<__WilFeatureTraits_Feature_ActivationErrorDialogsRejuv>::GetImpl(void)'::`2'::impl
0x18016b695  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_ActivationErrorDialogsRejuv@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ActivationErrorDialogsRejuv>::__private_IsEnabled(void)
0x18016b69a  test    al, al
0x18016b69c  jz      short loc_18016B6EB
0x18016b69e  xor     eax, eax
0x18016b6a0  test    rbx, rbx
0x18016b6a3  jz      short loc_18016B6CC
0x18016b6a5  mov     rcx, rbx; pszPath
0x18016b6a8  call    cs:__imp_PathIsFileSpecW
0x18016b6af  nop     dword ptr [rax+rax+00h]
0x18016b6b4  test    eax, eax
0x18016b6b6  jnz     short loc_18016B6C9
0x18016b6b8  mov     rcx, rbx; pszPath
0x18016b6bb  call    cs:__imp_PathFindFileNameW
0x18016b6c2  nop     dword ptr [rax+rax+00h]
0x18016b6c7  jmp     short loc_18016B6CC
0x18016b6c9  mov     rax, rbx
0x18016b6cc  mov     rdx, [rdi+18h]
0x18016b6d0  lea     r8, [rsp+58h+arg_8]
0x18016b6d5  mov     [rsp+58h+arg_8], rax
0x18016b6da  lea     rcx, [rsp+58h+arg_0]
0x18016b6df  mov     eax, [rdx+74h]
0x18016b6e2  mov     dword ptr [rsp+58h+arg_0], eax
0x18016b6e6  call    ??$ActivationErrorDialogLaunch@HAEBJPEBG@ActivationErrorTelemetry@@SAX$$QEAHAEBJ$$QEAPEBG@Z; ActivationErrorTelemetry::ActivationErrorDialogLaunch<int,long const &,ushort const *>(int &&,long const &,ushort const * &&)
0x18016b6eb  test    rbx, rbx
0x18016b6ee  jz      loc_18016B7E9
0x18016b6f4  mov     rax, [rdi+18h]
0x18016b6f8  mov     ecx, [rax]; int
0x18016b6fa  call    ?IsCodeIntegrityError@@YA_NJ@Z; IsCodeIntegrityError(long)
0x18016b6ff  test    al, al
0x18016b701  jnz     short loc_18016B779
0x18016b703  call    ?IsNightsWatchDesktopError@@YA_NJ@Z; IsNightsWatchDesktopError(long)
0x18016b708  test    al, al
0x18016b70a  jnz     short loc_18016B779
0x18016b70c  lea     rsi, [rdi+20h]
0x18016b710  mov     rcx, rsi
0x18016b713  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18016b718  or      rbp, 0FFFFFFFFFFFFFFFFh
0x18016b71c  mov     rdx, rsi; unsigned __int16 *
0x18016b71f  mov     rcx, rbx; pszItem
0x18016b722  mov     [rsi+8], rbp
0x18016b726  mov     [rsi+10h], rbp
0x18016b72a  call    ?GetNormalDisplayNameFromAppId@ImmersiveAppHelpers@@YAJPEBGPEAPEAG@Z; ImmersiveAppHelpers::GetNormalDisplayNameFromAppId(ushort const *,ushort * *)
0x18016b72f  cmp     qword ptr [rsi], 0
0x18016b733  jnz     loc_18016B7E9
0x18016b739  mov     r9d, ebp; cchCount2
0x18016b73c  mov     [rsp+58h+bIgnoreCase], 1; bIgnoreCase
0x18016b744  lea     r8, aMicrosoftGamin_0; "Microsoft.GamingServices_8wekyb3d8bbwe!"...
0x18016b74b  mov     edx, ebp; cchCount1
0x18016b74d  mov     rcx, rbx; lpString1
0x18016b750  call    cs:__imp_CompareStringOrdinal
0x18016b757  nop     dword ptr [rax+rax+00h]
0x18016b75c  cmp     eax, 2
0x18016b75f  jnz     loc_18016B7E9
0x18016b765  mov     r8, rbp
0x18016b768  lea     rdx, aGamingservices; "GamingServices"
0x18016b76f  mov     rcx, rsi
0x18016b772  call    ?_Initialize@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Initialize(ushort const *,unsigned __int64)
0x18016b777  jmp     short loc_18016B7E9
0x18016b779  call    ?IsRunningWdagContainer@@YA_NXZ; IsRunningWdagContainer(void)
0x18016b77e  test    al, al
0x18016b780  jz      short loc_18016B793
0x18016b782  mov     rcx, rbx; pszPath
0x18016b785  call    cs:__imp_PathFindFileNameW
0x18016b78c  nop     dword ptr [rax+rax+00h]
0x18016b791  jmp     short loc_18016B796
0x18016b793  mov     rax, rbx
0x18016b796  lea     rcx, [rdi+20h]
0x18016b79a  or      r8, 0FFFFFFFFFFFFFFFFh
0x18016b79e  mov     rdx, rax
0x18016b7a1  call    ?_Initialize@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Initialize(ushort const *,unsigned __int64)
0x18016b7a6  mov     rcx, [rdi+18h]
0x18016b7aa  mov     ecx, [rcx]; int
0x18016b7ac  call    ?IsCodeIntegrityError@@YA_NJ@Z; IsCodeIntegrityError(long)
0x18016b7b1  test    al, al
0x18016b7b3  jz      short loc_18016B7E9
0x18016b7b5  call    ?IsNightsWatchUIEnabled@@YA_NXZ; IsNightsWatchUIEnabled(void)
0x18016b7ba  test    al, al
0x18016b7bc  jnz     short loc_18016B7E9
0x18016b7be  mov     rdx, [rdi+18h]
0x18016b7c2  lea     r9, pszDefault
0x18016b7c9  lea     r8, [rsp+58h+var_28]
0x18016b7ce  mov     rcx, rbx
0x18016b7d1  movups  xmm0, xmmword ptr [rdx+64h]
0x18016b7d5  mov     edx, [rdx]
0x18016b7d7  movdqu  [rsp+58h+var_28], xmm0
0x18016b7dd  call    cs:__imp_?WldpTraceLoggingWDACBlockDialogShown@@YAXPEBGJU_GUID@@0@Z; WldpTraceLoggingWDACBlockDialogShown(ushort const *,long,_GUID,ushort const *)
0x18016b7e4  nop     dword ptr [rax+rax+00h]
0x18016b7e9  mov     rdx, rbx; unsigned __int16 *
0x18016b7ec  mov     rcx, rdi; this
0x18016b7ef  call    ?CreateAndShowAlert@CActivationErrorPopup@@AEAAJPEBG@Z; CActivationErrorPopup::CreateAndShowAlert(ushort const *)
0x18016b7f4  mov     esi, eax
0x18016b7f6  test    eax, eax
0x18016b7f8  js      short loc_18016B84B
0x18016b7fa  mov     eax, [rdi+38h]
0x18016b7fd  mov     [r14], eax
0x18016b800  test    byte ptr cs:Microsoft_Windows_Immersive_ShellEnableBits, 8
0x18016b807  jz      short loc_18016B828
0x18016b809  mov     r9, [rdi+18h]
0x18016b80d  mov     r8, rbx
0x18016b810  mov     eax, [rdi+38h]
0x18016b813  mov     [rsp+58h+var_30], eax
0x18016b817  lea     rcx, [r9+64h]
0x18016b81b  mov     r9d, [r9]
0x18016b81e  mov     qword ptr [rsp+58h+bIgnoreCase], rcx
0x18016b823  call    McTemplateU0zqjq_EventWriteTransfer
0x18016b828  mov     rax, [rdi+18h]
0x18016b82c  mov     esi, [rax+58h]
0x18016b82f  test    esi, esi
0x18016b831  jz      short loc_18016B839
0x18016b833  cmp     dword ptr [rdi+38h], 2
0x18016b837  jz      short loc_18016B84B
0x18016b839  mov     esi, [rax+5Ch]
0x18016b83c  test    esi, esi
0x18016b83e  jz      short loc_18016B846
0x18016b840  cmp     dword ptr [rdi+38h], 3
0x18016b844  jz      short loc_18016B84B
0x18016b846  mov     esi, 270259h
0x18016b84b  xor     eax, eax
0x18016b84d  test    rbx, rbx
0x18016b850  jz      short loc_18016B879
0x18016b852  mov     rcx, rbx; pszPath
0x18016b855  call    cs:__imp_PathIsFileSpecW
0x18016b85c  nop     dword ptr [rax+rax+00h]
0x18016b861  test    eax, eax
0x18016b863  jnz     short loc_18016B876
0x18016b865  mov     rcx, rbx; pszPath
0x18016b868  call    cs:__imp_PathFindFileNameW
0x18016b86f  nop     dword ptr [rax+rax+00h]
0x18016b874  jmp     short loc_18016B879
0x18016b876  mov     rax, rbx
0x18016b879  mov     rcx, [rdi+18h]
0x18016b87d  lea     r8, [rsp+58h+arg_0]
0x18016b882  mov     rdx, r14
0x18016b885  mov     [rsp+58h+arg_0], rax
0x18016b88a  call    ??$ActivationBlocked@AEBJAEAW4ACTIVATIONERROR_DISMISS_METHOD@@PEBG@ActivationErrorTelemetry@@SAXAEBJAEAW4ACTIVATIONERROR_DISMISS_METHOD@@$$QEAPEBG@Z; ActivationErrorTelemetry::ActivationBlocked<long const &,ACTIVATIONERROR_DISMISS_METHOD &,ushort const *>(long const &,ACTIVATIONERROR_DISMISS_METHOD &,ushort const * &&)
0x18016b88f  mov     rbx, [rsp+58h+arg_10]
0x18016b894  mov     eax, esi
0x18016b896  mov     rbp, [rsp+58h+arg_18]
0x18016b89b  add     rsp, 40h
0x18016b89f  pop     r14
0x18016b8a1  pop     rdi
0x18016b8a2  pop     rsi
0x18016b8a3  retn
```
