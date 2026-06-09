# BaseSrvUpdateVDMSequenceNumber

- ea: `0x18000c678`
- end: `0x18000c819`
- name: `BaseSrvUpdateVDMSequenceNumber`
- size: `417`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, loader_planting, service_task, installer_update`

## callers

- `0x180007170`

## callees

- `0x180009a08`
- `0x18000a764`
- `0x18000a790`
- `0x18000ab84`
- `0x18000b704`
- `0x18000c678`
- `0x18000c9c0`

## import_xrefs

- `ntdll!RtlEnterCriticalSection` at `0x18000c6cb`
- `ntdll!RtlEnterCriticalSection` at `0x18000c6cb`
- `ntdll!RtlLeaveCriticalSection` at `0x18000c7ff`
- `ntdll!RtlLeaveCriticalSection` at `0x18000c7ff`
- `ntdll!DbgPrint` at `0x18000c7ec`
- `ntdll!DbgPrint` at `0x18000c7ec`
- `CSRSRV!CsrUnlockProcess` at `0x18000c7d7`
- `CSRSRV!CsrUnlockProcess` at `0x18000c7d7`
- `CSRSRV!CsrLockProcessByClientId` at `0x18000c720`
- `CSRSRV!CsrLockProcessByClientId` at `0x18000c7a5`
- `CSRSRV!CsrLockProcessByClientId` at `0x18000c720`
- `CSRSRV!CsrLockProcessByClientId` at `0x18000c7a5`

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
  __int64 v16; // rdi
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
    if ( ConsoleRecord < 0 || (v16 = v19[0], *(_DWORD *)(v19[0] + 44LL)) )
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
    *(_QWORD *)(v16 + 44) = *(unsigned int *)(v18 + 88);
    *(_DWORD *)(v16 + 56) = a4;
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
      *(_QWORD *)(v13 + 80) = *(unsigned int *)(v18 + 88);
      *(_DWORD *)(v13 + 24) = a4;
LABEL_22:
      CsrUnlockProcess(v18);
      goto LABEL_24;
    }
    BaseSrvDeleteSharedWowRecord(v14, v13);
  }
LABEL_24:
  RtlLeaveCriticalSection(&BaseSrvVDMCriticalSection);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x18000c678  push    rbp
0x18000c67a  push    rbx
0x18000c67b  push    rsi
0x18000c67c  push    rdi
0x18000c67d  push    r14
0x18000c67f  mov     rbp, rsp
0x18000c682  sub     rsp, 40h
0x18000c686  mov     rbx, rdx
0x18000c689  mov     [rbp+var_18], 0
0x18000c691  mov     r14d, ecx
0x18000c694  mov     [rbp+var_20], 0
0x18000c69b  mov     rcx, [rbp+arg_20]
0x18000c69f  lea     rdx, [rbp+var_20]
0x18000c6a3  mov     rsi, r9
0x18000c6a6  mov     edi, r8d
0x18000c6a9  call    BaseSrvGetVdmSequence
0x18000c6ae  test    eax, eax
0x18000c6b0  jns     short loc_18000C6BC
0x18000c6b2  mov     eax, 0C000000Dh
0x18000c6b7  jmp     loc_18000C80D
0x18000c6bc  lea     rcx, BaseSrvVDMCriticalSection; CriticalSection
0x18000c6c3  mov     [rbp+var_10], 0
0x18000c6cb  call    cs:__imp_RtlEnterCriticalSection
0x18000c6d2  nop     dword ptr [rax+rax+00h]
0x18000c6d7  test    r14b, 20h
0x18000c6db  jz      loc_18000C76C
0x18000c6e1  lea     r8, [rbp+var_10]
0x18000c6e5  test    rbx, rbx
0x18000c6e8  jnz     short loc_18000C6F3
0x18000c6ea  xor     edx, edx
0x18000c6ec  call    BaseSrvFindSharedWowRecordByConsoleHandle
0x18000c6f1  jmp     short loc_18000C6FD
0x18000c6f3  xor     r9d, r9d
0x18000c6f6  mov     edx, edi
0x18000c6f8  call    BaseSrvFindSharedWowRecordByTaskId
0x18000c6fd  mov     ebx, eax
0x18000c6ff  test    eax, eax
0x18000c701  js      short loc_18000C760
0x18000c703  mov     rdi, [rbp+var_10]
0x18000c707  cmp     dword ptr [rdi+50h], 0
0x18000c70b  jnz     short loc_18000C760
0x18000c70d  mov     eax, [rdi+54h]
0x18000c710  cmp     [rbp+var_20], eax
0x18000c713  jnz     loc_18000C7F8
0x18000c719  lea     rdx, [rbp+var_18]
0x18000c71d  mov     rcx, rsi
0x18000c720  call    cs:__imp_CsrLockProcessByClientId
0x18000c727  nop     dword ptr [rax+rax+00h]
0x18000c72c  mov     ebx, eax
0x18000c72e  test    eax, eax
0x18000c730  js      short loc_18000C753
0x18000c732  mov     rax, [rbp+var_18]
0x18000c736  or      dword ptr [rax+5Ch], 2
0x18000c73a  mov     rax, [rbp+var_18]
0x18000c73e  mov     ecx, [rax+58h]
0x18000c741  mov     [rdi+50h], ecx
0x18000c744  mov     dword ptr [rdi+54h], 0
0x18000c74b  mov     [rdi+18h], esi
0x18000c74e  jmp     loc_18000C7D3
0x18000c753  mov     rdx, rdi
0x18000c756  call    BaseSrvDeleteSharedWowRecord
0x18000c75b  jmp     loc_18000C7F8
0x18000c760  lea     rcx, aBasesrvWowIsIn; "BASESRV: WOW is in inconsistent state. "...
0x18000c767  jmp     loc_18000C7EC
0x18000c76c  lea     rdx, [rbp+var_10]
0x18000c770  test    rbx, rbx
0x18000c773  jnz     short loc_18000C77E
0x18000c775  mov     ecx, edi
0x18000c777  call    GetConsoleRecordDosSesId
0x18000c77c  jmp     short loc_18000C786
0x18000c77e  mov     rcx, rbx
0x18000c781  call    BaseSrvGetConsoleRecord
0x18000c786  mov     ebx, eax
0x18000c788  test    eax, eax
0x18000c78a  js      short loc_18000C7E5
0x18000c78c  mov     rdi, [rbp+var_10]
0x18000c790  cmp     dword ptr [rdi+2Ch], 0
0x18000c794  jnz     short loc_18000C7E5
0x18000c796  mov     eax, [rdi+30h]
0x18000c799  cmp     [rbp+var_20], eax
0x18000c79c  jnz     short loc_18000C7F8
0x18000c79e  lea     rdx, [rbp+var_18]
0x18000c7a2  mov     rcx, rsi
0x18000c7a5  call    cs:__imp_CsrLockProcessByClientId
0x18000c7ac  nop     dword ptr [rax+rax+00h]
0x18000c7b1  mov     ebx, eax
0x18000c7b3  test    eax, eax
0x18000c7b5  js      short loc_18000C7F8
0x18000c7b7  mov     rax, [rbp+var_18]
0x18000c7bb  or      dword ptr [rax+5Ch], 2
0x18000c7bf  mov     rax, [rbp+var_18]
0x18000c7c3  mov     ecx, [rax+58h]
0x18000c7c6  mov     [rdi+2Ch], ecx
0x18000c7c9  mov     dword ptr [rdi+30h], 0
0x18000c7d0  mov     [rdi+38h], esi
0x18000c7d3  mov     rcx, [rbp+var_18]
0x18000c7d7  call    cs:__imp_CsrUnlockProcess
0x18000c7de  nop     dword ptr [rax+rax+00h]
0x18000c7e3  jmp     short loc_18000C7F8
0x18000c7e5  lea     rcx, aBasesrvDosIsIn; "BASESRV: DOS is in inconsistent state. "...
0x18000c7ec  call    cs:__imp_DbgPrint
0x18000c7f3  nop     dword ptr [rax+rax+00h]
0x18000c7f8  lea     rcx, BaseSrvVDMCriticalSection; CriticalSection
0x18000c7ff  call    cs:__imp_RtlLeaveCriticalSection
0x18000c806  nop     dword ptr [rax+rax+00h]
0x18000c80b  mov     eax, ebx
0x18000c80d  add     rsp, 40h
0x18000c811  pop     r14
0x18000c813  pop     rdi
0x18000c814  pop     rsi
0x18000c815  pop     rbx
0x18000c816  pop     rbp
0x18000c817  retn
```
