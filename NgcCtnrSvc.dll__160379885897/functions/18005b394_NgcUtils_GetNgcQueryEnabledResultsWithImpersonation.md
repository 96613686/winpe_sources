# NgcUtils::GetNgcQueryEnabledResultsWithImpersonation

- ea: `0x18005b394`
- end: `0x18005b5e6`
- name: `NgcUtils::GetNgcQueryEnabledResultsWithImpersonation`
- size: `594`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18005b5ec`

## callees

- `0x180017f68`
- `0x18001a77c`
- `0x180022e68`
- `0x180023278`
- `0x1800232a0`
- `0x180024c4c`
- `0x1800264b8`
- `0x18005b308`
- `0x18005b378`
- `0x18005b394`
- `0x18005b640`
- `0x18005c1e4`

## import_xrefs

- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18005b4bf`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18005b4bf`
- `RPCRT4!RpcRevertToSelfEx` at `0x18005b473`
- `RPCRT4!RpcRevertToSelfEx` at `0x18005b5a9`
- `RPCRT4!RpcRevertToSelfEx` at `0x18005b473`
- `RPCRT4!RpcRevertToSelfEx` at `0x18005b5a9`
- `RPCRT4!RpcImpersonateClient` at `0x18005b3fc`
- `RPCRT4!RpcImpersonateClient` at `0x18005b3fc`
- `cryptngc!NgcQueryEnabled` at `0x18005b534`
- `cryptngc!NgcQueryEnabled` at `0x18005b534`
- `dsreg!DsrGetJoinInfo` at `0x18005b3b5`
- `dsreg!DsrGetJoinInfo` at `0x18005b3b5`

## string_xrefs

- `0x18005b3ce`: `onecore\ds\security\ngc\utils\common\lib\policyutils.cpp`
- `0x18005b413`: `onecore\ds\security\ngc\utils\common\lib\policyutils.cpp`
- `0x18005b455`: `onecore\ds\security\ngc\utils\common\lib\policyutils.cpp`
- `0x18005b48e`: `onecore\ds\security\ngc\utils\common\lib\policyutils.cpp`
- `0x18005b4d3`: `onecore\ds\security\ngc\utils\common\lib\policyutils.cpp`
- `0x18005b54d`: `onecore\ds\security\ngc\utils\common\lib\policyutils.cpp`
- `0x18005b5c0`: `onecore\ds\security\ngc\utils\common\lib\policyutils.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall NgcUtils::GetNgcQueryEnabledResultsWithImpersonation(__int64 a1, __int64 a2)
{
  int JoinInfo; // eax
  unsigned int LastError; // ebx
  unsigned int v4; // eax
  __int64 v5; // rcx
  int UserSidFromToken; // eax
  unsigned int v7; // eax
  const char *v8; // r9
  int v9; // eax
  char NgcDeploymentTypeHelper; // al
  int v11; // edx
  int v12; // ecx
  unsigned int v13; // eax
  unsigned int v15; // [rsp+20h] [rbp-48h]
  int *v16; // [rsp+20h] [rbp-48h]
  LPWSTR StringSid; // [rsp+38h] [rbp-30h] BYREF
  __int64 v18; // [rsp+40h] [rbp-28h] BYREF
  PSID Sid[2]; // [rsp+48h] [rbp-20h] BYREF
  __int64 v20; // [rsp+58h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+10h]
  __int64 v22; // [rsp+80h] [rbp+18h] BYREF
  __int64 v23; // [rsp+88h] [rbp+20h]
  int v24; // [rsp+90h] [rbp+28h] BYREF
  unsigned int v25; // [rsp+98h] [rbp+30h] BYREF

  v23 = a2;
  v22 = a1;
  v18 = 0;
  JoinInfo = DsrGetJoinInfo(0, &v18);
  LastError = JoinInfo;
  if ( JoinInfo < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x26,
      (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\policyutils.cpp",
      (const char *)(unsigned int)JoinInfo,
      v15);
    goto LABEL_21;
  }
  if ( !v18 || !*(_DWORD *)v18 )
    goto LABEL_20;
  v4 = RpcImpersonateClient(0);
  if ( v4 )
  {
    LastError = wil::details::in1diag3::Return_Win32(
                  retaddr,
                  (void *)0x2D,
                  (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\policyutils.cpp",
                  (const char *)v4,
                  v15);
    goto LABEL_21;
  }
  BYTE1(v23) = 1;
  *(_OWORD *)Sid = 0;
  v20 = 0;
  UserSidFromToken = NgcUtils::GetUserSidFromToken(v5, Sid);
  LastError = UserSidFromToken;
  if ( UserSidFromToken < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x34,
      (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\policyutils.cpp",
      (const char *)(unsigned int)UserSidFromToken,
      v15);
    goto LABEL_9;
  }
  StringSid = 0;
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    &StringSid,
    0);
  if ( ConvertSidToStringSidW(Sid[0], &StringSid) )
  {
    LODWORD(v22) = 2;
    v25 = 0;
    v24 = 32;
    v16 = &v24;
    v9 = NgcQueryEnabled(StringSid, *(_QWORD *)(v18 + 32), &v22, &v25);
    LastError = v9;
    if ( v9 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x42,
        (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\policyutils.cpp",
        (const char *)(unsigned int)v9,
        (int)&v24);
      goto LABEL_13;
    }
    NgcDeploymentTypeHelper = NgcUtils::GetNgcDeploymentTypeHelper(&v24);
    if ( (Microsoft_Windows_HelloForBusinessEnableBits & 0x10) != 0 )
      McTemplateU0kqqq_EventWriteTransfer(v12, v11, Sid[0], v22, v25, NgcDeploymentTypeHelper);
    dword_1800BED20 = v22;
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&StringSid);
    std::vector<unsigned char>::_Tidy(Sid);
    v13 = RpcRevertToSelfEx(0);
    if ( v13 )
      wil::details::in1diag3::_Log_Win32(
        retaddr,
        (void *)0x30,
        (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\policyutils.cpp",
        (const char *)v13,
        (unsigned int)v16);
LABEL_20:
    LastError = 0;
    goto LABEL_21;
  }
  LastError = wil::details::in1diag3::Return_GetLastError(
                retaddr,
                (void *)0x37,
                (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\policyutils.cpp",
                v8);
LABEL_13:
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&StringSid);
LABEL_9:
  std::vector<unsigned char>::_Tidy(Sid);
  v7 = RpcRevertToSelfEx(0);
  if ( v7 )
    wil::details::in1diag3::_Log_Win32(
      retaddr,
      (void *)0x30,
      (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\policyutils.cpp",
      (const char *)v7,
      v15);
LABEL_21:
  wil::details::unique_storage<wil::details::resource_policy<_DSREG_JOIN_INFO *,void (*)(_DSREG_JOIN_INFO *),&void DsrFreeJoinInfo(_DSREG_JOIN_INFO *),wistd::integral_constant<unsigned __int64,0>,_DSREG_JOIN_INFO *,_DSREG_JOIN_INFO *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_DSREG_JOIN_INFO *,void (*)(_DSREG_JOIN_INFO *),&void DsrFreeJoinInfo(_DSREG_JOIN_INFO *),wistd::integral_constant<unsigned __int64,0>,_DSREG_JOIN_INFO *,_DSREG_JOIN_INFO *,0,std::nullptr_t>>(&v18);
  return LastError;
}

```

## disassembly

```asm
0x18005b394  mov     [rsp-10h+arg_8], rdx
0x18005b399  mov     [rsp-10h+arg_0], rcx
0x18005b39e  push    rbp
0x18005b39f  push    rbx
0x18005b3a0  mov     rbp, rsp
0x18005b3a3  sub     rsp, 68h
0x18005b3a7  mov     [rbp+var_28], 0
0x18005b3af  lea     rdx, [rbp+var_28]
0x18005b3b3  xor     ecx, ecx
0x18005b3b5  call    cs:__imp_DsrGetJoinInfo
0x18005b3bc  nop     dword ptr [rax+rax+00h]
0x18005b3c1  mov     ebx, eax
0x18005b3c3  test    eax, eax
0x18005b3c5  jns     short loc_18005B3E4
0x18005b3c7  mov     rcx, [rbp+10h]; this
0x18005b3cb  mov     r9d, eax; char *
0x18005b3ce  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x18005b3d5  mov     edx, 26h ; '&'; void *
0x18005b3da  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005b3df  jmp     loc_18005B5D3
0x18005b3e4  mov     rax, [rbp+var_28]
0x18005b3e8  test    rax, rax
0x18005b3eb  jz      loc_18005B5D1
0x18005b3f1  cmp     dword ptr [rax], 0
0x18005b3f4  jz      loc_18005B5D1
0x18005b3fa  xor     ecx, ecx; BindingHandle
0x18005b3fc  call    cs:__imp_RpcImpersonateClient
0x18005b403  nop     dword ptr [rax+rax+00h]
0x18005b408  test    eax, eax
0x18005b40a  jz      short loc_18005B42B
0x18005b40c  mov     rcx, [rbp+10h]; this
0x18005b410  mov     r9d, eax; char *
0x18005b413  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x18005b41a  mov     edx, 2Dh ; '-'; void *
0x18005b41f  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18005b424  mov     ebx, eax
0x18005b426  jmp     loc_18005B5D3
0x18005b42b  mov     byte ptr [rbp+arg_8+1], 1
0x18005b42f  xorps   xmm0, xmm0
0x18005b432  movdqu  xmmword ptr [rbp+Sid], xmm0
0x18005b437  mov     [rbp+var_10], 0
0x18005b43f  lea     rdx, [rbp+Sid]
0x18005b443  call    NgcUtils__GetUserSidFromToken
0x18005b448  mov     ebx, eax
0x18005b44a  test    eax, eax
0x18005b44c  jns     short loc_18005B4A4
0x18005b44e  mov     rcx, [rbp+10h]; this
0x18005b452  mov     r9d, eax; char *
0x18005b455  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x18005b45c  mov     edx, 34h ; '4'; void *
0x18005b461  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005b466  nop
0x18005b467  lea     rcx, [rbp+Sid]
0x18005b46b  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x18005b470  nop
0x18005b471  xor     ecx, ecx; BindingHandle
0x18005b473  call    cs:__imp_RpcRevertToSelfEx
0x18005b47a  nop     dword ptr [rax+rax+00h]
0x18005b47f  mov     rcx, [rbp+10h]; this
0x18005b483  test    eax, eax
0x18005b485  jz      loc_18005B5D3
0x18005b48b  mov     r9d, eax; char *
0x18005b48e  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x18005b495  mov     edx, 30h ; '0'; void *
0x18005b49a  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x18005b49f  jmp     loc_18005B5D3
0x18005b4a4  mov     [rbp+StringSid], 0
0x18005b4ac  xor     edx, edx
0x18005b4ae  lea     rcx, [rbp+StringSid]
0x18005b4b2  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18005b4b7  lea     rdx, [rbp+StringSid]; StringSid
0x18005b4bb  mov     rcx, [rbp+Sid]; Sid
0x18005b4bf  call    cs:__imp_ConvertSidToStringSidW
0x18005b4c6  nop     dword ptr [rax+rax+00h]
0x18005b4cb  test    eax, eax
0x18005b4cd  jnz     short loc_18005B4F2
0x18005b4cf  mov     rcx, [rbp+10h]; this
0x18005b4d3  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x18005b4da  lea     edx, [rax+37h]; void *
0x18005b4dd  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18005b4e2  mov     ebx, eax
0x18005b4e4  lea     rcx, [rbp+StringSid]
0x18005b4e8  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x18005b4ed  jmp     loc_18005B467
0x18005b4f2  mov     [rbp+var_38], 0
0x18005b4f9  mov     dword ptr [rbp+arg_0], 2
0x18005b500  mov     [rbp+arg_18], 0
0x18005b507  mov     [rbp+arg_10], 20h ; ' '
0x18005b50e  lea     rax, [rbp+var_38]
0x18005b512  mov     [rsp+68h+var_40], rax
0x18005b517  lea     rax, [rbp+arg_10]
0x18005b51b  mov     qword ptr [rsp+68h+var_48], rax; int
0x18005b520  lea     r9, [rbp+arg_18]
0x18005b524  lea     r8, [rbp+arg_0]
0x18005b528  mov     rdx, [rbp+var_28]
0x18005b52c  mov     rdx, [rdx+20h]
0x18005b530  mov     rcx, [rbp+StringSid]
0x18005b534  call    cs:__imp_NgcQueryEnabled
0x18005b53b  nop     dword ptr [rax+rax+00h]
0x18005b540  mov     ebx, eax
0x18005b542  test    eax, eax
0x18005b544  jns     short loc_18005B560
0x18005b546  mov     rcx, [rbp+10h]; this
0x18005b54a  mov     r9d, eax; char *
0x18005b54d  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x18005b554  mov     edx, 42h ; 'B'; void *
0x18005b559  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005b55e  jmp     short loc_18005B4E4
0x18005b560  lea     rcx, [rbp+arg_10]
0x18005b564  call    ?GetNgcDeploymentTypeHelper@NgcUtils@@YA?AW4_NgcDeploymentTypes@@AEBW4_NgcEnabledModifiers@@@Z; NgcUtils::GetNgcDeploymentTypeHelper(_NgcEnabledModifiers const &)
0x18005b569  test    cs:Microsoft_Windows_HelloForBusinessEnableBits, 10h
0x18005b570  jz      short loc_18005B58A
0x18005b572  mov     dword ptr [rsp+68h+var_40], eax
0x18005b576  mov     eax, [rbp+arg_18]
0x18005b579  mov     [rsp+68h+var_48], eax; unsigned int
0x18005b57d  mov     r9d, dword ptr [rbp+arg_0]
0x18005b581  mov     r8, [rbp+Sid]
0x18005b585  call    McTemplateU0kqqq_EventWriteTransfer
0x18005b58a  mov     eax, dword ptr [rbp+arg_0]
0x18005b58d  mov     cs:dword_1800BED20, eax
0x18005b593  lea     rcx, [rbp+StringSid]
0x18005b597  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x18005b59c  nop
0x18005b59d  lea     rcx, [rbp+Sid]
0x18005b5a1  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x18005b5a6  nop
0x18005b5a7  xor     ecx, ecx; BindingHandle
0x18005b5a9  call    cs:__imp_RpcRevertToSelfEx
0x18005b5b0  nop     dword ptr [rax+rax+00h]
0x18005b5b5  mov     rcx, [rbp+10h]; this
0x18005b5b9  test    eax, eax
0x18005b5bb  jz      short loc_18005B5D1
0x18005b5bd  mov     r9d, eax; char *
0x18005b5c0  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x18005b5c7  mov     edx, 30h ; '0'; void *
0x18005b5cc  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x18005b5d1  xor     ebx, ebx
0x18005b5d3  lea     rcx, [rbp+var_28]
0x18005b5d7  call    ??1?$unique_storage@U?$resource_policy@PEAU_DSREG_JOIN_INFO@@P6AXPEAU1@@Z$1?DsrFreeJoinInfo@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_DSREG_JOIN_INFO *,void (*)(_DSREG_JOIN_INFO *),&DsrFreeJoinInfo(_DSREG_JOIN_INFO *),wistd::integral_constant<unsigned __int64,0>,_DSREG_JOIN_INFO *,_DSREG_JOIN_INFO *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_DSREG_JOIN_INFO *,void (*)(_DSREG_JOIN_INFO *),&DsrFreeJoinInfo(_DSREG_JOIN_INFO *),wistd::integral_constant<unsigned __int64,0>,_DSREG_JOIN_INFO *,_DSREG_JOIN_INFO *,0,std::nullptr_t>>(void)
0x18005b5dc  mov     eax, ebx
0x18005b5de  add     rsp, 68h
0x18005b5e2  pop     rbx
0x18005b5e3  pop     rbp
0x18005b5e4  retn
```
