# NgcUtils::GetUserSidFromToken

- ea: `0x180074d0c`
- end: `0x180074ea2`
- name: `NgcUtils::GetUserSidFromToken`
- size: `406`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180071fcc`

## callees

- `0x180002654`
- `0x1800084c8`
- `0x180011c1c`
- `0x1800178c0`
- `0x18001ddec`
- `0x180074d0c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180074d55`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180074dcb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180074d55`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180074dcb`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180074d4b`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180074dc1`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180074d4b`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180074dc1`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180074e7a`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180074e7a`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180074e13`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180074e13`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall NgcUtils::GetUserSidFromToken(__int64 a1, PSID *a2)
{
  signed int v3; // ebx
  int v4; // r8d
  int v5; // r9d
  DWORD LastError; // eax
  int v7; // r8d
  int v8; // r9d
  DWORD LengthSid; // eax
  DWORD v10; // r14d
  char *v11; // rdx
  char *v12; // rsi
  unsigned __int64 v13; // rcx
  size_t v14; // rbx
  LPVOID TokenInformation[4]; // [rsp+30h] [rbp-20h] BYREF
  DWORD TokenInformationLength; // [rsp+70h] [rbp+20h] BYREF
  int v18; // [rsp+74h] [rbp+24h]
  DWORD v19; // [rsp+80h] [rbp+30h] BYREF

  v18 = HIDWORD(a1);
  TokenInformationLength = 0;
  if ( GetTokenInformation((HANDLE)0xFFFFFFFFFFFFFFFALL, TokenUser, 0, 0, &TokenInformationLength)
    || (v3 = GetLastError(), v3 == 122) )
  {
    std::vector<unsigned char>::vector<unsigned char>(TokenInformation, TokenInformationLength);
    if ( GetTokenInformation(
           (HANDLE)0xFFFFFFFFFFFFFFFALL,
           TokenUser,
           TokenInformation[0],
           TokenInformationLength,
           &TokenInformationLength) )
    {
      LengthSid = GetLengthSid(*(PSID *)TokenInformation[0]);
      v10 = LengthSid;
      v11 = (char *)*a2;
      v12 = (char *)a2[1];
      v13 = v12 - (_BYTE *)*a2;
      if ( LengthSid >= v13 )
      {
        if ( LengthSid > v13 )
        {
          if ( LengthSid <= (unsigned __int64)((_BYTE *)a2[2] - v11) )
          {
            v14 = LengthSid - v13;
            memset_0(a2[1], 0, v14);
            a2[1] = &v12[v14];
          }
          else
          {
            std::vector<unsigned char>::_Resize_reallocate<std::_Value_init_tag>(a2, LengthSid);
          }
        }
      }
      else
      {
        a2[1] = &v11[LengthSid];
      }
      CopySid(v10, *a2, *(PSID *)TokenInformation[0]);
      v3 = 0;
    }
    else
    {
      LastError = GetLastError();
      v3 = LastError;
      if ( *(_DWORD *)g_logProvider > 2u )
      {
        v19 = LastError;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
          g_logProvider,
          (unsigned int)&dword_1800B3D3C,
          v7,
          v8,
          (__int64)&v19);
      }
      if ( v3 > 0 )
        v3 = (unsigned __int16)v3 | 0x80070000;
    }
    std::vector<unsigned char>::_Tidy(TokenInformation);
  }
  else
  {
    if ( *(_DWORD *)g_logProvider > 2u )
    {
      v19 = v3;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
        g_logProvider,
        (unsigned int)&byte_1800B3D67,
        v4,
        v5,
        (__int64)&v19);
    }
    if ( v3 > 0 )
      return (unsigned __int16)v3 | 0x80070000;
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180074d0c  mov     r11, rsp
0x180074d0f  mov     [r11+10h], rbx
0x180074d13  mov     [r11+20h], rsi
0x180074d17  mov     [r11+8], rcx
0x180074d1b  push    rbp
0x180074d1c  push    rdi
0x180074d1d  push    r14
0x180074d1f  mov     rbp, rsp
0x180074d22  sub     rsp, 50h
0x180074d26  mov     rdi, rdx
0x180074d29  mov     [rbp+TokenInformationLength], 0
0x180074d30  lea     rax, [rbp+TokenInformationLength]
0x180074d34  mov     [r11-48h], rax
0x180074d38  xor     r9d, r9d; TokenInformationLength
0x180074d3b  xor     r8d, r8d; TokenInformation
0x180074d3e  lea     esi, [r9+1]
0x180074d42  mov     edx, esi; TokenInformationClass
0x180074d44  lea     r14, [r9-6]
0x180074d48  mov     rcx, r14; TokenHandle
0x180074d4b  call    cs:__imp_GetTokenInformation
0x180074d51  test    eax, eax
0x180074d53  jnz     short loc_180074D9E
0x180074d55  call    cs:__imp_GetLastError
0x180074d5b  mov     ebx, eax
0x180074d5d  cmp     eax, 7Ah ; 'z'
0x180074d60  jz      short loc_180074D9E
0x180074d62  mov     rcx, cs:g_logProvider
0x180074d69  mov     eax, [rcx]
0x180074d6b  cmp     eax, 2
0x180074d6e  jbe     short loc_180074D88
0x180074d70  mov     [rbp+arg_10], ebx
0x180074d73  lea     rax, [rbp+arg_10]
0x180074d77  mov     [rsp+50h+ReturnLength], rax
0x180074d7c  lea     rdx, byte_1800B3D67
0x180074d83  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x180074d88  test    ebx, ebx
0x180074d8a  jle     loc_180074E8B
0x180074d90  movzx   ebx, bx
0x180074d93  or      ebx, 80070000h
0x180074d99  jmp     loc_180074E8B
0x180074d9e  mov     edx, [rbp+TokenInformationLength]
0x180074da1  lea     rcx, [rbp+TokenInformation]
0x180074da5  call    ??0?$vector@EV?$allocator@E@std@@@std@@QEAA@_KAEBV?$allocator@E@1@@Z; std::vector<uchar>::vector<uchar>(unsigned __int64,std::allocator<uchar> const &)
0x180074daa  nop
0x180074dab  lea     rax, [rbp+TokenInformationLength]
0x180074daf  mov     [rsp+50h+ReturnLength], rax; ReturnLength
0x180074db4  mov     r9d, [rbp+TokenInformationLength]; TokenInformationLength
0x180074db8  mov     r8, [rbp+TokenInformation]; TokenInformation
0x180074dbc  mov     edx, esi; TokenInformationClass
0x180074dbe  mov     rcx, r14; TokenHandle
0x180074dc1  call    cs:__imp_GetTokenInformation
0x180074dc7  test    eax, eax
0x180074dc9  jnz     short loc_180074E0C
0x180074dcb  call    cs:__imp_GetLastError
0x180074dd1  mov     ebx, eax
0x180074dd3  mov     rcx, cs:g_logProvider
0x180074dda  mov     edx, [rcx]
0x180074ddc  cmp     edx, 2
0x180074ddf  jbe     short loc_180074DF9
0x180074de1  mov     [rbp+arg_10], eax
0x180074de4  lea     rax, [rbp+arg_10]
0x180074de8  mov     [rsp+50h+ReturnLength], rax
0x180074ded  lea     rdx, dword_1800B3D3C
0x180074df4  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x180074df9  test    ebx, ebx
0x180074dfb  jle     loc_180074E82
0x180074e01  movzx   ebx, bx
0x180074e04  or      ebx, 80070000h
0x180074e0a  jmp     short loc_180074E82
0x180074e0c  mov     rcx, [rbp+TokenInformation]
0x180074e10  mov     rcx, [rcx]; pSid
0x180074e13  call    cs:__imp_GetLengthSid
0x180074e19  mov     r14d, eax
0x180074e1c  mov     rdx, [rdi]
0x180074e1f  mov     rsi, [rdi+8]
0x180074e23  mov     rcx, rsi
0x180074e26  sub     rcx, rdx
0x180074e29  mov     ebx, eax
0x180074e2b  cmp     r14, rcx
0x180074e2e  jnb     short loc_180074E3A
0x180074e30  lea     rcx, [r14+rdx]
0x180074e34  mov     [rdi+8], rcx
0x180074e38  jmp     short loc_180074E6D
0x180074e3a  jbe     short loc_180074E6D
0x180074e3c  mov     rax, [rdi+10h]
0x180074e40  sub     rax, rdx
0x180074e43  cmp     rbx, rax
0x180074e46  jbe     short loc_180074E55
0x180074e48  mov     rdx, rbx
0x180074e4b  mov     rcx, rdi
0x180074e4e  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@EV?$allocator@E@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<uchar>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x180074e53  jmp     short loc_180074E6D
0x180074e55  sub     rbx, rcx
0x180074e58  mov     r8, rbx; Size
0x180074e5b  xor     edx, edx; Val
0x180074e5d  mov     rcx, rsi; void *
0x180074e60  call    memset_0
0x180074e65  lea     rax, [rbx+rsi]
0x180074e69  mov     [rdi+8], rax
0x180074e6d  mov     r8, [rbp+TokenInformation]
0x180074e71  mov     r8, [r8]; pSourceSid
0x180074e74  mov     rdx, [rdi]; pDestinationSid
0x180074e77  mov     ecx, r14d; nDestinationSidLength
0x180074e7a  call    cs:__imp_CopySid
0x180074e80  xor     ebx, ebx
0x180074e82  lea     rcx, [rbp+TokenInformation]
0x180074e86  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x180074e8b  mov     eax, ebx
0x180074e8d  lea     r11, [rsp+50h+var_s0]
0x180074e92  mov     rbx, [r11+28h]
0x180074e96  mov     rsi, [r11+38h]
0x180074e9a  mov     rsp, r11
0x180074e9d  pop     r14
0x180074e9f  pop     rdi
0x180074ea0  pop     rbp
0x180074ea1  retn
```
