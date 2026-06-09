# CWLIDBinding::Bind(void)

- ea: `0x180007150`
- end: `0x180007304`
- name: `?Bind@CWLIDBinding@@QEAAJXZ`
- size: `436`
- prototype: `__int64 __fastcall(CWLIDBinding *__hidden this)`
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1800066d4`
- `0x180006a78`

## callees

- `0x180001cb0`
- `0x1800070d8`
- `0x180007114`
- `0x180007150`

## import_xrefs

- `RPCRT4!RpcBindingSetAuthInfoExW` at `0x1800072b6`
- `RPCRT4!RpcBindingSetAuthInfoExW` at `0x1800072b6`
- `RPCRT4!RpcStringBindingComposeW` at `0x180007265`
- `RPCRT4!RpcStringBindingComposeW` at `0x180007265`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x180007288`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x180007288`

## string_xrefs

- `0x1800071be`: `Security=impersonation dynamic false`

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
0x180007150  push    rbp
0x180007152  push    rbx
0x180007153  push    rsi
0x180007154  push    rdi
0x180007155  lea     rbp, [rsp-28h]
0x18000715a  sub     rsp, 128h
0x180007161  mov     rax, cs:__security_cookie
0x180007168  xor     rax, rsp
0x18000716b  mov     [rbp+40h+var_30], rax
0x18000716f  xor     esi, esi
0x180007171  mov     [rbp+40h+var_80], 80040001h
0x180007178  xorps   xmm0, xmm0
0x18000717b  mov     [rsp+140h+var_E8], rsi
0x180007180  lea     rax, [rbp+40h+var_98]
0x180007184  mov     [rsp+140h+var_D8], rsi
0x180007189  movups  [rbp+40h+var_B8], xmm0
0x18000718d  mov     qword ptr [rbp+40h+var_B8+8], rax
0x180007191  lea     rdx, ProtSeq; "ncalrpc"
0x180007198  lea     rax, [rbp+40h+var_80]
0x18000719c  mov     [rsp+140h+var_E0], rsi
0x1800071a1  movups  [rbp+40h+var_A8], xmm0
0x1800071a5  mov     qword ptr [rbp+40h+var_A8+8], rax
0x1800071a9  mov     rdi, rcx
0x1800071ac  lea     rax, [rsp+140h+var_E8]
0x1800071b1  mov     [rsp+140h+Binding], rsi
0x1800071b6  mov     [rsp+140h+StringBinding], rax; StringBinding
0x1800071bb  xor     r9d, r9d; Endpoint
0x1800071be  lea     rax, Options; "Security=impersonation dynamic false"
0x1800071c5  mov     [rsp+140h+var_F0], rsi
0x1800071ca  xor     r8d, r8d; NetworkAddr
0x1800071cd  mov     [rsp+140h+Options], rax; Options
0x1800071d2  xor     ecx, ecx; ObjUuid
0x1800071d4  mov     [rsp+140h+var_F8], rsi
0x1800071d9  mov     [rbp+40h+var_7C], rsi
0x1800071dd  mov     [rbp+40h+var_74], esi
0x1800071e0  mov     [rbp+40h+var_70], 14h
0x1800071e7  mov     [rbp+40h+var_6C], 300002h
0x1800071ee  mov     [rbp+40h+var_68], 1
0x1800071f5  mov     [rbp+40h+var_64], 280000h
0x1800071fc  mov     [rbp+40h+var_60], 80000000h
0x180007203  mov     [rbp+40h+var_5C], 601h
0x18000720a  mov     [rbp+40h+var_58], 5000000h
0x180007211  mov     [rbp+40h+var_54], 50h ; 'P'
0x180007218  mov     [rbp+40h+var_50], 0AFFF0147h
0x18000721f  mov     [rbp+40h+var_4C], 863F8CDDh
0x180007226  mov     [rbp+40h+var_48], 0CB6E37BCh
0x18000722d  mov     [rbp+40h+var_44], 0A1B3151Ah
0x180007234  mov     [rbp+40h+var_40], 2E8CC86Bh
0x18000723b  mov     [rbp+40h+var_98], 101h
0x180007242  mov     [rbp+40h+var_94], 5000000h
0x180007249  mov     [rbp+40h+var_90], 12h
0x180007250  mov     dword ptr [rsp+140h+var_D0], 5
0x180007258  mov     dword ptr [rsp+140h+var_D0+4], 1
0x180007260  movups  xmmword ptr [rsp+140h+var_D0+8], xmm0
0x180007265  call    cs:__imp_RpcStringBindingComposeW
0x18000726b  mov     ebx, eax
0x18000726d  test    eax, eax
0x18000726f  jz      short loc_18000727E
0x180007271  jle     short loc_1800072D6
0x180007273  movzx   ebx, ax
0x180007276  or      ebx, 80070000h
0x18000727c  jmp     short loc_1800072D6
0x18000727e  mov     rcx, [rsp+140h+var_E8]; StringBinding
0x180007283  lea     rdx, [rsp+140h+Binding]; Binding
0x180007288  call    cs:__imp_RpcBindingFromStringBindingW
0x18000728e  mov     ebx, eax
0x180007290  test    eax, eax
0x180007292  jnz     short loc_180007271
0x180007294  mov     rcx, [rsp+140h+Binding]; Binding
0x180007299  lea     rax, [rsp+140h+var_D0]
0x18000729e  mov     [rsp+140h+SecurityQOS], rax; SecurityQOS
0x1800072a3  lea     r9d, [rbx+0Ah]; AuthnSvc
0x1800072a7  mov     dword ptr [rsp+140h+StringBinding], esi; AuthzSvc
0x1800072ab  lea     r8d, [rbx+6]; AuthnLevel
0x1800072af  xor     edx, edx; ServerPrincName
0x1800072b1  mov     [rsp+140h+Options], rsi; AuthIdentity
0x1800072b6  call    cs:__imp_RpcBindingSetAuthInfoExW
0x1800072bc  mov     ebx, eax
0x1800072be  test    eax, eax
0x1800072c0  jnz     short loc_180007271
0x1800072c2  mov     rcx, [rsp+140h+Binding]
0x1800072c7  mov     ebx, esi
0x1800072c9  mov     [rdi], rcx
0x1800072cc  mov     [rsp+140h+Binding], rsi
0x1800072d1  mov     [rsp+140h+var_F8], rsi
0x1800072d6  lea     rcx, [rsp+140h+Binding]
0x1800072db  call    ??1?$Auto@PEAXVRpcBindingHandleFunctor@@VDummyContext@@@@QEAA@XZ; Auto<void *,RpcBindingHandleFunctor,DummyContext>::~Auto<void *,RpcBindingHandleFunctor,DummyContext>(void)
0x1800072e0  lea     rcx, [rsp+140h+var_E8]
0x1800072e5  call    ??1?$Auto@PEAGVRpcWstrFunctor@@VDummyContext@@@@QEAA@XZ; Auto<ushort *,RpcWstrFunctor,DummyContext>::~Auto<ushort *,RpcWstrFunctor,DummyContext>(void)
0x1800072ea  mov     eax, ebx
0x1800072ec  mov     rcx, [rbp+40h+var_30]
0x1800072f0  xor     rcx, rsp; StackCookie
0x1800072f3  call    __security_check_cookie
0x1800072f8  add     rsp, 128h
0x1800072ff  pop     rdi
0x180007300  pop     rsi
0x180007301  pop     rbx
0x180007302  pop     rbp
0x180007303  retn
```
