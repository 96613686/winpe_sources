# SDDLToSecurityDescriptor(IRequestContext *,ushort const *,void * *,int)

- ea: `0x180036864`
- end: `0x180036cf7`
- name: `?SDDLToSecurityDescriptor@@YAHPEAVIRequestContext@@PEBGPEAPEAXH@Z`
- size: `1171`
- prototype: `__int64 __fastcall(struct IRequestContext *, const unsigned __int16 *, void **, BOOL)`
- caller_count: `6`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180038050`
- `0x18003bab0`
- `0x180058b3c`
- `0x1800e7d50`
- `0x18012f0f8`
- `0x180199f84`

## callees

- `0x180005d10`
- `0x180036864`
- `0x180103850`
- `0x180112380`
- `0x1801133b0`
- `0x18011ae5c`
- `0x18012a93c`
- `0x1801c2010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180036974`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180036a66`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180036b3f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180036bd1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180036974`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180036a66`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180036b3f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180036bd1`
- `api-ms-win-security-base-l1-1-0!MapGenericMask` at `0x180036a4b`
- `api-ms-win-security-base-l1-1-0!MapGenericMask` at `0x180036a4b`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x1800369d2`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x1800369d2`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x180036961`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x180036961`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorOwner` at `0x1800368fe`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorOwner` at `0x1800368fe`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorGroup` at `0x180036b6a`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorGroup` at `0x180036b6a`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1800368db`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1800368db`

## string_xrefs

- `0x180036936`: `onecore\admin\wmi\wmx\config\configutils.cpp`

## pseudocode

```c
__int64 __fastcall SDDLToSecurityDescriptor(struct IRequestContext *a1, const unsigned __int16 *a2, void **a3, BOOL a4)
{
  unsigned int SecurityDescriptorOwner; // esi
  PSECURITY_DESCRIPTOR v8; // rcx
  __int64 v9; // r8
  PSECURITY_DESCRIPTOR v11; // rcx
  void (__fastcall *v12)(struct IRequestContext *, _QWORD); // rbx
  DWORD v13; // eax
  struct _ACL *v14; // rcx
  DWORD v15; // eax
  int v16; // r12d
  int v17; // r15d
  _DWORD *v18; // rbx
  char *v19; // r13
  PVOID *v20; // rcx
  char v21; // al
  DWORD *v22; // rcx
  BOOL v23; // eax
  void (__fastcall *v24)(struct IRequestContext *, _QWORD); // rbx
  DWORD v25; // eax
  PSECURITY_DESCRIPTOR v26; // rcx
  DWORD LastError; // eax
  DWORD v28; // ebx
  DWORD v29; // [rsp+30h] [rbp-20h]
  BOOL bDaclDefaulted; // [rsp+34h] [rbp-1Ch] BYREF
  LPVOID pAce; // [rsp+38h] [rbp-18h] BYREF
  PACL pDacl; // [rsp+40h] [rbp-10h] BYREF
  PSID pOwner; // [rsp+90h] [rbp+40h] BYREF
  BOOL bOwnerDefaulted; // [rsp+A8h] [rbp+58h] BYREF

  bOwnerDefaulted = a4;
  if ( !a1 )
  {
    WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\config\\configutils.cpp", 0x282u, L"642", 0x54Fu, 0);
    return 0;
  }
  if ( !a2 )
  {
    WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\config\\configutils.cpp", 0x283u, L"643", 0x54Fu, a1);
    return 0;
  }
  if ( !a3 )
  {
    WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\config\\configutils.cpp", 0x284u, L"644", 0x54Fu, a1);
    return 0;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200000) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 33, &WPP_56614427bb63350db5b96d546a520a16_Traceguids);
  SecurityDescriptorOwner = ConvertStringSecurityDescriptorToSecurityDescriptorW(a2, 1u, a3, 0);
  if ( !SecurityDescriptorOwner )
  {
    LastError = GetLastError();
    v28 = LastError;
    if ( LastError == 1332 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0 )
        WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 34, &WPP_56614427bb63350db5b96d546a520a16_Traceguids, a2);
    }
    else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0 )
    {
      WPP_SF_dS(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        35,
        (unsigned int)&WPP_56614427bb63350db5b96d546a520a16_Traceguids,
        LastError,
        (__int64)a2);
    }
    (*(void (__fastcall **)(struct IRequestContext *, __int64, __int64, const unsigned __int16 *, DWORD))(*(_QWORD *)a1 + 64LL))(
      a1,
      2150858773LL,
      1077134204,
      a2,
      v28);
    return SecurityDescriptorOwner;
  }
  v8 = *a3;
  pOwner = 0;
  bOwnerDefaulted = 0;
  SecurityDescriptorOwner = GetSecurityDescriptorOwner(v8, &pOwner, &bOwnerDefaulted);
  if ( !SecurityDescriptorOwner )
    goto LABEL_14;
  if ( !pOwner )
  {
    v9 = 1077134205;
    goto LABEL_38;
  }
  v26 = *a3;
  pOwner = 0;
  bOwnerDefaulted = 0;
  SecurityDescriptorOwner = GetSecurityDescriptorGroup(v26, &pOwner, &bOwnerDefaulted);
  if ( !SecurityDescriptorOwner )
    goto LABEL_14;
  if ( !pOwner )
  {
    v9 = 1077134206;
LABEL_38:
    SecurityDescriptorOwner = 0;
    (*(void (__fastcall **)(struct IRequestContext *, __int64, __int64, const unsigned __int16 *))(*(_QWORD *)a1 + 64LL))(
      a1,
      2150858773LL,
      v9,
      a2);
    return SecurityDescriptorOwner;
  }
  v11 = *a3;
  LODWORD(pOwner) = 0;
  pDacl = 0;
  bDaclDefaulted = 0;
  SecurityDescriptorOwner = GetSecurityDescriptorDacl(v11, (LPBOOL)&pOwner, &pDacl, &bDaclDefaulted);
  if ( !SecurityDescriptorOwner )
  {
LABEL_14:
    v12 = *(void (__fastcall **)(struct IRequestContext *, _QWORD))(*(_QWORD *)a1 + 72LL);
    v13 = GetLastError();
    v12(a1, v13);
    return SecurityDescriptorOwner;
  }
  if ( !(_DWORD)pOwner )
    goto LABEL_37;
  v14 = pDacl;
  if ( !pDacl )
    goto LABEL_37;
  v15 = 0;
  bOwnerDefaulted = 0;
  v16 = 0;
  v17 = 0;
  while ( 1 )
  {
    v29 = v15;
    pAce = 0;
    if ( !GetAce(v14, v15, &pAce) )
      break;
    v18 = pAce;
    v19 = (char *)pAce;
    v20 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200000) != 0 )
    {
      WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 36, &WPP_56614427bb63350db5b96d546a520a16_Traceguids);
      v20 = (PVOID *)WPP_GLOBAL_Control;
      v18 = pAce;
    }
    v21 = *v19;
    if ( *v19 && v21 != 9 )
    {
      if ( v21 == 1 || v21 == 10 )
      {
        ++v17;
        if ( v20 != &WPP_GLOBAL_Control && (*((_DWORD *)v20 + 7) & 0x200000) != 0 )
          WPP_SF_LLL(v20[2], 38, &WPP_56614427bb63350db5b96d546a520a16_Traceguids);
        v22 = v18 + 1;
        if ( (v18[1] & 0xFFFFFFF) != 0 || !*v22 )
        {
          SecurityDescriptorOwner = 0;
          (*(void (__fastcall **)(struct IRequestContext *, __int64, __int64, const unsigned __int16 *))(*(_QWORD *)a1 + 64LL))(
            a1,
            2150858773LL,
            1077134209,
            a2);
          goto LABEL_35;
        }
LABEL_29:
        MapGenericMask(v22, (PGENERIC_MAPPING)&GenericMapping);
      }
      v23 = bOwnerDefaulted;
      goto LABEL_31;
    }
    ++v16;
    if ( v20 != &WPP_GLOBAL_Control && (*((_DWORD *)v20 + 7) & 0x200000) != 0 )
      WPP_SF_LLL(v20[2], 37, &WPP_56614427bb63350db5b96d546a520a16_Traceguids);
    v22 = v18 + 1;
    if ( (v18[1] & 0xFFFFFFF) == 0 && *v22 )
      goto LABEL_29;
    SecurityDescriptorOwner = 0;
    (*(void (__fastcall **)(struct IRequestContext *, __int64, __int64, const unsigned __int16 *))(*(_QWORD *)a1 + 64LL))(
      a1,
      2150858773LL,
      1077134209,
      a2);
    v23 = 1;
    bOwnerDefaulted = 1;
LABEL_31:
    if ( v23 )
      goto LABEL_35;
    v14 = pDacl;
    v15 = v29 + 1;
  }
  if ( GetLastError() != 87 )
  {
    SecurityDescriptorOwner = 0;
    v24 = *(void (__fastcall **)(struct IRequestContext *, _QWORD))(*(_QWORD *)a1 + 72LL);
    v25 = GetLastError();
    v24(a1, v25);
  }
LABEL_35:
  if ( !v16 && !v17 )
  {
LABEL_37:
    v9 = 1077134207;
    goto LABEL_38;
  }
  return SecurityDescriptorOwner;
}

```

## disassembly

```asm
0x180036864  mov     [rsp-38h+arg_8], rbx
0x180036869  mov     [rsp-38h+bOwnerDefaulted], r9d
0x18003686e  push    rbp
0x18003686f  push    rsi
0x180036870  push    rdi
0x180036871  push    r12
0x180036873  push    r13
0x180036875  push    r14
0x180036877  push    r15
0x180036879  mov     rbp, rsp
0x18003687c  sub     rsp, 50h
0x180036880  xor     r13d, r13d
0x180036883  mov     rbx, r8
0x180036886  mov     r14, rdx
0x180036889  mov     rdi, rcx
0x18003688c  test    rcx, rcx
0x18003688f  jz      loc_18003691F
0x180036895  test    rdx, rdx
0x180036898  jz      loc_180036B8F
0x18003689e  test    rbx, rbx
0x1800368a1  jz      loc_180036BA5
0x1800368a7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800368ae  lea     r15, WPP_GLOBAL_Control
0x1800368b5  lea     r12, WPP_56614427bb63350db5b96d546a520a16_Traceguids
0x1800368bc  cmp     rcx, r15
0x1800368bf  jz      short loc_1800368CE
0x1800368c1  test    dword ptr [rcx+1Ch], 200000h
0x1800368c8  jnz     loc_180036BBB
0x1800368ce  xor     r9d, r9d; SecurityDescriptorSize
0x1800368d1  mov     r8, rbx; SecurityDescriptor
0x1800368d4  mov     rcx, r14; StringSecurityDescriptor
0x1800368d7  lea     edx, [r9+1]; StringSDRevision
0x1800368db  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x1800368e1  mov     esi, eax
0x1800368e3  test    eax, eax
0x1800368e5  jz      loc_180036BD1
0x1800368eb  mov     rcx, [rbx]; pSecurityDescriptor
0x1800368ee  lea     r8, [rbp+bOwnerDefaulted]; lpbOwnerDefaulted
0x1800368f2  lea     rdx, [rbp+pOwner]; pOwner
0x1800368f6  mov     [rbp+pOwner], r13
0x1800368fa  mov     [rbp+bOwnerDefaulted], r13d
0x1800368fe  call    cs:__imp_GetSecurityDescriptorOwner
0x180036904  mov     esi, eax
0x180036906  test    eax, eax
0x180036908  jz      short loc_18003696D
0x18003690a  cmp     [rbp+pOwner], r13
0x18003690e  jnz     loc_180036B57
0x180036914  mov     r8d, 4033C37Dh
0x18003691a  jmp     loc_180036A8D
0x18003691f  mov     [rsp+50h+var_30], r13; struct IRequestContext *
0x180036924  lea     r8, a642; "642"
0x18003692b  mov     edx, 282h; unsigned int
0x180036930  mov     r9d, 54Fh; unsigned int
0x180036936  lea     rcx, aOnecoreAdminWm_22; "onecore\\admin\\wmi\\wmx\\config\\confi"...
0x18003693d  call    ?WSManError@@YAXPEBGK0KPEAVIRequestContext@@@Z; WSManError(ushort const *,ulong,ushort const *,ulong,IRequestContext *)
0x180036942  xor     eax, eax
0x180036944  jmp     short loc_180036989
0x180036946  mov     rcx, [rbx]; pSecurityDescriptor
0x180036949  lea     r9, [rbp+bDaclDefaulted]; lpbDaclDefaulted
0x18003694d  lea     r8, [rbp+pDacl]; pDacl
0x180036951  mov     dword ptr [rbp+pOwner], r13d
0x180036955  lea     rdx, [rbp+pOwner]; lpbDaclPresent
0x180036959  mov     [rbp+pDacl], r13
0x18003695d  mov     [rbp+bDaclDefaulted], r13d
0x180036961  call    cs:__imp_GetSecurityDescriptorDacl
0x180036967  mov     esi, eax
0x180036969  test    eax, eax
0x18003696b  jnz     short loc_1800369A1
0x18003696d  mov     rax, [rdi]
0x180036970  mov     rbx, [rax+48h]
0x180036974  call    cs:__imp_GetLastError
0x18003697a  mov     edx, eax
0x18003697c  mov     rcx, rdi
0x18003697f  mov     rax, rbx
0x180036982  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036987  mov     eax, esi
0x180036989  mov     rbx, [rsp+50h+arg_8]
0x180036991  add     rsp, 50h
0x180036995  pop     r15
0x180036997  pop     r14
0x180036999  pop     r13
0x18003699b  pop     r12
0x18003699d  pop     rdi
0x18003699e  pop     rsi
0x18003699f  pop     rbp
0x1800369a0  retn
0x1800369a1  cmp     dword ptr [rbp+pOwner], r13d
0x1800369a5  jz      loc_180036A87
0x1800369ab  mov     rcx, [rbp+pDacl]; pAcl
0x1800369af  test    rcx, rcx
0x1800369b2  jz      loc_180036A87
0x1800369b8  mov     eax, r13d
0x1800369bb  mov     [rbp+bOwnerDefaulted], r13d
0x1800369bf  mov     r12d, r13d
0x1800369c2  mov     r15d, r13d
0x1800369c5  lea     r8, [rbp+pAce]; pAce
0x1800369c9  mov     [rbp+var_20], eax
0x1800369cc  mov     edx, eax; dwAceIndex
0x1800369ce  mov     [rbp+pAce], r13
0x1800369d2  call    cs:__imp_GetAce
0x1800369d8  test    eax, eax
0x1800369da  jz      loc_180036A66
0x1800369e0  mov     rbx, [rbp+pAce]
0x1800369e4  mov     r13, rbx
0x1800369e7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800369ee  lea     rdx, WPP_GLOBAL_Control
0x1800369f5  cmp     rcx, rdx
0x1800369f8  jz      short loc_180036A07
0x1800369fa  test    dword ptr [rcx+1Ch], 200000h
0x180036a01  jnz     loc_180036C5F
0x180036a07  mov     al, [r13+0]
0x180036a0b  xor     r13d, r13d
0x180036a0e  test    al, al
0x180036a10  jnz     loc_180036AAC
0x180036a16  inc     r12d
0x180036a19  cmp     rcx, rdx
0x180036a1c  jz      short loc_180036A2B
0x180036a1e  test    dword ptr [rcx+1Ch], 200000h
0x180036a25  jnz     loc_180036C97
0x180036a2b  lea     rcx, [rbx+4]; AccessMask
0x180036a2f  test    dword ptr [rcx], 0FFFFFFFh
0x180036a35  jnz     loc_180036CCA
0x180036a3b  cmp     [rcx], r13d
0x180036a3e  jz      loc_180036CCA
0x180036a44  lea     rdx, GenericMapping; GenericMapping
0x180036a4b  call    cs:__imp_MapGenericMask
0x180036a51  mov     eax, [rbp+bOwnerDefaulted]
0x180036a54  test    eax, eax
0x180036a56  jnz     short loc_180036A75
0x180036a58  mov     eax, [rbp+var_20]
0x180036a5b  mov     rcx, [rbp+pDacl]
0x180036a5f  inc     eax
0x180036a61  jmp     loc_1800369C5
0x180036a66  call    cs:__imp_GetLastError
0x180036a6c  cmp     eax, 57h ; 'W'
0x180036a6f  jnz     loc_180036B35
0x180036a75  test    r12d, r12d
0x180036a78  jnz     loc_180036987
0x180036a7e  test    r15d, r15d
0x180036a81  jnz     loc_180036987
0x180036a87  mov     r8d, 4033C37Fh
0x180036a8d  mov     rax, [rdi]
0x180036a90  mov     r9, r14
0x180036a93  mov     edx, 80338015h
0x180036a98  mov     rcx, rdi
0x180036a9b  mov     esi, r13d
0x180036a9e  mov     rax, [rax+40h]
0x180036aa2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036aa7  jmp     loc_180036987
0x180036aac  cmp     al, 9
0x180036aae  jz      loc_180036A16
0x180036ab4  cmp     al, 1
0x180036ab6  jz      short loc_180036ABC
0x180036ab8  cmp     al, 0Ah
0x180036aba  jnz     short loc_180036A51
0x180036abc  inc     r15d
0x180036abf  cmp     rcx, rdx
0x180036ac2  jz      short loc_180036AFB
0x180036ac4  test    dword ptr [rcx+1Ch], 200000h
0x180036acb  jz      short loc_180036AFB
0x180036acd  mov     r9d, [rbx+4]
0x180036ad1  mov     r8d, 0FFFFFFFh
0x180036ad7  mov     rcx, [rcx+10h]
0x180036adb  mov     eax, r9d
0x180036ade  and     eax, r8d
0x180036ae1  mov     edx, 26h ; '&'
0x180036ae6  mov     [rsp+50h+var_28], eax
0x180036aea  mov     dword ptr [rsp+50h+var_30], r8d
0x180036aef  lea     r8, WPP_56614427bb63350db5b96d546a520a16_Traceguids
0x180036af6  call    WPP_SF_LLL
0x180036afb  lea     rcx, [rbx+4]
0x180036aff  test    dword ptr [rcx], 0FFFFFFFh
0x180036b05  jnz     short loc_180036B10
0x180036b07  cmp     [rcx], r13d
0x180036b0a  jnz     loc_180036A44
0x180036b10  mov     rax, [rdi]
0x180036b13  mov     r9, r14
0x180036b16  mov     edx, 80338015h
0x180036b1b  mov     r8d, 4033C381h
0x180036b21  mov     rcx, rdi
0x180036b24  mov     esi, r13d
0x180036b27  mov     rax, [rax+40h]
0x180036b2b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036b30  jmp     loc_180036A75
0x180036b35  mov     rax, [rdi]
0x180036b38  mov     esi, r13d
0x180036b3b  mov     rbx, [rax+48h]
0x180036b3f  call    cs:__imp_GetLastError
0x180036b45  mov     edx, eax
0x180036b47  mov     rcx, rdi
0x180036b4a  mov     rax, rbx
0x180036b4d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036b52  jmp     loc_180036A75
0x180036b57  mov     rcx, [rbx]; pSecurityDescriptor
0x180036b5a  lea     r8, [rbp+bOwnerDefaulted]; lpbGroupDefaulted
0x180036b5e  lea     rdx, [rbp+pOwner]; pGroup
0x180036b62  mov     [rbp+pOwner], r13
0x180036b66  mov     [rbp+bOwnerDefaulted], r13d
0x180036b6a  call    cs:__imp_GetSecurityDescriptorGroup
0x180036b70  mov     esi, eax
0x180036b72  test    eax, eax
0x180036b74  jz      loc_18003696D
0x180036b7a  cmp     [rbp+pOwner], r13
0x180036b7e  jnz     loc_180036946
0x180036b84  mov     r8d, 4033C37Eh
0x180036b8a  jmp     loc_180036A8D
0x180036b8f  mov     [rsp+50h+var_30], rdi
0x180036b94  lea     r8, a643; "643"
0x180036b9b  mov     edx, 283h
0x180036ba0  jmp     loc_180036930
0x180036ba5  mov     [rsp+50h+var_30], rdi
0x180036baa  lea     r8, a644; "644"
0x180036bb1  mov     edx, 284h
0x180036bb6  jmp     loc_180036930
0x180036bbb  mov     rcx, [rcx+10h]
0x180036bbf  mov     edx, 21h ; '!'
0x180036bc4  mov     r8, r12
0x180036bc7  call    WPP_SF_
0x180036bcc  jmp     loc_1800368CE
0x180036bd1  call    cs:__imp_GetLastError
0x180036bd7  mov     ebx, eax
0x180036bd9  cmp     eax, 534h
0x180036bde  jnz     short loc_180036C0B
0x180036be0  mov     rcx, cs:WPP_GLOBAL_Control
0x180036be7  cmp     rcx, r15
0x180036bea  jz      short loc_180036C39
0x180036bec  test    dword ptr [rcx+1Ch], 400000h
0x180036bf3  jz      short loc_180036C39
0x180036bf5  mov     rcx, [rcx+10h]
0x180036bf9  mov     edx, 22h ; '"'
0x180036bfe  mov     r9, r14
0x180036c01  mov     r8, r12
0x180036c04  call    WPP_SF_S
0x180036c09  jmp     short loc_180036C39
0x180036c0b  mov     rcx, cs:WPP_GLOBAL_Control
0x180036c12  cmp     rcx, r15
0x180036c15  jz      short loc_180036C39
0x180036c17  test    dword ptr [rcx+1Ch], 400000h
0x180036c1e  jz      short loc_180036C39
0x180036c20  mov     rcx, [rcx+10h]
0x180036c24  mov     edx, 23h ; '#'
0x180036c29  mov     r9d, ebx
0x180036c2c  mov     [rsp+50h+var_30], r14
0x180036c31  mov     r8, r12
0x180036c34  call    WPP_SF_dS
0x180036c39  mov     rax, [rdi]
0x180036c3c  mov     r9, r14
0x180036c3f  mov     edx, 80338015h
0x180036c44  mov     dword ptr [rsp+50h+var_30], ebx
0x180036c48  mov     r8d, 4033C37Ch
0x180036c4e  mov     rcx, rdi
0x180036c51  mov     rax, [rax+40h]
0x180036c55  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036c5a  jmp     loc_180036987
0x180036c5f  movzx   eax, word ptr [rbx+2]
0x180036c63  lea     r8, WPP_56614427bb63350db5b96d546a520a16_Traceguids
0x180036c6a  movzx   r9d, byte ptr [rbx]
0x180036c6e  mov     edx, 24h ; '$'
0x180036c73  mov     rcx, [rcx+10h]
0x180036c77  mov     dword ptr [rsp+50h+var_30], eax
0x180036c7b  call    WPP_SF_Dd
0x180036c80  mov     rcx, cs:WPP_GLOBAL_Control
0x180036c87  lea     rdx, WPP_GLOBAL_Control
0x180036c8e  mov     rbx, [rbp+pAce]
0x180036c92  jmp     loc_180036A07
0x180036c97  mov     r9d, [rbx+4]
0x180036c9b  mov     r8d, 0FFFFFFFh
0x180036ca1  mov     rcx, [rcx+10h]
0x180036ca5  mov     eax, r9d
0x180036ca8  and     eax, r8d
0x180036cab  mov     edx, 25h ; '%'
0x180036cb0  mov     [rsp+50h+var_28], eax
0x180036cb4  mov     dword ptr [rsp+50h+var_30], r8d
0x180036cb9  lea     r8, WPP_56614427bb63350db5b96d546a520a16_Traceguids
0x180036cc0  call    WPP_SF_LLL
0x180036cc5  jmp     loc_180036A2B
0x180036cca  mov     rax, [rdi]
0x180036ccd  mov     r9, r14
0x180036cd0  mov     edx, 80338015h
0x180036cd5  mov     r8d, 4033C381h
0x180036cdb  mov     rcx, rdi
0x180036cde  mov     esi, r13d
0x180036ce1  mov     rax, [rax+40h]
0x180036ce5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036cea  mov     eax, 1
0x180036cef  mov     [rbp+bOwnerDefaulted], eax
0x180036cf2  jmp     loc_180036A54
```
