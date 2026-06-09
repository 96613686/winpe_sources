# MdmHttpWrapper::MdmSendRequestToCS(ushort const *,ushort const *,ushort const *,ushort const *,Windows::Data::Json::IJsonObject *,ushort * *,ulong *)

- ea: `0x180010b0c`
- end: `0x180010f89`
- name: `?MdmSendRequestToCS@MdmHttpWrapper@@SAJPEBG000PEAUIJsonObject@Json@Data@Windows@@PEAPEAGPEAK@Z`
- size: `1149`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, struct Windows::Data::Json::IJsonObject *, unsigned __int16 **, unsigned int *)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x180005550`

## callees

- `0x180001520`
- `0x180001544`
- `0x1800028e4`
- `0x180002de4`
- `0x180006548`
- `0x18000b88c`
- `0x180010b0c`
- `0x18001d51c`
- `0x18001f010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180010d5e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180010d5e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180010d04`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180010f35`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180010d04`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180010f35`

## string_xrefs

- `0x180010bd2`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmhttpwrapper.cpp`
- `0x180010d42`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmhttpwrapper.cpp`
- `0x180010dea`: `CHR(CreateHttpRequest(pMdmTransport.GetAddressOf()))`
- `0x180010bfe`: `CPR(pwszPath)`
- `0x180010cd7`: `CHR(pRequestJsonObjectLocal.As(&pRequestJsonObjectAsValue))`
- `0x180010d2e`: `CHR(pRequestJsonObjectAsValue->Stringify(hstrBody.GetAddressOf()))`
- `0x180010e86`: `CHR(pMdmTransport->SendRequestToCommandService( pwszMethod, pwszPath, pwszMainTicket, pwszSecondaryTicket, wstrRequestBody, &dwHttpStatus, fReadResponse ? &pwszBuffer : nullptr ))`

## pseudocode

```c
__int64 __fastcall MdmHttpWrapper::MdmSendRequestToCS(
        const unsigned __int16 *a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        struct Windows::Data::Json::IJsonObject *a5,
        unsigned __int16 **a6,
        unsigned int *a7)
{
  const unsigned __int16 *v7; // rsi
  struct Windows::Data::Json::IJsonObject *v8; // rbx
  int v9; // r8d
  int v10; // edi
  int v11; // r13d
  __int64 (__fastcall *v12)(struct Windows::Data::Json::IJsonObject *, GUID *, __int64 *); // rsi
  __int64 v13; // rcx
  __int64 v14; // rsi
  __int64 (__fastcall *v15)(__int64, HSTRING *); // rdi
  int v16; // eax
  int v17; // edx
  int v18; // ecx
  PCWSTR StringRawBuffer; // rax
  __int64 v20; // r8
  unsigned __int64 v21; // rdx
  __int128 *v22; // rsi
  __int64 v23; // rdi
  unsigned int v24; // eax
  __int64 v25; // rcx
  __int64 v27; // [rsp+0h] [rbp-108h] BYREF
  __int64 v28; // [rsp+20h] [rbp-E8h]
  const char *v29; // [rsp+28h] [rbp-E0h]
  unsigned int v30; // [rsp+50h] [rbp-B8h] BYREF
  __int64 v31; // [rsp+58h] [rbp-B0h] BYREF
  HSTRING string; // [rsp+60h] [rbp-A8h] BYREF
  void *v33; // [rsp+68h] [rbp-A0h] BYREF
  const unsigned __int16 *v34; // [rsp+70h] [rbp-98h]
  struct IMdmTransport *v35; // [rsp+78h] [rbp-90h] BYREF
  struct Windows::Data::Json::IJsonObject *v36; // [rsp+80h] [rbp-88h]
  const unsigned __int16 *v37; // [rsp+88h] [rbp-80h]
  const unsigned __int16 *v38; // [rsp+90h] [rbp-78h]
  const unsigned __int16 *v39; // [rsp+98h] [rbp-70h]
  __int128 v40; // [rsp+A0h] [rbp-68h] BYREF
  unsigned __int64 v41; // [rsp+B0h] [rbp-58h]
  unsigned __int64 v42; // [rsp+B8h] [rbp-50h]

  v37 = a4;
  v38 = a3;
  v7 = a2;
  v34 = a2;
  v39 = a1;
  v40 = 0;
  v41 = 0;
  v42 = 7;
  LOWORD(v40) = 0;
  v35 = 0;
  v30 = 0;
  string = 0;
  v33 = 0;
  v8 = 0;
  v36 = 0;
  v31 = 0;
  if ( !a1 )
  {
    v9 = -2147024809;
    v10 = -2147024809;
    if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) == 0 )
      goto LABEL_50;
    v29 = "CPR(pwszMethod)";
    LODWORD(v28) = 456;
    goto LABEL_4;
  }
  if ( !a2 )
  {
    v10 = -2147024809;
    if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) == 0 )
      goto LABEL_50;
    McTemplateU0dsqs_EventWriteTransfer(
      (_DWORD)a1,
      0,
      -2147024809,
      (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmhttpwrapper.cpp",
      201,
      "CPR(pwszPath)");
    goto LABEL_48;
  }
  v11 = 0;
  if ( a7 )
    *a7 = 0;
  if ( a6 )
  {
    if ( *a6 )
    {
      v10 = -2147024809;
      if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) == 0 )
        goto LABEL_50;
      McTemplateU0dsqs_EventWriteTransfer(
        (_DWORD)a1,
        (_DWORD)a2,
        -2147024809,
        (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmhttpwrapper.cpp",
        210,
        "CBR(*ppwszBuffer == nullptr)");
      goto LABEL_48;
    }
    v11 = 1;
  }
  if ( a5 )
  {
    (*(void (__fastcall **)(struct Windows::Data::Json::IJsonObject *))(*(_QWORD *)a5 + 8LL))(a5);
    v8 = a5;
    v36 = a5;
    v12 = **(__int64 (__fastcall ***)(struct Windows::Data::Json::IJsonObject *, GUID *, __int64 *))a5;
    v13 = v31;
    if ( v31 )
    {
      v31 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
    }
    v10 = v12(a5, &GUID_a3219ecb_f0b3_4dcd_beee_19d48cd3ed1e, &v31);
    if ( v10 < 0 )
    {
      if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) == 0 )
        goto LABEL_48;
      v29 = "CHR(pRequestJsonObjectLocal.As(&pRequestJsonObjectAsValue))";
      LODWORD(v28) = 473;
      goto LABEL_21;
    }
    v14 = v31;
    v15 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v31 + 56LL);
    WindowsDeleteString(string);
    if ( __eh34_try(-1, 0) )
    {
      __eh34_scope_strut(0);
      string = 0;
      v16 = v15(v14, &string);
    }
    if ( __eh34_catch(0) )
    {
      if ( __eh34_catch_type(0, &std::bad_alloc `RTTI Type Descriptor', 0) )
      {
        LODWORD(v34) = -2147024882;
        if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
          McTemplateU0dsqs_EventWriteTransfer(
            v18,
            (unsigned int)&v27,
            -2147024882,
            (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmhttpwrapper.cpp",
            226,
            "CHR(((HRESULT)0x8007000EL))");
        v10 = (int)v34;
        v8 = v36;
        __eh34_try_continuation(0, &std::bad_alloc `RTTI Type Descriptor', &loc_180010E03);
        goto LABEL_48;
      }
    }
    v10 = v16;
    if ( v16 < 0 )
    {
      if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
        McTemplateU0dsqs_EventWriteTransfer(
          v18,
          v17,
          v16,
          (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmhttpwrapper.cpp",
          221,
          "CHR(pRequestJsonObjectAsValue->Stringify(hstrBody.GetAddressOf()))");
      goto LABEL_48;
    }
    StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
    v21 = -1;
    do
      ++v21;
    while ( StringRawBuffer[v21] );
    if ( v21 > v42 )
    {
      std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(
        (char **)&v40,
        v21,
        v20,
        StringRawBuffer);
    }
    else
    {
      v22 = &v40;
      if ( v42 > 7 )
        v22 = (__int128 *)v40;
      v41 = v21;
      v23 = 2 * v21;
      memmove_0(v22, StringRawBuffer, 2 * v21);
      *(_WORD *)((char *)v22 + v23) = 0;
    }
    v7 = v34;
  }
  v10 = CreateHttpRequest(&v35, (int)a2);
  if ( v10 < 0 )
  {
    if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) == 0 )
      goto LABEL_48;
    v29 = "CHR(CreateHttpRequest(pMdmTransport.GetAddressOf()))";
    LODWORD(v28) = 486;
    goto LABEL_21;
  }
  v10 = (*(__int64 (__fastcall **)(struct IMdmTransport *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, __int128 *, unsigned int *, unsigned __int64))(*(_QWORD *)v35 + 24LL))(
          v35,
          v39,
          v7,
          v38,
          v37,
          &v40,
          &v30,
          (unsigned __int64)&v33 & -(__int64)(v11 != 0));
  if ( v10 < 0 )
  {
    if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) == 0 )
      goto LABEL_48;
    v29 = "CHR(pMdmTransport->SendRequestToCommandService( pwszMethod, pwszPath, pwszMainTicket, pwszSecondaryTicket, wst"
          "rRequestBody, &dwHttpStatus, fReadResponse ? &pwszBuffer : nullptr ))";
    LODWORD(v28) = 495;
LABEL_21:
    v9 = v10;
LABEL_4:
    McTemplateU0dsqs_EventWriteTransfer(
      (_DWORD)a1,
      (_DWORD)a2,
      v9,
      (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmhttpwrapper.cpp",
      v28,
      v29);
    goto LABEL_48;
  }
  v24 = v30;
  if ( a7 )
    *a7 = v30;
  if ( v24 - 200 <= 0x63 )
  {
    if ( v11 )
    {
      *a6 = (unsigned __int16 *)v33;
      v33 = 0;
    }
    goto LABEL_48;
  }
  v10 = -2147467259;
  if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
  {
    v29 = "CHR(((HRESULT)0x80004005L))";
    LODWORD(v28) = 504;
    goto LABEL_21;
  }
LABEL_48:
  if ( v33 )
    operator delete(v33);
LABEL_50:
  v25 = v31;
  if ( v31 )
  {
    v31 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
  }
  if ( v8 )
    (*(void (__fastcall **)(struct Windows::Data::Json::IJsonObject *))(*(_QWORD *)v8 + 16LL))(v8);
  WindowsDeleteString(string);
  string = 0;
  if ( v35 )
    (*(void (__fastcall **)(struct IMdmTransport *))(*(_QWORD *)v35 + 16LL))(v35);
  std::wstring::~wstring((char **)&v40);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x180010b0c  mov     r11, rsp
0x180010b0f  push    rbx
0x180010b10  push    rsi
0x180010b11  push    rdi
0x180010b12  push    r12
0x180010b14  push    r13
0x180010b16  push    r14
0x180010b18  push    r15
0x180010b1a  sub     rsp, 0D0h
0x180010b21  mov     rax, cs:__security_cookie
0x180010b28  xor     rax, rsp
0x180010b2b  mov     [rsp+108h+var_48], rax
0x180010b33  mov     [rsp+108h+var_80], r9
0x180010b3b  mov     [rsp+108h+var_78], r8
0x180010b43  mov     rsi, rdx
0x180010b46  mov     [rsp+108h+var_98], rdx
0x180010b4b  mov     [rsp+108h+var_70], rcx
0x180010b53  mov     r12, [rsp+108h+arg_28]
0x180010b5b  mov     r15, [rsp+108h+arg_30]
0x180010b63  xorps   xmm0, xmm0
0x180010b66  movups  xmmword ptr [r11-68h], xmm0
0x180010b6b  xor     r14d, r14d
0x180010b6e  mov     [r11-58h], r14
0x180010b72  mov     qword ptr [r11-50h], 7
0x180010b7a  mov     [r11-68h], r14w
0x180010b7f  mov     [rsp+108h+var_90], r14
0x180010b84  mov     [rsp+108h+var_B8], r14d
0x180010b89  mov     [rsp+108h+string], r14
0x180010b8e  mov     [rsp+108h+var_A0], r14
0x180010b93  mov     ebx, r14d
0x180010b96  mov     [rsp+108h+var_88], rbx
0x180010b9e  mov     [rsp+108h+var_B0], r14
0x180010ba3  test    rcx, rcx
0x180010ba6  jnz     short loc_180010BE3
0x180010ba8  mov     r8d, 80070057h
0x180010bae  mov     edi, r8d
0x180010bb1  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x180010bb8  jz      loc_180010EFF
0x180010bbe  lea     rax, aCprPwszmethod; "CPR(pwszMethod)"
0x180010bc5  mov     [rsp+108h+var_E0], rax
0x180010bca  mov     dword ptr [rsp+108h+var_E8], 1C8h
0x180010bd2  lea     r9, aOnecoreuapShel_7; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x180010bd9  call    McTemplateU0dsqs_EventWriteTransfer
0x180010bde  jmp     loc_180010EEF
0x180010be3  test    rdx, rdx
0x180010be6  jnz     short loc_180010C14
0x180010be8  mov     r8d, 80070057h
0x180010bee  mov     edi, r8d
0x180010bf1  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x180010bf8  jz      loc_180010EFF
0x180010bfe  lea     rax, aCprPwszpath; "CPR(pwszPath)"
0x180010c05  mov     [rsp+108h+var_E0], rax
0x180010c0a  mov     dword ptr [rsp+108h+var_E8], 1C9h
0x180010c12  jmp     short loc_180010BD2
0x180010c14  mov     r13d, r14d
0x180010c17  test    r15, r15
0x180010c1a  jz      short loc_180010C1F
0x180010c1c  mov     [r15], r14d
0x180010c1f  test    r12, r12
0x180010c22  jz      short loc_180010C5F
0x180010c24  cmp     [r12], r14
0x180010c28  jz      short loc_180010C59
0x180010c2a  mov     r8d, 80070057h
0x180010c30  mov     edi, r8d
0x180010c33  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x180010c3a  jz      loc_180010EFF
0x180010c40  lea     rax, aCbrPpwszbuffer; "CBR(*ppwszBuffer == nullptr)"
0x180010c47  mov     [rsp+108h+var_E0], rax
0x180010c4c  mov     dword ptr [rsp+108h+var_E8], 1D2h
0x180010c54  jmp     loc_180010BD2
0x180010c59  mov     r13d, 1
0x180010c5f  mov     rdi, [rsp+108h+arg_20]
0x180010c67  test    rdi, rdi
0x180010c6a  jz      loc_180010DCD
0x180010c70  mov     rax, [rdi]
0x180010c73  mov     rcx, rdi
0x180010c76  mov     rax, [rax+8]
0x180010c7a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010c7f  nop
0x180010c80  mov     rbx, rdi
0x180010c83  mov     [rsp+108h+var_88], rbx
0x180010c8b  mov     rax, [rdi]
0x180010c8e  mov     rsi, [rax]
0x180010c91  mov     rcx, [rsp+108h+var_B0]
0x180010c96  test    rcx, rcx
0x180010c99  jz      short loc_180010CAD
0x180010c9b  mov     [rsp+108h+var_B0], r14
0x180010ca0  mov     rax, [rcx]
0x180010ca3  mov     rax, [rax+10h]
0x180010ca7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010cac  nop
0x180010cad  lea     r8, [rsp+108h+var_B0]
0x180010cb2  lea     rdx, _GUID_a3219ecb_f0b3_4dcd_beee_19d48cd3ed1e
0x180010cb9  mov     rcx, rdi
0x180010cbc  mov     rax, rsi
0x180010cbf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010cc4  mov     edi, eax
0x180010cc6  test    eax, eax
0x180010cc8  jns     short loc_180010CF3
0x180010cca  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x180010cd1  jz      loc_180010EEF
0x180010cd7  lea     rax, aChrPrequestjso_0; "CHR(pRequestJsonObjectLocal.As(&pReques"...
0x180010cde  mov     [rsp+108h+var_E0], rax
0x180010ce3  mov     dword ptr [rsp+108h+var_E8], 1D9h
0x180010ceb  mov     r8d, edi
0x180010cee  jmp     loc_180010BD2
0x180010cf3  mov     rsi, [rsp+108h+var_B0]
0x180010cf8  mov     rax, [rsi]
0x180010cfb  mov     rdi, [rax+38h]
0x180010cff  mov     rcx, [rsp+108h+string]; string
0x180010d04  call    cs:__imp_WindowsDeleteString
0x180010d0a  mov     [rsp+108h+string], r14
0x180010d0f  lea     rdx, [rsp+108h+string]
0x180010d14  mov     rcx, rsi
0x180010d17  mov     rax, rdi
0x180010d1a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010d1f  mov     edi, eax
0x180010d21  test    eax, eax
0x180010d23  jns     short loc_180010D57
0x180010d25  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x180010d2c  jz      short loc_180010D52
0x180010d2e  lea     rax, aChrPrequestjso; "CHR(pRequestJsonObjectAsValue->Stringif"...
0x180010d35  mov     [rsp+108h+var_E0], rax
0x180010d3a  mov     dword ptr [rsp+108h+var_E8], 1DDh
0x180010d42  lea     r9, aOnecoreuapShel_7; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x180010d49  mov     r8d, edi
0x180010d4c  call    McTemplateU0dsqs_EventWriteTransfer
0x180010d51  nop
0x180010d52  jmp     loc_180010EEF
0x180010d57  xor     edx, edx; length
0x180010d59  mov     rcx, [rsp+108h+string]; string
0x180010d5e  call    cs:__imp_WindowsGetStringRawBuffer
0x180010d64  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180010d68  inc     rdx
0x180010d6b  cmp     [rax+rdx*2], r14w
0x180010d70  jnz     short loc_180010D68
0x180010d72  cmp     rdx, [rsp+108h+var_50]
0x180010d7a  ja      short loc_180010DB7
0x180010d7c  lea     rsi, [rsp+108h+var_68]
0x180010d84  cmp     [rsp+108h+var_50], 7
0x180010d8d  cmova   rsi, qword ptr [rsp+108h+var_68]
0x180010d96  mov     [rsp+108h+var_58], rdx
0x180010d9e  lea     rdi, [rdx+rdx]
0x180010da2  mov     r8, rdi; Size
0x180010da5  mov     rdx, rax; Src
0x180010da8  mov     rcx, rsi; void *
0x180010dab  call    memmove_0
0x180010db0  mov     [rdi+rsi], r14w
0x180010db5  jmp     short loc_180010DC8
0x180010db7  mov     r9, rax
0x180010dba  lea     rcx, [rsp+108h+var_68]
0x180010dc2  call    ??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z; std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)
0x180010dc7  nop
0x180010dc8  mov     rsi, [rsp+108h+var_98]
0x180010dcd  lea     rcx, [rsp+108h+var_90]; struct IMdmTransport **
0x180010dd2  call    ?CreateHttpRequest@@YAJPEAPEAUIMdmTransport@@@Z; CreateHttpRequest(IMdmTransport * *)
0x180010dd7  mov     edi, eax
0x180010dd9  test    eax, eax
0x180010ddb  jns     short loc_180010E17
0x180010ddd  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x180010de4  jz      loc_180010EEF
0x180010dea  lea     rax, aChrCreatehttpr; "CHR(CreateHttpRequest(pMdmTransport.Get"...
0x180010df1  mov     [rsp+108h+var_E0], rax
0x180010df6  mov     dword ptr [rsp+108h+var_E8], 1E6h
0x180010dfe  jmp     loc_180010CEB
0x180010e03  xor     r14d, r14d
0x180010e06  mov     edi, dword ptr [rsp+108h+var_98]
0x180010e0a  mov     rbx, [rsp+108h+var_88]
0x180010e12  jmp     loc_180010EEF
0x180010e17  mov     r11, [rsp+108h+var_90]
0x180010e1c  mov     r10, [r11]
0x180010e1f  mov     eax, r13d
0x180010e22  neg     eax
0x180010e24  sbb     rcx, rcx
0x180010e27  lea     rax, [rsp+108h+var_A0]
0x180010e2c  and     rcx, rax
0x180010e2f  mov     [rsp+108h+var_D0], rcx
0x180010e34  lea     rax, [rsp+108h+var_B8]
0x180010e39  mov     [rsp+108h+var_D8], rax
0x180010e3e  lea     rax, [rsp+108h+var_68]
0x180010e46  mov     [rsp+108h+var_E0], rax
0x180010e4b  mov     rax, [rsp+108h+var_80]
0x180010e53  mov     [rsp+108h+var_E8], rax
0x180010e58  mov     r9, [rsp+108h+var_78]
0x180010e60  mov     r8, rsi
0x180010e63  mov     rdx, [rsp+108h+var_70]
0x180010e6b  mov     rcx, r11
0x180010e6e  mov     rax, [r10+18h]
0x180010e72  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010e77  mov     edi, eax
0x180010e79  test    eax, eax
0x180010e7b  jns     short loc_180010E9F
0x180010e7d  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x180010e84  jz      short loc_180010EEF
0x180010e86  lea     rax, aChrPmdmtranspo_0; "CHR(pMdmTransport->SendRequestToCommand"...
0x180010e8d  mov     [rsp+108h+var_E0], rax
0x180010e92  mov     dword ptr [rsp+108h+var_E8], 1EFh
0x180010e9a  jmp     loc_180010CEB
0x180010e9f  mov     eax, [rsp+108h+var_B8]
0x180010ea3  test    r15, r15
0x180010ea6  jz      short loc_180010EAB
0x180010ea8  mov     [r15], eax
0x180010eab  add     eax, 0FFFFFF38h
0x180010eb0  cmp     eax, 63h ; 'c'
0x180010eb3  jbe     short loc_180010EDC
0x180010eb5  mov     edi, 80004005h
0x180010eba  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x180010ec1  jz      short loc_180010EEF
0x180010ec3  lea     rax, aChrHresult0x80_2; "CHR(((HRESULT)0x80004005L))"
0x180010eca  mov     [rsp+108h+var_E0], rax
0x180010ecf  mov     dword ptr [rsp+108h+var_E8], 1F8h
0x180010ed7  jmp     loc_180010CEB
0x180010edc  test    r13d, r13d
0x180010edf  jz      short loc_180010EEF
0x180010ee1  mov     rax, [rsp+108h+var_A0]
0x180010ee6  mov     [r12], rax
0x180010eea  mov     [rsp+108h+var_A0], r14
0x180010eef  mov     rcx, [rsp+108h+var_A0]; void *
0x180010ef4  test    rcx, rcx
0x180010ef7  jz      short loc_180010EFF
0x180010ef9  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180010efe  nop
0x180010eff  mov     rcx, [rsp+108h+var_B0]
0x180010f04  test    rcx, rcx
0x180010f07  jz      short loc_180010F1B
0x180010f09  mov     [rsp+108h+var_B0], r14
0x180010f0e  mov     rax, [rcx]
0x180010f11  mov     rax, [rax+10h]
0x180010f15  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010f1a  nop
0x180010f1b  test    rbx, rbx
0x180010f1e  jz      short loc_180010F30
0x180010f20  mov     rax, [rbx]
0x180010f23  mov     rcx, rbx
0x180010f26  mov     rax, [rax+10h]
0x180010f2a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010f2f  nop
0x180010f30  mov     rcx, [rsp+108h+string]; string
0x180010f35  call    cs:__imp_WindowsDeleteString
0x180010f3b  mov     [rsp+108h+string], r14
0x180010f40  mov     rcx, [rsp+108h+var_90]
0x180010f45  test    rcx, rcx
0x180010f48  jz      short loc_180010F57
0x180010f4a  mov     rax, [rcx]
0x180010f4d  mov     rax, [rax+10h]
0x180010f51  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010f56  nop
0x180010f57  lea     rcx, [rsp+108h+var_68]
0x180010f5f  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180010f64  mov     eax, edi
0x180010f66  mov     rcx, [rsp+108h+var_48]
0x180010f6e  xor     rcx, rsp; StackCookie
0x180010f71  call    __security_check_cookie
0x180010f76  add     rsp, 0D0h
0x180010f7d  pop     r15
0x180010f7f  pop     r14
0x180010f81  pop     r13
0x180010f83  pop     r12
0x180010f85  pop     rdi
0x180010f86  pop     rsi
0x180010f87  pop     rbx
0x180010f88  retn
```
