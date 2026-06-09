# DMCSP_DevDetail_GetRadioSwV

- ea: `0x180008980`
- end: `0x180008b3d`
- name: `DMCSP_DevDetail_GetRadioSwV`
- size: `445`
- prototype: `__int64 __fastcall(unsigned __int64, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x180004304`
- `0x180005384`
- `0x180007ffc`
- `0x180008980`
- `0x18000b010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800089e1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800089e1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180008ab1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180008ab1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180008a01`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180008af7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180008a01`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180008af7`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180008a24`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180008a24`

## pseudocode

```c
__int64 __fastcall DMCSP_DevDetail_GetRadioSwV(unsigned int a1, unsigned __int16 *a2)
{
  unsigned __int64 v3; // rsi
  HRESULT ActivationFactory; // ebx
  HSTRING v5; // rbx
  __int64 v6; // rdi
  int (__fastcall *v7)(__int64, __int64 *); // rbx
  __int64 v8; // rbx
  __int64 (__fastcall *v9)(__int64, __int64 *); // rdi
  const unsigned __int16 *StringRawBuffer; // r8
  unsigned __int64 v11; // rdx
  __int64 v13; // [rsp+20h] [rbp-30h] BYREF
  __int64 v14; // [rsp+28h] [rbp-28h] BYREF
  HSTRING v15; // [rsp+30h] [rbp-20h] BYREF
  HSTRING string; // [rsp+38h] [rbp-18h] BYREF
  HSTRING v17[2]; // [rsp+40h] [rbp-10h] BYREF
  UINT32 length; // [rsp+80h] [rbp+30h] BYREF
  __int64 v19; // [rsp+88h] [rbp+38h] BYREF

  v3 = a1;
  v17[0] = 0;
  v14 = 0;
  v13 = 0;
  v19 = 0;
  v15 = 0;
  length = 0;
  string = 0;
  ActivationFactory = WindowsCreateString(L"Windows.Networking.NetworkOperators.MobileBroadbandModem", 0x38u, &string);
  if ( ActivationFactory >= 0 )
  {
    v5 = string;
    v17[0] = string;
    WindowsDeleteString(0);
    Microsoft::WRL::ComPtr<Windows::Networking::NetworkOperators::IMobileBroadbandDeviceInformation>::InternalRelease(&v14);
    ActivationFactory = RoGetActivationFactory(v5, &GUID_f99ed637_d6f1_4a78_8cbc_6421a65063c8, &v14);
    if ( ActivationFactory >= 0 )
    {
      v6 = v14;
      v7 = *(int (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v14 + 64LL);
      Microsoft::WRL::ComPtr<Windows::Networking::NetworkOperators::IMobileBroadbandDeviceInformation>::InternalRelease(&v13);
      if ( v7(v6, &v13) < 0 || (v8 = v13) == 0 )
      {
        v11 = v3;
        StringRawBuffer = L"Not Present";
        goto LABEL_13;
      }
      v9 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v13 + 56LL);
      Microsoft::WRL::ComPtr<Windows::Networking::NetworkOperators::IMobileBroadbandDeviceInformation>::InternalRelease(&v19);
      ActivationFactory = v9(v8, &v19);
      if ( ActivationFactory >= 0 )
      {
        ActivationFactory = (*(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v19 + 72LL))(v19, &v15);
        if ( ActivationFactory >= 0 )
        {
          StringRawBuffer = WindowsGetStringRawBuffer(v15, &length);
          if ( !StringRawBuffer )
          {
            ActivationFactory = -2147418113;
            goto LABEL_14;
          }
          if ( length >= (unsigned int)v3 )
          {
            ActivationFactory = -2147024774;
            goto LABEL_14;
          }
          v11 = length + 1;
LABEL_13:
          ActivationFactory = StringCchCopyW(a2, v11, StringRawBuffer);
        }
      }
    }
  }
LABEL_14:
  WindowsDeleteString(v15);
  Microsoft::WRL::ComPtr<Windows::Networking::NetworkOperators::IMobileBroadbandDeviceInformation>::InternalRelease(&v19);
  Microsoft::WRL::ComPtr<Windows::Networking::NetworkOperators::IMobileBroadbandDeviceInformation>::InternalRelease(&v13);
  Microsoft::WRL::ComPtr<Windows::Networking::NetworkOperators::IMobileBroadbandDeviceInformation>::InternalRelease(&v14);
  Windows::Internal::String::~String((Windows::Internal::String *)v17);
  return (unsigned int)ActivationFactory;
}

```

## disassembly

```asm
0x180008980  mov     [rsp-18h+arg_0], rbx
0x180008985  mov     [rsp-18h+arg_8], rsi
0x18000898a  push    rbp
0x18000898b  push    rdi
0x18000898c  push    r14
0x18000898e  mov     rbp, rsp
0x180008991  sub     rsp, 50h
0x180008995  mov     r14, rdx
0x180008998  mov     esi, ecx
0x18000899a  mov     edx, 38h ; '8'; length
0x18000899f  mov     [rbp+var_10], 0
0x1800089a7  lea     rcx, ?RuntimeClass_Windows_Networking_NetworkOperators_MobileBroadbandModem@@3QBGB; "Windows.Networking.NetworkOperators.Mob"...
0x1800089ae  mov     [rbp+var_28], 0
0x1800089b6  lea     r8, [rbp+string]; string
0x1800089ba  mov     [rbp+var_30], 0
0x1800089c2  mov     [rbp+arg_18], 0
0x1800089ca  mov     [rbp+var_20], 0
0x1800089d2  mov     [rbp+length], 0
0x1800089d9  mov     [rbp+string], 0
0x1800089e1  call    cs:__imp_WindowsCreateString
0x1800089e8  nop     dword ptr [rax+rax+00h]
0x1800089ed  mov     ebx, eax
0x1800089ef  test    eax, eax
0x1800089f1  js      loc_180008AF3
0x1800089f7  mov     rbx, [rbp+string]
0x1800089fb  xor     ecx, ecx; string
0x1800089fd  mov     [rbp+var_10], rbx
0x180008a01  call    cs:__imp_WindowsDeleteString
0x180008a08  nop     dword ptr [rax+rax+00h]
0x180008a0d  lea     rcx, [rbp+var_28]
0x180008a11  call    ?InternalRelease@?$ComPtr@UIMobileBroadbandDeviceInformation@NetworkOperators@Networking@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Networking::NetworkOperators::IMobileBroadbandDeviceInformation>::InternalRelease(void)
0x180008a16  lea     r8, [rbp+var_28]
0x180008a1a  mov     rcx, rbx
0x180008a1d  lea     rdx, _GUID_f99ed637_d6f1_4a78_8cbc_6421a65063c8
0x180008a24  call    cs:__imp_RoGetActivationFactory
0x180008a2b  nop     dword ptr [rax+rax+00h]
0x180008a30  mov     ebx, eax
0x180008a32  test    eax, eax
0x180008a34  js      loc_180008AF3
0x180008a3a  mov     rdi, [rbp+var_28]
0x180008a3e  lea     rcx, [rbp+var_30]
0x180008a42  mov     rax, [rdi]
0x180008a45  mov     rbx, [rax+40h]
0x180008a49  call    ?InternalRelease@?$ComPtr@UIMobileBroadbandDeviceInformation@NetworkOperators@Networking@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Networking::NetworkOperators::IMobileBroadbandDeviceInformation>::InternalRelease(void)
0x180008a4e  lea     rdx, [rbp+var_30]
0x180008a52  mov     rcx, rdi
0x180008a55  mov     rax, rbx
0x180008a58  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008a5d  test    eax, eax
0x180008a5f  js      short loc_180008ADF
0x180008a61  mov     rbx, [rbp+var_30]
0x180008a65  test    rbx, rbx
0x180008a68  jz      short loc_180008ADF
0x180008a6a  mov     rax, [rbx]
0x180008a6d  lea     rcx, [rbp+arg_18]
0x180008a71  mov     rdi, [rax+38h]
0x180008a75  call    ?InternalRelease@?$ComPtr@UIMobileBroadbandDeviceInformation@NetworkOperators@Networking@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Networking::NetworkOperators::IMobileBroadbandDeviceInformation>::InternalRelease(void)
0x180008a7a  lea     rdx, [rbp+arg_18]
0x180008a7e  mov     rcx, rbx
0x180008a81  mov     rax, rdi
0x180008a84  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008a89  mov     ebx, eax
0x180008a8b  test    eax, eax
0x180008a8d  js      short loc_180008AF3
0x180008a8f  mov     rcx, [rbp+arg_18]
0x180008a93  lea     rdx, [rbp+var_20]
0x180008a97  mov     rax, [rcx]
0x180008a9a  mov     rax, [rax+48h]
0x180008a9e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008aa3  mov     ebx, eax
0x180008aa5  test    eax, eax
0x180008aa7  js      short loc_180008AF3
0x180008aa9  mov     rcx, [rbp+var_20]; string
0x180008aad  lea     rdx, [rbp+length]; length
0x180008ab1  call    cs:__imp_WindowsGetStringRawBuffer
0x180008ab8  nop     dword ptr [rax+rax+00h]
0x180008abd  mov     r8, rax
0x180008ac0  test    rax, rax
0x180008ac3  jnz     short loc_180008ACC
0x180008ac5  mov     ebx, 8000FFFFh
0x180008aca  jmp     short loc_180008AF3
0x180008acc  mov     eax, [rbp+length]
0x180008acf  cmp     eax, esi
0x180008ad1  jnb     short loc_180008AD8
0x180008ad3  lea     edx, [rax+1]
0x180008ad6  jmp     short loc_180008AE9
0x180008ad8  mov     ebx, 8007007Ah
0x180008add  jmp     short loc_180008AF3
0x180008adf  mov     rdx, rsi; unsigned __int64
0x180008ae2  lea     r8, aNotPresent; "Not Present"
0x180008ae9  mov     rcx, r14; unsigned __int16 *
0x180008aec  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180008af1  mov     ebx, eax
0x180008af3  mov     rcx, [rbp+var_20]; string
0x180008af7  call    cs:__imp_WindowsDeleteString
0x180008afe  nop     dword ptr [rax+rax+00h]
0x180008b03  lea     rcx, [rbp+arg_18]
0x180008b07  call    ?InternalRelease@?$ComPtr@UIMobileBroadbandDeviceInformation@NetworkOperators@Networking@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Networking::NetworkOperators::IMobileBroadbandDeviceInformation>::InternalRelease(void)
0x180008b0c  lea     rcx, [rbp+var_30]
0x180008b10  call    ?InternalRelease@?$ComPtr@UIMobileBroadbandDeviceInformation@NetworkOperators@Networking@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Networking::NetworkOperators::IMobileBroadbandDeviceInformation>::InternalRelease(void)
0x180008b15  lea     rcx, [rbp+var_28]
0x180008b19  call    ?InternalRelease@?$ComPtr@UIMobileBroadbandDeviceInformation@NetworkOperators@Networking@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Networking::NetworkOperators::IMobileBroadbandDeviceInformation>::InternalRelease(void)
0x180008b1e  lea     rcx, [rbp+var_10]; this
0x180008b22  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x180008b27  mov     rsi, [rsp+50h+arg_8]
0x180008b2c  mov     eax, ebx
0x180008b2e  mov     rbx, [rsp+50h+arg_0]
0x180008b33  add     rsp, 50h
0x180008b37  pop     r14
0x180008b39  pop     rdi
0x180008b3a  pop     rbp
0x180008b3b  retn
```
