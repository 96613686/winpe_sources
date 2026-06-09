# AiGetClientInformation(void *,void * *,void * *,ulong *,ulong *)

- ea: `0x18000a230`
- end: `0x18000a4dd`
- name: `?AiGetClientInformation@@YAKPEAXPEAPEAX1PEAK2@Z`
- size: `685`
- prototype: `unsigned int __fastcall(void *, void **, void **, unsigned int *, unsigned int *)`
- caller_count: `17`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18001ab00`
- `0x1800230e0`
- `0x180025940`
- `0x180027464`
- `0x180027d78`
- `0x1800286a4`
- `0x18002a1d8`
- `0x18002c72c`
- `0x18002cc58`
- `0x18002cf84`
- `0x180032810`
- `0x18003a560`
- `0x18003a620`
- `0x18003a8b0`
- `0x18003b9f0`
- `0x18003db90`
- `0x18003e094`

## callees

- `0x18000a230`

## import_xrefs

- `RPCRT4!RpcImpersonateClient` at `0x18000a2fe`
- `RPCRT4!RpcImpersonateClient` at `0x18000a2fe`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x18000a28e`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x18000a28e`
- `RPCRT4!RpcRevertToSelf` at `0x18000a380`
- `RPCRT4!RpcRevertToSelf` at `0x18000a380`
- `ntdll!NtClose` at `0x18000a40c`
- `ntdll!NtClose` at `0x18000a4b7`
- `ntdll!NtClose` at `0x18000a4cc`
- `ntdll!NtClose` at `0x18000a40c`
- `ntdll!NtClose` at `0x18000a4b7`
- `ntdll!NtClose` at `0x18000a4cc`
- `ntdll!RtlNtStatusToDosError` at `0x18000a46f`
- `ntdll!RtlNtStatusToDosError` at `0x18000a46f`
- `ntdll!NtOpenProcess` at `0x18000a2d7`
- `ntdll!NtOpenProcess` at `0x18000a2d7`
- `ntdll!NtQueryInformationToken` at `0x18000a459`
- `ntdll!NtQueryInformationToken` at `0x18000a459`
- `ntdll!NtOpenThreadToken` at `0x18000a325`
- `ntdll!NtOpenThreadToken` at `0x18000a325`
- `ntdll!NtDuplicateToken` at `0x18000a371`
- `ntdll!NtDuplicateToken` at `0x18000a371`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x18000a484`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x18000a49a`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x18000a484`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x18000a49a`

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
0x18000a230  mov     rax, rsp
0x18000a233  push    rbp
0x18000a234  push    rbx
0x18000a235  lea     rbp, [rax-57h]
0x18000a239  sub     rsp, 0A8h
0x18000a240  mov     [rax+8], rsi
0x18000a244  xorps   xmm1, xmm1
0x18000a247  mov     [rax+10h], rdi
0x18000a24b  xorps   xmm0, xmm0
0x18000a24e  mov     [rax+18h], r12
0x18000a252  mov     rsi, r9
0x18000a255  xor     r12d, r12d
0x18000a258  mov     [rax-18h], r15
0x18000a25c  mov     r15, rdx
0x18000a25f  mov     [rbp+4Fh+ReturnLength], r12d
0x18000a263  lea     rdx, [rbp+4Fh+Pid]; Pid
0x18000a267  mov     [rbp+4Fh+Pid], r12d
0x18000a26b  mov     rdi, r8
0x18000a26e  mov     [rbp+4Fh+TokenInformation], r12d
0x18000a272  mov     [rbp+4Fh+ProcessHandle], r12
0x18000a276  mov     [rbp+4Fh+TokenHandle], r12
0x18000a27a  mov     [rbp+4Fh+NewTokenHandle], r12
0x18000a27e  movups  xmmword ptr [rbp+2Fh], xmm0
0x18000a282  movups  xmmword ptr [rbp+4Fh+ObjectAttributes.Length], xmm1
0x18000a286  movups  xmmword ptr [rbp+4Fh+ObjectAttributes.ObjectName], xmm1
0x18000a28a  movups  xmmword ptr [rbp+4Fh+ObjectAttributes.SecurityDescriptor], xmm1
0x18000a28e  call    cs:__imp_I_RpcBindingInqLocalClientPID
0x18000a295  nop     dword ptr [rax+rax+00h]
0x18000a29a  mov     ebx, eax
0x18000a29c  test    eax, eax
0x18000a29e  jnz     loc_18000A3DE
0x18000a2a4  mov     eax, [rbp+4Fh+Pid]
0x18000a2a7  lea     r9, [rbp+4Fh+ClientId]; ClientId
0x18000a2ab  xorps   xmm0, xmm0
0x18000a2ae  mov     [rbp+4Fh+ClientId.UniqueProcess], rax
0x18000a2b2  lea     r8, [rbp+4Fh+ObjectAttributes]; ObjectAttributes
0x18000a2b6  mov     [rbp+4Fh+ObjectAttributes.Length], 30h ; '0'
0x18000a2bd  mov     edx, 1004C0h; DesiredAccess
0x18000a2c2  mov     [rbp+4Fh+ObjectAttributes.RootDirectory], r12
0x18000a2c6  lea     rcx, [rbp+4Fh+ProcessHandle]; ProcessHandle
0x18000a2ca  mov     [rbp+4Fh+ObjectAttributes.Attributes], r12d
0x18000a2ce  movdqu  xmmword ptr [rbp+4Fh+ObjectAttributes.SecurityDescriptor], xmm0
0x18000a2d3  mov     [rbp+4Fh+ObjectAttributes.ObjectName], r12
0x18000a2d7  call    cs:__imp_NtOpenProcess
0x18000a2de  nop     dword ptr [rax+rax+00h]
0x18000a2e3  test    eax, eax
0x18000a2e5  js      loc_18000A482
0x18000a2eb  mov     [rsp+0B0h+arg_18], r14
0x18000a2f3  test    rdi, rdi
0x18000a2f6  jz      loc_18000A3A4
0x18000a2fc  xor     ecx, ecx; BindingHandle
0x18000a2fe  call    cs:__imp_RpcImpersonateClient
0x18000a305  nop     dword ptr [rax+rax+00h]
0x18000a30a  mov     ebx, eax
0x18000a30c  test    eax, eax
0x18000a30e  jnz     loc_18000A3D6
0x18000a314  lea     r9, [rbp+4Fh+TokenHandle]; TokenHandle
0x18000a318  mov     r8b, 1; OpenAsSelf
0x18000a31b  mov     edx, 0F01FFh; DesiredAccess
0x18000a320  lea     rcx, [r12-2]; ThreadHandle
0x18000a325  call    cs:__imp_NtOpenThreadToken
0x18000a32c  nop     dword ptr [rax+rax+00h]
0x18000a331  mov     r14d, eax
0x18000a334  test    eax, eax
0x18000a336  js      short loc_18000A380
0x18000a338  mov     rcx, [rbp+4Fh+TokenHandle]; ExistingTokenHandle
0x18000a33c  lea     rax, [rbp+4Fh+NewTokenHandle]
0x18000a340  xorps   xmm0, xmm0
0x18000a343  mov     [rsp+28h], rax; NewTokenHandle
0x18000a348  xor     r9d, r9d; EffectiveOnly
0x18000a34b  mov     [rsp+0B0h+TokenType], 1; TokenType
0x18000a353  lea     r8, [rbp+4Fh+ObjectAttributes]; ObjectAttributes
0x18000a357  mov     [rbp+4Fh+ObjectAttributes.Length], 30h ; '0'
0x18000a35e  xor     edx, edx; DesiredAccess
0x18000a360  mov     [rbp+4Fh+ObjectAttributes.RootDirectory], r12
0x18000a364  mov     [rbp+4Fh+ObjectAttributes.Attributes], r12d
0x18000a368  mov     [rbp+4Fh+ObjectAttributes.ObjectName], r12
0x18000a36c  movdqu  xmmword ptr [rbp+4Fh+ObjectAttributes.SecurityDescriptor], xmm0
0x18000a371  call    cs:__imp_NtDuplicateToken
0x18000a378  nop     dword ptr [rax+rax+00h]
0x18000a37d  mov     r14d, eax
0x18000a380  call    cs:__imp_RpcRevertToSelf
0x18000a387  nop     dword ptr [rax+rax+00h]
0x18000a38c  mov     ebx, eax
0x18000a38e  test    r14d, r14d
0x18000a391  js      loc_18000A497
0x18000a397  test    eax, eax
0x18000a399  jnz     short loc_18000A3D6
0x18000a39b  test    rsi, rsi
0x18000a39e  jnz     loc_18000A43E
0x18000a3a4  mov     rax, [rbp+4Fh+ProcessHandle]
0x18000a3a8  mov     [r15], rax
0x18000a3ab  mov     [rbp+4Fh+ProcessHandle], r12
0x18000a3af  test    rdi, rdi
0x18000a3b2  jz      short loc_18000A3BF
0x18000a3b4  mov     rax, [rbp+4Fh+NewTokenHandle]
0x18000a3b8  mov     [rdi], rax
0x18000a3bb  mov     [rbp+4Fh+NewTokenHandle], r12
0x18000a3bf  test    rsi, rsi
0x18000a3c2  jnz     loc_18000A4AD
0x18000a3c8  mov     rcx, [rbp+4Fh+arg_20]
0x18000a3cc  test    rcx, rcx
0x18000a3cf  jz      short loc_18000A3D6
0x18000a3d1  mov     eax, [rbp+4Fh+Pid]
0x18000a3d4  mov     [rcx], eax
0x18000a3d6  mov     r14, [rsp+0B0h+arg_18]
0x18000a3de  mov     rcx, [rbp+4Fh+NewTokenHandle]; Handle
0x18000a3e2  mov     r15, [rsp+0A0h]
0x18000a3ea  mov     rdi, [rsp+0B0h+arg_8]
0x18000a3f2  mov     rsi, [rsp+0B0h+arg_0]
0x18000a3fa  test    rcx, rcx
0x18000a3fd  jnz     loc_18000A4B7
0x18000a403  mov     rcx, [rbp+4Fh+TokenHandle]; Handle
0x18000a407  test    rcx, rcx
0x18000a40a  jz      short loc_18000A41C
0x18000a40c  call    cs:__imp_NtClose
0x18000a413  nop     dword ptr [rax+rax+00h]
0x18000a418  mov     [rbp+4Fh+TokenHandle], r12
0x18000a41c  mov     rcx, [rbp+4Fh+ProcessHandle]; Handle
0x18000a420  mov     r12, [rsp+0B0h+arg_10]
0x18000a428  test    rcx, rcx
0x18000a42b  jnz     loc_18000A4CC
0x18000a431  mov     eax, ebx
0x18000a433  add     rsp, 0A8h
0x18000a43a  pop     rbx
0x18000a43b  pop     rbp
0x18000a43c  retn
0x18000a43e  mov     rcx, [rbp+4Fh+NewTokenHandle]; TokenHandle
0x18000a442  lea     rax, [rbp+4Fh+ReturnLength]
0x18000a446  mov     r9d, 4; TokenInformationLength
0x18000a44c  mov     qword ptr [rsp+0B0h+TokenType], rax; ReturnLength
0x18000a451  lea     r8, [rbp+4Fh+TokenInformation]; TokenInformation
0x18000a455  lea     edx, [r9+8]; TokenInformationClass
0x18000a459  call    cs:__imp_NtQueryInformationToken
0x18000a460  nop     dword ptr [rax+rax+00h]
0x18000a465  test    eax, eax
0x18000a467  jns     loc_18000A3A4
0x18000a46d  mov     ecx, eax; Status
0x18000a46f  call    cs:__imp_RtlNtStatusToDosError
0x18000a476  nop     dword ptr [rax+rax+00h]
0x18000a47b  mov     ebx, eax
0x18000a47d  jmp     loc_18000A3D6
0x18000a482  mov     ecx, eax; Status
0x18000a484  call    cs:__imp_RtlNtStatusToDosErrorNoTeb
0x18000a48b  nop     dword ptr [rax+rax+00h]
0x18000a490  mov     ebx, eax
0x18000a492  jmp     loc_18000A3DE
0x18000a497  mov     ecx, r14d; Status
0x18000a49a  call    cs:__imp_RtlNtStatusToDosErrorNoTeb
0x18000a4a1  nop     dword ptr [rax+rax+00h]
0x18000a4a6  mov     ebx, eax
0x18000a4a8  jmp     loc_18000A3D6
0x18000a4ad  mov     eax, [rbp+4Fh+TokenInformation]
0x18000a4b0  mov     [rsi], eax
0x18000a4b2  jmp     loc_18000A3C8
0x18000a4b7  call    cs:__imp_NtClose
0x18000a4be  nop     dword ptr [rax+rax+00h]
0x18000a4c3  mov     [rbp+4Fh+NewTokenHandle], r12
0x18000a4c7  jmp     loc_18000A403
0x18000a4cc  call    cs:__imp_NtClose
0x18000a4d3  nop     dword ptr [rax+rax+00h]
0x18000a4d8  jmp     loc_18000A431
```
