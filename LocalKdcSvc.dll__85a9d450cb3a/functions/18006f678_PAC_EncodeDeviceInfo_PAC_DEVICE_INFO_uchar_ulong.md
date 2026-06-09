# PAC_EncodeDeviceInfo(_PAC_DEVICE_INFO *,uchar * *,ulong *)

- ea: `0x18006f678`
- end: `0x18006f7f6`
- name: `?PAC_EncodeDeviceInfo@@YAJPEAU_PAC_DEVICE_INFO@@PEAPEAEPEAK@Z`
- size: `382`
- prototype: `__int64 __fastcall(struct _PAC_DEVICE_INFO *, unsigned __int8 **, unsigned int *)`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x18007006c`
- `0x180071134`

## callees

- `0x18005a060`
- `0x18005a090`
- `0x18006f678`

## import_xrefs

- `RPCRT4!I_RpcMapWin32Status` at `0x18006f75f`
- `RPCRT4!I_RpcMapWin32Status` at `0x18006f75f`
- `RPCRT4!MesIncrementalHandleReset` at `0x18006f753`
- `RPCRT4!MesIncrementalHandleReset` at `0x18006f753`
- `RPCRT4!NdrMesTypeEncode3` at `0x18006f79b`
- `RPCRT4!NdrMesTypeEncode3` at `0x18006f79b`
- `RPCRT4!NdrMesTypeAlignSize3` at `0x18006f70b`
- `RPCRT4!NdrMesTypeAlignSize3` at `0x18006f70b`
- `RPCRT4!MesHandleFree` at `0x18006f7e2`
- `RPCRT4!MesHandleFree` at `0x18006f7e2`
- `RPCRT4!MesEncodeIncrementalHandleCreate` at `0x18006f6c5`
- `RPCRT4!MesEncodeIncrementalHandleCreate` at `0x18006f6c5`

## pseudocode

```c
__int64 __fastcall PAC_EncodeDeviceInfo(struct _PAC_DEVICE_INFO *a1, unsigned __int8 **a2, unsigned int *a3)
{
  unsigned __int8 *v5; // rbx
  unsigned int v6; // edi
  unsigned int v7; // esi
  unsigned __int8 *v8; // rax
  RPC_STATUS v9; // eax
  __int128 v11; // [rsp+38h] [rbp-40h] BYREF
  struct _PAC_DEVICE_INFO *pObject; // [rsp+80h] [rbp+8h] BYREF
  handle_t Handle; // [rsp+88h] [rbp+10h] BYREF
  unsigned __int8 *v14; // [rsp+90h] [rbp+18h]

  pObject = a1;
  Handle = 0;
  v11 = 0;
  v5 = 0;
  v14 = 0;
  *a2 = 0;
  *a3 = 0;
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
               5u,
               &pObject),
        v8 = (unsigned __int8 *)MIDL_user_allocate(v7),
        v5 = v8,
        (v14 = v8) == 0) )
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
      NdrMesTypeEncode3(Handle, &pPicklingInfo, &pProxyInfo, (const unsigned int **)&ArrTypeOffset, 5u, &pObject);
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
0x18006f678  mov     rax, rsp
0x18006f67b  mov     [rax+8], rcx
0x18006f67f  push    rbx
0x18006f680  push    rsi
0x18006f681  push    rdi
0x18006f682  push    r14
0x18006f684  push    r15
0x18006f686  sub     rsp, 50h
0x18006f68a  mov     r14, r8
0x18006f68d  mov     r15, rdx
0x18006f690  mov     qword ptr [rax+10h], 0
0x18006f698  xorps   xmm0, xmm0
0x18006f69b  movups  xmmword ptr [rax-40h], xmm0
0x18006f69f  xor     ebx, ebx
0x18006f6a1  mov     [rsp+78h+arg_10], rbx
0x18006f6a9  mov     [rdx], rbx
0x18006f6ac  mov     [r8], ebx
0x18006f6af  lea     r9, [rax+10h]; pHandle
0x18006f6b3  lea     r8, ?destroy@?$__func@V_lambda_8db0ce862824541f40dfb767113f1e28_@@$$A6A_NPEAX_K01I@Z@__function@wistd@@UEAAXXZ; WriteFn
0x18006f6ba  lea     rdx, ?PacReadFcn@@YAXPEAXPEAPEADPEAI@Z; AllocFn
0x18006f6c1  lea     rcx, [rax-40h]; UserState
0x18006f6c5  call    cs:__imp_MesEncodeIncrementalHandleCreate
0x18006f6cb  test    eax, eax
0x18006f6cd  jz      short loc_18006F6D9
0x18006f6cf  mov     edi, 0C000009Ah
0x18006f6d4  jmp     loc_18006F7C8
0x18006f6d9  lea     rax, [rsp+78h+arg_0]
0x18006f6e1  mov     [rsp+78h+pObject], rax; pObject
0x18006f6e6  mov     [rsp+78h+nTypeIndex], 5; nTypeIndex
0x18006f6ee  lea     r9, ArrTypeOffset; ArrTypeOffset
0x18006f6f5  lea     r8, pProxyInfo; pProxyInfo
0x18006f6fc  lea     rdx, pPicklingInfo; pPicklingInfo
0x18006f703  mov     rcx, [rsp+78h+Handle]; Handle
0x18006f70b  call    cs:__imp_NdrMesTypeAlignSize3
0x18006f711  mov     rsi, rax
0x18006f714  mov     [rsp+78h+var_48], esi
0x18006f718  mov     ecx, esi; size
0x18006f71a  call    MIDL_user_allocate
0x18006f71f  mov     rbx, rax
0x18006f722  mov     [rsp+78h+arg_10], rax
0x18006f72a  test    rax, rax
0x18006f72d  jz      short loc_18006F6CF
0x18006f72f  xor     edi, edi
0x18006f731  mov     [rsp+78h+var_38], esi
0x18006f735  mov     [rsp+78h+var_40], rax
0x18006f73a  mov     dword ptr [rsp+78h+pObject], edi; Operation
0x18006f73e  mov     qword ptr [rsp+78h+nTypeIndex], rdi; ReadFn
0x18006f743  xor     r9d, r9d; WriteFn
0x18006f746  xor     r8d, r8d; AllocFn
0x18006f749  xor     edx, edx; UserState
0x18006f74b  mov     rcx, [rsp+78h+Handle]; Handle
0x18006f753  call    cs:__imp_MesIncrementalHandleReset
0x18006f759  test    eax, eax
0x18006f75b  jz      short loc_18006F769
0x18006f75d  mov     ecx, eax; Status
0x18006f75f  call    cs:__imp_I_RpcMapWin32Status
0x18006f765  mov     edi, eax
0x18006f767  jmp     short loc_18006F7C8
0x18006f769  lea     rax, [rsp+78h+arg_0]
0x18006f771  mov     [rsp+78h+pObject], rax; pObject
0x18006f776  mov     [rsp+78h+nTypeIndex], 5; nTypeIndex
0x18006f77e  lea     r9, ArrTypeOffset; ArrTypeOffset
0x18006f785  lea     r8, pProxyInfo; pProxyInfo
0x18006f78c  lea     rdx, pPicklingInfo; pPicklingInfo
0x18006f793  mov     rcx, [rsp+78h+Handle]; Handle
0x18006f79b  call    cs:__imp_NdrMesTypeEncode3
0x18006f7a1  nop
0x18006f7a2  mov     [r15], rbx
0x18006f7a5  mov     [r14], esi
0x18006f7a8  xor     ebx, ebx
0x18006f7aa  jmp     short loc_18006F7C8
0x18006f7ac  mov     edi, 0C000000Dh
0x18006f7b1  mov     rbx, [rsp+78h+arg_10]
0x18006f7b9  jmp     short loc_18006F7C8
0x18006f7bb  mov     edi, 0C000000Dh
0x18006f7c0  mov     rbx, [rsp+78h+arg_10]
0x18006f7c8  test    rbx, rbx
0x18006f7cb  jz      short loc_18006F7D5
0x18006f7cd  mov     rcx, rbx; void *
0x18006f7d0  call    MIDL_user_free
0x18006f7d5  mov     rcx, [rsp+78h+Handle]; Handle
0x18006f7dd  test    rcx, rcx
0x18006f7e0  jz      short loc_18006F7E8
0x18006f7e2  call    cs:__imp_MesHandleFree
0x18006f7e8  mov     eax, edi
0x18006f7ea  add     rsp, 50h
0x18006f7ee  pop     r15
0x18006f7f0  pop     r14
0x18006f7f2  pop     rdi
0x18006f7f3  pop     rsi
0x18006f7f4  pop     rbx
0x18006f7f5  retn
```
