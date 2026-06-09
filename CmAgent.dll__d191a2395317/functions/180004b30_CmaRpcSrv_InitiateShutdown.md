# CmaRpcSrv_InitiateShutdown

- ea: `0x180004b30`
- end: `0x180004c28`
- name: `CmaRpcSrv_InitiateShutdown`
- size: `248`
- prototype: `RPC_STATUS __fastcall(PRPC_ASYNC_STATE pAsync)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callees

- `0x1800045e4`
- `0x180004b30`
- `0x180007b4c`
- `0x18000a768`
- `0x180024d60`

## import_xrefs

- `RPCRT4!RpcAsyncCompleteCall` at `0x180004c0f`
- `RPCRT4!RpcAsyncCompleteCall` at `0x180004c0f`
- `ntdll!RtlAcquirePrivilege` at `0x180004b5d`
- `ntdll!RtlAcquirePrivilege` at `0x180004b5d`
- `api-ms-win-core-shutdown-l1-1-1!InitiateShutdownW` at `0x180004bbc`
- `api-ms-win-core-shutdown-l1-1-1!InitiateShutdownW` at `0x180004bbc`

## string_xrefs

- `0x180004b75`: `onecore\base\gendrv\silos\csl\lib\CslPrivilege.h`
- `0x180004b94`: `onecore\base\gendrv\silos\clem\agent\core\lib\core.cpp`
- `0x180004be2`: `onecore\base\gendrv\silos\clem\agent\core\lib\core.cpp`

## pseudocode

```c
RPC_STATUS __fastcall CmaRpcSrv_InitiateShutdown(PRPC_ASYNC_STATE pAsync)
{
  NTSTATUS v2; // eax
  int v3; // eax
  int v4; // ebx
  DWORD v5; // eax
  DWORD dwReason; // [rsp+20h] [rbp-28h]
  DWORD dwReasona; // [rsp+20h] [rbp-28h]
  DWORD dwReasonb; // [rsp+20h] [rbp-28h]
  PVOID v10[3]; // [rsp+30h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  ULONG v12; // [rsp+60h] [rbp+18h] BYREF
  int Reply; // [rsp+68h] [rbp+20h] BYREF

  v10[0] = 0;
  v12 = 19;
  v2 = RtlAcquirePrivilege(&v12, 1u, 0, v10);
  if ( v2 >= 0
    || (v3 = wil::details::in1diag3::Return_NtStatus(
               retaddr,
               (void *)0x52,
               (unsigned int)"onecore\\base\\gendrv\\silos\\csl\\lib\\CslPrivilege.h",
               (const char *)(unsigned int)v2,
               dwReason),
        v4 = v3,
        v3 >= 0) )
  {
    v5 = InitiateShutdownW(0, 0, 0, 0x800Bu, 0x80000000);
    if ( v5 )
    {
      if ( v5 == 1115 )
        v4 = -2147023781;
      else
        v4 = wil::details::in1diag3::Return_Win32(
               retaddr,
               (void *)0x3F1,
               (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\agent\\core\\lib\\core.cpp",
               (const char *)v5,
               dwReasonb);
    }
    else
    {
      v4 = 0;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3DA,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\agent\\core\\lib\\core.cpp",
      (const char *)(unsigned int)v3,
      dwReasona);
  }
  Csl::AcquiredPrivileges::~AcquiredPrivileges((Csl::AcquiredPrivileges *)v10);
  Reply = v4;
  return RpcAsyncCompleteCall(pAsync, &Reply);
}

```

## disassembly

```asm
0x180004b30  mov     rax, rsp
0x180004b33  mov     [rax+8], rbx
0x180004b37  push    rdi
0x180004b38  sub     rsp, 40h
0x180004b3c  mov     rdi, rcx
0x180004b3f  mov     qword ptr [rax-18h], 0
0x180004b47  mov     dword ptr [rax+18h], 13h
0x180004b4e  lea     r9, [rax-18h]; ReturnedState
0x180004b52  xor     r8d, r8d; Flags
0x180004b55  lea     edx, [r8+1]; NumPriv
0x180004b59  lea     rcx, [rax+18h]; Privilege
0x180004b5d  call    cs:__imp_RtlAcquirePrivilege
0x180004b64  nop     dword ptr [rax+rax+00h]
0x180004b69  test    eax, eax
0x180004b6b  jns     short loc_180004BA7
0x180004b6d  mov     rcx, [rsp+48h]; this
0x180004b72  mov     r9d, eax; char *
0x180004b75  lea     r8, aOnecoreBaseGen; "onecore\\base\\gendrv\\silos\\csl\\lib"...
0x180004b7c  mov     edx, 52h ; 'R'; void *
0x180004b81  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x180004b86  mov     ebx, eax
0x180004b88  test    eax, eax
0x180004b8a  jns     short loc_180004BA7
0x180004b8c  mov     rcx, [rsp+48h]; this
0x180004b91  mov     r9d, eax; char *
0x180004b94  lea     r8, aOnecoreBaseGen_8; "onecore\\base\\gendrv\\silos\\clem\\age"...
0x180004b9b  mov     edx, 3DAh; void *
0x180004ba0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004ba5  jmp     short loc_180004BF9
0x180004ba7  mov     [rsp+48h+dwReason], 80000000h; unsigned int
0x180004baf  mov     r9d, 800Bh; dwShutdownFlags
0x180004bb5  xor     r8d, r8d; dwGracePeriod
0x180004bb8  xor     edx, edx; lpMessage
0x180004bba  xor     ecx, ecx; lpMachineName
0x180004bbc  call    cs:__imp_InitiateShutdownW
0x180004bc3  nop     dword ptr [rax+rax+00h]
0x180004bc8  test    eax, eax
0x180004bca  jz      short loc_180004BF7
0x180004bcc  cmp     eax, 45Bh
0x180004bd1  jnz     short loc_180004BDA
0x180004bd3  mov     ebx, 8007045Bh
0x180004bd8  jmp     short loc_180004BF9
0x180004bda  mov     rcx, [rsp+48h]; this
0x180004bdf  mov     r9d, eax; char *
0x180004be2  lea     r8, aOnecoreBaseGen_8; "onecore\\base\\gendrv\\silos\\clem\\age"...
0x180004be9  mov     edx, 3F1h; void *
0x180004bee  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180004bf3  mov     ebx, eax
0x180004bf5  jmp     short loc_180004BF9
0x180004bf7  xor     ebx, ebx
0x180004bf9  lea     rcx, [rsp+48h+var_18]; this
0x180004bfe  call    ??1AcquiredPrivileges@Csl@@QEAA@XZ; Csl::AcquiredPrivileges::~AcquiredPrivileges(void)
0x180004c03  mov     [rsp+48h+Reply], ebx
0x180004c07  lea     rdx, [rsp+48h+Reply]; Reply
0x180004c0c  mov     rcx, rdi; pAsync
0x180004c0f  call    cs:__imp_RpcAsyncCompleteCall
0x180004c16  nop     dword ptr [rax+rax+00h]
0x180004c1b  nop
0x180004c1c  mov     rbx, [rsp+48h+arg_0]
0x180004c21  add     rsp, 40h
0x180004c25  pop     rdi
0x180004c26  retn
```
