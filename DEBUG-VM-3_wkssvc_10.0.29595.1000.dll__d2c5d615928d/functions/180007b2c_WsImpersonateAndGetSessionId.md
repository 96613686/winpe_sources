# WsImpersonateAndGetSessionId

- ea: `0x180007b2c`
- end: `0x180007c6e`
- name: `WsImpersonateAndGetSessionId`
- size: `322`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x180008484`

## callees

- `0x180007b2c`
- `0x180007c80`
- `0x18002ecc0`

## import_xrefs

- `ntdll!NtOpenThreadToken` at `0x180007bba`
- `ntdll!NtOpenThreadToken` at `0x180007bba`
- `ntdll!NtClose` at `0x180007c03`
- `ntdll!NtClose` at `0x180007c03`
- `ntdll!NtQueryInformationToken` at `0x180007bed`
- `ntdll!NtQueryInformationToken` at `0x180007bed`
- `RPCRT4!RpcImpersonateClient` at `0x180007b52`
- `RPCRT4!RpcImpersonateClient` at `0x180007b52`
- `RPCRT4!RpcRevertToSelf` at `0x180007c13`
- `RPCRT4!RpcRevertToSelf` at `0x180007c13`

## pseudocode

```c
__int64 __fastcall WsImpersonateAndGetSessionId(_DWORD *a1)
{
  RPC_STATUS v2; // eax
  int v3; // r8d
  int v5; // ebx
  unsigned int v6; // esi
  int v7; // ebx
  RPC_STATUS v8; // eax
  int v9; // r8d
  int TokenInformation; // [rsp+58h] [rbp+10h] BYREF
  ULONG ReturnLength; // [rsp+60h] [rbp+18h] BYREF
  void *TokenHandle; // [rsp+68h] [rbp+20h] BYREF

  TokenHandle = 0;
  TokenInformation = 0;
  ReturnLength = 0;
  v2 = RpcImpersonateClient(0);
  if ( v2 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      if ( *((_BYTE *)WPP_GLOBAL_Control + 25) )
        WPP_SF_sdL(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, v3, (unsigned int)"unknown", 0, v2);
    }
    return 5;
  }
  else
  {
    v5 = NtOpenThreadToken((HANDLE)0xFFFFFFFFFFFFFFFELL, 8u, 1u, &TokenHandle);
    v6 = NetpNtStatusToApiStatus(v5);
    if ( v5 >= 0 )
    {
      v7 = NtQueryInformationToken(TokenHandle, TokenSessionId, &TokenInformation, 4u, &ReturnLength);
      v6 = NetpNtStatusToApiStatus(v7);
      NtClose(TokenHandle);
      if ( v7 >= 0 )
        *a1 = TokenInformation;
    }
    v8 = RpcRevertToSelf();
    if ( v8 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) )
      {
        WPP_SF_sdL(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, v9, (unsigned int)"unknown", 0, v8);
      }
      __fastfail(7u);
    }
    return v6;
  }
}

```

## disassembly

```asm
0x180007b2c  push    rbx
0x180007b2e  push    rsi
0x180007b2f  push    rdi
0x180007b30  sub     rsp, 30h
0x180007b34  mov     rdi, rcx
0x180007b37  mov     [rsp+48h+TokenHandle], 0
0x180007b40  xor     ecx, ecx; BindingHandle
0x180007b42  mov     [rsp+48h+TokenInformation], 0
0x180007b4a  mov     [rsp+48h+arg_10], 0
0x180007b52  call    cs:__imp_RpcImpersonateClient
0x180007b58  test    eax, eax
0x180007b5a  jz      short loc_180007BA6
0x180007b5c  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x180007b63  lea     rdx, WPP_GLOBAL_Control
0x180007b6a  cmp     rcx, rdx
0x180007b6d  jz      short loc_180007B9C
0x180007b6f  test    byte ptr [rcx+1Ch], 4
0x180007b73  jz      short loc_180007B9C
0x180007b75  cmp     byte ptr [rcx+19h], 1
0x180007b79  jb      short loc_180007B9C
0x180007b7b  mov     rcx, [rcx+10h]
0x180007b7f  lea     r9, aUnknown; "unknown"
0x180007b86  mov     [rsp+48h+var_20], eax
0x180007b8a  mov     edx, 0Ah
0x180007b8f  mov     dword ptr [rsp+48h+ReturnLength], 0
0x180007b97  call    WPP_SF_sdL
0x180007b9c  mov     eax, 5
0x180007ba1  jmp     loc_180007C66
0x180007ba6  lea     r9, [rsp+48h+TokenHandle]; TokenHandle
0x180007bab  mov     r8b, 1; OpenAsSelf
0x180007bae  mov     edx, 8; DesiredAccess
0x180007bb3  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x180007bba  call    cs:__imp_NtOpenThreadToken
0x180007bc0  mov     ecx, eax; Status
0x180007bc2  mov     ebx, eax
0x180007bc4  call    NetpNtStatusToApiStatus
0x180007bc9  mov     esi, eax
0x180007bcb  test    ebx, ebx
0x180007bcd  js      short loc_180007C13
0x180007bcf  mov     rcx, [rsp+48h+TokenHandle]; TokenHandle
0x180007bd4  lea     rax, [rsp+48h+arg_10]
0x180007bd9  mov     r9d, 4; TokenInformationLength
0x180007bdf  mov     [rsp+48h+ReturnLength], rax; ReturnLength
0x180007be4  lea     r8, [rsp+48h+TokenInformation]; TokenInformation
0x180007be9  lea     edx, [r9+8]; TokenInformationClass
0x180007bed  call    cs:__imp_NtQueryInformationToken
0x180007bf3  mov     ecx, eax; Status
0x180007bf5  mov     ebx, eax
0x180007bf7  call    NetpNtStatusToApiStatus
0x180007bfc  mov     rcx, [rsp+48h+TokenHandle]; Handle
0x180007c01  mov     esi, eax
0x180007c03  call    cs:__imp_NtClose
0x180007c09  test    ebx, ebx
0x180007c0b  js      short loc_180007C13
0x180007c0d  mov     eax, [rsp+48h+TokenInformation]
0x180007c11  mov     [rdi], eax
0x180007c13  call    cs:__imp_RpcRevertToSelf
0x180007c19  test    eax, eax
0x180007c1b  jz      short loc_180007C64
0x180007c1d  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x180007c24  lea     rdx, WPP_GLOBAL_Control
0x180007c2b  cmp     rcx, rdx
0x180007c2e  jz      short loc_180007C5D
0x180007c30  test    byte ptr [rcx+1Ch], 4
0x180007c34  jz      short loc_180007C5D
0x180007c36  cmp     byte ptr [rcx+19h], 1
0x180007c3a  jb      short loc_180007C5D
0x180007c3c  mov     rcx, [rcx+10h]
0x180007c40  lea     r9, aUnknown; "unknown"
0x180007c47  mov     [rsp+48h+var_20], eax
0x180007c4b  mov     edx, 0Bh
0x180007c50  mov     dword ptr [rsp+48h+ReturnLength], 0
0x180007c58  call    WPP_SF_sdL
0x180007c5d  mov     ecx, 7
0x180007c62  int     29h; Win8: RtlFailFast(ecx)
0x180007c64  mov     eax, esi
0x180007c66  add     rsp, 30h
0x180007c6a  pop     rdi
0x180007c6b  pop     rsi
0x180007c6c  pop     rbx
0x180007c6d  retn
```
