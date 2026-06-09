# AuditpSetGlobalSacl

- ea: `0x18004459c`
- end: `0x1800446d4`
- name: `AuditpSetGlobalSacl`
- size: `312`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800443f0`

## callees

- `0x18004459c`
- `0x1800720b0`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x180044680`
- `ntdll!RtlNtStatusToDosError` at `0x180044680`
- `api-ms-win-security-base-l1-1-0!GetAclInformation` at `0x1800445e8`
- `api-ms-win-security-base-l1-1-0!GetAclInformation` at `0x1800445e8`
- `KERNEL32!GetLastError` at `0x1800445f8`
- `KERNEL32!GetLastError` at `0x1800445f8`
- `KERNEL32!SetLastError` at `0x1800446a0`
- `KERNEL32!SetLastError` at `0x1800446a0`
- `RPCRT4!NdrClientCall3` at `0x180044669`
- `RPCRT4!NdrClientCall3` at `0x180044669`

## pseudocode

```c
bool __fastcall AuditpSetGlobalSacl(__int64 a1, ACL *a2)
{
  ULONG LastError; // ebx
  NTSTATUS Pointer; // eax
  bool v4; // zf
  __int64 v6; // [rsp+60h] [rbp-28h] BYREF
  int v7; // [rsp+68h] [rbp-20h]

  LastError = 0;
  v6 = 0;
  v7 = 0;
  if ( !a2 || GetAclInformation(a2, &v6, 0xCu, AclSizeInformation) )
  {
    Pointer = (unsigned int)NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&stru_1800751F0, 0x67u, 0).Pointer;
    if ( Pointer < 0 )
      LastError = RtlNtStatusToDosError(Pointer);
  }
  else
  {
    LastError = GetLastError();
  }
  v4 = LastError == 0;
  if ( LastError )
  {
    SetLastError(LastError);
    return LastError == 0;
  }
  return v4;
}

```

## disassembly

```asm
0x18004459c  mov     r11, rsp
0x18004459f  mov     [r11+18h], rbx
0x1800445a3  mov     [r11+20h], rsi
0x1800445a7  push    rdi
0x1800445a8  sub     rsp, 80h
0x1800445af  mov     rax, cs:__security_cookie
0x1800445b6  xor     rax, rsp
0x1800445b9  mov     [rsp+88h+var_18], rax
0x1800445be  mov     rdi, rdx
0x1800445c1  mov     rsi, rcx
0x1800445c4  xor     ebx, ebx
0x1800445c6  xor     eax, eax
0x1800445c8  mov     [r11-28h], rax
0x1800445cc  mov     [rsp+88h+var_20], eax
0x1800445d0  mov     dword ptr [rsp+88h+var_58+4], eax
0x1800445d4  test    rdx, rdx
0x1800445d7  jz      short loc_18004461E
0x1800445d9  lea     r9d, [rbx+2]; dwAclInformationClass
0x1800445dd  lea     r8d, [rbx+0Ch]; nAclInformationLength
0x1800445e1  lea     rdx, [r11-28h]; pAclInformation
0x1800445e5  mov     rcx, rdi; pAcl
0x1800445e8  call    cs:__imp_GetAclInformation
0x1800445ef  nop     dword ptr [rax+rax+00h]
0x1800445f4  test    eax, eax
0x1800445f6  jnz     short loc_18004460B
0x1800445f8  call    cs:__imp_GetLastError
0x1800445ff  nop     dword ptr [rax+rax+00h]
0x180044604  mov     ebx, eax
0x180044606  jmp     loc_18004469A
0x18004460b  mov     ecx, [rsp+88h+var_20]
0x18004460f  add     ecx, [rsp+88h+var_24]
0x180044613  mov     dword ptr [rsp+88h+var_58], ecx
0x180044617  mov     qword ptr [rsp+88h+var_58+8], rdi
0x18004461c  jmp     short loc_180044627
0x18004461e  mov     dword ptr [rsp+88h+var_58], eax
0x180044622  mov     qword ptr [rsp+88h+var_58+8], rax
0x180044627  mov     [rsp+88h+var_40], 0
0x180044630  movaps  xmm0, [rsp+88h+var_58]
0x180044635  movdqa  [rsp+88h+var_58], xmm0
0x18004463b  movups  xmm1, xmmword ptr [rsi]
0x18004463e  movdqu  [rsp+88h+var_38], xmm1
0x180044644  lea     rax, [rsp+88h+var_58]
0x180044649  mov     [rsp+88h+var_60], rax
0x18004464e  lea     rax, [rsp+88h+var_38]
0x180044653  mov     [rsp+88h+var_68], rax
0x180044658  xor     r9d, r9d
0x18004465b  xor     r8d, r8d; pReturnValue
0x18004465e  lea     edx, [r9+67h]; nProcNum
0x180044662  lea     rcx, stru_1800751F0; pProxyInfo
0x180044669  call    cs:__imp_NdrClientCall3
0x180044670  nop     dword ptr [rax+rax+00h]
0x180044675  mov     [rsp+88h+var_40], rax
0x18004467a  test    eax, eax
0x18004467c  jns     short loc_180044692
0x18004467e  mov     ecx, eax; Status
0x180044680  call    cs:__imp_RtlNtStatusToDosError
0x180044687  nop     dword ptr [rax+rax+00h]
0x18004468c  mov     ebx, eax
0x18004468e  mov     [rsp+88h+var_48], eax
0x180044692  jmp     short loc_18004469A
0x180044694  mov     ebx, eax
0x180044696  mov     [rsp+88h+var_48], eax
0x18004469a  test    ebx, ebx
0x18004469c  jz      short loc_1800446AE
0x18004469e  mov     ecx, ebx; dwErrCode
0x1800446a0  call    cs:__imp_SetLastError
0x1800446a7  nop     dword ptr [rax+rax+00h]
0x1800446ac  test    ebx, ebx
0x1800446ae  setz    al
0x1800446b1  mov     rcx, [rsp+88h+var_18]
0x1800446b6  xor     rcx, rsp; StackCookie
0x1800446b9  call    __security_check_cookie
0x1800446be  lea     r11, [rsp+88h+var_8]
0x1800446c6  mov     rbx, [r11+20h]
0x1800446ca  mov     rsi, [r11+28h]
0x1800446ce  mov     rsp, r11
0x1800446d1  pop     rdi
0x1800446d2  retn
0x180072b48  push    rbp
0x180072b4a  sub     rsp, 30h
0x180072b4e  mov     rbp, rdx
0x180072b51  mov     rcx, [rcx]
0x180072b54  mov     ecx, [rcx]; ExceptionCode
0x180072b56  call    cs:__imp_I_RpcExceptionFilter
0x180072b5d  nop     dword ptr [rax+rax+00h]
0x180072b62  nop
0x180072b63  add     rsp, 30h
0x180072b67  pop     rbp
0x180072b68  retn
```
