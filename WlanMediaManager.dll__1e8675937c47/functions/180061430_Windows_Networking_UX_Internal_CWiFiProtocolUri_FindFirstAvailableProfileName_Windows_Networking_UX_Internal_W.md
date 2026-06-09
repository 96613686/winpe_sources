# Windows::Networking::UX::Internal::CWiFiProtocolUri::_FindFirstAvailableProfileName(Windows::Networking::UX::Internal::WlanMediaManager *,HSTRING__ * *,Windows::Networking::UX::IWiFiProfile * *)

- ea: `0x180061430`
- end: `0x180061705`
- name: `?_FindFirstAvailableProfileName@CWiFiProtocolUri@Internal@UX@Networking@Windows@@AEAAJPEAVWlanMediaManager@2345@PEAPEAUHSTRING__@@PEAPEAUIWiFiProfile@345@@Z`
- size: `725`
- prototype: `int(Windows::Networking::UX::Internal::CWiFiProtocolUri *__hidden this, struct Windows::Networking::UX::Internal::WlanMediaManager *, HSTRING *, struct Windows::Networking::UX::IWiFiProfile **)`
- caller_count: `1`
- callee_count: `14`
- tags: `broker_com_uri`

## callers

- `0x180060cf0`

## callees

- `0x180003ed0`
- `0x180008e30`
- `0x1800097b4`
- `0x18000e094`
- `0x180011a20`
- `0x18001b838`
- `0x18001c044`
- `0x1800218a4`
- `0x1800373ec`
- `0x18005f690`
- `0x180060148`
- `0x180060660`
- `0x180061430`
- `0x18008e010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18006160c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18006168c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18006160c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18006168c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180061482`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180061482`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800615ea`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006164d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180061675`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800616ae`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800615ea`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006164d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180061675`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800616ae`

## string_xrefs

- `0x1800615bd`: `onecoreuap\net\ux\wlanmediamanager\lib\cwifiprotocoluri.cpp`
- `0x1800616c8`: `onecoreuap\net\ux\wlanmediamanager\lib\cwifiprotocoluri.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=6 #try_helpers=1
__int64 __fastcall Windows::Networking::UX::Internal::CWiFiProtocolUri::_FindFirstAvailableProfileName(
        Windows::Networking::UX::Internal::CWiFiProtocolUri *this,
        struct Windows::Networking::UX::Internal::WlanMediaManager *a2,
        HSTRING *a3,
        struct Windows::Networking::UX::IWiFiProfile **a4)
{
  int v8; // edi
  int i; // ebx
  __int64 v10; // rdx
  __int64 v11; // r8
  __int64 v12; // rax
  __int64 v13; // rdx
  __int64 v14; // r8
  __int64 v15; // rax
  __int64 v16; // rdx
  __int64 v17; // r8
  __int64 v18; // rdx
  __int64 v19; // rdx
  __int64 v20; // r8
  int v21; // eax
  __int64 v22; // rdx
  __int64 v23; // r8
  unsigned int v24; // esi
  __int64 v25; // rdx
  __int64 v26; // r8
  __int64 v28; // rdx
  __int64 v29; // r8
  struct Windows::Networking::UX::IWiFiProfile *v30; // rcx
  __int64 v31; // rdx
  __int64 v32; // r8
  struct Windows::Networking::UX::IWiFiProfile *v33; // [rsp+20h] [rbp-E8h] BYREF
  HSTRING string; // [rsp+28h] [rbp-E0h] BYREF
  struct _GUID v35; // [rsp+30h] [rbp-D8h] BYREF
  __int128 v36; // [rsp+40h] [rbp-C8h]
  _BYTE v37[32]; // [rsp+50h] [rbp-B8h] BYREF
  _BYTE v38[74]; // [rsp+70h] [rbp-98h] BYREF
  _BYTE v39[6]; // [rsp+BAh] [rbp-4Eh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+108h] [rbp+0h]

  v8 = 0;
  v35.Data1 = 0;
  *a4 = 0;
  for ( i = 0; ; ++i )
  {
    if ( i >= 10 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1B8,
        (unsigned int)"onecoreuap\\net\\ux\\wlanmediamanager\\lib\\cwifiprotocoluri.cpp",
        (const char *)0x80070490LL,
        (int)v33);
      return 2147943568LL;
    }
    string = 0;
    WindowsGetStringRawBuffer(*((HSTRING *)this + 15), 0);
    std::wstring::wstring(v37);
    if ( i > 0 )
    {
      v12 = std::_UIntegral_to_buff<unsigned short,unsigned int>(v39, (unsigned int)i);
      std::wstring::wstring(v38, v12, v39);
      v15 = std::wstring::_Insert<unsigned short>(v38, v13, v14, 1);
      v35 = 0;
      v36 = 0;
      v35 = *(struct _GUID *)v15;
      v36 = *(_OWORD *)(v15 + 16);
      *(_QWORD *)(v15 + 16) = 0;
      *(_QWORD *)(v15 + 24) = 7;
      *(_WORD *)v15 = 0;
      v8 |= 7u;
      v18 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&v35, v16, v17);
      std::wstring::_Append<unsigned short>(v37, v18, v36);
      std::wstring::_Tidy_deallocate(&v35);
      std::wstring::_Tidy_deallocate(v38);
    }
    *(_QWORD *)&v35.Data1 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v37, v10, v11);
    Microsoft::WRL::Wrappers::HString::Set<unsigned short *>(&string, &v35);
    v33 = 0;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v33, v19, v20);
    v35 = *(struct _GUID *)((char *)this + 72);
    if ( (int)Windows::Networking::UX::Internal::WlanMediaManager::Category_GetProfile(a2, &v35, string, &v33) < 0 )
    {
      WindowsDuplicateString(string, a3);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v33, v31, v32);
      std::wstring::_Tidy_deallocate(v37);
      WindowsDeleteString(string);
      return 0;
    }
    v35.Data1 = 0;
    v21 = (*(__int64 (__fastcall **)(struct Windows::Networking::UX::IWiFiProfile *, struct _GUID *))(*(_QWORD *)v33 + 64LL))(
            v33,
            &v35);
    v24 = v21;
    if ( v21 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1A6,
        (unsigned int)"onecoreuap\\net\\ux\\wlanmediamanager\\lib\\cwifiprotocoluri.cpp",
        (const char *)(unsigned int)v21,
        (int)v33);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v33, v25, v26);
      std::wstring::_Tidy_deallocate(v37);
      WindowsDeleteString(string);
      return v24;
    }
    if ( v35.Data1 == *((_DWORD *)this + 35) )
      break;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v33, v22, v23);
    std::wstring::_Tidy_deallocate(v37);
    WindowsDeleteString(string);
  }
  WindowsDuplicateString(string, a3);
  v30 = v33;
  if ( v33 )
  {
    (*(void (__fastcall **)(struct Windows::Networking::UX::IWiFiProfile *))(*(_QWORD *)v33 + 8LL))(v33);
    v30 = v33;
  }
  *a4 = v30;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v33, v28, v29);
  std::wstring::_Tidy_deallocate(v37);
  WindowsDeleteString(string);
  return 0;
}

```

## disassembly

```asm
0x180061430  push    rbx
0x180061432  push    rsi
0x180061433  push    rdi
0x180061434  push    r12
0x180061436  push    r13
0x180061438  push    r14
0x18006143a  push    r15
0x18006143c  sub     rsp, 0D0h
0x180061443  mov     rax, cs:__security_cookie
0x18006144a  xor     rax, rsp
0x18006144d  mov     [rsp+108h+var_48], rax
0x180061455  mov     r12, r9
0x180061458  mov     r15, r8
0x18006145b  mov     r13, rdx
0x18006145e  mov     r14, rcx
0x180061461  xor     esi, esi
0x180061463  mov     edi, esi
0x180061465  mov     [rsp+108h+var_D8.Data1], esi
0x180061469  mov     [r9], rsi
0x18006146c  mov     ebx, esi
0x18006146e  cmp     ebx, 0Ah
0x180061471  jge     loc_1800616B8
0x180061477  mov     [rsp+108h+string], rsi
0x18006147c  xor     edx, edx; length
0x18006147e  mov     rcx, [r14+78h]; string
0x180061482  call    cs:__imp_WindowsGetStringRawBuffer
0x180061488  mov     rdx, rax
0x18006148b  lea     rcx, [rsp+108h+var_B8]
0x180061490  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180061495  nop
0x180061496  test    ebx, ebx
0x180061498  jle     loc_18006153B
0x18006149e  mov     edx, ebx
0x1800614a0  lea     rcx, [rsp+108h+var_4E]
0x1800614a8  call    ??$_UIntegral_to_buff@GI@std@@YAPEAGPEAGI@Z; std::_UIntegral_to_buff<ushort,uint>(ushort *,uint)
0x1800614ad  lea     r8, [rsp+108h+var_4E]
0x1800614b5  mov     rdx, rax
0x1800614b8  lea     rcx, [rsp+108h+var_98]
0x1800614bd  call    ??$?0PEAG$0A@@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEAG0AEBV?$allocator@G@1@@Z; std::wstring::wstring(ushort *,ushort *,std::allocator<ushort> const &)
0x1800614c2  or      edi, 3
0x1800614c5  mov     r9d, 1
0x1800614cb  lea     rcx, [rsp+108h+var_98]
0x1800614d0  call    ??$_Insert@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KQEBG0@Z; std::wstring::_Insert<ushort>(unsigned __int64,ushort const * const,unsigned __int64)
0x1800614d5  xorps   xmm0, xmm0
0x1800614d8  movups  xmmword ptr [rsp+108h+var_D8.Data1], xmm0
0x1800614dd  xorps   xmm1, xmm1
0x1800614e0  movdqu  [rsp+108h+var_C8], xmm1
0x1800614e6  movups  xmm0, xmmword ptr [rax]
0x1800614e9  movups  xmmword ptr [rsp+108h+var_D8.Data1], xmm0
0x1800614ee  movups  xmm1, xmmword ptr [rax+10h]
0x1800614f2  movups  [rsp+108h+var_C8], xmm1
0x1800614f7  mov     [rax+10h], rsi
0x1800614fb  mov     qword ptr [rax+18h], 7
0x180061503  mov     [rax], si
0x180061506  or      edi, 4
0x180061509  lea     rcx, [rsp+108h+var_D8]
0x18006150e  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180061513  mov     rdx, rax
0x180061516  mov     r8, qword ptr [rsp+108h+var_C8]
0x18006151b  lea     rcx, [rsp+108h+var_B8]
0x180061520  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x180061525  nop
0x180061526  lea     rcx, [rsp+108h+var_D8]
0x18006152b  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180061530  nop
0x180061531  lea     rcx, [rsp+108h+var_98]
0x180061536  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18006153b  lea     rcx, [rsp+108h+var_B8]
0x180061540  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180061545  mov     qword ptr [rsp+108h+var_D8.Data1], rax
0x18006154a  lea     rdx, [rsp+108h+var_D8]
0x18006154f  lea     rcx, [rsp+108h+string]
0x180061554  call    ??$Set@PEAG@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEAGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HString::Set<ushort *>(ushort * const &,Microsoft::WRL::Details::Dummy)
0x180061559  mov     [rsp+108h+var_E8], rsi; int
0x18006155e  lea     rcx, [rsp+108h+var_E8]
0x180061563  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180061568  movups  xmm0, xmmword ptr [r14+48h]
0x18006156d  movdqu  xmmword ptr [rsp+108h+var_D8.Data1], xmm0
0x180061573  lea     r9, [rsp+108h+var_E8]; struct Windows::Networking::UX::IWiFiProfile **
0x180061578  mov     r8, [rsp+108h+string]; HSTRING
0x18006157d  lea     rdx, [rsp+108h+var_D8]; struct _GUID
0x180061582  mov     rcx, r13; this
0x180061585  call    ?Category_GetProfile@WlanMediaManager@Internal@UX@Networking@Windows@@QEAAJU_GUID@@PEAUHSTRING__@@PEAPEAUIWiFiProfile@345@@Z; Windows::Networking::UX::Internal::WlanMediaManager::Category_GetProfile(_GUID,HSTRING__ *,Windows::Networking::UX::IWiFiProfile * *)
0x18006158a  test    eax, eax
0x18006158c  js      loc_180061684
0x180061592  mov     [rsp+108h+var_D8.Data1], esi
0x180061596  mov     rcx, [rsp+108h+var_E8]
0x18006159b  mov     rax, [rcx]
0x18006159e  lea     rdx, [rsp+108h+var_D8]
0x1800615a3  mov     rax, [rax+40h]
0x1800615a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800615ac  mov     esi, eax
0x1800615ae  test    eax, eax
0x1800615b0  jns     short loc_1800615F7
0x1800615b2  mov     rcx, [rsp+108h]; this
0x1800615ba  mov     r9d, eax; char *
0x1800615bd  lea     r8, aOnecoreuapNetU_5; "onecoreuap\\net\\ux\\wlanmediamanager\\"...
0x1800615c4  mov     edx, 1A6h; void *
0x1800615c9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800615ce  nop
0x1800615cf  lea     rcx, [rsp+108h+var_E8]
0x1800615d4  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800615d9  nop
0x1800615da  lea     rcx, [rsp+108h+var_B8]
0x1800615df  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800615e4  nop
0x1800615e5  mov     rcx, [rsp+108h+string]; string
0x1800615ea  call    cs:__imp_WindowsDeleteString
0x1800615f0  mov     eax, esi
0x1800615f2  jmp     loc_1800616E1
0x1800615f7  mov     eax, [r14+8Ch]
0x1800615fe  cmp     [rsp+108h+var_D8.Data1], eax
0x180061602  jnz     short loc_18006165A
0x180061604  mov     rdx, r15; newString
0x180061607  mov     rcx, [rsp+108h+string]; string
0x18006160c  call    cs:__imp_WindowsDuplicateString
0x180061612  nop
0x180061613  mov     rcx, [rsp+108h+var_E8]
0x180061618  test    rcx, rcx
0x18006161b  jz      short loc_18006162E
0x18006161d  mov     rax, [rcx]
0x180061620  mov     rax, [rax+8]
0x180061624  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180061629  mov     rcx, [rsp+108h+var_E8]
0x18006162e  mov     [r12], rcx
0x180061632  lea     rcx, [rsp+108h+var_E8]
0x180061637  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18006163c  nop
0x18006163d  lea     rcx, [rsp+108h+var_B8]
0x180061642  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180061647  nop
0x180061648  mov     rcx, [rsp+108h+string]; string
0x18006164d  call    cs:__imp_WindowsDeleteString
0x180061653  xor     eax, eax
0x180061655  jmp     loc_1800616E1
0x18006165a  lea     rcx, [rsp+108h+var_E8]
0x18006165f  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180061664  nop
0x180061665  lea     rcx, [rsp+108h+var_B8]
0x18006166a  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18006166f  nop
0x180061670  mov     rcx, [rsp+108h+string]; string
0x180061675  call    cs:__imp_WindowsDeleteString
0x18006167b  inc     ebx
0x18006167d  xor     esi, esi
0x18006167f  jmp     loc_18006146E
0x180061684  mov     rdx, r15; newString
0x180061687  mov     rcx, [rsp+108h+string]; string
0x18006168c  call    cs:__imp_WindowsDuplicateString
0x180061692  nop
0x180061693  lea     rcx, [rsp+108h+var_E8]
0x180061698  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18006169d  nop
0x18006169e  lea     rcx, [rsp+108h+var_B8]
0x1800616a3  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800616a8  nop
0x1800616a9  mov     rcx, [rsp+108h+string]; string
0x1800616ae  call    cs:__imp_WindowsDeleteString
0x1800616b4  xor     eax, eax
0x1800616b6  jmp     short loc_1800616E1
0x1800616b8  mov     rcx, [rsp+108h]; this
0x1800616c0  mov     ebx, 80070490h
0x1800616c5  mov     r9d, ebx; char *
0x1800616c8  lea     r8, aOnecoreuapNetU_5; "onecoreuap\\net\\ux\\wlanmediamanager\\"...
0x1800616cf  mov     edx, 1B8h; void *
0x1800616d4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800616d9  mov     eax, ebx
0x1800616db  jmp     short loc_1800616E1
0x1800616dd  mov     eax, [rsp+108h+var_D8.Data1]
0x1800616e1  mov     rcx, [rsp+108h+var_48]
0x1800616e9  xor     rcx, rsp; StackCookie
0x1800616ec  call    __security_check_cookie
0x1800616f1  add     rsp, 0D0h
0x1800616f8  pop     r15
0x1800616fa  pop     r14
0x1800616fc  pop     r13
0x1800616fe  pop     r12
0x180061700  pop     rdi
0x180061701  pop     rsi
0x180061702  pop     rbx
0x180061703  retn
```
