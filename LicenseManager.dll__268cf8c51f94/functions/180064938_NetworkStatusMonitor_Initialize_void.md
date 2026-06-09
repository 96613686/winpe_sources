# NetworkStatusMonitor::Initialize(void)

- ea: `0x180064938`
- end: `0x180064b19`
- name: `?Initialize@NetworkStatusMonitor@@QEAAXXZ`
- size: `481`
- prototype: `void __fastcall(NetworkStatusMonitor *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180064898`

## callees

- `0x180004738`
- `0x180013b50`
- `0x1800593bc`
- `0x180064938`
- `0x180075e60`
- `0x1800b8010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180064a29`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180064a29`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180064acb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180064acb`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18006499f`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18006499f`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800649c0`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800649c0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180064989`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180064989`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall NetworkStatusMonitor::Initialize(NetworkStatusMonitor *this)
{
  HRESULT v2; // eax
  _QWORD *v3; // r14
  int ActivationFactory; // eax
  __int64 v5; // rdi
  __int64 (__fastcall *v6)(__int64, _QWORD *); // rbx
  int v7; // eax
  int v8; // eax
  int v9; // eax
  __int64 v10; // rcx
  int Format; // [rsp+20h] [rbp-50h]
  int v12; // [rsp+28h] [rbp-48h]
  int v13; // [rsp+30h] [rbp-40h] BYREF
  _QWORD v14[2]; // [rsp+38h] [rbp-38h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+48h] [rbp-28h] BYREF
  HSTRING string; // [rsp+60h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+18h]

  v14[0] = 0;
  v13 = 0;
  string = 0;
  v2 = WindowsCreateStringReference(
         L"Windows.Networking.Connectivity.NetworkInformation",
         0x32u,
         &hstringHeader,
         &string);
  if ( v2 < 0 )
    RaiseException(v2, 1u, 0, 0);
  v3 = (_QWORD *)((char *)this + 80);
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease((char *)this + 80);
  ActivationFactory = RoGetActivationFactory(string, &GUID_5074f851_950d_4165_9c15_365619481eea, (char *)this + 80);
  if ( ActivationFactory < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x29,
      (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\networkstatusmonitor.cpp",
      (const char *)(unsigned int)ActivationFactory,
      Format);
  v5 = *v3;
  v6 = *(__int64 (__fastcall **)(__int64, _QWORD *))(*(_QWORD *)*v3 + 56LL);
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(v14);
  v7 = v6(v5, v14);
  if ( v7 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x2A,
      (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\networkstatusmonitor.cpp",
      (const char *)(unsigned int)v7,
      Format);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  v14[1] = (char *)this + 16;
  if ( !*((_QWORD *)this + 9) )
  {
    v8 = (*(__int64 (__fastcall **)(_QWORD, NetworkStatusMonitor *))(*(_QWORD *)*v3 + 96LL))(*v3, this);
    if ( v8 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x31,
        (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\networkstatusmonitor.cpp",
        (const char *)(unsigned int)v8,
        Format);
  }
  if ( v14[0]
    && !*((_BYTE *)this + 56)
    && (*(int (__fastcall **)(_QWORD, int *))(*(_QWORD *)v14[0] + 56LL))(v14[0], &v13) >= 0 )
  {
    v9 = v13;
    *((_DWORD *)this + 15) = v13;
    v12 = v9;
    LogMessage(
      3u,
      "onecoreuap\\enduser\\winstore\\licensemanager\\lib\\networkstatusmonitor.cpp",
      0x39u,
      "NetworkStatusMonitor::Initialize",
      (wchar_t *)L"Network connectivity level initialized to 0x%x",
      v12);
  }
  if ( this != (NetworkStatusMonitor *)-16LL )
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  string = 0;
  v10 = v14[0];
  if ( v14[0] )
  {
    v14[0] = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
  }
}

```

## disassembly

```asm
0x180064938  mov     [rsp-18h+arg_8], rbx
0x18006493d  mov     [rsp-18h+arg_10], rsi
0x180064942  push    rbp
0x180064943  push    rdi
0x180064944  push    r14
0x180064946  mov     rbp, rsp
0x180064949  sub     rsp, 70h
0x18006494d  mov     rax, cs:__security_cookie
0x180064954  xor     rax, rsp
0x180064957  mov     [rbp+var_8], rax
0x18006495b  mov     rsi, rcx
0x18006495e  mov     [rbp+var_38], 0
0x180064966  mov     [rbp+var_40], 0
0x18006496d  mov     [rbp+string], 0
0x180064975  lea     r9, [rbp+string]; string
0x180064979  lea     r8, [rbp+hstringHeader]; hstringHeader
0x18006497d  mov     edx, 32h ; '2'; length
0x180064982  lea     rcx, ?RuntimeClass_Windows_Networking_Connectivity_NetworkInformation@@3QBGB; "Windows.Networking.Connectivity.Network"...
0x180064989  call    cs:__imp_WindowsCreateStringReference
0x18006498f  test    eax, eax
0x180064991  jns     short loc_1800649A6
0x180064993  xor     r9d, r9d; lpArguments
0x180064996  xor     r8d, r8d; nNumberOfArguments
0x180064999  lea     edx, [r9+1]; dwExceptionFlags
0x18006499d  mov     ecx, eax; dwExceptionCode
0x18006499f  call    cs:__imp_RaiseException
0x1800649a5  nop
0x1800649a6  lea     r14, [rsi+50h]
0x1800649aa  mov     rcx, r14
0x1800649ad  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800649b2  mov     r8, r14
0x1800649b5  lea     rdx, _GUID_5074f851_950d_4165_9c15_365619481eea
0x1800649bc  mov     rcx, [rbp+string]
0x1800649c0  call    cs:__imp_RoGetActivationFactory
0x1800649c6  mov     rcx, [rbp+18h]; this
0x1800649ca  test    eax, eax
0x1800649cc  jns     short loc_1800649E3
0x1800649ce  mov     r9d, eax; char *
0x1800649d1  lea     r8, aOnecoreuapEndu_5; "onecoreuap\\enduser\\winstore\\licensem"...
0x1800649d8  mov     edx, 29h ; ')'; void *
0x1800649dd  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800649e3  mov     rdi, [r14]
0x1800649e6  mov     rax, [rdi]
0x1800649e9  mov     rbx, [rax+38h]
0x1800649ed  lea     rcx, [rbp+var_38]
0x1800649f1  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800649f6  lea     rdx, [rbp+var_38]
0x1800649fa  mov     rcx, rdi
0x1800649fd  mov     rax, rbx
0x180064a00  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180064a05  mov     rcx, [rbp+18h]; this
0x180064a09  test    eax, eax
0x180064a0b  jns     short loc_180064A22
0x180064a0d  mov     r9d, eax; char *
0x180064a10  lea     r8, aOnecoreuapEndu_5; "onecoreuap\\enduser\\winstore\\licensem"...
0x180064a17  mov     edx, 2Ah ; '*'; void *
0x180064a1c  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180064a22  lea     rbx, [rsi+10h]
0x180064a26  mov     rcx, rbx; lpCriticalSection
0x180064a29  call    cs:__imp_EnterCriticalSection
0x180064a2f  mov     [rbp+var_30], rbx
0x180064a33  lea     r8, [rsi+48h]
0x180064a37  cmp     qword ptr [r8], 0
0x180064a3b  jnz     short loc_180064A6C
0x180064a3d  mov     rcx, [r14]
0x180064a40  mov     rax, [rcx]
0x180064a43  mov     rdx, rsi
0x180064a46  mov     rax, [rax+60h]
0x180064a4a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180064a4f  mov     rcx, [rbp+18h]; this
0x180064a53  test    eax, eax
0x180064a55  jns     short loc_180064A6C
0x180064a57  mov     r9d, eax; char *
0x180064a5a  lea     r8, aOnecoreuapEndu_5; "onecoreuap\\enduser\\winstore\\licensem"...
0x180064a61  mov     edx, 31h ; '1'; void *
0x180064a66  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180064a6c  mov     rcx, [rbp+var_38]
0x180064a70  test    rcx, rcx
0x180064a73  jz      short loc_180064AC3
0x180064a75  cmp     byte ptr [rsi+38h], 0
0x180064a79  jnz     short loc_180064AC3
0x180064a7b  mov     rax, [rcx]
0x180064a7e  lea     rdx, [rbp+var_40]
0x180064a82  mov     rax, [rax+38h]
0x180064a86  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180064a8b  test    eax, eax
0x180064a8d  js      short loc_180064AC3
0x180064a8f  mov     eax, [rbp+var_40]
0x180064a92  mov     [rsi+3Ch], eax
0x180064a95  mov     [rsp+70h+var_48], eax
0x180064a99  lea     rax, aNetworkConnect_0; "Network connectivity level initialized "...
0x180064aa0  mov     [rsp+70h+Format], rax; Format
0x180064aa5  lea     r9, aNetworkstatusm_1; "NetworkStatusMonitor::Initialize"
0x180064aac  mov     r8d, 39h ; '9'; unsigned int
0x180064ab2  lea     rdx, aOnecoreuapEndu_5; "onecoreuap\\enduser\\winstore\\licensem"...
0x180064ab9  lea     ecx, [r8-36h]; unsigned int
0x180064abd  call    ?LogMessage@@YAXIPEBDI0PEBGZZ; LogMessage(uint,char const *,uint,char const *,ushort const *,...)
0x180064ac2  nop
0x180064ac3  test    rbx, rbx
0x180064ac6  jz      short loc_180064AD2
0x180064ac8  mov     rcx, rbx; lpCriticalSection
0x180064acb  call    cs:__imp_LeaveCriticalSection
0x180064ad1  nop
0x180064ad2  mov     [rbp+string], 0
0x180064ada  mov     rcx, [rbp+var_38]
0x180064ade  test    rcx, rcx
0x180064ae1  jz      short loc_180064AF8
0x180064ae3  mov     [rbp+var_38], 0
0x180064aeb  mov     rax, [rcx]
0x180064aee  mov     rax, [rax+10h]
0x180064af2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180064af7  nop
0x180064af8  mov     rcx, [rbp+var_8]
0x180064afc  xor     rcx, rsp; StackCookie
0x180064aff  call    __security_check_cookie
0x180064b04  lea     r11, [rsp+70h+var_s0]
0x180064b09  mov     rbx, [r11+28h]
0x180064b0d  mov     rsi, [r11+30h]
0x180064b11  mov     rsp, r11
0x180064b14  pop     r14
0x180064b16  pop     rdi
0x180064b17  pop     rbp
0x180064b18  retn
```
