# RegistryChangeCallback

- ea: `0x18000da20`
- end: `0x18000db42`
- name: `RegistryChangeCallback`
- size: `290`
- prototype: `void __fastcall(PTP_CALLBACK_INSTANCE Instance, _QWORD *Context, PTP_WAIT Wait, __int64 WaitResult)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, service_task`

## callees

- `0x18000da20`
- `0x18000e43c`
- `0x18000e478`
- `0x180019010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18000da5d`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18000da5d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000dae6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000dae6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000da71`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000da71`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18000db02`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18000db02`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000daab`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000daab`
- `api-ms-win-core-registry-l1-1-0!RegNotifyChangeKeyValue` at `0x18000dad6`
- `api-ms-win-core-registry-l1-1-0!RegNotifyChangeKeyValue` at `0x18000dad6`

## string_xrefs

- `0x18000da9d`: `System\CurrentControlSet\Services\IpxlatCfgSvc`
- `0x18000da46`: `Calling local registry change callback`
- `0x18000db0e`: `Failed to re-register for registry change notification`

## pseudocode

```c
void __fastcall RegistryChangeCallback(
        PTP_CALLBACK_INSTANCE Instance,
        _QWORD *Context,
        PTP_WAIT Wait,
        __int64 WaitResult)
{
  struct _RTL_CRITICAL_SECTION *v5; // rsi
  PHKEY v6; // rcx
  PHKEY phkResult; // rax
  unsigned __int16 v8; // ax
  LSTATUS v9; // edi

  if ( !::phkResult )
    return;
  IPxlatPolicyMgrLogger::LogInfo(
    (IPxlatPolicyMgrLogger *)(::phkResult + 15),
    L"Calling local registry change callback",
    Wait,
    WaitResult);
  ResetEvent(::phkResult[6]);
  v5 = (struct _RTL_CRITICAL_SECTION *)(::phkResult + 10);
  EnterCriticalSection((LPCRITICAL_SECTION)::phkResult + 2);
  v6 = ::phkResult;
  phkResult = ::phkResult + 5;
  if ( ::phkResult[5] )
    goto LABEL_5;
  *phkResult = 0;
  v8 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"System\\CurrentControlSet\\Services\\IpxlatCfgSvc", 0, 0x20019u, phkResult);
  v9 = v8;
  if ( !v8 )
  {
    v6 = ::phkResult;
LABEL_5:
    v9 = RegNotifyChangeKeyValue(v6[5], 1, 0x10000007u, v6[6], 1);
  }
  if ( v5 )
    LeaveCriticalSection(v5);
  if ( v9 )
    IPxlatPolicyMgrLogger::LogError(
      (IPxlatPolicyMgrLogger *)(::phkResult + 15),
      v9,
      L"Failed to re-register for registry change notification");
  else
    SetThreadpoolWait((PTP_WAIT)::phkResult[7], ::phkResult[6], 0);
  if ( Context )
  {
    if ( *Context )
      ((void (__fastcall *)(_QWORD))*Context)(Context[1]);
  }
}

```

## disassembly

```asm
0x18000da20  mov     [rsp+arg_0], rbx
0x18000da25  mov     [rsp+arg_8], rsi
0x18000da2a  push    rdi
0x18000da2b  sub     rsp, 30h
0x18000da2f  mov     rcx, cs:phkResult
0x18000da36  mov     rbx, rdx
0x18000da39  test    rcx, rcx
0x18000da3c  jz      loc_18000DB32
0x18000da42  add     rcx, 78h ; 'x'; this
0x18000da46  lea     rdx, aCallingLocalRe; "Calling local registry change callback"
0x18000da4d  call    ?LogInfo@IPxlatPolicyMgrLogger@@QEAAXPEBGZZ; IPxlatPolicyMgrLogger::LogInfo(ushort const *,...)
0x18000da52  mov     rcx, cs:phkResult
0x18000da59  mov     rcx, [rcx+30h]; hEvent
0x18000da5d  call    cs:__imp_ResetEvent
0x18000da63  mov     rsi, cs:phkResult
0x18000da6a  add     rsi, 50h ; 'P'
0x18000da6e  mov     rcx, rsi; lpCriticalSection
0x18000da71  call    cs:__imp_EnterCriticalSection
0x18000da77  mov     rcx, cs:phkResult
0x18000da7e  lea     rax, [rcx+28h]
0x18000da82  cmp     qword ptr [rax], 0
0x18000da86  jnz     short loc_18000DABF
0x18000da88  mov     r9d, 20019h; samDesired
0x18000da8e  mov     qword ptr [rax], 0
0x18000da95  xor     r8d, r8d; ulOptions
0x18000da98  mov     [rsp+38h+phkResult], rax; phkResult
0x18000da9d  lea     rdx, SubKey; "System\\CurrentControlSet\\Services\\Ip"...
0x18000daa4  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000daab  call    cs:__imp_RegOpenKeyExW
0x18000dab1  movzx   edi, ax
0x18000dab4  test    edi, edi
0x18000dab6  jnz     short loc_18000DADE
0x18000dab8  mov     rcx, cs:phkResult
0x18000dabf  mov     r9, [rcx+30h]; hEvent
0x18000dac3  mov     edx, 1; bWatchSubtree
0x18000dac8  mov     rcx, [rcx+28h]; hKey
0x18000dacc  mov     r8d, 10000007h; dwNotifyFilter
0x18000dad2  mov     dword ptr [rsp+38h+phkResult], edx; fAsynchronous
0x18000dad6  call    cs:__imp_RegNotifyChangeKeyValue
0x18000dadc  mov     edi, eax
0x18000dade  test    rsi, rsi
0x18000dae1  jz      short loc_18000DAEC
0x18000dae3  mov     rcx, rsi; lpCriticalSection
0x18000dae6  call    cs:__imp_LeaveCriticalSection
0x18000daec  mov     rcx, cs:phkResult
0x18000daf3  test    edi, edi
0x18000daf5  jnz     short loc_18000DB0A
0x18000daf7  mov     rdx, [rcx+30h]; h
0x18000dafb  xor     r8d, r8d; pftTimeout
0x18000dafe  mov     rcx, [rcx+38h]; pwa
0x18000db02  call    cs:__imp_SetThreadpoolWait
0x18000db08  jmp     short loc_18000DB1C
0x18000db0a  add     rcx, 78h ; 'x'; this
0x18000db0e  lea     r8, aFailedToReRegi; "Failed to re-register for registry chan"...
0x18000db15  mov     edx, edi; unsigned int
0x18000db17  call    ?LogError@IPxlatPolicyMgrLogger@@QEAAXIPEBGZZ; IPxlatPolicyMgrLogger::LogError(uint,ushort const *,...)
0x18000db1c  test    rbx, rbx
0x18000db1f  jz      short loc_18000DB32
0x18000db21  mov     rax, [rbx]
0x18000db24  test    rax, rax
0x18000db27  jz      short loc_18000DB32
0x18000db29  mov     rcx, [rbx+8]
0x18000db2d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000db32  mov     rbx, [rsp+38h+arg_0]
0x18000db37  mov     rsi, [rsp+38h+arg_8]
0x18000db3c  add     rsp, 30h
0x18000db40  pop     rdi
0x18000db41  retn
```
