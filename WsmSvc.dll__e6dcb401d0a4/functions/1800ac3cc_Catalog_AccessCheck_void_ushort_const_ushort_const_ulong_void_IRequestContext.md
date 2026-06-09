# Catalog::AccessCheck(void *,ushort const *,ushort const *,ulong,void *,IRequestContext &)

- ea: `0x1800ac3cc`
- end: `0x1800ac65c`
- name: `?AccessCheck@Catalog@@AEBA_NPEAXPEBG1K0AEAVIRequestContext@@@Z`
- size: `656`
- prototype: `char __fastcall(Catalog *this, void *, WCHAR *, WCHAR *, DWORD DesiredAccess, PSECURITY_DESCRIPTOR SecurityDescriptor, struct IRequestContext *)`
- caller_count: `2`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800ac0d8`
- `0x18012d088`

## callees

- `0x18002aee0`
- `0x1800ac3cc`
- `0x180103850`
- `0x1801123a8`
- `0x18012352c`
- `0x1801c2010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ac3fd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ac4dd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ac5e8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ac3fd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ac4dd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ac5e8`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x1800ac3f3`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x1800ac3f3`
- `api-ms-win-security-base-l1-1-0!AccessCheckAndAuditAlarmW` at `0x1800ac4cb`
- `api-ms-win-security-base-l1-1-0!AccessCheckAndAuditAlarmW` at `0x1800ac4cb`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
char __fastcall Catalog::AccessCheck(
        Catalog *this,
        void *a2,
        WCHAR *a3,
        WCHAR *a4,
        DWORD DesiredAccess,
        PSECURITY_DESCRIPTOR SecurityDescriptor,
        struct IRequestContext *a7)
{
  __int64 LastError; // rbx
  _QWORD *v11; // rcx
  __int64 v12; // rdx
  __int64 v13; // r9
  BOOL v14; // eax
  struct IRequestContext *v15; // r14
  __int64 v16; // rbx
  char v17; // bl
  void (__fastcall *v18)(struct IRequestContext *, _QWORD); // rbx
  DWORD v19; // eax
  unsigned int v20; // eax
  BOOL pfGenerateOnClose; // [rsp+60h] [rbp-38h] BYREF
  Catalog *AccessStatus; // [rsp+A0h] [rbp+8h] BYREF
  DWORD GrantedAccess; // [rsp+A8h] [rbp+10h] BYREF

  AccessStatus = this;
  if ( a2 && !ImpersonateLoggedOnUser(a2) )
  {
    LastError = GetLastError();
    (*(void (__fastcall **)(struct IRequestContext *, __int64))(*(_QWORD *)a7 + 72LL))(a7, LastError);
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) == 0 )
      return 0;
    v12 = 29;
    v13 = (unsigned int)LastError;
LABEL_24:
    WPP_SF_d(v11[2], v12, &WPP_da7ed40d09913eb0c9debd1bc41fe78b_Traceguids, v13);
    return 0;
  }
  GrantedAccess = 0;
  LODWORD(AccessStatus) = 0;
  pfGenerateOnClose = 0;
  v14 = AccessCheckAndAuditAlarmW(
          L"WS-Management Listener",
          0,
          a3,
          a4,
          SecurityDescriptor,
          DesiredAccess,
          (PGENERIC_MAPPING)&stru_1801D9E78,
          0,
          &GrantedAccess,
          (LPBOOL)&AccessStatus,
          &pfGenerateOnClose);
  v15 = a7;
  if ( !v14 )
  {
    v16 = GetLastError();
    (*(void (__fastcall **)(struct IRequestContext *, __int64))(*(_QWORD *)v15 + 72LL))(v15, v16);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) != 0 )
      WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, &WPP_da7ed40d09913eb0c9debd1bc41fe78b_Traceguids);
LABEL_10:
    v17 = 0;
    goto LABEL_19;
  }
  if ( !(_DWORD)AccessStatus )
  {
    (*(void (__fastcall **)(struct IRequestContext *))(*(_QWORD *)a7 + 32LL))(a7);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x20000) != 0 )
      WPP_SF_dSS(*((_QWORD *)WPP_GLOBAL_Control + 2), (__int64)a3, (__int64)a4);
    goto LABEL_10;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x20000) != 0 )
    WPP_SF_dSS(*((_QWORD *)WPP_GLOBAL_Control + 2), (__int64)a3, (__int64)a4);
  v17 = 1;
LABEL_19:
  if ( a2 && !(unsigned int)CSecurity::RevertToSelf() )
  {
    v18 = *(void (__fastcall **)(struct IRequestContext *, _QWORD))(*(_QWORD *)v15 + 72LL);
    v19 = GetLastError();
    v18(v15, v19);
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) == 0 )
      return 0;
    v20 = (*(__int64 (__fastcall **)(struct IRequestContext *))(*(_QWORD *)v15 + 152LL))(v15);
    v11 = WPP_GLOBAL_Control;
    v12 = 30;
    v13 = v20;
    goto LABEL_24;
  }
  return v17;
}

```

## disassembly

```asm
0x1800ac3cc  mov     [rsp+arg_10], rbx
0x1800ac3d1  mov     [rsp+arg_0], rcx
0x1800ac3d6  push    rbp
0x1800ac3d7  push    rdi
0x1800ac3d8  push    r12
0x1800ac3da  push    r14
0x1800ac3dc  push    r15
0x1800ac3de  sub     rsp, 70h
0x1800ac3e2  mov     rbx, r9
0x1800ac3e5  mov     r15, r8
0x1800ac3e8  mov     rbp, rdx
0x1800ac3eb  test    rdx, rdx
0x1800ac3ee  jz      short loc_1800AC44C
0x1800ac3f0  mov     rcx, rdx; hToken
0x1800ac3f3  call    cs:__imp_ImpersonateLoggedOnUser
0x1800ac3f9  test    eax, eax
0x1800ac3fb  jnz     short loc_1800AC44C
0x1800ac3fd  call    cs:__imp_GetLastError
0x1800ac403  mov     rcx, [rsp+98h+arg_30]
0x1800ac40b  mov     ebx, eax
0x1800ac40d  mov     rdx, [rcx]
0x1800ac410  mov     rax, [rdx+48h]
0x1800ac414  mov     edx, ebx
0x1800ac416  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ac41b  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ac422  lea     rdi, WPP_GLOBAL_Control
0x1800ac429  cmp     rcx, rdi
0x1800ac42c  jz      loc_1800AC641
0x1800ac432  test    dword ptr [rcx+1Ch], 40000h
0x1800ac439  jz      loc_1800AC641
0x1800ac43f  mov     edx, 1Dh
0x1800ac444  mov     r9d, ebx
0x1800ac447  jmp     loc_1800AC631
0x1800ac44c  mov     r12d, [rsp+98h+arg_20]
0x1800ac454  lea     rax, [rsp+98h+var_38]
0x1800ac459  mov     [rsp+98h+pfGenerateOnClose], rax; pfGenerateOnClose
0x1800ac45e  lea     rcx, SubsystemName; "WS-Management Listener"
0x1800ac465  lea     rax, [rsp+98h+arg_0]
0x1800ac46d  mov     [rsp+98h+arg_8], 0
0x1800ac478  mov     [rsp+98h+AccessStatus], rax; AccessStatus
0x1800ac47d  mov     r9, rbx; ObjectName
0x1800ac480  lea     rax, [rsp+98h+arg_8]
0x1800ac488  mov     dword ptr [rsp+98h+arg_0], 0
0x1800ac493  mov     [rsp+98h+GrantedAccess], rax; GrantedAccess
0x1800ac498  mov     r8, r15; ObjectTypeName
0x1800ac49b  mov     [rsp+98h+ObjectCreation], 0; ObjectCreation
0x1800ac4a3  lea     rax, stru_1801D9E78
0x1800ac4aa  mov     [rsp+98h+GenericMapping], rax; GenericMapping
0x1800ac4af  xor     edx, edx; HandleId
0x1800ac4b1  mov     rax, [rsp+98h+arg_28]
0x1800ac4b9  mov     [rsp+98h+DesiredAccess], r12d; DesiredAccess
0x1800ac4be  mov     [rsp+98h+SecurityDescriptor], rax; SecurityDescriptor
0x1800ac4c3  mov     [rsp+98h+var_38], 0
0x1800ac4cb  call    cs:__imp_AccessCheckAndAuditAlarmW
0x1800ac4d1  mov     r14, [rsp+98h+arg_30]
0x1800ac4d9  test    eax, eax
0x1800ac4db  jnz     short loc_1800AC535
0x1800ac4dd  call    cs:__imp_GetLastError
0x1800ac4e3  mov     rcx, [r14]
0x1800ac4e6  mov     ebx, eax
0x1800ac4e8  mov     edx, ebx
0x1800ac4ea  mov     rax, [rcx+48h]
0x1800ac4ee  mov     rcx, r14
0x1800ac4f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ac4f6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ac4fd  lea     rdi, WPP_GLOBAL_Control
0x1800ac504  cmp     rcx, rdi
0x1800ac507  jz      short loc_1800AC52E
0x1800ac509  test    dword ptr [rcx+1Ch], 40000h
0x1800ac510  jz      short loc_1800AC52E
0x1800ac512  mov     rcx, [rcx+10h]
0x1800ac516  lea     r8, WPP_da7ed40d09913eb0c9debd1bc41fe78b_Traceguids
0x1800ac51d  mov     edx, 1Ah
0x1800ac522  mov     dword ptr [rsp+98h+SecurityDescriptor], ebx
0x1800ac526  mov     r9d, r12d
0x1800ac529  call    WPP_SF_Dd
0x1800ac52e  xor     bl, bl
0x1800ac530  jmp     loc_1800AC5D3
0x1800ac535  cmp     dword ptr [rsp+98h+arg_0], 0
0x1800ac53d  jnz     short loc_1800AC58E
0x1800ac53f  mov     rax, [r14]
0x1800ac542  mov     rcx, r14
0x1800ac545  mov     rax, [rax+20h]
0x1800ac549  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ac54e  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ac555  lea     rdi, WPP_GLOBAL_Control
0x1800ac55c  cmp     rcx, rdi
0x1800ac55f  jz      short loc_1800AC52E
0x1800ac561  test    dword ptr [rcx+1Ch], 20000h
0x1800ac568  jz      short loc_1800AC52E
0x1800ac56a  mov     rcx, [rcx+10h]; LoggerHandle
0x1800ac56e  lea     r8, WPP_da7ed40d09913eb0c9debd1bc41fe78b_Traceguids
0x1800ac575  mov     edx, 1Bh
0x1800ac57a  mov     qword ptr [rsp+98h+DesiredAccess], rbx; __int64
0x1800ac57f  mov     r9d, r12d
0x1800ac582  mov     [rsp+98h+SecurityDescriptor], r15; __int64
0x1800ac587  call    WPP_SF_dSS
0x1800ac58c  jmp     short loc_1800AC52E
0x1800ac58e  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ac595  lea     rdi, WPP_GLOBAL_Control
0x1800ac59c  cmp     rcx, rdi
0x1800ac59f  jz      short loc_1800AC5D1
0x1800ac5a1  test    dword ptr [rcx+1Ch], 20000h
0x1800ac5a8  jz      short loc_1800AC5D1
0x1800ac5aa  mov     r9d, [rsp+98h+arg_8]
0x1800ac5b2  lea     r8, WPP_da7ed40d09913eb0c9debd1bc41fe78b_Traceguids
0x1800ac5b9  mov     rcx, [rcx+10h]; LoggerHandle
0x1800ac5bd  mov     edx, 1Ch
0x1800ac5c2  mov     qword ptr [rsp+98h+DesiredAccess], rbx; __int64
0x1800ac5c7  mov     [rsp+98h+SecurityDescriptor], r15; __int64
0x1800ac5cc  call    WPP_SF_dSS
0x1800ac5d1  mov     bl, 1
0x1800ac5d3  test    rbp, rbp
0x1800ac5d6  jz      short loc_1800AC645
0x1800ac5d8  call    ?RevertToSelf@CSecurity@@SAHXZ; CSecurity::RevertToSelf(void)
0x1800ac5dd  test    eax, eax
0x1800ac5df  jnz     short loc_1800AC645
0x1800ac5e1  mov     rax, [r14]
0x1800ac5e4  mov     rbx, [rax+48h]
0x1800ac5e8  call    cs:__imp_GetLastError
0x1800ac5ee  mov     edx, eax
0x1800ac5f0  mov     rcx, r14
0x1800ac5f3  mov     rax, rbx
0x1800ac5f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ac5fb  mov     rax, cs:WPP_GLOBAL_Control
0x1800ac602  cmp     rax, rdi
0x1800ac605  jz      short loc_1800AC641
0x1800ac607  test    dword ptr [rax+1Ch], 40000h
0x1800ac60e  jz      short loc_1800AC641
0x1800ac610  mov     rax, [r14]
0x1800ac613  mov     rcx, r14
0x1800ac616  mov     rax, [rax+98h]
0x1800ac61d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ac622  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ac629  mov     edx, 1Eh
0x1800ac62e  mov     r9d, eax
0x1800ac631  mov     rcx, [rcx+10h]
0x1800ac635  lea     r8, WPP_da7ed40d09913eb0c9debd1bc41fe78b_Traceguids
0x1800ac63c  call    WPP_SF_d
0x1800ac641  xor     al, al
0x1800ac643  jmp     short loc_1800AC647
0x1800ac645  mov     al, bl
0x1800ac647  mov     rbx, [rsp+98h+arg_10]
0x1800ac64f  add     rsp, 70h
0x1800ac653  pop     r15
0x1800ac655  pop     r14
0x1800ac657  pop     r12
0x1800ac659  pop     rdi
0x1800ac65a  pop     rbp
0x1800ac65b  retn
```
