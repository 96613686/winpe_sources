# DeviceAccessHandler::ExtractUserSidString(void *)

- ea: `0x18007cb94`
- end: `0x18007cd17`
- name: `?ExtractUserSidString@DeviceAccessHandler@@AEAAJPEAX@Z`
- size: `387`
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
- `0x18007cb94`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007cbd0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007cc74`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007ccb9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007cbd0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007cc74`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007ccb9`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18007ccaf`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18007ccaf`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18007cbc6`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18007cc6a`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18007cbc6`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18007cc6a`

## pseudocode

```c
__int64 __fastcall DeviceAccessHandler::ExtractUserSidString(LPWSTR *this, void *a2)
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
  if ( GetTokenInformation(a2, TokenUser, 0, 0, &TokenInformationLength)
    || (v5 = GetLastError(), v5 == 122)
    || (v5 > 0 ? (v2 = (unsigned __int16)v5 | 0x80070000) : (v2 = v5), v2 >= 0) )
  {
    unique = (const struct std::nothrow_t *)wil::make_unique_nothrow<unsigned char [0]>(v12, TokenInformationLength);
    wistd::unique_ptr<unsigned long [0],wistd::default_delete<unsigned long [0]>>::operator=(&TokenInformation, unique);
    wistd::unique_ptr<unsigned char [0],wistd::default_delete<unsigned char [0]>>::reset(v12);
    v8 = (PSID *)TokenInformation;
    if ( TokenInformation )
    {
      if ( GetTokenInformation(a2, TokenUser, TokenInformation, TokenInformationLength, &TokenInformationLength) )
        goto LABEL_18;
      LastError = GetLastError();
      v2 = LastError;
      if ( LastError > 0 )
        v2 = (unsigned __int16)LastError | 0x80070000;
      if ( v2 >= 0 )
      {
LABEL_18:
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
          this + 9,
          0);
        if ( !ConvertSidToStringSidW(*v8, this + 9) )
        {
          v10 = GetLastError();
          v2 = v10;
          if ( v10 > 0 )
            v2 = (unsigned __int16)v10 | 0x80070000;
          if ( v2 < 0 && g_wppLevels )
          {
            v6 = 83;
            goto LABEL_24;
          }
        }
      }
      else if ( g_wppLevels )
      {
        v6 = 82;
        goto LABEL_24;
      }
    }
    else
    {
      v2 = -2147024882;
      if ( g_wppLevels )
      {
        v6 = (unsigned int)((_DWORD)TokenInformation + 81);
        goto LABEL_24;
      }
    }
  }
  else if ( g_wppLevels )
  {
    v6 = 80;
LABEL_24:
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v6, &WPP_0624fae52b0938a3be09ac660a5d0b65_Traceguids, this, v2);
  }
  wistd::unique_ptr<unsigned char [0],wistd::default_delete<unsigned char [0]>>::reset(&TokenInformation);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x18007cb94  mov     rax, rsp
0x18007cb97  mov     [rax+8], rbx
0x18007cb9b  push    rbp
0x18007cb9c  push    rsi
0x18007cb9d  push    rdi
0x18007cb9e  sub     rsp, 40h
0x18007cba2  xor     esi, esi
0x18007cba4  mov     rdi, rdx
0x18007cba7  mov     [rax+20h], rsi
0x18007cbab  mov     rbp, rcx
0x18007cbae  mov     [rax+18h], esi
0x18007cbb1  lea     rax, [rax+18h]
0x18007cbb5  xor     r9d, r9d; TokenInformationLength
0x18007cbb8  mov     [rsp+58h+ReturnLength], rax; ReturnLength
0x18007cbbd  lea     edx, [rsi+1]; TokenInformationClass
0x18007cbc0  xor     r8d, r8d; TokenInformation
0x18007cbc3  mov     rcx, rdi; TokenHandle
0x18007cbc6  call    cs:__imp_GetTokenInformation
0x18007cbcc  test    eax, eax
0x18007cbce  jnz     short loc_18007CC07
0x18007cbd0  call    cs:__imp_GetLastError
0x18007cbd6  cmp     eax, 7Ah ; 'z'
0x18007cbd9  jz      short loc_18007CC07
0x18007cbdb  test    eax, eax
0x18007cbdd  jg      short loc_18007CBE3
0x18007cbdf  mov     esi, eax
0x18007cbe1  jmp     short loc_18007CBEC
0x18007cbe3  movzx   esi, ax
0x18007cbe6  or      esi, 80070000h
0x18007cbec  test    esi, esi
0x18007cbee  jns     short loc_18007CC07
0x18007cbf0  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18007cbf7  jb      loc_18007CCFE
0x18007cbfd  mov     edx, 50h ; 'P'
0x18007cc02  jmp     loc_18007CCE0
0x18007cc07  mov     edx, [rsp+58h+TokenInformationLength]
0x18007cc0b  lea     rcx, [rsp+58h+var_28]
0x18007cc10  call    ??$make_unique_nothrow@$$BY0A@E@wil@@YA?AV?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@wistd@@@wistd@@_K@Z; wil::make_unique_nothrow<uchar [0]>(unsigned __int64)
0x18007cc15  mov     rdx, rax
0x18007cc18  lea     rcx, [rsp+58h+TokenInformation]
0x18007cc1d  call    ??4?$unique_ptr@$$BY0A@KU?$default_delete@$$BY0A@K@wistd@@@wistd@@QEAAAEAV01@$$QEAV01@@Z; wistd::unique_ptr<ulong [0],wistd::default_delete<ulong [0]>>::operator=(wistd::unique_ptr<ulong [0],wistd::default_delete<ulong [0]>> &&)
0x18007cc22  lea     rcx, [rsp+58h+var_28]
0x18007cc27  call    ?reset@?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@wistd@@@wistd@@QEAAX$$T@Z; wistd::unique_ptr<uchar [0],wistd::default_delete<uchar [0]>>::reset(std::nullptr_t)
0x18007cc2c  mov     rbx, [rsp+58h+TokenInformation]
0x18007cc31  test    rbx, rbx
0x18007cc34  jnz     short loc_18007CC50
0x18007cc36  mov     esi, 8007000Eh
0x18007cc3b  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18007cc42  jb      loc_18007CCFE
0x18007cc48  lea     edx, [rbx+51h]
0x18007cc4b  jmp     loc_18007CCE0
0x18007cc50  mov     r9d, [rsp+58h+TokenInformationLength]; TokenInformationLength
0x18007cc55  lea     rax, [rsp+58h+TokenInformationLength]
0x18007cc5a  mov     r8, rbx; TokenInformation
0x18007cc5d  mov     [rsp+58h+ReturnLength], rax; ReturnLength
0x18007cc62  mov     edx, 1; TokenInformationClass
0x18007cc67  mov     rcx, rdi; TokenHandle
0x18007cc6a  call    cs:__imp_GetTokenInformation
0x18007cc70  test    eax, eax
0x18007cc72  jnz     short loc_18007CC9D
0x18007cc74  call    cs:__imp_GetLastError
0x18007cc7a  mov     esi, eax
0x18007cc7c  test    eax, eax
0x18007cc7e  jle     short loc_18007CC89
0x18007cc80  movzx   esi, ax
0x18007cc83  or      esi, 80070000h
0x18007cc89  test    esi, esi
0x18007cc8b  jns     short loc_18007CC9D
0x18007cc8d  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18007cc94  jb      short loc_18007CCFE
0x18007cc96  mov     edx, 52h ; 'R'
0x18007cc9b  jmp     short loc_18007CCE0
0x18007cc9d  xor     edx, edx
0x18007cc9f  lea     rcx, [rbp+48h]
0x18007cca3  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18007cca8  mov     rcx, [rbx]; Sid
0x18007ccab  lea     rdx, [rbp+48h]; StringSid
0x18007ccaf  call    cs:__imp_ConvertSidToStringSidW
0x18007ccb5  test    eax, eax
0x18007ccb7  jnz     short loc_18007CCFE
0x18007ccb9  call    cs:__imp_GetLastError
0x18007ccbf  mov     esi, eax
0x18007ccc1  test    eax, eax
0x18007ccc3  jle     short loc_18007CCCE
0x18007ccc5  movzx   esi, ax
0x18007ccc8  or      esi, 80070000h
0x18007ccce  test    esi, esi
0x18007ccd0  jns     short loc_18007CCFE
0x18007ccd2  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18007ccd9  jb      short loc_18007CCFE
0x18007ccdb  mov     edx, 53h ; 'S'
0x18007cce0  mov     rcx, cs:WPP_GLOBAL_Control
0x18007cce7  lea     r8, WPP_0624fae52b0938a3be09ac660a5d0b65_Traceguids
0x18007ccee  mov     r9, rbp
0x18007ccf1  mov     dword ptr [rsp+58h+ReturnLength], esi
0x18007ccf5  mov     rcx, [rcx+10h]
0x18007ccf9  call    WPP_SF_qD
0x18007ccfe  lea     rcx, [rsp+58h+TokenInformation]
0x18007cd03  call    ?reset@?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@wistd@@@wistd@@QEAAX$$T@Z; wistd::unique_ptr<uchar [0],wistd::default_delete<uchar [0]>>::reset(std::nullptr_t)
0x18007cd08  mov     rbx, [rsp+58h+arg_0]
0x18007cd0d  mov     eax, esi
0x18007cd0f  add     rsp, 40h
0x18007cd13  pop     rdi
0x18007cd14  pop     rsi
0x18007cd15  pop     rbp
0x18007cd16  retn
```
