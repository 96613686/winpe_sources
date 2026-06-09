# InitiateSessionAsync(ushort const *,Windows::Internal::Management::Provision::DeviceManagementInitiationInformation,bool)

- ea: `0x140012c28`
- end: `0x140013290`
- name: `?InitiateSessionAsync@@YAJPEBGUDeviceManagementInitiationInformation@Provision@Management@Internal@Windows@@_N@Z`
- size: `1640`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140019a6c`

## callees

- `0x1400042f0`
- `0x140009140`
- `0x1400095b4`
- `0x14000ae80`
- `0x14000b604`
- `0x140012c28`
- `0x14005d010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x140012cdb`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x140012d59`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x140012cdb`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x140012d59`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x140012cc2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x140012d6c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x140012d97`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x140012cc2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x140012d6c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x140012d97`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x140012c99`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x14001325d`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x140012c99`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x14001325d`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x140012dd1`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x140012dd1`
- `api-ms-win-core-winrt-l1-1-0!RoInitialize` at `0x140012c6e`
- `api-ms-win-core-winrt-l1-1-0!RoInitialize` at `0x140012c6e`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
__int64 __fastcall InitiateSessionAsync(const WCHAR *a1, __int64 a2, char a3)
{
  int v6; // eax
  unsigned int v7; // edi
  int v9; // eax
  __int64 v10; // rcx
  unsigned __int64 v11; // rdi
  HRESULT StringReference; // eax
  int v13; // edx
  unsigned int v14; // r8d
  __int64 v15; // rdi
  __int64 v16; // rcx
  int ActivationFactory; // eax
  __int64 v18; // rcx
  __int64 v19; // rcx
  __int64 v20; // rcx
  int v21; // eax
  __int64 v22; // rcx
  __int64 v23; // rcx
  __int64 v24; // rcx
  __int64 v25; // rcx
  __int64 v26; // rdi
  __int64 (__fastcall *v27)(__int64, __int64, HSTRING, __int64); // rsi
  __int64 v28; // rcx
  int v29; // eax
  int v30; // edx
  void **v31; // r8
  unsigned int v32; // ebx
  __int64 v33; // rcx
  __int64 v34; // rcx
  __int64 v35; // rcx
  __int64 v36; // rcx
  __int64 v37; // rcx
  __int64 v38; // rcx
  int v39; // eax
  __int64 v40; // rcx
  __int64 v41; // rcx
  __int64 v42; // rdi
  __int64 (__fastcall *v43)(__int64, HSTRING, __int64, int *); // rsi
  __int64 v44; // rcx
  int v45; // eax
  __int64 v46; // rcx
  __int64 v47; // rcx
  int v48; // eax
  __int64 v49; // rcx
  __int64 v50; // rcx
  __int64 v51; // rcx
  int v52; // eax
  __int64 v53; // rcx
  __int64 v54; // rcx
  __int64 v55; // rcx
  __int64 v56; // rcx
  __int64 v57; // rcx
  __int64 v58; // rcx
  int *v59; // [rsp+20h] [rbp-69h]
  char v60; // [rsp+30h] [rbp-59h] BYREF
  int v61[2]; // [rsp+38h] [rbp-51h] BYREF
  __int64 v62; // [rsp+40h] [rbp-49h] BYREF
  __int64 v63; // [rsp+48h] [rbp-41h] BYREF
  __int64 v64; // [rsp+50h] [rbp-39h] BYREF
  __int64 v65; // [rsp+58h] [rbp-31h] BYREF
  unsigned int v66; // [rsp+60h] [rbp-29h] BYREF
  char *v67; // [rsp+68h] [rbp-21h]
  char v68; // [rsp+70h] [rbp-19h]
  HSTRING string; // [rsp+78h] [rbp-11h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+80h] [rbp-9h] BYREF
  HSTRING v71; // [rsp+98h] [rbp+Fh] BYREF
  HSTRING_HEADER v72; // [rsp+A0h] [rbp+17h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+5Fh]

  v60 = 0;
  v67 = &v60;
  v68 = 1;
  v6 = RoInitialize(1);
  v7 = v6;
  if ( v6 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x340,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollactivities\\exe\\main.cpp",
      (const char *)(unsigned int)v6,
      (int)v59);
LABEL_3:
    if ( v60 )
      RoUninitialize();
    return v7;
  }
  v60 = 1;
  v62 = 0;
  if ( WindowsCreateStringReference(
         L"Windows.Internal.Management.Provision.SessionManager",
         0x34u,
         &hstringHeader,
         &string) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  v9 = Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Internal::Management::Provision::ISessionManager>>(
         (__int64)string,
         &v62);
  v7 = v9;
  if ( v9 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x344,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollactivities\\exe\\main.cpp",
      (const char *)(unsigned int)v9,
      (int)v59);
    v10 = v62;
    if ( v62 )
    {
      v62 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
    }
    goto LABEL_3;
  }
  *(_QWORD *)v61 = 0;
  v11 = -1;
  do
    ++v11;
  while ( a1[v11] );
  if ( v11 > 0xFFFFFFFF )
  {
    LODWORD(v11) = -1;
    RaiseException(0xC000000D, 1u, 0, 0);
  }
  WindowsCreateStringReference(a1, v11, &v72, &v71);
  if ( !a3 )
  {
    v42 = v62;
    v43 = *(__int64 (__fastcall **)(__int64, HSTRING, __int64, int *))(*(_QWORD *)v62 + 80LL);
    v44 = *(_QWORD *)v61;
    if ( *(_QWORD *)v61 )
    {
      *(_QWORD *)v61 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v44 + 16LL))(v44);
    }
    v45 = v43(v42, v71, a2, v61);
    v32 = v45;
    if ( v45 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x356,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollactivities\\exe\\main.cpp",
        (const char *)(unsigned int)v45,
        (int)v59);
      v46 = *(_QWORD *)v61;
      if ( *(_QWORD *)v61 )
      {
        *(_QWORD *)v61 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v46 + 16LL))(v46);
      }
      v47 = v62;
      if ( v62 )
      {
        v62 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v47 + 16LL))(v47);
      }
      goto LABEL_90;
    }
    goto LABEL_54;
  }
  v63 = 0;
  *(_QWORD *)&hstringHeader.Reserved.Reserved2[16] = 0;
  StringReference = WindowsCreateStringReference(
                      L"Windows.System.User",
                      0x13u,
                      (HSTRING_HEADER *)&string,
                      (HSTRING *)&hstringHeader.Reserved.Reserved2[16]);
  if ( StringReference < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)StringReference, v13, v14);
    JUMPOUT(0x14001328FLL);
  }
  v15 = *(_QWORD *)&hstringHeader.Reserved.Reserved2[16];
  v16 = v63;
  if ( v63 )
  {
    v63 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
  }
  ActivationFactory = RoGetActivationFactory(v15, &GUID_74a37e11_2eb5_4487_b0d5_2c6790e013e9, &v63);
  v7 = ActivationFactory;
  if ( ActivationFactory < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x34D,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollactivities\\exe\\main.cpp",
      (const char *)(unsigned int)ActivationFactory,
      (int)v59);
    v18 = v63;
    if ( v63 )
    {
      v63 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
    }
    v19 = *(_QWORD *)v61;
    if ( *(_QWORD *)v61 )
    {
      *(_QWORD *)v61 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
    }
    v20 = v62;
    if ( v62 )
    {
      v62 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
    }
    goto LABEL_3;
  }
  v64 = 0;
  v21 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v63 + 48LL))(v63, &v64);
  v7 = v21;
  if ( v21 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x350,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollactivities\\exe\\main.cpp",
      (const char *)(unsigned int)v21,
      (int)v59);
    v22 = v64;
    if ( v64 )
    {
      v64 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
    }
    v23 = v63;
    if ( v63 )
    {
      v63 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
    }
    v24 = *(_QWORD *)v61;
    if ( *(_QWORD *)v61 )
    {
      *(_QWORD *)v61 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
    }
    v25 = v62;
    if ( v62 )
    {
      v62 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
    }
    goto LABEL_3;
  }
  v26 = v62;
  v27 = *(__int64 (__fastcall **)(__int64, __int64, HSTRING, __int64))(*(_QWORD *)v62 + 64LL);
  v28 = *(_QWORD *)v61;
  if ( *(_QWORD *)v61 )
  {
    *(_QWORD *)v61 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 16LL))(v28);
  }
  v59 = v61;
  v29 = v27(v26, v64, v71, a2);
  v32 = v29;
  if ( v29 >= 0 )
  {
    v37 = v64;
    if ( v64 )
    {
      v64 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v37 + 16LL))(v37);
    }
    v38 = v63;
    if ( v63 )
    {
      v63 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v38 + 16LL))(v38);
    }
LABEL_54:
    v39 = WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Management::Provision::SessionResult *>,Windows::Foundation::IAsyncOperation<Windows::Internal::Management::Provision::SessionResult *>>(
            *(int (__fastcall ****)(_QWORD, GUID *, __int64 *))v61,
            v30,
            v31);
    v32 = v39;
    if ( v39 >= 0 )
    {
      v65 = 0;
      v48 = (*(__int64 (__fastcall **)(_QWORD, __int64 *))(**(_QWORD **)v61 + 64LL))(*(_QWORD *)v61, &v65);
      v32 = v48;
      if ( v48 >= 0 )
      {
        v66 = 0;
        v52 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v65 + 64LL))(v65, &v66);
        v32 = v52;
        if ( v52 >= 0 )
        {
          v32 = v66;
          v56 = v65;
          if ( v65 )
          {
            v65 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v56 + 16LL))(v56);
          }
          v57 = *(_QWORD *)v61;
          if ( *(_QWORD *)v61 )
          {
            *(_QWORD *)v61 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v57 + 16LL))(v57);
          }
          v58 = v62;
          if ( v62 )
          {
            v62 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v58 + 16LL))(v58);
          }
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x360,
            (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollactivities\\exe\\main.cpp",
            (const char *)(unsigned int)v52,
            (int)v59);
          v53 = v65;
          if ( v65 )
          {
            v65 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v53 + 16LL))(v53);
          }
          v54 = *(_QWORD *)v61;
          if ( *(_QWORD *)v61 )
          {
            *(_QWORD *)v61 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v54 + 16LL))(v54);
          }
          v55 = v62;
          if ( v62 )
          {
            v62 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v55 + 16LL))(v55);
          }
        }
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x35D,
          (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollactivities\\exe\\main.cpp",
          (const char *)(unsigned int)v48,
          (int)v59);
        v49 = v65;
        if ( v65 )
        {
          v65 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v49 + 16LL))(v49);
        }
        v50 = *(_QWORD *)v61;
        if ( *(_QWORD *)v61 )
        {
          *(_QWORD *)v61 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v50 + 16LL))(v50);
        }
        v51 = v62;
        if ( v62 )
        {
          v62 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v51 + 16LL))(v51);
        }
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x359,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollactivities\\exe\\main.cpp",
        (const char *)(unsigned int)v39,
        (int)v59);
      v40 = *(_QWORD *)v61;
      if ( *(_QWORD *)v61 )
      {
        *(_QWORD *)v61 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v40 + 16LL))(v40);
      }
      v41 = v62;
      if ( v62 )
      {
        v62 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v41 + 16LL))(v41);
      }
    }
    goto LABEL_90;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x352,
    (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollactivities\\exe\\main.cpp",
    (const char *)(unsigned int)v29,
    (int)v61);
  v33 = v64;
  if ( v64 )
  {
    v64 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v33 + 16LL))(v33);
  }
  v34 = v63;
  if ( v63 )
  {
    v63 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v34 + 16LL))(v34);
  }
  v35 = *(_QWORD *)v61;
  if ( *(_QWORD *)v61 )
  {
    *(_QWORD *)v61 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v35 + 16LL))(v35);
  }
  v36 = v62;
  if ( v62 )
  {
    v62 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v36 + 16LL))(v36);
  }
LABEL_90:
  if ( v60 )
    RoUninitialize();
  return v32;
}

```

## disassembly

```asm
0x140012c28  mov     [rsp-8+arg_10], rbx
0x140012c2d  push    rbp
0x140012c2e  push    rsi
0x140012c2f  push    rdi
0x140012c30  push    r14
0x140012c32  push    r15
0x140012c34  lea     rbp, [rsp-37h]
0x140012c39  sub     rsp, 0C0h
0x140012c40  mov     rax, cs:__security_cookie
0x140012c47  xor     rax, rsp
0x140012c4a  mov     [rbp+57h+var_28], rax
0x140012c4e  mov     r14b, r8b
0x140012c51  mov     rbx, rdx
0x140012c54  mov     rsi, rcx
0x140012c57  xor     r15d, r15d
0x140012c5a  mov     [rbp+57h+var_B0], r15b
0x140012c5e  lea     rax, [rbp+57h+var_B0]
0x140012c62  mov     [rbp+57h+var_78], rax
0x140012c66  mov     [rbp+57h+var_70], 1
0x140012c6a  lea     ecx, [r15+1]
0x140012c6e  call    cs:__imp_RoInitialize
0x140012c74  mov     edi, eax
0x140012c76  test    eax, eax
0x140012c78  jns     short loc_140012CA6
0x140012c7a  mov     rcx, [rbp+5Fh]; this
0x140012c7e  mov     r9d, eax; char *
0x140012c81  lea     r8, aOnecoreuapAdmi_12; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x140012c88  mov     edx, 340h; void *
0x140012c8d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140012c92  nop
0x140012c93  cmp     [rbp+57h+var_B0], r15b
0x140012c97  jz      short loc_140012C9F
0x140012c99  call    cs:__imp_RoUninitialize
0x140012c9f  mov     eax, edi
0x140012ca1  jmp     loc_140013265
0x140012ca6  mov     [rbp+57h+var_B0], 1
0x140012caa  mov     [rbp+57h+var_A0], r15
0x140012cae  lea     r9, [rbp+57h+string]; string
0x140012cb2  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x140012cb6  mov     edx, 34h ; '4'; length
0x140012cbb  lea     rcx, ?RuntimeClass_Windows_Internal_Management_Provision_SessionManager@@3QBGB; "Windows.Internal.Management.Provision.S"...
0x140012cc2  call    cs:__imp_WindowsCreateStringReference
0x140012cc8  test    eax, eax
0x140012cca  jns     short loc_140012CE1
0x140012ccc  xor     r9d, r9d; lpArguments
0x140012ccf  xor     r8d, r8d; nNumberOfArguments
0x140012cd2  lea     edx, [r9+1]; dwExceptionFlags
0x140012cd6  mov     ecx, 0C000000Dh; dwExceptionCode
0x140012cdb  call    cs:__imp_RaiseException
0x140012ce1  lea     rdx, [rbp+57h+var_A0]
0x140012ce5  mov     rcx, [rbp+57h+string]
0x140012ce9  call    ??$ActivateInstance@V?$ComPtr@UISessionManager@Provision@Management@Internal@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UISessionManager@Provision@Management@Internal@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Internal::Management::Provision::ISessionManager>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Internal::Management::Provision::ISessionManager>>)
0x140012cee  mov     edi, eax
0x140012cf0  test    eax, eax
0x140012cf2  jns     short loc_140012D2C
0x140012cf4  mov     rcx, [rbp+5Fh]; this
0x140012cf8  mov     r9d, eax; char *
0x140012cfb  lea     r8, aOnecoreuapAdmi_12; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x140012d02  mov     edx, 344h; void *
0x140012d07  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140012d0c  nop
0x140012d0d  mov     rcx, [rbp+57h+var_A0]
0x140012d11  test    rcx, rcx
0x140012d14  jz      short loc_140012D27
0x140012d16  mov     [rbp+57h+var_A0], r15
0x140012d1a  mov     rax, [rcx]
0x140012d1d  mov     rax, [rax+10h]
0x140012d21  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140012d26  nop
0x140012d27  jmp     loc_140012C93
0x140012d2c  mov     qword ptr [rbp+57h+var_A8], r15
0x140012d30  or      rdi, 0FFFFFFFFFFFFFFFFh
0x140012d34  inc     rdi
0x140012d37  cmp     [rsi+rdi*2], r15w
0x140012d3c  jnz     short loc_140012D34
0x140012d3e  mov     eax, 0FFFFFFFFh
0x140012d43  cmp     rdi, rax
0x140012d46  jbe     short loc_140012D5F
0x140012d48  mov     edi, eax
0x140012d4a  xor     r9d, r9d; lpArguments
0x140012d4d  xor     r8d, r8d; nNumberOfArguments
0x140012d50  lea     edx, [r9+1]; dwExceptionFlags
0x140012d54  mov     ecx, 0C000000Dh; dwExceptionCode
0x140012d59  call    cs:__imp_RaiseException
0x140012d5f  lea     r9, [rbp+57h+var_48]; string
0x140012d63  lea     r8, [rbp+57h+var_40]; hstringHeader
0x140012d67  mov     edx, edi; length
0x140012d69  mov     rcx, rsi; sourceString
0x140012d6c  call    cs:__imp_WindowsCreateStringReference
0x140012d72  test    r14b, r14b
0x140012d75  jz      loc_14001305E
0x140012d7b  mov     [rbp+57h+var_98], r15
0x140012d7f  mov     qword ptr [rbp+57h+hstringHeader.Reserved+10h], r15
0x140012d83  lea     r9, [rbp+57h+hstringHeader.Reserved+10h]; string
0x140012d87  lea     r8, [rbp+57h+string]; hstringHeader
0x140012d8b  mov     edx, 13h; length
0x140012d90  lea     rcx, ?RuntimeClass_Windows_System_User@@3QBGB; "Windows.System.User"
0x140012d97  call    cs:__imp_WindowsCreateStringReference
0x140012d9d  test    eax, eax
0x140012d9f  js      loc_140013288
0x140012da5  mov     rdi, qword ptr [rbp+57h+hstringHeader.Reserved+10h]
0x140012da9  mov     rcx, [rbp+57h+var_98]
0x140012dad  test    rcx, rcx
0x140012db0  jz      short loc_140012DC3
0x140012db2  mov     [rbp+57h+var_98], r15
0x140012db6  mov     rax, [rcx]
0x140012db9  mov     rax, [rax+10h]
0x140012dbd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140012dc2  nop
0x140012dc3  lea     r8, [rbp+57h+var_98]
0x140012dc7  lea     rdx, _GUID_74a37e11_2eb5_4487_b0d5_2c6790e013e9
0x140012dce  mov     rcx, rdi
0x140012dd1  call    cs:__imp_RoGetActivationFactory
0x140012dd7  mov     edi, eax
0x140012dd9  test    eax, eax
0x140012ddb  jns     short loc_140012E49
0x140012ddd  mov     rcx, [rbp+5Fh]; this
0x140012de1  mov     r9d, eax; char *
0x140012de4  lea     r8, aOnecoreuapAdmi_12; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x140012deb  mov     edx, 34Dh; void *
0x140012df0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140012df5  nop
0x140012df6  mov     rcx, [rbp+57h+var_98]
0x140012dfa  test    rcx, rcx
0x140012dfd  jz      short loc_140012E10
0x140012dff  mov     [rbp+57h+var_98], r15
0x140012e03  mov     rax, [rcx]
0x140012e06  mov     rax, [rax+10h]
0x140012e0a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140012e0f  nop
0x140012e10  mov     rcx, qword ptr [rbp+57h+var_A8]
0x140012e14  test    rcx, rcx
0x140012e17  jz      short loc_140012E2A
0x140012e19  mov     qword ptr [rbp+57h+var_A8], r15
0x140012e1d  mov     rax, [rcx]
0x140012e20  mov     rax, [rax+10h]
0x140012e24  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140012e29  nop
0x140012e2a  mov     rcx, [rbp+57h+var_A0]
0x140012e2e  test    rcx, rcx
0x140012e31  jz      short loc_140012E44
0x140012e33  mov     [rbp+57h+var_A0], r15
0x140012e37  mov     rax, [rcx]
0x140012e3a  mov     rax, [rax+10h]
0x140012e3e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140012e43  nop
0x140012e44  jmp     loc_140012C93
0x140012e49  mov     [rbp+57h+var_90], r15
0x140012e4d  mov     rcx, [rbp+57h+var_98]
0x140012e51  mov     rax, [rcx]
0x140012e54  lea     rdx, [rbp+57h+var_90]
0x140012e58  mov     rax, [rax+30h]
0x140012e5c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140012e61  mov     edi, eax
0x140012e63  test    eax, eax
0x140012e65  jns     loc_140012EF1
0x140012e6b  mov     rcx, [rbp+5Fh]; this
0x140012e6f  mov     r9d, eax; char *
0x140012e72  lea     r8, aOnecoreuapAdmi_12; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x140012e79  mov     edx, 350h; void *
0x140012e7e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140012e83  nop
0x140012e84  mov     rcx, [rbp+57h+var_90]
0x140012e88  test    rcx, rcx
0x140012e8b  jz      short loc_140012E9E
0x140012e8d  mov     [rbp+57h+var_90], r15
0x140012e91  mov     rax, [rcx]
0x140012e94  mov     rax, [rax+10h]
0x140012e98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140012e9d  nop
0x140012e9e  mov     rcx, [rbp+57h+var_98]
0x140012ea2  test    rcx, rcx
0x140012ea5  jz      short loc_140012EB8
0x140012ea7  mov     [rbp+57h+var_98], r15
0x140012eab  mov     rax, [rcx]
0x140012eae  mov     rax, [rax+10h]
0x140012eb2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140012eb7  nop
0x140012eb8  mov     rcx, qword ptr [rbp+57h+var_A8]
0x140012ebc  test    rcx, rcx
0x140012ebf  jz      short loc_140012ED2
0x140012ec1  mov     qword ptr [rbp+57h+var_A8], r15
0x140012ec5  mov     rax, [rcx]
0x140012ec8  mov     rax, [rax+10h]
0x140012ecc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140012ed1  nop
0x140012ed2  mov     rcx, [rbp+57h+var_A0]
0x140012ed6  test    rcx, rcx
0x140012ed9  jz      short loc_140012EEC
0x140012edb  mov     [rbp+57h+var_A0], r15
0x140012edf  mov     rax, [rcx]
0x140012ee2  mov     rax, [rax+10h]
0x140012ee6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140012eeb  nop
0x140012eec  jmp     loc_140012C93
0x140012ef1  mov     rdi, [rbp+57h+var_A0]
0x140012ef5  mov     rax, [rdi]
0x140012ef8  mov     rsi, [rax+40h]
0x140012efc  mov     rcx, qword ptr [rbp+57h+var_A8]
0x140012f00  test    rcx, rcx
0x140012f03  jz      short loc_140012F16
0x140012f05  mov     qword ptr [rbp+57h+var_A8], r15
0x140012f09  mov     rax, [rcx]
0x140012f0c  mov     rax, [rax+10h]
0x140012f10  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140012f15  nop
0x140012f16  lea     rax, [rbp+57h+var_A8]
0x140012f1a  mov     qword ptr [rsp+0E0h+var_C0], rax; int
0x140012f1f  mov     r9, rbx
0x140012f22  mov     r8, [rbp+57h+var_48]
0x140012f26  mov     rdx, [rbp+57h+var_90]
0x140012f2a  mov     rcx, rdi
0x140012f2d  mov     rax, rsi
0x140012f30  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140012f35  mov     ebx, eax
0x140012f37  test    eax, eax
0x140012f39  jns     loc_140012FC5
0x140012f3f  mov     rcx, [rbp+5Fh]; this
0x140012f43  mov     r9d, eax; char *
0x140012f46  lea     r8, aOnecoreuapAdmi_12; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x140012f4d  mov     edx, 352h; void *
0x140012f52  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140012f57  nop
0x140012f58  mov     rcx, [rbp+57h+var_90]
0x140012f5c  test    rcx, rcx
0x140012f5f  jz      short loc_140012F72
0x140012f61  mov     [rbp+57h+var_90], r15
0x140012f65  mov     rax, [rcx]
0x140012f68  mov     rax, [rax+10h]
0x140012f6c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140012f71  nop
0x140012f72  mov     rcx, [rbp+57h+var_98]
0x140012f76  test    rcx, rcx
0x140012f79  jz      short loc_140012F8C
0x140012f7b  mov     [rbp+57h+var_98], r15
0x140012f7f  mov     rax, [rcx]
0x140012f82  mov     rax, [rax+10h]
0x140012f86  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140012f8b  nop
0x140012f8c  mov     rcx, qword ptr [rbp+57h+var_A8]
0x140012f90  test    rcx, rcx
0x140012f93  jz      short loc_140012FA6
0x140012f95  mov     qword ptr [rbp+57h+var_A8], r15
0x140012f99  mov     rax, [rcx]
0x140012f9c  mov     rax, [rax+10h]
0x140012fa0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140012fa5  nop
0x140012fa6  mov     rcx, [rbp+57h+var_A0]
0x140012faa  test    rcx, rcx
0x140012fad  jz      short loc_140012FC0
0x140012faf  mov     [rbp+57h+var_A0], r15
0x140012fb3  mov     rax, [rcx]
0x140012fb6  mov     rax, [rax+10h]
0x140012fba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140012fbf  nop
0x140012fc0  jmp     loc_140013257
0x140012fc5  mov     rcx, [rbp+57h+var_90]
0x140012fc9  test    rcx, rcx
0x140012fcc  jz      short loc_140012FDF
0x140012fce  mov     [rbp+57h+var_90], r15
0x140012fd2  mov     rax, [rcx]
0x140012fd5  mov     rax, [rax+10h]
0x140012fd9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140012fde  nop
0x140012fdf  mov     rcx, [rbp+57h+var_98]
0x140012fe3  test    rcx, rcx
0x140012fe6  jz      short loc_140012FF9
0x140012fe8  mov     [rbp+57h+var_98], r15
0x140012fec  mov     rax, [rcx]
0x140012fef  mov     rax, [rax+10h]
0x140012ff3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140012ff8  nop
0x140012ff9  mov     rcx, qword ptr [rbp+57h+var_A8]
0x140012ffd  call    ??$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVSessionResult@Provision@Management@Internal@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVSessionResult@Provision@Management@Internal@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVSessionResult@Provision@Management@Internal@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z; WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Management::Provision::SessionResult *>,Windows::Foundation::IAsyncOperation<Windows::Internal::Management::Provision::SessionResult *>>(Windows::Foundation::IAsyncOperation<Windows::Internal::Management::Provision::SessionResult *> *,tagCOWAIT_FLAGS,void *)
0x140013002  mov     ebx, eax
0x140013004  test    eax, eax
0x140013006  jns     loc_1400130F5
0x14001300c  mov     rcx, [rbp+5Fh]; this
0x140013010  mov     r9d, eax; char *
0x140013013  lea     r8, aOnecoreuapAdmi_12; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x14001301a  mov     edx, 359h; void *
0x14001301f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140013024  nop
0x140013025  mov     rcx, qword ptr [rbp+57h+var_A8]
0x140013029  test    rcx, rcx
0x14001302c  jz      short loc_14001303F
0x14001302e  mov     qword ptr [rbp+57h+var_A8], r15
0x140013032  mov     rax, [rcx]
0x140013035  mov     rax, [rax+10h]
0x140013039  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001303e  nop
0x14001303f  mov     rcx, [rbp+57h+var_A0]
0x140013043  test    rcx, rcx
0x140013046  jz      short loc_140013059
0x140013048  mov     [rbp+57h+var_A0], r15
0x14001304c  mov     rax, [rcx]
0x14001304f  mov     rax, [rax+10h]
0x140013053  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140013058  nop
0x140013059  jmp     loc_140013257
  ... truncated ...
```
