# Wallet::ServerUtils::GetCallerAppContainerSid(utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> &)

- ea: `0x18001cc50`
- end: `0x18001cdef`
- name: `?GetCallerAppContainerSid@ServerUtils@Wallet@@YAJAEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@Z`
- size: `415`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x180027140`

## callees

- `0x180002e48`
- `0x180013fe4`
- `0x18001b458`
- `0x18001cc50`

## import_xrefs

- `msvcrt!??_V@YAXPEAX@Z` at `0x18001cd3d`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18001cdd9`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18001cd3d`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18001cdd9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001cc8c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001cc8c`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18001cca0`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18001cca0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ccb2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ccfd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ccb2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ccfd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001cdc8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001cdc8`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18001ccf3`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18001cd6c`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18001ccf3`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18001cd6c`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18001cd81`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18001cd81`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001cdb1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001cdb1`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x18001cc7c`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x18001cc7c`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x18001cca8`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x18001cca8`

## pseudocode

```c
__int64 __fastcall Wallet::ServerUtils::GetCallerAppContainerSid(__int64 a1)
{
  PSID *v1; // rbx
  signed int v3; // edi
  HANDLE CurrentThread; // rax
  BOOL v5; // edi
  signed int v6; // eax
  DWORD LastError; // eax
  bool v8; // sf
  void *v10; // [rsp+30h] [rbp-10h] BYREF
  LPVOID TokenInformation; // [rsp+38h] [rbp-8h] BYREF
  DWORD TokenInformationLength; // [rsp+68h] [rbp+28h] BYREF
  void *TokenHandle; // [rsp+70h] [rbp+30h] BYREF
  LPWSTR StringSid; // [rsp+78h] [rbp+38h] BYREF

  v1 = 0;
  StringSid = 0;
  TokenInformation = 0;
  TokenInformationLength = 0;
  TokenHandle = 0;
  v3 = CoImpersonateClient();
  if ( v3 < 0 )
    goto LABEL_18;
  CurrentThread = GetCurrentThread();
  v5 = OpenThreadToken(CurrentThread, 0xCu, 1, &TokenHandle);
  CoRevertToSelf();
  if ( !v5 )
    goto LABEL_3;
  if ( GetTokenInformation(TokenHandle, TokenAppContainerSid, 0, 0, &TokenInformationLength) )
    goto LABEL_13;
  LastError = GetLastError();
  v3 = 0;
  if ( LastError != 122 )
    v3 = LastError;
  v8 = v3 < 0;
  if ( v3 > 0 )
  {
    v3 = (unsigned __int16)v3 | 0x80070000;
    v8 = v3 < 0;
  }
  if ( !v8 )
  {
LABEL_13:
    v10 = operator new[](TokenInformationLength);
    std::unique_ptr<unsigned char [0]>::operator=(&TokenInformation, &v10);
    operator delete[](v10);
    v1 = (PSID *)TokenInformation;
    if ( !TokenInformation )
    {
      v3 = -2147024882;
      goto LABEL_18;
    }
    if ( GetTokenInformation(
           TokenHandle,
           TokenAppContainerSid,
           TokenInformation,
           TokenInformationLength,
           &TokenInformationLength)
      && ConvertSidToStringSidW(*v1, &StringSid) )
    {
      v3 = (unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                              a1,
                              StringSid) == 0
         ? 0x8007000E
         : 0;
      goto LABEL_18;
    }
LABEL_3:
    v6 = GetLastError();
    v3 = v6;
    if ( v6 )
    {
      if ( v6 > 0 )
        v3 = (unsigned __int16)v6 | 0x80070000;
    }
    else
    {
      v3 = -2143748092;
    }
  }
LABEL_18:
  if ( StringSid )
  {
    LocalFree(StringSid);
    StringSid = 0;
  }
  if ( TokenHandle )
  {
    CloseHandle(TokenHandle);
    TokenHandle = 0;
  }
  operator delete[](v1);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x18001cc50  mov     [rsp-18h+arg_0], rbx
0x18001cc55  push    rbp
0x18001cc56  push    rdi
0x18001cc57  push    r14
0x18001cc59  mov     rbp, rsp
0x18001cc5c  sub     rsp, 40h
0x18001cc60  xor     ebx, ebx
0x18001cc62  mov     [rbp+StringSid], 0
0x18001cc6a  mov     [rbp+TokenInformation], rbx
0x18001cc6e  mov     r14, rcx
0x18001cc71  mov     [rbp+TokenInformationLength], ebx
0x18001cc74  mov     [rbp+TokenHandle], 0
0x18001cc7c  call    cs:__imp_CoImpersonateClient
0x18001cc82  mov     edi, eax
0x18001cc84  test    eax, eax
0x18001cc86  js      loc_18001CDA8
0x18001cc8c  call    cs:__imp_GetCurrentThread
0x18001cc92  mov     rcx, rax; ThreadHandle
0x18001cc95  lea     r9, [rbp+TokenHandle]; TokenHandle
0x18001cc99  lea     edx, [rbx+0Ch]; DesiredAccess
0x18001cc9c  lea     r8d, [rbx+1]; OpenAsSelf
0x18001cca0  call    cs:__imp_OpenThreadToken
0x18001cca6  mov     edi, eax
0x18001cca8  call    cs:__imp_CoRevertToSelf
0x18001ccae  test    edi, edi
0x18001ccb0  jnz     short loc_18001CCDC
0x18001ccb2  call    cs:__imp_GetLastError
0x18001ccb8  mov     edi, eax
0x18001ccba  test    eax, eax
0x18001ccbc  jz      short loc_18001CCD2
0x18001ccbe  jle     loc_18001CDA8
0x18001ccc4  movzx   edi, ax
0x18001ccc7  or      edi, 80070000h
0x18001cccd  jmp     loc_18001CDA8
0x18001ccd2  mov     edi, 80390004h
0x18001ccd7  jmp     loc_18001CDA8
0x18001ccdc  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x18001cce0  lea     rax, [rbp+TokenInformationLength]
0x18001cce4  xor     r9d, r9d; TokenInformationLength
0x18001cce7  mov     [rsp+40h+ReturnLength], rax; ReturnLength
0x18001ccec  xor     r8d, r8d; TokenInformation
0x18001ccef  lea     edx, [r9+1Fh]; TokenInformationClass
0x18001ccf3  call    cs:__imp_GetTokenInformation
0x18001ccf9  test    eax, eax
0x18001ccfb  jnz     short loc_18001CD20
0x18001ccfd  call    cs:__imp_GetLastError
0x18001cd03  xor     edi, edi
0x18001cd05  cmp     eax, 7Ah ; 'z'
0x18001cd08  cmovnz  edi, eax
0x18001cd0b  test    edi, edi
0x18001cd0d  jle     short loc_18001CD1A
0x18001cd0f  movzx   edi, di
0x18001cd12  or      edi, 80070000h
0x18001cd18  test    edi, edi
0x18001cd1a  js      loc_18001CDA8
0x18001cd20  mov     ecx, [rbp+TokenInformationLength]; unsigned __int64
0x18001cd23  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18001cd28  lea     rdx, [rbp+var_10]
0x18001cd2c  mov     [rbp+var_10], rax
0x18001cd30  lea     rcx, [rbp+TokenInformation]
0x18001cd34  call    ??4?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@std@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::unique_ptr<uchar [0]>::operator=(std::unique_ptr<uchar [0]> &&)
0x18001cd39  mov     rcx, [rbp+var_10]
0x18001cd3d  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x18001cd43  mov     rbx, [rbp+TokenInformation]
0x18001cd47  test    rbx, rbx
0x18001cd4a  jnz     short loc_18001CD53
0x18001cd4c  mov     edi, 8007000Eh
0x18001cd51  jmp     short loc_18001CDA8
0x18001cd53  mov     r9d, [rbp+TokenInformationLength]; TokenInformationLength
0x18001cd57  lea     rax, [rbp+TokenInformationLength]
0x18001cd5b  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x18001cd5f  mov     r8, rbx; TokenInformation
0x18001cd62  mov     edx, 1Fh; TokenInformationClass
0x18001cd67  mov     [rsp+40h+ReturnLength], rax; ReturnLength
0x18001cd6c  call    cs:__imp_GetTokenInformation
0x18001cd72  test    eax, eax
0x18001cd74  jz      loc_18001CCB2
0x18001cd7a  mov     rcx, [rbx]; Sid
0x18001cd7d  lea     rdx, [rbp+StringSid]; StringSid
0x18001cd81  call    cs:__imp_ConvertSidToStringSidW
0x18001cd87  test    eax, eax
0x18001cd89  jz      loc_18001CCB2
0x18001cd8f  mov     rdx, [rbp+StringSid]
0x18001cd93  mov     rcx, r14
0x18001cd96  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *)
0x18001cd9b  neg     al
0x18001cd9d  mov     edi, 8007000Eh
0x18001cda2  sbb     ecx, ecx
0x18001cda4  not     ecx
0x18001cda6  and     edi, ecx
0x18001cda8  mov     rcx, [rbp+StringSid]; hMem
0x18001cdac  test    rcx, rcx
0x18001cdaf  jz      short loc_18001CDBF
0x18001cdb1  call    cs:__imp_LocalFree
0x18001cdb7  mov     [rbp+StringSid], 0
0x18001cdbf  mov     rcx, [rbp+TokenHandle]; hObject
0x18001cdc3  test    rcx, rcx
0x18001cdc6  jz      short loc_18001CDD6
0x18001cdc8  call    cs:__imp_CloseHandle
0x18001cdce  mov     [rbp+TokenHandle], 0
0x18001cdd6  mov     rcx, rbx
0x18001cdd9  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x18001cddf  mov     rbx, [rsp+40h+arg_0]
0x18001cde4  mov     eax, edi
0x18001cde6  add     rsp, 40h
0x18001cdea  pop     r14
0x18001cdec  pop     rdi
0x18001cded  pop     rbp
0x18001cdee  retn
```
