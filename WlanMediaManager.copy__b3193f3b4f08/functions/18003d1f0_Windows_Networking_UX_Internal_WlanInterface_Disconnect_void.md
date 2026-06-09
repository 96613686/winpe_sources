# Windows::Networking::UX::Internal::WlanInterface::Disconnect(void)

- ea: `0x18003d1f0`
- end: `0x18003d488`
- name: `?Disconnect@WlanInterface@Internal@UX@Networking@Windows@@QEAAJXZ`
- size: `664`
- prototype: `__int64 __fastcall(Windows::Networking::UX::Internal::WlanInterface *__hidden this)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180026b00`

## callees

- `0x180003ed0`
- `0x180008e30`
- `0x18000de4c`
- `0x1800121e8`
- `0x1800141a0`
- `0x18001d4d4`
- `0x18003ab80`
- `0x18003d1f0`
- `0x180047bb4`
- `0x18004a558`
- `0x1800748ac`
- `0x18008e010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003d301`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003d3f7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003d301`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003d3f7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003d2c3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003d3a2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003d3d0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003d455`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003d2c3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003d3a2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003d3d0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003d455`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall Windows::Networking::UX::Internal::WlanInterface::Disconnect(
        Windows::Networking::UX::Internal::WlanInterface *this)
{
  struct Windows::Networking::UX::IAvailableNetwork *v2; // rbx
  int (__fastcall *v3)(struct Windows::Networking::UX::IAvailableNetwork *, HSTRING *); // rdi
  __int64 v4; // rdi
  const unsigned __int16 *StringRawBuffer; // rax
  int v6; // eax
  __int64 v7; // rdx
  __int64 v8; // r8
  int (__fastcall *v9)(struct Windows::Networking::UX::IAvailableNetwork *, GUID *, _BYTE *); // rdi
  __int64 v10; // rdx
  __int64 v11; // r8
  unsigned int v12; // r14d
  int (__fastcall *v13)(struct Windows::Networking::UX::IAvailableNetwork *, HSTRING *); // rdi
  const unsigned __int16 *v14; // rax
  __int64 v15; // rdx
  __int64 v16; // r8
  _BYTE v18[8]; // [rsp+20h] [rbp-48h] BYREF
  HSTRING string; // [rsp+28h] [rbp-40h] BYREF
  HSTRING v20; // [rsp+30h] [rbp-38h] BYREF
  struct Windows::Networking::UX::IAvailableNetwork *v21; // [rsp+38h] [rbp-30h] BYREF
  _BYTE v22[20]; // [rsp+40h] [rbp-28h] BYREF
  int v23; // [rsp+54h] [rbp-14h]

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 74, &WPP_1d38a1f9e6943a38c061f6c5b3807675_Traceguids);
  v21 = 0;
  *((_BYTE *)this + 1168) = 1;
  wil::EnterCriticalSection(&string, (char *)this + 1304);
  Microsoft::WRL::ComPtr<Windows::Networking::UX::IAvailableNetwork>::operator=(&v21);
  wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(&string);
  v18[0] = 0;
  v2 = v21;
  if ( v21
    && (*(int (__fastcall **)(struct Windows::Networking::UX::IAvailableNetwork *, _QWORD, _BYTE *))(*(_QWORD *)v21 + 160LL))(
         v21,
         0,
         v18) >= 0
    && v18[0] )
  {
    string = 0;
    v3 = *(int (__fastcall **)(struct Windows::Networking::UX::IAvailableNetwork *, HSTRING *))(*(_QWORD *)v2 + 48LL);
    WindowsDeleteString(0);
    string = 0;
    if ( v3(v2, &string) >= 0 )
    {
      Windows::Networking::UX::Internal::WlanInterface::_GetNetworkInterfaceGuid(this, (struct _GUID *)v22, v2);
      v4 = *((_QWORD *)this + 3);
      StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
      v6 = Windows::Networking::UX::Internal::ProfileManager::SetProfileAutoConnect(
             (Windows::Networking::UX::Internal::ProfileManager *)(v4 + 656),
             (const struct _GUID *)v22,
             StringRawBuffer,
             0);
      if ( v6 >= 0 )
      {
        *(_QWORD *)v22 = 0;
        v9 = **(int (__fastcall ***)(struct Windows::Networking::UX::IAvailableNetwork *, GUID *, _BYTE *))v2;
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v22, v7, v8);
        if ( v9(v2, &GUID_ac2798f8_4bd2_4d64_be61_7002641cd494, v22) >= 0 )
          (*(void (__fastcall **)(_QWORD, _QWORD))(**(_QWORD **)v22 + 192LL))(*(_QWORD *)v22, 0);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v22, v10, v11);
      }
      else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          75,
          &WPP_1d38a1f9e6943a38c061f6c5b3807675_Traceguids,
          (unsigned int)v6);
      }
    }
    WindowsDeleteString(string);
  }
  v12 = (*(__int64 (__fastcall **)(Windows::Networking::UX::Internal::WlanInterface *))(*(_QWORD *)this + 24LL))(this);
  v20 = 0;
  if ( v2 )
  {
    v13 = *(int (__fastcall **)(struct Windows::Networking::UX::IAvailableNetwork *, HSTRING *))(*(_QWORD *)v2 + 48LL);
    WindowsDeleteString(0);
    v20 = 0;
    if ( v13(v2, &v20) >= 0 )
    {
      v14 = WindowsGetStringRawBuffer(v20, 0);
      *(_DWORD *)v22 = 13;
      *(_OWORD *)&v22[4] = *(_OWORD *)((char *)this + 1204);
      v23 = 71;
      NetworkingTriageScenario::GetConnected::UXModelWiFiDisconnectAction(
        (const struct NetworkingTriageScenario::GetConnected::RequiredFields *)v22,
        v14,
        v12);
    }
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 76, &WPP_1d38a1f9e6943a38c061f6c5b3807675_Traceguids, v12);
  WindowsDeleteString(v20);
  v20 = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v21, v15, v16);
  return v12;
}

```

## disassembly

```asm
0x18003d1f0  push    rbp
0x18003d1f2  push    rbx
0x18003d1f3  push    rsi
0x18003d1f4  push    rdi
0x18003d1f5  push    r12
0x18003d1f7  push    r14
0x18003d1f9  mov     rbp, rsp
0x18003d1fc  sub     rsp, 68h
0x18003d200  mov     rax, cs:__security_cookie
0x18003d207  xor     rax, rsp
0x18003d20a  mov     [rbp+var_10], rax
0x18003d20e  mov     rsi, rcx
0x18003d211  lea     r12, WPP_GLOBAL_Control
0x18003d218  mov     rcx, cs:WPP_GLOBAL_Control
0x18003d21f  cmp     rcx, r12
0x18003d222  jz      short loc_18003D23F
0x18003d224  test    byte ptr [rcx+1Ch], 8
0x18003d228  jz      short loc_18003D23F
0x18003d22a  mov     edx, 4Ah ; 'J'
0x18003d22f  lea     r8, WPP_1d38a1f9e6943a38c061f6c5b3807675_Traceguids
0x18003d236  mov     rcx, [rcx+10h]
0x18003d23a  call    WPP_SF_
0x18003d23f  mov     [rbp+var_30], 0
0x18003d247  mov     byte ptr [rsi+490h], 1
0x18003d24e  lea     rdx, [rsi+518h]
0x18003d255  lea     rcx, [rbp+string]
0x18003d259  call    ?EnterCriticalSection@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_CRITICAL_SECTION@@@Z; wil::EnterCriticalSection(_RTL_CRITICAL_SECTION *)
0x18003d25e  mov     rdx, [rsi+2A0h]
0x18003d265  lea     rcx, [rbp+var_30]
0x18003d269  call    ??4?$ComPtr@UIAvailableNetwork@UX@Networking@Windows@@@WRL@Microsoft@@QEAAAEAV012@PEAUIAvailableNetwork@UX@Networking@Windows@@@Z; Microsoft::WRL::ComPtr<Windows::Networking::UX::IAvailableNetwork>::operator=(Windows::Networking::UX::IAvailableNetwork *)
0x18003d26e  lea     rcx, [rbp+string]
0x18003d272  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x18003d277  mov     [rbp+var_48], 0
0x18003d27b  mov     rbx, [rbp+var_30]
0x18003d27f  test    rbx, rbx
0x18003d282  jz      loc_18003D3A8
0x18003d288  mov     rax, [rbx]
0x18003d28b  lea     r8, [rbp+var_48]
0x18003d28f  xor     edx, edx
0x18003d291  mov     rcx, rbx
0x18003d294  mov     rax, [rax+0A0h]
0x18003d29b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d2a0  test    eax, eax
0x18003d2a2  js      loc_18003D3A8
0x18003d2a8  cmp     [rbp+var_48], 0
0x18003d2ac  jz      loc_18003D3A8
0x18003d2b2  mov     [rbp+string], 0
0x18003d2ba  mov     rax, [rbx]
0x18003d2bd  mov     rdi, [rax+30h]
0x18003d2c1  xor     ecx, ecx; string
0x18003d2c3  call    cs:__imp_WindowsDeleteString
0x18003d2c9  mov     [rbp+string], 0
0x18003d2d1  lea     rdx, [rbp+string]
0x18003d2d5  mov     rcx, rbx
0x18003d2d8  mov     rax, rdi
0x18003d2db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d2e0  test    eax, eax
0x18003d2e2  js      loc_18003D39E
0x18003d2e8  mov     r8, rbx; struct Windows::Networking::UX::IAvailableNetwork *
0x18003d2eb  lea     rdx, [rbp+var_28]; retstr
0x18003d2ef  mov     rcx, rsi; this
0x18003d2f2  call    ?_GetNetworkInterfaceGuid@WlanInterface@Internal@UX@Networking@Windows@@IEAA?AU_GUID@@PEAUIAvailableNetwork@345@@Z; Windows::Networking::UX::Internal::WlanInterface::_GetNetworkInterfaceGuid(Windows::Networking::UX::IAvailableNetwork *)
0x18003d2f7  mov     rdi, [rsi+18h]
0x18003d2fb  xor     edx, edx; length
0x18003d2fd  mov     rcx, [rbp+string]; string
0x18003d301  call    cs:__imp_WindowsGetStringRawBuffer
0x18003d307  xor     r9d, r9d; bool
0x18003d30a  mov     r8, rax; unsigned __int16 *
0x18003d30d  lea     rdx, [rbp+var_28]; struct _GUID *
0x18003d311  lea     rcx, [rdi+290h]; this
0x18003d318  call    ?SetProfileAutoConnect@ProfileManager@Internal@UX@Networking@Windows@@QEAAJPEBU_GUID@@PEBG_N@Z; Windows::Networking::UX::Internal::ProfileManager::SetProfileAutoConnect(_GUID const *,ushort const *,bool)
0x18003d31d  test    eax, eax
0x18003d31f  jns     short loc_18003D34D
0x18003d321  mov     rcx, cs:WPP_GLOBAL_Control
0x18003d328  cmp     rcx, r12
0x18003d32b  jz      short loc_18003D39E
0x18003d32d  test    byte ptr [rcx+1Ch], 2
0x18003d331  jz      short loc_18003D39E
0x18003d333  mov     edx, 4Bh ; 'K'
0x18003d338  mov     r9d, eax
0x18003d33b  lea     r8, WPP_1d38a1f9e6943a38c061f6c5b3807675_Traceguids
0x18003d342  mov     rcx, [rcx+10h]
0x18003d346  call    WPP_SF_d
0x18003d34b  jmp     short loc_18003D39E
0x18003d34d  mov     qword ptr [rbp+var_28], 0
0x18003d355  mov     rax, [rbx]
0x18003d358  mov     rdi, [rax]
0x18003d35b  lea     rcx, [rbp+var_28]
0x18003d35f  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18003d364  lea     r8, [rbp+var_28]
0x18003d368  lea     rdx, _GUID_ac2798f8_4bd2_4d64_be61_7002641cd494
0x18003d36f  mov     rcx, rbx
0x18003d372  mov     rax, rdi
0x18003d375  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d37a  test    eax, eax
0x18003d37c  js      short loc_18003D394
0x18003d37e  mov     rcx, qword ptr [rbp+var_28]
0x18003d382  mov     rax, [rcx]
0x18003d385  xor     edx, edx
0x18003d387  mov     rax, [rax+0C0h]
0x18003d38e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d393  nop
0x18003d394  lea     rcx, [rbp+var_28]
0x18003d398  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18003d39d  nop
0x18003d39e  mov     rcx, [rbp+string]; string
0x18003d3a2  call    cs:__imp_WindowsDeleteString
0x18003d3a8  mov     rax, [rsi]
0x18003d3ab  mov     rcx, rsi
0x18003d3ae  mov     rax, [rax+18h]
0x18003d3b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d3b7  mov     r14d, eax
0x18003d3ba  mov     [rbp+var_38], 0
0x18003d3c2  test    rbx, rbx
0x18003d3c5  jz      short loc_18003D426
0x18003d3c7  mov     rcx, [rbx]
0x18003d3ca  mov     rdi, [rcx+30h]
0x18003d3ce  xor     ecx, ecx; string
0x18003d3d0  call    cs:__imp_WindowsDeleteString
0x18003d3d6  mov     [rbp+var_38], 0
0x18003d3de  lea     rdx, [rbp+var_38]
0x18003d3e2  mov     rcx, rbx
0x18003d3e5  mov     rax, rdi
0x18003d3e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d3ed  test    eax, eax
0x18003d3ef  js      short loc_18003D426
0x18003d3f1  xor     edx, edx; length
0x18003d3f3  mov     rcx, [rbp+var_38]; string
0x18003d3f7  call    cs:__imp_WindowsGetStringRawBuffer
0x18003d3fd  mov     dword ptr [rbp+var_28], 0Dh
0x18003d404  movups  xmm0, xmmword ptr [rsi+4B4h]
0x18003d40b  movdqu  xmmword ptr [rbp+var_28+4], xmm0
0x18003d410  mov     [rbp+var_14], 47h ; 'G'
0x18003d417  mov     r8d, r14d; int
0x18003d41a  mov     rdx, rax; unsigned __int16 *
0x18003d41d  lea     rcx, [rbp+var_28]; struct NetworkingTriageScenario::GetConnected::RequiredFields *
0x18003d421  call    ?UXModelWiFiDisconnectAction@GetConnected@NetworkingTriageScenario@@SAXAEBURequiredFields@12@PEBGJ@Z; NetworkingTriageScenario::GetConnected::UXModelWiFiDisconnectAction(NetworkingTriageScenario::GetConnected::RequiredFields const &,ushort const *,long)
0x18003d426  mov     rcx, cs:WPP_GLOBAL_Control
0x18003d42d  cmp     rcx, r12
0x18003d430  jz      short loc_18003D451
0x18003d432  test    byte ptr [rcx+1Ch], 8
0x18003d436  jz      short loc_18003D451
0x18003d438  mov     edx, 4Ch ; 'L'
0x18003d43d  mov     r9d, r14d
0x18003d440  lea     r8, WPP_1d38a1f9e6943a38c061f6c5b3807675_Traceguids
0x18003d447  mov     rcx, [rcx+10h]
0x18003d44b  call    WPP_SF_d
0x18003d450  nop
0x18003d451  mov     rcx, [rbp+var_38]; string
0x18003d455  call    cs:__imp_WindowsDeleteString
0x18003d45b  mov     [rbp+var_38], 0
0x18003d463  lea     rcx, [rbp+var_30]
0x18003d467  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18003d46c  mov     eax, r14d
0x18003d46f  mov     rcx, [rbp+var_10]
0x18003d473  xor     rcx, rsp; StackCookie
0x18003d476  call    __security_check_cookie
0x18003d47b  add     rsp, 68h
0x18003d47f  pop     r14
0x18003d481  pop     r12
0x18003d483  pop     rdi
0x18003d484  pop     rsi
0x18003d485  pop     rbx
0x18003d486  pop     rbp
0x18003d487  retn
```
