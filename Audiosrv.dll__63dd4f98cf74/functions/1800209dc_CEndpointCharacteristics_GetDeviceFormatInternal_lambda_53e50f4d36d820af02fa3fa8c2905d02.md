# CEndpointCharacteristics::GetDeviceFormatInternal__lambda_53e50f4d36d820af02fa3fa8c2905d02___

- ea: `0x1800209dc`
- end: `0x180020d26`
- name: `CEndpointCharacteristics::GetDeviceFormatInternal__lambda_53e50f4d36d820af02fa3fa8c2905d02___`
- size: `842`
- prototype: `__int64 __fastcall(CEndpointCharacteristics *this, char, unsigned __int8, int, _OWORD *, LPVOID *)`
- caller_count: `3`
- callee_count: `14`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x1800202b0`
- `0x1800208b0`
- `0x180026f04`

## callees

- `0x180008a2c`
- `0x18001280c`
- `0x1800209dc`
- `0x18002318c`
- `0x18003a020`
- `0x18003c9b8`
- `0x18003d040`
- `0x18004f298`
- `0x18008a9a8`
- `0x1800cbfcc`
- `0x1800cd8d0`
- `0x1801445dc`
- `0x180144600`
- `0x18016c010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180020bd0`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180020c92`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180020cc3`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180020bd0`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180020c92`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180020cc3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180020aa8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180020be4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180020c5e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180020aa8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180020be4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180020c5e`

## string_xrefs

- `0x180020a89`: `avcore\audiocore\server\lib\audioserviceutil\endpointcharacteristics.cpp`
- `0x180020b0d`: `avcore\audiocore\server\lib\audioserviceutil\endpointcharacteristics.cpp`
- `0x180020b52`: `avcore\audiocore\server\lib\audioserviceutil\endpointcharacteristics.cpp`
- `0x180020bb8`: `avcore\audiocore\server\lib\audioserviceutil\endpointcharacteristics.cpp`
- `0x180020c7c`: `avcore\audiocore\server\lib\audioserviceutil\endpointcharacteristics.cpp`
- `0x180020cdf`: `avcore\audiocore\server\lib\audioserviceutil\endpointcharacteristics.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall CEndpointCharacteristics::GetDeviceFormatInternal__lambda_53e50f4d36d820af02fa3fa8c2905d02___(
        CEndpointCharacteristics *this,
        char a2,
        unsigned __int8 a3,
        int a4,
        _OWORD *a5,
        LPVOID *a6)
{
  int v7; // r15d
  int DefaultFormat__lambda_53e50f4d36d820af02fa3fa8c2905d02; // edi
  int updated; // ebx
  void *v11; // rcx
  GUID fmtid; // xmm0
  DWORD pid; // eax
  int v15; // eax
  unsigned int v16; // r8d
  const char *v17; // r9
  const struct tWAVEFORMATEX *v18; // rbx
  __int64 v19; // rdx
  void *v20; // rcx
  bool v21; // zf
  void *v22; // rcx
  int v23; // eax
  unsigned int v24; // [rsp+20h] [rbp-89h]
  char *v25; // [rsp+28h] [rbp-81h]
  LPVOID pv; // [rsp+40h] [rbp-69h] BYREF
  LPVOID *p_pv; // [rsp+48h] [rbp-61h] BYREF
  struct tWAVEFORMATEX *v28; // [rsp+50h] [rbp-59h] BYREF
  char v29; // [rsp+58h] [rbp-51h]
  PROPVARIANT pvar[2]; // [rsp+60h] [rbp-49h] BYREF
  struct tWAVEFORMATEX *Src[2]; // [rsp+70h] [rbp-39h]
  int v32[4]; // [rsp+80h] [rbp-29h] BYREF
  __int128 v33; // [rsp+90h] [rbp-19h]
  GUID v34; // [rsp+A0h] [rbp-9h] BYREF
  DWORD v35; // [rsp+B0h] [rbp+7h]
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+4Fh]

  v7 = a3;
  *a6 = 0;
  pv = 0;
  if ( !a2 )
  {
    if ( a4 == 3 )
    {
      fmtid = (GUID)PKEY_AudioEngine_KeywordDetector_DeviceFormat;
      pid = 0;
    }
    else
    {
      fmtid = PKEY_AudioEngine_DeviceFormat.fmtid;
      pid = PKEY_AudioEngine_DeviceFormat.pid;
    }
    v34 = fmtid;
    v35 = pid;
    *(_OWORD *)pvar = 0;
    Src[0] = 0;
    v15 = (*(__int64 (__fastcall **)(_QWORD, GUID *, PROPVARIANT *))(**((_QWORD **)this + 9) + 40LL))(
            *((_QWORD *)this + 9),
            &v34,
            pvar);
    if ( v15 >= 0 )
    {
      if ( LOWORD(pvar[0]) )
      {
        if ( LOWORD(pvar[0]) == 65 )
        {
          if ( IsValidWfxBlob((struct tagPROPVARIANT *)pvar) )
          {
            v18 = Src[0];
            if ( (unsigned __int8)lambda_53e50f4d36d820af02fa3fa8c2905d02_::operator()(a5, Src[0]) )
            {
              p_pv = &pv;
              v28 = 0;
              v29 = 1;
              updated = CloneWaveFormat(v18, &v28);
              wil::details::out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>(&p_pv);
              if ( updated < 0 )
              {
                v19 = 6592;
                goto LABEL_20;
              }
            }
          }
          else
          {
            wil::details::in1diag3::Log_Win32(retaddr, (void *)0x19C5, v16, v17, v24);
          }
        }
        else
        {
          LODWORD(v25) = LOWORD(pvar[0]);
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
        (const char *)(unsigned int)v15,
        v24);
    }
    if ( pv )
      goto LABEL_35;
    p_pv = &pv;
    v28 = 0;
    v29 = 1;
    *(_OWORD *)v32 = *a5;
    v33 = a5[1];
    DefaultFormat__lambda_53e50f4d36d820af02fa3fa8c2905d02 = CEndpointCharacteristics::GetDefaultFormat__lambda_53e50f4d36d820af02fa3fa8c2905d02___(
                                                               (int)this,
                                                               v7,
                                                               a4,
                                                               (int)v32,
                                                               &v28);
    if ( v29 )
    {
      v22 = *p_pv;
      *p_pv = v28;
      if ( v22 )
        CoTaskMemFree(v22);
    }
    if ( DefaultFormat__lambda_53e50f4d36d820af02fa3fa8c2905d02 < 0 )
    {
      updated = -2004287484;
      if ( DefaultFormat__lambda_53e50f4d36d820af02fa3fa8c2905d02 != -2004287484 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x19D8,
          (unsigned int)"avcore\\audiocore\\server\\lib\\audioserviceutil\\endpointcharacteristics.cpp",
          (const char *)(unsigned int)DefaultFormat__lambda_53e50f4d36d820af02fa3fa8c2905d02,
          v24);
        PropVariantClear(pvar);
        goto LABEL_5;
      }
      goto LABEL_21;
    }
    updated = CEndpointCharacteristics::UpdateDeviceFormatEPProperty(this, v7, a4, (const struct tWAVEFORMATEX *)pv);
    if ( updated >= 0 )
    {
LABEL_35:
      PropVariantClear(pvar);
      goto LABEL_36;
    }
    v19 = 6619;
LABEL_20:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v19,
      (unsigned int)"avcore\\audiocore\\server\\lib\\audioserviceutil\\endpointcharacteristics.cpp",
      (const char *)(unsigned int)updated,
      v24);
LABEL_21:
    PropVariantClear(pvar);
    goto LABEL_22;
  }
  p_pv = &pv;
  v28 = 0;
  v29 = 1;
  *(_OWORD *)pvar = *a5;
  *(_OWORD *)Src = a5[1];
  DefaultFormat__lambda_53e50f4d36d820af02fa3fa8c2905d02 = CEndpointCharacteristics::GetDefaultFormat__lambda_53e50f4d36d820af02fa3fa8c2905d02___(
                                                             (int)this,
                                                             a3,
                                                             a4,
                                                             (int)pvar,
                                                             &v28);
  wil::details::out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>(&p_pv);
  if ( DefaultFormat__lambda_53e50f4d36d820af02fa3fa8c2905d02 >= 0 )
  {
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
    goto LABEL_22;
  }
  updated = -2004287484;
  if ( DefaultFormat__lambda_53e50f4d36d820af02fa3fa8c2905d02 != -2004287484 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x19AB,
      (unsigned int)"avcore\\audiocore\\server\\lib\\audioserviceutil\\endpointcharacteristics.cpp",
      (const char *)(unsigned int)DefaultFormat__lambda_53e50f4d36d820af02fa3fa8c2905d02,
      v24);
LABEL_5:
    v11 = pv;
    pv = 0;
    if ( v11 )
      CoTaskMemFree(v11);
    return (unsigned int)DefaultFormat__lambda_53e50f4d36d820af02fa3fa8c2905d02;
  }
LABEL_22:
  v20 = pv;
  v21 = pv == 0;
  pv = 0;
  if ( !v21 )
    CoTaskMemFree(v20);
  return (unsigned int)updated;
}

```

## disassembly

```asm
0x1800209dc  mov     [rsp-8+arg_8], rbx
0x1800209e1  push    rbp
0x1800209e2  push    rsi
0x1800209e3  push    rdi
0x1800209e4  push    r12
0x1800209e6  push    r13
0x1800209e8  push    r14
0x1800209ea  push    r15
0x1800209ec  lea     rbp, [rsp-17h]
0x1800209f1  sub     rsp, 0C0h
0x1800209f8  mov     rax, cs:__security_cookie
0x1800209ff  xor     rax, rsp
0x180020a02  mov     [rbp+47h+var_38], rax
0x180020a06  mov     esi, r9d
0x180020a09  movzx   r15d, r8b
0x180020a0d  mov     r14, rcx
0x180020a10  mov     rdi, [rbp+47h+arg_20]
0x180020a14  mov     r12, [rbp+47h+arg_28]
0x180020a18  xor     r13d, r13d
0x180020a1b  mov     [r12], r13
0x180020a1f  mov     [rbp+47h+pv], r13
0x180020a23  test    dl, dl
0x180020a25  jz      loc_180020AB5
0x180020a2b  lea     rax, [rbp+47h+pv]
0x180020a2f  mov     [rbp+47h+var_A8], rax
0x180020a33  mov     [rbp+47h+var_A0], r13
0x180020a37  mov     [rbp+47h+var_98], 1
0x180020a3b  movaps  xmm0, xmmword ptr [rdi]
0x180020a3e  movaps  xmmword ptr [rbp+47h+pvar], xmm0
0x180020a42  movaps  xmm1, xmmword ptr [rdi+10h]
0x180020a46  movaps  xmmword ptr [rbp+47h+Src], xmm1
0x180020a4a  mov     edx, r15d; int
0x180020a4d  lea     rax, [rbp+47h+var_A0]
0x180020a51  mov     [rsp+0F0h+var_D0], rax; int
0x180020a56  lea     r9, [rbp+47h+pvar]; int
0x180020a5a  mov     r8d, esi; int
0x180020a5d  call    CEndpointCharacteristics__GetDefaultFormat__lambda_53e50f4d36d820af02fa3fa8c2905d02___
0x180020a62  mov     edi, eax
0x180020a64  lea     rcx, [rbp+47h+var_A8]
0x180020a68  call    ??1?$out_param_t@V?$unique_ptr@U_GUID@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>(void)
0x180020a6d  test    edi, edi
0x180020a6f  jns     loc_180020CC9
0x180020a75  mov     ebx, 88890004h
0x180020a7a  cmp     edi, ebx
0x180020a7c  jz      loc_180020BD7
0x180020a82  mov     rcx, [rbp+4Fh]; this
0x180020a86  mov     r9d, edi; char *
0x180020a89  lea     r8, aAvcoreAudiocor_53; "avcore\\audiocore\\server\\lib\\audiose"...
0x180020a90  mov     edx, 19ABh; void *
0x180020a95  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180020a9a  nop
0x180020a9b  mov     rcx, [rbp+47h+pv]; pv
0x180020a9f  mov     [rbp+47h+pv], r13
0x180020aa3  test    rcx, rcx
0x180020aa6  jz      short loc_180020AAE
0x180020aa8  call    cs:__imp_CoTaskMemFree
0x180020aae  mov     eax, edi
0x180020ab0  jmp     loc_180020CFF
0x180020ab5  cmp     esi, 3
0x180020ab8  jnz     short loc_180020AC9
0x180020aba  movups  xmm0, cs:PKEY_AudioEngine_KeywordDetector_DeviceFormat
0x180020ac1  mov     eax, cs:dword_18018AAD8
0x180020ac7  jmp     short loc_180020AD6
0x180020ac9  movups  xmm0, xmmword ptr cs:PKEY_AudioEngine_DeviceFormat.fmtid.Data1
0x180020ad0  mov     eax, cs:PKEY_AudioEngine_DeviceFormat.pid
0x180020ad6  movups  [rbp+47h+var_50], xmm0
0x180020ada  mov     [rbp+47h+var_40], eax
0x180020add  xorps   xmm0, xmm0
0x180020ae0  xor     eax, eax
0x180020ae2  movups  xmmword ptr [rbp+47h+pvar], xmm0
0x180020ae6  mov     [rbp+47h+Src], rax
0x180020aea  mov     rcx, [rcx+48h]
0x180020aee  mov     rax, [rcx]
0x180020af1  lea     r8, [rbp+47h+pvar]
0x180020af5  lea     rdx, [rbp+47h+var_50]
0x180020af9  mov     rax, [rax+28h]
0x180020afd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020b02  mov     rcx, [rbp+4Fh]; this
0x180020b06  test    eax, eax
0x180020b08  jns     short loc_180020B23
0x180020b0a  mov     r9d, eax; char *
0x180020b0d  lea     r8, aAvcoreAudiocor_53; "avcore\\audiocore\\server\\lib\\audiose"...
0x180020b14  mov     edx, 19B4h; void *
0x180020b19  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180020b1e  jmp     loc_180020BFF
0x180020b23  movzx   eax, word ptr [rbp+47h+pvar]
0x180020b27  test    eax, eax
0x180020b29  jz      loc_180020BFF
0x180020b2f  cmp     eax, 41h ; 'A'
0x180020b32  jz      short loc_180020B68
0x180020b34  mov     rcx, [rbp+4Fh]; this
0x180020b38  mov     [rsp+0F0h+var_C0], eax
0x180020b3c  mov     dword ptr [rsp+0F0h+var_C8], eax; char *
0x180020b40  lea     rax, aUnexpectedVart_1; "Unexpected vartype %d (0x%08x)"
0x180020b47  mov     [rsp+0F0h+var_D0], rax; unsigned int
0x180020b4c  mov     r9d, 0Dh; char *
0x180020b52  lea     r8, aAvcoreAudiocor_53; "avcore\\audiocore\\server\\lib\\audiose"...
0x180020b59  mov     edx, 19D1h; void *
0x180020b5e  call    ?Log_Win32Msg@in1diag3@details@wil@@YAKPEAXIPEBDK1ZZ; wil::details::in1diag3::Log_Win32Msg(void *,uint,char const *,ulong,char const *,...)
0x180020b63  jmp     loc_180020BFF
0x180020b68  lea     rcx, [rbp+47h+pvar]; struct tagPROPVARIANT *
0x180020b6c  call    ?IsValidWfxBlob@@YAHPEAUtagPROPVARIANT@@@Z; IsValidWfxBlob(tagPROPVARIANT *)
0x180020b71  test    eax, eax
0x180020b73  jz      short loc_180020BF1
0x180020b75  mov     rbx, [rbp+47h+Src]
0x180020b79  mov     rdx, rbx
0x180020b7c  mov     rcx, rdi
0x180020b7f  call    _lambda_53e50f4d36d820af02fa3fa8c2905d02___operator__
0x180020b84  test    al, al
0x180020b86  jz      short loc_180020BFF
0x180020b88  lea     rax, [rbp+47h+pv]
0x180020b8c  mov     [rbp+47h+var_A8], rax
0x180020b90  mov     [rbp+47h+var_A0], r13
0x180020b94  mov     [rbp+47h+var_98], 1
0x180020b98  lea     rdx, [rbp+47h+var_A0]; struct tWAVEFORMATEX **
0x180020b9c  mov     rcx, rbx; Src
0x180020b9f  call    ?CloneWaveFormat@@YAJPEBUtWAVEFORMATEX@@PEAPEAU1@@Z; CloneWaveFormat(tWAVEFORMATEX const *,tWAVEFORMATEX * *)
0x180020ba4  mov     ebx, eax
0x180020ba6  lea     rcx, [rbp+47h+var_A8]
0x180020baa  call    ??1?$out_param_t@V?$unique_ptr@U_GUID@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>(void)
0x180020baf  test    ebx, ebx
0x180020bb1  jns     short loc_180020BFF
0x180020bb3  mov     edx, 19C0h; void *
0x180020bb8  lea     r8, aAvcoreAudiocor_53; "avcore\\audiocore\\server\\lib\\audiose"...
0x180020bbf  mov     r9d, ebx; char *
0x180020bc2  mov     rcx, [rbp+4Fh]; this
0x180020bc6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180020bcb  nop
0x180020bcc  lea     rcx, [rbp+47h+pvar]; pvar
0x180020bd0  call    cs:__imp_PropVariantClear
0x180020bd6  nop
0x180020bd7  mov     rcx, [rbp+47h+pv]; pv
0x180020bdb  test    rcx, rcx
0x180020bde  mov     [rbp+47h+pv], r13
0x180020be2  jz      short loc_180020BEA
0x180020be4  call    cs:__imp_CoTaskMemFree
0x180020bea  mov     eax, ebx
0x180020bec  jmp     loc_180020CFF
0x180020bf1  mov     rcx, [rbp+4Fh]; this
0x180020bf5  mov     edx, 19C5h; void *
0x180020bfa  call    ?Log_Win32@in1diag3@details@wil@@YAKPEAXIPEBDK@Z; wil::details::in1diag3::Log_Win32(void *,uint,char const *,ulong)
0x180020bff  cmp     [rbp+47h+pv], r13
0x180020c03  jnz     loc_180020CBF
0x180020c09  lea     rax, [rbp+47h+pv]
0x180020c0d  mov     [rbp+47h+var_A8], rax
0x180020c11  mov     [rbp+47h+var_A0], r13
0x180020c15  mov     [rbp+47h+var_98], 1
0x180020c19  movaps  xmm0, xmmword ptr [rdi]
0x180020c1c  movaps  xmmword ptr [rbp+47h+var_70], xmm0
0x180020c20  movaps  xmm1, xmmword ptr [rdi+10h]
0x180020c24  movaps  [rbp+47h+var_60], xmm1
0x180020c28  mov     edx, r15d; int
0x180020c2b  lea     rax, [rbp+47h+var_A0]
0x180020c2f  mov     [rsp+0F0h+var_D0], rax; int
0x180020c34  lea     r9, [rbp+47h+var_70]; int
0x180020c38  mov     r8d, esi; int
0x180020c3b  mov     rcx, r14; int
0x180020c3e  call    CEndpointCharacteristics__GetDefaultFormat__lambda_53e50f4d36d820af02fa3fa8c2905d02___
0x180020c43  mov     edi, eax
0x180020c45  cmp     [rbp+47h+var_98], r13b
0x180020c49  jz      short loc_180020C64
0x180020c4b  mov     r8, [rbp+47h+var_A8]
0x180020c4f  mov     rcx, [r8]; pv
0x180020c52  mov     rdx, [rbp+47h+var_A0]
0x180020c56  mov     [r8], rdx
0x180020c59  test    rcx, rcx
0x180020c5c  jz      short loc_180020C64
0x180020c5e  call    cs:__imp_CoTaskMemFree
0x180020c64  test    edi, edi
0x180020c66  jns     short loc_180020C9D
0x180020c68  mov     ebx, 88890004h
0x180020c6d  cmp     edi, ebx
0x180020c6f  jz      loc_180020BCC
0x180020c75  mov     rcx, [rbp+4Fh]; this
0x180020c79  mov     r9d, edi; char *
0x180020c7c  lea     r8, aAvcoreAudiocor_53; "avcore\\audiocore\\server\\lib\\audiose"...
0x180020c83  mov     edx, 19D8h; void *
0x180020c88  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180020c8d  nop
0x180020c8e  lea     rcx, [rbp+47h+pvar]; pvar
0x180020c92  call    cs:__imp_PropVariantClear
0x180020c98  jmp     loc_180020A9B
0x180020c9d  mov     r9, [rbp+47h+pv]; struct tWAVEFORMATEX *
0x180020ca1  mov     r8d, esi; enum __MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001
0x180020ca4  mov     dl, r15b; bool
0x180020ca7  mov     rcx, r14; this
0x180020caa  call    ?UpdateDeviceFormatEPProperty@CEndpointCharacteristics@@QEAAJ_NW4__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001@@PEBUtWAVEFORMATEX@@@Z; CEndpointCharacteristics::UpdateDeviceFormatEPProperty(bool,__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001,tWAVEFORMATEX const *)
0x180020caf  mov     ebx, eax
0x180020cb1  test    eax, eax
0x180020cb3  jns     short loc_180020CBF
0x180020cb5  mov     edx, 19DBh
0x180020cba  jmp     loc_180020BB8
0x180020cbf  lea     rcx, [rbp+47h+pvar]; pvar
0x180020cc3  call    cs:__imp_PropVariantClear
0x180020cc9  mov     rcx, [rbp+47h+pv]; struct tWAVEFORMATEX *
0x180020ccd  call    ?ValidateWaveFormatEx@@YAJPEBUtWAVEFORMATEX@@@Z; ValidateWaveFormatEx(tWAVEFORMATEX const *)
0x180020cd2  mov     ebx, eax
0x180020cd4  test    eax, eax
0x180020cd6  jns     short loc_180020CF5
0x180020cd8  mov     rcx, [rbp+4Fh]; this
0x180020cdc  mov     r9d, eax; char *
0x180020cdf  lea     r8, aAvcoreAudiocor_53; "avcore\\audiocore\\server\\lib\\audiose"...
0x180020ce6  mov     edx, 19E0h; void *
0x180020ceb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180020cf0  jmp     loc_180020BD7
0x180020cf5  mov     rax, [rbp+47h+pv]
0x180020cf9  mov     [r12], rax
0x180020cfd  xor     eax, eax
0x180020cff  mov     rcx, [rbp+47h+var_38]
0x180020d03  xor     rcx, rsp; StackCookie
0x180020d06  call    __security_check_cookie
0x180020d0b  mov     rbx, [rsp+0F0h+arg_8]
0x180020d13  add     rsp, 0C0h
0x180020d1a  pop     r15
0x180020d1c  pop     r14
0x180020d1e  pop     r13
0x180020d20  pop     r12
0x180020d22  pop     rdi
0x180020d23  pop     rsi
0x180020d24  pop     rbp
0x180020d25  retn
```
