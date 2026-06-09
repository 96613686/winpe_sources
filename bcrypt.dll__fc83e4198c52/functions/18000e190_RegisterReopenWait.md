# RegisterReopenWait

- ea: `0x18000e190`
- end: `0x18000e25f`
- name: `RegisterReopenWait`
- size: `207`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180004800`

## callees

- `0x180005060`
- `0x18000e190`

## import_xrefs

- `ntdll!RtlEnterCriticalSection` at `0x18000e19d`
- `ntdll!RtlEnterCriticalSection` at `0x18000e19d`
- `ntdll!RtlLeaveCriticalSection` at `0x18000e1f8`
- `ntdll!RtlLeaveCriticalSection` at `0x18000e1f8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e20d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e21d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e22d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e20d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e21d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e22d`
- `api-ms-win-core-threadpool-private-l1-1-0!RegisterWaitForSingleObjectEx` at `0x18000e1d9`
- `api-ms-win-core-threadpool-private-l1-1-0!RegisterWaitForSingleObjectEx` at `0x18000e1d9`

## string_xrefs

- `0x18000e248`: `onecore\ds\security\cryptoapi\ncrypt\common\syspref.c`

## pseudocode

```c
__int64 RegisterReopenWait()
{
  unsigned int LastError; // ebx
  __int64 v1; // rax

  RtlEnterCriticalSection(CriticalSection);
  LastError = 0;
  if ( !WaitHandle && g_fLoadCNGDone )
  {
    v1 = RegisterWaitForSingleObjectEx(qword_180024AF0, ReopenSystemPreferredRngCallback, 0, 0xFFFFFFFFLL, 16);
    if ( v1 )
    {
      _InterlockedExchange64((volatile __int64 *)&WaitHandle, v1);
    }
    else
    {
      if ( (int)GetLastError() > 0 )
        LastError = (unsigned __int16)GetLastError() | 0xC0070000;
      else
        LastError = GetLastError();
      DebugTraceError(LastError, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\common\\syspref.c", 214);
    }
  }
  RtlLeaveCriticalSection(CriticalSection);
  return LastError;
}

```

## disassembly

```asm
0x18000e190  push    rbx
0x18000e192  sub     rsp, 30h
0x18000e196  mov     rcx, cs:CriticalSection; CriticalSection
0x18000e19d  call    cs:__imp_RtlEnterCriticalSection
0x18000e1a4  nop     dword ptr [rax+rax+00h]
0x18000e1a9  xor     ebx, ebx
0x18000e1ab  cmp     cs:WaitHandle, rbx
0x18000e1b2  jnz     short loc_18000E1F1
0x18000e1b4  cmp     cs:g_fLoadCNGDone, ebx
0x18000e1ba  jz      short loc_18000E1F1
0x18000e1bc  mov     rcx, cs:qword_180024AF0
0x18000e1c3  lea     rdx, ReopenSystemPreferredRngCallback
0x18000e1ca  or      r9d, 0FFFFFFFFh
0x18000e1ce  mov     [rsp+38h+var_18], 10h
0x18000e1d6  xor     r8d, r8d
0x18000e1d9  call    cs:__imp_RegisterWaitForSingleObjectEx
0x18000e1e0  nop     dword ptr [rax+rax+00h]
0x18000e1e5  test    rax, rax
0x18000e1e8  jz      short loc_18000E20D
0x18000e1ea  xchg    rax, cs:WaitHandle
0x18000e1f1  mov     rcx, cs:CriticalSection; CriticalSection
0x18000e1f8  call    cs:__imp_RtlLeaveCriticalSection
0x18000e1ff  nop     dword ptr [rax+rax+00h]
0x18000e204  mov     eax, ebx
0x18000e206  add     rsp, 30h
0x18000e20a  pop     rbx
0x18000e20b  retn
0x18000e20d  call    cs:__imp_GetLastError
0x18000e214  nop     dword ptr [rax+rax+00h]
0x18000e219  test    eax, eax
0x18000e21b  jg      short loc_18000E22D
0x18000e21d  call    cs:__imp_GetLastError
0x18000e224  nop     dword ptr [rax+rax+00h]
0x18000e229  mov     ebx, eax
0x18000e22b  jmp     short loc_18000E242
0x18000e22d  call    cs:__imp_GetLastError
0x18000e234  nop     dword ptr [rax+rax+00h]
0x18000e239  movzx   ebx, ax
0x18000e23c  or      ebx, 0C0070000h
0x18000e242  mov     r9d, 0D6h
0x18000e248  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000e24f  lea     rdx, aStatus; "Status"
0x18000e256  mov     ecx, ebx
0x18000e258  call    DebugTraceError
0x18000e25d  jmp     short loc_18000E1F1
```
