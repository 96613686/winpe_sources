# CallerIdentity::GetProcessAppIdWithAppResolverFallback(void *,ushort * *)

- ea: `0x180055dd0`
- end: `0x180055e87`
- name: `?GetProcessAppIdWithAppResolverFallback@CallerIdentity@@YAJPEAXPEAPEAG@Z`
- size: `183`
- prototype: `__int64 __fastcall(HANDLE Process, void *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180022958`

## callees

- `0x180055dd0`
- `0x180055e90`
- `0x180056464`
- `0x18005a010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x180055e34`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x180055e34`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180055e25`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180055e25`

## pseudocode

```c
__int64 __fastcall CallerIdentity::GetProcessAppIdWithAppResolverFallback(
        HANDLE Process,
        _QWORD *a2,
        unsigned __int16 **a3)
{
  int ProcessAppId; // ebx
  DWORD ProcessId; // eax
  LPVOID ppv; // [rsp+60h] [rbp+18h] BYREF

  ProcessAppId = CallerIdentity::GetProcessAppId(Process, a2, a3);
  if ( ProcessAppId < 0 )
  {
    ppv = 0;
    Microsoft::WRL::ComPtr<IApplicationResolver>::InternalRelease(&ppv);
    ProcessAppId = CoCreateInstance(
                     &GUID_660b90c8_73a9_4b58_8cae_355b7f55341b,
                     0,
                     3u,
                     &GUID_de25675a_72de_44b4_9373_05170450c140,
                     &ppv);
    if ( ProcessAppId >= 0 )
    {
      ProcessId = GetProcessId(Process);
      ProcessAppId = (*(__int64 (__fastcall **)(LPVOID, _QWORD, _QWORD *, _QWORD, _QWORD, _QWORD))(*(_QWORD *)ppv + 48LL))(
                       ppv,
                       ProcessId,
                       a2,
                       0,
                       0,
                       0);
    }
    Microsoft::WRL::ComPtr<IApplicationResolver>::InternalRelease(&ppv);
  }
  return (unsigned int)ProcessAppId;
}

```

## disassembly

```asm
0x180055dd0  mov     [rsp+arg_0], rbx
0x180055dd5  mov     [rsp+arg_8], rsi
0x180055dda  push    rdi
0x180055ddb  sub     rsp, 40h
0x180055ddf  mov     rdi, rdx
0x180055de2  mov     rsi, rcx
0x180055de5  call    ?GetProcessAppId@CallerIdentity@@YAJPEAXPEAPEAG@Z; CallerIdentity::GetProcessAppId(void *,ushort * *)
0x180055dea  mov     ebx, eax
0x180055dec  test    eax, eax
0x180055dee  jns     loc_180055E75
0x180055df4  lea     rcx, [rsp+48h+arg_10]
0x180055df9  mov     [rsp+48h+arg_10], 0
0x180055e02  call    ?InternalRelease@?$ComPtr@UIApplicationResolver@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IApplicationResolver>::InternalRelease(void)
0x180055e07  xor     edx, edx; pUnkOuter
0x180055e09  lea     rax, [rsp+48h+arg_10]
0x180055e0e  lea     r9, _GUID_de25675a_72de_44b4_9373_05170450c140; riid
0x180055e15  mov     [rsp+48h+ppv], rax; ppv
0x180055e1a  lea     rcx, _GUID_660b90c8_73a9_4b58_8cae_355b7f55341b; rclsid
0x180055e21  lea     r8d, [rdx+3]; dwClsContext
0x180055e25  call    cs:__imp_CoCreateInstance
0x180055e2b  mov     ebx, eax
0x180055e2d  test    eax, eax
0x180055e2f  js      short loc_180055E6B
0x180055e31  mov     rcx, rsi; Process
0x180055e34  call    cs:__imp_GetProcessId
0x180055e3a  mov     rcx, [rsp+48h+arg_10]
0x180055e3f  xor     r9d, r9d
0x180055e42  mov     r10d, eax
0x180055e45  mov     [rsp+48h+var_20], 0
0x180055e4e  mov     r8, rdi
0x180055e51  mov     [rsp+48h+ppv], 0
0x180055e5a  mov     rdx, [rcx]
0x180055e5d  mov     rax, [rdx+30h]
0x180055e61  mov     edx, r10d
0x180055e64  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055e69  mov     ebx, eax
0x180055e6b  lea     rcx, [rsp+48h+arg_10]
0x180055e70  call    ?InternalRelease@?$ComPtr@UIApplicationResolver@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IApplicationResolver>::InternalRelease(void)
0x180055e75  mov     rsi, [rsp+48h+arg_8]
0x180055e7a  mov     eax, ebx
0x180055e7c  mov     rbx, [rsp+48h+arg_0]
0x180055e81  add     rsp, 40h
0x180055e85  pop     rdi
0x180055e86  retn
```
