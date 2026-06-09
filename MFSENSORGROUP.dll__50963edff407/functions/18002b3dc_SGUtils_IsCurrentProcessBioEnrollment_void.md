# SGUtils_IsCurrentProcessBioEnrollment(void)

- ea: `0x18002b3dc`
- end: `0x18002b71b`
- name: `?SGUtils_IsCurrentProcessBioEnrollment@@YA_NXZ`
- size: `831`
- prototype: `bool(void)`
- caller_count: `3`
- callee_count: `13`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180012284`
- `0x18002eb64`
- `0x180057220`

## callees

- `0x18000c348`
- `0x18000f5a0`
- `0x1800133fc`
- `0x180028eb4`
- `0x18002af88`
- `0x18002b3dc`
- `0x18002b724`
- `0x18002b778`
- `0x18002b798`
- `0x180031920`
- `0x18003491c`
- `0x180051a1c`
- `0x180051a9c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b45a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b4bf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b539`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b59e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b45a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b4bf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b539`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b59e`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18002b418`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18002b418`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18002b406`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18002b406`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002b495`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002b495`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002b4ae`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002b562`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002b4ae`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002b562`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18002b587`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18002b587`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18002b43f`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18002b6a4`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18002b43f`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18002b6a4`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18002b6cb`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18002b6cb`

## pseudocode

```c
bool SGUtils_IsCurrentProcessBioEnrollment(void)
{
  HANDLE CurrentProcess; // rax
  void *v1; // rbx
  signed int v2; // eax
  __int64 v3; // r8
  signed int LastError; // eax
  void *v6; // rbx
  signed int v7; // eax
  __int64 v8; // r8
  HLOCAL v9; // rdi
  signed int v10; // eax
  bool v11; // bl
  void **unique; // rax
  PSID *v13; // rbx
  BOOL v14; // eax
  const char *v15; // r9
  _QWORD v16[2]; // [rsp+30h] [rbp-10h] BYREF
  DWORD TokenInformationLength; // [rsp+60h] [rbp+20h] BYREF
  void *TokenHandle; // [rsp+68h] [rbp+28h] BYREF
  HLOCAL hMem; // [rsp+70h] [rbp+30h] BYREF
  LPVOID TokenInformation; // [rsp+78h] [rbp+38h] BYREF

  TokenInformation = 0;
  TokenInformationLength = 0;
  hMem = 0;
  TokenHandle = 0;
  CurrentProcess = GetCurrentProcess();
  if ( !OpenProcessToken(CurrentProcess, 0xEu, &TokenHandle) )
  {
    if ( byte_18008D62D )
    {
      LastError = GetLastError();
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 27),
        156,
        &WPP_cc6378c746ea368f019c0ec88e4d78a0_Traceguids,
        (unsigned int)LastError);
    }
    goto LABEL_7;
  }
  if ( !GetTokenInformation(TokenHandle, TokenAppContainerSid, 0, 0, &TokenInformationLength) )
  {
    if ( byte_18008D62D )
    {
      v1 = TokenHandle;
      v2 = GetLastError();
      if ( v2 > 0 )
        v2 = (unsigned __int16)v2 | 0x80070000;
      WPP_SF_Dq(*((_QWORD *)WPP_GLOBAL_Control + 27), 157, v3, (unsigned int)v2, v1);
    }
LABEL_7:
    if ( TokenHandle )
      CloseHandle(TokenHandle);
    if ( hMem )
      LocalFree(hMem);
    return 0;
  }
  if ( TokenInformationLength == 8 )
  {
    if ( (unsigned __int8)byte_18008D62D >= 8u )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 27), 158, &WPP_cc6378c746ea368f019c0ec88e4d78a0_Traceguids, 8);
LABEL_17:
    wil::details::unique_storage<wil::details::handle_null_only_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_only_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&hMem);
    wistd::unique_ptr<unsigned char [0],wistd::default_delete<unsigned char [0]>>::reset(&TokenInformation);
    return 0;
  }
  unique = (void **)wil::make_unique_nothrow<unsigned char [0]>(v16, TokenInformationLength);
  wistd::unique_ptr<unsigned char [0],wistd::default_delete<unsigned char [0]>>::operator=(&TokenInformation, unique);
  wistd::unique_ptr<unsigned char [0],wistd::default_delete<unsigned char [0]>>::reset(v16);
  v13 = (PSID *)TokenInformation;
  if ( !TokenInformation )
  {
    if ( byte_18008D62D )
      WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 27));
    goto LABEL_17;
  }
  if ( !GetTokenInformation(
          TokenHandle,
          TokenAppContainerSid,
          TokenInformation,
          TokenInformationLength,
          &TokenInformationLength) )
  {
    if ( byte_18008D62D )
    {
      v6 = TokenHandle;
      v7 = GetLastError();
      if ( v7 > 0 )
        v7 = (unsigned __int16)v7 | 0x80070000;
      WPP_SF_Dq(*((_QWORD *)WPP_GLOBAL_Control + 27), 160, v8, (unsigned int)v7, v6);
    }
    goto LABEL_17;
  }
  v9 = hMem;
  if ( hMem )
  {
    wil::last_error_context::last_error_context((wil::last_error_context *)v16);
    LocalFree(v9);
    wil::last_error_context::~last_error_context((wil::last_error_context *)v16);
  }
  hMem = 0;
  if ( ConvertStringSidToSidW(
         L"S-1-15-2-19479607-1015771884-3827151630-3301822711-2267158487-4079414233-1230461222",
         &hMem) )
  {
    v14 = EqualSid(hMem, *v13);
    v11 = v14;
    if ( byte_18008D62D )
    {
      v15 = "is";
      if ( !v14 )
        v15 = "is_not";
      WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 27), 162, &WPP_cc6378c746ea368f019c0ec88e4d78a0_Traceguids, v15);
    }
  }
  else
  {
    if ( byte_18008D62D )
    {
      v10 = GetLastError();
      if ( v10 > 0 )
        v10 = (unsigned __int16)v10 | 0x80070000;
      WPP_SF_dS(
        *((_QWORD *)WPP_GLOBAL_Control + 27),
        161,
        (unsigned int)&WPP_cc6378c746ea368f019c0ec88e4d78a0_Traceguids,
        v10,
        (__int64)L"S-1-15-2-19479607-1015771884-3827151630-3301822711-2267158487-4079414233-1230461222");
    }
    v11 = 0;
  }
  wil::details::unique_storage<wil::details::handle_null_only_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_only_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&hMem);
  wistd::unique_ptr<unsigned char [0],wistd::default_delete<unsigned char [0]>>::reset(&TokenInformation);
  return v11;
}

```

## disassembly

```asm
0x18002b3dc  push    rbp
0x18002b3de  push    rbx
0x18002b3df  push    rdi
0x18002b3e0  mov     rbp, rsp
0x18002b3e3  sub     rsp, 40h
0x18002b3e7  mov     [rbp+TokenInformation], 0
0x18002b3ef  mov     [rbp+TokenInformationLength], 0
0x18002b3f6  mov     [rbp+hMem], 0
0x18002b3fe  mov     [rbp+TokenHandle], 0
0x18002b406  call    cs:__imp_GetCurrentProcess
0x18002b40c  lea     r8, [rbp+TokenHandle]; TokenHandle
0x18002b410  mov     edx, 0Eh; DesiredAccess
0x18002b415  mov     rcx, rax; ProcessHandle
0x18002b418  call    cs:__imp_OpenProcessToken
0x18002b41e  test    eax, eax
0x18002b420  jz      loc_18002B4B6
0x18002b426  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x18002b42a  lea     rax, [rbp+TokenInformationLength]
0x18002b42e  xor     r9d, r9d; TokenInformationLength
0x18002b431  mov     [rsp+40h+ReturnLength], rax; ReturnLength
0x18002b436  xor     r8d, r8d; TokenInformation
0x18002b439  lea     edi, [r9+1Fh]
0x18002b43d  mov     edx, edi; TokenInformationClass
0x18002b43f  call    cs:__imp_GetTokenInformation
0x18002b445  test    eax, eax
0x18002b447  jnz     loc_18002B5FB
0x18002b44d  cmp     cs:byte_18008D62D, 1
0x18002b454  jb      short loc_18002B48C
0x18002b456  mov     rbx, [rbp+TokenHandle]
0x18002b45a  call    cs:__imp_GetLastError
0x18002b460  test    eax, eax
0x18002b462  jle     short loc_18002B46C
0x18002b464  movzx   eax, ax
0x18002b467  or      eax, 80070000h
0x18002b46c  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b473  mov     edx, 9Dh
0x18002b478  mov     r9d, eax
0x18002b47b  mov     [rsp+40h+ReturnLength], rbx
0x18002b480  mov     rcx, [rcx+0D8h]
0x18002b487  call    WPP_SF_Dq
0x18002b48c  mov     rcx, [rbp+TokenHandle]; hObject
0x18002b490  test    rcx, rcx
0x18002b493  jz      short loc_18002B49B
0x18002b495  call    cs:__imp_CloseHandle
0x18002b49b  mov     rcx, [rbp+hMem]; hMem
0x18002b49f  test    rcx, rcx
0x18002b4a2  jnz     short loc_18002B4AE
0x18002b4a4  xor     al, al
0x18002b4a6  add     rsp, 40h
0x18002b4aa  pop     rdi
0x18002b4ab  pop     rbx
0x18002b4ac  pop     rbp
0x18002b4ad  retn
0x18002b4ae  call    cs:__imp_LocalFree
0x18002b4b4  jmp     short loc_18002B4A4
0x18002b4b6  cmp     cs:byte_18008D62D, 1
0x18002b4bd  jb      short loc_18002B48C
0x18002b4bf  call    cs:__imp_GetLastError
0x18002b4c5  test    eax, eax
0x18002b4c7  jle     short loc_18002B4D1
0x18002b4c9  movzx   eax, ax
0x18002b4cc  or      eax, 80070000h
0x18002b4d1  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b4d8  lea     r8, WPP_cc6378c746ea368f019c0ec88e4d78a0_Traceguids
0x18002b4df  mov     edx, 9Ch
0x18002b4e4  mov     r9d, eax
0x18002b4e7  mov     rcx, [rcx+0D8h]
0x18002b4ee  call    WPP_SF_d
0x18002b4f3  jmp     short loc_18002B48C
0x18002b4f5  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b4fc  mov     edx, 0A0h
0x18002b501  mov     r9d, eax
0x18002b504  mov     [rsp+40h+ReturnLength], rbx
0x18002b509  mov     rcx, [rcx+0D8h]
0x18002b510  call    WPP_SF_Dq
0x18002b515  lea     rcx, [rbp+TokenHandle]
0x18002b519  call    ??1?$unique_storage@U?$handle_null_only_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_only_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_only_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18002b51e  lea     rcx, [rbp+hMem]
0x18002b522  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18002b527  lea     rcx, [rbp+TokenInformation]
0x18002b52b  call    ?reset@?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@wistd@@@wistd@@QEAAX$$T@Z; wistd::unique_ptr<uchar [0],wistd::default_delete<uchar [0]>>::reset(std::nullptr_t)
0x18002b530  jmp     loc_18002B4A4
0x18002b535  mov     rbx, [rbp+TokenHandle]
0x18002b539  call    cs:__imp_GetLastError
0x18002b53f  test    eax, eax
0x18002b541  jle     short loc_18002B4F5
0x18002b543  movzx   eax, ax
0x18002b546  or      eax, 80070000h
0x18002b54b  jmp     short loc_18002B4F5
0x18002b54d  mov     rdi, [rbp+hMem]
0x18002b551  test    rdi, rdi
0x18002b554  jz      short loc_18002B571
0x18002b556  lea     rcx, [rbp+var_10]; this
0x18002b55a  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18002b55f  mov     rcx, rdi; hMem
0x18002b562  call    cs:__imp_LocalFree
0x18002b568  lea     rcx, [rbp+var_10]; this
0x18002b56c  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18002b571  lea     rdi, aS1152194796071; "S-1-15-2-19479607-1015771884-3827151630"...
0x18002b578  mov     [rbp+hMem], 0
0x18002b580  mov     rcx, rdi; StringSid
0x18002b583  lea     rdx, [rbp+hMem]; Sid
0x18002b587  call    cs:__imp_ConvertStringSidToSidW
0x18002b58d  test    eax, eax
0x18002b58f  jnz     loc_18002B6C4
0x18002b595  cmp     cs:byte_18008D62D, 1
0x18002b59c  jb      short loc_18002B5D7
0x18002b59e  call    cs:__imp_GetLastError
0x18002b5a4  test    eax, eax
0x18002b5a6  jle     short loc_18002B5B0
0x18002b5a8  movzx   eax, ax
0x18002b5ab  or      eax, 80070000h
0x18002b5b0  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b5b7  lea     r8, WPP_cc6378c746ea368f019c0ec88e4d78a0_Traceguids
0x18002b5be  mov     edx, 0A1h
0x18002b5c3  mov     [rsp+40h+ReturnLength], rdi
0x18002b5c8  mov     r9d, eax
0x18002b5cb  mov     rcx, [rcx+0D8h]
0x18002b5d2  call    WPP_SF_dS
0x18002b5d7  xor     ebx, ebx
0x18002b5d9  lea     rcx, [rbp+TokenHandle]
0x18002b5dd  call    ??1?$unique_storage@U?$handle_null_only_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_only_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_only_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18002b5e2  lea     rcx, [rbp+hMem]
0x18002b5e6  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18002b5eb  lea     rcx, [rbp+TokenInformation]
0x18002b5ef  call    ?reset@?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@wistd@@@wistd@@QEAAX$$T@Z; wistd::unique_ptr<uchar [0],wistd::default_delete<uchar [0]>>::reset(std::nullptr_t)
0x18002b5f4  mov     al, bl
0x18002b5f6  jmp     loc_18002B4A6
0x18002b5fb  mov     r9d, 8
0x18002b601  cmp     [rbp+TokenInformationLength], r9d
0x18002b605  jnz     short loc_18002B638
0x18002b607  cmp     cs:byte_18008D62D, r9b
0x18002b60e  jb      loc_18002B515
0x18002b614  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b61b  lea     r8, WPP_cc6378c746ea368f019c0ec88e4d78a0_Traceguids
0x18002b622  mov     edx, 9Eh
0x18002b627  mov     rcx, [rcx+0D8h]
0x18002b62e  call    WPP_SF_d
0x18002b633  jmp     loc_18002B515
0x18002b638  mov     edx, [rbp+TokenInformationLength]
0x18002b63b  lea     rcx, [rbp+var_10]
0x18002b63f  call    ??$make_unique_nothrow@$$BY0A@E@wil@@YA?AV?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@wistd@@@wistd@@_K@Z; wil::make_unique_nothrow<uchar [0]>(unsigned __int64)
0x18002b644  mov     rdx, rax
0x18002b647  lea     rcx, [rbp+TokenInformation]
0x18002b64b  call    ??4?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@wistd@@@wistd@@QEAAAEAV01@$$QEAV01@@Z; wistd::unique_ptr<uchar [0],wistd::default_delete<uchar [0]>>::operator=(wistd::unique_ptr<uchar [0],wistd::default_delete<uchar [0]>> &&)
0x18002b650  lea     rcx, [rbp+var_10]
0x18002b654  call    ?reset@?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@wistd@@@wistd@@QEAAX$$T@Z; wistd::unique_ptr<uchar [0],wistd::default_delete<uchar [0]>>::reset(std::nullptr_t)
0x18002b659  mov     rbx, [rbp+TokenInformation]
0x18002b65d  test    rbx, rbx
0x18002b660  jnz     short loc_18002B68E
0x18002b662  cmp     cs:byte_18008D62D, 1
0x18002b669  jb      loc_18002B515
0x18002b66f  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b676  mov     eax, [rbp+TokenInformationLength]
0x18002b679  mov     dword ptr [rsp+40h+ReturnLength], eax
0x18002b67d  mov     rcx, [rcx+0D8h]
0x18002b684  call    WPP_SF_Dd
0x18002b689  jmp     loc_18002B515
0x18002b68e  mov     r9d, [rbp+TokenInformationLength]; TokenInformationLength
0x18002b692  lea     rax, [rbp+TokenInformationLength]
0x18002b696  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x18002b69a  mov     r8, rbx; TokenInformation
0x18002b69d  mov     edx, edi; TokenInformationClass
0x18002b69f  mov     [rsp+40h+ReturnLength], rax; ReturnLength
0x18002b6a4  call    cs:__imp_GetTokenInformation
0x18002b6aa  test    eax, eax
0x18002b6ac  jnz     loc_18002B54D
0x18002b6b2  cmp     cs:byte_18008D62D, 1
0x18002b6b9  jb      loc_18002B515
0x18002b6bf  jmp     loc_18002B535
0x18002b6c4  mov     rdx, [rbx]; pSid2
0x18002b6c7  mov     rcx, [rbp+hMem]; pSid1
0x18002b6cb  call    cs:__imp_EqualSid
0x18002b6d1  test    eax, eax
0x18002b6d3  setnz   bl
0x18002b6d6  cmp     cs:byte_18008D62D, 1
0x18002b6dd  jb      loc_18002B5D9
0x18002b6e3  test    eax, eax
0x18002b6e5  lea     rcx, aIsNot; "is_not"
0x18002b6ec  lea     r9, aIs; "is"
0x18002b6f3  mov     edx, 0A2h
0x18002b6f8  cmovz   r9, rcx
0x18002b6fc  lea     r8, WPP_cc6378c746ea368f019c0ec88e4d78a0_Traceguids
0x18002b703  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b70a  mov     rcx, [rcx+0D8h]
0x18002b711  call    WPP_SF_s
0x18002b716  jmp     loc_18002B5D9
```
