# Windows::Networking::UX::Internal::MBCategory::tp_UpdateRegistration(WWAN_REGISTER_OBJECT)

- ea: `0x18000c890`
- end: `0x18000cc48`
- name: `?tp_UpdateRegistration@MBCategory@Internal@UX@Networking@Windows@@AEAAXUWWAN_REGISTER_OBJECT@@@Z`
- size: `952`
- prototype: ``
- caller_count: `2`
- callee_count: `9`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18001dc70`
- `0x180028130`

## callees

- `0x180008c84`
- `0x18000ad20`
- `0x18000c890`
- `0x18000ccb0`
- `0x18001a494`
- `0x18001bfa8`
- `0x1800242fc`
- `0x18003a2d8`
- `0x180051908`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18000ca35`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18000cc01`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18000ca35`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18000cc01`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000c973`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000c9a9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000ca00`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000cbcc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000c973`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000c9a9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000ca00`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000cbcc`

## string_xrefs

- `0x18000c91a`: `MBCategory::tp_UpdateRegistration. Register Object is not ready.`
- `0x18000ca06`: `updated ProviderName. old ProviderName=%ls, new ProviderName=%ls`
- `0x18000ca15`: `Windows::Networking::UX::Internal::MBCategory::tp_UpdateRegistration`
- `0x18000cac5`: `Windows::Networking::UX::Internal::MBCategory::tp_UpdateRegistration`
- `0x18000cafb`: `Windows::Networking::UX::Internal::MBCategory::tp_UpdateRegistration`
- `0x18000cb4d`: `Windows::Networking::UX::Internal::MBCategory::tp_UpdateRegistration`
- `0x18000cb87`: `Windows::Networking::UX::Internal::MBCategory::tp_UpdateRegistration`
- `0x18000cba8`: `Windows::Networking::UX::Internal::MBCategory::tp_UpdateRegistration`
- `0x18000cbe1`: `Windows::Networking::UX::Internal::MBCategory::tp_UpdateRegistration`
- `0x18000cab5`: `updated NetworkError. old NetworkError=%d, new NetworkError=%d`
- `0x18000cb25`: `updated registerState. old registerState=%d, new registerState=%d, old _fIsRoaming=%hs, new _fIsRoaming=%hs`
- `0x18000cb98`: `updated registerMode. old registerMode=%d, new registerMode=%d`
- `0x18000cbd2`: `updated ProviderId. old ProviderId=%ls, new ProviderId=%ls`

## pseudocode

```c
void __fastcall Windows::Networking::UX::Internal::MBCategory::tp_UpdateRegistration(__int64 a1, __int64 a2)
{
  char v2; // r15
  int v3; // r9d
  unsigned int v6; // edx
  unsigned int v7; // ebx
  __int64 *v8; // rax
  int v9; // ebp
  int v10; // esi
  int v11; // r9d
  PCWSTR StringRawBuffer; // rax
  __int64 v13; // r8
  int v14; // ecx
  int v15; // edx
  const wchar_t *v16; // rdi
  PCWSTR v17; // rax
  signed __int64 v18; // r8
  int v19; // ecx
  int v20; // edx
  const wchar_t *v21; // rax
  unsigned int v22; // ebx
  __int64 *v23; // rax
  const wchar_t *v24; // rax
  _DWORD v25[4]; // [rsp+40h] [rbp-38h] BYREF

  v2 = 0;
  v3 = *(_DWORD *)(a1 + 744);
  if ( v3 != *(_DWORD *)a2 )
  {
    MBSettingUXLogging::Info(
      "Windows::Networking::UX::Internal::MBCategory::tp_UpdateRegistration",
      0xF0Bu,
      "updated NetworkError. old NetworkError=%d, new NetworkError=%d",
      v3,
      *(_DWORD *)a2);
    v2 = 1;
    *(_DWORD *)(a1 + 744) = *(_DWORD *)a2;
  }
  v6 = *(_DWORD *)(a2 + 208);
  if ( v6 )
  {
    v25[0] = Windows::Networking::UX::Internal::MBCategory::_HResultFromWwanStatus(
               (Windows::Networking::UX::Internal::MBCategory *)a1,
               v6);
    MBSettingUXLogging::WarnHRESULT<char const (&)[65],long>(
      "MBCategory::tp_UpdateRegistration. Register Object is not ready.",
      v25);
  }
  else
  {
    v7 = *(_DWORD *)(a2 + 4);
    if ( v7 > 6 )
    {
      v9 = 0;
      v10 = 0;
      MBSettingUXLogging::Error(
        "Windows::Networking::UX::Internal::MBCategory::tp_UpdateRegistration",
        0xF1Cu,
        "Received WWAN_REGISTER_STATE is not supported. Received WWAN_REGISTER_STATE=%d, Max WWAN_REGISTER_STATE=%d",
        v7,
        7);
    }
    else
    {
      v8 = &qword_180061A40;
      while ( 1 )
      {
        v9 = 0;
        if ( *(_DWORD *)v8 == v7 )
          break;
        if ( ++v8 == &qword_180061A78 )
          goto LABEL_8;
      }
      if ( v8 == &qword_180061A78 )
      {
LABEL_8:
        v10 = 0;
        MicrosoftTelemetryAssertTriggeredArgs(&qword_180061A78, v7);
        goto LABEL_29;
      }
      v10 = *((_DWORD *)v8 + 1);
LABEL_29:
      MBSettingUXLogging::Verbose(
        "Windows::Networking::UX::Internal::MBCategory::_MbRegisterStateFromWwanRegisterState",
        0x16C8u,
        "wwanRegisterState=%d, mbRegisterState=%d",
        v7,
        v10);
    }
    if ( *(_DWORD *)(a1 + 720) != v10 )
    {
      MBSettingUXLogging::Info(
        "Windows::Networking::UX::Internal::MBCategory::tp_UpdateRegistration",
        0xF2Eu,
        "updated registerState. old registerState=%d, new registerState=%d, old _fIsRoaming=%hs, new _fIsRoaming=%hs");
      *(_DWORD *)(a1 + 720) = v10;
      v2 = 1;
      *(_BYTE *)(a1 + 88) = (unsigned int)(v10 - 4) <= 1;
    }
    v22 = *(_DWORD *)(a2 + 8);
    if ( v22 > 2 )
    {
      MBSettingUXLogging::Error(
        "Windows::Networking::UX::Internal::MBCategory::tp_UpdateRegistration",
        0xF3Eu,
        "Received WWAN_REGISTER_MODE is not supported. Received WWAN_REGISTER_MODE=%d, Max WWAN_REGISTER_MODE=%d",
        v22,
        3);
    }
    else
    {
      v23 = &qword_180061A78;
      while ( *(_DWORD *)v23 != v22 )
      {
        if ( ++v23 == (__int64 *)"Enter interfaceConnectivity=%d, authProxy=%d" )
          goto LABEL_36;
      }
      if ( v23 != (__int64 *)"Enter interfaceConnectivity=%d, authProxy=%d" )
      {
        v9 = *((_DWORD *)v23 + 1);
        goto LABEL_12;
      }
LABEL_36:
      MicrosoftTelemetryAssertTriggeredArgs("Enter interfaceConnectivity=%d, authProxy=%d", v22);
LABEL_12:
      MBSettingUXLogging::Verbose(
        "Windows::Networking::UX::Internal::MBCategory::_MbRegisterModeFromWwanRegisterMode",
        0x16D0u,
        "wwanRegisterMode=%d, mbRegisterMode=%d",
        v22,
        v9);
    }
    v11 = *(_DWORD *)(a1 + 724);
    if ( v11 != v9 )
    {
      MBSettingUXLogging::Info(
        "Windows::Networking::UX::Internal::MBCategory::tp_UpdateRegistration",
        0xF48u,
        "updated registerMode. old registerMode=%d, new registerMode=%d",
        v11,
        v9);
      *(_DWORD *)(a1 + 724) = v9;
      v2 = 1;
    }
    StringRawBuffer = WindowsGetStringRawBuffer(*(HSTRING *)(a1 + 728), 0);
    v13 = a2 + 26 - (_QWORD)StringRawBuffer;
    do
    {
      v14 = *(PCWSTR)((char *)StringRawBuffer + v13);
      v15 = *StringRawBuffer - v14;
      if ( v15 )
        break;
      ++StringRawBuffer;
    }
    while ( v14 );
    if ( v15 )
    {
      v21 = WindowsGetStringRawBuffer(*(HSTRING *)(a1 + 728), 0);
      MBSettingUXLogging::Info(
        "Windows::Networking::UX::Internal::MBCategory::tp_UpdateRegistration",
        0xF55u,
        "updated ProviderName. old ProviderName=%ls, new ProviderName=%ls",
        v21,
        (const wchar_t *)(a2 + 26));
      WindowsCreateString((PCNZWCH)(a2 + 26), 0x15u, (HSTRING *)(a1 + 728));
      v2 = 1;
    }
    v16 = (const wchar_t *)(a2 + 12);
    v17 = WindowsGetStringRawBuffer(*(HSTRING *)(a1 + 736), 0);
    v18 = (char *)v16 - (char *)v17;
    do
    {
      v19 = *(PCWSTR)((char *)v17 + v18);
      v20 = *v17 - v19;
      if ( v20 )
        break;
      ++v17;
    }
    while ( v19 );
    if ( v20 )
    {
      v24 = WindowsGetStringRawBuffer(*(HSTRING *)(a1 + 736), 0);
      MBSettingUXLogging::Info(
        "Windows::Networking::UX::Internal::MBCategory::tp_UpdateRegistration",
        0xF62u,
        "updated ProviderId. old ProviderId=%ls, new ProviderId=%ls",
        v24,
        v16);
      WindowsCreateString(v16, 7u, (HSTRING *)(a1 + 736));
      Windows::Networking::UX::Internal::MBCategory::_SubmitThreadpoolInvoke(a1, 7);
      Windows::Networking::UX::Internal::MBCategory::tp_RefreshInterface((Windows::Networking::UX::Internal::MBCategory *)a1);
      Windows::Networking::UX::Internal::MBCategory::_SubmitThreadpoolInvoke(a1, 3);
      return;
    }
  }
  if ( v2 )
  {
    Windows::Networking::UX::Internal::MBCategory::_SubmitThreadpoolInvoke(a1, 7);
    Windows::Networking::UX::Internal::MBCategory::tp_RefreshInterface((Windows::Networking::UX::Internal::MBCategory *)a1);
  }
}

```

## disassembly

```asm
0x18000c890  push    rdi
0x18000c892  push    r14
0x18000c894  push    r15
0x18000c896  sub     rsp, 60h
0x18000c89a  mov     eax, [rdx]
0x18000c89c  xor     r15b, r15b
0x18000c89f  mov     r9d, [rcx+2E8h]
0x18000c8a6  mov     rdi, rdx
0x18000c8a9  mov     r14, rcx
0x18000c8ac  cmp     r9d, eax
0x18000c8af  jnz     loc_18000CAB5
0x18000c8b5  mov     edx, [rdi+0D0h]; unsigned int
0x18000c8bb  mov     [rsp+78h+arg_10], rbx
0x18000c8c3  test    edx, edx
0x18000c8c5  jnz     short loc_18000C90C
0x18000c8c7  mov     ebx, [rdi+4]
0x18000c8ca  mov     [rsp+78h+var_20], rbp
0x18000c8cf  mov     [rsp+78h+var_28], rsi
0x18000c8d4  cmp     ebx, 6
0x18000c8d7  ja      loc_18000CAE2
0x18000c8dd  lea     rax, qword_180061A40
0x18000c8e4  lea     rcx, qword_180061A78
0x18000c8eb  xor     ebp, ebp
0x18000c8ed  cmp     [rax], ebx
0x18000c8ef  jz      loc_18000CA43
0x18000c8f5  add     rax, 8
0x18000c8f9  cmp     rax, rcx
0x18000c8fc  jnz     short loc_18000C8EB
0x18000c8fe  mov     esi, ebp
0x18000c900  mov     edx, ebx
0x18000c902  call    MicrosoftTelemetryAssertTriggeredArgs
0x18000c907  jmp     loc_18000CA4F
0x18000c90c  call    ?_HResultFromWwanStatus@MBCategory@Internal@UX@Networking@Windows@@AEAAJK@Z; Windows::Networking::UX::Internal::MBCategory::_HResultFromWwanStatus(ulong)
0x18000c911  lea     rdx, [rsp+78h+var_38]
0x18000c916  mov     [rsp+78h+var_38], eax
0x18000c91a  lea     rcx, aMbcategoryTpUp; "MBCategory::tp_UpdateRegistration. Regi"...
0x18000c921  call    ??$WarnHRESULT@AEAY0EB@$$CBDJ@MBSettingUXLogging@@SAXAEAY0EB@$$CBD$$QEAJ@Z; MBSettingUXLogging::WarnHRESULT<char const (&)[65],long>(char const (&)[65],long &&)
0x18000c926  jmp     loc_18000C9DC
0x18000c92b  cmp     rax, rcx
0x18000c92e  jz      loc_18000CAA9
0x18000c934  mov     ebp, [rax+4]
0x18000c937  mov     r9d, ebx
0x18000c93a  mov     dword ptr [rsp+78h+var_58], ebp
0x18000c93e  lea     r8, aWwanregistermo; "wwanRegisterMode=%d, mbRegisterMode=%d"
0x18000c945  mov     edx, 16D0h; unsigned int
0x18000c94a  lea     rcx, aWindowsNetwork_159; "Windows::Networking::UX::Internal::MBCa"...
0x18000c951  call    ?Verbose@MBSettingUXLogging@@SAXPEBDK0ZZ; MBSettingUXLogging::Verbose(char const *,ulong,char const *,...)
0x18000c956  mov     r9d, [r14+2D4h]
0x18000c95d  cmp     r9d, ebp
0x18000c960  jnz     loc_18000CB98
0x18000c966  mov     rcx, [r14+2D8h]; string
0x18000c96d  lea     rbx, [rdi+1Ah]
0x18000c971  xor     edx, edx; length
0x18000c973  call    cs:__imp_WindowsGetStringRawBuffer
0x18000c979  mov     rbp, [rsp+78h+var_20]
0x18000c97e  mov     r8, rbx
0x18000c981  sub     r8, rax
0x18000c984  movzx   edx, word ptr [rax]
0x18000c987  movzx   ecx, word ptr [rax+r8]
0x18000c98c  sub     edx, ecx
0x18000c98e  jnz     short loc_18000C998
0x18000c990  add     rax, 2
0x18000c994  test    ecx, ecx
0x18000c996  jnz     short loc_18000C984
0x18000c998  test    edx, edx
0x18000c99a  jnz     short loc_18000C9F7
0x18000c99c  mov     rcx, [r14+2E0h]; string
0x18000c9a3  xor     edx, edx; length
0x18000c9a5  add     rdi, 0Ch
0x18000c9a9  call    cs:__imp_WindowsGetStringRawBuffer
0x18000c9af  mov     rsi, [rsp+78h+var_28]
0x18000c9b4  mov     r8, rdi
0x18000c9b7  sub     r8, rax
0x18000c9ba  nop     word ptr [rax+rax+00h]
0x18000c9c0  movzx   edx, word ptr [rax]
0x18000c9c3  movzx   ecx, word ptr [rax+r8]
0x18000c9c8  sub     edx, ecx
0x18000c9ca  jnz     short loc_18000C9D4
0x18000c9cc  add     rax, 2
0x18000c9d0  test    ecx, ecx
0x18000c9d2  jnz     short loc_18000C9C0
0x18000c9d4  test    edx, edx
0x18000c9d6  jnz     loc_18000CBC3
0x18000c9dc  test    r15b, r15b
0x18000c9df  jnz     loc_18000CC2E
0x18000c9e5  mov     rbx, [rsp+78h+arg_10]
0x18000c9ed  add     rsp, 60h
0x18000c9f1  pop     r15
0x18000c9f3  pop     r14
0x18000c9f5  pop     rdi
0x18000c9f6  retn
0x18000c9f7  mov     rcx, [r14+2D8h]; string
0x18000c9fe  xor     edx, edx; length
0x18000ca00  call    cs:__imp_WindowsGetStringRawBuffer
0x18000ca06  lea     r8, aUpdatedProvide; "updated ProviderName. old ProviderName="...
0x18000ca0d  mov     [rsp+78h+var_58], rbx
0x18000ca12  mov     r9, rax
0x18000ca15  lea     rcx, aWindowsNetwork_285; "Windows::Networking::UX::Internal::MBCa"...
0x18000ca1c  mov     edx, 0F55h; unsigned int
0x18000ca21  call    ?Info@MBSettingUXLogging@@SAXPEBDK0ZZ; MBSettingUXLogging::Info(char const *,ulong,char const *,...)
0x18000ca26  lea     r8, [r14+2D8h]; string
0x18000ca2d  mov     edx, 15h; length
0x18000ca32  mov     rcx, rbx; sourceString
0x18000ca35  call    cs:__imp_WindowsCreateString
0x18000ca3b  mov     r15b, 1
0x18000ca3e  jmp     loc_18000C99C
0x18000ca43  cmp     rax, rcx
0x18000ca46  jz      loc_18000C8FE
0x18000ca4c  mov     esi, [rax+4]
0x18000ca4f  mov     r9d, ebx
0x18000ca52  mov     dword ptr [rsp+78h+var_58], esi
0x18000ca56  lea     r8, aWwanregisterst; "wwanRegisterState=%d, mbRegisterState=%"...
0x18000ca5d  mov     edx, 16C8h; unsigned int
0x18000ca62  lea     rcx, aWindowsNetwork_61; "Windows::Networking::UX::Internal::MBCa"...
0x18000ca69  call    ?Verbose@MBSettingUXLogging@@SAXPEBDK0ZZ; MBSettingUXLogging::Verbose(char const *,ulong,char const *,...)
0x18000ca6e  mov     r9d, [r14+2D0h]
0x18000ca75  cmp     r9d, esi
0x18000ca78  jnz     loc_18000CB0E
0x18000ca7e  mov     ebx, [rdi+8]
0x18000ca81  cmp     ebx, 2
0x18000ca84  ja      loc_18000CB70
0x18000ca8a  lea     rax, qword_180061A78
0x18000ca91  lea     rcx, aEnterInterface; "Enter interfaceConnectivity=%d, authPro"...
0x18000ca98  cmp     [rax], ebx
0x18000ca9a  jz      loc_18000C92B
0x18000caa0  add     rax, 8
0x18000caa4  cmp     rax, rcx
0x18000caa7  jnz     short loc_18000CA98
0x18000caa9  mov     edx, ebx
0x18000caab  call    MicrosoftTelemetryAssertTriggeredArgs
0x18000cab0  jmp     loc_18000C937
0x18000cab5  lea     r8, aUpdatedNetwork; "updated NetworkError. old NetworkError="...
0x18000cabc  mov     dword ptr [rsp+78h+var_58], eax
0x18000cac0  mov     edx, 0F0Bh; unsigned int
0x18000cac5  lea     rcx, aWindowsNetwork_285; "Windows::Networking::UX::Internal::MBCa"...
0x18000cacc  call    ?Info@MBSettingUXLogging@@SAXPEBDK0ZZ; MBSettingUXLogging::Info(char const *,ulong,char const *,...)
0x18000cad1  mov     eax, [rdi]
0x18000cad3  mov     r15b, 1
0x18000cad6  mov     [r14+2E8h], eax
0x18000cadd  jmp     loc_18000C8B5
0x18000cae2  xor     ebp, ebp
0x18000cae4  mov     dword ptr [rsp+78h+var_58], 7
0x18000caec  mov     r9d, ebx
0x18000caef  lea     r8, aReceivedWwanRe; "Received WWAN_REGISTER_STATE is not sup"...
0x18000caf6  mov     edx, 0F1Ch; unsigned int
0x18000cafb  lea     rcx, aWindowsNetwork_285; "Windows::Networking::UX::Internal::MBCa"...
0x18000cb02  mov     esi, ebp
0x18000cb04  call    ?Error@MBSettingUXLogging@@SAXPEBDK0ZZ; MBSettingUXLogging::Error(char const *,ulong,char const *,...)
0x18000cb09  jmp     loc_18000CA6E
0x18000cb0e  lea     rdx, aFalse; "false"
0x18000cb15  lea     eax, [rsi-4]
0x18000cb18  cmp     eax, 1
0x18000cb1b  lea     rcx, aTrue; "true"
0x18000cb22  mov     rax, rcx
0x18000cb25  lea     r8, aUpdatedRegiste_0; "updated registerState. old registerStat"...
0x18000cb2c  setbe   bl
0x18000cb2f  test    bl, bl
0x18000cb31  cmovz   rax, rdx
0x18000cb35  cmp     byte ptr [r14+58h], 0
0x18000cb3a  mov     [rsp+78h+var_48], rax
0x18000cb3f  cmovz   rcx, rdx
0x18000cb43  mov     edx, 0F2Eh; unsigned int
0x18000cb48  mov     [rsp+78h+var_50], rcx
0x18000cb4d  lea     rcx, aWindowsNetwork_285; "Windows::Networking::UX::Internal::MBCa"...
0x18000cb54  mov     dword ptr [rsp+78h+var_58], esi
0x18000cb58  call    ?Info@MBSettingUXLogging@@SAXPEBDK0ZZ; MBSettingUXLogging::Info(char const *,ulong,char const *,...)
0x18000cb5d  mov     [r14+2D0h], esi
0x18000cb64  mov     r15b, 1
0x18000cb67  mov     [r14+58h], bl
0x18000cb6b  jmp     loc_18000CA7E
0x18000cb70  mov     r9d, ebx
0x18000cb73  mov     dword ptr [rsp+78h+var_58], 3
0x18000cb7b  lea     r8, aReceivedWwanRe_0; "Received WWAN_REGISTER_MODE is not supp"...
0x18000cb82  mov     edx, 0F3Eh; unsigned int
0x18000cb87  lea     rcx, aWindowsNetwork_285; "Windows::Networking::UX::Internal::MBCa"...
0x18000cb8e  call    ?Error@MBSettingUXLogging@@SAXPEBDK0ZZ; MBSettingUXLogging::Error(char const *,ulong,char const *,...)
0x18000cb93  jmp     loc_18000C956
0x18000cb98  lea     r8, aUpdatedRegiste; "updated registerMode. old registerMode="...
0x18000cb9f  mov     dword ptr [rsp+78h+var_58], ebp
0x18000cba3  mov     edx, 0F48h; unsigned int
0x18000cba8  lea     rcx, aWindowsNetwork_285; "Windows::Networking::UX::Internal::MBCa"...
0x18000cbaf  call    ?Info@MBSettingUXLogging@@SAXPEBDK0ZZ; MBSettingUXLogging::Info(char const *,ulong,char const *,...)
0x18000cbb4  mov     [r14+2D4h], ebp
0x18000cbbb  mov     r15b, 1
0x18000cbbe  jmp     loc_18000C966
0x18000cbc3  mov     rcx, [r14+2E0h]; string
0x18000cbca  xor     edx, edx; length
0x18000cbcc  call    cs:__imp_WindowsGetStringRawBuffer
0x18000cbd2  lea     r8, aUpdatedProvide_0; "updated ProviderId. old ProviderId=%ls,"...
0x18000cbd9  mov     [rsp+78h+var_58], rdi
0x18000cbde  mov     r9, rax
0x18000cbe1  lea     rcx, aWindowsNetwork_285; "Windows::Networking::UX::Internal::MBCa"...
0x18000cbe8  mov     edx, 0F62h; unsigned int
0x18000cbed  call    ?Info@MBSettingUXLogging@@SAXPEBDK0ZZ; MBSettingUXLogging::Info(char const *,ulong,char const *,...)
0x18000cbf2  lea     r8, [r14+2E0h]; string
0x18000cbf9  mov     edx, 7; length
0x18000cbfe  mov     rcx, rdi; sourceString
0x18000cc01  call    cs:__imp_WindowsCreateString
0x18000cc07  mov     edx, 7
0x18000cc0c  mov     rcx, r14
0x18000cc0f  call    ?_SubmitThreadpoolInvoke@MBCategory@Internal@UX@Networking@Windows@@AEAAJW4MbInterfaceChangeProperty@345@@Z; Windows::Networking::UX::Internal::MBCategory::_SubmitThreadpoolInvoke(Windows::Networking::UX::MbInterfaceChangeProperty)
0x18000cc14  mov     rcx, r14; this
0x18000cc17  call    ?tp_RefreshInterface@MBCategory@Internal@UX@Networking@Windows@@AEAAXXZ; Windows::Networking::UX::Internal::MBCategory::tp_RefreshInterface(void)
0x18000cc1c  mov     edx, 3
0x18000cc21  mov     rcx, r14
0x18000cc24  call    ?_SubmitThreadpoolInvoke@MBCategory@Internal@UX@Networking@Windows@@AEAAJW4MbInterfaceChangeProperty@345@@Z; Windows::Networking::UX::Internal::MBCategory::_SubmitThreadpoolInvoke(Windows::Networking::UX::MbInterfaceChangeProperty)
0x18000cc29  jmp     loc_18000C9E5
0x18000cc2e  mov     edx, 7
0x18000cc33  mov     rcx, r14
0x18000cc36  call    ?_SubmitThreadpoolInvoke@MBCategory@Internal@UX@Networking@Windows@@AEAAJW4MbInterfaceChangeProperty@345@@Z; Windows::Networking::UX::Internal::MBCategory::_SubmitThreadpoolInvoke(Windows::Networking::UX::MbInterfaceChangeProperty)
0x18000cc3b  mov     rcx, r14; this
0x18000cc3e  call    ?tp_RefreshInterface@MBCategory@Internal@UX@Networking@Windows@@AEAAXXZ; Windows::Networking::UX::Internal::MBCategory::tp_RefreshInterface(void)
0x18000cc43  jmp     loc_18000C9E5
```
