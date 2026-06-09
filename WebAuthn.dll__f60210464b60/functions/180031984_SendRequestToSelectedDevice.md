# _SendRequestToSelectedDevice

- ea: `0x180031984`
- end: `0x180031ddc`
- name: `_SendRequestToSelectedDevice`
- size: `1112`
- prototype: ``
- caller_count: `2`
- callee_count: `17`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001b5e8`
- `0x18002a830`

## callees

- `0x18000c5ec`
- `0x18000c9d0`
- `0x18001687c`
- `0x1800168ac`
- `0x180018d2c`
- `0x18001c0d4`
- `0x18001c0f4`
- `0x1800205e4`
- `0x180025880`
- `0x180027338`
- `0x180031708`
- `0x180031984`
- `0x18004a610`
- `0x18004baa4`
- `0x1800537a4`
- `0x1800c7b64`
- `0x18013c090`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180031c62`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180031c81`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180031c62`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180031c81`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180031c0c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180031cf4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180031d96`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180031c0c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180031cf4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180031d96`
- `RPCRT4!UuidCreate` at `0x180031a33`
- `RPCRT4!UuidCreate` at `0x180031a33`

## string_xrefs

- `0x180031af6`: `onecore\ds\security\fido\webauthn\dll\webauthnctap.cpp`
- `0x180031be8`: `onecore\ds\security\fido\webauthn\dll\webauthnctap.cpp`
- `0x180031d78`: `onecore\ds\security\fido\webauthn\dll\webauthnctap.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall SendRequestToSelectedDevice(
        void *a1,
        unsigned int a2,
        unsigned int a3,
        UUID *a4,
        unsigned int a5,
        unsigned __int8 *a6,
        struct _WEBAUTHN_CTAP_RPC_PROTECTED *a7,
        __int64 a8,
        _QWORD *a9)
{
  struct _GUID *p_Uuid; // r12
  unsigned int v13; // ebx
  HLOCAL v14; // rsi
  unsigned int v15; // ebx
  unsigned int v16; // edi
  unsigned int v17; // r14d
  unsigned int v18; // eax
  __int64 v19; // rdx
  __int64 v20; // r9
  HLOCAL v21; // rcx
  bool v22; // zf
  _QWORD *v23; // r15
  unsigned int i; // edi
  __int64 v25; // r14
  __int64 v26; // r13
  __int64 v27; // rcx
  __int64 v28; // rdx
  __int64 v29; // rcx
  __int64 v30; // rdx
  __int64 v31; // rcx
  unsigned int v32; // edi
  HLOCAL v33; // r14
  HLOCAL v34; // rcx
  unsigned int v35; // eax
  unsigned int v36; // r15d
  HLOCAL v37; // rcx
  int v39; // [rsp+20h] [rbp-E0h]
  int v40; // [rsp+20h] [rbp-E0h]
  int v41; // [rsp+20h] [rbp-E0h]
  HLOCAL hMem; // [rsp+80h] [rbp-80h] BYREF
  unsigned int v43; // [rsp+88h] [rbp-78h] BYREF
  HLOCAL v44; // [rsp+90h] [rbp-70h] BYREF
  int v45; // [rsp+98h] [rbp-68h] BYREF
  unsigned int v46; // [rsp+9Ch] [rbp-64h] BYREF
  __int64 v47; // [rsp+A0h] [rbp-60h] BYREF
  void *p_hMem; // [rsp+A8h] [rbp-58h] BYREF
  unsigned __int8 *v49; // [rsp+B0h] [rbp-50h] BYREF
  char v50; // [rsp+B8h] [rbp-48h]
  UUID *v51; // [rsp+C0h] [rbp-40h]
  unsigned __int8 *v52; // [rsp+C8h] [rbp-38h] BYREF
  __int64 v53; // [rsp+D0h] [rbp-30h] BYREF
  _QWORD *v54; // [rsp+D8h] [rbp-28h]
  _QWORD v55[2]; // [rsp+E0h] [rbp-20h] BYREF
  UUID Uuid; // [rsp+F0h] [rbp-10h] BYREF
  _BYTE v57[576]; // [rsp+100h] [rbp+0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+388h] [rbp+288h]

  p_Uuid = a4;
  v51 = a4;
  v53 = a8;
  v54 = a9;
  v55[0] = 1;
  v55[1] = &v53;
  v47 = 0;
  v45 = 0;
  v13 = 0;
  memset_0(v57, 0, 0x238u);
  v46 = 0;
  v52 = 0;
  v43 = 0;
  v14 = 0;
  hMem = 0;
  Uuid = 0;
  *v54 = 0;
  if ( !p_Uuid )
  {
    UuidCreate(&Uuid);
    p_Uuid = &Uuid;
    v51 = &Uuid;
  }
  if ( a5 && *a6 == 6 && a7 && *(_DWORD *)a7 && *((_DWORD *)a7 + 4) )
    v13 = 0x4000;
  p_hMem = &v52;
  v49 = 0;
  v50 = 1;
  v15 = I_EncodeRpcRequest(
          a2,
          v13,
          a3,
          0,
          p_Uuid,
          (struct _CTAPCBOR_DEVICE_INFO_LIST *)v55,
          a5,
          a6,
          a7,
          0,
          0,
          0,
          (struct _CTAPCBOR_RPC_REQUEST *)v57,
          &v46,
          &v49);
  wil::details::out_param_t<wistd::unique_ptr<unsigned char,wil::hlocal_secure_deleter>>::~out_param_t<wistd::unique_ptr<unsigned char,wil::hlocal_secure_deleter>>(&p_hMem);
  if ( (v15 & 0x80000000) != 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x8BB,
      (unsigned int)"onecore\\ds\\security\\fido\\webauthn\\dll\\webauthnctap.cpp",
      (const char *)v15,
      v39);
    goto LABEL_41;
  }
  v15 = I_SendRpcRequest(
          a1,
          0,
          (const struct _CTAPCBOR_RPC_REQUEST *)v57,
          v46,
          v52,
          1u,
          &v43,
          (unsigned __int8 **)&hMem);
  v16 = v43;
  v14 = hMem;
  if ( !v43 )
    goto LABEL_41;
  v43 = 0;
  v44 = 0;
  if ( (unsigned int)CtapCborIsArray(v16, hMem) )
  {
    hMem = 0;
    p_hMem = &hMem;
    v49 = 0;
    v50 = 1;
    v17 = CtapCborDecodeDeviceResponseInfoList(v16, (_DWORD)v14, (unsigned int)&v49, (unsigned int)&v47, (__int64)&v45);
    wil::details::out_param_t<wistd::unique_ptr<_CTAPCBOR_DEVICE_RESPONSE_INFO_LIST,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<_CTAPCBOR_DEVICE_RESPONSE_INFO_LIST,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>(&p_hMem);
    if ( v17 )
    {
      EventWriteCborDecodeError(
        (_DWORD)p_Uuid,
        (unsigned int)"CtapCborDecodeDeviceResponseInfoList",
        v17,
        v16,
        (__int64)v14,
        v47,
        v45);
      v18 = HRESULT_FROM_CBOR_ERROR(v17);
      v19 = 2274;
LABEL_15:
      v20 = v18;
      v15 = v18;
LABEL_16:
      wil::details::in1diag3::Log_Hr(
        retaddr,
        (void *)v19,
        (unsigned int)"onecore\\ds\\security\\fido\\webauthn\\dll\\webauthnctap.cpp",
        (const char *)v20,
        v40);
      v21 = hMem;
      v22 = hMem == 0;
      hMem = 0;
      if ( !v22 )
        LocalFree(v21);
      goto LABEL_39;
    }
    v23 = hMem;
    for ( i = 0; ; ++i )
    {
      if ( i >= *(_DWORD *)v23 )
        goto LABEL_35;
      v25 = v53;
      if ( v53 )
      {
        v26 = *(_QWORD *)(v23[1] + 40LL * i + 8);
        if ( v26 )
        {
          v27 = *(_QWORD *)(v53 + 16);
          if ( v27 )
          {
            v28 = *(_QWORD *)(v26 + 16);
            if ( v28 )
            {
              if ( !(unsigned int)_o__wcsicmp(v27, v28) )
              {
                v29 = *(_QWORD *)(v25 + 32);
                if ( v29 )
                {
                  v30 = *(_QWORD *)(v26 + 32);
                  if ( v30 )
                  {
                    if ( !(unsigned int)_o__wcsicmp(v29, v30) )
                      break;
                  }
                }
              }
            }
          }
        }
      }
    }
    v31 = v23[1] + 40LL * i;
    if ( !v31 )
    {
LABEL_35:
      v15 = -2146893807;
      v20 = 2148073489LL;
      v19 = 2292;
      goto LABEL_16;
    }
    p_hMem = &v44;
    v49 = 0;
    v50 = 1;
    v32 = CtapCborEncodeDeviceResponseInfo(v31, &v43, &v49, &v45);
    wil::details::out_param_t<wistd::unique_ptr<_CTAPCBOR_DEVICE_RESPONSE_INFO_LIST,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<_CTAPCBOR_DEVICE_RESPONSE_INFO_LIST,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>(&p_hMem);
    if ( v32 )
    {
      v18 = HRESULT_FROM_CBOR_ERROR(v32);
      v19 = 2302;
      goto LABEL_15;
    }
    v33 = v44;
    v34 = hMem;
    hMem = 0;
    if ( v34 )
      LocalFree(v34);
    v16 = v43;
    LODWORD(p_Uuid) = (_DWORD)v51;
  }
  else
  {
    v33 = v14;
  }
  v35 = CtapCborDecodeDeviceResponseInfo(v16, (_DWORD)v33, (_DWORD)v54, (unsigned int)&v47, (__int64)&v45);
  v36 = v35;
  if ( v35 )
  {
    EventWriteCborDecodeError(
      (_DWORD)p_Uuid,
      (unsigned int)"CtapCborDecodeSingleResponseInfo",
      v35,
      v16,
      (__int64)v33,
      v47,
      v45);
    v15 = HRESULT_FROM_CBOR_ERROR(v36);
    wil::details::in1diag3::Log_Hr(
      retaddr,
      (void *)0x91B,
      (unsigned int)"onecore\\ds\\security\\fido\\webauthn\\dll\\webauthnctap.cpp",
      (const char *)v15,
      v41);
  }
LABEL_39:
  v37 = v44;
  v22 = v44 == 0;
  v44 = 0;
  if ( !v22 )
    LocalFree(v37);
LABEL_41:
  CtapCltFree(v14);
  wistd::unique_ptr<unsigned char,wil::hlocal_secure_deleter>::reset(&v52, 0);
  return v15;
}

```

## disassembly

```asm
0x180031984  mov     [rsp-8+arg_8], rbx
0x180031989  push    rbp
0x18003198a  push    rsi
0x18003198b  push    rdi
0x18003198c  push    r12
0x18003198e  push    r13
0x180031990  push    r14
0x180031992  push    r15
0x180031994  lea     rbp, [rsp-250h]
0x18003199c  sub     rsp, 350h
0x1800319a3  mov     rax, cs:__security_cookie
0x1800319aa  xor     rax, rsp
0x1800319ad  mov     [rbp+280h+var_40], rax
0x1800319b4  mov     r12, r9
0x1800319b7  mov     [rbp+280h+var_2C0], r9
0x1800319bb  mov     r15d, r8d
0x1800319be  mov     r14d, edx
0x1800319c1  mov     rdi, rcx
0x1800319c4  mov     rax, [rbp+280h+arg_38]
0x1800319cb  mov     [rbp+280h+var_2B0], rax
0x1800319cf  mov     rax, [rbp+280h+arg_40]
0x1800319d6  mov     [rbp+280h+var_2A8], rax
0x1800319da  mov     [rbp+280h+var_2A0], 1
0x1800319e2  lea     rax, [rbp+280h+var_2B0]
0x1800319e6  mov     [rbp+280h+var_298], rax
0x1800319ea  xor     r13d, r13d
0x1800319ed  mov     [rbp+280h+var_2E0], r13
0x1800319f1  mov     [rbp+280h+var_2E8], r13d
0x1800319f5  mov     ebx, r13d
0x1800319f8  xor     edx, edx; Val
0x1800319fa  mov     r8d, 238h; Size
0x180031a00  lea     rcx, [rbp+280h+var_280]; void *
0x180031a04  call    memset_0
0x180031a09  mov     [rbp+280h+var_2E4], r13d
0x180031a0d  mov     [rbp+280h+var_2B8], r13
0x180031a11  mov     [rbp+280h+var_2F8], r13d
0x180031a15  mov     esi, r13d
0x180031a18  mov     [rbp+280h+hMem], r13
0x180031a1c  xorps   xmm0, xmm0
0x180031a1f  movups  xmmword ptr [rbp+280h+Uuid.Data1], xmm0
0x180031a23  mov     rax, [rbp+280h+var_2A8]
0x180031a27  mov     [rax], r13
0x180031a2a  test    r12, r12
0x180031a2d  jnz     short loc_180031A41
0x180031a2f  lea     rcx, [rbp+280h+Uuid]; Uuid
0x180031a33  call    cs:__imp_UuidCreate
0x180031a39  lea     r12, [rbp+280h+Uuid]
0x180031a3d  mov     [rbp+280h+var_2C0], r12
0x180031a41  mov     rax, [rbp+280h+arg_30]
0x180031a48  mov     rcx, [rbp+280h+arg_28]
0x180031a4f  mov     edx, [rbp+280h+arg_20]
0x180031a55  cmp     edx, 1
0x180031a58  jb      short loc_180031A77
0x180031a5a  cmp     byte ptr [rcx], 6
0x180031a5d  jnz     short loc_180031A77
0x180031a5f  test    rax, rax
0x180031a62  jz      short loc_180031A77
0x180031a64  cmp     [rax], r13d
0x180031a67  jz      short loc_180031A77
0x180031a69  mov     r8d, 4000h
0x180031a6f  cmp     [rax+10h], r13d
0x180031a73  cmovnz  ebx, r8d
0x180031a77  lea     r8, [rbp+280h+var_2B8]
0x180031a7b  mov     [rbp+280h+var_2D8], r8
0x180031a7f  mov     [rbp+280h+var_2D0], r13
0x180031a83  mov     [rbp+280h+var_2C8], 1
0x180031a87  lea     r8, [rbp+280h+var_2D0]
0x180031a8b  mov     [rsp+380h+var_310], r8; unsigned __int8 **
0x180031a90  lea     r8, [rbp+280h+var_2E4]
0x180031a94  mov     [rsp+380h+var_318], r8; unsigned int *
0x180031a99  lea     r8, [rbp+280h+var_280]
0x180031a9d  mov     [rsp+380h+var_320], r8; struct _CTAPCBOR_RPC_REQUEST *
0x180031aa2  mov     [rsp+380h+var_328], r13; unsigned __int16 *
0x180031aa7  mov     [rsp+380h+var_330], r13; unsigned __int8 *
0x180031aac  mov     [rsp+380h+var_338], r13d; unsigned int
0x180031ab1  mov     [rsp+380h+var_340], rax; struct _WEBAUTHN_CTAP_RPC_PROTECTED *
0x180031ab6  mov     [rsp+380h+var_348], rcx; unsigned __int8 *
0x180031abb  mov     dword ptr [rsp+380h+var_350], edx; unsigned int
0x180031abf  lea     rax, [rbp+280h+var_2A0]
0x180031ac3  mov     [rsp+380h+var_358], rax; struct _CTAPCBOR_DEVICE_INFO_LIST *
0x180031ac8  mov     [rsp+380h+var_360], r12; int
0x180031acd  xor     r9d, r9d; unsigned int
0x180031ad0  mov     r8d, r15d; unsigned int
0x180031ad3  mov     edx, ebx; unsigned int
0x180031ad5  mov     ecx, r14d; unsigned int
0x180031ad8  call    ?I_EncodeRpcRequest@@YAJKKKKPEAU_GUID@@PEAU_CTAPCBOR_DEVICE_INFO_LIST@@KPEAEPEAU_WEBAUTHN_CTAP_RPC_PROTECTED@@KPEBEPEBGPEAU_CTAPCBOR_RPC_REQUEST@@PEAKPEAPEAE@Z; I_EncodeRpcRequest(ulong,ulong,ulong,ulong,_GUID *,_CTAPCBOR_DEVICE_INFO_LIST *,ulong,uchar *,_WEBAUTHN_CTAP_RPC_PROTECTED *,ulong,uchar const *,ushort const *,_CTAPCBOR_RPC_REQUEST *,ulong *,uchar * *)
0x180031add  mov     ebx, eax
0x180031adf  lea     rcx, [rbp+280h+var_2D8]
0x180031ae3  call    ??1?$out_param_t@V?$unique_ptr@EUhlocal_secure_deleter@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<uchar,wil::hlocal_secure_deleter>>::~out_param_t<wistd::unique_ptr<uchar,wil::hlocal_secure_deleter>>(void)
0x180031ae8  mov     rcx, [rbp+288h]; this
0x180031aef  test    ebx, ebx
0x180031af1  jns     short loc_180031B0C
0x180031af3  mov     r9d, ebx; char *
0x180031af6  lea     r8, aOnecoreDsSecur_27; "onecore\\ds\\security\\fido\\webauthn\\"...
0x180031afd  mov     edx, 8BBh; void *
0x180031b02  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180031b07  jmp     loc_180031D9C
0x180031b0c  mov     rax, [rbp+280h+var_2B8]
0x180031b10  lea     rcx, [rbp+280h+hMem]
0x180031b14  mov     [rsp+380h+var_348], rcx; unsigned __int8 **
0x180031b19  lea     rcx, [rbp+280h+var_2F8]
0x180031b1d  mov     [rsp+380h+var_350], rcx; unsigned int *
0x180031b22  mov     dword ptr [rsp+380h+var_358], 1; unsigned int
0x180031b2a  mov     [rsp+380h+var_360], rax; unsigned __int8 *
0x180031b2f  mov     r9d, [rbp+280h+var_2E4]; unsigned int
0x180031b33  lea     r8, [rbp+280h+var_280]; struct _CTAPCBOR_RPC_REQUEST *
0x180031b37  xor     edx, edx; int
0x180031b39  mov     rcx, rdi; void *
0x180031b3c  call    ?I_SendRpcRequest@@YAJPEAXHPEBU_CTAPCBOR_RPC_REQUEST@@KPEAEKPEAKPEAPEAE@Z; I_SendRpcRequest(void *,int,_CTAPCBOR_RPC_REQUEST const *,ulong,uchar *,ulong,ulong *,uchar * *)
0x180031b41  mov     ebx, eax
0x180031b43  mov     edi, [rbp+280h+var_2F8]
0x180031b46  mov     rsi, [rbp+280h+hMem]
0x180031b4a  test    edi, edi
0x180031b4c  jz      loc_180031D9C
0x180031b52  mov     [rbp+280h+var_2F8], r13d
0x180031b56  mov     [rbp+280h+var_2F0], r13
0x180031b5a  mov     rdx, rsi
0x180031b5d  mov     ecx, edi
0x180031b5f  call    CtapCborIsArray
0x180031b64  test    eax, eax
0x180031b66  jz      loc_180031D15
0x180031b6c  mov     [rbp+280h+hMem], r13
0x180031b70  lea     rax, [rbp+280h+hMem]
0x180031b74  mov     [rbp+280h+var_2D8], rax
0x180031b78  mov     [rbp+280h+var_2D0], r13
0x180031b7c  mov     [rbp+280h+var_2C8], 1
0x180031b80  lea     rax, [rbp+280h+var_2E8]
0x180031b84  mov     [rsp+380h+var_360], rax
0x180031b89  lea     r9, [rbp+280h+var_2E0]
0x180031b8d  lea     r8, [rbp+280h+var_2D0]
0x180031b91  mov     rdx, rsi
0x180031b94  mov     ecx, edi
0x180031b96  call    CtapCborDecodeDeviceResponseInfoList
0x180031b9b  mov     r14d, eax
0x180031b9e  lea     rcx, [rbp+280h+var_2D8]
0x180031ba2  call    ??1?$out_param_t@V?$unique_ptr@U_CTAPCBOR_DEVICE_RESPONSE_INFO_LIST@@U?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<_CTAPCBOR_DEVICE_RESPONSE_INFO_LIST,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<_CTAPCBOR_DEVICE_RESPONSE_INFO_LIST,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>(void)
0x180031ba7  test    r14d, r14d
0x180031baa  jz      short loc_180031C17
0x180031bac  mov     edx, [rbp+280h+var_2E8]
0x180031baf  mov     dword ptr [rsp+380h+var_350], edx
0x180031bb3  mov     rdx, [rbp+280h+var_2E0]
0x180031bb7  mov     [rsp+380h+var_358], rdx
0x180031bbc  mov     [rsp+380h+var_360], rsi; int
0x180031bc1  mov     r9d, edi
0x180031bc4  mov     r8d, r14d
0x180031bc7  lea     rdx, aCtapcbordecode_3; "CtapCborDecodeDeviceResponseInfoList"
0x180031bce  mov     rcx, r12
0x180031bd1  call    _EventWriteCborDecodeError
0x180031bd6  mov     ecx, r14d
0x180031bd9  call    _HRESULT_FROM_CBOR_ERROR
0x180031bde  mov     edx, 8E2h; void *
0x180031be3  mov     r9d, eax; char *
0x180031be6  mov     ebx, eax
0x180031be8  lea     r8, aOnecoreDsSecur_27; "onecore\\ds\\security\\fido\\webauthn\\"...
0x180031bef  mov     rcx, [rbp+288h]; this
0x180031bf6  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x180031bfb  mov     rcx, [rbp+280h+hMem]; hMem
0x180031bff  test    rcx, rcx
0x180031c02  mov     [rbp+280h+hMem], r13
0x180031c06  jz      loc_180031D89
0x180031c0c  call    cs:__imp_LocalFree
0x180031c12  jmp     loc_180031D89
0x180031c17  mov     r15, [rbp+280h+hMem]
0x180031c1b  mov     edi, r13d
0x180031c1e  cmp     edi, [r15]
0x180031c21  jnb     loc_180031D03
0x180031c27  mov     r14, [rbp+280h+var_2B0]
0x180031c2b  test    r14, r14
0x180031c2e  jz      loc_180031CDC
0x180031c34  mov     eax, edi
0x180031c36  lea     r12, [rax+rax*4]
0x180031c3a  mov     rax, [r15+8]
0x180031c3e  mov     r13, [rax+r12*8+8]
0x180031c43  test    r13, r13
0x180031c46  jz      loc_180031CD9
0x180031c4c  mov     rcx, [r14+10h]
0x180031c50  test    rcx, rcx
0x180031c53  jz      loc_180031CD9
0x180031c59  mov     rdx, [r13+10h]
0x180031c5d  test    rdx, rdx
0x180031c60  jz      short loc_180031CD9
0x180031c62  call    cs:__imp__o__wcsicmp
0x180031c68  test    eax, eax
0x180031c6a  jnz     short loc_180031CD9
0x180031c6c  mov     rcx, [r14+20h]
0x180031c70  test    rcx, rcx
0x180031c73  jz      short loc_180031CD9
0x180031c75  mov     rdx, [r13+20h]
0x180031c79  xor     r13d, r13d
0x180031c7c  test    rdx, rdx
0x180031c7f  jz      short loc_180031CDC
0x180031c81  call    cs:__imp__o__wcsicmp
0x180031c87  test    eax, eax
0x180031c89  jnz     short loc_180031CDC
0x180031c8b  mov     rax, [r15+8]
0x180031c8f  lea     rcx, [rax+r12*8]
0x180031c93  test    rcx, rcx
0x180031c96  jz      short loc_180031D03
0x180031c98  lea     rax, [rbp+280h+var_2F0]
0x180031c9c  mov     [rbp+280h+var_2D8], rax
0x180031ca0  mov     [rbp+280h+var_2D0], r13
0x180031ca4  mov     [rbp+280h+var_2C8], 1
0x180031ca8  lea     r9, [rbp+280h+var_2E8]
0x180031cac  lea     r8, [rbp+280h+var_2D0]
0x180031cb0  lea     rdx, [rbp+280h+var_2F8]
0x180031cb4  call    CtapCborEncodeDeviceResponseInfo
0x180031cb9  mov     edi, eax
0x180031cbb  lea     rcx, [rbp+280h+var_2D8]
0x180031cbf  call    ??1?$out_param_t@V?$unique_ptr@U_CTAPCBOR_DEVICE_RESPONSE_INFO_LIST@@U?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<_CTAPCBOR_DEVICE_RESPONSE_INFO_LIST,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<_CTAPCBOR_DEVICE_RESPONSE_INFO_LIST,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>(void)
0x180031cc4  test    edi, edi
0x180031cc6  jz      short loc_180031CE3
0x180031cc8  mov     ecx, edi
0x180031cca  call    _HRESULT_FROM_CBOR_ERROR
0x180031ccf  mov     edx, 8FEh
0x180031cd4  jmp     loc_180031BE3
0x180031cd9  xor     r13d, r13d
0x180031cdc  inc     edi
0x180031cde  jmp     loc_180031C1E
0x180031ce3  mov     r14, [rbp+280h+var_2F0]
0x180031ce7  mov     rcx, [rbp+280h+hMem]; hMem
0x180031ceb  mov     [rbp+280h+hMem], r13
0x180031cef  test    rcx, rcx
0x180031cf2  jz      short loc_180031CFA
0x180031cf4  call    cs:__imp_LocalFree
0x180031cfa  mov     edi, [rbp+280h+var_2F8]
0x180031cfd  mov     r12, [rbp+280h+var_2C0]
0x180031d01  jmp     short loc_180031D18
0x180031d03  mov     ebx, 80090011h
0x180031d08  mov     r9d, ebx
0x180031d0b  mov     edx, 8F4h
0x180031d10  jmp     loc_180031BE8
0x180031d15  mov     r14, rsi
0x180031d18  lea     rax, [rbp+280h+var_2E8]
0x180031d1c  mov     [rsp+380h+var_360], rax
0x180031d21  lea     r9, [rbp+280h+var_2E0]
0x180031d25  mov     r8, [rbp+280h+var_2A8]
0x180031d29  mov     rdx, r14
0x180031d2c  mov     ecx, edi
0x180031d2e  call    CtapCborDecodeDeviceResponseInfo
0x180031d33  mov     r15d, eax
0x180031d36  test    eax, eax
0x180031d38  jz      short loc_180031D89
0x180031d3a  mov     ecx, [rbp+280h+var_2E8]
0x180031d3d  mov     dword ptr [rsp+380h+var_350], ecx
0x180031d41  mov     rcx, [rbp+280h+var_2E0]
0x180031d45  mov     [rsp+380h+var_358], rcx
0x180031d4a  mov     [rsp+380h+var_360], r14; int
0x180031d4f  mov     r9d, edi
0x180031d52  mov     r8d, eax
0x180031d55  lea     rdx, aCtapcbordecode; "CtapCborDecodeSingleResponseInfo"
0x180031d5c  mov     rcx, r12
0x180031d5f  call    _EventWriteCborDecodeError
0x180031d64  mov     ecx, r15d
0x180031d67  call    _HRESULT_FROM_CBOR_ERROR
0x180031d6c  mov     ebx, eax
0x180031d6e  mov     rcx, [rbp+288h]; this
0x180031d75  mov     r9d, eax; char *
0x180031d78  lea     r8, aOnecoreDsSecur_27; "onecore\\ds\\security\\fido\\webauthn\\"...
0x180031d7f  mov     edx, 91Bh; void *
0x180031d84  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x180031d89  mov     rcx, [rbp+280h+var_2F0]; hMem
0x180031d8d  test    rcx, rcx
0x180031d90  mov     [rbp+280h+var_2F0], r13
0x180031d94  jz      short loc_180031D9C
0x180031d96  call    cs:__imp_LocalFree
0x180031d9c  mov     rcx, rsi; lpMem
0x180031d9f  call    CtapCltFree
0x180031da4  nop
0x180031da5  xor     edx, edx
0x180031da7  lea     rcx, [rbp+280h+var_2B8]
0x180031dab  call    ?reset@?$unique_ptr@EUhlocal_secure_deleter@wil@@@wistd@@QEAAXPEAE@Z; wistd::unique_ptr<uchar,wil::hlocal_secure_deleter>::reset(uchar *)
0x180031db0  mov     eax, ebx
0x180031db2  mov     rcx, [rbp+280h+var_40]
0x180031db9  xor     rcx, rsp; StackCookie
0x180031dbc  call    __security_check_cookie
0x180031dc1  mov     rbx, [rsp+380h+arg_8]
0x180031dc9  add     rsp, 350h
0x180031dd0  pop     r15
0x180031dd2  pop     r14
0x180031dd4  pop     r13
0x180031dd6  pop     r12
0x180031dd8  pop     rdi
0x180031dd9  pop     rsi
0x180031dda  pop     rbp
0x180031ddb  retn
```
