# DetectActivePCRBank(ushort *)

- ea: `0x1800249d8`
- end: `0x180024bfb`
- name: `?DetectActivePCRBank@@YAJPEAG@Z`
- size: `547`
- prototype: `__int64 __fastcall(unsigned __int16 *)`
- caller_count: `4`
- callee_count: `9`
- tags: `file_ops, registry_config`

## callers

- `0x180023894`
- `0x180026830`
- `0x18002fd90`
- `0x18005bae0`

## callees

- `0x1800133c4`
- `0x180014a60`
- `0x1800157c0`
- `0x1800249d8`
- `0x180024c04`
- `0x18005767c`
- `0x1800768a0`
- `0x180076998`
- `0x18007704c`

## import_xrefs

- `tbs!Tbsip_Context_Close` at `0x180024ab5`
- `tbs!Tbsip_Context_Close` at `0x180024b6f`
- `tbs!Tbsip_Context_Close` at `0x180024b91`
- `tbs!Tbsip_Context_Close` at `0x180024ab5`
- `tbs!Tbsip_Context_Close` at `0x180024b6f`
- `tbs!Tbsip_Context_Close` at `0x180024b91`
- `tbs!Tbsi_Get_TCG_Log` at `0x180024a50`
- `tbs!Tbsi_Get_TCG_Log` at `0x180024b30`
- `tbs!Tbsi_Get_TCG_Log` at `0x180024a50`
- `tbs!Tbsi_Get_TCG_Log` at `0x180024b30`
- `tbs!Tbsi_Context_Create` at `0x180024a29`
- `tbs!Tbsi_Context_Create` at `0x180024a29`

## pseudocode

```c
__int64 __fastcall DetectActivePCRBank(unsigned __int16 *a1)
{
  signed int TCG_Log; // eax
  unsigned int v3; // edi
  __int64 v4; // rdx
  void *v5; // rbx
  int inited; // eax
  const struct std::nothrow_t *v7; // rdx
  size_t v9; // rdi
  void *v10; // rax
  signed int v11; // eax
  const struct std::nothrow_t *v12; // rdx
  const struct std::nothrow_t *v13; // rdx
  __int64 v14; // rdx
  int *v15[3]; // [rsp+20h] [rbp-50h] BYREF
  _OWORD v16[3]; // [rsp+38h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+18h]
  unsigned int pOutputBufLen; // [rsp+90h] [rbp+20h] BYREF
  PVOID phContext; // [rsp+98h] [rbp+28h] BYREF
  TBS_CONTEXT_PARAMS pContextParams; // [rsp+A0h] [rbp+30h] BYREF
  int v21; // [rsp+A4h] [rbp+34h]

  KspFunctionLogger::KspFunctionLogger((KspFunctionLogger *)v15, L"DetectActivePCRBank", 1);
  if ( !a1 )
  {
    v3 = -2146893785;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x289,
      (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\tpmhelpers20.cpp",
      (const char *)0x80090027LL,
      (int)v15[0]);
    goto LABEL_11;
  }
  *a1 = 4;
  pContextParams.version = 2;
  v21 = 6;
  phContext = 0;
  TCG_Log = Tbsi_Context_Create(&pContextParams, &phContext);
  v3 = TCG_Log;
  if ( TCG_Log < 0 )
  {
    v14 = 663;
LABEL_26:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v14,
      (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\tpmhelpers20.cpp",
      (const char *)(unsigned int)TCG_Log,
      (int)v15[0]);
    goto LABEL_23;
  }
  pOutputBufLen = 0;
  TCG_Log = Tbsi_Get_TCG_Log(phContext, 0, &pOutputBufLen);
  v3 = TCG_Log;
  if ( TCG_Log < 0 )
  {
    v14 = 666;
    goto LABEL_26;
  }
  v4 = pOutputBufLen;
  v5 = 0;
  if ( !pOutputBufLen )
  {
LABEL_5:
    memset(v16, 0, 46);
    inited = WbclApiInitIterator(v5, v4, v16);
    v3 = inited;
    if ( inited >= 0 )
    {
      *a1 = WORD6(v16[2]);
      if ( v5 )
        operator delete(v5, v7);
      if ( phContext )
        Tbsip_Context_Close(phContext);
      v3 = 0;
      goto LABEL_11;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2A5,
      (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\tpmhelpers20.cpp",
      (const char *)(unsigned int)inited,
      (int)v15[0]);
    if ( v5 )
      operator delete(v5, v13);
LABEL_23:
    wil::details::unique_storage<wil::details::resource_policy<void *,unsigned int (*)(void *),&unsigned int Tbsip_Context_Close(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,unsigned int (*)(void *),&unsigned int Tbsip_Context_Close(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&phContext);
    goto LABEL_11;
  }
  v9 = pOutputBufLen;
  v10 = operator new[](pOutputBufLen, (const struct std::nothrow_t *)&std::nothrow);
  v5 = v10;
  if ( v10 )
  {
    memset_0(v10, 0, v9);
    v11 = Tbsi_Get_TCG_Log(phContext, (PBYTE)v5, &pOutputBufLen);
    v3 = v11;
    if ( v11 >= 0 )
    {
      v4 = pOutputBufLen;
      goto LABEL_5;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2A1,
      (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\tpmhelpers20.cpp",
      (const char *)(unsigned int)v11,
      (int)v15[0]);
    operator delete(v5, v12);
    if ( phContext )
      Tbsip_Context_Close(phContext);
  }
  else
  {
    if ( phContext )
      Tbsip_Context_Close(phContext);
    v3 = -2147024888;
  }
LABEL_11:
  KspFunctionLogger::~KspFunctionLogger(v15);
  return v3;
}

```

## disassembly

```asm
0x1800249d8  mov     [rsp-18h+arg_18], rbx
0x1800249dd  push    rbp
0x1800249de  push    rsi
0x1800249df  push    rdi
0x1800249e0  mov     rbp, rsp
0x1800249e3  sub     rsp, 70h
0x1800249e7  mov     rsi, rcx
0x1800249ea  lea     rdx, aDetectactivepc; "DetectActivePCRBank"
0x1800249f1  lea     rcx, [rbp+var_50]; this
0x1800249f5  mov     r8b, 1; bool
0x1800249f8  call    ??0KspFunctionLogger@@QEAA@QEBG_N@Z; KspFunctionLogger::KspFunctionLogger(ushort const * const,bool)
0x1800249fd  test    rsi, rsi
0x180024a00  jz      loc_180024ADF
0x180024a06  lea     rdx, [rbp+phContext]; phContext
0x180024a0a  mov     word ptr [rsi], 4
0x180024a0f  lea     rcx, [rbp+pContextParams]; pContextParams
0x180024a13  mov     [rbp+pContextParams.version], 2
0x180024a1a  mov     [rbp+arg_14], 6
0x180024a21  mov     [rbp+phContext], 0
0x180024a29  call    cs:__imp_Tbsi_Context_Create
0x180024a30  nop     dword ptr [rax+rax+00h]
0x180024a35  mov     edi, eax
0x180024a37  test    eax, eax
0x180024a39  js      loc_180024BDA
0x180024a3f  mov     rcx, [rbp+phContext]; hContext
0x180024a43  lea     r8, [rbp+pOutputBufLen]; pOutputBufLen
0x180024a47  xor     edx, edx; pOutputBuf
0x180024a49  mov     [rbp+pOutputBufLen], 0
0x180024a50  call    cs:__imp_Tbsi_Get_TCG_Log
0x180024a57  nop     dword ptr [rax+rax+00h]
0x180024a5c  mov     edi, eax
0x180024a5e  test    eax, eax
0x180024a60  js      loc_180024BE1
0x180024a66  mov     edx, [rbp+pOutputBufLen]
0x180024a69  xor     ebx, ebx
0x180024a6b  test    edx, edx
0x180024a6d  jnz     loc_180024AFE
0x180024a73  xorps   xmm0, xmm0
0x180024a76  lea     r8, [rbp+var_38]
0x180024a7a  movups  [rbp+var_28], xmm0
0x180024a7e  mov     rcx, rbx
0x180024a81  movups  [rbp+var_28+0Eh], xmm0
0x180024a85  movups  [rbp+var_38], xmm0
0x180024a89  call    WbclApiInitIterator
0x180024a8e  mov     edi, eax
0x180024a90  test    eax, eax
0x180024a92  js      loc_180024BA7
0x180024a98  movzx   eax, [rbp+var_C]
0x180024a9c  mov     [rsi], ax
0x180024a9f  test    rbx, rbx
0x180024aa2  jz      short loc_180024AAC
0x180024aa4  mov     rcx, rbx; void *
0x180024aa7  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180024aac  mov     rcx, [rbp+phContext]; hContext
0x180024ab0  test    rcx, rcx
0x180024ab3  jz      short loc_180024AC1
0x180024ab5  call    cs:__imp_Tbsip_Context_Close
0x180024abc  nop     dword ptr [rax+rax+00h]
0x180024ac1  xor     edi, edi
0x180024ac3  lea     rcx, [rbp+var_50]; this
0x180024ac7  call    ??1KspFunctionLogger@@QEAA@XZ; KspFunctionLogger::~KspFunctionLogger(void)
0x180024acc  mov     rbx, [rsp+70h+arg_18]
0x180024ad4  mov     eax, edi
0x180024ad6  add     rsp, 70h
0x180024ada  pop     rdi
0x180024adb  pop     rsi
0x180024adc  pop     rbp
0x180024add  retn
0x180024adf  mov     rcx, [rbp+18h]; this
0x180024ae3  lea     r8, aOnecoreBaseNgs_14; "onecore\\base\\ngscb\\platformcrypto\\p"...
0x180024aea  mov     edi, 80090027h
0x180024aef  mov     edx, 289h; void *
0x180024af4  mov     r9d, edi; char *
0x180024af7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180024afc  jmp     short loc_180024AC3
0x180024afe  mov     rdi, rdx
0x180024b01  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180024b08  mov     rcx, rdi; unsigned __int64
0x180024b0b  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180024b10  mov     rbx, rax
0x180024b13  test    rax, rax
0x180024b16  jz      short loc_180024B88
0x180024b18  mov     r8, rdi; Size
0x180024b1b  xor     edx, edx; Val
0x180024b1d  mov     rcx, rax; void *
0x180024b20  call    memset_0
0x180024b25  mov     rcx, [rbp+phContext]; hContext
0x180024b29  lea     r8, [rbp+pOutputBufLen]; pOutputBufLen
0x180024b2d  mov     rdx, rbx; pOutputBuf
0x180024b30  call    cs:__imp_Tbsi_Get_TCG_Log
0x180024b37  nop     dword ptr [rax+rax+00h]
0x180024b3c  mov     edi, eax
0x180024b3e  test    eax, eax
0x180024b40  jns     short loc_180024B80
0x180024b42  mov     rcx, [rbp+18h]; this
0x180024b46  lea     r8, aOnecoreBaseNgs_14; "onecore\\base\\ngscb\\platformcrypto\\p"...
0x180024b4d  mov     r9d, eax; char *
0x180024b50  mov     edx, 2A1h; void *
0x180024b55  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180024b5a  mov     rcx, rbx; void *
0x180024b5d  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180024b62  mov     rcx, [rbp+phContext]; hContext
0x180024b66  test    rcx, rcx
0x180024b69  jz      loc_180024AC3
0x180024b6f  call    cs:__imp_Tbsip_Context_Close
0x180024b76  nop     dword ptr [rax+rax+00h]
0x180024b7b  jmp     loc_180024AC3
0x180024b80  mov     edx, [rbp+pOutputBufLen]
0x180024b83  jmp     loc_180024A73
0x180024b88  mov     rcx, [rbp+phContext]; hContext
0x180024b8c  test    rcx, rcx
0x180024b8f  jz      short loc_180024B9D
0x180024b91  call    cs:__imp_Tbsip_Context_Close
0x180024b98  nop     dword ptr [rax+rax+00h]
0x180024b9d  mov     edi, 80070008h
0x180024ba2  jmp     loc_180024AC3
0x180024ba7  mov     rcx, [rbp+18h]; this
0x180024bab  lea     r8, aOnecoreBaseNgs_14; "onecore\\base\\ngscb\\platformcrypto\\p"...
0x180024bb2  mov     r9d, eax; char *
0x180024bb5  mov     edx, 2A5h; void *
0x180024bba  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180024bbf  test    rbx, rbx
0x180024bc2  jz      short loc_180024BCC
0x180024bc4  mov     rcx, rbx; void *
0x180024bc7  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180024bcc  lea     rcx, [rbp+phContext]
0x180024bd0  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AIPEAX@Z$1?Tbsip_Context_Close@@YAI0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,uint (*)(void *),&Tbsip_Context_Close(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,uint (*)(void *),&Tbsip_Context_Close(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180024bd5  jmp     loc_180024AC3
0x180024bda  mov     edx, 297h
0x180024bdf  jmp     short loc_180024BE6
0x180024be1  mov     edx, 29Ah; void *
0x180024be6  mov     rcx, [rbp+18h]; this
0x180024bea  lea     r8, aOnecoreBaseNgs_14; "onecore\\base\\ngscb\\platformcrypto\\p"...
0x180024bf1  mov     r9d, eax; char *
0x180024bf4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180024bf9  jmp     short loc_180024BCC
```
