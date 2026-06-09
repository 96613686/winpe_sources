# CWLIDBinding::Bind(void)

- ea: `0x1800231a4`
- end: `0x180023358`
- name: `?Bind@CWLIDBinding@@QEAAJXZ`
- size: `436`
- prototype: `__int64 __fastcall(CWLIDBinding *__hidden this)`
- caller_count: `19`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18001c9ac`
- `0x18001d028`
- `0x18001d3bc`
- `0x18001ddc0`
- `0x18001e4cc`
- `0x18001e838`
- `0x18001eba4`
- `0x18001f228`
- `0x18001f5e0`
- `0x18001f990`
- `0x18001fd34`
- `0x180020098`
- `0x180020404`
- `0x1800207ac`
- `0x180020b18`
- `0x180021514`
- `0x180021bd8`
- `0x1800228bc`
- `0x180022c40`

## callees

- `0x180003160`
- `0x18002312c`
- `0x180023168`
- `0x1800231a4`

## import_xrefs

- `RPCRT4!RpcStringBindingComposeW` at `0x1800232b9`
- `RPCRT4!RpcStringBindingComposeW` at `0x1800232b9`
- `RPCRT4!RpcBindingSetAuthInfoExW` at `0x18002330a`
- `RPCRT4!RpcBindingSetAuthInfoExW` at `0x18002330a`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x1800232dc`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x1800232dc`

## string_xrefs

- `0x180023212`: `Security=impersonation dynamic false`

## pseudocode

```c
__int64 __fastcall CWLIDBinding::Bind(CWLIDBinding *this)
{
  RPC_STATUS v2; // eax
  unsigned int v3; // ebx
  bool v4; // cc
  RPC_BINDING_HANDLE Binding; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v7; // [rsp+48h] [rbp-B8h]
  __int64 v8; // [rsp+50h] [rbp-B0h]
  RPC_WSTR StringBinding[3]; // [rsp+58h] [rbp-A8h] BYREF
  _BYTE SecurityQOS[24]; // [rsp+70h] [rbp-90h] BYREF
  __int64 v11; // [rsp+88h] [rbp-78h]
  _DWORD *v12; // [rsp+90h] [rbp-70h]
  __int64 v13; // [rsp+98h] [rbp-68h]
  int *v14; // [rsp+A0h] [rbp-60h]
  _DWORD v15[6]; // [rsp+A8h] [rbp-58h] BYREF
  int v16; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v17; // [rsp+C4h] [rbp-3Ch]
  int v18; // [rsp+CCh] [rbp-34h]
  int v19; // [rsp+D0h] [rbp-30h]
  int v20; // [rsp+D4h] [rbp-2Ch]
  int v21; // [rsp+D8h] [rbp-28h]
  int v22; // [rsp+DCh] [rbp-24h]
  unsigned int v23; // [rsp+E0h] [rbp-20h]
  int v24; // [rsp+E4h] [rbp-1Ch]
  int v25; // [rsp+E8h] [rbp-18h]
  int v26; // [rsp+ECh] [rbp-14h]
  int v27; // [rsp+F0h] [rbp-10h]
  int v28; // [rsp+F4h] [rbp-Ch]
  int v29; // [rsp+F8h] [rbp-8h]
  int v30; // [rsp+FCh] [rbp-4h]
  int v31; // [rsp+100h] [rbp+0h]

  v16 = -2147221503;
  memset(StringBinding, 0, sizeof(StringBinding));
  v11 = 0;
  v12 = v15;
  v13 = 0;
  v14 = &v16;
  Binding = 0;
  v8 = 0;
  v7 = 0;
  v17 = 0;
  v18 = 0;
  v19 = 20;
  v20 = 3145730;
  v21 = 1;
  v22 = 2621440;
  v23 = 0x80000000;
  v24 = 1537;
  v25 = 83886080;
  v26 = 80;
  v27 = -1342242489;
  v28 = -2042655523;
  v29 = -881969220;
  v30 = -1582099174;
  v31 = 780978283;
  v15[0] = 257;
  v15[1] = 83886080;
  v15[2] = 18;
  *(_DWORD *)SecurityQOS = 5;
  *(_DWORD *)&SecurityQOS[4] = 1;
  *(_OWORD *)&SecurityQOS[8] = 0;
  v2 = RpcStringBindingComposeW(
         0,
         (RPC_WSTR)L"ncalrpc",
         0,
         0,
         (RPC_WSTR)L"Security=impersonation dynamic false",
         StringBinding);
  v3 = v2;
  v4 = v2 <= 0;
  if ( v2
    || (v2 = RpcBindingFromStringBindingW(StringBinding[0], &Binding), v3 = v2, v4 = v2 <= 0, v2)
    || (v2 = RpcBindingSetAuthInfoExW(Binding, 0, 6u, 0xAu, 0, 0, (RPC_SECURITY_QOS *)SecurityQOS),
        v3 = v2,
        v4 = v2 <= 0,
        v2) )
  {
    if ( !v4 )
      v3 = (unsigned __int16)v2 | 0x80070000;
  }
  else
  {
    v3 = 0;
    *(_QWORD *)this = Binding;
    Binding = 0;
    v7 = 0;
  }
  Auto<void *,RpcBindingHandleFunctor,DummyContext>::~Auto<void *,RpcBindingHandleFunctor,DummyContext>(&Binding);
  Auto<unsigned short *,RpcWstrFunctor,DummyContext>::~Auto<unsigned short *,RpcWstrFunctor,DummyContext>(StringBinding);
  return v3;
}

```

## disassembly

```asm
0x1800231a4  push    rbp
0x1800231a6  push    rbx
0x1800231a7  push    rsi
0x1800231a8  push    rdi
0x1800231a9  lea     rbp, [rsp-28h]
0x1800231ae  sub     rsp, 128h
0x1800231b5  mov     rax, cs:__security_cookie
0x1800231bc  xor     rax, rsp
0x1800231bf  mov     [rbp+40h+var_30], rax
0x1800231c3  xor     esi, esi
0x1800231c5  mov     [rbp+40h+var_80], 80040001h
0x1800231cc  xorps   xmm0, xmm0
0x1800231cf  mov     [rsp+140h+var_E8], rsi
0x1800231d4  lea     rax, [rbp+40h+var_98]
0x1800231d8  mov     [rsp+140h+var_D8], rsi
0x1800231dd  movups  [rbp+40h+var_B8], xmm0
0x1800231e1  mov     qword ptr [rbp+40h+var_B8+8], rax
0x1800231e5  lea     rdx, ProtSeq; "ncalrpc"
0x1800231ec  lea     rax, [rbp+40h+var_80]
0x1800231f0  mov     [rsp+140h+var_E0], rsi
0x1800231f5  movups  [rbp+40h+var_A8], xmm0
0x1800231f9  mov     qword ptr [rbp+40h+var_A8+8], rax
0x1800231fd  mov     rdi, rcx
0x180023200  lea     rax, [rsp+140h+var_E8]
0x180023205  mov     [rsp+140h+Binding], rsi
0x18002320a  mov     [rsp+140h+StringBinding], rax; StringBinding
0x18002320f  xor     r9d, r9d; Endpoint
0x180023212  lea     rax, Options; "Security=impersonation dynamic false"
0x180023219  mov     [rsp+140h+var_F0], rsi
0x18002321e  xor     r8d, r8d; NetworkAddr
0x180023221  mov     [rsp+140h+Options], rax; Options
0x180023226  xor     ecx, ecx; ObjUuid
0x180023228  mov     [rsp+140h+var_F8], rsi
0x18002322d  mov     [rbp+40h+var_7C], rsi
0x180023231  mov     [rbp+40h+var_74], esi
0x180023234  mov     [rbp+40h+var_70], 14h
0x18002323b  mov     [rbp+40h+var_6C], 300002h
0x180023242  mov     [rbp+40h+var_68], 1
0x180023249  mov     [rbp+40h+var_64], 280000h
0x180023250  mov     [rbp+40h+var_60], 80000000h
0x180023257  mov     [rbp+40h+var_5C], 601h
0x18002325e  mov     [rbp+40h+var_58], 5000000h
0x180023265  mov     [rbp+40h+var_54], 50h ; 'P'
0x18002326c  mov     [rbp+40h+var_50], 0AFFF0147h
0x180023273  mov     [rbp+40h+var_4C], 863F8CDDh
0x18002327a  mov     [rbp+40h+var_48], 0CB6E37BCh
0x180023281  mov     [rbp+40h+var_44], 0A1B3151Ah
0x180023288  mov     [rbp+40h+var_40], 2E8CC86Bh
0x18002328f  mov     [rbp+40h+var_98], 101h
0x180023296  mov     [rbp+40h+var_94], 5000000h
0x18002329d  mov     [rbp+40h+var_90], 12h
0x1800232a4  mov     dword ptr [rsp+140h+var_D0], 5
0x1800232ac  mov     dword ptr [rsp+140h+var_D0+4], 1
0x1800232b4  movups  xmmword ptr [rsp+140h+var_D0+8], xmm0
0x1800232b9  call    cs:__imp_RpcStringBindingComposeW
0x1800232bf  mov     ebx, eax
0x1800232c1  test    eax, eax
0x1800232c3  jz      short loc_1800232D2
0x1800232c5  jle     short loc_18002332A
0x1800232c7  movzx   ebx, ax
0x1800232ca  or      ebx, 80070000h
0x1800232d0  jmp     short loc_18002332A
0x1800232d2  mov     rcx, [rsp+140h+var_E8]; StringBinding
0x1800232d7  lea     rdx, [rsp+140h+Binding]; Binding
0x1800232dc  call    cs:__imp_RpcBindingFromStringBindingW
0x1800232e2  mov     ebx, eax
0x1800232e4  test    eax, eax
0x1800232e6  jnz     short loc_1800232C5
0x1800232e8  mov     rcx, [rsp+140h+Binding]; Binding
0x1800232ed  lea     rax, [rsp+140h+var_D0]
0x1800232f2  mov     [rsp+140h+SecurityQOS], rax; SecurityQOS
0x1800232f7  lea     r9d, [rbx+0Ah]; AuthnSvc
0x1800232fb  mov     dword ptr [rsp+140h+StringBinding], esi; AuthzSvc
0x1800232ff  lea     r8d, [rbx+6]; AuthnLevel
0x180023303  xor     edx, edx; ServerPrincName
0x180023305  mov     [rsp+140h+Options], rsi; AuthIdentity
0x18002330a  call    cs:__imp_RpcBindingSetAuthInfoExW
0x180023310  mov     ebx, eax
0x180023312  test    eax, eax
0x180023314  jnz     short loc_1800232C5
0x180023316  mov     rcx, [rsp+140h+Binding]
0x18002331b  mov     ebx, esi
0x18002331d  mov     [rdi], rcx
0x180023320  mov     [rsp+140h+Binding], rsi
0x180023325  mov     [rsp+140h+var_F8], rsi
0x18002332a  lea     rcx, [rsp+140h+Binding]
0x18002332f  call    ??1?$Auto@PEAXVRpcBindingHandleFunctor@@VDummyContext@@@@QEAA@XZ; Auto<void *,RpcBindingHandleFunctor,DummyContext>::~Auto<void *,RpcBindingHandleFunctor,DummyContext>(void)
0x180023334  lea     rcx, [rsp+140h+var_E8]
0x180023339  call    ??1?$Auto@PEAGVRpcWstrFunctor@@VDummyContext@@@@QEAA@XZ; Auto<ushort *,RpcWstrFunctor,DummyContext>::~Auto<ushort *,RpcWstrFunctor,DummyContext>(void)
0x18002333e  mov     eax, ebx
0x180023340  mov     rcx, [rbp+40h+var_30]
0x180023344  xor     rcx, rsp; StackCookie
0x180023347  call    __security_check_cookie
0x18002334c  add     rsp, 128h
0x180023353  pop     rdi
0x180023354  pop     rsi
0x180023355  pop     rbx
0x180023356  pop     rbp
0x180023357  retn
```
