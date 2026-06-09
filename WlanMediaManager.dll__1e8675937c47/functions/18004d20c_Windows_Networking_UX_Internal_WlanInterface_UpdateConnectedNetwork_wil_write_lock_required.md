# Windows::Networking::UX::Internal::WlanInterface::_UpdateConnectedNetwork(wil::write_lock_required)

- ea: `0x18004d20c`
- end: `0x18004d747`
- name: `?_UpdateConnectedNetwork@WlanInterface@Internal@UX@Networking@Windows@@IEAAXUwrite_lock_required@wil@@@Z`
- size: `1339`
- prototype: ``
- caller_count: `7`
- callee_count: `18`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x18003b22c`
- `0x18003ceac`
- `0x180041c70`
- `0x180042308`
- `0x18004245c`
- `0x180042a80`
- `0x18004cb00`

## callees

- `0x180003ed0`
- `0x18000623d`
- `0x180008e30`
- `0x18000de4c`
- `0x1800121e8`
- `0x1800141a0`
- `0x180014ef8`
- `0x18001b230`
- `0x18001d568`
- `0x18002b930`
- `0x1800303b8`
- `0x1800359ac`
- `0x180049498`
- `0x18004a1b0`
- `0x18004d20c`
- `0x18004d8d0`
- `0x1800521b4`
- `0x18008e010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004d4a8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004d577`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004d670`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004d6c2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004d4a8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004d577`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004d670`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004d6c2`
- `wlanapi!AcmGenerateConnectionId` at `0x18004d2d6`
- `wlanapi!AcmGenerateConnectionId` at `0x18004d304`
- `wlanapi!AcmGenerateConnectionId` at `0x18004d2d6`
- `wlanapi!AcmGenerateConnectionId` at `0x18004d304`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall Windows::Networking::UX::Internal::WlanInterface::_UpdateConnectedNetwork(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        struct _GUID *a4)
{
  PVOID *v5; // rcx
  signed int ConnectionId; // eax
  bool v7; // sf
  int v8; // r15d
  unsigned int v9; // edi
  GUID v10; // xmm0
  int v11; // eax
  int v12; // eax
  int v13; // eax
  __int64 (__fastcall ***v14)(_QWORD, GUID *, __int64); // rdi
  __int64 (__fastcall *v15)(_QWORD, GUID *, __int64); // rbx
  int v16; // eax
  wil::details::in1diag3 *v17; // rcx
  __int64 v18; // rdx
  unsigned int i; // ebx
  GUID *v20; // r14
  __int64 v21; // rdx
  __int64 v22; // rdx
  __int64 v23; // rdx
  __int64 v24; // r8
  __int64 v25; // rcx
  __int64 v26; // rdx
  __int64 v27; // rdx
  __int64 v28; // r8
  BOOL v29; // r14d
  __int64 (__fastcall ***v30)(_QWORD, GUID *, __int64); // rdi
  __int64 (__fastcall *v31)(_QWORD, GUID *, __int64); // rbx
  __int64 ProfileBlockedReason; // rbx
  __int64 v33; // rdx
  __int64 v34; // r8
  int v36; // [rsp+20h] [rbp-89h]
  __int64 (__fastcall ***v37)(_QWORD, GUID *, __int64); // [rsp+30h] [rbp-79h] BYREF
  __int64 (__fastcall ***v38)(_QWORD, GUID *, __int64); // [rsp+38h] [rbp-71h] BYREF
  HSTRING string; // [rsp+40h] [rbp-69h] BYREF
  __int64 v40; // [rsp+48h] [rbp-61h] BYREF
  GUID Buf2; // [rsp+50h] [rbp-59h] BYREF
  HSTRING v42; // [rsp+60h] [rbp-49h] BYREF
  GUID Buf1; // [rsp+70h] [rbp-39h] BYREF
  GUID v44; // [rsp+80h] [rbp-29h] BYREF
  struct _DOT11_SSID v45; // [rsp+90h] [rbp-19h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+108h] [rbp+5Fh]

  v5 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 202, &WPP_1d38a1f9e6943a38c061f6c5b3807675_Traceguids);
    v5 = (PVOID *)WPP_GLOBAL_Control;
  }
  Buf2 = GUID_NULL;
  v44 = GUID_NULL;
  v38 = 0;
  if ( (unsigned int)(*(_DWORD *)(a1 + 1264) - 2) <= 3 )
  {
    memset(&v45, 0, 32);
    if ( (unsigned int)Windows::Networking::UX::Internal::AccessPointHelpers::GetTetheringNetworkSignature(
                         (Windows::Networking::UX::Internal::AccessPointHelpers *)(a1 + 648),
                         (const struct _GUID *)(a1 + 564),
                         &v45,
                         a4) )
    {
      ConnectionId = AcmGenerateConnectionId(a1 + 648, a1 + 44, &v45);
      v7 = ConnectionId < 0;
      if ( ConnectionId > 0 )
      {
        ConnectionId = (unsigned __int16)ConnectionId | 0x80070000;
        v7 = ConnectionId < 0;
      }
      if ( v7 )
      {
        v9 = 1;
      }
      else
      {
        v8 = *(_DWORD *)(a1 + 48);
        *(_DWORD *)(a1 + 48) = 1;
        v9 = 2;
        ConnectionId = AcmGenerateConnectionId(a1 + 648, a1 + 44, &v45.ucSSID[12]);
        if ( ConnectionId > 0 )
          ConnectionId = (unsigned __int16)ConnectionId | 0x80070000;
        *(_DWORD *)(a1 + 48) = v8;
      }
      if ( ConnectionId < 0 )
        goto LABEL_14;
    }
    else
    {
      v9 = 1;
    }
    for ( i = 0; i < v9; ++i )
    {
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v38, a2, a3);
      v20 = (GUID *)((char *)&v45 + 16 * i);
      Buf1 = *v20;
      if ( (int)Windows::Networking::UX::Internal::WlanInterface::_GetAvailableNetwork(a1, v21, &Buf1, &v38) < 0 )
      {
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v38, a2, a3);
        if ( (int)Windows::Networking::UX::Internal::WlanInterface::_GetNetworkByInfoSignature(a1, v22, v20, &v38) < 0 )
          continue;
      }
      v10 = *v20;
      v44 = *v20;
      goto LABEL_15;
    }
LABEL_14:
    v10 = v44;
LABEL_15:
    if ( !v38 )
      goto LABEL_43;
    Buf2 = v10;
    v37 = 0;
    if ( (int)Microsoft::WRL::ComPtr<Windows::Networking::UX::IAvailableNetwork>::As<Windows::Networking::UX::Internal::IWlanAvailableNetwork>(
                &v38,
                (__int64)&v37,
                a3) < 0 )
    {
LABEL_42:
      Windows::Networking::UX::Internal::WlanInterface::_UpdateNetworkConnectivity(
        a1,
        v38,
        *(unsigned int *)(a1 + 1264));
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v37, v23, v24);
LABEL_43:
      v5 = (PVOID *)WPP_GLOBAL_Control;
      goto LABEL_44;
    }
    ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64), _QWORD))(*v37)[7])(
      v37,
      *(unsigned int *)(a1 + 620));
    ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64), _QWORD))(*v37)[31])(v37, 0);
    ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64), _QWORD))(*v37)[32])(
      v37,
      *(unsigned int *)(a1 + 1272));
    LODWORD(v40) = 0;
    if ( ((int (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64), __int64 *))(*v38)[18])(v38, &v40) >= 0
      && (unsigned int)(v40 - 10) <= 1 )
    {
      v11 = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64), __int64))(*v37)[27])(v37, 11);
      if ( v11 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0xA36,
          (unsigned int)"onecoreuap\\net\\ux\\wlanmediamanager\\lib\\wlaninterface.cpp",
          (const char *)(unsigned int)v11,
          v36);
    }
    wil::EnterCriticalSection(&Buf1, a1 + 752);
    if ( *(_DWORD *)(a1 + 1264) == 2 || *(_QWORD *)(a1 + 792) )
      goto LABEL_41;
    v12 = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64), __int64))(*v37)[29])(v37, a1 + 52);
    if ( v12 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0xA3D,
        (unsigned int)"onecoreuap\\net\\ux\\wlanmediamanager\\lib\\wlaninterface.cpp",
        (const char *)(unsigned int)v12,
        v36);
    v13 = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64), __int64))(*v37)[30])(v37, a1 + 52);
    if ( v13 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0xA3E,
        (unsigned int)"onecoreuap\\net\\ux\\wlanmediamanager\\lib\\wlaninterface.cpp",
        (const char *)(unsigned int)v13,
        v36);
    if ( (unsigned int)(v40 - 10) > 1 )
    {
LABEL_41:
      wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(&Buf1);
      goto LABEL_42;
    }
    string = 0;
    v14 = v38;
    v15 = (*v38)[6];
    WindowsDeleteString(0);
    string = 0;
    v16 = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64), HSTRING *))v15)(v14, &string);
    v17 = retaddr;
    if ( v16 >= 0 )
    {
      v42 = string;
      v16 = Microsoft::WRL::Wrappers::HString::Set((HSTRING *)(a1 + 1232), &v42);
      v17 = retaddr;
      if ( v16 >= 0 )
      {
LABEL_40:
        WindowsDeleteString(string);
        goto LABEL_41;
      }
      v18 = 2633;
    }
    else
    {
      v18 = 2631;
    }
    wil::details::in1diag3::_Log_Hr(
      v17,
      (void *)v18,
      (unsigned int)"onecoreuap\\net\\ux\\wlanmediamanager\\lib\\wlaninterface.cpp",
      (const char *)(unsigned int)v16,
      v36);
    goto LABEL_40;
  }
LABEL_44:
  if ( v5 != &WPP_GLOBAL_Control && (*((_BYTE *)v5 + 28) & 8) != 0 )
    WPP_SF_q_guid_((unsigned int)v5[2], a2, a3, *(_QWORD *)(a1 + 672), (__int64)&v44);
  v25 = *(_QWORD *)(a1 + 672);
  if ( v25 )
  {
    Buf1 = 0;
    if ( (*(int (__fastcall **)(__int64, GUID *))(*(_QWORD *)v25 + 64LL))(v25, &Buf1) >= 0 )
    {
      if ( memcmp_0(&Buf1, &Buf2, 0x10u) )
      {
        v37 = 0;
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v37, a2, a3);
        Buf2 = Buf1;
        if ( (int)Windows::Networking::UX::Internal::WlanInterface::_GetAvailableNetwork(a1, v26, &Buf2, &v37) >= 0 )
        {
          v29 = 0;
          v40 = 0;
          if ( (int)Microsoft::WRL::ComPtr<Windows::Networking::UX::IAvailableNetwork>::As<Windows::Networking::UX::Internal::IWlanAvailableNetwork>(
                      &v37,
                      (__int64)&v40,
                      v28) >= 0 )
          {
            string = 0;
            v30 = v37;
            v31 = (*v37)[7];
            WindowsDeleteString(0);
            string = 0;
            if ( ((int (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64), HSTRING *))v31)(v30, &string) >= 0 )
            {
              ProfileBlockedReason = (unsigned int)Windows::Networking::UX::Internal::WlanClient::GetProfileBlockedReason(
                                                     *(_QWORD *)(a1 + 24),
                                                     a1 + 648,
                                                     string);
              (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v40 + 248LL))(v40, ProfileBlockedReason);
              v29 = ProfileBlockedReason != 0;
            }
            WindowsDeleteString(string);
          }
          Windows::Networking::UX::Internal::WlanInterface::_UpdateNetworkConnectivity(a1, v37, v29);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(
            &v40,
            v33,
            v34);
        }
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v37, v27, v28);
      }
    }
  }
  *(_QWORD *)(a1 + 672) = v38;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 204, &WPP_1d38a1f9e6943a38c061f6c5b3807675_Traceguids);
  return Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v38, a2, a3);
}

```

## disassembly

```asm
0x18004d20c  push    rbp
0x18004d20e  push    rbx
0x18004d20f  push    rsi
0x18004d210  push    rdi
0x18004d211  push    r12
0x18004d213  push    r13
0x18004d215  push    r14
0x18004d217  push    r15
0x18004d219  lea     rbp, [rsp-1Fh]
0x18004d21e  sub     rsp, 0C8h
0x18004d225  mov     rax, cs:__security_cookie
0x18004d22c  xor     rax, rsp
0x18004d22f  mov     qword ptr [rbp+57h+var_70.ucSSID+1Ch], rax
0x18004d233  mov     rsi, rcx
0x18004d236  lea     r15, WPP_GLOBAL_Control
0x18004d23d  mov     rcx, cs:WPP_GLOBAL_Control
0x18004d244  cmp     rcx, r15
0x18004d247  jz      short loc_18004D26B
0x18004d249  test    byte ptr [rcx+1Ch], 8
0x18004d24d  jz      short loc_18004D26B
0x18004d24f  mov     edx, 0CAh
0x18004d254  lea     r8, WPP_1d38a1f9e6943a38c061f6c5b3807675_Traceguids
0x18004d25b  mov     rcx, [rcx+10h]
0x18004d25f  call    WPP_SF_
0x18004d264  mov     rcx, cs:WPP_GLOBAL_Control
0x18004d26b  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18004d272  movdqu  [rbp+57h+Buf2], xmm0
0x18004d277  movdqu  [rbp+57h+var_80], xmm0
0x18004d27c  xor     r12d, r12d
0x18004d27f  mov     [rbp+57h+var_C8], r12
0x18004d283  mov     eax, [rsi+4F0h]
0x18004d289  sub     eax, 2
0x18004d28c  lea     r13d, [r12+1]
0x18004d291  cmp     eax, 3
0x18004d294  ja      loc_18004D5AB
0x18004d29a  mov     [rbp+57h+var_70.uSSIDLength], r12d
0x18004d29e  xorps   xmm0, xmm0
0x18004d2a1  movups  xmmword ptr [rbp+57h+var_70.ucSSID], xmm0
0x18004d2a5  movups  xmmword ptr [rbp+57h+var_70.ucSSID+0Ch], xmm0
0x18004d2a9  lea     rbx, [rsi+288h]
0x18004d2b0  lea     rdx, [rsi+234h]; struct _GUID *
0x18004d2b7  lea     r8, [rbp+57h+var_70]; struct _DOT11_SSID *
0x18004d2bb  mov     rcx, rbx; this
0x18004d2be  call    ?GetTetheringNetworkSignature@AccessPointHelpers@Internal@UX@Networking@Windows@@YAJAEBU_GUID@@AEBU_DOT11_SSID@@PEAU6@@Z; Windows::Networking::UX::Internal::AccessPointHelpers::GetTetheringNetworkSignature(_GUID const &,_DOT11_SSID const &,_GUID *)
0x18004d2c3  test    eax, eax
0x18004d2c5  jz      loc_18004D4D3
0x18004d2cb  lea     r8, [rbp+57h+var_70]
0x18004d2cf  lea     rdx, [rsi+2Ch]
0x18004d2d3  mov     rcx, rbx
0x18004d2d6  call    cs:__imp_AcmGenerateConnectionId
0x18004d2dc  test    eax, eax
0x18004d2de  jle     short loc_18004D2EA
0x18004d2e0  movzx   eax, ax
0x18004d2e3  or      eax, 80070000h
0x18004d2e8  test    eax, eax
0x18004d2ea  js      short loc_18004D323
0x18004d2ec  mov     r15d, [rsi+30h]
0x18004d2f0  mov     [rsi+30h], r13d
0x18004d2f4  mov     edi, 2
0x18004d2f9  lea     r8, [rbp+57h+var_70.ucSSID+0Ch]
0x18004d2fd  lea     rdx, [rsi+2Ch]
0x18004d301  mov     rcx, rbx
0x18004d304  call    cs:__imp_AcmGenerateConnectionId
0x18004d30a  test    eax, eax
0x18004d30c  jle     short loc_18004D316
0x18004d30e  movzx   eax, ax
0x18004d311  or      eax, 80070000h
0x18004d316  mov     [rsi+30h], r15d
0x18004d31a  lea     r15, WPP_GLOBAL_Control
0x18004d321  jmp     short loc_18004D326
0x18004d323  mov     edi, r13d
0x18004d326  test    eax, eax
0x18004d328  jns     loc_18004D4D6
0x18004d32e  movaps  xmm0, [rbp+57h+var_80]
0x18004d332  cmp     [rbp+57h+var_C8], r12
0x18004d336  jz      loc_18004D5A4
0x18004d33c  movdqa  [rbp+57h+Buf2], xmm0
0x18004d341  mov     [rbp+57h+var_D0], r12
0x18004d345  lea     rdx, [rbp+57h+var_D0]
0x18004d349  lea     rcx, [rbp+57h+var_C8]
0x18004d34d  call    ??$As@UIWlanAvailableNetwork@Internal@UX@Networking@Windows@@@?$ComPtr@UIAvailableNetwork@UX@Networking@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIWlanAvailableNetwork@Internal@UX@Networking@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::Networking::UX::IAvailableNetwork>::As<Windows::Networking::UX::Internal::IWlanAvailableNetwork>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Networking::UX::Internal::IWlanAvailableNetwork>>)
0x18004d352  test    eax, eax
0x18004d354  js      loc_18004D587
0x18004d35a  mov     rcx, [rbp+57h+var_D0]
0x18004d35e  mov     rax, [rcx]
0x18004d361  mov     edx, [rsi+26Ch]
0x18004d367  mov     rax, [rax+38h]
0x18004d36b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d370  mov     rcx, [rbp+57h+var_D0]
0x18004d374  mov     rax, [rcx]
0x18004d377  xor     edx, edx
0x18004d379  mov     rax, [rax+0F8h]
0x18004d380  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d385  mov     rcx, [rbp+57h+var_D0]
0x18004d389  mov     rax, [rcx]
0x18004d38c  mov     edx, [rsi+4F8h]
0x18004d392  mov     rax, [rax+100h]
0x18004d399  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d39e  mov     dword ptr [rbp+57h+var_B8], r12d
0x18004d3a2  mov     rcx, [rbp+57h+var_C8]
0x18004d3a6  mov     rax, [rcx]
0x18004d3a9  lea     rdx, [rbp+57h+var_B8]
0x18004d3ad  mov     rax, [rax+90h]
0x18004d3b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d3b9  lea     r14, aOnecoreuapNetU_20; "onecoreuap\\net\\ux\\wlanmediamanager\\"...
0x18004d3c0  test    eax, eax
0x18004d3c2  js      short loc_18004D3FF
0x18004d3c4  mov     eax, dword ptr [rbp+57h+var_B8]
0x18004d3c7  add     eax, 0FFFFFFF6h
0x18004d3ca  cmp     eax, r13d
0x18004d3cd  ja      short loc_18004D3FF
0x18004d3cf  mov     rcx, [rbp+57h+var_D0]
0x18004d3d3  mov     rax, [rcx]
0x18004d3d6  mov     edx, 0Bh
0x18004d3db  mov     rax, [rax+0D8h]
0x18004d3e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d3e7  mov     rcx, [rbp+5Fh]; this
0x18004d3eb  test    eax, eax
0x18004d3ed  jns     short loc_18004D3FF
0x18004d3ef  mov     r9d, eax; char *
0x18004d3f2  mov     r8, r14; unsigned int
0x18004d3f5  mov     edx, 0A36h; void *
0x18004d3fa  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18004d3ff  lea     rdx, [rsi+2F0h]
0x18004d406  lea     rcx, [rbp+57h+Buf1]
0x18004d40a  call    ?EnterCriticalSection@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_CRITICAL_SECTION@@@Z; wil::EnterCriticalSection(_RTL_CRITICAL_SECTION *)
0x18004d40f  nop
0x18004d410  cmp     dword ptr [rsi+4F0h], 2
0x18004d417  jz      loc_18004D57E
0x18004d41d  cmp     [rsi+318h], r12
0x18004d424  jnz     loc_18004D57E
0x18004d42a  mov     rcx, [rbp+57h+var_D0]
0x18004d42e  mov     rax, [rcx]
0x18004d431  lea     rdx, [rsi+34h]
0x18004d435  mov     rax, [rax+0E8h]
0x18004d43c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d441  mov     rcx, [rbp+5Fh]; this
0x18004d445  test    eax, eax
0x18004d447  jns     short loc_18004D459
0x18004d449  mov     r9d, eax; char *
0x18004d44c  mov     r8, r14; unsigned int
0x18004d44f  mov     edx, 0A3Dh; void *
0x18004d454  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18004d459  mov     rcx, [rbp+57h+var_D0]
0x18004d45d  mov     rax, [rcx]
0x18004d460  lea     rdx, [rsi+34h]
0x18004d464  mov     rax, [rax+0F0h]
0x18004d46b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d470  mov     rcx, [rbp+5Fh]; this
0x18004d474  test    eax, eax
0x18004d476  jns     short loc_18004D488
0x18004d478  mov     r9d, eax; char *
0x18004d47b  mov     r8, r14; unsigned int
0x18004d47e  mov     edx, 0A3Eh; void *
0x18004d483  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18004d488  mov     eax, dword ptr [rbp+57h+var_B8]
0x18004d48b  add     eax, 0FFFFFFF6h
0x18004d48e  cmp     eax, r13d
0x18004d491  ja      loc_18004D57E
0x18004d497  mov     [rbp+57h+string], r12
0x18004d49b  mov     rdi, [rbp+57h+var_C8]
0x18004d49f  mov     rax, [rdi]
0x18004d4a2  mov     rbx, [rax+30h]
0x18004d4a6  xor     ecx, ecx; string
0x18004d4a8  call    cs:__imp_WindowsDeleteString
0x18004d4ae  mov     [rbp+57h+string], r12
0x18004d4b2  lea     rdx, [rbp+57h+string]
0x18004d4b6  mov     rcx, rdi
0x18004d4b9  mov     rax, rbx
0x18004d4bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d4c1  mov     rcx, [rbp+5Fh]
0x18004d4c5  test    eax, eax
0x18004d4c7  jns     short loc_18004D542
0x18004d4c9  mov     edx, 0A47h
0x18004d4ce  jmp     loc_18004D567
0x18004d4d3  mov     edi, r13d
0x18004d4d6  mov     ebx, r12d
0x18004d4d9  cmp     ebx, edi
0x18004d4db  jnb     loc_18004D32E
0x18004d4e1  lea     rcx, [rbp+57h+var_C8]
0x18004d4e5  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18004d4ea  mov     eax, ebx
0x18004d4ec  shl     rax, 4
0x18004d4f0  lea     r14, [rbp+57h+var_70]
0x18004d4f4  add     r14, rax
0x18004d4f7  movups  xmm0, xmmword ptr [r14]
0x18004d4fb  movdqu  [rbp+57h+Buf1], xmm0
0x18004d500  lea     r9, [rbp+57h+var_C8]
0x18004d504  lea     r8, [rbp+57h+Buf1]
0x18004d508  mov     rcx, rsi
0x18004d50b  call    ?_GetAvailableNetwork@WlanInterface@Internal@UX@Networking@Windows@@IEAAJUread_lock_required@wil@@U_GUID@@PEAPEAUIAvailableNetwork@345@@Z; Windows::Networking::UX::Internal::WlanInterface::_GetAvailableNetwork(wil::read_lock_required,_GUID,Windows::Networking::UX::IAvailableNetwork * *)
0x18004d510  test    eax, eax
0x18004d512  jns     short loc_18004D535
0x18004d514  lea     rcx, [rbp+57h+var_C8]
0x18004d518  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18004d51d  lea     r9, [rbp+57h+var_C8]
0x18004d521  mov     r8, r14
0x18004d524  mov     rcx, rsi
0x18004d527  call    ?_GetNetworkByInfoSignature@WlanInterface@Internal@UX@Networking@Windows@@IEAAJUread_lock_required@wil@@AEBU_GUID@@PEAPEAUIAvailableNetwork@345@@Z; Windows::Networking::UX::Internal::WlanInterface::_GetNetworkByInfoSignature(wil::read_lock_required,_GUID const &,Windows::Networking::UX::IAvailableNetwork * *)
0x18004d52c  test    eax, eax
0x18004d52e  jns     short loc_18004D535
0x18004d530  add     ebx, r13d
0x18004d533  jmp     short loc_18004D4D9
0x18004d535  movups  xmm0, xmmword ptr [r14]
0x18004d539  movaps  [rbp+57h+var_80], xmm0
0x18004d53d  jmp     loc_18004D332
0x18004d542  mov     rax, [rbp+57h+string]
0x18004d546  mov     [rbp+57h+var_A0], rax
0x18004d54a  lea     rcx, [rsi+4D0h]; newString
0x18004d551  lea     rdx, [rbp+57h+var_A0]; HSTRING *
0x18004d555  call    ?Set@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEAUHSTRING__@@@Z; Microsoft::WRL::Wrappers::HString::Set(HSTRING__ * const &)
0x18004d55a  mov     rcx, [rbp+5Fh]; this
0x18004d55e  test    eax, eax
0x18004d560  jns     short loc_18004D573
0x18004d562  mov     edx, 0A49h; void *
0x18004d567  mov     r9d, eax; char *
0x18004d56a  mov     r8, r14; unsigned int
0x18004d56d  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18004d572  nop
0x18004d573  mov     rcx, [rbp+57h+string]; string
0x18004d577  call    cs:__imp_WindowsDeleteString
0x18004d57d  nop
0x18004d57e  lea     rcx, [rbp+57h+Buf1]
0x18004d582  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x18004d587  mov     r8d, [rsi+4F0h]
0x18004d58e  mov     rdx, [rbp+57h+var_C8]
0x18004d592  mov     rcx, rsi
0x18004d595  call    ?_UpdateNetworkConnectivity@WlanInterface@Internal@UX@Networking@Windows@@IEAAJPEAUIAvailableNetwork@345@W4NetworkConnectivity@345@@Z; Windows::Networking::UX::Internal::WlanInterface::_UpdateNetworkConnectivity(Windows::Networking::UX::IAvailableNetwork *,Windows::Networking::UX::NetworkConnectivity)
0x18004d59a  nop
0x18004d59b  lea     rcx, [rbp+57h+var_D0]
0x18004d59f  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18004d5a4  mov     rcx, cs:WPP_GLOBAL_Control
0x18004d5ab  cmp     rcx, r15
0x18004d5ae  jz      short loc_18004D5CF
0x18004d5b0  test    byte ptr [rcx+1Ch], 8
0x18004d5b4  jz      short loc_18004D5CF
0x18004d5b6  lea     rax, [rbp+57h+var_80]
0x18004d5ba  mov     qword ptr [rsp+100h+var_E0], rax
0x18004d5bf  mov     r9, [rsi+2A0h]
0x18004d5c6  mov     rcx, [rcx+10h]
0x18004d5ca  call    WPP_SF_q_guid_
0x18004d5cf  mov     rcx, [rsi+2A0h]
0x18004d5d6  test    rcx, rcx
0x18004d5d9  jz      loc_18004D6EB
0x18004d5df  xorps   xmm0, xmm0
0x18004d5e2  movups  [rbp+57h+Buf1], xmm0
0x18004d5e6  mov     rax, [rcx]
0x18004d5e9  lea     rdx, [rbp+57h+Buf1]
0x18004d5ed  mov     rax, [rax+40h]
0x18004d5f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d5f6  test    eax, eax
0x18004d5f8  js      loc_18004D6EB
0x18004d5fe  mov     r8d, 10h; Size
0x18004d604  lea     rdx, [rbp+57h+Buf2]; Buf2
0x18004d608  lea     rcx, [rbp+57h+Buf1]; Buf1
0x18004d60c  call    memcmp_0
0x18004d611  test    eax, eax
0x18004d613  jz      loc_18004D6EB
0x18004d619  mov     [rbp+57h+var_D0], r12
0x18004d61d  lea     rcx, [rbp+57h+var_D0]
0x18004d621  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18004d626  movaps  xmm0, [rbp+57h+Buf1]
0x18004d62a  movdqa  [rbp+57h+Buf2], xmm0
0x18004d62f  lea     r9, [rbp+57h+var_D0]
0x18004d633  lea     r8, [rbp+57h+Buf2]
0x18004d637  mov     rcx, rsi
0x18004d63a  call    ?_GetAvailableNetwork@WlanInterface@Internal@UX@Networking@Windows@@IEAAJUread_lock_required@wil@@U_GUID@@PEAPEAUIAvailableNetwork@345@@Z; Windows::Networking::UX::Internal::WlanInterface::_GetAvailableNetwork(wil::read_lock_required,_GUID,Windows::Networking::UX::IAvailableNetwork * *)
0x18004d63f  test    eax, eax
0x18004d641  js      loc_18004D6E2
0x18004d647  mov     r14d, r12d
0x18004d64a  mov     [rbp+57h+var_B8], r12
0x18004d64e  lea     rdx, [rbp+57h+var_B8]
0x18004d652  lea     rcx, [rbp+57h+var_D0]
0x18004d656  call    ??$As@UIWlanAvailableNetwork@Internal@UX@Networking@Windows@@@?$ComPtr@UIAvailableNetwork@UX@Networking@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIWlanAvailableNetwork@Internal@UX@Networking@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::Networking::UX::IAvailableNetwork>::As<Windows::Networking::UX::Internal::IWlanAvailableNetwork>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Networking::UX::Internal::IWlanAvailableNetwork>>)
0x18004d65b  test    eax, eax
0x18004d65d  js      short loc_18004D6C8
0x18004d65f  mov     [rbp+57h+string], r12
0x18004d663  mov     rdi, [rbp+57h+var_D0]
0x18004d667  mov     rax, [rdi]
0x18004d66a  mov     rbx, [rax+38h]
0x18004d66e  xor     ecx, ecx; string
0x18004d670  call    cs:__imp_WindowsDeleteString
0x18004d676  mov     [rbp+57h+string], r12
0x18004d67a  lea     rdx, [rbp+57h+string]
0x18004d67e  mov     rcx, rdi
0x18004d681  mov     rax, rbx
0x18004d684  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d689  test    eax, eax
0x18004d68b  js      short loc_18004D6BE
0x18004d68d  lea     rdx, [rsi+288h]
0x18004d694  mov     r8, [rbp+57h+string]
0x18004d698  mov     rcx, [rsi+18h]
0x18004d69c  call    ?GetProfileBlockedReason@WlanClient@Internal@UX@Networking@Windows@@QEAA?AW4NetworkBlockedReason@345@AEBU_GUID@@PEAUHSTRING__@@@Z; Windows::Networking::UX::Internal::WlanClient::GetProfileBlockedReason(_GUID const &,HSTRING__ *)
0x18004d6a1  mov     ebx, eax
0x18004d6a3  mov     rcx, [rbp+57h+var_B8]
0x18004d6a7  mov     rdx, [rcx]
0x18004d6aa  mov     rax, [rdx+0F8h]
0x18004d6b1  mov     edx, ebx
0x18004d6b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d6b8  test    ebx, ebx
  ... truncated ...
```
