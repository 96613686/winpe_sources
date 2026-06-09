# AutoStubBias<Windows::Foundation::IAsyncOperation<Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus>>::~AutoStubBias<Windows::Foundation::IAsyncOperation<Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus>>(void)

- ea: `0x18000dafc`
- end: `0x18000db37`
- name: `??1?$AutoStubBias@U?$IAsyncOperation@W4AppCapabilityAccessStatus@AppCapabilityAccess@Authorization@Security@Windows@@@Foundation@Windows@@U?$IAsyncOperationCompletedHandler@W4AppCapabilityAccessStatus@AppCapabilityAccess@Authorization@Security@Windows@@@23@@@QEAA@XZ`
- size: `59`
- prototype: `__int64 __fastcall(int *)`
- caller_count: `5`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18000ff50`
- `0x18001024c`
- `0x180019810`
- `0x180020c0e`
- `0x180020c56`

## callees

- `0x180007630`
- `0x18000dafc`
- `0x180022010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoReleaseMarshalData` at `0x18000db24`
- `api-ms-win-core-com-l1-1-0!CoReleaseMarshalData` at `0x18000db24`

## pseudocode

```c
__int64 __fastcall AutoStubBias<Windows::Foundation::IAsyncOperation<enum Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus>,Windows::Foundation::IAsyncOperationCompletedHandler<enum Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus>>::~AutoStubBias<Windows::Foundation::IAsyncOperation<enum Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus>,Windows::Foundation::IAsyncOperationCompletedHandler<enum Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus>>(
        int *a1)
{
  if ( a1[2] >= 0 )
  {
    (*(void (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD))(**(_QWORD **)a1 + 40LL))(*(_QWORD *)a1, 0, 0, 0);
    CoReleaseMarshalData(*(LPSTREAM *)a1);
  }
  return Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(a1);
}

```

## disassembly

```asm
0x18000dafc  push    rbx
0x18000dafe  sub     rsp, 30h
0x18000db02  mov     rbx, rcx
0x18000db05  xor     edx, edx
0x18000db07  cmp     [rcx+8], edx
0x18000db0a  jl      short loc_18000DB2A
0x18000db0c  mov     rcx, [rcx]
0x18000db0f  mov     rax, [rcx]
0x18000db12  xor     r9d, r9d
0x18000db15  xor     r8d, r8d
0x18000db18  mov     rax, [rax+28h]
0x18000db1c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000db21  mov     rcx, [rbx]; pStm
0x18000db24  call    cs:__imp_CoReleaseMarshalData
0x18000db2a  mov     rcx, rbx
0x18000db2d  add     rsp, 30h
0x18000db31  pop     rbx
0x18000db32  jmp     ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
```
