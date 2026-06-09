# Windows::Internal::Bluetooth::Helpers::sdp_service_lookup::begin(void)

- ea: `0x18004ba18`
- end: `0x18004bc23`
- name: `?begin@sdp_service_lookup@Helpers@Bluetooth@Internal@Windows@@QEAA?AViterator@12345@XZ`
- size: `523`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, registry_config, service_task`

## callers

- `0x1800414bc`

## callees

- `0x180001dd0`
- `0x1800029cc`
- `0x18000e0c0`
- `0x18003ee98`
- `0x18003f290`
- `0x18003f728`
- `0x1800453bc`
- `0x1800457dc`
- `0x18004b1f4`
- `0x18004ba18`
- `0x18004bcb8`
- `0x18004bd54`

## import_xrefs

- `WS2_32!WSAAddressToStringW` at `0x18004baae`
- `WS2_32!WSAAddressToStringW` at `0x18004baae`
- `WS2_32!WSALookupServiceBeginW` at `0x18004bb78`
- `WS2_32!WSALookupServiceBeginW` at `0x18004bb78`
- `WS2_32!__imp_WSAGetLastError` at `0x18004bab9`
- `WS2_32!__imp_WSAGetLastError` at `0x18004bb95`
- `WS2_32!__imp_WSAGetLastError` at `0x18004bab9`
- `WS2_32!__imp_WSAGetLastError` at `0x18004bb95`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void *__fastcall Windows::Internal::Bluetooth::Helpers::sdp_service_lookup::begin(__int64 a1, void *a2)
{
  int v4; // edx
  int v5; // r8d
  int v6; // r9d
  int Error; // eax
  DWORD v8; // ebx
  __int64 v9; // rcx
  __int64 v10; // rax
  int lpdwAddressStringLength; // [rsp+20h] [rbp-E0h]
  HANDLE hLookup; // [rsp+30h] [rbp-D0h] BYREF
  DWORD dwAddressStringLength; // [rsp+38h] [rbp-C8h] BYREF
  _BYTE v15[32]; // [rsp+40h] [rbp-C0h] BYREF
  struct _WSAQuerySetW qsRestrictions; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE saAddress[26]; // [rsp+E0h] [rbp-20h] BYREF
  int v18; // [rsp+FAh] [rbp-6h]
  WCHAR szAddressString[20]; // [rsp+100h] [rbp+0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+148h] [rbp+48h]

  hLookup = a2;
  *(_OWORD *)&saAddress[10] = 0;
  v18 = 0;
  strcpy(saAddress, " ");
  *(_QWORD *)&saAddress[2] = *(_QWORD *)a1;
  wcscpy(szAddressString, L"(12:34:56:78:9A:BC)");
  dwAddressStringLength = 20;
  if ( WSAAddressToStringW((LPSOCKADDR)saAddress, 0x1Eu, 0, szAddressString, &dwAddressStringLength) == -1 )
  {
    Error = WSAGetLastError();
    if ( Error > 0 )
      Error = (unsigned __int16)Error | 0x80070000;
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x342,
      (unsigned int)"onecore\\drivers\\wdm\\bluetooth\\libs\\bthhelpers\\bthsdphelpers.cpp",
      (const char *)(unsigned int)Error,
      lpdwAddressStringLength);
  }
  v8 = *(_BYTE *)(a1 + 24) != 0 ? 4608 : 512;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    WPP_SF_sSd(*((_QWORD *)WPP_GLOBAL_Control + 2), v4, v5, v6, (__int64)szAddressString, 0);
  *(_QWORD *)&qsRestrictions.dwSize = 120;
  memset_0(&qsRestrictions.lpszServiceInstanceName, 0, 0x70u);
  qsRestrictions.dwNameSpace = 16;
  qsRestrictions.lpszContext = szAddressString;
  qsRestrictions.lpServiceClassId = (LPGUID)(a1 + 8);
  hLookup = 0;
  wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&int WSALookupServiceEnd(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(
    &hLookup,
    0);
  if ( WSALookupServiceBeginW(&qsRestrictions, v8, &hLookup) == -1 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
    {
      WSAGetLastError();
      WPP_SF_sd(*((_QWORD *)WPP_GLOBAL_Control + 2), 29);
    }
    Windows::Internal::Bluetooth::Helpers::sdp_service_lookup::end(v9, a2);
  }
  else
  {
    v10 = Windows::Internal::Bluetooth::Helpers::sdp_service_lookup::iterator::iterator((__int64)v15, &hLookup, v8);
    Windows::Internal::Bluetooth::Helpers::sdp_service_lookup::iterator::iterator((__int64)a2, v10);
    Windows::Internal::Bluetooth::Helpers::sdp_service_lookup::iterator::~iterator((Windows::Internal::Bluetooth::Helpers::sdp_service_lookup::iterator *)v15);
  }
  wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&int WSALookupServiceEnd(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,int (*)(void *),&int WSALookupServiceEnd(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&hLookup);
  return a2;
}

```

## disassembly

```asm
0x18004ba18  mov     [rsp-8+arg_10], rbx
0x18004ba1d  mov     [rsp-8+arg_18], rsi
0x18004ba22  push    rbp
0x18004ba23  push    rdi
0x18004ba24  push    r15
0x18004ba26  lea     rbp, [rsp-30h]
0x18004ba2b  sub     rsp, 130h
0x18004ba32  mov     rax, cs:__security_cookie
0x18004ba39  xor     rax, rsp
0x18004ba3c  mov     [rbp+40h+var_18], rax
0x18004ba40  mov     rdi, rdx
0x18004ba43  mov     rsi, rcx
0x18004ba46  mov     [rsp+140h+hLookup], rdx
0x18004ba4b  xorps   xmm0, xmm0
0x18004ba4e  movdqu  xmmword ptr [rbp+40h+saAddress+0Ah], xmm0
0x18004ba53  mov     [rbp+40h+var_46], 0
0x18004ba5a  mov     eax, 20h ; ' '
0x18004ba5f  mov     word ptr [rbp+40h+saAddress], ax
0x18004ba63  mov     rax, [rcx]
0x18004ba66  mov     qword ptr [rbp+40h+saAddress+2], rax
0x18004ba6a  movups  xmm0, xmmword ptr cs:a123456789aBc; "(12:34:56:78:9A:BC)"
0x18004ba71  movups  xmmword ptr [rbp+40h+szAddressString], xmm0
0x18004ba75  movups  xmm1, xmmword ptr cs:a123456789aBc+10h; "6:78:9A:BC)"
0x18004ba7c  movups  [rbp+40h+var_30], xmm1
0x18004ba80  movsd   xmm0, qword ptr cs:a123456789aBc+20h; "BC)"
0x18004ba88  movsd   [rbp+40h+var_20], xmm0
0x18004ba8d  mov     [rsp+140h+dwAddressStringLength], 14h
0x18004ba95  lea     rax, [rsp+140h+dwAddressStringLength]
0x18004ba9a  mov     [rsp+140h+lpdwAddressStringLength], rax; int
0x18004ba9f  lea     r9, [rbp+40h+szAddressString]; lpszAddressString
0x18004baa3  xor     r8d, r8d; lpProtocolInfo
0x18004baa6  lea     edx, [r8+1Eh]; dwAddressLength
0x18004baaa  lea     rcx, [rbp+40h+saAddress]; lpsaAddress
0x18004baae  call    cs:__imp_WSAAddressToStringW
0x18004bab4  cmp     eax, 0FFFFFFFFh
0x18004bab7  jnz     short loc_18004BAE4
0x18004bab9  call    cs:__imp_WSAGetLastError
0x18004babf  test    eax, eax
0x18004bac1  jle     short loc_18004BACB
0x18004bac3  movzx   eax, ax
0x18004bac6  or      eax, 80070000h
0x18004bacb  mov     rcx, [rbp+48h]; this
0x18004bacf  mov     r9d, eax; char *
0x18004bad2  lea     r8, aOnecoreDrivers_28; "onecore\\drivers\\wdm\\bluetooth\\libs"...
0x18004bad9  mov     edx, 342h; void *
0x18004bade  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18004bae4  mov     al, [rsi+18h]
0x18004bae7  neg     al
0x18004bae9  sbb     ebx, ebx
0x18004baeb  and     ebx, 1000h
0x18004baf1  add     ebx, 200h
0x18004baf7  lea     r15, WPP_GLOBAL_Control
0x18004bafe  mov     rcx, cs:WPP_GLOBAL_Control
0x18004bb05  cmp     rcx, r15
0x18004bb08  jz      short loc_18004BB26
0x18004bb0a  cmp     byte ptr [rcx+19h], 5
0x18004bb0e  jb      short loc_18004BB26
0x18004bb10  mov     [rsp+140h+var_118], ebx
0x18004bb14  lea     rax, [rbp+40h+szAddressString]
0x18004bb18  mov     [rsp+140h+lpdwAddressStringLength], rax
0x18004bb1d  mov     rcx, [rcx+10h]
0x18004bb21  call    WPP_SF_sSd
0x18004bb26  mov     qword ptr [rsp+140h+qsRestrictions.dwSize], 78h ; 'x'
0x18004bb2f  xor     edx, edx; Val
0x18004bb31  lea     r8d, [rdx+70h]; Size
0x18004bb35  lea     rcx, [rsp+140h+qsRestrictions.lpszServiceInstanceName]; void *
0x18004bb3a  call    memset_0
0x18004bb3f  mov     [rbp+40h+qsRestrictions.dwNameSpace], 10h
0x18004bb46  lea     rax, [rbp+40h+szAddressString]
0x18004bb4a  mov     [rbp+40h+qsRestrictions.lpszContext], rax
0x18004bb4e  lea     rax, [rsi+8]
0x18004bb52  mov     [rsp+140h+qsRestrictions.lpServiceClassId], rax
0x18004bb57  mov     [rsp+140h+hLookup], 0
0x18004bb60  xor     edx, edx
0x18004bb62  lea     rcx, [rsp+140h+hLookup]
0x18004bb67  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AHPEAX@Z$1?WSALookupServiceEnd@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&WSALookupServiceEnd(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(void *)
0x18004bb6c  lea     r8, [rsp+140h+hLookup]; lphLookup
0x18004bb71  mov     edx, ebx; dwControlFlags
0x18004bb73  lea     rcx, [rsp+140h+qsRestrictions]; lpqsRestrictions
0x18004bb78  call    cs:__imp_WSALookupServiceBeginW
0x18004bb7e  cmp     eax, 0FFFFFFFFh
0x18004bb81  jnz     short loc_18004BBCA
0x18004bb83  mov     rax, cs:WPP_GLOBAL_Control
0x18004bb8a  cmp     rax, r15
0x18004bb8d  jz      short loc_18004BBC0
0x18004bb8f  cmp     byte ptr [rax+19h], 3
0x18004bb93  jb      short loc_18004BBC0
0x18004bb95  call    cs:__imp_WSAGetLastError
0x18004bb9b  test    eax, eax
0x18004bb9d  jle     short loc_18004BBA7
0x18004bb9f  movzx   eax, ax
0x18004bba2  or      eax, 80070000h
0x18004bba7  mov     edx, 1Dh
0x18004bbac  mov     dword ptr [rsp+140h+lpdwAddressStringLength], eax
0x18004bbb0  mov     rcx, cs:WPP_GLOBAL_Control
0x18004bbb7  mov     rcx, [rcx+10h]
0x18004bbbb  call    WPP_SF_sd
0x18004bbc0  mov     rdx, rdi
0x18004bbc3  call    ?end@sdp_service_lookup@Helpers@Bluetooth@Internal@Windows@@QEAA?AViterator@12345@XZ; Windows::Internal::Bluetooth::Helpers::sdp_service_lookup::end(void)
0x18004bbc8  jmp     short loc_18004BBF2
0x18004bbca  mov     r8d, ebx
0x18004bbcd  lea     rdx, [rsp+140h+hLookup]
0x18004bbd2  lea     rcx, [rsp+140h+var_100]
0x18004bbd7  call    ??0iterator@sdp_service_lookup@Helpers@Bluetooth@Internal@Windows@@QEAA@$$QEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AHPEAX@Z$1?WSALookupServiceEnd@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@K@Z; Windows::Internal::Bluetooth::Helpers::sdp_service_lookup::iterator::iterator(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&WSALookupServiceEnd(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>> &&,ulong)
0x18004bbdc  mov     rdx, rax
0x18004bbdf  mov     rcx, rdi
0x18004bbe2  call    ??0iterator@sdp_service_lookup@Helpers@Bluetooth@Internal@Windows@@QEAA@$$QEAV012345@@Z; Windows::Internal::Bluetooth::Helpers::sdp_service_lookup::iterator::iterator(Windows::Internal::Bluetooth::Helpers::sdp_service_lookup::iterator &&)
0x18004bbe7  lea     rcx, [rsp+140h+var_100]; this
0x18004bbec  call    ??1iterator@sdp_service_lookup@Helpers@Bluetooth@Internal@Windows@@QEAA@XZ; Windows::Internal::Bluetooth::Helpers::sdp_service_lookup::iterator::~iterator(void)
0x18004bbf1  nop
0x18004bbf2  lea     rcx, [rsp+140h+hLookup]
0x18004bbf7  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AHPEAX@Z$1?WSALookupServiceEnd@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&WSALookupServiceEnd(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,int (*)(void *),&WSALookupServiceEnd(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18004bbfc  mov     rax, rdi
0x18004bbff  mov     rcx, [rbp+40h+var_18]
0x18004bc03  xor     rcx, rsp; StackCookie
0x18004bc06  call    __security_check_cookie
0x18004bc0b  lea     r11, [rsp+140h+var_10]
0x18004bc13  mov     rbx, [r11+30h]
0x18004bc17  mov     rsi, [r11+38h]
0x18004bc1b  mov     rsp, r11
0x18004bc1e  pop     r15
0x18004bc20  pop     rdi
0x18004bc21  pop     rbp
0x18004bc22  retn
```
