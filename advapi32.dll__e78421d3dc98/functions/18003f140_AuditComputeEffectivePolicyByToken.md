# AuditComputeEffectivePolicyByToken

- ea: `0x18003f140`
- end: `0x18003f26c`
- name: `AuditComputeEffectivePolicyByToken`
- size: `300`
- prototype: `BOOLEAN __stdcall(HANDLE hTokenHandle, const GUID *pSubCategoryGuids, ULONG dwPolicyCount, PAUDIT_POLICY_INFORMATION *ppAuditPolicy)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callees

- `0x18003f140`
- `0x180065090`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x18003f236`
- `ntdll!RtlFreeHeap` at `0x18003f236`
- `ntdll!NtQueryInformationToken` at `0x18003f192`
- `ntdll!NtQueryInformationToken` at `0x18003f1ec`
- `ntdll!NtQueryInformationToken` at `0x18003f192`
- `ntdll!NtQueryInformationToken` at `0x18003f1ec`
- `ntdll!RtlAllocateHeap` at `0x18003f1b7`
- `ntdll!RtlAllocateHeap` at `0x18003f1b7`
- `ntdll!RtlNtStatusToDosError` at `0x18003f1ca`
- `ntdll!RtlNtStatusToDosError` at `0x18003f1ca`
- `KERNEL32!GetLastError` at `0x18003f212`
- `KERNEL32!GetLastError` at `0x18003f212`
- `KERNEL32!SetLastError` at `0x18003f242`
- `KERNEL32!SetLastError` at `0x18003f242`
- `api-ms-win-security-audit-l1-1-0!AuditComputeEffectivePolicyBySid` at `0x18003f208`
- `api-ms-win-security-audit-l1-1-0!AuditComputeEffectivePolicyBySid` at `0x18003f208`

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
0x18003f140  push    rbx
0x18003f142  push    rbp
0x18003f143  push    rsi
0x18003f144  push    rdi
0x18003f145  push    r14
0x18003f147  sub     rsp, 0B0h
0x18003f14e  mov     rax, cs:__security_cookie
0x18003f155  xor     rax, rsp
0x18003f158  mov     [rsp+0D8h+var_38], rax
0x18003f160  mov     r14, r9
0x18003f163  mov     [rsp+0D8h+TokenInformationLength], 0
0x18003f16b  mov     r9d, 54h ; 'T'; TokenInformationLength
0x18003f171  lea     rax, [rsp+0D8h+TokenInformationLength]
0x18003f176  mov     ebp, r8d
0x18003f179  mov     [rsp+0D8h+ReturnLength], rax; ReturnLength
0x18003f17e  mov     rsi, rdx
0x18003f181  lea     r8, [rsp+0D8h+TokenInformation]; TokenInformation
0x18003f186  mov     rbx, rcx
0x18003f189  lea     rdi, [rsp+0D8h+TokenInformation]
0x18003f18e  lea     edx, [r9-53h]; TokenInformationClass
0x18003f192  call    cs:__imp_NtQueryInformationToken
0x18003f198  test    eax, eax
0x18003f19a  jns     short loc_18003F1FA
0x18003f19c  cmp     eax, 0C0000023h
0x18003f1a1  jnz     short loc_18003F1F6
0x18003f1a3  mov     rcx, gs:60h
0x18003f1ac  xor     edx, edx; Flags
0x18003f1ae  mov     r8d, [rsp+0D8h+TokenInformationLength]; Size
0x18003f1b3  mov     rcx, [rcx+30h]; HeapHandle
0x18003f1b7  call    cs:__imp_RtlAllocateHeap
0x18003f1bd  mov     rdi, rax
0x18003f1c0  test    rax, rax
0x18003f1c3  jnz     short loc_18003F1D2
0x18003f1c5  mov     ecx, 0C000009Ah; Status
0x18003f1ca  call    cs:__imp_RtlNtStatusToDosError
0x18003f1d0  jmp     short loc_18003F218
0x18003f1d2  mov     r9d, [rsp+0D8h+TokenInformationLength]; TokenInformationLength
0x18003f1d7  lea     rax, [rsp+0D8h+TokenInformationLength]
0x18003f1dc  mov     r8, rdi; TokenInformation
0x18003f1df  mov     [rsp+0D8h+ReturnLength], rax; ReturnLength
0x18003f1e4  mov     edx, 1; TokenInformationClass
0x18003f1e9  mov     rcx, rbx; TokenHandle
0x18003f1ec  call    cs:__imp_NtQueryInformationToken
0x18003f1f2  test    eax, eax
0x18003f1f4  jns     short loc_18003F1FA
0x18003f1f6  mov     ecx, eax
0x18003f1f8  jmp     short loc_18003F1CA
0x18003f1fa  mov     rcx, [rdi]; pSid
0x18003f1fd  mov     r9, r14; ppAuditPolicy
0x18003f200  mov     r8d, ebp; dwPolicyCount
0x18003f203  mov     rdx, rsi; pSubCategoryGuids
0x18003f206  xor     ebx, ebx
0x18003f208  call    cs:__imp_AuditComputeEffectivePolicyBySid
0x18003f20e  test    al, al
0x18003f210  jnz     short loc_18003F21A
0x18003f212  call    cs:__imp_GetLastError
0x18003f218  mov     ebx, eax
0x18003f21a  lea     rax, [rsp+0D8h+TokenInformation]
0x18003f21f  cmp     rdi, rax
0x18003f222  jz      short loc_18003F23C
0x18003f224  mov     rcx, gs:60h
0x18003f22d  mov     r8, rdi; P
0x18003f230  xor     edx, edx; Flags
0x18003f232  mov     rcx, [rcx+30h]; HeapHandle
0x18003f236  call    cs:__imp_RtlFreeHeap
0x18003f23c  test    ebx, ebx
0x18003f23e  jz      short loc_18003F24C
0x18003f240  mov     ecx, ebx; dwErrCode
0x18003f242  call    cs:__imp_SetLastError
0x18003f248  xor     al, al
0x18003f24a  jmp     short loc_18003F24E
0x18003f24c  mov     al, 1
0x18003f24e  mov     rcx, [rsp+0D8h+var_38]
0x18003f256  xor     rcx, rsp; StackCookie
0x18003f259  call    __security_check_cookie
0x18003f25e  add     rsp, 0B0h
0x18003f265  pop     r14
0x18003f267  pop     rdi
0x18003f268  pop     rsi
0x18003f269  pop     rbp
0x18003f26a  pop     rbx
0x18003f26b  retn
```
