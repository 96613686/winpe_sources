# Windows::Networking::UX::Internal::CWiFiProtocolUri::_StartConnection(Windows::Networking::UX::Internal::WlanMediaManager *,HSTRING__ *,uchar)

- ea: `0x1800626d4`
- end: `0x180062a08`
- name: `?_StartConnection@CWiFiProtocolUri@Internal@UX@Networking@Windows@@AEAAJPEAVWlanMediaManager@2345@PEAUHSTRING__@@E@Z`
- size: `820`
- prototype: `int(Windows::Networking::UX::Internal::CWiFiProtocolUri *__hidden this, struct Windows::Networking::UX::Internal::WlanMediaManager *, HSTRING, unsigned __int8)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180060cf0`

## callees

- `0x180008e30`
- `0x1800097b4`
- `0x180022184`
- `0x180022958`
- `0x1800626d4`
- `0x18008e010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCompareStringOrdinal` at `0x180062889`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCompareStringOrdinal` at `0x180062889`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180062808`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180062851`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800628b7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006295d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180062991`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800629ba`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180062808`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180062851`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800628b7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006295d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180062991`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800629ba`

## string_xrefs

- `0x180062738`: `onecoreuap\net\ux\wlanmediamanager\lib\cwifiprotocoluri.cpp`
- `0x18006278c`: `onecoreuap\net\ux\wlanmediamanager\lib\cwifiprotocoluri.cpp`
- `0x18006283a`: `onecoreuap\net\ux\wlanmediamanager\lib\cwifiprotocoluri.cpp`
- `0x1800628a0`: `onecoreuap\net\ux\wlanmediamanager\lib\cwifiprotocoluri.cpp`
- `0x18006293c`: `onecoreuap\net\ux\wlanmediamanager\lib\cwifiprotocoluri.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall Windows::Networking::UX::Internal::CWiFiProtocolUri::_StartConnection(
        Windows::Networking::UX::Internal::CWiFiProtocolUri *this,
        struct Windows::Networking::UX::Internal::WlanMediaManager *a2,
        HSTRING a3)
{
  int AvailableNetworkList; // eax
  unsigned int v6; // ebx
  __int64 v7; // rdx
  __int64 v8; // r8
  __int64 result; // rax
  int v10; // eax
  __int64 v11; // rdx
  __int64 v12; // r8
  unsigned int v13; // ebx
  __int64 v14; // rdx
  __int64 v15; // r8
  const char *v16; // r9
  int v17; // [rsp+20h] [rbp-88h]
  __int64 v18; // [rsp+50h] [rbp-58h] BYREF
  struct Windows::Networking::UX::IUserInputType *v19[2]; // [rsp+60h] [rbp-48h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+0h]

  v18 = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v18, a2, a3);
  *(_OWORD *)v19 = *(_OWORD *)((char *)this + 72);
  AvailableNetworkList = Windows::Networking::UX::Internal::WlanMediaManager::Category_get_AvailableNetworkList(
                           a2,
                           v19,
                           &v18);
  v6 = AvailableNetworkList;
  if ( AvailableNetworkList >= 0 )
  {
    try
    {
      v10 = (*(__int64 (**)(void))(*(_QWORD *)v18 + 56LL))();
      v13 = v10;
      if ( v10 >= 0 )
      {
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v18, v11, v12);
        result = 2147943568LL;
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x213,
          (unsigned int)"onecoreuap\\net\\ux\\wlanmediamanager\\lib\\cwifiprotocoluri.cpp",
          (const char *)(unsigned int)v10,
          v17);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v18, v14, v15);
        result = v13;
      }
    }
    catch ( ... )
    {
      return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                             retaddr,
                             (void *)0x22B,
                             (unsigned int)"onecoreuap\\net\\ux\\wlanmediamanager\\lib\\cwifiprotocoluri.cpp",
                             v16);
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x210,
      (unsigned int)"onecoreuap\\net\\ux\\wlanmediamanager\\lib\\cwifiprotocoluri.cpp",
      (const char *)(unsigned int)AvailableNetworkList,
      v17);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v18, v7, v8);
    return v6;
  }
  return result;
}

```

## disassembly

```asm
0x1800626d4  mov     rax, rsp
0x1800626d7  mov     [rax+10h], rbx
0x1800626db  mov     [rax+18h], rsi
0x1800626df  push    rdi
0x1800626e0  push    r12
0x1800626e2  push    r13
0x1800626e4  push    r14
0x1800626e6  push    r15
0x1800626e8  sub     rsp, 80h
0x1800626ef  mov     r13b, r9b
0x1800626f2  mov     r12, r8
0x1800626f5  mov     r14, rdx
0x1800626f8  mov     r15, rcx
0x1800626fb  xor     edi, edi
0x1800626fd  mov     [rax-58h], rdi
0x180062701  lea     rcx, [rax-58h]
0x180062705  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18006270a  movups  xmm0, xmmword ptr [r15+48h]
0x18006270f  movdqu  xmmword ptr [rsp+0A8h+var_48], xmm0
0x180062715  lea     r8, [rsp+0A8h+var_58]
0x18006271a  lea     rdx, [rsp+0A8h+var_48]
0x18006271f  mov     rcx, r14
0x180062722  call    ?Category_get_AvailableNetworkList@WlanMediaManager@Internal@UX@Networking@Windows@@QEAAJU_GUID@@PEAPEAU?$IVector@PEAUIAvailableNetwork@UX@Networking@Windows@@@Collections@Foundation@5@@Z; Windows::Networking::UX::Internal::WlanMediaManager::Category_get_AvailableNetworkList(_GUID,Windows::Foundation::Collections::IVector<Windows::Networking::UX::IAvailableNetwork *> * *)
0x180062727  mov     ebx, eax
0x180062729  test    eax, eax
0x18006272b  jns     short loc_18006275B
0x18006272d  mov     rcx, [rsp+0A8h]; this
0x180062735  mov     r9d, eax; char *
0x180062738  lea     r8, aOnecoreuapNetU_5; "onecoreuap\\net\\ux\\wlanmediamanager\\"...
0x18006273f  mov     edx, 210h; void *
0x180062744  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180062749  nop
0x18006274a  lea     rcx, [rsp+0A8h+var_58]
0x18006274f  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180062754  mov     eax, ebx
0x180062756  jmp     loc_1800629EA
0x18006275b  mov     [rsp+0A8h+arg_0], edi
0x180062762  mov     rcx, [rsp+0A8h+var_58]
0x180062767  mov     rax, [rcx]
0x18006276a  lea     rdx, [rsp+0A8h+arg_0]
0x180062772  mov     rax, [rax+38h]
0x180062776  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006277b  mov     ebx, eax
0x18006277d  test    eax, eax
0x18006277f  jns     short loc_1800627AF
0x180062781  mov     rcx, [rsp+0A8h]; this
0x180062789  mov     r9d, eax; char *
0x18006278c  lea     r8, aOnecoreuapNetU_5; "onecoreuap\\net\\ux\\wlanmediamanager\\"...
0x180062793  mov     edx, 213h; void *
0x180062798  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006279d  nop
0x18006279e  lea     rcx, [rsp+0A8h+var_58]
0x1800627a3  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800627a8  mov     eax, ebx
0x1800627aa  jmp     loc_1800629EA
0x1800627af  mov     esi, edi
0x1800627b1  cmp     esi, [rsp+0A8h+arg_0]
0x1800627b8  jnb     loc_1800629D2
0x1800627be  mov     [rsp+0A8h+var_50], rdi
0x1800627c3  mov     rdi, [rsp+0A8h+var_58]
0x1800627c8  mov     rax, [rdi]
0x1800627cb  mov     rbx, [rax+30h]
0x1800627cf  lea     rcx, [rsp+0A8h+var_50]
0x1800627d4  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800627d9  lea     r8, [rsp+0A8h+var_50]
0x1800627de  mov     edx, esi
0x1800627e0  mov     rcx, rdi
0x1800627e3  mov     rax, rbx
0x1800627e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800627eb  xor     edi, edi
0x1800627ed  test    eax, eax
0x1800627ef  js      loc_1800629C1
0x1800627f5  mov     [rsp+0A8h+string], rdi
0x1800627fa  mov     rdi, [rsp+0A8h+var_50]
0x1800627ff  mov     rax, [rdi]
0x180062802  mov     rbx, [rax+38h]
0x180062806  xor     ecx, ecx; string
0x180062808  call    cs:__imp_WindowsDeleteString
0x18006280e  mov     [rsp+0A8h+string], 0
0x180062817  lea     rdx, [rsp+0A8h+string]
0x18006281c  mov     rcx, rdi
0x18006281f  mov     rax, rbx
0x180062822  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180062827  mov     ebx, eax
0x180062829  xor     edi, edi
0x18006282b  test    eax, eax
0x18006282d  jns     short loc_180062878
0x18006282f  mov     rcx, [rsp+0A8h]; this
0x180062837  mov     r9d, eax; char *
0x18006283a  lea     r8, aOnecoreuapNetU_5; "onecoreuap\\net\\ux\\wlanmediamanager\\"...
0x180062841  mov     edx, 21Bh; void *
0x180062846  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006284b  nop
0x18006284c  mov     rcx, [rsp+0A8h+string]; string
0x180062851  call    cs:__imp_WindowsDeleteString
0x180062857  mov     [rsp+0A8h+string], rdi
0x18006285c  lea     rcx, [rsp+0A8h+var_50]
0x180062861  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180062866  nop
0x180062867  lea     rcx, [rsp+0A8h+var_58]
0x18006286c  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180062871  mov     eax, ebx
0x180062873  jmp     loc_1800629EA
0x180062878  mov     [rsp+0A8h+result], edi
0x18006287c  lea     r8, [rsp+0A8h+result]; result
0x180062881  mov     rdx, r12; string2
0x180062884  mov     rcx, [rsp+0A8h+string]; string1
0x180062889  call    cs:__imp_WindowsCompareStringOrdinal
0x18006288f  mov     ebx, eax
0x180062891  test    eax, eax
0x180062893  jns     short loc_1800628DE
0x180062895  mov     rcx, [rsp+0A8h]; this
0x18006289d  mov     r9d, eax; char *
0x1800628a0  lea     r8, aOnecoreuapNetU_5; "onecoreuap\\net\\ux\\wlanmediamanager\\"...
0x1800628a7  mov     edx, 21Eh; void *
0x1800628ac  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800628b1  nop
0x1800628b2  mov     rcx, [rsp+0A8h+string]; string
0x1800628b7  call    cs:__imp_WindowsDeleteString
0x1800628bd  mov     [rsp+0A8h+string], rdi
0x1800628c2  lea     rcx, [rsp+0A8h+var_50]
0x1800628c7  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800628cc  nop
0x1800628cd  lea     rcx, [rsp+0A8h+var_58]
0x1800628d2  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800628d7  mov     eax, ebx
0x1800628d9  jmp     loc_1800629EA
0x1800628de  cmp     [rsp+0A8h+result], edi
0x1800628e2  jnz     loc_1800629B5
0x1800628e8  mov     [rsp+0A8h+var_48], rdi
0x1800628ed  lea     rcx, [rsp+0A8h+var_48]
0x1800628f2  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800628f7  movups  xmm0, xmmword ptr [r15+48h]
0x1800628fc  movdqu  xmmword ptr [rsp+0A8h+var_38.Data1], xmm0
0x180062902  lea     rax, [rsp+0A8h+var_48]
0x180062907  mov     [rsp+0A8h+var_78], rax; struct Windows::Networking::UX::IUserInputType **
0x18006290c  mov     qword ptr [rsp+0A8h+var_80], rdi; char
0x180062911  mov     [rsp+0A8h+var_88], dil; int
0x180062916  mov     r9b, r13b; unsigned __int8
0x180062919  mov     r8, [rsp+0A8h+var_50]; struct Windows::Networking::UX::IAvailableNetwork *
0x18006291e  lea     rdx, [rsp+0A8h+var_38]; struct _GUID *
0x180062923  mov     rcx, r14; this
0x180062926  call    ?Category_StartConnection@WlanMediaManager@Internal@UX@Networking@Windows@@QEAAJU_GUID@@PEAUIAvailableNetwork@345@EE_KPEAPEAUIUserInputType@345@@Z; Windows::Networking::UX::Internal::WlanMediaManager::Category_StartConnection(_GUID,Windows::Networking::UX::IAvailableNetwork *,uchar,uchar,unsigned __int64,Windows::Networking::UX::IUserInputType * *)
0x18006292b  mov     ebx, eax
0x18006292d  test    eax, eax
0x18006292f  jns     short loc_180062981
0x180062931  mov     rcx, [rsp+0A8h]; this
0x180062939  mov     r9d, eax; char *
0x18006293c  lea     r8, aOnecoreuapNetU_5; "onecoreuap\\net\\ux\\wlanmediamanager\\"...
0x180062943  mov     edx, 224h; void *
0x180062948  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006294d  lea     rcx, [rsp+0A8h+var_48]
0x180062952  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180062957  nop
0x180062958  mov     rcx, [rsp+0A8h+string]; string
0x18006295d  call    cs:__imp_WindowsDeleteString
0x180062963  mov     [rsp+0A8h+string], rdi
0x180062968  lea     rcx, [rsp+0A8h+var_50]
0x18006296d  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180062972  nop
0x180062973  lea     rcx, [rsp+0A8h+var_58]
0x180062978  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18006297d  mov     eax, ebx
0x18006297f  jmp     short loc_1800629EA
0x180062981  lea     rcx, [rsp+0A8h+var_48]
0x180062986  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18006298b  nop
0x18006298c  mov     rcx, [rsp+0A8h+string]; string
0x180062991  call    cs:__imp_WindowsDeleteString
0x180062997  mov     [rsp+0A8h+string], rdi
0x18006299c  lea     rcx, [rsp+0A8h+var_50]
0x1800629a1  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800629a6  nop
0x1800629a7  lea     rcx, [rsp+0A8h+var_58]
0x1800629ac  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800629b1  xor     eax, eax
0x1800629b3  jmp     short loc_1800629EA
0x1800629b5  mov     rcx, [rsp+0A8h+string]; string
0x1800629ba  call    cs:__imp_WindowsDeleteString
0x1800629c0  nop
0x1800629c1  lea     rcx, [rsp+0A8h+var_50]
0x1800629c6  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800629cb  inc     esi
0x1800629cd  jmp     loc_1800627B1
0x1800629d2  lea     rcx, [rsp+0A8h+var_58]
0x1800629d7  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800629dc  mov     eax, 80070490h
0x1800629e1  jmp     short loc_1800629EA
0x1800629e3  mov     eax, [rsp+0A8h+arg_0]
0x1800629ea  lea     r11, [rsp+0A8h+var_28]
0x1800629f2  mov     rbx, [r11+38h]
0x1800629f6  mov     rsi, [r11+40h]
0x1800629fa  mov     rsp, r11
0x1800629fd  pop     r15
0x1800629ff  pop     r14
0x180062a01  pop     r13
0x180062a03  pop     r12
0x180062a05  pop     rdi
0x180062a06  retn
```
