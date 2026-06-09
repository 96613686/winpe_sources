# WsdpBindClient

- ea: `0x18003011c`
- end: `0x18003037e`
- name: `WsdpBindClient`
- size: `610`
- prototype: `__int64 __fastcall(unsigned __int16 *, RPC_BINDING_HANDLE *Binding)`
- caller_count: `3`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18002fe34`
- `0x18002ffd0`
- `0x180055460`

## callees

- `0x180028bd4`
- `0x18002ec60`
- `0x18003011c`
- `0x1800720b0`

## import_xrefs

- `KERNELBASE!LocalAlloc` at `0x1800302c0`
- `KERNELBASE!LocalAlloc` at `0x1800302c0`
- `KERNEL32!LocalFree` at `0x18003030c`
- `KERNEL32!LocalFree` at `0x180030370`
- `KERNEL32!LocalFree` at `0x18007268f`
- `KERNEL32!LocalFree` at `0x18003030c`
- `KERNEL32!LocalFree` at `0x180030370`
- `KERNEL32!LocalFree` at `0x18007268f`
- `RPCRT4!RpcStringFreeW` at `0x180030331`
- `RPCRT4!RpcStringFreeW` at `0x180072679`
- `RPCRT4!RpcStringFreeW` at `0x180030331`
- `RPCRT4!RpcStringFreeW` at `0x180072679`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x1800301ad`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x1800301ad`
- `RPCRT4!RpcStringBindingComposeW` at `0x180030189`
- `RPCRT4!RpcStringBindingComposeW` at `0x180030252`
- `RPCRT4!RpcStringBindingComposeW` at `0x180030189`
- `RPCRT4!RpcStringBindingComposeW` at `0x180030252`
- `RPCRT4!RpcBindingSetAuthInfoExW` at `0x18003021c`
- `RPCRT4!RpcBindingSetAuthInfoExW` at `0x18003021c`

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
      v17 = qword_1800AE7A0;
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
0x18003011c  mov     [rsp+arg_10], rbx
0x180030121  push    rsi
0x180030122  push    rdi
0x180030123  push    r12
0x180030125  push    r14
0x180030127  push    r15
0x180030129  sub     rsp, 90h
0x180030130  mov     rax, cs:__security_cookie
0x180030137  xor     rax, rsp
0x18003013a  mov     [rsp+0B8h+var_30], rax
0x180030142  mov     r15, rdx
0x180030145  mov     rsi, rcx
0x180030148  xor     r12d, r12d
0x18003014b  mov     [rsp+0B8h+String], r12
0x180030150  mov     edi, r12d
0x180030153  mov     [rsp+0B8h+var_70], r12
0x180030158  test    rcx, rcx
0x18003015b  jz      short loc_180030167
0x18003015d  cmp     r12w, [rcx]
0x180030161  jnz     loc_18003022F
0x180030167  lea     rax, [rsp+0B8h+String]
0x18003016c  mov     [rsp+0B8h+StringBinding], rax; StringBinding
0x180030171  mov     [rsp+0B8h+Options], r12; Options
0x180030176  lea     r9, aWindowsshutdow; "WindowsShutdown"
0x18003017d  mov     r8, rsi; NetworkAddr
0x180030180  lea     rdx, aNcalrpc; "ncalrpc"
0x180030187  xor     ecx, ecx; ObjUuid
0x180030189  call    cs:__imp_RpcStringBindingComposeW
0x180030190  nop     dword ptr [rax+rax+00h]
0x180030195  mov     r14d, 0Ah
0x18003019b  mov     ebx, eax
0x18003019d  test    eax, eax
0x18003019f  jnz     loc_180030325
0x1800301a5  mov     rdx, r15; Binding
0x1800301a8  mov     rcx, [rsp+0B8h+String]; StringBinding
0x1800301ad  call    cs:__imp_RpcBindingFromStringBindingW
0x1800301b4  nop     dword ptr [rax+rax+00h]
0x1800301b9  mov     ebx, eax
0x1800301bb  test    eax, eax
0x1800301bd  jnz     loc_180030325
0x1800301c3  xorps   xmm0, xmm0
0x1800301c6  xor     eax, eax
0x1800301c8  movups  xmmword ptr [rsp+0B8h+var_68.Version], xmm0
0x1800301cd  movups  [rsp+0B8h+var_58], xmm0
0x1800301d2  mov     [rsp+0B8h+var_48], rax
0x1800301d7  lea     eax, [rbx+3]
0x1800301da  mov     qword ptr [rsp+0B8h+var_68.Version], rax
0x1800301df  mov     [rsp+0B8h+var_68.IdentityTracking], r12d
0x1800301e4  mov     [rsp+0B8h+var_68.ImpersonationType], eax
0x1800301e8  lea     rax, qword_1800AE7A0
0x1800301ef  mov     [rsp+0B8h+var_48], rax
0x1800301f4  test    rsi, rsi
0x1800301f7  jnz     short loc_180030269
0x1800301f9  lea     rax, [rsp+0B8h+var_68]
0x1800301fe  mov     [rsp+0B8h+SecurityQOS], rax; SecurityQOS
0x180030203  mov     dword ptr [rsp+0B8h+StringBinding], r12d; AuthzSvc
0x180030208  mov     [rsp+0B8h+Options], r12; AuthIdentity
0x18003020d  mov     r9d, r14d; AuthnSvc
0x180030210  mov     r8d, 6; AuthnLevel
0x180030216  mov     rdx, rdi; ServerPrincName
0x180030219  mov     rcx, [r15]; Binding
0x18003021c  call    cs:__imp_RpcBindingSetAuthInfoExW
0x180030223  nop     dword ptr [rax+rax+00h]
0x180030228  mov     ebx, eax
0x18003022a  jmp     loc_180030325
0x18003022f  lea     rax, [rsp+0B8h+String]
0x180030234  mov     [rsp+0B8h+StringBinding], rax; StringBinding
0x180030239  mov     [rsp+0B8h+Options], r12; Options
0x18003023e  xor     r9d, r9d; Endpoint
0x180030241  mov     r8, rsi; NetworkAddr
0x180030244  lea     rdx, aNcacnIpTcp; "ncacn_ip_tcp"
0x18003024b  lea     rcx, ObjUuid; "765294BA-60BC-48B8-92E9-89FD77769D91"
0x180030252  call    cs:__imp_RpcStringBindingComposeW
0x180030259  nop     dword ptr [rax+rax+00h]
0x18003025e  mov     r14d, 9
0x180030264  jmp     loc_18003019B
0x180030269  cmp     [rsi], r12w
0x18003026d  jz      short loc_1800301F9
0x18003026f  cmp     r14d, 0Ah
0x180030273  jz      short loc_1800301F9
0x180030275  movsd   xmm0, qword ptr cs:aHost; "host/"
0x18003027d  movsd   qword ptr [rsp+0B8h+pszSrc], xmm0
0x180030283  mov     eax, dword ptr cs:aHost+8; "/"
0x180030289  mov     [rsp+0B8h+var_38], eax
0x180030290  lea     rdx, [rsp+0B8h+pszSrc]
0x180030295  or      rax, 0FFFFFFFFFFFFFFFFh
0x180030299  mov     rcx, rax
0x18003029c  inc     rcx
0x18003029f  cmp     [rdx+rcx*2], r12w
0x1800302a4  jnz     short loc_18003029C
0x1800302a6  inc     rax
0x1800302a9  cmp     [rsi+rax*2], r12w
0x1800302ae  jnz     short loc_1800302A6
0x1800302b0  lea     rbx, [rax+1]
0x1800302b4  add     rbx, rcx
0x1800302b7  lea     rdx, [rbx+rbx]; uBytes
0x1800302bb  mov     ecx, 40h ; '@'; uFlags
0x1800302c0  call    cs:__imp_LocalAlloc
0x1800302c7  nop     dword ptr [rax+rax+00h]
0x1800302cc  mov     rdi, rax
0x1800302cf  mov     [rsp+0B8h+var_70], rax
0x1800302d4  test    rax, rax
0x1800302d7  jz      short loc_180030320
0x1800302d9  lea     r8, [rsp+0B8h+pszSrc]; pszSrc
0x1800302de  mov     rdx, rbx; cchDest
0x1800302e1  mov     rcx, rax; pszDest
0x1800302e4  call    StringCchCopyW
0x1800302e9  test    eax, eax
0x1800302eb  js      short loc_180030309
0x1800302ed  mov     r8, rsi; unsigned __int16 *
0x1800302f0  mov     rdx, rbx; unsigned __int64
0x1800302f3  mov     rcx, rdi; unsigned __int16 *
0x1800302f6  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800302fb  test    eax, eax
0x1800302fd  js      short loc_180030309
0x1800302ff  or      [rsp+0B8h+var_68.Capabilities], 1
0x180030304  jmp     loc_1800301F9
0x180030309  mov     rcx, rdi; hMem
0x18003030c  call    cs:__imp_LocalFree
0x180030313  nop     dword ptr [rax+rax+00h]
0x180030318  mov     rdi, r12
0x18003031b  mov     [rsp+0B8h+var_70], r12
0x180030320  mov     ebx, 6D2h
0x180030325  cmp     [rsp+0B8h+String], r12
0x18003032a  jz      short loc_18003033D
0x18003032c  lea     rcx, [rsp+0B8h+String]; String
0x180030331  call    cs:__imp_RpcStringFreeW
0x180030338  nop     dword ptr [rax+rax+00h]
0x18003033d  test    rdi, rdi
0x180030340  jnz     short loc_18003036D
0x180030342  mov     eax, ebx
0x180030344  mov     rcx, [rsp+0B8h+var_30]
0x18003034c  xor     rcx, rsp; StackCookie
0x18003034f  call    __security_check_cookie
0x180030354  mov     rbx, [rsp+0B8h+arg_10]
0x18003035c  add     rsp, 90h
0x180030363  pop     r15
0x180030365  pop     r14
0x180030367  pop     r12
0x180030369  pop     rdi
0x18003036a  pop     rsi
0x18003036b  retn
0x18003036d  mov     rcx, rdi; hMem
0x180030370  call    cs:__imp_LocalFree
0x180030377  nop     dword ptr [rax+rax+00h]
0x18003037c  jmp     short loc_180030342
0x180072665  push    rbp
0x180072667  sub     rsp, 40h
0x18007266b  mov     rbp, rdx
0x18007266e  cmp     qword ptr [rbp+40h], 0
0x180072673  jz      short loc_180072686
0x180072675  lea     rcx, [rbp+40h]; String
0x180072679  call    cs:__imp_RpcStringFreeW
0x180072680  nop     dword ptr [rax+rax+00h]
0x180072685  nop
0x180072686  mov     rcx, [rbp+48h]; hMem
0x18007268a  test    rcx, rcx
0x18007268d  jz      short loc_18007269C
0x18007268f  call    cs:__imp_LocalFree
0x180072696  nop     dword ptr [rax+rax+00h]
0x18007269b  nop
0x18007269c  add     rsp, 40h
0x1800726a0  pop     rbp
0x1800726a1  retn
```
