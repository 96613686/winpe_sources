# NgcUtils::GetNgcEnabledModifiers

- ea: `0x180071fcc`
- end: `0x180072172`
- name: `NgcUtils::GetNgcEnabledModifiers`
- size: `422`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180072178`

## callees

- `0x18000d60c`
- `0x18000d62c`
- `0x180011c1c`
- `0x180070bd4`
- `0x180070bf4`
- `0x180071fcc`
- `0x180074d0c`
- `0x180078adc`

## import_xrefs

- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18007208e`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18007208e`
- `cryptngc!NgcQueryEnabled` at `0x180072106`
- `cryptngc!NgcQueryEnabled` at `0x180072106`

## string_xrefs

- `0x18007200a`: `onecore\ds\security\ngc\utils\common\lib\policyutils.cpp`
- `0x18007205c`: `onecore\ds\security\ngc\utils\common\lib\policyutils.cpp`
- `0x18007209c`: `onecore\ds\security\ngc\utils\common\lib\policyutils.cpp`
- `0x180072119`: `onecore\ds\security\ngc\utils\common\lib\policyutils.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall NgcUtils::GetNgcEnabledModifiers(int *a1)
{
  int v2; // eax
  int JoinInfo; // eax
  __int64 v4; // rcx
  unsigned int LastError; // ebx
  _DWORD *v6; // rbx
  int UserSidFromToken; // eax
  int v8; // edi
  const char *v9; // r9
  int v10; // eax
  int v12; // [rsp+20h] [rbp-40h]
  LPWSTR StringSid; // [rsp+30h] [rbp-30h] BYREF
  _DWORD *v14; // [rsp+38h] [rbp-28h] BYREF
  PSID Sid[2]; // [rsp+40h] [rbp-20h] BYREF
  __int64 v16; // [rsp+50h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+18h]
  int v18; // [rsp+90h] [rbp+30h] BYREF
  int v19; // [rsp+98h] [rbp+38h] BYREF

  v2 = dword_1800C91F0;
  if ( dword_1800C91F0 )
    goto LABEL_14;
  v14 = 0;
  JoinInfo = DsrGetJoinInfo(a1, &v14);
  LastError = JoinInfo;
  if ( JoinInfo >= 0 )
  {
    v6 = v14;
    if ( !v14 || !*v14 )
    {
      LastError = 0;
      goto LABEL_16;
    }
    *(_OWORD *)Sid = 0;
    v16 = 0;
    UserSidFromToken = NgcUtils::GetUserSidFromToken(v4, Sid);
    v8 = UserSidFromToken;
    if ( UserSidFromToken < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x6B,
        (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\policyutils.cpp",
        (const char *)(unsigned int)UserSidFromToken,
        v12);
      std::vector<unsigned char>::_Tidy(Sid);
      LastError = v8;
      goto LABEL_16;
    }
    StringSid = 0;
    if ( !ConvertSidToStringSidW(Sid[0], &StringSid) )
    {
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0x6E,
                    (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\policyutils.cpp",
                    v9);
LABEL_10:
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&StringSid);
      std::vector<unsigned char>::_Tidy(Sid);
      goto LABEL_16;
    }
    v19 = 2;
    v18 = 0;
    dword_1800C91F0 |= 0x20u;
    v10 = NgcQueryEnabled(StringSid, *((_QWORD *)v6 + 4), &v19, &v18);
    LastError = v10;
    if ( v10 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x7A,
        (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\policyutils.cpp",
        (const char *)(unsigned int)v10,
        (int)&dword_1800C91F0);
      goto LABEL_10;
    }
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&StringSid);
    std::vector<unsigned char>::_Tidy(Sid);
    wil::details::unique_storage<wil::details::resource_policy<_DSREG_JOIN_INFO *,void (*)(_DSREG_JOIN_INFO *),&void DsrFreeJoinInfo(_DSREG_JOIN_INFO *),wistd::integral_constant<unsigned __int64,0>,_DSREG_JOIN_INFO *,_DSREG_JOIN_INFO *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_DSREG_JOIN_INFO *,void (*)(_DSREG_JOIN_INFO *),&void DsrFreeJoinInfo(_DSREG_JOIN_INFO *),wistd::integral_constant<unsigned __int64,0>,_DSREG_JOIN_INFO *,_DSREG_JOIN_INFO *,0,std::nullptr_t>>(&v14);
    v2 = dword_1800C91F0;
LABEL_14:
    *a1 = v2;
    return 0;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x63,
    (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\policyutils.cpp",
    (const char *)(unsigned int)JoinInfo,
    v12);
LABEL_16:
  wil::details::unique_storage<wil::details::resource_policy<_DSREG_JOIN_INFO *,void (*)(_DSREG_JOIN_INFO *),&void DsrFreeJoinInfo(_DSREG_JOIN_INFO *),wistd::integral_constant<unsigned __int64,0>,_DSREG_JOIN_INFO *,_DSREG_JOIN_INFO *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_DSREG_JOIN_INFO *,void (*)(_DSREG_JOIN_INFO *),&void DsrFreeJoinInfo(_DSREG_JOIN_INFO *),wistd::integral_constant<unsigned __int64,0>,_DSREG_JOIN_INFO *,_DSREG_JOIN_INFO *,0,std::nullptr_t>>(&v14);
  return LastError;
}

```

## disassembly

```asm
0x180071fcc  mov     [rsp-18h+arg_0], rbx
0x180071fd1  push    rbp
0x180071fd2  push    rsi
0x180071fd3  push    rdi
0x180071fd4  mov     rbp, rsp
0x180071fd7  sub     rsp, 60h
0x180071fdb  mov     rsi, rcx
0x180071fde  mov     eax, cs:dword_1800C91F0
0x180071fe4  test    eax, eax
0x180071fe6  jnz     loc_18007214F
0x180071fec  mov     [rbp+var_28], 0
0x180071ff4  lea     rdx, [rbp+var_28]
0x180071ff8  call    DsrGetJoinInfo
0x180071ffd  mov     ebx, eax
0x180071fff  test    eax, eax
0x180072001  jns     short loc_180072020
0x180072003  mov     rcx, [rbp+18h]; this
0x180072007  mov     r9d, eax; char *
0x18007200a  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x180072011  mov     edx, 63h ; 'c'; void *
0x180072016  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007201b  jmp     loc_180072165
0x180072020  mov     rbx, [rbp+var_28]
0x180072024  test    rbx, rbx
0x180072027  jz      loc_180072163
0x18007202d  cmp     dword ptr [rbx], 0
0x180072030  jz      loc_180072163
0x180072036  xorps   xmm0, xmm0
0x180072039  movdqu  xmmword ptr [rbp+Sid], xmm0
0x18007203e  mov     [rbp+var_10], 0
0x180072046  lea     rdx, [rbp+Sid]
0x18007204a  call    NgcUtils__GetUserSidFromToken
0x18007204f  mov     edi, eax
0x180072051  test    eax, eax
0x180072053  jns     short loc_18007207E
0x180072055  mov     rcx, [rbp+18h]; this
0x180072059  mov     r9d, eax; char *
0x18007205c  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x180072063  mov     edx, 6Bh ; 'k'; void *
0x180072068  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007206d  nop
0x18007206e  lea     rcx, [rbp+Sid]
0x180072072  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x180072077  mov     ebx, edi
0x180072079  jmp     loc_180072165
0x18007207e  mov     [rbp+StringSid], 0
0x180072086  lea     rdx, [rbp+StringSid]; StringSid
0x18007208a  mov     rcx, [rbp+Sid]; Sid
0x18007208e  call    cs:__imp_ConvertSidToStringSidW
0x180072094  test    eax, eax
0x180072096  jnz     short loc_1800720C5
0x180072098  mov     rcx, [rbp+18h]; this
0x18007209c  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x1800720a3  lea     edx, [rax+6Eh]; void *
0x1800720a6  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800720ab  mov     ebx, eax
0x1800720ad  lea     rcx, [rbp+StringSid]
0x1800720b1  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800720b6  nop
0x1800720b7  lea     rcx, [rbp+Sid]
0x1800720bb  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x1800720c0  jmp     loc_180072165
0x1800720c5  mov     [rbp+arg_18], 2
0x1800720cc  mov     [rbp+arg_10], 0
0x1800720d3  mov     [rbp+arg_8], 0
0x1800720da  or      cs:dword_1800C91F0, 20h
0x1800720e1  lea     rax, [rbp+arg_8]
0x1800720e5  mov     [rsp+60h+var_38], rax
0x1800720ea  lea     rax, dword_1800C91F0
0x1800720f1  mov     qword ptr [rsp+60h+var_40], rax; int
0x1800720f6  lea     r9, [rbp+arg_10]
0x1800720fa  lea     r8, [rbp+arg_18]
0x1800720fe  mov     rdx, [rbx+20h]
0x180072102  mov     rcx, [rbp+StringSid]
0x180072106  call    cs:__imp_NgcQueryEnabled
0x18007210c  mov     ebx, eax
0x18007210e  test    eax, eax
0x180072110  jns     short loc_18007212C
0x180072112  mov     rcx, [rbp+18h]; this
0x180072116  mov     r9d, eax; char *
0x180072119  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x180072120  mov     edx, 7Ah ; 'z'; void *
0x180072125  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007212a  jmp     short loc_1800720AD
0x18007212c  lea     rcx, [rbp+StringSid]
0x180072130  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180072135  nop
0x180072136  lea     rcx, [rbp+Sid]
0x18007213a  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x18007213f  nop
0x180072140  lea     rcx, [rbp+var_28]
0x180072144  call    ??1?$unique_storage@U?$resource_policy@PEAU_DSREG_JOIN_INFO@@P6AXPEAU1@@Z$1?DsrFreeJoinInfo@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_DSREG_JOIN_INFO *,void (*)(_DSREG_JOIN_INFO *),&DsrFreeJoinInfo(_DSREG_JOIN_INFO *),wistd::integral_constant<unsigned __int64,0>,_DSREG_JOIN_INFO *,_DSREG_JOIN_INFO *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_DSREG_JOIN_INFO *,void (*)(_DSREG_JOIN_INFO *),&DsrFreeJoinInfo(_DSREG_JOIN_INFO *),wistd::integral_constant<unsigned __int64,0>,_DSREG_JOIN_INFO *,_DSREG_JOIN_INFO *,0,std::nullptr_t>>(void)
0x180072149  mov     eax, cs:dword_1800C91F0
0x18007214f  mov     [rsi], eax
0x180072151  xor     eax, eax
0x180072153  mov     rbx, [rsp+60h+arg_0]
0x18007215b  add     rsp, 60h
0x18007215f  pop     rdi
0x180072160  pop     rsi
0x180072161  pop     rbp
0x180072162  retn
0x180072163  xor     ebx, ebx
0x180072165  lea     rcx, [rbp+var_28]
0x180072169  call    ??1?$unique_storage@U?$resource_policy@PEAU_DSREG_JOIN_INFO@@P6AXPEAU1@@Z$1?DsrFreeJoinInfo@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_DSREG_JOIN_INFO *,void (*)(_DSREG_JOIN_INFO *),&DsrFreeJoinInfo(_DSREG_JOIN_INFO *),wistd::integral_constant<unsigned __int64,0>,_DSREG_JOIN_INFO *,_DSREG_JOIN_INFO *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_DSREG_JOIN_INFO *,void (*)(_DSREG_JOIN_INFO *),&DsrFreeJoinInfo(_DSREG_JOIN_INFO *),wistd::integral_constant<unsigned __int64,0>,_DSREG_JOIN_INFO *,_DSREG_JOIN_INFO *,0,std::nullptr_t>>(void)
0x18007216e  mov     eax, ebx
0x180072170  jmp     short loc_180072153
```
