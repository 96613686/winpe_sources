# CProtocolActivatedEventArgs::RuntimeClassInitialize(Windows::Foundation::IUriRuntimeClass *)

- ea: `0x180099240`
- end: `0x180099379`
- name: `?RuntimeClassInitialize@CProtocolActivatedEventArgs@@QEAAJPEAUIUriRuntimeClass@Foundation@Windows@@@Z`
- size: `313`
- prototype: `int(CProtocolActivatedEventArgs *__hidden this, struct Windows::Foundation::IUriRuntimeClass *)`
- caller_count: `2`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x18007689c`
- `0x180098b30`

## callees

- `0x18000b5c0`
- `0x180011328`
- `0x18003ec88`
- `0x18003f284`
- `0x180048324`
- `0x180099240`
- `0x1800a0010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18009927b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18009927b`
- `api-ms-win-core-com-l1-1-1!RoGetAgileReference` at `0x1800992e8`
- `api-ms-win-core-com-l1-1-1!RoGetAgileReference` at `0x1800992e8`
- `api-ms-win-shcore-thread-l1-1-0!GetProcessReference` at `0x180099364`
- `api-ms-win-shcore-thread-l1-1-0!GetProcessReference` at `0x180099364`

## string_xrefs

- `0x1800992a2`: `onecoreuap\shell\lib\activationeventsshell\protocolactivated.cpp`
- `0x1800992fc`: `onecoreuap\shell\lib\activationeventsshell\protocolactivated.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CProtocolActivatedEventArgs::RuntimeClassInitialize(
        CProtocolActivatedEventArgs *this,
        struct Windows::Foundation::IUriRuntimeClass *a2)
{
  HSTRING v4; // rbx
  HRESULT v5; // eax
  int v6; // eax
  unsigned int v7; // esi
  HSTRING *v9; // rax
  HSTRING *v10; // rbx
  int AgileReference; // eax
  unsigned int v12; // ebx
  __int64 v13; // rcx
  int v14; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  HSTRING string; // [rsp+40h] [rbp+8h] BYREF
  __int64 v17; // [rsp+50h] [rbp+18h] BYREF

  v4 = (HSTRING)((char *)this + 328);
  if ( *((_QWORD *)this + 41) )
    MicrosoftTelemetryAssertTriggeredNoArgs(this);
  string = 0;
  v5 = WindowsCreateString(&Src, 0, &string);
  v6 = Windows::Internal::String::FreeAndAssignOnSuccess(v5, string, (HSTRING *)this + 42);
  v7 = v6;
  if ( v6 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x27,
      (unsigned int)"onecoreuap\\shell\\lib\\activationeventsshell\\protocolactivated.cpp",
      (const char *)(unsigned int)v6,
      v14);
    return v7;
  }
  string = v4;
  v9 = (HSTRING *)Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::AgileRef>::operator Microsoft::WRL::AgileRef *(&string);
  v10 = v9;
  if ( a2 )
  {
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(v9);
    AgileReference = RoGetAgileReference(0, &GUID_9e365e57_48b2_4160_956f_c7385120bbfc, a2, v10);
    v12 = AgileReference;
    if ( AgileReference < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x28,
        (unsigned int)"onecoreuap\\shell\\lib\\activationeventsshell\\protocolactivated.cpp",
        (const char *)(unsigned int)AgileReference,
        v14);
      return v12;
    }
  }
  else
  {
    v17 = 0;
    string = *v9;
    *v9 = 0;
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&string);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v17);
  }
  v13 = *((_QWORD *)this + 43);
  *((_QWORD *)this + 43) = 0;
  if ( v13 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
  GetProcessReference((char *)this + 344);
  return 0;
}

```

## disassembly

```asm
0x180099240  mov     [rsp+arg_8], rbx
0x180099245  push    rbp
0x180099246  push    rsi
0x180099247  push    rdi; int
0x180099248  sub     rsp, 20h
0x18009924c  mov     rbp, rdx
0x18009924f  mov     rdi, rcx
0x180099252  lea     rbx, [rcx+148h]
0x180099259  cmp     qword ptr [rbx], 0
0x18009925d  jz      short loc_180099264
0x18009925f  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180099264  mov     [rsp+38h+string], 0
0x18009926d  lea     r8, [rsp+38h+string]; string
0x180099272  xor     edx, edx; length
0x180099274  lea     rcx, Src; sourceString
0x18009927b  call    cs:__imp_WindowsCreateString
0x180099281  lea     r8, [rdi+150h]; HSTRING *
0x180099288  mov     rdx, [rsp+38h+string]; HSTRING
0x18009928d  mov     ecx, eax; int
0x18009928f  call    ?FreeAndAssignOnSuccess@String@Internal@Windows@@CAJJPEAUHSTRING__@@PEAPEAU4@@Z; Windows::Internal::String::FreeAndAssignOnSuccess(long,HSTRING__ *,HSTRING__ * *)
0x180099294  mov     esi, eax
0x180099296  test    eax, eax
0x180099298  jns     short loc_1800992BA
0x18009929a  mov     rcx, [rsp+38h]; this
0x18009929f  mov     r9d, eax; char *
0x1800992a2  lea     r8, aOnecoreuapShel_3; "onecoreuap\\shell\\lib\\activationevent"...
0x1800992a9  mov     edx, 27h ; '''; void *
0x1800992ae  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800992b3  mov     eax, esi
0x1800992b5  jmp     loc_18009936C
0x1800992ba  mov     [rsp+38h+string], rbx
0x1800992bf  lea     rcx, [rsp+38h+string]
0x1800992c4  call    ??B?$ComPtrRef@VAgileRef@WRL@Microsoft@@@Details@WRL@Microsoft@@QEAAPEAVAgileRef@23@XZ; Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::AgileRef>::operator Microsoft::WRL::AgileRef *(void)
0x1800992c9  mov     rbx, rax
0x1800992cc  test    rbp, rbp
0x1800992cf  jz      short loc_180099311
0x1800992d1  mov     rcx, rax
0x1800992d4  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800992d9  mov     r9, rbx
0x1800992dc  mov     r8, rbp
0x1800992df  lea     rdx, _GUID_9e365e57_48b2_4160_956f_c7385120bbfc
0x1800992e6  xor     ecx, ecx
0x1800992e8  call    cs:__imp_RoGetAgileReference
0x1800992ee  mov     ebx, eax
0x1800992f0  test    eax, eax
0x1800992f2  jns     short loc_18009933F
0x1800992f4  mov     rcx, [rsp+38h]; this
0x1800992f9  mov     r9d, eax; char *
0x1800992fc  lea     r8, aOnecoreuapShel_3; "onecoreuap\\shell\\lib\\activationevent"...
0x180099303  mov     edx, 28h ; '('; void *
0x180099308  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18009930d  mov     eax, ebx
0x18009930f  jmp     short loc_18009936C
0x180099311  mov     [rsp+38h+arg_10], 0
0x18009931a  mov     rax, [rax]
0x18009931d  mov     [rsp+38h+string], rax
0x180099322  mov     qword ptr [rbx], 0
0x180099329  lea     rcx, [rsp+38h+string]
0x18009932e  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180099333  nop
0x180099334  lea     rcx, [rsp+38h+arg_10]
0x180099339  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18009933e  nop
0x18009933f  lea     rbx, [rdi+158h]
0x180099346  mov     rcx, [rbx]
0x180099349  mov     qword ptr [rbx], 0
0x180099350  test    rcx, rcx
0x180099353  jz      short loc_180099361
0x180099355  mov     rax, [rcx]
0x180099358  mov     rax, [rax+10h]
0x18009935c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180099361  mov     rcx, rbx
0x180099364  call    cs:__imp_GetProcessReference
0x18009936a  xor     eax, eax
0x18009936c  mov     rbx, [rsp+38h+arg_8]
0x180099371  add     rsp, 20h
0x180099375  pop     rdi
0x180099376  pop     rsi
0x180099377  pop     rbp
0x180099378  retn
```
