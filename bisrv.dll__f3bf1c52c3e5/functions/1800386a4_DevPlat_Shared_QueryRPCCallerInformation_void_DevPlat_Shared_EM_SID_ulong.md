# DevPlat::Shared::QueryRPCCallerInformation(void *,DevPlat::Shared::_EM_SID *,ulong *)

- ea: `0x1800386a4`
- end: `0x180038802`
- name: `?QueryRPCCallerInformation@Shared@DevPlat@@YAJPEAXPEAU_EM_SID@12@PEAK@Z`
- size: `350`
- prototype: `int(DevPlat::Shared *__hidden this, void *, struct DevPlat::Shared::_EM_SID *, unsigned int *)`
- caller_count: `4`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x180038530`
- `0x1800385e0`
- `0x18006a010`
- `0x18006a1f0`

## callees

- `0x1800386a4`
- `0x18009467a`
- `0x1800946a0`

## import_xrefs

- `ntdll!NtOpenThreadToken` at `0x1800386f8`
- `ntdll!NtOpenThreadToken` at `0x1800386f8`
- `ntdll!RtlValidSid` at `0x18003877b`
- `ntdll!RtlValidSid` at `0x18003877b`
- `ntdll!RtlCopySid` at `0x18003876c`
- `ntdll!RtlCopySid` at `0x18003876c`
- `ntdll!NtClose` at `0x1800387b8`
- `ntdll!NtClose` at `0x1800387b8`
- `ntdll!NtQueryInformationToken` at `0x18003874f`
- `ntdll!NtQueryInformationToken` at `0x1800387a3`
- `ntdll!NtQueryInformationToken` at `0x18003874f`
- `ntdll!NtQueryInformationToken` at `0x1800387a3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800386e2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800386e2`
- `RPCRT4!RpcRevertToSelf` at `0x1800387ad`
- `RPCRT4!RpcRevertToSelf` at `0x1800387ad`
- `RPCRT4!RpcImpersonateClient` at `0x1800386d4`
- `RPCRT4!RpcImpersonateClient` at `0x1800386d4`

## pseudocode

```c
__int64 __fastcall DevPlat::Shared::QueryRPCCallerInformation(
        DevPlat::Shared *this,
        void *a2,
        struct DevPlat::Shared::_EM_SID *a3,
        unsigned int *a4)
{
  HANDLE CurrentThread; // rax
  NTSTATUS v7; // ebx
  void *v8; // rsi
  unsigned int v9; // ebx
  NTSTATUS v10; // eax
  ULONG ReturnLength; // [rsp+30h] [rbp-88h] BYREF
  void *TokenHandle; // [rsp+38h] [rbp-80h] BYREF
  PSID TokenInformation[10]; // [rsp+40h] [rbp-78h] BYREF

  TokenHandle = 0;
  if ( RpcImpersonateClient(this) )
  {
    v9 = -805306367;
    goto LABEL_10;
  }
  CurrentThread = GetCurrentThread();
  v7 = NtOpenThreadToken(CurrentThread, 8u, 1u, &TokenHandle);
  if ( v7 < 0 )
    goto LABEL_11;
  v8 = TokenHandle;
  ReturnLength = 0;
  memset_0(TokenInformation, 0, 0x48u);
  if ( !v8 )
  {
    v9 = -2147024809;
    goto LABEL_10;
  }
  if ( a2 )
  {
    v7 = NtQueryInformationToken(v8, TokenUser, TokenInformation, 0x48u, &ReturnLength);
    if ( v7 < 0 )
      goto LABEL_11;
    v7 = RtlCopySid(0x44u, a2, TokenInformation[0]);
    if ( v7 < 0 )
      goto LABEL_11;
    if ( !RtlValidSid(a2) )
    {
      v9 = -805306248;
      goto LABEL_10;
    }
  }
  v9 = 0;
  if ( a3 )
  {
    v10 = NtQueryInformationToken(v8, TokenSessionId, a3, 4u, &ReturnLength);
    if ( v10 < 0 )
    {
      v7 = v10;
LABEL_11:
      v9 = v7 | 0x10000000;
    }
  }
LABEL_10:
  RpcRevertToSelf();
  NtClose(TokenHandle);
  return v9;
}

```

## disassembly

```asm
0x1800386a4  mov     [rsp+arg_18], rbx
0x1800386a9  push    rbp
0x1800386aa  push    rsi
0x1800386ab  push    rdi
0x1800386ac  sub     rsp, 0A0h
0x1800386b3  mov     rax, cs:__security_cookie
0x1800386ba  xor     rax, rsp
0x1800386bd  mov     [rsp+0B8h+var_28], rax
0x1800386c5  mov     rbp, r8
0x1800386c8  mov     [rsp+0B8h+TokenHandle], 0
0x1800386d1  mov     rdi, rdx
0x1800386d4  call    cs:__imp_RpcImpersonateClient
0x1800386da  test    eax, eax
0x1800386dc  jnz     loc_1800387E9
0x1800386e2  call    cs:__imp_GetCurrentThread
0x1800386e8  lea     r9, [rsp+0B8h+TokenHandle]; TokenHandle
0x1800386ed  mov     r8b, 1; OpenAsSelf
0x1800386f0  mov     rcx, rax; ThreadHandle
0x1800386f3  mov     edx, 8; DesiredAccess
0x1800386f8  call    cs:__imp_NtOpenThreadToken
0x1800386fe  mov     ebx, eax
0x180038700  test    eax, eax
0x180038702  js      loc_1800387E3
0x180038708  mov     rsi, [rsp+0B8h+TokenHandle]
0x18003870d  lea     rcx, [rsp+0B8h+TokenInformation]; void *
0x180038712  mov     ebx, 48h ; 'H'
0x180038717  mov     [rsp+0B8h+var_88], 0
0x18003871f  mov     r8d, ebx; Size
0x180038722  xor     edx, edx; Val
0x180038724  call    memset_0
0x180038729  test    rsi, rsi
0x18003872c  jz      loc_1800387F0
0x180038732  test    rdi, rdi
0x180038735  jz      short loc_180038785
0x180038737  lea     rax, [rsp+0B8h+var_88]
0x18003873c  mov     r9d, ebx; TokenInformationLength
0x18003873f  lea     r8, [rsp+0B8h+TokenInformation]; TokenInformation
0x180038744  mov     [rsp+0B8h+ReturnLength], rax; ReturnLength
0x180038749  lea     edx, [rbx-47h]; TokenInformationClass
0x18003874c  mov     rcx, rsi; TokenHandle
0x18003874f  call    cs:__imp_NtQueryInformationToken
0x180038755  mov     ebx, eax
0x180038757  test    eax, eax
0x180038759  js      loc_1800387E3
0x18003875f  mov     r8, [rsp+0B8h+TokenInformation]; SourceSid
0x180038764  mov     rdx, rdi; DestinationSid
0x180038767  mov     ecx, 44h ; 'D'; DestinationSidLength
0x18003876c  call    cs:__imp_RtlCopySid
0x180038772  mov     ebx, eax
0x180038774  test    eax, eax
0x180038776  js      short loc_1800387E3
0x180038778  mov     rcx, rdi; Sid
0x18003877b  call    cs:__imp_RtlValidSid
0x180038781  test    al, al
0x180038783  jz      short loc_1800387F7
0x180038785  xor     ebx, ebx
0x180038787  test    rbp, rbp
0x18003878a  jz      short loc_1800387AD
0x18003878c  lea     rax, [rsp+0B8h+var_88]
0x180038791  mov     r8, rbp; TokenInformation
0x180038794  lea     r9d, [rbx+4]; TokenInformationLength
0x180038798  mov     [rsp+0B8h+ReturnLength], rax; ReturnLength
0x18003879d  lea     edx, [rbx+0Ch]; TokenInformationClass
0x1800387a0  mov     rcx, rsi; TokenHandle
0x1800387a3  call    cs:__imp_NtQueryInformationToken
0x1800387a9  test    eax, eax
0x1800387ab  js      short loc_1800387FE
0x1800387ad  call    cs:__imp_RpcRevertToSelf
0x1800387b3  mov     rcx, [rsp+0B8h+TokenHandle]; Handle
0x1800387b8  call    cs:__imp_NtClose
0x1800387be  mov     eax, ebx
0x1800387c0  mov     rcx, [rsp+0B8h+var_28]
0x1800387c8  xor     rcx, rsp; StackCookie
0x1800387cb  call    __security_check_cookie
0x1800387d0  mov     rbx, [rsp+0B8h+arg_18]
0x1800387d8  add     rsp, 0A0h
0x1800387df  pop     rdi
0x1800387e0  pop     rsi
0x1800387e1  pop     rbp
0x1800387e2  retn
0x1800387e3  bts     ebx, 1Ch
0x1800387e7  jmp     short loc_1800387AD
0x1800387e9  mov     ebx, 0D0000001h
0x1800387ee  jmp     short loc_1800387AD
0x1800387f0  mov     ebx, 80070057h
0x1800387f5  jmp     short loc_1800387AD
0x1800387f7  mov     ebx, 0D0000078h
0x1800387fc  jmp     short loc_1800387AD
0x1800387fe  mov     ebx, eax
0x180038800  jmp     short loc_1800387E3
```
