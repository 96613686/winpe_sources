# PAC_EncodeValidationInformationEx(_NETLOGON_VALIDATION_SAM_INFO4 *,uchar * *,ulong *)

- ea: `0x18006fafc`
- end: `0x18006fc72`
- name: `?PAC_EncodeValidationInformationEx@@YAJPEAU_NETLOGON_VALIDATION_SAM_INFO4@@PEAPEAEPEAK@Z`
- size: `374`
- prototype: `__int64 __fastcall(struct _NETLOGON_VALIDATION_SAM_INFO4 *, unsigned __int8 **, unsigned int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180070918`

## callees

- `0x18005a060`
- `0x18005a090`
- `0x18006fafc`

## import_xrefs

- `RPCRT4!I_RpcMapWin32Status` at `0x18006fbda`
- `RPCRT4!I_RpcMapWin32Status` at `0x18006fbda`
- `RPCRT4!MesIncrementalHandleReset` at `0x18006fbce`
- `RPCRT4!MesIncrementalHandleReset` at `0x18006fbce`
- `RPCRT4!NdrMesTypeEncode3` at `0x18006fc13`
- `RPCRT4!NdrMesTypeEncode3` at `0x18006fc13`
- `RPCRT4!NdrMesTypeAlignSize3` at `0x18006fb89`
- `RPCRT4!NdrMesTypeAlignSize3` at `0x18006fb89`
- `RPCRT4!MesHandleFree` at `0x18006fc54`
- `RPCRT4!MesHandleFree` at `0x18006fc54`
- `RPCRT4!MesEncodeIncrementalHandleCreate` at `0x18006fb46`
- `RPCRT4!MesEncodeIncrementalHandleCreate` at `0x18006fb46`

## pseudocode

```c
__int64 __fastcall PAC_EncodeValidationInformationEx(
        struct _NETLOGON_VALIDATION_SAM_INFO4 *a1,
        unsigned __int8 **a2,
        unsigned int *a3)
{
  unsigned __int8 *v5; // rbx
  unsigned int v6; // edi
  unsigned int v7; // esi
  unsigned __int8 *v8; // rax
  RPC_STATUS v9; // eax
  __int128 v11; // [rsp+40h] [rbp-28h] BYREF
  struct _NETLOGON_VALIDATION_SAM_INFO4 *pObject; // [rsp+70h] [rbp+8h] BYREF
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
               4u,
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
      NdrMesTypeEncode3(Handle, &pPicklingInfo, &pProxyInfo, (const unsigned int **)&ArrTypeOffset, 4u, &pObject);
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
0x18006fafc  mov     rax, rsp
0x18006faff  mov     [rax+10h], rbx
0x18006fb03  mov     [rax+18h], rsi
0x18006fb07  mov     [rax+8], rcx
0x18006fb0b  push    rdi
0x18006fb0c  push    r14
0x18006fb0e  push    r15
0x18006fb10  sub     rsp, 50h
0x18006fb14  mov     r14, r8
0x18006fb17  mov     r15, rdx
0x18006fb1a  mov     qword ptr [rax+20h], 0
0x18006fb22  xorps   xmm0, xmm0
0x18006fb25  movups  xmmword ptr [rax-28h], xmm0
0x18006fb29  xor     ebx, ebx
0x18006fb2b  mov     [rsp+68h+var_30], rbx
0x18006fb30  lea     r9, [rax+20h]; pHandle
0x18006fb34  lea     r8, ?destroy@?$__func@V_lambda_8db0ce862824541f40dfb767113f1e28_@@$$A6A_NPEAX_K01I@Z@__function@wistd@@UEAAXXZ; WriteFn
0x18006fb3b  lea     rdx, ?PacReadFcn@@YAXPEAXPEAPEADPEAI@Z; AllocFn
0x18006fb42  lea     rcx, [rax-28h]; UserState
0x18006fb46  call    cs:__imp_MesEncodeIncrementalHandleCreate
0x18006fb4c  test    eax, eax
0x18006fb4e  jz      short loc_18006FB5A
0x18006fb50  mov     edi, 0C000009Ah
0x18006fb55  jmp     loc_18006FC3A
0x18006fb5a  lea     rax, [rsp+68h+arg_0]
0x18006fb5f  mov     [rsp+68h+pObject], rax; pObject
0x18006fb64  mov     [rsp+68h+nTypeIndex], 4; nTypeIndex
0x18006fb6c  lea     r9, ArrTypeOffset; ArrTypeOffset
0x18006fb73  lea     r8, pProxyInfo; pProxyInfo
0x18006fb7a  lea     rdx, pPicklingInfo; pPicklingInfo
0x18006fb81  mov     rcx, [rsp+68h+Handle]; Handle
0x18006fb89  call    cs:__imp_NdrMesTypeAlignSize3
0x18006fb8f  mov     rsi, rax
0x18006fb92  mov     [rsp+68h+var_38], esi
0x18006fb96  mov     ecx, esi; size
0x18006fb98  call    MIDL_user_allocate
0x18006fb9d  mov     rbx, rax
0x18006fba0  mov     [rsp+68h+var_30], rax
0x18006fba5  test    rax, rax
0x18006fba8  jz      short loc_18006FB50
0x18006fbaa  xor     edi, edi
0x18006fbac  mov     [rsp+68h+var_20], esi
0x18006fbb0  mov     [rsp+68h+var_28], rax
0x18006fbb5  mov     dword ptr [rsp+68h+pObject], edi; Operation
0x18006fbb9  mov     qword ptr [rsp+68h+nTypeIndex], rdi; ReadFn
0x18006fbbe  xor     r9d, r9d; WriteFn
0x18006fbc1  xor     r8d, r8d; AllocFn
0x18006fbc4  xor     edx, edx; UserState
0x18006fbc6  mov     rcx, [rsp+68h+Handle]; Handle
0x18006fbce  call    cs:__imp_MesIncrementalHandleReset
0x18006fbd4  test    eax, eax
0x18006fbd6  jz      short loc_18006FBE4
0x18006fbd8  mov     ecx, eax; Status
0x18006fbda  call    cs:__imp_I_RpcMapWin32Status
0x18006fbe0  mov     edi, eax
0x18006fbe2  jmp     short loc_18006FC3A
0x18006fbe4  lea     rax, [rsp+68h+arg_0]
0x18006fbe9  mov     [rsp+68h+pObject], rax; pObject
0x18006fbee  mov     [rsp+68h+nTypeIndex], 4; nTypeIndex
0x18006fbf6  lea     r9, ArrTypeOffset; ArrTypeOffset
0x18006fbfd  lea     r8, pProxyInfo; pProxyInfo
0x18006fc04  lea     rdx, pPicklingInfo; pPicklingInfo
0x18006fc0b  mov     rcx, [rsp+68h+Handle]; Handle
0x18006fc13  call    cs:__imp_NdrMesTypeEncode3
0x18006fc19  nop
0x18006fc1a  mov     [r15], rbx
0x18006fc1d  mov     [r14], esi
0x18006fc20  xor     ebx, ebx
0x18006fc22  jmp     short loc_18006FC3A
0x18006fc24  mov     edi, 0C000000Dh
0x18006fc29  mov     rbx, [rsp+68h+var_30]
0x18006fc2e  jmp     short loc_18006FC3A
0x18006fc30  mov     edi, 0C000000Dh
0x18006fc35  mov     rbx, [rsp+68h+var_30]
0x18006fc3a  test    rbx, rbx
0x18006fc3d  jz      short loc_18006FC47
0x18006fc3f  mov     rcx, rbx; void *
0x18006fc42  call    MIDL_user_free
0x18006fc47  mov     rcx, [rsp+68h+Handle]; Handle
0x18006fc4f  test    rcx, rcx
0x18006fc52  jz      short loc_18006FC5A
0x18006fc54  call    cs:__imp_MesHandleFree
0x18006fc5a  mov     eax, edi
0x18006fc5c  lea     r11, [rsp+68h+var_18]
0x18006fc61  mov     rbx, [r11+28h]
0x18006fc65  mov     rsi, [r11+30h]
0x18006fc69  mov     rsp, r11
0x18006fc6c  pop     r15
0x18006fc6e  pop     r14
0x18006fc70  pop     rdi
0x18006fc71  retn
```
