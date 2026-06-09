# RpcSecurityCallback(void * *,void *)

- ea: `0x180141240`
- end: `0x18014133d`
- name: `?RpcSecurityCallback@@YAJPEAPEAXPEAX@Z`
- size: `253`
- prototype: `__int64 __fastcall(void **, void *)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180141240`
- `0x180144882`
- `0x1801448c0`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x180141311`
- `KERNEL32!CloseHandle` at `0x180141311`
- `KERNEL32!GetCurrentThread` at `0x1801412d3`
- `KERNEL32!GetCurrentThread` at `0x1801412d3`
- `ADVAPI32!OpenThreadToken` at `0x1801412ea`
- `ADVAPI32!OpenThreadToken` at `0x1801412ea`
- `RPCRT4!RpcImpersonateClient` at `0x1801412c9`
- `RPCRT4!RpcImpersonateClient` at `0x1801412c9`
- `RPCRT4!RpcServerInqCallAttributesW` at `0x1801412ab`
- `RPCRT4!RpcServerInqCallAttributesW` at `0x1801412ab`
- `RPCRT4!RpcRevertToSelf` at `0x1801412f7`
- `RPCRT4!RpcRevertToSelf` at `0x1801412ff`
- `RPCRT4!RpcRevertToSelf` at `0x1801412f7`
- `RPCRT4!RpcRevertToSelf` at `0x1801412ff`
- `RPCRT4!I_RpcBindingInqTransportType` at `0x180141283`
- `RPCRT4!I_RpcBindingInqTransportType` at `0x180141283`

## pseudocode

```c
__int64 __fastcall RpcSecurityCallback(void **a1, void *a2)
{
  HANDLE CurrentThread; // rax
  RPC_STATUS v3; // ebx
  unsigned int Type; // [rsp+20h] [rbp-A8h] BYREF
  void *TokenHandle; // [rsp+28h] [rbp-A0h] BYREF
  _DWORD RpcCallAttributes[10]; // [rsp+40h] [rbp-88h] BYREF
  int v8; // [rsp+68h] [rbp-60h]
  int v9; // [rsp+6Ch] [rbp-5Ch]

  Type = 0;
  TokenHandle = 0;
  memset_0(RpcCallAttributes, 0, 0x70u);
  if ( I_RpcBindingInqTransportType(0, &Type) )
    return 5;
  if ( Type != 4 )
    return 5;
  RpcCallAttributes[0] = 2;
  if ( RpcServerInqCallAttributesW(0, RpcCallAttributes) || (v8 & 6) != 6 || !v9 || RpcImpersonateClient(0) )
    return 5;
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 8u, 1, &TokenHandle) )
  {
    v3 = RpcRevertToSelf();
  }
  else
  {
    v3 = 5;
    RpcRevertToSelf();
  }
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  if ( v3 )
    return 5;
  else
    return 0;
}

```

## disassembly

```asm
0x180141240  push    rbx
0x180141242  sub     rsp, 0C0h
0x180141249  mov     rax, cs:__security_cookie
0x180141250  xor     rax, rsp
0x180141253  mov     [rsp+0C8h+var_18], rax
0x18014125b  xor     edx, edx; Val
0x18014125d  mov     [rsp+0C8h+Type], 0
0x180141265  lea     rcx, [rsp+0C8h+RpcCallAttributes]; void *
0x18014126a  mov     [rsp+0C8h+TokenHandle], 0
0x180141273  lea     r8d, [rdx+70h]; Size
0x180141277  call    memset_0
0x18014127c  lea     rdx, [rsp+0C8h+Type]; Type
0x180141281  xor     ecx, ecx; Binding
0x180141283  call    cs:__imp_I_RpcBindingInqTransportType
0x180141289  test    eax, eax
0x18014128b  jnz     loc_18014131F
0x180141291  cmp     [rsp+0C8h+Type], 4
0x180141296  jnz     loc_18014131F
0x18014129c  lea     rdx, [rsp+0C8h+RpcCallAttributes]; RpcCallAttributes
0x1801412a1  mov     [rsp+0C8h+RpcCallAttributes], 2
0x1801412a9  xor     ecx, ecx; ClientBinding
0x1801412ab  call    cs:__imp_RpcServerInqCallAttributesW
0x1801412b1  test    eax, eax
0x1801412b3  jnz     short loc_18014131F
0x1801412b5  mov     eax, [rsp+0C8h+var_60]
0x1801412b9  and     eax, 6
0x1801412bc  cmp     al, 6
0x1801412be  jnz     short loc_18014131F
0x1801412c0  cmp     [rsp+0C8h+var_5C], 0
0x1801412c5  jz      short loc_18014131F
0x1801412c7  xor     ecx, ecx; BindingHandle
0x1801412c9  call    cs:__imp_RpcImpersonateClient
0x1801412cf  test    eax, eax
0x1801412d1  jnz     short loc_18014131F
0x1801412d3  call    cs:__imp_GetCurrentThread
0x1801412d9  mov     edx, 8; DesiredAccess
0x1801412de  lea     r9, [rsp+0C8h+TokenHandle]; TokenHandle
0x1801412e3  mov     rcx, rax; ThreadHandle
0x1801412e6  lea     r8d, [rdx-7]; OpenAsSelf
0x1801412ea  call    cs:__imp_OpenThreadToken
0x1801412f0  test    eax, eax
0x1801412f2  jnz     short loc_1801412FF
0x1801412f4  lea     ebx, [rax+5]
0x1801412f7  call    cs:__imp_RpcRevertToSelf
0x1801412fd  jmp     short loc_180141307
0x1801412ff  call    cs:__imp_RpcRevertToSelf
0x180141305  mov     ebx, eax
0x180141307  mov     rcx, [rsp+0C8h+TokenHandle]; hObject
0x18014130c  test    rcx, rcx
0x18014130f  jz      short loc_180141317
0x180141311  call    cs:__imp_CloseHandle
0x180141317  test    ebx, ebx
0x180141319  jnz     short loc_18014131F
0x18014131b  xor     eax, eax
0x18014131d  jmp     short loc_180141324
0x18014131f  mov     eax, 5
0x180141324  mov     rcx, [rsp+0C8h+var_18]
0x18014132c  xor     rcx, rsp; StackCookie
0x18014132f  call    __security_check_cookie
0x180141334  add     rsp, 0C0h
0x18014133b  pop     rbx
0x18014133c  retn
```
