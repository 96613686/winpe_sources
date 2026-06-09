# Catalog::AddWmiGroupAce(IRequestContext &)

- ea: `0x18007965c`
- end: `0x180079b92`
- name: `?AddWmiGroupAce@Catalog@@QEAA_NAEAVIRequestContext@@@Z`
- size: `1334`
- prototype: `bool __fastcall(Catalog *__hidden this, struct IRequestContext *)`
- caller_count: `3`
- callee_count: `12`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800b9850`
- `0x1800ee08c`
- `0x180173484`

## callees

- `0x180008920`
- `0x18000f700`
- `0x180013760`
- `0x1800621e0`
- `0x180062ac4`
- `0x180064250`
- `0x18007965c`
- `0x180079b98`
- `0x1800b5490`
- `0x1801123a8`
- `0x18012e814`
- `0x1801c2010`

## import_xrefs

- `msvcrt!swprintf_s` at `0x180079775`
- `msvcrt!swprintf_s` at `0x180079775`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800797d4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800797fb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800798bf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180079a3d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180079a66`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180079b1c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800797d4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800797fb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800798bf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180079a3d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180079a66`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180079b1c`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x1800799af`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x1800799af`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x180079994`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x180079994`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x180079960`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x180079960`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountNameW` at `0x1800797ce`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountNameW` at `0x180079899`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountNameW` at `0x1800797ce`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountNameW` at `0x180079899`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
char __fastcall Catalog::AddWmiGroupAce(Catalog *this, struct IRequestContext *a2)
{
  PSID *v4; // r13
  DWORD v5; // r12d
  const WCHAR *ComputerNameW; // rsi
  unsigned int v7; // eax
  __int64 v9; // rax
  unsigned __int64 v10; // r15
  __int64 v11; // rax
  wchar_t *v12; // rbx
  DWORD v13; // eax
  char v14; // si
  __int64 v15; // rax
  __int64 v16; // rax
  WCHAR *ReferencedDomainName; // rax
  DWORD v18; // eax
  __int64 i; // rbx
  _QWORD *v20; // r15
  _QWORD *j; // r14
  void **v22; // rbx
  void *v23; // rcx
  struct _ACL *v24; // rcx
  LPVOID v25; // rdx
  LPWSTR v26; // rax
  void (__fastcall *v27)(struct IRequestContext *, _QWORD); // rbx
  DWORD v28; // eax
  void (__fastcall *v29)(struct IRequestContext *, _QWORD); // rbx
  DWORD v30; // eax
  unsigned int v31; // eax
  unsigned int v32; // eax
  void (__fastcall *v33)(struct IRequestContext *, _QWORD); // rbx
  DWORD LastError; // eax
  BOOL bDaclPresent; // [rsp+40h] [rbp-30h] BYREF
  BOOL bDaclDefaulted; // [rsp+44h] [rbp-2Ch] BYREF
  LPVOID pAce; // [rsp+48h] [rbp-28h] BYREF
  WCHAR *v38; // [rsp+50h] [rbp-20h] BYREF
  wchar_t *v39; // [rsp+58h] [rbp-18h] BYREF
  PACL pDacl; // [rsp+60h] [rbp-10h] BYREF
  DWORD cchReferencedDomainName; // [rsp+B0h] [rbp+40h] BYREF
  DWORD cbSid; // [rsp+C0h] [rbp+50h] BYREF
  enum _SID_NAME_USE peUse; // [rsp+C8h] [rbp+58h] BYREF

  v4 = (PSID *)((char *)this + 288);
  AutoCleanup<AutoDeleteVector<unsigned short *>,unsigned short * *>::ReleasePtr((char *)this + 288);
  v5 = 0;
  *v4 = 0;
  cbSid = 0;
  cchReferencedDomainName = 0;
  peUse = 0;
  ComputerNameW = GetComputerNameW(a2);
  if ( !ComputerNameW )
  {
    v7 = (*(__int64 (__fastcall **)(struct IRequestContext *))(*(_QWORD *)a2 + 152LL))(a2);
    if ( v7 == 2 )
      return 1;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 31, &WPP_da7ed40d09913eb0c9debd1bc41fe78b_Traceguids, v7);
    return 0;
  }
  v9 = -1;
  do
    ++v9;
  while ( ComputerNameW[v9] );
  v10 = (unsigned int)(v9 + 23);
  v11 = 2 * v10;
  if ( !is_mul_ok(v10, 2u) )
    v11 = -1;
  v12 = (wchar_t *)WSManMemory::Alloc(v11, 0, 0);
  v39 = v12;
  if ( v12 )
  {
    if ( swprintf_s(v12, v10, L"%ls\\%ls", ComputerNameW, L"WinRMRemoteWMIUsers__") == -1 )
    {
      (*(void (__fastcall **)(struct IRequestContext *, __int64, const wchar_t *, __int64))(*(_QWORD *)a2 + 88LL))(
        a2,
        1077134176,
        L"swprintf_s",
        1359);
LABEL_61:
      v14 = 0;
      goto LABEL_62;
    }
    LookupAccountNameW(ComputerNameW, v12, 0, &cbSid, 0, &cchReferencedDomainName, &peUse);
    if ( GetLastError() == 122 )
    {
      v15 = WSManMemory::Alloc(cbSid, 0, 0);
      AutoDeleteVector<_WINRS_RUN_COMMAND_ARG>::operator=(v4, v15);
      v16 = 2LL * cchReferencedDomainName;
      if ( !is_mul_ok(cchReferencedDomainName, 2u) )
        v16 = -1;
      ReferencedDomainName = (WCHAR *)WSManMemory::Alloc(v16, 0, 0);
      v38 = ReferencedDomainName;
      if ( !*v4 || !ReferencedDomainName )
      {
        (*(void (__fastcall **)(struct IRequestContext *))(*(_QWORD *)a2 + 24LL))(a2);
        AutoCleanup<AutoDeleteVector<unsigned short *>,unsigned short * *>::ReleasePtr(&v38);
        goto LABEL_65;
      }
      if ( LookupAccountNameW(ComputerNameW, v12, *v4, &cbSid, ReferencedDomainName, &cchReferencedDomainName, &peUse) )
      {
        for ( i = *((_QWORD *)this + 1); ; i = *(_QWORD *)(i + 72) )
        {
          v14 = 1;
          if ( !i )
            goto LABEL_63;
          if ( (unsigned int)StringCchEquals(*(const unsigned __int16 **)i, L"WMI Provider") )
            break;
        }
        v20 = *(_QWORD **)(i + 80);
LABEL_34:
        if ( !v20 )
        {
LABEL_63:
          AutoCleanup<AutoDeleteVector<unsigned short *>,unsigned short * *>::ReleasePtr(&v38);
          goto LABEL_62;
        }
        for ( j = (_QWORD *)v20[1]; ; j = (_QWORD *)j[5] )
        {
          if ( !j )
          {
            v20 = (_QWORD *)*v20;
            goto LABEL_34;
          }
          v22 = (void **)(j + 2);
          v23 = (void *)j[2];
          if ( v23 )
          {
            pDacl = 0;
            bDaclPresent = 0;
            bDaclDefaulted = 0;
            if ( !GetSecurityDescriptorDacl(v23, &bDaclPresent, &pDacl, &bDaclDefaulted) )
            {
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) != 0 )
              {
                v32 = (*(__int64 (__fastcall **)(struct IRequestContext *))(*(_QWORD *)a2 + 152LL))(a2);
                WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 34, &WPP_da7ed40d09913eb0c9debd1bc41fe78b_Traceguids, v32);
              }
              v33 = *(void (__fastcall **)(struct IRequestContext *, _QWORD))(*(_QWORD *)a2 + 72LL);
              LastError = GetLastError();
              v33(a2, LastError);
              goto LABEL_60;
            }
            if ( bDaclPresent )
            {
              v24 = pDacl;
              if ( pDacl )
                break;
            }
          }
LABEL_49:
          ;
        }
        while ( 1 )
        {
          pAce = 0;
          if ( !GetAce(v24, v5, &pAce) )
            break;
          if ( !*(_BYTE *)pAce && EqualSid((char *)pAce + 8, *v4) )
          {
            v5 = 0;
            goto LABEL_49;
          }
          ++v5;
          v24 = pDacl;
        }
        v5 = 0;
        pAce = 0;
        if ( (unsigned int)CSecurity::AdjustSecurityDescriptorWithSid(*v22, *v4, 7u, 0, &pAce) )
        {
          v25 = pAce;
          pAce = 0;
          AutoCleanup<AutoLocalFree,void *>::operator=(j + 2, v25);
          v26 = SecurityDescriptorToSDDL((__int64)a2, *v22);
          AutoCleanup<AutoLocalFree,void *>::operator=(j + 3, v26);
          if ( j[3] )
          {
            AutoCleanup<AutoSecurityDescriptor,void *>::~AutoCleanup<AutoSecurityDescriptor,void *>(&pAce);
            goto LABEL_49;
          }
          v27 = *(void (__fastcall **)(struct IRequestContext *, _QWORD))(*(_QWORD *)a2 + 72LL);
          v28 = GetLastError();
          v27(a2, v28);
        }
        else
        {
          v29 = *(void (__fastcall **)(struct IRequestContext *, _QWORD))(*(_QWORD *)a2 + 72LL);
          v30 = GetLastError();
          v29(a2, v30);
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) != 0 )
          {
            v31 = (*(__int64 (__fastcall **)(struct IRequestContext *))(*(_QWORD *)a2 + 152LL))(a2);
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 35, &WPP_da7ed40d09913eb0c9debd1bc41fe78b_Traceguids, v31);
          }
        }
        AutoCleanup<AutoSecurityDescriptor,void *>::~AutoCleanup<AutoSecurityDescriptor,void *>(&pAce);
LABEL_60:
        AutoCleanup<AutoDeleteVector<unsigned short *>,unsigned short * *>::ReleasePtr(&v38);
        goto LABEL_61;
      }
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) != 0 )
      {
        v18 = GetLastError();
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 33, &WPP_da7ed40d09913eb0c9debd1bc41fe78b_Traceguids, v18);
      }
      AutoCleanup<AutoDeleteVector<unsigned short *>,unsigned short * *>::ReleasePtr(&v38);
    }
    else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) != 0 )
    {
      v13 = GetLastError();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 32, &WPP_da7ed40d09913eb0c9debd1bc41fe78b_Traceguids, v13);
    }
    v14 = 1;
LABEL_62:
    AutoCleanup<AutoDeleteVector<unsigned short *>,unsigned short * *>::ReleasePtr(&v39);
    return v14;
  }
  (*(void (__fastcall **)(struct IRequestContext *))(*(_QWORD *)a2 + 24LL))(a2);
LABEL_65:
  AutoCleanup<AutoDeleteVector<unsigned short *>,unsigned short * *>::ReleasePtr(&v39);
  return 0;
}

```

## disassembly

```asm
0x18007965c  mov     [rsp-38h+arg_8], rbx
0x180079661  push    rbp
0x180079662  push    rsi
0x180079663  push    rdi
0x180079664  push    r12
0x180079666  push    r13
0x180079668  push    r14
0x18007966a  push    r15
0x18007966c  mov     rbp, rsp
0x18007966f  sub     rsp, 70h
0x180079673  mov     rdi, rdx
0x180079676  mov     r14, rcx
0x180079679  lea     r13, [rcx+120h]
0x180079680  mov     rcx, r13
0x180079683  call    ?ReleasePtr@?$AutoCleanup@V?$AutoDeleteVector@PEAG@@PEAPEAG@@AEAAXXZ; AutoCleanup<AutoDeleteVector<ushort *>,ushort * *>::ReleasePtr(void)
0x180079688  xor     r12d, r12d
0x18007968b  mov     [r13+0], r12
0x18007968f  mov     [rbp+cbSid], r12d
0x180079693  mov     [rbp+arg_0], r12d
0x180079697  mov     [rbp+arg_18], r12d
0x18007969b  mov     rcx, rdi; struct IRequestContext *
0x18007969e  call    ?GetComputerNameW@@YAPEBGAEAVIRequestContext@@@Z; GetComputerNameW(IRequestContext &)
0x1800796a3  mov     rsi, rax
0x1800796a6  test    rax, rax
0x1800796a9  jnz     short loc_18007970B
0x1800796ab  mov     rax, [rdi]
0x1800796ae  mov     rcx, rdi
0x1800796b1  mov     rax, [rax+98h]
0x1800796b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800796bd  mov     r9d, eax
0x1800796c0  cmp     eax, 2
0x1800796c3  jnz     short loc_1800796CD
0x1800796c5  lea     eax, [rsi+1]
0x1800796c8  jmp     loc_180079B7A
0x1800796cd  lea     rax, WPP_GLOBAL_Control
0x1800796d4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800796db  cmp     rcx, rax
0x1800796de  jz      loc_180079B78
0x1800796e4  test    dword ptr [rcx+1Ch], 40000h
0x1800796eb  jz      loc_180079B78
0x1800796f1  mov     edx, 1Fh
0x1800796f6  lea     r8, WPP_da7ed40d09913eb0c9debd1bc41fe78b_Traceguids
0x1800796fd  mov     rcx, [rcx+10h]
0x180079701  call    WPP_SF_d
0x180079706  jmp     loc_180079B78
0x18007970b  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18007970f  mov     rax, rcx
0x180079712  inc     rax
0x180079715  cmp     [rsi+rax*2], r12w
0x18007971a  jnz     short loc_180079712
0x18007971c  lea     r15d, [rax+17h]
0x180079720  mov     eax, 2
0x180079725  mul     r15
0x180079728  cmovb   rax, rcx
0x18007972c  xor     r8d, r8d
0x18007972f  xor     edx, edx
0x180079731  mov     rcx, rax
0x180079734  call    ?Alloc@WSManMemory@@SAPEAX_KHW4_NitsFaultMode@@@Z; WSManMemory::Alloc(unsigned __int64,int,_NitsFaultMode)
0x180079739  mov     rbx, rax
0x18007973c  mov     [rbp+var_18], rax
0x180079740  test    rax, rax
0x180079743  jnz     short loc_180079759
0x180079745  mov     rax, [rdi]
0x180079748  mov     rcx, rdi
0x18007974b  mov     rax, [rax+18h]
0x18007974f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180079754  jmp     loc_180079B6F
0x180079759  lea     rax, aWinrmremotewmi; "WinRMRemoteWMIUsers__"
0x180079760  mov     [rsp+70h+ReferencedDomainName], rax
0x180079765  mov     r9, rsi
0x180079768  lea     r8, aLsLs; "%ls\\%ls"
0x18007976f  mov     rdx, r15; BufferCount
0x180079772  mov     rcx, rbx; Buffer
0x180079775  call    cs:__imp_swprintf_s
0x18007977b  or      r15, 0FFFFFFFFFFFFFFFFh
0x18007977f  cmp     eax, r15d
0x180079782  jnz     short loc_1800797AA
0x180079784  mov     rax, [rdi]
0x180079787  mov     r9d, 54Fh
0x18007978d  lea     r8, aSwprintfS; "swprintf_s"
0x180079794  mov     edx, 4033C360h
0x180079799  mov     rcx, rdi
0x18007979c  mov     rax, [rax+58h]
0x1800797a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800797a5  jmp     loc_180079B39
0x1800797aa  lea     rax, [rbp+arg_18]
0x1800797ae  mov     [rsp+70h+peUse], rax; peUse
0x1800797b3  lea     rax, [rbp+arg_0]
0x1800797b7  mov     [rsp+70h+cchReferencedDomainName], rax; cchReferencedDomainName
0x1800797bc  mov     [rsp+70h+ReferencedDomainName], r12; ReferencedDomainName
0x1800797c1  lea     r9, [rbp+cbSid]; cbSid
0x1800797c5  xor     r8d, r8d; Sid
0x1800797c8  mov     rdx, rbx; lpAccountName
0x1800797cb  mov     rcx, rsi; lpSystemName
0x1800797ce  call    cs:__imp_LookupAccountNameW
0x1800797d4  call    cs:__imp_GetLastError
0x1800797da  cmp     eax, 7Ah ; 'z'
0x1800797dd  jz      short loc_18007982A
0x1800797df  lea     rax, WPP_GLOBAL_Control
0x1800797e6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800797ed  cmp     rcx, rax
0x1800797f0  jz      short loc_180079820
0x1800797f2  test    dword ptr [rcx+1Ch], 40000h
0x1800797f9  jz      short loc_180079820
0x1800797fb  call    cs:__imp_GetLastError
0x180079801  mov     edx, 20h ; ' '
0x180079806  mov     r9d, eax
0x180079809  lea     r8, WPP_da7ed40d09913eb0c9debd1bc41fe78b_Traceguids
0x180079810  mov     rcx, cs:WPP_GLOBAL_Control
0x180079817  mov     rcx, [rcx+10h]
0x18007981b  call    WPP_SF_d
0x180079820  mov     esi, 1
0x180079825  jmp     loc_180079B3C
0x18007982a  mov     ecx, [rbp+cbSid]
0x18007982d  xor     r8d, r8d
0x180079830  xor     edx, edx
0x180079832  call    ?Alloc@WSManMemory@@SAPEAX_KHW4_NitsFaultMode@@@Z; WSManMemory::Alloc(unsigned __int64,int,_NitsFaultMode)
0x180079837  mov     rdx, rax
0x18007983a  mov     rcx, r13
0x18007983d  call    ??4?$AutoDeleteVector@U_WINRS_RUN_COMMAND_ARG@@@@QEAAAEAV0@PEAU_WINRS_RUN_COMMAND_ARG@@@Z; AutoDeleteVector<_WINRS_RUN_COMMAND_ARG>::operator=(_WINRS_RUN_COMMAND_ARG *)
0x180079842  mov     ecx, [rbp+arg_0]
0x180079845  mov     eax, 2
0x18007984a  mul     rcx
0x18007984d  cmovb   rax, r15
0x180079851  xor     r8d, r8d
0x180079854  xor     edx, edx
0x180079856  mov     rcx, rax
0x180079859  call    ?Alloc@WSManMemory@@SAPEAX_KHW4_NitsFaultMode@@@Z; WSManMemory::Alloc(unsigned __int64,int,_NitsFaultMode)
0x18007985e  mov     [rbp+var_20], rax
0x180079862  mov     r8, [r13+0]; Sid
0x180079866  test    r8, r8
0x180079869  jz      loc_180079B55
0x18007986f  test    rax, rax
0x180079872  jz      loc_180079B55
0x180079878  lea     rcx, [rbp+arg_18]
0x18007987c  mov     [rsp+70h+peUse], rcx; peUse
0x180079881  lea     rcx, [rbp+arg_0]
0x180079885  mov     [rsp+70h+cchReferencedDomainName], rcx; cchReferencedDomainName
0x18007988a  mov     [rsp+70h+ReferencedDomainName], rax; ReferencedDomainName
0x18007988f  lea     r9, [rbp+cbSid]; cbSid
0x180079893  mov     rdx, rbx; lpAccountName
0x180079896  mov     rcx, rsi; lpSystemName
0x180079899  call    cs:__imp_LookupAccountNameW
0x18007989f  test    eax, eax
0x1800798a1  jnz     short loc_1800798F3
0x1800798a3  lea     rax, WPP_GLOBAL_Control
0x1800798aa  mov     rcx, cs:WPP_GLOBAL_Control
0x1800798b1  cmp     rcx, rax
0x1800798b4  jz      short loc_1800798E5
0x1800798b6  test    dword ptr [rcx+1Ch], 40000h
0x1800798bd  jz      short loc_1800798E5
0x1800798bf  call    cs:__imp_GetLastError
0x1800798c5  mov     edx, 21h ; '!'
0x1800798ca  mov     r9d, eax
0x1800798cd  lea     r8, WPP_da7ed40d09913eb0c9debd1bc41fe78b_Traceguids
0x1800798d4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800798db  mov     rcx, [rcx+10h]
0x1800798df  call    WPP_SF_d
0x1800798e4  nop
0x1800798e5  lea     rcx, [rbp+var_20]
0x1800798e9  call    ?ReleasePtr@?$AutoCleanup@V?$AutoDeleteVector@PEAG@@PEAPEAG@@AEAAXXZ; AutoCleanup<AutoDeleteVector<ushort *>,ushort * *>::ReleasePtr(void)
0x1800798ee  jmp     loc_180079820
0x1800798f3  mov     rbx, [r14+8]
0x1800798f7  mov     esi, 1
0x1800798fc  test    rbx, rbx
0x1800798ff  jz      loc_180079B4A
0x180079905  lea     rdx, aWmiProvider; "WMI Provider"
0x18007990c  mov     rcx, [rbx]; unsigned __int16 *
0x18007990f  call    ?StringCchEquals@@YAHPEBG0@Z; StringCchEquals(ushort const *,ushort const *)
0x180079914  test    eax, eax
0x180079916  jnz     short loc_18007991E
0x180079918  mov     rbx, [rbx+48h]
0x18007991c  jmp     short loc_1800798F7
0x18007991e  mov     r15, [rbx+50h]
0x180079922  test    r15, r15
0x180079925  jz      loc_180079B4A
0x18007992b  mov     r14, [r15+8]
0x18007992f  test    r14, r14
0x180079932  jz      loc_180079A2E
0x180079938  lea     rbx, [r14+10h]
0x18007993c  mov     rcx, [rbx]; pSecurityDescriptor
0x18007993f  test    rcx, rcx
0x180079942  jz      loc_180079A25
0x180079948  mov     [rbp+pDacl], r12
0x18007994c  mov     [rbp+bDaclPresent], r12d
0x180079950  mov     [rbp+bDaclDefaulted], r12d
0x180079954  lea     r9, [rbp+bDaclDefaulted]; lpbDaclDefaulted
0x180079958  lea     r8, [rbp+pDacl]; pDacl
0x18007995c  lea     rdx, [rbp+bDaclPresent]; lpbDaclPresent
0x180079960  call    cs:__imp_GetSecurityDescriptorDacl
0x180079966  test    eax, eax
0x180079968  jz      loc_180079AC8
0x18007996e  cmp     [rbp+bDaclPresent], r12d
0x180079972  jz      loc_180079A25
0x180079978  mov     rcx, [rbp+pDacl]; pAcl
0x18007997c  test    rcx, rcx
0x18007997f  jz      loc_180079A25
0x180079985  mov     [rbp+pAce], 0
0x18007998d  lea     r8, [rbp+pAce]; pAce
0x180079991  mov     edx, r12d; dwAceIndex
0x180079994  call    cs:__imp_GetAce
0x18007999a  test    eax, eax
0x18007999c  jz      short loc_1800799C2
0x18007999e  mov     rcx, [rbp+pAce]
0x1800799a2  cmp     byte ptr [rcx], 0
0x1800799a5  jnz     short loc_1800799B9
0x1800799a7  add     rcx, 8; pSid1
0x1800799ab  mov     rdx, [r13+0]; pSid2
0x1800799af  call    cs:__imp_EqualSid
0x1800799b5  test    eax, eax
0x1800799b7  jnz     short loc_180079A22
0x1800799b9  add     r12d, esi
0x1800799bc  mov     rcx, [rbp+pDacl]
0x1800799c0  jmp     short loc_180079985
0x1800799c2  xor     r12d, r12d
0x1800799c5  mov     [rbp+pAce], r12
0x1800799c9  lea     rax, [rbp+pAce]
0x1800799cd  mov     [rsp+70h+ReferencedDomainName], rax; struct AutoSecurityDescriptor *
0x1800799d2  xor     r9d, r9d; unsigned int
0x1800799d5  lea     r8d, [r12+7]; unsigned int
0x1800799da  mov     rdx, [r13+0]; pSid
0x1800799de  mov     rcx, [rbx]; pSelfRelativeSecurityDescriptor
0x1800799e1  call    ?AdjustSecurityDescriptorWithSid@CSecurity@@SAHPEAX0KKAEAVAutoSecurityDescriptor@@@Z; CSecurity::AdjustSecurityDescriptorWithSid(void *,void *,ulong,ulong,AutoSecurityDescriptor &)
0x1800799e6  test    eax, eax
0x1800799e8  jz      short loc_180079A5F
0x1800799ea  mov     rdx, [rbp+pAce]
0x1800799ee  mov     [rbp+pAce], r12
0x1800799f2  mov     rcx, rbx
0x1800799f5  call    ??4?$AutoCleanup@VAutoLocalFree@@PEAX@@QEAAAEAVAutoLocalFree@@PEAX@Z; AutoCleanup<AutoLocalFree,void *>::operator=(void *)
0x1800799fa  mov     rdx, [rbx]
0x1800799fd  mov     rcx, rdi
0x180079a00  call    SecurityDescriptorToSDDL
0x180079a05  mov     rdx, rax
0x180079a08  lea     rcx, [r14+18h]
0x180079a0c  call    ??4?$AutoCleanup@VAutoLocalFree@@PEAX@@QEAAAEAVAutoLocalFree@@PEAX@Z; AutoCleanup<AutoLocalFree,void *>::operator=(void *)
0x180079a11  cmp     [r14+18h], r12
0x180079a15  jz      short loc_180079A36
0x180079a17  lea     rcx, [rbp+pAce]; void *
0x180079a1b  call    ??1?$AutoCleanup@VAutoSecurityDescriptor@@PEAX@@QEAA@XZ; AutoCleanup<AutoSecurityDescriptor,void *>::~AutoCleanup<AutoSecurityDescriptor,void *>(void)
0x180079a20  jmp     short loc_180079A25
0x180079a22  xor     r12d, r12d
0x180079a25  mov     r14, [r14+28h]
0x180079a29  jmp     loc_18007992F
0x180079a2e  mov     r15, [r15]
0x180079a31  jmp     loc_180079922
0x180079a36  mov     rax, [rdi]
0x180079a39  mov     rbx, [rax+48h]
0x180079a3d  call    cs:__imp_GetLastError
0x180079a43  mov     edx, eax
0x180079a45  mov     rcx, rdi
0x180079a48  mov     rax, rbx
0x180079a4b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180079a50  nop
0x180079a51  lea     rcx, [rbp+pAce]; void *
0x180079a55  call    ??1?$AutoCleanup@VAutoSecurityDescriptor@@PEAX@@QEAA@XZ; AutoCleanup<AutoSecurityDescriptor,void *>::~AutoCleanup<AutoSecurityDescriptor,void *>(void)
0x180079a5a  jmp     loc_180079B30
0x180079a5f  mov     rax, [rdi]
0x180079a62  mov     rbx, [rax+48h]
0x180079a66  call    cs:__imp_GetLastError
0x180079a6c  mov     edx, eax
0x180079a6e  mov     rcx, rdi
0x180079a71  mov     rax, rbx
0x180079a74  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180079a79  lea     rax, WPP_GLOBAL_Control
0x180079a80  mov     rcx, cs:WPP_GLOBAL_Control
0x180079a87  cmp     rcx, rax
0x180079a8a  jz      short loc_180079A51
0x180079a8c  test    dword ptr [rcx+1Ch], 40000h
0x180079a93  jz      short loc_180079A51
0x180079a95  mov     rax, [rdi]
0x180079a98  mov     rcx, rdi
0x180079a9b  mov     rax, [rax+98h]
0x180079aa2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180079aa7  mov     edx, 23h ; '#'
0x180079aac  mov     r9d, eax
0x180079aaf  lea     r8, WPP_da7ed40d09913eb0c9debd1bc41fe78b_Traceguids
0x180079ab6  mov     rcx, cs:WPP_GLOBAL_Control
0x180079abd  mov     rcx, [rcx+10h]
0x180079ac1  call    WPP_SF_d
0x180079ac6  jmp     short loc_180079A51
0x180079ac8  lea     rax, WPP_GLOBAL_Control
0x180079acf  mov     rcx, cs:WPP_GLOBAL_Control
0x180079ad6  cmp     rcx, rax
0x180079ad9  jz      short loc_180079B15
0x180079adb  test    dword ptr [rcx+1Ch], 40000h
0x180079ae2  jz      short loc_180079B15
0x180079ae4  mov     rax, [rdi]
0x180079ae7  mov     rcx, rdi
0x180079aea  mov     rax, [rax+98h]
0x180079af1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180079af6  mov     edx, 22h ; '"'
0x180079afb  mov     r9d, eax
0x180079afe  lea     r8, WPP_da7ed40d09913eb0c9debd1bc41fe78b_Traceguids
0x180079b05  mov     rcx, cs:WPP_GLOBAL_Control
0x180079b0c  mov     rcx, [rcx+10h]
0x180079b10  call    WPP_SF_d
0x180079b15  mov     rax, [rdi]
0x180079b18  mov     rbx, [rax+48h]
0x180079b1c  call    cs:__imp_GetLastError
0x180079b22  mov     edx, eax
  ... truncated ...
```
