# DeviceAccessHandler::ExtractPackageSidString(void *)

- ea: `0x18007c880`
- end: `0x18007ca26`
- name: `?ExtractPackageSidString@DeviceAccessHandler@@AEAAJPEAX@Z`
- size: `422`
- prototype: `int(DeviceAccessHandler *__hidden this, void *)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18007d914`

## callees

- `0x180009608`
- `0x180009f50`
- `0x18000a91c`
- `0x180017a3c`
- `0x180017a64`
- `0x18007c880`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007c8bc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007c983`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007c9c8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007c8bc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007c983`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007c9c8`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18007c9be`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18007c9be`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18007c8b2`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18007c979`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18007c8b2`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18007c979`

## pseudocode

```c
__int64 __fastcall DeviceAccessHandler::ExtractPackageSidString(LPWSTR *this, void *a2)
{
  signed int v2; // esi
  signed int v5; // eax
  __int64 v6; // rdx
  const struct std::nothrow_t *unique; // rax
  PSID *v8; // rbx
  signed int LastError; // eax
  signed int v10; // eax
  _QWORD v12[5]; // [rsp+30h] [rbp-28h] BYREF
  DWORD TokenInformationLength; // [rsp+70h] [rbp+18h] BYREF
  LPVOID TokenInformation; // [rsp+78h] [rbp+20h] BYREF

  v2 = 0;
  TokenInformation = 0;
  TokenInformationLength = 0;
  if ( GetTokenInformation(a2, TokenAppContainerSid, 0, 0, &TokenInformationLength)
    || (v5 = GetLastError(), v5 == 122)
    || (v5 > 0 ? (v2 = (unsigned __int16)v5 | 0x80070000) : (v2 = v5), v2 >= 0) )
  {
    if ( TokenInformationLength == 8 )
    {
      v2 = -2147023728;
      if ( g_wppLevels )
      {
        v6 = 86;
        goto LABEL_27;
      }
    }
    else
    {
      unique = (const struct std::nothrow_t *)wil::make_unique_nothrow<unsigned char [0]>(v12, TokenInformationLength);
      wistd::unique_ptr<unsigned long [0],wistd::default_delete<unsigned long [0]>>::operator=(
        &TokenInformation,
        unique);
      wistd::unique_ptr<unsigned char [0],wistd::default_delete<unsigned char [0]>>::reset(v12);
      v8 = (PSID *)TokenInformation;
      if ( TokenInformation )
      {
        if ( GetTokenInformation(
               a2,
               TokenAppContainerSid,
               TokenInformation,
               TokenInformationLength,
               &TokenInformationLength) )
        {
          goto LABEL_21;
        }
        LastError = GetLastError();
        v2 = LastError;
        if ( LastError > 0 )
          v2 = (unsigned __int16)LastError | 0x80070000;
        if ( v2 >= 0 )
        {
LABEL_21:
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
            this + 8,
            0);
          if ( !ConvertSidToStringSidW(*v8, this + 8) )
          {
            v10 = GetLastError();
            v2 = v10;
            if ( v10 > 0 )
              v2 = (unsigned __int16)v10 | 0x80070000;
            if ( v2 < 0 && g_wppLevels )
            {
              v6 = 89;
              goto LABEL_27;
            }
          }
        }
        else if ( g_wppLevels )
        {
          v6 = 88;
          goto LABEL_27;
        }
      }
      else
      {
        v2 = -2147024882;
        if ( g_wppLevels )
        {
          v6 = (unsigned int)((_DWORD)TokenInformation + 87);
          goto LABEL_27;
        }
      }
    }
  }
  else if ( g_wppLevels )
  {
    v6 = 85;
LABEL_27:
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v6, &WPP_0624fae52b0938a3be09ac660a5d0b65_Traceguids, this, v2);
  }
  wistd::unique_ptr<unsigned char [0],wistd::default_delete<unsigned char [0]>>::reset(&TokenInformation);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x18007c880  mov     rax, rsp
0x18007c883  mov     [rax+8], rbx
0x18007c887  push    rbp
0x18007c888  push    rsi
0x18007c889  push    rdi
0x18007c88a  sub     rsp, 40h
0x18007c88e  xor     esi, esi
0x18007c890  mov     rdi, rdx
0x18007c893  mov     [rax+20h], rsi
0x18007c897  mov     rbp, rcx
0x18007c89a  mov     [rax+18h], esi
0x18007c89d  lea     rax, [rax+18h]
0x18007c8a1  xor     r9d, r9d; TokenInformationLength
0x18007c8a4  mov     [rsp+58h+ReturnLength], rax; ReturnLength
0x18007c8a9  lea     edx, [rsi+1Fh]; TokenInformationClass
0x18007c8ac  xor     r8d, r8d; TokenInformation
0x18007c8af  mov     rcx, rdi; TokenHandle
0x18007c8b2  call    cs:__imp_GetTokenInformation
0x18007c8b8  test    eax, eax
0x18007c8ba  jnz     short loc_18007C8F3
0x18007c8bc  call    cs:__imp_GetLastError
0x18007c8c2  cmp     eax, 7Ah ; 'z'
0x18007c8c5  jz      short loc_18007C8F3
0x18007c8c7  test    eax, eax
0x18007c8c9  jg      short loc_18007C8CF
0x18007c8cb  mov     esi, eax
0x18007c8cd  jmp     short loc_18007C8D8
0x18007c8cf  movzx   esi, ax
0x18007c8d2  or      esi, 80070000h
0x18007c8d8  test    esi, esi
0x18007c8da  jns     short loc_18007C8F3
0x18007c8dc  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18007c8e3  jb      loc_18007CA0D
0x18007c8e9  mov     edx, 55h ; 'U'
0x18007c8ee  jmp     loc_18007C9EF
0x18007c8f3  cmp     [rsp+58h+TokenInformationLength], 8
0x18007c8f8  jnz     short loc_18007C916
0x18007c8fa  mov     esi, 80070490h
0x18007c8ff  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18007c906  jb      loc_18007CA0D
0x18007c90c  mov     edx, 56h ; 'V'
0x18007c911  jmp     loc_18007C9EF
0x18007c916  mov     edx, [rsp+58h+TokenInformationLength]
0x18007c91a  lea     rcx, [rsp+58h+var_28]
0x18007c91f  call    ??$make_unique_nothrow@$$BY0A@E@wil@@YA?AV?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@wistd@@@wistd@@_K@Z; wil::make_unique_nothrow<uchar [0]>(unsigned __int64)
0x18007c924  mov     rdx, rax
0x18007c927  lea     rcx, [rsp+58h+TokenInformation]
0x18007c92c  call    ??4?$unique_ptr@$$BY0A@KU?$default_delete@$$BY0A@K@wistd@@@wistd@@QEAAAEAV01@$$QEAV01@@Z; wistd::unique_ptr<ulong [0],wistd::default_delete<ulong [0]>>::operator=(wistd::unique_ptr<ulong [0],wistd::default_delete<ulong [0]>> &&)
0x18007c931  lea     rcx, [rsp+58h+var_28]
0x18007c936  call    ?reset@?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@wistd@@@wistd@@QEAAX$$T@Z; wistd::unique_ptr<uchar [0],wistd::default_delete<uchar [0]>>::reset(std::nullptr_t)
0x18007c93b  mov     rbx, [rsp+58h+TokenInformation]
0x18007c940  test    rbx, rbx
0x18007c943  jnz     short loc_18007C95F
0x18007c945  mov     esi, 8007000Eh
0x18007c94a  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18007c951  jb      loc_18007CA0D
0x18007c957  lea     edx, [rbx+57h]
0x18007c95a  jmp     loc_18007C9EF
0x18007c95f  mov     r9d, [rsp+58h+TokenInformationLength]; TokenInformationLength
0x18007c964  lea     rax, [rsp+58h+TokenInformationLength]
0x18007c969  mov     r8, rbx; TokenInformation
0x18007c96c  mov     [rsp+58h+ReturnLength], rax; ReturnLength
0x18007c971  mov     edx, 1Fh; TokenInformationClass
0x18007c976  mov     rcx, rdi; TokenHandle
0x18007c979  call    cs:__imp_GetTokenInformation
0x18007c97f  test    eax, eax
0x18007c981  jnz     short loc_18007C9AC
0x18007c983  call    cs:__imp_GetLastError
0x18007c989  mov     esi, eax
0x18007c98b  test    eax, eax
0x18007c98d  jle     short loc_18007C998
0x18007c98f  movzx   esi, ax
0x18007c992  or      esi, 80070000h
0x18007c998  test    esi, esi
0x18007c99a  jns     short loc_18007C9AC
0x18007c99c  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18007c9a3  jb      short loc_18007CA0D
0x18007c9a5  mov     edx, 58h ; 'X'
0x18007c9aa  jmp     short loc_18007C9EF
0x18007c9ac  xor     edx, edx
0x18007c9ae  lea     rcx, [rbp+40h]
0x18007c9b2  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18007c9b7  mov     rcx, [rbx]; Sid
0x18007c9ba  lea     rdx, [rbp+40h]; StringSid
0x18007c9be  call    cs:__imp_ConvertSidToStringSidW
0x18007c9c4  test    eax, eax
0x18007c9c6  jnz     short loc_18007CA0D
0x18007c9c8  call    cs:__imp_GetLastError
0x18007c9ce  mov     esi, eax
0x18007c9d0  test    eax, eax
0x18007c9d2  jle     short loc_18007C9DD
0x18007c9d4  movzx   esi, ax
0x18007c9d7  or      esi, 80070000h
0x18007c9dd  test    esi, esi
0x18007c9df  jns     short loc_18007CA0D
0x18007c9e1  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18007c9e8  jb      short loc_18007CA0D
0x18007c9ea  mov     edx, 59h ; 'Y'
0x18007c9ef  mov     rcx, cs:WPP_GLOBAL_Control
0x18007c9f6  lea     r8, WPP_0624fae52b0938a3be09ac660a5d0b65_Traceguids
0x18007c9fd  mov     r9, rbp
0x18007ca00  mov     dword ptr [rsp+58h+ReturnLength], esi
0x18007ca04  mov     rcx, [rcx+10h]
0x18007ca08  call    WPP_SF_qD
0x18007ca0d  lea     rcx, [rsp+58h+TokenInformation]
0x18007ca12  call    ?reset@?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@wistd@@@wistd@@QEAAX$$T@Z; wistd::unique_ptr<uchar [0],wistd::default_delete<uchar [0]>>::reset(std::nullptr_t)
0x18007ca17  mov     rbx, [rsp+58h+arg_0]
0x18007ca1c  mov     eax, esi
0x18007ca1e  add     rsp, 40h
0x18007ca22  pop     rdi
0x18007ca23  pop     rsi
0x18007ca24  pop     rbp
0x18007ca25  retn
```
