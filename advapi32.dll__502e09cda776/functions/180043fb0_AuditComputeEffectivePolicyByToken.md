# AuditComputeEffectivePolicyByToken

- ea: `0x180043fb0`
- end: `0x18004410d`
- name: `AuditComputeEffectivePolicyByToken`
- size: `349`
- prototype: `BOOLEAN __stdcall(HANDLE hTokenHandle, const GUID *pSubCategoryGuids, ULONG dwPolicyCount, PAUDIT_POLICY_INFORMATION *ppAuditPolicy)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callees

- `0x180043fb0`
- `0x1800720b0`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x1800440ca`
- `ntdll!RtlFreeHeap` at `0x1800440ca`
- `ntdll!NtQueryInformationToken` at `0x180044002`
- `ntdll!NtQueryInformationToken` at `0x18004406e`
- `ntdll!NtQueryInformationToken` at `0x180044002`
- `ntdll!NtQueryInformationToken` at `0x18004406e`
- `ntdll!RtlAllocateHeap` at `0x18004402d`
- `ntdll!RtlAllocateHeap` at `0x18004402d`
- `ntdll!RtlNtStatusToDosError` at `0x180044046`
- `ntdll!RtlNtStatusToDosError` at `0x180044046`
- `KERNEL32!GetLastError` at `0x1800440a0`
- `KERNEL32!GetLastError` at `0x1800440a0`
- `KERNEL32!SetLastError` at `0x1800440dc`
- `KERNEL32!SetLastError` at `0x1800440dc`
- `api-ms-win-security-audit-l1-1-0!AuditComputeEffectivePolicyBySid` at `0x180044090`
- `api-ms-win-security-audit-l1-1-0!AuditComputeEffectivePolicyBySid` at `0x180044090`

## pseudocode

```c
BOOLEAN __stdcall AuditComputeEffectivePolicyByToken(
        HANDLE hTokenHandle,
        const GUID *pSubCategoryGuids,
        ULONG dwPolicyCount,
        PAUDIT_POLICY_INFORMATION *ppAuditPolicy)
{
  PSID *Heap; // rdi
  NTSTATUS InformationToken; // eax
  NTSTATUS v10; // ecx
  ULONG LastError; // eax
  DWORD v12; // ebx
  ULONG TokenInformationLength[4]; // [rsp+30h] [rbp-A8h] BYREF
  _BYTE TokenInformation[96]; // [rsp+40h] [rbp-98h] BYREF

  TokenInformationLength[0] = 0;
  Heap = (PSID *)TokenInformation;
  InformationToken = NtQueryInformationToken(hTokenHandle, TokenUser, TokenInformation, 0x54u, TokenInformationLength);
  if ( InformationToken < 0 )
  {
    if ( InformationToken != -1073741789 )
      goto LABEL_7;
    Heap = (PSID *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, TokenInformationLength[0]);
    if ( !Heap )
    {
      v10 = -1073741670;
LABEL_5:
      LastError = RtlNtStatusToDosError(v10);
      goto LABEL_10;
    }
    InformationToken = NtQueryInformationToken(
                         hTokenHandle,
                         TokenUser,
                         Heap,
                         TokenInformationLength[0],
                         TokenInformationLength);
    if ( InformationToken < 0 )
    {
LABEL_7:
      v10 = InformationToken;
      goto LABEL_5;
    }
  }
  v12 = 0;
  if ( AuditComputeEffectivePolicyBySid(*Heap, pSubCategoryGuids, dwPolicyCount, ppAuditPolicy) )
    goto LABEL_11;
  LastError = GetLastError();
LABEL_10:
  v12 = LastError;
LABEL_11:
  if ( Heap != (PSID *)TokenInformation )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Heap);
  if ( !v12 )
    return 1;
  SetLastError(v12);
  return 0;
}

```

## disassembly

```asm
0x180043fb0  push    rbx
0x180043fb2  push    rbp
0x180043fb3  push    rsi
0x180043fb4  push    rdi
0x180043fb5  push    r14
0x180043fb7  sub     rsp, 0B0h
0x180043fbe  mov     rax, cs:__security_cookie
0x180043fc5  xor     rax, rsp
0x180043fc8  mov     [rsp+0D8h+var_38], rax
0x180043fd0  mov     r14, r9
0x180043fd3  mov     [rsp+0D8h+TokenInformationLength], 0
0x180043fdb  mov     r9d, 54h ; 'T'; TokenInformationLength
0x180043fe1  lea     rax, [rsp+0D8h+TokenInformationLength]
0x180043fe6  mov     ebp, r8d
0x180043fe9  mov     [rsp+0D8h+ReturnLength], rax; ReturnLength
0x180043fee  mov     rsi, rdx
0x180043ff1  lea     r8, [rsp+0D8h+TokenInformation]; TokenInformation
0x180043ff6  mov     rbx, rcx
0x180043ff9  lea     rdi, [rsp+0D8h+TokenInformation]
0x180043ffe  lea     edx, [r9-53h]; TokenInformationClass
0x180044002  call    cs:__imp_NtQueryInformationToken
0x180044009  nop     dword ptr [rax+rax+00h]
0x18004400e  test    eax, eax
0x180044010  jns     short loc_180044082
0x180044012  cmp     eax, 0C0000023h
0x180044017  jnz     short loc_18004407E
0x180044019  mov     rcx, gs:60h
0x180044022  xor     edx, edx; Flags
0x180044024  mov     r8d, [rsp+0D8h+TokenInformationLength]; Size
0x180044029  mov     rcx, [rcx+30h]; HeapHandle
0x18004402d  call    cs:__imp_RtlAllocateHeap
0x180044034  nop     dword ptr [rax+rax+00h]
0x180044039  mov     rdi, rax
0x18004403c  test    rax, rax
0x18004403f  jnz     short loc_180044054
0x180044041  mov     ecx, 0C000009Ah; Status
0x180044046  call    cs:__imp_RtlNtStatusToDosError
0x18004404d  nop     dword ptr [rax+rax+00h]
0x180044052  jmp     short loc_1800440AC
0x180044054  mov     r9d, [rsp+0D8h+TokenInformationLength]; TokenInformationLength
0x180044059  lea     rax, [rsp+0D8h+TokenInformationLength]
0x18004405e  mov     r8, rdi; TokenInformation
0x180044061  mov     [rsp+0D8h+ReturnLength], rax; ReturnLength
0x180044066  mov     edx, 1; TokenInformationClass
0x18004406b  mov     rcx, rbx; TokenHandle
0x18004406e  call    cs:__imp_NtQueryInformationToken
0x180044075  nop     dword ptr [rax+rax+00h]
0x18004407a  test    eax, eax
0x18004407c  jns     short loc_180044082
0x18004407e  mov     ecx, eax
0x180044080  jmp     short loc_180044046
0x180044082  mov     rcx, [rdi]; pSid
0x180044085  mov     r9, r14; ppAuditPolicy
0x180044088  mov     r8d, ebp; dwPolicyCount
0x18004408b  mov     rdx, rsi; pSubCategoryGuids
0x18004408e  xor     ebx, ebx
0x180044090  call    cs:__imp_AuditComputeEffectivePolicyBySid
0x180044097  nop     dword ptr [rax+rax+00h]
0x18004409c  test    al, al
0x18004409e  jnz     short loc_1800440AE
0x1800440a0  call    cs:__imp_GetLastError
0x1800440a7  nop     dword ptr [rax+rax+00h]
0x1800440ac  mov     ebx, eax
0x1800440ae  lea     rax, [rsp+0D8h+TokenInformation]
0x1800440b3  cmp     rdi, rax
0x1800440b6  jz      short loc_1800440D6
0x1800440b8  mov     rcx, gs:60h
0x1800440c1  mov     r8, rdi; P
0x1800440c4  xor     edx, edx; Flags
0x1800440c6  mov     rcx, [rcx+30h]; HeapHandle
0x1800440ca  call    cs:__imp_RtlFreeHeap
0x1800440d1  nop     dword ptr [rax+rax+00h]
0x1800440d6  test    ebx, ebx
0x1800440d8  jz      short loc_1800440EC
0x1800440da  mov     ecx, ebx; dwErrCode
0x1800440dc  call    cs:__imp_SetLastError
0x1800440e3  nop     dword ptr [rax+rax+00h]
0x1800440e8  xor     al, al
0x1800440ea  jmp     short loc_1800440EE
0x1800440ec  mov     al, 1
0x1800440ee  mov     rcx, [rsp+0D8h+var_38]
0x1800440f6  xor     rcx, rsp; StackCookie
0x1800440f9  call    __security_check_cookie
0x1800440fe  add     rsp, 0B0h
0x180044105  pop     r14
0x180044107  pop     rdi
0x180044108  pop     rsi
0x180044109  pop     rbp
0x18004410a  pop     rbx
0x18004410b  retn
```
