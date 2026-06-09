# DMCSP_DevDetail_GetCommercializationOperator

- ea: `0x1800083c0`
- end: `0x180008598`
- name: `DMCSP_DevDetail_GetCommercializationOperator`
- size: `472`
- prototype: `__int64 __fastcall(unsigned int, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x180004304`
- `0x180005384`
- `0x180007ffc`
- `0x180008020`
- `0x1800083c0`
- `0x18000b010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18000843c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18000843c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000850c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000850c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000845c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180008552`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000845c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180008552`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18000847f`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18000847f`

## pseudocode

```c
__int64 __fastcall DMCSP_DevDetail_GetCommercializationOperator(unsigned int a1, unsigned __int16 *a2)
{
  unsigned __int64 v3; // rsi
  HRESULT OneCoreInformation; // ebx
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
  OneCoreInformation = QueryOneCoreInformation(L"OneCoreOperatorName", a1, a2);
  if ( OneCoreInformation < 0 )
  {
    string = 0;
    OneCoreInformation = WindowsCreateString(
                           L"Windows.Networking.NetworkOperators.MobileBroadbandModem",
                           0x38u,
                           &string);
    if ( OneCoreInformation >= 0 )
    {
      v5 = string;
      v17[0] = string;
      WindowsDeleteString(0);
      Microsoft::WRL::ComPtr<Windows::Networking::NetworkOperators::IMobileBroadbandDeviceInformation>::InternalRelease(&v14);
      OneCoreInformation = RoGetActivationFactory(v5, &GUID_f99ed637_d6f1_4a78_8cbc_6421a65063c8, &v14);
      if ( OneCoreInformation >= 0 )
      {
        v6 = v14;
        v7 = *(int (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v14 + 64LL);
        Microsoft::WRL::ComPtr<Windows::Networking::NetworkOperators::IMobileBroadbandDeviceInformation>::InternalRelease(&v13);
        if ( v7(v6, &v13) < 0 || (v8 = v13) == 0 )
        {
          v11 = v3;
          StringRawBuffer = L"Not Present";
          goto LABEL_14;
        }
        v9 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v13 + 56LL);
        Microsoft::WRL::ComPtr<Windows::Networking::NetworkOperators::IMobileBroadbandDeviceInformation>::InternalRelease(&v19);
        OneCoreInformation = v9(v8, &v19);
        if ( OneCoreInformation >= 0 )
        {
          OneCoreInformation = (*(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v19 + 72LL))(v19, &v15);
          if ( OneCoreInformation >= 0 )
          {
            StringRawBuffer = WindowsGetStringRawBuffer(v15, &length);
            if ( !StringRawBuffer )
            {
              OneCoreInformation = -2147418113;
              goto LABEL_15;
            }
            if ( length >= (unsigned int)v3 )
            {
              OneCoreInformation = -2147024774;
              goto LABEL_15;
            }
            v11 = length + 1;
LABEL_14:
            OneCoreInformation = StringCchCopyW(a2, v11, StringRawBuffer);
          }
        }
      }
    }
  }
LABEL_15:
  WindowsDeleteString(v15);
  Microsoft::WRL::ComPtr<Windows::Networking::NetworkOperators::IMobileBroadbandDeviceInformation>::InternalRelease(&v19);
  Microsoft::WRL::ComPtr<Windows::Networking::NetworkOperators::IMobileBroadbandDeviceInformation>::InternalRelease(&v13);
  Microsoft::WRL::ComPtr<Windows::Networking::NetworkOperators::IMobileBroadbandDeviceInformation>::InternalRelease(&v14);
  Windows::Internal::String::~String((Windows::Internal::String *)v17);
  return (unsigned int)OneCoreInformation;
}

```

## disassembly

```asm
0x1800083c0  mov     [rsp-18h+arg_0], rbx
0x1800083c5  mov     [rsp-18h+arg_8], rsi
0x1800083ca  push    rbp
0x1800083cb  push    rdi
0x1800083cc  push    r14
0x1800083ce  mov     rbp, rsp
0x1800083d1  sub     rsp, 50h
0x1800083d5  mov     r14, rdx
0x1800083d8  mov     esi, ecx
0x1800083da  mov     r8, rdx; unsigned __int16 *
0x1800083dd  mov     [rbp+var_10], 0
0x1800083e5  mov     edx, ecx; unsigned int
0x1800083e7  mov     [rbp+var_28], 0
0x1800083ef  lea     rcx, aOnecoreoperato; "OneCoreOperatorName"
0x1800083f6  mov     [rbp+var_30], 0
0x1800083fe  mov     [rbp+arg_18], 0
0x180008406  mov     [rbp+var_20], 0
0x18000840e  mov     [rbp+length], 0
0x180008415  call    ?QueryOneCoreInformation@@YAJPEBGKPEAG@Z; QueryOneCoreInformation(ushort const *,ulong,ushort *)
0x18000841a  mov     ebx, eax
0x18000841c  test    eax, eax
0x18000841e  jns     loc_18000854E
0x180008424  lea     r8, [rbp+string]; string
0x180008428  mov     [rbp+string], 0
0x180008430  mov     edx, 38h ; '8'; length
0x180008435  lea     rcx, ?RuntimeClass_Windows_Networking_NetworkOperators_MobileBroadbandModem@@3QBGB; "Windows.Networking.NetworkOperators.Mob"...
0x18000843c  call    cs:__imp_WindowsCreateString
0x180008443  nop     dword ptr [rax+rax+00h]
0x180008448  mov     ebx, eax
0x18000844a  test    eax, eax
0x18000844c  js      loc_18000854E
0x180008452  mov     rbx, [rbp+string]
0x180008456  xor     ecx, ecx; string
0x180008458  mov     [rbp+var_10], rbx
0x18000845c  call    cs:__imp_WindowsDeleteString
0x180008463  nop     dword ptr [rax+rax+00h]
0x180008468  lea     rcx, [rbp+var_28]
0x18000846c  call    ?InternalRelease@?$ComPtr@UIMobileBroadbandDeviceInformation@NetworkOperators@Networking@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Networking::NetworkOperators::IMobileBroadbandDeviceInformation>::InternalRelease(void)
0x180008471  lea     r8, [rbp+var_28]
0x180008475  mov     rcx, rbx
0x180008478  lea     rdx, _GUID_f99ed637_d6f1_4a78_8cbc_6421a65063c8
0x18000847f  call    cs:__imp_RoGetActivationFactory
0x180008486  nop     dword ptr [rax+rax+00h]
0x18000848b  mov     ebx, eax
0x18000848d  test    eax, eax
0x18000848f  js      loc_18000854E
0x180008495  mov     rdi, [rbp+var_28]
0x180008499  lea     rcx, [rbp+var_30]
0x18000849d  mov     rax, [rdi]
0x1800084a0  mov     rbx, [rax+40h]
0x1800084a4  call    ?InternalRelease@?$ComPtr@UIMobileBroadbandDeviceInformation@NetworkOperators@Networking@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Networking::NetworkOperators::IMobileBroadbandDeviceInformation>::InternalRelease(void)
0x1800084a9  lea     rdx, [rbp+var_30]
0x1800084ad  mov     rcx, rdi
0x1800084b0  mov     rax, rbx
0x1800084b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800084b8  test    eax, eax
0x1800084ba  js      short loc_18000853A
0x1800084bc  mov     rbx, [rbp+var_30]
0x1800084c0  test    rbx, rbx
0x1800084c3  jz      short loc_18000853A
0x1800084c5  mov     rax, [rbx]
0x1800084c8  lea     rcx, [rbp+arg_18]
0x1800084cc  mov     rdi, [rax+38h]
0x1800084d0  call    ?InternalRelease@?$ComPtr@UIMobileBroadbandDeviceInformation@NetworkOperators@Networking@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Networking::NetworkOperators::IMobileBroadbandDeviceInformation>::InternalRelease(void)
0x1800084d5  lea     rdx, [rbp+arg_18]
0x1800084d9  mov     rcx, rbx
0x1800084dc  mov     rax, rdi
0x1800084df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800084e4  mov     ebx, eax
0x1800084e6  test    eax, eax
0x1800084e8  js      short loc_18000854E
0x1800084ea  mov     rcx, [rbp+arg_18]
0x1800084ee  lea     rdx, [rbp+var_20]
0x1800084f2  mov     rax, [rcx]
0x1800084f5  mov     rax, [rax+48h]
0x1800084f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800084fe  mov     ebx, eax
0x180008500  test    eax, eax
0x180008502  js      short loc_18000854E
0x180008504  mov     rcx, [rbp+var_20]; string
0x180008508  lea     rdx, [rbp+length]; length
0x18000850c  call    cs:__imp_WindowsGetStringRawBuffer
0x180008513  nop     dword ptr [rax+rax+00h]
0x180008518  mov     r8, rax
0x18000851b  test    rax, rax
0x18000851e  jnz     short loc_180008527
0x180008520  mov     ebx, 8000FFFFh
0x180008525  jmp     short loc_18000854E
0x180008527  mov     eax, [rbp+length]
0x18000852a  cmp     eax, esi
0x18000852c  jnb     short loc_180008533
0x18000852e  lea     edx, [rax+1]
0x180008531  jmp     short loc_180008544
0x180008533  mov     ebx, 8007007Ah
0x180008538  jmp     short loc_18000854E
0x18000853a  mov     rdx, rsi; unsigned __int64
0x18000853d  lea     r8, aNotPresent; "Not Present"
0x180008544  mov     rcx, r14; unsigned __int16 *
0x180008547  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000854c  mov     ebx, eax
0x18000854e  mov     rcx, [rbp+var_20]; string
0x180008552  call    cs:__imp_WindowsDeleteString
0x180008559  nop     dword ptr [rax+rax+00h]
0x18000855e  lea     rcx, [rbp+arg_18]
0x180008562  call    ?InternalRelease@?$ComPtr@UIMobileBroadbandDeviceInformation@NetworkOperators@Networking@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Networking::NetworkOperators::IMobileBroadbandDeviceInformation>::InternalRelease(void)
0x180008567  lea     rcx, [rbp+var_30]
0x18000856b  call    ?InternalRelease@?$ComPtr@UIMobileBroadbandDeviceInformation@NetworkOperators@Networking@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Networking::NetworkOperators::IMobileBroadbandDeviceInformation>::InternalRelease(void)
0x180008570  lea     rcx, [rbp+var_28]
0x180008574  call    ?InternalRelease@?$ComPtr@UIMobileBroadbandDeviceInformation@NetworkOperators@Networking@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Networking::NetworkOperators::IMobileBroadbandDeviceInformation>::InternalRelease(void)
0x180008579  lea     rcx, [rbp+var_10]; this
0x18000857d  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x180008582  mov     rsi, [rsp+50h+arg_8]
0x180008587  mov     eax, ebx
0x180008589  mov     rbx, [rsp+50h+arg_0]
0x18000858e  add     rsp, 50h
0x180008592  pop     r14
0x180008594  pop     rdi
0x180008595  pop     rbp
0x180008596  retn
```
