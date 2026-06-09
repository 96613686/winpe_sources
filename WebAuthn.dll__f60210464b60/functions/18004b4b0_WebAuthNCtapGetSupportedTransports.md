# WebAuthNCtapGetSupportedTransports

- ea: `0x18004b4b0`
- end: `0x18004b773`
- name: `WebAuthNCtapGetSupportedTransports`
- size: `707`
- prototype: ``
- caller_count: `0`
- callee_count: `12`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000c5ec`
- `0x18000c9d0`
- `0x18001687c`
- `0x18001c0d4`
- `0x18001c0f4`
- `0x1800205e4`
- `0x180031708`
- `0x18004a610`
- `0x18004b4b0`
- `0x18004baa4`
- `0x1800537a4`
- `0x18013c090`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004b682`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004b695`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004b682`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004b695`
- `RPCRT4!UuidCreate` at `0x18004b571`
- `RPCRT4!UuidCreate` at `0x18004b571`

## string_xrefs

- `0x18004b5ff`: `onecore\ds\security\fido\webauthn\dll\webauthnctap.cpp`
- `0x18004b651`: `onecore\ds\security\fido\webauthn\dll\webauthnctap.cpp`
- `0x18004b746`: `onecore\ds\security\fido\webauthn\dll\webauthnctap.cpp`

## pseudocode

```c
__int64 __fastcall WebAuthNCtapGetSupportedTransports(int *a1, struct _GUID *p_Uuid)
{
  int v4; // ebx
  unsigned __int8 *v5; // rdi
  int v6; // esi
  int v7; // eax
  HLOCAL v8; // rcx
  HLOCAL v9; // rcx
  unsigned int v11; // esi
  unsigned int v12; // r15d
  unsigned int v13; // eax
  int v14; // [rsp+20h] [rbp-E0h]
  int v15; // [rsp+20h] [rbp-E0h]
  int v16; // [rsp+20h] [rbp-E0h]
  unsigned __int8 v17[4]; // [rsp+80h] [rbp-80h] BYREF
  unsigned int v18; // [rsp+84h] [rbp-7Ch] BYREF
  unsigned int v19; // [rsp+88h] [rbp-78h] BYREF
  int v20; // [rsp+8Ch] [rbp-74h] BYREF
  unsigned __int8 *v21; // [rsp+90h] [rbp-70h] BYREF
  HLOCAL hMem; // [rsp+98h] [rbp-68h] BYREF
  HLOCAL v23; // [rsp+A0h] [rbp-60h] BYREF
  HLOCAL *p_hMem; // [rsp+A8h] [rbp-58h] BYREF
  unsigned __int8 *v25; // [rsp+B0h] [rbp-50h] BYREF
  char v26; // [rsp+B8h] [rbp-48h]
  __int64 v27; // [rsp+C0h] [rbp-40h] BYREF
  int *v28; // [rsp+C8h] [rbp-38h] BYREF
  _QWORD v29[2]; // [rsp+D0h] [rbp-30h] BYREF
  UUID Uuid; // [rsp+E0h] [rbp-20h] BYREF
  _BYTE v31[576]; // [rsp+F0h] [rbp-10h] BYREF
  int v32; // [rsp+330h] [rbp+230h] BYREF
  _BYTE v33[8]; // [rsp+338h] [rbp+238h] BYREF
  const wchar_t *v34; // [rsp+340h] [rbp+240h]
  wil::details::in1diag3 *retaddr; // [rsp+488h] [rbp+388h]

  v17[0] = 4;
  v4 = 1;
  memset_0(v31, 0, 0x238u);
  v18 = 0;
  v23 = 0;
  memset_0(v33, 0, 0x108u);
  v29[0] = 1;
  v28 = &v32;
  v29[1] = &v28;
  v34 = L"MicrosoftCtapNfcProvider";
  v19 = 0;
  v5 = 0;
  v21 = 0;
  hMem = 0;
  v27 = 0;
  v20 = 0;
  v32 = 1;
  Uuid = 0;
  if ( !p_Uuid )
  {
    UuidCreate(&Uuid);
    p_Uuid = &Uuid;
  }
  v25 = 0;
  p_hMem = &v23;
  v26 = 1;
  v6 = I_EncodeRpcRequest(
         0,
         0x80000u,
         0,
         0x2710u,
         p_Uuid,
         (struct _CTAPCBOR_DEVICE_INFO_LIST *)v29,
         1u,
         v17,
         0,
         0,
         0,
         0,
         (struct _CTAPCBOR_RPC_REQUEST *)v31,
         &v18,
         &v25);
  wil::details::out_param_t<wistd::unique_ptr<_CTAPCBOR_DEVICE_RESPONSE_INFO_LIST,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<_CTAPCBOR_DEVICE_RESPONSE_INFO_LIST,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>(&p_hMem);
  if ( v6 < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x14E2,
      (unsigned int)"onecore\\ds\\security\\fido\\webauthn\\dll\\webauthnctap.cpp",
      (const char *)(unsigned int)v6,
      v14);
    goto LABEL_8;
  }
  v7 = I_SendRpcRequest(0, 0, (const struct _CTAPCBOR_RPC_REQUEST *)v31, v18, (unsigned __int8 *)v23, 0, &v19, &v21);
  if ( v7 < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x14EC,
      (unsigned int)"onecore\\ds\\security\\fido\\webauthn\\dll\\webauthnctap.cpp",
      (const char *)(unsigned int)v7,
      v15);
LABEL_7:
    v5 = v21;
    goto LABEL_8;
  }
  v11 = v19;
  if ( !v19 )
    goto LABEL_7;
  v5 = v21;
  p_hMem = &hMem;
  v25 = 0;
  v26 = 1;
  v12 = CtapCborDecodeDeviceResponseInfoList(v19, (_DWORD)v21, (unsigned int)&v25, (unsigned int)&v27, (__int64)&v20);
  wil::details::out_param_t<wistd::unique_ptr<_CTAPCBOR_DEVICE_RESPONSE_INFO_LIST,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<_CTAPCBOR_DEVICE_RESPONSE_INFO_LIST,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>(&p_hMem);
  if ( v12 )
  {
    EventWriteCborDecodeError(
      (_DWORD)p_Uuid,
      (unsigned int)"CtapCborDecodeDeviceResponseInfoList",
      v12,
      v11,
      (__int64)v5,
      v27,
      v20);
    v13 = HRESULT_FROM_CBOR_ERROR(v12);
    wil::details::in1diag3::Log_Hr(
      retaddr,
      (void *)0x1501,
      (unsigned int)"onecore\\ds\\security\\fido\\webauthn\\dll\\webauthnctap.cpp",
      (const char *)v13,
      v16);
  }
  else if ( *(_DWORD *)hMem )
  {
    v4 = 3;
  }
LABEL_8:
  CtapCltFree(v5);
  v8 = hMem;
  *a1 = v4;
  hMem = 0;
  if ( v8 )
    LocalFree(v8);
  v9 = v23;
  v23 = 0;
  if ( v9 )
    LocalFree(v9);
  return 0;
}

```

## disassembly

```asm
0x18004b4b0  mov     [rsp-8+arg_10], rbx
0x18004b4b5  push    rbp
0x18004b4b6  push    rsi
0x18004b4b7  push    rdi
0x18004b4b8  push    r12
0x18004b4ba  push    r13
0x18004b4bc  push    r14
0x18004b4be  push    r15
0x18004b4c0  lea     rbp, [rsp-350h]
0x18004b4c8  sub     rsp, 450h
0x18004b4cf  mov     rax, cs:__security_cookie
0x18004b4d6  xor     rax, rsp
0x18004b4d9  mov     [rbp+380h+var_40], rax
0x18004b4e0  mov     r14, rdx
0x18004b4e3  mov     [rbp+380h+var_400], 4
0x18004b4e7  mov     r12, rcx
0x18004b4ea  xor     edx, edx; Val
0x18004b4ec  lea     rcx, [rbp+380h+var_390]; void *
0x18004b4f0  mov     r8d, 238h; Size
0x18004b4f6  mov     ebx, 1
0x18004b4fb  call    memset_0
0x18004b500  xor     r13d, r13d
0x18004b503  lea     rcx, [rbp+380h+var_148]; void *
0x18004b50a  xor     edx, edx; Val
0x18004b50c  mov     [rbp+380h+var_3FC], r13d
0x18004b510  mov     r8d, 108h; Size
0x18004b516  mov     [rbp+380h+var_3E0], r13
0x18004b51a  call    memset_0
0x18004b51f  mov     [rbp+380h+var_3B0], rbx
0x18004b523  lea     rax, [rbp+380h+var_150]
0x18004b52a  mov     [rbp+380h+var_3B8], rax
0x18004b52e  lea     rax, [rbp+380h+var_3B8]
0x18004b532  mov     [rbp+380h+var_3A8], rax
0x18004b536  lea     rax, aMicrosoftctapn; "MicrosoftCtapNfcProvider"
0x18004b53d  mov     [rbp+380h+var_140], rax
0x18004b544  xorps   xmm0, xmm0
0x18004b547  mov     [rbp+380h+var_3F8], r13d
0x18004b54b  mov     edi, r13d
0x18004b54e  mov     [rbp+380h+var_3F0], r13
0x18004b552  mov     [rbp+380h+hMem], r13
0x18004b556  mov     [rbp+380h+var_3C0], r13
0x18004b55a  mov     [rbp+380h+var_3F4], r13d
0x18004b55e  mov     [rbp+380h+var_150], ebx
0x18004b564  movups  xmmword ptr [rbp+380h+Uuid.Data1], xmm0
0x18004b568  test    r14, r14
0x18004b56b  jnz     short loc_18004B57B
0x18004b56d  lea     rcx, [rbp+380h+Uuid]; Uuid
0x18004b571  call    cs:__imp_UuidCreate
0x18004b577  lea     r14, [rbp+380h+Uuid]
0x18004b57b  lea     rax, [rbp+380h+var_3E0]
0x18004b57f  mov     [rbp+380h+var_3D0], r13
0x18004b583  mov     [rbp+380h+var_3D8], rax
0x18004b587  mov     r9d, 2710h; unsigned int
0x18004b58d  lea     rax, [rbp+380h+var_3D0]
0x18004b591  mov     [rbp+380h+var_3C8], bl
0x18004b594  mov     [rsp+480h+var_410], rax; unsigned __int8 **
0x18004b599  xor     r8d, r8d; unsigned int
0x18004b59c  lea     rax, [rbp+380h+var_3FC]
0x18004b5a0  mov     edx, 80000h; unsigned int
0x18004b5a5  mov     [rsp+480h+var_418], rax; unsigned int *
0x18004b5aa  xor     ecx, ecx; unsigned int
0x18004b5ac  lea     rax, [rbp+380h+var_390]
0x18004b5b0  mov     [rsp+480h+var_420], rax; struct _CTAPCBOR_RPC_REQUEST *
0x18004b5b5  lea     rax, [rbp+380h+var_400]
0x18004b5b9  mov     [rsp+480h+var_428], r13; unsigned __int16 *
0x18004b5be  mov     [rsp+480h+var_430], r13; unsigned __int8 *
0x18004b5c3  mov     [rsp+480h+var_438], r13d; unsigned int
0x18004b5c8  mov     [rsp+480h+var_440], r13; struct _WEBAUTHN_CTAP_RPC_PROTECTED *
0x18004b5cd  mov     [rsp+480h+var_448], rax; unsigned __int8 *
0x18004b5d2  lea     rax, [rbp+380h+var_3B0]
0x18004b5d6  mov     dword ptr [rsp+480h+var_450], ebx; unsigned int
0x18004b5da  mov     [rsp+480h+var_458], rax; struct _CTAPCBOR_DEVICE_INFO_LIST *
0x18004b5df  mov     [rsp+480h+var_460], r14; int
0x18004b5e4  call    ?I_EncodeRpcRequest@@YAJKKKKPEAU_GUID@@PEAU_CTAPCBOR_DEVICE_INFO_LIST@@KPEAEPEAU_WEBAUTHN_CTAP_RPC_PROTECTED@@KPEBEPEBGPEAU_CTAPCBOR_RPC_REQUEST@@PEAKPEAPEAE@Z; I_EncodeRpcRequest(ulong,ulong,ulong,ulong,_GUID *,_CTAPCBOR_DEVICE_INFO_LIST *,ulong,uchar *,_WEBAUTHN_CTAP_RPC_PROTECTED *,ulong,uchar const *,ushort const *,_CTAPCBOR_RPC_REQUEST *,ulong *,uchar * *)
0x18004b5e9  lea     rcx, [rbp+380h+var_3D8]
0x18004b5ed  mov     esi, eax
0x18004b5ef  call    ??1?$out_param_t@V?$unique_ptr@U_CTAPCBOR_DEVICE_RESPONSE_INFO_LIST@@U?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<_CTAPCBOR_DEVICE_RESPONSE_INFO_LIST,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<_CTAPCBOR_DEVICE_RESPONSE_INFO_LIST,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>(void)
0x18004b5f4  test    esi, esi
0x18004b5f6  jns     short loc_18004B615
0x18004b5f8  mov     rcx, [rbp+388h]; this
0x18004b5ff  lea     r8, aOnecoreDsSecur_27; "onecore\\ds\\security\\fido\\webauthn\\"...
0x18004b606  mov     r9d, esi; char *
0x18004b609  mov     edx, 14E2h; void *
0x18004b60e  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18004b613  jmp     short loc_18004B669
0x18004b615  mov     rax, [rbp+380h+var_3E0]
0x18004b619  lea     rcx, [rbp+380h+var_3F0]
0x18004b61d  mov     r9d, [rbp+380h+var_3FC]; unsigned int
0x18004b621  lea     r8, [rbp+380h+var_390]; struct _CTAPCBOR_RPC_REQUEST *
0x18004b625  mov     [rsp+480h+var_448], rcx; unsigned __int8 **
0x18004b62a  xor     edx, edx; int
0x18004b62c  lea     rcx, [rbp+380h+var_3F8]
0x18004b630  mov     [rsp+480h+var_450], rcx; unsigned int *
0x18004b635  xor     ecx, ecx; void *
0x18004b637  mov     dword ptr [rsp+480h+var_458], r13d; unsigned int
0x18004b63c  mov     [rsp+480h+var_460], rax; int
0x18004b641  call    ?I_SendRpcRequest@@YAJPEAXHPEBU_CTAPCBOR_RPC_REQUEST@@KPEAEKPEAKPEAPEAE@Z; I_SendRpcRequest(void *,int,_CTAPCBOR_RPC_REQUEST const *,ulong,uchar *,ulong,ulong *,uchar * *)
0x18004b646  test    eax, eax
0x18004b648  jns     short loc_18004B6C7
0x18004b64a  mov     rcx, [rbp+388h]; this
0x18004b651  lea     r8, aOnecoreDsSecur_27; "onecore\\ds\\security\\fido\\webauthn\\"...
0x18004b658  mov     r9d, eax; char *
0x18004b65b  mov     edx, 14ECh; void *
0x18004b660  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18004b665  mov     rdi, [rbp+380h+var_3F0]
0x18004b669  mov     rcx, rdi; lpMem
0x18004b66c  call    CtapCltFree
0x18004b671  mov     rcx, [rbp+380h+hMem]; hMem
0x18004b675  mov     [r12], ebx
0x18004b679  mov     [rbp+380h+hMem], r13
0x18004b67d  test    rcx, rcx
0x18004b680  jz      short loc_18004B688
0x18004b682  call    cs:__imp_LocalFree
0x18004b688  mov     rcx, [rbp+380h+var_3E0]; hMem
0x18004b68c  mov     [rbp+380h+var_3E0], r13
0x18004b690  test    rcx, rcx
0x18004b693  jz      short loc_18004B69B
0x18004b695  call    cs:__imp_LocalFree
0x18004b69b  xor     eax, eax
0x18004b69d  mov     rcx, [rbp+380h+var_40]
0x18004b6a4  xor     rcx, rsp; StackCookie
0x18004b6a7  call    __security_check_cookie
0x18004b6ac  mov     rbx, [rsp+480h+arg_10]
0x18004b6b4  add     rsp, 450h
0x18004b6bb  pop     r15
0x18004b6bd  pop     r14
0x18004b6bf  pop     r13
0x18004b6c1  pop     r12
0x18004b6c3  pop     rdi
0x18004b6c4  pop     rsi
0x18004b6c5  pop     rbp
0x18004b6c6  retn
0x18004b6c7  mov     esi, [rbp+380h+var_3F8]
0x18004b6ca  test    esi, esi
0x18004b6cc  jz      short loc_18004B665
0x18004b6ce  mov     rdi, [rbp+380h+var_3F0]
0x18004b6d2  lea     rax, [rbp+380h+hMem]
0x18004b6d6  mov     [rbp+380h+var_3D8], rax
0x18004b6da  lea     r9, [rbp+380h+var_3C0]
0x18004b6de  lea     rax, [rbp+380h+var_3F4]
0x18004b6e2  mov     [rbp+380h+var_3D0], r13
0x18004b6e6  lea     r8, [rbp+380h+var_3D0]
0x18004b6ea  mov     [rsp+480h+var_460], rax
0x18004b6ef  mov     rdx, rdi
0x18004b6f2  mov     [rbp+380h+var_3C8], bl
0x18004b6f5  mov     ecx, esi
0x18004b6f7  call    CtapCborDecodeDeviceResponseInfoList
0x18004b6fc  lea     rcx, [rbp+380h+var_3D8]
0x18004b700  mov     r15d, eax
0x18004b703  call    ??1?$out_param_t@V?$unique_ptr@U_CTAPCBOR_DEVICE_RESPONSE_INFO_LIST@@U?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<_CTAPCBOR_DEVICE_RESPONSE_INFO_LIST,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<_CTAPCBOR_DEVICE_RESPONSE_INFO_LIST,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>(void)
0x18004b708  test    r15d, r15d
0x18004b70b  jz      short loc_18004B75F
0x18004b70d  mov     edx, [rbp+380h+var_3F4]
0x18004b710  mov     r9d, esi
0x18004b713  mov     dword ptr [rsp+480h+var_450], edx
0x18004b717  mov     r8d, r15d
0x18004b71a  mov     rdx, [rbp+380h+var_3C0]
0x18004b71e  mov     rcx, r14
0x18004b721  mov     [rsp+480h+var_458], rdx
0x18004b726  lea     rdx, aCtapcbordecode_3; "CtapCborDecodeDeviceResponseInfoList"
0x18004b72d  mov     [rsp+480h+var_460], rdi; int
0x18004b732  call    _EventWriteCborDecodeError
0x18004b737  mov     ecx, r15d
0x18004b73a  call    _HRESULT_FROM_CBOR_ERROR
0x18004b73f  mov     rcx, [rbp+388h]; this
0x18004b746  lea     r8, aOnecoreDsSecur_27; "onecore\\ds\\security\\fido\\webauthn\\"...
0x18004b74d  mov     r9d, eax; char *
0x18004b750  mov     edx, 1501h; void *
0x18004b755  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x18004b75a  jmp     loc_18004B669
0x18004b75f  mov     rax, [rbp+380h+hMem]
0x18004b763  mov     ecx, 3
0x18004b768  cmp     [rax], r13d
0x18004b76b  cmovnz  ebx, ecx
0x18004b76e  jmp     loc_18004B669
```
