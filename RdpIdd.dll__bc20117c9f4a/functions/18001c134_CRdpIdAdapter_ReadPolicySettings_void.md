# CRdpIdAdapter::ReadPolicySettings(void)

- ea: `0x18001c134`
- end: `0x18001c291`
- name: `?ReadPolicySettings@CRdpIdAdapter@@QEAAXXZ`
- size: `349`
- prototype: `void __fastcall(CRdpIdAdapter *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180013fdc`

## callees

- `0x180002458`
- `0x18000d614`
- `0x180014c60`
- `0x18001c134`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001c171`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001c171`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001c1b2`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001c1b2`

## string_xrefs

- `0x18001c16a`: `SOFTWARE\Policies\Microsoft\Windows NT\Terminal Services`
- `0x18001c215`: `CRdpIdAdapter::ReadPolicySettings`

## pseudocode

```c
void __fastcall CRdpIdAdapter::ReadPolicySettings(CRdpIdAdapter *this)
{
  _DWORD *v2; // rcx
  int v3; // r8d
  int v4; // r9d
  int v5; // [rsp+60h] [rbp+27h] BYREF
  int v6; // [rsp+64h] [rbp+2Bh] BYREF
  HKEY hKey; // [rsp+68h] [rbp+2Fh] BYREF
  __int64 v8; // [rsp+70h] [rbp+37h] BYREF
  const char *v9; // [rsp+78h] [rbp+3Fh] BYREF
  const char *v10; // [rsp+80h] [rbp+47h] BYREF
  const char *v11; // [rsp+88h] [rbp+4Fh] BYREF
  char v12; // [rsp+A8h] [rbp+6Fh] BYREF
  int Data; // [rsp+B0h] [rbp+77h] BYREF
  DWORD cbData; // [rsp+B8h] [rbp+7Fh] BYREF

  hKey = 0;
  if ( !RegOpenKeyExW(
          HKEY_LOCAL_MACHINE,
          L"SOFTWARE\\Policies\\Microsoft\\Windows NT\\Terminal Services",
          0,
          0x20019u,
          &hKey) )
  {
    Data = 0;
    cbData = 4;
    if ( !RegQueryValueExW(hKey, L"fPreferPrecisePresentRegions", 0, 0, (LPBYTE)&Data, &cbData) )
    {
      *((_BYTE *)this + 436) = Data != 0;
      v2 = *(_DWORD **)(wil::details::static_lazy<RdpIddLoggingProvider>::get() + 8);
      if ( *v2 > 4u )
      {
        v12 = *((_BYTE *)this + 436);
        v8 = *((_QWORD *)this + 65);
        v5 = *((_DWORD *)this + 129);
        v9 = "Policy fPreferPrecisePresentRegions is applied";
        v10 = "CRdpIdAdapter::ReadPolicySettings";
        v11 = "onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\adapter.cpp";
        v6 = 464;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>>(
          (_DWORD)v2,
          (unsigned int)byte_18004E025,
          v3,
          v4,
          (__int64)&v11,
          (__int64)&v6,
          (__int64)&v10,
          (__int64)&v9,
          (__int64)&v5,
          (__int64)&v8,
          (__int64)&v12);
      }
    }
  }
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
}

```

## disassembly

```asm
0x18001c134  mov     [rsp-8+arg_0], rbx
0x18001c139  push    rbp
0x18001c13a  lea     rbp, [rsp-57h]
0x18001c13f  sub     rsp, 90h
0x18001c146  mov     rbx, rcx
0x18001c149  mov     [rbp+57h+hKey], 0
0x18001c151  lea     rax, [rbp+57h+hKey]
0x18001c155  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001c15c  mov     r9d, 20019h; samDesired
0x18001c162  mov     [rsp+90h+phkResult], rax; phkResult
0x18001c167  xor     r8d, r8d; ulOptions
0x18001c16a  lea     rdx, SubKey; "SOFTWARE\\Policies\\Microsoft\\Windows "...
0x18001c171  call    cs:__imp_RegOpenKeyExW
0x18001c178  nop     dword ptr [rax+rax+00h]
0x18001c17d  test    eax, eax
0x18001c17f  jnz     loc_18001C276
0x18001c185  mov     rcx, [rbp+57h+hKey]; hKey
0x18001c189  lea     rdx, ValueName; "fPreferPrecisePresentRegions"
0x18001c190  mov     [rbp+57h+Data], eax
0x18001c193  xor     r9d, r9d; lpType
0x18001c196  lea     rax, [rbp+57h+cbData]
0x18001c19a  mov     [rbp+57h+cbData], 4
0x18001c1a1  mov     [rsp+90h+lpcbData], rax; lpcbData
0x18001c1a6  xor     r8d, r8d; lpReserved
0x18001c1a9  lea     rax, [rbp+57h+Data]
0x18001c1ad  mov     [rsp+90h+phkResult], rax; lpData
0x18001c1b2  call    cs:__imp_RegQueryValueExW
0x18001c1b9  nop     dword ptr [rax+rax+00h]
0x18001c1be  test    eax, eax
0x18001c1c0  jnz     loc_18001C276
0x18001c1c6  cmp     [rbp+57h+Data], eax
0x18001c1c9  setnz   al
0x18001c1cc  mov     [rbx+1B4h], al
0x18001c1d2  call    ?get@?$static_lazy@VRdpIddLoggingProvider@@@details@wil@@QEAAPEAVRdpIddLoggingProvider@@P6AXXZ@Z; wil::details::static_lazy<RdpIddLoggingProvider>::get(void (*)(void))
0x18001c1d7  mov     rcx, [rax+8]
0x18001c1db  mov     eax, [rcx]
0x18001c1dd  cmp     eax, 4
0x18001c1e0  jbe     loc_18001C276
0x18001c1e6  mov     al, [rbx+1B4h]
0x18001c1ec  lea     rdx, byte_18004E025
0x18001c1f3  mov     [rbp+57h+arg_8], al
0x18001c1f6  mov     rax, [rbx+208h]
0x18001c1fd  mov     [rbp+57h+var_20], rax
0x18001c201  mov     eax, [rbx+204h]
0x18001c207  mov     [rbp+57h+var_30], eax
0x18001c20a  lea     rax, aPolicyFpreferp; "Policy fPreferPrecisePresentRegions is "...
0x18001c211  mov     [rbp+57h+var_18], rax
0x18001c215  lea     rax, aCrdpidadapterR_2; "CRdpIdAdapter::ReadPolicySettings"
0x18001c21c  mov     [rbp+57h+var_10], rax
0x18001c220  lea     rax, aOnecoreuapTerm_15; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpi"...
0x18001c227  mov     [rbp+57h+var_8], rax
0x18001c22b  lea     rax, [rbp+57h+arg_8]
0x18001c22f  mov     [rsp+90h+var_40], rax
0x18001c234  lea     rax, [rbp+57h+var_20]
0x18001c238  mov     [rsp+90h+var_48], rax
0x18001c23d  lea     rax, [rbp+57h+var_30]
0x18001c241  mov     [rsp+90h+var_50], rax
0x18001c246  lea     rax, [rbp+57h+var_18]
0x18001c24a  mov     [rsp+90h+var_58], rax
0x18001c24f  lea     rax, [rbp+57h+var_10]
0x18001c253  mov     [rsp+90h+var_60], rax
0x18001c258  lea     rax, [rbp+57h+var_2C]
0x18001c25c  mov     [rsp+90h+lpcbData], rax
0x18001c261  lea     rax, [rbp+57h+var_8]
0x18001c265  mov     [rsp+90h+phkResult], rax
0x18001c26a  mov     [rbp+57h+var_2C], 1D0h
0x18001c271  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U1@U2@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$00@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@334AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$00@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<1> const &)
0x18001c276  lea     rcx, [rbp+57h+hKey]
0x18001c27a  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18001c27f  mov     rbx, [rsp+90h+arg_0]
0x18001c287  add     rsp, 90h
0x18001c28e  pop     rbp
0x18001c28f  retn
```
