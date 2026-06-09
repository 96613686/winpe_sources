# CEndpointCharacteristics::GetDeviceFormatInternal__lambda_8e14c3ef8ca8112e9c42aed54b541fda___

- ea: `0x18003c4c8`
- end: `0x18003c84f`
- name: `CEndpointCharacteristics::GetDeviceFormatInternal__lambda_8e14c3ef8ca8112e9c42aed54b541fda___`
- size: `903`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x18003a8f0`

## callees

- `0x1800088dc`
- `0x1800126bc`
- `0x18002303c`
- `0x18003afe0`
- `0x18003c4c8`
- `0x18003caf8`
- `0x18003cee0`
- `0x1800423fc`
- `0x18004f728`
- `0x1800cdfbc`
- `0x1800cf8c0`
- `0x180143ccc`
- `0x180143cf0`
- `0x18016b010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18003c6f8`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18003c7b8`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18003c7ea`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18003c6f8`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18003c7b8`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18003c7ea`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003c57b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003c5be`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003c70e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003c57b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003c5be`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003c70e`

## string_xrefs

- `0x18003c59d`: `avcore\audiocore\server\lib\audioserviceutil\endpointcharacteristics.cpp`
- `0x18003c623`: `avcore\audiocore\server\lib\audioserviceutil\endpointcharacteristics.cpp`
- `0x18003c668`: `avcore\audiocore\server\lib\audioserviceutil\endpointcharacteristics.cpp`
- `0x18003c6e0`: `avcore\audiocore\server\lib\audioserviceutil\endpointcharacteristics.cpp`
- `0x18003c7a2`: `avcore\audiocore\server\lib\audioserviceutil\endpointcharacteristics.cpp`
- `0x18003c807`: `avcore\audiocore\server\lib\audioserviceutil\endpointcharacteristics.cpp`

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
                v20 = 6593;
                goto LABEL_23;
              }
            }
          }
          else
          {
            wil::details::in1diag3::Log_Win32(retaddr, (void *)0x19C6, v17, v18, v24);
          }
        }
        else
        {
          LODWORD(v25) = pvar.vt;
          wil::details::in1diag3::Log_Win32Msg(
            retaddr,
            (void *)0x19D2,
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
        (void *)0x19B5,
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
          (void *)0x19D9,
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
        (void *)0x19E1,
        (unsigned int)"avcore\\audiocore\\server\\lib\\audioserviceutil\\endpointcharacteristics.cpp",
        (const char *)(unsigned int)v23,
        v24);
      goto LABEL_25;
    }
    v20 = 6620;
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
      (void *)0x19AC,
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
0x18003c4c8  mov     [rsp-8+arg_8], rbx
0x18003c4cd  push    rbp
0x18003c4ce  push    rsi
0x18003c4cf  push    rdi
0x18003c4d0  push    r12
0x18003c4d2  push    r13
0x18003c4d4  push    r14
0x18003c4d6  push    r15
0x18003c4d8  lea     rbp, [rsp-17h]
0x18003c4dd  sub     rsp, 0E0h
0x18003c4e4  mov     rax, cs:__security_cookie
0x18003c4eb  xor     rax, rsp
0x18003c4ee  mov     [rbp+47h+var_38], rax
0x18003c4f2  mov     esi, r9d
0x18003c4f5  movzx   r15d, r8b
0x18003c4f9  mov     r14, rcx
0x18003c4fc  mov     rdi, [rbp+47h+arg_20]
0x18003c500  mov     r12, [rbp+47h+arg_28]
0x18003c504  xor     r13d, r13d
0x18003c507  mov     [r12], r13
0x18003c50b  mov     [rsp+110h+pv], r13
0x18003c510  test    dl, dl
0x18003c512  jz      loc_18003C5CB
0x18003c518  lea     rax, [rsp+110h+pv]
0x18003c51d  mov     [rbp+47h+pvar], rax
0x18003c521  mov     [rbp+47h+pvar+8], r13
0x18003c525  mov     byte ptr [rbp+47h+Src], 1
0x18003c529  movaps  xmm0, xmmword ptr [rdi]
0x18003c52c  movaps  xmmword ptr [rbp+47h+var_90], xmm0
0x18003c530  movaps  xmm1, xmmword ptr [rdi+10h]
0x18003c534  movaps  [rbp+47h+var_80], xmm1
0x18003c538  movaps  xmm0, xmmword ptr [rdi+20h]
0x18003c53c  movaps  [rbp+47h+var_70], xmm0
0x18003c540  movaps  xmm1, xmmword ptr [rdi+30h]
0x18003c544  movaps  [rbp+47h+var_60], xmm1
0x18003c548  mov     edx, r15d; int
0x18003c54b  lea     rax, [rbp+47h+pvar+8]
0x18003c54f  mov     [rsp+110h+var_F0], rax; int
0x18003c554  lea     r9, [rbp+47h+var_90]; int
0x18003c558  mov     r8d, esi; int
0x18003c55b  call    CEndpointCharacteristics__GetDefaultFormat__lambda_8e14c3ef8ca8112e9c42aed54b541fda___
0x18003c560  mov     edi, eax
0x18003c562  cmp     byte ptr [rbp+47h+Src], r13b
0x18003c566  jz      short loc_18003C581
0x18003c568  mov     r8, [rbp+47h+pvar]
0x18003c56c  mov     rcx, [r8]; pv
0x18003c56f  mov     rdx, [rbp+47h+pvar+8]
0x18003c573  mov     [r8], rdx
0x18003c576  test    rcx, rcx
0x18003c579  jz      short loc_18003C581
0x18003c57b  call    cs:__imp_CoTaskMemFree
0x18003c581  test    edi, edi
0x18003c583  jns     loc_18003C7F0
0x18003c589  mov     ebx, 88890004h
0x18003c58e  cmp     edi, ebx
0x18003c590  jz      loc_18003C6FF
0x18003c596  mov     rcx, [rbp+4Fh]; this
0x18003c59a  mov     r9d, edi; char *
0x18003c59d  lea     r8, aAvcoreAudiocor_52; "avcore\\audiocore\\server\\lib\\audiose"...
0x18003c5a4  mov     edx, 19ACh; void *
0x18003c5a9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003c5ae  nop
0x18003c5af  mov     rcx, [rsp+110h+pv]; pv
0x18003c5b4  mov     [rsp+110h+pv], r13
0x18003c5b9  test    rcx, rcx
0x18003c5bc  jz      short loc_18003C5C4
0x18003c5be  call    cs:__imp_CoTaskMemFree
0x18003c5c4  mov     eax, edi
0x18003c5c6  jmp     loc_18003C828
0x18003c5cb  cmp     esi, 3
0x18003c5ce  jnz     short loc_18003C5DF
0x18003c5d0  movups  xmm0, cs:PKEY_AudioEngine_KeywordDetector_DeviceFormat
0x18003c5d7  mov     eax, cs:dword_180189A88
0x18003c5dd  jmp     short loc_18003C5EC
0x18003c5df  movups  xmm0, xmmword ptr cs:PKEY_AudioEngine_DeviceFormat.fmtid.Data1
0x18003c5e6  mov     eax, cs:PKEY_AudioEngine_DeviceFormat.pid
0x18003c5ec  movups  [rbp+47h+var_50], xmm0
0x18003c5f0  mov     [rbp+47h+var_40], eax
0x18003c5f3  xorps   xmm0, xmm0
0x18003c5f6  xor     eax, eax
0x18003c5f8  movups  xmmword ptr [rbp+47h+pvar], xmm0
0x18003c5fc  mov     [rbp+47h+Src], rax
0x18003c600  mov     rcx, [rcx+48h]
0x18003c604  mov     rax, [rcx]
0x18003c607  lea     r8, [rbp+47h+pvar]
0x18003c60b  lea     rdx, [rbp+47h+var_50]
0x18003c60f  mov     rax, [rax+28h]
0x18003c613  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c618  mov     rcx, [rbp+4Fh]; this
0x18003c61c  test    eax, eax
0x18003c61e  jns     short loc_18003C639
0x18003c620  mov     r9d, eax; char *
0x18003c623  lea     r8, aAvcoreAudiocor_52; "avcore\\audiocore\\server\\lib\\audiose"...
0x18003c62a  mov     edx, 19B5h; void *
0x18003c62f  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18003c634  jmp     loc_18003C729
0x18003c639  movzx   eax, word ptr [rbp+47h+pvar]
0x18003c63d  test    eax, eax
0x18003c63f  jz      loc_18003C729
0x18003c645  cmp     eax, 41h ; 'A'
0x18003c648  jz      short loc_18003C67E
0x18003c64a  mov     rcx, [rbp+4Fh]; this
0x18003c64e  mov     [rsp+110h+var_E0], eax
0x18003c652  mov     dword ptr [rsp+110h+var_E8], eax; char *
0x18003c656  lea     rax, aUnexpectedVart_1; "Unexpected vartype %d (0x%08x)"
0x18003c65d  mov     [rsp+110h+var_F0], rax; unsigned int
0x18003c662  mov     r9d, 0Dh; char *
0x18003c668  lea     r8, aAvcoreAudiocor_52; "avcore\\audiocore\\server\\lib\\audiose"...
0x18003c66f  mov     edx, 19D2h; void *
0x18003c674  call    ?Log_Win32Msg@in1diag3@details@wil@@YAKPEAXIPEBDK1ZZ; wil::details::in1diag3::Log_Win32Msg(void *,uint,char const *,ulong,char const *,...)
0x18003c679  jmp     loc_18003C729
0x18003c67e  lea     rcx, [rbp+47h+pvar]; struct tagPROPVARIANT *
0x18003c682  call    ?IsValidWfxBlob@@YAHPEAUtagPROPVARIANT@@@Z; IsValidWfxBlob(tagPROPVARIANT *)
0x18003c687  test    eax, eax
0x18003c689  jz      loc_18003C71B
0x18003c68f  mov     rbx, [rbp+47h+Src]
0x18003c693  mov     [rsp+110h+var_D0], r13b
0x18003c698  lea     r8, [rsp+110h+var_D0]
0x18003c69d  mov     rdx, rbx
0x18003c6a0  mov     rcx, rdi
0x18003c6a3  call    _lambda_5789e60fd85b99cd3c89d9f341e01d71___operator__
0x18003c6a8  cmp     [rsp+110h+var_D0], r13b
0x18003c6ad  jz      short loc_18003C729
0x18003c6af  lea     rax, [rsp+110h+pv]
0x18003c6b4  mov     [rbp+47h+var_A8], rax
0x18003c6b8  mov     [rbp+47h+var_A0], r13
0x18003c6bc  mov     [rbp+47h+var_98], 1
0x18003c6c0  lea     rdx, [rbp+47h+var_A0]; struct tWAVEFORMATEX **
0x18003c6c4  mov     rcx, rbx; Src
0x18003c6c7  call    ?CloneWaveFormat@@YAJPEBUtWAVEFORMATEX@@PEAPEAU1@@Z; CloneWaveFormat(tWAVEFORMATEX const *,tWAVEFORMATEX * *)
0x18003c6cc  mov     ebx, eax
0x18003c6ce  lea     rcx, [rbp+47h+var_A8]
0x18003c6d2  call    ??1?$out_param_t@V?$unique_ptr@U_GUID@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>(void)
0x18003c6d7  test    ebx, ebx
0x18003c6d9  jns     short loc_18003C729
0x18003c6db  mov     edx, 19C1h; void *
0x18003c6e0  lea     r8, aAvcoreAudiocor_52; "avcore\\audiocore\\server\\lib\\audiose"...
0x18003c6e7  mov     r9d, ebx; char *
0x18003c6ea  mov     rcx, [rbp+4Fh]; this
0x18003c6ee  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003c6f3  nop
0x18003c6f4  lea     rcx, [rbp+47h+pvar]; pvar
0x18003c6f8  call    cs:__imp_PropVariantClear
0x18003c6fe  nop
0x18003c6ff  mov     rcx, [rsp+110h+pv]; pv
0x18003c704  test    rcx, rcx
0x18003c707  mov     [rsp+110h+pv], r13
0x18003c70c  jz      short loc_18003C714
0x18003c70e  call    cs:__imp_CoTaskMemFree
0x18003c714  mov     eax, ebx
0x18003c716  jmp     loc_18003C828
0x18003c71b  mov     rcx, [rbp+4Fh]; this
0x18003c71f  mov     edx, 19C6h; void *
0x18003c724  call    ?Log_Win32@in1diag3@details@wil@@YAKPEAXIPEBDK@Z; wil::details::in1diag3::Log_Win32(void *,uint,char const *,ulong)
0x18003c729  cmp     [rsp+110h+pv], r13
0x18003c72e  jnz     loc_18003C7E6
0x18003c734  lea     rax, [rsp+110h+pv]
0x18003c739  mov     [rbp+47h+var_A8], rax
0x18003c73d  mov     [rbp+47h+var_A0], r13
0x18003c741  mov     [rbp+47h+var_98], 1
0x18003c745  movaps  xmm0, xmmword ptr [rdi]
0x18003c748  movaps  xmmword ptr [rbp+47h+var_90], xmm0
0x18003c74c  movaps  xmm1, xmmword ptr [rdi+10h]
0x18003c750  movaps  [rbp+47h+var_80], xmm1
0x18003c754  movaps  xmm0, xmmword ptr [rdi+20h]
0x18003c758  movaps  [rbp+47h+var_70], xmm0
0x18003c75c  movaps  xmm1, xmmword ptr [rdi+30h]
0x18003c760  movaps  [rbp+47h+var_60], xmm1
0x18003c764  mov     edx, r15d; int
0x18003c767  lea     rax, [rbp+47h+var_A0]
0x18003c76b  mov     [rsp+110h+var_F0], rax; int
0x18003c770  lea     r9, [rbp+47h+var_90]; int
0x18003c774  mov     r8d, esi; int
0x18003c777  mov     rcx, r14; int
0x18003c77a  call    CEndpointCharacteristics__GetDefaultFormat__lambda_8e14c3ef8ca8112e9c42aed54b541fda___
0x18003c77f  mov     edi, eax
0x18003c781  lea     rcx, [rbp+47h+var_A8]
0x18003c785  call    ??1?$out_param_t@V?$unique_ptr@U_GUID@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>(void)
0x18003c78a  test    edi, edi
0x18003c78c  jns     short loc_18003C7C3
0x18003c78e  mov     ebx, 88890004h
0x18003c793  cmp     edi, ebx
0x18003c795  jz      loc_18003C6F4
0x18003c79b  mov     rcx, [rbp+4Fh]; this
0x18003c79f  mov     r9d, edi; char *
0x18003c7a2  lea     r8, aAvcoreAudiocor_52; "avcore\\audiocore\\server\\lib\\audiose"...
0x18003c7a9  mov     edx, 19D9h; void *
0x18003c7ae  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003c7b3  nop
0x18003c7b4  lea     rcx, [rbp+47h+pvar]; pvar
0x18003c7b8  call    cs:__imp_PropVariantClear
0x18003c7be  jmp     loc_18003C5AF
0x18003c7c3  mov     r9, [rsp+110h+pv]; struct tWAVEFORMATEX *
0x18003c7c8  mov     r8d, esi; enum __MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001
0x18003c7cb  mov     dl, r15b; bool
0x18003c7ce  mov     rcx, r14; this
0x18003c7d1  call    ?UpdateDeviceFormatEPProperty@CEndpointCharacteristics@@QEAAJ_NW4__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001@@PEBUtWAVEFORMATEX@@@Z; CEndpointCharacteristics::UpdateDeviceFormatEPProperty(bool,__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001,tWAVEFORMATEX const *)
0x18003c7d6  mov     ebx, eax
0x18003c7d8  test    eax, eax
0x18003c7da  jns     short loc_18003C7E6
0x18003c7dc  mov     edx, 19DCh
0x18003c7e1  jmp     loc_18003C6E0
0x18003c7e6  lea     rcx, [rbp+47h+pvar]; pvar
0x18003c7ea  call    cs:__imp_PropVariantClear
0x18003c7f0  mov     rcx, [rsp+110h+pv]; struct tWAVEFORMATEX *
0x18003c7f5  call    ?ValidateWaveFormatEx@@YAJPEBUtWAVEFORMATEX@@@Z; ValidateWaveFormatEx(tWAVEFORMATEX const *)
0x18003c7fa  mov     ebx, eax
0x18003c7fc  test    eax, eax
0x18003c7fe  jns     short loc_18003C81D
0x18003c800  mov     rcx, [rbp+4Fh]; this
0x18003c804  mov     r9d, eax; char *
0x18003c807  lea     r8, aAvcoreAudiocor_52; "avcore\\audiocore\\server\\lib\\audiose"...
0x18003c80e  mov     edx, 19E1h; void *
0x18003c813  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003c818  jmp     loc_18003C6FF
0x18003c81d  mov     rax, [rsp+110h+pv]
0x18003c822  mov     [r12], rax
0x18003c826  xor     eax, eax
0x18003c828  mov     rcx, [rbp+47h+var_38]
0x18003c82c  xor     rcx, rsp; StackCookie
0x18003c82f  call    __security_check_cookie
0x18003c834  mov     rbx, [rsp+110h+arg_8]
0x18003c83c  add     rsp, 0E0h
0x18003c843  pop     r15
0x18003c845  pop     r14
0x18003c847  pop     r13
0x18003c849  pop     r12
0x18003c84b  pop     rdi
0x18003c84c  pop     rsi
0x18003c84d  pop     rbp
0x18003c84e  retn
```
