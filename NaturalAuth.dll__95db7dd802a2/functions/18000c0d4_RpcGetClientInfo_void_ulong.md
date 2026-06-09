# RpcGetClientInfo(void *,ulong *)

- ea: `0x18000c0d4`
- end: `0x18000c26d`
- name: `?RpcGetClientInfo@@YAJPEAXPEAK@Z`
- size: `409`
- prototype: `__int64 __fastcall(void *, unsigned int *)`
- caller_count: `4`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x18000cde0`
- `0x18000ce70`
- `0x18000d090`
- `0x18000d110`

## callees

- `0x18000a7f8`
- `0x18000c0d4`

## import_xrefs

- `ntdll!NtQueryInformationToken` at `0x18000c1c6`
- `ntdll!NtQueryInformationToken` at `0x18000c1c6`
- `ntdll!NtClose` at `0x18000c211`
- `ntdll!NtClose` at `0x18000c211`
- `ntdll!NtOpenThreadToken` at `0x18000c17f`
- `ntdll!NtOpenThreadToken` at `0x18000c17f`
- `ntdll!RtlNtStatusToDosError` at `0x18000c14a`
- `ntdll!RtlNtStatusToDosError` at `0x18000c14a`
- `RPCRT4!I_RpcMapWin32Status` at `0x18000c108`
- `RPCRT4!I_RpcMapWin32Status` at `0x18000c224`
- `RPCRT4!I_RpcMapWin32Status` at `0x18000c108`
- `RPCRT4!I_RpcMapWin32Status` at `0x18000c224`
- `RPCRT4!RpcRevertToSelf` at `0x18000c21c`
- `RPCRT4!RpcRevertToSelf` at `0x18000c21c`
- `RPCRT4!RpcImpersonateClient` at `0x18000c100`
- `RPCRT4!RpcImpersonateClient` at `0x18000c100`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall RpcGetClientInfo(void *a1, unsigned int *a2)
{
  RPC_STATUS v3; // eax
  int v4; // ebx
  char v5; // bp
  _QWORD *v6; // rcx
  __int64 v7; // rdx
  NTSTATUS v8; // ecx
  signed int v9; // eax
  unsigned int v10; // ebx
  NTSTATUS v11; // eax
  NTSTATUS v12; // esi
  RPC_STATUS v13; // eax
  int v14; // eax
  void *TokenHandle; // [rsp+30h] [rbp-28h] BYREF
  unsigned int TokenInformation; // [rsp+70h] [rbp+18h] BYREF
  ULONG ReturnLength; // [rsp+78h] [rbp+20h] BYREF

  TokenHandle = 0;
  TokenInformation = -1;
  ReturnLength = 0;
  v3 = RpcImpersonateClient(a1);
  v4 = I_RpcMapWin32Status(v3);
  if ( v4 < 0 )
  {
    v5 = 0;
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_6;
    v7 = 26;
LABEL_5:
    WPP_SF_d(v6[2], v7, &WPP_e2b6b4cf14243e9ce41376c4a3f62423_Traceguids, (unsigned int)v4);
LABEL_6:
    v8 = v4;
    goto LABEL_7;
  }
  v5 = 1;
  v4 = NtOpenThreadToken((HANDLE)0xFFFFFFFFFFFFFFFELL, 8u, 1u, &TokenHandle);
  if ( v4 < 0 )
  {
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_6;
    v7 = 27;
    goto LABEL_5;
  }
  v10 = 0;
  if ( !a2 )
    goto LABEL_20;
  v11 = NtQueryInformationToken(TokenHandle, TokenSessionId, &TokenInformation, 4u, &ReturnLength);
  v12 = v11;
  if ( v11 >= 0 )
  {
    *a2 = TokenInformation;
    goto LABEL_20;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      28,
      &WPP_e2b6b4cf14243e9ce41376c4a3f62423_Traceguids,
      (unsigned int)v11);
  v8 = v12;
LABEL_7:
  v9 = RtlNtStatusToDosError(v8);
  v10 = v9;
  if ( v9 > 0 )
    v10 = (unsigned __int16)v9 | 0x80070000;
LABEL_20:
  if ( TokenHandle )
    NtClose(TokenHandle);
  if ( v5 )
  {
    v13 = RpcRevertToSelf();
    v14 = I_RpcMapWin32Status(v13);
    if ( v14 < 0 && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        29,
        &WPP_e2b6b4cf14243e9ce41376c4a3f62423_Traceguids,
        (unsigned int)v14);
  }
  return v10;
}

```

## disassembly

```asm
0x18000c0d4  mov     rax, rsp
0x18000c0d7  mov     [rax+8], rbx
0x18000c0db  mov     [rax+10h], rbp
0x18000c0df  push    rsi
0x18000c0e0  push    rdi
0x18000c0e1  push    r14
0x18000c0e3  sub     rsp, 40h
0x18000c0e7  mov     rdi, rdx
0x18000c0ea  mov     qword ptr [rax-28h], 0
0x18000c0f2  mov     dword ptr [rax+18h], 0FFFFFFFFh
0x18000c0f9  mov     dword ptr [rax+20h], 0
0x18000c100  call    cs:__imp_RpcImpersonateClient
0x18000c106  mov     ecx, eax; Status
0x18000c108  call    cs:__imp_I_RpcMapWin32Status
0x18000c10e  lea     r14, WPP_GLOBAL_Control
0x18000c115  mov     ebx, eax
0x18000c117  test    eax, eax
0x18000c119  jns     short loc_18000C168
0x18000c11b  xor     bpl, bpl
0x18000c11e  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c125  cmp     rcx, r14
0x18000c128  jz      short loc_18000C148
0x18000c12a  test    byte ptr [rcx+1Ch], 1
0x18000c12e  jz      short loc_18000C148
0x18000c130  mov     edx, 1Ah
0x18000c135  mov     rcx, [rcx+10h]
0x18000c139  lea     r8, WPP_e2b6b4cf14243e9ce41376c4a3f62423_Traceguids
0x18000c140  mov     r9d, ebx
0x18000c143  call    WPP_SF_d
0x18000c148  mov     ecx, ebx; Status
0x18000c14a  call    cs:__imp_RtlNtStatusToDosError
0x18000c150  mov     ebx, eax
0x18000c152  test    eax, eax
0x18000c154  jle     loc_18000C207
0x18000c15a  movzx   ebx, ax
0x18000c15d  or      ebx, 80070000h
0x18000c163  jmp     loc_18000C207
0x18000c168  mov     bpl, 1
0x18000c16b  lea     r9, [rsp+58h+TokenHandle]; TokenHandle
0x18000c170  mov     r8b, bpl; OpenAsSelf
0x18000c173  mov     edx, 8; DesiredAccess
0x18000c178  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x18000c17f  call    cs:__imp_NtOpenThreadToken
0x18000c185  mov     ebx, eax
0x18000c187  test    eax, eax
0x18000c189  jns     short loc_18000C1A4
0x18000c18b  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c192  cmp     rcx, r14
0x18000c195  jz      short loc_18000C148
0x18000c197  test    [rcx+1Ch], bpl
0x18000c19b  jz      short loc_18000C148
0x18000c19d  mov     edx, 1Bh
0x18000c1a2  jmp     short loc_18000C135
0x18000c1a4  xor     ebx, ebx
0x18000c1a6  test    rdi, rdi
0x18000c1a9  jz      short loc_18000C207
0x18000c1ab  mov     rcx, [rsp+58h+TokenHandle]; TokenHandle
0x18000c1b0  lea     rax, [rsp+58h+arg_18]
0x18000c1b5  lea     r9d, [rbx+4]; TokenInformationLength
0x18000c1b9  mov     [rsp+58h+ReturnLength], rax; ReturnLength
0x18000c1be  lea     r8, [rsp+58h+TokenInformation]; TokenInformation
0x18000c1c3  lea     edx, [rbx+0Ch]; TokenInformationClass
0x18000c1c6  call    cs:__imp_NtQueryInformationToken
0x18000c1cc  mov     esi, eax
0x18000c1ce  test    eax, eax
0x18000c1d0  jns     short loc_18000C201
0x18000c1d2  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c1d9  cmp     rcx, r14
0x18000c1dc  jz      short loc_18000C1FA
0x18000c1de  test    [rcx+1Ch], bpl
0x18000c1e2  jz      short loc_18000C1FA
0x18000c1e4  mov     rcx, [rcx+10h]
0x18000c1e8  lea     edx, [rbx+1Ch]
0x18000c1eb  mov     r9d, eax
0x18000c1ee  lea     r8, WPP_e2b6b4cf14243e9ce41376c4a3f62423_Traceguids
0x18000c1f5  call    WPP_SF_d
0x18000c1fa  mov     ecx, esi
0x18000c1fc  jmp     loc_18000C14A
0x18000c201  mov     eax, [rsp+58h+TokenInformation]
0x18000c205  mov     [rdi], eax
0x18000c207  mov     rcx, [rsp+58h+TokenHandle]; Handle
0x18000c20c  test    rcx, rcx
0x18000c20f  jz      short loc_18000C217
0x18000c211  call    cs:__imp_NtClose
0x18000c217  test    bpl, bpl
0x18000c21a  jz      short loc_18000C258
0x18000c21c  call    cs:__imp_RpcRevertToSelf
0x18000c222  mov     ecx, eax; Status
0x18000c224  call    cs:__imp_I_RpcMapWin32Status
0x18000c22a  test    eax, eax
0x18000c22c  jns     short loc_18000C258
0x18000c22e  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c235  cmp     rcx, r14
0x18000c238  jz      short loc_18000C258
0x18000c23a  test    byte ptr [rcx+1Ch], 1
0x18000c23e  jz      short loc_18000C258
0x18000c240  mov     rcx, [rcx+10h]
0x18000c244  lea     r8, WPP_e2b6b4cf14243e9ce41376c4a3f62423_Traceguids
0x18000c24b  mov     edx, 1Dh
0x18000c250  mov     r9d, eax
0x18000c253  call    WPP_SF_d
0x18000c258  mov     rbp, [rsp+58h+arg_8]
0x18000c25d  mov     eax, ebx
0x18000c25f  mov     rbx, [rsp+58h+arg_0]
0x18000c264  add     rsp, 40h
0x18000c268  pop     r14
0x18000c26a  pop     rdi
0x18000c26b  pop     rsi
0x18000c26c  retn
```
