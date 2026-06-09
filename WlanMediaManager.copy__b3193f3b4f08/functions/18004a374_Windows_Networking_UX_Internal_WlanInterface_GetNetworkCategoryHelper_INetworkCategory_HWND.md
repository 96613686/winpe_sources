# Windows::Networking::UX::Internal::WlanInterface::_GetNetworkCategoryHelper(INetworkCategory * *,HWND__ *)

- ea: `0x18004a374`
- end: `0x18004a552`
- name: `?_GetNetworkCategoryHelper@WlanInterface@Internal@UX@Networking@Windows@@IEAAJPEAPEAUINetworkCategory@@PEAUHWND__@@@Z`
- size: `478`
- prototype: `__int64 __fastcall(Windows::Networking::UX::Internal::WlanInterface *__hidden this, struct INetworkCategory **, HWND)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18004c24c`

## callees

- `0x180003ed0`
- `0x180008e30`
- `0x18000de4c`
- `0x18001d4d4`
- `0x18004a374`
- `0x1800693b8`
- `0x18008e010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18004a428`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18004a4d1`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18004a428`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18004a4d1`
- `api-ms-win-shcore-sysinfo-l1-1-0!IsOS` at `0x18004a3df`
- `api-ms-win-shcore-sysinfo-l1-1-0!IsOS` at `0x18004a3df`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall Windows::Networking::UX::Internal::WlanInterface::_GetNetworkCategoryHelper(
        Windows::Networking::UX::Internal::WlanInterface *this,
        struct INetworkCategory **a2,
        HWND a3)
{
  __int64 v5; // rdx
  Windows::Networking::UX::Internal *v6; // rcx
  __int64 v7; // r8
  __int64 v8; // rdx
  HRESULT v9; // ebx
  __int64 v10; // r8
  LPVOID v11; // rdi
  __int64 (__fastcall *v12)(LPVOID, GUID *, GUID *, LPVOID *); // rbx
  __int64 v13; // rdx
  __int64 v14; // r8
  struct INetworkCategory *v15; // rcx
  LPVOID v17; // [rsp+30h] [rbp-30h] BYREF
  LPVOID ppv; // [rsp+38h] [rbp-28h] BYREF
  _DWORD v19[4]; // [rsp+40h] [rbp-20h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 183, &WPP_1d38a1f9e6943a38c061f6c5b3807675_Traceguids);
  *a2 = 0;
  v17 = 0;
  if ( IsOS(0x1Cu) || !Windows::Networking::UX::Internal::IsDesktop(v6) )
  {
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v17, v5, v7);
    v9 = CoCreateInstance(&CLSID_NetworkCategory, 0, 0x17u, &GUID_de5c5263_a528_4a77_a112_38d26a559ff8, &v17);
  }
  else
  {
    ppv = 0;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppv, v5, v7);
    v9 = CoCreateInstance(
           &CLSID_MultiObjectElevationFactory,
           0,
           0x17u,
           &GUID_6fabda16_031e_47e3_b2a2_2339c05ccb9e,
           &ppv);
    if ( v9 >= 0 )
    {
      v19[0] = -442482455;
      v19[1] = 1294209175;
      v19[2] = 1933352632;
      v19[3] = 366360064;
      v9 = (*(__int64 (__fastcall **)(LPVOID, HWND, _DWORD *))(*(_QWORD *)ppv + 24LL))(ppv, a3, v19);
      if ( v9 >= 0 )
      {
        v11 = ppv;
        v12 = *(__int64 (__fastcall **)(LPVOID, GUID *, GUID *, LPVOID *))(*(_QWORD *)ppv + 40LL);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v17, v8, v10);
        v9 = v12(v11, &CLSID_NetworkCategory, &GUID_de5c5263_a528_4a77_a112_38d26a559ff8, &v17);
      }
    }
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppv, v8, v10);
  }
  if ( v9 >= 0 )
  {
    v15 = (struct INetworkCategory *)v17;
    if ( v17 )
    {
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v17 + 8LL))(v17);
      v15 = (struct INetworkCategory *)v17;
    }
    *a2 = v15;
    v9 = 0;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      184,
      &WPP_1d38a1f9e6943a38c061f6c5b3807675_Traceguids,
      (unsigned int)v9);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v17, v13, v14);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18004a374  mov     [rsp-18h+arg_0], rbx
0x18004a379  mov     [rsp-18h+arg_18], rsi
0x18004a37e  push    rbp
0x18004a37f  push    rdi
0x18004a380  push    r15
0x18004a382  mov     rbp, rsp
0x18004a385  sub     rsp, 60h
0x18004a389  mov     rax, cs:__security_cookie
0x18004a390  xor     rax, rsp
0x18004a393  mov     [rbp+var_10], rax
0x18004a397  mov     rdi, r8
0x18004a39a  mov     rsi, rdx
0x18004a39d  lea     r15, WPP_GLOBAL_Control
0x18004a3a4  mov     rcx, cs:WPP_GLOBAL_Control
0x18004a3ab  cmp     rcx, r15
0x18004a3ae  jz      short loc_18004A3CB
0x18004a3b0  test    byte ptr [rcx+1Ch], 40h
0x18004a3b4  jz      short loc_18004A3CB
0x18004a3b6  mov     edx, 0B7h
0x18004a3bb  lea     r8, WPP_1d38a1f9e6943a38c061f6c5b3807675_Traceguids
0x18004a3c2  mov     rcx, [rcx+10h]
0x18004a3c6  call    WPP_SF_
0x18004a3cb  mov     qword ptr [rsi], 0
0x18004a3d2  mov     [rbp+var_30], 0
0x18004a3da  mov     ecx, 1Ch; dwOS
0x18004a3df  call    cs:__imp_IsOS
0x18004a3e5  test    eax, eax
0x18004a3e7  jnz     loc_18004A4AB
0x18004a3ed  call    ?IsDesktop@Internal@UX@Networking@Windows@@YA_NXZ; Windows::Networking::UX::Internal::IsDesktop(void)
0x18004a3f2  test    al, al
0x18004a3f4  jz      loc_18004A4AB
0x18004a3fa  mov     [rbp+var_28], 0
0x18004a402  lea     rcx, [rbp+var_28]
0x18004a406  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18004a40b  lea     rax, [rbp+var_28]
0x18004a40f  mov     [rsp+60h+ppv], rax; ppv
0x18004a414  lea     r9, _GUID_6fabda16_031e_47e3_b2a2_2339c05ccb9e; riid
0x18004a41b  xor     edx, edx; pUnkOuter
0x18004a41d  lea     r8d, [rdx+17h]; dwClsContext
0x18004a421  lea     rcx, CLSID_MultiObjectElevationFactory; rclsid
0x18004a428  call    cs:__imp_CoCreateInstance
0x18004a42e  mov     ebx, eax
0x18004a430  test    eax, eax
0x18004a432  js      short loc_18004A4A0
0x18004a434  mov     [rbp+var_20], 0E5A040E9h
0x18004a43b  mov     [rbp+var_1C], 4D241097h
0x18004a442  mov     [rbp+var_18], 733C9EB8h
0x18004a449  mov     [rbp+var_14], 15D63600h
0x18004a450  mov     rcx, [rbp+var_28]
0x18004a454  mov     rax, [rcx]
0x18004a457  lea     r8, [rbp+var_20]
0x18004a45b  mov     rdx, rdi
0x18004a45e  mov     rax, [rax+18h]
0x18004a462  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a467  mov     ebx, eax
0x18004a469  test    eax, eax
0x18004a46b  js      short loc_18004A4A0
0x18004a46d  mov     rdi, [rbp+var_28]
0x18004a471  mov     rax, [rdi]
0x18004a474  mov     rbx, [rax+28h]
0x18004a478  lea     rcx, [rbp+var_30]
0x18004a47c  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18004a481  lea     r9, [rbp+var_30]
0x18004a485  lea     r8, _GUID_de5c5263_a528_4a77_a112_38d26a559ff8
0x18004a48c  lea     rdx, CLSID_NetworkCategory
0x18004a493  mov     rcx, rdi
0x18004a496  mov     rax, rbx
0x18004a499  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a49e  mov     ebx, eax
0x18004a4a0  lea     rcx, [rbp+var_28]
0x18004a4a4  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18004a4a9  jmp     short loc_18004A4D9
0x18004a4ab  lea     rcx, [rbp+var_30]
0x18004a4af  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18004a4b4  lea     rax, [rbp+var_30]
0x18004a4b8  mov     [rsp+60h+ppv], rax; ppv
0x18004a4bd  lea     r9, _GUID_de5c5263_a528_4a77_a112_38d26a559ff8; riid
0x18004a4c4  xor     edx, edx; pUnkOuter
0x18004a4c6  lea     r8d, [rdx+17h]; dwClsContext
0x18004a4ca  lea     rcx, CLSID_NetworkCategory; rclsid
0x18004a4d1  call    cs:__imp_CoCreateInstance
0x18004a4d7  mov     ebx, eax
0x18004a4d9  test    ebx, ebx
0x18004a4db  js      short loc_18004A4FB
0x18004a4dd  mov     rcx, [rbp+var_30]
0x18004a4e1  test    rcx, rcx
0x18004a4e4  jz      short loc_18004A4F6
0x18004a4e6  mov     rax, [rcx]
0x18004a4e9  mov     rax, [rax+8]
0x18004a4ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a4f2  mov     rcx, [rbp+var_30]
0x18004a4f6  mov     [rsi], rcx
0x18004a4f9  xor     ebx, ebx
0x18004a4fb  mov     rcx, cs:WPP_GLOBAL_Control
0x18004a502  cmp     rcx, r15
0x18004a505  jz      short loc_18004A526
0x18004a507  test    byte ptr [rcx+1Ch], 40h
0x18004a50b  jz      short loc_18004A526
0x18004a50d  mov     edx, 0B8h
0x18004a512  mov     r9d, ebx
0x18004a515  lea     r8, WPP_1d38a1f9e6943a38c061f6c5b3807675_Traceguids
0x18004a51c  mov     rcx, [rcx+10h]
0x18004a520  call    WPP_SF_d
0x18004a525  nop
0x18004a526  lea     rcx, [rbp+var_30]
0x18004a52a  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18004a52f  mov     eax, ebx
0x18004a531  mov     rcx, [rbp+var_10]
0x18004a535  xor     rcx, rsp; StackCookie
0x18004a538  call    __security_check_cookie
0x18004a53d  lea     r11, [rsp+60h+var_s0]
0x18004a542  mov     rbx, [r11+20h]
0x18004a546  mov     rsi, [r11+38h]
0x18004a54a  mov     rsp, r11
0x18004a54d  pop     r15
0x18004a54f  pop     rdi
0x18004a550  pop     rbp
0x18004a551  retn
```
