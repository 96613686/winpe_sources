# MdmHttpWrapper::MdmSendRequestToCSWithDelegation(ushort const *,ushort const *,ushort const *,ushort const *,Windows::Data::Json::IJsonObject *,ushort * *,ulong *)

- ea: `0x18001134c`
- end: `0x1800117dc`
- name: `?MdmSendRequestToCSWithDelegation@MdmHttpWrapper@@SAJPEBG000PEAUIJsonObject@Json@Data@Windows@@PEAPEAGPEAK@Z`
- size: `1168`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, struct Windows::Data::Json::IJsonObject *, unsigned __int16 **, unsigned int *)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x1800056c0`

## callees

- `0x180001520`
- `0x180001544`
- `0x1800028e4`
- `0x180002de8`
- `0x1800065c0`
- `0x18000bb9c`
- `0x18001134c`
- `0x18001dbfc`
- `0x18001f010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800115a4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800115a4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180011544`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180011781`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180011544`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180011781`

## string_xrefs

- `0x180011412`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmhttpwrapper.cpp`
- `0x180011588`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmhttpwrapper.cpp`
- `0x180011636`: `CHR(CreateHttpRequest(pMdmTransport.GetAddressOf()))`
- `0x18001143e`: `CPR(pwszPath)`
- `0x180011517`: `CHR(pRequestJsonObjectLocal.As(&pRequestJsonObjectAsValue))`
- `0x180011574`: `CHR(pRequestJsonObjectAsValue->Stringify(hstrBody.GetAddressOf()))`
- `0x1800116d2`: `CHR(pMdmTransport->SendDelegationRequestToCommandService( pwszMethod, pwszPath, pwszDeviceTicket, pwszDelegationTicket, wstrRequestBody, &dwHttpStatus, fReadResponse ? &pwszBuffer : nullptr ))`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
__int64 __fastcall MdmHttpWrapper::MdmSendRequestToCSWithDelegation(
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
  int v17; // ecx
  PCWSTR StringRawBuffer; // rax
  __int64 v19; // r8
  unsigned __int64 v20; // rdx
  __int128 *v21; // rsi
  __int64 v22; // rdi
  unsigned int v23; // eax
  __int64 v24; // rcx
  _BYTE v26[32]; // [rsp+0h] [rbp-108h] BYREF
  __int64 v27; // [rsp+20h] [rbp-E8h]
  const char *v28; // [rsp+28h] [rbp-E0h]
  unsigned int v29; // [rsp+50h] [rbp-B8h] BYREF
  __int64 v30; // [rsp+58h] [rbp-B0h] BYREF
  HSTRING string; // [rsp+60h] [rbp-A8h] BYREF
  void *v32; // [rsp+68h] [rbp-A0h] BYREF
  const unsigned __int16 *v33; // [rsp+70h] [rbp-98h]
  struct IMdmTransport *v34; // [rsp+78h] [rbp-90h] BYREF
  struct Windows::Data::Json::IJsonObject *v35; // [rsp+80h] [rbp-88h]
  const unsigned __int16 *v36; // [rsp+88h] [rbp-80h]
  const unsigned __int16 *v37; // [rsp+90h] [rbp-78h]
  const unsigned __int16 *v38; // [rsp+98h] [rbp-70h]
  __int128 v39; // [rsp+A0h] [rbp-68h] BYREF
  unsigned __int64 v40; // [rsp+B0h] [rbp-58h]
  unsigned __int64 v41; // [rsp+B8h] [rbp-50h]

  v36 = a4;
  v37 = a3;
  v7 = a2;
  v33 = a2;
  v38 = a1;
  v39 = 0;
  v40 = 0;
  v41 = 7;
  LOWORD(v39) = 0;
  v34 = 0;
  v29 = 0;
  string = 0;
  v32 = 0;
  v8 = 0;
  v35 = 0;
  v30 = 0;
  if ( !a1 )
  {
    v9 = -2147024809;
    v10 = -2147024809;
    if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) == 0 )
      goto LABEL_51;
    v28 = "CPR(pwszMethod)";
    LODWORD(v27) = 370;
    goto LABEL_4;
  }
  if ( !a2 )
  {
    v10 = -2147024809;
    if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) == 0 )
      goto LABEL_51;
    McTemplateU0dsqs_EventWriteTransfer(
      (_DWORD)a1,
      0,
      -2147024809,
      (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmhttpwrapper.cpp",
      115,
      "CPR(pwszPath)");
    goto LABEL_49;
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
        goto LABEL_51;
      McTemplateU0dsqs_EventWriteTransfer(
        (_DWORD)a1,
        (_DWORD)a2,
        -2147024809,
        (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmhttpwrapper.cpp",
        124,
        "CBR(*ppwszBuffer == nullptr)");
      goto LABEL_49;
    }
    v11 = 1;
  }
  if ( a5 )
  {
    (*(void (__fastcall **)(struct Windows::Data::Json::IJsonObject *))(*(_QWORD *)a5 + 8LL))(a5);
    v8 = a5;
    v35 = a5;
    v12 = **(__int64 (__fastcall ***)(struct Windows::Data::Json::IJsonObject *, GUID *, __int64 *))a5;
    v13 = v30;
    if ( v30 )
    {
      v30 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
    }
    v10 = v12(a5, &GUID_a3219ecb_f0b3_4dcd_beee_19d48cd3ed1e, &v30);
    if ( v10 < 0 )
    {
      if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) == 0 )
        goto LABEL_49;
      v28 = "CHR(pRequestJsonObjectLocal.As(&pRequestJsonObjectAsValue))";
      LODWORD(v27) = 387;
      goto LABEL_22;
    }
    v14 = v30;
    v15 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v30 + 56LL);
    WindowsDeleteString(string);
    try
    {
      string = 0;
      v16 = v15(v14, &string);
    }
    catch ( std::bad_alloc )
    {
      a2 = (const unsigned __int16 *)v26;
      LODWORD(v33) = -2147024882;
      if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
        McTemplateU0dsqs_EventWriteTransfer(
          v17,
          (unsigned int)v26,
          -2147024882,
          (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmhttpwrapper.cpp",
          140,
          "CHR(((HRESULT)0x8007000EL))");
      v10 = (int)v33;
      v8 = v35;
      goto LABEL_49;
    }
    v10 = v16;
    if ( v16 < 0 )
    {
      if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
        McTemplateU0dsqs_EventWriteTransfer(
          v17,
          (_DWORD)a2,
          v16,
          (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmhttpwrapper.cpp",
          135,
          "CHR(pRequestJsonObjectAsValue->Stringify(hstrBody.GetAddressOf()))");
      goto LABEL_49;
    }
    StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
    v20 = -1;
    do
      ++v20;
    while ( StringRawBuffer[v20] );
    if ( v20 > v41 )
    {
      std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(
        &v39,
        v20,
        v19,
        StringRawBuffer);
    }
    else
    {
      v21 = &v39;
      if ( v41 > 7 )
        v21 = (__int128 *)v39;
      v40 = v20;
      v22 = 2 * v20;
      memmove_0(v21, StringRawBuffer, 2 * v20);
      *(_WORD *)((char *)v21 + v22) = 0;
    }
    v7 = v33;
  }
  v10 = CreateHttpRequest(&v34);
  if ( v10 < 0 )
  {
    if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) == 0 )
      goto LABEL_49;
    v28 = "CHR(CreateHttpRequest(pMdmTransport.GetAddressOf()))";
    LODWORD(v27) = 400;
    goto LABEL_22;
  }
  v10 = (*(__int64 (__fastcall **)(struct IMdmTransport *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, __int128 *, unsigned int *, unsigned __int64))(*(_QWORD *)v34 + 32LL))(
          v34,
          v38,
          v7,
          v37,
          v36,
          &v39,
          &v29,
          (unsigned __int64)&v32 & -(__int64)(v11 != 0));
  if ( v10 < 0 )
  {
    if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) == 0 )
      goto LABEL_49;
    v28 = "CHR(pMdmTransport->SendDelegationRequestToCommandService( pwszMethod, pwszPath, pwszDeviceTicket, pwszDelegati"
          "onTicket, wstrRequestBody, &dwHttpStatus, fReadResponse ? &pwszBuffer : nullptr ))";
    LODWORD(v27) = 409;
    goto LABEL_22;
  }
  v23 = v29;
  if ( a7 )
    *a7 = v29;
  if ( v23 - 200 <= 0x63 )
  {
    if ( v11 )
    {
      *a6 = (unsigned __int16 *)v32;
      v32 = 0;
    }
    goto LABEL_49;
  }
  v10 = -2147467259;
  if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
  {
    v28 = "CHR(((HRESULT)0x80004005L))";
    LODWORD(v27) = 418;
LABEL_22:
    v9 = v10;
LABEL_4:
    McTemplateU0dsqs_EventWriteTransfer(
      (_DWORD)a1,
      (_DWORD)a2,
      v9,
      (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmhttpwrapper.cpp",
      v27,
      v28);
  }
LABEL_49:
  if ( v32 )
    operator delete(v32, (unsigned __int64)a2);
LABEL_51:
  v24 = v30;
  if ( v30 )
  {
    v30 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
  }
  if ( v8 )
    (*(void (__fastcall **)(struct Windows::Data::Json::IJsonObject *))(*(_QWORD *)v8 + 16LL))(v8);
  WindowsDeleteString(string);
  string = 0;
  if ( v34 )
    (*(void (__fastcall **)(struct IMdmTransport *))(*(_QWORD *)v34 + 16LL))(v34);
  std::wstring::~wstring(&v39);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x18001134c  mov     r11, rsp
0x18001134f  push    rbx
0x180011350  push    rsi
0x180011351  push    rdi
0x180011352  push    r12
0x180011354  push    r13
0x180011356  push    r14
0x180011358  push    r15
0x18001135a  sub     rsp, 0D0h
0x180011361  mov     rax, cs:__security_cookie
0x180011368  xor     rax, rsp
0x18001136b  mov     [rsp+108h+var_48], rax
0x180011373  mov     [rsp+108h+var_80], r9
0x18001137b  mov     [rsp+108h+var_78], r8
0x180011383  mov     rsi, rdx
0x180011386  mov     [rsp+108h+var_98], rdx
0x18001138b  mov     [rsp+108h+var_70], rcx
0x180011393  mov     r12, [rsp+108h+arg_28]
0x18001139b  mov     r15, [rsp+108h+arg_30]
0x1800113a3  xorps   xmm0, xmm0
0x1800113a6  movups  xmmword ptr [r11-68h], xmm0
0x1800113ab  xor     r14d, r14d
0x1800113ae  mov     [r11-58h], r14
0x1800113b2  mov     qword ptr [r11-50h], 7
0x1800113ba  mov     [r11-68h], r14w
0x1800113bf  mov     [rsp+108h+var_90], r14
0x1800113c4  mov     [rsp+108h+var_B8], r14d
0x1800113c9  mov     [rsp+108h+string], r14
0x1800113ce  mov     [rsp+108h+var_A0], r14
0x1800113d3  mov     ebx, r14d
0x1800113d6  mov     [rsp+108h+var_88], rbx
0x1800113de  mov     [rsp+108h+var_B0], r14
0x1800113e3  test    rcx, rcx
0x1800113e6  jnz     short loc_180011423
0x1800113e8  mov     r8d, 80070057h
0x1800113ee  mov     edi, r8d
0x1800113f1  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x1800113f8  jz      loc_18001174B
0x1800113fe  lea     rax, aCprPwszmethod; "CPR(pwszMethod)"
0x180011405  mov     [rsp+108h+var_E0], rax
0x18001140a  mov     dword ptr [rsp+108h+var_E8], 172h
0x180011412  lea     r9, aOnecoreuapShel_7; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x180011419  call    McTemplateU0dsqs_EventWriteTransfer
0x18001141e  jmp     loc_18001173B
0x180011423  test    rdx, rdx
0x180011426  jnz     short loc_180011454
0x180011428  mov     r8d, 80070057h
0x18001142e  mov     edi, r8d
0x180011431  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x180011438  jz      loc_18001174B
0x18001143e  lea     rax, aCprPwszpath; "CPR(pwszPath)"
0x180011445  mov     [rsp+108h+var_E0], rax
0x18001144a  mov     dword ptr [rsp+108h+var_E8], 173h
0x180011452  jmp     short loc_180011412
0x180011454  mov     r13d, r14d
0x180011457  test    r15, r15
0x18001145a  jz      short loc_18001145F
0x18001145c  mov     [r15], r14d
0x18001145f  test    r12, r12
0x180011462  jz      short loc_18001149F
0x180011464  cmp     [r12], r14
0x180011468  jz      short loc_180011499
0x18001146a  mov     r8d, 80070057h
0x180011470  mov     edi, r8d
0x180011473  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18001147a  jz      loc_18001174B
0x180011480  lea     rax, aCbrPpwszbuffer; "CBR(*ppwszBuffer == nullptr)"
0x180011487  mov     [rsp+108h+var_E0], rax
0x18001148c  mov     dword ptr [rsp+108h+var_E8], 17Ch
0x180011494  jmp     loc_180011412
0x180011499  mov     r13d, 1
0x18001149f  mov     rdi, [rsp+108h+arg_20]
0x1800114a7  test    rdi, rdi
0x1800114aa  jz      loc_180011619
0x1800114b0  mov     rax, [rdi]
0x1800114b3  mov     rcx, rdi
0x1800114b6  mov     rax, [rax+8]
0x1800114ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800114bf  nop
0x1800114c0  mov     rbx, rdi
0x1800114c3  mov     [rsp+108h+var_88], rbx
0x1800114cb  mov     rax, [rdi]
0x1800114ce  mov     rsi, [rax]
0x1800114d1  mov     rcx, [rsp+108h+var_B0]
0x1800114d6  test    rcx, rcx
0x1800114d9  jz      short loc_1800114ED
0x1800114db  mov     [rsp+108h+var_B0], r14
0x1800114e0  mov     rax, [rcx]
0x1800114e3  mov     rax, [rax+10h]
0x1800114e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800114ec  nop
0x1800114ed  lea     r8, [rsp+108h+var_B0]
0x1800114f2  lea     rdx, _GUID_a3219ecb_f0b3_4dcd_beee_19d48cd3ed1e
0x1800114f9  mov     rcx, rdi
0x1800114fc  mov     rax, rsi
0x1800114ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011504  mov     edi, eax
0x180011506  test    eax, eax
0x180011508  jns     short loc_180011533
0x18001150a  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x180011511  jz      loc_18001173B
0x180011517  lea     rax, aChrPrequestjso_0; "CHR(pRequestJsonObjectLocal.As(&pReques"...
0x18001151e  mov     [rsp+108h+var_E0], rax
0x180011523  mov     dword ptr [rsp+108h+var_E8], 183h
0x18001152b  mov     r8d, edi
0x18001152e  jmp     loc_180011412
0x180011533  mov     rsi, [rsp+108h+var_B0]
0x180011538  mov     rax, [rsi]
0x18001153b  mov     rdi, [rax+38h]
0x18001153f  mov     rcx, [rsp+108h+string]; string
0x180011544  call    cs:__imp_WindowsDeleteString
0x18001154b  nop     dword ptr [rax+rax+00h]
0x180011550  mov     [rsp+108h+string], r14
0x180011555  lea     rdx, [rsp+108h+string]
0x18001155a  mov     rcx, rsi
0x18001155d  mov     rax, rdi
0x180011560  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011565  mov     edi, eax
0x180011567  test    eax, eax
0x180011569  jns     short loc_18001159D
0x18001156b  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x180011572  jz      short loc_180011598
0x180011574  lea     rax, aChrPrequestjso; "CHR(pRequestJsonObjectAsValue->Stringif"...
0x18001157b  mov     [rsp+108h+var_E0], rax
0x180011580  mov     dword ptr [rsp+108h+var_E8], 187h
0x180011588  lea     r9, aOnecoreuapShel_7; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x18001158f  mov     r8d, edi
0x180011592  call    McTemplateU0dsqs_EventWriteTransfer
0x180011597  nop
0x180011598  jmp     loc_18001173B
0x18001159d  xor     edx, edx; length
0x18001159f  mov     rcx, [rsp+108h+string]; string
0x1800115a4  call    cs:__imp_WindowsGetStringRawBuffer
0x1800115ab  nop     dword ptr [rax+rax+00h]
0x1800115b0  or      rdx, 0FFFFFFFFFFFFFFFFh
0x1800115b4  inc     rdx
0x1800115b7  cmp     [rax+rdx*2], r14w
0x1800115bc  jnz     short loc_1800115B4
0x1800115be  cmp     rdx, [rsp+108h+var_50]
0x1800115c6  ja      short loc_180011603
0x1800115c8  lea     rsi, [rsp+108h+var_68]
0x1800115d0  cmp     [rsp+108h+var_50], 7
0x1800115d9  cmova   rsi, qword ptr [rsp+108h+var_68]
0x1800115e2  mov     [rsp+108h+var_58], rdx
0x1800115ea  lea     rdi, [rdx+rdx]
0x1800115ee  mov     r8, rdi; Size
0x1800115f1  mov     rdx, rax; Src
0x1800115f4  mov     rcx, rsi; void *
0x1800115f7  call    memmove_0
0x1800115fc  mov     [rdi+rsi], r14w
0x180011601  jmp     short loc_180011614
0x180011603  mov     r9, rax
0x180011606  lea     rcx, [rsp+108h+var_68]
0x18001160e  call    ??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z; std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)
0x180011613  nop
0x180011614  mov     rsi, [rsp+108h+var_98]
0x180011619  lea     rcx, [rsp+108h+var_90]; struct IMdmTransport **
0x18001161e  call    ?CreateHttpRequest@@YAJPEAPEAUIMdmTransport@@@Z; CreateHttpRequest(IMdmTransport * *)
0x180011623  mov     edi, eax
0x180011625  test    eax, eax
0x180011627  jns     short loc_180011663
0x180011629  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x180011630  jz      loc_18001173B
0x180011636  lea     rax, aChrCreatehttpr; "CHR(CreateHttpRequest(pMdmTransport.Get"...
0x18001163d  mov     [rsp+108h+var_E0], rax
0x180011642  mov     dword ptr [rsp+108h+var_E8], 190h
0x18001164a  jmp     loc_18001152B
0x18001164f  xor     r14d, r14d
0x180011652  mov     edi, dword ptr [rsp+108h+var_98]
0x180011656  mov     rbx, [rsp+108h+var_88]
0x18001165e  jmp     loc_18001173B
0x180011663  mov     r11, [rsp+108h+var_90]
0x180011668  mov     r10, [r11]
0x18001166b  mov     eax, r13d
0x18001166e  neg     eax
0x180011670  sbb     rcx, rcx
0x180011673  lea     rax, [rsp+108h+var_A0]
0x180011678  and     rcx, rax
0x18001167b  mov     [rsp+108h+var_D0], rcx
0x180011680  lea     rax, [rsp+108h+var_B8]
0x180011685  mov     [rsp+108h+var_D8], rax
0x18001168a  lea     rax, [rsp+108h+var_68]
0x180011692  mov     [rsp+108h+var_E0], rax
0x180011697  mov     rax, [rsp+108h+var_80]
0x18001169f  mov     [rsp+108h+var_E8], rax
0x1800116a4  mov     r9, [rsp+108h+var_78]
0x1800116ac  mov     r8, rsi
0x1800116af  mov     rdx, [rsp+108h+var_70]
0x1800116b7  mov     rcx, r11
0x1800116ba  mov     rax, [r10+20h]
0x1800116be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800116c3  mov     edi, eax
0x1800116c5  test    eax, eax
0x1800116c7  jns     short loc_1800116EB
0x1800116c9  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x1800116d0  jz      short loc_18001173B
0x1800116d2  lea     rax, aChrPmdmtranspo_2; "CHR(pMdmTransport->SendDelegationReques"...
0x1800116d9  mov     [rsp+108h+var_E0], rax
0x1800116de  mov     dword ptr [rsp+108h+var_E8], 199h
0x1800116e6  jmp     loc_18001152B
0x1800116eb  mov     eax, [rsp+108h+var_B8]
0x1800116ef  test    r15, r15
0x1800116f2  jz      short loc_1800116F7
0x1800116f4  mov     [r15], eax
0x1800116f7  add     eax, 0FFFFFF38h
0x1800116fc  cmp     eax, 63h ; 'c'
0x1800116ff  jbe     short loc_180011728
0x180011701  mov     edi, 80004005h
0x180011706  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18001170d  jz      short loc_18001173B
0x18001170f  lea     rax, aChrHresult0x80_2; "CHR(((HRESULT)0x80004005L))"
0x180011716  mov     [rsp+108h+var_E0], rax
0x18001171b  mov     dword ptr [rsp+108h+var_E8], 1A2h
0x180011723  jmp     loc_18001152B
0x180011728  test    r13d, r13d
0x18001172b  jz      short loc_18001173B
0x18001172d  mov     rax, [rsp+108h+var_A0]
0x180011732  mov     [r12], rax
0x180011736  mov     [rsp+108h+var_A0], r14
0x18001173b  mov     rcx, [rsp+108h+var_A0]; void *
0x180011740  test    rcx, rcx
0x180011743  jz      short loc_18001174B
0x180011745  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001174a  nop
0x18001174b  mov     rcx, [rsp+108h+var_B0]
0x180011750  test    rcx, rcx
0x180011753  jz      short loc_180011767
0x180011755  mov     [rsp+108h+var_B0], r14
0x18001175a  mov     rax, [rcx]
0x18001175d  mov     rax, [rax+10h]
0x180011761  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011766  nop
0x180011767  test    rbx, rbx
0x18001176a  jz      short loc_18001177C
0x18001176c  mov     rax, [rbx]
0x18001176f  mov     rcx, rbx
0x180011772  mov     rax, [rax+10h]
0x180011776  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001177b  nop
0x18001177c  mov     rcx, [rsp+108h+string]; string
0x180011781  call    cs:__imp_WindowsDeleteString
0x180011788  nop     dword ptr [rax+rax+00h]
0x18001178d  mov     [rsp+108h+string], r14
0x180011792  mov     rcx, [rsp+108h+var_90]
0x180011797  test    rcx, rcx
0x18001179a  jz      short loc_1800117A9
0x18001179c  mov     rax, [rcx]
0x18001179f  mov     rax, [rax+10h]
0x1800117a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800117a8  nop
0x1800117a9  lea     rcx, [rsp+108h+var_68]
0x1800117b1  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800117b6  mov     eax, edi
0x1800117b8  mov     rcx, [rsp+108h+var_48]
0x1800117c0  xor     rcx, rsp; StackCookie
0x1800117c3  call    __security_check_cookie
0x1800117c8  add     rsp, 0D0h
0x1800117cf  pop     r15
0x1800117d1  pop     r14
0x1800117d3  pop     r13
0x1800117d5  pop     r12
0x1800117d7  pop     rdi
0x1800117d8  pop     rsi
0x1800117d9  pop     rbx
0x1800117da  retn
```
