# _WluiiRpcSecurityCallback

- ea: `0x1800463b0`
- end: `0x18004659d`
- name: `_WluiiRpcSecurityCallback`
- size: `493`
- prototype: `__int64 __fastcall(RPC_IF_HANDLE InterfaceUuid, void *Context)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x1800463b0`
- `0x18006c000`
- `0x18009b790`

## import_xrefs

- `ntdll!NtOpenProcessToken` at `0x180046503`
- `ntdll!NtOpenProcessToken` at `0x180046503`
- `ntdll!NtOpenProcess` at `0x1800464ea`
- `ntdll!NtOpenProcess` at `0x1800464ea`
- `ntdll!NtClose` at `0x180046564`
- `ntdll!NtClose` at `0x180046574`
- `ntdll!NtClose` at `0x18009c36e`
- `ntdll!NtClose` at `0x18009c37e`
- `ntdll!NtClose` at `0x180046564`
- `ntdll!NtClose` at `0x180046574`
- `ntdll!NtClose` at `0x18009c36e`
- `ntdll!NtClose` at `0x18009c37e`
- `ntdll!NtQueryInformationToken` at `0x18004652b`
- `ntdll!NtQueryInformationToken` at `0x18004652b`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x180046491`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x180046491`
- `RPCRT4!I_RpcBindingIsClientLocal` at `0x180046471`
- `RPCRT4!I_RpcBindingIsClientLocal` at `0x180046471`
- `RPCRT4!RpcBindingInqAuthClientW` at `0x180046445`
- `RPCRT4!RpcBindingInqAuthClientW` at `0x180046445`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall WluiiRpcSecurityCallback(RPC_IF_HANDLE InterfaceUuid, void *Context)
{
  unsigned int v3; // ebx
  unsigned int AuthnLevel; // [rsp+30h] [rbp-B8h] BYREF
  unsigned int AuthnSvc; // [rsp+34h] [rbp-B4h] BYREF
  unsigned int ClientLocalFlag; // [rsp+38h] [rbp-B0h] BYREF
  unsigned int Pid; // [rsp+3Ch] [rbp-ACh] BYREF
  void *TokenHandle; // [rsp+40h] [rbp-A8h] BYREF
  void *ProcessHandle; // [rsp+48h] [rbp-A0h] BYREF
  ULONG ReturnLength; // [rsp+50h] [rbp-98h] BYREF
  __int64 Buf1; // [rsp+58h] [rbp-90h] BYREF
  _CLIENT_ID ClientId; // [rsp+60h] [rbp-88h] BYREF
  _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+70h] [rbp-78h] BYREF
  _BYTE TokenInformation[48]; // [rsp+A0h] [rbp-48h] BYREF
  __int64 v16; // [rsp+D0h] [rbp-18h]

  ClientLocalFlag = 0;
  TokenHandle = 0;
  ProcessHandle = 0;
  Buf1 = 999;
  memset(TokenInformation, 0, sizeof(TokenInformation));
  v16 = 0;
  ReturnLength = 0;
  Pid = 0;
  memset(&ObjectAttributes, 0, 44);
  ClientId = 0;
  AuthnLevel = 0;
  AuthnSvc = 0;
  if ( RpcBindingInqAuthClientW(Context, 0, 0, &AuthnLevel, &AuthnSvc, 0)
    || AuthnLevel < 6
    || AuthnSvc != 10
    || I_RpcBindingIsClientLocal(Context, &ClientLocalFlag)
    || !ClientLocalFlag
    || I_RpcBindingInqLocalClientPID(Context, &Pid)
    || (ObjectAttributes.Length = 48,
        memset(&ObjectAttributes.RootDirectory, 0, 20),
        *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0,
        ClientId.UniqueProcess = (HANDLE)(int)Pid,
        ClientId.UniqueThread = 0,
        NtOpenProcess(&ProcessHandle, 0x1000u, &ObjectAttributes, &ClientId) < 0)
    || NtOpenProcessToken(ProcessHandle, 8u, &TokenHandle) < 0
    || NtQueryInformationToken(TokenHandle, TokenStatistics, TokenInformation, 0x38u, &ReturnLength) < 0 )
  {
    v3 = 5;
  }
  else
  {
    v3 = memcmp_0(&Buf1, &TokenInformation[8], 8u) != 0 ? 5 : 0;
  }
  if ( TokenHandle )
    NtClose(TokenHandle);
  if ( ProcessHandle )
    NtClose(ProcessHandle);
  return v3;
}

```

## disassembly

```asm
0x1800463b0  mov     r11, rsp
0x1800463b3  mov     [r11+8], rbx
0x1800463b7  push    rdi
0x1800463b8  sub     rsp, 0E0h
0x1800463bf  mov     rax, cs:__security_cookie
0x1800463c6  xor     rax, rsp
0x1800463c9  mov     [rsp+0E8h+var_10], rax
0x1800463d1  mov     rbx, rdx
0x1800463d4  xor     edi, edi
0x1800463d6  mov     [rsp+0E8h+ClientLocalFlag], edi
0x1800463da  mov     [rsp+0E8h+TokenHandle], rdi
0x1800463df  mov     [rsp+0E8h+ProcessHandle], rdi
0x1800463e4  mov     [rsp+0E8h+Buf1], 3E7h
0x1800463ed  xorps   xmm0, xmm0
0x1800463f0  xor     eax, eax
0x1800463f2  movups  xmmword ptr [r11-48h], xmm0
0x1800463f7  movups  xmmword ptr [r11-38h], xmm0
0x1800463fc  movups  xmmword ptr [r11-28h], xmm0
0x180046401  mov     [r11-18h], rax
0x180046405  mov     [rsp+0E8h+ReturnLength], edi
0x180046409  mov     [rsp+0E8h+Pid], edi
0x18004640d  movups  xmmword ptr [rsp+0E8h+ObjectAttributes.Length], xmm0
0x180046412  movups  xmmword ptr [r11-68h], xmm0
0x180046417  movups  xmmword ptr [r11-5Ch], xmm0
0x18004641c  movups  xmmword ptr [rsp+0E8h+ClientId.UniqueProcess], xmm0
0x180046421  mov     [rsp+0E8h+AuthnLevel], edi
0x180046425  mov     [rsp+0E8h+var_B4], edi
0x180046429  mov     [rsp+0E8h+AuthzSvc], rdi; AuthzSvc
0x18004642e  lea     rax, [rsp+0E8h+var_B4]
0x180046433  mov     [rsp+0E8h+AuthnSvc], rax; AuthnSvc
0x180046438  lea     r9, [rsp+0E8h+AuthnLevel]; AuthnLevel
0x18004643d  xor     r8d, r8d; ServerPrincName
0x180046440  xor     edx, edx; Privs
0x180046442  mov     rcx, rbx; ClientBinding
0x180046445  call    cs:__imp_RpcBindingInqAuthClientW
0x18004644b  test    eax, eax
0x18004644d  jnz     loc_180046555
0x180046453  cmp     [rsp+0E8h+AuthnLevel], 6
0x180046458  jb      loc_180046555
0x18004645e  cmp     [rsp+0E8h+var_B4], 0Ah
0x180046463  jnz     loc_180046555
0x180046469  lea     rdx, [rsp+0E8h+ClientLocalFlag]; ClientLocalFlag
0x18004646e  mov     rcx, rbx; BindingHandle
0x180046471  call    cs:__imp_I_RpcBindingIsClientLocal
0x180046477  test    eax, eax
0x180046479  jnz     loc_180046555
0x18004647f  cmp     [rsp+0E8h+ClientLocalFlag], edi
0x180046483  jz      loc_180046555
0x180046489  lea     rdx, [rsp+0E8h+Pid]; Pid
0x18004648e  mov     rcx, rbx; Binding
0x180046491  call    cs:__imp_I_RpcBindingInqLocalClientPID
0x180046497  test    eax, eax
0x180046499  jnz     loc_180046555
0x18004649f  mov     [rsp+0E8h+ObjectAttributes.Length], 30h ; '0'
0x1800464a7  mov     [rsp+0E8h+ObjectAttributes.RootDirectory], rdi
0x1800464ac  mov     [rsp+0E8h+ObjectAttributes.Attributes], edi
0x1800464b3  mov     [rsp+0E8h+ObjectAttributes.ObjectName], rdi
0x1800464bb  xorps   xmm0, xmm0
0x1800464be  movdqu  xmmword ptr [rsp+0E8h+ObjectAttributes.SecurityDescriptor], xmm0
0x1800464c7  movsxd  rax, [rsp+0E8h+Pid]
0x1800464cc  mov     [rsp+0E8h+ClientId.UniqueProcess], rax
0x1800464d1  mov     [rsp+0E8h+ClientId.UniqueThread], rdi
0x1800464d6  lea     r9, [rsp+0E8h+ClientId]; ClientId
0x1800464db  lea     r8, [rsp+0E8h+ObjectAttributes]; ObjectAttributes
0x1800464e0  mov     edx, 1000h; DesiredAccess
0x1800464e5  lea     rcx, [rsp+0E8h+ProcessHandle]; ProcessHandle
0x1800464ea  call    cs:__imp_NtOpenProcess
0x1800464f0  test    eax, eax
0x1800464f2  js      short loc_180046555
0x1800464f4  lea     r8, [rsp+0E8h+TokenHandle]; TokenHandle
0x1800464f9  lea     ebx, [rdi+8]
0x1800464fc  mov     edx, ebx; DesiredAccess
0x1800464fe  mov     rcx, [rsp+0E8h+ProcessHandle]; ProcessHandle
0x180046503  call    cs:__imp_NtOpenProcessToken
0x180046509  test    eax, eax
0x18004650b  js      short loc_180046555
0x18004650d  lea     rax, [rsp+0E8h+ReturnLength]
0x180046512  mov     [rsp+0E8h+AuthnSvc], rax; ReturnLength
0x180046517  lea     r9d, [rdi+38h]; TokenInformationLength
0x18004651b  lea     r8, [rsp+0E8h+TokenInformation]; TokenInformation
0x180046523  lea     edx, [rdi+0Ah]; TokenInformationClass
0x180046526  mov     rcx, [rsp+0E8h+TokenHandle]; TokenHandle
0x18004652b  call    cs:__imp_NtQueryInformationToken
0x180046531  test    eax, eax
0x180046533  js      short loc_180046555
0x180046535  mov     r8d, ebx; Size
0x180046538  lea     rdx, [rsp+0E8h+Buf2]; Buf2
0x180046540  lea     rcx, [rsp+0E8h+Buf1]; Buf1
0x180046545  call    memcmp_0
0x18004654a  neg     eax
0x18004654c  sbb     ecx, ecx
0x18004654e  lea     ebx, [rdi+5]
0x180046551  and     ebx, ecx
0x180046553  jmp     short loc_18004655A
0x180046555  mov     ebx, 5
0x18004655a  mov     rcx, [rsp+0E8h+TokenHandle]; Handle
0x18004655f  test    rcx, rcx
0x180046562  jz      short loc_18004656A
0x180046564  call    cs:__imp_NtClose
0x18004656a  mov     rcx, [rsp+0E8h+ProcessHandle]; Handle
0x18004656f  test    rcx, rcx
0x180046572  jz      short loc_18004657A
0x180046574  call    cs:__imp_NtClose
0x18004657a  mov     eax, ebx
0x18004657c  mov     rcx, [rsp+0E8h+var_10]
0x180046584  xor     rcx, rsp; StackCookie
0x180046587  call    __security_check_cookie
0x18004658c  mov     rbx, [rsp+0E8h+arg_0]
0x180046594  add     rsp, 0E0h
0x18004659b  pop     rdi
0x18004659c  retn
0x18009c35c  push    rbp
0x18009c35e  sub     rsp, 30h
0x18009c362  mov     rbp, rdx
0x18009c365  mov     rcx, [rbp+40h]; Handle
0x18009c369  test    rcx, rcx
0x18009c36c  jz      short loc_18009C375
0x18009c36e  call    cs:__imp_NtClose
0x18009c374  nop
0x18009c375  mov     rcx, [rbp+48h]; Handle
0x18009c379  test    rcx, rcx
0x18009c37c  jz      short loc_18009C385
0x18009c37e  call    cs:__imp_NtClose
0x18009c384  nop
0x18009c385  add     rsp, 30h
0x18009c389  pop     rbp
0x18009c38a  retn
```
