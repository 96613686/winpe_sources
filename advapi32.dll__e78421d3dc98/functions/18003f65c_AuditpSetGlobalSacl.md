# AuditpSetGlobalSacl

- ea: `0x18003f65c`
- end: `0x18003f775`
- name: `AuditpSetGlobalSacl`
- size: `281`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18003f4f0`

## callees

- `0x18003f65c`
- `0x180065090`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x18003f72e`
- `ntdll!RtlNtStatusToDosError` at `0x18003f72e`
- `api-ms-win-security-base-l1-1-0!GetAclInformation` at `0x18003f6a8`
- `api-ms-win-security-base-l1-1-0!GetAclInformation` at `0x18003f6a8`
- `KERNEL32!GetLastError` at `0x18003f6b2`
- `KERNEL32!GetLastError` at `0x18003f6b2`
- `KERNEL32!SetLastError` at `0x18003f748`
- `KERNEL32!SetLastError` at `0x18003f748`
- `RPCRT4!NdrClientCall3` at `0x18003f71d`
- `RPCRT4!NdrClientCall3` at `0x18003f71d`

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
    Pointer = (unsigned int)NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&stru_180067210, 0x67u, 0).Pointer;
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
0x18003f65c  mov     r11, rsp
0x18003f65f  mov     [r11+18h], rbx
0x18003f663  mov     [r11+20h], rsi
0x18003f667  push    rdi
0x18003f668  sub     rsp, 80h
0x18003f66f  mov     rax, cs:__security_cookie
0x18003f676  xor     rax, rsp
0x18003f679  mov     [rsp+88h+var_18], rax
0x18003f67e  mov     rdi, rdx
0x18003f681  mov     rsi, rcx
0x18003f684  xor     ebx, ebx
0x18003f686  xor     eax, eax
0x18003f688  mov     [r11-28h], rax
0x18003f68c  mov     [rsp+88h+var_20], eax
0x18003f690  mov     dword ptr [rsp+88h+var_58+4], eax
0x18003f694  test    rdx, rdx
0x18003f697  jz      short loc_18003F6D2
0x18003f699  lea     r9d, [rbx+2]; dwAclInformationClass
0x18003f69d  lea     r8d, [rbx+0Ch]; nAclInformationLength
0x18003f6a1  lea     rdx, [r11-28h]; pAclInformation
0x18003f6a5  mov     rcx, rdi; pAcl
0x18003f6a8  call    cs:__imp_GetAclInformation
0x18003f6ae  test    eax, eax
0x18003f6b0  jnz     short loc_18003F6BF
0x18003f6b2  call    cs:__imp_GetLastError
0x18003f6b8  mov     ebx, eax
0x18003f6ba  jmp     loc_18003F742
0x18003f6bf  mov     ecx, [rsp+88h+var_20]
0x18003f6c3  add     ecx, [rsp+88h+var_24]
0x18003f6c7  mov     dword ptr [rsp+88h+var_58], ecx
0x18003f6cb  mov     qword ptr [rsp+88h+var_58+8], rdi
0x18003f6d0  jmp     short loc_18003F6DB
0x18003f6d2  mov     dword ptr [rsp+88h+var_58], eax
0x18003f6d6  mov     qword ptr [rsp+88h+var_58+8], rax
0x18003f6db  mov     [rsp+88h+var_40], 0
0x18003f6e4  movaps  xmm0, [rsp+88h+var_58]
0x18003f6e9  movdqa  [rsp+88h+var_58], xmm0
0x18003f6ef  movups  xmm1, xmmword ptr [rsi]
0x18003f6f2  movdqu  [rsp+88h+var_38], xmm1
0x18003f6f8  lea     rax, [rsp+88h+var_58]
0x18003f6fd  mov     [rsp+88h+var_60], rax
0x18003f702  lea     rax, [rsp+88h+var_38]
0x18003f707  mov     [rsp+88h+var_68], rax
0x18003f70c  xor     r9d, r9d
0x18003f70f  xor     r8d, r8d; pReturnValue
0x18003f712  lea     edx, [r9+67h]; nProcNum
0x18003f716  lea     rcx, stru_180067210; pProxyInfo
0x18003f71d  call    cs:__imp_NdrClientCall3
0x18003f723  mov     [rsp+88h+var_40], rax
0x18003f728  test    eax, eax
0x18003f72a  jns     short loc_18003F73A
0x18003f72c  mov     ecx, eax; Status
0x18003f72e  call    cs:__imp_RtlNtStatusToDosError
0x18003f734  mov     ebx, eax
0x18003f736  mov     [rsp+88h+var_48], eax
0x18003f73a  jmp     short loc_18003F742
0x18003f73c  mov     ebx, eax
0x18003f73e  mov     [rsp+88h+var_48], eax
0x18003f742  test    ebx, ebx
0x18003f744  jz      short loc_18003F750
0x18003f746  mov     ecx, ebx; dwErrCode
0x18003f748  call    cs:__imp_SetLastError
0x18003f74e  test    ebx, ebx
0x18003f750  setz    al
0x18003f753  mov     rcx, [rsp+88h+var_18]
0x18003f758  xor     rcx, rsp; StackCookie
0x18003f75b  call    __security_check_cookie
0x18003f760  lea     r11, [rsp+88h+var_8]
0x18003f768  mov     rbx, [r11+20h]
0x18003f76c  mov     rsi, [r11+28h]
0x18003f770  mov     rsp, r11
0x18003f773  pop     rdi
0x18003f774  retn
0x1800659ff  push    rbp
0x180065a01  sub     rsp, 30h
0x180065a05  mov     rbp, rdx
0x180065a08  mov     rcx, [rcx]
0x180065a0b  mov     ecx, [rcx]; ExceptionCode
0x180065a0d  call    cs:__imp_I_RpcExceptionFilter
0x180065a13  nop
0x180065a14  add     rsp, 30h
0x180065a18  pop     rbp
0x180065a19  retn
```
