# MdmHttpWrapper::MdmSendRequestToCSWithDelegation(ushort const *,ushort const *,ushort const *,ushort const *,Windows::Data::Json::IJsonObject *,ushort * *,ulong *)

- ea: `0x180010f90`
- end: `0x18001140d`
- name: `?MdmSendRequestToCSWithDelegation@MdmHttpWrapper@@SAJPEBG000PEAUIJsonObject@Json@Data@Windows@@PEAPEAGPEAK@Z`
- size: `1149`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, struct Windows::Data::Json::IJsonObject *, unsigned __int16 **, unsigned int *)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x180005670`

## callees

- `0x180001520`
- `0x180001544`
- `0x1800028e4`
- `0x180002de4`
- `0x180006548`
- `0x18000b88c`
- `0x180010f90`
- `0x18001d51c`
- `0x18001f010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800111e2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800111e2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180011188`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800113b9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180011188`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800113b9`

## string_xrefs

- `0x180011056`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmhttpwrapper.cpp`
- `0x1800111c6`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmhttpwrapper.cpp`
- `0x18001126e`: `CHR(CreateHttpRequest(pMdmTransport.GetAddressOf()))`
- `0x180011082`: `CPR(pwszPath)`
- `0x18001115b`: `CHR(pRequestJsonObjectLocal.As(&pRequestJsonObjectAsValue))`
- `0x1800111b2`: `CHR(pRequestJsonObjectAsValue->Stringify(hstrBody.GetAddressOf()))`
- `0x18001130a`: `CHR(pMdmTransport->SendDelegationRequestToCommandService( pwszMethod, pwszPath, pwszDeviceTicket, pwszDelegationTicket, wstrRequestBody, &dwHttpStatus, fReadResponse ? &pwszBuffer : nullptr ))`

## pseudocode

```c
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
    LODWORD(v28) = 370;
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
      115,
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
        124,
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
      LODWORD(v28) = 387;
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
            140,
            "CHR(((HRESULT)0x8007000EL))");
        v10 = (int)v34;
        v8 = v36;
        __eh34_try_continuation(0, &std::bad_alloc `RTTI Type Descriptor', &loc_180011287);
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
          135,
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
    LODWORD(v28) = 400;
    goto LABEL_21;
  }
  v10 = (*(__int64 (__fastcall **)(struct IMdmTransport *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, __int128 *, unsigned int *, unsigned __int64))(*(_QWORD *)v35 + 32LL))(
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
    v29 = "CHR(pMdmTransport->SendDelegationRequestToCommandService( pwszMethod, pwszPath, pwszDeviceTicket, pwszDelegati"
          "onTicket, wstrRequestBody, &dwHttpStatus, fReadResponse ? &pwszBuffer : nullptr ))";
    LODWORD(v28) = 409;
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
    LODWORD(v28) = 418;
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
0x180010f90  mov     r11, rsp
0x180010f93  push    rbx
0x180010f94  push    rsi
0x180010f95  push    rdi
0x180010f96  push    r12
0x180010f98  push    r13
0x180010f9a  push    r14
0x180010f9c  push    r15
0x180010f9e  sub     rsp, 0D0h
0x180010fa5  mov     rax, cs:__security_cookie
0x180010fac  xor     rax, rsp
0x180010faf  mov     [rsp+108h+var_48], rax
0x180010fb7  mov     [rsp+108h+var_80], r9
0x180010fbf  mov     [rsp+108h+var_78], r8
0x180010fc7  mov     rsi, rdx
0x180010fca  mov     [rsp+108h+var_98], rdx
0x180010fcf  mov     [rsp+108h+var_70], rcx
0x180010fd7  mov     r12, [rsp+108h+arg_28]
0x180010fdf  mov     r15, [rsp+108h+arg_30]
0x180010fe7  xorps   xmm0, xmm0
0x180010fea  movups  xmmword ptr [r11-68h], xmm0
0x180010fef  xor     r14d, r14d
0x180010ff2  mov     [r11-58h], r14
0x180010ff6  mov     qword ptr [r11-50h], 7
0x180010ffe  mov     [r11-68h], r14w
0x180011003  mov     [rsp+108h+var_90], r14
0x180011008  mov     [rsp+108h+var_B8], r14d
0x18001100d  mov     [rsp+108h+string], r14
0x180011012  mov     [rsp+108h+var_A0], r14
0x180011017  mov     ebx, r14d
0x18001101a  mov     [rsp+108h+var_88], rbx
0x180011022  mov     [rsp+108h+var_B0], r14
0x180011027  test    rcx, rcx
0x18001102a  jnz     short loc_180011067
0x18001102c  mov     r8d, 80070057h
0x180011032  mov     edi, r8d
0x180011035  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18001103c  jz      loc_180011383
0x180011042  lea     rax, aCprPwszmethod; "CPR(pwszMethod)"
0x180011049  mov     [rsp+108h+var_E0], rax
0x18001104e  mov     dword ptr [rsp+108h+var_E8], 172h
0x180011056  lea     r9, aOnecoreuapShel_7; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x18001105d  call    McTemplateU0dsqs_EventWriteTransfer
0x180011062  jmp     loc_180011373
0x180011067  test    rdx, rdx
0x18001106a  jnz     short loc_180011098
0x18001106c  mov     r8d, 80070057h
0x180011072  mov     edi, r8d
0x180011075  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18001107c  jz      loc_180011383
0x180011082  lea     rax, aCprPwszpath; "CPR(pwszPath)"
0x180011089  mov     [rsp+108h+var_E0], rax
0x18001108e  mov     dword ptr [rsp+108h+var_E8], 173h
0x180011096  jmp     short loc_180011056
0x180011098  mov     r13d, r14d
0x18001109b  test    r15, r15
0x18001109e  jz      short loc_1800110A3
0x1800110a0  mov     [r15], r14d
0x1800110a3  test    r12, r12
0x1800110a6  jz      short loc_1800110E3
0x1800110a8  cmp     [r12], r14
0x1800110ac  jz      short loc_1800110DD
0x1800110ae  mov     r8d, 80070057h
0x1800110b4  mov     edi, r8d
0x1800110b7  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x1800110be  jz      loc_180011383
0x1800110c4  lea     rax, aCbrPpwszbuffer; "CBR(*ppwszBuffer == nullptr)"
0x1800110cb  mov     [rsp+108h+var_E0], rax
0x1800110d0  mov     dword ptr [rsp+108h+var_E8], 17Ch
0x1800110d8  jmp     loc_180011056
0x1800110dd  mov     r13d, 1
0x1800110e3  mov     rdi, [rsp+108h+arg_20]
0x1800110eb  test    rdi, rdi
0x1800110ee  jz      loc_180011251
0x1800110f4  mov     rax, [rdi]
0x1800110f7  mov     rcx, rdi
0x1800110fa  mov     rax, [rax+8]
0x1800110fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011103  nop
0x180011104  mov     rbx, rdi
0x180011107  mov     [rsp+108h+var_88], rbx
0x18001110f  mov     rax, [rdi]
0x180011112  mov     rsi, [rax]
0x180011115  mov     rcx, [rsp+108h+var_B0]
0x18001111a  test    rcx, rcx
0x18001111d  jz      short loc_180011131
0x18001111f  mov     [rsp+108h+var_B0], r14
0x180011124  mov     rax, [rcx]
0x180011127  mov     rax, [rax+10h]
0x18001112b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011130  nop
0x180011131  lea     r8, [rsp+108h+var_B0]
0x180011136  lea     rdx, _GUID_a3219ecb_f0b3_4dcd_beee_19d48cd3ed1e
0x18001113d  mov     rcx, rdi
0x180011140  mov     rax, rsi
0x180011143  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011148  mov     edi, eax
0x18001114a  test    eax, eax
0x18001114c  jns     short loc_180011177
0x18001114e  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x180011155  jz      loc_180011373
0x18001115b  lea     rax, aChrPrequestjso_0; "CHR(pRequestJsonObjectLocal.As(&pReques"...
0x180011162  mov     [rsp+108h+var_E0], rax
0x180011167  mov     dword ptr [rsp+108h+var_E8], 183h
0x18001116f  mov     r8d, edi
0x180011172  jmp     loc_180011056
0x180011177  mov     rsi, [rsp+108h+var_B0]
0x18001117c  mov     rax, [rsi]
0x18001117f  mov     rdi, [rax+38h]
0x180011183  mov     rcx, [rsp+108h+string]; string
0x180011188  call    cs:__imp_WindowsDeleteString
0x18001118e  mov     [rsp+108h+string], r14
0x180011193  lea     rdx, [rsp+108h+string]
0x180011198  mov     rcx, rsi
0x18001119b  mov     rax, rdi
0x18001119e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800111a3  mov     edi, eax
0x1800111a5  test    eax, eax
0x1800111a7  jns     short loc_1800111DB
0x1800111a9  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x1800111b0  jz      short loc_1800111D6
0x1800111b2  lea     rax, aChrPrequestjso; "CHR(pRequestJsonObjectAsValue->Stringif"...
0x1800111b9  mov     [rsp+108h+var_E0], rax
0x1800111be  mov     dword ptr [rsp+108h+var_E8], 187h
0x1800111c6  lea     r9, aOnecoreuapShel_7; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x1800111cd  mov     r8d, edi
0x1800111d0  call    McTemplateU0dsqs_EventWriteTransfer
0x1800111d5  nop
0x1800111d6  jmp     loc_180011373
0x1800111db  xor     edx, edx; length
0x1800111dd  mov     rcx, [rsp+108h+string]; string
0x1800111e2  call    cs:__imp_WindowsGetStringRawBuffer
0x1800111e8  or      rdx, 0FFFFFFFFFFFFFFFFh
0x1800111ec  inc     rdx
0x1800111ef  cmp     [rax+rdx*2], r14w
0x1800111f4  jnz     short loc_1800111EC
0x1800111f6  cmp     rdx, [rsp+108h+var_50]
0x1800111fe  ja      short loc_18001123B
0x180011200  lea     rsi, [rsp+108h+var_68]
0x180011208  cmp     [rsp+108h+var_50], 7
0x180011211  cmova   rsi, qword ptr [rsp+108h+var_68]
0x18001121a  mov     [rsp+108h+var_58], rdx
0x180011222  lea     rdi, [rdx+rdx]
0x180011226  mov     r8, rdi; Size
0x180011229  mov     rdx, rax; Src
0x18001122c  mov     rcx, rsi; void *
0x18001122f  call    memmove_0
0x180011234  mov     [rdi+rsi], r14w
0x180011239  jmp     short loc_18001124C
0x18001123b  mov     r9, rax
0x18001123e  lea     rcx, [rsp+108h+var_68]
0x180011246  call    ??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z; std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)
0x18001124b  nop
0x18001124c  mov     rsi, [rsp+108h+var_98]
0x180011251  lea     rcx, [rsp+108h+var_90]; struct IMdmTransport **
0x180011256  call    ?CreateHttpRequest@@YAJPEAPEAUIMdmTransport@@@Z; CreateHttpRequest(IMdmTransport * *)
0x18001125b  mov     edi, eax
0x18001125d  test    eax, eax
0x18001125f  jns     short loc_18001129B
0x180011261  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x180011268  jz      loc_180011373
0x18001126e  lea     rax, aChrCreatehttpr; "CHR(CreateHttpRequest(pMdmTransport.Get"...
0x180011275  mov     [rsp+108h+var_E0], rax
0x18001127a  mov     dword ptr [rsp+108h+var_E8], 190h
0x180011282  jmp     loc_18001116F
0x180011287  xor     r14d, r14d
0x18001128a  mov     edi, dword ptr [rsp+108h+var_98]
0x18001128e  mov     rbx, [rsp+108h+var_88]
0x180011296  jmp     loc_180011373
0x18001129b  mov     r11, [rsp+108h+var_90]
0x1800112a0  mov     r10, [r11]
0x1800112a3  mov     eax, r13d
0x1800112a6  neg     eax
0x1800112a8  sbb     rcx, rcx
0x1800112ab  lea     rax, [rsp+108h+var_A0]
0x1800112b0  and     rcx, rax
0x1800112b3  mov     [rsp+108h+var_D0], rcx
0x1800112b8  lea     rax, [rsp+108h+var_B8]
0x1800112bd  mov     [rsp+108h+var_D8], rax
0x1800112c2  lea     rax, [rsp+108h+var_68]
0x1800112ca  mov     [rsp+108h+var_E0], rax
0x1800112cf  mov     rax, [rsp+108h+var_80]
0x1800112d7  mov     [rsp+108h+var_E8], rax
0x1800112dc  mov     r9, [rsp+108h+var_78]
0x1800112e4  mov     r8, rsi
0x1800112e7  mov     rdx, [rsp+108h+var_70]
0x1800112ef  mov     rcx, r11
0x1800112f2  mov     rax, [r10+20h]
0x1800112f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800112fb  mov     edi, eax
0x1800112fd  test    eax, eax
0x1800112ff  jns     short loc_180011323
0x180011301  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x180011308  jz      short loc_180011373
0x18001130a  lea     rax, aChrPmdmtranspo_2; "CHR(pMdmTransport->SendDelegationReques"...
0x180011311  mov     [rsp+108h+var_E0], rax
0x180011316  mov     dword ptr [rsp+108h+var_E8], 199h
0x18001131e  jmp     loc_18001116F
0x180011323  mov     eax, [rsp+108h+var_B8]
0x180011327  test    r15, r15
0x18001132a  jz      short loc_18001132F
0x18001132c  mov     [r15], eax
0x18001132f  add     eax, 0FFFFFF38h
0x180011334  cmp     eax, 63h ; 'c'
0x180011337  jbe     short loc_180011360
0x180011339  mov     edi, 80004005h
0x18001133e  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x180011345  jz      short loc_180011373
0x180011347  lea     rax, aChrHresult0x80_2; "CHR(((HRESULT)0x80004005L))"
0x18001134e  mov     [rsp+108h+var_E0], rax
0x180011353  mov     dword ptr [rsp+108h+var_E8], 1A2h
0x18001135b  jmp     loc_18001116F
0x180011360  test    r13d, r13d
0x180011363  jz      short loc_180011373
0x180011365  mov     rax, [rsp+108h+var_A0]
0x18001136a  mov     [r12], rax
0x18001136e  mov     [rsp+108h+var_A0], r14
0x180011373  mov     rcx, [rsp+108h+var_A0]; void *
0x180011378  test    rcx, rcx
0x18001137b  jz      short loc_180011383
0x18001137d  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180011382  nop
0x180011383  mov     rcx, [rsp+108h+var_B0]
0x180011388  test    rcx, rcx
0x18001138b  jz      short loc_18001139F
0x18001138d  mov     [rsp+108h+var_B0], r14
0x180011392  mov     rax, [rcx]
0x180011395  mov     rax, [rax+10h]
0x180011399  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001139e  nop
0x18001139f  test    rbx, rbx
0x1800113a2  jz      short loc_1800113B4
0x1800113a4  mov     rax, [rbx]
0x1800113a7  mov     rcx, rbx
0x1800113aa  mov     rax, [rax+10h]
0x1800113ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800113b3  nop
0x1800113b4  mov     rcx, [rsp+108h+string]; string
0x1800113b9  call    cs:__imp_WindowsDeleteString
0x1800113bf  mov     [rsp+108h+string], r14
0x1800113c4  mov     rcx, [rsp+108h+var_90]
0x1800113c9  test    rcx, rcx
0x1800113cc  jz      short loc_1800113DB
0x1800113ce  mov     rax, [rcx]
0x1800113d1  mov     rax, [rax+10h]
0x1800113d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800113da  nop
0x1800113db  lea     rcx, [rsp+108h+var_68]
0x1800113e3  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800113e8  mov     eax, edi
0x1800113ea  mov     rcx, [rsp+108h+var_48]
0x1800113f2  xor     rcx, rsp; StackCookie
0x1800113f5  call    __security_check_cookie
0x1800113fa  add     rsp, 0D0h
0x180011401  pop     r15
0x180011403  pop     r14
0x180011405  pop     r13
0x180011407  pop     r12
0x180011409  pop     rdi
0x18001140a  pop     rsi
0x18001140b  pop     rbx
0x18001140c  retn
```
