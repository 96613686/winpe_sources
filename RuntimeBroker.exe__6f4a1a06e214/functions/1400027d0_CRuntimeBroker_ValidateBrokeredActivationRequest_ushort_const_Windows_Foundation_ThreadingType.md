# CRuntimeBroker::ValidateBrokeredActivationRequest(ushort const *,Windows::Foundation::ThreadingType &)

- ea: `0x1400027d0`
- end: `0x140002d48`
- name: `?ValidateBrokeredActivationRequest@CRuntimeBroker@@CAJPEBGAEAW4ThreadingType@Foundation@Windows@@@Z`
- size: `1400`
- prototype: `__int64 __fastcall(PCNZWCH sourceString, enum Windows::Foundation::ThreadingType *)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140002260`
- `0x140002590`

## callees

- `0x1400027d0`
- `0x140002d50`
- `0x140004ea0`
- `0x140008c80`
- `0x140010010`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!AccessCheckByType` at `0x140002af2`
- `api-ms-win-security-base-l1-1-0!AccessCheckByType` at `0x140002af2`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x140002a6e`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x140002a6e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140002c36`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140002c54`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140002c76`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140002c36`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140002c54`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140002c76`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x140002c91`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x140002c91`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x140002a36`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x140002a36`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x140002a1e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x140002a1e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140002b54`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140002b54`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x140002a47`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x140002a47`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x1400029f9`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x1400029f9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x14000284f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x14000284f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14000283a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x140002b67`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x140002b8e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x140002b9c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x140002bc1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14000283a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x140002b67`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x140002b8e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x140002b9c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x140002bc1`
- `combase!__imp_RoGetRegistrationStoreContext` at `0x14000288e`
- `combase!__imp_RoGetRegistrationStoreContext` at `0x14000288e`

## pseudocode

```c
__int64 __fastcall CRuntimeBroker::ValidateBrokeredActivationRequest(
        PCNZWCH sourceString,
        enum Windows::Foundation::ThreadingType *a2)
{
  unsigned __int64 v4; // rbx
  HRESULT v5; // eax
  int RegistrationStoreContext; // ebx
  int v7; // eax
  __int16 v8; // dx
  __int16 v9; // cx
  __int64 *v10; // rsi
  HRESULT v11; // eax
  HANDLE CurrentThread; // rax
  signed int v13; // edi
  BOOL inited; // eax
  unsigned __int8 near **v15; // rdx
  __int64 v16; // rcx
  __int64 v17; // rcx
  char v19; // al
  signed int LastError; // eax
  signed int v21; // eax
  int v22; // eax
  __int64 v23; // [rsp+60h] [rbp-A0h] BYREF
  HSTRING string; // [rsp+68h] [rbp-98h] BYREF
  WINBOOL AccessStatus; // [rsp+70h] [rbp-90h] BYREF
  DWORD GrantedAccess; // [rsp+74h] [rbp-8Ch] BYREF
  DWORD PrivilegeSetLength; // [rsp+78h] [rbp-88h] BYREF
  __int64 v28; // [rsp+80h] [rbp-80h] BYREF
  void **v29; // [rsp+88h] [rbp-78h] BYREF
  void *TokenHandle; // [rsp+90h] [rbp-70h] BYREF
  __int64 v31; // [rsp+98h] [rbp-68h] BYREF
  __int64 v32; // [rsp+A0h] [rbp-60h] BYREF
  int v33; // [rsp+B0h] [rbp-50h] BYREF
  char v34; // [rsp+B8h] [rbp-48h]
  HSTRING v35; // [rsp+C0h] [rbp-40h]
  char v36; // [rsp+C8h] [rbp-38h]
  HSTRING v37[2]; // [rsp+D0h] [rbp-30h]
  char v38; // [rsp+E0h] [rbp-20h]
  int v39; // [rsp+E4h] [rbp-1Ch]
  char v40; // [rsp+E8h] [rbp-18h]
  int v41; // [rsp+ECh] [rbp-14h]
  __int64 v42; // [rsp+F0h] [rbp-10h]
  char v43; // [rsp+F8h] [rbp-8h]
  HSTRING v44; // [rsp+100h] [rbp+0h]
  char v45; // [rsp+108h] [rbp+8h]
  __int64 v46; // [rsp+10Ch] [rbp+Ch]
  char v47; // [rsp+118h] [rbp+18h]
  PSECURITY_DESCRIPTOR pSecurityDescriptor[2]; // [rsp+120h] [rbp+20h]
  char v49; // [rsp+130h] [rbp+30h]
  int v50; // [rsp+134h] [rbp+34h]
  struct _PRIVILEGE_SET PrivilegeSet; // [rsp+140h] [rbp+40h] BYREF
  struct _GENERIC_MAPPING GenericMapping; // [rsp+158h] [rbp+58h] BYREF

  v23 = 0;
  v28 = 0;
  string = 0;
  if ( sourceString )
  {
    v4 = -1;
    do
      ++v4;
    while ( sourceString[v4] );
    if ( v4 > 0xFFFFFFFF )
    {
      RegistrationStoreContext = -2147024362;
      goto LABEL_9;
    }
    WindowsDeleteString(0);
    string = 0;
    v5 = WindowsCreateString(sourceString, v4, &string);
  }
  else
  {
    v5 = Microsoft::WRL::Wrappers::HString::Set(
           (Microsoft::WRL::Wrappers::HString *)&string,
           (const unsigned __int16 *)&Format,
           0);
  }
  RegistrationStoreContext = v5;
  if ( v5 >= 0 )
  {
    RegistrationStoreContext = RoGetRegistrationStoreContext(0, 0, 0, &GUID_0fe5a50b_6ca2_47ed_8560_aa7920f978f2, &v23);
    if ( RegistrationStoreContext >= 0 )
      RegistrationStoreContext = (*(__int64 (__fastcall **)(__int64, HSTRING, __int64 *))(*(_QWORD *)v23 + 80LL))(
                                   v23,
                                   string,
                                   &v28);
  }
LABEL_9:
  if ( RegistrationStoreContext == -2147024894 )
  {
    RegistrationStoreContext = -2147024891;
    goto LABEL_49;
  }
  if ( RegistrationStoreContext < 0 )
    goto LABEL_49;
  v34 = 0;
  v36 = 0;
  v38 = 0;
  v37[1] = 0;
  v40 = 0;
  v43 = 0;
  v45 = 0;
  v47 = 0;
  v49 = 0;
  v35 = 0;
  v37[0] = 0;
  v39 = 0;
  v41 = 0;
  v42 = 0;
  v44 = 0;
  v46 = 0;
  pSecurityDescriptor[0] = 0;
  pSecurityDescriptor[1] = 0;
  v50 = 0;
  v31 = 0;
  v32 = 0;
  v7 = (*(__int64 (__fastcall **)(__int64, __int64, int *, __int64 *, __int64 *))(*(_QWORD *)v23 + 120LL))(
         v23,
         v28,
         &v33,
         &v31,
         &v32);
  RegistrationStoreContext = v7;
  if ( !v40 )
    goto LABEL_59;
  if ( v7 < 0 )
  {
    if ( v7 != -2147024894 )
      goto LABEL_44;
LABEL_59:
    RegistrationStoreContext = -2147024891;
    goto LABEL_44;
  }
  v8 = v31;
  if ( (v31 & 0x10) != 0 )
    goto LABEL_59;
  v9 = v32;
  if ( (v32 & 0x10) != 0 )
  {
    RegistrationStoreContext = -2147024883;
    goto LABEL_44;
  }
  if ( v41 != 1 )
    goto LABEL_59;
  if ( (v31 & 1) != 0 )
  {
    RegistrationStoreContext = -2147024894;
    goto LABEL_44;
  }
  if ( (v32 & 1) != 0 )
  {
    RegistrationStoreContext = -2147024883;
    goto LABEL_44;
  }
  if ( v33 )
    goto LABEL_59;
  if ( v38 )
    *(_DWORD *)a2 = v39;
  else
    RegistrationStoreContext = -2147024894;
  if ( (v8 & 8) != 0 )
  {
    RegistrationStoreContext = -2147024894;
    goto LABEL_44;
  }
  if ( (v9 & 8) != 0 )
  {
    RegistrationStoreContext = -2147024883;
    goto LABEL_44;
  }
  if ( RegistrationStoreContext >= 0 )
  {
    if ( !byte_140018608 )
      goto LABEL_25;
    v19 = 0;
    if ( BYTE4(v46) )
      v19 = BYTE5(v46);
    if ( (v8 & 0x100) != 0 )
    {
      RegistrationStoreContext = -2147024894;
      goto LABEL_44;
    }
    if ( (v9 & 0x100) != 0 )
    {
      RegistrationStoreContext = -2147024883;
      goto LABEL_44;
    }
    if ( !v19 )
    {
LABEL_25:
      if ( (v8 & 0x400) != 0 )
      {
        RegistrationStoreContext = -2147024894;
        goto LABEL_44;
      }
      if ( (v9 & 0x400) != 0 )
      {
        RegistrationStoreContext = -2147024883;
        goto LABEL_44;
      }
      v10 = `CRuntimeBroker::CheckActivationPermissions'::`2'::defaultActivationPermission;
      if ( pSecurityDescriptor[0] )
        v10 = (__int64 *)pSecurityDescriptor[0];
      v11 = CoImpersonateClient();
      if ( v11 >= 0 )
      {
        v29 = &Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::`vftable';
        TokenHandle = 0;
        CurrentThread = GetCurrentThread();
        if ( OpenThreadToken(CurrentThread, 8u, 1, &TokenHandle) )
        {
          v13 = 0;
        }
        else
        {
          LastError = GetLastError();
          v13 = LastError;
          if ( LastError > 0 )
            v13 = (unsigned __int16)LastError | 0x80070000;
        }
        CoRevertToSelf();
        RegistrationStoreContext = -2147024891;
        if ( v13 >= 0 )
        {
          inited = InitOnceExecuteOnce(
                     &`CRuntimeBroker::GetSelfSid'::`2'::rtbSelfSidInitOnce,
                     CRuntimeBroker::QueryProcessTokenSid,
                     0,
                     0);
          v15 = &CRuntimeBroker::s_rtbSelfSid;
          *(_QWORD *)&PrivilegeSet.PrivilegeCount = 1;
          PrivilegeSetLength = 20;
          if ( !inited )
            v15 = 0;
          GrantedAccess = 0;
          AccessStatus = 0;
          PrivilegeSet.Privilege[0].Luid = 0;
          PrivilegeSet.Privilege[0].Attributes = 0;
          GenericMapping = 0;
          if ( AccessCheckByType(
                 v10,
                 v15,
                 TokenHandle,
                 8u,
                 0,
                 0,
                 &GenericMapping,
                 &PrivilegeSet,
                 &PrivilegeSetLength,
                 &GrantedAccess,
                 &AccessStatus) )
          {
            goto LABEL_36;
          }
          v21 = GetLastError();
          v13 = v21;
          if ( v21 > 0 )
            v13 = (unsigned __int16)v21 | 0x80070000;
          if ( v13 >= 0 )
          {
LABEL_36:
            v13 = -2147024891;
            if ( AccessStatus )
              v13 = 0;
          }
        }
        v29 = &Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::`vftable';
        if ( TokenHandle
          && !(unsigned __int8)Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::InternalClose(&v29) )
        {
          v22 = GetLastError();
          if ( v22 > 0 )
            v22 = (unsigned __int16)v22 | 0x80070000;
          RaiseException(v22, 1u, 0, 0);
          __debugbreak();
        }
        if ( v13 >= 0 )
          RegistrationStoreContext = v13;
        goto LABEL_44;
      }
      if ( v11 == -2147417833 )
      {
        RegistrationStoreContext = 0;
        goto LABEL_44;
      }
    }
    goto LABEL_59;
  }
LABEL_44:
  if ( pSecurityDescriptor[0] )
  {
    LocalFree(pSecurityDescriptor[0]);
    pSecurityDescriptor[0] = 0;
    LOWORD(pSecurityDescriptor[1]) = 0;
  }
  WindowsDeleteString(v44);
  v16 = v42;
  v44 = 0;
  if ( v42 )
  {
    v42 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
  }
  WindowsDeleteString(v37[0]);
  v37[0] = 0;
  WindowsDeleteString(v35);
LABEL_49:
  if ( v28 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 32LL))(v23);
  WindowsDeleteString(string);
  v17 = v23;
  string = 0;
  if ( v23 )
  {
    v23 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
  }
  return (unsigned int)RegistrationStoreContext;
}

```

## disassembly

```asm
0x1400027d0  push    rbp
0x1400027d2  push    rbx
0x1400027d3  push    rsi
0x1400027d4  push    rdi
0x1400027d5  push    r14
0x1400027d7  lea     rbp, [rsp-70h]
0x1400027dc  sub     rsp, 170h
0x1400027e3  mov     rax, cs:__security_cookie
0x1400027ea  xor     rax, rsp
0x1400027ed  mov     [rbp+90h+var_28], rax
0x1400027f1  xor     r14d, r14d
0x1400027f4  mov     rsi, rdx
0x1400027f7  mov     [rsp+190h+var_130], r14
0x1400027fc  mov     rdi, rcx
0x1400027ff  mov     [rbp+90h+var_110], r14
0x140002803  mov     [rsp+190h+string], r14
0x140002808  test    rcx, rcx
0x14000280b  jz      loc_140002C98
0x140002811  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x140002818  nop     dword ptr [rax+rax+00000000h]
0x140002820  inc     rbx
0x140002823  cmp     [rcx+rbx*2], r14w
0x140002828  jnz     short loc_140002820
0x14000282a  mov     eax, 0FFFFFFFFh
0x14000282f  cmp     rbx, rax
0x140002832  ja      loc_140002B36
0x140002838  xor     ecx, ecx; string
0x14000283a  call    cs:__imp_WindowsDeleteString
0x140002840  mov     edx, ebx; length
0x140002842  mov     [rsp+190h+string], r14
0x140002847  lea     r8, [rsp+190h+string]; string
0x14000284c  mov     rcx, rdi; sourceString
0x14000284f  call    cs:__imp_WindowsCreateString
0x140002855  mov     ebx, eax
0x140002857  test    eax, eax
0x140002859  js      short loc_1400028B6
0x14000285b  mov     rcx, [rsp+190h+var_130]
0x140002860  test    rcx, rcx
0x140002863  jz      short loc_140002876
0x140002865  mov     [rsp+190h+var_130], r14
0x14000286a  mov     rax, [rcx]
0x14000286d  mov     rax, [rax+10h]
0x140002871  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002876  lea     rax, [rsp+190h+var_130]
0x14000287b  xor     r8d, r8d
0x14000287e  lea     r9, _GUID_0fe5a50b_6ca2_47ed_8560_aa7920f978f2
0x140002885  mov     [rsp+190h+ObjectTypeList], rax
0x14000288a  xor     edx, edx
0x14000288c  xor     ecx, ecx
0x14000288e  call    cs:__imp_RoGetRegistrationStoreContext
0x140002894  mov     ebx, eax
0x140002896  test    eax, eax
0x140002898  js      short loc_1400028B6
0x14000289a  mov     rcx, [rsp+190h+var_130]
0x14000289f  lea     r8, [rbp+90h+var_110]
0x1400028a3  mov     rdx, [rsp+190h+string]
0x1400028a8  mov     rax, [rcx]
0x1400028ab  mov     rax, [rax+50h]
0x1400028af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400028b4  mov     ebx, eax
0x1400028b6  cmp     ebx, 80070002h
0x1400028bc  jz      loc_140002CB1
0x1400028c2  test    ebx, ebx
0x1400028c4  js      loc_140002BA2
0x1400028ca  mov     rcx, [rsp+190h+var_130]
0x1400028cf  lea     rdx, [rbp+90h+var_F0]
0x1400028d3  xor     eax, eax
0x1400028d5  mov     [rbp+90h+var_D8], r14b
0x1400028d9  xorps   xmm0, xmm0
0x1400028dc  mov     [rbp+90h+var_C8], al
0x1400028df  movups  xmmword ptr [rbp+90h+pSecurityDescriptor], xmm0
0x1400028e3  mov     [rbp+90h+var_B0], al
0x1400028e6  lea     r9, [rbp+90h+var_F8]
0x1400028ea  movups  xmmword ptr [rbp+90h+var_C0], xmm0
0x1400028ee  mov     [rbp+90h+var_A8], al
0x1400028f1  lea     r8, [rbp+90h+var_E0]
0x1400028f5  mov     [rbp+90h+var_98], al
0x1400028f8  mov     [rbp+90h+var_88], al
0x1400028fb  mov     [rbp+90h+var_78], al
0x1400028fe  mov     [rbp+90h+var_60], al
0x140002901  mov     [rbp+90h+var_D0], r14
0x140002905  mov     [rbp+90h+var_C0], r14
0x140002909  mov     [rbp+90h+var_AC], r14d
0x14000290d  mov     [rbp+90h+var_A4], r14d
0x140002911  mov     [rbp+90h+var_A0], r14
0x140002915  mov     [rbp+90h+var_90], r14
0x140002919  mov     [rbp+90h+var_84], r14
0x14000291d  mov     [rbp+90h+pSecurityDescriptor], r14
0x140002921  mov     word ptr [rbp+90h+pSecurityDescriptor+8], r14w
0x140002926  mov     [rbp+90h+var_5C], r14d
0x14000292a  mov     [rbp+90h+var_F8], r14
0x14000292e  mov     [rbp+90h+var_F0], r14
0x140002932  mov     rax, [rcx]
0x140002935  mov     [rsp+190h+ObjectTypeList], rdx
0x14000293a  mov     rdx, [rbp+90h+var_110]
0x14000293e  mov     rax, [rax+78h]
0x140002942  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002947  mov     ebx, eax
0x140002949  cmp     [rbp+90h+var_A8], r14b
0x14000294d  jz      loc_140002C2C
0x140002953  test    eax, eax
0x140002955  js      loc_140002B40
0x14000295b  mov     rdx, [rbp+90h+var_F8]
0x14000295f  test    dl, 10h
0x140002962  jnz     loc_140002C2C
0x140002968  mov     rcx, [rbp+90h+var_F0]
0x14000296c  test    cl, 10h
0x14000296f  jnz     loc_140002CBB
0x140002975  cmp     [rbp+90h+var_A4], 1
0x140002979  jnz     loc_140002C2C
0x14000297f  test    dl, 1
0x140002982  jnz     loc_140002CC5
0x140002988  test    cl, 1
0x14000298b  jnz     loc_140002CCF
0x140002991  cmp     [rbp+90h+var_E0], r14d
0x140002995  jnz     loc_140002C2C
0x14000299b  cmp     [rbp+90h+var_B0], r14b
0x14000299f  jz      loc_140002CD9
0x1400029a5  mov     eax, [rbp+90h+var_AC]
0x1400029a8  mov     [rsi], eax
0x1400029aa  test    dl, 8
0x1400029ad  jnz     loc_140002CE3
0x1400029b3  test    cl, 8
0x1400029b6  jnz     loc_140002CED
0x1400029bc  test    ebx, ebx
0x1400029be  js      loc_140002B4B
0x1400029c4  cmp     cs:byte_140018608, r14b
0x1400029cb  jnz     loc_140002C03
0x1400029d1  bt      rdx, 0Ah
0x1400029d6  jb      loc_140002D14
0x1400029dc  bt      rcx, 0Ah
0x1400029e1  jb      loc_140002D1E
0x1400029e7  mov     rax, [rbp+90h+pSecurityDescriptor]
0x1400029eb  lea     rsi, ?defaultActivationPermission@?1??CheckActivationPermissions@CRuntimeBroker@@CAJPEAX@Z@4QBEB; uchar const near * const `CRuntimeBroker::CheckActivationPermissions(void *)'::`2'::defaultActivationPermission
0x1400029f2  test    rax, rax
0x1400029f5  cmovnz  rsi, rax
0x1400029f9  call    cs:__imp_CoImpersonateClient
0x1400029ff  test    eax, eax
0x140002a01  js      loc_140002D35
0x140002a07  mov     [rsp+190h+arg_10], r15
0x140002a0f  lea     r15, ??_7?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::`vftable'
0x140002a16  mov     [rbp+90h+var_108], r15
0x140002a1a  mov     [rbp+90h+TokenHandle], r14
0x140002a1e  call    cs:__imp_GetCurrentThread
0x140002a24  lea     r9, [rbp+90h+TokenHandle]; TokenHandle
0x140002a28  mov     edx, 8; DesiredAccess
0x140002a2d  mov     rcx, rax; ThreadHandle
0x140002a30  mov     r8d, 1; OpenAsSelf
0x140002a36  call    cs:__imp_OpenThreadToken
0x140002a3c  test    eax, eax
0x140002a3e  jz      loc_140002C36
0x140002a44  mov     edi, r14d
0x140002a47  call    cs:__imp_CoRevertToSelf
0x140002a4d  mov     ebx, 80070005h
0x140002a52  test    edi, edi
0x140002a54  js      loc_140002B0B
0x140002a5a  xor     r9d, r9d; Context
0x140002a5d  lea     rdx, ?QueryProcessTokenSid@CRuntimeBroker@@SAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; InitFn
0x140002a64  xor     r8d, r8d; Parameter
0x140002a67  lea     rcx, ?rtbSelfSidInitOnce@?1??GetSelfSid@CRuntimeBroker@@SAPEAXXZ@4T_RTL_RUN_ONCE@@A; InitOnce
0x140002a6e  call    cs:__imp_InitOnceExecuteOnce
0x140002a74  mov     r8, [rbp+90h+TokenHandle]; ClientToken
0x140002a78  lea     rdx, ?s_rtbSelfSid@CRuntimeBroker@@2PAEA; uchar near * CRuntimeBroker::s_rtbSelfSid
0x140002a7f  test    eax, eax
0x140002a81  mov     qword ptr [rbp+90h+var_50.PrivilegeCount], 1
0x140002a89  xorps   xmm0, xmm0
0x140002a8c  mov     [rsp+190h+var_118], 14h
0x140002a94  cmovz   rdx, r14; PrincipalSelfSid
0x140002a98  mov     [rsp+190h+var_11C], r14d
0x140002a9d  xor     eax, eax
0x140002a9f  mov     [rsp+190h+var_120], r14d
0x140002aa4  mov     qword ptr [rbp+90h+var_50.Privilege.Luid.LowPart], rax
0x140002aa8  mov     r9d, 8; DesiredAccess
0x140002aae  mov     [rbp+90h+var_50.Privilege.Attributes], eax
0x140002ab1  mov     rcx, rsi; pSecurityDescriptor
0x140002ab4  lea     rax, [rsp+190h+var_120]
0x140002ab9  mov     [rsp+190h+AccessStatus], rax; AccessStatus
0x140002abe  lea     rax, [rsp+190h+var_11C]
0x140002ac3  mov     [rsp+190h+GrantedAccess], rax; GrantedAccess
0x140002ac8  lea     rax, [rsp+190h+var_118]
0x140002acd  mov     [rsp+190h+PrivilegeSetLength], rax; PrivilegeSetLength
0x140002ad2  lea     rax, [rbp+90h+var_50]
0x140002ad6  mov     [rsp+190h+PrivilegeSet], rax; PrivilegeSet
0x140002adb  lea     rax, [rbp+90h+var_38]
0x140002adf  mov     [rsp+190h+GenericMapping], rax; GenericMapping
0x140002ae4  mov     [rsp+190h+ObjectTypeListLength], r14d; ObjectTypeListLength
0x140002ae9  mov     [rsp+190h+ObjectTypeList], r14; ObjectTypeList
0x140002aee  movups  xmmword ptr [rbp+90h+var_38.GenericRead], xmm0
0x140002af2  call    cs:__imp_AccessCheckByType
0x140002af8  test    eax, eax
0x140002afa  jz      loc_140002C54
0x140002b00  cmp     [rsp+190h+var_120], r14d
0x140002b05  mov     edi, ebx
0x140002b07  cmovnz  edi, r14d
0x140002b0b  mov     [rbp+90h+var_108], r15
0x140002b0f  mov     r15, [rsp+190h+arg_10]
0x140002b17  cmp     [rbp+90h+TokenHandle], r14
0x140002b1b  jz      short loc_140002B2E
0x140002b1d  lea     rcx, [rbp+90h+var_108]
0x140002b21  call    ?InternalClose@?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::InternalClose(void)
0x140002b26  test    al, al
0x140002b28  jz      loc_140002C76
0x140002b2e  test    edi, edi
0x140002b30  js      short loc_140002B4B
0x140002b32  mov     ebx, edi
0x140002b34  jmp     short loc_140002B4B
0x140002b36  mov     ebx, 80070216h
0x140002b3b  jmp     loc_1400028B6
0x140002b40  cmp     eax, 80070002h
0x140002b45  jz      loc_140002C2C
0x140002b4b  mov     rcx, [rbp+90h+pSecurityDescriptor]; hMem
0x140002b4f  test    rcx, rcx
0x140002b52  jz      short loc_140002B63
0x140002b54  call    cs:__imp_LocalFree
0x140002b5a  mov     [rbp+90h+pSecurityDescriptor], r14
0x140002b5e  mov     word ptr [rbp+90h+pSecurityDescriptor+8], r14w
0x140002b63  mov     rcx, [rbp+90h+var_90]; string
0x140002b67  call    cs:__imp_WindowsDeleteString
0x140002b6d  mov     rcx, [rbp+90h+var_A0]
0x140002b71  mov     [rbp+90h+var_90], r14
0x140002b75  test    rcx, rcx
0x140002b78  jz      short loc_140002B8A
0x140002b7a  mov     [rbp+90h+var_A0], r14
0x140002b7e  mov     rax, [rcx]
0x140002b81  mov     rax, [rax+10h]
0x140002b85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002b8a  mov     rcx, [rbp+90h+var_C0]; string
0x140002b8e  call    cs:__imp_WindowsDeleteString
0x140002b94  mov     rcx, [rbp+90h+var_D0]; string
0x140002b98  mov     [rbp+90h+var_C0], r14
0x140002b9c  call    cs:__imp_WindowsDeleteString
0x140002ba2  mov     rdx, [rbp+90h+var_110]
0x140002ba6  test    rdx, rdx
0x140002ba9  jz      short loc_140002BBC
0x140002bab  mov     rcx, [rsp+190h+var_130]
0x140002bb0  mov     rax, [rcx]
0x140002bb3  mov     rax, [rax+20h]
0x140002bb7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002bbc  mov     rcx, [rsp+190h+string]; string
0x140002bc1  call    cs:__imp_WindowsDeleteString
0x140002bc7  mov     rcx, [rsp+190h+var_130]
0x140002bcc  mov     [rsp+190h+string], r14
0x140002bd1  test    rcx, rcx
0x140002bd4  jz      short loc_140002BE7
0x140002bd6  mov     [rsp+190h+var_130], r14
0x140002bdb  mov     rax, [rcx]
0x140002bde  mov     rax, [rax+10h]
0x140002be2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002be7  mov     eax, ebx
0x140002be9  mov     rcx, [rbp+90h+var_28]
0x140002bed  xor     rcx, rsp; StackCookie
0x140002bf0  call    __security_check_cookie
0x140002bf5  add     rsp, 170h
0x140002bfc  pop     r14
0x140002bfe  pop     rdi
0x140002bff  pop     rsi
0x140002c00  pop     rbx
0x140002c01  pop     rbp
0x140002c02  retn
0x140002c03  xor     al, al
0x140002c05  cmp     byte ptr [rbp+90h+var_84+4], al
0x140002c08  jnz     loc_140002CF7
0x140002c0e  bt      rdx, 8
0x140002c13  jb      loc_140002D00
0x140002c19  bt      rcx, 8
0x140002c1e  jb      loc_140002D0A
0x140002c24  test    al, al
0x140002c26  jz      loc_1400029D1
0x140002c2c  mov     ebx, 80070005h
0x140002c31  jmp     loc_140002B4B
0x140002c36  call    cs:__imp_GetLastError
0x140002c3c  mov     edi, eax
0x140002c3e  test    eax, eax
0x140002c40  jle     loc_140002A47
0x140002c46  movzx   edi, ax
0x140002c49  or      edi, 80070000h
0x140002c4f  jmp     loc_140002A47
0x140002c54  call    cs:__imp_GetLastError
0x140002c5a  mov     edi, eax
0x140002c5c  test    eax, eax
0x140002c5e  jle     short loc_140002C69
0x140002c60  movzx   edi, ax
0x140002c63  or      edi, 80070000h
0x140002c69  test    edi, edi
0x140002c6b  js      loc_140002B0B
0x140002c71  jmp     loc_140002B00
0x140002c76  call    cs:__imp_GetLastError
0x140002c7c  test    eax, eax
0x140002c7e  jg      loc_140002D28
0x140002c84  xor     r9d, r9d; lpArguments
0x140002c87  xor     r8d, r8d; nNumberOfArguments
0x140002c8a  mov     edx, 1; dwExceptionFlags
0x140002c8f  mov     ecx, eax; dwExceptionCode
0x140002c91  call    cs:__imp_RaiseException
0x140002c97  int     3; Trap to Debugger
0x140002c98  xor     r8d, r8d; unsigned int
0x140002c9b  lea     rdx, Format; unsigned __int16 *
0x140002ca2  lea     rcx, [rsp+190h+string]; this
0x140002ca7  call    ?Set@HString@Wrappers@WRL@Microsoft@@QEAAJPEBGI@Z; Microsoft::WRL::Wrappers::HString::Set(ushort const *,uint)
0x140002cac  jmp     loc_140002855
  ... truncated ...
```
