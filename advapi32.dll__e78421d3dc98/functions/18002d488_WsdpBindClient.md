# WsdpBindClient

- ea: `0x18002d488`
- end: `0x18002d6b9`
- name: `WsdpBindClient`
- size: `561`
- prototype: `__int64 __fastcall(unsigned __int16 *, RPC_BINDING_HANDLE *Binding)`
- caller_count: `3`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18002d1e0`
- `0x18002d35c`
- `0x18004efbc`

## callees

- `0x180026000`
- `0x18002b8c0`
- `0x18002d488`
- `0x180065090`

## import_xrefs

- `KERNELBASE!LocalAlloc` at `0x18002d614`
- `KERNELBASE!LocalAlloc` at `0x18002d614`
- `KERNEL32!LocalFree` at `0x18002d65a`
- `KERNEL32!LocalFree` at `0x18002d6b1`
- `KERNEL32!LocalFree` at `0x1800655b5`
- `KERNEL32!LocalFree` at `0x18002d65a`
- `KERNEL32!LocalFree` at `0x18002d6b1`
- `KERNEL32!LocalFree` at `0x1800655b5`
- `RPCRT4!RpcStringFreeW` at `0x18002d679`
- `RPCRT4!RpcStringFreeW` at `0x1800655a5`
- `RPCRT4!RpcStringFreeW` at `0x18002d679`
- `RPCRT4!RpcStringFreeW` at `0x1800655a5`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x18002d513`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x18002d513`
- `RPCRT4!RpcStringBindingComposeW` at `0x18002d4f5`
- `RPCRT4!RpcStringBindingComposeW` at `0x18002d5ac`
- `RPCRT4!RpcStringBindingComposeW` at `0x18002d4f5`
- `RPCRT4!RpcStringBindingComposeW` at `0x18002d5ac`
- `RPCRT4!RpcBindingSetAuthInfoExW` at `0x18002d57c`
- `RPCRT4!RpcBindingSetAuthInfoExW` at `0x18002d57c`

## pseudocode

```c
__int64 __fastcall WsdpBindClient(unsigned __int16 *a1, RPC_BINDING_HANDLE *Binding)
{
  unsigned __int16 *v4; // rdi
  RPC_STATUS v5; // eax
  unsigned int v6; // r14d
  unsigned int v7; // ebx
  __int64 v8; // rax
  __int64 v9; // rcx
  size_t v10; // rbx
  wchar_t *v11; // rax
  RPC_WSTR String; // [rsp+40h] [rbp-78h] BYREF
  wchar_t *v14; // [rsp+48h] [rbp-70h]
  RPC_SECURITY_QOS SecurityQOS; // [rsp+50h] [rbp-68h] BYREF
  __int128 v16; // [rsp+60h] [rbp-58h]
  __int64 *v17; // [rsp+70h] [rbp-48h]
  wchar_t pszSrc[8]; // [rsp+78h] [rbp-40h] BYREF

  String = 0;
  v4 = 0;
  v14 = 0;
  if ( a1 && *a1 )
  {
    v5 = RpcStringBindingComposeW(
           (RPC_WSTR)L"765294BA-60BC-48B8-92E9-89FD77769D91",
           (RPC_WSTR)L"ncacn_ip_tcp",
           a1,
           0,
           0,
           &String);
    v6 = 9;
  }
  else
  {
    v5 = RpcStringBindingComposeW(0, (RPC_WSTR)L"ncalrpc", a1, (RPC_WSTR)L"WindowsShutdown", 0, &String);
    v6 = 10;
  }
  v7 = v5;
  if ( !v5 )
  {
    v7 = RpcBindingFromStringBindingW(String, Binding);
    if ( !v7 )
    {
      v16 = 0;
      *(_QWORD *)&SecurityQOS.Version = 3;
      SecurityQOS.IdentityTracking = 0;
      SecurityQOS.ImpersonationType = 3;
      v17 = qword_18009F7A0;
      if ( !a1 || !*a1 || v6 == 10 )
        goto LABEL_7;
      wcscpy(pszSrc, L"host/");
      v8 = -1;
      v9 = -1;
      do
        ++v9;
      while ( pszSrc[v9] );
      do
        ++v8;
      while ( a1[v8] );
      v10 = v9 + v8 + 1;
      v11 = (wchar_t *)LocalAlloc(0x40u, 2 * v10);
      v4 = v11;
      v14 = v11;
      if ( v11 )
      {
        if ( StringCchCopyW(v11, v10, pszSrc) >= 0 && (int)StringCchCatW(v4, v10, a1) >= 0 )
        {
          SecurityQOS.Capabilities |= 1u;
LABEL_7:
          v7 = RpcBindingSetAuthInfoExW(*Binding, v4, 6u, v6, 0, 0, &SecurityQOS);
          goto LABEL_20;
        }
        LocalFree(v4);
        v4 = 0;
        v14 = 0;
      }
      v7 = 1746;
    }
  }
LABEL_20:
  if ( String )
    RpcStringFreeW(&String);
  if ( v4 )
    LocalFree(v4);
  return v7;
}

```

## disassembly

```asm
0x18002d488  mov     [rsp+arg_10], rbx
0x18002d48d  push    rsi
0x18002d48e  push    rdi
0x18002d48f  push    r12
0x18002d491  push    r14
0x18002d493  push    r15
0x18002d495  sub     rsp, 90h
0x18002d49c  mov     rax, cs:__security_cookie
0x18002d4a3  xor     rax, rsp
0x18002d4a6  mov     [rsp+0B8h+var_30], rax
0x18002d4ae  mov     r15, rdx
0x18002d4b1  mov     rsi, rcx
0x18002d4b4  xor     r12d, r12d
0x18002d4b7  mov     [rsp+0B8h+String], r12
0x18002d4bc  mov     edi, r12d
0x18002d4bf  mov     [rsp+0B8h+var_70], r12
0x18002d4c4  test    rcx, rcx
0x18002d4c7  jz      short loc_18002D4D3
0x18002d4c9  cmp     r12w, [rcx]
0x18002d4cd  jnz     loc_18002D589
0x18002d4d3  lea     rax, [rsp+0B8h+String]
0x18002d4d8  mov     [rsp+0B8h+StringBinding], rax; StringBinding
0x18002d4dd  mov     [rsp+0B8h+Options], r12; Options
0x18002d4e2  lea     r9, aWindowsshutdow; "WindowsShutdown"
0x18002d4e9  mov     r8, rsi; NetworkAddr
0x18002d4ec  lea     rdx, aNcalrpc; "ncalrpc"
0x18002d4f3  xor     ecx, ecx; ObjUuid
0x18002d4f5  call    cs:__imp_RpcStringBindingComposeW
0x18002d4fb  mov     r14d, 0Ah
0x18002d501  mov     ebx, eax
0x18002d503  test    eax, eax
0x18002d505  jnz     loc_18002D66D
0x18002d50b  mov     rdx, r15; Binding
0x18002d50e  mov     rcx, [rsp+0B8h+String]; StringBinding
0x18002d513  call    cs:__imp_RpcBindingFromStringBindingW
0x18002d519  mov     ebx, eax
0x18002d51b  test    eax, eax
0x18002d51d  jnz     loc_18002D66D
0x18002d523  xorps   xmm0, xmm0
0x18002d526  xor     eax, eax
0x18002d528  movups  xmmword ptr [rsp+0B8h+var_68.Version], xmm0
0x18002d52d  movups  [rsp+0B8h+var_58], xmm0
0x18002d532  mov     [rsp+0B8h+var_48], rax
0x18002d537  lea     eax, [rbx+3]
0x18002d53a  mov     qword ptr [rsp+0B8h+var_68.Version], rax
0x18002d53f  mov     [rsp+0B8h+var_68.IdentityTracking], r12d
0x18002d544  mov     [rsp+0B8h+var_68.ImpersonationType], eax
0x18002d548  lea     rax, qword_18009F7A0
0x18002d54f  mov     [rsp+0B8h+var_48], rax
0x18002d554  test    rsi, rsi
0x18002d557  jnz     short loc_18002D5BD
0x18002d559  lea     rax, [rsp+0B8h+var_68]
0x18002d55e  mov     [rsp+0B8h+SecurityQOS], rax; SecurityQOS
0x18002d563  mov     dword ptr [rsp+0B8h+StringBinding], r12d; AuthzSvc
0x18002d568  mov     [rsp+0B8h+Options], r12; AuthIdentity
0x18002d56d  mov     r9d, r14d; AuthnSvc
0x18002d570  mov     r8d, 6; AuthnLevel
0x18002d576  mov     rdx, rdi; ServerPrincName
0x18002d579  mov     rcx, [r15]; Binding
0x18002d57c  call    cs:__imp_RpcBindingSetAuthInfoExW
0x18002d582  mov     ebx, eax
0x18002d584  jmp     loc_18002D66D
0x18002d589  lea     rax, [rsp+0B8h+String]
0x18002d58e  mov     [rsp+0B8h+StringBinding], rax; StringBinding
0x18002d593  mov     [rsp+0B8h+Options], r12; Options
0x18002d598  xor     r9d, r9d; Endpoint
0x18002d59b  mov     r8, rsi; NetworkAddr
0x18002d59e  lea     rdx, aNcacnIpTcp; "ncacn_ip_tcp"
0x18002d5a5  lea     rcx, ObjUuid; "765294BA-60BC-48B8-92E9-89FD77769D91"
0x18002d5ac  call    cs:__imp_RpcStringBindingComposeW
0x18002d5b2  mov     r14d, 9
0x18002d5b8  jmp     loc_18002D501
0x18002d5bd  cmp     [rsi], r12w
0x18002d5c1  jz      short loc_18002D559
0x18002d5c3  cmp     r14d, 0Ah
0x18002d5c7  jz      short loc_18002D559
0x18002d5c9  movsd   xmm0, qword ptr cs:aHost; "host/"
0x18002d5d1  movsd   qword ptr [rsp+0B8h+pszSrc], xmm0
0x18002d5d7  mov     eax, dword ptr cs:aHost+8; "/"
0x18002d5dd  mov     [rsp+0B8h+var_38], eax
0x18002d5e4  lea     rdx, [rsp+0B8h+pszSrc]
0x18002d5e9  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002d5ed  mov     rcx, rax
0x18002d5f0  inc     rcx
0x18002d5f3  cmp     [rdx+rcx*2], r12w
0x18002d5f8  jnz     short loc_18002D5F0
0x18002d5fa  inc     rax
0x18002d5fd  cmp     [rsi+rax*2], r12w
0x18002d602  jnz     short loc_18002D5FA
0x18002d604  lea     rbx, [rax+1]
0x18002d608  add     rbx, rcx
0x18002d60b  lea     rdx, [rbx+rbx]; uBytes
0x18002d60f  mov     ecx, 40h ; '@'; uFlags
0x18002d614  call    cs:__imp_LocalAlloc
0x18002d61a  mov     rdi, rax
0x18002d61d  mov     [rsp+0B8h+var_70], rax
0x18002d622  test    rax, rax
0x18002d625  jz      short loc_18002D668
0x18002d627  lea     r8, [rsp+0B8h+pszSrc]; pszSrc
0x18002d62c  mov     rdx, rbx; cchDest
0x18002d62f  mov     rcx, rax; pszDest
0x18002d632  call    StringCchCopyW
0x18002d637  test    eax, eax
0x18002d639  js      short loc_18002D657
0x18002d63b  mov     r8, rsi; unsigned __int16 *
0x18002d63e  mov     rdx, rbx; unsigned __int64
0x18002d641  mov     rcx, rdi; unsigned __int16 *
0x18002d644  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18002d649  test    eax, eax
0x18002d64b  js      short loc_18002D657
0x18002d64d  or      [rsp+0B8h+var_68.Capabilities], 1
0x18002d652  jmp     loc_18002D559
0x18002d657  mov     rcx, rdi; hMem
0x18002d65a  call    cs:__imp_LocalFree
0x18002d660  mov     rdi, r12
0x18002d663  mov     [rsp+0B8h+var_70], r12
0x18002d668  mov     ebx, 6D2h
0x18002d66d  cmp     [rsp+0B8h+String], r12
0x18002d672  jz      short loc_18002D67F
0x18002d674  lea     rcx, [rsp+0B8h+String]; String
0x18002d679  call    cs:__imp_RpcStringFreeW
0x18002d67f  test    rdi, rdi
0x18002d682  jnz     short loc_18002D6AE
0x18002d684  mov     eax, ebx
0x18002d686  mov     rcx, [rsp+0B8h+var_30]
0x18002d68e  xor     rcx, rsp; StackCookie
0x18002d691  call    __security_check_cookie
0x18002d696  mov     rbx, [rsp+0B8h+arg_10]
0x18002d69e  add     rsp, 90h
0x18002d6a5  pop     r15
0x18002d6a7  pop     r14
0x18002d6a9  pop     r12
0x18002d6ab  pop     rdi
0x18002d6ac  pop     rsi
0x18002d6ad  retn
0x18002d6ae  mov     rcx, rdi; hMem
0x18002d6b1  call    cs:__imp_LocalFree
0x18002d6b7  jmp     short loc_18002D684
0x180065591  push    rbp
0x180065593  sub     rsp, 40h
0x180065597  mov     rbp, rdx
0x18006559a  cmp     qword ptr [rbp+40h], 0
0x18006559f  jz      short loc_1800655AC
0x1800655a1  lea     rcx, [rbp+40h]; String
0x1800655a5  call    cs:__imp_RpcStringFreeW
0x1800655ab  nop
0x1800655ac  mov     rcx, [rbp+48h]; hMem
0x1800655b0  test    rcx, rcx
0x1800655b3  jz      short loc_1800655BC
0x1800655b5  call    cs:__imp_LocalFree
0x1800655bb  nop
0x1800655bc  add     rsp, 40h
0x1800655c0  pop     rbp
0x1800655c1  retn
```
