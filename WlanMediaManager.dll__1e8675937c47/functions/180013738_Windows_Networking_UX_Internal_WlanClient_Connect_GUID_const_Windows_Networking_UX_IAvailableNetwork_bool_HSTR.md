# Windows::Networking::UX::Internal::WlanClient::Connect(_GUID const &,Windows::Networking::UX::IAvailableNetwork *,bool,HSTRING__ *,_WLAN_PRECONNECT_INPUT_RESPONSE const *)

- ea: `0x180013738`
- end: `0x1800139ea`
- name: `?Connect@WlanClient@Internal@UX@Networking@Windows@@QEAAJAEBU_GUID@@PEAUIAvailableNetwork@345@_NPEAUHSTRING__@@PEBU_WLAN_PRECONNECT_INPUT_RESPONSE@@@Z`
- size: `690`
- prototype: `__int64 __fastcall(Windows::Networking::UX::Internal::WlanClient *__hidden this, const struct _GUID *, struct Windows::Networking::UX::IAvailableNetwork *, bool, HSTRING, const struct _WLAN_PRECONNECT_INPUT_RESPONSE *)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18003cc80`

## callees

- `0x180003ed0`
- `0x180008e30`
- `0x18000de4c`
- `0x180013738`
- `0x180016c08`
- `0x18001a7d0`
- `0x18001c1f4`
- `0x18001d4d4`
- `0x18002feb0`
- `0x18008e010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180013915`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180013915`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800137c0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800138ee`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180013986`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800139c4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800137c0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800138ee`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180013986`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800139c4`
- `wlanapi!WlanConnectWithInput` at `0x1800138c8`
- `wlanapi!WlanConnectWithInput` at `0x1800138c8`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall Windows::Networking::UX::Internal::WlanClient::Connect(
        Windows::Networking::UX::Internal::WlanClient *this,
        const struct _GUID *a2,
        struct Windows::Networking::UX::IAvailableNetwork *a3,
        bool a4,
        HSTRING a5,
        const struct _WLAN_PRECONNECT_INPUT_RESPONSE *a6)
{
  Windows::Networking::UX::Internal::WlanClient *v10; // rcx
  __int64 v11; // rdx
  signed int inited; // edi
  __int64 v13; // r8
  struct Windows::Networking::UX::Internal::IAccessPointHelper **v14; // rdx
  int AccessPointHelper; // eax
  __int64 v16; // rdx
  __int64 v17; // r8
  _QWORD *v18; // rcx
  __int64 v19; // rdx
  int v20; // eax
  int (__fastcall *v21)(struct Windows::Networking::UX::IAvailableNetwork *, HSTRING *); // rbx
  const unsigned __int16 *StringRawBuffer; // rax
  HSTRING string; // [rsp+40h] [rbp-69h] BYREF
  HSTRING v25; // [rsp+48h] [rbp-61h] BYREF
  _WLAN_CONNECTION_PARAMETERS v26; // [rsp+50h] [rbp-59h] BYREF
  int v27; // [rsp+78h] [rbp-31h] BYREF
  struct _GUID v28; // [rsp+7Ch] [rbp-2Dh]
  int v29; // [rsp+8Ch] [rbp-1Dh]
  struct _DOT11_SSID v30; // [rsp+90h] [rbp-19h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, &WPP_21979ef79db039135e573b3136931b8d_Traceguids);
  memset(&v26, 0, sizeof(v26));
  memset(&v30, 0, sizeof(v30));
  WindowsDeleteString(0);
  v25 = 0;
  inited = Windows::Networking::UX::Internal::WlanClient::_InitConnectionParam(v10, a3, a4, a5, &v26, &v30, &v25);
  if ( inited >= 0 )
  {
    if ( !a6 )
    {
      string = 0;
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&string, v11, v13);
      AccessPointHelper = Windows::Networking::UX::Internal::AccessPointHelpers::GetAccessPointHelper(
                            (Windows::Networking::UX::Internal::AccessPointHelpers *)&string,
                            v14);
      inited = AccessPointHelper;
      if ( AccessPointHelper >= 0 )
      {
        AccessPointHelper = (*(__int64 (__fastcall **)(HSTRING, _QWORD, const struct _GUID *, _WLAN_CONNECTION_PARAMETERS *))(*(_QWORD *)string + 32LL))(
                              string,
                              *((_QWORD *)this + 2),
                              a2,
                              &v26);
        inited = AccessPointHelper;
        if ( AccessPointHelper >= 0 )
        {
          Windows::Networking::UX::Internal::WlanClient::_TrySetNewProfilePosition(this, a2, &v26);
          goto LABEL_16;
        }
        v18 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
          goto LABEL_16;
        v19 = 21;
      }
      else
      {
        v18 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
          goto LABEL_16;
        v19 = 20;
      }
      WPP_SF_d(v18[2], v19, &WPP_21979ef79db039135e573b3136931b8d_Traceguids, (unsigned int)AccessPointHelper);
LABEL_16:
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&string, v16, v17);
      goto LABEL_26;
    }
    v20 = WlanConnectWithInput(a2, &v26, a6);
    inited = v20;
    if ( v20 > 0 )
      inited = (unsigned __int16)v20 | 0x80070000;
    string = 0;
    v21 = *(int (__fastcall **)(struct Windows::Networking::UX::IAvailableNetwork *, HSTRING *))(*(_QWORD *)a3 + 48LL);
    WindowsDeleteString(0);
    string = 0;
    if ( v21(a3, &string) >= 0 )
    {
      StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
      v27 = 13;
      v28 = *a2;
      v29 = 71;
      NetworkingTriageScenario::GetConnected::UXModelWlanConnectAction(
        (const struct NetworkingTriageScenario::GetConnected::RequiredFields *)&v27,
        StringRawBuffer,
        v26.strProfile,
        inited);
    }
    if ( inited < 0 && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        22,
        &WPP_21979ef79db039135e573b3136931b8d_Traceguids,
        (unsigned int)inited);
    WindowsDeleteString(string);
  }
LABEL_26:
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      23,
      &WPP_21979ef79db039135e573b3136931b8d_Traceguids,
      (unsigned int)inited);
  WindowsDeleteString(v25);
  return (unsigned int)inited;
}

```

## disassembly

```asm
0x180013738  push    rbp
0x18001373a  push    rbx
0x18001373b  push    rsi
0x18001373c  push    rdi
0x18001373d  push    r12
0x18001373f  push    r14
0x180013741  push    r15
0x180013743  lea     rbp, [rsp-17h]
0x180013748  sub     rsp, 0C0h
0x18001374f  mov     rax, cs:__security_cookie
0x180013756  xor     rax, rsp
0x180013759  mov     [rbp+47h+var_38], rax
0x18001375d  mov     dil, r9b
0x180013760  mov     r15, r8
0x180013763  mov     rsi, rdx
0x180013766  mov     r14, rcx
0x180013769  mov     r12, [rbp+47h+arg_20]
0x18001376d  mov     rbx, [rbp+47h+arg_28]
0x180013771  lea     rax, WPP_GLOBAL_Control
0x180013778  mov     rcx, cs:WPP_GLOBAL_Control
0x18001377f  cmp     rcx, rax
0x180013782  jz      short loc_18001379F
0x180013784  test    byte ptr [rcx+1Ch], 40h
0x180013788  jz      short loc_18001379F
0x18001378a  mov     edx, 13h
0x18001378f  lea     r8, WPP_21979ef79db039135e573b3136931b8d_Traceguids
0x180013796  mov     rcx, [rcx+10h]
0x18001379a  call    WPP_SF_
0x18001379f  xorps   xmm0, xmm0
0x1800137a2  xor     eax, eax
0x1800137a4  movups  xmmword ptr [rbp+47h+var_A0.wlanConnectionMode], xmm0
0x1800137a8  movups  xmmword ptr [rbp+47h+var_A0.pDot11Ssid], xmm0
0x1800137ac  mov     qword ptr [rbp+47h+var_A0.dot11BssType], rax
0x1800137b0  xorps   xmm1, xmm1
0x1800137b3  movups  xmmword ptr [rbp+47h+var_60.uSSIDLength], xmm1
0x1800137b7  movups  xmmword ptr [rbp+47h+var_60.ucSSID+0Ch], xmm1
0x1800137bb  mov     dword ptr [rbp+47h+var_60.ucSSID+1Ch], eax
0x1800137be  xor     ecx, ecx; string
0x1800137c0  call    cs:__imp_WindowsDeleteString
0x1800137c6  mov     [rbp+47h+var_A8], 0
0x1800137ce  lea     rax, [rbp+47h+var_A8]
0x1800137d2  mov     [rsp+0F0h+var_C0], rax; HSTRING *
0x1800137d7  lea     rax, [rbp+47h+var_60]
0x1800137db  mov     [rsp+0F0h+var_C8], rax; struct _DOT11_SSID *
0x1800137e0  lea     rax, [rbp+47h+var_A0]
0x1800137e4  mov     [rsp+0F0h+var_D0], rax; struct _WLAN_CONNECTION_PARAMETERS *
0x1800137e9  mov     r9, r12; HSTRING
0x1800137ec  mov     r8b, dil; bool
0x1800137ef  mov     rdx, r15; struct Windows::Networking::UX::IAvailableNetwork *
0x1800137f2  call    ?_InitConnectionParam@WlanClient@Internal@UX@Networking@Windows@@IEAAJPEAUIAvailableNetwork@345@_NPEAUHSTRING__@@PEAU_WLAN_CONNECTION_PARAMETERS@@PEAU_DOT11_SSID@@PEAPEAU7@@Z; Windows::Networking::UX::Internal::WlanClient::_InitConnectionParam(Windows::Networking::UX::IAvailableNetwork *,bool,HSTRING__ *,_WLAN_CONNECTION_PARAMETERS *,_DOT11_SSID *,HSTRING__ * *)
0x1800137f7  mov     edi, eax
0x1800137f9  test    eax, eax
0x1800137fb  js      loc_18001398E
0x180013801  test    rbx, rbx
0x180013804  jnz     loc_1800138BE
0x18001380a  mov     [rbp+47h+string], rbx
0x18001380e  lea     rcx, [rbp+47h+string]
0x180013812  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180013817  lea     rcx, [rbp+47h+string]; this
0x18001381b  call    ?GetAccessPointHelper@AccessPointHelpers@Internal@UX@Networking@Windows@@YAJPEAPEAUIAccessPointHelper@2345@@Z; Windows::Networking::UX::Internal::AccessPointHelpers::GetAccessPointHelper(Windows::Networking::UX::Internal::IAccessPointHelper * *)
0x180013820  mov     edi, eax
0x180013822  test    eax, eax
0x180013824  jns     short loc_180013846
0x180013826  mov     rcx, cs:WPP_GLOBAL_Control
0x18001382d  lea     rbx, WPP_GLOBAL_Control
0x180013834  cmp     rcx, rbx
0x180013837  jz      short loc_1800138B0
0x180013839  test    byte ptr [rcx+1Ch], 2
0x18001383d  jz      short loc_1800138B0
0x18001383f  mov     edx, 14h
0x180013844  jmp     short loc_180013885
0x180013846  mov     rcx, [rbp+47h+string]
0x18001384a  mov     rax, [rcx]
0x18001384d  lea     r9, [rbp+47h+var_A0]
0x180013851  mov     r8, rsi
0x180013854  mov     rdx, [r14+10h]
0x180013858  mov     rax, [rax+20h]
0x18001385c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013861  mov     edi, eax
0x180013863  test    eax, eax
0x180013865  jns     short loc_18001389A
0x180013867  mov     rcx, cs:WPP_GLOBAL_Control
0x18001386e  lea     rbx, WPP_GLOBAL_Control
0x180013875  cmp     rcx, rbx
0x180013878  jz      short loc_1800138B0
0x18001387a  test    byte ptr [rcx+1Ch], 2
0x18001387e  jz      short loc_1800138B0
0x180013880  mov     edx, 15h
0x180013885  mov     r9d, eax
0x180013888  lea     r8, WPP_21979ef79db039135e573b3136931b8d_Traceguids
0x18001388f  mov     rcx, [rcx+10h]
0x180013893  call    WPP_SF_d
0x180013898  jmp     short loc_1800138B0
0x18001389a  lea     r8, [rbp+47h+var_A0]; struct _WLAN_CONNECTION_PARAMETERS *
0x18001389e  mov     rdx, rsi; struct _GUID *
0x1800138a1  mov     rcx, r14; this
0x1800138a4  call    ?_TrySetNewProfilePosition@WlanClient@Internal@UX@Networking@Windows@@IEAAXAEBU_GUID@@PEAU_WLAN_CONNECTION_PARAMETERS@@@Z; Windows::Networking::UX::Internal::WlanClient::_TrySetNewProfilePosition(_GUID const &,_WLAN_CONNECTION_PARAMETERS *)
0x1800138a9  lea     rbx, WPP_GLOBAL_Control
0x1800138b0  lea     rcx, [rbp+47h+string]
0x1800138b4  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800138b9  jmp     loc_180013995
0x1800138be  mov     r8, rbx
0x1800138c1  lea     rdx, [rbp+47h+var_A0]
0x1800138c5  mov     rcx, rsi
0x1800138c8  call    cs:__imp_WlanConnectWithInput
0x1800138ce  mov     edi, eax
0x1800138d0  test    eax, eax
0x1800138d2  jle     short loc_1800138DD
0x1800138d4  movzx   edi, ax
0x1800138d7  or      edi, 80070000h
0x1800138dd  mov     [rbp+47h+string], 0
0x1800138e5  mov     rax, [r15]
0x1800138e8  mov     rbx, [rax+30h]
0x1800138ec  xor     ecx, ecx; string
0x1800138ee  call    cs:__imp_WindowsDeleteString
0x1800138f4  mov     [rbp+47h+string], 0
0x1800138fc  lea     rdx, [rbp+47h+string]
0x180013900  mov     rcx, r15
0x180013903  mov     rax, rbx
0x180013906  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001390b  test    eax, eax
0x18001390d  js      short loc_180013944
0x18001390f  xor     edx, edx; length
0x180013911  mov     rcx, [rbp+47h+string]; string
0x180013915  call    cs:__imp_WindowsGetStringRawBuffer
0x18001391b  mov     [rbp+47h+var_78], 0Dh
0x180013922  movups  xmm0, xmmword ptr [rsi]
0x180013925  movdqu  [rbp+47h+var_74], xmm0
0x18001392a  mov     [rbp+47h+var_64], 47h ; 'G'
0x180013931  mov     r9d, edi; int
0x180013934  mov     r8, [rbp+47h+var_A0.strProfile]; unsigned __int16 *
0x180013938  mov     rdx, rax; unsigned __int16 *
0x18001393b  lea     rcx, [rbp+47h+var_78]; struct NetworkingTriageScenario::GetConnected::RequiredFields *
0x18001393f  call    ?UXModelWlanConnectAction@GetConnected@NetworkingTriageScenario@@SAXAEBURequiredFields@12@PEBG1J@Z; NetworkingTriageScenario::GetConnected::UXModelWlanConnectAction(NetworkingTriageScenario::GetConnected::RequiredFields const &,ushort const *,ushort const *,long)
0x180013944  test    edi, edi
0x180013946  jns     short loc_18001397B
0x180013948  mov     rcx, cs:WPP_GLOBAL_Control
0x18001394f  lea     rbx, WPP_GLOBAL_Control
0x180013956  cmp     rcx, rbx
0x180013959  jz      short loc_180013982
0x18001395b  test    byte ptr [rcx+1Ch], 2
0x18001395f  jz      short loc_180013982
0x180013961  mov     edx, 16h
0x180013966  mov     r9d, edi
0x180013969  lea     r8, WPP_21979ef79db039135e573b3136931b8d_Traceguids
0x180013970  mov     rcx, [rcx+10h]
0x180013974  call    WPP_SF_d
0x180013979  jmp     short loc_180013982
0x18001397b  lea     rbx, WPP_GLOBAL_Control
0x180013982  mov     rcx, [rbp+47h+string]; string
0x180013986  call    cs:__imp_WindowsDeleteString
0x18001398c  jmp     short loc_180013995
0x18001398e  lea     rbx, WPP_GLOBAL_Control
0x180013995  mov     rcx, cs:WPP_GLOBAL_Control
0x18001399c  cmp     rcx, rbx
0x18001399f  jz      short loc_1800139C0
0x1800139a1  test    byte ptr [rcx+1Ch], 40h
0x1800139a5  jz      short loc_1800139C0
0x1800139a7  mov     edx, 17h
0x1800139ac  mov     r9d, edi
0x1800139af  lea     r8, WPP_21979ef79db039135e573b3136931b8d_Traceguids
0x1800139b6  mov     rcx, [rcx+10h]
0x1800139ba  call    WPP_SF_d
0x1800139bf  nop
0x1800139c0  mov     rcx, [rbp+47h+var_A8]; string
0x1800139c4  call    cs:__imp_WindowsDeleteString
0x1800139ca  mov     eax, edi
0x1800139cc  mov     rcx, [rbp+47h+var_38]
0x1800139d0  xor     rcx, rsp; StackCookie
0x1800139d3  call    __security_check_cookie
0x1800139d8  add     rsp, 0C0h
0x1800139df  pop     r15
0x1800139e1  pop     r14
0x1800139e3  pop     r12
0x1800139e5  pop     rdi
0x1800139e6  pop     rsi
0x1800139e7  pop     rbx
0x1800139e8  pop     rbp
0x1800139e9  retn
```
