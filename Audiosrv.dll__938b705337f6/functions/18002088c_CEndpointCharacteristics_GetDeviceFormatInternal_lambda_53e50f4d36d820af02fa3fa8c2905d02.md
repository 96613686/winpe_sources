# CEndpointCharacteristics::GetDeviceFormatInternal__lambda_53e50f4d36d820af02fa3fa8c2905d02___

- ea: `0x18002088c`
- end: `0x180020bd6`
- name: `CEndpointCharacteristics::GetDeviceFormatInternal__lambda_53e50f4d36d820af02fa3fa8c2905d02___`
- size: `842`
- prototype: ``
- caller_count: `3`
- callee_count: `14`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x180020160`
- `0x180020760`
- `0x180026da8`

## callees

- `0x1800088dc`
- `0x1800126bc`
- `0x18002088c`
- `0x18002303c`
- `0x180039ec0`
- `0x18003c858`
- `0x18003cee0`
- `0x1800423fc`
- `0x18004f728`
- `0x1800cdfbc`
- `0x1800cf8c0`
- `0x180143ccc`
- `0x180143cf0`
- `0x18016b010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180020a80`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180020b42`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180020b73`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180020a80`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180020b42`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180020b73`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180020958`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180020a94`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180020b0e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180020958`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180020a94`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180020b0e`

## string_xrefs

- `0x180020939`: `avcore\audiocore\server\lib\audioserviceutil\endpointcharacteristics.cpp`
- `0x1800209bd`: `avcore\audiocore\server\lib\audioserviceutil\endpointcharacteristics.cpp`
- `0x180020a02`: `avcore\audiocore\server\lib\audioserviceutil\endpointcharacteristics.cpp`
- `0x180020a68`: `avcore\audiocore\server\lib\audioserviceutil\endpointcharacteristics.cpp`
- `0x180020b2c`: `avcore\audiocore\server\lib\audioserviceutil\endpointcharacteristics.cpp`
- `0x180020b8f`: `avcore\audiocore\server\lib\audioserviceutil\endpointcharacteristics.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CEndpointCharacteristics::GetDeviceFormatInternal__lambda_53e50f4d36d820af02fa3fa8c2905d02___(
        CEndpointCharacteristics *this,
        char a2,
        unsigned __int8 a3,
        enum __MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001 a4,
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
          if ( (unsigned int)IsValidWfxBlob((struct tagPROPVARIANT *)pvar) )
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
                v19 = 6593;
                goto LABEL_20;
              }
            }
          }
          else
          {
            wil::details::in1diag3::Log_Win32(retaddr, (void *)0x19C6, v16, v17, v24);
          }
        }
        else
        {
          LODWORD(v25) = LOWORD(pvar[0]);
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
          (void *)0x19D9,
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
    v19 = 6620;
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
      (void *)0x19E1,
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
      (void *)0x19AC,
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
0x18002088c  mov     [rsp-8+arg_8], rbx
0x180020891  push    rbp
0x180020892  push    rsi
0x180020893  push    rdi
0x180020894  push    r12
0x180020896  push    r13
0x180020898  push    r14
0x18002089a  push    r15
0x18002089c  lea     rbp, [rsp-17h]
0x1800208a1  sub     rsp, 0C0h
0x1800208a8  mov     rax, cs:__security_cookie
0x1800208af  xor     rax, rsp
0x1800208b2  mov     [rbp+47h+var_38], rax
0x1800208b6  mov     esi, r9d
0x1800208b9  movzx   r15d, r8b
0x1800208bd  mov     r14, rcx
0x1800208c0  mov     rdi, [rbp+47h+arg_20]
0x1800208c4  mov     r12, [rbp+47h+arg_28]
0x1800208c8  xor     r13d, r13d
0x1800208cb  mov     [r12], r13
0x1800208cf  mov     [rbp+47h+pv], r13
0x1800208d3  test    dl, dl
0x1800208d5  jz      loc_180020965
0x1800208db  lea     rax, [rbp+47h+pv]
0x1800208df  mov     [rbp+47h+var_A8], rax
0x1800208e3  mov     [rbp+47h+var_A0], r13
0x1800208e7  mov     [rbp+47h+var_98], 1
0x1800208eb  movaps  xmm0, xmmword ptr [rdi]
0x1800208ee  movaps  xmmword ptr [rbp+47h+pvar], xmm0
0x1800208f2  movaps  xmm1, xmmword ptr [rdi+10h]
0x1800208f6  movaps  xmmword ptr [rbp+47h+Src], xmm1
0x1800208fa  mov     edx, r15d; int
0x1800208fd  lea     rax, [rbp+47h+var_A0]
0x180020901  mov     [rsp+0F0h+var_D0], rax; int
0x180020906  lea     r9, [rbp+47h+pvar]; int
0x18002090a  mov     r8d, esi; int
0x18002090d  call    CEndpointCharacteristics__GetDefaultFormat__lambda_53e50f4d36d820af02fa3fa8c2905d02___
0x180020912  mov     edi, eax
0x180020914  lea     rcx, [rbp+47h+var_A8]
0x180020918  call    ??1?$out_param_t@V?$unique_ptr@U_GUID@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>(void)
0x18002091d  test    edi, edi
0x18002091f  jns     loc_180020B79
0x180020925  mov     ebx, 88890004h
0x18002092a  cmp     edi, ebx
0x18002092c  jz      loc_180020A87
0x180020932  mov     rcx, [rbp+4Fh]; this
0x180020936  mov     r9d, edi; char *
0x180020939  lea     r8, aAvcoreAudiocor_52; "avcore\\audiocore\\server\\lib\\audiose"...
0x180020940  mov     edx, 19ACh; void *
0x180020945  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002094a  nop
0x18002094b  mov     rcx, [rbp+47h+pv]; pv
0x18002094f  mov     [rbp+47h+pv], r13
0x180020953  test    rcx, rcx
0x180020956  jz      short loc_18002095E
0x180020958  call    cs:__imp_CoTaskMemFree
0x18002095e  mov     eax, edi
0x180020960  jmp     loc_180020BAF
0x180020965  cmp     esi, 3
0x180020968  jnz     short loc_180020979
0x18002096a  movups  xmm0, cs:PKEY_AudioEngine_KeywordDetector_DeviceFormat
0x180020971  mov     eax, cs:dword_180189A88
0x180020977  jmp     short loc_180020986
0x180020979  movups  xmm0, xmmword ptr cs:PKEY_AudioEngine_DeviceFormat.fmtid.Data1
0x180020980  mov     eax, cs:PKEY_AudioEngine_DeviceFormat.pid
0x180020986  movups  [rbp+47h+var_50], xmm0
0x18002098a  mov     [rbp+47h+var_40], eax
0x18002098d  xorps   xmm0, xmm0
0x180020990  xor     eax, eax
0x180020992  movups  xmmword ptr [rbp+47h+pvar], xmm0
0x180020996  mov     [rbp+47h+Src], rax
0x18002099a  mov     rcx, [rcx+48h]
0x18002099e  mov     rax, [rcx]
0x1800209a1  lea     r8, [rbp+47h+pvar]
0x1800209a5  lea     rdx, [rbp+47h+var_50]
0x1800209a9  mov     rax, [rax+28h]
0x1800209ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800209b2  mov     rcx, [rbp+4Fh]; this
0x1800209b6  test    eax, eax
0x1800209b8  jns     short loc_1800209D3
0x1800209ba  mov     r9d, eax; char *
0x1800209bd  lea     r8, aAvcoreAudiocor_52; "avcore\\audiocore\\server\\lib\\audiose"...
0x1800209c4  mov     edx, 19B5h; void *
0x1800209c9  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800209ce  jmp     loc_180020AAF
0x1800209d3  movzx   eax, word ptr [rbp+47h+pvar]
0x1800209d7  test    eax, eax
0x1800209d9  jz      loc_180020AAF
0x1800209df  cmp     eax, 41h ; 'A'
0x1800209e2  jz      short loc_180020A18
0x1800209e4  mov     rcx, [rbp+4Fh]; this
0x1800209e8  mov     [rsp+0F0h+var_C0], eax
0x1800209ec  mov     dword ptr [rsp+0F0h+var_C8], eax; char *
0x1800209f0  lea     rax, aUnexpectedVart_1; "Unexpected vartype %d (0x%08x)"
0x1800209f7  mov     [rsp+0F0h+var_D0], rax; unsigned int
0x1800209fc  mov     r9d, 0Dh; char *
0x180020a02  lea     r8, aAvcoreAudiocor_52; "avcore\\audiocore\\server\\lib\\audiose"...
0x180020a09  mov     edx, 19D2h; void *
0x180020a0e  call    ?Log_Win32Msg@in1diag3@details@wil@@YAKPEAXIPEBDK1ZZ; wil::details::in1diag3::Log_Win32Msg(void *,uint,char const *,ulong,char const *,...)
0x180020a13  jmp     loc_180020AAF
0x180020a18  lea     rcx, [rbp+47h+pvar]; struct tagPROPVARIANT *
0x180020a1c  call    ?IsValidWfxBlob@@YAHPEAUtagPROPVARIANT@@@Z; IsValidWfxBlob(tagPROPVARIANT *)
0x180020a21  test    eax, eax
0x180020a23  jz      short loc_180020AA1
0x180020a25  mov     rbx, [rbp+47h+Src]
0x180020a29  mov     rdx, rbx
0x180020a2c  mov     rcx, rdi
0x180020a2f  call    _lambda_53e50f4d36d820af02fa3fa8c2905d02___operator__
0x180020a34  test    al, al
0x180020a36  jz      short loc_180020AAF
0x180020a38  lea     rax, [rbp+47h+pv]
0x180020a3c  mov     [rbp+47h+var_A8], rax
0x180020a40  mov     [rbp+47h+var_A0], r13
0x180020a44  mov     [rbp+47h+var_98], 1
0x180020a48  lea     rdx, [rbp+47h+var_A0]; struct tWAVEFORMATEX **
0x180020a4c  mov     rcx, rbx; Src
0x180020a4f  call    ?CloneWaveFormat@@YAJPEBUtWAVEFORMATEX@@PEAPEAU1@@Z; CloneWaveFormat(tWAVEFORMATEX const *,tWAVEFORMATEX * *)
0x180020a54  mov     ebx, eax
0x180020a56  lea     rcx, [rbp+47h+var_A8]
0x180020a5a  call    ??1?$out_param_t@V?$unique_ptr@U_GUID@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>(void)
0x180020a5f  test    ebx, ebx
0x180020a61  jns     short loc_180020AAF
0x180020a63  mov     edx, 19C1h; void *
0x180020a68  lea     r8, aAvcoreAudiocor_52; "avcore\\audiocore\\server\\lib\\audiose"...
0x180020a6f  mov     r9d, ebx; char *
0x180020a72  mov     rcx, [rbp+4Fh]; this
0x180020a76  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180020a7b  nop
0x180020a7c  lea     rcx, [rbp+47h+pvar]; pvar
0x180020a80  call    cs:__imp_PropVariantClear
0x180020a86  nop
0x180020a87  mov     rcx, [rbp+47h+pv]; pv
0x180020a8b  test    rcx, rcx
0x180020a8e  mov     [rbp+47h+pv], r13
0x180020a92  jz      short loc_180020A9A
0x180020a94  call    cs:__imp_CoTaskMemFree
0x180020a9a  mov     eax, ebx
0x180020a9c  jmp     loc_180020BAF
0x180020aa1  mov     rcx, [rbp+4Fh]; this
0x180020aa5  mov     edx, 19C6h; void *
0x180020aaa  call    ?Log_Win32@in1diag3@details@wil@@YAKPEAXIPEBDK@Z; wil::details::in1diag3::Log_Win32(void *,uint,char const *,ulong)
0x180020aaf  cmp     [rbp+47h+pv], r13
0x180020ab3  jnz     loc_180020B6F
0x180020ab9  lea     rax, [rbp+47h+pv]
0x180020abd  mov     [rbp+47h+var_A8], rax
0x180020ac1  mov     [rbp+47h+var_A0], r13
0x180020ac5  mov     [rbp+47h+var_98], 1
0x180020ac9  movaps  xmm0, xmmword ptr [rdi]
0x180020acc  movaps  xmmword ptr [rbp+47h+var_70], xmm0
0x180020ad0  movaps  xmm1, xmmword ptr [rdi+10h]
0x180020ad4  movaps  [rbp+47h+var_60], xmm1
0x180020ad8  mov     edx, r15d; int
0x180020adb  lea     rax, [rbp+47h+var_A0]
0x180020adf  mov     [rsp+0F0h+var_D0], rax; int
0x180020ae4  lea     r9, [rbp+47h+var_70]; int
0x180020ae8  mov     r8d, esi; int
0x180020aeb  mov     rcx, r14; int
0x180020aee  call    CEndpointCharacteristics__GetDefaultFormat__lambda_53e50f4d36d820af02fa3fa8c2905d02___
0x180020af3  mov     edi, eax
0x180020af5  cmp     [rbp+47h+var_98], r13b
0x180020af9  jz      short loc_180020B14
0x180020afb  mov     r8, [rbp+47h+var_A8]
0x180020aff  mov     rcx, [r8]; pv
0x180020b02  mov     rdx, [rbp+47h+var_A0]
0x180020b06  mov     [r8], rdx
0x180020b09  test    rcx, rcx
0x180020b0c  jz      short loc_180020B14
0x180020b0e  call    cs:__imp_CoTaskMemFree
0x180020b14  test    edi, edi
0x180020b16  jns     short loc_180020B4D
0x180020b18  mov     ebx, 88890004h
0x180020b1d  cmp     edi, ebx
0x180020b1f  jz      loc_180020A7C
0x180020b25  mov     rcx, [rbp+4Fh]; this
0x180020b29  mov     r9d, edi; char *
0x180020b2c  lea     r8, aAvcoreAudiocor_52; "avcore\\audiocore\\server\\lib\\audiose"...
0x180020b33  mov     edx, 19D9h; void *
0x180020b38  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180020b3d  nop
0x180020b3e  lea     rcx, [rbp+47h+pvar]; pvar
0x180020b42  call    cs:__imp_PropVariantClear
0x180020b48  jmp     loc_18002094B
0x180020b4d  mov     r9, [rbp+47h+pv]; struct tWAVEFORMATEX *
0x180020b51  mov     r8d, esi; enum __MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001
0x180020b54  mov     dl, r15b; bool
0x180020b57  mov     rcx, r14; this
0x180020b5a  call    ?UpdateDeviceFormatEPProperty@CEndpointCharacteristics@@QEAAJ_NW4__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001@@PEBUtWAVEFORMATEX@@@Z; CEndpointCharacteristics::UpdateDeviceFormatEPProperty(bool,__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001,tWAVEFORMATEX const *)
0x180020b5f  mov     ebx, eax
0x180020b61  test    eax, eax
0x180020b63  jns     short loc_180020B6F
0x180020b65  mov     edx, 19DCh
0x180020b6a  jmp     loc_180020A68
0x180020b6f  lea     rcx, [rbp+47h+pvar]; pvar
0x180020b73  call    cs:__imp_PropVariantClear
0x180020b79  mov     rcx, [rbp+47h+pv]; struct tWAVEFORMATEX *
0x180020b7d  call    ?ValidateWaveFormatEx@@YAJPEBUtWAVEFORMATEX@@@Z; ValidateWaveFormatEx(tWAVEFORMATEX const *)
0x180020b82  mov     ebx, eax
0x180020b84  test    eax, eax
0x180020b86  jns     short loc_180020BA5
0x180020b88  mov     rcx, [rbp+4Fh]; this
0x180020b8c  mov     r9d, eax; char *
0x180020b8f  lea     r8, aAvcoreAudiocor_52; "avcore\\audiocore\\server\\lib\\audiose"...
0x180020b96  mov     edx, 19E1h; void *
0x180020b9b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180020ba0  jmp     loc_180020A87
0x180020ba5  mov     rax, [rbp+47h+pv]
0x180020ba9  mov     [r12], rax
0x180020bad  xor     eax, eax
0x180020baf  mov     rcx, [rbp+47h+var_38]
0x180020bb3  xor     rcx, rsp; StackCookie
0x180020bb6  call    __security_check_cookie
0x180020bbb  mov     rbx, [rsp+0F0h+arg_8]
0x180020bc3  add     rsp, 0C0h
0x180020bca  pop     r15
0x180020bcc  pop     r14
0x180020bce  pop     r13
0x180020bd0  pop     r12
0x180020bd2  pop     rdi
0x180020bd3  pop     rsi
0x180020bd4  pop     rbp
0x180020bd5  retn
```
