# InitiateSessionAsDeviceAsyncWithAlerts(ushort const *,int,Windows::Internal::Management::Provision::DeviceManagementAlertInformation *,Windows::Internal::Management::Provision::DeviceManagementInitiationInformation)

- ea: `0x140012964`
- end: `0x140012c22`
- name: `?InitiateSessionAsDeviceAsyncWithAlerts@@YAJPEBGHPEAUDeviceManagementAlertInformation@Provision@Management@Internal@Windows@@UDeviceManagementInitiationInformation@2345@@Z`
- size: `702`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140019a6c`

## callees

- `0x1400042f0`
- `0x1400095b4`
- `0x14000ae80`
- `0x14000b604`
- `0x140012964`
- `0x14005d010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x140012a17`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x140012a95`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x140012a17`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x140012a95`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1400129fe`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x140012aa8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1400129fe`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x140012aa8`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x1400129d5`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x140012b52`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x140012bf7`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x1400129d5`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x140012b52`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x140012bf7`
- `api-ms-win-core-winrt-l1-1-0!RoInitialize` at `0x1400129aa`
- `api-ms-win-core-winrt-l1-1-0!RoInitialize` at `0x1400129aa`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall InitiateSessionAsDeviceAsyncWithAlerts(const WCHAR *a1, __int64 a2, int a3, __int64 a4)
{
  int v7; // eax
  unsigned int v8; // edi
  int v10; // eax
  __int64 v11; // rcx
  unsigned __int64 v12; // rdi
  __int64 v13; // rdi
  __int64 (__fastcall *v14)(__int64, HSTRING, __int64, __int64); // rsi
  int (__fastcall ***v15)(_QWORD, GUID *, __int64 *); // rcx
  int v16; // eax
  int v17; // edx
  void **v18; // r8
  unsigned int v19; // ebx
  int (__fastcall ***v20)(_QWORD, GUID *, __int64 *); // rcx
  __int64 v21; // rcx
  int v22; // eax
  int (__fastcall ***v23)(_QWORD, GUID *, __int64 *); // rcx
  __int64 v24; // rcx
  int (__fastcall ***v25)(_QWORD, GUID *, __int64 *); // rcx
  __int64 v26; // rcx
  int v27; // [rsp+20h] [rbp-59h]
  char v28; // [rsp+40h] [rbp-39h] BYREF
  int (__fastcall ***v29)(_QWORD, GUID *, __int64 *); // [rsp+48h] [rbp-31h]
  __int64 v30[2]; // [rsp+50h] [rbp-29h] BYREF
  char v31; // [rsp+60h] [rbp-19h]
  HSTRING string; // [rsp+68h] [rbp-11h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+70h] [rbp-9h] BYREF
  HSTRING v34; // [rsp+88h] [rbp+Fh] BYREF
  HSTRING_HEADER v35; // [rsp+90h] [rbp+17h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+5Fh]

  v28 = 0;
  v30[1] = (__int64)&v28;
  v31 = 1;
  v7 = RoInitialize(1);
  v8 = v7;
  if ( v7 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x370,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollactivities\\exe\\main.cpp",
      (const char *)(unsigned int)v7,
      v27);
LABEL_3:
    if ( v28 )
      RoUninitialize();
    return v8;
  }
  v28 = 1;
  v30[0] = 0;
  if ( WindowsCreateStringReference(
         L"Windows.Internal.Management.Provision.SessionManager",
         0x34u,
         &hstringHeader,
         &string) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  v10 = Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Internal::Management::Provision::ISessionManager>>(
          (__int64)string,
          v30);
  v8 = v10;
  if ( v10 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x374,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollactivities\\exe\\main.cpp",
      (const char *)(unsigned int)v10,
      v27);
    v11 = v30[0];
    if ( v30[0] )
    {
      v30[0] = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
    }
    goto LABEL_3;
  }
  v29 = 0;
  v12 = -1;
  do
    ++v12;
  while ( a1[v12] );
  if ( v12 > 0xFFFFFFFF )
  {
    LODWORD(v12) = -1;
    RaiseException(0xC000000D, 1u, 0, 0);
  }
  WindowsCreateStringReference(a1, v12, &v35, &v34);
  v13 = v30[0];
  v14 = *(__int64 (__fastcall **)(__int64, HSTRING, __int64, __int64))(*(_QWORD *)v30[0] + 88LL);
  v15 = v29;
  if ( v29 )
  {
    v29 = 0;
    ((void (__fastcall *)(int (__fastcall ***)(_QWORD, GUID *, __int64 *)))(*v15)[2])(v15);
  }
  v16 = v14(v13, v34, a4, 1);
  v19 = v16;
  if ( v16 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x379,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollactivities\\exe\\main.cpp",
      (const char *)(unsigned int)v16,
      a3);
    v20 = v29;
    if ( v29 )
    {
      v29 = 0;
      ((void (__fastcall *)(int (__fastcall ***)(_QWORD, GUID *, __int64 *)))(*v20)[2])(v20);
    }
    v21 = v30[0];
    if ( v30[0] )
    {
      v30[0] = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
    }
LABEL_23:
    if ( v28 )
      RoUninitialize();
    return v19;
  }
  v22 = WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Management::Provision::SessionResult *>,Windows::Foundation::IAsyncOperation<Windows::Internal::Management::Provision::SessionResult *>>(
          v29,
          v17,
          v18);
  v19 = v22;
  if ( v22 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x37B,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollactivities\\exe\\main.cpp",
      (const char *)(unsigned int)v22,
      a3);
    v23 = v29;
    if ( v29 )
    {
      v29 = 0;
      ((void (__fastcall *)(int (__fastcall ***)(_QWORD, GUID *, __int64 *)))(*v23)[2])(v23);
    }
    v24 = v30[0];
    if ( v30[0] )
    {
      v30[0] = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
    }
    goto LABEL_23;
  }
  v25 = v29;
  if ( v29 )
  {
    v29 = 0;
    ((void (__fastcall *)(int (__fastcall ***)(_QWORD, GUID *, __int64 *)))(*v25)[2])(v25);
  }
  v26 = v30[0];
  if ( v30[0] )
  {
    v30[0] = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
  }
  if ( v28 )
    RoUninitialize();
  return 0;
}

```

## disassembly

```asm
0x140012964  mov     [rsp-8+arg_8], rbx
0x140012969  push    rbp
0x14001296a  push    rsi
0x14001296b  push    rdi
0x14001296c  push    r14
0x14001296e  push    r15
0x140012970  lea     rbp, [rsp-37h]
0x140012975  sub     rsp, 0B0h
0x14001297c  mov     rax, cs:__security_cookie
0x140012983  xor     rax, rsp
0x140012986  mov     [rbp+57h+var_28], rax
0x14001298a  mov     rbx, r9
0x14001298d  mov     r14, r8
0x140012990  mov     rsi, rcx
0x140012993  xor     r15d, r15d
0x140012996  mov     [rbp+57h+var_90], r15b
0x14001299a  lea     rax, [rbp+57h+var_90]
0x14001299e  mov     [rbp+57h+var_78], rax
0x1400129a2  mov     [rbp+57h+var_70], 1
0x1400129a6  lea     ecx, [r15+1]
0x1400129aa  call    cs:__imp_RoInitialize
0x1400129b0  mov     edi, eax
0x1400129b2  test    eax, eax
0x1400129b4  jns     short loc_1400129E2
0x1400129b6  mov     rcx, [rbp+5Fh]; this
0x1400129ba  mov     r9d, eax; char *
0x1400129bd  lea     r8, aOnecoreuapAdmi_12; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x1400129c4  mov     edx, 370h; void *
0x1400129c9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400129ce  nop
0x1400129cf  cmp     [rbp+57h+var_90], r15b
0x1400129d3  jz      short loc_1400129DB
0x1400129d5  call    cs:__imp_RoUninitialize
0x1400129db  mov     eax, edi
0x1400129dd  jmp     loc_140012BFF
0x1400129e2  mov     [rbp+57h+var_90], 1
0x1400129e6  mov     [rbp+57h+var_80], r15
0x1400129ea  lea     r9, [rbp+57h+string]; string
0x1400129ee  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x1400129f2  mov     edx, 34h ; '4'; length
0x1400129f7  lea     rcx, ?RuntimeClass_Windows_Internal_Management_Provision_SessionManager@@3QBGB; "Windows.Internal.Management.Provision.S"...
0x1400129fe  call    cs:__imp_WindowsCreateStringReference
0x140012a04  test    eax, eax
0x140012a06  jns     short loc_140012A1D
0x140012a08  xor     r9d, r9d; lpArguments
0x140012a0b  xor     r8d, r8d; nNumberOfArguments
0x140012a0e  lea     edx, [r9+1]; dwExceptionFlags
0x140012a12  mov     ecx, 0C000000Dh; dwExceptionCode
0x140012a17  call    cs:__imp_RaiseException
0x140012a1d  lea     rdx, [rbp+57h+var_80]
0x140012a21  mov     rcx, [rbp+57h+string]
0x140012a25  call    ??$ActivateInstance@V?$ComPtr@UISessionManager@Provision@Management@Internal@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UISessionManager@Provision@Management@Internal@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Internal::Management::Provision::ISessionManager>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Internal::Management::Provision::ISessionManager>>)
0x140012a2a  mov     edi, eax
0x140012a2c  test    eax, eax
0x140012a2e  jns     short loc_140012A68
0x140012a30  mov     rcx, [rbp+5Fh]; this
0x140012a34  mov     r9d, eax; char *
0x140012a37  lea     r8, aOnecoreuapAdmi_12; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x140012a3e  mov     edx, 374h; void *
0x140012a43  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140012a48  nop
0x140012a49  mov     rcx, [rbp+57h+var_80]
0x140012a4d  test    rcx, rcx
0x140012a50  jz      short loc_140012A63
0x140012a52  mov     [rbp+57h+var_80], r15
0x140012a56  mov     rax, [rcx]
0x140012a59  mov     rax, [rax+10h]
0x140012a5d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140012a62  nop
0x140012a63  jmp     loc_1400129CF
0x140012a68  mov     [rbp+57h+var_88], r15
0x140012a6c  or      rdi, 0FFFFFFFFFFFFFFFFh
0x140012a70  inc     rdi
0x140012a73  cmp     [rsi+rdi*2], r15w
0x140012a78  jnz     short loc_140012A70
0x140012a7a  mov     eax, 0FFFFFFFFh
0x140012a7f  cmp     rdi, rax
0x140012a82  jbe     short loc_140012A9B
0x140012a84  mov     edi, eax
0x140012a86  xor     r9d, r9d; lpArguments
0x140012a89  xor     r8d, r8d; nNumberOfArguments
0x140012a8c  lea     edx, [r9+1]; dwExceptionFlags
0x140012a90  mov     ecx, 0C000000Dh; dwExceptionCode
0x140012a95  call    cs:__imp_RaiseException
0x140012a9b  lea     r9, [rbp+57h+var_48]; string
0x140012a9f  lea     r8, [rbp+57h+var_40]; hstringHeader
0x140012aa3  mov     edx, edi; length
0x140012aa5  mov     rcx, rsi; sourceString
0x140012aa8  call    cs:__imp_WindowsCreateStringReference
0x140012aae  mov     rdi, [rbp+57h+var_80]
0x140012ab2  mov     rax, [rdi]
0x140012ab5  mov     rsi, [rax+58h]
0x140012ab9  mov     rcx, [rbp+57h+var_88]
0x140012abd  test    rcx, rcx
0x140012ac0  jz      short loc_140012AD3
0x140012ac2  mov     [rbp+57h+var_88], r15
0x140012ac6  mov     rax, [rcx]
0x140012ac9  mov     rax, [rax+10h]
0x140012acd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140012ad2  nop
0x140012ad3  lea     rax, [rbp+57h+var_88]
0x140012ad7  mov     [rsp+0D0h+var_A8], rax
0x140012adc  mov     qword ptr [rsp+0D0h+var_B0], r14; int
0x140012ae1  mov     r9d, 1
0x140012ae7  mov     r8, rbx
0x140012aea  mov     rdx, [rbp+57h+var_48]
0x140012aee  mov     rcx, rdi
0x140012af1  mov     rax, rsi
0x140012af4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140012af9  mov     ebx, eax
0x140012afb  test    eax, eax
0x140012afd  jns     short loc_140012B5F
0x140012aff  mov     rcx, [rbp+5Fh]; this
0x140012b03  mov     r9d, eax; char *
0x140012b06  lea     r8, aOnecoreuapAdmi_12; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x140012b0d  mov     edx, 379h; void *
0x140012b12  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140012b17  nop
0x140012b18  mov     rcx, [rbp+57h+var_88]
0x140012b1c  test    rcx, rcx
0x140012b1f  jz      short loc_140012B32
0x140012b21  mov     [rbp+57h+var_88], r15
0x140012b25  mov     rax, [rcx]
0x140012b28  mov     rax, [rax+10h]
0x140012b2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140012b31  nop
0x140012b32  mov     rcx, [rbp+57h+var_80]
0x140012b36  test    rcx, rcx
0x140012b39  jz      short loc_140012B4C
0x140012b3b  mov     [rbp+57h+var_80], r15
0x140012b3f  mov     rax, [rcx]
0x140012b42  mov     rax, [rax+10h]
0x140012b46  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140012b4b  nop
0x140012b4c  cmp     [rbp+57h+var_90], r15b
0x140012b50  jz      short loc_140012B58
0x140012b52  call    cs:__imp_RoUninitialize
0x140012b58  mov     eax, ebx
0x140012b5a  jmp     loc_140012BFF
0x140012b5f  mov     rcx, [rbp+57h+var_88]
0x140012b63  call    ??$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVSessionResult@Provision@Management@Internal@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVSessionResult@Provision@Management@Internal@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVSessionResult@Provision@Management@Internal@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z; WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Management::Provision::SessionResult *>,Windows::Foundation::IAsyncOperation<Windows::Internal::Management::Provision::SessionResult *>>(Windows::Foundation::IAsyncOperation<Windows::Internal::Management::Provision::SessionResult *> *,tagCOWAIT_FLAGS,void *)
0x140012b68  mov     ebx, eax
0x140012b6a  test    eax, eax
0x140012b6c  jns     short loc_140012BBD
0x140012b6e  mov     rcx, [rbp+5Fh]; this
0x140012b72  mov     r9d, eax; char *
0x140012b75  lea     r8, aOnecoreuapAdmi_12; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x140012b7c  mov     edx, 37Bh; void *
0x140012b81  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140012b86  nop
0x140012b87  mov     rcx, [rbp+57h+var_88]
0x140012b8b  test    rcx, rcx
0x140012b8e  jz      short loc_140012BA1
0x140012b90  mov     [rbp+57h+var_88], r15
0x140012b94  mov     rax, [rcx]
0x140012b97  mov     rax, [rax+10h]
0x140012b9b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140012ba0  nop
0x140012ba1  mov     rcx, [rbp+57h+var_80]
0x140012ba5  test    rcx, rcx
0x140012ba8  jz      short loc_140012BBB
0x140012baa  mov     [rbp+57h+var_80], r15
0x140012bae  mov     rax, [rcx]
0x140012bb1  mov     rax, [rax+10h]
0x140012bb5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140012bba  nop
0x140012bbb  jmp     short loc_140012B4C
0x140012bbd  mov     rcx, [rbp+57h+var_88]
0x140012bc1  test    rcx, rcx
0x140012bc4  jz      short loc_140012BD7
0x140012bc6  mov     [rbp+57h+var_88], r15
0x140012bca  mov     rax, [rcx]
0x140012bcd  mov     rax, [rax+10h]
0x140012bd1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140012bd6  nop
0x140012bd7  mov     rcx, [rbp+57h+var_80]
0x140012bdb  test    rcx, rcx
0x140012bde  jz      short loc_140012BF1
0x140012be0  mov     [rbp+57h+var_80], r15
0x140012be4  mov     rax, [rcx]
0x140012be7  mov     rax, [rax+10h]
0x140012beb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140012bf0  nop
0x140012bf1  cmp     [rbp+57h+var_90], r15b
0x140012bf5  jz      short loc_140012BFD
0x140012bf7  call    cs:__imp_RoUninitialize
0x140012bfd  xor     eax, eax
0x140012bff  mov     rcx, [rbp+57h+var_28]
0x140012c03  xor     rcx, rsp; StackCookie
0x140012c06  call    __security_check_cookie
0x140012c0b  mov     rbx, [rsp+0D0h+arg_8]
0x140012c13  add     rsp, 0B0h
0x140012c1a  pop     r15
0x140012c1c  pop     r14
0x140012c1e  pop     rdi
0x140012c1f  pop     rsi
0x140012c20  pop     rbp
0x140012c21  retn
```
