# CConnectedUser::GetConnectedAADUserInfo(IPropertyStore *)

- ea: `0x1800183dc`
- end: `0x180018abc`
- name: `?GetConnectedAADUserInfo@CConnectedUser@@QEAAJPEAUIPropertyStore@@@Z`
- size: `1760`
- prototype: `__int64 __fastcall(CConnectedUser *__hidden this, struct IPropertyStore *)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180008910`

## callees

- `0x18000ad00`
- `0x18000caf0`
- `0x18000e530`
- `0x18000f034`
- `0x18001448c`
- `0x1800144b4`
- `0x180015a04`
- `0x1800183dc`
- `0x180019722`
- `0x180019750`
- `0x18001b010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180018a79`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180018a79`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180018558`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180018633`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18001870e`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800187e9`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800188e2`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800189d7`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180018558`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180018633`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18001870e`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800187e9`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800188e2`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800189d7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001880c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018905`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001880c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018905`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18001845f`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18001845f`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180018802`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800188fb`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180018802`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800188fb`
- `SspiCli!LsaFreeReturnBuffer` at `0x180018a69`
- `SspiCli!LsaFreeReturnBuffer` at `0x180018a69`
- `PROPSYS!InitPropVariantFromCLSID` at `0x1800184c0`
- `PROPSYS!InitPropVariantFromCLSID` at `0x1800184c0`

## pseudocode

```c
__int64 __fastcall CConnectedUser::GetConnectedAADUserInfo(CConnectedUser *this, struct IPropertyStore *a2)
{
  unsigned int v4; // ecx
  int v5; // ebx
  char *v6; // rsi
  int inited; // ebx
  CIdentityProfileHandler *v8; // rcx
  __int64 v9; // rdx
  __int64 v10; // r9
  signed int v11; // eax
  signed int LastError; // eax
  __int64 v13; // rax
  _BYTE *v14; // rcx
  unsigned int v16; // [rsp+20h] [rbp-99h] BYREF
  LPVOID pv; // [rsp+28h] [rbp-91h] BYREF
  struct tagPROPVARIANT ppropvar; // [rsp+30h] [rbp-89h] BYREF
  unsigned int v19; // [rsp+48h] [rbp-71h] BYREF
  LPWSTR Src; // [rsp+50h] [rbp-69h] BYREF
  LPWSTR StringSid; // [rsp+58h] [rbp-61h] BYREF
  PVOID Buffer; // [rsp+60h] [rbp-59h] BYREF
  int v23; // [rsp+70h] [rbp-49h] BYREF
  __int128 v24; // [rsp+74h] [rbp-45h]
  _BYTE pDestinationSid[76]; // [rsp+84h] [rbp-35h] BYREF

  memset_0(&v23, 0, 0x58u);
  memset(&ppropvar, 0, sizeof(ppropvar));
  pv = 0;
  v16 = 0;
  StringSid = 0;
  Src = 0;
  v23 = 15;
  v24 = xmmword_18001E7E0;
  v19 = 0;
  Buffer = 0;
  CopySid(0x44u, pDestinationSid, *((PSID *)this + 12));
  v5 = CallCloudAPPackage(v4, &v23, &v19, &Buffer);
  v6 = (char *)Buffer;
  if ( v5 >= 0 && Buffer )
  {
    if ( *((_WORD *)Buffer + 4) && *((_WORD *)Buffer + 20) && *((_WORD *)Buffer + 12) && *((_WORD *)Buffer + 28) )
    {
      inited = InitPropVariantFromCLSID((const IID *const)((char *)this + 68), (PROPVARIANT *)&ppropvar);
      if ( inited >= 0 )
      {
        inited = ((__int64 (__fastcall *)(struct IPropertyStore *, const PROPERTYKEY *, struct tagPROPVARIANT *))a2->lpVtbl->SetValue)(
                   a2,
                   &PKEY_Identity_ProviderID,
                   &ppropvar);
        if ( inited >= 0 )
        {
          PropVariantClear((PROPVARIANT *)&ppropvar);
          inited = UnicodeStringToCString((struct _UNICODE_STRING *)(v6 + 8), (unsigned __int16 **)&pv, &v16);
          if ( inited >= 0 )
          {
            inited = InitPropVariantFromString((const unsigned __int16 *)pv, &ppropvar);
            if ( inited >= 0 )
            {
              inited = ((__int64 (__fastcall *)(struct IPropertyStore *, const PROPERTYKEY *, struct tagPROPVARIANT *))a2->lpVtbl->SetValue)(
                         a2,
                         &PKEY_IdentityProvider_Name,
                         &ppropvar);
              if ( inited >= 0 )
              {
                PropVariantClear((PROPVARIANT *)&ppropvar);
                inited = UnicodeStringToCString((struct _UNICODE_STRING *)(v6 + 24), (unsigned __int16 **)&pv, &v16);
                if ( inited >= 0 )
                {
                  inited = InitPropVariantFromString((const unsigned __int16 *)pv, &ppropvar);
                  if ( inited >= 0 )
                  {
                    inited = ((__int64 (__fastcall *)(struct IPropertyStore *, const PROPERTYKEY *, struct tagPROPVARIANT *))a2->lpVtbl->SetValue)(
                               a2,
                               &PKEY_Identity_DisplayName,
                               &ppropvar);
                    if ( inited >= 0 )
                    {
                      PropVariantClear((PROPVARIANT *)&ppropvar);
                      inited = UnicodeStringToCString(
                                 (struct _UNICODE_STRING *)(v6 + 40),
                                 (unsigned __int16 **)&pv,
                                 &v16);
                      if ( inited >= 0 )
                      {
                        inited = InitPropVariantFromString((const unsigned __int16 *)pv, &ppropvar);
                        if ( inited >= 0 )
                        {
                          inited = ((__int64 (__fastcall *)(struct IPropertyStore *, const PROPERTYKEY *, struct tagPROPVARIANT *))a2->lpVtbl->SetValue)(
                                     a2,
                                     &PKEY_Identity_UserName,
                                     &ppropvar);
                          if ( inited >= 0 )
                          {
                            PropVariantClear((PROPVARIANT *)&ppropvar);
                            wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
                              &StringSid,
                              0);
                            if ( ConvertSidToStringSidW(*((PSID *)this + 12), &StringSid) )
                            {
                              inited = InitPropVariantFromString(StringSid, &ppropvar);
                              if ( inited >= 0 )
                              {
                                inited = ((__int64 (__fastcall *)(struct IPropertyStore *, const PROPERTYKEY *, struct tagPROPVARIANT *))a2->lpVtbl->SetValue)(
                                           a2,
                                           &PKEY_Identity_PrimarySid,
                                           &ppropvar);
                                if ( inited >= 0 )
                                {
                                  PropVariantClear((PROPVARIANT *)&ppropvar);
                                  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
                                    &Src,
                                    0);
                                  if ( ConvertSidToStringSidW(v6 + 76, &Src) )
                                  {
                                    inited = InitPropVariantFromString(Src, &ppropvar);
                                    if ( inited >= 0 )
                                    {
                                      inited = ((__int64 (__fastcall *)(struct IPropertyStore *, const PROPERTYKEY *, struct tagPROPVARIANT *))a2->lpVtbl->SetValue)(
                                                 a2,
                                                 &PKEY_Identity_InternetSid,
                                                 &ppropvar);
                                      if ( inited >= 0 )
                                      {
                                        PropVariantClear((PROPVARIANT *)&ppropvar);
                                        goto LABEL_91;
                                      }
                                      v8 = WPP_GLOBAL_Control;
                                      if ( WPP_GLOBAL_Control != (CIdentityProfileHandler *)&WPP_GLOBAL_Control
                                        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
                                      {
                                        v9 = 65;
                                        goto LABEL_11;
                                      }
                                    }
                                    else
                                    {
                                      v8 = WPP_GLOBAL_Control;
                                      if ( WPP_GLOBAL_Control != (CIdentityProfileHandler *)&WPP_GLOBAL_Control
                                        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
                                      {
                                        v9 = 64;
                                        goto LABEL_11;
                                      }
                                    }
                                  }
                                  else
                                  {
                                    LastError = GetLastError();
                                    v10 = (unsigned int)LastError;
                                    if ( LastError > 0 )
                                      inited = (unsigned __int16)LastError | 0x80070000;
                                    else
                                      inited = LastError;
                                    v8 = WPP_GLOBAL_Control;
                                    if ( WPP_GLOBAL_Control != (CIdentityProfileHandler *)&WPP_GLOBAL_Control
                                      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
                                    {
                                      v9 = 63;
                                      goto LABEL_12;
                                    }
                                  }
                                }
                                else
                                {
                                  v8 = WPP_GLOBAL_Control;
                                  if ( WPP_GLOBAL_Control != (CIdentityProfileHandler *)&WPP_GLOBAL_Control
                                    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
                                  {
                                    v9 = 62;
                                    goto LABEL_11;
                                  }
                                }
                              }
                              else
                              {
                                v8 = WPP_GLOBAL_Control;
                                if ( WPP_GLOBAL_Control != (CIdentityProfileHandler *)&WPP_GLOBAL_Control
                                  && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
                                {
                                  v9 = 61;
                                  goto LABEL_11;
                                }
                              }
                            }
                            else
                            {
                              v11 = GetLastError();
                              v10 = (unsigned int)v11;
                              if ( v11 > 0 )
                                inited = (unsigned __int16)v11 | 0x80070000;
                              else
                                inited = v11;
                              v8 = WPP_GLOBAL_Control;
                              if ( WPP_GLOBAL_Control != (CIdentityProfileHandler *)&WPP_GLOBAL_Control
                                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
                              {
                                v9 = 60;
                                goto LABEL_12;
                              }
                            }
                          }
                          else
                          {
                            v8 = WPP_GLOBAL_Control;
                            if ( WPP_GLOBAL_Control != (CIdentityProfileHandler *)&WPP_GLOBAL_Control
                              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
                            {
                              v9 = 59;
                              goto LABEL_11;
                            }
                          }
                        }
                        else
                        {
                          v8 = WPP_GLOBAL_Control;
                          if ( WPP_GLOBAL_Control != (CIdentityProfileHandler *)&WPP_GLOBAL_Control
                            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
                          {
                            v9 = 58;
                            goto LABEL_11;
                          }
                        }
                      }
                      else
                      {
                        v8 = WPP_GLOBAL_Control;
                        if ( WPP_GLOBAL_Control != (CIdentityProfileHandler *)&WPP_GLOBAL_Control
                          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
                        {
                          v9 = 57;
                          goto LABEL_11;
                        }
                      }
                    }
                    else
                    {
                      v8 = WPP_GLOBAL_Control;
                      if ( WPP_GLOBAL_Control != (CIdentityProfileHandler *)&WPP_GLOBAL_Control
                        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
                      {
                        v9 = 56;
                        goto LABEL_11;
                      }
                    }
                  }
                  else
                  {
                    v8 = WPP_GLOBAL_Control;
                    if ( WPP_GLOBAL_Control != (CIdentityProfileHandler *)&WPP_GLOBAL_Control
                      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
                    {
                      v9 = 55;
                      goto LABEL_11;
                    }
                  }
                }
                else
                {
                  v8 = WPP_GLOBAL_Control;
                  if ( WPP_GLOBAL_Control != (CIdentityProfileHandler *)&WPP_GLOBAL_Control
                    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
                  {
                    v9 = 54;
                    goto LABEL_11;
                  }
                }
              }
              else
              {
                v8 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control != (CIdentityProfileHandler *)&WPP_GLOBAL_Control
                  && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
                {
                  v9 = 53;
                  goto LABEL_11;
                }
              }
            }
            else
            {
              v8 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != (CIdentityProfileHandler *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
              {
                v9 = 52;
                goto LABEL_11;
              }
            }
          }
          else
          {
            v8 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (CIdentityProfileHandler *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
            {
              v9 = 51;
              goto LABEL_11;
            }
          }
        }
        else
        {
          v8 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (CIdentityProfileHandler *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
          {
            v9 = 50;
            goto LABEL_11;
          }
        }
      }
      else
      {
        v8 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (CIdentityProfileHandler *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        {
          v9 = 49;
LABEL_11:
          v10 = (unsigned int)inited;
LABEL_12:
          WPP_SF_d(*((_QWORD *)v8 + 2), v9, WPP_08388c1448a138cd62261a2bdb1dad4c_Traceguids, v10);
        }
      }
    }
    else
    {
      inited = 0;
      if ( WPP_GLOBAL_Control != (CIdentityProfileHandler *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 48, WPP_08388c1448a138cd62261a2bdb1dad4c_Traceguids);
      }
    }
  }
  else
  {
    if ( WPP_GLOBAL_Control != (CIdentityProfileHandler *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        47,
        WPP_08388c1448a138cd62261a2bdb1dad4c_Traceguids,
        (unsigned int)v5);
    }
    inited = v5 | 0x10000000;
  }
LABEL_91:
  v13 = v19;
  if ( v19 && v6 )
  {
    v14 = v6;
    do
    {
      *v14++ = 0;
      --v13;
    }
    while ( v13 );
    LsaFreeReturnBuffer(v6);
  }
  if ( pv )
    CoTaskMemFree(pv);
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>((void **)&Src);
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>((void **)&StringSid);
  return (unsigned int)inited;
}

```

## disassembly

```asm
0x1800183dc  mov     [rsp-8+arg_10], rbx
0x1800183e1  push    rbp
0x1800183e2  push    rsi
0x1800183e3  push    rdi
0x1800183e4  push    r12
0x1800183e6  push    r13
0x1800183e8  push    r14
0x1800183ea  push    r15
0x1800183ec  lea     rbp, [rsp-27h]
0x1800183f1  sub     rsp, 0E0h
0x1800183f8  mov     rax, cs:__security_cookie
0x1800183ff  xor     rax, rsp
0x180018402  mov     [rbp+57h+var_40], rax
0x180018406  mov     rdi, rdx
0x180018409  mov     r13, rcx
0x18001840c  xor     edx, edx; Val
0x18001840e  lea     r8d, [rdx+58h]; Size
0x180018412  lea     rcx, [rbp+57h+var_A0]; void *
0x180018416  call    memset_0
0x18001841b  xorps   xmm0, xmm0
0x18001841e  xor     eax, eax
0x180018420  movups  xmmword ptr [rsp+110h+ppropvar], xmm0
0x180018425  mov     [rbp+57h+var_D0], rax
0x180018429  mov     [rsp+110h+pv], rax
0x18001842e  mov     [rsp+110h+var_F0], eax
0x180018432  mov     [rbp+57h+StringSid], rax
0x180018436  mov     [rbp+57h+Src], rax
0x18001843a  mov     [rbp+57h+var_A0], 0Fh
0x180018441  movups  xmm0, cs:xmmword_18001E7E0
0x180018448  movdqu  [rbp+57h+var_9C], xmm0
0x18001844d  mov     [rbp+57h+var_C8], eax
0x180018450  mov     [rbp+57h+Buffer], rax
0x180018454  mov     r8, [r13+60h]; pSourceSid
0x180018458  lea     rdx, [rbp+57h+pDestinationSid]; pDestinationSid
0x18001845c  lea     ecx, [rax+44h]; nDestinationSidLength
0x18001845f  call    cs:__imp_CopySid
0x180018465  lea     r9, [rbp+57h+Buffer]; void **
0x180018469  lea     r8, [rbp+57h+var_C8]; unsigned int *
0x18001846d  lea     rdx, [rbp+57h+var_A0]; void *
0x180018471  call    ?CallCloudAPPackage@@YAJKPEAXPEAKPEAPEAX@Z; CallCloudAPPackage(ulong,void *,ulong *,void * *)
0x180018476  mov     ebx, eax
0x180018478  mov     rsi, [rbp+57h+Buffer]
0x18001847c  xor     eax, eax
0x18001847e  test    ebx, ebx
0x180018480  js      loc_180018A11
0x180018486  test    rsi, rsi
0x180018489  jz      loc_180018A11
0x18001848f  cmp     [rsi+8], ax
0x180018493  jz      loc_1800189DF
0x180018499  cmp     [rsi+28h], ax
0x18001849d  jz      loc_1800189DF
0x1800184a3  cmp     [rsi+18h], ax
0x1800184a7  jz      loc_1800189DF
0x1800184ad  cmp     [rsi+38h], ax
0x1800184b1  jz      loc_1800189DF
0x1800184b7  lea     rcx, [r13+44h]; clsid
0x1800184bb  lea     rdx, [rsp+110h+ppropvar]; ppropvar
0x1800184c0  call    cs:__imp_InitPropVariantFromCLSID
0x1800184c6  mov     ebx, eax
0x1800184c8  test    eax, eax
0x1800184ca  jns     short loc_18001850A
0x1800184cc  lea     rax, WPP_GLOBAL_Control
0x1800184d3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800184da  cmp     rcx, rax
0x1800184dd  jz      loc_180018A46
0x1800184e3  test    byte ptr [rcx+1Ch], 4
0x1800184e7  jz      loc_180018A46
0x1800184ed  mov     edx, 31h ; '1'
0x1800184f2  mov     r9d, ebx
0x1800184f5  lea     r8, WPP_08388c1448a138cd62261a2bdb1dad4c_Traceguids
0x1800184fc  mov     rcx, [rcx+10h]
0x180018500  call    WPP_SF_d
0x180018505  jmp     loc_180018A46
0x18001850a  mov     rax, [rdi]
0x18001850d  lea     r8, [rsp+110h+ppropvar]
0x180018512  lea     rdx, PKEY_Identity_ProviderID
0x180018519  mov     rcx, rdi
0x18001851c  mov     rax, [rax+30h]
0x180018520  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018525  mov     ebx, eax
0x180018527  test    eax, eax
0x180018529  jns     short loc_180018553
0x18001852b  lea     rax, WPP_GLOBAL_Control
0x180018532  mov     rcx, cs:WPP_GLOBAL_Control
0x180018539  cmp     rcx, rax
0x18001853c  jz      loc_180018A46
0x180018542  test    byte ptr [rcx+1Ch], 4
0x180018546  jz      loc_180018A46
0x18001854c  mov     edx, 32h ; '2'
0x180018551  jmp     short loc_1800184F2
0x180018553  lea     rcx, [rsp+110h+ppropvar]; pvar
0x180018558  call    cs:__imp_PropVariantClear
0x18001855e  lea     r8, [rsp+110h+var_F0]; unsigned int *
0x180018563  lea     rdx, [rsp+110h+pv]; unsigned __int16 **
0x180018568  lea     rcx, [rsi+8]; struct _UNICODE_STRING *
0x18001856c  call    ?UnicodeStringToCString@@YAJPEAU_UNICODE_STRING@@PEAPEAGPEAK@Z; UnicodeStringToCString(_UNICODE_STRING *,ushort * *,ulong *)
0x180018571  mov     ebx, eax
0x180018573  test    eax, eax
0x180018575  jns     short loc_1800185A2
0x180018577  lea     rax, WPP_GLOBAL_Control
0x18001857e  mov     rcx, cs:WPP_GLOBAL_Control
0x180018585  cmp     rcx, rax
0x180018588  jz      loc_180018A46
0x18001858e  test    byte ptr [rcx+1Ch], 4
0x180018592  jz      loc_180018A46
0x180018598  mov     edx, 33h ; '3'
0x18001859d  jmp     loc_1800184F2
0x1800185a2  lea     rdx, [rsp+110h+ppropvar]; struct tagPROPVARIANT *
0x1800185a7  mov     rcx, [rsp+110h+pv]; Src
0x1800185ac  call    ?InitPropVariantFromString@@YAJPEBGPEAUtagPROPVARIANT@@@Z; InitPropVariantFromString(ushort const *,tagPROPVARIANT *)
0x1800185b1  mov     ebx, eax
0x1800185b3  test    eax, eax
0x1800185b5  jns     short loc_1800185E2
0x1800185b7  lea     rax, WPP_GLOBAL_Control
0x1800185be  mov     rcx, cs:WPP_GLOBAL_Control
0x1800185c5  cmp     rcx, rax
0x1800185c8  jz      loc_180018A46
0x1800185ce  test    byte ptr [rcx+1Ch], 4
0x1800185d2  jz      loc_180018A46
0x1800185d8  mov     edx, 34h ; '4'
0x1800185dd  jmp     loc_1800184F2
0x1800185e2  mov     rax, [rdi]
0x1800185e5  lea     r8, [rsp+110h+ppropvar]
0x1800185ea  lea     rdx, PKEY_IdentityProvider_Name
0x1800185f1  mov     rcx, rdi
0x1800185f4  mov     rax, [rax+30h]
0x1800185f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800185fd  mov     ebx, eax
0x1800185ff  test    eax, eax
0x180018601  jns     short loc_18001862E
0x180018603  lea     rax, WPP_GLOBAL_Control
0x18001860a  mov     rcx, cs:WPP_GLOBAL_Control
0x180018611  cmp     rcx, rax
0x180018614  jz      loc_180018A46
0x18001861a  test    byte ptr [rcx+1Ch], 4
0x18001861e  jz      loc_180018A46
0x180018624  mov     edx, 35h ; '5'
0x180018629  jmp     loc_1800184F2
0x18001862e  lea     rcx, [rsp+110h+ppropvar]; pvar
0x180018633  call    cs:__imp_PropVariantClear
0x180018639  lea     r8, [rsp+110h+var_F0]; unsigned int *
0x18001863e  lea     rdx, [rsp+110h+pv]; unsigned __int16 **
0x180018643  lea     rcx, [rsi+18h]; struct _UNICODE_STRING *
0x180018647  call    ?UnicodeStringToCString@@YAJPEAU_UNICODE_STRING@@PEAPEAGPEAK@Z; UnicodeStringToCString(_UNICODE_STRING *,ushort * *,ulong *)
0x18001864c  mov     ebx, eax
0x18001864e  test    eax, eax
0x180018650  jns     short loc_18001867D
0x180018652  lea     rax, WPP_GLOBAL_Control
0x180018659  mov     rcx, cs:WPP_GLOBAL_Control
0x180018660  cmp     rcx, rax
0x180018663  jz      loc_180018A46
0x180018669  test    byte ptr [rcx+1Ch], 4
0x18001866d  jz      loc_180018A46
0x180018673  mov     edx, 36h ; '6'
0x180018678  jmp     loc_1800184F2
0x18001867d  lea     rdx, [rsp+110h+ppropvar]; struct tagPROPVARIANT *
0x180018682  mov     rcx, [rsp+110h+pv]; Src
0x180018687  call    ?InitPropVariantFromString@@YAJPEBGPEAUtagPROPVARIANT@@@Z; InitPropVariantFromString(ushort const *,tagPROPVARIANT *)
0x18001868c  mov     ebx, eax
0x18001868e  test    eax, eax
0x180018690  jns     short loc_1800186BD
0x180018692  lea     rax, WPP_GLOBAL_Control
0x180018699  mov     rcx, cs:WPP_GLOBAL_Control
0x1800186a0  cmp     rcx, rax
0x1800186a3  jz      loc_180018A46
0x1800186a9  test    byte ptr [rcx+1Ch], 4
0x1800186ad  jz      loc_180018A46
0x1800186b3  mov     edx, 37h ; '7'
0x1800186b8  jmp     loc_1800184F2
0x1800186bd  mov     rax, [rdi]
0x1800186c0  lea     r8, [rsp+110h+ppropvar]
0x1800186c5  lea     rdx, PKEY_Identity_DisplayName
0x1800186cc  mov     rcx, rdi
0x1800186cf  mov     rax, [rax+30h]
0x1800186d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800186d8  mov     ebx, eax
0x1800186da  test    eax, eax
0x1800186dc  jns     short loc_180018709
0x1800186de  lea     rax, WPP_GLOBAL_Control
0x1800186e5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800186ec  cmp     rcx, rax
0x1800186ef  jz      loc_180018A46
0x1800186f5  test    byte ptr [rcx+1Ch], 4
0x1800186f9  jz      loc_180018A46
0x1800186ff  mov     edx, 38h ; '8'
0x180018704  jmp     loc_1800184F2
0x180018709  lea     rcx, [rsp+110h+ppropvar]; pvar
0x18001870e  call    cs:__imp_PropVariantClear
0x180018714  lea     r8, [rsp+110h+var_F0]; unsigned int *
0x180018719  lea     rdx, [rsp+110h+pv]; unsigned __int16 **
0x18001871e  lea     rcx, [rsi+28h]; struct _UNICODE_STRING *
0x180018722  call    ?UnicodeStringToCString@@YAJPEAU_UNICODE_STRING@@PEAPEAGPEAK@Z; UnicodeStringToCString(_UNICODE_STRING *,ushort * *,ulong *)
0x180018727  mov     ebx, eax
0x180018729  test    eax, eax
0x18001872b  jns     short loc_180018758
0x18001872d  lea     rax, WPP_GLOBAL_Control
0x180018734  mov     rcx, cs:WPP_GLOBAL_Control
0x18001873b  cmp     rcx, rax
0x18001873e  jz      loc_180018A46
0x180018744  test    byte ptr [rcx+1Ch], 4
0x180018748  jz      loc_180018A46
0x18001874e  mov     edx, 39h ; '9'
0x180018753  jmp     loc_1800184F2
0x180018758  lea     rdx, [rsp+110h+ppropvar]; struct tagPROPVARIANT *
0x18001875d  mov     rcx, [rsp+110h+pv]; Src
0x180018762  call    ?InitPropVariantFromString@@YAJPEBGPEAUtagPROPVARIANT@@@Z; InitPropVariantFromString(ushort const *,tagPROPVARIANT *)
0x180018767  mov     ebx, eax
0x180018769  test    eax, eax
0x18001876b  jns     short loc_180018798
0x18001876d  lea     rax, WPP_GLOBAL_Control
0x180018774  mov     rcx, cs:WPP_GLOBAL_Control
0x18001877b  cmp     rcx, rax
0x18001877e  jz      loc_180018A46
0x180018784  test    byte ptr [rcx+1Ch], 4
0x180018788  jz      loc_180018A46
0x18001878e  mov     edx, 3Ah ; ':'
0x180018793  jmp     loc_1800184F2
0x180018798  mov     rax, [rdi]
0x18001879b  lea     r8, [rsp+110h+ppropvar]
0x1800187a0  lea     rdx, PKEY_Identity_UserName
0x1800187a7  mov     rcx, rdi
0x1800187aa  mov     rax, [rax+30h]
0x1800187ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800187b3  mov     ebx, eax
0x1800187b5  test    eax, eax
0x1800187b7  jns     short loc_1800187E4
0x1800187b9  lea     rax, WPP_GLOBAL_Control
0x1800187c0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800187c7  cmp     rcx, rax
0x1800187ca  jz      loc_180018A46
0x1800187d0  test    byte ptr [rcx+1Ch], 4
0x1800187d4  jz      loc_180018A46
0x1800187da  mov     edx, 3Bh ; ';'
0x1800187df  jmp     loc_1800184F2
0x1800187e4  lea     rcx, [rsp+110h+ppropvar]; pvar
0x1800187e9  call    cs:__imp_PropVariantClear
0x1800187ef  xor     edx, edx
0x1800187f1  lea     rcx, [rbp+57h+StringSid]
0x1800187f5  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x1800187fa  lea     rdx, [rbp+57h+StringSid]; StringSid
0x1800187fe  mov     rcx, [r13+60h]; Sid
0x180018802  call    cs:__imp_ConvertSidToStringSidW
0x180018808  test    eax, eax
0x18001880a  jnz     short loc_180018852
0x18001880c  call    cs:__imp_GetLastError
0x180018812  mov     r9d, eax
0x180018815  test    eax, eax
0x180018817  jg      short loc_18001881D
0x180018819  mov     ebx, eax
0x18001881b  jmp     short loc_180018827
0x18001881d  movzx   ebx, r9w
0x180018821  or      ebx, 80070000h
0x180018827  lea     rax, WPP_GLOBAL_Control
0x18001882e  mov     rcx, cs:WPP_GLOBAL_Control
0x180018835  cmp     rcx, rax
0x180018838  jz      loc_180018A46
0x18001883e  test    byte ptr [rcx+1Ch], 4
0x180018842  jz      loc_180018A46
0x180018848  mov     edx, 3Ch ; '<'
0x18001884d  jmp     loc_1800184F5
0x180018852  lea     rdx, [rsp+110h+ppropvar]; struct tagPROPVARIANT *
0x180018857  mov     rcx, [rbp+57h+StringSid]; Src
0x18001885b  call    ?InitPropVariantFromString@@YAJPEBGPEAUtagPROPVARIANT@@@Z; InitPropVariantFromString(ushort const *,tagPROPVARIANT *)
0x180018860  mov     ebx, eax
0x180018862  test    eax, eax
0x180018864  jns     short loc_180018891
0x180018866  lea     rax, WPP_GLOBAL_Control
0x18001886d  mov     rcx, cs:WPP_GLOBAL_Control
0x180018874  cmp     rcx, rax
0x180018877  jz      loc_180018A46
0x18001887d  test    byte ptr [rcx+1Ch], 4
0x180018881  jz      loc_180018A46
0x180018887  mov     edx, 3Dh ; '='
0x18001888c  jmp     loc_1800184F2
0x180018891  mov     rax, [rdi]
0x180018894  lea     r8, [rsp+110h+ppropvar]
0x180018899  lea     rdx, PKEY_Identity_PrimarySid
0x1800188a0  mov     rcx, rdi
0x1800188a3  mov     rax, [rax+30h]
0x1800188a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800188ac  mov     ebx, eax
0x1800188ae  test    eax, eax
0x1800188b0  jns     short loc_1800188DD
0x1800188b2  lea     rax, WPP_GLOBAL_Control
0x1800188b9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800188c0  cmp     rcx, rax
0x1800188c3  jz      loc_180018A46
0x1800188c9  test    byte ptr [rcx+1Ch], 4
0x1800188cd  jz      loc_180018A46
0x1800188d3  mov     edx, 3Eh ; '>'
0x1800188d8  jmp     loc_1800184F2
0x1800188dd  lea     rcx, [rsp+110h+ppropvar]; pvar
0x1800188e2  call    cs:__imp_PropVariantClear
0x1800188e8  xor     edx, edx
0x1800188ea  lea     rcx, [rbp+57h+Src]
0x1800188ee  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x1800188f3  lea     rcx, [rsi+4Ch]; Sid
0x1800188f7  lea     rdx, [rbp+57h+Src]; StringSid
0x1800188fb  call    cs:__imp_ConvertSidToStringSidW
0x180018901  test    eax, eax
  ... truncated ...
```
