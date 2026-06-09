# MdmHttpWrapper::MdmSendRequestToCS(ushort const *,ushort const *,ushort const *,ushort const *,Windows::Data::Json::IJsonObject *,ushort * *,ulong *)

- ea: `0x180010eb4`
- end: `0x180011344`
- name: `?MdmSendRequestToCS@MdmHttpWrapper@@SAJPEBG000PEAUIJsonObject@Json@Data@Windows@@PEAPEAGPEAK@Z`
- size: `1168`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, struct Windows::Data::Json::IJsonObject *, unsigned __int16 **, unsigned int *)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x1800055a0`

## callees

- `0x180001520`
- `0x180001544`
- `0x1800028e4`
- `0x180002de8`
- `0x1800065c0`
- `0x18000bb9c`
- `0x180010eb4`
- `0x18001dbfc`
- `0x18001f010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001110c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001110c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800110ac`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800112e9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800110ac`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800112e9`

## string_xrefs

- `0x180010f7a`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmhttpwrapper.cpp`
- `0x1800110f0`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmhttpwrapper.cpp`
- `0x18001119e`: `CHR(CreateHttpRequest(pMdmTransport.GetAddressOf()))`
- `0x180010fa6`: `CPR(pwszPath)`
- `0x18001107f`: `CHR(pRequestJsonObjectLocal.As(&pRequestJsonObjectAsValue))`
- `0x1800110dc`: `CHR(pRequestJsonObjectAsValue->Stringify(hstrBody.GetAddressOf()))`
- `0x18001123a`: `CHR(pMdmTransport->SendRequestToCommandService( pwszMethod, pwszPath, pwszMainTicket, pwszSecondaryTicket, wstrRequestBody, &dwHttpStatus, fReadResponse ? &pwszBuffer : nullptr ))`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
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
    LODWORD(v27) = 456;
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
      201,
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
        210,
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
      LODWORD(v27) = 473;
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
          226,
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
          221,
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
    LODWORD(v27) = 486;
    goto LABEL_22;
  }
  v10 = (*(__int64 (__fastcall **)(struct IMdmTransport *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, __int128 *, unsigned int *, unsigned __int64))(*(_QWORD *)v34 + 24LL))(
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
    v28 = "CHR(pMdmTransport->SendRequestToCommandService( pwszMethod, pwszPath, pwszMainTicket, pwszSecondaryTicket, wst"
          "rRequestBody, &dwHttpStatus, fReadResponse ? &pwszBuffer : nullptr ))";
    LODWORD(v27) = 495;
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
    LODWORD(v27) = 504;
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
0x180010eb4  mov     r11, rsp
0x180010eb7  push    rbx
0x180010eb8  push    rsi
0x180010eb9  push    rdi
0x180010eba  push    r12
0x180010ebc  push    r13
0x180010ebe  push    r14
0x180010ec0  push    r15
0x180010ec2  sub     rsp, 0D0h
0x180010ec9  mov     rax, cs:__security_cookie
0x180010ed0  xor     rax, rsp
0x180010ed3  mov     [rsp+108h+var_48], rax
0x180010edb  mov     [rsp+108h+var_80], r9
0x180010ee3  mov     [rsp+108h+var_78], r8
0x180010eeb  mov     rsi, rdx
0x180010eee  mov     [rsp+108h+var_98], rdx
0x180010ef3  mov     [rsp+108h+var_70], rcx
0x180010efb  mov     r12, [rsp+108h+arg_28]
0x180010f03  mov     r15, [rsp+108h+arg_30]
0x180010f0b  xorps   xmm0, xmm0
0x180010f0e  movups  xmmword ptr [r11-68h], xmm0
0x180010f13  xor     r14d, r14d
0x180010f16  mov     [r11-58h], r14
0x180010f1a  mov     qword ptr [r11-50h], 7
0x180010f22  mov     [r11-68h], r14w
0x180010f27  mov     [rsp+108h+var_90], r14
0x180010f2c  mov     [rsp+108h+var_B8], r14d
0x180010f31  mov     [rsp+108h+string], r14
0x180010f36  mov     [rsp+108h+var_A0], r14
0x180010f3b  mov     ebx, r14d
0x180010f3e  mov     [rsp+108h+var_88], rbx
0x180010f46  mov     [rsp+108h+var_B0], r14
0x180010f4b  test    rcx, rcx
0x180010f4e  jnz     short loc_180010F8B
0x180010f50  mov     r8d, 80070057h
0x180010f56  mov     edi, r8d
0x180010f59  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x180010f60  jz      loc_1800112B3
0x180010f66  lea     rax, aCprPwszmethod; "CPR(pwszMethod)"
0x180010f6d  mov     [rsp+108h+var_E0], rax
0x180010f72  mov     dword ptr [rsp+108h+var_E8], 1C8h
0x180010f7a  lea     r9, aOnecoreuapShel_7; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x180010f81  call    McTemplateU0dsqs_EventWriteTransfer
0x180010f86  jmp     loc_1800112A3
0x180010f8b  test    rdx, rdx
0x180010f8e  jnz     short loc_180010FBC
0x180010f90  mov     r8d, 80070057h
0x180010f96  mov     edi, r8d
0x180010f99  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x180010fa0  jz      loc_1800112B3
0x180010fa6  lea     rax, aCprPwszpath; "CPR(pwszPath)"
0x180010fad  mov     [rsp+108h+var_E0], rax
0x180010fb2  mov     dword ptr [rsp+108h+var_E8], 1C9h
0x180010fba  jmp     short loc_180010F7A
0x180010fbc  mov     r13d, r14d
0x180010fbf  test    r15, r15
0x180010fc2  jz      short loc_180010FC7
0x180010fc4  mov     [r15], r14d
0x180010fc7  test    r12, r12
0x180010fca  jz      short loc_180011007
0x180010fcc  cmp     [r12], r14
0x180010fd0  jz      short loc_180011001
0x180010fd2  mov     r8d, 80070057h
0x180010fd8  mov     edi, r8d
0x180010fdb  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x180010fe2  jz      loc_1800112B3
0x180010fe8  lea     rax, aCbrPpwszbuffer; "CBR(*ppwszBuffer == nullptr)"
0x180010fef  mov     [rsp+108h+var_E0], rax
0x180010ff4  mov     dword ptr [rsp+108h+var_E8], 1D2h
0x180010ffc  jmp     loc_180010F7A
0x180011001  mov     r13d, 1
0x180011007  mov     rdi, [rsp+108h+arg_20]
0x18001100f  test    rdi, rdi
0x180011012  jz      loc_180011181
0x180011018  mov     rax, [rdi]
0x18001101b  mov     rcx, rdi
0x18001101e  mov     rax, [rax+8]
0x180011022  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011027  nop
0x180011028  mov     rbx, rdi
0x18001102b  mov     [rsp+108h+var_88], rbx
0x180011033  mov     rax, [rdi]
0x180011036  mov     rsi, [rax]
0x180011039  mov     rcx, [rsp+108h+var_B0]
0x18001103e  test    rcx, rcx
0x180011041  jz      short loc_180011055
0x180011043  mov     [rsp+108h+var_B0], r14
0x180011048  mov     rax, [rcx]
0x18001104b  mov     rax, [rax+10h]
0x18001104f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011054  nop
0x180011055  lea     r8, [rsp+108h+var_B0]
0x18001105a  lea     rdx, _GUID_a3219ecb_f0b3_4dcd_beee_19d48cd3ed1e
0x180011061  mov     rcx, rdi
0x180011064  mov     rax, rsi
0x180011067  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001106c  mov     edi, eax
0x18001106e  test    eax, eax
0x180011070  jns     short loc_18001109B
0x180011072  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x180011079  jz      loc_1800112A3
0x18001107f  lea     rax, aChrPrequestjso_0; "CHR(pRequestJsonObjectLocal.As(&pReques"...
0x180011086  mov     [rsp+108h+var_E0], rax
0x18001108b  mov     dword ptr [rsp+108h+var_E8], 1D9h
0x180011093  mov     r8d, edi
0x180011096  jmp     loc_180010F7A
0x18001109b  mov     rsi, [rsp+108h+var_B0]
0x1800110a0  mov     rax, [rsi]
0x1800110a3  mov     rdi, [rax+38h]
0x1800110a7  mov     rcx, [rsp+108h+string]; string
0x1800110ac  call    cs:__imp_WindowsDeleteString
0x1800110b3  nop     dword ptr [rax+rax+00h]
0x1800110b8  mov     [rsp+108h+string], r14
0x1800110bd  lea     rdx, [rsp+108h+string]
0x1800110c2  mov     rcx, rsi
0x1800110c5  mov     rax, rdi
0x1800110c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800110cd  mov     edi, eax
0x1800110cf  test    eax, eax
0x1800110d1  jns     short loc_180011105
0x1800110d3  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x1800110da  jz      short loc_180011100
0x1800110dc  lea     rax, aChrPrequestjso; "CHR(pRequestJsonObjectAsValue->Stringif"...
0x1800110e3  mov     [rsp+108h+var_E0], rax
0x1800110e8  mov     dword ptr [rsp+108h+var_E8], 1DDh
0x1800110f0  lea     r9, aOnecoreuapShel_7; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x1800110f7  mov     r8d, edi
0x1800110fa  call    McTemplateU0dsqs_EventWriteTransfer
0x1800110ff  nop
0x180011100  jmp     loc_1800112A3
0x180011105  xor     edx, edx; length
0x180011107  mov     rcx, [rsp+108h+string]; string
0x18001110c  call    cs:__imp_WindowsGetStringRawBuffer
0x180011113  nop     dword ptr [rax+rax+00h]
0x180011118  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18001111c  inc     rdx
0x18001111f  cmp     [rax+rdx*2], r14w
0x180011124  jnz     short loc_18001111C
0x180011126  cmp     rdx, [rsp+108h+var_50]
0x18001112e  ja      short loc_18001116B
0x180011130  lea     rsi, [rsp+108h+var_68]
0x180011138  cmp     [rsp+108h+var_50], 7
0x180011141  cmova   rsi, qword ptr [rsp+108h+var_68]
0x18001114a  mov     [rsp+108h+var_58], rdx
0x180011152  lea     rdi, [rdx+rdx]
0x180011156  mov     r8, rdi; Size
0x180011159  mov     rdx, rax; Src
0x18001115c  mov     rcx, rsi; void *
0x18001115f  call    memmove_0
0x180011164  mov     [rdi+rsi], r14w
0x180011169  jmp     short loc_18001117C
0x18001116b  mov     r9, rax
0x18001116e  lea     rcx, [rsp+108h+var_68]
0x180011176  call    ??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z; std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)
0x18001117b  nop
0x18001117c  mov     rsi, [rsp+108h+var_98]
0x180011181  lea     rcx, [rsp+108h+var_90]; struct IMdmTransport **
0x180011186  call    ?CreateHttpRequest@@YAJPEAPEAUIMdmTransport@@@Z; CreateHttpRequest(IMdmTransport * *)
0x18001118b  mov     edi, eax
0x18001118d  test    eax, eax
0x18001118f  jns     short loc_1800111CB
0x180011191  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x180011198  jz      loc_1800112A3
0x18001119e  lea     rax, aChrCreatehttpr; "CHR(CreateHttpRequest(pMdmTransport.Get"...
0x1800111a5  mov     [rsp+108h+var_E0], rax
0x1800111aa  mov     dword ptr [rsp+108h+var_E8], 1E6h
0x1800111b2  jmp     loc_180011093
0x1800111b7  xor     r14d, r14d
0x1800111ba  mov     edi, dword ptr [rsp+108h+var_98]
0x1800111be  mov     rbx, [rsp+108h+var_88]
0x1800111c6  jmp     loc_1800112A3
0x1800111cb  mov     r11, [rsp+108h+var_90]
0x1800111d0  mov     r10, [r11]
0x1800111d3  mov     eax, r13d
0x1800111d6  neg     eax
0x1800111d8  sbb     rcx, rcx
0x1800111db  lea     rax, [rsp+108h+var_A0]
0x1800111e0  and     rcx, rax
0x1800111e3  mov     [rsp+108h+var_D0], rcx
0x1800111e8  lea     rax, [rsp+108h+var_B8]
0x1800111ed  mov     [rsp+108h+var_D8], rax
0x1800111f2  lea     rax, [rsp+108h+var_68]
0x1800111fa  mov     [rsp+108h+var_E0], rax
0x1800111ff  mov     rax, [rsp+108h+var_80]
0x180011207  mov     [rsp+108h+var_E8], rax
0x18001120c  mov     r9, [rsp+108h+var_78]
0x180011214  mov     r8, rsi
0x180011217  mov     rdx, [rsp+108h+var_70]
0x18001121f  mov     rcx, r11
0x180011222  mov     rax, [r10+18h]
0x180011226  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001122b  mov     edi, eax
0x18001122d  test    eax, eax
0x18001122f  jns     short loc_180011253
0x180011231  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x180011238  jz      short loc_1800112A3
0x18001123a  lea     rax, aChrPmdmtranspo_0; "CHR(pMdmTransport->SendRequestToCommand"...
0x180011241  mov     [rsp+108h+var_E0], rax
0x180011246  mov     dword ptr [rsp+108h+var_E8], 1EFh
0x18001124e  jmp     loc_180011093
0x180011253  mov     eax, [rsp+108h+var_B8]
0x180011257  test    r15, r15
0x18001125a  jz      short loc_18001125F
0x18001125c  mov     [r15], eax
0x18001125f  add     eax, 0FFFFFF38h
0x180011264  cmp     eax, 63h ; 'c'
0x180011267  jbe     short loc_180011290
0x180011269  mov     edi, 80004005h
0x18001126e  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x180011275  jz      short loc_1800112A3
0x180011277  lea     rax, aChrHresult0x80_2; "CHR(((HRESULT)0x80004005L))"
0x18001127e  mov     [rsp+108h+var_E0], rax
0x180011283  mov     dword ptr [rsp+108h+var_E8], 1F8h
0x18001128b  jmp     loc_180011093
0x180011290  test    r13d, r13d
0x180011293  jz      short loc_1800112A3
0x180011295  mov     rax, [rsp+108h+var_A0]
0x18001129a  mov     [r12], rax
0x18001129e  mov     [rsp+108h+var_A0], r14
0x1800112a3  mov     rcx, [rsp+108h+var_A0]; void *
0x1800112a8  test    rcx, rcx
0x1800112ab  jz      short loc_1800112B3
0x1800112ad  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800112b2  nop
0x1800112b3  mov     rcx, [rsp+108h+var_B0]
0x1800112b8  test    rcx, rcx
0x1800112bb  jz      short loc_1800112CF
0x1800112bd  mov     [rsp+108h+var_B0], r14
0x1800112c2  mov     rax, [rcx]
0x1800112c5  mov     rax, [rax+10h]
0x1800112c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800112ce  nop
0x1800112cf  test    rbx, rbx
0x1800112d2  jz      short loc_1800112E4
0x1800112d4  mov     rax, [rbx]
0x1800112d7  mov     rcx, rbx
0x1800112da  mov     rax, [rax+10h]
0x1800112de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800112e3  nop
0x1800112e4  mov     rcx, [rsp+108h+string]; string
0x1800112e9  call    cs:__imp_WindowsDeleteString
0x1800112f0  nop     dword ptr [rax+rax+00h]
0x1800112f5  mov     [rsp+108h+string], r14
0x1800112fa  mov     rcx, [rsp+108h+var_90]
0x1800112ff  test    rcx, rcx
0x180011302  jz      short loc_180011311
0x180011304  mov     rax, [rcx]
0x180011307  mov     rax, [rax+10h]
0x18001130b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011310  nop
0x180011311  lea     rcx, [rsp+108h+var_68]
0x180011319  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001131e  mov     eax, edi
0x180011320  mov     rcx, [rsp+108h+var_48]
0x180011328  xor     rcx, rsp; StackCookie
0x18001132b  call    __security_check_cookie
0x180011330  add     rsp, 0D0h
0x180011337  pop     r15
0x180011339  pop     r14
0x18001133b  pop     r13
0x18001133d  pop     r12
0x18001133f  pop     rdi
0x180011340  pop     rsi
0x180011341  pop     rbx
0x180011342  retn
```
