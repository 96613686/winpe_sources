# Windows::Networking::UX::Internal::WlanClient::_InitConnectionParam(Windows::Networking::UX::IAvailableNetwork *,bool,HSTRING__ *,_WLAN_CONNECTION_PARAMETERS *,_DOT11_SSID *,HSTRING__ * *)

- ea: `0x18001a7d0`
- end: `0x18001ab29`
- name: `?_InitConnectionParam@WlanClient@Internal@UX@Networking@Windows@@IEAAJPEAUIAvailableNetwork@345@_NPEAUHSTRING__@@PEAU_WLAN_CONNECTION_PARAMETERS@@PEAU_DOT11_SSID@@PEAPEAU7@@Z`
- size: `857`
- prototype: `int(Windows::Networking::UX::Internal::WlanClient *__hidden this, struct Windows::Networking::UX::IAvailableNetwork *, bool, HSTRING, struct _WLAN_CONNECTION_PARAMETERS *, struct _DOT11_SSID *, HSTRING *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180013738`

## callees

- `0x180008e30`
- `0x18000de4c`
- `0x18001a7d0`
- `0x18001d4d4`
- `0x18008e010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001a9c8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001aa5f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001a9c8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001aa5f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001a96a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001a9ec`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001a96a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001a9ec`
- `wlanapi!WlanStringToUtf8Ssid` at `0x18001aa6b`
- `wlanapi!WlanStringToUtf8Ssid` at `0x18001aa6b`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Windows::Networking::UX::Internal::WlanClient::_InitConnectionParam(
        Windows::Networking::UX::Internal::WlanClient *this,
        struct Windows::Networking::UX::IAvailableNetwork *a2,
        char a3,
        HSTRING a4,
        struct _WLAN_CONNECTION_PARAMETERS *a5,
        struct _DOT11_SSID *length,
        HSTRING *a7)
{
  int v10; // r15d
  struct _DOT11_SSID *v11; // rdi
  struct _WLAN_CONNECTION_PARAMETERS *v12; // rsi
  int v13; // eax
  __int64 v14; // rdx
  __int64 v15; // r8
  unsigned int v16; // ebx
  PVOID *v17; // rcx
  __int64 (__fastcall *v18)(struct Windows::Networking::UX::IAvailableNetwork *, GUID *, struct _WLAN_CONNECTION_PARAMETERS **); // rbx
  int v19; // eax
  __int64 v20; // rdx
  __int64 v21; // r8
  __int64 (__fastcall *v22)(struct Windows::Networking::UX::IAvailableNetwork *, HSTRING *); // rbx
  int v23; // eax
  HSTRING v24; // rax
  PCWSTR StringRawBuffer; // rax
  int v26; // eax
  Windows::Networking::UX::Internal::WlanClient *v28; // [rsp+60h] [rbp+40h] BYREF
  HSTRING string; // [rsp+68h] [rbp+48h] BYREF

  v28 = this;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 111, &WPP_21979ef79db039135e573b3136931b8d_Traceguids);
  v10 = 0;
  *a7 = 0;
  v11 = length;
  length->uSSIDLength = 0;
  v12 = a5;
  *(_OWORD *)&a5->wlanConnectionMode = 0;
  *(_OWORD *)&v12->pDot11Ssid = 0;
  *(_QWORD *)&v12->dot11BssType = 0;
  LOBYTE(v28) = 0;
  v13 = (*(__int64 (__fastcall **)(struct Windows::Networking::UX::IAvailableNetwork *, Windows::Networking::UX::Internal::WlanClient **))(*(_QWORD *)a2 + 136LL))(
          a2,
          &v28);
  v16 = v13;
  if ( v13 >= 0 )
  {
    a5 = 0;
    v18 = **(__int64 (__fastcall ***)(struct Windows::Networking::UX::IAvailableNetwork *, GUID *, struct _WLAN_CONNECTION_PARAMETERS **))a2;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&a5, v14, v15);
    v19 = v18(a2, &GUID_ac2798f8_4bd2_4d64_be61_7002641cd494, &a5);
    v16 = v19;
    if ( v19 >= 0 )
    {
      if ( (_BYTE)v28 )
      {
        if ( (*(unsigned __int8 (__fastcall **)(struct _WLAN_CONNECTION_PARAMETERS *))(*(_QWORD *)&a5->wlanConnectionMode
                                                                                     + 128LL))(a5) )
        {
          v11 = 0;
        }
        else
        {
          *(_OWORD *)&v11->uSSIDLength = 0;
          *(_OWORD *)&v11->ucSSID[12] = 0;
          *(_DWORD *)&v11->ucSSID[28] = 0;
          (*(void (__fastcall **)(struct _WLAN_CONNECTION_PARAMETERS *, struct _DOT11_SSID *))(*(_QWORD *)&a5->wlanConnectionMode
                                                                                             + 80LL))(
            a5,
            v11);
        }
        string = 0;
        v22 = *(__int64 (__fastcall **)(struct Windows::Networking::UX::IAvailableNetwork *, HSTRING *))(*(_QWORD *)a2 + 56LL);
        WindowsDeleteString(0);
        string = 0;
        v23 = v22(a2, &string);
        v16 = v23;
        if ( v23 >= 0 )
        {
          LODWORD(length) = 0;
          v12->strProfile = WindowsGetStringRawBuffer(string, (UINT32 *)&length);
          v24 = string;
          string = 0;
          *a7 = v24;
        }
        else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            114,
            &WPP_21979ef79db039135e573b3136931b8d_Traceguids,
            (unsigned int)v23);
        }
        WindowsDeleteString(string);
      }
      else
      {
        LOBYTE(a7) = 0;
        (*(void (__fastcall **)(struct Windows::Networking::UX::IAvailableNetwork *, HSTRING **))(*(_QWORD *)a2 + 120LL))(
          a2,
          &a7);
        v10 = 3 - ((_BYTE)a7 != 0);
        v12->dwFlags |= 0x10u;
        if ( a3 )
          v12->dwFlags |= 0x20u;
        *(_OWORD *)&v11->uSSIDLength = 0;
        *(_OWORD *)&v11->ucSSID[12] = 0;
        *(_DWORD *)&v11->ucSSID[28] = 0;
        if ( (*(unsigned __int8 (__fastcall **)(struct _WLAN_CONNECTION_PARAMETERS *))(*(_QWORD *)&a5->wlanConnectionMode
                                                                                     + 136LL))(a5) )
        {
          v12->dwFlags |= 1u;
          LODWORD(length) = 0;
          StringRawBuffer = WindowsGetStringRawBuffer(a4, (UINT32 *)&length);
          v26 = WlanStringToUtf8Ssid(StringRawBuffer, v11);
          v16 = v26;
          if ( v26 > 0 )
            v16 = (unsigned __int16)v26 | 0x80070000;
          if ( (v16 & 0x80000000) != 0
            && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
          {
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 115, &WPP_21979ef79db039135e573b3136931b8d_Traceguids, v16);
          }
        }
        else
        {
          (*(void (__fastcall **)(struct _WLAN_CONNECTION_PARAMETERS *, struct _DOT11_SSID *))(*(_QWORD *)&a5->wlanConnectionMode
                                                                                             + 80LL))(
            a5,
            v11);
        }
      }
      v12->pDot11Ssid = v11;
      v12->dot11BssType = dot11_BSS_type_infrastructure;
      v12->wlanConnectionMode = v10;
    }
    else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        113,
        &WPP_21979ef79db039135e573b3136931b8d_Traceguids,
        (unsigned int)v19);
    }
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&a5, v20, v21);
    goto LABEL_34;
  }
  v17 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
    return v16;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      112,
      &WPP_21979ef79db039135e573b3136931b8d_Traceguids,
      (unsigned int)v13);
LABEL_34:
    v17 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v17 != &WPP_GLOBAL_Control && (*((_BYTE *)v17 + 28) & 0x40) != 0 )
    WPP_SF_d(v17[2], 116, &WPP_21979ef79db039135e573b3136931b8d_Traceguids, v16);
  return v16;
}

```

## disassembly

```asm
0x18001a7d0  mov     [rsp-38h+arg_10], rbx
0x18001a7d5  mov     [rsp-38h+arg_0], rcx
0x18001a7da  push    rbp
0x18001a7db  push    rsi
0x18001a7dc  push    rdi
0x18001a7dd  push    r12
0x18001a7df  push    r13
0x18001a7e1  push    r14
0x18001a7e3  push    r15
0x18001a7e5  mov     rbp, rsp
0x18001a7e8  sub     rsp, 20h
0x18001a7ec  mov     r13, r9
0x18001a7ef  mov     r12b, r8b
0x18001a7f2  mov     r14, rdx
0x18001a7f5  lea     rax, WPP_GLOBAL_Control
0x18001a7fc  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a803  cmp     rcx, rax
0x18001a806  jz      short loc_18001A823
0x18001a808  test    byte ptr [rcx+1Ch], 40h
0x18001a80c  jz      short loc_18001A823
0x18001a80e  mov     edx, 6Fh ; 'o'
0x18001a813  lea     r8, WPP_21979ef79db039135e573b3136931b8d_Traceguids
0x18001a81a  mov     rcx, [rcx+10h]
0x18001a81e  call    WPP_SF_
0x18001a823  xor     r15d, r15d
0x18001a826  mov     rax, [rbp+arg_30]
0x18001a82a  mov     [rax], r15
0x18001a82d  mov     rdi, [rbp+length]
0x18001a831  mov     [rdi], r15d
0x18001a834  xorps   xmm0, xmm0
0x18001a837  xor     eax, eax
0x18001a839  mov     rsi, [rbp+arg_20]
0x18001a83d  movups  xmmword ptr [rsi], xmm0
0x18001a840  movups  xmmword ptr [rsi+10h], xmm0
0x18001a844  mov     [rsi+20h], rax
0x18001a848  mov     byte ptr [rbp+arg_0], r15b
0x18001a84c  mov     rax, [r14]
0x18001a84f  lea     rdx, [rbp+arg_0]
0x18001a853  mov     rcx, r14
0x18001a856  mov     rax, [rax+88h]
0x18001a85d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a862  mov     ebx, eax
0x18001a864  test    eax, eax
0x18001a866  jns     short loc_18001A8A5
0x18001a868  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a86f  lea     r14, WPP_GLOBAL_Control
0x18001a876  cmp     rcx, r14
0x18001a879  jz      loc_18001AB12
0x18001a87f  test    byte ptr [rcx+1Ch], 2
0x18001a883  jz      loc_18001AAEF
0x18001a889  lea     edx, [r15+70h]
0x18001a88d  mov     r9d, eax
0x18001a890  lea     r8, WPP_21979ef79db039135e573b3136931b8d_Traceguids
0x18001a897  mov     rcx, [rcx+10h]
0x18001a89b  call    WPP_SF_d
0x18001a8a0  jmp     loc_18001AAE8
0x18001a8a5  mov     [rbp+arg_20], r15
0x18001a8a9  mov     rax, [r14]
0x18001a8ac  mov     rbx, [rax]
0x18001a8af  lea     rcx, [rbp+arg_20]
0x18001a8b3  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18001a8b8  lea     r8, [rbp+arg_20]
0x18001a8bc  lea     rdx, _GUID_ac2798f8_4bd2_4d64_be61_7002641cd494
0x18001a8c3  mov     rcx, r14
0x18001a8c6  mov     rax, rbx
0x18001a8c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a8ce  mov     ebx, eax
0x18001a8d0  test    eax, eax
0x18001a8d2  jns     short loc_18001A912
0x18001a8d4  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a8db  lea     r14, WPP_GLOBAL_Control
0x18001a8e2  cmp     rcx, r14
0x18001a8e5  jz      loc_18001AADF
0x18001a8eb  test    byte ptr [rcx+1Ch], 2
0x18001a8ef  jz      loc_18001AADF
0x18001a8f5  mov     edx, 71h ; 'q'
0x18001a8fa  mov     r9d, eax
0x18001a8fd  lea     r8, WPP_21979ef79db039135e573b3136931b8d_Traceguids
0x18001a904  mov     rcx, [rcx+10h]
0x18001a908  call    WPP_SF_d
0x18001a90d  jmp     loc_18001AADF
0x18001a912  cmp     byte ptr [rbp+arg_0], r15b
0x18001a916  jz      loc_18001A9F7
0x18001a91c  mov     rcx, [rbp+arg_20]
0x18001a920  mov     rax, [rcx]
0x18001a923  mov     rax, [rax+80h]
0x18001a92a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a92f  xor     r12d, r12d
0x18001a932  test    al, al
0x18001a934  jz      short loc_18001A93B
0x18001a936  mov     edi, r12d
0x18001a939  jmp     short loc_18001A95D
0x18001a93b  xorps   xmm0, xmm0
0x18001a93e  xor     eax, eax
0x18001a940  movups  xmmword ptr [rdi], xmm0
0x18001a943  movups  xmmword ptr [rdi+10h], xmm0
0x18001a947  mov     [rdi+20h], eax
0x18001a94a  mov     rcx, [rbp+arg_20]
0x18001a94e  mov     rax, [rcx]
0x18001a951  mov     rdx, rdi
0x18001a954  mov     rax, [rax+50h]
0x18001a958  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a95d  mov     [rbp+string], r12
0x18001a961  mov     rax, [r14]
0x18001a964  mov     rbx, [rax+38h]
0x18001a968  xor     ecx, ecx; string
0x18001a96a  call    cs:__imp_WindowsDeleteString
0x18001a970  mov     [rbp+string], r12
0x18001a974  lea     rdx, [rbp+string]
0x18001a978  mov     rcx, r14
0x18001a97b  mov     rax, rbx
0x18001a97e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a983  mov     ebx, eax
0x18001a985  test    eax, eax
0x18001a987  jns     short loc_18001A9BC
0x18001a989  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a990  lea     r14, WPP_GLOBAL_Control
0x18001a997  cmp     rcx, r14
0x18001a99a  jz      short loc_18001A9E8
0x18001a99c  test    byte ptr [rcx+1Ch], 2
0x18001a9a0  jz      short loc_18001A9E8
0x18001a9a2  mov     edx, 72h ; 'r'
0x18001a9a7  mov     r9d, eax
0x18001a9aa  lea     r8, WPP_21979ef79db039135e573b3136931b8d_Traceguids
0x18001a9b1  mov     rcx, [rcx+10h]
0x18001a9b5  call    WPP_SF_d
0x18001a9ba  jmp     short loc_18001A9E8
0x18001a9bc  mov     dword ptr [rbp+length], r12d
0x18001a9c0  lea     rdx, [rbp+length]; length
0x18001a9c4  mov     rcx, [rbp+string]; string
0x18001a9c8  call    cs:__imp_WindowsGetStringRawBuffer
0x18001a9ce  mov     [rsi+8], rax
0x18001a9d2  mov     rax, [rbp+string]
0x18001a9d6  mov     [rbp+string], r12
0x18001a9da  mov     rcx, [rbp+arg_30]
0x18001a9de  mov     [rcx], rax
0x18001a9e1  lea     r14, WPP_GLOBAL_Control
0x18001a9e8  mov     rcx, [rbp+string]; string
0x18001a9ec  call    cs:__imp_WindowsDeleteString
0x18001a9f2  jmp     loc_18001AAD1
0x18001a9f7  mov     byte ptr [rbp+arg_30], r15b
0x18001a9fb  mov     rax, [r14]
0x18001a9fe  lea     rdx, [rbp+arg_30]
0x18001aa02  mov     rcx, r14
0x18001aa05  mov     rax, [rax+78h]
0x18001aa09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001aa0e  mov     al, byte ptr [rbp+arg_30]
0x18001aa11  neg     al
0x18001aa13  sbb     r15d, r15d
0x18001aa16  add     r15d, 3
0x18001aa1a  or      dword ptr [rsi+24h], 10h
0x18001aa1e  test    r12b, r12b
0x18001aa21  jz      short loc_18001AA27
0x18001aa23  or      dword ptr [rsi+24h], 20h
0x18001aa27  xorps   xmm0, xmm0
0x18001aa2a  xor     eax, eax
0x18001aa2c  movups  xmmword ptr [rdi], xmm0
0x18001aa2f  movups  xmmword ptr [rdi+10h], xmm0
0x18001aa33  mov     [rdi+20h], eax
0x18001aa36  mov     rcx, [rbp+arg_20]
0x18001aa3a  mov     rax, [rcx]
0x18001aa3d  mov     rax, [rax+88h]
0x18001aa44  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001aa49  test    al, al
0x18001aa4b  jz      short loc_18001AAB7
0x18001aa4d  or      dword ptr [rsi+24h], 1
0x18001aa51  mov     dword ptr [rbp+length], 0
0x18001aa58  lea     rdx, [rbp+length]; length
0x18001aa5c  mov     rcx, r13; string
0x18001aa5f  call    cs:__imp_WindowsGetStringRawBuffer
0x18001aa65  mov     rcx, rax
0x18001aa68  mov     rdx, rdi
0x18001aa6b  call    cs:__imp_WlanStringToUtf8Ssid
0x18001aa71  mov     ebx, eax
0x18001aa73  test    eax, eax
0x18001aa75  jle     short loc_18001AA80
0x18001aa77  movzx   ebx, ax
0x18001aa7a  or      ebx, 80070000h
0x18001aa80  test    ebx, ebx
0x18001aa82  jns     short loc_18001AACA
0x18001aa84  mov     rcx, cs:WPP_GLOBAL_Control
0x18001aa8b  lea     r14, WPP_GLOBAL_Control
0x18001aa92  cmp     rcx, r14
0x18001aa95  jz      short loc_18001AAD1
0x18001aa97  test    byte ptr [rcx+1Ch], 2
0x18001aa9b  jz      short loc_18001AAD1
0x18001aa9d  mov     edx, 73h ; 's'
0x18001aaa2  mov     r9d, ebx
0x18001aaa5  lea     r8, WPP_21979ef79db039135e573b3136931b8d_Traceguids
0x18001aaac  mov     rcx, [rcx+10h]
0x18001aab0  call    WPP_SF_d
0x18001aab5  jmp     short loc_18001AAD1
0x18001aab7  mov     rcx, [rbp+arg_20]
0x18001aabb  mov     rax, [rcx]
0x18001aabe  mov     rdx, rdi
0x18001aac1  mov     rax, [rax+50h]
0x18001aac5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001aaca  lea     r14, WPP_GLOBAL_Control
0x18001aad1  mov     [rsi+10h], rdi
0x18001aad5  mov     dword ptr [rsi+20h], 1
0x18001aadc  mov     [rsi], r15d
0x18001aadf  lea     rcx, [rbp+arg_20]
0x18001aae3  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18001aae8  mov     rcx, cs:WPP_GLOBAL_Control
0x18001aaef  cmp     rcx, r14
0x18001aaf2  jz      short loc_18001AB12
0x18001aaf4  test    byte ptr [rcx+1Ch], 40h
0x18001aaf8  jz      short loc_18001AB12
0x18001aafa  mov     edx, 74h ; 't'
0x18001aaff  mov     r9d, ebx
0x18001ab02  lea     r8, WPP_21979ef79db039135e573b3136931b8d_Traceguids
0x18001ab09  mov     rcx, [rcx+10h]
0x18001ab0d  call    WPP_SF_d
0x18001ab12  mov     eax, ebx
0x18001ab14  mov     rbx, [rsp+20h+arg_10]
0x18001ab19  add     rsp, 20h
0x18001ab1d  pop     r15
0x18001ab1f  pop     r14
0x18001ab21  pop     r13
0x18001ab23  pop     r12
0x18001ab25  pop     rdi
0x18001ab26  pop     rsi
0x18001ab27  pop     rbp
0x18001ab28  retn
```
