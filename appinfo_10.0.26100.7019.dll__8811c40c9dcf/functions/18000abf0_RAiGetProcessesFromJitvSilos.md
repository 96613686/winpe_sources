# RAiGetProcessesFromJitvSilos

- ea: `0x18000abf0`
- end: `0x18000af0a`
- name: `RAiGetProcessesFromJitvSilos`
- size: `794`
- prototype: `__int64 __usercall@<rax>(PRPC_ASYNC_STATE pAsync@<rcx>, RPC_BINDING_HANDLE Binding@<rdx>, __int64)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x18000abf0`
- `0x18003b5cc`
- `0x18003b634`

## import_xrefs

- `RPCRT4!RpcRevertToSelf` at `0x18000ad51`
- `RPCRT4!RpcRevertToSelf` at `0x18000ad51`
- `RPCRT4!RpcImpersonateClient` at `0x18000acd0`
- `RPCRT4!RpcImpersonateClient` at `0x18000acd0`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x18000ac6f`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x18000ac6f`
- `RPCRT4!RpcAsyncCompleteCall` at `0x18000ade7`
- `RPCRT4!RpcAsyncCompleteCall` at `0x18000ade7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000aee5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000aef9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000aee5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000aef9`
- `ntdll!NtClose` at `0x18000ad8b`
- `ntdll!NtClose` at `0x18000ae40`
- `ntdll!NtClose` at `0x18000ae96`
- `ntdll!NtClose` at `0x18000ad8b`
- `ntdll!NtClose` at `0x18000ae40`
- `ntdll!NtClose` at `0x18000ae96`
- `ntdll!NtOpenProcess` at `0x18000acba`
- `ntdll!NtOpenProcess` at `0x18000acba`
- `ntdll!NtOpenThreadToken` at `0x18000acf7`
- `ntdll!NtOpenThreadToken` at `0x18000acf7`
- `ntdll!NtDuplicateToken` at `0x18000ad43`
- `ntdll!NtDuplicateToken` at `0x18000ad43`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x18000ae70`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x18000ae83`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x18000ae70`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x18000ae83`
- `ext-ms-win-desktopappx-l1-2-0!GetProcessesFromJitvSilos` at `0x18000adba`
- `ext-ms-win-desktopappx-l1-2-0!GetProcessesFromJitvSilos` at `0x18000adba`

## pseudocode

```c
int __fastcall RAiGetProcessesFromJitvSilos(
        PRPC_ASYNC_STATE pAsync,
        RPC_BINDING_HANDLE Binding,
        __int64 a3,
        __int64 a4,
        __int64 a5)
{
  HANDLE v9; // rdi
  char *v10; // rbx
  int v11; // r8d
  int v12; // r14d
  int v13; // eax
  int v14; // esi
  RPC_STATUS v15; // eax
  int ProcessesFromJitvSilos; // esi
  int v17; // eax
  int result; // eax
  unsigned int Pid; // [rsp+30h] [rbp-41h] BYREF
  HANDLE Handle; // [rsp+38h] [rbp-39h] BYREF
  void *TokenHandle; // [rsp+40h] [rbp-31h] BYREF
  void *ProcessHandle; // [rsp+48h] [rbp-29h] BYREF
  int Reply; // [rsp+50h] [rbp-21h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+58h] [rbp-19h] BYREF
  struct _CLIENT_ID ClientId; // [rsp+88h] [rbp+17h] BYREF

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 32, &WPP_e8c8bde4cfdd31ad7ca53050940b7a3e_Traceguids, a3);
  Pid = 0;
  ProcessHandle = 0;
  TokenHandle = 0;
  v9 = 0;
  Handle = 0;
  v10 = 0;
  ClientId = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  v12 = I_RpcBindingInqLocalClientPID(Binding, &Pid);
  if ( !v12 )
  {
    ClientId.UniqueProcess = (HANDLE)Pid;
    ObjectAttributes.Length = 48;
    memset(&ObjectAttributes.RootDirectory, 0, 20);
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    v13 = NtOpenProcess(&ProcessHandle, 0x1004C0u, &ObjectAttributes, &ClientId);
    if ( v13 < 0 )
    {
      v12 = RtlNtStatusToDosErrorNoTeb(v13);
    }
    else
    {
      v12 = RpcImpersonateClient(0);
      if ( !v12 )
      {
        v14 = NtOpenThreadToken((HANDLE)0xFFFFFFFFFFFFFFFELL, 0xF01FFu, 1u, &TokenHandle);
        if ( v14 >= 0 )
        {
          ObjectAttributes.Length = 48;
          memset(&ObjectAttributes.RootDirectory, 0, 20);
          *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
          v14 = NtDuplicateToken(TokenHandle, 0, &ObjectAttributes, 0, TokenPrimary, &Handle);
        }
        v15 = RpcRevertToSelf();
        v12 = v15;
        if ( v14 < 0 )
        {
          v12 = RtlNtStatusToDosErrorNoTeb(v14);
        }
        else if ( !v15 )
        {
          v10 = (char *)ProcessHandle;
          v9 = Handle;
          ProcessHandle = 0;
LABEL_12:
          Handle = 0;
          goto LABEL_13;
        }
      }
    }
  }
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
  ProcessesFromJitvSilos = v12;
  if ( v12 >= 0 )
    ProcessesFromJitvSilos = GetProcessesFromJitvSilos(a3, a4, a5);
  if ( ProcessesFromJitvSilos < 0
    && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_SD(*((_QWORD *)WPP_GLOBAL_Control + 2), 33, v11, a3, ProcessesFromJitvSilos);
  }
  v17 = (unsigned __int16)ProcessesFromJitvSilos;
  if ( ProcessesFromJitvSilos >= 0 )
    v17 = 0;
  Reply = v17;
  RpcAsyncCompleteCall(pAsync, &Reply);
  if ( (((unsigned __int64)v9 + 1) & 0xFFFFFFFFFFFFFFFEuLL) != 0 )
    CloseHandle(v9);
  result = (_DWORD)v10 - 1;
  if ( (unsigned __int64)(v10 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    return CloseHandle(v10);
  return result;
}

```

## disassembly

```asm
0x18000abf0  mov     [rsp-8+arg_0], rbx
0x18000abf5  mov     [rsp-8+arg_8], rsi
0x18000abfa  mov     [rsp-8+arg_10], rdi
0x18000abff  push    rbp
0x18000ac00  push    r12
0x18000ac02  push    r13
0x18000ac04  push    r14
0x18000ac06  push    r15
0x18000ac08  lea     rbp, [rsp-2Fh]
0x18000ac0d  sub     rsp, 0A0h
0x18000ac14  mov     r12, r9
0x18000ac17  mov     r13, r8
0x18000ac1a  mov     rsi, rdx
0x18000ac1d  mov     r15, rcx
0x18000ac20  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ac27  lea     rax, WPP_GLOBAL_Control
0x18000ac2e  cmp     rcx, rax
0x18000ac31  jz      short loc_18000AC3D
0x18000ac33  test    byte ptr [rcx+1Ch], 1
0x18000ac37  jnz     loc_18000AE51
0x18000ac3d  xor     eax, eax
0x18000ac3f  lea     rdx, [rbp+4Fh+Pid]; Pid
0x18000ac43  xorps   xmm1, xmm1
0x18000ac46  mov     [rbp+4Fh+Pid], eax
0x18000ac49  xorps   xmm0, xmm0
0x18000ac4c  mov     [rbp+4Fh+ProcessHandle], rax
0x18000ac50  mov     rcx, rsi; Binding
0x18000ac53  mov     [rbp+4Fh+TokenHandle], rax
0x18000ac57  mov     edi, eax
0x18000ac59  mov     [rbp+4Fh+Handle], rax
0x18000ac5d  mov     ebx, eax
0x18000ac5f  movups  xmmword ptr [rbp+4Fh+ClientId.UniqueProcess], xmm0
0x18000ac63  movups  xmmword ptr [rbp+4Fh+ObjectAttributes.Length], xmm1
0x18000ac67  movups  xmmword ptr [rbp+4Fh+ObjectAttributes.ObjectName], xmm1
0x18000ac6b  movups  xmmword ptr [rbp+4Fh+ObjectAttributes.SecurityDescriptor], xmm1
0x18000ac6f  call    cs:__imp_I_RpcBindingInqLocalClientPID
0x18000ac76  nop     dword ptr [rax+rax+00h]
0x18000ac7b  xor     esi, esi
0x18000ac7d  mov     r14d, eax
0x18000ac80  test    eax, eax
0x18000ac82  jnz     loc_18000AE33
0x18000ac88  mov     eax, [rbp+4Fh+Pid]
0x18000ac8b  lea     r9, [rbp+4Fh+ClientId]; ClientId
0x18000ac8f  xorps   xmm0, xmm0
0x18000ac92  mov     [rbp+4Fh+ClientId.UniqueProcess], rax
0x18000ac96  lea     r8, [rbp+4Fh+ObjectAttributes]; ObjectAttributes
0x18000ac9a  mov     [rbp+4Fh+ObjectAttributes.Length], 30h ; '0'
0x18000aca1  mov     edx, 1004C0h; DesiredAccess
0x18000aca6  mov     [rbp+4Fh+ObjectAttributes.RootDirectory], rsi
0x18000acaa  lea     rcx, [rbp+4Fh+ProcessHandle]; ProcessHandle
0x18000acae  mov     [rbp+4Fh+ObjectAttributes.Attributes], esi
0x18000acb1  movdqu  xmmword ptr [rbp+4Fh+ObjectAttributes.SecurityDescriptor], xmm0
0x18000acb6  mov     [rbp+4Fh+ObjectAttributes.ObjectName], rsi
0x18000acba  call    cs:__imp_NtOpenProcess
0x18000acc1  nop     dword ptr [rax+rax+00h]
0x18000acc6  test    eax, eax
0x18000acc8  js      loc_18000AE6E
0x18000acce  xor     ecx, ecx; BindingHandle
0x18000acd0  call    cs:__imp_RpcImpersonateClient
0x18000acd7  nop     dword ptr [rax+rax+00h]
0x18000acdc  mov     r14d, eax
0x18000acdf  test    eax, eax
0x18000ace1  jnz     loc_18000AE33
0x18000ace7  lea     r9, [rbp+4Fh+TokenHandle]; TokenHandle
0x18000aceb  mov     r8b, 1; OpenAsSelf
0x18000acee  mov     edx, 0F01FFh; DesiredAccess
0x18000acf3  lea     rcx, [rbx-2]; ThreadHandle
0x18000acf7  call    cs:__imp_NtOpenThreadToken
0x18000acfe  nop     dword ptr [rax+rax+00h]
0x18000ad03  mov     esi, eax
0x18000ad05  test    eax, eax
0x18000ad07  js      short loc_18000AD51
0x18000ad09  xor     ecx, ecx
0x18000ad0b  mov     [rbp+4Fh+ObjectAttributes.Length], 30h ; '0'
0x18000ad12  lea     rax, [rbp+4Fh+Handle]
0x18000ad16  mov     [rbp+4Fh+ObjectAttributes.RootDirectory], rcx
0x18000ad1a  mov     [rbp+4Fh+ObjectAttributes.Attributes], ecx
0x18000ad1d  lea     r8, [rbp+4Fh+ObjectAttributes]; ObjectAttributes
0x18000ad21  mov     [rbp+4Fh+ObjectAttributes.ObjectName], rcx
0x18000ad25  xorps   xmm0, xmm0
0x18000ad28  mov     rcx, [rbp+4Fh+TokenHandle]; ExistingTokenHandle
0x18000ad2c  xor     r9d, r9d; EffectiveOnly
0x18000ad2f  mov     [rsp+0C0h+NewTokenHandle], rax; NewTokenHandle
0x18000ad34  xor     edx, edx; DesiredAccess
0x18000ad36  movdqu  xmmword ptr [rbp+4Fh+ObjectAttributes.SecurityDescriptor], xmm0
0x18000ad3b  mov     [rsp+0C0h+TokenType], 1; TokenType
0x18000ad43  call    cs:__imp_NtDuplicateToken
0x18000ad4a  nop     dword ptr [rax+rax+00h]
0x18000ad4f  mov     esi, eax
0x18000ad51  call    cs:__imp_RpcRevertToSelf
0x18000ad58  nop     dword ptr [rax+rax+00h]
0x18000ad5d  mov     r14d, eax
0x18000ad60  test    esi, esi
0x18000ad62  js      loc_18000AE81
0x18000ad68  xor     esi, esi
0x18000ad6a  test    eax, eax
0x18000ad6c  jnz     loc_18000AE33
0x18000ad72  mov     rbx, [rbp+4Fh+ProcessHandle]
0x18000ad76  mov     rdi, [rbp+4Fh+Handle]
0x18000ad7a  mov     [rbp+4Fh+ProcessHandle], rsi
0x18000ad7e  mov     [rbp+4Fh+Handle], rsi
0x18000ad82  mov     rcx, [rbp+4Fh+TokenHandle]; Handle
0x18000ad86  test    rcx, rcx
0x18000ad89  jz      short loc_18000AD9B
0x18000ad8b  call    cs:__imp_NtClose
0x18000ad92  nop     dword ptr [rax+rax+00h]
0x18000ad97  mov     [rbp+4Fh+TokenHandle], rsi
0x18000ad9b  mov     rcx, [rbp+4Fh+ProcessHandle]; Handle
0x18000ad9f  test    rcx, rcx
0x18000ada2  jnz     loc_18000AE96
0x18000ada8  mov     esi, r14d
0x18000adab  test    r14d, r14d
0x18000adae  js      short loc_18000ADC8
0x18000adb0  mov     r8, [rbp+4Fh+arg_20]
0x18000adb4  mov     rdx, r12
0x18000adb7  mov     rcx, r13
0x18000adba  call    cs:__imp_GetProcessesFromJitvSilos
0x18000adc1  nop     dword ptr [rax+rax+00h]
0x18000adc6  mov     esi, eax
0x18000adc8  test    esi, esi
0x18000adca  js      loc_18000AEA7
0x18000add0  movzx   eax, si
0x18000add3  lea     rdx, [rbp+4Fh+Reply]; Reply
0x18000add7  mov     ecx, 0
0x18000addc  test    esi, esi
0x18000adde  cmovns  eax, ecx
0x18000ade1  mov     rcx, r15; pAsync
0x18000ade4  mov     [rbp+4Fh+Reply], eax
0x18000ade7  call    cs:__imp_RpcAsyncCompleteCall
0x18000adee  nop     dword ptr [rax+rax+00h]
0x18000adf3  lea     rax, [rdi+1]
0x18000adf7  test    rax, 0FFFFFFFFFFFFFFFEh
0x18000adfd  jnz     loc_18000AEE2
0x18000ae03  lea     rax, [rbx-1]
0x18000ae07  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000ae0b  jbe     loc_18000AEF6
0x18000ae11  lea     r11, [rsp+0C0h+var_20]
0x18000ae19  mov     rbx, [r11+30h]
0x18000ae1d  mov     rsi, [r11+38h]
0x18000ae21  mov     rdi, [r11+40h]
0x18000ae25  mov     rsp, r11
0x18000ae28  pop     r15
0x18000ae2a  pop     r14
0x18000ae2c  pop     r13
0x18000ae2e  pop     r12
0x18000ae30  pop     rbp
0x18000ae31  retn
0x18000ae33  mov     rcx, [rbp+4Fh+Handle]; Handle
0x18000ae37  test    rcx, rcx
0x18000ae3a  jz      loc_18000AD82
0x18000ae40  call    cs:__imp_NtClose
0x18000ae47  nop     dword ptr [rax+rax+00h]
0x18000ae4c  jmp     loc_18000AD7E
0x18000ae51  mov     rcx, [rcx+10h]
0x18000ae55  lea     r8, WPP_e8c8bde4cfdd31ad7ca53050940b7a3e_Traceguids
0x18000ae5c  mov     edx, 20h ; ' '
0x18000ae61  mov     r9, r13
0x18000ae64  call    WPP_SF_S
0x18000ae69  jmp     loc_18000AC3D
0x18000ae6e  mov     ecx, eax; Status
0x18000ae70  call    cs:__imp_RtlNtStatusToDosErrorNoTeb
0x18000ae77  nop     dword ptr [rax+rax+00h]
0x18000ae7c  mov     r14d, eax
0x18000ae7f  jmp     short loc_18000AE33
0x18000ae81  mov     ecx, esi; Status
0x18000ae83  call    cs:__imp_RtlNtStatusToDosErrorNoTeb
0x18000ae8a  nop     dword ptr [rax+rax+00h]
0x18000ae8f  mov     r14d, eax
0x18000ae92  xor     esi, esi
0x18000ae94  jmp     short loc_18000AE33
0x18000ae96  call    cs:__imp_NtClose
0x18000ae9d  nop     dword ptr [rax+rax+00h]
0x18000aea2  jmp     loc_18000ADA8
0x18000aea7  mov     rcx, cs:WPP_GLOBAL_Control
0x18000aeae  lea     rax, WPP_GLOBAL_Control
0x18000aeb5  cmp     rcx, rax
0x18000aeb8  jz      loc_18000ADD0
0x18000aebe  test    byte ptr [rcx+1Ch], 1
0x18000aec2  jz      loc_18000ADD0
0x18000aec8  mov     rcx, [rcx+10h]
0x18000aecc  mov     edx, 21h ; '!'
0x18000aed1  mov     r9, r13
0x18000aed4  mov     [rsp+0C0h+TokenType], esi
0x18000aed8  call    WPP_SF_SD
0x18000aedd  jmp     loc_18000ADD0
0x18000aee2  mov     rcx, rdi; hObject
0x18000aee5  call    cs:__imp_CloseHandle
0x18000aeec  nop     dword ptr [rax+rax+00h]
0x18000aef1  jmp     loc_18000AE03
0x18000aef6  mov     rcx, rbx; hObject
0x18000aef9  call    cs:__imp_CloseHandle
0x18000af00  nop     dword ptr [rax+rax+00h]
0x18000af05  jmp     loc_18000AE11
```
