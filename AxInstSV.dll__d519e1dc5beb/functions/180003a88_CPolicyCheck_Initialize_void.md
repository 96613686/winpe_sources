# CPolicyCheck::Initialize(void)

- ea: `0x180003a88`
- end: `0x180003af3`
- name: `?Initialize@CPolicyCheck@@QEAAJXZ`
- size: `107`
- prototype: `__int64 __fastcall(CPolicyCheck *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18000c224`

## callees

- `0x180003a88`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180003ae0`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180003ae0`
- `ntdll!RtlInitializeResource` at `0x180003aa0`
- `ntdll!RtlInitializeResource` at `0x180003aa0`

## pseudocode

```c
__int64 __fastcall CPolicyCheck::Initialize(CPolicyCheck *this)
{
  RtlInitializeResource((PRTL_RESOURCE)((char *)this + 16));
  *((_DWORD *)this + 2) = 1;
  CoCreateInstance(&CLSID_InternetSecurityManager, 0, 1u, &IID_IInternetSecurityManager, (LPVOID *)this + 21);
  return 0;
}

```

## disassembly

```asm
0x180003a88  mov     [rsp+arg_8], rbx
0x180003a8d  mov     [rsp+arg_0], rcx
0x180003a92  push    rdi
0x180003a93  sub     rsp, 30h
0x180003a97  mov     rbx, rcx
0x180003a9a  xor     edi, edi
0x180003a9c  add     rcx, 10h; Resource
0x180003aa0  call    cs:__imp_RtlInitializeResource
0x180003aa6  mov     dword ptr [rbx+8], 1
0x180003aad  jmp     short loc_180003AC0
0x180003aaf  mov     rbx, [rsp+38h+arg_0]
0x180003ab4  mov     dword ptr [rbx+8], 0
0x180003abb  mov     edi, 80004005h
0x180003ac0  lea     rcx, [rbx+0A8h]
0x180003ac7  mov     [rsp+38h+ppv], rcx; ppv
0x180003acc  lea     r9, IID_IInternetSecurityManager; riid
0x180003ad3  xor     edx, edx; pUnkOuter
0x180003ad5  lea     r8d, [rdx+1]; dwClsContext
0x180003ad9  lea     rcx, CLSID_InternetSecurityManager; rclsid
0x180003ae0  call    cs:__imp_CoCreateInstance
0x180003ae6  mov     eax, edi
0x180003ae8  mov     rbx, [rsp+38h+arg_8]
0x180003aed  add     rsp, 30h
0x180003af1  pop     rdi
0x180003af2  retn
```
