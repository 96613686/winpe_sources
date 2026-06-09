# ResetRegTreeSecurityInternal(HKEY__ *,ushort const *,void *)

- ea: `0x1800a457c`
- end: `0x1800a47a4`
- name: `?ResetRegTreeSecurityInternal@@YAJPEAUHKEY__@@PEBGPEAX@Z`
- size: `552`
- prototype: `int(HKEY, const unsigned __int16 *, void *)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800a508c`

## callees

- `0x180005020`
- `0x180012fc8`
- `0x1800a457c`
- `0x1800aed10`
- `0x1800af918`
- `0x1800b0f54`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a4756`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a4756`
- `ADVAPI32!TreeResetNamedSecurityInfoW` at `0x1800a4719`
- `ADVAPI32!TreeResetNamedSecurityInfoW` at `0x1800a4719`
- `NTMARTA!AccTreeResetNamedSecurityInfo` at `0x1800a473e`
- `NTMARTA!AccTreeResetNamedSecurityInfo` at `0x1800a473e`
- `api-ms-win-security-provider-l1-1-0!SetEntriesInAclW` at `0x1800a46c7`
- `api-ms-win-security-provider-l1-1-0!SetEntriesInAclW` at `0x1800a46c7`

## string_xrefs

- `0x1800a4611`: `onecore\admin\appmodel\common\removeregistrytree.cpp`
- `0x1800a4674`: `onecore\admin\appmodel\common\removeregistrytree.cpp`

## pseudocode

```c
__int64 __fastcall ResetRegTreeSecurityInternal(HKEY a1, const unsigned __int16 *a2, WCHAR *a3)
{
  int v6; // edi
  __int64 v7; // rdx
  int v9; // eax
  signed int v10; // ebx
  DWORD v11; // eax
  int pGroup; // [rsp+20h] [rbp-E0h]
  PACL NewAcl; // [rsp+60h] [rbp-A0h] BYREF
  struct _EXPLICIT_ACCESS_W pListOfExplicitEntries; // [rsp+68h] [rbp-98h] BYREF
  WCHAR pObjectName; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE v16[526]; // [rsp+A2h] [rbp-5Eh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2E8h] [rbp+1E8h]

  NewAcl = 0;
  pObjectName = 0;
  memset(&pListOfExplicitEntries, 0, sizeof(pListOfExplicitEntries));
  memset_0(v16, 0, 0x208u);
  if ( a1 == HKEY_LOCAL_MACHINE )
  {
    v6 = StringCchCatW(&pObjectName, 0x105u, L"MACHINE\\");
    if ( v6 < 0 )
    {
      v7 = 85;
LABEL_4:
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)v7,
        (unsigned int)"onecore\\admin\\appmodel\\common\\removeregistrytree.cpp",
        (const char *)(unsigned int)v6,
        pGroup);
      return (unsigned int)v6;
    }
  }
  else
  {
    if ( a1 != HKEY_USERS )
      return 2147942487LL;
    v6 = StringCchCatW(&pObjectName, 0x105u, L"USERS\\");
    if ( v6 < 0 )
    {
      v7 = 89;
      goto LABEL_4;
    }
  }
  v9 = StringCchCatW(&pObjectName, 0x105u, a2);
  v10 = v9;
  if ( v9 >= 0 )
  {
    pListOfExplicitEntries.grfAccessPermissions = 268697600;
    pListOfExplicitEntries.grfAccessMode = GRANT_ACCESS;
    pListOfExplicitEntries.grfInheritance = 3;
    pListOfExplicitEntries.Trustee.pMultipleTrustee = 0;
    *(_QWORD *)&pListOfExplicitEntries.Trustee.MultipleTrusteeOperation = 0;
    pListOfExplicitEntries.Trustee.TrusteeType = TRUSTEE_IS_USER;
    pListOfExplicitEntries.Trustee.ptstrName = a3;
    v10 = SetEntriesInAclW(1u, &pListOfExplicitEntries, 0, &NewAcl);
    if ( !v10 )
    {
      if ( (unsigned __int8)IsTreeResetNamedSecurityInfoWPresent() )
        v11 = TreeResetNamedSecurityInfoW(
                &pObjectName,
                SE_REGISTRY_KEY,
                0x80000004,
                0,
                0,
                NewAcl,
                0,
                0,
                0,
                ProgressInvokeNever,
                0);
      else
        v11 = AccTreeResetNamedSecurityInfo(&pObjectName, 4, 2147483652LL, 0, 0, NewAcl, 0, 2, 0, 1, 0);
      v10 = v11;
    }
    if ( NewAcl )
      LocalFree(NewAcl);
    if ( v10 > 0 )
      return (unsigned __int16)v10 | 0x80070000;
  }
  else
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x64,
      (unsigned int)"onecore\\admin\\appmodel\\common\\removeregistrytree.cpp",
      (const char *)(unsigned int)v9,
      pGroup);
  }
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x1800a457c  mov     [rsp-8+arg_0], rbx
0x1800a4581  push    rbp
0x1800a4582  push    rsi
0x1800a4583  push    rdi
0x1800a4584  push    r14
0x1800a4586  push    r15
0x1800a4588  lea     rbp, [rsp-1C0h]
0x1800a4590  sub     rsp, 2C0h
0x1800a4597  mov     rax, cs:__security_cookie
0x1800a459e  xor     rax, rsp
0x1800a45a1  mov     [rbp+1E0h+var_30], rax
0x1800a45a8  xorps   xmm0, xmm0
0x1800a45ab  mov     r14, r8
0x1800a45ae  mov     rsi, rdx
0x1800a45b1  mov     rbx, rcx
0x1800a45b4  xor     r15d, r15d
0x1800a45b7  lea     rcx, [rbp+1E0h+var_23E]; void *
0x1800a45bb  xor     edx, edx; Val
0x1800a45bd  mov     [rsp+2E0h+NewAcl], r15
0x1800a45c2  mov     r8d, 208h; Size
0x1800a45c8  mov     [rbp+1E0h+pObjectName], r15w
0x1800a45cd  movups  xmmword ptr [rsp+2E0h+pListOfExplicitEntries.grfAccessPermissions], xmm0
0x1800a45d2  movups  xmmword ptr [rsp+2E0h+pListOfExplicitEntries.Trustee.pMultipleTrustee], xmm0
0x1800a45d7  movups  xmmword ptr [rbp+1E0h+pListOfExplicitEntries.Trustee.TrusteeType], xmm0
0x1800a45db  call    memset_0
0x1800a45e0  cmp     rbx, 0FFFFFFFF80000002h
0x1800a45e7  jnz     short loc_1800A4627
0x1800a45e9  mov     ebx, 105h
0x1800a45ee  lea     r8, aMachine_1; "MACHINE\\"
0x1800a45f5  mov     edx, ebx; unsigned __int64
0x1800a45f7  lea     rcx, [rbp+1E0h+pObjectName]; unsigned __int16 *
0x1800a45fb  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800a4600  mov     edi, eax
0x1800a4602  test    eax, eax
0x1800a4604  jns     short loc_1800A4658
0x1800a4606  lea     edx, [r15+55h]; void *
0x1800a460a  mov     rcx, [rbp+1E8h]; this
0x1800a4611  lea     r8, aOnecoreAdminAp_112; "onecore\\admin\\appmodel\\common\\remov"...
0x1800a4618  mov     r9d, edi; char *
0x1800a461b  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800a4620  mov     eax, edi
0x1800a4622  jmp     loc_1800A477D
0x1800a4627  cmp     rbx, 0FFFFFFFF80000003h
0x1800a462e  jnz     loc_1800A4778
0x1800a4634  mov     ebx, 105h
0x1800a4639  lea     r8, aUsers; "USERS\\"
0x1800a4640  mov     edx, ebx; unsigned __int64
0x1800a4642  lea     rcx, [rbp+1E0h+pObjectName]; unsigned __int16 *
0x1800a4646  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800a464b  mov     edi, eax
0x1800a464d  test    eax, eax
0x1800a464f  jns     short loc_1800A4658
0x1800a4651  mov     edx, 59h ; 'Y'
0x1800a4656  jmp     short loc_1800A460A
0x1800a4658  mov     r8, rsi; unsigned __int16 *
0x1800a465b  lea     rcx, [rbp+1E0h+pObjectName]; unsigned __int16 *
0x1800a465f  mov     rdx, rbx; unsigned __int64
0x1800a4662  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800a4667  mov     ebx, eax
0x1800a4669  test    eax, eax
0x1800a466b  jns     short loc_1800A468F
0x1800a466d  mov     rcx, [rbp+1E8h]; this
0x1800a4674  lea     r8, aOnecoreAdminAp_112; "onecore\\admin\\appmodel\\common\\remov"...
0x1800a467b  mov     r9d, eax; char *
0x1800a467e  mov     edx, 64h ; 'd'; void *
0x1800a4683  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800a4688  mov     eax, ebx
0x1800a468a  jmp     loc_1800A477D
0x1800a468f  mov     edi, 1
0x1800a4694  mov     [rsp+2E0h+pListOfExplicitEntries.grfAccessPermissions], 10040000h
0x1800a469c  mov     ecx, edi; cCountOfExplicitEntries
0x1800a469e  mov     [rsp+2E0h+pListOfExplicitEntries.grfAccessMode], edi
0x1800a46a2  lea     r9, [rsp+2E0h+NewAcl]; NewAcl
0x1800a46a7  mov     [rsp+2E0h+pListOfExplicitEntries.grfInheritance], 3
0x1800a46af  xor     r8d, r8d; OldAcl
0x1800a46b2  mov     [rsp+2E0h+pListOfExplicitEntries.Trustee.pMultipleTrustee], r15
0x1800a46b7  lea     rdx, [rsp+2E0h+pListOfExplicitEntries]; pListOfExplicitEntries
0x1800a46bc  mov     qword ptr [rbp+1E0h+pListOfExplicitEntries.Trustee.MultipleTrusteeOperation], r15
0x1800a46c0  mov     [rbp+1E0h+pListOfExplicitEntries.Trustee.TrusteeType], edi
0x1800a46c3  mov     [rbp+1E0h+pListOfExplicitEntries.Trustee.ptstrName], r14
0x1800a46c7  call    cs:__imp_SetEntriesInAclW
0x1800a46ce  nop     dword ptr [rax+rax+00h]
0x1800a46d3  mov     ebx, eax
0x1800a46d5  test    eax, eax
0x1800a46d7  jnz     short loc_1800A474C
0x1800a46d9  call    IsTreeResetNamedSecurityInfoWPresent
0x1800a46de  mov     [rsp+2E0h+Args], r15; Args
0x1800a46e3  lea     edx, [rdi+3]; ObjectType
0x1800a46e6  xor     r9d, r9d; pOwner
0x1800a46e9  mov     [rsp+2E0h+ProgressInvokeSetting], edi; ProgressInvokeSetting
0x1800a46ed  test    al, al
0x1800a46ef  mov     [rsp+2E0h+fnProgress], r15; fnProgress
0x1800a46f4  mov     rax, [rsp+2E0h+NewAcl]
0x1800a46f9  lea     rcx, [rbp+1E0h+pObjectName]; pObjectName
0x1800a46fd  mov     r8d, 80000004h; SecurityInfo
0x1800a4703  jz      short loc_1800A4727
0x1800a4705  mov     [rsp+2E0h+KeepExplicit], r15d; KeepExplicit
0x1800a470a  mov     [rsp+2E0h+pSacl], r15; pSacl
0x1800a470f  mov     [rsp+2E0h+pDacl], rax; pDacl
0x1800a4714  mov     [rsp+2E0h+pGroup], r15; pGroup
0x1800a4719  call    cs:__imp_TreeResetNamedSecurityInfoW
0x1800a4720  nop     dword ptr [rax+rax+00h]
0x1800a4725  jmp     short loc_1800A474A
0x1800a4727  mov     [rsp+2E0h+KeepExplicit], 2
0x1800a472f  mov     [rsp+2E0h+pSacl], r15
0x1800a4734  mov     [rsp+2E0h+pDacl], rax
0x1800a4739  mov     [rsp+2E0h+pGroup], r15
0x1800a473e  call    cs:__imp_AccTreeResetNamedSecurityInfo
0x1800a4745  nop     dword ptr [rax+rax+00h]
0x1800a474a  mov     ebx, eax
0x1800a474c  mov     rcx, [rsp+2E0h+NewAcl]; hMem
0x1800a4751  test    rcx, rcx
0x1800a4754  jz      short loc_1800A4762
0x1800a4756  call    cs:__imp_LocalFree
0x1800a475d  nop     dword ptr [rax+rax+00h]
0x1800a4762  test    ebx, ebx
0x1800a4764  jle     loc_1800A4688
0x1800a476a  movzx   ebx, bx
0x1800a476d  or      ebx, 80070000h
0x1800a4773  jmp     loc_1800A4688
0x1800a4778  mov     eax, 80070057h
0x1800a477d  mov     rcx, [rbp+1E0h+var_30]
0x1800a4784  xor     rcx, rsp; StackCookie
0x1800a4787  call    __security_check_cookie
0x1800a478c  mov     rbx, [rsp+2E0h+arg_0]
0x1800a4794  add     rsp, 2C0h
0x1800a479b  pop     r15
0x1800a479d  pop     r14
0x1800a479f  pop     rdi
0x1800a47a0  pop     rsi
0x1800a47a1  pop     rbp
0x1800a47a2  retn
```
