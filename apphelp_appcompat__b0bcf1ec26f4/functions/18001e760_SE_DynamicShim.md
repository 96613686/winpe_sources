# SE_DynamicShim

- ea: `0x18001e760`
- end: `0x18001ea64`
- name: `SE_DynamicShim`
- size: `772`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18002cba0`

## callees

- `0x180007518`
- `0x180007e94`
- `0x180008f08`
- `0x18000a23c`
- `0x18000f114`
- `0x180017334`
- `0x180017658`
- `0x18001d2a8`
- `0x18001e198`
- `0x18001e760`
- `0x18001ea6c`
- `0x18001f7f8`
- `0x18002c0ec`
- `0x18002ce44`
- `0x180059270`

## import_xrefs

- `ntdll!RtlLeaveCriticalSection` at `0x18001e947`
- `ntdll!RtlLeaveCriticalSection` at `0x18001e947`
- `ntdll!RtlEnterCriticalSection` at `0x18001e7b3`
- `ntdll!RtlEnterCriticalSection` at `0x18001e7b3`
- `ntdll!RtlInitAnsiStringEx` at `0x18001e866`
- `ntdll!RtlInitAnsiStringEx` at `0x18001e866`
- `ntdll!LdrInitShimEngineDynamic` at `0x18001e907`
- `ntdll!LdrInitShimEngineDynamic` at `0x18001e907`
- `ntdll!RtlAnsiStringToUnicodeString` at `0x18001e88d`
- `ntdll!RtlAnsiStringToUnicodeString` at `0x18001e88d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001e81c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001e81c`

## string_xrefs

- `0x18001e98a`: `Failed to create engine`
- `0x18001ea23`: `Failed to get shim dll list`

## pseudocode

```c
_BOOL8 __fastcall SE_DynamicShim(__int64 a1, __int64 a2, __int64 a3, const char *a4)
{
  int ShimDllList; // ebx
  __int64 v9; // rax
  int v10; // r12d
  PWSTR Buffer; // rbx
  DWORD CurrentProcessId; // eax
  int v13; // ecx
  int v14; // edi
  __int64 v16; // r8
  const char *v17; // r9
  struct _UNICODE_STRING v18; // [rsp+30h] [rbp-D0h] BYREF
  struct _STRING DestinationString; // [rsp+40h] [rbp-C0h] BYREF
  __int128 v20; // [rsp+50h] [rbp-B0h] BYREF
  char v21; // [rsp+60h] [rbp-A0h] BYREF

  DestinationString = 0;
  v18 = 0;
  v20 = 0;
  ShimDllList = RtlEnterCriticalSection(&g_EngineLock);
  if ( ShimDllList < 0 )
  {
    AslLogCallPrintf(1, "SE_DynamicShim", 3258, "Failed to lock engine.");
    return ShimDllList >= 0;
  }
  v9 = g_Engine;
  if ( !g_Engine )
  {
    SeProcessAttach();
    SepApplyDebugPolicy();
    v9 = g_Engine;
  }
  v10 = g_InitState;
  g_InitState = 2;
  if ( !v9 )
  {
    ShimDllList = SeEngineCreate();
    if ( ShimDllList < 0 )
    {
      AslLogCallPrintf(1, "SE_DynamicShim", 3288, "Failed to create engine");
      goto LABEL_29;
    }
  }
  if ( !(unsigned int)SdbIsValidQueryResult(a2, a3) )
  {
    v16 = 3298;
    v17 = "Invalid query result";
LABEL_28:
    ShimDllList = -1073741595;
    AslLogCallPrintf(1, "SE_DynamicShim", v16, v17);
LABEL_29:
    v14 = 3;
    if ( v10 != 3 )
      v14 = 0;
    goto LABEL_16;
  }
  ShimDllList = SeSdbProcessLayers(0);
  if ( ShimDllList < 0 )
  {
    AslLogCallPrintf(1, "SE_DynamicShim", 3312, "Failed to propagate layers");
    goto LABEL_29;
  }
  Buffer = 0;
  CurrentProcessId = GetCurrentProcessId();
  TraceQueryResult(a1, a2, a3, CurrentProcessId, 0x2000000);
  SepDumpQueryResult(a1, a2, a3);
  SepDumpQueryResultToState(a2, a3);
  if ( a4 && *a4 )
  {
    RtlInitAnsiStringEx(&DestinationString, a4);
    v18.MaximumLength = 520;
    v18.Buffer = (PWSTR)&v21;
    ShimDllList = RtlAnsiStringToUnicodeString(&v18, &DestinationString, 0);
    if ( ShimDllList < 0 )
    {
      AslLogCallPrintf(1, "SE_DynamicShim", 3345, "Failed to convert module name to UNICODE");
      goto LABEL_29;
    }
    Buffer = v18.Buffer;
  }
  ShimDllList = SeSdbProcessQueryResult(v13, a2, a3, 0, (__int64)Buffer);
  if ( ShimDllList < 0 )
  {
    AslLogCallPrintf(1, "SE_DynamicShim", 3363, "Failed to initialize engine from query result");
    goto LABEL_29;
  }
  ShimDllList = SeFlagManagerExecute(*(_QWORD *)g_Engine);
  if ( ShimDllList < 0 )
  {
    AslLogCallPrintf(1, "SE_DynamicShim", 3373, "Failed to apply flags");
    goto LABEL_29;
  }
  ShimDllList = SeShimManagerGetShimDllList(&v20, *(_QWORD *)(g_Engine + 16));
  if ( ShimDllList < 0 )
  {
    AslLogCallPrintf(1, "SE_DynamicShim", 3391, "Failed to get shim dll list");
    goto LABEL_29;
  }
  if ( !(unsigned int)LdrInitShimEngineDynamic(g_DataTableEntry->DllBase, &v20) )
  {
    v16 = 3400;
    v17 = "Failed to connect engine to loader";
    goto LABEL_28;
  }
  v14 = 3;
  g_InitState = 3;
  SeShimManagerNotifyShims(*(_QWORD *)(g_Engine + 16), 1, 1);
  ShimDllList = 0;
LABEL_16:
  g_InitState = v14;
  RtlLeaveCriticalSection(&g_EngineLock);
  return ShimDllList >= 0;
}

```

## disassembly

```asm
0x18001e760  push    rbp
0x18001e762  push    rbx
0x18001e763  push    rsi
0x18001e764  push    rdi
0x18001e765  push    r12
0x18001e767  push    r14
0x18001e769  push    r15
0x18001e76b  lea     rbp, [rsp-180h]
0x18001e773  sub     rsp, 280h
0x18001e77a  mov     rax, cs:__security_cookie
0x18001e781  xor     rax, rsp
0x18001e784  mov     [rbp+1B0h+var_40], rax
0x18001e78b  xorps   xmm0, xmm0
0x18001e78e  mov     r15, rcx
0x18001e791  xorps   xmm1, xmm1
0x18001e794  lea     rcx, g_EngineLock; CriticalSection
0x18001e79b  movups  xmmword ptr [rsp+2B0h+DestinationString.Length], xmm0
0x18001e7a0  mov     r14, r9
0x18001e7a3  mov     rsi, r8
0x18001e7a6  movups  xmmword ptr [rsp+2B0h+var_280.Length], xmm1
0x18001e7ab  mov     rdi, rdx
0x18001e7ae  movups  [rsp+2B0h+var_260], xmm0
0x18001e7b3  call    cs:__imp_RtlEnterCriticalSection
0x18001e7b9  mov     ebx, eax
0x18001e7bb  test    eax, eax
0x18001e7bd  js      loc_18001E9BE
0x18001e7c3  mov     rax, cs:g_Engine
0x18001e7ca  test    rax, rax
0x18001e7cd  jz      loc_18001E9A8
0x18001e7d3  mov     r12d, cs:g_InitState
0x18001e7da  mov     cs:g_InitState, 2
0x18001e7e4  test    rax, rax
0x18001e7e7  jz      loc_18001E975
0x18001e7ed  mov     rdx, rsi
0x18001e7f0  mov     rcx, rdi
0x18001e7f3  call    SdbIsValidQueryResult
0x18001e7f8  test    eax, eax
0x18001e7fa  jz      loc_18001E9E1
0x18001e800  mov     r9, rsi
0x18001e803  mov     r8, r15
0x18001e806  mov     rdx, rdi
0x18001e809  xor     ecx, ecx; pszDest
0x18001e80b  call    SeSdbProcessLayers
0x18001e810  mov     ebx, eax
0x18001e812  test    eax, eax
0x18001e814  js      loc_18001E9F0
0x18001e81a  xor     ebx, ebx
0x18001e81c  call    cs:__imp_GetCurrentProcessId
0x18001e822  mov     r8, rsi
0x18001e825  mov     dword ptr [rsp+2B0h+var_290], 2000000h
0x18001e82d  mov     r9d, eax
0x18001e830  mov     rdx, rdi
0x18001e833  mov     rcx, r15
0x18001e836  call    TraceQueryResult
0x18001e83b  mov     r8, rsi
0x18001e83e  mov     rdx, rdi
0x18001e841  mov     rcx, r15
0x18001e844  call    SepDumpQueryResult
0x18001e849  mov     rdx, rsi
0x18001e84c  mov     rcx, rdi
0x18001e84f  call    SepDumpQueryResultToState
0x18001e854  test    r14, r14
0x18001e857  jz      short loc_18001E8A2
0x18001e859  cmp     [r14], bl
0x18001e85c  jz      short loc_18001E8A2
0x18001e85e  mov     rdx, r14; SourceString
0x18001e861  lea     rcx, [rsp+2B0h+DestinationString]; DestinationString
0x18001e866  call    cs:__imp_RtlInitAnsiStringEx
0x18001e86c  mov     eax, 208h
0x18001e871  lea     rdx, [rsp+2B0h+DestinationString]; SourceString
0x18001e876  mov     [rsp+2B0h+var_280.MaximumLength], ax
0x18001e87b  lea     rcx, [rsp+2B0h+var_280]; DestinationString
0x18001e880  lea     rax, [rsp+2B0h+var_250]
0x18001e885  xor     r8d, r8d; AllocateDestinationString
0x18001e888  mov     [rsp+2B0h+var_280.Buffer], rax
0x18001e88d  call    cs:__imp_RtlAnsiStringToUnicodeString
0x18001e893  mov     ebx, eax
0x18001e895  test    eax, eax
0x18001e897  js      loc_18001E9FF
0x18001e89d  mov     rbx, [rsp+2B0h+var_280.Buffer]
0x18001e8a2  xor     r9d, r9d
0x18001e8a5  mov     [rsp+2B0h+var_290], rbx
0x18001e8aa  mov     r8, rsi
0x18001e8ad  mov     rdx, rdi
0x18001e8b0  call    SeSdbProcessQueryResult
0x18001e8b5  mov     ebx, eax
0x18001e8b7  test    eax, eax
0x18001e8b9  js      loc_18001E996
0x18001e8bf  mov     rcx, cs:g_Engine
0x18001e8c6  mov     rcx, [rcx]
0x18001e8c9  call    SeFlagManagerExecute
0x18001e8ce  mov     ebx, eax
0x18001e8d0  test    eax, eax
0x18001e8d2  js      loc_18001EA0E
0x18001e8d8  mov     rdx, cs:g_Engine
0x18001e8df  lea     rcx, [rsp+2B0h+var_260]
0x18001e8e4  mov     rdx, [rdx+10h]
0x18001e8e8  call    SeShimManagerGetShimDllList
0x18001e8ed  mov     ebx, eax
0x18001e8ef  test    eax, eax
0x18001e8f1  js      loc_18001EA1D
0x18001e8f7  mov     rcx, cs:g_DataTableEntry
0x18001e8fe  lea     rdx, [rsp+2B0h+var_260]
0x18001e903  mov     rcx, [rcx+30h]
0x18001e907  call    cs:__imp_LdrInitShimEngineDynamic
0x18001e90d  test    eax, eax
0x18001e90f  jz      loc_18001EA2C
0x18001e915  mov     edi, 3
0x18001e91a  mov     cs:g_InitState, edi
0x18001e920  lea     ecx, [rdi-2]
0x18001e923  mov     r8d, ecx
0x18001e926  mov     edx, ecx
0x18001e928  mov     rcx, cs:g_Engine
0x18001e92f  mov     rcx, [rcx+10h]
0x18001e933  call    SeShimManagerNotifyShims
0x18001e938  xor     ebx, ebx
0x18001e93a  lea     rcx, g_EngineLock; CriticalSection
0x18001e941  mov     cs:g_InitState, edi
0x18001e947  call    cs:__imp_RtlLeaveCriticalSection
0x18001e94d  not     ebx
0x18001e94f  shr     ebx, 1Fh
0x18001e952  mov     eax, ebx
0x18001e954  mov     rcx, [rbp+1B0h+var_40]
0x18001e95b  xor     rcx, rsp; StackCookie
0x18001e95e  call    __security_check_cookie
0x18001e963  add     rsp, 280h
0x18001e96a  pop     r15
0x18001e96c  pop     r14
0x18001e96e  pop     r12
0x18001e970  pop     rdi
0x18001e971  pop     rsi
0x18001e972  pop     rbx
0x18001e973  pop     rbp
0x18001e974  retn
0x18001e975  call    SeEngineCreate
0x18001e97a  mov     ebx, eax
0x18001e97c  test    eax, eax
0x18001e97e  jns     loc_18001E7ED
0x18001e984  mov     r8d, 0CD8h
0x18001e98a  lea     r9, aFailedToCreate_25; "Failed to create engine"
0x18001e991  jmp     loc_18001EA3E
0x18001e996  mov     r8d, 0D23h
0x18001e99c  lea     r9, aFailedToInitia_6; "Failed to initialize engine from query "...
0x18001e9a3  jmp     loc_18001EA3E
0x18001e9a8  call    SeProcessAttach
0x18001e9ad  call    SepApplyDebugPolicy
0x18001e9b2  mov     rax, cs:g_Engine
0x18001e9b9  jmp     loc_18001E7D3
0x18001e9be  lea     r9, aFailedToLockEn_0; "Failed to lock engine."
0x18001e9c5  mov     r8d, 0CBAh
0x18001e9cb  lea     rdx, aSeDynamicshim_0; "SE_DynamicShim"
0x18001e9d2  mov     ecx, 1
0x18001e9d7  call    AslLogCallPrintf
0x18001e9dc  jmp     loc_18001E94D
0x18001e9e1  mov     r8d, 0CE2h
0x18001e9e7  lea     r9, aInvalidQueryRe; "Invalid query result"
0x18001e9ee  jmp     short loc_18001EA39
0x18001e9f0  mov     r8d, 0CF0h
0x18001e9f6  lea     r9, aFailedToPropag; "Failed to propagate layers"
0x18001e9fd  jmp     short loc_18001EA3E
0x18001e9ff  mov     r8d, 0D11h
0x18001ea05  lea     r9, aFailedToConver_3; "Failed to convert module name to UNICOD"...
0x18001ea0c  jmp     short loc_18001EA3E
0x18001ea0e  mov     r8d, 0D2Dh
0x18001ea14  lea     r9, aFailedToApplyF; "Failed to apply flags"
0x18001ea1b  jmp     short loc_18001EA3E
0x18001ea1d  mov     r8d, 0D3Fh
0x18001ea23  lea     r9, aFailedToGetShi_1; "Failed to get shim dll list"
0x18001ea2a  jmp     short loc_18001EA3E
0x18001ea2c  mov     r8d, 0D48h
0x18001ea32  lea     r9, aFailedToConnec; "Failed to connect engine to loader"
0x18001ea39  mov     ebx, 0C00000E5h
0x18001ea3e  lea     rdx, aSeDynamicshim_0; "SE_DynamicShim"
0x18001ea45  mov     ecx, 1
0x18001ea4a  call    AslLogCallPrintf
0x18001ea4f  mov     edi, 3
0x18001ea54  cmp     r12d, edi
0x18001ea57  jz      loc_18001E93A
0x18001ea5d  xor     edi, edi
0x18001ea5f  jmp     loc_18001E93A
```
