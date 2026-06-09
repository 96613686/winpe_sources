# UserOOBEController::s_GetDefaultAccountSid(ushort * *)

- ea: `0x18002849c`
- end: `0x18002867b`
- name: `?s_GetDefaultAccountSid@UserOOBEController@@CAJPEAPEAG@Z`
- size: `479`
- prototype: `__int64 __fastcall(unsigned __int16 **)`
- caller_count: `3`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180028684`
- `0x180029260`
- `0x18002abbc`

## callees

- `0x1800032b0`
- `0x1800054ac`
- `0x180005768`
- `0x180007114`
- `0x180007134`
- `0x18000a5e8`
- `0x18001e7b4`
- `0x18002849c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18002850a`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18002850a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800285f9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800285f9`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18002861b`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18002861b`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountNameW` at `0x18002859d`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountNameW` at `0x18002859d`

## string_xrefs

- `0x180028534`: `shell\oobe\user\dll\useroobecontroller.cpp`
- `0x1800285ca`: `shell\oobe\user\dll\useroobecontroller.cpp`
- `0x18002862c`: `shell\oobe\user\dll\useroobecontroller.cpp`

## pseudocode

```c
__int64 __fastcall UserOOBEController::s_GetDefaultAccountSid(HLOCAL *a1)
{
  int ValueW; // ebx
  bool v3; // sf
  int Error; // ebx
  unsigned int LastError; // edi
  const char *v7; // r9
  int pdwType; // [rsp+20h] [rbp-E0h]
  int pdwTypea; // [rsp+20h] [rbp-E0h]
  HLOCAL hMem; // [rsp+40h] [rbp-C0h] BYREF
  DWORD pcbData; // [rsp+48h] [rbp-B8h] BYREF
  enum _SID_NAME_USE peUse; // [rsp+50h] [rbp-B0h] BYREF
  DWORD cchReferencedDomainName; // [rsp+54h] [rbp-ACh] BYREF
  DWORD cbSid; // [rsp+58h] [rbp-A8h] BYREF
  WCHAR ReferencedDomainName[16]; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE Sid[80]; // [rsp+80h] [rbp-80h] BYREF
  WCHAR AccountName[264]; // [rsp+D0h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+318h] [rbp+218h]

  *a1 = 0;
  pcbData = 514;
  ValueW = RegGetValueW(
             HKEY_LOCAL_MACHINE,
             L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\OOBE",
             L"DefaultAccountSAMName",
             2u,
             0,
             AccountName,
             &pcbData);
  if ( ValueW )
  {
    AccountName[0] = 0;
    v3 = ValueW < 0;
    if ( ValueW <= 0 )
      goto LABEL_5;
    ValueW = (unsigned __int16)ValueW | 0x80070000;
  }
  v3 = ValueW < 0;
LABEL_5:
  if ( v3 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x31B,
      (unsigned int)"shell\\oobe\\user\\dll\\useroobecontroller.cpp",
      (const char *)(unsigned int)ValueW,
      pdwType);
    return (unsigned int)ValueW;
  }
  cbSid = 68;
  cchReferencedDomainName = 16;
  peUse = 0;
  hMem = 0;
  if ( LookupAccountNameW(0, AccountName, Sid, &cbSid, ReferencedDomainName, &cchReferencedDomainName, &peUse) )
  {
    Error = 0;
    goto LABEL_10;
  }
  LastError = -2147023564;
  Error = ResultFromKnownLastError();
  if ( Error != -2147023564 )
  {
LABEL_10:
    if ( Error >= 0 )
    {
      hMem = 0;
      if ( ConvertSidToStringSidW(Sid, (LPWSTR *)&hMem) )
      {
        LastError = 0;
        *a1 = hMem;
        hMem = 0;
      }
      else
      {
        LastError = wil::details::in1diag3::Return_GetLastError(
                      retaddr,
                      (void *)0x327,
                      (unsigned int)"shell\\oobe\\user\\dll\\useroobecontroller.cpp",
                      v7);
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x326,
        (unsigned int)"shell\\oobe\\user\\dll\\useroobecontroller.cpp",
        (const char *)(unsigned int)Error,
        pdwTypea);
      LastError = Error;
    }
  }
  wil::details::unique_storage<wil::details::resource_policy<_TOKEN_GROUPS *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_TOKEN_GROUPS *,_TOKEN_GROUPS *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_TOKEN_GROUPS *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_TOKEN_GROUPS *,_TOKEN_GROUPS *,0,std::nullptr_t>>(&hMem);
  return LastError;
}

```

## disassembly

```asm
0x18002849c  push    rbp
0x18002849e  push    rbx
0x18002849f  push    rsi
0x1800284a0  push    rdi
0x1800284a1  lea     rbp, [rsp-1F8h]
0x1800284a9  sub     rsp, 2F8h
0x1800284b0  mov     rax, cs:__security_cookie
0x1800284b7  xor     rax, rsp
0x1800284ba  mov     [rbp+210h+var_30], rax
0x1800284c1  lea     rax, [rsp+310h+var_2C8]
0x1800284c6  mov     qword ptr [rcx], 0
0x1800284cd  mov     [rsp+310h+pcbData], rax; pcbData
0x1800284d2  lea     r8, aDefaultaccount_0; "DefaultAccountSAMName"
0x1800284d9  lea     rax, [rbp+210h+AccountName]
0x1800284dd  mov     [rsp+310h+var_2C8], 202h
0x1800284e5  mov     rsi, rcx
0x1800284e8  mov     [rsp+310h+pvData], rax; pvData
0x1800284ed  mov     r9d, 2; dwFlags
0x1800284f3  mov     [rsp+310h+pdwType], 0; int
0x1800284fc  lea     rdx, aSoftwareMicros_1; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x180028503  mov     rcx, 0FFFFFFFF80000002h; hkey
0x18002850a  call    cs:__imp_RegGetValueW
0x180028510  mov     ebx, eax
0x180028512  test    eax, eax
0x180028514  jz      short loc_180028529
0x180028516  xor     eax, eax
0x180028518  mov     [rbp+210h+AccountName], ax
0x18002851c  test    ebx, ebx
0x18002851e  jle     short loc_18002852B
0x180028520  movzx   ebx, bx
0x180028523  or      ebx, 80070000h
0x180028529  test    ebx, ebx
0x18002852b  jns     short loc_18002854F
0x18002852d  mov     rcx, [rbp+218h]; this
0x180028534  lea     r8, aShellOobeUserD_0; "shell\\oobe\\user\\dll\\useroobecontrol"...
0x18002853b  mov     r9d, ebx; char *
0x18002853e  mov     edx, 31Bh; void *
0x180028543  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180028548  mov     eax, ebx
0x18002854a  jmp     loc_180028660
0x18002854f  lea     rax, [rsp+310h+peUse]
0x180028554  mov     [rsp+310h+cbSid], 44h ; 'D'
0x18002855c  mov     [rsp+310h+pcbData], rax; peUse
0x180028561  lea     r9, [rsp+310h+cbSid]; cbSid
0x180028566  lea     rax, [rsp+310h+cchReferencedDomainName]
0x18002856b  mov     [rsp+310h+cchReferencedDomainName], 10h
0x180028573  mov     [rsp+310h+pvData], rax; cchReferencedDomainName
0x180028578  lea     r8, [rbp+210h+Sid]; Sid
0x18002857c  lea     rax, [rsp+310h+ReferencedDomainName]
0x180028581  mov     [rsp+310h+peUse], 0
0x180028589  lea     rdx, [rbp+210h+AccountName]; lpAccountName
0x18002858d  mov     [rsp+310h+pdwType], rax; int
0x180028592  xor     ecx, ecx; lpSystemName
0x180028594  mov     [rsp+310h+hMem], 0
0x18002859d  call    cs:__imp_LookupAccountNameW
0x1800285a3  test    eax, eax
0x1800285a5  jz      short loc_1800285AB
0x1800285a7  xor     ebx, ebx
0x1800285a9  jmp     short loc_1800285BF
0x1800285ab  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1800285b0  mov     edi, 80070534h
0x1800285b5  mov     ebx, eax
0x1800285b7  cmp     eax, edi
0x1800285b9  jz      loc_180028654
0x1800285bf  test    ebx, ebx
0x1800285c1  jns     short loc_1800285E2
0x1800285c3  mov     rcx, [rbp+218h]; this
0x1800285ca  lea     r8, aShellOobeUserD_0; "shell\\oobe\\user\\dll\\useroobecontrol"...
0x1800285d1  mov     r9d, ebx; char *
0x1800285d4  mov     edx, 326h; void *
0x1800285d9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800285de  mov     edi, ebx
0x1800285e0  jmp     short loc_180028654
0x1800285e2  mov     rbx, [rsp+310h+hMem]
0x1800285e7  test    rbx, rbx
0x1800285ea  jz      short loc_180028609
0x1800285ec  lea     rcx, [rsp+310h+var_2C8]; this
0x1800285f1  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x1800285f6  mov     rcx, rbx; hMem
0x1800285f9  call    cs:__imp_LocalFree
0x1800285ff  lea     rcx, [rsp+310h+var_2C8]; this
0x180028604  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180028609  lea     rdx, [rsp+310h+hMem]; StringSid
0x18002860e  mov     [rsp+310h+hMem], 0
0x180028617  lea     rcx, [rbp+210h+Sid]; Sid
0x18002861b  call    cs:__imp_ConvertSidToStringSidW
0x180028621  test    eax, eax
0x180028623  jnz     short loc_180028641
0x180028625  mov     rcx, [rbp+218h]; this
0x18002862c  lea     r8, aShellOobeUserD_0; "shell\\oobe\\user\\dll\\useroobecontrol"...
0x180028633  mov     edx, 327h; void *
0x180028638  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18002863d  mov     edi, eax
0x18002863f  jmp     short loc_180028654
0x180028641  mov     rax, [rsp+310h+hMem]
0x180028646  xor     edi, edi
0x180028648  mov     [rsi], rax
0x18002864b  mov     [rsp+310h+hMem], 0
0x180028654  lea     rcx, [rsp+310h+hMem]
0x180028659  call    ??1?$unique_storage@U?$resource_policy@PEAU_TOKEN_GROUPS@@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_TOKEN_GROUPS *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_TOKEN_GROUPS *,_TOKEN_GROUPS *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_TOKEN_GROUPS *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_TOKEN_GROUPS *,_TOKEN_GROUPS *,0,std::nullptr_t>>(void)
0x18002865e  mov     eax, edi
0x180028660  mov     rcx, [rbp+210h+var_30]
0x180028667  xor     rcx, rsp; StackCookie
0x18002866a  call    __security_check_cookie
0x18002866f  add     rsp, 2F8h
0x180028676  pop     rdi
0x180028677  pop     rsi
0x180028678  pop     rbx
0x180028679  pop     rbp
0x18002867a  retn
```
