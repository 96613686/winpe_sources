# CDisplayBroker::Initialize(Windows::Devices::Display::Core::IDisplayManager *)

- ea: `0x18005eb18`
- end: `0x18005ec03`
- name: `?Initialize@CDisplayBroker@@QEAAJPEAUIDisplayManager@Core@Display@Devices@Windows@@@Z`
- size: `235`
- prototype: `__int64 __fastcall(CDisplayBroker *__hidden this, struct Windows::Devices::Display::Core::IDisplayManager *)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x1800afb50`

## callees

- `0x18001f43c`
- `0x18005eb18`
- `0x18005ec0c`
- `0x18005ecb0`
- `0x180095130`
- `0x1800ea010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18005eb6f`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18005eb6f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18005eb59`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18005eb59`

## string_xrefs

- `0x18005eb52`: `DispBrokerDesktop.SessionBrokerInstance`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CDisplayBroker::Initialize(
        CDisplayBroker *this,
        struct Windows::Devices::Display::Core::IDisplayManager *a2)
{
  HRESULT v4; // eax
  HSTRING v5; // rbx
  int v6; // eax
  unsigned int v7; // ebx
  int v8; // eax
  HSTRING_HEADER v10; // [rsp+30h] [rbp-38h] BYREF
  HSTRING v11; // [rsp+48h] [rbp-20h] BYREF

  v11 = 0;
  v4 = WindowsCreateStringReference(L"DispBrokerDesktop.SessionBrokerInstance", 0x27u, &v10, &v11);
  if ( v4 < 0 )
  {
    RaiseException(v4, 1u, 0, 0);
    __debugbreak();
  }
  v5 = v11;
  Microsoft::WRL::ComPtr<DispBrokerDesktop::ISessionBrokerInstance>::InternalRelease(this);
  v6 = Windows::Foundation::ActivateInstance<DispBrokerDesktop::ISessionBrokerInstance>(v5, this);
  v7 = v6;
  if ( v6 < 0 )
  {
    MilInstrumentationCheckHR_MaybeFailFast(0x14u, 0, 0, v6, 0x1Du, 0);
  }
  else
  {
    v8 = (*(__int64 (__fastcall **)(_QWORD, struct Windows::Devices::Display::Core::IDisplayManager *))(**(_QWORD **)this + 48LL))(
           *(_QWORD *)this,
           a2);
    v7 = v8;
    if ( v8 < 0 )
      MilInstrumentationCheckHR_MaybeFailFast(0x14u, 0, 0, v8, 0x1Eu, 0);
  }
  return v7;
}

```

## disassembly

```asm
0x18005eb18  mov     r11, rsp
0x18005eb1b  mov     [r11+18h], rbx
0x18005eb1f  mov     [r11+20h], rsi
0x18005eb23  push    rdi
0x18005eb24  sub     rsp, 60h
0x18005eb28  mov     rax, cs:__security_cookie
0x18005eb2f  xor     rax, rsp
0x18005eb32  mov     [rsp+68h+var_18], rax
0x18005eb37  mov     rsi, rdx
0x18005eb3a  mov     rdi, rcx
0x18005eb3d  mov     qword ptr [r11-20h], 0
0x18005eb45  lea     r9, [r11-20h]; string
0x18005eb49  lea     r8, [r11-38h]; hstringHeader
0x18005eb4d  mov     edx, 27h ; '''; length
0x18005eb52  lea     rcx, aDispbrokerdesk; "DispBrokerDesktop.SessionBrokerInstance"
0x18005eb59  call    cs:__imp_WindowsCreateStringReference
0x18005eb5f  test    eax, eax
0x18005eb61  jns     short loc_18005EB76
0x18005eb63  xor     r9d, r9d; lpArguments
0x18005eb66  xor     r8d, r8d; nNumberOfArguments
0x18005eb69  lea     edx, [r9+1]; dwExceptionFlags
0x18005eb6d  mov     ecx, eax; dwExceptionCode
0x18005eb6f  call    cs:__imp_RaiseException
0x18005eb75  int     3; Trap to Debugger
0x18005eb76  mov     rbx, [rsp+68h+var_20]
0x18005eb7b  mov     rcx, rdi
0x18005eb7e  call    ?InternalRelease@?$ComPtr@UISessionBrokerInstance@DispBrokerDesktop@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<DispBrokerDesktop::ISessionBrokerInstance>::InternalRelease(void)
0x18005eb83  mov     rdx, rdi
0x18005eb86  mov     rcx, rbx
0x18005eb89  call    ??$ActivateInstance@UISessionBrokerInstance@DispBrokerDesktop@@@Foundation@Windows@@YAJPEAUHSTRING__@@PEAPEAUISessionBrokerInstance@DispBrokerDesktop@@@Z; Windows::Foundation::ActivateInstance<DispBrokerDesktop::ISessionBrokerInstance>(HSTRING__ *,DispBrokerDesktop::ISessionBrokerInstance * *)
0x18005eb8e  mov     ebx, eax
0x18005eb90  test    eax, eax
0x18005eb92  js      short loc_18005EBCD
0x18005eb94  mov     rcx, [rdi]
0x18005eb97  mov     rax, [rcx]
0x18005eb9a  mov     rdx, rsi
0x18005eb9d  mov     rax, [rax+30h]
0x18005eba1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005eba6  mov     ebx, eax
0x18005eba8  test    eax, eax
0x18005ebaa  js      short loc_18005EBF0
0x18005ebac  mov     eax, ebx
0x18005ebae  mov     rcx, [rsp+68h+var_18]
0x18005ebb3  xor     rcx, rsp; StackCookie
0x18005ebb6  call    __security_check_cookie
0x18005ebbb  lea     r11, [rsp+68h+var_8]
0x18005ebc0  mov     rbx, [r11+20h]
0x18005ebc4  mov     rsi, [r11+28h]
0x18005ebc8  mov     rsp, r11
0x18005ebcb  pop     rdi
0x18005ebcc  retn
0x18005ebcd  mov     [rsp+68h+var_40], 0; void *
0x18005ebd6  mov     [rsp+68h+var_48], 1Dh; unsigned int
0x18005ebde  mov     r9d, eax; int
0x18005ebe1  xor     r8d, r8d; unsigned int
0x18005ebe4  xor     edx, edx; int *
0x18005ebe6  lea     ecx, [rdx+14h]; unsigned int
0x18005ebe9  call    ?MilInstrumentationCheckHR_MaybeFailFast@@YAXKQEBJIJIPEAX@Z; MilInstrumentationCheckHR_MaybeFailFast(ulong,long const * const,uint,long,uint,void *)
0x18005ebee  jmp     short loc_18005EBAC
0x18005ebf0  mov     [rsp+68h+var_40], 0
0x18005ebf9  mov     [rsp+68h+var_48], 1Eh
0x18005ec01  jmp     short loc_18005EBDE
```
