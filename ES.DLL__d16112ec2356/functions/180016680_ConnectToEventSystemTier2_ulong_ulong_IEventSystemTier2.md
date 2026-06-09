# ConnectToEventSystemTier2(ulong,ulong,IEventSystemTier2 * *)

- ea: `0x180016680`
- end: `0x18001687c`
- name: `?ConnectToEventSystemTier2@@YAJKKPEAPEAUIEventSystemTier2@@@Z`
- size: `508`
- prototype: `__int64 __fastcall(DWORD dwImpLevel, DWORD dwCapabilities, struct IEventSystemTier2 **)`
- caller_count: `3`
- callee_count: `2`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180016548`
- `0x180017610`
- `0x18001c6c8`

## callees

- `0x180016680`
- `0x180046010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoGetClassObject` at `0x1800166d4`
- `api-ms-win-core-com-l1-1-0!CoGetClassObject` at `0x1800166d4`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x1800167ad`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x180016837`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x1800167ad`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x180016837`
- `api-ms-win-core-com-l1-1-0!CoCopyProxy` at `0x18001675b`
- `api-ms-win-core-com-l1-1-0!CoCopyProxy` at `0x1800167e2`
- `api-ms-win-core-com-l1-1-0!CoCopyProxy` at `0x18001675b`
- `api-ms-win-core-com-l1-1-0!CoCopyProxy` at `0x1800167e2`

## pseudocode

```c
__int64 __fastcall ConnectToEventSystemTier2(DWORD dwImpLevel, DWORD dwCapabilities, IUnknown **a3)
{
  DWORD v4; // edx
  HRESULT ClassObject; // ebx
  HRESULT v9; // eax
  IUnknown *v10; // rcx
  HRESULT v11; // eax
  IUnknown *v12; // rcx
  IUnknown *ppCopy[2]; // [rsp+40h] [rbp-10h] BYREF
  IUnknown *ppv; // [rsp+90h] [rbp+40h] BYREF
  IUnknown *pProxy; // [rsp+98h] [rbp+48h] BYREF

  v4 = 4;
  ppv = 0;
  pProxy = 0;
  if ( g_fRunningASService )
    v4 = 1;
  ClassObject = CoGetClassObject(
                  &CLSID_CEventSystemTier2,
                  v4,
                  0,
                  &GUID_64b8f404_a4ae_11d1_b7b6_00c04fb926af,
                  (LPVOID *)&ppv);
  if ( ClassObject < 0 )
    goto LABEL_4;
  if ( !g_fRunningASService )
  {
    ppCopy[0] = 0;
    v11 = CoCopyProxy(ppv, ppCopy);
    ClassObject = v11;
    if ( v11 < 0 )
    {
      if ( v11 == -2147467262 )
        goto LABEL_6;
    }
    else
    {
      ((void (__fastcall *)(IUnknown *))ppv->lpVtbl->Release)(ppv);
      v12 = ppCopy[0];
      ppv = ppCopy[0];
      ppCopy[0] = 0;
      ClassObject = CoSetProxyBlanket(
                      v12,
                      0xFFFFFFFF,
                      0xFFFFFFFF,
                      (OLECHAR *)0xFFFFFFFFFFFFFFFFLL,
                      0,
                      2u,
                      (RPC_AUTH_IDENTITY_HANDLE)0xFFFFFFFFFFFFFFFFLL,
                      0x800u);
      if ( ClassObject >= 0 )
        goto LABEL_6;
    }
    ((void (__fastcall *)(IUnknown *))ppv->lpVtbl->Release)(ppv);
    goto LABEL_4;
  }
LABEL_6:
  ClassObject = ((__int64 (__fastcall *)(IUnknown *, const WCHAR *, GUID *, IUnknown **))ppv->lpVtbl[1].Release)(
                  ppv,
                  L"{26c409cc-ae86-11d1-b616-00805fc79216}",
                  &IID_IEventSystemTier2,
                  &pProxy);
  ((void (__fastcall *)(IUnknown *))ppv->lpVtbl->Release)(ppv);
  ppv = 0;
  if ( ClassObject >= 0 && !g_fRunningASService )
  {
    ppCopy[0] = 0;
    v9 = CoCopyProxy(pProxy, ppCopy);
    ClassObject = v9;
    if ( v9 < 0 )
    {
      if ( v9 == -2147467262 )
      {
        ClassObject = 0;
        goto LABEL_4;
      }
    }
    else
    {
      ((void (__fastcall *)(IUnknown *))pProxy->lpVtbl->Release)(pProxy);
      v10 = ppCopy[0];
      pProxy = ppCopy[0];
      ppCopy[0] = 0;
      ClassObject = CoSetProxyBlanket(
                      v10,
                      0xFFFFFFFF,
                      0xFFFFFFFF,
                      (OLECHAR *)0xFFFFFFFFFFFFFFFFLL,
                      0,
                      dwImpLevel,
                      (RPC_AUTH_IDENTITY_HANDLE)0xFFFFFFFFFFFFFFFFLL,
                      dwCapabilities);
      if ( ClassObject >= 0 )
        goto LABEL_4;
    }
    ((void (__fastcall *)(IUnknown *))pProxy->lpVtbl->Release)(pProxy);
    pProxy = 0;
  }
LABEL_4:
  *a3 = pProxy;
  return (unsigned int)ClassObject;
}

```

## disassembly

```asm
0x180016680  mov     [rsp-28h+arg_0], rbx
0x180016685  push    rbp
0x180016686  push    rsi
0x180016687  push    rdi
0x180016688  push    r14
0x18001668a  push    r15
0x18001668c  mov     rbp, rsp
0x18001668f  sub     rsp, 50h
0x180016693  xor     r15d, r15d
0x180016696  lea     r9, _GUID_64b8f404_a4ae_11d1_b7b6_00c04fb926af; riid
0x18001669d  cmp     cs:g_fRunningASService, r15d
0x1800166a4  mov     esi, edx
0x1800166a6  mov     edx, 4
0x1800166ab  mov     [rbp+arg_10], r15
0x1800166af  mov     eax, 1
0x1800166b4  mov     [rbp+pProxy], r15
0x1800166b8  cmovnz  edx, eax; dwClsContext
0x1800166bb  mov     rdi, r8
0x1800166be  lea     rax, [rbp+arg_10]
0x1800166c2  mov     r14d, ecx
0x1800166c5  xor     r8d, r8d; pvReserved
0x1800166c8  mov     [rsp+50h+ppv], rax; ppv
0x1800166cd  lea     rcx, CLSID_CEventSystemTier2; rclsid
0x1800166d4  call    cs:__imp_CoGetClassObject
0x1800166da  mov     ebx, eax
0x1800166dc  test    eax, eax
0x1800166de  jns     short loc_1800166FD
0x1800166e0  mov     rax, [rbp+pProxy]
0x1800166e4  mov     [rdi], rax
0x1800166e7  mov     eax, ebx
0x1800166e9  mov     rbx, [rsp+50h+arg_0]
0x1800166f1  add     rsp, 50h
0x1800166f5  pop     r15
0x1800166f7  pop     r14
0x1800166f9  pop     rdi
0x1800166fa  pop     rsi
0x1800166fb  pop     rbp
0x1800166fc  retn
0x1800166fd  cmp     cs:g_fRunningASService, r15d
0x180016704  jz      loc_1800167D6
0x18001670a  mov     rcx, [rbp+arg_10]
0x18001670e  lea     r9, [rbp+pProxy]
0x180016712  lea     r8, IID_IEventSystemTier2
0x180016719  lea     rdx, a26c409ccAe8611; "{26c409cc-ae86-11d1-b616-00805fc79216}"
0x180016720  mov     rax, [rcx]
0x180016723  mov     rax, [rax+28h]
0x180016727  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001672c  mov     rcx, [rbp+arg_10]
0x180016730  mov     ebx, eax
0x180016732  mov     rax, [rcx]
0x180016735  mov     rax, [rax+10h]
0x180016739  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001673e  mov     [rbp+arg_10], r15
0x180016742  test    ebx, ebx
0x180016744  js      short loc_1800166E0
0x180016746  cmp     cs:g_fRunningASService, r15d
0x18001674d  jnz     short loc_1800166E0
0x18001674f  mov     rcx, [rbp+pProxy]; pProxy
0x180016753  lea     rdx, [rbp+ppCopy]; ppCopy
0x180016757  mov     [rbp+ppCopy], r15
0x18001675b  call    cs:__imp_CoCopyProxy
0x180016761  mov     ebx, eax
0x180016763  test    eax, eax
0x180016765  js      loc_180016869
0x18001676b  mov     rcx, [rbp+pProxy]
0x18001676f  mov     rax, [rcx]
0x180016772  mov     rax, [rax+10h]
0x180016776  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001677b  mov     rcx, [rbp+ppCopy]; pProxy
0x18001677f  mov     edx, 0FFFFFFFFh; dwAuthnSvc
0x180016784  mov     [rsp+50h+dwCapabilities], esi; dwCapabilities
0x180016788  mov     r8d, edx; dwAuthzSvc
0x18001678b  mov     [rsp+50h+pAuthInfo], 0FFFFFFFFFFFFFFFFh; pAuthInfo
0x180016794  mov     r9, 0FFFFFFFFFFFFFFFFh; pServerPrincName
0x18001679b  mov     [rsp+50h+dwImpLevel], r14d; dwImpLevel
0x1800167a0  mov     [rbp+pProxy], rcx
0x1800167a4  mov     [rbp+ppCopy], r15
0x1800167a8  mov     dword ptr [rsp+50h+ppv], r15d; dwAuthnLevel
0x1800167ad  call    cs:__imp_CoSetProxyBlanket
0x1800167b3  mov     ebx, eax
0x1800167b5  test    eax, eax
0x1800167b7  jns     loc_1800166E0
0x1800167bd  mov     rcx, [rbp+pProxy]
0x1800167c1  mov     rax, [rcx]
0x1800167c4  mov     rax, [rax+10h]
0x1800167c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800167cd  mov     [rbp+pProxy], r15
0x1800167d1  jmp     loc_1800166E0
0x1800167d6  mov     rcx, [rbp+arg_10]; pProxy
0x1800167da  lea     rdx, [rbp+ppCopy]; ppCopy
0x1800167de  mov     [rbp+ppCopy], r15
0x1800167e2  call    cs:__imp_CoCopyProxy
0x1800167e8  mov     ebx, eax
0x1800167ea  test    eax, eax
0x1800167ec  js      short loc_180016849
0x1800167ee  mov     rcx, [rbp+arg_10]
0x1800167f2  mov     rax, [rcx]
0x1800167f5  mov     rax, [rax+10h]
0x1800167f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800167fe  mov     rcx, [rbp+ppCopy]; pProxy
0x180016802  mov     edx, 0FFFFFFFFh; dwAuthnSvc
0x180016807  mov     [rsp+50h+dwCapabilities], 800h; dwCapabilities
0x18001680f  mov     r8d, edx; dwAuthzSvc
0x180016812  mov     [rsp+50h+pAuthInfo], 0FFFFFFFFFFFFFFFFh; pAuthInfo
0x18001681b  mov     r9, 0FFFFFFFFFFFFFFFFh; pServerPrincName
0x180016822  mov     [rsp+50h+dwImpLevel], 2; dwImpLevel
0x18001682a  mov     [rbp+arg_10], rcx
0x18001682e  mov     [rbp+ppCopy], r15
0x180016832  mov     dword ptr [rsp+50h+ppv], r15d; dwAuthnLevel
0x180016837  call    cs:__imp_CoSetProxyBlanket
0x18001683d  mov     ebx, eax
0x18001683f  test    eax, eax
0x180016841  jns     loc_18001670A
0x180016847  jmp     short loc_180016854
0x180016849  cmp     eax, 80004002h
0x18001684e  jz      loc_18001670A
0x180016854  mov     rcx, [rbp+arg_10]
0x180016858  mov     rax, [rcx]
0x18001685b  mov     rax, [rax+10h]
0x18001685f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016864  jmp     loc_1800166E0
0x180016869  cmp     eax, 80004002h
0x18001686e  jnz     loc_1800167BD
0x180016874  mov     ebx, r15d
0x180016877  jmp     loc_1800166E0
```
