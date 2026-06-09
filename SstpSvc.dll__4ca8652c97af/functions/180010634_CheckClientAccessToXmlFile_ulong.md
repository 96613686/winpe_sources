# CheckClientAccessToXmlFile(ulong)

- ea: `0x180010634`
- end: `0x18001098d`
- name: `?CheckClientAccessToXmlFile@@YAHK@Z`
- size: `857`
- prototype: `_BOOL8 __fastcall()`
- caller_count: `2`
- callee_count: `7`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800138c0`
- `0x180014490`

## callees

- `0x180007944`
- `0x18000827c`
- `0x180008360`
- `0x180008850`
- `0x180010634`
- `0x18001bcba`
- `0x18001bcf0`

## import_xrefs

- `msvcrt!??_V@YAXPEAX@Z` at `0x18001093f`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18001094d`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18001093f`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18001094d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010765`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800107a0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010814`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001088b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010765`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800107a0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010814`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001088b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001095e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001095e`
- `RPCRT4!RpcRevertToSelf` at `0x1800108e1`
- `RPCRT4!RpcRevertToSelf` at `0x1800108e1`
- `RPCRT4!RpcImpersonateClient` at `0x1800107ce`
- `RPCRT4!RpcImpersonateClient` at `0x1800107ce`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800107f1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800107f1`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18001080a`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18001080a`
- `api-ms-win-security-base-l1-1-0!AccessCheck` at `0x180010881`
- `api-ms-win-security-base-l1-1-0!AccessCheck` at `0x180010881`
- `api-ms-win-security-base-l1-1-0!GetFileSecurityW` at `0x18001075b`
- `api-ms-win-security-base-l1-1-0!GetFileSecurityW` at `0x180010796`
- `api-ms-win-security-base-l1-1-0!GetFileSecurityW` at `0x18001075b`
- `api-ms-win-security-base-l1-1-0!GetFileSecurityW` at `0x180010796`
- `api-ms-win-security-base-l1-1-0!MapGenericMask` at `0x18001083e`
- `api-ms-win-security-base-l1-1-0!MapGenericMask` at `0x18001083e`

## string_xrefs

- `0x1800106fb`: `CheckClientAccessToXmlFile: GetXmlFilePath failed with error %d`
- `0x1800107b7`: `CheckClientAccessToXmlFile: GetFileSecurity method failed with error %d`
- `0x1800107e5`: `CheckClientAccess: RpcImpersonateClient failed with error %d`
- `0x18001082b`: `CheckClientAccess: OpenThreadToken failed with error %d`
- `0x18001089e`: `CheckClientAccess: AccessCheck failed with error %d`
- `0x1800108ff`: `CheckClientAccess: RpcRevertToSelf failed with error %d`

## pseudocode

```c
_BOOL8 __fastcall CheckClientAccessToXmlFile()
{
  void *v0; // rsi
  unsigned int XmlFilePath; // eax
  WCHAR *v2; // rdi
  DWORD LastError; // eax
  const wchar_t *v4; // rdx
  HANDLE CurrentThread; // rax
  unsigned int v6; // eax
  DWORD nLength; // [rsp+40h] [rbp-878h] BYREF
  DWORD AccessMask; // [rsp+48h] [rbp-870h] BYREF
  BOOL AccessStatus; // [rsp+50h] [rbp-868h] BYREF
  LPCWSTR lpFileName; // [rsp+58h] [rbp-860h] BYREF
  DWORD GrantedAccess; // [rsp+60h] [rbp-858h] BYREF
  DWORD PrivilegeSetLength; // [rsp+64h] [rbp-854h] BYREF
  HANDLE TokenHandle; // [rsp+68h] [rbp-850h] BYREF
  GENERIC_MAPPING GenericMapping; // [rsp+78h] [rbp-840h] BYREF
  _PRIVILEGE_SET PrivilegeSet; // [rsp+88h] [rbp-830h] BYREF
  int v17; // [rsp+A0h] [rbp-818h] BYREF
  _BYTE v18[2044]; // [rsp+A4h] [rbp-814h] BYREF
  std::bad_alloc *v19; // [rsp+8A0h] [rbp-18h] BYREF

  AccessMask = 1179926;
  TokenHandle = (HANDLE)-1LL;
  memset(&PrivilegeSet, 0, sizeof(PrivilegeSet));
  PrivilegeSetLength = 20;
  AccessStatus = 0;
  GenericMapping.GenericRead = 1179785;
  GenericMapping.GenericWrite = 1179926;
  GenericMapping.GenericExecute = 1179808;
  GenericMapping.GenericAll = 2032127;
  GrantedAccess = 0;
  v0 = 0;
  nLength = 0;
  lpFileName = 0;
  v17 = 0;
  memset_0(v18, 0, sizeof(v18));
  XmlFilePath = GetXmlFilePath((unsigned __int16 **)&lpFileName);
  if ( XmlFilePath )
  {
    if ( (byte_18002D803 & 8) != 0 )
    {
      LOWORD(v17) = 0;
      FormatRRASErrorString(&v17, L"CheckClientAccessToXmlFile: GetXmlFilePath failed with error %d", XmlFilePath);
      if ( (byte_18002D803 & 8) != 0 )
        McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasSSTPSvcTraceError, &v17);
    }
    goto LABEL_5;
  }
  v2 = (WCHAR *)lpFileName;
  if ( !GetFileSecurityW(lpFileName, 7u, 0, nLength, &nLength) )
  {
    LastError = GetLastError();
    if ( LastError == 122 )
    {
      if ( __eh34_try(-1, 0) )
      {
        __eh34_scope_strut(0);
        v0 = operator new[](nLength);
      }
      if ( __eh34_catch(0) )
      {
        if ( __eh34_catch_type(0, &std::bad_alloc `RTTI Type Descriptor', &v19) )
        {
          v0 = 0;
          __eh34_try_continuation(0, &std::bad_alloc `RTTI Type Descriptor', &loc_1800107C3);
LABEL_5:
          v2 = (WCHAR *)lpFileName;
          goto LABEL_27;
        }
      }
      if ( GetFileSecurityW(v2, 7u, v0, nLength, &nLength) )
        goto LABEL_14;
      LastError = GetLastError();
    }
    if ( LastError )
    {
      if ( (byte_18002D803 & 8) == 0 )
        goto LABEL_27;
      v4 = L"CheckClientAccessToXmlFile: GetFileSecurity method failed with error %d";
      goto LABEL_25;
    }
  }
LABEL_14:
  LastError = RpcImpersonateClient(0);
  if ( LastError )
  {
    if ( (byte_18002D803 & 8) == 0 )
      goto LABEL_27;
    v4 = L"CheckClientAccess: RpcImpersonateClient failed with error %d";
  }
  else
  {
    CurrentThread = GetCurrentThread();
    if ( OpenThreadToken(CurrentThread, 0xF01FFu, 1, &TokenHandle) || (LastError = GetLastError()) == 0 )
    {
      MapGenericMask(&AccessMask, &GenericMapping);
      if ( AccessCheck(
             v0,
             TokenHandle,
             AccessMask,
             &GenericMapping,
             &PrivilegeSet,
             &PrivilegeSetLength,
             &GrantedAccess,
             &AccessStatus) )
      {
        goto LABEL_27;
      }
      LastError = GetLastError();
      if ( !LastError || (byte_18002D803 & 8) == 0 )
        goto LABEL_27;
      v4 = L"CheckClientAccess: AccessCheck failed with error %d";
    }
    else
    {
      if ( (byte_18002D803 & 8) == 0 )
        goto LABEL_27;
      v4 = L"CheckClientAccess: OpenThreadToken failed with error %d";
    }
  }
LABEL_25:
  LOWORD(v17) = 0;
  FormatRRASErrorString(&v17, v4, LastError);
  if ( (byte_18002D803 & 8) != 0 )
    McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasSSTPSvcTraceError, &v17);
LABEL_27:
  v6 = RpcRevertToSelf();
  if ( v6 )
  {
    if ( (byte_18002D803 & 8) != 0 )
    {
      LOWORD(v17) = 0;
      FormatRRASErrorString(&v17, L"CheckClientAccess: RpcRevertToSelf failed with error %d", v6);
      if ( (byte_18002D803 & 8) != 0 )
        McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasSSTPSvcTraceError, &v17);
    }
  }
  if ( v0 )
    operator delete[](v0);
  if ( v2 )
    operator delete[](v2);
  if ( TokenHandle != (HANDLE)-1LL )
    CloseHandle(TokenHandle);
  return AccessStatus;
}

```

## disassembly

```asm
0x180010634  mov     [rsp+arg_0], rbx
0x180010639  mov     [rsp+arg_8], rsi
0x18001063e  push    rdi
0x18001063f  sub     rsp, 8B0h
0x180010646  mov     rax, cs:__security_cookie
0x18001064d  xor     rax, rsp
0x180010650  mov     [rsp+8B8h+var_10], rax
0x180010658  mov     ecx, 120116h
0x18001065d  mov     [rsp+8B8h+AccessMask], ecx
0x180010661  mov     [rsp+8B8h+TokenHandle], 0FFFFFFFFFFFFFFFFh
0x18001066a  xorps   xmm0, xmm0
0x18001066d  xor     eax, eax
0x18001066f  movups  xmmword ptr [rsp+8B8h+PrivilegeSet.PrivilegeCount], xmm0
0x180010677  mov     [rsp+8B8h+PrivilegeSet.Privilege.Attributes], eax
0x18001067e  mov     [rsp+8B8h+var_854], 14h
0x180010686  xor     ebx, ebx
0x180010688  mov     [rsp+8B8h+var_868], ebx
0x18001068c  mov     [rsp+8B8h+GenericMapping.GenericRead], 120089h
0x180010694  mov     [rsp+8B8h+GenericMapping.GenericWrite], ecx
0x180010698  mov     [rsp+8B8h+GenericMapping.GenericExecute], 1200A0h
0x1800106a3  mov     [rsp+8B8h+GenericMapping.GenericAll], 1F01FFh
0x1800106ae  mov     [rsp+8B8h+var_858], ebx
0x1800106b2  mov     esi, ebx
0x1800106b4  mov     [rsp+8B8h+nLength], ebx
0x1800106b8  mov     [rsp+8B8h+lpFileName], rbx
0x1800106bd  mov     [rsp+8B8h+var_818], ebx
0x1800106c4  xor     edx, edx; Val
0x1800106c6  mov     r8d, 7FCh; Size
0x1800106cc  lea     rcx, [rsp+8B8h+var_814]; void *
0x1800106d4  call    memset_0
0x1800106d9  lea     rcx, [rsp+8B8h+lpFileName]; unsigned __int16 **
0x1800106de  call    ?GetXmlFilePath@@YAKPEAPEAG@Z; GetXmlFilePath(ushort * *)
0x1800106e3  test    eax, eax
0x1800106e5  jz      short loc_18001073D
0x1800106e7  test    cs:byte_18002D803, 8
0x1800106ee  jz      short loc_180010733
0x1800106f0  mov     word ptr [rsp+8B8h+var_818], bx
0x1800106f8  mov     r8d, eax
0x1800106fb  lea     rdx, aCheckclientacc_3; "CheckClientAccessToXmlFile: GetXmlFileP"...
0x180010702  lea     rcx, [rsp+8B8h+var_818]
0x18001070a  call    FormatRRASErrorString
0x18001070f  test    cs:byte_18002D803, 8
0x180010716  jz      short loc_180010733
0x180010718  lea     r8, [rsp+8B8h+var_818]
0x180010720  lea     rdx, RasSSTPSvcTraceError
0x180010727  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18001072e  call    McTemplateU0z_EventWriteTransfer
0x180010733  mov     rdi, [rsp+8B8h+lpFileName]
0x180010738  jmp     loc_1800108E1
0x18001073d  lea     rax, [rsp+8B8h+nLength]
0x180010742  mov     [rsp+8B8h+lpnLengthNeeded], rax; lpnLengthNeeded
0x180010747  mov     r9d, [rsp+8B8h+nLength]; nLength
0x18001074c  xor     r8d, r8d; pSecurityDescriptor
0x18001074f  lea     edx, [r8+7]; RequestedInformation
0x180010753  mov     rdi, [rsp+8B8h+lpFileName]
0x180010758  mov     rcx, rdi; lpFileName
0x18001075b  call    cs:__imp_GetFileSecurityW
0x180010761  test    eax, eax
0x180010763  jnz     short loc_1800107CC
0x180010765  call    cs:__imp_GetLastError
0x18001076b  cmp     eax, 7Ah ; 'z'
0x18001076e  jnz     short loc_1800107A6
0x180010770  mov     ecx, [rsp+8B8h+nLength]; unsigned __int64
0x180010774  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180010779  mov     rsi, rax
0x18001077c  lea     rax, [rsp+8B8h+nLength]
0x180010781  mov     [rsp+8B8h+lpnLengthNeeded], rax; lpnLengthNeeded
0x180010786  mov     r9d, [rsp+8B8h+nLength]; nLength
0x18001078b  mov     r8, rsi; pSecurityDescriptor
0x18001078e  mov     edx, 7; RequestedInformation
0x180010793  mov     rcx, rdi; lpFileName
0x180010796  call    cs:__imp_GetFileSecurityW
0x18001079c  test    eax, eax
0x18001079e  jnz     short loc_1800107CC
0x1800107a0  call    cs:__imp_GetLastError
0x1800107a6  test    eax, eax
0x1800107a8  jz      short loc_1800107CC
0x1800107aa  test    cs:byte_18002D803, 8
0x1800107b1  jz      loc_1800108E1
0x1800107b7  lea     rdx, aCheckclientacc_4; "CheckClientAccessToXmlFile: GetFileSecu"...
0x1800107be  jmp     loc_1800108A5
0x1800107c3  xor     ebx, ebx
0x1800107c5  mov     esi, ebx
0x1800107c7  jmp     loc_180010733
0x1800107cc  xor     ecx, ecx; BindingHandle
0x1800107ce  call    cs:__imp_RpcImpersonateClient
0x1800107d4  test    eax, eax
0x1800107d6  jz      short loc_1800107F1
0x1800107d8  test    cs:byte_18002D803, 8
0x1800107df  jz      loc_1800108E1
0x1800107e5  lea     rdx, aCheckclientacc_2; "CheckClientAccess: RpcImpersonateClient"...
0x1800107ec  jmp     loc_1800108A5
0x1800107f1  call    cs:__imp_GetCurrentThread
0x1800107f7  mov     rcx, rax; ThreadHandle
0x1800107fa  lea     r9, [rsp+8B8h+TokenHandle]; TokenHandle
0x1800107ff  mov     edx, 0F01FFh; DesiredAccess
0x180010804  mov     r8d, 1; OpenAsSelf
0x18001080a  call    cs:__imp_OpenThreadToken
0x180010810  test    eax, eax
0x180010812  jnz     short loc_180010834
0x180010814  call    cs:__imp_GetLastError
0x18001081a  test    eax, eax
0x18001081c  jz      short loc_180010834
0x18001081e  test    cs:byte_18002D803, 8
0x180010825  jz      loc_1800108E1
0x18001082b  lea     rdx, aCheckclientacc_0; "CheckClientAccess: OpenThreadToken fail"...
0x180010832  jmp     short loc_1800108A5
0x180010834  lea     rdx, [rsp+8B8h+GenericMapping]; GenericMapping
0x180010839  lea     rcx, [rsp+8B8h+AccessMask]; AccessMask
0x18001083e  call    cs:__imp_MapGenericMask
0x180010844  lea     rax, [rsp+8B8h+var_868]
0x180010849  mov     [rsp+8B8h+AccessStatus], rax; AccessStatus
0x18001084e  lea     rax, [rsp+8B8h+var_858]
0x180010853  mov     [rsp+8B8h+GrantedAccess], rax; GrantedAccess
0x180010858  lea     rax, [rsp+8B8h+var_854]
0x18001085d  mov     [rsp+8B8h+PrivilegeSetLength], rax; PrivilegeSetLength
0x180010862  lea     rax, [rsp+8B8h+PrivilegeSet]
0x18001086a  mov     [rsp+8B8h+lpnLengthNeeded], rax; PrivilegeSet
0x18001086f  lea     r9, [rsp+8B8h+GenericMapping]; GenericMapping
0x180010874  mov     r8d, [rsp+8B8h+AccessMask]; DesiredAccess
0x180010879  mov     rdx, [rsp+8B8h+TokenHandle]; ClientToken
0x18001087e  mov     rcx, rsi; pSecurityDescriptor
0x180010881  call    cs:__imp_AccessCheck
0x180010887  test    eax, eax
0x180010889  jnz     short loc_1800108E1
0x18001088b  call    cs:__imp_GetLastError
0x180010891  test    eax, eax
0x180010893  jz      short loc_1800108E1
0x180010895  test    cs:byte_18002D803, 8
0x18001089c  jz      short loc_1800108E1
0x18001089e  lea     rdx, aCheckclientacc_1; "CheckClientAccess: AccessCheck failed w"...
0x1800108a5  mov     word ptr [rsp+8B8h+var_818], bx
0x1800108ad  mov     r8d, eax
0x1800108b0  lea     rcx, [rsp+8B8h+var_818]
0x1800108b8  call    FormatRRASErrorString
0x1800108bd  test    cs:byte_18002D803, 8
0x1800108c4  jz      short loc_1800108E1
0x1800108c6  lea     r8, [rsp+8B8h+var_818]
0x1800108ce  lea     rdx, RasSSTPSvcTraceError
0x1800108d5  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x1800108dc  call    McTemplateU0z_EventWriteTransfer
0x1800108e1  call    cs:__imp_RpcRevertToSelf
0x1800108e7  test    eax, eax
0x1800108e9  jz      short loc_180010937
0x1800108eb  test    cs:byte_18002D803, 8
0x1800108f2  jz      short loc_180010937
0x1800108f4  mov     word ptr [rsp+8B8h+var_818], bx
0x1800108fc  mov     r8d, eax
0x1800108ff  lea     rdx, aCheckclientacc; "CheckClientAccess: RpcRevertToSelf fail"...
0x180010906  lea     rcx, [rsp+8B8h+var_818]
0x18001090e  call    FormatRRASErrorString
0x180010913  test    cs:byte_18002D803, 8
0x18001091a  jz      short loc_180010937
0x18001091c  lea     r8, [rsp+8B8h+var_818]
0x180010924  lea     rdx, RasSSTPSvcTraceError
0x18001092b  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180010932  call    McTemplateU0z_EventWriteTransfer
0x180010937  test    rsi, rsi
0x18001093a  jz      short loc_180010945
0x18001093c  mov     rcx, rsi
0x18001093f  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180010945  test    rdi, rdi
0x180010948  jz      short loc_180010953
0x18001094a  mov     rcx, rdi
0x18001094d  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180010953  mov     rcx, [rsp+8B8h+TokenHandle]; hObject
0x180010958  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18001095c  jz      short loc_180010964
0x18001095e  call    cs:__imp_CloseHandle
0x180010964  mov     eax, [rsp+8B8h+var_868]
0x180010968  mov     rcx, [rsp+8B8h+var_10]
0x180010970  xor     rcx, rsp; StackCookie
0x180010973  call    __security_check_cookie
0x180010978  lea     r11, [rsp+8B8h+var_8]
0x180010980  mov     rbx, [r11+10h]
0x180010984  mov     rsi, [r11+18h]
0x180010988  mov     rsp, r11
0x18001098b  pop     rdi
0x18001098c  retn
```
