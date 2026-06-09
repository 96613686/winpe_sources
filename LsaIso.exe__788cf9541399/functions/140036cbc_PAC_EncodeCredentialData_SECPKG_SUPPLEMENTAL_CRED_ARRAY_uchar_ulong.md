# PAC_EncodeCredentialData(_SECPKG_SUPPLEMENTAL_CRED_ARRAY *,uchar * *,ulong *)

- ea: `0x140036cbc`
- end: `0x140036e37`
- name: `?PAC_EncodeCredentialData@@YAJPEAU_SECPKG_SUPPLEMENTAL_CRED_ARRAY@@PEAPEAEPEAK@Z`
- size: `379`
- prototype: `__int64 __fastcall(struct _SECPKG_SUPPLEMENTAL_CRED_ARRAY *, unsigned __int8 **, unsigned int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x1400145ac`

## callees

- `0x1400066f0`
- `0x140006720`
- `0x140036cbc`

## import_xrefs

- `RPCRT4!MesEncodeIncrementalHandleCreate` at `0x140036d06`
- `RPCRT4!MesEncodeIncrementalHandleCreate` at `0x140036d06`
- `RPCRT4!MesIncrementalHandleReset` at `0x140036d93`
- `RPCRT4!MesIncrementalHandleReset` at `0x140036d93`
- `RPCRT4!NdrMesTypeAlignSize3` at `0x140036d49`
- `RPCRT4!NdrMesTypeAlignSize3` at `0x140036d49`
- `RPCRT4!NdrMesTypeEncode3` at `0x140036dd8`
- `RPCRT4!NdrMesTypeEncode3` at `0x140036dd8`
- `RPCRT4!MesHandleFree` at `0x140036e19`
- `RPCRT4!MesHandleFree` at `0x140036e19`
- `RPCRT4!I_RpcMapWin32Status` at `0x140036d9f`
- `RPCRT4!I_RpcMapWin32Status` at `0x140036d9f`

## pseudocode

```c
__int64 __fastcall PAC_EncodeCredentialData(
        struct _SECPKG_SUPPLEMENTAL_CRED_ARRAY *a1,
        unsigned __int8 **a2,
        unsigned int *a3)
{
  unsigned __int8 *v5; // rdi
  unsigned int v6; // ebx
  unsigned int v7; // esi
  unsigned __int8 *v8; // rax
  RPC_STATUS v9; // eax
  __int128 v11; // [rsp+40h] [rbp-28h] BYREF
  struct _SECPKG_SUPPLEMENTAL_CRED_ARRAY *pObject; // [rsp+70h] [rbp+8h] BYREF
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
    || (v7 = (NdrMesTypeAlignSize3(
                Handle,
                &stru_14004BE00,
                &pProxyInfo,
                (const unsigned int **)&off_1400521D8,
                2u,
                &pObject)
            + 7)
           & 0xFFFFFFF8,
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
      NdrMesTypeEncode3(Handle, &stru_14004BE00, &pProxyInfo, (const unsigned int **)&off_1400521D8, 2u, &pObject);
      *a2 = v5;
      *a3 = v7;
      v5 = 0;
    }
  }
  if ( v5 )
    SafeAllocaFreeToHeap(v5);
  if ( Handle )
    MesHandleFree(Handle);
  return v6;
}

```

## disassembly

```asm
0x140036cbc  mov     rax, rsp
0x140036cbf  mov     [rax+10h], rbx
0x140036cc3  mov     [rax+18h], rsi
0x140036cc7  mov     [rax+8], rcx
0x140036ccb  push    rdi
0x140036ccc  push    r14
0x140036cce  push    r15
0x140036cd0  sub     rsp, 50h
0x140036cd4  mov     r14, r8
0x140036cd7  mov     r15, rdx
0x140036cda  mov     qword ptr [rax+20h], 0
0x140036ce2  xorps   xmm0, xmm0
0x140036ce5  movups  xmmword ptr [rax-28h], xmm0
0x140036ce9  xor     edi, edi
0x140036ceb  mov     [rsp+68h+var_30], rdi
0x140036cf0  lea     r9, [rax+20h]; pHandle
0x140036cf4  lea     r8, ?destroy@?$__func@V_lambda_8db0ce862824541f40dfb767113f1e28_@@$$A6A_NPEAX_K01I@Z@__function@wistd@@UEAAXXZ; WriteFn
0x140036cfb  lea     rdx, ?PacReadFcn@@YAXPEAXPEAPEADPEAI@Z; AllocFn
0x140036d02  lea     rcx, [rax-28h]; UserState
0x140036d06  call    cs:__imp_MesEncodeIncrementalHandleCreate
0x140036d0c  test    eax, eax
0x140036d0e  jz      short loc_140036D1A
0x140036d10  mov     ebx, 0C000009Ah
0x140036d15  jmp     loc_140036DFF
0x140036d1a  lea     rax, [rsp+68h+arg_0]
0x140036d1f  mov     [rsp+68h+pObject], rax; pObject
0x140036d24  mov     [rsp+68h+nTypeIndex], 2; nTypeIndex
0x140036d2c  lea     r9, off_1400521D8; ArrTypeOffset
0x140036d33  lea     r8, pProxyInfo; pProxyInfo
0x140036d3a  lea     rdx, stru_14004BE00; pPicklingInfo
0x140036d41  mov     rcx, [rsp+68h+Handle]; Handle
0x140036d49  call    cs:__imp_NdrMesTypeAlignSize3
0x140036d4f  mov     [rsp+68h+var_38], eax
0x140036d53  add     eax, 7
0x140036d56  and     eax, 0FFFFFFF8h
0x140036d59  mov     esi, eax
0x140036d5b  mov     ecx, eax; size
0x140036d5d  call    MIDL_user_allocate
0x140036d62  mov     rdi, rax
0x140036d65  mov     [rsp+68h+var_30], rax
0x140036d6a  test    rax, rax
0x140036d6d  jz      short loc_140036D10
0x140036d6f  xor     ebx, ebx
0x140036d71  mov     [rsp+68h+var_20], esi
0x140036d75  mov     [rsp+68h+var_28], rax
0x140036d7a  mov     dword ptr [rsp+68h+pObject], ebx; Operation
0x140036d7e  mov     qword ptr [rsp+68h+nTypeIndex], rbx; ReadFn
0x140036d83  xor     r9d, r9d; WriteFn
0x140036d86  xor     r8d, r8d; AllocFn
0x140036d89  xor     edx, edx; UserState
0x140036d8b  mov     rcx, [rsp+68h+Handle]; Handle
0x140036d93  call    cs:__imp_MesIncrementalHandleReset
0x140036d99  test    eax, eax
0x140036d9b  jz      short loc_140036DA9
0x140036d9d  mov     ecx, eax; Status
0x140036d9f  call    cs:__imp_I_RpcMapWin32Status
0x140036da5  mov     ebx, eax
0x140036da7  jmp     short loc_140036DFF
0x140036da9  lea     rax, [rsp+68h+arg_0]
0x140036dae  mov     [rsp+68h+pObject], rax; pObject
0x140036db3  mov     [rsp+68h+nTypeIndex], 2; nTypeIndex
0x140036dbb  lea     r9, off_1400521D8; ArrTypeOffset
0x140036dc2  lea     r8, pProxyInfo; pProxyInfo
0x140036dc9  lea     rdx, stru_14004BE00; pPicklingInfo
0x140036dd0  mov     rcx, [rsp+68h+Handle]; Handle
0x140036dd8  call    cs:__imp_NdrMesTypeEncode3
0x140036dde  nop
0x140036ddf  mov     [r15], rdi
0x140036de2  mov     [r14], esi
0x140036de5  xor     edi, edi
0x140036de7  jmp     short loc_140036DFF
0x140036de9  mov     ebx, 0C000000Dh
0x140036dee  mov     rdi, [rsp+68h+var_30]
0x140036df3  jmp     short loc_140036DFF
0x140036df5  mov     ebx, 0C000000Dh
0x140036dfa  mov     rdi, [rsp+68h+var_30]
0x140036dff  test    rdi, rdi
0x140036e02  jz      short loc_140036E0C
0x140036e04  mov     rcx, rdi; void *
0x140036e07  call    SafeAllocaFreeToHeap
0x140036e0c  mov     rcx, [rsp+68h+Handle]; Handle
0x140036e14  test    rcx, rcx
0x140036e17  jz      short loc_140036E1F
0x140036e19  call    cs:__imp_MesHandleFree
0x140036e1f  mov     eax, ebx
0x140036e21  lea     r11, [rsp+68h+var_18]
0x140036e26  mov     rbx, [r11+28h]
0x140036e2a  mov     rsi, [r11+30h]
0x140036e2e  mov     rsp, r11
0x140036e31  pop     r15
0x140036e33  pop     r14
0x140036e35  pop     rdi
0x140036e36  retn
```
