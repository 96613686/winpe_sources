# PAC_EncodeS4UDelegationInformation(_S4U_DELEGATION_INFO *,uchar * *,ulong *)

- ea: `0x18006f7fc`
- end: `0x18006f972`
- name: `?PAC_EncodeS4UDelegationInformation@@YAJPEAU_S4U_DELEGATION_INFO@@PEAPEAEPEAK@Z`
- size: `374`
- prototype: `__int64 __fastcall(struct _S4U_DELEGATION_INFO *, unsigned __int8 **, unsigned int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x1800709c4`

## callees

- `0x18005a060`
- `0x18005a090`
- `0x18006f7fc`

## import_xrefs

- `RPCRT4!I_RpcMapWin32Status` at `0x18006f8da`
- `RPCRT4!I_RpcMapWin32Status` at `0x18006f8da`
- `RPCRT4!MesIncrementalHandleReset` at `0x18006f8ce`
- `RPCRT4!MesIncrementalHandleReset` at `0x18006f8ce`
- `RPCRT4!NdrMesTypeEncode3` at `0x18006f913`
- `RPCRT4!NdrMesTypeEncode3` at `0x18006f913`
- `RPCRT4!NdrMesTypeAlignSize3` at `0x18006f889`
- `RPCRT4!NdrMesTypeAlignSize3` at `0x18006f889`
- `RPCRT4!MesHandleFree` at `0x18006f954`
- `RPCRT4!MesHandleFree` at `0x18006f954`
- `RPCRT4!MesEncodeIncrementalHandleCreate` at `0x18006f846`
- `RPCRT4!MesEncodeIncrementalHandleCreate` at `0x18006f846`

## pseudocode

```c
__int64 __fastcall PAC_EncodeS4UDelegationInformation(
        struct _S4U_DELEGATION_INFO *a1,
        unsigned __int8 **a2,
        unsigned int *a3)
{
  unsigned __int8 *v5; // rbx
  unsigned int v6; // edi
  unsigned int v7; // esi
  unsigned __int8 *v8; // rax
  RPC_STATUS v9; // eax
  __int128 v11; // [rsp+40h] [rbp-28h] BYREF
  struct _S4U_DELEGATION_INFO *pObject; // [rsp+70h] [rbp+8h] BYREF
  handle_t Handle; // [rsp+88h] [rbp+20h] BYREF

  pObject = a1;
  Handle = 0;
  v11 = 0;
  v5 = 0;
  if ( MesEncodeIncrementalHandleCreate(
         &v11,
         PacReadFcn,
         (MIDL_ES_WRITE)wistd::__function::__func<_lambda_8db0ce862824541f40dfb767113f1e28_,bool (void *,unsigned __int64,void *,unsigned __int64,unsigned int)>::destroy,
         &Handle)
    || (v7 = NdrMesTypeAlignSize3(
               Handle,
               &pPicklingInfo,
               &pProxyInfo,
               (const unsigned int **)&ArrTypeOffset,
               3u,
               &pObject),
        v8 = (unsigned __int8 *)MIDL_user_allocate(v7),
        (v5 = v8) == 0) )
  {
    v6 = -1073741670;
  }
  else
  {
    v6 = 0;
    DWORD2(v11) = v7;
    *(_QWORD *)&v11 = v8;
    v9 = MesIncrementalHandleReset(Handle, 0, 0, 0, 0, MES_ENCODE);
    if ( v9 )
    {
      v6 = I_RpcMapWin32Status(v9);
    }
    else
    {
      NdrMesTypeEncode3(Handle, &pPicklingInfo, &pProxyInfo, (const unsigned int **)&ArrTypeOffset, 3u, &pObject);
      *a2 = v5;
      *a3 = v7;
      v5 = 0;
    }
  }
  if ( v5 )
    MIDL_user_free(v5);
  if ( Handle )
    MesHandleFree(Handle);
  return v6;
}

```

## disassembly

```asm
0x18006f7fc  mov     rax, rsp
0x18006f7ff  mov     [rax+10h], rbx
0x18006f803  mov     [rax+18h], rsi
0x18006f807  mov     [rax+8], rcx
0x18006f80b  push    rdi
0x18006f80c  push    r14
0x18006f80e  push    r15
0x18006f810  sub     rsp, 50h
0x18006f814  mov     r14, r8
0x18006f817  mov     r15, rdx
0x18006f81a  mov     qword ptr [rax+20h], 0
0x18006f822  xorps   xmm0, xmm0
0x18006f825  movups  xmmword ptr [rax-28h], xmm0
0x18006f829  xor     ebx, ebx
0x18006f82b  mov     [rsp+68h+var_30], rbx
0x18006f830  lea     r9, [rax+20h]; pHandle
0x18006f834  lea     r8, ?destroy@?$__func@V_lambda_8db0ce862824541f40dfb767113f1e28_@@$$A6A_NPEAX_K01I@Z@__function@wistd@@UEAAXXZ; WriteFn
0x18006f83b  lea     rdx, ?PacReadFcn@@YAXPEAXPEAPEADPEAI@Z; AllocFn
0x18006f842  lea     rcx, [rax-28h]; UserState
0x18006f846  call    cs:__imp_MesEncodeIncrementalHandleCreate
0x18006f84c  test    eax, eax
0x18006f84e  jz      short loc_18006F85A
0x18006f850  mov     edi, 0C000009Ah
0x18006f855  jmp     loc_18006F93A
0x18006f85a  lea     rax, [rsp+68h+arg_0]
0x18006f85f  mov     [rsp+68h+pObject], rax; pObject
0x18006f864  mov     [rsp+68h+nTypeIndex], 3; nTypeIndex
0x18006f86c  lea     r9, ArrTypeOffset; ArrTypeOffset
0x18006f873  lea     r8, pProxyInfo; pProxyInfo
0x18006f87a  lea     rdx, pPicklingInfo; pPicklingInfo
0x18006f881  mov     rcx, [rsp+68h+Handle]; Handle
0x18006f889  call    cs:__imp_NdrMesTypeAlignSize3
0x18006f88f  mov     rsi, rax
0x18006f892  mov     [rsp+68h+var_38], esi
0x18006f896  mov     ecx, esi; size
0x18006f898  call    MIDL_user_allocate
0x18006f89d  mov     rbx, rax
0x18006f8a0  mov     [rsp+68h+var_30], rax
0x18006f8a5  test    rax, rax
0x18006f8a8  jz      short loc_18006F850
0x18006f8aa  xor     edi, edi
0x18006f8ac  mov     [rsp+68h+var_20], esi
0x18006f8b0  mov     [rsp+68h+var_28], rax
0x18006f8b5  mov     dword ptr [rsp+68h+pObject], edi; Operation
0x18006f8b9  mov     qword ptr [rsp+68h+nTypeIndex], rdi; ReadFn
0x18006f8be  xor     r9d, r9d; WriteFn
0x18006f8c1  xor     r8d, r8d; AllocFn
0x18006f8c4  xor     edx, edx; UserState
0x18006f8c6  mov     rcx, [rsp+68h+Handle]; Handle
0x18006f8ce  call    cs:__imp_MesIncrementalHandleReset
0x18006f8d4  test    eax, eax
0x18006f8d6  jz      short loc_18006F8E4
0x18006f8d8  mov     ecx, eax; Status
0x18006f8da  call    cs:__imp_I_RpcMapWin32Status
0x18006f8e0  mov     edi, eax
0x18006f8e2  jmp     short loc_18006F93A
0x18006f8e4  lea     rax, [rsp+68h+arg_0]
0x18006f8e9  mov     [rsp+68h+pObject], rax; pObject
0x18006f8ee  mov     [rsp+68h+nTypeIndex], 3; nTypeIndex
0x18006f8f6  lea     r9, ArrTypeOffset; ArrTypeOffset
0x18006f8fd  lea     r8, pProxyInfo; pProxyInfo
0x18006f904  lea     rdx, pPicklingInfo; pPicklingInfo
0x18006f90b  mov     rcx, [rsp+68h+Handle]; Handle
0x18006f913  call    cs:__imp_NdrMesTypeEncode3
0x18006f919  nop
0x18006f91a  mov     [r15], rbx
0x18006f91d  mov     [r14], esi
0x18006f920  xor     ebx, ebx
0x18006f922  jmp     short loc_18006F93A
0x18006f924  mov     edi, 0C000000Dh
0x18006f929  mov     rbx, [rsp+68h+var_30]
0x18006f92e  jmp     short loc_18006F93A
0x18006f930  mov     edi, 0C000000Dh
0x18006f935  mov     rbx, [rsp+68h+var_30]
0x18006f93a  test    rbx, rbx
0x18006f93d  jz      short loc_18006F947
0x18006f93f  mov     rcx, rbx; void *
0x18006f942  call    MIDL_user_free
0x18006f947  mov     rcx, [rsp+68h+Handle]; Handle
0x18006f94f  test    rcx, rcx
0x18006f952  jz      short loc_18006F95A
0x18006f954  call    cs:__imp_MesHandleFree
0x18006f95a  mov     eax, edi
0x18006f95c  lea     r11, [rsp+68h+var_18]
0x18006f961  mov     rbx, [r11+28h]
0x18006f965  mov     rsi, [r11+30h]
0x18006f969  mov     rsp, r11
0x18006f96c  pop     r15
0x18006f96e  pop     r14
0x18006f970  pop     rdi
0x18006f971  retn
```
