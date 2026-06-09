# CSecurity::AdjustSecurityDescriptorWithNewAcls(_SECURITY_DESCRIPTOR *,_ACL *,_ACL *,void * *)

- ea: `0x18012636c`
- end: `0x18012689a`
- name: `?AdjustSecurityDescriptorWithNewAcls@CSecurity@@SAHPEAU_SECURITY_DESCRIPTOR@@PEAU_ACL@@1PEAPEAX@Z`
- size: `1326`
- prototype: `__int64 __fastcall(PSECURITY_DESCRIPTOR pSelfRelativeSecurityDescriptor, struct _ACL *, struct _ACL *, void **)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18012a480`

## callees

- `0x180005d10`
- `0x180008920`
- `0x180013760`
- `0x1800621e0`
- `0x180112380`
- `0x1801123a8`
- `0x18012636c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18012684e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18012684e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180126493`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801264bb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801265ee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18012666d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801266bb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180126703`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180126726`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801267db`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180126493`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801264bb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801265ee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18012666d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801266bb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180126703`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180126726`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801267db`
- `api-ms-win-security-base-l1-1-0!MakeAbsoluteSD` at `0x18012648b`
- `api-ms-win-security-base-l1-1-0!MakeAbsoluteSD` at `0x18012663f`
- `api-ms-win-security-base-l1-1-0!MakeAbsoluteSD` at `0x18012648b`
- `api-ms-win-security-base-l1-1-0!MakeAbsoluteSD` at `0x18012663f`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x1801265c0`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x1801265c0`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x18012668d`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x18012668d`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorSacl` at `0x1801266d5`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorSacl` at `0x1801266d5`
- `api-ms-win-security-base-l1-1-0!MakeSelfRelativeSD` at `0x18012671e`
- `api-ms-win-security-base-l1-1-0!MakeSelfRelativeSD` at `0x1801267b5`
- `api-ms-win-security-base-l1-1-0!MakeSelfRelativeSD` at `0x18012671e`
- `api-ms-win-security-base-l1-1-0!MakeSelfRelativeSD` at `0x1801267b5`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalAlloc` at `0x180126798`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalAlloc` at `0x180126798`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x180126804`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x180126804`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall CSecurity::AdjustSecurityDescriptorWithNewAcls(
        PSECURITY_DESCRIPTOR pSelfRelativeSecurityDescriptor,
        struct _ACL *a2,
        struct _ACL *a3,
        void **a4)
{
  const unsigned __int16 *v6; // r8
  __int64 v7; // rdx
  BOOL AbsoluteSD; // ebx
  DWORD LastError; // eax
  DWORD v10; // eax
  __int64 v11; // rdx
  _QWORD *v12; // rcx
  __int64 v13; // rax
  __int64 v14; // rax
  __int64 v15; // rax
  __int64 v16; // rax
  __int64 v17; // rax
  struct _ACL *pSacl; // rdi
  PSID pOwner; // rsi
  PSID pPrimaryGroup; // r14
  PSECURITY_DESCRIPTOR v21; // rbx
  BOOL SelfRelativeSD; // edi
  HLOCAL v23; // rax
  DWORD v24; // eax
  PACL pDacl; // [rsp+60h] [rbp-19h] BYREF
  PSID v27; // [rsp+68h] [rbp-11h] BYREF
  PSID v28; // [rsp+70h] [rbp-9h] BYREF
  PACL v29; // [rsp+78h] [rbp-1h] BYREF
  PSECURITY_DESCRIPTOR pSecurityDescriptor; // [rsp+80h] [rbp+7h] BYREF
  DWORD dwOwnerSize; // [rsp+88h] [rbp+Fh] BYREF
  DWORD dwSaclSize; // [rsp+8Ch] [rbp+13h] BYREF
  DWORD dwDaclSize; // [rsp+90h] [rbp+17h] BYREF
  DWORD dwAbsoluteSecurityDescriptorSize; // [rsp+94h] [rbp+1Bh] BYREF
  DWORD dwBufferLength[14]; // [rsp+98h] [rbp+1Fh] BYREF
  DWORD dwPrimaryGroupSize; // [rsp+F8h] [rbp+7Fh] BYREF

  if ( a4 )
  {
    if ( !a2 )
    {
      v6 = L"931";
      v7 = 931;
      goto LABEL_3;
    }
    if ( !pSelfRelativeSecurityDescriptor )
    {
      v6 = L"932";
      v7 = 932;
      goto LABEL_3;
    }
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000000) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 42, WPP_5b789da118f632ad9796e014c1252c4d_Traceguids);
    dwBufferLength[0] = 0;
    pSecurityDescriptor = 0;
    dwAbsoluteSecurityDescriptorSize = 40;
    pDacl = 0;
    v29 = 0;
    v28 = 0;
    v27 = 0;
    dwDaclSize = 0;
    dwSaclSize = 0;
    dwOwnerSize = 0;
    dwPrimaryGroupSize = 0;
    AbsoluteSD = MakeAbsoluteSD(
                   pSelfRelativeSecurityDescriptor,
                   0,
                   &dwAbsoluteSecurityDescriptorSize,
                   0,
                   &dwDaclSize,
                   0,
                   &dwSaclSize,
                   0,
                   &dwOwnerSize,
                   0,
                   &dwPrimaryGroupSize);
    LastError = GetLastError();
    if ( AbsoluteSD )
    {
      if ( LastError != 122 )
      {
        WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\stdlib\\sec.cpp", 965, L"965", 0x54Fu, 0);
        goto LABEL_57;
      }
    }
    else if ( LastError != 122 )
    {
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000000) == 0 )
        goto LABEL_57;
      v10 = GetLastError();
      v11 = 43;
      goto LABEL_16;
    }
    v13 = WSManMemory::Alloc(dwDaclSize, 0, 0);
    AutoDeleteVector<_WINRS_RUN_COMMAND_ARG>::operator=(&pDacl, v13);
    v14 = WSManMemory::Alloc(dwSaclSize, 0, 0);
    AutoDeleteVector<_WINRS_RUN_COMMAND_ARG>::operator=(&v29, v14);
    v15 = WSManMemory::Alloc(dwOwnerSize, 0, 0);
    AutoDeleteVector<_WINRS_RUN_COMMAND_ARG>::operator=(&v28, v15);
    v16 = WSManMemory::Alloc(dwPrimaryGroupSize, 0, 0);
    AutoDeleteVector<_WINRS_RUN_COMMAND_ARG>::operator=(&v27, v16);
    v17 = WSManMemory::Alloc(dwAbsoluteSecurityDescriptorSize, 0, 0);
    AutoDeleteVector<_WINRS_RUN_COMMAND_ARG>::operator=(&pSecurityDescriptor, v17);
    if ( pDacl )
    {
      pSacl = v29;
      if ( v29 )
      {
        pOwner = v28;
        if ( v28 )
        {
          pPrimaryGroup = v27;
          if ( v27 )
          {
            v21 = pSecurityDescriptor;
            if ( pSecurityDescriptor )
            {
              if ( !InitializeSecurityDescriptor(pSecurityDescriptor, 1u) )
              {
                if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
                  || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000000) == 0 )
                {
                  goto LABEL_57;
                }
                v10 = GetLastError();
                v11 = 44;
                goto LABEL_16;
              }
              if ( !MakeAbsoluteSD(
                      pSelfRelativeSecurityDescriptor,
                      v21,
                      &dwAbsoluteSecurityDescriptorSize,
                      pDacl,
                      &dwDaclSize,
                      pSacl,
                      &dwSaclSize,
                      pOwner,
                      &dwOwnerSize,
                      pPrimaryGroup,
                      &dwPrimaryGroupSize) )
              {
                if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
                  || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000000) == 0 )
                {
                  goto LABEL_57;
                }
                v10 = GetLastError();
                v11 = 45;
                goto LABEL_16;
              }
              if ( !SetSecurityDescriptorDacl(v21, 1, a2, 0) )
              {
                if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
                  || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000000) == 0 )
                {
                  goto LABEL_57;
                }
                v10 = GetLastError();
                v11 = 46;
                goto LABEL_16;
              }
              if ( !SetSecurityDescriptorSacl(v21, 1, a3, 0) )
              {
                if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
                  || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000000) == 0 )
                {
                  goto LABEL_57;
                }
                v10 = GetLastError();
                v11 = 47;
LABEL_16:
                v12 = WPP_GLOBAL_Control;
LABEL_46:
                WPP_SF_d(v12[2], v11, WPP_5b789da118f632ad9796e014c1252c4d_Traceguids, v10);
LABEL_57:
                AutoCleanup<AutoDeleteVector<unsigned short *>,unsigned short * *>::ReleasePtr(&v27);
                AutoCleanup<AutoDeleteVector<unsigned short *>,unsigned short * *>::ReleasePtr(&v28);
                AutoCleanup<AutoDeleteVector<unsigned short *>,unsigned short * *>::ReleasePtr(&v29);
                AutoCleanup<AutoDeleteVector<unsigned short *>,unsigned short * *>::ReleasePtr(&pDacl);
                AutoCleanup<AutoDeleteVector<unsigned short *>,unsigned short * *>::ReleasePtr(&pSecurityDescriptor);
                return 0;
              }
              SelfRelativeSD = MakeSelfRelativeSD(v21, *a4, dwBufferLength);
              v10 = GetLastError();
              if ( SelfRelativeSD )
              {
                if ( v10 != 122 )
                {
                  WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\stdlib\\sec.cpp", 1025, L"1025", 0x54Fu, 0);
                  goto LABEL_57;
                }
              }
              else if ( v10 != 122 )
              {
                v12 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
                  || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000000) == 0 )
                {
                  goto LABEL_57;
                }
                v11 = 48;
                goto LABEL_46;
              }
              v23 = LocalAlloc(0, dwBufferLength[0]);
              *a4 = v23;
              if ( v23 )
              {
                if ( MakeSelfRelativeSD(v21, v23, dwBufferLength) )
                {
                  AutoCleanup<AutoDeleteVector<unsigned short *>,unsigned short * *>::ReleasePtr(&v27);
                  AutoCleanup<AutoDeleteVector<unsigned short *>,unsigned short * *>::ReleasePtr(&v28);
                  AutoCleanup<AutoDeleteVector<unsigned short *>,unsigned short * *>::ReleasePtr(&v29);
                  AutoCleanup<AutoDeleteVector<unsigned short *>,unsigned short * *>::ReleasePtr(&pDacl);
                  AutoCleanup<AutoDeleteVector<unsigned short *>,unsigned short * *>::ReleasePtr(&pSecurityDescriptor);
                  return 1;
                }
                if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                  && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000000) != 0 )
                {
                  v24 = GetLastError();
                  WPP_SF_d(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    49,
                    WPP_5b789da118f632ad9796e014c1252c4d_Traceguids,
                    v24);
                }
                LocalFree(*a4);
                *a4 = 0;
                goto LABEL_57;
              }
            }
          }
        }
      }
    }
    SetLastError(0xEu);
    goto LABEL_57;
  }
  v6 = L"930";
  v7 = 930;
LABEL_3:
  WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\stdlib\\sec.cpp", v7, v6, 0x54Fu, 0);
  return 0;
}

```

## disassembly

```asm
0x18012636c  mov     [rsp-8+arg_10], r8
0x180126371  mov     [rsp-8+arg_8], rdx
0x180126376  push    rbp
0x180126377  push    rbx
0x180126378  push    rsi
0x180126379  push    rdi
0x18012637a  push    r12
0x18012637c  push    r13
0x18012637e  push    r14
0x180126380  lea     rbp, [rsp-27h]
0x180126385  sub     rsp, 0A0h
0x18012638c  mov     r12, r9
0x18012638f  mov     rax, rdx
0x180126392  mov     r13, rcx
0x180126395  xor     r14d, r14d
0x180126398  test    r9, r9
0x18012639b  jnz     short loc_1801263C5
0x18012639d  lea     r8, a930; "930"
0x1801263a4  mov     edx, 3A2h; unsigned int
0x1801263a9  mov     [rsp+0D0h+lpdwDaclSize], r14; struct IRequestContext *
0x1801263ae  mov     r9d, 54Fh; unsigned int
0x1801263b4  lea     rcx, aOnecoreAdminWm_142; "onecore\\admin\\wmi\\wmx\\stdlib\\sec.c"...
0x1801263bb  call    ?WSManError@@YAXPEBGK0KPEAVIRequestContext@@@Z; WSManError(ushort const *,ulong,ushort const *,ulong,IRequestContext *)
0x1801263c0  jmp     loc_180126886
0x1801263c5  test    rax, rax
0x1801263c8  jnz     short loc_1801263D8
0x1801263ca  lea     r8, a931; "931"
0x1801263d1  mov     edx, 3A3h
0x1801263d6  jmp     short loc_1801263A9
0x1801263d8  test    r13, r13
0x1801263db  jnz     short loc_1801263EB
0x1801263dd  lea     r8, a932; "932"
0x1801263e4  mov     edx, 3A4h
0x1801263e9  jmp     short loc_1801263A9
0x1801263eb  lea     rsi, WPP_GLOBAL_Control
0x1801263f2  mov     edi, 10000000h
0x1801263f7  mov     rcx, cs:WPP_GLOBAL_Control
0x1801263fe  cmp     rcx, rsi
0x180126401  jz      short loc_18012641D
0x180126403  test    [rcx+1Ch], edi
0x180126406  jz      short loc_18012641D
0x180126408  mov     edx, 2Ah ; '*'
0x18012640d  lea     r8, WPP_5b789da118f632ad9796e014c1252c4d_Traceguids
0x180126414  mov     rcx, [rcx+10h]
0x180126418  call    WPP_SF_
0x18012641d  mov     [rbp+57h+dwBufferLength], r14d
0x180126421  mov     [rbp+57h+pSecurityDescriptor], r14
0x180126425  mov     [rbp+57h+dwAbsoluteSecurityDescriptorSize], 28h ; '('
0x18012642c  mov     [rbp+57h+pDacl], r14
0x180126430  mov     [rbp+57h+var_58], r14
0x180126434  mov     [rbp+57h+var_60], r14
0x180126438  mov     [rbp+57h+var_68], r14
0x18012643c  mov     [rbp+57h+dwDaclSize], r14d
0x180126440  mov     [rbp+57h+dwSaclSize], r14d
0x180126444  mov     [rbp+57h+dwOwnerSize], r14d
0x180126448  mov     [rbp+57h+dwPrimaryGroupSize], r14d
0x18012644c  lea     rax, [rbp+57h+dwPrimaryGroupSize]
0x180126450  mov     [rsp+0D0h+lpdwPrimaryGroupSize], rax; lpdwPrimaryGroupSize
0x180126455  mov     [rsp+0D0h+pPrimaryGroup], r14; pPrimaryGroup
0x18012645a  lea     rax, [rbp+57h+dwOwnerSize]
0x18012645e  mov     [rsp+0D0h+lpdwOwnerSize], rax; lpdwOwnerSize
0x180126463  mov     [rsp+0D0h+pOwner], r14; pOwner
0x180126468  lea     rax, [rbp+57h+dwSaclSize]
0x18012646c  mov     [rsp+0D0h+lpdwSaclSize], rax; lpdwSaclSize
0x180126471  mov     [rsp+0D0h+pSacl], r14; pSacl
0x180126476  lea     rax, [rbp+57h+dwDaclSize]
0x18012647a  mov     [rsp+0D0h+lpdwDaclSize], rax; lpdwDaclSize
0x18012647f  xor     r9d, r9d; pDacl
0x180126482  lea     r8, [rbp+57h+dwAbsoluteSecurityDescriptorSize]; lpdwAbsoluteSecurityDescriptorSize
0x180126486  xor     edx, edx; pAbsoluteSecurityDescriptor
0x180126488  mov     rcx, r13; pSelfRelativeSecurityDescriptor
0x18012648b  call    cs:__imp_MakeAbsoluteSD
0x180126491  mov     ebx, eax
0x180126493  call    cs:__imp_GetLastError
0x180126499  test    ebx, ebx
0x18012649b  jnz     short loc_1801264D0
0x18012649d  cmp     eax, 7Ah ; 'z'
0x1801264a0  jz      short loc_1801264FD
0x1801264a2  mov     rax, cs:WPP_GLOBAL_Control
0x1801264a9  cmp     rax, rsi
0x1801264ac  jz      loc_180126855
0x1801264b2  test    [rax+1Ch], edi
0x1801264b5  jz      loc_180126855
0x1801264bb  call    cs:__imp_GetLastError
0x1801264c1  lea     edx, [rbx+2Bh]
0x1801264c4  mov     rcx, cs:WPP_GLOBAL_Control
0x1801264cb  jmp     loc_18012675C
0x1801264d0  cmp     eax, 7Ah ; 'z'
0x1801264d3  jz      short loc_1801264FD
0x1801264d5  mov     [rsp+0D0h+lpdwDaclSize], r14; struct IRequestContext *
0x1801264da  lea     r8, a965; "965"
0x1801264e1  mov     edx, 3C5h; unsigned int
0x1801264e6  mov     r9d, 54Fh; unsigned int
0x1801264ec  lea     rcx, aOnecoreAdminWm_142; "onecore\\admin\\wmi\\wmx\\stdlib\\sec.c"...
0x1801264f3  call    ?WSManError@@YAXPEBGK0KPEAVIRequestContext@@@Z; WSManError(ushort const *,ulong,ushort const *,ulong,IRequestContext *)
0x1801264f8  jmp     loc_180126855
0x1801264fd  mov     ecx, [rbp+57h+dwDaclSize]
0x180126500  xor     r8d, r8d
0x180126503  xor     edx, edx
0x180126505  call    ?Alloc@WSManMemory@@SAPEAX_KHW4_NitsFaultMode@@@Z; WSManMemory::Alloc(unsigned __int64,int,_NitsFaultMode)
0x18012650a  mov     rdx, rax
0x18012650d  lea     rcx, [rbp+57h+pDacl]
0x180126511  call    ??4?$AutoDeleteVector@U_WINRS_RUN_COMMAND_ARG@@@@QEAAAEAV0@PEAU_WINRS_RUN_COMMAND_ARG@@@Z; AutoDeleteVector<_WINRS_RUN_COMMAND_ARG>::operator=(_WINRS_RUN_COMMAND_ARG *)
0x180126516  mov     ecx, [rbp+57h+dwSaclSize]
0x180126519  xor     r8d, r8d
0x18012651c  xor     edx, edx
0x18012651e  call    ?Alloc@WSManMemory@@SAPEAX_KHW4_NitsFaultMode@@@Z; WSManMemory::Alloc(unsigned __int64,int,_NitsFaultMode)
0x180126523  mov     rdx, rax
0x180126526  lea     rcx, [rbp+57h+var_58]
0x18012652a  call    ??4?$AutoDeleteVector@U_WINRS_RUN_COMMAND_ARG@@@@QEAAAEAV0@PEAU_WINRS_RUN_COMMAND_ARG@@@Z; AutoDeleteVector<_WINRS_RUN_COMMAND_ARG>::operator=(_WINRS_RUN_COMMAND_ARG *)
0x18012652f  mov     ecx, [rbp+57h+dwOwnerSize]
0x180126532  xor     r8d, r8d
0x180126535  xor     edx, edx
0x180126537  call    ?Alloc@WSManMemory@@SAPEAX_KHW4_NitsFaultMode@@@Z; WSManMemory::Alloc(unsigned __int64,int,_NitsFaultMode)
0x18012653c  mov     rdx, rax
0x18012653f  lea     rcx, [rbp+57h+var_60]
0x180126543  call    ??4?$AutoDeleteVector@U_WINRS_RUN_COMMAND_ARG@@@@QEAAAEAV0@PEAU_WINRS_RUN_COMMAND_ARG@@@Z; AutoDeleteVector<_WINRS_RUN_COMMAND_ARG>::operator=(_WINRS_RUN_COMMAND_ARG *)
0x180126548  mov     ecx, [rbp+57h+dwPrimaryGroupSize]
0x18012654b  xor     r8d, r8d
0x18012654e  xor     edx, edx
0x180126550  call    ?Alloc@WSManMemory@@SAPEAX_KHW4_NitsFaultMode@@@Z; WSManMemory::Alloc(unsigned __int64,int,_NitsFaultMode)
0x180126555  mov     rdx, rax
0x180126558  lea     rcx, [rbp+57h+var_68]
0x18012655c  call    ??4?$AutoDeleteVector@U_WINRS_RUN_COMMAND_ARG@@@@QEAAAEAV0@PEAU_WINRS_RUN_COMMAND_ARG@@@Z; AutoDeleteVector<_WINRS_RUN_COMMAND_ARG>::operator=(_WINRS_RUN_COMMAND_ARG *)
0x180126561  mov     ecx, [rbp+57h+dwAbsoluteSecurityDescriptorSize]
0x180126564  xor     r8d, r8d
0x180126567  xor     edx, edx
0x180126569  call    ?Alloc@WSManMemory@@SAPEAX_KHW4_NitsFaultMode@@@Z; WSManMemory::Alloc(unsigned __int64,int,_NitsFaultMode)
0x18012656e  mov     rdx, rax
0x180126571  lea     rcx, [rbp+57h+pSecurityDescriptor]
0x180126575  call    ??4?$AutoDeleteVector@U_WINRS_RUN_COMMAND_ARG@@@@QEAAAEAV0@PEAU_WINRS_RUN_COMMAND_ARG@@@Z; AutoDeleteVector<_WINRS_RUN_COMMAND_ARG>::operator=(_WINRS_RUN_COMMAND_ARG *)
0x18012657a  cmp     [rbp+57h+pDacl], r14
0x18012657e  jz      loc_180126849
0x180126584  mov     rdi, [rbp+57h+var_58]
0x180126588  test    rdi, rdi
0x18012658b  jz      loc_180126849
0x180126591  mov     rsi, [rbp+57h+var_60]
0x180126595  test    rsi, rsi
0x180126598  jz      loc_180126849
0x18012659e  mov     r14, [rbp+57h+var_68]
0x1801265a2  test    r14, r14
0x1801265a5  jz      loc_180126849
0x1801265ab  mov     rbx, [rbp+57h+pSecurityDescriptor]
0x1801265af  test    rbx, rbx
0x1801265b2  jz      loc_180126849
0x1801265b8  mov     edx, 1; dwRevision
0x1801265bd  mov     rcx, rbx; pSecurityDescriptor
0x1801265c0  call    cs:__imp_InitializeSecurityDescriptor
0x1801265c6  test    eax, eax
0x1801265c8  jnz     short loc_1801265FE
0x1801265ca  mov     rax, cs:WPP_GLOBAL_Control
0x1801265d1  lea     rdx, WPP_GLOBAL_Control
0x1801265d8  cmp     rax, rdx
0x1801265db  jz      loc_180126855
0x1801265e1  test    dword ptr [rax+1Ch], 10000000h
0x1801265e8  jz      loc_180126855
0x1801265ee  call    cs:__imp_GetLastError
0x1801265f4  mov     edx, 2Ch ; ','
0x1801265f9  jmp     loc_1801264C4
0x1801265fe  lea     rax, [rbp+57h+dwPrimaryGroupSize]
0x180126602  mov     [rsp+0D0h+lpdwPrimaryGroupSize], rax; lpdwPrimaryGroupSize
0x180126607  mov     [rsp+0D0h+pPrimaryGroup], r14; pPrimaryGroup
0x18012660c  lea     rax, [rbp+57h+dwOwnerSize]
0x180126610  mov     [rsp+0D0h+lpdwOwnerSize], rax; lpdwOwnerSize
0x180126615  mov     [rsp+0D0h+pOwner], rsi; pOwner
0x18012661a  lea     rax, [rbp+57h+dwSaclSize]
0x18012661e  mov     [rsp+0D0h+lpdwSaclSize], rax; lpdwSaclSize
0x180126623  mov     [rsp+0D0h+pSacl], rdi; pSacl
0x180126628  lea     rax, [rbp+57h+dwDaclSize]
0x18012662c  mov     [rsp+0D0h+lpdwDaclSize], rax; lpdwDaclSize
0x180126631  mov     r9, [rbp+57h+pDacl]; pDacl
0x180126635  lea     r8, [rbp+57h+dwAbsoluteSecurityDescriptorSize]; lpdwAbsoluteSecurityDescriptorSize
0x180126639  mov     rdx, rbx; pAbsoluteSecurityDescriptor
0x18012663c  mov     rcx, r13; pSelfRelativeSecurityDescriptor
0x18012663f  call    cs:__imp_MakeAbsoluteSD
0x180126645  test    eax, eax
0x180126647  jnz     short loc_18012667D
0x180126649  mov     rax, cs:WPP_GLOBAL_Control
0x180126650  lea     rdx, WPP_GLOBAL_Control
0x180126657  cmp     rax, rdx
0x18012665a  jz      loc_180126855
0x180126660  test    dword ptr [rax+1Ch], 10000000h
0x180126667  jz      loc_180126855
0x18012666d  call    cs:__imp_GetLastError
0x180126673  mov     edx, 2Dh ; '-'
0x180126678  jmp     loc_1801264C4
0x18012667d  xor     r9d, r9d; bDaclDefaulted
0x180126680  mov     r8, [rbp+57h+arg_8]; pDacl
0x180126684  lea     esi, [r9+1]
0x180126688  mov     edx, esi; bDaclPresent
0x18012668a  mov     rcx, rbx; pSecurityDescriptor
0x18012668d  call    cs:__imp_SetSecurityDescriptorDacl
0x180126693  test    eax, eax
0x180126695  jnz     short loc_1801266C9
0x180126697  mov     rax, cs:WPP_GLOBAL_Control
0x18012669e  lea     rdx, WPP_GLOBAL_Control
0x1801266a5  cmp     rax, rdx
0x1801266a8  jz      loc_180126855
0x1801266ae  test    dword ptr [rax+1Ch], 10000000h
0x1801266b5  jz      loc_180126855
0x1801266bb  call    cs:__imp_GetLastError
0x1801266c1  lea     edx, [rsi+2Dh]
0x1801266c4  jmp     loc_1801264C4
0x1801266c9  xor     r9d, r9d; bSaclDefaulted
0x1801266cc  mov     r8, [rbp+57h+arg_10]; pSacl
0x1801266d0  mov     edx, esi; bSaclPresent
0x1801266d2  mov     rcx, rbx; pSecurityDescriptor
0x1801266d5  call    cs:__imp_SetSecurityDescriptorSacl
0x1801266db  test    eax, eax
0x1801266dd  jnz     short loc_180126713
0x1801266df  mov     rax, cs:WPP_GLOBAL_Control
0x1801266e6  lea     rdx, WPP_GLOBAL_Control
0x1801266ed  cmp     rax, rdx
0x1801266f0  jz      loc_180126855
0x1801266f6  test    dword ptr [rax+1Ch], 10000000h
0x1801266fd  jz      loc_180126855
0x180126703  call    cs:__imp_GetLastError
0x180126709  mov     edx, 2Fh ; '/'
0x18012670e  jmp     loc_1801264C4
0x180126713  lea     r8, [rbp+57h+dwBufferLength]; lpdwBufferLength
0x180126717  mov     rdx, [r12]; pSelfRelativeSecurityDescriptor
0x18012671b  mov     rcx, rbx; pAbsoluteSecurityDescriptor
0x18012671e  call    cs:__imp_MakeSelfRelativeSD
0x180126724  mov     edi, eax
0x180126726  call    cs:__imp_GetLastError
0x18012672c  test    edi, edi
0x18012672e  jnz     short loc_180126774
0x180126730  cmp     eax, 7Ah ; 'z'
0x180126733  jz      short loc_180126793
0x180126735  mov     rcx, cs:WPP_GLOBAL_Control
0x18012673c  lea     rdx, WPP_GLOBAL_Control
0x180126743  cmp     rcx, rdx
0x180126746  jz      loc_180126855
0x18012674c  test    dword ptr [rcx+1Ch], 10000000h
0x180126753  jz      loc_180126855
0x180126759  lea     edx, [rdi+30h]
0x18012675c  mov     r9d, eax
0x18012675f  lea     r8, WPP_5b789da118f632ad9796e014c1252c4d_Traceguids
0x180126766  mov     rcx, [rcx+10h]
0x18012676a  call    WPP_SF_d
0x18012676f  jmp     loc_180126855
0x180126774  cmp     eax, 7Ah ; 'z'
0x180126777  jz      short loc_180126793
0x180126779  mov     [rsp+0D0h+lpdwDaclSize], 0
0x180126782  lea     r8, a1025; "1025"
0x180126789  mov     edx, 401h
0x18012678e  jmp     loc_1801264E6
0x180126793  mov     edx, [rbp+57h+dwBufferLength]; uBytes
0x180126796  xor     ecx, ecx; uFlags
0x180126798  call    cs:__imp_LocalAlloc
0x18012679e  mov     [r12], rax
0x1801267a2  test    rax, rax
0x1801267a5  jz      loc_180126849
0x1801267ab  lea     r8, [rbp+57h+dwBufferLength]; lpdwBufferLength
0x1801267af  mov     rdx, rax; pSelfRelativeSecurityDescriptor
0x1801267b2  mov     rcx, rbx; pAbsoluteSecurityDescriptor
0x1801267b5  call    cs:__imp_MakeSelfRelativeSD
0x1801267bb  test    eax, eax
0x1801267bd  jnz     short loc_180126814
0x1801267bf  mov     rax, cs:WPP_GLOBAL_Control
0x1801267c6  lea     rdx, WPP_GLOBAL_Control
0x1801267cd  cmp     rax, rdx
0x1801267d0  jz      short loc_180126800
0x1801267d2  test    dword ptr [rax+1Ch], 10000000h
0x1801267d9  jz      short loc_180126800
0x1801267db  call    cs:__imp_GetLastError
0x1801267e1  mov     edx, 31h ; '1'
0x1801267e6  mov     r9d, eax
0x1801267e9  lea     r8, WPP_5b789da118f632ad9796e014c1252c4d_Traceguids
0x1801267f0  mov     rcx, cs:WPP_GLOBAL_Control
0x1801267f7  mov     rcx, [rcx+10h]
0x1801267fb  call    WPP_SF_d
0x180126800  mov     rcx, [r12]; hMem
0x180126804  call    cs:__imp_LocalFree
0x18012680a  mov     qword ptr [r12], 0
0x180126812  jmp     short loc_180126855
0x180126814  lea     rcx, [rbp+57h+var_68]
0x180126818  call    ?ReleasePtr@?$AutoCleanup@V?$AutoDeleteVector@PEAG@@PEAPEAG@@AEAAXXZ; AutoCleanup<AutoDeleteVector<ushort *>,ushort * *>::ReleasePtr(void)
0x18012681d  nop
0x18012681e  lea     rcx, [rbp+57h+var_60]
0x180126822  call    ?ReleasePtr@?$AutoCleanup@V?$AutoDeleteVector@PEAG@@PEAPEAG@@AEAAXXZ; AutoCleanup<AutoDeleteVector<ushort *>,ushort * *>::ReleasePtr(void)
0x180126827  nop
0x180126828  lea     rcx, [rbp+57h+var_58]
0x18012682c  call    ?ReleasePtr@?$AutoCleanup@V?$AutoDeleteVector@PEAG@@PEAPEAG@@AEAAXXZ; AutoCleanup<AutoDeleteVector<ushort *>,ushort * *>::ReleasePtr(void)
0x180126831  nop
0x180126832  lea     rcx, [rbp+57h+pDacl]
0x180126836  call    ?ReleasePtr@?$AutoCleanup@V?$AutoDeleteVector@PEAG@@PEAPEAG@@AEAAXXZ; AutoCleanup<AutoDeleteVector<ushort *>,ushort * *>::ReleasePtr(void)
0x18012683b  nop
0x18012683c  lea     rcx, [rbp+57h+pSecurityDescriptor]
0x180126840  call    ?ReleasePtr@?$AutoCleanup@V?$AutoDeleteVector@PEAG@@PEAPEAG@@AEAAXXZ; AutoCleanup<AutoDeleteVector<ushort *>,ushort * *>::ReleasePtr(void)
0x180126845  mov     eax, esi
0x180126847  jmp     short loc_180126888
0x180126849  mov     ecx, 0Eh; dwErrCode
0x18012684e  call    cs:__imp_SetLastError
0x180126854  nop
0x180126855  lea     rcx, [rbp+57h+var_68]
0x180126859  call    ?ReleasePtr@?$AutoCleanup@V?$AutoDeleteVector@PEAG@@PEAPEAG@@AEAAXXZ; AutoCleanup<AutoDeleteVector<ushort *>,ushort * *>::ReleasePtr(void)
0x18012685e  nop
0x18012685f  lea     rcx, [rbp+57h+var_60]
0x180126863  call    ?ReleasePtr@?$AutoCleanup@V?$AutoDeleteVector@PEAG@@PEAPEAG@@AEAAXXZ; AutoCleanup<AutoDeleteVector<ushort *>,ushort * *>::ReleasePtr(void)
  ... truncated ...
```
