# CAudioDGModule::InitializeSecurity(ulong,ulong,ulong)

- ea: `0x1400327a8`
- end: `0x140032c1a`
- name: `?InitializeSecurity@CAudioDGModule@@AEAAJKKK@Z`
- size: `1138`
- prototype: `__int64 __fastcall(CAudioDGModule *__hidden this, unsigned int, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14004bcc4`

## callees

- `0x1400327a8`
- `0x140055de0`
- `0x140069128`
- `0x1400b5010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140032872`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140032a6c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140032872`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140032a6c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400328e6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400328ef`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400328f8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140032901`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14003290a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140032913`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400328e6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400328ef`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400328f8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140032901`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14003290a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140032913`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x14003289c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1400328b9`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x140032a41`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x140032a85`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x140032a98`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x14003289c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1400328b9`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x140032a41`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x140032a85`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x140032a98`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x140032b3f`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x140032b3f`
- `api-ms-win-core-com-l1-1-0!CoInitializeSecurity` at `0x1400329f7`
- `api-ms-win-core-com-l1-1-0!CoInitializeSecurity` at `0x1400329f7`
- `api-ms-win-security-base-l1-1-0!MakeAbsoluteSD` at `0x140032864`
- `api-ms-win-security-base-l1-1-0!MakeAbsoluteSD` at `0x14003299d`
- `api-ms-win-security-base-l1-1-0!MakeAbsoluteSD` at `0x140032864`
- `api-ms-win-security-base-l1-1-0!MakeAbsoluteSD` at `0x14003299d`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x140032816`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x140032816`

## string_xrefs

- `0x140032c04`: `CAudioDGModule::InitializeSecurity`

## pseudocode

```c
__int64 __fastcall CAudioDGModule::InitializeSecurity(CAudioDGModule *this)
{
  HLOCAL v1; // rdi
  struct _ACL *v2; // rsi
  struct _ACL *pSacl; // r14
  void *pOwner; // r15
  void *pPrimaryGroup; // r12
  signed int LastError; // eax
  int v7; // ebx
  DWORD v8; // edx
  HLOCAL v9; // rax
  DWORD v10; // r8d
  _QWORD *v12; // rcx
  __int64 v13; // rdx
  HLOCAL v14; // rax
  DWORD dwAbsoluteSecurityDescriptorSize; // [rsp+68h] [rbp-9h] BYREF
  ULONG SecurityDescriptorSize; // [rsp+6Ch] [rbp-5h] BYREF
  LPVOID ppv; // [rsp+70h] [rbp-1h] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+78h] [rbp+7h] BYREF
  DWORD dwDaclSize; // [rsp+D8h] [rbp+67h] BYREF
  int v20; // [rsp+DCh] [rbp+6Bh]
  DWORD dwSaclSize; // [rsp+E0h] [rbp+6Fh] BYREF
  DWORD dwPrimaryGroupSize; // [rsp+E8h] [rbp+77h] BYREF
  DWORD dwOwnerSize; // [rsp+F0h] [rbp+7Fh] BYREF

  v20 = HIDWORD(this);
  ppv = 0;
  SecurityDescriptor = 0;
  SecurityDescriptorSize = 0;
  v1 = 0;
  dwAbsoluteSecurityDescriptorSize = 0;
  v2 = 0;
  dwDaclSize = 0;
  pSacl = 0;
  dwSaclSize = 0;
  pOwner = 0;
  dwOwnerSize = 0;
  pPrimaryGroup = 0;
  dwPrimaryGroupSize = 0;
  if ( !ConvertStringSecurityDescriptorToSecurityDescriptorW(
          L"O:LSG:LSD:(A;;0x1;;;RC)(A;;0x1;;;AU)(A;;0x1;;;IU)(A;;0x1;;;AC)(A;;0x1;;;S-1-15-3-1024-1692970155-4054893335-18"
           "5714091-3362601943-3526593181-1159816984-2199008581-497492991)",
          1u,
          &SecurityDescriptor,
          &SecurityDescriptorSize) )
    goto LABEL_33;
  if ( MakeAbsoluteSD(
         SecurityDescriptor,
         0,
         &dwAbsoluteSecurityDescriptorSize,
         0,
         &dwDaclSize,
         0,
         &dwSaclSize,
         0,
         &dwOwnerSize,
         0,
         &dwPrimaryGroupSize) )
  {
    v7 = -2147418113;
    goto LABEL_17;
  }
  LastError = GetLastError();
  v7 = LastError;
  if ( LastError != 122 )
    goto LABEL_31;
  if ( dwAbsoluteSecurityDescriptorSize )
    v1 = LocalAlloc(0x40u, dwAbsoluteSecurityDescriptorSize);
  if ( dwDaclSize )
    v2 = (struct _ACL *)LocalAlloc(0x40u, dwDaclSize);
  if ( dwSaclSize )
    pSacl = (struct _ACL *)LocalAlloc(0x40u, dwSaclSize);
  v8 = dwOwnerSize;
  if ( dwOwnerSize )
  {
    v9 = LocalAlloc(0x40u, dwOwnerSize);
    v8 = dwOwnerSize;
    pOwner = v9;
  }
  v10 = dwPrimaryGroupSize;
  if ( dwPrimaryGroupSize )
  {
    v14 = LocalAlloc(0x40u, dwPrimaryGroupSize);
    v8 = dwOwnerSize;
    pPrimaryGroup = v14;
    v10 = dwPrimaryGroupSize;
  }
  if ( dwAbsoluteSecurityDescriptorSize && !v1
    || dwDaclSize && !v2
    || dwSaclSize && !pSacl
    || v8 && !pOwner
    || v10 && !pPrimaryGroup )
  {
    v7 = -2147024882;
    goto LABEL_17;
  }
  if ( !MakeAbsoluteSD(
          SecurityDescriptor,
          v1,
          &dwAbsoluteSecurityDescriptorSize,
          v2,
          &dwDaclSize,
          pSacl,
          &dwSaclSize,
          pOwner,
          &dwOwnerSize,
          pPrimaryGroup,
          &dwPrimaryGroupSize) )
  {
LABEL_33:
    LastError = GetLastError();
    v7 = LastError;
LABEL_31:
    if ( LastError > 0 )
      v7 = (unsigned __int16)LastError | 0x80070000;
    goto LABEL_17;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, WPP_545dd1bf131637e2bfef642b9620b691_Traceguids, 12320);
  }
  v7 = CoInitializeSecurity(v1, -1, 0, 0, 4u, 2u, 0, 0x3020u, 0);
  if ( v7 >= 0 )
  {
    v7 = CoCreateInstance(&CLSID_GlobalOptions, 0, 1u, &IID_IGlobalOptions, &ppv);
    if ( v7 >= 0 )
    {
      v7 = (*(__int64 (__fastcall **)(LPVOID, __int64, __int64))(*(_QWORD *)ppv + 24LL))(ppv, 5, 1);
      if ( v7 >= 0 )
        v7 = (*(__int64 (__fastcall **)(LPVOID, __int64, __int64))(*(_QWORD *)ppv + 24LL))(ppv, 1, 2);
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
    }
    else
    {
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        v13 = 22;
        goto LABEL_45;
      }
    }
  }
  else
  {
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      v13 = 21;
LABEL_45:
      WPP_SF_d(v12[2], v13, WPP_545dd1bf131637e2bfef642b9620b691_Traceguids, (unsigned int)v7);
    }
  }
LABEL_17:
  LocalFree(SecurityDescriptor);
  LocalFree(v1);
  LocalFree(v2);
  LocalFree(pSacl);
  LocalFree(pOwner);
  LocalFree(pPrimaryGroup);
  if ( v7 < 0 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        23,
        WPP_545dd1bf131637e2bfef642b9620b691_Traceguids,
        (unsigned int)v7);
    }
    AudDGTraceLoggingErrorHelper("CAudioDGModule::InitializeSecurity", 0x28Fu, v7);
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1400327a8  mov     rax, rsp
0x1400327ab  mov     [rax+20h], r9d
0x1400327af  mov     [rax+18h], r8d
0x1400327b3  mov     [rax+10h], edx
0x1400327b6  mov     [rax+8], rcx
0x1400327ba  push    rbp
0x1400327bb  push    rbx
0x1400327bc  push    rsi
0x1400327bd  push    rdi
0x1400327be  push    r12
0x1400327c0  push    r13
0x1400327c2  push    r14
0x1400327c4  push    r15
0x1400327c6  lea     rbp, [rax-5Fh]
0x1400327ca  sub     rsp, 88h
0x1400327d1  xor     r13d, r13d
0x1400327d4  lea     r9, [rbp+57h+SecurityDescriptorSize]; SecurityDescriptorSize
0x1400327d8  lea     r8, [rbp+57h+SecurityDescriptor]; SecurityDescriptor
0x1400327dc  mov     [rbp+57h+ppv], r13
0x1400327e0  lea     rcx, aOLsgLsdA0x1RcA; "O:LSG:LSD:(A;;0x1;;;RC)(A;;0x1;;;AU)(A;"...
0x1400327e7  mov     [rbp+57h+SecurityDescriptor], r13
0x1400327eb  mov     [rbp+57h+SecurityDescriptorSize], r13d
0x1400327ef  mov     edi, r13d
0x1400327f2  lea     edx, [r13+1]; StringSDRevision
0x1400327f6  mov     [rbp+57h+dwAbsoluteSecurityDescriptorSize], r13d
0x1400327fa  mov     esi, r13d
0x1400327fd  mov     [rbp+57h+dwDaclSize], r13d
0x140032801  mov     r14d, r13d
0x140032804  mov     [rbp+57h+dwSaclSize], r13d
0x140032808  mov     r15d, r13d
0x14003280b  mov     [rbp+57h+dwOwnerSize], r13d
0x14003280f  mov     r12d, r13d
0x140032812  mov     [rbp+57h+dwPrimaryGroupSize], r13d
0x140032816  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x14003281c  test    eax, eax
0x14003281e  jz      loc_140032A6C
0x140032824  mov     rcx, [rbp+57h+SecurityDescriptor]; pSelfRelativeSecurityDescriptor
0x140032828  lea     rax, [rbp+57h+dwPrimaryGroupSize]
0x14003282c  mov     [rsp+50h], rax; lpdwPrimaryGroupSize
0x140032831  lea     r8, [rbp+57h+dwAbsoluteSecurityDescriptorSize]; lpdwAbsoluteSecurityDescriptorSize
0x140032835  mov     [rsp+0C0h+pPrimaryGroup], r13; pPrimaryGroup
0x14003283a  lea     rax, [rbp+57h+dwOwnerSize]
0x14003283e  mov     [rsp+0C0h+lpdwOwnerSize], rax; lpdwOwnerSize
0x140032843  xor     r9d, r9d; pDacl
0x140032846  mov     [rsp+0C0h+pOwner], r13; pOwner
0x14003284b  lea     rax, [rbp+57h+dwSaclSize]
0x14003284f  mov     [rsp+0C0h+lpdwSaclSize], rax; lpdwSaclSize
0x140032854  xor     edx, edx; pAbsoluteSecurityDescriptor
0x140032856  lea     rax, [rbp+57h+dwDaclSize]
0x14003285a  mov     [rsp+0C0h+pSacl], r13; pSacl
0x14003285f  mov     [rsp+0C0h+lpdwDaclSize], rax; lpdwDaclSize
0x140032864  call    cs:__imp_MakeAbsoluteSD
0x14003286a  test    eax, eax
0x14003286c  jnz     loc_140032A76
0x140032872  call    cs:__imp_GetLastError
0x140032878  mov     ebx, eax
0x14003287a  cmp     eax, 7Ah ; 'z'
0x14003287d  jnz     loc_140032A56
0x140032883  lea     ebx, [rax-3Ah]
0x140032886  mov     eax, [rbp+57h+dwAbsoluteSecurityDescriptorSize]
0x140032889  test    eax, eax
0x14003288b  jnz     loc_140032A80
0x140032891  mov     ecx, [rbp+57h+dwDaclSize]
0x140032894  test    ecx, ecx
0x140032896  jz      short loc_1400328A5
0x140032898  mov     edx, ecx; uBytes
0x14003289a  mov     ecx, ebx; uFlags
0x14003289c  call    cs:__imp_LocalAlloc
0x1400328a2  mov     rsi, rax
0x1400328a5  mov     ecx, [rbp+57h+dwSaclSize]
0x1400328a8  test    ecx, ecx
0x1400328aa  jnz     loc_140032A93
0x1400328b0  mov     edx, [rbp+57h+dwOwnerSize]; uBytes
0x1400328b3  test    edx, edx
0x1400328b5  jz      short loc_1400328C5
0x1400328b7  mov     ecx, ebx; uFlags
0x1400328b9  call    cs:__imp_LocalAlloc
0x1400328bf  mov     edx, [rbp+57h+dwOwnerSize]
0x1400328c2  mov     r15, rax
0x1400328c5  mov     r8d, [rbp+57h+dwPrimaryGroupSize]
0x1400328c9  test    r8d, r8d
0x1400328cc  jnz     loc_140032A3C
0x1400328d2  cmp     [rbp+57h+dwAbsoluteSecurityDescriptorSize], r13d
0x1400328d6  jbe     short loc_140032937
0x1400328d8  test    rdi, rdi
0x1400328db  jnz     short loc_140032937
0x1400328dd  mov     ebx, 8007000Eh
0x1400328e2  mov     rcx, [rbp+57h+SecurityDescriptor]; hMem
0x1400328e6  call    cs:__imp_LocalFree
0x1400328ec  mov     rcx, rdi; hMem
0x1400328ef  call    cs:__imp_LocalFree
0x1400328f5  mov     rcx, rsi; hMem
0x1400328f8  call    cs:__imp_LocalFree
0x1400328fe  mov     rcx, r14; hMem
0x140032901  call    cs:__imp_LocalFree
0x140032907  mov     rcx, r15; hMem
0x14003290a  call    cs:__imp_LocalFree
0x140032910  mov     rcx, r12; hMem
0x140032913  call    cs:__imp_LocalFree
0x140032919  test    ebx, ebx
0x14003291b  js      loc_140032BC7
0x140032921  mov     eax, ebx
0x140032923  add     rsp, 88h
0x14003292a  pop     r15
0x14003292c  pop     r14
0x14003292e  pop     r13
0x140032930  pop     r12
0x140032932  pop     rdi
0x140032933  pop     rsi
0x140032934  pop     rbx
0x140032935  pop     rbp
0x140032936  retn
0x140032937  cmp     [rbp+57h+dwDaclSize], r13d
0x14003293b  ja      loc_140032AA6
0x140032941  cmp     [rbp+57h+dwSaclSize], r13d
0x140032945  ja      loc_140032AB4
0x14003294b  test    edx, edx
0x14003294d  jnz     loc_140032AC2
0x140032953  test    r8d, r8d
0x140032956  jnz     loc_140032AD0
0x14003295c  mov     rcx, [rbp+57h+SecurityDescriptor]; pSelfRelativeSecurityDescriptor
0x140032960  lea     rax, [rbp+57h+dwPrimaryGroupSize]
0x140032964  mov     [rsp+50h], rax; lpdwPrimaryGroupSize
0x140032969  lea     r8, [rbp+57h+dwAbsoluteSecurityDescriptorSize]; lpdwAbsoluteSecurityDescriptorSize
0x14003296d  mov     [rsp+0C0h+pPrimaryGroup], r12; pPrimaryGroup
0x140032972  lea     rax, [rbp+57h+dwOwnerSize]
0x140032976  mov     [rsp+0C0h+lpdwOwnerSize], rax; lpdwOwnerSize
0x14003297b  mov     r9, rsi; pDacl
0x14003297e  mov     [rsp+0C0h+pOwner], r15; pOwner
0x140032983  lea     rax, [rbp+57h+dwSaclSize]
0x140032987  mov     [rsp+0C0h+lpdwSaclSize], rax; lpdwSaclSize
0x14003298c  mov     rdx, rdi; pAbsoluteSecurityDescriptor
0x14003298f  lea     rax, [rbp+57h+dwDaclSize]
0x140032993  mov     [rsp+0C0h+pSacl], r14; pSacl
0x140032998  mov     [rsp+0C0h+lpdwDaclSize], rax; lpdwDaclSize
0x14003299d  call    cs:__imp_MakeAbsoluteSD
0x1400329a3  test    eax, eax
0x1400329a5  jz      loc_140032A6C
0x1400329ab  mov     rcx, cs:WPP_GLOBAL_Control
0x1400329b2  lea     rax, WPP_GLOBAL_Control
0x1400329b9  mov     ebx, 3020h
0x1400329be  cmp     rcx, rax
0x1400329c1  jz      short loc_1400329CD
0x1400329c3  test    byte ptr [rcx+1Ch], 10h
0x1400329c7  jnz     loc_140032ADE
0x1400329cd  mov     [rsp+0C0h+lpdwOwnerSize], r13; pReserved3
0x1400329d2  xor     r9d, r9d; pReserved1
0x1400329d5  mov     dword ptr [rsp+0C0h+pOwner], ebx; dwCapabilities
0x1400329d9  xor     r8d, r8d; asAuthSvc
0x1400329dc  mov     [rsp+0C0h+lpdwSaclSize], r13; pAuthList
0x1400329e1  or      edx, 0FFFFFFFFh; cAuthSvc
0x1400329e4  mov     dword ptr [rsp+0C0h+pSacl], 2; dwImpLevel
0x1400329ec  mov     rcx, rdi; pSecDesc
0x1400329ef  mov     dword ptr [rsp+0C0h+lpdwDaclSize], 4; dwAuthnLevel
0x1400329f7  call    cs:__imp_CoInitializeSecurity
0x1400329fd  mov     ebx, eax
0x1400329ff  test    eax, eax
0x140032a01  jns     loc_140032B22
0x140032a07  mov     rcx, cs:WPP_GLOBAL_Control
0x140032a0e  lea     rax, WPP_GLOBAL_Control
0x140032a15  cmp     rcx, rax
0x140032a18  jz      loc_1400328E2
0x140032a1e  test    byte ptr [rcx+1Ch], 10h
0x140032a22  jz      loc_1400328E2
0x140032a28  cmp     byte ptr [rcx+19h], 4
0x140032a2c  jb      loc_1400328E2
0x140032a32  mov     edx, 15h
0x140032a37  jmp     loc_140032B0A
0x140032a3c  mov     rdx, r8; uBytes
0x140032a3f  mov     ecx, ebx; uFlags
0x140032a41  call    cs:__imp_LocalAlloc
0x140032a47  mov     edx, [rbp+57h+dwOwnerSize]
0x140032a4a  mov     r12, rax
0x140032a4d  mov     r8d, [rbp+57h+dwPrimaryGroupSize]
0x140032a51  jmp     loc_1400328D2
0x140032a56  test    eax, eax
0x140032a58  jle     loc_1400328E2
0x140032a5e  movzx   ebx, ax
0x140032a61  or      ebx, 80070000h
0x140032a67  jmp     loc_1400328E2
0x140032a6c  call    cs:__imp_GetLastError
0x140032a72  mov     ebx, eax
0x140032a74  jmp     short loc_140032A56
0x140032a76  mov     ebx, 8000FFFFh
0x140032a7b  jmp     loc_1400328E2
0x140032a80  mov     rdx, rax; uBytes
0x140032a83  mov     ecx, ebx; uFlags
0x140032a85  call    cs:__imp_LocalAlloc
0x140032a8b  mov     rdi, rax
0x140032a8e  jmp     loc_140032891
0x140032a93  mov     rdx, rcx; uBytes
0x140032a96  mov     ecx, ebx; uFlags
0x140032a98  call    cs:__imp_LocalAlloc
0x140032a9e  mov     r14, rax
0x140032aa1  jmp     loc_1400328B0
0x140032aa6  test    rsi, rsi
0x140032aa9  jz      loc_1400328DD
0x140032aaf  jmp     loc_140032941
0x140032ab4  test    r14, r14
0x140032ab7  jz      loc_1400328DD
0x140032abd  jmp     loc_14003294B
0x140032ac2  test    r15, r15
0x140032ac5  jz      loc_1400328DD
0x140032acb  jmp     loc_140032953
0x140032ad0  test    r12, r12
0x140032ad3  jz      loc_1400328DD
0x140032ad9  jmp     loc_14003295C
0x140032ade  cmp     byte ptr [rcx+19h], 4
0x140032ae2  jb      loc_1400329CD
0x140032ae8  mov     rcx, [rcx+10h]
0x140032aec  lea     r8, WPP_545dd1bf131637e2bfef642b9620b691_Traceguids
0x140032af3  mov     edx, 14h
0x140032af8  mov     r9d, ebx
0x140032afb  call    WPP_SF_d
0x140032b00  jmp     loc_1400329CD
0x140032b05  mov     edx, 16h
0x140032b0a  mov     rcx, [rcx+10h]
0x140032b0e  lea     r8, WPP_545dd1bf131637e2bfef642b9620b691_Traceguids
0x140032b15  mov     r9d, ebx
0x140032b18  call    WPP_SF_d
0x140032b1d  jmp     loc_1400328E2
0x140032b22  xor     edx, edx; pUnkOuter
0x140032b24  lea     rax, [rbp+57h+ppv]
0x140032b28  lea     r9, IID_IGlobalOptions; riid
0x140032b2f  mov     [rsp+0C0h+lpdwDaclSize], rax; ppv
0x140032b34  lea     rcx, CLSID_GlobalOptions; rclsid
0x140032b3b  lea     r8d, [rdx+1]; dwClsContext
0x140032b3f  call    cs:__imp_CoCreateInstance
0x140032b45  mov     ebx, eax
0x140032b47  test    eax, eax
0x140032b49  jns     short loc_140032B78
0x140032b4b  mov     rcx, cs:WPP_GLOBAL_Control
0x140032b52  lea     rax, WPP_GLOBAL_Control
0x140032b59  cmp     rcx, rax
0x140032b5c  jz      loc_1400328E2
0x140032b62  test    byte ptr [rcx+1Ch], 10h
0x140032b66  jz      loc_1400328E2
0x140032b6c  cmp     byte ptr [rcx+19h], 4
0x140032b70  jb      loc_1400328E2
0x140032b76  jmp     short loc_140032B05
0x140032b78  mov     rcx, [rbp+57h+ppv]
0x140032b7c  mov     edx, 5
0x140032b81  mov     rax, [rcx]
0x140032b84  lea     r8d, [rdx-4]
0x140032b88  mov     rax, [rax+18h]
0x140032b8c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140032b91  mov     ebx, eax
0x140032b93  test    eax, eax
0x140032b95  js      short loc_140032BB2
0x140032b97  mov     rcx, [rbp+57h+ppv]
0x140032b9b  mov     edx, 1
0x140032ba0  mov     rax, [rcx]
0x140032ba3  lea     r8d, [rdx+1]
0x140032ba7  mov     rax, [rax+18h]
0x140032bab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140032bb0  mov     ebx, eax
0x140032bb2  mov     rcx, [rbp+57h+ppv]
0x140032bb6  mov     rax, [rcx]
0x140032bb9  mov     rax, [rax+10h]
0x140032bbd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140032bc2  jmp     loc_1400328E2
0x140032bc7  mov     rcx, cs:WPP_GLOBAL_Control
0x140032bce  lea     rax, WPP_GLOBAL_Control
0x140032bd5  cmp     rcx, rax
0x140032bd8  jz      short loc_140032C01
0x140032bda  test    dword ptr [rcx+1Ch], 40000h
0x140032be1  jz      short loc_140032C01
0x140032be3  cmp     byte ptr [rcx+19h], 2
0x140032be7  jb      short loc_140032C01
0x140032be9  mov     rcx, [rcx+10h]
0x140032bed  lea     r8, WPP_545dd1bf131637e2bfef642b9620b691_Traceguids
0x140032bf4  mov     edx, 17h
0x140032bf9  mov     r9d, ebx
0x140032bfc  call    WPP_SF_d
0x140032c01  mov     r8d, ebx; int
0x140032c04  lea     rcx, aCaudiodgmodule_0; "CAudioDGModule::InitializeSecurity"
0x140032c0b  mov     edx, 28Fh; unsigned int
0x140032c10  call    ?AudDGTraceLoggingErrorHelper@@YAXPEBDIJ@Z; AudDGTraceLoggingErrorHelper(char const *,uint,long)
0x140032c15  jmp     loc_140032921
```
