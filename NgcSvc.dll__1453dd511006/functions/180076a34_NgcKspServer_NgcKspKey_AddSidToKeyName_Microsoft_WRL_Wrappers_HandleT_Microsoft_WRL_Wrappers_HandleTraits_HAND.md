# NgcKspServer::NgcKspKey::AddSidToKeyName(Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits> const &,NgcUtils::NgcKeyName &)

- ea: `0x180076a34`
- end: `0x180076c19`
- name: `?AddSidToKeyName@NgcKspKey@NgcKspServer@@KAJAEBV?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@AEAVNgcKeyName@NgcUtils@@@Z`
- size: `485`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1800126d0`

## callees

- `0x18000782c`
- `0x180010990`
- `0x180025120`
- `0x180028d18`
- `0x18002a3bc`
- `0x18002c9d8`
- `0x180034cf8`
- `0x180046d90`
- `0x18004d980`
- `0x180076a34`
- `0x18008f2dc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180076b3d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180076b3d`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180076b12`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180076b12`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180076b33`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180076b33`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180076be9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180076c01`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180076be9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180076c01`

## string_xrefs

- `0x180076aa8`: `onecore\ds\security\ngc\kspsvc\svc\ops.cpp`
- `0x180076b5c`: `onecore\ds\security\ngc\kspsvc\svc\ops.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall NgcKspServer::NgcKspKey::AddSidToKeyName(__int64 a1, _QWORD *a2)
{
  char IsEnabled; // al
  void *v6; // rcx
  signed int UserSid; // ebx
  __int64 LengthSid; // rbx
  PSID v9; // rcx
  HLOCAL v10; // rcx
  unsigned int v11; // [rsp+20h] [rbp-40h]
  _QWORD v12[2]; // [rsp+30h] [rbp-30h] BYREF
  char v13; // [rsp+40h] [rbp-20h]
  _BYTE v14[24]; // [rsp+48h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+18h]
  signed int v16; // [rsp+88h] [rbp+28h] BYREF
  HLOCAL hMem; // [rsp+90h] [rbp+30h] BYREF
  PSID pDestinationSid; // [rsp+98h] [rbp+38h] BYREF

  if ( *a2 != a2[1] )
    return 0;
  hMem = 0;
  IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::GetImpl'::`2'::impl);
  v6 = *(void **)(a1 + 8);
  v12[1] = 0;
  v13 = 1;
  v12[0] = &hMem;
  if ( !IsEnabled )
  {
    UserSid = GetUserSid(v6);
    wil::details::out_param_t<wistd::unique_ptr<unsigned char,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<unsigned char,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>((__int64)v12);
    if ( UserSid < 0 )
    {
      if ( (unsigned int)dword_180122070 > 2 )
      {
        v16 = UserSid;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
          (__int64)&dword_180122070,
          (unsigned __int8 *)byte_180104325,
          0,
          0,
          (__int64)&v16);
      }
      goto LABEL_19;
    }
    goto LABEL_9;
  }
  UserSid = GetUserSid(v6);
  wil::details::out_param_t<wistd::unique_ptr<unsigned char,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<unsigned char,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>((__int64)v12);
  if ( UserSid >= 0 )
  {
LABEL_9:
    LengthSid = GetLengthSid(*(PSID *)hMem);
    wil::make_unique_hlocal<unsigned char [0]>(&pDestinationSid);
    if ( CopySid(LengthSid, pDestinationSid, *(PSID *)hMem) )
    {
      std::vector<unsigned char>::vector<unsigned char>(v14, pDestinationSid, (char *)pDestinationSid + LengthSid);
      UserSid = NgcUtils::NgcKeyName::SetSid(a2, v14);
      std::vector<unsigned char>::_Tidy(v14);
    }
    else
    {
      UserSid = GetLastError();
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::GetImpl'::`2'::impl) )
      {
        wil::details::in1diag3::Log_Win32(
          retaddr,
          (void *)0x4A2,
          (unsigned int)"onecore\\ds\\security\\ngc\\kspsvc\\svc\\ops.cpp",
          (const char *)(unsigned int)UserSid,
          v11);
      }
      else if ( (unsigned int)dword_180122070 > 2 )
      {
        v16 = UserSid;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
          (__int64)&dword_180122070,
          (unsigned __int8 *)byte_1801042F7,
          0,
          0,
          (__int64)&v16);
      }
      if ( UserSid > 0 )
        UserSid = (unsigned __int16)UserSid | 0x80070000;
    }
    v9 = pDestinationSid;
    pDestinationSid = 0;
    if ( v9 )
      LocalFree(v9);
    goto LABEL_19;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x486,
    (unsigned int)"onecore\\ds\\security\\ngc\\kspsvc\\svc\\ops.cpp",
    (const char *)(unsigned int)UserSid,
    v11);
LABEL_19:
  v10 = hMem;
  hMem = 0;
  if ( v10 )
    LocalFree(v10);
  return (unsigned int)UserSid;
}

```

## disassembly

```asm
0x180076a34  mov     [rsp-18h+arg_0], rbx
0x180076a39  push    rbp
0x180076a3a  push    rsi
0x180076a3b  push    rdi
0x180076a3c  mov     rbp, rsp
0x180076a3f  sub     rsp, 60h
0x180076a43  mov     rdi, rdx
0x180076a46  mov     rbx, rcx
0x180076a49  mov     rax, [rdx+8]
0x180076a4d  cmp     [rdx], rax
0x180076a50  jz      short loc_180076A59
0x180076a52  xor     eax, eax
0x180076a54  jmp     loc_180076C09
0x180076a59  mov     [rbp+hMem], 0
0x180076a61  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration> `wil::Feature<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::GetImpl(void)'::`2'::impl
0x180076a68  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::__private_IsEnabled(void)
0x180076a6d  mov     rcx, [rbx+8]; TokenHandle
0x180076a71  mov     [rbp+var_28], 0
0x180076a79  mov     [rbp+var_20], 1
0x180076a7d  lea     rdx, [rbp+var_28]
0x180076a81  test    al, al
0x180076a83  lea     rax, [rbp+hMem]
0x180076a87  mov     [rbp+var_30], rax
0x180076a8b  jz      short loc_180076ABE
0x180076a8d  call    GetUserSid
0x180076a92  mov     ebx, eax
0x180076a94  lea     rcx, [rbp+var_30]
0x180076a98  call    ??1?$out_param_t@V?$unique_ptr@EU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<uchar,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<uchar,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>(void)
0x180076a9d  test    ebx, ebx
0x180076a9f  jns     short loc_180076B0B
0x180076aa1  mov     rcx, [rbp+18h]; this
0x180076aa5  mov     r9d, ebx; char *
0x180076aa8  lea     r8, aOnecoreDsSecur_43; "onecore\\ds\\security\\ngc\\kspsvc\\svc"...
0x180076aaf  mov     edx, 486h; void *
0x180076ab4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180076ab9  jmp     loc_180076BF0
0x180076abe  call    GetUserSid
0x180076ac3  mov     ebx, eax
0x180076ac5  lea     rcx, [rbp+var_30]
0x180076ac9  call    ??1?$out_param_t@V?$unique_ptr@EU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<uchar,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<uchar,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>(void)
0x180076ace  test    ebx, ebx
0x180076ad0  jns     short loc_180076B0B
0x180076ad2  mov     ecx, cs:dword_180122070
0x180076ad8  cmp     ecx, 2
0x180076adb  jbe     loc_180076BF0
0x180076ae1  mov     [rbp+arg_8], ebx
0x180076ae4  lea     rax, [rbp+arg_8]
0x180076ae8  mov     qword ptr [rsp+60h+var_40], rax
0x180076aed  xor     r9d, r9d
0x180076af0  xor     r8d, r8d
0x180076af3  lea     rdx, byte_180104325
0x180076afa  lea     rcx, dword_180122070
0x180076b01  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x180076b06  jmp     loc_180076BF0
0x180076b0b  mov     rcx, [rbp+hMem]
0x180076b0f  mov     rcx, [rcx]; pSid
0x180076b12  call    cs:__imp_GetLengthSid
0x180076b18  mov     ebx, eax
0x180076b1a  mov     edx, eax
0x180076b1c  lea     rcx, [rbp+pDestinationSid]
0x180076b20  call    ??$make_unique_hlocal@$$BY0A@E@wil@@YA?AV?$unique_ptr@$$BY0A@EU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@_K@Z; wil::make_unique_hlocal<uchar [0]>(unsigned __int64)
0x180076b25  nop
0x180076b26  mov     r8, [rbp+hMem]
0x180076b2a  mov     r8, [r8]; pSourceSid
0x180076b2d  mov     rdx, [rbp+pDestinationSid]; pDestinationSid
0x180076b31  mov     ecx, ebx; nDestinationSidLength
0x180076b33  call    cs:__imp_CopySid
0x180076b39  test    eax, eax
0x180076b3b  jnz     short loc_180076BAE
0x180076b3d  call    cs:__imp_GetLastError
0x180076b43  mov     ebx, eax
0x180076b45  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration> `wil::Feature<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::GetImpl(void)'::`2'::impl
0x180076b4c  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::__private_IsEnabled(void)
0x180076b51  test    al, al
0x180076b53  jz      short loc_180076B6F
0x180076b55  mov     rcx, [rbp+18h]; this
0x180076b59  mov     r9d, ebx; char *
0x180076b5c  lea     r8, aOnecoreDsSecur_43; "onecore\\ds\\security\\ngc\\kspsvc\\svc"...
0x180076b63  mov     edx, 4A2h; void *
0x180076b68  call    ?Log_Win32@in1diag3@details@wil@@YAKPEAXIPEBDK@Z; wil::details::in1diag3::Log_Win32(void *,uint,char const *,ulong)
0x180076b6d  jmp     short loc_180076B9F
0x180076b6f  mov     eax, cs:dword_180122070
0x180076b75  cmp     eax, 2
0x180076b78  jbe     short loc_180076B9F
0x180076b7a  mov     [rbp+arg_8], ebx
0x180076b7d  lea     rax, [rbp+arg_8]
0x180076b81  mov     qword ptr [rsp+60h+var_40], rax
0x180076b86  xor     r9d, r9d
0x180076b89  xor     r8d, r8d
0x180076b8c  lea     rdx, byte_1801042F7
0x180076b93  lea     rcx, dword_180122070
0x180076b9a  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x180076b9f  test    ebx, ebx
0x180076ba1  jle     short loc_180076BD8
0x180076ba3  movzx   ebx, bx
0x180076ba6  or      ebx, 80070000h
0x180076bac  jmp     short loc_180076BD8
0x180076bae  mov     rdx, [rbp+pDestinationSid]
0x180076bb2  lea     r8, [rbx+rdx]
0x180076bb6  lea     rcx, [rbp+var_18]
0x180076bba  call    ??$?0PEBE$0A@@?$vector@EV?$allocator@E@std@@@std@@QEAA@PEBE0AEBV?$allocator@E@1@@Z; std::vector<uchar>::vector<uchar>(uchar const *,uchar const *,std::allocator<uchar> const &)
0x180076bbf  nop
0x180076bc0  lea     rdx, [rbp+var_18]
0x180076bc4  mov     rcx, rdi
0x180076bc7  call    ?SetSid@NgcKeyName@NgcUtils@@QEAAJAEBV?$vector@EV?$allocator@E@std@@@std@@@Z; NgcUtils::NgcKeyName::SetSid(std::vector<uchar> const &)
0x180076bcc  mov     ebx, eax
0x180076bce  lea     rcx, [rbp+var_18]
0x180076bd2  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x180076bd7  nop
0x180076bd8  mov     rcx, [rbp+pDestinationSid]; hMem
0x180076bdc  mov     [rbp+pDestinationSid], 0
0x180076be4  test    rcx, rcx
0x180076be7  jz      short loc_180076BF0
0x180076be9  call    cs:__imp_LocalFree
0x180076bef  nop
0x180076bf0  mov     rcx, [rbp+hMem]; hMem
0x180076bf4  mov     [rbp+hMem], 0
0x180076bfc  test    rcx, rcx
0x180076bff  jz      short loc_180076C07
0x180076c01  call    cs:__imp_LocalFree
0x180076c07  mov     eax, ebx
0x180076c09  mov     rbx, [rsp+60h+arg_0]
0x180076c11  add     rsp, 60h
0x180076c15  pop     rdi
0x180076c16  pop     rsi
0x180076c17  pop     rbp
0x180076c18  retn
```
