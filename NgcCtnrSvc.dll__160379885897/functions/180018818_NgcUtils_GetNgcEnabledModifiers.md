# NgcUtils::GetNgcEnabledModifiers

- ea: `0x180018818`
- end: `0x1800189eb`
- name: `NgcUtils::GetNgcEnabledModifiers`
- size: `467`
- prototype: ``
- caller_count: `2`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18000d8bc`
- `0x1800187b4`

## callees

- `0x1800068a0`
- `0x180017f68`
- `0x180018818`
- `0x18001a77c`
- `0x180022e68`
- `0x180023278`
- `0x180024c4c`
- `0x1800264b8`
- `0x18005c1e4`

## import_xrefs

- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800188f0`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800188f0`
- `cryptngc!NgcQueryEnabled` at `0x18001895c`
- `cryptngc!NgcQueryEnabled` at `0x18001895c`
- `dsreg!DsrFreeJoinInfo` at `0x180018876`
- `dsreg!DsrFreeJoinInfo` at `0x1800189dd`
- `dsreg!DsrFreeJoinInfo` at `0x180018876`
- `dsreg!DsrFreeJoinInfo` at `0x1800189dd`
- `dsreg!DsrGetJoinInfo` at `0x180018842`
- `dsreg!DsrGetJoinInfo` at `0x180018842`

## string_xrefs

- `0x18001885b`: `onecore\ds\security\ngc\utils\common\lib\policyutils.cpp`
- `0x1800188bf`: `onecore\ds\security\ngc\utils\common\lib\policyutils.cpp`
- `0x180018904`: `onecore\ds\security\ngc\utils\common\lib\policyutils.cpp`
- `0x180018975`: `onecore\ds\security\ngc\utils\common\lib\policyutils.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall NgcUtils::GetNgcEnabledModifiers(int *a1)
{
  int v2; // eax
  int JoinInfo; // eax
  unsigned int LastError; // ebx
  __int64 v6; // rcx
  int UserSidFromToken; // eax
  const char *v8; // r9
  int v9; // eax
  int v10; // [rsp+20h] [rbp-40h]
  LPWSTR StringSid; // [rsp+30h] [rbp-30h] BYREF
  __int64 v12; // [rsp+38h] [rbp-28h] BYREF
  PSID Sid[4]; // [rsp+40h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+18h]
  int v15; // [rsp+90h] [rbp+30h] BYREF
  int v16; // [rsp+98h] [rbp+38h] BYREF

  v2 = dword_1800C18A4;
  if ( !dword_1800C18A4 )
  {
    v12 = 0;
    JoinInfo = DsrGetJoinInfo(0, &v12);
    LastError = JoinInfo;
    if ( JoinInfo < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x63,
        (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\policyutils.cpp",
        (const char *)(unsigned int)JoinInfo,
        v10);
      if ( v12 )
        DsrFreeJoinInfo();
      return LastError;
    }
    if ( !v12 || !*(_DWORD *)v12 )
    {
      if ( v12 )
        DsrFreeJoinInfo();
      return 0;
    }
    std::vector<_GUID>::vector<_GUID>(Sid);
    UserSidFromToken = NgcUtils::GetUserSidFromToken(v6, Sid);
    LastError = UserSidFromToken;
    if ( UserSidFromToken < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x6B,
        (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\policyutils.cpp",
        (const char *)(unsigned int)UserSidFromToken,
        v10);
LABEL_15:
      std::vector<unsigned char>::_Tidy(Sid);
      wil::details::unique_storage<wil::details::resource_policy<_DSREG_JOIN_INFO *,void (*)(_DSREG_JOIN_INFO *),&void DsrFreeJoinInfo(_DSREG_JOIN_INFO *),wistd::integral_constant<unsigned __int64,0>,_DSREG_JOIN_INFO *,_DSREG_JOIN_INFO *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_DSREG_JOIN_INFO *,void (*)(_DSREG_JOIN_INFO *),&void DsrFreeJoinInfo(_DSREG_JOIN_INFO *),wistd::integral_constant<unsigned __int64,0>,_DSREG_JOIN_INFO *,_DSREG_JOIN_INFO *,0,std::nullptr_t>>(&v12);
      return LastError;
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
LABEL_14:
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&StringSid);
      goto LABEL_15;
    }
    v16 = 2;
    v15 = 0;
    dword_1800C18A4 |= 0x20u;
    v9 = NgcQueryEnabled(StringSid, *(_QWORD *)(v12 + 32), &v16, &v15);
    LastError = v9;
    if ( v9 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x7A,
        (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\policyutils.cpp",
        (const char *)(unsigned int)v9,
        (int)&dword_1800C18A4);
      goto LABEL_14;
    }
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&StringSid);
    std::vector<unsigned char>::_Tidy(Sid);
    wil::details::unique_storage<wil::details::resource_policy<_DSREG_JOIN_INFO *,void (*)(_DSREG_JOIN_INFO *),&void DsrFreeJoinInfo(_DSREG_JOIN_INFO *),wistd::integral_constant<unsigned __int64,0>,_DSREG_JOIN_INFO *,_DSREG_JOIN_INFO *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_DSREG_JOIN_INFO *,void (*)(_DSREG_JOIN_INFO *),&void DsrFreeJoinInfo(_DSREG_JOIN_INFO *),wistd::integral_constant<unsigned __int64,0>,_DSREG_JOIN_INFO *,_DSREG_JOIN_INFO *,0,std::nullptr_t>>(&v12);
    v2 = dword_1800C18A4;
  }
  *a1 = v2;
  return 0;
}

```

## disassembly

```asm
0x180018818  push    rbp
0x18001881a  push    rbx
0x18001881b  push    rdi
0x18001881c  mov     rbp, rsp
0x18001881f  sub     rsp, 60h
0x180018823  mov     rdi, rcx
0x180018826  mov     eax, cs:dword_1800C18A4
0x18001882c  test    eax, eax
0x18001882e  jnz     loc_1800189CB
0x180018834  mov     [rbp+var_28], 0
0x18001883c  lea     rdx, [rbp+var_28]
0x180018840  xor     ecx, ecx
0x180018842  call    cs:__imp_DsrGetJoinInfo
0x180018849  nop     dword ptr [rax+rax+00h]
0x18001884e  mov     ebx, eax
0x180018850  test    eax, eax
0x180018852  jns     short loc_180018889
0x180018854  mov     rcx, [rbp+18h]; this
0x180018858  mov     r9d, eax; char *
0x18001885b  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x180018862  mov     edx, 63h ; 'c'; void *
0x180018867  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001886c  nop
0x18001886d  mov     rcx, [rbp+var_28]
0x180018871  test    rcx, rcx
0x180018874  jz      short loc_180018882
0x180018876  call    cs:__imp_DsrFreeJoinInfo
0x18001887d  nop     dword ptr [rax+rax+00h]
0x180018882  mov     eax, ebx
0x180018884  jmp     loc_1800189CF
0x180018889  mov     rcx, [rbp+var_28]
0x18001888d  test    rcx, rcx
0x180018890  jz      loc_1800189D8
0x180018896  cmp     dword ptr [rcx], 0
0x180018899  jz      loc_1800189D8
0x18001889f  lea     rcx, [rbp+Sid]
0x1800188a3  call    ??0?$vector@U_GUID@@V?$allocator@U_GUID@@@std@@@std@@QEAA@XZ; std::vector<_GUID>::vector<_GUID>(void)
0x1800188a8  nop
0x1800188a9  lea     rdx, [rbp+Sid]
0x1800188ad  call    NgcUtils__GetUserSidFromToken
0x1800188b2  mov     ebx, eax
0x1800188b4  test    eax, eax
0x1800188b6  jns     short loc_1800188D5
0x1800188b8  mov     rcx, [rbp+18h]; this
0x1800188bc  mov     r9d, eax; char *
0x1800188bf  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x1800188c6  mov     edx, 6Bh ; 'k'; void *
0x1800188cb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800188d0  jmp     loc_180018990
0x1800188d5  mov     [rbp+StringSid], 0
0x1800188dd  xor     edx, edx
0x1800188df  lea     rcx, [rbp+StringSid]
0x1800188e3  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x1800188e8  lea     rdx, [rbp+StringSid]; StringSid
0x1800188ec  mov     rcx, [rbp+Sid]; Sid
0x1800188f0  call    cs:__imp_ConvertSidToStringSidW
0x1800188f7  nop     dword ptr [rax+rax+00h]
0x1800188fc  test    eax, eax
0x1800188fe  jnz     short loc_180018917
0x180018900  mov     rcx, [rbp+18h]; this
0x180018904  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x18001890b  lea     edx, [rax+6Eh]; void *
0x18001890e  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180018913  mov     ebx, eax
0x180018915  jmp     short loc_180018986
0x180018917  mov     [rbp+arg_18], 2
0x18001891e  mov     [rbp+arg_10], 0
0x180018925  mov     [rbp+arg_8], 0
0x18001892c  or      cs:dword_1800C18A4, 20h
0x180018933  lea     rax, [rbp+arg_8]
0x180018937  mov     [rsp+60h+var_38], rax
0x18001893c  lea     rax, dword_1800C18A4
0x180018943  mov     qword ptr [rsp+60h+var_40], rax; int
0x180018948  lea     r9, [rbp+arg_10]
0x18001894c  lea     r8, [rbp+arg_18]
0x180018950  mov     rdx, [rbp+var_28]
0x180018954  mov     rdx, [rdx+20h]
0x180018958  mov     rcx, [rbp+StringSid]
0x18001895c  call    cs:__imp_NgcQueryEnabled
0x180018963  nop     dword ptr [rax+rax+00h]
0x180018968  mov     ebx, eax
0x18001896a  test    eax, eax
0x18001896c  jns     short loc_1800189A8
0x18001896e  mov     rcx, [rbp+18h]; this
0x180018972  mov     r9d, eax; char *
0x180018975  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x18001897c  mov     edx, 7Ah ; 'z'; void *
0x180018981  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180018986  lea     rcx, [rbp+StringSid]
0x18001898a  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x18001898f  nop
0x180018990  lea     rcx, [rbp+Sid]
0x180018994  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x180018999  nop
0x18001899a  lea     rcx, [rbp+var_28]
0x18001899e  call    ??1?$unique_storage@U?$resource_policy@PEAU_DSREG_JOIN_INFO@@P6AXPEAU1@@Z$1?DsrFreeJoinInfo@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_DSREG_JOIN_INFO *,void (*)(_DSREG_JOIN_INFO *),&DsrFreeJoinInfo(_DSREG_JOIN_INFO *),wistd::integral_constant<unsigned __int64,0>,_DSREG_JOIN_INFO *,_DSREG_JOIN_INFO *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_DSREG_JOIN_INFO *,void (*)(_DSREG_JOIN_INFO *),&DsrFreeJoinInfo(_DSREG_JOIN_INFO *),wistd::integral_constant<unsigned __int64,0>,_DSREG_JOIN_INFO *,_DSREG_JOIN_INFO *,0,std::nullptr_t>>(void)
0x1800189a3  jmp     loc_180018882
0x1800189a8  lea     rcx, [rbp+StringSid]
0x1800189ac  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x1800189b1  nop
0x1800189b2  lea     rcx, [rbp+Sid]
0x1800189b6  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x1800189bb  nop
0x1800189bc  lea     rcx, [rbp+var_28]
0x1800189c0  call    ??1?$unique_storage@U?$resource_policy@PEAU_DSREG_JOIN_INFO@@P6AXPEAU1@@Z$1?DsrFreeJoinInfo@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_DSREG_JOIN_INFO *,void (*)(_DSREG_JOIN_INFO *),&DsrFreeJoinInfo(_DSREG_JOIN_INFO *),wistd::integral_constant<unsigned __int64,0>,_DSREG_JOIN_INFO *,_DSREG_JOIN_INFO *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_DSREG_JOIN_INFO *,void (*)(_DSREG_JOIN_INFO *),&DsrFreeJoinInfo(_DSREG_JOIN_INFO *),wistd::integral_constant<unsigned __int64,0>,_DSREG_JOIN_INFO *,_DSREG_JOIN_INFO *,0,std::nullptr_t>>(void)
0x1800189c5  mov     eax, cs:dword_1800C18A4
0x1800189cb  mov     [rdi], eax
0x1800189cd  xor     eax, eax
0x1800189cf  add     rsp, 60h
0x1800189d3  pop     rdi
0x1800189d4  pop     rbx
0x1800189d5  pop     rbp
0x1800189d6  retn
0x1800189d8  test    rcx, rcx
0x1800189db  jz      short loc_1800189CD
0x1800189dd  call    cs:__imp_DsrFreeJoinInfo
0x1800189e4  nop     dword ptr [rax+rax+00h]
0x1800189e9  jmp     short loc_1800189CD
```
