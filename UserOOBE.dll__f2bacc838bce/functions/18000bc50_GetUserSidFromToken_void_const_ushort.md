# GetUserSidFromToken(void * const,ushort * *)

- ea: `0x18000bc50`
- end: `0x18000be54`
- name: `?GetUserSidFromToken@@YAJQEAXPEAPEAG@Z`
- size: `516`
- prototype: `__int64 __fastcall(void *const, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18000bef8`

## callees

- `0x180004200`
- `0x180007114`
- `0x180007134`
- `0x180009f90`
- `0x180009fc4`
- `0x18000a144`
- `0x18000a5e8`
- `0x18000bc50`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bca2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bca2`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18000bdc2`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18000bdc2`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000bc98`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000bd6e`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000bc98`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000bd6e`

## pseudocode

```c
__int64 __fastcall GetUserSidFromToken(void *const a1, unsigned __int16 **a2)
{
  signed int LastError; // eax
  unsigned int v5; // ebx
  __int64 result; // rax
  char *v7; // rdi
  char *v8; // rax
  size_t v9; // rbx
  const char *v10; // r9
  unsigned int v11; // ebx
  const char *v12; // r9
  const char *v13; // r9
  unsigned int v14; // ebx
  unsigned __int16 *v15; // rax
  int ReturnLength; // [rsp+20h] [rbp-38h]
  LPVOID TokenInformation; // [rsp+30h] [rbp-28h] BYREF
  void *v18; // [rsp+38h] [rbp-20h]
  __int64 v19; // [rsp+40h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  void *TokenInformationLength; // [rsp+60h] [rbp+8h] BYREF
  LPWSTR StringSid; // [rsp+68h] [rbp+10h] BYREF

  TokenInformationLength = a1;
  *a2 = 0;
  std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<enum OOBEMonitorEvent const,unsigned long>>>>>>::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<enum OOBEMonitorEvent const,unsigned long>>>>>>(&TokenInformation);
  LODWORD(TokenInformationLength) = 0;
  if ( !GetTokenInformation((HANDLE)0xFFFFFFFFFFFFFFFALL, TokenUser, 0, 0, (PDWORD)&TokenInformationLength) )
  {
    LastError = GetLastError();
    v5 = LastError;
    if ( LastError != 122 )
    {
      if ( LastError > 0 )
        v5 = (unsigned __int16)LastError | 0x80070000;
      if ( (v5 & 0x80000000) != 0 )
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x12,
          (unsigned int)"onecore\\internal\\shell\\inc\\private\\candidateuserhelpers.h",
          (const char *)v5,
          ReturnLength);
      if ( TokenInformation )
        std::_Deallocate<16>(TokenInformation, v19 - (_QWORD)TokenInformation);
      return v5;
    }
  }
  try
  {
    v7 = (char *)v18;
    if ( (unsigned int)TokenInformationLength >= (unsigned __int64)((_BYTE *)v18 - (_BYTE *)TokenInformation) )
    {
      if ( (unsigned int)TokenInformationLength <= (unsigned __int64)((_BYTE *)v18 - (_BYTE *)TokenInformation) )
        goto LABEL_17;
      if ( (unsigned int)TokenInformationLength > (unsigned __int64)(v19 - (_QWORD)TokenInformation) )
      {
        std::vector<unsigned char>::_Resize_reallocate<std::_Value_init_tag>(
          &TokenInformation,
          (unsigned int)TokenInformationLength);
        goto LABEL_17;
      }
      v9 = (unsigned int)TokenInformationLength - ((_BYTE *)v18 - (_BYTE *)TokenInformation);
      memset_0(v18, 0, v9);
      v8 = &v7[v9];
    }
    else
    {
      v8 = (char *)TokenInformation + (unsigned int)TokenInformationLength;
    }
    v18 = v8;
LABEL_17:
    if ( GetTokenInformation(
           (HANDLE)0xFFFFFFFFFFFFFFFALL,
           TokenUser,
           TokenInformation,
           (DWORD)TokenInformationLength,
           (PDWORD)&TokenInformationLength) )
    {
      StringSid = 0;
      if ( ConvertSidToStringSidW(*(PSID *)TokenInformation, &StringSid) )
      {
        v15 = StringSid;
        StringSid = 0;
        *a2 = v15;
        wil::details::unique_storage<wil::details::resource_policy<_TOKEN_GROUPS *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_TOKEN_GROUPS *,_TOKEN_GROUPS *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_TOKEN_GROUPS *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_TOKEN_GROUPS *,_TOKEN_GROUPS *,0,std::nullptr_t>>(&StringSid);
        if ( TokenInformation )
          std::_Deallocate<16>(TokenInformation, v19 - (_QWORD)TokenInformation);
        result = 0;
      }
      else
      {
        v14 = wil::details::in1diag3::Return_GetLastError(
                retaddr,
                (void *)0x1A,
                (unsigned int)"onecore\\internal\\shell\\inc\\private\\candidateuserhelpers.h",
                v13);
        wil::details::unique_storage<wil::details::resource_policy<_TOKEN_GROUPS *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_TOKEN_GROUPS *,_TOKEN_GROUPS *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_TOKEN_GROUPS *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_TOKEN_GROUPS *,_TOKEN_GROUPS *,0,std::nullptr_t>>(&StringSid);
        if ( TokenInformation )
          std::_Deallocate<16>(TokenInformation, v19 - (_QWORD)TokenInformation);
        result = v14;
      }
    }
    else
    {
      v11 = wil::details::in1diag3::Return_GetLastError(
              retaddr,
              (void *)0x16,
              (unsigned int)"onecore\\internal\\shell\\inc\\private\\candidateuserhelpers.h",
              v10);
      if ( TokenInformation )
        std::_Deallocate<16>(TokenInformation, v19 - (_QWORD)TokenInformation);
      result = v11;
    }
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x1F,
                           (unsigned int)"onecore\\internal\\shell\\inc\\private\\candidateuserhelpers.h",
                           v12);
  }
  return result;
}

```

## disassembly

```asm
0x18000bc50  mov     rax, rsp
0x18000bc53  mov     [rax+18h], rbx
0x18000bc57  mov     [rax+20h], rsi
0x18000bc5b  mov     [rax+8], rcx
0x18000bc5f  push    rdi
0x18000bc60  sub     rsp, 50h
0x18000bc64  mov     rsi, rdx
0x18000bc67  mov     qword ptr [rdx], 0
0x18000bc6e  lea     rcx, [rax-28h]
0x18000bc72  call    ??$?0AEBV?$allocator@U?$pair@$$CBW4OOBEMonitorEvent@@K@std@@@std@@$0A@@?$_Hash_vec@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBW4OOBEMonitorEvent@@K@std@@@std@@@std@@@std@@@std@@@std@@QEAA@AEBV?$allocator@U?$pair@$$CBW4OOBEMonitorEvent@@K@std@@@1@@Z; std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<OOBEMonitorEvent const,ulong>>>>>>::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<OOBEMonitorEvent const,ulong>>>>>>(std::allocator<std::pair<OOBEMonitorEvent const,ulong>> const &)
0x18000bc77  nop
0x18000bc78  mov     dword ptr [rsp+58h+TokenInformationLength], 0
0x18000bc80  lea     rax, [rsp+58h+TokenInformationLength]
0x18000bc85  mov     qword ptr [rsp+58h+ReturnLength], rax; int
0x18000bc8a  xor     r9d, r9d; TokenInformationLength
0x18000bc8d  xor     r8d, r8d; TokenInformation
0x18000bc90  lea     edx, [r9+1]; TokenInformationClass
0x18000bc94  lea     rcx, [r9-6]; TokenHandle
0x18000bc98  call    cs:__imp_GetTokenInformation
0x18000bc9e  test    eax, eax
0x18000bca0  jnz     short loc_18000BCF8
0x18000bca2  call    cs:__imp_GetLastError
0x18000bca8  mov     ebx, eax
0x18000bcaa  cmp     eax, 7Ah ; 'z'
0x18000bcad  jz      short loc_18000BCF8
0x18000bcaf  test    eax, eax
0x18000bcb1  jle     short loc_18000BCBC
0x18000bcb3  movzx   ebx, ax
0x18000bcb6  or      ebx, 80070000h
0x18000bcbc  test    ebx, ebx
0x18000bcbe  jns     short loc_18000BCDA
0x18000bcc0  mov     rcx, [rsp+58h]; this
0x18000bcc5  mov     r9d, ebx; char *
0x18000bcc8  lea     r8, aOnecoreInterna_7; "onecore\\internal\\shell\\inc\\private"...
0x18000bccf  mov     edx, 12h; void *
0x18000bcd4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000bcd9  nop
0x18000bcda  mov     rcx, [rsp+58h+TokenInformation]
0x18000bcdf  test    rcx, rcx
0x18000bce2  jz      short loc_18000BCF1
0x18000bce4  mov     rdx, [rsp+58h+var_18]
0x18000bce9  sub     rdx, rcx
0x18000bcec  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18000bcf1  mov     eax, ebx
0x18000bcf3  jmp     loc_18000BE43
0x18000bcf8  mov     ebx, dword ptr [rsp+58h+TokenInformationLength]
0x18000bcfc  mov     rdx, [rsp+58h+TokenInformation]
0x18000bd01  mov     rdi, [rsp+58h+var_20]
0x18000bd06  mov     rcx, rdi
0x18000bd09  sub     rcx, rdx
0x18000bd0c  cmp     rbx, rcx
0x18000bd0f  jnb     short loc_18000BD17
0x18000bd11  lea     rax, [rbx+rdx]
0x18000bd15  jmp     short loc_18000BD49
0x18000bd17  jbe     short loc_18000BD4E
0x18000bd19  mov     rax, [rsp+58h+var_18]
0x18000bd1e  sub     rax, rdx
0x18000bd21  cmp     rbx, rax
0x18000bd24  jbe     short loc_18000BD35
0x18000bd26  mov     rdx, rbx
0x18000bd29  lea     rcx, [rsp+58h+TokenInformation]
0x18000bd2e  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@EV?$allocator@E@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<uchar>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x18000bd33  jmp     short loc_18000BD4E
0x18000bd35  sub     rbx, rcx
0x18000bd38  mov     r8, rbx; Size
0x18000bd3b  xor     edx, edx; Val
0x18000bd3d  mov     rcx, rdi; void *
0x18000bd40  call    memset_0
0x18000bd45  lea     rax, [rbx+rdi]
0x18000bd49  mov     [rsp+58h+var_20], rax
0x18000bd4e  lea     rax, [rsp+58h+TokenInformationLength]
0x18000bd53  mov     qword ptr [rsp+58h+ReturnLength], rax; ReturnLength
0x18000bd58  mov     r9d, dword ptr [rsp+58h+TokenInformationLength]; TokenInformationLength
0x18000bd5d  mov     r8, [rsp+58h+TokenInformation]; TokenInformation
0x18000bd62  mov     edx, 1; TokenInformationClass
0x18000bd67  mov     rcx, 0FFFFFFFFFFFFFFFAh; TokenHandle
0x18000bd6e  call    cs:__imp_GetTokenInformation
0x18000bd74  test    eax, eax
0x18000bd76  jnz     short loc_18000BDAC
0x18000bd78  mov     rcx, [rsp+58h]; this
0x18000bd7d  lea     r8, aOnecoreInterna_7; "onecore\\internal\\shell\\inc\\private"...
0x18000bd84  lea     edx, [rax+16h]; void *
0x18000bd87  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000bd8c  mov     ebx, eax
0x18000bd8e  mov     rcx, [rsp+58h+TokenInformation]
0x18000bd93  test    rcx, rcx
0x18000bd96  jz      short loc_18000BDA5
0x18000bd98  mov     rdx, [rsp+58h+var_18]
0x18000bd9d  sub     rdx, rcx
0x18000bda0  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18000bda5  mov     eax, ebx
0x18000bda7  jmp     loc_18000BE43
0x18000bdac  mov     [rsp+58h+StringSid], 0
0x18000bdb5  lea     rdx, [rsp+58h+StringSid]; StringSid
0x18000bdba  mov     rcx, [rsp+58h+TokenInformation]
0x18000bdbf  mov     rcx, [rcx]; Sid
0x18000bdc2  call    cs:__imp_ConvertSidToStringSidW
0x18000bdc8  test    eax, eax
0x18000bdca  jnz     short loc_18000BE08
0x18000bdcc  mov     rcx, [rsp+58h]; this
0x18000bdd1  lea     r8, aOnecoreInterna_7; "onecore\\internal\\shell\\inc\\private"...
0x18000bdd8  lea     edx, [rax+1Ah]; void *
0x18000bddb  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000bde0  mov     ebx, eax
0x18000bde2  lea     rcx, [rsp+58h+StringSid]
0x18000bde7  call    ??1?$unique_storage@U?$resource_policy@PEAU_TOKEN_GROUPS@@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_TOKEN_GROUPS *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_TOKEN_GROUPS *,_TOKEN_GROUPS *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_TOKEN_GROUPS *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_TOKEN_GROUPS *,_TOKEN_GROUPS *,0,std::nullptr_t>>(void)
0x18000bdec  nop
0x18000bded  mov     rcx, [rsp+58h+TokenInformation]
0x18000bdf2  test    rcx, rcx
0x18000bdf5  jz      short loc_18000BE04
0x18000bdf7  mov     rdx, [rsp+58h+var_18]
0x18000bdfc  sub     rdx, rcx
0x18000bdff  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18000be04  mov     eax, ebx
0x18000be06  jmp     short loc_18000BE43
0x18000be08  mov     rax, [rsp+58h+StringSid]
0x18000be0d  mov     [rsp+58h+StringSid], 0
0x18000be16  mov     [rsi], rax
0x18000be19  lea     rcx, [rsp+58h+StringSid]
0x18000be1e  call    ??1?$unique_storage@U?$resource_policy@PEAU_TOKEN_GROUPS@@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_TOKEN_GROUPS *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_TOKEN_GROUPS *,_TOKEN_GROUPS *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_TOKEN_GROUPS *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_TOKEN_GROUPS *,_TOKEN_GROUPS *,0,std::nullptr_t>>(void)
0x18000be23  nop
0x18000be24  mov     rcx, [rsp+58h+TokenInformation]
0x18000be29  test    rcx, rcx
0x18000be2c  jz      short loc_18000BE3B
0x18000be2e  mov     rdx, [rsp+58h+var_18]
0x18000be33  sub     rdx, rcx
0x18000be36  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18000be3b  xor     eax, eax
0x18000be3d  jmp     short loc_18000BE43
0x18000be3f  mov     eax, dword ptr [rsp+58h+TokenInformationLength]
0x18000be43  mov     rbx, [rsp+58h+arg_10]
0x18000be48  mov     rsi, [rsp+58h+arg_18]
0x18000be4d  add     rsp, 50h
0x18000be51  pop     rdi
0x18000be52  retn
```
