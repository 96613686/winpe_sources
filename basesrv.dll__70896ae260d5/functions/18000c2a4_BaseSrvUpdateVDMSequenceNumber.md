# BaseSrvUpdateVDMSequenceNumber

- ea: `0x18000c2a4`
- end: `0x18000c44d`
- name: `BaseSrvUpdateVDMSequenceNumber`
- size: `425`
- prototype: `__int64 __fastcall(char, __int64, unsigned int, __int64, __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, loader_planting, service_task, installer_update`

## callers

- `0x180006ee0`

## callees

- `0x180009730`
- `0x18000a4e0`
- `0x18000a50c`
- `0x18000a8fc`
- `0x18000b458`
- `0x18000c2a4`
- `0x18000c5e4`

## import_xrefs

- `ntdll!RtlEnterCriticalSection` at `0x18000c2fa`
- `ntdll!RtlEnterCriticalSection` at `0x18000c2fa`
- `ntdll!RtlLeaveCriticalSection` at `0x18000c424`
- `ntdll!RtlLeaveCriticalSection` at `0x18000c424`
- `ntdll!DbgPrint` at `0x18000c411`
- `ntdll!DbgPrint` at `0x18000c411`
- `CSRSRV!CsrUnlockProcess` at `0x18000c3fc`
- `CSRSRV!CsrUnlockProcess` at `0x18000c3fc`
- `CSRSRV!CsrLockProcessByClientId` at `0x18000c34f`
- `CSRSRV!CsrLockProcessByClientId` at `0x18000c3cc`
- `CSRSRV!CsrLockProcessByClientId` at `0x18000c34f`
- `CSRSRV!CsrLockProcessByClientId` at `0x18000c3cc`

## pseudocode

```c
__int64 __fastcall BaseSrvUpdateVDMSequenceNumber(char a1, __int64 a2, unsigned int a3, __int64 a4, __int64 a5)
{
  __int64 v10; // rcx
  int SharedWowRecordByTaskId; // eax
  int v12; // ebx
  __int64 v13; // rdi
  __int64 v14; // rcx
  int ConsoleRecord; // eax
  _DWORD *v16; // rdi
  int v17; // [rsp+20h] [rbp-20h] BYREF
  __int64 v18; // [rsp+28h] [rbp-18h] BYREF
  _QWORD v19[2]; // [rsp+30h] [rbp-10h] BYREF

  v18 = 0;
  v17 = 0;
  if ( (int)BaseSrvGetVdmSequence(a5, &v17) < 0 )
    return 3221225485LL;
  v19[0] = 0;
  RtlEnterCriticalSection(&BaseSrvVDMCriticalSection);
  if ( (a1 & 0x20) == 0 )
  {
    if ( a2 )
      ConsoleRecord = BaseSrvGetConsoleRecord(a2, v19);
    else
      ConsoleRecord = GetConsoleRecordDosSesId(a3, v19);
    v12 = ConsoleRecord;
    if ( ConsoleRecord < 0 || (v16 = (_DWORD *)v19[0], *(_DWORD *)(v19[0] + 44LL)) )
    {
      DbgPrint("BASESRV: DOS is in inconsistent state. Contact DOS Team\n");
      goto LABEL_24;
    }
    if ( v17 != *(_DWORD *)(v19[0] + 48LL) )
      goto LABEL_24;
    v12 = CsrLockProcessByClientId(a4, &v18);
    if ( v12 < 0 )
      goto LABEL_24;
    *(_DWORD *)(v18 + 92) |= 2u;
    v16[11] = *(_DWORD *)(v18 + 88);
    v16[12] = 0;
    v16[14] = a4;
    goto LABEL_22;
  }
  if ( a2 )
    SharedWowRecordByTaskId = BaseSrvFindSharedWowRecordByTaskId(v10, a3, v19, 0);
  else
    SharedWowRecordByTaskId = BaseSrvFindSharedWowRecordByConsoleHandle(v10, 0, v19);
  v12 = SharedWowRecordByTaskId;
  if ( SharedWowRecordByTaskId < 0 || (v13 = v19[0], *(_DWORD *)(v19[0] + 80LL)) )
  {
    DbgPrint("BASESRV: WOW is in inconsistent state. Contact WOW Team\n");
  }
  else if ( v17 == *(_DWORD *)(v19[0] + 84LL) )
  {
    v12 = CsrLockProcessByClientId(a4, &v18);
    if ( v12 >= 0 )
    {
      *(_DWORD *)(v18 + 92) |= 2u;
      *(_DWORD *)(v13 + 80) = *(_DWORD *)(v18 + 88);
      *(_DWORD *)(v13 + 84) = 0;
      *(_DWORD *)(v13 + 24) = a4;
LABEL_22:
      CsrUnlockProcess(v18);
      goto LABEL_24;
    }
    BaseSrvDeleteSharedWowRecord(v14, (_QWORD *)v13);
  }
LABEL_24:
  RtlLeaveCriticalSection(&BaseSrvVDMCriticalSection);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x18000c2a4  mov     rax, rsp
0x18000c2a7  mov     [rax+8], rbx
0x18000c2ab  mov     [rax+10h], rsi
0x18000c2af  mov     [rax+18h], rdi
0x18000c2b3  mov     [rax+20h], r14
0x18000c2b7  push    rbp
0x18000c2b8  mov     rbp, rsp
0x18000c2bb  sub     rsp, 40h
0x18000c2bf  and     [rbp+var_18], 0
0x18000c2c4  mov     rbx, rdx
0x18000c2c7  and     [rbp+var_20], 0
0x18000c2cb  lea     rdx, [rbp+var_20]
0x18000c2cf  mov     esi, ecx
0x18000c2d1  mov     r14, r9
0x18000c2d4  mov     rcx, [rbp+arg_20]
0x18000c2d8  mov     edi, r8d
0x18000c2db  call    BaseSrvGetVdmSequence
0x18000c2e0  test    eax, eax
0x18000c2e2  jns     short loc_18000C2EE
0x18000c2e4  mov     eax, 0C000000Dh
0x18000c2e9  jmp     loc_18000C432
0x18000c2ee  and     [rbp+var_10], 0
0x18000c2f3  lea     rcx, BaseSrvVDMCriticalSection; CriticalSection
0x18000c2fa  call    cs:__imp_RtlEnterCriticalSection
0x18000c301  nop     dword ptr [rax+rax+00h]
0x18000c306  test    sil, 20h
0x18000c30a  jz      loc_18000C393
0x18000c310  lea     r8, [rbp+var_10]
0x18000c314  test    rbx, rbx
0x18000c317  jnz     short loc_18000C322
0x18000c319  xor     edx, edx
0x18000c31b  call    BaseSrvFindSharedWowRecordByConsoleHandle
0x18000c320  jmp     short loc_18000C32C
0x18000c322  xor     r9d, r9d
0x18000c325  mov     edx, edi
0x18000c327  call    BaseSrvFindSharedWowRecordByTaskId
0x18000c32c  mov     ebx, eax
0x18000c32e  test    eax, eax
0x18000c330  js      short loc_18000C38A
0x18000c332  mov     rdi, [rbp+var_10]
0x18000c336  cmp     dword ptr [rdi+50h], 0
0x18000c33a  jnz     short loc_18000C38A
0x18000c33c  mov     eax, [rdi+54h]
0x18000c33f  cmp     [rbp+var_20], eax
0x18000c342  jnz     loc_18000C41D
0x18000c348  lea     rdx, [rbp+var_18]
0x18000c34c  mov     rcx, r14
0x18000c34f  call    cs:__imp_CsrLockProcessByClientId
0x18000c356  nop     dword ptr [rax+rax+00h]
0x18000c35b  mov     ebx, eax
0x18000c35d  test    eax, eax
0x18000c35f  js      short loc_18000C37D
0x18000c361  mov     rax, [rbp+var_18]
0x18000c365  or      dword ptr [rax+5Ch], 2
0x18000c369  mov     rax, [rbp+var_18]
0x18000c36d  mov     ecx, [rax+58h]
0x18000c370  mov     [rdi+50h], ecx
0x18000c373  and     dword ptr [rdi+54h], 0
0x18000c377  mov     [rdi+18h], r14d
0x18000c37b  jmp     short loc_18000C3F8
0x18000c37d  mov     rdx, rdi
0x18000c380  call    BaseSrvDeleteSharedWowRecord
0x18000c385  jmp     loc_18000C41D
0x18000c38a  lea     rcx, aBasesrvWowIsIn; "BASESRV: WOW is in inconsistent state. "...
0x18000c391  jmp     short loc_18000C411
0x18000c393  lea     rdx, [rbp+var_10]
0x18000c397  test    rbx, rbx
0x18000c39a  jnz     short loc_18000C3A5
0x18000c39c  mov     ecx, edi
0x18000c39e  call    GetConsoleRecordDosSesId
0x18000c3a3  jmp     short loc_18000C3AD
0x18000c3a5  mov     rcx, rbx
0x18000c3a8  call    BaseSrvGetConsoleRecord
0x18000c3ad  mov     ebx, eax
0x18000c3af  test    eax, eax
0x18000c3b1  js      short loc_18000C40A
0x18000c3b3  mov     rdi, [rbp+var_10]
0x18000c3b7  cmp     dword ptr [rdi+2Ch], 0
0x18000c3bb  jnz     short loc_18000C40A
0x18000c3bd  mov     eax, [rdi+30h]
0x18000c3c0  cmp     [rbp+var_20], eax
0x18000c3c3  jnz     short loc_18000C41D
0x18000c3c5  lea     rdx, [rbp+var_18]
0x18000c3c9  mov     rcx, r14
0x18000c3cc  call    cs:__imp_CsrLockProcessByClientId
0x18000c3d3  nop     dword ptr [rax+rax+00h]
0x18000c3d8  mov     ebx, eax
0x18000c3da  test    eax, eax
0x18000c3dc  js      short loc_18000C41D
0x18000c3de  mov     rax, [rbp+var_18]
0x18000c3e2  or      dword ptr [rax+5Ch], 2
0x18000c3e6  mov     rax, [rbp+var_18]
0x18000c3ea  mov     ecx, [rax+58h]
0x18000c3ed  mov     [rdi+2Ch], ecx
0x18000c3f0  and     dword ptr [rdi+30h], 0
0x18000c3f4  mov     [rdi+38h], r14d
0x18000c3f8  mov     rcx, [rbp+var_18]
0x18000c3fc  call    cs:__imp_CsrUnlockProcess
0x18000c403  nop     dword ptr [rax+rax+00h]
0x18000c408  jmp     short loc_18000C41D
0x18000c40a  lea     rcx, aBasesrvDosIsIn; "BASESRV: DOS is in inconsistent state. "...
0x18000c411  call    cs:__imp_DbgPrint
0x18000c418  nop     dword ptr [rax+rax+00h]
0x18000c41d  lea     rcx, BaseSrvVDMCriticalSection; CriticalSection
0x18000c424  call    cs:__imp_RtlLeaveCriticalSection
0x18000c42b  nop     dword ptr [rax+rax+00h]
0x18000c430  mov     eax, ebx
0x18000c432  mov     rbx, [rsp+40h+arg_0]
0x18000c437  mov     rsi, [rsp+40h+arg_8]
0x18000c43c  mov     rdi, [rsp+40h+arg_10]
0x18000c441  mov     r14, [rsp+40h+arg_18]
0x18000c446  add     rsp, 40h
0x18000c44a  pop     rbp
0x18000c44b  retn
```
