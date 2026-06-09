# CreateRemoteHandler

- ea: `0x180097b50`
- end: `0x180097cf8`
- name: `CreateRemoteHandler`
- size: `424`
- prototype: `HRESULT __fastcall(const _GUID *rclsid, IUnknown *pUnkOuter, const _GUID *ppv, void **flags, unsigned int fComOuterObject, int *fOle1Server, int *rclsid)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18002b1b4`

## callees

- `0x180075a58`
- `0x180097b50`
- `0x1800ce010`

## import_xrefs

- `api-ms-win-core-com-private-l1-1-0!InternalCreateIdentityHandler` at `0x180097c64`
- `api-ms-win-core-com-private-l1-1-0!InternalCreateIdentityHandler` at `0x180097c64`
- `api-ms-win-core-com-private-l1-3-1!CoIsOle1Class` at `0x180097b8e`
- `api-ms-win-core-com-private-l1-3-1!CoIsOle1Class` at `0x180097b8e`
- `api-ms-win-core-com-private-l1-1-1!InternalCStdIdentityGetIProxyManager` at `0x180097cc3`
- `api-ms-win-core-com-private-l1-1-1!InternalCStdIdentityGetIProxyManager` at `0x180097cc3`
- `api-ms-win-core-com-private-l1-1-1!InternalCStdIdentityUpdateFlags` at `0x180097cb8`
- `api-ms-win-core-com-private-l1-1-1!InternalCStdIdentityUpdateFlags` at `0x180097cb8`
- `api-ms-win-core-com-private-l1-1-1!InternalCStdIdentityGetInternalUnk` at `0x180097c93`
- `api-ms-win-core-com-private-l1-1-1!InternalCStdIdentityGetInternalUnk` at `0x180097c93`

## pseudocode

```c
__int64 __fastcall CreateRemoteHandler(
        const _GUID *rclsid,
        IUnknown *pUnkOuter,
        _GUID *ppv,
        void **flags,
        __int16 fComOuterObject,
        int *fOle1Server,
        int *rclsid_0)
{
  int *v7; // r15
  int *v9; // rdi
  struct _TEB *v12; // rax
  int v13; // ebx
  IUnknown *v14; // rax
  IUnknown *v15; // rdi
  void *InternalUnk; // rax
  __int64 IProxyManager; // rax
  int v19; // [rsp+30h] [rbp-28h]
  CStdIdentity *pStdId; // [rsp+70h] [rbp+18h] BYREF

  pStdId = (CStdIdentity *)ppv;
  v7 = fOle1Server;
  v9 = rclsid_0;
  *fOle1Server = 0;
  *v9 = 0;
  if ( CoIsOle1Class(rclsid) )
  {
    v12 = NtCurrentTeb();
    *v9 = 1;
    if ( (*((_BYTE *)v12->ReservedForOle + 20) & 0x40) != 0 )
    {
      return (unsigned int)-2147467242;
    }
    else
    {
      if ( (*((_BYTE *)NtCurrentTeb()->ReservedForOle + 20) & 0x40) != 0 )
        return (unsigned int)-2147024882;
      v14 = CDdeObject::Create(pUnkOuter, rclsid, 2u, 0, 0, 0, v19);
      if ( (v15 = v14) == 0 )
      {
        return (unsigned int)-2147024882;
      }
      else
      {
        v13 = ((__int64 (__fastcall *)(IUnknown *, GUID *, void **))v14->lpVtbl->QueryInterface)(
                v14,
                &IID_IUnknown,
                flags);
        ((void (__fastcall *)(IUnknown *))v15->lpVtbl->Release)(v15);
      }
    }
  }
  else
  {
    pStdId = 0;
    if ( (fComOuterObject & 0x200) != 0 || (fComOuterObject & 0x2000) == 0 )
    {
      v13 = ((__int64 (__fastcall *)(IUnknown *, GUID *, CStdIdentity **))pUnkOuter->lpVtbl->QueryInterface)(
              pUnkOuter,
              &IID_IStdIdentity,
              &pStdId);
      if ( v13 >= 0 )
      {
        InternalUnk = (void *)InternalCStdIdentityGetInternalUnk(pStdId);
        *flags = InternalUnk;
        (*(void (__fastcall **)(void *))(*(_QWORD *)InternalUnk + 8LL))(InternalUnk);
        InternalCStdIdentityUpdateFlags(pStdId, 1025);
        IProxyManager = InternalCStdIdentityGetIProxyManager(pStdId);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)IProxyManager + 16LL))(IProxyManager);
        *v7 = 1;
      }
    }
    else
    {
      return (unsigned int)InternalCreateIdentityHandler(pUnkOuter, &IID_IUnknown, flags);
    }
  }
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x180097b50  mov     [rsp+arg_0], rbx
0x180097b55  mov     [rsp+arg_8], rsi
0x180097b5a  mov     [rsp+pStdId], r8
0x180097b5f  push    rdi
0x180097b60  push    r14
0x180097b62  push    r15
0x180097b64  sub     rsp, 40h
0x180097b68  mov     r15, [rsp+58h+arg_28]
0x180097b70  mov     r14, ppv
0x180097b73  mov     rdi, [rsp+58h+rclsid_0]
0x180097b7b  mov     rbx, pUnkOuter
0x180097b7e  mov     rsi, rclsid
0x180097b81  mov     dword ptr [r15], 0
0x180097b88  mov     dword ptr [rdi], 0
0x180097b8e  call    cs:__imp_CoIsOle1Class
0x180097b94  test    eax, eax
0x180097b96  jz      loc_180097C34
0x180097b9c  mov     rax, gs:30h
0x180097ba5  mov     dword ptr [rdi], 1
0x180097bab  mov     rclsid, [rax+1758h]
0x180097bb2  test    byte ptr [rclsid+14h], 40h
0x180097bb6  jz      short loc_180097BC2
0x180097bb8  mov     ebx, 80004016h
0x180097bbd  jmp     loc_180097CE2
0x180097bc2  mov     rax, gs:30h
0x180097bcb  mov     rclsid, [rax+1758h]
0x180097bd2  test    byte ptr [rclsid+14h], 40h
0x180097bd6  jnz     short loc_180097C2A
0x180097bd8  xor     r9d, r9d; aTopic
0x180097bdb  mov     pUnkOuter, rsi; clsid
0x180097bde  mov     [rsp+58h+ppdde], ppv; ppdde
0x180097be3  mov     rclsid, rbx; pUnkOuter
0x180097be6  mov     [rsp+58h+szItem], ppv; szItem
0x180097beb  lea     r8d, [ppv+2]; ulObjType
0x180097bef  call    ?Create@CDdeObject@@SAPEAUIUnknown@@PEAU2@AEBU_GUID@@KGPEAGPEAPEAV1@H@Z; CDdeObject::Create(IUnknown *,_GUID const &,ulong,ushort,ushort *,CDdeObject * *,int)
0x180097bf4  mov     rdi, rax
0x180097bf7  test    rax, rax
0x180097bfa  jz      short loc_180097C2A
0x180097bfc  mov     rclsid, [rax]
0x180097bff  lea     pUnkOuter, IID_IUnknown
0x180097c06  mov     r8, r14
0x180097c09  mov     rax, [rclsid]
0x180097c0c  mov     rclsid, rdi
0x180097c0f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180097c14  mov     rclsid, [rdi]
0x180097c17  mov     ebx, eax
0x180097c19  mov     rax, [rclsid+10h]
0x180097c1d  mov     rclsid, rdi
0x180097c20  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180097c25  jmp     loc_180097CE2
0x180097c2a  mov     ebx, 8007000Eh
0x180097c2f  jmp     loc_180097CE2
0x180097c34  test    dword ptr [rsp+58h+arg_20], 200h
0x180097c3f  mov     [rsp+58h+pStdId], 0
0x180097c48  jnz     short loc_180097C6E
0x180097c4a  test    dword ptr [rsp+58h+arg_20], 2000h
0x180097c55  jz      short loc_180097C6E
0x180097c57  mov     r8, r14
0x180097c5a  lea     pUnkOuter, IID_IUnknown
0x180097c61  mov     rclsid, rbx
0x180097c64  call    cs:__imp_InternalCreateIdentityHandler
0x180097c6a  mov     ebx, eax
0x180097c6c  jmp     short loc_180097CE2
0x180097c6e  mov     rax, [rbx]
0x180097c71  lea     r8, [rsp+58h+pStdId]
0x180097c76  lea     pUnkOuter, IID_IStdIdentity
0x180097c7d  mov     rclsid, rbx
0x180097c80  mov     rax, [rax]
0x180097c83  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180097c88  mov     ebx, eax
0x180097c8a  test    eax, eax
0x180097c8c  js      short loc_180097CE2
0x180097c8e  mov     rclsid, [rsp+58h+pStdId]
0x180097c93  call    cs:__imp_InternalCStdIdentityGetInternalUnk
0x180097c99  mov     [r14], rax
0x180097c9c  mov     pUnkOuter, rax
0x180097c9f  mov     rclsid, [rax]
0x180097ca2  mov     rax, [rclsid+8]
0x180097ca6  mov     rclsid, pUnkOuter
0x180097ca9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180097cae  mov     rclsid, [rsp+58h+pStdId]
0x180097cb3  mov     edx, 401h
0x180097cb8  call    cs:__imp_InternalCStdIdentityUpdateFlags
0x180097cbe  mov     rclsid, [rsp+58h+pStdId]
0x180097cc3  call    cs:__imp_InternalCStdIdentityGetIProxyManager
0x180097cc9  mov     pUnkOuter, rax
0x180097ccc  mov     rclsid, [rax]
0x180097ccf  mov     rax, [rclsid+10h]
0x180097cd3  mov     rclsid, pUnkOuter
0x180097cd6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180097cdb  mov     dword ptr [r15], 1
0x180097ce2  mov     rsi, [rsp+58h+arg_8]
0x180097ce7  mov     eax, ebx
0x180097ce9  mov     rbx, [rsp+58h+arg_0]
0x180097cee  add     rsp, 40h
0x180097cf2  pop     r15
0x180097cf4  pop     r14
0x180097cf6  pop     rdi
0x180097cf7  retn
```
