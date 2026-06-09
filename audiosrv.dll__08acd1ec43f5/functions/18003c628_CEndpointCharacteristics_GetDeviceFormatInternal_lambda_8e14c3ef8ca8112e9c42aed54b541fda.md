# CEndpointCharacteristics::GetDeviceFormatInternal__lambda_8e14c3ef8ca8112e9c42aed54b541fda___

- ea: `0x18003c628`
- end: `0x18003c9af`
- name: `CEndpointCharacteristics::GetDeviceFormatInternal__lambda_8e14c3ef8ca8112e9c42aed54b541fda___`
- size: `903`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x18003aa50`

## callees

- `0x180008a2c`
- `0x18001280c`
- `0x18002318c`
- `0x18003b140`
- `0x18003c628`
- `0x18003cc58`
- `0x18003d040`
- `0x18004f298`
- `0x18008a9a8`
- `0x1800cbfcc`
- `0x1800cd8d0`
- `0x1801445dc`
- `0x180144600`
- `0x18016c010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18003c858`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18003c918`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18003c94a`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18003c858`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18003c918`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18003c94a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003c6db`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003c71e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003c86e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003c6db`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003c71e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003c86e`

## string_xrefs

- `0x18003c6fd`: `avcore\audiocore\server\lib\audioserviceutil\endpointcharacteristics.cpp`
- `0x18003c783`: `avcore\audiocore\server\lib\audioserviceutil\endpointcharacteristics.cpp`
- `0x18003c7c8`: `avcore\audiocore\server\lib\audioserviceutil\endpointcharacteristics.cpp`
- `0x18003c840`: `avcore\audiocore\server\lib\audioserviceutil\endpointcharacteristics.cpp`
- `0x18003c902`: `avcore\audiocore\server\lib\audioserviceutil\endpointcharacteristics.cpp`
- `0x18003c967`: `avcore\audiocore\server\lib\audioserviceutil\endpointcharacteristics.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CEndpointCharacteristics::GetDeviceFormatInternal__lambda_8e14c3ef8ca8112e9c42aed54b541fda___(
        CEndpointCharacteristics *this,
        char a2,
        unsigned __int8 a3,
        enum __MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001 a4,
        _OWORD *a5,
        LPVOID *a6)
{
  int v7; // r15d
  int DefaultFormat__lambda_8e14c3ef8ca8112e9c42aed54b541fda; // edi
  void *v10; // rcx
  int updated; // ebx
  void *v12; // rcx
  GUID fmtid; // xmm0
  DWORD pid; // eax
  int v16; // eax
  unsigned int v17; // r8d
  const char *v18; // r9
  BYTE *pData; // rbx
  __int64 v20; // rdx
  void *v21; // rcx
  bool v22; // zf
  int v23; // eax
  unsigned int v24; // [rsp+20h] [rbp-A9h]
  char *v25; // [rsp+28h] [rbp-A1h]
  _BYTE v26[8]; // [rsp+40h] [rbp-89h] BYREF
  LPVOID pv; // [rsp+48h] [rbp-81h] BYREF
  struct tagPROPVARIANT pvar; // [rsp+50h] [rbp-79h] BYREF
  LPVOID *p_pv; // [rsp+68h] [rbp-61h] BYREF
  struct tWAVEFORMATEX *v30; // [rsp+70h] [rbp-59h] BYREF
  char v31; // [rsp+78h] [rbp-51h]
  int v32[4]; // [rsp+80h] [rbp-49h] BYREF
  __int128 v33; // [rsp+90h] [rbp-39h]
  __int128 v34; // [rsp+A0h] [rbp-29h]
  __int128 v35; // [rsp+B0h] [rbp-19h]
  GUID v36; // [rsp+C0h] [rbp-9h] BYREF
  DWORD v37; // [rsp+D0h] [rbp+7h]
  wil::details::in1diag3 *retaddr; // [rsp+118h] [rbp+4Fh]

  v7 = a3;
  *a6 = 0;
  pv = 0;
  if ( !a2 )
  {
    if ( a4 == eKeywordDetectorConnector )
    {
      fmtid = (GUID)PKEY_AudioEngine_KeywordDetector_DeviceFormat;
      pid = 0;
    }
    else
    {
      fmtid = PKEY_AudioEngine_DeviceFormat.fmtid;
      pid = PKEY_AudioEngine_DeviceFormat.pid;
    }
    v36 = fmtid;
    v37 = pid;
    memset(&pvar, 0, sizeof(pvar));
    v16 = (*(__int64 (__fastcall **)(_QWORD, GUID *, struct tagPROPVARIANT *))(**((_QWORD **)this + 9) + 40LL))(
            *((_QWORD *)this + 9),
            &v36,
            &pvar);
    if ( v16 >= 0 )
    {
      if ( pvar.vt )
      {
        if ( pvar.vt == 65 )
        {
          if ( (unsigned int)IsValidWfxBlob(&pvar) )
          {
            pData = pvar.bstrblobVal.pData;
            v26[0] = 0;
            lambda_5789e60fd85b99cd3c89d9f341e01d71_::operator()(a5, pvar.bstrblobVal.pData, v26);
            if ( v26[0] )
            {
              p_pv = &pv;
              v30 = 0;
              v31 = 1;
              updated = CloneWaveFormat((const struct tWAVEFORMATEX *)pData, &v30);
              wil::details::out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>(&p_pv);
              if ( updated < 0 )
              {
                v20 = 6592;
                goto LABEL_23;
              }
            }
          }
          else
          {
            wil::details::in1diag3::Log_Win32(retaddr, (void *)0x19C5, v17, v18, v24);
          }
        }
        else
        {
          LODWORD(v25) = pvar.vt;
          wil::details::in1diag3::Log_Win32Msg(
            retaddr,
            (void *)0x19D1,
            (unsigned int)"avcore\\audiocore\\server\\lib\\audioserviceutil\\endpointcharacteristics.cpp",
            (const char *)0xD,
            (unsigned int)"Unexpected vartype %d (0x%08x)",
            v25);
        }
      }
    }
    else
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x19B4,
        (unsigned int)"avcore\\audiocore\\server\\lib\\audioserviceutil\\endpointcharacteristics.cpp",
        (const char *)(unsigned int)v16,
        v24);
    }
    if ( pv )
      goto LABEL_35;
    p_pv = &pv;
    v30 = 0;
    v31 = 1;
    *(_OWORD *)v32 = *a5;
    v33 = a5[1];
    v34 = a5[2];
    v35 = a5[3];
    DefaultFormat__lambda_8e14c3ef8ca8112e9c42aed54b541fda = CEndpointCharacteristics::GetDefaultFormat__lambda_8e14c3ef8ca8112e9c42aed54b541fda___(
                                                               (int)this,
                                                               v7,
                                                               a4,
                                                               (int)v32,
                                                               &v30);
    wil::details::out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>(&p_pv);
    if ( DefaultFormat__lambda_8e14c3ef8ca8112e9c42aed54b541fda < 0 )
    {
      updated = -2004287484;
      if ( DefaultFormat__lambda_8e14c3ef8ca8112e9c42aed54b541fda != -2004287484 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x19D8,
          (unsigned int)"avcore\\audiocore\\server\\lib\\audioserviceutil\\endpointcharacteristics.cpp",
          (const char *)(unsigned int)DefaultFormat__lambda_8e14c3ef8ca8112e9c42aed54b541fda,
          v24);
        PropVariantClear((PROPVARIANT *)&pvar);
        goto LABEL_8;
      }
      goto LABEL_24;
    }
    updated = CEndpointCharacteristics::UpdateDeviceFormatEPProperty(this, v7, a4, (const struct tWAVEFORMATEX *)pv);
    if ( updated >= 0 )
    {
LABEL_35:
      PropVariantClear((PROPVARIANT *)&pvar);
LABEL_36:
      v23 = ValidateWaveFormatEx((const struct tWAVEFORMATEX *)pv);
      updated = v23;
      if ( v23 >= 0 )
      {
        *a6 = pv;
        return 0;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x19E0,
        (unsigned int)"avcore\\audiocore\\server\\lib\\audioserviceutil\\endpointcharacteristics.cpp",
        (const char *)(unsigned int)v23,
        v24);
      goto LABEL_25;
    }
    v20 = 6619;
LABEL_23:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v20,
      (unsigned int)"avcore\\audiocore\\server\\lib\\audioserviceutil\\endpointcharacteristics.cpp",
      (const char *)(unsigned int)updated,
      v24);
LABEL_24:
    PropVariantClear((PROPVARIANT *)&pvar);
    goto LABEL_25;
  }
  *(_QWORD *)&pvar.vt = &pv;
  pvar.hVal.QuadPart = 0;
  *((_BYTE *)&pvar.decVal + 16) = 1;
  *(_OWORD *)v32 = *a5;
  v33 = a5[1];
  v34 = a5[2];
  v35 = a5[3];
  DefaultFormat__lambda_8e14c3ef8ca8112e9c42aed54b541fda = CEndpointCharacteristics::GetDefaultFormat__lambda_8e14c3ef8ca8112e9c42aed54b541fda___(
                                                             (int)this,
                                                             a3,
                                                             a4,
                                                             (int)v32,
                                                             (struct tWAVEFORMATEX **)&pvar.hVal.QuadPart);
  if ( *((_BYTE *)&pvar.decVal + 16) )
  {
    v10 = **(void ***)&pvar.vt;
    **(_QWORD **)&pvar.vt = pvar.hVal.QuadPart;
    if ( v10 )
      CoTaskMemFree(v10);
  }
  if ( DefaultFormat__lambda_8e14c3ef8ca8112e9c42aed54b541fda >= 0 )
    goto LABEL_36;
  updated = -2004287484;
  if ( DefaultFormat__lambda_8e14c3ef8ca8112e9c42aed54b541fda != -2004287484 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x19AB,
      (unsigned int)"avcore\\audiocore\\server\\lib\\audioserviceutil\\endpointcharacteristics.cpp",
      (const char *)(unsigned int)DefaultFormat__lambda_8e14c3ef8ca8112e9c42aed54b541fda,
      v24);
LABEL_8:
    v12 = pv;
    pv = 0;
    if ( v12 )
      CoTaskMemFree(v12);
    return (unsigned int)DefaultFormat__lambda_8e14c3ef8ca8112e9c42aed54b541fda;
  }
LABEL_25:
  v21 = pv;
  v22 = pv == 0;
  pv = 0;
  if ( !v22 )
    CoTaskMemFree(v21);
  return (unsigned int)updated;
}

```

## disassembly

```asm
0x18003c628  mov     [rsp-8+arg_8], rbx
0x18003c62d  push    rbp
0x18003c62e  push    rsi
0x18003c62f  push    rdi
0x18003c630  push    r12
0x18003c632  push    r13
0x18003c634  push    r14
0x18003c636  push    r15
0x18003c638  lea     rbp, [rsp-17h]
0x18003c63d  sub     rsp, 0E0h
0x18003c644  mov     rax, cs:__security_cookie
0x18003c64b  xor     rax, rsp
0x18003c64e  mov     [rbp+47h+var_38], rax
0x18003c652  mov     esi, r9d
0x18003c655  movzx   r15d, r8b
0x18003c659  mov     r14, rcx
0x18003c65c  mov     rdi, [rbp+47h+arg_20]
0x18003c660  mov     r12, [rbp+47h+arg_28]
0x18003c664  xor     r13d, r13d
0x18003c667  mov     [r12], r13
0x18003c66b  mov     [rsp+110h+pv], r13
0x18003c670  test    dl, dl
0x18003c672  jz      loc_18003C72B
0x18003c678  lea     rax, [rsp+110h+pv]
0x18003c67d  mov     [rbp+47h+pvar], rax
0x18003c681  mov     [rbp+47h+pvar+8], r13
0x18003c685  mov     byte ptr [rbp+47h+Src], 1
0x18003c689  movaps  xmm0, xmmword ptr [rdi]
0x18003c68c  movaps  xmmword ptr [rbp+47h+var_90], xmm0
0x18003c690  movaps  xmm1, xmmword ptr [rdi+10h]
0x18003c694  movaps  [rbp+47h+var_80], xmm1
0x18003c698  movaps  xmm0, xmmword ptr [rdi+20h]
0x18003c69c  movaps  [rbp+47h+var_70], xmm0
0x18003c6a0  movaps  xmm1, xmmword ptr [rdi+30h]
0x18003c6a4  movaps  [rbp+47h+var_60], xmm1
0x18003c6a8  mov     edx, r15d; int
0x18003c6ab  lea     rax, [rbp+47h+pvar+8]
0x18003c6af  mov     [rsp+110h+var_F0], rax; int
0x18003c6b4  lea     r9, [rbp+47h+var_90]; int
0x18003c6b8  mov     r8d, esi; int
0x18003c6bb  call    CEndpointCharacteristics__GetDefaultFormat__lambda_8e14c3ef8ca8112e9c42aed54b541fda___
0x18003c6c0  mov     edi, eax
0x18003c6c2  cmp     byte ptr [rbp+47h+Src], r13b
0x18003c6c6  jz      short loc_18003C6E1
0x18003c6c8  mov     r8, [rbp+47h+pvar]
0x18003c6cc  mov     rcx, [r8]; pv
0x18003c6cf  mov     rdx, [rbp+47h+pvar+8]
0x18003c6d3  mov     [r8], rdx
0x18003c6d6  test    rcx, rcx
0x18003c6d9  jz      short loc_18003C6E1
0x18003c6db  call    cs:__imp_CoTaskMemFree
0x18003c6e1  test    edi, edi
0x18003c6e3  jns     loc_18003C950
0x18003c6e9  mov     ebx, 88890004h
0x18003c6ee  cmp     edi, ebx
0x18003c6f0  jz      loc_18003C85F
0x18003c6f6  mov     rcx, [rbp+4Fh]; this
0x18003c6fa  mov     r9d, edi; char *
0x18003c6fd  lea     r8, aAvcoreAudiocor_53; "avcore\\audiocore\\server\\lib\\audiose"...
0x18003c704  mov     edx, 19ABh; void *
0x18003c709  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003c70e  nop
0x18003c70f  mov     rcx, [rsp+110h+pv]; pv
0x18003c714  mov     [rsp+110h+pv], r13
0x18003c719  test    rcx, rcx
0x18003c71c  jz      short loc_18003C724
0x18003c71e  call    cs:__imp_CoTaskMemFree
0x18003c724  mov     eax, edi
0x18003c726  jmp     loc_18003C988
0x18003c72b  cmp     esi, 3
0x18003c72e  jnz     short loc_18003C73F
0x18003c730  movups  xmm0, cs:PKEY_AudioEngine_KeywordDetector_DeviceFormat
0x18003c737  mov     eax, cs:dword_18018AAD8
0x18003c73d  jmp     short loc_18003C74C
0x18003c73f  movups  xmm0, xmmword ptr cs:PKEY_AudioEngine_DeviceFormat.fmtid.Data1
0x18003c746  mov     eax, cs:PKEY_AudioEngine_DeviceFormat.pid
0x18003c74c  movups  [rbp+47h+var_50], xmm0
0x18003c750  mov     [rbp+47h+var_40], eax
0x18003c753  xorps   xmm0, xmm0
0x18003c756  xor     eax, eax
0x18003c758  movups  xmmword ptr [rbp+47h+pvar], xmm0
0x18003c75c  mov     [rbp+47h+Src], rax
0x18003c760  mov     rcx, [rcx+48h]
0x18003c764  mov     rax, [rcx]
0x18003c767  lea     r8, [rbp+47h+pvar]
0x18003c76b  lea     rdx, [rbp+47h+var_50]
0x18003c76f  mov     rax, [rax+28h]
0x18003c773  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c778  mov     rcx, [rbp+4Fh]; this
0x18003c77c  test    eax, eax
0x18003c77e  jns     short loc_18003C799
0x18003c780  mov     r9d, eax; char *
0x18003c783  lea     r8, aAvcoreAudiocor_53; "avcore\\audiocore\\server\\lib\\audiose"...
0x18003c78a  mov     edx, 19B4h; void *
0x18003c78f  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18003c794  jmp     loc_18003C889
0x18003c799  movzx   eax, word ptr [rbp+47h+pvar]
0x18003c79d  test    eax, eax
0x18003c79f  jz      loc_18003C889
0x18003c7a5  cmp     eax, 41h ; 'A'
0x18003c7a8  jz      short loc_18003C7DE
0x18003c7aa  mov     rcx, [rbp+4Fh]; this
0x18003c7ae  mov     [rsp+110h+var_E0], eax
0x18003c7b2  mov     dword ptr [rsp+110h+var_E8], eax; char *
0x18003c7b6  lea     rax, aUnexpectedVart_1; "Unexpected vartype %d (0x%08x)"
0x18003c7bd  mov     [rsp+110h+var_F0], rax; unsigned int
0x18003c7c2  mov     r9d, 0Dh; char *
0x18003c7c8  lea     r8, aAvcoreAudiocor_53; "avcore\\audiocore\\server\\lib\\audiose"...
0x18003c7cf  mov     edx, 19D1h; void *
0x18003c7d4  call    ?Log_Win32Msg@in1diag3@details@wil@@YAKPEAXIPEBDK1ZZ; wil::details::in1diag3::Log_Win32Msg(void *,uint,char const *,ulong,char const *,...)
0x18003c7d9  jmp     loc_18003C889
0x18003c7de  lea     rcx, [rbp+47h+pvar]; struct tagPROPVARIANT *
0x18003c7e2  call    ?IsValidWfxBlob@@YAHPEAUtagPROPVARIANT@@@Z; IsValidWfxBlob(tagPROPVARIANT *)
0x18003c7e7  test    eax, eax
0x18003c7e9  jz      loc_18003C87B
0x18003c7ef  mov     rbx, [rbp+47h+Src]
0x18003c7f3  mov     [rsp+110h+var_D0], r13b
0x18003c7f8  lea     r8, [rsp+110h+var_D0]
0x18003c7fd  mov     rdx, rbx
0x18003c800  mov     rcx, rdi
0x18003c803  call    _lambda_5789e60fd85b99cd3c89d9f341e01d71___operator__
0x18003c808  cmp     [rsp+110h+var_D0], r13b
0x18003c80d  jz      short loc_18003C889
0x18003c80f  lea     rax, [rsp+110h+pv]
0x18003c814  mov     [rbp+47h+var_A8], rax
0x18003c818  mov     [rbp+47h+var_A0], r13
0x18003c81c  mov     [rbp+47h+var_98], 1
0x18003c820  lea     rdx, [rbp+47h+var_A0]; struct tWAVEFORMATEX **
0x18003c824  mov     rcx, rbx; Src
0x18003c827  call    ?CloneWaveFormat@@YAJPEBUtWAVEFORMATEX@@PEAPEAU1@@Z; CloneWaveFormat(tWAVEFORMATEX const *,tWAVEFORMATEX * *)
0x18003c82c  mov     ebx, eax
0x18003c82e  lea     rcx, [rbp+47h+var_A8]
0x18003c832  call    ??1?$out_param_t@V?$unique_ptr@U_GUID@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>(void)
0x18003c837  test    ebx, ebx
0x18003c839  jns     short loc_18003C889
0x18003c83b  mov     edx, 19C0h; void *
0x18003c840  lea     r8, aAvcoreAudiocor_53; "avcore\\audiocore\\server\\lib\\audiose"...
0x18003c847  mov     r9d, ebx; char *
0x18003c84a  mov     rcx, [rbp+4Fh]; this
0x18003c84e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003c853  nop
0x18003c854  lea     rcx, [rbp+47h+pvar]; pvar
0x18003c858  call    cs:__imp_PropVariantClear
0x18003c85e  nop
0x18003c85f  mov     rcx, [rsp+110h+pv]; pv
0x18003c864  test    rcx, rcx
0x18003c867  mov     [rsp+110h+pv], r13
0x18003c86c  jz      short loc_18003C874
0x18003c86e  call    cs:__imp_CoTaskMemFree
0x18003c874  mov     eax, ebx
0x18003c876  jmp     loc_18003C988
0x18003c87b  mov     rcx, [rbp+4Fh]; this
0x18003c87f  mov     edx, 19C5h; void *
0x18003c884  call    ?Log_Win32@in1diag3@details@wil@@YAKPEAXIPEBDK@Z; wil::details::in1diag3::Log_Win32(void *,uint,char const *,ulong)
0x18003c889  cmp     [rsp+110h+pv], r13
0x18003c88e  jnz     loc_18003C946
0x18003c894  lea     rax, [rsp+110h+pv]
0x18003c899  mov     [rbp+47h+var_A8], rax
0x18003c89d  mov     [rbp+47h+var_A0], r13
0x18003c8a1  mov     [rbp+47h+var_98], 1
0x18003c8a5  movaps  xmm0, xmmword ptr [rdi]
0x18003c8a8  movaps  xmmword ptr [rbp+47h+var_90], xmm0
0x18003c8ac  movaps  xmm1, xmmword ptr [rdi+10h]
0x18003c8b0  movaps  [rbp+47h+var_80], xmm1
0x18003c8b4  movaps  xmm0, xmmword ptr [rdi+20h]
0x18003c8b8  movaps  [rbp+47h+var_70], xmm0
0x18003c8bc  movaps  xmm1, xmmword ptr [rdi+30h]
0x18003c8c0  movaps  [rbp+47h+var_60], xmm1
0x18003c8c4  mov     edx, r15d; int
0x18003c8c7  lea     rax, [rbp+47h+var_A0]
0x18003c8cb  mov     [rsp+110h+var_F0], rax; int
0x18003c8d0  lea     r9, [rbp+47h+var_90]; int
0x18003c8d4  mov     r8d, esi; int
0x18003c8d7  mov     rcx, r14; int
0x18003c8da  call    CEndpointCharacteristics__GetDefaultFormat__lambda_8e14c3ef8ca8112e9c42aed54b541fda___
0x18003c8df  mov     edi, eax
0x18003c8e1  lea     rcx, [rbp+47h+var_A8]
0x18003c8e5  call    ??1?$out_param_t@V?$unique_ptr@U_GUID@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>(void)
0x18003c8ea  test    edi, edi
0x18003c8ec  jns     short loc_18003C923
0x18003c8ee  mov     ebx, 88890004h
0x18003c8f3  cmp     edi, ebx
0x18003c8f5  jz      loc_18003C854
0x18003c8fb  mov     rcx, [rbp+4Fh]; this
0x18003c8ff  mov     r9d, edi; char *
0x18003c902  lea     r8, aAvcoreAudiocor_53; "avcore\\audiocore\\server\\lib\\audiose"...
0x18003c909  mov     edx, 19D8h; void *
0x18003c90e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003c913  nop
0x18003c914  lea     rcx, [rbp+47h+pvar]; pvar
0x18003c918  call    cs:__imp_PropVariantClear
0x18003c91e  jmp     loc_18003C70F
0x18003c923  mov     r9, [rsp+110h+pv]; struct tWAVEFORMATEX *
0x18003c928  mov     r8d, esi; enum __MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001
0x18003c92b  mov     dl, r15b; bool
0x18003c92e  mov     rcx, r14; this
0x18003c931  call    ?UpdateDeviceFormatEPProperty@CEndpointCharacteristics@@QEAAJ_NW4__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001@@PEBUtWAVEFORMATEX@@@Z; CEndpointCharacteristics::UpdateDeviceFormatEPProperty(bool,__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001,tWAVEFORMATEX const *)
0x18003c936  mov     ebx, eax
0x18003c938  test    eax, eax
0x18003c93a  jns     short loc_18003C946
0x18003c93c  mov     edx, 19DBh
0x18003c941  jmp     loc_18003C840
0x18003c946  lea     rcx, [rbp+47h+pvar]; pvar
0x18003c94a  call    cs:__imp_PropVariantClear
0x18003c950  mov     rcx, [rsp+110h+pv]; struct tWAVEFORMATEX *
0x18003c955  call    ?ValidateWaveFormatEx@@YAJPEBUtWAVEFORMATEX@@@Z; ValidateWaveFormatEx(tWAVEFORMATEX const *)
0x18003c95a  mov     ebx, eax
0x18003c95c  test    eax, eax
0x18003c95e  jns     short loc_18003C97D
0x18003c960  mov     rcx, [rbp+4Fh]; this
0x18003c964  mov     r9d, eax; char *
0x18003c967  lea     r8, aAvcoreAudiocor_53; "avcore\\audiocore\\server\\lib\\audiose"...
0x18003c96e  mov     edx, 19E0h; void *
0x18003c973  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003c978  jmp     loc_18003C85F
0x18003c97d  mov     rax, [rsp+110h+pv]
0x18003c982  mov     [r12], rax
0x18003c986  xor     eax, eax
0x18003c988  mov     rcx, [rbp+47h+var_38]
0x18003c98c  xor     rcx, rsp; StackCookie
0x18003c98f  call    __security_check_cookie
0x18003c994  mov     rbx, [rsp+110h+arg_8]
0x18003c99c  add     rsp, 0E0h
0x18003c9a3  pop     r15
0x18003c9a5  pop     r14
0x18003c9a7  pop     r13
0x18003c9a9  pop     r12
0x18003c9ab  pop     rdi
0x18003c9ac  pop     rsi
0x18003c9ad  pop     rbp
0x18003c9ae  retn
```
