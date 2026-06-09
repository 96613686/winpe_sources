# NgcUtils::GetNgcEnabledModifiers

- ea: `0x18008f3b4`
- end: `0x18008f56c`
- name: `NgcUtils::GetNgcEnabledModifiers`
- size: `440`
- prototype: ``
- caller_count: `2`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180078a9c`
- `0x18008f574`

## callees

- `0x18000782c`
- `0x180007964`
- `0x180010990`
- `0x180020a0c`
- `0x1800281e0`
- `0x1800288a0`
- `0x1800334f0`
- `0x18004f1dc`
- `0x18008f3b4`

## import_xrefs

- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18008f488`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18008f488`
- `cryptngc!NgcQueryEnabled` at `0x18008f500`
- `cryptngc!NgcQueryEnabled` at `0x18008f500`

## string_xrefs

- `0x18008f3f2`: `onecore\ds\security\ngc\utils\common\lib\policyutils.cpp`
- `0x18008f44b`: `onecore\ds\security\ngc\utils\common\lib\policyutils.cpp`
- `0x18008f496`: `onecore\ds\security\ngc\utils\common\lib\policyutils.cpp`
- `0x18008f513`: `onecore\ds\security\ngc\utils\common\lib\policyutils.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall NgcUtils::GetNgcEnabledModifiers(int *a1)
{
  int v2; // eax
  int JoinInfo; // eax
  unsigned int LastError; // ebx
  _DWORD *v5; // rbx
  int UserSidFromToken; // eax
  int v7; // edi
  const char *v8; // r9
  int v9; // eax
  int v11; // [rsp+20h] [rbp-40h]
  LPWSTR StringSid; // [rsp+30h] [rbp-30h] BYREF
  _DWORD *v13; // [rsp+38h] [rbp-28h] BYREF
  PSID Sid[2]; // [rsp+40h] [rbp-20h] BYREF
  __int64 v15; // [rsp+50h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+18h]
  int v17; // [rsp+90h] [rbp+30h] BYREF
  int v18; // [rsp+98h] [rbp+38h] BYREF

  v2 = dword_180123264;
  if ( dword_180123264 )
    goto LABEL_14;
  v13 = 0;
  JoinInfo = DsrGetJoinInfo(a1, &v13);
  LastError = JoinInfo;
  if ( JoinInfo >= 0 )
  {
    v5 = v13;
    if ( !v13 || !*v13 )
    {
      LastError = 0;
      goto LABEL_16;
    }
    *(_OWORD *)Sid = 0;
    v15 = 0;
    UserSidFromToken = NgcUtils::GetUserSidFromToken((HANDLE)0xFFFFFFFFFFFFFFFALL, (const void **)Sid);
    v7 = UserSidFromToken;
    if ( UserSidFromToken < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x6B,
        (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\policyutils.cpp",
        (const char *)(unsigned int)UserSidFromToken,
        v11);
      std::vector<unsigned char>::_Tidy(Sid);
      LastError = v7;
      goto LABEL_16;
    }
    StringSid = 0;
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
      &StringSid,
      0);
    if ( !ConvertSidToStringSidW(Sid[0], &StringSid) )
    {
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0x6E,
                    (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\policyutils.cpp",
                    v8);
LABEL_10:
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&StringSid);
      std::vector<unsigned char>::_Tidy(Sid);
      goto LABEL_16;
    }
    v18 = 2;
    v17 = 0;
    dword_180123264 |= 0x20u;
    v9 = NgcQueryEnabled(StringSid, *((_QWORD *)v5 + 4), &v18, &v17);
    LastError = v9;
    if ( v9 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x7A,
        (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\policyutils.cpp",
        (const char *)(unsigned int)v9,
        (int)&dword_180123264);
      goto LABEL_10;
    }
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&StringSid);
    std::vector<unsigned char>::_Tidy(Sid);
    wil::details::unique_storage<wil::details::resource_policy<_DSREG_JOIN_INFO *,void (*)(_DSREG_JOIN_INFO *),&void DsrFreeJoinInfo(_DSREG_JOIN_INFO *),wistd::integral_constant<unsigned __int64,0>,_DSREG_JOIN_INFO *,_DSREG_JOIN_INFO *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_DSREG_JOIN_INFO *,void (*)(_DSREG_JOIN_INFO *),&void DsrFreeJoinInfo(_DSREG_JOIN_INFO *),wistd::integral_constant<unsigned __int64,0>,_DSREG_JOIN_INFO *,_DSREG_JOIN_INFO *,0,std::nullptr_t>>(&v13);
    v2 = dword_180123264;
LABEL_14:
    *a1 = v2;
    return 0;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x63,
    (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\policyutils.cpp",
    (const char *)(unsigned int)JoinInfo,
    v11);
LABEL_16:
  wil::details::unique_storage<wil::details::resource_policy<_DSREG_JOIN_INFO *,void (*)(_DSREG_JOIN_INFO *),&void DsrFreeJoinInfo(_DSREG_JOIN_INFO *),wistd::integral_constant<unsigned __int64,0>,_DSREG_JOIN_INFO *,_DSREG_JOIN_INFO *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_DSREG_JOIN_INFO *,void (*)(_DSREG_JOIN_INFO *),&void DsrFreeJoinInfo(_DSREG_JOIN_INFO *),wistd::integral_constant<unsigned __int64,0>,_DSREG_JOIN_INFO *,_DSREG_JOIN_INFO *,0,std::nullptr_t>>(&v13);
  return LastError;
}

```

## disassembly

```asm
0x18008f3b4  mov     [rsp-18h+arg_0], rbx
0x18008f3b9  push    rbp
0x18008f3ba  push    rsi
0x18008f3bb  push    rdi
0x18008f3bc  mov     rbp, rsp
0x18008f3bf  sub     rsp, 60h
0x18008f3c3  mov     rsi, rcx
0x18008f3c6  mov     eax, cs:dword_180123264
0x18008f3cc  test    eax, eax
0x18008f3ce  jnz     loc_18008F549
0x18008f3d4  mov     [rbp+var_28], 0
0x18008f3dc  lea     rdx, [rbp+var_28]
0x18008f3e0  call    DsrGetJoinInfo
0x18008f3e5  mov     ebx, eax
0x18008f3e7  test    eax, eax
0x18008f3e9  jns     short loc_18008F408
0x18008f3eb  mov     rcx, [rbp+18h]; this
0x18008f3ef  mov     r9d, eax; char *
0x18008f3f2  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x18008f3f9  mov     edx, 63h ; 'c'; void *
0x18008f3fe  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008f403  jmp     loc_18008F55F
0x18008f408  mov     rbx, [rbp+var_28]
0x18008f40c  test    rbx, rbx
0x18008f40f  jz      loc_18008F55D
0x18008f415  cmp     dword ptr [rbx], 0
0x18008f418  jz      loc_18008F55D
0x18008f41e  xorps   xmm0, xmm0
0x18008f421  movdqu  xmmword ptr [rbp+Sid], xmm0
0x18008f426  mov     [rbp+var_10], 0
0x18008f42e  lea     rdx, [rbp+Sid]
0x18008f432  mov     rcx, 0FFFFFFFFFFFFFFFAh; TokenHandle
0x18008f439  call    NgcUtils__GetUserSidFromToken
0x18008f43e  mov     edi, eax
0x18008f440  test    eax, eax
0x18008f442  jns     short loc_18008F46D
0x18008f444  mov     rcx, [rbp+18h]; this
0x18008f448  mov     r9d, eax; char *
0x18008f44b  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x18008f452  mov     edx, 6Bh ; 'k'; void *
0x18008f457  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008f45c  nop
0x18008f45d  lea     rcx, [rbp+Sid]
0x18008f461  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x18008f466  mov     ebx, edi
0x18008f468  jmp     loc_18008F55F
0x18008f46d  mov     [rbp+StringSid], 0
0x18008f475  xor     edx, edx
0x18008f477  lea     rcx, [rbp+StringSid]
0x18008f47b  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18008f480  lea     rdx, [rbp+StringSid]; StringSid
0x18008f484  mov     rcx, [rbp+Sid]; Sid
0x18008f488  call    cs:__imp_ConvertSidToStringSidW
0x18008f48e  test    eax, eax
0x18008f490  jnz     short loc_18008F4BF
0x18008f492  mov     rcx, [rbp+18h]; this
0x18008f496  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x18008f49d  lea     edx, [rax+6Eh]; void *
0x18008f4a0  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18008f4a5  mov     ebx, eax
0x18008f4a7  lea     rcx, [rbp+StringSid]; void *
0x18008f4ab  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x18008f4b0  nop
0x18008f4b1  lea     rcx, [rbp+Sid]
0x18008f4b5  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x18008f4ba  jmp     loc_18008F55F
0x18008f4bf  mov     [rbp+arg_18], 2
0x18008f4c6  mov     [rbp+arg_10], 0
0x18008f4cd  mov     [rbp+arg_8], 0
0x18008f4d4  or      cs:dword_180123264, 20h
0x18008f4db  lea     rax, [rbp+arg_8]
0x18008f4df  mov     [rsp+60h+var_38], rax
0x18008f4e4  lea     rax, dword_180123264
0x18008f4eb  mov     qword ptr [rsp+60h+var_40], rax; int
0x18008f4f0  lea     r9, [rbp+arg_10]
0x18008f4f4  lea     r8, [rbp+arg_18]
0x18008f4f8  mov     rdx, [rbx+20h]
0x18008f4fc  mov     rcx, [rbp+StringSid]
0x18008f500  call    cs:__imp_NgcQueryEnabled
0x18008f506  mov     ebx, eax
0x18008f508  test    eax, eax
0x18008f50a  jns     short loc_18008F526
0x18008f50c  mov     rcx, [rbp+18h]; this
0x18008f510  mov     r9d, eax; char *
0x18008f513  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x18008f51a  mov     edx, 7Ah ; 'z'; void *
0x18008f51f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008f524  jmp     short loc_18008F4A7
0x18008f526  lea     rcx, [rbp+StringSid]; void *
0x18008f52a  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x18008f52f  nop
0x18008f530  lea     rcx, [rbp+Sid]
0x18008f534  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x18008f539  nop
0x18008f53a  lea     rcx, [rbp+var_28]
0x18008f53e  call    ??1?$unique_storage@U?$resource_policy@PEAU_DSREG_JOIN_INFO@@P6AXPEAU1@@Z$1?DsrFreeJoinInfo@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_DSREG_JOIN_INFO *,void (*)(_DSREG_JOIN_INFO *),&DsrFreeJoinInfo(_DSREG_JOIN_INFO *),wistd::integral_constant<unsigned __int64,0>,_DSREG_JOIN_INFO *,_DSREG_JOIN_INFO *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_DSREG_JOIN_INFO *,void (*)(_DSREG_JOIN_INFO *),&DsrFreeJoinInfo(_DSREG_JOIN_INFO *),wistd::integral_constant<unsigned __int64,0>,_DSREG_JOIN_INFO *,_DSREG_JOIN_INFO *,0,std::nullptr_t>>(void)
0x18008f543  mov     eax, cs:dword_180123264
0x18008f549  mov     [rsi], eax
0x18008f54b  xor     eax, eax
0x18008f54d  mov     rbx, [rsp+60h+arg_0]
0x18008f555  add     rsp, 60h
0x18008f559  pop     rdi
0x18008f55a  pop     rsi
0x18008f55b  pop     rbp
0x18008f55c  retn
0x18008f55d  xor     ebx, ebx
0x18008f55f  lea     rcx, [rbp+var_28]
0x18008f563  call    ??1?$unique_storage@U?$resource_policy@PEAU_DSREG_JOIN_INFO@@P6AXPEAU1@@Z$1?DsrFreeJoinInfo@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_DSREG_JOIN_INFO *,void (*)(_DSREG_JOIN_INFO *),&DsrFreeJoinInfo(_DSREG_JOIN_INFO *),wistd::integral_constant<unsigned __int64,0>,_DSREG_JOIN_INFO *,_DSREG_JOIN_INFO *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_DSREG_JOIN_INFO *,void (*)(_DSREG_JOIN_INFO *),&DsrFreeJoinInfo(_DSREG_JOIN_INFO *),wistd::integral_constant<unsigned __int64,0>,_DSREG_JOIN_INFO *,_DSREG_JOIN_INFO *,0,std::nullptr_t>>(void)
0x18008f568  mov     eax, ebx
0x18008f56a  jmp     short loc_18008F54D
```
