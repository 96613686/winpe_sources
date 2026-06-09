# GetIMSI(ushort (&)[32])

- ea: `0x180063f10`
- end: `0x180064107`
- name: `?GetIMSI@@YAJAEAY0CA@G@Z`
- size: `503`
- prototype: `__int64 __fastcall(unsigned __int16 (*)[32])`
- caller_count: `0`
- callee_count: `7`
- tags: `installer_update, broker_com_uri`

## callees

- `0x1800583e8`
- `0x180059ca8`
- `0x180059cd4`
- `0x180063ab8`
- `0x180063f10`
- `0x180064a44`
- `0x1800c0010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180063fa3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180064050`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800640bc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180063fa3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180064050`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800640bc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180064081`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180064081`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180063f83`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180063f83`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180063fc6`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180063fc6`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall GetIMSI(unsigned __int16 (*a1)[32], __int64 a2)
{
  HRESULT ActivationFactory; // ebx
  HSTRING v4; // rbx
  __int64 v5; // rdi
  __int64 (__fastcall *v6)(__int64, __int64 *); // rbx
  __int64 v7; // rbx
  __int64 (__fastcall *v8)(__int64, __int64 *); // rdi
  __int64 v9; // rdi
  __int64 (__fastcall *v10)(__int64, HSTRING *); // rbx
  const unsigned __int16 *StringRawBuffer; // r8
  __int64 v13; // [rsp+20h] [rbp-20h] BYREF
  __int64 v14; // [rsp+28h] [rbp-18h] BYREF
  HSTRING string; // [rsp+30h] [rbp-10h] BYREF
  HSTRING v16; // [rsp+38h] [rbp-8h] BYREF
  UINT32 length; // [rsp+68h] [rbp+28h] BYREF
  HSTRING v18; // [rsp+70h] [rbp+30h] BYREF
  __int64 v19; // [rsp+78h] [rbp+38h] BYREF

  v16 = 0;
  v14 = 0;
  v13 = 0;
  v19 = 0;
  v18 = 0;
  length = 0;
  McGenEventRegister_EventRegister(
    MICROSOFT_WINDOWSPHONE_DMPHONEUTILS,
    a2,
    MICROSOFT_WINDOWSPHONE_DMPHONEUTILS_Context,
    MICROSOFT_WINDOWSPHONE_DMPHONEUTILS_Context);
  string = 0;
  ActivationFactory = WindowsCreateString(L"Windows.Networking.NetworkOperators.MobileBroadbandModem", 0x38u, &string);
  if ( ActivationFactory >= 0 )
  {
    v4 = string;
    v16 = string;
    WindowsDeleteString(0);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v14);
    ActivationFactory = RoGetActivationFactory(v4, &GUID_f99ed637_d6f1_4a78_8cbc_6421a65063c8, &v14);
    if ( ActivationFactory >= 0 )
    {
      v5 = v14;
      v6 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v14 + 64LL);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v13);
      ActivationFactory = v6(v5, &v13);
      if ( ActivationFactory >= 0 )
      {
        v7 = v13;
        if ( v13 )
        {
          v8 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v13 + 56LL);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v19);
          ActivationFactory = v8(v7, &v19);
          if ( ActivationFactory >= 0 )
          {
            v9 = v19;
            v10 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v19 + 120LL);
            WindowsDeleteString(v18);
            v18 = 0;
            ActivationFactory = v10(v9, &v18);
            if ( ActivationFactory >= 0 )
            {
              StringRawBuffer = WindowsGetStringRawBuffer(v18, &length);
              if ( StringRawBuffer )
                ActivationFactory = StringCchCopyW((unsigned __int16 *)a1, length + 1, StringRawBuffer);
              else
                ActivationFactory = -2147418113;
            }
          }
        }
        else
        {
          ActivationFactory = -2147020577;
        }
      }
    }
  }
  McGenEventUnregister_EventUnregister(MICROSOFT_WINDOWSPHONE_DMPHONEUTILS_Context);
  WindowsDeleteString(v18);
  v18 = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v19);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v13);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v14);
  Windows::Internal::String::~String((Windows::Internal::String *)&v16);
  return (unsigned int)ActivationFactory;
}

```

## disassembly

```asm
0x180063f10  mov     [rsp-18h+arg_0], rbx
0x180063f15  push    rbp
0x180063f16  push    rsi
0x180063f17  push    rdi
0x180063f18  mov     rbp, rsp
0x180063f1b  sub     rsp, 40h
0x180063f1f  mov     rsi, rcx
0x180063f22  mov     [rbp+var_8], 0
0x180063f2a  mov     [rbp+var_18], 0
0x180063f32  mov     [rbp+var_20], 0
0x180063f3a  mov     [rbp+arg_18], 0
0x180063f42  mov     [rbp+arg_10], 0
0x180063f4a  mov     [rbp+length], 0
0x180063f51  lea     r9, MICROSOFT_WINDOWSPHONE_DMPHONEUTILS_Context
0x180063f58  lea     r8, MICROSOFT_WINDOWSPHONE_DMPHONEUTILS_Context
0x180063f5f  lea     rcx, MICROSOFT_WINDOWSPHONE_DMPHONEUTILS
0x180063f66  call    McGenEventRegister_EventRegister
0x180063f6b  mov     [rbp+string], 0
0x180063f73  lea     r8, [rbp+string]; string
0x180063f77  mov     edx, 38h ; '8'; length
0x180063f7c  lea     rcx, ?RuntimeClass_Windows_Networking_NetworkOperators_MobileBroadbandModem@@3QBGB; "Windows.Networking.NetworkOperators.Mob"...
0x180063f83  call    cs:__imp_WindowsCreateString
0x180063f8a  nop     dword ptr [rax+rax+00h]
0x180063f8f  mov     ebx, eax
0x180063f91  test    eax, eax
0x180063f93  js      loc_1800640AB
0x180063f99  mov     rbx, [rbp+string]
0x180063f9d  mov     [rbp+var_8], rbx
0x180063fa1  xor     ecx, ecx; string
0x180063fa3  call    cs:__imp_WindowsDeleteString
0x180063faa  nop     dword ptr [rax+rax+00h]
0x180063faf  lea     rcx, [rbp+var_18]
0x180063fb3  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180063fb8  lea     r8, [rbp+var_18]
0x180063fbc  lea     rdx, _GUID_f99ed637_d6f1_4a78_8cbc_6421a65063c8
0x180063fc3  mov     rcx, rbx
0x180063fc6  call    cs:__imp_RoGetActivationFactory
0x180063fcd  nop     dword ptr [rax+rax+00h]
0x180063fd2  mov     ebx, eax
0x180063fd4  test    eax, eax
0x180063fd6  js      loc_1800640AB
0x180063fdc  mov     rdi, [rbp+var_18]
0x180063fe0  mov     rax, [rdi]
0x180063fe3  mov     rbx, [rax+40h]
0x180063fe7  lea     rcx, [rbp+var_20]
0x180063feb  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180063ff0  lea     rdx, [rbp+var_20]
0x180063ff4  mov     rcx, rdi
0x180063ff7  mov     rax, rbx
0x180063ffa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180063fff  mov     ebx, eax
0x180064001  test    eax, eax
0x180064003  js      loc_1800640AB
0x180064009  mov     rbx, [rbp+var_20]
0x18006400d  test    rbx, rbx
0x180064010  jnz     short loc_18006401C
0x180064012  mov     ebx, 800710DFh
0x180064017  jmp     loc_1800640AB
0x18006401c  mov     rax, [rbx]
0x18006401f  mov     rdi, [rax+38h]
0x180064023  lea     rcx, [rbp+arg_18]
0x180064027  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18006402c  lea     rdx, [rbp+arg_18]
0x180064030  mov     rcx, rbx
0x180064033  mov     rax, rdi
0x180064036  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006403b  mov     ebx, eax
0x18006403d  test    eax, eax
0x18006403f  js      short loc_1800640AB
0x180064041  mov     rdi, [rbp+arg_18]
0x180064045  mov     rax, [rdi]
0x180064048  mov     rbx, [rax+78h]
0x18006404c  mov     rcx, [rbp+arg_10]; string
0x180064050  call    cs:__imp_WindowsDeleteString
0x180064057  nop     dword ptr [rax+rax+00h]
0x18006405c  mov     [rbp+arg_10], 0
0x180064064  lea     rdx, [rbp+arg_10]
0x180064068  mov     rcx, rdi
0x18006406b  mov     rax, rbx
0x18006406e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180064073  mov     ebx, eax
0x180064075  test    eax, eax
0x180064077  js      short loc_1800640AB
0x180064079  lea     rdx, [rbp+length]; length
0x18006407d  mov     rcx, [rbp+arg_10]; string
0x180064081  call    cs:__imp_WindowsGetStringRawBuffer
0x180064088  nop     dword ptr [rax+rax+00h]
0x18006408d  mov     r8, rax; unsigned __int16 *
0x180064090  test    rax, rax
0x180064093  jnz     short loc_18006409C
0x180064095  mov     ebx, 8000FFFFh
0x18006409a  jmp     short loc_1800640AB
0x18006409c  mov     edx, [rbp+length]
0x18006409f  inc     edx; unsigned __int64
0x1800640a1  mov     rcx, rsi; unsigned __int16 *
0x1800640a4  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800640a9  mov     ebx, eax
0x1800640ab  lea     rcx, MICROSOFT_WINDOWSPHONE_DMPHONEUTILS_Context
0x1800640b2  call    McGenEventUnregister_EventUnregister
0x1800640b7  nop
0x1800640b8  mov     rcx, [rbp+arg_10]; string
0x1800640bc  call    cs:__imp_WindowsDeleteString
0x1800640c3  nop     dword ptr [rax+rax+00h]
0x1800640c8  mov     [rbp+arg_10], 0
0x1800640d0  lea     rcx, [rbp+arg_18]
0x1800640d4  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800640d9  nop
0x1800640da  lea     rcx, [rbp+var_20]
0x1800640de  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800640e3  nop
0x1800640e4  lea     rcx, [rbp+var_18]
0x1800640e8  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800640ed  nop
0x1800640ee  lea     rcx, [rbp+var_8]; this
0x1800640f2  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x1800640f7  mov     eax, ebx
0x1800640f9  mov     rbx, [rsp+40h+arg_0]
0x1800640fe  add     rsp, 40h
0x180064102  pop     rdi
0x180064103  pop     rsi
0x180064104  pop     rbp
0x180064105  retn
```
