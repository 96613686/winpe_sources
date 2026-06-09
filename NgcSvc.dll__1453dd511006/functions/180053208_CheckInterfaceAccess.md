# CheckInterfaceAccess

- ea: `0x180053208`
- end: `0x18005339c`
- name: `CheckInterfaceAccess`
- size: `404`
- prototype: `__int64 __fastcall(HANDLE ClientToken)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x1800531ac`

## callees

- `0x180007964`
- `0x18002c9d8`
- `0x180053208`
- `0x1800533a4`
- `0x18005cee0`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!MapGenericMask` at `0x1800532cc`
- `api-ms-win-security-base-l1-1-0!MapGenericMask` at `0x1800532cc`
- `api-ms-win-security-base-l1-1-0!AccessCheck` at `0x180053326`
- `api-ms-win-security-base-l1-1-0!AccessCheck` at `0x180053326`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005329d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180053375`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005329d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180053375`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180053262`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180053262`

## string_xrefs

- `0x18005327b`: `onecore\ds\security\devicecredential\service\util\dcautil.cpp`
- `0x180053334`: `onecore\ds\security\devicecredential\service\util\dcautil.cpp`

## pseudocode

```c
__int64 __fastcall CheckInterfaceAccess(HANDLE ClientToken, __int64 a2, bool *a3)
{
  BOOL v5; // ebx
  const char *v6; // r9
  unsigned int LastError; // ebx
  HLOCAL v8; // rcx
  const char *v10; // r9
  int v11; // eax
  HLOCAL v12; // rcx
  HLOCAL hMem; // [rsp+40h] [rbp-19h] BYREF
  DWORD AccessMask; // [rsp+48h] [rbp-11h] BYREF
  WINBOOL AccessStatus; // [rsp+4Ch] [rbp-Dh] BYREF
  DWORD GrantedAccess; // [rsp+50h] [rbp-9h] BYREF
  DWORD PrivilegeSetLength; // [rsp+54h] [rbp-5h] BYREF
  HLOCAL *p_hMem; // [rsp+58h] [rbp-1h] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+60h] [rbp+7h] BYREF
  char v20; // [rsp+68h] [rbp+Fh]
  _GENERIC_MAPPING GenericMapping; // [rsp+70h] [rbp+17h] BYREF
  struct _PRIVILEGE_SET PrivilegeSet; // [rsp+80h] [rbp+27h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+5Fh]

  *a3 = 0;
  hMem = 0;
  SecurityDescriptor = 0;
  v20 = 1;
  p_hMem = &hMem;
  v5 = ConvertStringSecurityDescriptorToSecurityDescriptorW(
         L"O:SYG:SYD:(A;;RC;;;SY)(A;;RC;;;S-1-5-80-2381253463-2694003897-3435975801-3559003598-683041300)",
         1u,
         &SecurityDescriptor,
         0);
  wil::details::out_param_t<wistd::unique_ptr<unsigned char,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<unsigned char,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>((__int64)&p_hMem);
  if ( !v5 )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x60,
                  (unsigned int)"onecore\\ds\\security\\devicecredential\\service\\util\\dcautil.cpp",
                  v6);
LABEL_3:
    v8 = hMem;
    hMem = 0;
    if ( v8 )
      LocalFree(v8);
    return LastError;
  }
  AccessMask = 0x80000000;
  *(_QWORD *)&GenericMapping.GenericRead = 0x20000;
  GenericMapping.GenericAll = 0x20000;
  GenericMapping.GenericExecute = 0;
  MapGenericMask(&AccessMask, &GenericMapping);
  AccessStatus = 0;
  GrantedAccess = 0;
  memset(&PrivilegeSet, 0, sizeof(PrivilegeSet));
  PrivilegeSetLength = 20;
  if ( !AccessCheck(
          hMem,
          ClientToken,
          AccessMask,
          &GenericMapping,
          &PrivilegeSet,
          &PrivilegeSetLength,
          &GrantedAccess,
          &AccessStatus) )
  {
    v11 = wil::details::in1diag3::Log_GetLastError(
            retaddr,
            (void *)0x73,
            (unsigned int)"onecore\\ds\\security\\devicecredential\\service\\util\\dcautil.cpp",
            v10);
    LastError = v11;
    if ( v11 > 0 )
      LastError = (unsigned __int16)v11 | 0x80070000;
    goto LABEL_3;
  }
  v12 = hMem;
  hMem = 0;
  *a3 = AccessStatus != 0;
  if ( v12 )
    LocalFree(v12);
  return 0;
}

```

## disassembly

```asm
0x180053208  mov     [rsp-8+arg_8], rbx
0x18005320d  push    rbp
0x18005320e  push    rsi
0x18005320f  push    rdi
0x180053210  lea     rbp, [rsp-47h]
0x180053215  sub     rsp, 0A0h
0x18005321c  mov     rax, cs:__security_cookie
0x180053223  xor     rax, rsp
0x180053226  mov     [rbp+57h+var_18], rax
0x18005322a  xor     r9d, r9d; SecurityDescriptorSize
0x18005322d  mov     byte ptr [r8], 0
0x180053231  mov     rdi, r8
0x180053234  mov     [rbp+57h+hMem], 0
0x18005323c  mov     rsi, rcx
0x18005323f  mov     [rbp+57h+SecurityDescriptor], 0
0x180053247  lea     rax, [rbp+57h+hMem]
0x18005324b  mov     [rbp+57h+var_48], 1
0x18005324f  lea     edx, [r9+1]; StringSDRevision
0x180053253  mov     [rbp+57h+var_58], rax
0x180053257  lea     r8, [rbp+57h+SecurityDescriptor]; SecurityDescriptor
0x18005325b  lea     rcx, StringSecurityDescriptor; "O:SYG:SYD:(A;;RC;;;SY)(A;;RC;;;S-1-5-80"...
0x180053262  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x180053268  lea     rcx, [rbp+57h+var_58]
0x18005326c  mov     ebx, eax
0x18005326e  call    ??1?$out_param_t@V?$unique_ptr@EU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<uchar,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<uchar,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>(void)
0x180053273  test    ebx, ebx
0x180053275  jnz     short loc_1800532AA
0x180053277  mov     rcx, [rbp+5Fh]; this
0x18005327b  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\devicecredential"...
0x180053282  lea     edx, [rbx+60h]; void *
0x180053285  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18005328a  mov     ebx, eax
0x18005328c  mov     rcx, [rbp+57h+hMem]; hMem
0x180053290  mov     [rbp+57h+hMem], 0
0x180053298  test    rcx, rcx
0x18005329b  jz      short loc_1800532A3
0x18005329d  call    cs:__imp_LocalFree
0x1800532a3  mov     eax, ebx
0x1800532a5  jmp     loc_18005337D
0x1800532aa  mov     eax, 20000h
0x1800532af  mov     [rbp+57h+AccessMask], 80000000h
0x1800532b6  lea     rdx, [rbp+57h+GenericMapping]; GenericMapping
0x1800532ba  mov     qword ptr [rbp+57h+GenericMapping.GenericRead], rax
0x1800532be  lea     rcx, [rbp+57h+AccessMask]; AccessMask
0x1800532c2  mov     [rbp+57h+GenericMapping.GenericAll], eax
0x1800532c5  mov     [rbp+57h+GenericMapping.GenericExecute], 0
0x1800532cc  call    cs:__imp_MapGenericMask
0x1800532d2  mov     r8d, [rbp+57h+AccessMask]; DesiredAccess
0x1800532d6  lea     r9, [rbp+57h+GenericMapping]; GenericMapping
0x1800532da  mov     rcx, [rbp+57h+hMem]; pSecurityDescriptor
0x1800532de  xor     eax, eax
0x1800532e0  mov     [rbp+57h+var_30.Privilege.Attributes], eax
0x1800532e3  xorps   xmm0, xmm0
0x1800532e6  lea     rax, [rbp+57h+var_64]
0x1800532ea  mov     [rbp+57h+var_64], 0
0x1800532f1  mov     [rsp+0B0h+AccessStatus], rax; AccessStatus
0x1800532f6  mov     rdx, rsi; ClientToken
0x1800532f9  lea     rax, [rbp+57h+var_60]
0x1800532fd  mov     [rbp+57h+var_60], 0
0x180053304  mov     [rsp+0B0h+GrantedAccess], rax; GrantedAccess
0x180053309  lea     rax, [rbp+57h+var_5C]
0x18005330d  mov     [rsp+0B0h+PrivilegeSetLength], rax; PrivilegeSetLength
0x180053312  lea     rax, [rbp+57h+var_30]
0x180053316  mov     [rsp+0B0h+PrivilegeSet], rax; PrivilegeSet
0x18005331b  movups  xmmword ptr [rbp+57h+var_30.PrivilegeCount], xmm0
0x18005331f  mov     [rbp+57h+var_5C], 14h
0x180053326  call    cs:__imp_AccessCheck
0x18005332c  test    eax, eax
0x18005332e  jnz     short loc_18005335B
0x180053330  mov     rcx, [rbp+5Fh]; this
0x180053334  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\devicecredential"...
0x18005333b  lea     edx, [rax+73h]; void *
0x18005333e  call    ?Log_GetLastError@in1diag3@details@wil@@YAKPEAXIPEBD@Z; wil::details::in1diag3::Log_GetLastError(void *,uint,char const *)
0x180053343  mov     ebx, eax
0x180053345  test    eax, eax
0x180053347  jle     loc_18005328C
0x18005334d  movzx   ebx, ax
0x180053350  or      ebx, 80070000h
0x180053356  jmp     loc_18005328C
0x18005335b  cmp     [rbp+57h+var_64], 0
0x18005335f  mov     rcx, [rbp+57h+hMem]; hMem
0x180053363  setnz   al
0x180053366  mov     [rbp+57h+hMem], 0
0x18005336e  mov     [rdi], al
0x180053370  test    rcx, rcx
0x180053373  jz      short loc_18005337B
0x180053375  call    cs:__imp_LocalFree
0x18005337b  xor     eax, eax
0x18005337d  mov     rcx, [rbp+57h+var_18]
0x180053381  xor     rcx, rsp; StackCookie
0x180053384  call    __security_check_cookie
0x180053389  mov     rbx, [rsp+0B0h+arg_8]
0x180053391  add     rsp, 0A0h
0x180053398  pop     rdi
0x180053399  pop     rsi
0x18005339a  pop     rbp
0x18005339b  retn
```
