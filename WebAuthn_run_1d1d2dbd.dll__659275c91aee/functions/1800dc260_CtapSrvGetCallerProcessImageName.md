# _CtapSrvGetCallerProcessImageName

- ea: `0x1800dc260`
- end: `0x1800dc3dc`
- name: `_CtapSrvGetCallerProcessImageName`
- size: `380`
- prototype: `__int64 __fastcall(RPC_BINDING_HANDLE BindingHandle)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation`

## callers

- `0x18000d640`
- `0x18001dfb8`

## callees

- `0x180007f90`
- `0x18002bbf4`
- `0x1800466ec`
- `0x1800dc260`
- `0x1800dc690`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800dc299`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800dc299`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800dc35c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800dc35c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800dc319`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800dc319`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1800dc2ed`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1800dc2ed`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x1800dc33d`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x1800dc33d`
- `RPCRT4!RpcImpersonateClient` at `0x1800dc2c7`
- `RPCRT4!RpcImpersonateClient` at `0x1800dc2c7`
- `RPCRT4!RpcRevertToSelfEx` at `0x1800dc36a`
- `RPCRT4!RpcRevertToSelfEx` at `0x1800dc36a`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x1800dc2aa`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x1800dc2aa`

## string_xrefs

- `0x1800dc2d3`: `Impersonate`
- `0x1800dc302`: `OpenProcess`

## pseudocode

```c
__int64 __fastcall CtapSrvGetCallerProcessImageName(RPC_BINDING_HANDLE BindingHandle, WCHAR **a2)
{
  WCHAR *v2; // rsi
  int v5; // r14d
  DWORD CurrentProcessId; // eax
  unsigned int NonzeroLastError; // ebx
  const char *v8; // rdi
  HANDLE v9; // r15
  WCHAR *v10; // rax
  RPC_STATUS v11; // eax
  unsigned int Pid; // [rsp+50h] [rbp+8h] BYREF
  DWORD dwSize; // [rsp+58h] [rbp+10h] BYREF

  v2 = 0;
  Pid = 0;
  dwSize = 1023;
  v5 = 1;
  if ( BindingHandle == (RPC_BINDING_HANDLE)1 )
  {
    v5 = 0;
    CurrentProcessId = GetCurrentProcessId();
    Pid = CurrentProcessId;
    goto LABEL_8;
  }
  NonzeroLastError = I_RpcBindingInqLocalClientPID(BindingHandle, &Pid);
  if ( NonzeroLastError )
  {
LABEL_23:
    v8 = "InqClientPID";
    goto LABEL_24;
  }
  if ( !Pid )
  {
    NonzeroLastError = -2147418113;
    goto LABEL_23;
  }
  NonzeroLastError = RpcImpersonateClient(BindingHandle);
  if ( NonzeroLastError )
  {
    v8 = "Impersonate";
    goto LABEL_24;
  }
  CurrentProcessId = Pid;
LABEL_8:
  v9 = OpenProcess(0x1000u, 0, CurrentProcessId);
  if ( v9 )
  {
    v8 = 0;
    v10 = (WCHAR *)LocalAlloc(0x40u, 2LL * (dwSize + 1));
    v2 = v10;
    if ( v10 )
    {
      if ( QueryFullProcessImageNameW(v9, 0, v10, &dwSize) )
      {
        NonzeroLastError = 0;
      }
      else
      {
        NonzeroLastError = _GetNonzeroLastError();
        v8 = "Query";
      }
    }
    else
    {
      NonzeroLastError = _GetNonzeroLastError();
    }
    CloseHandle(v9);
  }
  else
  {
    NonzeroLastError = _GetNonzeroLastError();
    v8 = "OpenProcess";
  }
  if ( v5 )
  {
    v11 = RpcRevertToSelfEx(BindingHandle);
    if ( v11 )
    {
      if ( !NonzeroLastError )
      {
        NonzeroLastError = v11;
        v8 = "Revert";
      }
      goto LABEL_24;
    }
  }
  if ( NonzeroLastError )
  {
LABEL_24:
    FidoFree(v2);
    v2 = 0;
  }
  CtapSrvLogStringEvent(L"ImageName", v2);
  *a2 = v2;
  CtapSrvLogError(NonzeroLastError, "_CtapSrvGetCallerProcessImageName", v8);
  return NonzeroLastError;
}

```

## disassembly

```asm
0x1800dc260  mov     rax, rsp
0x1800dc263  mov     [rax+18h], rbx
0x1800dc267  mov     [rax+20h], rbp
0x1800dc26b  push    rsi
0x1800dc26c  push    rdi
0x1800dc26d  push    r12
0x1800dc26f  push    r14
0x1800dc271  push    r15
0x1800dc273  sub     rsp, 20h
0x1800dc277  xor     esi, esi
0x1800dc279  mov     dword ptr [rax+8], 0
0x1800dc280  mov     r12, rdx
0x1800dc283  mov     dword ptr [rax+10h], 3FFh
0x1800dc28a  mov     rbp, rcx
0x1800dc28d  lea     r14d, [rsi+1]
0x1800dc291  cmp     rcx, r14
0x1800dc294  jnz     short loc_1800DC2A5
0x1800dc296  xor     r14d, r14d
0x1800dc299  call    cs:__imp_GetCurrentProcessId
0x1800dc29f  mov     [rsp+48h+Pid], eax
0x1800dc2a3  jmp     short loc_1800DC2E3
0x1800dc2a5  lea     rdx, [rsp+48h+Pid]; Pid
0x1800dc2aa  call    cs:__imp_I_RpcBindingInqLocalClientPID
0x1800dc2b0  mov     ebx, eax
0x1800dc2b2  test    eax, eax
0x1800dc2b4  jnz     loc_1800DC38E
0x1800dc2ba  cmp     [rsp+48h+Pid], esi
0x1800dc2be  jz      loc_1800DC389
0x1800dc2c4  mov     rcx, rbp; BindingHandle
0x1800dc2c7  call    cs:__imp_RpcImpersonateClient
0x1800dc2cd  mov     ebx, eax
0x1800dc2cf  test    eax, eax
0x1800dc2d1  jz      short loc_1800DC2DF
0x1800dc2d3  lea     rdi, aImpersonate; "Impersonate"
0x1800dc2da  jmp     loc_1800DC395
0x1800dc2df  mov     eax, [rsp+48h+Pid]
0x1800dc2e3  mov     r8d, eax; dwProcessId
0x1800dc2e6  xor     edx, edx; bInheritHandle
0x1800dc2e8  mov     ecx, 1000h; dwDesiredAccess
0x1800dc2ed  call    cs:__imp_OpenProcess
0x1800dc2f3  mov     r15, rax
0x1800dc2f6  test    rax, rax
0x1800dc2f9  jnz     short loc_1800DC30B
0x1800dc2fb  call    ?_GetNonzeroLastError@@YAKXZ; _GetNonzeroLastError(void)
0x1800dc300  mov     ebx, eax
0x1800dc302  lea     rdi, aOpenprocess; "OpenProcess"
0x1800dc309  jmp     short loc_1800DC362
0x1800dc30b  mov     edx, [rsp+48h+dwSize]
0x1800dc30f  xor     edi, edi
0x1800dc311  inc     edx
0x1800dc313  add     rdx, rdx; uBytes
0x1800dc316  lea     ecx, [rdi+40h]; uFlags
0x1800dc319  call    cs:__imp_LocalAlloc
0x1800dc31f  mov     rsi, rax
0x1800dc322  test    rax, rax
0x1800dc325  jnz     short loc_1800DC330
0x1800dc327  call    ?_GetNonzeroLastError@@YAKXZ; _GetNonzeroLastError(void)
0x1800dc32c  mov     ebx, eax
0x1800dc32e  jmp     short loc_1800DC359
0x1800dc330  lea     r9, [rsp+48h+dwSize]; lpdwSize
0x1800dc335  mov     r8, rax; lpExeName
0x1800dc338  xor     edx, edx; dwFlags
0x1800dc33a  mov     rcx, r15; hProcess
0x1800dc33d  call    cs:__imp_QueryFullProcessImageNameW
0x1800dc343  test    eax, eax
0x1800dc345  jnz     short loc_1800DC357
0x1800dc347  call    ?_GetNonzeroLastError@@YAKXZ; _GetNonzeroLastError(void)
0x1800dc34c  mov     ebx, eax
0x1800dc34e  lea     rdi, aQuery; "Query"
0x1800dc355  jmp     short loc_1800DC359
0x1800dc357  xor     ebx, ebx
0x1800dc359  mov     rcx, r15; hObject
0x1800dc35c  call    cs:__imp_CloseHandle
0x1800dc362  test    r14d, r14d
0x1800dc365  jz      short loc_1800DC383
0x1800dc367  mov     rcx, rbp; BindingHandle
0x1800dc36a  call    cs:__imp_RpcRevertToSelfEx
0x1800dc370  test    eax, eax
0x1800dc372  jz      short loc_1800DC383
0x1800dc374  test    ebx, ebx
0x1800dc376  jnz     short loc_1800DC395
0x1800dc378  mov     ebx, eax
0x1800dc37a  lea     rdi, aRevert; "Revert"
0x1800dc381  jmp     short loc_1800DC395
0x1800dc383  test    ebx, ebx
0x1800dc385  jz      short loc_1800DC39F
0x1800dc387  jmp     short loc_1800DC395
0x1800dc389  mov     ebx, 8000FFFFh
0x1800dc38e  lea     rdi, aInqclientpid; "InqClientPID"
0x1800dc395  mov     rcx, rsi; void *
0x1800dc398  call    ?FidoFree@@YAXPEAX@Z; FidoFree(void *)
0x1800dc39d  xor     esi, esi
0x1800dc39f  mov     rdx, rsi
0x1800dc3a2  lea     rcx, aImagename; "ImageName"
0x1800dc3a9  call    _CtapSrvLogStringEvent
0x1800dc3ae  mov     r8, rdi
0x1800dc3b1  mov     [r12], rsi
0x1800dc3b5  lea     rdx, aCtapsrvgetcall; "_CtapSrvGetCallerProcessImageName"
0x1800dc3bc  mov     ecx, ebx
0x1800dc3be  call    _CtapSrvLogError
0x1800dc3c3  mov     rbp, [rsp+48h+arg_18]
0x1800dc3c8  mov     eax, ebx
0x1800dc3ca  mov     rbx, [rsp+48h+arg_10]
0x1800dc3cf  add     rsp, 20h
0x1800dc3d3  pop     r15
0x1800dc3d5  pop     r14
0x1800dc3d7  pop     r12
0x1800dc3d9  pop     rdi
0x1800dc3da  pop     rsi
0x1800dc3db  retn
```
