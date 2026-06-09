# _CreateRestrictedTokenFromSpecifiedToken(ulong,void *,void * *)

- ea: `0x1800d1390`
- end: `0x1800d14e1`
- name: `?_CreateRestrictedTokenFromSpecifiedToken@@YAJKPEAXPEAPEAX@Z`
- size: `337`
- prototype: `__int64 __fastcall(DWORD nSubAuthority0, HANDLE ExistingTokenHandle, void **)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18003a7b8`
- `0x18003a980`

## callees

- `0x180006538`
- `0x18003aa84`
- `0x1800d1054`
- `0x1800d1390`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800d14b5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800d14b5`
- `api-ms-win-security-base-l1-1-0!CreateRestrictedToken` at `0x1800d1476`
- `api-ms-win-security-base-l1-1-0!CreateRestrictedToken` at `0x1800d1476`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x1800d1410`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x1800d1410`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800d14c0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800d14c0`

## pseudocode

```c
__int64 __fastcall _CreateRestrictedTokenFromSpecifiedToken(
        void *nSubAuthority0,
        HANDLE ExistingTokenHandle,
        void **a3)
{
  DWORD v5; // ebp
  int v6; // edi
  int Error; // ebx
  struct _SID_AND_ATTRIBUTES SidsToDisable; // [rsp+50h] [rbp-38h] BYREF
  void *cbSid; // [rsp+A0h] [rbp+18h] BYREF

  *a3 = 0;
  SidsToDisable = 0;
  v5 = (unsigned int)nSubAuthority0;
  v6 = 0;
  while ( !v6 )
  {
    LODWORD(cbSid) = 68;
    Error = CTCoAllocPolicy::Alloc(nSubAuthority0, 1u, 0x44u, &SidsToDisable.Sid);
    if ( Error < 0 )
    {
LABEL_7:
      v6 = 1;
      if ( Error < 0 )
        goto LABEL_14;
    }
    else
    {
      if ( !CreateWellKnownSid(WinBuiltinAdministratorsSid, 0, *(&SidsToDisable.Sid + 2 * v6), (DWORD *)&cbSid) )
      {
        Error = ResultFromKnownLastError();
        goto LABEL_7;
      }
      v6 = 1;
    }
  }
  cbSid = 0;
  if ( CreateRestrictedToken(ExistingTokenHandle, 1u, 1u, &SidsToDisable, 0, 0, 0, 0, &cbSid)
    || (Error = ResultFromKnownLastError(), Error >= 0) )
  {
    Error = AdjustTokenIntegrity(v5, cbSid);
    if ( Error < 0 )
      CloseHandle(cbSid);
    else
      *a3 = cbSid;
  }
LABEL_14:
  CoTaskMemFree(SidsToDisable.Sid);
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x1800d1390  mov     [rsp+arg_0], rbx
0x1800d1395  mov     [rsp+arg_8], rbp
0x1800d139a  push    rsi
0x1800d139b  push    rdi
0x1800d139c  push    r12
0x1800d139e  push    r14
0x1800d13a0  push    r15
0x1800d13a2  sub     rsp, 60h
0x1800d13a6  xorps   xmm0, xmm0
0x1800d13a9  mov     qword ptr [r8], 0
0x1800d13b0  movups  xmmword ptr [rsp+88h+SidsToDisable.Sid], xmm0
0x1800d13b5  mov     r14, r8
0x1800d13b8  mov     r12, rdx
0x1800d13bb  mov     ebp, ecx
0x1800d13bd  xor     edi, edi
0x1800d13bf  movsxd  rsi, edi
0x1800d13c2  mov     edx, 1; unsigned int
0x1800d13c7  cmp     rsi, 1
0x1800d13cb  jnb     short loc_1800D1430
0x1800d13cd  mov     rax, rsi
0x1800d13d0  mov     dword ptr [rsp+88h+cbSid], 44h ; 'D'
0x1800d13db  shl     rax, 4
0x1800d13df  lea     r15, [rsp+88h+SidsToDisable]
0x1800d13e4  add     r15, rax
0x1800d13e7  lea     r8d, [rdx+43h]; unsigned __int64
0x1800d13eb  mov     r9, r15; void **
0x1800d13ee  call    ?Alloc@CTCoAllocPolicy@@SAJPEAXK_KPEAPEAX@Z; CTCoAllocPolicy::Alloc(void *,ulong,unsigned __int64,void * *)
0x1800d13f3  mov     ebx, eax
0x1800d13f5  test    eax, eax
0x1800d13f7  js      short loc_1800D1425
0x1800d13f9  mov     r8, [r15]; pSid
0x1800d13fc  lea     rcx, qword_1801074B8
0x1800d1403  mov     ecx, [rcx+rsi*4]; WellKnownSidType
0x1800d1406  lea     r9, [rsp+88h+cbSid]; cbSid
0x1800d140e  xor     edx, edx; DomainSid
0x1800d1410  call    cs:__imp_CreateWellKnownSid
0x1800d1416  test    eax, eax
0x1800d1418  jz      short loc_1800D141E
0x1800d141a  inc     edi
0x1800d141c  jmp     short loc_1800D13BF
0x1800d141e  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1800d1423  mov     ebx, eax
0x1800d1425  inc     edi
0x1800d1427  test    ebx, ebx
0x1800d1429  jns     short loc_1800D13BF
0x1800d142b  jmp     loc_1800D14BB
0x1800d1430  lea     rax, [rsp+88h+cbSid]
0x1800d1438  mov     [rsp+88h+cbSid], 0
0x1800d1444  mov     [rsp+88h+NewTokenHandle], rax; NewTokenHandle
0x1800d1449  lea     r9, [rsp+88h+SidsToDisable]; SidsToDisable
0x1800d144e  mov     [rsp+88h+SidsToRestrict], 0; SidsToRestrict
0x1800d1457  mov     r8d, edx; DisableSidCount
0x1800d145a  mov     [rsp+88h+RestrictedSidCount], 0; RestrictedSidCount
0x1800d1462  mov     rcx, r12; ExistingTokenHandle
0x1800d1465  mov     [rsp+88h+PrivilegesToDelete], 0; PrivilegesToDelete
0x1800d146e  mov     [rsp+88h+DeletePrivilegeCount], 0; DeletePrivilegeCount
0x1800d1476  call    cs:__imp_CreateRestrictedToken
0x1800d147c  test    eax, eax
0x1800d147e  jnz     short loc_1800D148B
0x1800d1480  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1800d1485  mov     ebx, eax
0x1800d1487  test    eax, eax
0x1800d1489  js      short loc_1800D14BB
0x1800d148b  mov     rdx, [rsp+88h+cbSid]; TokenHandle
0x1800d1493  mov     ecx, ebp; nSubAuthority0
0x1800d1495  call    ?AdjustTokenIntegrity@@YAJKPEAX@Z; AdjustTokenIntegrity(ulong,void *)
0x1800d149a  mov     ebx, eax
0x1800d149c  test    eax, eax
0x1800d149e  js      short loc_1800D14AD
0x1800d14a0  mov     rax, [rsp+88h+cbSid]
0x1800d14a8  mov     [r14], rax
0x1800d14ab  jmp     short loc_1800D14BB
0x1800d14ad  mov     rcx, [rsp+88h+cbSid]; hObject
0x1800d14b5  call    cs:__imp_CloseHandle
0x1800d14bb  mov     rcx, [rsp+88h+SidsToDisable.Sid]; pv
0x1800d14c0  call    cs:__imp_CoTaskMemFree
0x1800d14c6  lea     r11, [rsp+88h+var_28]
0x1800d14cb  mov     eax, ebx
0x1800d14cd  mov     rbx, [r11+30h]
0x1800d14d1  mov     rbp, [r11+38h]
0x1800d14d5  mov     rsp, r11
0x1800d14d8  pop     r15
0x1800d14da  pop     r14
0x1800d14dc  pop     r12
0x1800d14de  pop     rdi
0x1800d14df  pop     rsi
0x1800d14e0  retn
```
