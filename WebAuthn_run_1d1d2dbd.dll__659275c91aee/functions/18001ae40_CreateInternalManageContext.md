# _CreateInternalManageContext

- ea: `0x18001ae40`
- end: `0x18001b077`
- name: `_CreateInternalManageContext`
- size: `567`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18001a6e0`
- `0x18001a970`

## callees

- `0x18001687c`
- `0x18001aaa0`
- `0x18001ae40`
- `0x18001c1b4`
- `0x18001c208`
- `0x18001c400`
- `0x1800205e4`
- `0x180031708`
- `0x18005378c`
- `0x18013c090`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001af75`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001af75`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001b048`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001b048`
- `RPCRT4!UuidCreate` at `0x18001ae9c`
- `RPCRT4!UuidCreate` at `0x18001ae9c`

## string_xrefs

- `0x18001af0b`: `onecore\ds\security\fido\webauthn\dll\webauthnctap.cpp`
- `0x18001af9c`: `onecore\ds\security\fido\webauthn\dll\webauthnctap.cpp`
- `0x18001b020`: `onecore\ds\security\fido\webauthn\dll\webauthnctap.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CreateInternalManageContext(
        void *a1,
        __int64 a2,
        int a3,
        struct _GUID *a4,
        struct _CTAPCBOR_DEVICE_INFO *a5,
        _QWORD *a6)
{
  struct _GUID *p_Uuid; // r14
  int v8; // ebx
  wil::details::in1diag3 *v9; // rcx
  unsigned __int64 v10; // r9
  __int64 v11; // rdx
  _QWORD *v12; // rbx
  size_t v13; // rsi
  const void *v14; // r15
  HLOCAL v15; // rax
  __int64 v16; // rdi
  int SelectedDeviceInformation; // eax
  __int64 v18; // rdx
  HLOCAL v19; // rcx
  int v21; // [rsp+20h] [rbp-69h]
  __int64 v22; // [rsp+50h] [rbp-39h] BYREF
  HLOCAL hMem; // [rsp+58h] [rbp-31h] BYREF
  int v24; // [rsp+60h] [rbp-29h]
  HLOCAL *p_hMem; // [rsp+68h] [rbp-21h] BYREF
  __int64 v26; // [rsp+70h] [rbp-19h] BYREF
  char v27; // [rsp+78h] [rbp-11h]
  UUID Uuid; // [rsp+80h] [rbp-9h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+4Fh]

  p_Uuid = a4;
  v24 = a3;
  Uuid = 0;
  hMem = 0;
  v22 = 0;
  *a6 = 0;
  if ( !a4 )
  {
    UuidCreate(&Uuid);
    p_Uuid = &Uuid;
  }
  p_hMem = &hMem;
  v26 = 0;
  v27 = 1;
  v8 = SelectDevice(a1, 4u, p_Uuid, a5, 0, 0, (__int64)&v26);
  wil::details::out_param_t<wistd::unique_ptr<_CTAPCBOR_DEVICE_RESPONSE_INFO_LIST,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<_CTAPCBOR_DEVICE_RESPONSE_INFO_LIST,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>(&p_hMem);
  v9 = retaddr;
  if ( v8 < 0 )
  {
    v10 = (unsigned int)v8;
    v11 = 7019;
LABEL_5:
    wil::details::in1diag3::_Log_Hr(
      v9,
      (void *)v11,
      (unsigned int)"onecore\\ds\\security\\fido\\webauthn\\dll\\webauthnctap.cpp",
      (const char *)v10,
      v21);
    goto LABEL_21;
  }
  if ( !hMem
    || (v12 = (_QWORD *)*((_QWORD *)hMem + 1)) == 0
    || (v13 = *((unsigned int *)hMem + 5), !(_DWORD)v13)
    || (v14 = (const void *)*((_QWORD *)hMem + 3)) == 0 )
  {
    v18 = 7025;
    goto LABEL_20;
  }
  if ( !v12[1] || !v12[2] || !v12[4] )
  {
    v18 = 7036;
LABEL_20:
    v8 = -2146893783;
    wil::details::in1diag3::Log_Hr(
      retaddr,
      (void *)v18,
      (unsigned int)"onecore\\ds\\security\\fido\\webauthn\\dll\\webauthnctap.cpp",
      (const char *)0x80090029LL,
      v21);
    goto LABEL_21;
  }
  v15 = LocalAlloc(0x40u, v13 + 64);
  wil::details::unique_storage<wil::details::resource_policy<_WEBAUTHN_CTAP_MANAGE_INTERNAL_CONTEXT *,void (*)(_WEBAUTHN_CTAP_MANAGE_INTERNAL_CONTEXT *),&void _FreeInternalManageContext(_WEBAUTHN_CTAP_MANAGE_INTERNAL_CONTEXT *),wistd::integral_constant<unsigned __int64,0>,_WEBAUTHN_CTAP_MANAGE_INTERNAL_CONTEXT *,_WEBAUTHN_CTAP_MANAGE_INTERNAL_CONTEXT *,0,std::nullptr_t>>::reset(
    &v22,
    v15);
  v16 = v22;
  if ( v22 )
  {
    *(_DWORD *)(v22 + 24) = v24;
    *(_QWORD *)(v16 + 16) = v16 + 64;
    *(_DWORD *)(v16 + 8) = v13;
    memcpy_0((void *)(v16 + 64), v14, v13);
    *(struct _GUID *)(v16 + 28) = *p_Uuid;
    SelectedDeviceInformation = CreateSelectedDeviceInformation(v12, 0, 0, v16);
    v8 = SelectedDeviceInformation;
    v9 = retaddr;
    if ( SelectedDeviceInformation < 0 )
    {
      v10 = (unsigned int)SelectedDeviceInformation;
      v11 = 7054;
      goto LABEL_5;
    }
    v22 = 0;
    *a6 = v16;
  }
  else
  {
    v8 = -2147024882;
    wil::details::in1diag3::Log_Hr(
      retaddr,
      (void *)0x1B81,
      (unsigned int)"onecore\\ds\\security\\fido\\webauthn\\dll\\webauthnctap.cpp",
      (const char *)0x8007000ELL,
      v21);
  }
LABEL_21:
  wil::details::unique_storage<wil::details::resource_policy<_WEBAUTHN_CTAP_MANAGE_INTERNAL_CONTEXT *,void (*)(_WEBAUTHN_CTAP_MANAGE_INTERNAL_CONTEXT *),&void _FreeInternalManageContext(_WEBAUTHN_CTAP_MANAGE_INTERNAL_CONTEXT *),wistd::integral_constant<unsigned __int64,0>,_WEBAUTHN_CTAP_MANAGE_INTERNAL_CONTEXT *,_WEBAUTHN_CTAP_MANAGE_INTERNAL_CONTEXT *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_WEBAUTHN_CTAP_MANAGE_INTERNAL_CONTEXT *,void (*)(_WEBAUTHN_CTAP_MANAGE_INTERNAL_CONTEXT *),&void _FreeInternalManageContext(_WEBAUTHN_CTAP_MANAGE_INTERNAL_CONTEXT *),wistd::integral_constant<unsigned __int64,0>,_WEBAUTHN_CTAP_MANAGE_INTERNAL_CONTEXT *,_WEBAUTHN_CTAP_MANAGE_INTERNAL_CONTEXT *,0,std::nullptr_t>>(&v22);
  v19 = hMem;
  hMem = 0;
  if ( v19 )
    LocalFree(v19);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18001ae40  mov     [rsp-8+arg_8], rbx
0x18001ae45  push    rbp
0x18001ae46  push    rsi
0x18001ae47  push    rdi
0x18001ae48  push    r12
0x18001ae4a  push    r13
0x18001ae4c  push    r14
0x18001ae4e  push    r15
0x18001ae50  lea     rbp, [rsp-17h]
0x18001ae55  sub     rsp, 0A0h
0x18001ae5c  mov     rax, cs:__security_cookie
0x18001ae63  xor     rax, rsp
0x18001ae66  mov     [rbp+47h+var_40], rax
0x18001ae6a  mov     r14, r9
0x18001ae6d  mov     esi, r8d
0x18001ae70  mov     [rbp+47h+var_70], r8d
0x18001ae74  mov     ebx, edx
0x18001ae76  mov     rdi, rcx
0x18001ae79  mov     r12, [rbp+47h+arg_28]
0x18001ae7d  xorps   xmm0, xmm0
0x18001ae80  movups  xmmword ptr [rbp+47h+Uuid.Data1], xmm0
0x18001ae84  xor     r13d, r13d
0x18001ae87  mov     [rbp+47h+hMem], r13
0x18001ae8b  mov     [rbp+47h+var_80], r13
0x18001ae8f  mov     [r12], r13
0x18001ae93  test    r9, r9
0x18001ae96  jnz     short loc_18001AEA6
0x18001ae98  lea     rcx, [rbp+47h+Uuid]; Uuid
0x18001ae9c  call    cs:__imp_UuidCreate
0x18001aea2  lea     r14, [rbp+47h+Uuid]
0x18001aea6  lea     rax, [rbp+47h+hMem]
0x18001aeaa  mov     [rbp+47h+var_68], rax
0x18001aeae  mov     [rbp+47h+var_60], r13
0x18001aeb2  mov     [rbp+47h+var_58], 1
0x18001aeb6  or      ebx, 2100000h
0x18001aebc  lea     rax, [rbp+47h+var_60]
0x18001aec0  mov     [rsp+0D0h+var_90], rax
0x18001aec5  mov     [rsp+0D0h+var_98], r13
0x18001aeca  mov     [rsp+0D0h+var_A0], r13d
0x18001aecf  mov     rax, [rbp+47h+arg_20]
0x18001aed3  mov     [rsp+0D0h+var_A8], rax
0x18001aed8  mov     qword ptr [rsp+0D0h+var_B0], r14; int
0x18001aedd  mov     r9d, esi
0x18001aee0  mov     r8d, ebx
0x18001aee3  mov     edx, 4
0x18001aee8  mov     rcx, rdi
0x18001aeeb  call    _SelectDevice
0x18001aef0  mov     ebx, eax
0x18001aef2  lea     rcx, [rbp+47h+var_68]
0x18001aef6  call    ??1?$out_param_t@V?$unique_ptr@U_CTAPCBOR_DEVICE_RESPONSE_INFO_LIST@@U?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<_CTAPCBOR_DEVICE_RESPONSE_INFO_LIST,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<_CTAPCBOR_DEVICE_RESPONSE_INFO_LIST,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>(void)
0x18001aefb  mov     rcx, [rbp+4Fh]; this
0x18001aeff  test    ebx, ebx
0x18001af01  jns     short loc_18001AF1C
0x18001af03  mov     r9d, ebx; char *
0x18001af06  mov     edx, 1B6Bh; void *
0x18001af0b  lea     r8, aOnecoreDsSecur_27; "onecore\\ds\\security\\fido\\webauthn\\"...
0x18001af12  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001af17  jmp     loc_18001B031
0x18001af1c  mov     rax, [rbp+47h+hMem]
0x18001af20  test    rax, rax
0x18001af23  jz      loc_18001B012
0x18001af29  mov     rbx, [rax+8]
0x18001af2d  test    rbx, rbx
0x18001af30  jz      loc_18001B012
0x18001af36  mov     esi, [rax+14h]
0x18001af39  test    esi, esi
0x18001af3b  jz      loc_18001B012
0x18001af41  mov     r15, [rax+18h]
0x18001af45  test    r15, r15
0x18001af48  jz      loc_18001B012
0x18001af4e  cmp     [rbx+8], r13
0x18001af52  jz      loc_18001B00B
0x18001af58  cmp     [rbx+10h], r13
0x18001af5c  jz      loc_18001B00B
0x18001af62  cmp     [rbx+20h], r13
0x18001af66  jz      loc_18001B00B
0x18001af6c  lea     rdx, [rsi+40h]; uBytes
0x18001af70  mov     ecx, 40h ; '@'; uFlags
0x18001af75  call    cs:__imp_LocalAlloc
0x18001af7b  mov     rdx, rax
0x18001af7e  lea     rcx, [rbp+47h+var_80]
0x18001af82  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_WEBAUTHN_CTAP_MANAGE_INTERNAL_CONTEXT@@P6AXPEAU1@@Z$1?_FreeInternalManageContext@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_WEBAUTHN_CTAP_MANAGE_INTERNAL_CONTEXT@@@Z; wil::details::unique_storage<wil::details::resource_policy<_WEBAUTHN_CTAP_MANAGE_INTERNAL_CONTEXT *,void (*)(_WEBAUTHN_CTAP_MANAGE_INTERNAL_CONTEXT *),&_FreeInternalManageContext(_WEBAUTHN_CTAP_MANAGE_INTERNAL_CONTEXT *),wistd::integral_constant<unsigned __int64,0>,_WEBAUTHN_CTAP_MANAGE_INTERNAL_CONTEXT *,_WEBAUTHN_CTAP_MANAGE_INTERNAL_CONTEXT *,0,std::nullptr_t>>::reset(_WEBAUTHN_CTAP_MANAGE_INTERNAL_CONTEXT *)
0x18001af87  mov     rdi, [rbp+47h+var_80]
0x18001af8b  test    rdi, rdi
0x18001af8e  jnz     short loc_18001AFB2
0x18001af90  mov     ebx, 8007000Eh
0x18001af95  mov     rcx, [rbp+4Fh]; this
0x18001af99  mov     r9d, ebx; char *
0x18001af9c  lea     r8, aOnecoreDsSecur_27; "onecore\\ds\\security\\fido\\webauthn\\"...
0x18001afa3  mov     edx, 1B81h; void *
0x18001afa8  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x18001afad  xor     r13d, r13d
0x18001afb0  jmp     short loc_18001B031
0x18001afb2  mov     eax, [rbp+47h+var_70]
0x18001afb5  mov     [rdi+18h], eax
0x18001afb8  lea     rcx, [rdi+40h]; void *
0x18001afbc  mov     [rdi+10h], rcx
0x18001afc0  mov     [rdi+8], esi
0x18001afc3  mov     r8, rsi; Size
0x18001afc6  mov     rdx, r15; Src
0x18001afc9  call    memcpy_0
0x18001afce  movups  xmm0, xmmword ptr [r14]
0x18001afd2  movdqu  xmmword ptr [rdi+1Ch], xmm0
0x18001afd7  mov     r9, rdi
0x18001afda  xor     r8d, r8d
0x18001afdd  xor     edx, edx
0x18001afdf  mov     rcx, rbx
0x18001afe2  call    _CreateSelectedDeviceInformation
0x18001afe7  mov     ebx, eax
0x18001afe9  mov     rcx, [rbp+4Fh]
0x18001afed  xor     r13d, r13d
0x18001aff0  test    eax, eax
0x18001aff2  jns     short loc_18001B001
0x18001aff4  mov     r9d, eax
0x18001aff7  mov     edx, 1B8Eh
0x18001affc  jmp     loc_18001AF0B
0x18001b001  mov     [rbp+47h+var_80], r13
0x18001b005  mov     [r12], rdi
0x18001b009  jmp     short loc_18001B031
0x18001b00b  mov     edx, 1B7Ch
0x18001b010  jmp     short loc_18001B017
0x18001b012  mov     edx, 1B71h; void *
0x18001b017  mov     r9d, 80090029h; char *
0x18001b01d  mov     ebx, r9d
0x18001b020  lea     r8, aOnecoreDsSecur_27; "onecore\\ds\\security\\fido\\webauthn\\"...
0x18001b027  mov     rcx, [rbp+4Fh]; this
0x18001b02b  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x18001b030  nop
0x18001b031  lea     rcx, [rbp+47h+var_80]
0x18001b035  call    ??1?$unique_storage@U?$resource_policy@PEAU_WEBAUTHN_CTAP_MANAGE_INTERNAL_CONTEXT@@P6AXPEAU1@@Z$1?_FreeInternalManageContext@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_WEBAUTHN_CTAP_MANAGE_INTERNAL_CONTEXT *,void (*)(_WEBAUTHN_CTAP_MANAGE_INTERNAL_CONTEXT *),&_FreeInternalManageContext(_WEBAUTHN_CTAP_MANAGE_INTERNAL_CONTEXT *),wistd::integral_constant<unsigned __int64,0>,_WEBAUTHN_CTAP_MANAGE_INTERNAL_CONTEXT *,_WEBAUTHN_CTAP_MANAGE_INTERNAL_CONTEXT *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_WEBAUTHN_CTAP_MANAGE_INTERNAL_CONTEXT *,void (*)(_WEBAUTHN_CTAP_MANAGE_INTERNAL_CONTEXT *),&_FreeInternalManageContext(_WEBAUTHN_CTAP_MANAGE_INTERNAL_CONTEXT *),wistd::integral_constant<unsigned __int64,0>,_WEBAUTHN_CTAP_MANAGE_INTERNAL_CONTEXT *,_WEBAUTHN_CTAP_MANAGE_INTERNAL_CONTEXT *,0,std::nullptr_t>>(void)
0x18001b03a  nop
0x18001b03b  mov     rcx, [rbp+47h+hMem]; hMem
0x18001b03f  mov     [rbp+47h+hMem], r13
0x18001b043  test    rcx, rcx
0x18001b046  jz      short loc_18001B04E
0x18001b048  call    cs:__imp_LocalFree
0x18001b04e  mov     eax, ebx
0x18001b050  mov     rcx, [rbp+47h+var_40]
0x18001b054  xor     rcx, rsp; StackCookie
0x18001b057  call    __security_check_cookie
0x18001b05c  mov     rbx, [rsp+0D0h+arg_8]
0x18001b064  add     rsp, 0A0h
0x18001b06b  pop     r15
0x18001b06d  pop     r14
0x18001b06f  pop     r13
0x18001b071  pop     r12
0x18001b073  pop     rdi
0x18001b074  pop     rsi
0x18001b075  pop     rbp
0x18001b076  retn
```
