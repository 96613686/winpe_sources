# SystemSettings::WorkplaceHandlers::GetUserSidFromToken

- ea: `0x1801acd30`
- end: `0x1801acf0b`
- name: `SystemSettings::WorkplaceHandlers::GetUserSidFromToken`
- size: `475`
- prototype: `__int64 __fastcall(HANDLE TokenHandle)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1801ac080`

## callees

- `0x180019a20`
- `0x18007f7bc`
- `0x18013a4b0`
- `0x1801aa828`
- `0x1801acd30`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801acd85`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801acd96`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801ace2a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801acebe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801acd85`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801acd96`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801ace2a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801acebe`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1801acdb9`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1801ace63`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1801acdb9`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1801ace63`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x1801aceae`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x1801aceae`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1801ace51`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1801ace51`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1801acd69`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1801ace1a`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1801acd69`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1801ace1a`

## pseudocode

```c
__int64 __fastcall SystemSettings::WorkplaceHandlers::GetUserSidFromToken(HANDLE TokenHandle, _QWORD *a2)
{
  unsigned int v4; // ebx
  __int64 v5; // rdx
  signed int LastError; // eax
  PSID *v7; // rdi
  PSID *v8; // rcx
  signed int v9; // eax
  DWORD LengthSid; // esi
  HLOCAL v11; // rax
  PSID v12; // rbx
  signed int v13; // eax
  int ReturnLength; // [rsp+20h] [rbp-28h]
  int ReturnLengtha; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  SIZE_T uBytes; // [rsp+60h] [rbp+18h] BYREF
  PSID pDestinationSid; // [rsp+68h] [rbp+20h] BYREF

  LODWORD(uBytes) = 0;
  pDestinationSid = 0;
  if ( GetTokenInformation(TokenHandle, TokenUser, 0, 0, (PDWORD)&uBytes) )
  {
    v4 = -2147418113;
    v5 = 129;
LABEL_8:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v5,
      (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\workplace\\src\\corpdevicemanagement.cpp",
      (const char *)v4,
      ReturnLength);
LABEL_9:
    wil::details::unique_storage<wil::details::resource_policy<_EXPLICIT_ACCESS_W *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_EXPLICIT_ACCESS_W *,_EXPLICIT_ACCESS_W *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_EXPLICIT_ACCESS_W *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_EXPLICIT_ACCESS_W *,_EXPLICIT_ACCESS_W *,0,std::nullptr_t>>(&pDestinationSid);
    v8 = 0;
    goto LABEL_21;
  }
  if ( GetLastError() != 122 )
  {
    LastError = GetLastError();
    v4 = LastError;
    if ( LastError > 0 )
      v4 = (unsigned __int16)LastError | 0x80070000;
    goto LABEL_9;
  }
  v7 = (PSID *)LocalAlloc(0, (unsigned int)uBytes);
  CTContainer_PolicyLocalMem::DestroyMem(0);
  if ( !v7 )
  {
    v4 = -2147024882;
    v5 = 137;
    goto LABEL_8;
  }
  if ( GetTokenInformation(TokenHandle, TokenUser, v7, uBytes, (PDWORD)&uBytes) )
  {
    LengthSid = GetLengthSid(*v7);
    v11 = LocalAlloc(0, LengthSid);
    wil::details::unique_storage<wil::details::resource_policy<_ACL *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_ACL *,_ACL *,0,std::nullptr_t>>::reset(
      &pDestinationSid,
      v11);
    v12 = pDestinationSid;
    if ( pDestinationSid )
    {
      if ( CopySid(LengthSid, pDestinationSid, *v7) )
      {
        *a2 = v12;
        v4 = 0;
        pDestinationSid = 0;
      }
      else
      {
        v13 = GetLastError();
        if ( v13 > 0 )
          v13 = (unsigned __int16)v13 | 0x80070000;
        v4 = v13;
      }
    }
    else
    {
      v4 = -2147024882;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x92,
        (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\workplace\\src\\corpdevicemanagement.cpp",
        (const char *)0x8007000ELL,
        ReturnLengtha);
    }
  }
  else
  {
    v9 = GetLastError();
    v4 = v9;
    if ( v9 > 0 )
      v4 = (unsigned __int16)v9 | 0x80070000;
  }
  wil::details::unique_storage<wil::details::resource_policy<_EXPLICIT_ACCESS_W *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_EXPLICIT_ACCESS_W *,_EXPLICIT_ACCESS_W *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_EXPLICIT_ACCESS_W *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_EXPLICIT_ACCESS_W *,_EXPLICIT_ACCESS_W *,0,std::nullptr_t>>(&pDestinationSid);
  v8 = v7;
LABEL_21:
  CTContainer_PolicyLocalMem::DestroyMem(v8);
  return v4;
}

```

## disassembly

```asm
0x1801acd30  mov     rax, rsp
0x1801acd33  mov     [rax+8], rbx
0x1801acd37  push    rsi
0x1801acd38  push    rdi
0x1801acd39  push    r14
0x1801acd3b  sub     rsp, 30h
0x1801acd3f  xor     r9d, r9d; TokenInformationLength
0x1801acd42  mov     dword ptr [rax+18h], 0
0x1801acd49  mov     qword ptr [rax+20h], 0
0x1801acd51  lea     rax, [rax+18h]
0x1801acd55  mov     r14, rdx
0x1801acd58  mov     qword ptr [rsp+48h+ReturnLength], rax; int
0x1801acd5d  xor     r8d, r8d; TokenInformation
0x1801acd60  mov     rbx, rcx
0x1801acd63  lea     esi, [r9+1]
0x1801acd67  mov     edx, esi; TokenInformationClass
0x1801acd69  call    cs:__imp_GetTokenInformation
0x1801acd70  nop     dword ptr [rax+rax+00h]
0x1801acd75  test    eax, eax
0x1801acd77  jz      short loc_1801ACD85
0x1801acd79  mov     ebx, 8000FFFFh
0x1801acd7e  mov     edx, 81h
0x1801acd83  jmp     short loc_1801ACDDE
0x1801acd85  call    cs:__imp_GetLastError
0x1801acd8c  nop     dword ptr [rax+rax+00h]
0x1801acd91  cmp     eax, 7Ah ; 'z'
0x1801acd94  jz      short loc_1801ACDB3
0x1801acd96  call    cs:__imp_GetLastError
0x1801acd9d  nop     dword ptr [rax+rax+00h]
0x1801acda2  mov     ebx, eax
0x1801acda4  test    eax, eax
0x1801acda6  jle     short loc_1801ACDF2
0x1801acda8  movzx   ebx, ax
0x1801acdab  or      ebx, 80070000h
0x1801acdb1  jmp     short loc_1801ACDF2
0x1801acdb3  mov     edx, dword ptr [rsp+48h+uBytes]; uBytes
0x1801acdb7  xor     ecx, ecx; uFlags
0x1801acdb9  call    cs:__imp_LocalAlloc
0x1801acdc0  nop     dword ptr [rax+rax+00h]
0x1801acdc5  xor     ecx, ecx; void *
0x1801acdc7  mov     rdi, rax
0x1801acdca  call    ?DestroyMem@CTContainer_PolicyLocalMem@@SAHPEAX@Z; CTContainer_PolicyLocalMem::DestroyMem(void *)
0x1801acdcf  test    rdi, rdi
0x1801acdd2  jnz     short loc_1801ACE03
0x1801acdd4  mov     ebx, 8007000Eh
0x1801acdd9  mov     edx, 89h; void *
0x1801acdde  mov     rcx, [rsp+48h]; this
0x1801acde3  lea     r8, aShellSystemset_62; "shell\\systemsettingsthreshold\\handler"...
0x1801acdea  mov     r9d, ebx; char *
0x1801acded  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801acdf2  lea     rcx, [rsp+48h+pDestinationSid]
0x1801acdf7  call    ??1?$unique_storage@U?$resource_policy@PEAU_EXPLICIT_ACCESS_W@@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_EXPLICIT_ACCESS_W *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_EXPLICIT_ACCESS_W *,_EXPLICIT_ACCESS_W *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_EXPLICIT_ACCESS_W *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_EXPLICIT_ACCESS_W *,_EXPLICIT_ACCESS_W *,0,std::nullptr_t>>(void)
0x1801acdfc  xor     ecx, ecx
0x1801acdfe  jmp     loc_1801ACEF5
0x1801ace03  mov     r9d, dword ptr [rsp+48h+uBytes]; TokenInformationLength
0x1801ace08  lea     rax, [rsp+48h+uBytes]
0x1801ace0d  mov     r8, rdi; TokenInformation
0x1801ace10  mov     qword ptr [rsp+48h+ReturnLength], rax; int
0x1801ace15  mov     edx, esi; TokenInformationClass
0x1801ace17  mov     rcx, rbx; TokenHandle
0x1801ace1a  call    cs:__imp_GetTokenInformation
0x1801ace21  nop     dword ptr [rax+rax+00h]
0x1801ace26  test    eax, eax
0x1801ace28  jnz     short loc_1801ACE4E
0x1801ace2a  call    cs:__imp_GetLastError
0x1801ace31  nop     dword ptr [rax+rax+00h]
0x1801ace36  mov     ebx, eax
0x1801ace38  test    eax, eax
0x1801ace3a  jle     loc_1801ACEE8
0x1801ace40  movzx   ebx, ax
0x1801ace43  or      ebx, 80070000h
0x1801ace49  jmp     loc_1801ACEE8
0x1801ace4e  mov     rcx, [rdi]; pSid
0x1801ace51  call    cs:__imp_GetLengthSid
0x1801ace58  nop     dword ptr [rax+rax+00h]
0x1801ace5d  mov     edx, eax; uBytes
0x1801ace5f  xor     ecx, ecx; uFlags
0x1801ace61  mov     esi, eax
0x1801ace63  call    cs:__imp_LocalAlloc
0x1801ace6a  nop     dword ptr [rax+rax+00h]
0x1801ace6f  mov     rdx, rax
0x1801ace72  lea     rcx, [rsp+48h+pDestinationSid]
0x1801ace77  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_ACL@@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_ACL@@@Z; wil::details::unique_storage<wil::details::resource_policy<_ACL *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_ACL *,_ACL *,0,std::nullptr_t>>::reset(_ACL *)
0x1801ace7c  mov     rbx, [rsp+48h+pDestinationSid]
0x1801ace81  test    rbx, rbx
0x1801ace84  jnz     short loc_1801ACEA6
0x1801ace86  mov     rcx, [rsp+48h]; this
0x1801ace8b  lea     r8, aShellSystemset_62; "shell\\systemsettingsthreshold\\handler"...
0x1801ace92  mov     ebx, 8007000Eh
0x1801ace97  mov     edx, 92h; void *
0x1801ace9c  mov     r9d, ebx; char *
0x1801ace9f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801acea4  jmp     short loc_1801ACEE8
0x1801acea6  mov     r8, [rdi]; pSourceSid
0x1801acea9  mov     rdx, rbx; pDestinationSid
0x1801aceac  mov     ecx, esi; nDestinationSidLength
0x1801aceae  call    cs:__imp_CopySid
0x1801aceb5  nop     dword ptr [rax+rax+00h]
0x1801aceba  test    eax, eax
0x1801acebc  jnz     short loc_1801ACEDA
0x1801acebe  call    cs:__imp_GetLastError
0x1801acec5  nop     dword ptr [rax+rax+00h]
0x1801aceca  test    eax, eax
0x1801acecc  jle     short loc_1801ACED6
0x1801acece  movzx   eax, ax
0x1801aced1  or      eax, 80070000h
0x1801aced6  mov     ebx, eax
0x1801aced8  jmp     short loc_1801ACEE8
0x1801aceda  mov     [r14], rbx
0x1801acedd  xor     ebx, ebx
0x1801acedf  mov     [rsp+48h+pDestinationSid], 0
0x1801acee8  lea     rcx, [rsp+48h+pDestinationSid]
0x1801aceed  call    ??1?$unique_storage@U?$resource_policy@PEAU_EXPLICIT_ACCESS_W@@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_EXPLICIT_ACCESS_W *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_EXPLICIT_ACCESS_W *,_EXPLICIT_ACCESS_W *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_EXPLICIT_ACCESS_W *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_EXPLICIT_ACCESS_W *,_EXPLICIT_ACCESS_W *,0,std::nullptr_t>>(void)
0x1801acef2  mov     rcx, rdi; void *
0x1801acef5  call    ?DestroyMem@CTContainer_PolicyLocalMem@@SAHPEAX@Z; CTContainer_PolicyLocalMem::DestroyMem(void *)
0x1801acefa  mov     eax, ebx
0x1801acefc  mov     rbx, [rsp+48h+arg_0]
0x1801acf01  add     rsp, 30h
0x1801acf05  pop     r14
0x1801acf07  pop     rdi
0x1801acf08  pop     rsi
0x1801acf09  retn
```
