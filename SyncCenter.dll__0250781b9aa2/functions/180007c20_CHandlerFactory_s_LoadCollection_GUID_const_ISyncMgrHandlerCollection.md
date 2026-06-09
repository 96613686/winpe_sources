# CHandlerFactory::s_LoadCollection(_GUID const &,ISyncMgrHandlerCollection * *)

- ea: `0x180007c20`
- end: `0x180007d29`
- name: `?s_LoadCollection@CHandlerFactory@@SAJAEBU_GUID@@PEAPEAUISyncMgrHandlerCollection@@@Z`
- size: `265`
- prototype: `__int64 __fastcall(IID *rclsid, struct ISyncMgrHandlerCollection **)`
- caller_count: `4`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800063f0`
- `0x180007964`
- `0x180016374`
- `0x180024854`

## callees

- `0x180005e00`
- `0x180007c20`
- `0x180012c9c`
- `0x180012e08`
- `0x180024598`
- `0x180053010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180007ca0`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180007d0f`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180007ca0`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180007d0f`

## pseudocode

```c
__int64 __fastcall CHandlerFactory::s_LoadCollection(IID *rclsid, struct ISyncMgrHandlerCollection **a2)
{
  HRESULT v5; // ebx
  LPVOID ppv; // [rsp+50h] [rbp+18h] BYREF

  if ( *(_OWORD *)rclsid == *(_OWORD *)&GUID_NULL )
    return (unsigned int)CSyncStaticHandlerCollection_CreateInstance(0, (const struct _GUID *)a2, (void **)a2);
  if ( !CClassHandlerKeys::ShouldIsolate(rclsid) )
    return (unsigned int)CoCreateInstance(rclsid, 0, 0x15u, &GUID_a7f337a3_d20b_45cb_9ed7_87d094ca5045, (LPVOID *)a2);
  v5 = RequestingIsolationServerStartup();
  if ( v5 >= 0 )
  {
    ppv = 0;
    v5 = CoCreateInstance(&CLSID_SyncMgrIsolationCollection, 0, 4u, &GUID_1a0e696d_2797_425c_83da_11690e066f95, &ppv);
    if ( v5 >= 0 )
    {
      v5 = (*(__int64 (__fastcall **)(LPVOID, IID *))(*(_QWORD *)ppv + 40LL))(ppv, rclsid);
      if ( v5 >= 0 )
        v5 = (**(__int64 (__fastcall ***)(LPVOID, GUID *, struct ISyncMgrHandlerCollection **))ppv)(
               ppv,
               &GUID_a7f337a3_d20b_45cb_9ed7_87d094ca5045,
               a2);
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
    }
    IsolationServerStartupCompleted();
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180007c20  mov     [rsp+arg_0], rbx
0x180007c25  mov     [rsp+arg_8], rsi
0x180007c2a  push    rdi
0x180007c2b  sub     rsp, 30h
0x180007c2f  mov     rax, [rcx]
0x180007c32  mov     rsi, rdx
0x180007c35  cmp     rax, qword ptr cs:GUID_NULL.Data1
0x180007c3c  mov     rdi, rcx
0x180007c3f  jnz     short loc_180007C5D
0x180007c41  mov     rax, [rcx+8]
0x180007c45  cmp     rax, qword ptr cs:GUID_NULL.Data4
0x180007c4c  jnz     short loc_180007C5D
0x180007c4e  mov     r8, rdx; void **
0x180007c51  xor     ecx, ecx; bool
0x180007c53  call    ?CSyncStaticHandlerCollection_CreateInstance@@YAJ_NAEBU_GUID@@PEAPEAX@Z; CSyncStaticHandlerCollection_CreateInstance(bool,_GUID const &,void * *)
0x180007c58  jmp     loc_180007D15
0x180007c5d  call    ?ShouldIsolate@CClassHandlerKeys@@SA_NAEBU_GUID@@@Z; CClassHandlerKeys::ShouldIsolate(_GUID const &)
0x180007c62  test    al, al
0x180007c64  jz      loc_180007CFA
0x180007c6a  call    ?RequestingIsolationServerStartup@@YAJXZ; RequestingIsolationServerStartup(void)
0x180007c6f  mov     ebx, eax
0x180007c71  test    eax, eax
0x180007c73  js      loc_180007D17
0x180007c79  xor     edx, edx; pUnkOuter
0x180007c7b  mov     [rsp+38h+arg_10], 0
0x180007c84  lea     rax, [rsp+38h+arg_10]
0x180007c89  lea     r9, _GUID_1a0e696d_2797_425c_83da_11690e066f95; riid
0x180007c90  mov     [rsp+38h+ppv], rax; ppv
0x180007c95  lea     rcx, CLSID_SyncMgrIsolationCollection; rclsid
0x180007c9c  lea     r8d, [rdx+4]; dwClsContext
0x180007ca0  call    cs:__imp_CoCreateInstance
0x180007ca6  mov     ebx, eax
0x180007ca8  test    eax, eax
0x180007caa  js      short loc_180007CF3
0x180007cac  mov     rcx, [rsp+38h+arg_10]
0x180007cb1  mov     rdx, rdi
0x180007cb4  mov     rax, [rcx]
0x180007cb7  mov     rax, [rax+28h]
0x180007cbb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007cc0  mov     ebx, eax
0x180007cc2  test    eax, eax
0x180007cc4  js      short loc_180007CE2
0x180007cc6  mov     rcx, [rsp+38h+arg_10]
0x180007ccb  lea     rdx, _GUID_a7f337a3_d20b_45cb_9ed7_87d094ca5045
0x180007cd2  mov     r8, rsi
0x180007cd5  mov     rax, [rcx]
0x180007cd8  mov     rax, [rax]
0x180007cdb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007ce0  mov     ebx, eax
0x180007ce2  mov     rcx, [rsp+38h+arg_10]
0x180007ce7  mov     rax, [rcx]
0x180007cea  mov     rax, [rax+10h]
0x180007cee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007cf3  call    ?IsolationServerStartupCompleted@@YAXXZ; IsolationServerStartupCompleted(void)
0x180007cf8  jmp     short loc_180007D17
0x180007cfa  xor     edx, edx; pUnkOuter
0x180007cfc  mov     [rsp+38h+ppv], rsi; ppv
0x180007d01  lea     r9, _GUID_a7f337a3_d20b_45cb_9ed7_87d094ca5045; riid
0x180007d08  mov     rcx, rdi; rclsid
0x180007d0b  lea     r8d, [rdx+15h]; dwClsContext
0x180007d0f  call    cs:__imp_CoCreateInstance
0x180007d15  mov     ebx, eax
0x180007d17  mov     rsi, [rsp+38h+arg_8]
0x180007d1c  mov     eax, ebx
0x180007d1e  mov     rbx, [rsp+38h+arg_0]
0x180007d23  add     rsp, 30h
0x180007d27  pop     rdi
0x180007d28  retn
```
