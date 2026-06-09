# GetICCID(ushort (&)[21])

- ea: `0x180063c10`
- end: `0x180063e0a`
- name: `?GetICCID@@YAJAEAY0BF@G@Z`
- size: `506`
- prototype: `__int64 __fastcall(unsigned __int16 (*)[21])`
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x1800583e8`
- `0x180059ca8`
- `0x180059cd4`
- `0x180063ab8`
- `0x180063c10`
- `0x180064a44`
- `0x1800c0010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180063ca3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180063d53`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180063dbf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180063ca3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180063d53`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180063dbf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180063d84`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180063d84`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180063c83`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180063c83`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180063cc6`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180063cc6`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall GetICCID(unsigned __int16 (*a1)[21], __int64 a2)
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
            v10 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v19 + 128LL);
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
0x180063c10  mov     [rsp-18h+arg_0], rbx
0x180063c15  push    rbp
0x180063c16  push    rsi
0x180063c17  push    rdi
0x180063c18  mov     rbp, rsp
0x180063c1b  sub     rsp, 40h
0x180063c1f  mov     rsi, rcx
0x180063c22  mov     [rbp+var_8], 0
0x180063c2a  mov     [rbp+var_18], 0
0x180063c32  mov     [rbp+var_20], 0
0x180063c3a  mov     [rbp+arg_18], 0
0x180063c42  mov     [rbp+arg_10], 0
0x180063c4a  mov     [rbp+length], 0
0x180063c51  lea     r9, MICROSOFT_WINDOWSPHONE_DMPHONEUTILS_Context
0x180063c58  lea     r8, MICROSOFT_WINDOWSPHONE_DMPHONEUTILS_Context
0x180063c5f  lea     rcx, MICROSOFT_WINDOWSPHONE_DMPHONEUTILS
0x180063c66  call    McGenEventRegister_EventRegister
0x180063c6b  mov     [rbp+string], 0
0x180063c73  lea     r8, [rbp+string]; string
0x180063c77  mov     edx, 38h ; '8'; length
0x180063c7c  lea     rcx, ?RuntimeClass_Windows_Networking_NetworkOperators_MobileBroadbandModem@@3QBGB; "Windows.Networking.NetworkOperators.Mob"...
0x180063c83  call    cs:__imp_WindowsCreateString
0x180063c8a  nop     dword ptr [rax+rax+00h]
0x180063c8f  mov     ebx, eax
0x180063c91  test    eax, eax
0x180063c93  js      loc_180063DAE
0x180063c99  mov     rbx, [rbp+string]
0x180063c9d  mov     [rbp+var_8], rbx
0x180063ca1  xor     ecx, ecx; string
0x180063ca3  call    cs:__imp_WindowsDeleteString
0x180063caa  nop     dword ptr [rax+rax+00h]
0x180063caf  lea     rcx, [rbp+var_18]
0x180063cb3  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180063cb8  lea     r8, [rbp+var_18]
0x180063cbc  lea     rdx, _GUID_f99ed637_d6f1_4a78_8cbc_6421a65063c8
0x180063cc3  mov     rcx, rbx
0x180063cc6  call    cs:__imp_RoGetActivationFactory
0x180063ccd  nop     dword ptr [rax+rax+00h]
0x180063cd2  mov     ebx, eax
0x180063cd4  test    eax, eax
0x180063cd6  js      loc_180063DAE
0x180063cdc  mov     rdi, [rbp+var_18]
0x180063ce0  mov     rax, [rdi]
0x180063ce3  mov     rbx, [rax+40h]
0x180063ce7  lea     rcx, [rbp+var_20]
0x180063ceb  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180063cf0  lea     rdx, [rbp+var_20]
0x180063cf4  mov     rcx, rdi
0x180063cf7  mov     rax, rbx
0x180063cfa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180063cff  mov     ebx, eax
0x180063d01  test    eax, eax
0x180063d03  js      loc_180063DAE
0x180063d09  mov     rbx, [rbp+var_20]
0x180063d0d  test    rbx, rbx
0x180063d10  jnz     short loc_180063D1C
0x180063d12  mov     ebx, 800710DFh
0x180063d17  jmp     loc_180063DAE
0x180063d1c  mov     rax, [rbx]
0x180063d1f  mov     rdi, [rax+38h]
0x180063d23  lea     rcx, [rbp+arg_18]
0x180063d27  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180063d2c  lea     rdx, [rbp+arg_18]
0x180063d30  mov     rcx, rbx
0x180063d33  mov     rax, rdi
0x180063d36  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180063d3b  mov     ebx, eax
0x180063d3d  test    eax, eax
0x180063d3f  js      short loc_180063DAE
0x180063d41  mov     rdi, [rbp+arg_18]
0x180063d45  mov     rax, [rdi]
0x180063d48  mov     rbx, [rax+80h]
0x180063d4f  mov     rcx, [rbp+arg_10]; string
0x180063d53  call    cs:__imp_WindowsDeleteString
0x180063d5a  nop     dword ptr [rax+rax+00h]
0x180063d5f  mov     [rbp+arg_10], 0
0x180063d67  lea     rdx, [rbp+arg_10]
0x180063d6b  mov     rcx, rdi
0x180063d6e  mov     rax, rbx
0x180063d71  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180063d76  mov     ebx, eax
0x180063d78  test    eax, eax
0x180063d7a  js      short loc_180063DAE
0x180063d7c  lea     rdx, [rbp+length]; length
0x180063d80  mov     rcx, [rbp+arg_10]; string
0x180063d84  call    cs:__imp_WindowsGetStringRawBuffer
0x180063d8b  nop     dword ptr [rax+rax+00h]
0x180063d90  mov     r8, rax; unsigned __int16 *
0x180063d93  test    rax, rax
0x180063d96  jnz     short loc_180063D9F
0x180063d98  mov     ebx, 8000FFFFh
0x180063d9d  jmp     short loc_180063DAE
0x180063d9f  mov     edx, [rbp+length]
0x180063da2  inc     edx; unsigned __int64
0x180063da4  mov     rcx, rsi; unsigned __int16 *
0x180063da7  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180063dac  mov     ebx, eax
0x180063dae  lea     rcx, MICROSOFT_WINDOWSPHONE_DMPHONEUTILS_Context
0x180063db5  call    McGenEventUnregister_EventUnregister
0x180063dba  nop
0x180063dbb  mov     rcx, [rbp+arg_10]; string
0x180063dbf  call    cs:__imp_WindowsDeleteString
0x180063dc6  nop     dword ptr [rax+rax+00h]
0x180063dcb  mov     [rbp+arg_10], 0
0x180063dd3  lea     rcx, [rbp+arg_18]
0x180063dd7  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180063ddc  nop
0x180063ddd  lea     rcx, [rbp+var_20]
0x180063de1  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180063de6  nop
0x180063de7  lea     rcx, [rbp+var_18]
0x180063deb  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180063df0  nop
0x180063df1  lea     rcx, [rbp+var_8]; this
0x180063df5  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x180063dfa  mov     eax, ebx
0x180063dfc  mov     rbx, [rsp+40h+arg_0]
0x180063e01  add     rsp, 40h
0x180063e05  pop     rdi
0x180063e06  pop     rsi
0x180063e07  pop     rbp
0x180063e08  retn
```
