# PAC_EncodeValidationInformation(_NETLOGON_VALIDATION_SAM_INFO3 *,uchar * *,ulong *)

- ea: `0x18006f978`
- end: `0x18006faf6`
- name: `?PAC_EncodeValidationInformation@@YAJPEAU_NETLOGON_VALIDATION_SAM_INFO3@@PEAPEAEPEAK@Z`
- size: `382`
- prototype: `__int64 __fastcall(struct _NETLOGON_VALIDATION_SAM_INFO3 *, unsigned __int8 **, unsigned int *)`
- caller_count: `3`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x18007069c`
- `0x180070ab4`
- `0x180071134`

## callees

- `0x18005a060`
- `0x18005a090`
- `0x18006f978`

## import_xrefs

- `RPCRT4!I_RpcMapWin32Status` at `0x18006fa5f`
- `RPCRT4!I_RpcMapWin32Status` at `0x18006fa5f`
- `RPCRT4!MesIncrementalHandleReset` at `0x18006fa53`
- `RPCRT4!MesIncrementalHandleReset` at `0x18006fa53`
- `RPCRT4!NdrMesTypeEncode3` at `0x18006fa9b`
- `RPCRT4!NdrMesTypeEncode3` at `0x18006fa9b`
- `RPCRT4!NdrMesTypeAlignSize3` at `0x18006fa0b`
- `RPCRT4!NdrMesTypeAlignSize3` at `0x18006fa0b`
- `RPCRT4!MesHandleFree` at `0x18006fae2`
- `RPCRT4!MesHandleFree` at `0x18006fae2`
- `RPCRT4!MesEncodeIncrementalHandleCreate` at `0x18006f9c5`
- `RPCRT4!MesEncodeIncrementalHandleCreate` at `0x18006f9c5`

## pseudocode

```c
__int64 __fastcall PAC_EncodeValidationInformation(
        struct _NETLOGON_VALIDATION_SAM_INFO3 *a1,
        unsigned __int8 **a2,
        unsigned int *a3)
{
  unsigned __int8 *v5; // rbx
  unsigned int v6; // edi
  unsigned int v7; // esi
  unsigned __int8 *v8; // rax
  RPC_STATUS v9; // eax
  __int128 v11; // [rsp+38h] [rbp-40h] BYREF
  struct _NETLOGON_VALIDATION_SAM_INFO3 *pObject; // [rsp+80h] [rbp+8h] BYREF
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
               1u,
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
      NdrMesTypeEncode3(Handle, &pPicklingInfo, &pProxyInfo, (const unsigned int **)&ArrTypeOffset, 1u, &pObject);
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
0x18006f978  mov     rax, rsp
0x18006f97b  mov     [rax+8], rcx
0x18006f97f  push    rbx
0x18006f980  push    rsi
0x18006f981  push    rdi
0x18006f982  push    r14
0x18006f984  push    r15
0x18006f986  sub     rsp, 50h
0x18006f98a  mov     r14, r8
0x18006f98d  mov     r15, rdx
0x18006f990  mov     qword ptr [rax+10h], 0
0x18006f998  xorps   xmm0, xmm0
0x18006f99b  movups  xmmword ptr [rax-40h], xmm0
0x18006f99f  xor     ebx, ebx
0x18006f9a1  mov     [rsp+78h+arg_10], rbx
0x18006f9a9  mov     [rdx], rbx
0x18006f9ac  mov     [r8], ebx
0x18006f9af  lea     r9, [rax+10h]; pHandle
0x18006f9b3  lea     r8, ?destroy@?$__func@V_lambda_8db0ce862824541f40dfb767113f1e28_@@$$A6A_NPEAX_K01I@Z@__function@wistd@@UEAAXXZ; WriteFn
0x18006f9ba  lea     rdx, ?PacReadFcn@@YAXPEAXPEAPEADPEAI@Z; AllocFn
0x18006f9c1  lea     rcx, [rax-40h]; UserState
0x18006f9c5  call    cs:__imp_MesEncodeIncrementalHandleCreate
0x18006f9cb  test    eax, eax
0x18006f9cd  jz      short loc_18006F9D9
0x18006f9cf  mov     edi, 0C000009Ah
0x18006f9d4  jmp     loc_18006FAC8
0x18006f9d9  lea     rax, [rsp+78h+arg_0]
0x18006f9e1  mov     [rsp+78h+pObject], rax; pObject
0x18006f9e6  mov     [rsp+78h+nTypeIndex], 1; nTypeIndex
0x18006f9ee  lea     r9, ArrTypeOffset; ArrTypeOffset
0x18006f9f5  lea     r8, pProxyInfo; pProxyInfo
0x18006f9fc  lea     rdx, pPicklingInfo; pPicklingInfo
0x18006fa03  mov     rcx, [rsp+78h+Handle]; Handle
0x18006fa0b  call    cs:__imp_NdrMesTypeAlignSize3
0x18006fa11  mov     rsi, rax
0x18006fa14  mov     [rsp+78h+var_48], esi
0x18006fa18  mov     ecx, esi; size
0x18006fa1a  call    MIDL_user_allocate
0x18006fa1f  mov     rbx, rax
0x18006fa22  mov     [rsp+78h+arg_10], rax
0x18006fa2a  test    rax, rax
0x18006fa2d  jz      short loc_18006F9CF
0x18006fa2f  xor     edi, edi
0x18006fa31  mov     [rsp+78h+var_38], esi
0x18006fa35  mov     [rsp+78h+var_40], rax
0x18006fa3a  mov     dword ptr [rsp+78h+pObject], edi; Operation
0x18006fa3e  mov     qword ptr [rsp+78h+nTypeIndex], rdi; ReadFn
0x18006fa43  xor     r9d, r9d; WriteFn
0x18006fa46  xor     r8d, r8d; AllocFn
0x18006fa49  xor     edx, edx; UserState
0x18006fa4b  mov     rcx, [rsp+78h+Handle]; Handle
0x18006fa53  call    cs:__imp_MesIncrementalHandleReset
0x18006fa59  test    eax, eax
0x18006fa5b  jz      short loc_18006FA69
0x18006fa5d  mov     ecx, eax; Status
0x18006fa5f  call    cs:__imp_I_RpcMapWin32Status
0x18006fa65  mov     edi, eax
0x18006fa67  jmp     short loc_18006FAC8
0x18006fa69  lea     rax, [rsp+78h+arg_0]
0x18006fa71  mov     [rsp+78h+pObject], rax; pObject
0x18006fa76  mov     [rsp+78h+nTypeIndex], 1; nTypeIndex
0x18006fa7e  lea     r9, ArrTypeOffset; ArrTypeOffset
0x18006fa85  lea     r8, pProxyInfo; pProxyInfo
0x18006fa8c  lea     rdx, pPicklingInfo; pPicklingInfo
0x18006fa93  mov     rcx, [rsp+78h+Handle]; Handle
0x18006fa9b  call    cs:__imp_NdrMesTypeEncode3
0x18006faa1  nop
0x18006faa2  mov     [r15], rbx
0x18006faa5  mov     [r14], esi
0x18006faa8  xor     ebx, ebx
0x18006faaa  jmp     short loc_18006FAC8
0x18006faac  mov     edi, 0C000000Dh
0x18006fab1  mov     rbx, [rsp+78h+arg_10]
0x18006fab9  jmp     short loc_18006FAC8
0x18006fabb  mov     edi, 0C000000Dh
0x18006fac0  mov     rbx, [rsp+78h+arg_10]
0x18006fac8  test    rbx, rbx
0x18006facb  jz      short loc_18006FAD5
0x18006facd  mov     rcx, rbx; void *
0x18006fad0  call    MIDL_user_free
0x18006fad5  mov     rcx, [rsp+78h+Handle]; Handle
0x18006fadd  test    rcx, rcx
0x18006fae0  jz      short loc_18006FAE8
0x18006fae2  call    cs:__imp_MesHandleFree
0x18006fae8  mov     eax, edi
0x18006faea  add     rsp, 50h
0x18006faee  pop     r15
0x18006faf0  pop     r14
0x18006faf2  pop     rdi
0x18006faf3  pop     rsi
0x18006faf4  pop     rbx
0x18006faf5  retn
```
