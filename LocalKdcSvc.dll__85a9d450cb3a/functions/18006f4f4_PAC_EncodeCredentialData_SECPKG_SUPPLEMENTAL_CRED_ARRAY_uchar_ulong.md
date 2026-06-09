# PAC_EncodeCredentialData(_SECPKG_SUPPLEMENTAL_CRED_ARRAY *,uchar * *,ulong *)

- ea: `0x18006f4f4`
- end: `0x18006f66f`
- name: `?PAC_EncodeCredentialData@@YAJPEAU_SECPKG_SUPPLEMENTAL_CRED_ARRAY@@PEAPEAEPEAK@Z`
- size: `379`
- prototype: `__int64 __fastcall(struct _SECPKG_SUPPLEMENTAL_CRED_ARRAY *, unsigned __int8 **, unsigned int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x18006e780`

## callees

- `0x18005a060`
- `0x18005a090`
- `0x18006f4f4`

## import_xrefs

- `RPCRT4!I_RpcMapWin32Status` at `0x18006f5d7`
- `RPCRT4!I_RpcMapWin32Status` at `0x18006f5d7`
- `RPCRT4!MesIncrementalHandleReset` at `0x18006f5cb`
- `RPCRT4!MesIncrementalHandleReset` at `0x18006f5cb`
- `RPCRT4!NdrMesTypeEncode3` at `0x18006f610`
- `RPCRT4!NdrMesTypeEncode3` at `0x18006f610`
- `RPCRT4!NdrMesTypeAlignSize3` at `0x18006f581`
- `RPCRT4!NdrMesTypeAlignSize3` at `0x18006f581`
- `RPCRT4!MesHandleFree` at `0x18006f651`
- `RPCRT4!MesHandleFree` at `0x18006f651`
- `RPCRT4!MesEncodeIncrementalHandleCreate` at `0x18006f53e`
- `RPCRT4!MesEncodeIncrementalHandleCreate` at `0x18006f53e`

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
                &pPicklingInfo,
                &pProxyInfo,
                (const unsigned int **)&ArrTypeOffset,
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
      NdrMesTypeEncode3(Handle, &pPicklingInfo, &pProxyInfo, (const unsigned int **)&ArrTypeOffset, 2u, &pObject);
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
0x18006f4f4  mov     rax, rsp
0x18006f4f7  mov     [rax+10h], rbx
0x18006f4fb  mov     [rax+18h], rsi
0x18006f4ff  mov     [rax+8], rcx
0x18006f503  push    rdi
0x18006f504  push    r14
0x18006f506  push    r15
0x18006f508  sub     rsp, 50h
0x18006f50c  mov     r14, r8
0x18006f50f  mov     r15, rdx
0x18006f512  mov     qword ptr [rax+20h], 0
0x18006f51a  xorps   xmm0, xmm0
0x18006f51d  movups  xmmword ptr [rax-28h], xmm0
0x18006f521  xor     edi, edi
0x18006f523  mov     [rsp+68h+var_30], rdi
0x18006f528  lea     r9, [rax+20h]; pHandle
0x18006f52c  lea     r8, ?destroy@?$__func@V_lambda_8db0ce862824541f40dfb767113f1e28_@@$$A6A_NPEAX_K01I@Z@__function@wistd@@UEAAXXZ; WriteFn
0x18006f533  lea     rdx, ?PacReadFcn@@YAXPEAXPEAPEADPEAI@Z; AllocFn
0x18006f53a  lea     rcx, [rax-28h]; UserState
0x18006f53e  call    cs:__imp_MesEncodeIncrementalHandleCreate
0x18006f544  test    eax, eax
0x18006f546  jz      short loc_18006F552
0x18006f548  mov     ebx, 0C000009Ah
0x18006f54d  jmp     loc_18006F637
0x18006f552  lea     rax, [rsp+68h+arg_0]
0x18006f557  mov     [rsp+68h+pObject], rax; pObject
0x18006f55c  mov     [rsp+68h+nTypeIndex], 2; nTypeIndex
0x18006f564  lea     r9, ArrTypeOffset; ArrTypeOffset
0x18006f56b  lea     r8, pProxyInfo; pProxyInfo
0x18006f572  lea     rdx, pPicklingInfo; pPicklingInfo
0x18006f579  mov     rcx, [rsp+68h+Handle]; Handle
0x18006f581  call    cs:__imp_NdrMesTypeAlignSize3
0x18006f587  mov     [rsp+68h+var_38], eax
0x18006f58b  add     eax, 7
0x18006f58e  and     eax, 0FFFFFFF8h
0x18006f591  mov     esi, eax
0x18006f593  mov     ecx, eax; size
0x18006f595  call    MIDL_user_allocate
0x18006f59a  mov     rdi, rax
0x18006f59d  mov     [rsp+68h+var_30], rax
0x18006f5a2  test    rax, rax
0x18006f5a5  jz      short loc_18006F548
0x18006f5a7  xor     ebx, ebx
0x18006f5a9  mov     [rsp+68h+var_20], esi
0x18006f5ad  mov     [rsp+68h+var_28], rax
0x18006f5b2  mov     dword ptr [rsp+68h+pObject], ebx; Operation
0x18006f5b6  mov     qword ptr [rsp+68h+nTypeIndex], rbx; ReadFn
0x18006f5bb  xor     r9d, r9d; WriteFn
0x18006f5be  xor     r8d, r8d; AllocFn
0x18006f5c1  xor     edx, edx; UserState
0x18006f5c3  mov     rcx, [rsp+68h+Handle]; Handle
0x18006f5cb  call    cs:__imp_MesIncrementalHandleReset
0x18006f5d1  test    eax, eax
0x18006f5d3  jz      short loc_18006F5E1
0x18006f5d5  mov     ecx, eax; Status
0x18006f5d7  call    cs:__imp_I_RpcMapWin32Status
0x18006f5dd  mov     ebx, eax
0x18006f5df  jmp     short loc_18006F637
0x18006f5e1  lea     rax, [rsp+68h+arg_0]
0x18006f5e6  mov     [rsp+68h+pObject], rax; pObject
0x18006f5eb  mov     [rsp+68h+nTypeIndex], 2; nTypeIndex
0x18006f5f3  lea     r9, ArrTypeOffset; ArrTypeOffset
0x18006f5fa  lea     r8, pProxyInfo; pProxyInfo
0x18006f601  lea     rdx, pPicklingInfo; pPicklingInfo
0x18006f608  mov     rcx, [rsp+68h+Handle]; Handle
0x18006f610  call    cs:__imp_NdrMesTypeEncode3
0x18006f616  nop
0x18006f617  mov     [r15], rdi
0x18006f61a  mov     [r14], esi
0x18006f61d  xor     edi, edi
0x18006f61f  jmp     short loc_18006F637
0x18006f621  mov     ebx, 0C000000Dh
0x18006f626  mov     rdi, [rsp+68h+var_30]
0x18006f62b  jmp     short loc_18006F637
0x18006f62d  mov     ebx, 0C000000Dh
0x18006f632  mov     rdi, [rsp+68h+var_30]
0x18006f637  test    rdi, rdi
0x18006f63a  jz      short loc_18006F644
0x18006f63c  mov     rcx, rdi; void *
0x18006f63f  call    MIDL_user_free
0x18006f644  mov     rcx, [rsp+68h+Handle]; Handle
0x18006f64c  test    rcx, rcx
0x18006f64f  jz      short loc_18006F657
0x18006f651  call    cs:__imp_MesHandleFree
0x18006f657  mov     eax, ebx
0x18006f659  lea     r11, [rsp+68h+var_18]
0x18006f65e  mov     rbx, [r11+28h]
0x18006f662  mov     rsi, [r11+30h]
0x18006f666  mov     rsp, r11
0x18006f669  pop     r15
0x18006f66b  pop     r14
0x18006f66d  pop     rdi
0x18006f66e  retn
```
