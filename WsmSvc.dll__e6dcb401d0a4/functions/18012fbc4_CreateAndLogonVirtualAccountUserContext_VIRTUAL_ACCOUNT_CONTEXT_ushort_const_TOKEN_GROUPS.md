# CreateAndLogonVirtualAccountUserContext(_VIRTUAL_ACCOUNT_CONTEXT * *,ushort const *,_TOKEN_GROUPS *)

- ea: `0x18012fbc4`
- end: `0x18012ff5f`
- name: `?CreateAndLogonVirtualAccountUserContext@@YAJPEAPEAU_VIRTUAL_ACCOUNT_CONTEXT@@PEBGPEAU_TOKEN_GROUPS@@@Z`
- size: `923`
- prototype: `__int64 __fastcall(struct _VIRTUAL_ACCOUNT_CONTEXT **, const unsigned __int16 *, struct _TOKEN_GROUPS *)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18012d8f4`

## callees

- `0x18005d800`
- `0x1800621e0`
- `0x180077490`
- `0x18012f9e8`
- `0x18012fbc4`
- `0x1801300a8`
- `0x180130138`
- `0x1801304a4`
- `0x1801304c8`
- `0x1801ba152`
- `0x1801ba1b0`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18012fee7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18012fee7`
- `ntdll!RtlFreeSid` at `0x18012febb`
- `ntdll!RtlFreeSid` at `0x18012feca`
- `ntdll!RtlFreeSid` at `0x18012febb`
- `ntdll!RtlFreeSid` at `0x18012feca`
- `ntdll!RtlAllocateAndInitializeSid` at `0x18012fd14`
- `ntdll!RtlAllocateAndInitializeSid` at `0x18012fd5e`
- `ntdll!RtlAllocateAndInitializeSid` at `0x18012fd14`
- `ntdll!RtlAllocateAndInitializeSid` at `0x18012fd5e`
- `ntdll!RtlInitUnicodeString` at `0x18012fcd3`
- `ntdll!RtlInitUnicodeString` at `0x18012fce0`
- `ntdll!RtlInitUnicodeString` at `0x18012fe39`
- `ntdll!RtlInitUnicodeString` at `0x18012fcd3`
- `ntdll!RtlInitUnicodeString` at `0x18012fce0`
- `ntdll!RtlInitUnicodeString` at `0x18012fe39`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x18012fed8`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x18012fed8`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaAddAccountRights` at `0x18012fe50`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaAddAccountRights` at `0x18012fe50`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaRemoveAccountRights` at `0x18012fe88`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaRemoveAccountRights` at `0x18012fe88`

## string_xrefs

- `0x18012fe2e`: `SeServiceLogonRight`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CreateAndLogonVirtualAccountUserContext(
        struct _VIRTUAL_ACCOUNT_CONTEXT **a1,
        const unsigned __int16 *a2,
        struct _TOKEN_GROUPS *a3)
{
  unsigned __int16 **v5; // rdi
  __int64 v6; // r14
  void *v7; // r15
  unsigned __int16 *v8; // rax
  unsigned __int16 *v9; // rsi
  int updated; // ebx
  signed __int32 v11; // r12d
  unsigned __int16 v12; // ax
  unsigned __int16 *v13; // rcx
  NTSTATUS v14; // eax
  unsigned __int16 **v15; // rax
  void *PolicyHandle; // rax
  NTSTATUS v17; // eax
  PSID v18; // rcx
  PSID AccountSid; // [rsp+60h] [rbp-49h] BYREF
  void *v21; // [rsp+68h] [rbp-41h] BYREF
  PSID Sid; // [rsp+70h] [rbp-39h] BYREF
  int v23; // [rsp+78h] [rbp-31h] BYREF
  struct _VIRTUAL_ACCOUNT_CONTEXT **v24; // [rsp+80h] [rbp-29h]
  struct _UNICODE_STRING DestinationString; // [rsp+88h] [rbp-21h] BYREF
  struct _UNICODE_STRING v26; // [rsp+98h] [rbp-11h] BYREF
  struct _UNICODE_STRING v27; // [rsp+A8h] [rbp-1h] BYREF
  _SID_IDENTIFIER_AUTHORITY IdentifierAuthority; // [rsp+B8h] [rbp+Fh] BYREF

  v24 = a1;
  *(_DWORD *)IdentifierAuthority.Value = 0;
  *(_WORD *)&IdentifierAuthority.Value[4] = 1280;
  v23 = 0;
  DestinationString = 0;
  v27 = 0;
  v5 = 0;
  Sid = 0;
  AccountSid = 0;
  v6 = -1;
  v21 = (void *)-1LL;
  v7 = 0;
  v8 = (unsigned __int16 *)WSManMemory::Alloc(512, 0, 0);
  v9 = v8;
  if ( !v8 )
  {
    updated = -2147024882;
LABEL_30:
    v18 = Sid;
    goto LABEL_31;
  }
  memset_0(v8, 0, 0x200u);
  v11 = _InterlockedExchangeAdd(&dword_180280C98, 1u);
  updated = StringCchPrintfW(v9, 0x100u, L"WinRM VA_%d_%s", (unsigned int)(v11 + 1), a2);
  if ( (int)(updated + 0x80000000) >= 0 && updated != -2147024774 )
  {
LABEL_29:
    WSManMemory::Free(v9, 0);
    goto LABEL_30;
  }
  v12 = *v9;
  if ( *v9 )
  {
    v13 = v9;
    do
    {
      if ( v12 == 92 )
        *v13 = 95;
      v12 = *++v13;
    }
    while ( *v13 );
  }
  RtlInitUnicodeString(&DestinationString, L"WinRM Virtual Users");
  RtlInitUnicodeString(&v27, v9);
  v14 = RtlAllocateAndInitializeSid(&IdentifierAuthority, 1u, 0x5Eu, 0, 0, 0, 0, 0, 0, 0, &Sid);
  if ( v14 < 0 )
    goto LABEL_11;
  v14 = RtlAllocateAndInitializeSid(&IdentifierAuthority, 2u, 0x5Eu, v11 + 1, 0, 0, 0, 0, 0, 0, &AccountSid);
  if ( v14 < 0 )
    goto LABEL_11;
  updated = AddSidMappingToLsa(&DestinationString, 0, Sid, (enum _LSA_SID_NAME_MAPPING_OPERATION_ERROR *)&v23);
  if ( updated < 0 )
    goto LABEL_29;
  updated = UpdateVirtualAccountRegEntry(v9, 0);
  if ( updated < 0 )
    goto LABEL_29;
  updated = AddSidMappingToLsa(&DestinationString, &v27, AccountSid, (enum _LSA_SID_NAME_MAPPING_OPERATION_ERROR *)&v23);
  if ( updated < 0 )
    goto LABEL_29;
  v15 = (unsigned __int16 **)WSManMemory::Alloc(32, 0, 0);
  v5 = v15;
  if ( !v15
    || (*(_OWORD *)v15 = 0, *((_OWORD *)v15 + 1) = 0, PolicyHandle = GetPolicyHandle(), (v7 = PolicyHandle) == 0) )
  {
    updated = -2147024882;
    goto LABEL_29;
  }
  if ( a3 )
  {
    updated = LogonVirtualAccountUser(v9, PolicyHandle, &v21, a3);
    if ( updated < 0 && updated != -2147023511 )
      goto LABEL_28;
    if ( updated != -2147023511 )
      goto LABEL_42;
    v6 = (__int64)v21;
  }
  v26 = 0;
  RtlInitUnicodeString(&v26, L"SeServiceLogonRight");
  v14 = LsaAddAccountRights(v7, AccountSid, (PLSA_UNICODE_STRING)&v26, 1u);
  if ( v14 < 0 )
  {
LABEL_11:
    updated = ResultFromWin32FromStatus(v14);
    goto LABEL_29;
  }
  updated = LogonVirtualAccountUser(v9, v7, &v21, a3);
  v17 = LsaRemoveAccountRights(v7, AccountSid, 0, (PLSA_UNICODE_STRING)&v26, 1u);
  if ( updated < 0 )
  {
LABEL_28:
    v6 = (__int64)v21;
    goto LABEL_29;
  }
  if ( v17 < 0 )
  {
    updated = ResultFromWin32FromStatus(v17);
    goto LABEL_28;
  }
LABEL_42:
  *v5 = v9;
  v5[1] = (unsigned __int16 *)Sid;
  v5[2] = (unsigned __int16 *)AccountSid;
  v5[3] = (unsigned __int16 *)v21;
  v18 = 0;
  Sid = 0;
  AccountSid = 0;
  v6 = -1;
  *v24 = (struct _VIRTUAL_ACCOUNT_CONTEXT *)v5;
  v5 = 0;
LABEL_31:
  if ( v18 )
    RtlFreeSid(v18);
  if ( AccountSid )
    RtlFreeSid(AccountSid);
  if ( v7 )
    LsaClose(v7);
  if ( v6 != -1 )
    CloseHandle((HANDLE)v6);
  if ( v5 )
    WSManMemory::Free(v5, 0);
  return (unsigned int)updated;
}

```

## disassembly

```asm
0x18012fbc4  mov     [rsp-8+arg_18], rbx
0x18012fbc9  push    rbp
0x18012fbca  push    rsi
0x18012fbcb  push    rdi
0x18012fbcc  push    r12
0x18012fbce  push    r13
0x18012fbd0  push    r14
0x18012fbd2  push    r15
0x18012fbd4  lea     rbp, [rsp-27h]
0x18012fbd9  sub     rsp, 0D0h
0x18012fbe0  mov     rax, cs:__security_cookie
0x18012fbe7  xor     rax, rsp
0x18012fbea  mov     [rbp+57h+var_40], rax
0x18012fbee  mov     r13, r8
0x18012fbf1  mov     rbx, rdx
0x18012fbf4  mov     [rbp+57h+var_80], rcx
0x18012fbf8  xor     r12d, r12d
0x18012fbfb  mov     dword ptr [rbp+57h+IdentifierAuthority.Value], r12d
0x18012fbff  mov     word ptr [rbp+57h+IdentifierAuthority.Value+4], 500h
0x18012fc05  mov     [rbp+57h+var_88], r12d
0x18012fc09  xorps   xmm0, xmm0
0x18012fc0c  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x18012fc10  xorps   xmm1, xmm1
0x18012fc13  movups  xmmword ptr [rbp+57h+var_58.Length], xmm1
0x18012fc17  mov     edi, r12d
0x18012fc1a  mov     [rbp+57h+var_90], r12
0x18012fc1e  mov     [rbp+57h+AccountSid], r12
0x18012fc22  or      r14, 0FFFFFFFFFFFFFFFFh
0x18012fc26  mov     [rbp+57h+var_98], r14
0x18012fc2a  mov     r15d, r12d
0x18012fc2d  xor     r8d, r8d
0x18012fc30  xor     edx, edx
0x18012fc32  mov     ecx, 200h
0x18012fc37  call    ?Alloc@WSManMemory@@SAPEAX_KHW4_NitsFaultMode@@@Z; WSManMemory::Alloc(unsigned __int64,int,_NitsFaultMode)
0x18012fc3c  mov     rsi, rax
0x18012fc3f  test    rax, rax
0x18012fc42  jnz     short loc_18012FC4E
0x18012fc44  mov     ebx, 8007000Eh
0x18012fc49  jmp     loc_18012FEB2
0x18012fc4e  xor     edx, edx; Val
0x18012fc50  mov     r8d, 200h; Size
0x18012fc56  mov     rcx, rsi; void *
0x18012fc59  call    memset_0
0x18012fc5e  mov     r12d, 1
0x18012fc64  lock xadd cs:dword_180280C98, r12d
0x18012fc6d  mov     qword ptr [rsp+100h+SubAuthority2], rbx
0x18012fc72  lea     r9d, [r12+1]
0x18012fc77  lea     r8, aWinrmVaDS; "WinRM VA_%d_%s"
0x18012fc7e  mov     edx, 100h; unsigned __int64
0x18012fc83  mov     rcx, rsi; unsigned __int16 *
0x18012fc86  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18012fc8b  mov     ebx, eax
0x18012fc8d  mov     ecx, 80000000h
0x18012fc92  add     eax, ecx
0x18012fc94  test    ecx, eax
0x18012fc96  jnz     short loc_18012FCA4
0x18012fc98  cmp     ebx, 8007007Ah
0x18012fc9e  jnz     loc_18012FEA7
0x18012fca4  movzx   eax, word ptr [rsi]
0x18012fca7  xor     ebx, ebx
0x18012fca9  test    ax, ax
0x18012fcac  jz      short loc_18012FCC8
0x18012fcae  mov     rcx, rsi
0x18012fcb1  cmp     ax, 5Ch ; '\'
0x18012fcb5  jnz     short loc_18012FCBC
0x18012fcb7  mov     word ptr [rcx], 5Fh ; '_'
0x18012fcbc  add     rcx, 2
0x18012fcc0  movzx   eax, word ptr [rcx]
0x18012fcc3  test    ax, ax
0x18012fcc6  jnz     short loc_18012FCB1
0x18012fcc8  lea     rdx, aWinrmVirtualUs; "WinRM Virtual Users"
0x18012fccf  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x18012fcd3  call    cs:__imp_RtlInitUnicodeString
0x18012fcd9  mov     rdx, rsi; SourceString
0x18012fcdc  lea     rcx, [rbp+57h+var_58]; DestinationString
0x18012fce0  call    cs:__imp_RtlInitUnicodeString
0x18012fce6  lea     rax, [rbp+57h+var_90]
0x18012fcea  mov     [rsp+100h+Sid], rax; Sid
0x18012fcef  mov     [rsp+100h+SubAuthority7], ebx; SubAuthority7
0x18012fcf3  mov     [rsp+100h+SubAuthority6], ebx; SubAuthority6
0x18012fcf7  mov     [rsp+100h+SubAuthority5], ebx; SubAuthority5
0x18012fcfb  mov     [rsp+100h+SubAuthority4], ebx; SubAuthority4
0x18012fcff  mov     [rsp+100h+SubAuthority3], ebx; SubAuthority3
0x18012fd03  mov     [rsp+100h+SubAuthority2], ebx; SubAuthority2
0x18012fd07  xor     r9d, r9d; SubAuthority1
0x18012fd0a  lea     r8d, [r9+5Eh]; SubAuthority0
0x18012fd0e  mov     dl, 1; SubAuthorityCount
0x18012fd10  lea     rcx, [rbp+57h+IdentifierAuthority]; IdentifierAuthority
0x18012fd14  call    cs:__imp_RtlAllocateAndInitializeSid
0x18012fd1a  test    eax, eax
0x18012fd1c  jns     short loc_18012FD2C
0x18012fd1e  mov     ecx, eax; int
0x18012fd20  call    ?ResultFromWin32FromStatus@@YAJJ@Z; ResultFromWin32FromStatus(long)
0x18012fd25  mov     ebx, eax
0x18012fd27  jmp     loc_18012FEA7
0x18012fd2c  lea     rax, [rbp+57h+AccountSid]
0x18012fd30  mov     [rsp+100h+Sid], rax; Sid
0x18012fd35  mov     [rsp+100h+SubAuthority7], ebx; SubAuthority7
0x18012fd39  mov     [rsp+100h+SubAuthority6], ebx; SubAuthority6
0x18012fd3d  mov     [rsp+100h+SubAuthority5], ebx; SubAuthority5
0x18012fd41  mov     [rsp+100h+SubAuthority4], ebx; SubAuthority4
0x18012fd45  mov     [rsp+100h+SubAuthority3], ebx; SubAuthority3
0x18012fd49  mov     [rsp+100h+SubAuthority2], ebx; SubAuthority2
0x18012fd4d  lea     r9d, [r12+1]; SubAuthority1
0x18012fd52  mov     r8d, 5Eh ; '^'; SubAuthority0
0x18012fd58  mov     dl, 2; SubAuthorityCount
0x18012fd5a  lea     rcx, [rbp+57h+IdentifierAuthority]; IdentifierAuthority
0x18012fd5e  call    cs:__imp_RtlAllocateAndInitializeSid
0x18012fd64  xor     r12d, r12d
0x18012fd67  test    eax, eax
0x18012fd69  js      short loc_18012FD1E
0x18012fd6b  lea     r9, [rbp+57h+var_88]; enum _LSA_SID_NAME_MAPPING_OPERATION_ERROR *
0x18012fd6f  mov     r8, [rbp+57h+var_90]; void *
0x18012fd73  xor     edx, edx; struct _UNICODE_STRING *
0x18012fd75  lea     rcx, [rbp+57h+DestinationString]; struct _UNICODE_STRING *
0x18012fd79  call    ?AddSidMappingToLsa@@YAJPEAU_UNICODE_STRING@@0PEAXPEAW4_LSA_SID_NAME_MAPPING_OPERATION_ERROR@@@Z; AddSidMappingToLsa(_UNICODE_STRING *,_UNICODE_STRING *,void *,_LSA_SID_NAME_MAPPING_OPERATION_ERROR *)
0x18012fd7e  mov     ebx, eax
0x18012fd80  test    eax, eax
0x18012fd82  js      loc_18012FEA7
0x18012fd88  xor     edx, edx; bool
0x18012fd8a  mov     rcx, rsi; lpSubKey
0x18012fd8d  call    ?UpdateVirtualAccountRegEntry@@YAJPEAG_N@Z; UpdateVirtualAccountRegEntry(ushort *,bool)
0x18012fd92  mov     ebx, eax
0x18012fd94  test    eax, eax
0x18012fd96  js      loc_18012FEA7
0x18012fd9c  lea     r9, [rbp+57h+var_88]; enum _LSA_SID_NAME_MAPPING_OPERATION_ERROR *
0x18012fda0  mov     r8, [rbp+57h+AccountSid]; void *
0x18012fda4  lea     rdx, [rbp+57h+var_58]; struct _UNICODE_STRING *
0x18012fda8  lea     rcx, [rbp+57h+DestinationString]; struct _UNICODE_STRING *
0x18012fdac  call    ?AddSidMappingToLsa@@YAJPEAU_UNICODE_STRING@@0PEAXPEAW4_LSA_SID_NAME_MAPPING_OPERATION_ERROR@@@Z; AddSidMappingToLsa(_UNICODE_STRING *,_UNICODE_STRING *,void *,_LSA_SID_NAME_MAPPING_OPERATION_ERROR *)
0x18012fdb1  mov     ebx, eax
0x18012fdb3  test    eax, eax
0x18012fdb5  js      loc_18012FEA7
0x18012fdbb  xor     r8d, r8d
0x18012fdbe  xor     edx, edx
0x18012fdc0  lea     ecx, [rdx+20h]
0x18012fdc3  call    ?Alloc@WSManMemory@@SAPEAX_KHW4_NitsFaultMode@@@Z; WSManMemory::Alloc(unsigned __int64,int,_NitsFaultMode)
0x18012fdc8  mov     rdi, rax
0x18012fdcb  test    rax, rax
0x18012fdce  jnz     short loc_18012FDDA
0x18012fdd0  mov     ebx, 8007000Eh
0x18012fdd5  jmp     loc_18012FEA7
0x18012fdda  xorps   xmm0, xmm0
0x18012fddd  movups  xmmword ptr [rax], xmm0
0x18012fde0  movups  xmmword ptr [rax+10h], xmm0
0x18012fde4  call    ?GetPolicyHandle@@YAPEAXXZ; GetPolicyHandle(void)
0x18012fde9  mov     r15, rax
0x18012fdec  test    rax, rax
0x18012fdef  jz      short loc_18012FDD0
0x18012fdf1  test    r13, r13
0x18012fdf4  jz      short loc_18012FE27
0x18012fdf6  mov     r9, r13; struct _TOKEN_GROUPS *
0x18012fdf9  lea     r8, [rbp+57h+var_98]; void **
0x18012fdfd  mov     rdx, rax; void *
0x18012fe00  mov     rcx, rsi; unsigned __int16 *
0x18012fe03  call    ?LogonVirtualAccountUser@@YAJPEBGPEAXPEAPEAXPEAU_TOKEN_GROUPS@@@Z; LogonVirtualAccountUser(ushort const *,void *,void * *,_TOKEN_GROUPS *)
0x18012fe08  mov     ebx, eax
0x18012fe0a  mov     eax, 80070569h
0x18012fe0f  test    ebx, ebx
0x18012fe11  jns     short loc_18012FE1B
0x18012fe13  cmp     ebx, eax
0x18012fe15  jnz     loc_18012FEA3
0x18012fe1b  cmp     ebx, eax
0x18012fe1d  jnz     loc_18012FF26
0x18012fe23  mov     r14, [rbp+57h+var_98]
0x18012fe27  xorps   xmm0, xmm0
0x18012fe2a  movups  xmmword ptr [rbp+57h+var_68.Length], xmm0
0x18012fe2e  lea     rdx, aSeservicelogon; "SeServiceLogonRight"
0x18012fe35  lea     rcx, [rbp+57h+var_68]; DestinationString
0x18012fe39  call    cs:__imp_RtlInitUnicodeString
0x18012fe3f  mov     r9d, 1; CountOfRights
0x18012fe45  lea     r8, [rbp+57h+var_68]; UserRights
0x18012fe49  mov     rdx, [rbp+57h+AccountSid]; AccountSid
0x18012fe4d  mov     rcx, r15; PolicyHandle
0x18012fe50  call    cs:__imp_LsaAddAccountRights
0x18012fe56  test    eax, eax
0x18012fe58  js      loc_18012FD1E
0x18012fe5e  mov     r9, r13; struct _TOKEN_GROUPS *
0x18012fe61  lea     r8, [rbp+57h+var_98]; void **
0x18012fe65  mov     rdx, r15; void *
0x18012fe68  mov     rcx, rsi; unsigned __int16 *
0x18012fe6b  call    ?LogonVirtualAccountUser@@YAJPEBGPEAXPEAPEAXPEAU_TOKEN_GROUPS@@@Z; LogonVirtualAccountUser(ushort const *,void *,void * *,_TOKEN_GROUPS *)
0x18012fe70  mov     ebx, eax
0x18012fe72  mov     [rsp+100h+SubAuthority2], 1; CountOfRights
0x18012fe7a  lea     r9, [rbp+57h+var_68]; UserRights
0x18012fe7e  xor     r8d, r8d; AllRights
0x18012fe81  mov     rdx, [rbp+57h+AccountSid]; AccountSid
0x18012fe85  mov     rcx, r15; PolicyHandle
0x18012fe88  call    cs:__imp_LsaRemoveAccountRights
0x18012fe8e  test    ebx, ebx
0x18012fe90  js      short loc_18012FEA3
0x18012fe92  test    eax, eax
0x18012fe94  jns     loc_18012FF26
0x18012fe9a  mov     ecx, eax; int
0x18012fe9c  call    ?ResultFromWin32FromStatus@@YAJJ@Z; ResultFromWin32FromStatus(long)
0x18012fea1  mov     ebx, eax
0x18012fea3  mov     r14, [rbp+57h+var_98]
0x18012fea7  xor     edx, edx; int
0x18012fea9  mov     rcx, rsi; void *
0x18012feac  call    ?Free@WSManMemory@@SAXPEAXH@Z; WSManMemory::Free(void *,int)
0x18012feb1  nop
0x18012feb2  mov     rcx, [rbp+57h+var_90]; Sid
0x18012feb6  test    rcx, rcx
0x18012feb9  jz      short loc_18012FEC1
0x18012febb  call    cs:__imp_RtlFreeSid
0x18012fec1  mov     rcx, [rbp+57h+AccountSid]; Sid
0x18012fec5  test    rcx, rcx
0x18012fec8  jz      short loc_18012FED0
0x18012feca  call    cs:__imp_RtlFreeSid
0x18012fed0  test    r15, r15
0x18012fed3  jz      short loc_18012FEDE
0x18012fed5  mov     rcx, r15; ObjectHandle
0x18012fed8  call    cs:__imp_LsaClose
0x18012fede  cmp     r14, 0FFFFFFFFFFFFFFFFh
0x18012fee2  jz      short loc_18012FEED
0x18012fee4  mov     rcx, r14; hObject
0x18012fee7  call    cs:__imp_CloseHandle
0x18012feed  test    rdi, rdi
0x18012fef0  jz      short loc_18012FEFD
0x18012fef2  xor     edx, edx; int
0x18012fef4  mov     rcx, rdi; void *
0x18012fef7  call    ?Free@WSManMemory@@SAXPEAXH@Z; WSManMemory::Free(void *,int)
0x18012fefc  nop
0x18012fefd  mov     eax, ebx
0x18012feff  mov     rcx, [rbp+57h+var_40]
0x18012ff03  xor     rcx, rsp; StackCookie
0x18012ff06  call    __security_check_cookie
0x18012ff0b  mov     rbx, [rsp+100h+arg_18]
0x18012ff13  add     rsp, 0D0h
0x18012ff1a  pop     r15
0x18012ff1c  pop     r14
0x18012ff1e  pop     r13
0x18012ff20  pop     r12
0x18012ff22  pop     rdi
0x18012ff23  pop     rsi
0x18012ff24  pop     rbp
0x18012ff25  retn
0x18012ff26  mov     [rdi], rsi
0x18012ff29  mov     rax, [rbp+57h+var_90]
0x18012ff2d  mov     [rdi+8], rax
0x18012ff31  mov     rax, [rbp+57h+AccountSid]
0x18012ff35  mov     [rdi+10h], rax
0x18012ff39  mov     rax, [rbp+57h+var_98]
0x18012ff3d  mov     [rdi+18h], rax
0x18012ff41  mov     rcx, r12
0x18012ff44  mov     [rbp+57h+var_90], rcx
0x18012ff48  mov     [rbp+57h+AccountSid], r12
0x18012ff4c  or      r14, 0FFFFFFFFFFFFFFFFh
0x18012ff50  mov     rax, [rbp+57h+var_80]
0x18012ff54  mov     [rax], rdi
0x18012ff57  mov     rdi, r12
0x18012ff5a  jmp     loc_18012FEB6
```
