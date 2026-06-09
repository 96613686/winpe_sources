# IPxlatPolicyMgrInitialize

- ea: `0x18000dc28`
- end: `0x18000dcc1`
- name: `IPxlatPolicyMgrInitialize`
- size: `153`
- prototype: `__int64()`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x18000b170`
- `0x18000ea3c`

## callees

- `0x18000214c`
- `0x180002a28`
- `0x18000dc28`
- `0x18000e43c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x18000dc7b`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x18000dc7b`

## string_xrefs

- `0x18000dc3e`: `IPxlatPolicyMgr is already initialized`

## pseudocode

```c
__int64 IPxlatPolicyMgrInitialize()
{
  __int64 result; // rax
  struct _RTL_CRITICAL_SECTION *v1; // rbx
  PHKEY v2; // rbx

  if ( phkResult )
  {
    IPxlatPolicyMgrLogger::LogError(
      (IPxlatPolicyMgrLogger *)(phkResult + 15),
      1247,
      L"IPxlatPolicyMgr is already initialized");
    return 1247;
  }
  else
  {
    try
    {
      v1 = (struct _RTL_CRITICAL_SECTION *)operator new(0xA0u);
      memset_0(v1, 0, 0xA0u);
      InitializeCriticalSectionEx(v1 + 2, 0, 0);
      phkResult = (PHKEY)v1;
      v1[3].DebugInfo = (PRTL_CRITICAL_SECTION_DEBUG)S_Microsoft_Windows_IPxlatCfg_Context;
      *(_OWORD *)&v1[3].LockCount = IPXLATCFG_POLICY_INFO_EVENT;
      *(_OWORD *)&v1[3].LockSemaphore = IPXLATCFG_POLICY_ERROR_EVENT;
      result = 0;
    }
    catch ( ... )
    {
      v2 = phkResult;
      if ( phkResult )
      {
        IPxlatPolicyMgrGlobals::~IPxlatPolicyMgrGlobals((IPxlatPolicyMgrGlobals *)phkResult);
        operator delete(v2);
      }
      phkResult = 0;
      return 14;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18000dc28  push    rbx
0x18000dc2a  sub     rsp, 20h
0x18000dc2e  mov     rcx, cs:phkResult
0x18000dc35  test    rcx, rcx
0x18000dc38  jz      short loc_18000DC55
0x18000dc3a  add     rcx, 78h ; 'x'; this
0x18000dc3e  lea     r8, aIpxlatpolicymg_4; "IPxlatPolicyMgr is already initialized"
0x18000dc45  mov     ebx, 4DFh
0x18000dc4a  mov     edx, ebx; unsigned int
0x18000dc4c  call    ?LogError@IPxlatPolicyMgrLogger@@QEAAXIPEBGZZ; IPxlatPolicyMgrLogger::LogError(uint,ushort const *,...)
0x18000dc51  mov     eax, ebx
0x18000dc53  jmp     short loc_18000DCBA
0x18000dc55  mov     ecx, 0A0h; Size
0x18000dc5a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000dc5f  mov     rbx, rax
0x18000dc62  xor     edx, edx; Val
0x18000dc64  mov     r8d, 0A0h; Size
0x18000dc6a  mov     rcx, rax; void *
0x18000dc6d  call    memset_0
0x18000dc72  lea     rcx, [rbx+50h]; lpCriticalSection
0x18000dc76  xor     r8d, r8d; Flags
0x18000dc79  xor     edx, edx; dwSpinCount
0x18000dc7b  call    cs:__imp_InitializeCriticalSectionEx
0x18000dc81  mov     cs:phkResult, rbx
0x18000dc88  movups  xmm1, cs:IPXLATCFG_POLICY_ERROR_EVENT
0x18000dc8f  movups  xmm0, cs:IPXLATCFG_POLICY_INFO_EVENT
0x18000dc96  mov     rax, cs:S_Microsoft_Windows_IPxlatCfg_Context
0x18000dc9d  mov     [rbx+78h], rax
0x18000dca1  movdqu  xmmword ptr [rbx+80h], xmm0
0x18000dca9  movdqu  xmmword ptr [rbx+90h], xmm1
0x18000dcb1  xor     eax, eax
0x18000dcb3  jmp     short loc_18000DCBA
0x18000dcb5  mov     eax, 0Eh
0x18000dcba  add     rsp, 20h
0x18000dcbe  pop     rbx
0x18000dcbf  retn
```
