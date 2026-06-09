# AiGetClientInformation(void *,void * *,void * *,ulong *,ulong *)

- ea: `0x180009d50`
- end: `0x180009fad`
- name: `?AiGetClientInformation@@YAKPEAXPEAPEAX1PEAK2@Z`
- size: `605`
- prototype: `__int64 __fastcall(void *, void **, void **, unsigned int *, unsigned int *)`
- caller_count: `18`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18001cb90`
- `0x180026ba0`
- `0x180029aa0`
- `0x18002b27c`
- `0x18002bc04`
- `0x18002c480`
- `0x18002e8bc`
- `0x18002ed98`
- `0x180031110`
- `0x180031414`
- `0x180031724`
- `0x180035dbc`
- `0x18003cd80`
- `0x18003ce30`
- `0x18003d070`
- `0x18003e220`
- `0x1800409a0`
- `0x180040d64`

## callees

- `0x180009d50`

## import_xrefs

- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x180009dae`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x180009dae`
- `RPCRT4!RpcImpersonateClient` at `0x180009e12`
- `RPCRT4!RpcImpersonateClient` at `0x180009e12`
- `RPCRT4!RpcRevertToSelf` at `0x180009e84`
- `RPCRT4!RpcRevertToSelf` at `0x180009e84`
- `ntdll!NtClose` at `0x180009f0a`
- `ntdll!NtClose` at `0x180009f93`
- `ntdll!NtClose` at `0x180009fa2`
- `ntdll!NtClose` at `0x180009f0a`
- `ntdll!NtClose` at `0x180009f93`
- `ntdll!NtClose` at `0x180009fa2`
- `ntdll!RtlNtStatusToDosError` at `0x180009f5d`
- `ntdll!RtlNtStatusToDosError` at `0x180009f5d`
- `ntdll!NtOpenProcess` at `0x180009df1`
- `ntdll!NtOpenProcess` at `0x180009df1`
- `ntdll!NtQueryInformationToken` at `0x180009f4d`
- `ntdll!NtQueryInformationToken` at `0x180009f4d`
- `ntdll!NtOpenThreadToken` at `0x180009e35`
- `ntdll!NtOpenThreadToken` at `0x180009e35`
- `ntdll!NtDuplicateToken` at `0x180009e7b`
- `ntdll!NtDuplicateToken` at `0x180009e7b`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x180009f6c`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x180009f7c`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x180009f6c`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x180009f7c`

## pseudocode

```c
__int64 __fastcall AiGetClientInformation(void *a1, void **a2, void **a3, unsigned int *a4, unsigned int *a5)
{
  ULONG v8; // ebx
  int v9; // eax
  int v10; // r14d
  RPC_STATUS v11; // eax
  int v13; // eax
  unsigned int Pid; // [rsp+38h] [rbp-31h] BYREF
  void *NewTokenHandle; // [rsp+40h] [rbp-29h] BYREF
  unsigned int TokenInformation; // [rsp+48h] [rbp-21h] BYREF
  void *TokenHandle; // [rsp+50h] [rbp-19h] BYREF
  void *ProcessHandle; // [rsp+58h] [rbp-11h] BYREF
  ULONG ReturnLength; // [rsp+60h] [rbp-9h] BYREF
  _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+68h] [rbp-1h] BYREF
  _CLIENT_ID ClientId; // [rsp+98h] [rbp+2Fh] BYREF

  ReturnLength = 0;
  Pid = 0;
  TokenInformation = 0;
  ProcessHandle = 0;
  TokenHandle = 0;
  NewTokenHandle = 0;
  ClientId = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  v8 = I_RpcBindingInqLocalClientPID(a1, &Pid);
  if ( !v8 )
  {
    ClientId.UniqueProcess = (HANDLE)Pid;
    ObjectAttributes.Length = 48;
    memset(&ObjectAttributes.RootDirectory, 0, 20);
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    v9 = NtOpenProcess(&ProcessHandle, 0x1004C0u, &ObjectAttributes, &ClientId);
    if ( v9 < 0 )
    {
      v8 = RtlNtStatusToDosErrorNoTeb(v9);
      goto LABEL_16;
    }
    if ( a3 )
    {
      v8 = RpcImpersonateClient(0);
      if ( v8 )
        goto LABEL_16;
      v10 = NtOpenThreadToken((HANDLE)0xFFFFFFFFFFFFFFFELL, 0xF01FFu, 1u, &TokenHandle);
      if ( v10 >= 0 )
      {
        ObjectAttributes.Length = 48;
        memset(&ObjectAttributes.RootDirectory, 0, 20);
        *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
        v10 = NtDuplicateToken(TokenHandle, 0, &ObjectAttributes, 0, TokenPrimary, &NewTokenHandle);
      }
      v11 = RpcRevertToSelf();
      v8 = v11;
      if ( v10 < 0 )
      {
        v8 = RtlNtStatusToDosErrorNoTeb(v10);
        goto LABEL_16;
      }
      if ( v11 )
        goto LABEL_16;
      if ( a4 )
      {
        v13 = NtQueryInformationToken(NewTokenHandle, TokenSessionId, &TokenInformation, 4u, &ReturnLength);
        if ( v13 < 0 )
        {
          v8 = RtlNtStatusToDosError(v13);
          goto LABEL_16;
        }
      }
    }
    *a2 = ProcessHandle;
    ProcessHandle = 0;
    if ( a3 )
    {
      *a3 = NewTokenHandle;
      NewTokenHandle = 0;
    }
    if ( a4 )
      *a4 = TokenInformation;
    if ( a5 )
      *a5 = Pid;
  }
LABEL_16:
  if ( NewTokenHandle )
  {
    NtClose(NewTokenHandle);
    NewTokenHandle = 0;
  }
  if ( TokenHandle )
  {
    NtClose(TokenHandle);
    TokenHandle = 0;
  }
  if ( ProcessHandle )
    NtClose(ProcessHandle);
  return v8;
}

```

## disassembly

```asm
0x180009d50  mov     rax, rsp
0x180009d53  push    rbp
0x180009d54  push    rbx
0x180009d55  lea     rbp, [rax-57h]
0x180009d59  sub     rsp, 0A8h
0x180009d60  mov     [rax+8], rsi
0x180009d64  xorps   xmm1, xmm1
0x180009d67  mov     [rax+10h], rdi
0x180009d6b  xorps   xmm0, xmm0
0x180009d6e  mov     [rax+18h], r12
0x180009d72  mov     rsi, r9
0x180009d75  xor     r12d, r12d
0x180009d78  mov     [rax-18h], r15
0x180009d7c  mov     r15, rdx
0x180009d7f  mov     [rbp+4Fh+ReturnLength], r12d
0x180009d83  lea     rdx, [rbp+4Fh+Pid]; Pid
0x180009d87  mov     [rbp+4Fh+Pid], r12d
0x180009d8b  mov     rdi, r8
0x180009d8e  mov     [rbp+4Fh+TokenInformation], r12d
0x180009d92  mov     [rbp+4Fh+ProcessHandle], r12
0x180009d96  mov     [rbp+4Fh+TokenHandle], r12
0x180009d9a  mov     [rbp+4Fh+NewTokenHandle], r12
0x180009d9e  movups  xmmword ptr [rbp+2Fh], xmm0
0x180009da2  movups  xmmword ptr [rbp+4Fh+ObjectAttributes.Length], xmm1
0x180009da6  movups  xmmword ptr [rbp+4Fh+ObjectAttributes.ObjectName], xmm1
0x180009daa  movups  xmmword ptr [rbp+4Fh+ObjectAttributes.SecurityDescriptor], xmm1
0x180009dae  call    cs:__imp_I_RpcBindingInqLocalClientPID
0x180009db4  mov     ebx, eax
0x180009db6  test    eax, eax
0x180009db8  jnz     loc_180009EDC
0x180009dbe  mov     eax, [rbp+4Fh+Pid]
0x180009dc1  lea     r9, [rbp+4Fh+ClientId]; ClientId
0x180009dc5  xorps   xmm0, xmm0
0x180009dc8  mov     [rbp+4Fh+ClientId.UniqueProcess], rax
0x180009dcc  lea     r8, [rbp+4Fh+ObjectAttributes]; ObjectAttributes
0x180009dd0  mov     [rbp+4Fh+ObjectAttributes.Length], 30h ; '0'
0x180009dd7  mov     edx, 1004C0h; DesiredAccess
0x180009ddc  mov     [rbp+4Fh+ObjectAttributes.RootDirectory], r12
0x180009de0  lea     rcx, [rbp+4Fh+ProcessHandle]; ProcessHandle
0x180009de4  mov     [rbp+4Fh+ObjectAttributes.Attributes], r12d
0x180009de8  movdqu  xmmword ptr [rbp+4Fh+ObjectAttributes.SecurityDescriptor], xmm0
0x180009ded  mov     [rbp+4Fh+ObjectAttributes.ObjectName], r12
0x180009df1  call    cs:__imp_NtOpenProcess
0x180009df7  test    eax, eax
0x180009df9  js      loc_180009F6A
0x180009dff  mov     [rsp+0B0h+arg_18], r14
0x180009e07  test    rdi, rdi
0x180009e0a  jz      loc_180009EA2
0x180009e10  xor     ecx, ecx; BindingHandle
0x180009e12  call    cs:__imp_RpcImpersonateClient
0x180009e18  mov     ebx, eax
0x180009e1a  test    eax, eax
0x180009e1c  jnz     loc_180009ED4
0x180009e22  lea     r9, [rbp+4Fh+TokenHandle]; TokenHandle
0x180009e26  mov     r8b, 1; OpenAsSelf
0x180009e29  mov     edx, 0F01FFh; DesiredAccess
0x180009e2e  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x180009e35  call    cs:__imp_NtOpenThreadToken
0x180009e3b  mov     r14d, eax
0x180009e3e  test    eax, eax
0x180009e40  js      short loc_180009E84
0x180009e42  mov     rcx, [rbp+4Fh+TokenHandle]; ExistingTokenHandle
0x180009e46  lea     rax, [rbp+4Fh+NewTokenHandle]
0x180009e4a  xorps   xmm0, xmm0
0x180009e4d  mov     [rsp+28h], rax; NewTokenHandle
0x180009e52  xor     r9d, r9d; EffectiveOnly
0x180009e55  mov     [rsp+0B0h+TokenType], 1; TokenType
0x180009e5d  lea     r8, [rbp+4Fh+ObjectAttributes]; ObjectAttributes
0x180009e61  mov     [rbp+4Fh+ObjectAttributes.Length], 30h ; '0'
0x180009e68  xor     edx, edx; DesiredAccess
0x180009e6a  mov     [rbp+4Fh+ObjectAttributes.RootDirectory], r12
0x180009e6e  mov     [rbp+4Fh+ObjectAttributes.Attributes], r12d
0x180009e72  mov     [rbp+4Fh+ObjectAttributes.ObjectName], r12
0x180009e76  movdqu  xmmword ptr [rbp+4Fh+ObjectAttributes.SecurityDescriptor], xmm0
0x180009e7b  call    cs:__imp_NtDuplicateToken
0x180009e81  mov     r14d, eax
0x180009e84  call    cs:__imp_RpcRevertToSelf
0x180009e8a  mov     ebx, eax
0x180009e8c  test    r14d, r14d
0x180009e8f  js      loc_180009F79
0x180009e95  test    eax, eax
0x180009e97  jnz     short loc_180009ED4
0x180009e99  test    rsi, rsi
0x180009e9c  jnz     loc_180009F31
0x180009ea2  mov     rax, [rbp+4Fh+ProcessHandle]
0x180009ea6  mov     [r15], rax
0x180009ea9  mov     [rbp+4Fh+ProcessHandle], r12
0x180009ead  test    rdi, rdi
0x180009eb0  jz      short loc_180009EBD
0x180009eb2  mov     rax, [rbp+4Fh+NewTokenHandle]
0x180009eb6  mov     [rdi], rax
0x180009eb9  mov     [rbp+4Fh+NewTokenHandle], r12
0x180009ebd  test    rsi, rsi
0x180009ec0  jnz     loc_180009F89
0x180009ec6  mov     rcx, [rbp+4Fh+arg_20]
0x180009eca  test    rcx, rcx
0x180009ecd  jz      short loc_180009ED4
0x180009ecf  mov     eax, [rbp+4Fh+Pid]
0x180009ed2  mov     [rcx], eax
0x180009ed4  mov     r14, [rsp+0B0h+arg_18]
0x180009edc  mov     rcx, [rbp+4Fh+NewTokenHandle]; Handle
0x180009ee0  mov     r15, [rsp+0A0h]
0x180009ee8  mov     rdi, [rsp+0B0h+arg_8]
0x180009ef0  mov     rsi, [rsp+0B0h+arg_0]
0x180009ef8  test    rcx, rcx
0x180009efb  jnz     loc_180009F93
0x180009f01  mov     rcx, [rbp+4Fh+TokenHandle]; Handle
0x180009f05  test    rcx, rcx
0x180009f08  jz      short loc_180009F14
0x180009f0a  call    cs:__imp_NtClose
0x180009f10  mov     [rbp+4Fh+TokenHandle], r12
0x180009f14  mov     rcx, [rbp+4Fh+ProcessHandle]; Handle
0x180009f18  mov     r12, [rsp+0B0h+arg_10]
0x180009f20  test    rcx, rcx
0x180009f23  jnz     short loc_180009FA2
0x180009f25  mov     eax, ebx
0x180009f27  add     rsp, 0A8h
0x180009f2e  pop     rbx
0x180009f2f  pop     rbp
0x180009f30  retn
0x180009f31  mov     rcx, [rbp+4Fh+NewTokenHandle]; TokenHandle
0x180009f35  lea     rax, [rbp+4Fh+ReturnLength]
0x180009f39  mov     r9d, 4; TokenInformationLength
0x180009f3f  mov     qword ptr [rsp+0B0h+TokenType], rax; ReturnLength
0x180009f44  lea     r8, [rbp+4Fh+TokenInformation]; TokenInformation
0x180009f48  mov     edx, 0Ch; TokenInformationClass
0x180009f4d  call    cs:__imp_NtQueryInformationToken
0x180009f53  test    eax, eax
0x180009f55  jns     loc_180009EA2
0x180009f5b  mov     ecx, eax; Status
0x180009f5d  call    cs:__imp_RtlNtStatusToDosError
0x180009f63  mov     ebx, eax
0x180009f65  jmp     loc_180009ED4
0x180009f6a  mov     ecx, eax; Status
0x180009f6c  call    cs:__imp_RtlNtStatusToDosErrorNoTeb
0x180009f72  mov     ebx, eax
0x180009f74  jmp     loc_180009EDC
0x180009f79  mov     ecx, r14d; Status
0x180009f7c  call    cs:__imp_RtlNtStatusToDosErrorNoTeb
0x180009f82  mov     ebx, eax
0x180009f84  jmp     loc_180009ED4
0x180009f89  mov     eax, [rbp+4Fh+TokenInformation]
0x180009f8c  mov     [rsi], eax
0x180009f8e  jmp     loc_180009EC6
0x180009f93  call    cs:__imp_NtClose
0x180009f99  mov     [rbp+4Fh+NewTokenHandle], r12
0x180009f9d  jmp     loc_180009F01
0x180009fa2  call    cs:__imp_NtClose
0x180009fa8  jmp     loc_180009F25
```
