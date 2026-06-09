# CConnectedUserStore::FindConnectedUserBySidEx(uchar *,ulong,IConnectedUser * *)

- ea: `0x180016400`
- end: `0x180016711`
- name: `?FindConnectedUserBySidEx@CConnectedUserStore@@UEAAJPEAEKPEAPEAUIConnectedUser@@@Z`
- size: `785`
- prototype: `__int64 __fastcall(CConnectedUserStore *this, unsigned __int8 *, DWORD, struct IConnectedUser **)`
- caller_count: `0`
- callee_count: `13`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callees

- `0x180003560`
- `0x180003a70`
- `0x18000acb0`
- `0x18000e39c`
- `0x18000e530`
- `0x18000edb4`
- `0x180014430`
- `0x1800144b4`
- `0x18001596c`
- `0x180016400`
- `0x180018ac4`
- `0x180019750`
- `0x18001b010`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800164c7`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800164c7`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x1800164b6`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x1800164b6`
- `api-ms-win-security-base-l1-1-0!EqualDomainSid` at `0x18001654c`
- `api-ms-win-security-base-l1-1-0!EqualDomainSid` at `0x18001654c`
- `api-ms-win-security-lsalookup-l1-1-2!LsaLookupUserAccountType` at `0x18001656b`
- `api-ms-win-security-lsalookup-l1-1-2!LsaLookupUserAccountType` at `0x18001656b`

## string_xrefs

- `0x18001644a`: `CConnectedUserStore::FindConnectedUserBySidEx`

## pseudocode

```c
__int64 __fastcall CConnectedUserStore::FindConnectedUserBySidEx(
        CConnectedUserStore *this,
        unsigned __int8 *a2,
        DWORD a3,
        struct IConnectedUser **a4)
{
  int v8; // ecx
  __int64 v9; // r8
  __int64 v10; // r9
  CIdentityProfileHandler *v11; // rcx
  __int64 v12; // rdx
  int v13; // ebx
  __int64 v14; // rdx
  CConnectedUser *v15; // rbx
  unsigned int v16; // ebx
  __int64 v17; // rdx
  __int64 v18; // r8
  int MachineSid; // [rsp+30h] [rbp-29h] BYREF
  BOOL pfEqual; // [rsp+34h] [rbp-25h] BYREF
  int v22; // [rsp+38h] [rbp-21h] BYREF
  PSID pSid2; // [rsp+40h] [rbp-19h] BYREF
  CConnectedUser *v24; // [rsp+48h] [rbp-11h] BYREF
  _BYTE v25[16]; // [rsp+50h] [rbp-9h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v26; // [rsp+60h] [rbp+7h] BYREF
  char v27; // [rsp+70h] [rbp+17h]

  pSid2 = 0;
  MachineSid = 0;
  v24 = 0;
  CLogBlock::CLogBlock((CLogBlock *)v25, "CConnectedUserStore::FindConnectedUserBySidEx", &MachineSid);
  if ( (Microsoft_Windows_Security_IdentityStoreEnableBits & 1) != 0 )
    McGenEventWrite_EventWriteTransfer(v8, (int)&FindUserBySidStart, v9, v10, &v26);
  if ( a2 )
  {
    if ( IsValidSid(a2) && GetLengthSid(a2) <= a3 )
    {
      *(_QWORD *)&v26.Size = 0;
      v26.Ptr = (ULONGLONG)&pSid2;
      v27 = 1;
      MachineSid = GetMachineSid((void **)&v26.Size);
      wil::details::out_param_ptr_t<void * *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>::~out_param_ptr_t<void * *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>(&v26);
      v10 = (unsigned int)MachineSid;
      if ( MachineSid >= 0 )
      {
        v22 = 0;
        pfEqual = 0;
        if ( !EqualDomainSid(a2, pSid2, &pfEqual) || !pfEqual )
        {
          MachineSid = -805305819;
          goto LABEL_36;
        }
        v13 = LsaLookupUserAccountType(a2, &v22);
        if ( v13 >= 0 )
        {
          if ( v22 != 5 )
          {
            MachineSid = (*(__int64 (__fastcall **)(CConnectedUserStore *, unsigned __int8 *, _QWORD, struct IConnectedUser **))(*(_QWORD *)this + 56LL))(
                           this,
                           a2,
                           a3,
                           a4);
            goto LABEL_36;
          }
          MachineSid = ATL::CComObject<CConnectedUser>::CreateInstance(&v24);
          v10 = (unsigned int)MachineSid;
          if ( MachineSid >= 0 )
          {
            v15 = v24;
            (*(void (__fastcall **)(CConnectedUser *, __int64, __int64, _QWORD))(*(_QWORD *)v24 + 8LL))(
              v24,
              v14,
              v9,
              (unsigned int)MachineSid);
            MachineSid = CConnectedUser::InitializeConnectedAADUser(v15, a2);
            if ( MachineSid >= 0 )
            {
              *a4 = v15;
              goto LABEL_36;
            }
            (*(void (__fastcall **)(CConnectedUser *))(*(_QWORD *)v15 + 16LL))(v15);
            v11 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (CIdentityProfileHandler *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
            {
              v10 = (unsigned int)MachineSid;
              v12 = 83;
              goto LABEL_35;
            }
          }
          else
          {
            v11 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (CIdentityProfileHandler *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
            {
              v12 = 82;
              goto LABEL_35;
            }
          }
        }
        else
        {
          LODWORD(v11) = (_DWORD)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (CIdentityProfileHandler *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
          {
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              81,
              WPP_b72d4e051fd83533ab7d0ff6c3008341_Traceguids,
              (unsigned int)v13);
          }
          MachineSid = v13 | 0x10000000;
        }
      }
      else
      {
        v11 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (CIdentityProfileHandler *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        {
          v12 = 80;
          goto LABEL_35;
        }
      }
    }
    else
    {
      MachineSid = -2147024809;
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CIdentityProfileHandler *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      {
        v12 = 79;
        v10 = 2147942487LL;
        goto LABEL_35;
      }
    }
  }
  else
  {
    MachineSid = -2147467261;
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CIdentityProfileHandler *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      v12 = 78;
      v10 = 2147500035LL;
LABEL_35:
      WPP_SF_d(*((_QWORD *)v11 + 2), v12, WPP_b72d4e051fd83533ab7d0ff6c3008341_Traceguids, v10);
    }
  }
LABEL_36:
  if ( (Microsoft_Windows_Security_IdentityStoreEnableBits & 1) != 0 )
    McGenEventWrite_EventWriteTransfer((int)v11, (int)&FindUserBySidStop, v9, v10, &v26);
  v16 = MapErrorCodes(MachineSid);
  CLogBlock::~CLogBlock((CLogBlock *)v25, v17, v18);
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&pSid2);
  return v16;
}

```

## disassembly

```asm
0x180016400  push    rbp
0x180016402  push    rbx
0x180016403  push    rsi
0x180016404  push    rdi
0x180016405  push    r14
0x180016407  push    r15
0x180016409  lea     rbp, [rsp-2Fh]
0x18001640e  sub     rsp, 88h
0x180016415  mov     rax, cs:__security_cookie
0x18001641c  xor     rax, rsp
0x18001641f  mov     [rbp+57h+var_38], rax
0x180016423  mov     r14d, r8d
0x180016426  mov     [rbp+57h+pSid2], 0
0x18001642e  mov     rdi, rdx
0x180016431  mov     [rbp+57h+var_80], 0
0x180016438  mov     r15, rcx
0x18001643b  mov     [rbp+57h+var_68], 0
0x180016443  lea     r8, [rbp+57h+var_80]; int *
0x180016447  mov     rsi, r9
0x18001644a  lea     rdx, aCconnecteduser_24; "CConnectedUserStore::FindConnectedUserB"...
0x180016451  lea     rcx, [rbp+57h+var_60]; this
0x180016455  call    ??0CLogBlock@@QEAA@PEBDPEAJ@Z; CLogBlock::CLogBlock(char const *,long *)
0x18001645a  test    cs:Microsoft_Windows_Security_IdentityStoreEnableBits, 1
0x180016461  jz      short loc_180016478
0x180016463  lea     rax, [rbp+57h+var_50]
0x180016467  lea     rdx, FindUserBySidStart; int
0x18001646e  mov     [rsp+0B0h+var_90], rax; PEVENT_DATA_DESCRIPTOR
0x180016473  call    McGenEventWrite_EventWriteTransfer
0x180016478  test    rdi, rdi
0x18001647b  jnz     short loc_1800164B3
0x18001647d  mov     [rbp+57h+var_80], 80004003h
0x180016484  mov     rcx, cs:WPP_GLOBAL_Control
0x18001648b  lea     rax, WPP_GLOBAL_Control
0x180016492  cmp     rcx, rax
0x180016495  jz      loc_1800166B9
0x18001649b  test    byte ptr [rcx+1Ch], 4
0x18001649f  jz      loc_1800166B9
0x1800164a5  lea     edx, [rdi+4Eh]
0x1800164a8  mov     r9d, 80004003h
0x1800164ae  jmp     loc_1800166A9
0x1800164b3  mov     rcx, rdi; pSid
0x1800164b6  call    cs:__imp_IsValidSid
0x1800164bc  test    eax, eax
0x1800164be  jz      loc_18001667E
0x1800164c4  mov     rcx, rdi; pSid
0x1800164c7  call    cs:__imp_GetLengthSid
0x1800164cd  cmp     eax, r14d
0x1800164d0  ja      loc_18001667E
0x1800164d6  lea     rax, [rbp+57h+pSid2]
0x1800164da  mov     qword ptr [rbp+57h+var_50.Size], 0
0x1800164e2  lea     rcx, [rbp+57h+var_50.Size]; void **
0x1800164e6  mov     [rbp+57h+var_50.Ptr], rax
0x1800164ea  mov     [rbp+57h+var_40], 1
0x1800164ee  call    ?GetMachineSid@@YAJPEAPEAX@Z; GetMachineSid(void * *)
0x1800164f3  lea     rcx, [rbp+57h+var_50]
0x1800164f7  mov     [rbp+57h+var_80], eax
0x1800164fa  call    ??1?$out_param_ptr_t@PEAPEAXV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_ptr_t<void * *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>::~out_param_ptr_t<void * *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>(void)
0x1800164ff  mov     r9d, [rbp+57h+var_80]
0x180016503  test    r9d, r9d
0x180016506  jns     short loc_180016533
0x180016508  mov     rcx, cs:WPP_GLOBAL_Control
0x18001650f  lea     rax, WPP_GLOBAL_Control
0x180016516  cmp     rcx, rax
0x180016519  jz      loc_1800166B9
0x18001651f  test    byte ptr [rcx+1Ch], 4
0x180016523  jz      loc_1800166B9
0x180016529  mov     edx, 50h ; 'P'
0x18001652e  jmp     loc_1800166A9
0x180016533  mov     rdx, [rbp+57h+pSid2]; pSid2
0x180016537  lea     r8, [rbp+57h+pfEqual]; pfEqual
0x18001653b  mov     rcx, rdi; pSid1
0x18001653e  mov     [rbp+57h+var_78], 0
0x180016545  mov     [rbp+57h+pfEqual], 0
0x18001654c  call    cs:__imp_EqualDomainSid
0x180016552  test    eax, eax
0x180016554  jz      loc_180016675
0x18001655a  cmp     [rbp+57h+pfEqual], 0
0x18001655e  jz      loc_180016675
0x180016564  lea     rdx, [rbp+57h+var_78]
0x180016568  mov     rcx, rdi
0x18001656b  call    cs:__imp_LsaLookupUserAccountType
0x180016571  mov     ebx, eax
0x180016573  test    eax, eax
0x180016575  jns     short loc_1800165B4
0x180016577  mov     rcx, cs:WPP_GLOBAL_Control
0x18001657e  lea     rax, WPP_GLOBAL_Control
0x180016585  cmp     rcx, rax
0x180016588  jz      short loc_1800165A8
0x18001658a  test    byte ptr [rcx+1Ch], 4
0x18001658e  jz      short loc_1800165A8
0x180016590  mov     rcx, [rcx+10h]
0x180016594  lea     r8, WPP_b72d4e051fd83533ab7d0ff6c3008341_Traceguids
0x18001659b  mov     edx, 51h ; 'Q'
0x1800165a0  mov     r9d, ebx
0x1800165a3  call    WPP_SF_d
0x1800165a8  bts     ebx, 1Ch
0x1800165ac  mov     [rbp+57h+var_80], ebx
0x1800165af  jmp     loc_1800166B9
0x1800165b4  cmp     [rbp+57h+var_78], 5
0x1800165b8  jz      short loc_1800165DA
0x1800165ba  mov     rax, [r15]
0x1800165bd  mov     r9, rsi
0x1800165c0  mov     r8d, r14d
0x1800165c3  mov     rdx, rdi
0x1800165c6  mov     rcx, r15
0x1800165c9  mov     rax, [rax+38h]
0x1800165cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800165d2  mov     [rbp+57h+var_80], eax
0x1800165d5  jmp     loc_1800166B9
0x1800165da  lea     rcx, [rbp+57h+var_68]
0x1800165de  call    ?CreateInstance@?$CComObject@VCConnectedUser@@@ATL@@SAJPEAPEAV12@@Z; ATL::CComObject<CConnectedUser>::CreateInstance(ATL::CComObject<CConnectedUser> * *)
0x1800165e3  mov     [rbp+57h+var_80], eax
0x1800165e6  mov     r9d, eax
0x1800165e9  test    eax, eax
0x1800165eb  jns     short loc_180016618
0x1800165ed  mov     rcx, cs:WPP_GLOBAL_Control
0x1800165f4  lea     rax, WPP_GLOBAL_Control
0x1800165fb  cmp     rcx, rax
0x1800165fe  jz      loc_1800166B9
0x180016604  test    byte ptr [rcx+1Ch], 4
0x180016608  jz      loc_1800166B9
0x18001660e  mov     edx, 52h ; 'R'
0x180016613  jmp     loc_1800166A9
0x180016618  mov     rbx, [rbp+57h+var_68]
0x18001661c  mov     rcx, rbx
0x18001661f  mov     rax, [rbx]
0x180016622  mov     rax, [rax+8]
0x180016626  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001662b  mov     rdx, rdi; void *
0x18001662e  mov     rcx, rbx; this
0x180016631  call    ?InitializeConnectedAADUser@CConnectedUser@@QEAAJPEAX@Z; CConnectedUser::InitializeConnectedAADUser(void *)
0x180016636  mov     [rbp+57h+var_80], eax
0x180016639  test    eax, eax
0x18001663b  jns     short loc_180016670
0x18001663d  mov     rax, [rbx]
0x180016640  mov     rcx, rbx
0x180016643  mov     rax, [rax+10h]
0x180016647  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001664c  mov     rcx, cs:WPP_GLOBAL_Control
0x180016653  lea     rax, WPP_GLOBAL_Control
0x18001665a  cmp     rcx, rax
0x18001665d  jz      short loc_1800166B9
0x18001665f  test    byte ptr [rcx+1Ch], 4
0x180016663  jz      short loc_1800166B9
0x180016665  mov     r9d, [rbp+57h+var_80]
0x180016669  mov     edx, 53h ; 'S'
0x18001666e  jmp     short loc_1800166A9
0x180016670  mov     [rsi], rbx
0x180016673  jmp     short loc_1800166B9
0x180016675  mov     [rbp+57h+var_80], 0D0000225h
0x18001667c  jmp     short loc_1800166B9
0x18001667e  mov     [rbp+57h+var_80], 80070057h
0x180016685  mov     rcx, cs:WPP_GLOBAL_Control
0x18001668c  lea     rax, WPP_GLOBAL_Control
0x180016693  cmp     rcx, rax
0x180016696  jz      short loc_1800166B9
0x180016698  test    byte ptr [rcx+1Ch], 4
0x18001669c  jz      short loc_1800166B9
0x18001669e  mov     edx, 4Fh ; 'O'
0x1800166a3  mov     r9d, 80070057h
0x1800166a9  mov     rcx, [rcx+10h]
0x1800166ad  lea     r8, WPP_b72d4e051fd83533ab7d0ff6c3008341_Traceguids
0x1800166b4  call    WPP_SF_d
0x1800166b9  test    cs:Microsoft_Windows_Security_IdentityStoreEnableBits, 1
0x1800166c0  jz      short loc_1800166D7
0x1800166c2  lea     rax, [rbp+57h+var_50]
0x1800166c6  lea     rdx, FindUserBySidStop; int
0x1800166cd  mov     [rsp+0B0h+var_90], rax; PEVENT_DATA_DESCRIPTOR
0x1800166d2  call    McGenEventWrite_EventWriteTransfer
0x1800166d7  mov     ecx, [rbp+57h+var_80]; int
0x1800166da  call    ?MapErrorCodes@@YAJJ@Z; MapErrorCodes(long)
0x1800166df  lea     rcx, [rbp+57h+var_60]; this
0x1800166e3  mov     ebx, eax
0x1800166e5  call    ??1CLogBlock@@QEAA@XZ; CLogBlock::~CLogBlock(void)
0x1800166ea  lea     rcx, [rbp+57h+pSid2]
0x1800166ee  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x1800166f3  mov     eax, ebx
0x1800166f5  mov     rcx, [rbp+57h+var_38]
0x1800166f9  xor     rcx, rsp; StackCookie
0x1800166fc  call    __security_check_cookie
0x180016701  add     rsp, 88h
0x180016708  pop     r15
0x18001670a  pop     r14
0x18001670c  pop     rdi
0x18001670d  pop     rsi
0x18001670e  pop     rbx
0x18001670f  pop     rbp
0x180016710  retn
```
