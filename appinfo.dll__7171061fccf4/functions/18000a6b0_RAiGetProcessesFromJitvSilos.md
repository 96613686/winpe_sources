# RAiGetProcessesFromJitvSilos

- ea: `0x18000a6b0`
- end: `0x18000a932`
- name: `RAiGetProcessesFromJitvSilos`
- size: `642`
- prototype: `int __fastcall(PRPC_ASYNC_STATE pAsync, RPC_BINDING_HANDLE Binding, __int64, __int64, __int64)`
- caller_count: `0`
- callee_count: `3`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x18000a6b0`
- `0x18003e9e8`
- `0x18003ea48`

## import_xrefs

- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x18000a720`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x18000a720`
- `RPCRT4!RpcImpersonateClient` at `0x18000a772`
- `RPCRT4!RpcImpersonateClient` at `0x18000a772`
- `RPCRT4!RpcRevertToSelf` at `0x18000a7e9`
- `RPCRT4!RpcRevertToSelf` at `0x18000a7e9`
- `RPCRT4!RpcAsyncCompleteCall` at `0x18000a8a8`
- `RPCRT4!RpcAsyncCompleteCall` at `0x18000a8a8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a91f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a92a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a91f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a92a`
- `ntdll!NtClose` at `0x18000a818`
- `ntdll!NtClose` at `0x18000a876`
- `ntdll!NtClose` at `0x18000a911`
- `ntdll!NtClose` at `0x18000a818`
- `ntdll!NtClose` at `0x18000a876`
- `ntdll!NtClose` at `0x18000a911`
- `ntdll!NtOpenProcess` at `0x18000a762`
- `ntdll!NtOpenProcess` at `0x18000a762`
- `ntdll!NtOpenThreadToken` at `0x18000a795`
- `ntdll!NtOpenThreadToken` at `0x18000a795`
- `ntdll!NtDuplicateToken` at `0x18000a7e1`
- `ntdll!NtDuplicateToken` at `0x18000a7e1`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x18000a8f5`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x18000a904`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x18000a8f5`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x18000a904`
- `ext-ms-win-desktopappx-l1-2-0!GetProcessesFromJitvSilos` at `0x18000a888`
- `ext-ms-win-desktopappx-l1-2-0!GetProcessesFromJitvSilos` at `0x18000a888`

## pseudocode

```c
int __fastcall RAiGetProcessesFromJitvSilos(
        PRPC_ASYNC_STATE pAsync,
        RPC_BINDING_HANDLE Binding,
        __int64 a3,
        __int64 a4,
        __int64 a5)
{
  int v9; // ebx
  int v10; // r8d
  int v11; // eax
  int v12; // edi
  RPC_STATUS v13; // eax
  char *v14; // rsi
  char *v15; // r14
  int ProcessesFromJitvSilos; // edi
  int v17; // edx
  int result; // eax
  unsigned int Pid; // [rsp+30h] [rbp-61h] BYREF
  HANDLE Handle; // [rsp+38h] [rbp-59h] BYREF
  void *TokenHandle; // [rsp+40h] [rbp-51h] BYREF
  void *ProcessHandle; // [rsp+48h] [rbp-49h] BYREF
  int Reply; // [rsp+50h] [rbp-41h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+58h] [rbp-39h] BYREF
  struct _CLIENT_ID ClientId; // [rsp+88h] [rbp-9h] BYREF

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 32, WPP_b23fa736e9853481a42645a0499c03f5_Traceguids, a3);
  Pid = 0;
  ProcessHandle = 0;
  TokenHandle = 0;
  Handle = 0;
  ClientId = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  v9 = I_RpcBindingInqLocalClientPID(Binding, &Pid);
  if ( !v9 )
  {
    ClientId.UniqueProcess = (HANDLE)Pid;
    ObjectAttributes.Length = 48;
    memset(&ObjectAttributes.RootDirectory, 0, 20);
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    v11 = NtOpenProcess(&ProcessHandle, 0x1004C0u, &ObjectAttributes, &ClientId);
    if ( v11 < 0 )
    {
      v9 = RtlNtStatusToDosErrorNoTeb(v11);
    }
    else
    {
      v9 = RpcImpersonateClient(0);
      if ( !v9 )
      {
        v12 = NtOpenThreadToken((HANDLE)0xFFFFFFFFFFFFFFFELL, 0xF01FFu, 1u, &TokenHandle);
        if ( v12 >= 0 )
        {
          ObjectAttributes.Length = 48;
          ObjectAttributes.RootDirectory = 0;
          ObjectAttributes.Attributes = v9;
          ObjectAttributes.ObjectName = 0;
          *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
          v12 = NtDuplicateToken(TokenHandle, 0, &ObjectAttributes, 0, TokenPrimary, &Handle);
        }
        v13 = RpcRevertToSelf();
        v9 = v13;
        if ( v12 < 0 )
        {
          v9 = RtlNtStatusToDosErrorNoTeb(v12);
        }
        else if ( !v13 )
        {
          v14 = (char *)ProcessHandle;
          v15 = (char *)Handle;
          ProcessHandle = 0;
LABEL_12:
          Handle = 0;
          goto LABEL_13;
        }
      }
    }
  }
  v15 = 0;
  v14 = 0;
  if ( Handle )
  {
    NtClose(Handle);
    goto LABEL_12;
  }
LABEL_13:
  if ( TokenHandle )
  {
    NtClose(TokenHandle);
    TokenHandle = 0;
  }
  if ( ProcessHandle )
    NtClose(ProcessHandle);
  ProcessesFromJitvSilos = v9;
  if ( v9 < 0 || (ProcessesFromJitvSilos = GetProcessesFromJitvSilos(a3, a4, a5), ProcessesFromJitvSilos < 0) )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_SD(*((_QWORD *)WPP_GLOBAL_Control + 2), 33, v10, a3, ProcessesFromJitvSilos);
  }
  v17 = (unsigned __int16)ProcessesFromJitvSilos;
  if ( ProcessesFromJitvSilos >= 0 )
    v17 = 0;
  Reply = v17;
  RpcAsyncCompleteCall(pAsync, &Reply);
  if ( (unsigned __int64)(v15 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(v15);
  result = (_DWORD)v14 - 1;
  if ( (unsigned __int64)(v14 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    return CloseHandle(v14);
  return result;
}

```

## disassembly

```asm
0x18000a6b0  push    rbp
0x18000a6b2  push    rbx
0x18000a6b3  push    rsi
0x18000a6b4  push    rdi
0x18000a6b5  push    r12
0x18000a6b7  push    r13
0x18000a6b9  push    r14
0x18000a6bb  push    r15
0x18000a6bd  lea     rbp, [rsp-17h]
0x18000a6c2  sub     rsp, 0A8h
0x18000a6c9  mov     r12, r9
0x18000a6cc  mov     r15, r8
0x18000a6cf  mov     rbx, rdx
0x18000a6d2  mov     r13, rcx
0x18000a6d5  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a6dc  lea     rax, WPP_GLOBAL_Control
0x18000a6e3  cmp     rcx, rax
0x18000a6e6  jz      short loc_18000A6F2
0x18000a6e8  test    byte ptr [rcx+1Ch], 1
0x18000a6ec  jnz     loc_18000A8D6
0x18000a6f2  xor     edi, edi
0x18000a6f4  lea     rdx, [rbp+4Fh+Pid]; Pid
0x18000a6f8  xorps   xmm1, xmm1
0x18000a6fb  mov     [rbp+4Fh+Pid], edi
0x18000a6fe  xorps   xmm0, xmm0
0x18000a701  mov     [rbp+4Fh+ProcessHandle], rdi
0x18000a705  mov     rcx, rbx; Binding
0x18000a708  mov     [rbp+4Fh+TokenHandle], rdi
0x18000a70c  mov     [rbp+4Fh+Handle], rdi
0x18000a710  movups  xmmword ptr [rbp+4Fh+ClientId.UniqueProcess], xmm0
0x18000a714  movups  xmmword ptr [rbp+4Fh+ObjectAttributes.Length], xmm1
0x18000a718  movups  xmmword ptr [rbp+4Fh+ObjectAttributes.ObjectName], xmm1
0x18000a71c  movups  xmmword ptr [rbp+4Fh+ObjectAttributes.SecurityDescriptor], xmm1
0x18000a720  call    cs:__imp_I_RpcBindingInqLocalClientPID
0x18000a726  mov     ebx, eax
0x18000a728  test    eax, eax
0x18000a72a  jnz     loc_18000A867
0x18000a730  mov     eax, [rbp+4Fh+Pid]
0x18000a733  lea     r9, [rbp+4Fh+ClientId]; ClientId
0x18000a737  xorps   xmm0, xmm0
0x18000a73a  mov     [rbp+4Fh+ClientId.UniqueProcess], rax
0x18000a73e  lea     r8, [rbp+4Fh+ObjectAttributes]; ObjectAttributes
0x18000a742  mov     [rbp+4Fh+ObjectAttributes.Length], 30h ; '0'
0x18000a749  mov     edx, 1004C0h; DesiredAccess
0x18000a74e  mov     [rbp+4Fh+ObjectAttributes.RootDirectory], rdi
0x18000a752  lea     rcx, [rbp+4Fh+ProcessHandle]; ProcessHandle
0x18000a756  mov     [rbp+4Fh+ObjectAttributes.Attributes], edi
0x18000a759  movdqu  xmmword ptr [rbp+4Fh+ObjectAttributes.SecurityDescriptor], xmm0
0x18000a75e  mov     [rbp+4Fh+ObjectAttributes.ObjectName], rdi
0x18000a762  call    cs:__imp_NtOpenProcess
0x18000a768  test    eax, eax
0x18000a76a  js      loc_18000A8F3
0x18000a770  xor     ecx, ecx; BindingHandle
0x18000a772  call    cs:__imp_RpcImpersonateClient
0x18000a778  mov     ebx, eax
0x18000a77a  test    eax, eax
0x18000a77c  jnz     loc_18000A867
0x18000a782  lea     r9, [rbp+4Fh+TokenHandle]; TokenHandle
0x18000a786  mov     r8b, 1; OpenAsSelf
0x18000a789  mov     edx, 0F01FFh; DesiredAccess
0x18000a78e  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x18000a795  call    cs:__imp_NtOpenThreadToken
0x18000a79b  mov     edi, eax
0x18000a79d  test    eax, eax
0x18000a79f  js      short loc_18000A7E9
0x18000a7a1  mov     rcx, [rbp+4Fh+TokenHandle]; ExistingTokenHandle
0x18000a7a5  lea     rax, [rbp+4Fh+Handle]
0x18000a7a9  xorps   xmm0, xmm0
0x18000a7ac  mov     [rsp+0E0h+NewTokenHandle], rax; NewTokenHandle
0x18000a7b1  xor     r9d, r9d; EffectiveOnly
0x18000a7b4  mov     [rsp+0E0h+TokenType], 1; TokenType
0x18000a7bc  lea     r8, [rbp+4Fh+ObjectAttributes]; ObjectAttributes
0x18000a7c0  mov     [rbp+4Fh+ObjectAttributes.Length], 30h ; '0'
0x18000a7c7  xor     edx, edx; DesiredAccess
0x18000a7c9  mov     [rbp+4Fh+ObjectAttributes.RootDirectory], 0
0x18000a7d1  mov     [rbp+4Fh+ObjectAttributes.Attributes], ebx
0x18000a7d4  mov     [rbp+4Fh+ObjectAttributes.ObjectName], 0
0x18000a7dc  movdqu  xmmword ptr [rbp+4Fh+ObjectAttributes.SecurityDescriptor], xmm0
0x18000a7e1  call    cs:__imp_NtDuplicateToken
0x18000a7e7  mov     edi, eax
0x18000a7e9  call    cs:__imp_RpcRevertToSelf
0x18000a7ef  mov     ebx, eax
0x18000a7f1  test    edi, edi
0x18000a7f3  js      loc_18000A902
0x18000a7f9  test    eax, eax
0x18000a7fb  jnz     short loc_18000A865
0x18000a7fd  mov     rsi, [rbp+4Fh+ProcessHandle]
0x18000a801  xor     edi, edi
0x18000a803  mov     r14, [rbp+4Fh+Handle]
0x18000a807  mov     [rbp+4Fh+ProcessHandle], rdi
0x18000a80b  mov     [rbp+4Fh+Handle], rdi
0x18000a80f  mov     rcx, [rbp+4Fh+TokenHandle]; Handle
0x18000a813  test    rcx, rcx
0x18000a816  jz      short loc_18000A822
0x18000a818  call    cs:__imp_NtClose
0x18000a81e  mov     [rbp+4Fh+TokenHandle], rdi
0x18000a822  mov     rcx, [rbp+4Fh+ProcessHandle]; Handle
0x18000a826  test    rcx, rcx
0x18000a829  jnz     loc_18000A911
0x18000a82f  mov     edi, ebx
0x18000a831  test    ebx, ebx
0x18000a833  jns     short loc_18000A87E
0x18000a835  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a83c  lea     rax, WPP_GLOBAL_Control
0x18000a843  cmp     rcx, rax
0x18000a846  jz      short loc_18000A894
0x18000a848  test    byte ptr [rcx+1Ch], 1
0x18000a84c  jz      short loc_18000A894
0x18000a84e  mov     rcx, [rcx+10h]
0x18000a852  mov     edx, 21h ; '!'
0x18000a857  mov     r9, r15
0x18000a85a  mov     [rsp+0E0h+TokenType], edi
0x18000a85e  call    WPP_SF_SD
0x18000a863  jmp     short loc_18000A894
0x18000a865  xor     edi, edi
0x18000a867  mov     rcx, [rbp+4Fh+Handle]; Handle
0x18000a86b  mov     r14, rdi
0x18000a86e  mov     rsi, rdi
0x18000a871  test    rcx, rcx
0x18000a874  jz      short loc_18000A80F
0x18000a876  call    cs:__imp_NtClose
0x18000a87c  jmp     short loc_18000A80B
0x18000a87e  mov     r8, [rbp+4Fh+arg_20]
0x18000a882  mov     rdx, r12
0x18000a885  mov     rcx, r15
0x18000a888  call    cs:__imp_GetProcessesFromJitvSilos
0x18000a88e  mov     edi, eax
0x18000a890  test    eax, eax
0x18000a892  js      short loc_18000A835
0x18000a894  xor     eax, eax
0x18000a896  movzx   edx, di
0x18000a899  test    edi, edi
0x18000a89b  mov     rcx, r13; pAsync
0x18000a89e  cmovns  edx, eax
0x18000a8a1  mov     [rbp+4Fh+Reply], edx
0x18000a8a4  lea     rdx, [rbp+4Fh+Reply]; Reply
0x18000a8a8  call    cs:__imp_RpcAsyncCompleteCall
0x18000a8ae  lea     rax, [r14-1]
0x18000a8b2  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000a8b6  jbe     short loc_18000A91C
0x18000a8b8  lea     rax, [rsi-1]
0x18000a8bc  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000a8c0  jbe     short loc_18000A927
0x18000a8c2  add     rsp, 0A8h
0x18000a8c9  pop     r15
0x18000a8cb  pop     r14
0x18000a8cd  pop     r13
0x18000a8cf  pop     r12
0x18000a8d1  pop     rdi
0x18000a8d2  pop     rsi
0x18000a8d3  pop     rbx
0x18000a8d4  pop     rbp
0x18000a8d5  retn
0x18000a8d6  mov     rcx, [rcx+10h]
0x18000a8da  lea     r8, WPP_b23fa736e9853481a42645a0499c03f5_Traceguids
0x18000a8e1  mov     edx, 20h ; ' '
0x18000a8e6  mov     r9, r15
0x18000a8e9  call    WPP_SF_S
0x18000a8ee  jmp     loc_18000A6F2
0x18000a8f3  mov     ecx, eax; Status
0x18000a8f5  call    cs:__imp_RtlNtStatusToDosErrorNoTeb
0x18000a8fb  mov     ebx, eax
0x18000a8fd  jmp     loc_18000A867
0x18000a902  mov     ecx, edi; Status
0x18000a904  call    cs:__imp_RtlNtStatusToDosErrorNoTeb
0x18000a90a  mov     ebx, eax
0x18000a90c  jmp     loc_18000A865
0x18000a911  call    cs:__imp_NtClose
0x18000a917  jmp     loc_18000A82F
0x18000a91c  mov     rcx, r14; hObject
0x18000a91f  call    cs:__imp_CloseHandle
0x18000a925  jmp     short loc_18000A8B8
0x18000a927  mov     rcx, rsi; hObject
0x18000a92a  call    cs:__imp_CloseHandle
0x18000a930  jmp     short loc_18000A8C2
```
