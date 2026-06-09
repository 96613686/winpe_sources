# RpcDSSRemoveExpiredTokens

- ea: `0x180007800`
- end: `0x180007866`
- name: `RpcDSSRemoveExpiredTokens`
- size: `102`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callees

- `0x180006f78`
- `0x180007800`
- `0x18000bf80`
- `0x18000c100`
- `0x18000c12c`
- `0x18000d68c`

## string_xrefs

- `0x18000780b`: `DSSRemoveExpiredTokens started.`
- `0x180007826`: `DSSRemoveExpiredTokens finished.`
- `0x18000784f`: `RpcDSSRemoveExpiredTokens`

## pseudocode

```c
__int64 __fastcall RpcDSSRemoveExpiredTokens(__int64 a1)
{
  int *v1; // rax
  int v2; // ebx
  __int64 v3; // rcx
  int *v4; // rax
  __int64 v5; // rcx
  int *v6; // rax
  int v8; // [rsp+20h] [rbp-18h]

  v1 = tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get(a1);
  DSLogger::LogServiceApiStarted((DSLogger *)v1, L"DSSRemoveExpiredTokens started.");
  v2 = DSSRemoveExpiredTokens();
  v4 = tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get(v3);
  DSLogger::LogServiceApiCompleted((DSLogger *)v4, L"DSSRemoveExpiredTokens finished.");
  if ( v2 < 0 )
  {
    v6 = tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get(v5);
    v8 = v2;
    DSLogger::LogError((DSLogger *)v6, L"RpcDSSRemoveExpiredTokens", 357, L"hr=0x%x.", v8);
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x180007800  push    rbx
0x180007802  sub     rsp, 30h
0x180007806  call    ?get@?$_LazyImpl@VDSLogger@@V?$lazy_construct@VDSLogger@@@tlx@@V?$static_lazy@VDSLogger@@$0A@V?$lazy_construct@VDSLogger@@@tlx@@@3@@tlx@@QEAAAEAVDSLogger@@XZ; tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get(void)
0x18000780b  lea     rdx, aDssremoveexpir_0; "DSSRemoveExpiredTokens started."
0x180007812  mov     rcx, rax; this
0x180007815  call    ?LogServiceApiStarted@DSLogger@@QEAAXPEBG@Z; DSLogger::LogServiceApiStarted(ushort const *)
0x18000781a  call    ?DSSRemoveExpiredTokens@@YAJXZ; DSSRemoveExpiredTokens(void)
0x18000781f  mov     ebx, eax
0x180007821  call    ?get@?$_LazyImpl@VDSLogger@@V?$lazy_construct@VDSLogger@@@tlx@@V?$static_lazy@VDSLogger@@$0A@V?$lazy_construct@VDSLogger@@@tlx@@@3@@tlx@@QEAAAEAVDSLogger@@XZ; tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get(void)
0x180007826  lea     rdx, aDssremoveexpir; "DSSRemoveExpiredTokens finished."
0x18000782d  mov     rcx, rax; this
0x180007830  call    ?LogServiceApiCompleted@DSLogger@@QEAAXPEBG@Z; DSLogger::LogServiceApiCompleted(ushort const *)
0x180007835  test    ebx, ebx
0x180007837  jns     short loc_18000785E
0x180007839  call    ?get@?$_LazyImpl@VDSLogger@@V?$lazy_construct@VDSLogger@@@tlx@@V?$static_lazy@VDSLogger@@$0A@V?$lazy_construct@VDSLogger@@@tlx@@@3@@tlx@@QEAAAEAVDSLogger@@XZ; tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get(void)
0x18000783e  lea     r9, aHr0xX; "hr=0x%x."
0x180007845  mov     [rsp+38h+var_18], ebx
0x180007849  mov     r8d, 165h; unsigned int
0x18000784f  lea     rdx, aRpcdssremoveex; "RpcDSSRemoveExpiredTokens"
0x180007856  mov     rcx, rax; this
0x180007859  call    ?LogError@DSLogger@@QEAAXPEBGK0ZZ; DSLogger::LogError(ushort const *,ulong,ushort const *,...)
0x18000785e  mov     eax, ebx
0x180007860  add     rsp, 30h
0x180007864  pop     rbx
0x180007865  retn
```
