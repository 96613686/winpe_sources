# sih::mutex::CreateSecurityDescriptor(void *,std::unique_ptr<_ACL,std::default_delete<_ACL>> &)

- ea: `0x140024300`
- end: `0x14002451a`
- name: `?CreateSecurityDescriptor@mutex@sih@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@PEAXAEAV?$unique_ptr@U_ACL@@U?$default_delete@U_ACL@@@std@@@std@@@Z`
- size: `538`
- prototype: `_QWORD *__fastcall(_QWORD *, void *, PACL *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x140024764`

## callees

- `0x14000e130`
- `0x14001b640`
- `0x14001b7e8`
- `0x140024300`
- `0x140045de4`
- `0x140046404`
- `0x1400481f8`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x14002436c`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x14002436c`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x1400243e1`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x1400243e1`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAceEx` at `0x14002438f`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAceEx` at `0x14002438f`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x1400243c7`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x1400243c7`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x140024321`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x140024321`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x140024332`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x140024332`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140024402`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400244de`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140024402`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400244de`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1400243a4`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1400243a4`

## string_xrefs

- `0x14002443e`: `!IsValidSid(CurrentSid)`
- `0x140024472`: `InitializeAcl`
- `0x1400244a8`: `AddAccessAllowedAceEx`
- `0x1400244e4`: `InitializeSecurityDescriptor`
- `0x140024408`: `SetSecurityDescriptorDacl`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_QWORD *__fastcall sih::mutex::CreateSecurityDescriptor(_QWORD *a1, void *a2, PACL *a3)
{
  DWORD v6; // r14d
  struct _ACL *v7; // rax
  PACL v8; // rcx
  _OWORD *v9; // rbx
  int v11; // ecx
  unsigned int v12; // eax
  int v13; // ecx
  unsigned int LastErrorHr; // eax
  int v15; // ecx
  unsigned int v16; // eax
  int v17; // ecx
  unsigned int v18; // eax
  _BYTE pExceptionObject[32]; // [rsp+30h] [rbp-50h] BYREF
  _BYTE v20[40]; // [rsp+50h] [rbp-30h] BYREF
  _QWORD *v21; // [rsp+78h] [rbp-8h]

  v21 = a1;
  if ( !IsValidSid(a2) )
  {
    std::string::string(pExceptionObject, "!IsValidSid(CurrentSid)");
    sih::hr_exception::hr_exception(v20, 2147942413LL, pExceptionObject);
    throw (sih::hr_exception *)v20;
  }
  v6 = GetLengthSid(a2) + 20;
  v7 = (struct _ACL *)operator new[](v6, (const struct std::nothrow_t *)&std::nothrow);
  v8 = *a3;
  *a3 = v7;
  if ( v8 )
    operator delete(v8, (const struct std::nothrow_t *)8);
  if ( !InitializeAcl(*a3, v6, 2u) )
  {
    std::string::string(v20, "InitializeAcl");
    LastErrorHr = GetLastErrorHr(v13);
    sih::hr_exception::hr_exception(pExceptionObject, LastErrorHr, v20);
    throw (sih::hr_exception *)pExceptionObject;
  }
  if ( !AddAccessAllowedAceEx(*a3, 2u, 0, 0x10000000u, a2) )
  {
    std::string::string(v20, "AddAccessAllowedAceEx");
    v16 = GetLastErrorHr(v15);
    sih::hr_exception::hr_exception(pExceptionObject, v16, v20);
    throw (sih::hr_exception *)pExceptionObject;
  }
  v9 = LocalAlloc(0, 0x28u);
  *v9 = 0;
  v9[1] = 0;
  *((_QWORD *)v9 + 4) = 0;
  if ( !InitializeSecurityDescriptor(v9, 1u) )
  {
    LocalFree(v9);
    std::string::string(v20, "InitializeSecurityDescriptor");
    v18 = GetLastErrorHr(v17);
    sih::hr_exception::hr_exception(pExceptionObject, v18, v20);
    throw (sih::hr_exception *)pExceptionObject;
  }
  if ( !SetSecurityDescriptorDacl(v9, 1, *a3, 0) )
  {
    LocalFree(v9);
    std::string::string(v20, "SetSecurityDescriptorDacl");
    v12 = GetLastErrorHr(v11);
    sih::hr_exception::hr_exception(pExceptionObject, v12, v20);
    throw (sih::hr_exception *)pExceptionObject;
  }
  *a1 = v9;
  return a1;
}

```

## disassembly

```asm
0x140024300  push    rbp
0x140024302  push    rbx
0x140024303  push    rsi
0x140024304  push    rdi
0x140024305  push    r14
0x140024307  mov     rbp, rsp
0x14002430a  sub     rsp, 80h
0x140024311  mov     rsi, r8
0x140024314  mov     rbx, rdx
0x140024317  mov     rdi, rcx
0x14002431a  mov     [rbp+var_8], rcx
0x14002431e  mov     rcx, rdx; pSid
0x140024321  call    cs:__imp_IsValidSid
0x140024327  test    eax, eax
0x140024329  jz      loc_14002443E
0x14002432f  mov     rcx, rbx; pSid
0x140024332  call    cs:__imp_GetLengthSid
0x140024338  lea     r14d, [rax+14h]
0x14002433c  mov     ecx, r14d; unsigned __int64
0x14002433f  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x140024346  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x14002434b  mov     rcx, [rsi]; void *
0x14002434e  mov     [rsi], rax
0x140024351  test    rcx, rcx
0x140024354  jz      short loc_140024360
0x140024356  mov     edx, 8; struct std::nothrow_t *
0x14002435b  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140024360  mov     r8d, 2; dwAclRevision
0x140024366  mov     edx, r14d; nAclLength
0x140024369  mov     rcx, [rsi]; pAcl
0x14002436c  call    cs:__imp_InitializeAcl
0x140024372  test    eax, eax
0x140024374  jz      loc_140024472
0x14002437a  mov     [rsp+80h+pSid], rbx; pSid
0x14002437f  mov     r9d, 10000000h; AccessMask
0x140024385  xor     r8d, r8d; AceFlags
0x140024388  lea     edx, [r8+2]; dwAceRevision
0x14002438c  mov     rcx, [rsi]; pAcl
0x14002438f  call    cs:__imp_AddAccessAllowedAceEx
0x140024395  test    eax, eax
0x140024397  jz      loc_1400244A8
0x14002439d  mov     edx, 28h ; '('; uBytes
0x1400243a2  xor     ecx, ecx; uFlags
0x1400243a4  call    cs:__imp_LocalAlloc
0x1400243aa  mov     rbx, rax
0x1400243ad  xorps   xmm0, xmm0
0x1400243b0  xor     eax, eax
0x1400243b2  movups  xmmword ptr [rbx], xmm0
0x1400243b5  movups  xmmword ptr [rbx+10h], xmm0
0x1400243b9  mov     [rbx+20h], rax
0x1400243bd  lea     r14d, [rax+1]
0x1400243c1  mov     edx, r14d; dwRevision
0x1400243c4  mov     rcx, rbx; pSecurityDescriptor
0x1400243c7  call    cs:__imp_InitializeSecurityDescriptor
0x1400243cd  mov     rcx, rbx; hMem
0x1400243d0  test    eax, eax
0x1400243d2  jz      loc_1400244DE
0x1400243d8  xor     r9d, r9d; bDaclDefaulted
0x1400243db  mov     r8, [rsi]; pDacl
0x1400243de  mov     edx, r14d; bDaclPresent
0x1400243e1  call    cs:__imp_SetSecurityDescriptorDacl
0x1400243e7  test    eax, eax
0x1400243e9  jz      short loc_1400243FF
0x1400243eb  mov     [rdi], rbx
0x1400243ee  mov     rax, rdi
0x1400243f1  add     rsp, 80h
0x1400243f8  pop     r14
0x1400243fa  pop     rdi
0x1400243fb  pop     rsi
0x1400243fc  pop     rbx
0x1400243fd  pop     rbp
0x1400243fe  retn
0x1400243ff  mov     rcx, rbx; hMem
0x140024402  call    cs:__imp_LocalFree
0x140024408  lea     rdx, aSetsecuritydes; "SetSecurityDescriptorDacl"
0x14002440f  lea     rcx, [rbp+var_30]
0x140024413  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x140024418  nop
0x140024419  call    ?GetLastErrorHr@@YAJH@Z; GetLastErrorHr(int)
0x14002441e  mov     edx, eax
0x140024420  lea     r8, [rbp+var_30]
0x140024424  lea     rcx, [rbp+pExceptionObject]
0x140024428  call    ??0hr_exception@sih@@QEAA@JAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; sih::hr_exception::hr_exception(long,std::string const &)
0x14002442d  lea     rdx, _TI3?AVhr_exception@sih@@; pThrowInfo
0x140024434  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x140024438  call    _CxxThrowException
0x14002443e  lea     rdx, aIsvalidsidCurr; "!IsValidSid(CurrentSid)"
0x140024445  lea     rcx, [rbp+pExceptionObject]
0x140024449  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x14002444e  nop
0x14002444f  lea     r8, [rbp+pExceptionObject]
0x140024453  mov     edx, 8007000Dh
0x140024458  lea     rcx, [rbp+var_30]
0x14002445c  call    ??0hr_exception@sih@@QEAA@JAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; sih::hr_exception::hr_exception(long,std::string const &)
0x140024461  lea     rdx, _TI3?AVhr_exception@sih@@; pThrowInfo
0x140024468  lea     rcx, [rbp+var_30]; pExceptionObject
0x14002446c  call    _CxxThrowException
0x140024472  lea     rdx, aInitializeacl; "InitializeAcl"
0x140024479  lea     rcx, [rbp+var_30]
0x14002447d  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x140024482  nop
0x140024483  call    ?GetLastErrorHr@@YAJH@Z; GetLastErrorHr(int)
0x140024488  mov     edx, eax
0x14002448a  lea     r8, [rbp+var_30]
0x14002448e  lea     rcx, [rbp+pExceptionObject]
0x140024492  call    ??0hr_exception@sih@@QEAA@JAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; sih::hr_exception::hr_exception(long,std::string const &)
0x140024497  lea     rdx, _TI3?AVhr_exception@sih@@; pThrowInfo
0x14002449e  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x1400244a2  call    _CxxThrowException
0x1400244a8  lea     rdx, aAddaccessallow; "AddAccessAllowedAceEx"
0x1400244af  lea     rcx, [rbp+var_30]
0x1400244b3  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1400244b8  nop
0x1400244b9  call    ?GetLastErrorHr@@YAJH@Z; GetLastErrorHr(int)
0x1400244be  mov     edx, eax
0x1400244c0  lea     r8, [rbp+var_30]
0x1400244c4  lea     rcx, [rbp+pExceptionObject]
0x1400244c8  call    ??0hr_exception@sih@@QEAA@JAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; sih::hr_exception::hr_exception(long,std::string const &)
0x1400244cd  lea     rdx, _TI3?AVhr_exception@sih@@; pThrowInfo
0x1400244d4  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x1400244d8  call    _CxxThrowException
0x1400244de  call    cs:__imp_LocalFree
0x1400244e4  lea     rdx, aInitializesecu; "InitializeSecurityDescriptor"
0x1400244eb  lea     rcx, [rbp+var_30]
0x1400244ef  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1400244f4  nop
0x1400244f5  call    ?GetLastErrorHr@@YAJH@Z; GetLastErrorHr(int)
0x1400244fa  mov     edx, eax
0x1400244fc  lea     r8, [rbp+var_30]
0x140024500  lea     rcx, [rbp+pExceptionObject]
0x140024504  call    ??0hr_exception@sih@@QEAA@JAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; sih::hr_exception::hr_exception(long,std::string const &)
0x140024509  lea     rdx, _TI3?AVhr_exception@sih@@; pThrowInfo
0x140024510  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x140024514  call    _CxxThrowException
```
