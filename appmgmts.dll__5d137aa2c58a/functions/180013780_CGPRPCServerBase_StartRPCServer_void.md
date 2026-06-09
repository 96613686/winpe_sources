# CGPRPCServerBase::StartRPCServer(void)

- ea: `0x180013780`
- end: `0x1800138bc`
- name: `?StartRPCServer@CGPRPCServerBase@@QEAAKXZ`
- size: `316`
- prototype: `__int64 __fastcall(CGPRPCServerBase *this)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800124bc`

## callees

- `0x180013780`

## import_xrefs

- `RPCRT4!RpcServerInterfaceGroupCreateW` at `0x18001386d`
- `RPCRT4!RpcServerInterfaceGroupCreateW` at `0x18001386d`
- `RPCRT4!UuidFromStringW` at `0x1800137c9`
- `RPCRT4!UuidFromStringW` at `0x1800137c9`
- `RPCRT4!RpcServerInterfaceGroupActivate` at `0x180013887`
- `RPCRT4!RpcServerInterfaceGroupActivate` at `0x180013887`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800138a6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800138a6`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001379e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001379e`

## pseudocode

```c
__int64 __fastcall CGPRPCServerBase::StartRPCServer(CGPRPCServerBase *this)
{
  UUID *v2; // rax
  unsigned int v3; // edi
  unsigned __int16 *v4; // rcx
  void *v5; // rcx
  int v7; // [rsp+20h] [rbp-69h]
  int v8; // [rsp+40h] [rbp-49h] BYREF
  const WCHAR *v9; // [rsp+48h] [rbp-41h]
  __int128 v10; // [rsp+50h] [rbp-39h]
  int v11; // [rsp+60h] [rbp-29h]
  int v12; // [rsp+70h] [rbp-19h] BYREF
  __int64 v13; // [rsp+78h] [rbp-11h]
  __int128 v14; // [rsp+80h] [rbp-9h]
  int v15; // [rsp+90h] [rbp+7h]
  __int64 v16; // [rsp+94h] [rbp+Bh]
  int (*v17)(void *, void *); // [rsp+A0h] [rbp+17h]
  char *v18; // [rsp+A8h] [rbp+1Fh]
  const wchar_t *v19; // [rsp+B0h] [rbp+27h]
  __int64 v20; // [rsp+B8h] [rbp+2Fh]

  v2 = (UUID *)LocalAlloc(0x40u, 0x10u);
  *((_QWORD *)this + 3) = v2;
  if ( v2 )
  {
    v4 = (unsigned __int16 *)*((_QWORD *)this + 5);
    *((_DWORD *)this + 4) = 1;
    v3 = UuidFromStringW(v4, v2);
    if ( !v3 )
    {
      v12 = 0;
      v13 = *((_QWORD *)this + 6);
      v14 = 0;
      v17 = CRpcServerUtility::AllowLocalOnlyServerSecurityCallback;
      v15 = 9;
      v19 = L"Group Policy RPC Interface";
      v16 = 1234;
      v9 = L"ncalrpc";
      v7 = *((_DWORD *)this + 14);
      v18 = (char *)this + 16;
      v20 = 0;
      v8 = 0;
      v10 = 0;
      v11 = 10;
      v3 = ((__int64 (__fastcall *)(int *, __int64, int *, __int64, int, void (__fastcall *)(void *, void *, unsigned int), _QWORD, void **))RpcServerInterfaceGroupCreateW)(
             &v12,
             1,
             &v8,
             1,
             v7,
             GpRpcInterfaceGroupIdleCallback,
             0,
             &GPRpcInterfaceGroup);
      if ( !v3 )
      {
        GPRpcInterfaceGroupCreated = 1;
        v3 = RpcServerInterfaceGroupActivate(GPRpcInterfaceGroup);
        if ( !v3 )
          *((_DWORD *)this + 3) = 1;
      }
    }
  }
  else
  {
    v3 = 14;
  }
  if ( !*((_DWORD *)this + 3) )
  {
    v5 = (void *)*((_QWORD *)this + 3);
    if ( v5 )
      LocalFree(v5);
  }
  return v3;
}

```

## disassembly

```asm
0x180013780  push    rbp
0x180013782  push    rbx
0x180013783  push    rsi
0x180013784  push    rdi
0x180013785  push    r15
0x180013787  lea     rbp, [rsp-37h]
0x18001378c  sub     rsp, 0C0h
0x180013793  mov     edx, 10h; uBytes
0x180013798  mov     rbx, rcx
0x18001379b  lea     ecx, [rdx+30h]; uFlags
0x18001379e  call    cs:__imp_LocalAlloc
0x1800137a4  mov     [rbx+18h], rax
0x1800137a8  test    rax, rax
0x1800137ab  jnz     short loc_1800137B5
0x1800137ad  lea     edi, [rax+0Eh]
0x1800137b0  jmp     loc_180013897
0x1800137b5  mov     rcx, [rbx+28h]; StringUuid
0x1800137b9  lea     rsi, [rbx+10h]
0x1800137bd  mov     r15d, 1
0x1800137c3  mov     rdx, rax; Uuid
0x1800137c6  mov     [rsi], r15d
0x1800137c9  call    cs:__imp_UuidFromStringW
0x1800137cf  mov     edi, eax
0x1800137d1  test    eax, eax
0x1800137d3  jnz     loc_180013897
0x1800137d9  mov     [rbp+57h+var_70], eax
0x1800137dc  lea     r8, [rbp+57h+var_A0]
0x1800137e0  mov     rax, [rbx+30h]
0x1800137e4  lea     rcx, [rbp+57h+var_70]
0x1800137e8  mov     [rbp+57h+var_68], rax
0x1800137ec  xorps   xmm0, xmm0
0x1800137ef  lea     rax, ?AllowLocalOnlyServerSecurityCallback@CRpcServerUtility@@SAJPEAX0@Z; CRpcServerUtility::AllowLocalOnlyServerSecurityCallback(void *,void *)
0x1800137f6  movdqa  [rbp+57h+var_60], xmm0
0x1800137fb  mov     [rbp+57h+var_40], rax
0x1800137ff  mov     r9d, r15d
0x180013802  lea     rax, aGroupPolicyRpc; "Group Policy RPC Interface"
0x180013809  mov     [rbp+57h+var_50], 9
0x180013810  mov     [rbp+57h+var_30], rax
0x180013814  mov     edx, r15d
0x180013817  lea     rax, aNcalrpc; "ncalrpc"
0x18001381e  mov     [rbp+57h+var_4C], 4D2h
0x180013826  mov     [rbp+57h+var_98], rax
0x18001382a  lea     rax, ?GPRpcInterfaceGroup@@3PEAXEA; void * GPRpcInterfaceGroup
0x180013831  mov     [rsp+0E0h+var_A8], rax
0x180013836  lea     rax, ?GpRpcInterfaceGroupIdleCallback@@YAXPEAX0K@Z; GpRpcInterfaceGroupIdleCallback(void *,void *,ulong)
0x18001383d  mov     [rsp+0E0h+var_B0], 0
0x180013846  mov     [rsp+0E0h+var_B8], rax
0x18001384b  mov     eax, [rbx+38h]
0x18001384e  mov     [rsp+0E0h+var_C0], eax
0x180013852  mov     [rbp+57h+var_38], rsi
0x180013856  mov     [rbp+57h+var_28], 0
0x18001385e  mov     [rbp+57h+var_A0], edi
0x180013861  movdqu  [rbp+57h+var_90], xmm0
0x180013866  mov     [rbp+57h+var_80], 0Ah
0x18001386d  call    cs:__imp_RpcServerInterfaceGroupCreateW
0x180013873  mov     edi, eax
0x180013875  test    eax, eax
0x180013877  jnz     short loc_180013897
0x180013879  mov     rcx, cs:?GPRpcInterfaceGroup@@3PEAXEA; void * GPRpcInterfaceGroup
0x180013880  mov     cs:?GPRpcInterfaceGroupCreated@@3HA, r15d; int GPRpcInterfaceGroupCreated
0x180013887  call    cs:__imp_RpcServerInterfaceGroupActivate
0x18001388d  mov     edi, eax
0x18001388f  test    eax, eax
0x180013891  jnz     short loc_180013897
0x180013893  mov     [rbx+0Ch], r15d
0x180013897  cmp     dword ptr [rbx+0Ch], 0
0x18001389b  jnz     short loc_1800138AC
0x18001389d  mov     rcx, [rbx+18h]; hMem
0x1800138a1  test    rcx, rcx
0x1800138a4  jz      short loc_1800138AC
0x1800138a6  call    cs:__imp_LocalFree
0x1800138ac  mov     eax, edi
0x1800138ae  add     rsp, 0C0h
0x1800138b5  pop     r15
0x1800138b7  pop     rdi
0x1800138b8  pop     rsi
0x1800138b9  pop     rbx
0x1800138ba  pop     rbp
0x1800138bb  retn
```
