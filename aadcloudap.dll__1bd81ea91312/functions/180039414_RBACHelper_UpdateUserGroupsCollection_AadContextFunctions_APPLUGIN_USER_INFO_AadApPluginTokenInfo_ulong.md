# RBACHelper::UpdateUserGroupsCollection(AadContextFunctions *,_APPLUGIN_USER_INFO *,_AadApPluginTokenInfo *,ulong)

- ea: `0x180039414`
- end: `0x180039701`
- name: `?UpdateUserGroupsCollection@RBACHelper@@CAJPEAVAadContextFunctions@@PEAU_APPLUGIN_USER_INFO@@PEAU_AadApPluginTokenInfo@@K@Z`
- size: `749`
- prototype: `__int64 __fastcall(struct AadContextFunctions *, struct _APPLUGIN_USER_INFO *, struct _AadApPluginTokenInfo *, unsigned int)`
- caller_count: `2`
- callee_count: `8`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18000cf50`
- `0x18000f5cc`

## callees

- `0x180003c20`
- `0x1800069c0`
- `0x180006ac4`
- `0x180007df8`
- `0x180039414`
- `0x180071e14`
- `0x180078780`
- `0x1800a8010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800394d6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800394e0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800394e8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800394d6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800394e0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800394e8`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x1800394cc`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x1800394cc`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800396ae`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800396ae`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180039540`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180039540`

## string_xrefs

- `0x180039463`: `RBACHelper::UpdateUserGroupsCollection`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall RBACHelper::UpdateUserGroupsCollection(
        struct AadContextFunctions *a1,
        struct _APPLUGIN_USER_INFO *a2,
        struct _AadApPluginTokenInfo *a3)
{
  void **v6; // rdi
  signed int v7; // eax
  unsigned int v8; // r15d
  __int64 v9; // r13
  void **v10; // rax
  const void *v11; // r8
  void **v12; // rax
  unsigned int v13; // ebx
  __int64 nSubAuthority2; // [rsp+20h] [rbp-69h]
  __int64 nSubAuthority4; // [rsp+30h] [rbp-59h]
  int v17; // [rsp+60h] [rbp-29h] BYREF
  PSID pSid2; // [rsp+68h] [rbp-21h] BYREF
  const char *v19[6]; // [rsp+70h] [rbp-19h] BYREF
  struct _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+A0h] [rbp+17h] BYREF

  v17 = 0;
  *(_DWORD *)pIdentifierAuthority.Value = 0;
  *(_WORD *)&pIdentifierAuthority.Value[4] = 1280;
  pSid2 = 0;
  v6 = 0;
  DbgTracePrintHelper<unsigned long>::DbgTracePrintHelper<unsigned long>(
    (__int64)v19,
    (int)"rbachelper.cpp",
    (int)"RBACHelper::UpdateUserGroupsCollection",
    (int)&v17);
  if ( !a1 || !a2 )
  {
    v7 = -1073741811;
    v17 = -1073741811;
    LODWORD(nSubAuthority4) = 491;
    goto LABEL_24;
  }
  if ( !AllocateAndInitializeSid(&pIdentifierAuthority, 2u, 0x20u, 0x22Bu, 0, 0, 0, 0, 0, 0, &pSid2) )
  {
    v7 = (int)GetLastError() > 0 ? (unsigned __int16)GetLastError() | 0xC0070000 : GetLastError();
    v17 = v7;
    if ( v7 < 0 )
    {
      LODWORD(nSubAuthority4) = 500;
LABEL_24:
      LODWORD(nSubAuthority2) = v7;
      WPPTraceLogA(
        2,
        0,
        "%x 0x%08x %s:%u : %s:%ws",
        2,
        nSubAuthority2,
        "rbachelper.cpp",
        nSubAuthority4,
        "NTSTATUS",
        &base);
      goto LABEL_25;
    }
  }
  if ( *((_QWORD *)a2 + 4) && *((_DWORD *)a2 + 6) )
  {
    v8 = 0;
    while ( !EqualSid(*(PSID *)(*((_QWORD *)a2 + 4) + 8LL * v8), pSid2) )
    {
      if ( ++v8 >= *((_DWORD *)a2 + 6) )
        goto LABEL_14;
    }
  }
  else
  {
LABEL_14:
    v9 = *((unsigned int *)a2 + 6);
    v10 = (void **)(*(__int64 (__fastcall **)(struct AadContextFunctions *, _QWORD))(*(_QWORD *)a1 + 24LL))(
                     a1,
                     (unsigned int)(8 * (v9 + 1)));
    v6 = v10;
    if ( !v10 )
    {
      v7 = -1073741801;
      v17 = -1073741801;
      LODWORD(nSubAuthority4) = 523;
      goto LABEL_24;
    }
    v11 = (const void *)*((_QWORD *)a2 + 4);
    if ( v11 )
    {
      memcpy_s_0(v10, 8LL * *((unsigned int *)a2 + 6), v11, 8LL * *((unsigned int *)a2 + 6));
      (*(void (__fastcall **)(struct AadContextFunctions *, _QWORD))(*(_QWORD *)a1 + 32LL))(a1, *((_QWORD *)a2 + 4));
      *((_QWORD *)a2 + 4) = 0;
      *((_DWORD *)a2 + 6) = 0;
      if ( a3 )
      {
        *((_QWORD *)a3 + 5) = 0;
        *((_DWORD *)a3 + 8) = 0;
      }
    }
    v7 = DuplicateSID(a1, pSid2, &v6[v9]);
    v17 = v7;
    if ( v7 < 0 )
    {
      LODWORD(nSubAuthority4) = 544;
      goto LABEL_24;
    }
    v12 = v6;
    *((_QWORD *)a2 + 4) = v6;
    *((_DWORD *)a2 + 6) = v9 + 1;
    v6 = 0;
    if ( a3 )
    {
      *((_QWORD *)a3 + 5) = v12;
      *((_DWORD *)a3 + 8) = *((_DWORD *)a2 + 6);
    }
  }
LABEL_25:
  if ( pSid2 )
    FreeSid(pSid2);
  if ( v6 )
    (*(void (__fastcall **)(struct AadContextFunctions *, void **))(*(_QWORD *)a1 + 32LL))(a1, v6);
  v13 = v17;
  DbgTracePrintHelper<long>::~DbgTracePrintHelper<long>(v19);
  return v13;
}

```

## disassembly

```asm
0x180039414  mov     [rsp-8+arg_18], rbx
0x180039419  push    rbp
0x18003941a  push    rsi
0x18003941b  push    rdi
0x18003941c  push    r12
0x18003941e  push    r13
0x180039420  push    r14
0x180039422  push    r15
0x180039424  lea     rbp, [rsp-27h]
0x180039429  sub     rsp, 0B0h
0x180039430  mov     rax, cs:__security_cookie
0x180039437  xor     rax, rsp
0x18003943a  mov     [rbp+57h+var_38], rax
0x18003943e  mov     r14, r8
0x180039441  mov     rbx, rdx
0x180039444  mov     r12, rcx
0x180039447  xor     r13d, r13d
0x18003944a  mov     [rbp+57h+var_80], r13d
0x18003944e  mov     dword ptr [rbp+57h+pIdentifierAuthority.Value], r13d
0x180039452  mov     word ptr [rbp+57h+pIdentifierAuthority.Value+4], 500h
0x180039458  mov     [rbp+57h+pSid2], r13
0x18003945c  mov     edi, r13d
0x18003945f  lea     r9, [rbp+57h+var_80]
0x180039463  lea     r8, aRbachelperUpda_0; "RBACHelper::UpdateUserGroupsCollection"
0x18003946a  lea     r15, aOnecoreuapDsEx_18+21h; "rbachelper.cpp"
0x180039471  mov     rdx, r15
0x180039474  lea     rcx, [rbp+57h+var_70]
0x180039478  call    ??0?$DbgTracePrintHelper@K@@QEAA@PEBD0AEAKW4AadTracingEventType@@@Z; DbgTracePrintHelper<ulong>::DbgTracePrintHelper<ulong>(char const *,char const *,ulong &,AadTracingEventType)
0x18003947d  nop
0x18003947e  test    r12, r12
0x180039481  jz      loc_18003965C
0x180039487  test    rbx, rbx
0x18003948a  jz      loc_18003965C
0x180039490  lea     rax, [rbp+57h+pSid2]
0x180039494  mov     [rsp+0E0h+pSid], rax; pSid
0x180039499  mov     [rsp+0E0h+nSubAuthority7], r13d; nSubAuthority7
0x18003949e  mov     [rsp+0E0h+nSubAuthority6], r13d; nSubAuthority6
0x1800394a3  mov     [rsp+0E0h+nSubAuthority5], r13d; nSubAuthority5
0x1800394a8  mov     dword ptr [rsp+0E0h+nSubAuthority4], r13d; nSubAuthority4
0x1800394ad  mov     [rsp+0E0h+nSubAuthority3], r13d; nSubAuthority3
0x1800394b2  mov     dword ptr [rsp+0E0h+nSubAuthority2], r13d; nSubAuthority2
0x1800394b7  lea     esi, [r13+2]
0x1800394bb  mov     r9d, 22Bh; nSubAuthority1
0x1800394c1  lea     r8d, [r13+20h]; nSubAuthority0
0x1800394c5  mov     dl, sil; nSubAuthorityCount
0x1800394c8  lea     rcx, [rbp+57h+pIdentifierAuthority]; pIdentifierAuthority
0x1800394cc  call    cs:__imp_AllocateAndInitializeSid
0x1800394d2  test    eax, eax
0x1800394d4  jnz     short loc_180039522
0x1800394d6  call    cs:__imp_GetLastError
0x1800394dc  test    eax, eax
0x1800394de  jg      short loc_1800394E8
0x1800394e0  call    cs:__imp_GetLastError
0x1800394e6  jmp     short loc_1800394F6
0x1800394e8  call    cs:__imp_GetLastError
0x1800394ee  movzx   eax, ax
0x1800394f1  or      eax, 0C0070000h
0x1800394f6  mov     [rbp+57h+var_80], eax
0x1800394f9  test    eax, eax
0x1800394fb  jns     short loc_180039522
0x1800394fd  lea     rcx, base
0x180039504  mov     qword ptr [rsp+0E0h+nSubAuthority6], rcx
0x180039509  lea     rcx, aNtstatus; "NTSTATUS"
0x180039510  mov     qword ptr [rsp+0E0h+nSubAuthority5], rcx
0x180039515  mov     dword ptr [rsp+0E0h+nSubAuthority4], 1F4h
0x18003951d  jmp     loc_180039689
0x180039522  cmp     [rbx+20h], r13
0x180039526  jz      short loc_180039557
0x180039528  cmp     [rbx+18h], r13d
0x18003952c  jbe     short loc_180039557
0x18003952e  mov     r15d, r13d
0x180039531  mov     eax, r15d
0x180039534  mov     rcx, [rbx+20h]
0x180039538  mov     rdx, [rbp+57h+pSid2]; pSid2
0x18003953c  mov     rcx, [rcx+rax*8]; pSid1
0x180039540  call    cs:__imp_EqualSid
0x180039546  test    eax, eax
0x180039548  jnz     loc_1800396A5
0x18003954e  inc     r15d
0x180039551  cmp     r15d, [rbx+18h]
0x180039555  jb      short loc_180039531
0x180039557  mov     r13d, [rbx+18h]
0x18003955b  lea     r15d, [r13+1]
0x18003955f  mov     rax, [r12]
0x180039563  lea     edx, ds:0[r15*8]
0x18003956b  mov     rcx, r12
0x18003956e  mov     rax, [rax+18h]
0x180039572  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039577  mov     rdi, rax
0x18003957a  test    rax, rax
0x18003957d  jnz     short loc_1800395B8
0x18003957f  mov     eax, 0C0000017h
0x180039584  mov     [rbp+57h+var_80], eax
0x180039587  lea     rcx, base
0x18003958e  mov     qword ptr [rsp+0E0h+nSubAuthority6], rcx
0x180039593  lea     rcx, aNtstatus; "NTSTATUS"
0x18003959a  mov     qword ptr [rsp+0E0h+nSubAuthority5], rcx
0x18003959f  mov     dword ptr [rsp+0E0h+nSubAuthority4], 20Bh
0x1800395a7  lea     rcx, aOnecoreuapDsEx_18+21h; "rbachelper.cpp"
0x1800395ae  mov     qword ptr [rsp+0E0h+nSubAuthority3], rcx
0x1800395b3  jmp     loc_18003968E
0x1800395b8  mov     r8, [rbx+20h]; Source
0x1800395bc  test    r8, r8
0x1800395bf  jz      short loc_1800395FD
0x1800395c1  mov     edx, [rbx+18h]
0x1800395c4  shl     rdx, 3; DestinationSize
0x1800395c8  mov     r9, rdx; SourceSize
0x1800395cb  mov     rcx, rdi; Destination
0x1800395ce  call    memcpy_s_0
0x1800395d3  mov     rax, [r12]
0x1800395d7  mov     rdx, [rbx+20h]
0x1800395db  mov     rcx, r12
0x1800395de  mov     rax, [rax+20h]
0x1800395e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800395e7  xor     eax, eax
0x1800395e9  mov     [rbx+20h], rax
0x1800395ed  mov     [rbx+18h], eax
0x1800395f0  test    r14, r14
0x1800395f3  jz      short loc_1800395FD
0x1800395f5  mov     [r14+28h], rax
0x1800395f9  mov     [r14+20h], eax
0x1800395fd  lea     r8, [rdi+r13*8]; void **
0x180039601  mov     rdx, [rbp+57h+pSid2]; void *
0x180039605  mov     rcx, r12; struct AadContextFunctions *
0x180039608  call    ?DuplicateSID@@YAJPEAVAadContextFunctions@@PEAXPEAPEAX@Z; DuplicateSID(AadContextFunctions *,void *,void * *)
0x18003960d  mov     [rbp+57h+var_80], eax
0x180039610  xor     r13d, r13d
0x180039613  test    eax, eax
0x180039615  jns     short loc_18003963C
0x180039617  lea     rcx, base
0x18003961e  mov     qword ptr [rsp+0E0h+nSubAuthority6], rcx
0x180039623  lea     rcx, aNtstatus; "NTSTATUS"
0x18003962a  mov     qword ptr [rsp+0E0h+nSubAuthority5], rcx
0x18003962f  mov     dword ptr [rsp+0E0h+nSubAuthority4], 220h
0x180039637  jmp     loc_1800395A7
0x18003963c  mov     rax, rdi
0x18003963f  mov     [rbx+20h], rdi
0x180039643  mov     [rbx+18h], r15d
0x180039647  mov     rdi, r13
0x18003964a  test    r14, r14
0x18003964d  jz      short loc_1800396A5
0x18003964f  mov     [r14+28h], rax
0x180039653  mov     eax, [rbx+18h]
0x180039656  mov     [r14+20h], eax
0x18003965a  jmp     short loc_1800396A5
0x18003965c  mov     eax, 0C000000Dh
0x180039661  mov     [rbp+57h+var_80], eax
0x180039664  lea     rcx, base
0x18003966b  mov     qword ptr [rsp+0E0h+nSubAuthority6], rcx
0x180039670  lea     rcx, aNtstatus; "NTSTATUS"
0x180039677  mov     qword ptr [rsp+0E0h+nSubAuthority5], rcx
0x18003967c  mov     dword ptr [rsp+0E0h+nSubAuthority4], 1EBh
0x180039684  mov     esi, 2
0x180039689  mov     qword ptr [rsp+0E0h+nSubAuthority3], r15
0x18003968e  mov     dword ptr [rsp+0E0h+nSubAuthority2], eax
0x180039692  mov     r9d, esi
0x180039695  lea     r8, aX0x08xSUSWs; "%x 0x%08x %s:%u : %s:%ws"
0x18003969c  xor     edx, edx
0x18003969e  mov     ecx, esi
0x1800396a0  call    ?WPPTraceLogA@@YAXKW4AadTracingEventType@@PEBDZZ; WPPTraceLogA(ulong,AadTracingEventType,char const *,...)
0x1800396a5  mov     rcx, [rbp+57h+pSid2]; pSid
0x1800396a9  test    rcx, rcx
0x1800396ac  jz      short loc_1800396B4
0x1800396ae  call    cs:__imp_FreeSid
0x1800396b4  test    rdi, rdi
0x1800396b7  jz      short loc_1800396CC
0x1800396b9  mov     rax, [r12]
0x1800396bd  mov     rdx, rdi
0x1800396c0  mov     rcx, r12
0x1800396c3  mov     rax, [rax+20h]
0x1800396c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800396cc  mov     ebx, [rbp+57h+var_80]
0x1800396cf  lea     rcx, [rbp+57h+var_70]
0x1800396d3  call    ??1?$DbgTracePrintHelper@J@@QEAA@XZ; DbgTracePrintHelper<long>::~DbgTracePrintHelper<long>(void)
0x1800396d8  mov     eax, ebx
0x1800396da  mov     rcx, [rbp+57h+var_38]
0x1800396de  xor     rcx, rsp; StackCookie
0x1800396e1  call    __security_check_cookie
0x1800396e6  mov     rbx, [rsp+0E0h+arg_18]
0x1800396ee  add     rsp, 0B0h
0x1800396f5  pop     r15
0x1800396f7  pop     r14
0x1800396f9  pop     r13
0x1800396fb  pop     r12
0x1800396fd  pop     rdi
0x1800396fe  pop     rsi
0x1800396ff  pop     rbp
0x180039700  retn
```
