# CSecurity::DuplicateCurrentToken(void * *,ulong,_SECURITY_ATTRIBUTES *,_SECURITY_IMPERSONATION_LEVEL,_TOKEN_TYPE,int)

- ea: `0x1800c6320`
- end: `0x1800c6606`
- name: `?DuplicateCurrentToken@CSecurity@@SAHPEAPEAXKPEAU_SECURITY_ATTRIBUTES@@W4_SECURITY_IMPERSONATION_LEVEL@@W4_TOKEN_TYPE@@H@Z`
- size: `742`
- prototype: `__int64 __fastcall(void **, DWORD dwDesiredAccess, LPSECURITY_ATTRIBUTES lpTokenAttributes, SECURITY_IMPERSONATION_LEVEL ImpersonationLevel, TOKEN_TYPE, int)`
- caller_count: `3`
- callee_count: `8`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x1800c6124`
- `0x180180390`
- `0x180180758`

## callees

- `0x180005d10`
- `0x180008920`
- `0x180071400`
- `0x1800c6320`
- `0x1800c6918`
- `0x1800c6a94`
- `0x180112380`
- `0x1801123a8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c64b2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c6570`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c64b2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c6570`
- `api-ms-win-security-base-l1-1-0!SetKernelObjectSecurity` at `0x1800c6553`
- `api-ms-win-security-base-l1-1-0!SetKernelObjectSecurity` at `0x1800c6553`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800c6593`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800c6593`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x1800c647a`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x1800c647a`
- `api-ms-win-security-base-l1-1-0!ImpersonateSelf` at `0x1800c63a5`
- `api-ms-win-security-base-l1-1-0!ImpersonateSelf` at `0x1800c63a5`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x1800c65c7`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x1800c65c7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800c637e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800c63ee`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800c637e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800c63ee`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800c6392`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800c6406`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800c6392`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800c6406`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CSecurity::DuplicateCurrentToken(
        void **a1,
        DWORD dwDesiredAccess,
        LPSECURITY_ATTRIBUTES lpTokenAttributes,
        SECURITY_IMPERSONATION_LEVEL ImpersonationLevel,
        TOKEN_TYPE TokenType,
        int a6)
{
  int v11; // r12d
  HANDLE CurrentThread; // rax
  unsigned int SecurityDescriptorForHandle; // ebx
  _QWORD *v14; // rcx
  __int64 v15; // rdx
  HANDLE v16; // rax
  DWORD LastError; // eax
  __int64 v18; // rdx
  _QWORD *v19; // rcx
  __int64 v20; // rdx
  void *TokenHandle; // [rsp+30h] [rbp-20h] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+38h] [rbp-18h] BYREF
  PSECURITY_DESCRIPTOR pSelfRelativeSecurityDescriptor[2]; // [rsp+40h] [rbp-10h] BYREF
  HANDLE Handle; // [rsp+80h] [rbp+30h] BYREF

  if ( !a1 )
  {
    WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\stdlib\\sec.cpp", 474, L"474", 0x54Fu, 0);
    return 0;
  }
  v11 = 0;
  TokenHandle = 0;
  Handle = 0;
  CurrentThread = GetCurrentThread();
  SecurityDescriptorForHandle = OpenThreadToken(CurrentThread, dwDesiredAccess, 1, &TokenHandle);
  if ( SecurityDescriptorForHandle )
    goto LABEL_13;
  SecurityDescriptorForHandle = ImpersonateSelf(SecurityImpersonation);
  if ( SecurityDescriptorForHandle )
  {
    v16 = GetCurrentThread();
    v11 = 1;
    SecurityDescriptorForHandle = OpenThreadToken(v16, dwDesiredAccess, 1, &TokenHandle);
    if ( !SecurityDescriptorForHandle )
    {
      v14 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000000) == 0 )
        goto LABEL_43;
      v15 = 25;
      goto LABEL_8;
    }
LABEL_13:
    if ( SecurityDescriptorForHandle != 1 || !TokenHandle )
      goto LABEL_43;
    pSelfRelativeSecurityDescriptor[0] = 0;
    SecurityDescriptor = 0;
    SecurityDescriptorForHandle = DuplicateTokenEx(
                                    TokenHandle,
                                    dwDesiredAccess,
                                    lpTokenAttributes,
                                    ImpersonationLevel,
                                    TokenType,
                                    &Handle);
    if ( !SecurityDescriptorForHandle )
    {
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000000) == 0 )
        goto LABEL_35;
      LastError = GetLastError();
      v18 = 26;
      goto LABEL_19;
    }
    if ( a6 )
    {
      SecurityDescriptorForHandle = CSecurity::GetSecurityDescriptorForHandle((struct IRequestContext *)Handle);
      if ( !SecurityDescriptorForHandle )
      {
        v19 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000000) == 0 )
          goto LABEL_35;
        v20 = 27;
        goto LABEL_29;
      }
      SecurityDescriptorForHandle = CSecurity::AdjustSecurityDescriptorWithNetworkServiceSid(
                                      pSelfRelativeSecurityDescriptor[0],
                                      (struct AutoSecurityDescriptor *)&SecurityDescriptor);
      if ( !SecurityDescriptorForHandle )
      {
        v19 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000000) == 0 )
          goto LABEL_35;
        v20 = 28;
LABEL_29:
        WPP_SF_(v19[2], v20, WPP_5b789da118f632ad9796e014c1252c4d_Traceguids);
        goto LABEL_35;
      }
      SecurityDescriptorForHandle = SetKernelObjectSecurity(Handle, 4u, SecurityDescriptor);
      if ( !SecurityDescriptorForHandle )
      {
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000000) == 0 )
          goto LABEL_35;
        LastError = GetLastError();
        v18 = 29;
LABEL_19:
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), v18, WPP_5b789da118f632ad9796e014c1252c4d_Traceguids, LastError);
        goto LABEL_35;
      }
    }
    *a1 = Handle;
    Handle = 0;
LABEL_35:
    if ( v11 == 1
      && !RevertToSelf()
      && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000000) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 30, WPP_5b789da118f632ad9796e014c1252c4d_Traceguids);
    }
    if ( SecurityDescriptor )
      LocalFree(SecurityDescriptor);
    AutoCleanup<AutoDeleteVector<unsigned short *>,unsigned short * *>::ReleasePtr(pSelfRelativeSecurityDescriptor);
    goto LABEL_43;
  }
  v14 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000000) == 0 )
    goto LABEL_43;
  v15 = 24;
LABEL_8:
  WPP_SF_(v14[2], v15, WPP_5b789da118f632ad9796e014c1252c4d_Traceguids);
LABEL_43:
  AutoCleanup<AutoHandle,void *>::ReleasePtr(&Handle);
  AutoCleanup<AutoHandle,void *>::ReleasePtr(&TokenHandle);
  return SecurityDescriptorForHandle;
}

```

## disassembly

```asm
0x1800c6320  mov     [rsp-28h+arg_8], rbx
0x1800c6325  mov     [rsp-28h+arg_10], rsi
0x1800c632a  push    rbp
0x1800c632b  push    rdi
0x1800c632c  push    r12
0x1800c632e  push    r14
0x1800c6330  push    r15
0x1800c6332  mov     rbp, rsp
0x1800c6335  sub     rsp, 50h
0x1800c6339  mov     esi, r9d
0x1800c633c  mov     r14, r8
0x1800c633f  mov     edi, edx
0x1800c6341  mov     r15, rcx
0x1800c6344  test    rcx, rcx
0x1800c6347  jnz     short loc_1800C6373
0x1800c6349  mov     qword ptr [rsp+50h+TokenType], rcx; struct IRequestContext *
0x1800c634e  mov     r9d, 54Fh; unsigned int
0x1800c6354  lea     r8, a474; "474"
0x1800c635b  mov     edx, 1DAh; unsigned int
0x1800c6360  lea     rcx, aOnecoreAdminWm_142; "onecore\\admin\\wmi\\wmx\\stdlib\\sec.c"...
0x1800c6367  call    ?WSManError@@YAXPEBGK0KPEAVIRequestContext@@@Z; WSManError(ushort const *,ulong,ushort const *,ulong,IRequestContext *)
0x1800c636c  xor     eax, eax
0x1800c636e  jmp     loc_1800C65ED
0x1800c6373  xor     r12d, r12d
0x1800c6376  mov     [rbp+TokenHandle], r12
0x1800c637a  mov     [rbp+Handle], r12
0x1800c637e  call    cs:__imp_GetCurrentThread
0x1800c6384  lea     r9, [rbp+TokenHandle]; TokenHandle
0x1800c6388  lea     r8d, [r12+1]; OpenAsSelf
0x1800c638d  mov     edx, edi; DesiredAccess
0x1800c638f  mov     rcx, rax; ThreadHandle
0x1800c6392  call    cs:__imp_OpenThreadToken
0x1800c6398  mov     ebx, eax
0x1800c639a  test    eax, eax
0x1800c639c  jnz     loc_1800C643C
0x1800c63a2  lea     ecx, [rax+2]; ImpersonationLevel
0x1800c63a5  call    cs:__imp_ImpersonateSelf
0x1800c63ab  mov     ebx, eax
0x1800c63ad  test    eax, eax
0x1800c63af  jnz     short loc_1800C63EE
0x1800c63b1  lea     rsi, WPP_GLOBAL_Control
0x1800c63b8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c63bf  cmp     rcx, rsi
0x1800c63c2  jz      loc_1800C65D8
0x1800c63c8  mov     edi, 10000000h
0x1800c63cd  test    [rcx+1Ch], edi
0x1800c63d0  jz      loc_1800C65D8
0x1800c63d6  lea     edx, [rax+18h]
0x1800c63d9  lea     r8, WPP_5b789da118f632ad9796e014c1252c4d_Traceguids
0x1800c63e0  mov     rcx, [rcx+10h]
0x1800c63e4  call    WPP_SF_
0x1800c63e9  jmp     loc_1800C65D8
0x1800c63ee  call    cs:__imp_GetCurrentThread
0x1800c63f4  lea     r9, [rbp+TokenHandle]; TokenHandle
0x1800c63f8  mov     r12d, 1
0x1800c63fe  mov     r8d, r12d; OpenAsSelf
0x1800c6401  mov     edx, edi; DesiredAccess
0x1800c6403  mov     rcx, rax; ThreadHandle
0x1800c6406  call    cs:__imp_OpenThreadToken
0x1800c640c  mov     ebx, eax
0x1800c640e  test    eax, eax
0x1800c6410  jnz     short loc_1800C643C
0x1800c6412  lea     rsi, WPP_GLOBAL_Control
0x1800c6419  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c6420  cmp     rcx, rsi
0x1800c6423  jz      loc_1800C65D8
0x1800c6429  mov     edi, 10000000h
0x1800c642e  test    [rcx+1Ch], edi
0x1800c6431  jz      loc_1800C65D8
0x1800c6437  lea     edx, [rax+19h]
0x1800c643a  jmp     short loc_1800C63D9
0x1800c643c  cmp     ebx, 1
0x1800c643f  jnz     loc_1800C65D8
0x1800c6445  mov     rcx, [rbp+TokenHandle]; hExistingToken
0x1800c6449  test    rcx, rcx
0x1800c644c  jz      loc_1800C65D8
0x1800c6452  mov     [rbp+pSelfRelativeSecurityDescriptor], 0
0x1800c645a  mov     [rbp+SecurityDescriptor], 0
0x1800c6462  lea     rax, [rbp+Handle]
0x1800c6466  mov     [rsp+50h+phNewToken], rax; phNewToken
0x1800c646b  mov     eax, [rbp+arg_20]
0x1800c646e  mov     [rsp+50h+TokenType], eax; TokenType
0x1800c6472  mov     r9d, esi; ImpersonationLevel
0x1800c6475  mov     r8, r14; lpTokenAttributes
0x1800c6478  mov     edx, edi; dwDesiredAccess
0x1800c647a  call    cs:__imp_DuplicateTokenEx
0x1800c6480  mov     ebx, eax
0x1800c6482  lea     rsi, WPP_GLOBAL_Control
0x1800c6489  mov     edi, 10000000h
0x1800c648e  lea     r14, WPP_5b789da118f632ad9796e014c1252c4d_Traceguids
0x1800c6495  test    eax, eax
0x1800c6497  jnz     short loc_1800C64D6
0x1800c6499  mov     rax, cs:WPP_GLOBAL_Control
0x1800c64a0  cmp     rax, rsi
0x1800c64a3  jz      loc_1800C658D
0x1800c64a9  test    [rax+1Ch], edi
0x1800c64ac  jz      loc_1800C658D
0x1800c64b2  call    cs:__imp_GetLastError
0x1800c64b8  lea     edx, [rbx+1Ah]
0x1800c64bb  mov     r9d, eax
0x1800c64be  mov     r8, r14
0x1800c64c1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c64c8  mov     rcx, [rcx+10h]
0x1800c64cc  call    WPP_SF_d
0x1800c64d1  jmp     loc_1800C658D
0x1800c64d6  cmp     [rbp+arg_28], 0
0x1800c64da  jz      loc_1800C657E
0x1800c64e0  lea     rdx, [rbp+pSelfRelativeSecurityDescriptor]
0x1800c64e4  mov     rcx, [rbp+Handle]; struct IRequestContext *
0x1800c64e8  call    ?GetSecurityDescriptorForHandle@CSecurity@@CAHPEAXAEAV?$AutoDeleteVector@E@@@Z; CSecurity::GetSecurityDescriptorForHandle(void *,AutoDeleteVector<uchar> &)
0x1800c64ed  mov     ebx, eax
0x1800c64ef  test    eax, eax
0x1800c64f1  jnz     short loc_1800C6511
0x1800c64f3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c64fa  cmp     rcx, rsi
0x1800c64fd  jz      loc_1800C658D
0x1800c6503  test    [rcx+1Ch], edi
0x1800c6506  jz      loc_1800C658D
0x1800c650c  lea     edx, [rax+1Bh]
0x1800c650f  jmp     short loc_1800C6538
0x1800c6511  lea     rdx, [rbp+SecurityDescriptor]; struct AutoSecurityDescriptor *
0x1800c6515  mov     rcx, [rbp+pSelfRelativeSecurityDescriptor]; pSelfRelativeSecurityDescriptor
0x1800c6519  call    ?AdjustSecurityDescriptorWithNetworkServiceSid@CSecurity@@CAHPEAXAEAVAutoSecurityDescriptor@@@Z; CSecurity::AdjustSecurityDescriptorWithNetworkServiceSid(void *,AutoSecurityDescriptor &)
0x1800c651e  mov     ebx, eax
0x1800c6520  test    eax, eax
0x1800c6522  jnz     short loc_1800C6546
0x1800c6524  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c652b  cmp     rcx, rsi
0x1800c652e  jz      short loc_1800C658D
0x1800c6530  test    [rcx+1Ch], edi
0x1800c6533  jz      short loc_1800C658D
0x1800c6535  lea     edx, [rax+1Ch]
0x1800c6538  mov     r8, r14
0x1800c653b  mov     rcx, [rcx+10h]
0x1800c653f  call    WPP_SF_
0x1800c6544  jmp     short loc_1800C658D
0x1800c6546  mov     r8, [rbp+SecurityDescriptor]; SecurityDescriptor
0x1800c654a  mov     edx, 4; SecurityInformation
0x1800c654f  mov     rcx, [rbp+Handle]; Handle
0x1800c6553  call    cs:__imp_SetKernelObjectSecurity
0x1800c6559  mov     ebx, eax
0x1800c655b  test    eax, eax
0x1800c655d  jnz     short loc_1800C657E
0x1800c655f  mov     rax, cs:WPP_GLOBAL_Control
0x1800c6566  cmp     rax, rsi
0x1800c6569  jz      short loc_1800C658D
0x1800c656b  test    [rax+1Ch], edi
0x1800c656e  jz      short loc_1800C658D
0x1800c6570  call    cs:__imp_GetLastError
0x1800c6576  lea     edx, [rbx+1Dh]
0x1800c6579  jmp     loc_1800C64BB
0x1800c657e  mov     rax, [rbp+Handle]
0x1800c6582  mov     [r15], rax
0x1800c6585  mov     [rbp+Handle], 0
0x1800c658d  cmp     r12d, 1
0x1800c6591  jnz     short loc_1800C65BE
0x1800c6593  call    cs:__imp_RevertToSelf
0x1800c6599  test    eax, eax
0x1800c659b  jnz     short loc_1800C65BE
0x1800c659d  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c65a4  cmp     rcx, rsi
0x1800c65a7  jz      short loc_1800C65BE
0x1800c65a9  test    [rcx+1Ch], edi
0x1800c65ac  jz      short loc_1800C65BE
0x1800c65ae  lea     edx, [rax+1Eh]
0x1800c65b1  mov     r8, r14
0x1800c65b4  mov     rcx, [rcx+10h]
0x1800c65b8  call    WPP_SF_
0x1800c65bd  nop
0x1800c65be  mov     rcx, [rbp+SecurityDescriptor]; hMem
0x1800c65c2  test    rcx, rcx
0x1800c65c5  jz      short loc_1800C65CE
0x1800c65c7  call    cs:__imp_LocalFree
0x1800c65cd  nop
0x1800c65ce  lea     rcx, [rbp+pSelfRelativeSecurityDescriptor]
0x1800c65d2  call    ?ReleasePtr@?$AutoCleanup@V?$AutoDeleteVector@PEAG@@PEAPEAG@@AEAAXXZ; AutoCleanup<AutoDeleteVector<ushort *>,ushort * *>::ReleasePtr(void)
0x1800c65d7  nop
0x1800c65d8  lea     rcx, [rbp+Handle]
0x1800c65dc  call    ?ReleasePtr@?$AutoCleanup@VAutoHandle@@PEAX@@AEAAXXZ; AutoCleanup<AutoHandle,void *>::ReleasePtr(void)
0x1800c65e1  nop
0x1800c65e2  lea     rcx, [rbp+TokenHandle]
0x1800c65e6  call    ?ReleasePtr@?$AutoCleanup@VAutoHandle@@PEAX@@AEAAXXZ; AutoCleanup<AutoHandle,void *>::ReleasePtr(void)
0x1800c65eb  mov     eax, ebx
0x1800c65ed  lea     r11, [rsp+50h+var_s0]
0x1800c65f2  mov     rbx, [r11+38h]
0x1800c65f6  mov     rsi, [r11+40h]
0x1800c65fa  mov     rsp, r11
0x1800c65fd  pop     r15
0x1800c65ff  pop     r14
0x1800c6601  pop     r12
0x1800c6603  pop     rdi
0x1800c6604  pop     rbp
0x1800c6605  retn
```
