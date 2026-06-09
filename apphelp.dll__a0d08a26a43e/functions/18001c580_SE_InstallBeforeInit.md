# SE_InstallBeforeInit

- ea: `0x18001c580`
- end: `0x18001c67e`
- name: `SE_InstallBeforeInit`
- size: `254`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callees

- `0x18000f114`
- `0x18001c580`
- `0x18001c684`
- `0x18001c73c`
- `0x18001e064`

## import_xrefs

- `ntdll!RtlLeaveCriticalSection` at `0x18001c61a`
- `ntdll!RtlLeaveCriticalSection` at `0x18001c61a`
- `ntdll!RtlEnterCriticalSection` at `0x18001c595`
- `ntdll!RtlEnterCriticalSection` at `0x18001c595`

## string_xrefs

- `0x18001c5f4`: `SE_InstallBeforeInit`
- `0x18001c637`: `SE_InstallBeforeInit`
- `0x18001c668`: `SE_InstallBeforeInit`
- `0x18001c5e7`: `Failed to validate loaded shim dlls`
- `0x18001c626`: `Failed to install hooks [%d]`
- `0x18001c65b`: `Required shim dll not loaded.  Some shims will be inactive.`

## pseudocode

```c
unsigned int SE_InstallBeforeInit()
{
  char v0; // bl
  __int64 v1; // rcx
  int v2; // eax
  unsigned int result; // eax
  int v4; // [rsp+40h] [rbp+8h] BYREF

  v4 = 0;
  if ( RtlEnterCriticalSection(&g_EngineLock) < 0 )
  {
    v0 = 0;
    result = (unsigned int)AslLogCallPrintf(1, "SE_InstallBeforeInit", 3138, "Failed to lock engine");
LABEL_8:
    g_InitState = 0;
    if ( !v0 )
      return result;
    return RtlLeaveCriticalSection(&g_EngineLock);
  }
  v0 = 1;
  if ( (int)SeShimManagerValidateShimDlls(&v4, *(_QWORD *)(g_Engine + 16), *(_QWORD *)(g_Engine + 40)) < 0 )
  {
    result = (unsigned int)AslLogCallPrintf(1, "SE_InstallBeforeInit", 3153, "Failed to validate loaded shim dlls");
    goto LABEL_8;
  }
  if ( !v4 )
    AslLogCallPrintf(2, "SE_InstallBeforeInit", 3158, "Required shim dll not loaded.  Some shims will be inactive.");
  v2 = SeEngineInstallHooks(v1);
  if ( v2 < 0 )
  {
    result = (unsigned int)AslLogCallPrintf(1, "SE_InstallBeforeInit", 3167, "Failed to install hooks [%d]", v2);
    goto LABEL_8;
  }
  g_InitState = 3;
  SeEngineDumpState();
  return RtlLeaveCriticalSection(&g_EngineLock);
}

```

## disassembly

```asm
0x18001c580  push    rbx
0x18001c582  sub     rsp, 30h
0x18001c586  lea     rcx, g_EngineLock; CriticalSection
0x18001c58d  mov     [rsp+38h+arg_0], 0
0x18001c595  call    cs:__imp_RtlEnterCriticalSection
0x18001c59b  test    eax, eax
0x18001c59d  js      loc_18001C64A
0x18001c5a3  mov     rdx, cs:g_Engine
0x18001c5aa  lea     rcx, [rsp+38h+arg_0]
0x18001c5af  mov     bl, 1
0x18001c5b1  mov     r8, [rdx+28h]
0x18001c5b5  mov     rdx, [rdx+10h]
0x18001c5b9  call    SeShimManagerValidateShimDlls
0x18001c5be  test    eax, eax
0x18001c5c0  js      short loc_18001C5E7
0x18001c5c2  cmp     [rsp+38h+arg_0], 0
0x18001c5c7  jz      loc_18001C65B
0x18001c5cd  call    SeEngineInstallHooks
0x18001c5d2  test    eax, eax
0x18001c5d4  js      short loc_18001C626
0x18001c5d6  mov     cs:g_InitState, 3
0x18001c5e0  call    SeEngineDumpState
0x18001c5e5  jmp     short loc_18001C613
0x18001c5e7  lea     r9, aFailedToValida; "Failed to validate loaded shim dlls"
0x18001c5ee  mov     r8d, 0C51h
0x18001c5f4  lea     rdx, aSeInstallbefor_0; "SE_InstallBeforeInit"
0x18001c5fb  mov     ecx, 1
0x18001c600  call    AslLogCallPrintf
0x18001c605  mov     cs:g_InitState, 0
0x18001c60f  test    bl, bl
0x18001c611  jz      short loc_18001C620
0x18001c613  lea     rcx, g_EngineLock; CriticalSection
0x18001c61a  call    cs:__imp_RtlLeaveCriticalSection
0x18001c620  add     rsp, 30h
0x18001c624  pop     rbx
0x18001c625  retn
0x18001c626  lea     r9, aFailedToInstal; "Failed to install hooks [%d]"
0x18001c62d  mov     [rsp+38h+var_18], eax
0x18001c631  mov     r8d, 0C5Fh
0x18001c637  lea     rdx, aSeInstallbefor_0; "SE_InstallBeforeInit"
0x18001c63e  mov     ecx, 1
0x18001c643  call    AslLogCallPrintf
0x18001c648  jmp     short loc_18001C605
0x18001c64a  xor     bl, bl
0x18001c64c  lea     r9, aFailedToLockEn; "Failed to lock engine"
0x18001c653  mov     r8d, 0C42h
0x18001c659  jmp     short loc_18001C5F4
0x18001c65b  lea     r9, aRequiredShimDl; "Required shim dll not loaded.  Some shi"...
0x18001c662  mov     r8d, 0C56h
0x18001c668  lea     rdx, aSeInstallbefor_0; "SE_InstallBeforeInit"
0x18001c66f  mov     ecx, 2
0x18001c674  call    AslLogCallPrintf
0x18001c679  jmp     loc_18001C5CD
```
