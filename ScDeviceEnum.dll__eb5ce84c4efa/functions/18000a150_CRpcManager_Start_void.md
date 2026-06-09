# CRpcManager::_Start(void)

- ea: `0x18000a150`
- end: `0x18000a41b`
- name: `?_Start@CRpcManager@@AEAAJXZ`
- size: `715`
- prototype: `__int64 __fastcall(CRpcManager *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180009fbc`

## callees

- `0x180006d40`
- `0x1800071d4`
- `0x180008bbc`
- `0x180009d34`
- `0x180009d50`
- `0x180009ea8`
- `0x18000a150`
- `0x18001e020`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a209`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a209`
- `RPCRT4!RpcServerInterfaceGroupCreateW` at `0x18000a30c`
- `RPCRT4!RpcServerInterfaceGroupCreateW` at `0x18000a30c`
- `RPCRT4!RpcServerInterfaceGroupActivate` at `0x18000a379`
- `RPCRT4!RpcServerInterfaceGroupActivate` at `0x18000a379`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18000a1f4`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18000a1f4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000a3ed`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000a3ed`

## pseudocode

```c
__int64 __fastcall CRpcManager::_Start(CRpcManager *this)
{
  BOOL v2; // ebx
  signed int LastError; // ebx
  __int64 v4; // rcx
  __int64 v5; // rcx
  _QWORD *v6; // rcx
  int v7; // edx
  __int64 v8; // rcx
  HLOCAL v9; // rcx
  signed int v11; // [rsp+40h] [rbp-C0h] BYREF
  HLOCAL hMem; // [rsp+48h] [rbp-B8h] BYREF
  void **v13; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v14; // [rsp+58h] [rbp-A8h] BYREF
  int v15; // [rsp+60h] [rbp-A0h] BYREF
  _QWORD *v16; // [rsp+68h] [rbp-98h] BYREF
  _QWORD v17[3]; // [rsp+70h] [rbp-90h] BYREF
  HLOCAL *p_hMem; // [rsp+88h] [rbp-78h] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+90h] [rbp-70h] BYREF
  char v20; // [rsp+98h] [rbp-68h]
  int v21; // [rsp+A0h] [rbp-60h] BYREF
  __int64 *v22; // [rsp+A8h] [rbp-58h]
  __int128 v23; // [rsp+B0h] [rbp-50h]
  int v24; // [rsp+C0h] [rbp-40h]
  __int64 v25; // [rsp+C4h] [rbp-3Ch]
  __int64 v26; // [rsp+D0h] [rbp-30h]
  __int64 v27; // [rsp+D8h] [rbp-28h]
  const wchar_t *v28; // [rsp+E0h] [rbp-20h]
  HLOCAL v29; // [rsp+E8h] [rbp-18h]
  int v30; // [rsp+F0h] [rbp-10h] BYREF
  const wchar_t *v31; // [rsp+F8h] [rbp-8h]
  __int128 v32; // [rsp+100h] [rbp+0h]
  int v33; // [rsp+110h] [rbp+10h]
  char v34[24]; // [rsp+118h] [rbp+18h] BYREF

  v17[0] = v34;
  v17[1] = &v15;
  v17[2] = &v11;
  v11 = 0;
  v15 = 0;
  strcpy(v34, "CRpcManager::_Start");
  lambda_db5cb04996fb80c183f90877eaca9bf7_::operator()(v17);
  hMem = 0;
  v15 = 1;
  v16 = v17;
  SecurityDescriptor = 0;
  p_hMem = &hMem;
  v20 = 1;
  v2 = ConvertStringSecurityDescriptorToSecurityDescriptorW(
         L"D:(A;;GR;;;S-1-5-80-2381253463-2694003897-3435975801-3559003598-683041300)",
         1u,
         &SecurityDescriptor,
         0);
  wil::details::out_param_t<wistd::unique_ptr<void,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<void,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>(&p_hMem);
  if ( v2 )
  {
    v21 = 0;
    v23 = 0;
    v22 = qword_180021EC0;
    v24 = 41;
    v28 = L"INgcContainerEnum";
    v29 = hMem;
    v31 = L"ncalrpc";
    v25 = 1234;
    v26 = 0;
    v27 = 0;
    v30 = 0;
    v32 = 0;
    v33 = 10;
    v13 = &Microsoft::WRL::Wrappers::HandleT<ScDeviceEnum::RpcInterfaceGroupTraits>::`vftable';
    v14 = 0;
    Microsoft::WRL::Wrappers::HandleT<ScDeviceEnum::SwDeviceHandleTraits>::Close(&v13);
    LastError = RpcServerInterfaceGroupCreateW(&v21, 1, &v30, 1, -1, 0, 0, &v14);
    if ( LastError )
    {
      WppTraceIndent(v5, 2);
      v6 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_15;
      }
      v7 = 15;
    }
    else
    {
      LastError = RpcServerInterfaceGroupActivate(v14);
      if ( !LastError )
      {
        Microsoft::WRL::Wrappers::HandleT<ScDeviceEnum::SwDeviceHandleTraits>::Close(this);
        LastError = v11;
        *((_QWORD *)this + 1) = v14;
        v14 = 0;
LABEL_24:
        v13 = &Microsoft::WRL::Wrappers::HandleT<ScDeviceEnum::RpcInterfaceGroupTraits>::`vftable';
        Microsoft::WRL::Wrappers::HandleT<ScDeviceEnum::SwDeviceHandleTraits>::Close(&v13);
        goto LABEL_25;
      }
      WppTraceIndent(v8, 2);
      v6 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
LABEL_15:
        if ( LastError > 0 )
          LastError = (unsigned __int16)LastError | 0x80070000;
        v11 = LastError;
        goto LABEL_24;
      }
      v7 = 16;
    }
    WPP_SF_sd(
      v6[2],
      v7,
      (unsigned int)WPP_928efe7f53c93aa4abf71bc4391f3d39_Traceguids,
      (_DWORD)WPP_pszIndent,
      LastError);
    goto LABEL_15;
  }
  LastError = GetLastError();
  WppTraceIndent(v4, 2);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      14,
      (unsigned int)WPP_928efe7f53c93aa4abf71bc4391f3d39_Traceguids,
      (_DWORD)WPP_pszIndent,
      LastError);
  }
  if ( LastError > 0 )
    LastError = (unsigned __int16)LastError | 0x80070000;
  v11 = LastError;
LABEL_25:
  v9 = hMem;
  hMem = 0;
  if ( v9 )
    LocalFree(v9);
  WppTraceUnwinder__lambda_db5cb04996fb80c183f90877eaca9bf7____::_WppTraceUnwinder__lambda_db5cb04996fb80c183f90877eaca9bf7____(&v16);
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x18000a150  push    rbp
0x18000a152  push    rbx
0x18000a153  push    rsi
0x18000a154  push    rdi
0x18000a155  push    r14
0x18000a157  push    r15
0x18000a159  lea     rbp, [rsp-48h]
0x18000a15e  sub     rsp, 148h
0x18000a165  mov     rax, cs:__security_cookie
0x18000a16c  xor     rax, rsp
0x18000a16f  mov     [rbp+70h+var_40], rax
0x18000a173  mov     eax, dword ptr cs:aCrpcmanagerSta_0+10h; "art"
0x18000a179  mov     rdi, rcx
0x18000a17c  movups  xmm0, xmmword ptr cs:aCrpcmanagerSta_0; "CRpcManager::_Start"
0x18000a183  mov     dword ptr [rbp+70h+var_58+10h], eax
0x18000a186  lea     rcx, [rsp+170h+var_100]
0x18000a18b  lea     rax, [rbp+70h+var_58]
0x18000a18f  xor     esi, esi
0x18000a191  mov     [rsp+170h+var_100], rax
0x18000a196  lea     rax, [rsp+170h+var_110]
0x18000a19b  mov     [rsp+170h+var_F8], rax
0x18000a1a0  lea     rax, [rsp+170h+var_130]
0x18000a1a5  mov     [rbp+70h+var_F0], rax
0x18000a1a9  mov     [rsp+170h+var_130], esi
0x18000a1ad  mov     [rsp+170h+var_110], esi
0x18000a1b1  movups  xmmword ptr [rbp+70h+var_58], xmm0
0x18000a1b5  call    _lambda_db5cb04996fb80c183f90877eaca9bf7___operator__
0x18000a1ba  lea     r14d, [rsi+1]
0x18000a1be  mov     [rsp+170h+hMem], rsi
0x18000a1c3  lea     rax, [rsp+170h+var_100]
0x18000a1c8  mov     [rsp+170h+var_110], r14d
0x18000a1cd  mov     [rsp+170h+var_108], rax
0x18000a1d2  lea     r8, [rbp+70h+SecurityDescriptor]; SecurityDescriptor
0x18000a1d6  lea     rax, [rsp+170h+hMem]
0x18000a1db  mov     [rbp+70h+SecurityDescriptor], rsi
0x18000a1df  xor     r9d, r9d; SecurityDescriptorSize
0x18000a1e2  mov     [rbp+70h+var_E8], rax
0x18000a1e6  mov     edx, r14d; StringSDRevision
0x18000a1e9  mov     [rbp+70h+var_D8], r14b
0x18000a1ed  lea     rcx, StringSecurityDescriptor; "D:(A;;GR;;;S-1-5-80-2381253463-26940038"...
0x18000a1f4  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x18000a1fa  lea     rcx, [rbp+70h+var_E8]
0x18000a1fe  mov     ebx, eax
0x18000a200  call    ??1?$out_param_t@V?$unique_ptr@XU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<void,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<void,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>(void)
0x18000a205  test    ebx, ebx
0x18000a207  jnz     short loc_18000A26C
0x18000a209  call    cs:__imp_GetLastError
0x18000a20f  lea     edx, [rsi+2]
0x18000a212  mov     ebx, eax
0x18000a214  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18000a219  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a220  lea     rax, WPP_GLOBAL_Control
0x18000a227  cmp     rcx, rax
0x18000a22a  jz      short loc_18000A256
0x18000a22c  test    [rcx+1Ch], r14b
0x18000a230  jz      short loc_18000A256
0x18000a232  cmp     byte ptr [rcx+19h], 2
0x18000a236  jb      short loc_18000A256
0x18000a238  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x18000a23f  lea     edx, [rsi+0Eh]
0x18000a242  mov     rcx, [rcx+10h]
0x18000a246  lea     r8, WPP_928efe7f53c93aa4abf71bc4391f3d39_Traceguids
0x18000a24d  mov     [rsp+170h+var_150], ebx
0x18000a251  call    WPP_SF_sd
0x18000a256  test    ebx, ebx
0x18000a258  jle     short loc_18000A263
0x18000a25a  movzx   ebx, bx
0x18000a25d  or      ebx, 80070000h
0x18000a263  mov     [rsp+170h+var_130], ebx
0x18000a267  jmp     loc_18000A3DE
0x18000a26c  xorps   xmm0, xmm0
0x18000a26f  mov     [rbp+70h+var_D0], esi
0x18000a272  lea     rax, qword_180021EC0
0x18000a279  movdqa  [rbp+70h+var_C0], xmm0
0x18000a27e  mov     [rbp+70h+var_C8], rax
0x18000a282  lea     r15, ??_7?$HandleT@URpcInterfaceGroupTraits@ScDeviceEnum@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<ScDeviceEnum::RpcInterfaceGroupTraits>::`vftable'
0x18000a289  lea     rax, aIngccontainere; "INgcContainerEnum"
0x18000a290  mov     [rbp+70h+var_B0], 29h ; ')'
0x18000a297  mov     [rbp+70h+var_90], rax
0x18000a29b  lea     rcx, [rsp+170h+var_120]
0x18000a2a0  mov     rax, [rsp+170h+hMem]
0x18000a2a5  mov     [rbp+70h+var_88], rax
0x18000a2a9  lea     rax, aNcalrpc; "ncalrpc"
0x18000a2b0  mov     [rbp+70h+var_78], rax
0x18000a2b4  mov     [rbp+70h+var_AC], 4D2h
0x18000a2bc  mov     [rbp+70h+var_A0], rsi
0x18000a2c0  mov     [rbp+70h+var_98], rsi
0x18000a2c4  mov     [rbp+70h+var_80], esi
0x18000a2c7  movdqu  [rbp+70h+var_70], xmm0
0x18000a2cc  mov     [rbp+70h+var_60], 0Ah
0x18000a2d3  mov     [rsp+170h+var_120], r15
0x18000a2d8  mov     [rsp+170h+var_118], rsi
0x18000a2dd  call    ?Close@?$HandleT@USwDeviceHandleTraits@ScDeviceEnum@@@Wrappers@WRL@Microsoft@@QEAAXXZ; Microsoft::WRL::Wrappers::HandleT<ScDeviceEnum::SwDeviceHandleTraits>::Close(void)
0x18000a2e2  lea     rax, [rsp+170h+var_118]
0x18000a2e7  mov     r9d, r14d
0x18000a2ea  mov     [rsp+170h+var_138], rax
0x18000a2ef  lea     r8, [rbp+70h+var_80]
0x18000a2f3  mov     [rsp+170h+var_140], rsi
0x18000a2f8  lea     rcx, [rbp+70h+var_D0]
0x18000a2fc  mov     [rsp+170h+var_148], rsi
0x18000a301  mov     edx, r14d
0x18000a304  mov     [rsp+170h+var_150], 0FFFFFFFFh
0x18000a30c  call    cs:__imp_RpcServerInterfaceGroupCreateW
0x18000a312  mov     ebx, eax
0x18000a314  test    eax, eax
0x18000a316  jz      short loc_18000A374
0x18000a318  mov     edx, 2
0x18000a31d  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18000a322  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a329  lea     rax, WPP_GLOBAL_Control
0x18000a330  cmp     rcx, rax
0x18000a333  jz      short loc_18000A361
0x18000a335  test    [rcx+1Ch], r14b
0x18000a339  jz      short loc_18000A361
0x18000a33b  cmp     byte ptr [rcx+19h], 2
0x18000a33f  jb      short loc_18000A361
0x18000a341  mov     edx, 0Fh
0x18000a346  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x18000a34d  lea     r8, WPP_928efe7f53c93aa4abf71bc4391f3d39_Traceguids
0x18000a354  mov     rcx, [rcx+10h]
0x18000a358  mov     [rsp+170h+var_150], ebx
0x18000a35c  call    WPP_SF_sd
0x18000a361  test    ebx, ebx
0x18000a363  jle     short loc_18000A36E
0x18000a365  movzx   ebx, bx
0x18000a368  or      ebx, 80070000h
0x18000a36e  mov     [rsp+170h+var_130], ebx
0x18000a372  jmp     short loc_18000A3CF
0x18000a374  mov     rcx, [rsp+170h+var_118]
0x18000a379  call    cs:__imp_RpcServerInterfaceGroupActivate
0x18000a37f  mov     ebx, eax
0x18000a381  test    eax, eax
0x18000a383  jz      short loc_18000A3B5
0x18000a385  mov     edx, 2
0x18000a38a  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18000a38f  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a396  lea     rax, WPP_GLOBAL_Control
0x18000a39d  cmp     rcx, rax
0x18000a3a0  jz      short loc_18000A361
0x18000a3a2  test    [rcx+1Ch], r14b
0x18000a3a6  jz      short loc_18000A361
0x18000a3a8  cmp     byte ptr [rcx+19h], 2
0x18000a3ac  jb      short loc_18000A361
0x18000a3ae  mov     edx, 10h
0x18000a3b3  jmp     short loc_18000A346
0x18000a3b5  mov     rcx, rdi
0x18000a3b8  call    ?Close@?$HandleT@USwDeviceHandleTraits@ScDeviceEnum@@@Wrappers@WRL@Microsoft@@QEAAXXZ; Microsoft::WRL::Wrappers::HandleT<ScDeviceEnum::SwDeviceHandleTraits>::Close(void)
0x18000a3bd  mov     rax, [rsp+170h+var_118]
0x18000a3c2  mov     ebx, [rsp+170h+var_130]
0x18000a3c6  mov     [rdi+8], rax
0x18000a3ca  mov     [rsp+170h+var_118], rsi
0x18000a3cf  lea     rcx, [rsp+170h+var_120]
0x18000a3d4  mov     [rsp+170h+var_120], r15
0x18000a3d9  call    ?Close@?$HandleT@USwDeviceHandleTraits@ScDeviceEnum@@@Wrappers@WRL@Microsoft@@QEAAXXZ; Microsoft::WRL::Wrappers::HandleT<ScDeviceEnum::SwDeviceHandleTraits>::Close(void)
0x18000a3de  mov     rcx, [rsp+170h+hMem]; hMem
0x18000a3e3  mov     [rsp+170h+hMem], rsi
0x18000a3e8  test    rcx, rcx
0x18000a3eb  jz      short loc_18000A3F3
0x18000a3ed  call    cs:__imp_LocalFree
0x18000a3f3  lea     rcx, [rsp+170h+var_108]
0x18000a3f8  call    WppTraceUnwinder__lambda_db5cb04996fb80c183f90877eaca9bf7_______WppTraceUnwinder__lambda_db5cb04996fb80c183f90877eaca9bf7____
0x18000a3fd  mov     eax, ebx
0x18000a3ff  mov     rcx, [rbp+70h+var_40]
0x18000a403  xor     rcx, rsp; StackCookie
0x18000a406  call    __security_check_cookie
0x18000a40b  add     rsp, 148h
0x18000a412  pop     r15
0x18000a414  pop     r14
0x18000a416  pop     rdi
0x18000a417  pop     rsi
0x18000a418  pop     rbx
0x18000a419  pop     rbp
0x18000a41a  retn
```
