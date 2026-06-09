# DllMain

- ea: `0x1801f2ba8`
- end: `0x1801f2ce8`
- name: `DllMain`
- size: `320`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting`

## callers

- `0x1801c8444`

## callees

- `0x180185314`
- `0x18018ef00`
- `0x1801c8138`
- `0x1801d0a88`
- `0x1801f298c`
- `0x1801f29c4`
- `0x1801f2ba8`
- `0x18020bccc`

## import_xrefs

- `KERNEL32!TlsSetValue` at `0x1801f2c74`
- `KERNEL32!TlsSetValue` at `0x1801f2c74`
- `KERNEL32!DeleteAtom` at `0x1801f2c83`
- `KERNEL32!DeleteAtom` at `0x1801f2c83`
- `KERNEL32!TryEnterCriticalSection` at `0x1801f2c4a`
- `KERNEL32!TryEnterCriticalSection` at `0x1801f2c4a`
- `KERNEL32!LeaveCriticalSection` at `0x1801f2c64`
- `KERNEL32!LeaveCriticalSection` at `0x1801f2c64`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
BOOL __stdcall DllMain(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  TraceLoggingClient *v4; // rax
  unsigned int v5; // edx
  int v6; // ebx
  unsigned int v8; // edx

  if ( fdwReason == 1 )
  {
    hProxyDll = hinstDLL;
    v4 = (TraceLoggingClient *)operator new(0x440u);
    if ( v4 )
      v4 = TraceLoggingClient::TraceLoggingClient(v4);
    g_pTraceLoggingClient = v4;
    v6 = AttachProcess(hinstDLL);
    if ( !v6 )
    {
      if ( g_pTraceLoggingClient )
      {
        TraceLoggingClient::`scalar deleting destructor'(g_pTraceLoggingClient, v5);
        g_pTraceLoggingClient = 0;
      }
    }
    return v6;
  }
  else
  {
    if ( fdwReason )
    {
      if ( fdwReason == 2 )
      {
        TlsSetValue(ThreadContextTLSEntry::s_tlsSlot, 0);
      }
      else
      {
        if ( fdwReason != 3 )
          return 0;
        if ( TryEnterCriticalSection(&CriticalSection) )
        {
          ThreadBoundThreadContextManager::DestroyContextAndEntryForCurrentThread();
          LeaveCriticalSection(&CriticalSection);
        }
      }
    }
    else
    {
      lockedDll = DeleteAtom(lockedDll);
      McGenEventUnregister_EventUnregister(&BERP_IE_Context);
      McGenEventUnregister_EventUnregister(&PROVIDER_JSCRIPT9_Context);
      McGenEventUnregister_EventUnregister(&PROVIDER_JSCRIPT9_INTERNAL_Context);
      if ( !lpvReserved )
      {
        if ( g_pTraceLoggingClient )
        {
          TraceLoggingClient::`scalar deleting destructor'(g_pTraceLoggingClient, v8);
          g_pTraceLoggingClient = 0;
        }
        DetachProcess();
      }
    }
    return 1;
  }
}

```

## disassembly

```asm
0x1801f2ba8  mov     rax, rsp
0x1801f2bab  mov     [rax+18h], r8
0x1801f2baf  mov     [rax+10h], edx
0x1801f2bb2  mov     [rax+8], rcx
0x1801f2bb6  push    rbx
0x1801f2bb7  sub     rsp, 30h
0x1801f2bbb  mov     qword ptr [rax-18h], 0FFFFFFFFFFFFFFFEh
0x1801f2bc3  mov     rbx, rcx
0x1801f2bc6  mov     eax, edx
0x1801f2bc8  cmp     eax, 1
0x1801f2bcb  jnz     short loc_1801F2C29
0x1801f2bcd  mov     cs:hProxyDll, rcx
0x1801f2bd4  mov     ecx, 440h; Size
0x1801f2bd9  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1801f2bde  mov     [rsp+38h+var_10], rax
0x1801f2be3  test    rax, rax
0x1801f2be6  jz      short loc_1801F2BF1
0x1801f2be8  mov     rcx, rax; this
0x1801f2beb  call    ??0TraceLoggingClient@@QEAA@XZ; TraceLoggingClient::TraceLoggingClient(void)
0x1801f2bf0  nop
0x1801f2bf1  mov     cs:g_pTraceLoggingClient, rax
0x1801f2bf8  mov     rcx, rbx
0x1801f2bfb  call    AttachProcess
0x1801f2c00  mov     ebx, eax
0x1801f2c02  test    eax, eax
0x1801f2c04  jnz     short loc_1801F2C22
0x1801f2c06  mov     rcx, cs:g_pTraceLoggingClient; this
0x1801f2c0d  test    rcx, rcx
0x1801f2c10  jz      short loc_1801F2C22
0x1801f2c12  call    ??_GTraceLoggingClient@@QEAAPEAXI@Z; TraceLoggingClient::`scalar deleting destructor'(uint)
0x1801f2c17  mov     cs:g_pTraceLoggingClient, 0
0x1801f2c22  mov     eax, ebx
0x1801f2c24  jmp     loc_1801F2CE2
0x1801f2c29  test    eax, eax
0x1801f2c2b  jz      short loc_1801F2C7C
0x1801f2c2d  sub     eax, 1
0x1801f2c30  jz      short loc_1801F2BD4
0x1801f2c32  sub     eax, 1
0x1801f2c35  jz      short loc_1801F2C6C
0x1801f2c37  cmp     eax, 1
0x1801f2c3a  jz      short loc_1801F2C43
0x1801f2c3c  xor     eax, eax
0x1801f2c3e  jmp     loc_1801F2CE2
0x1801f2c43  lea     rcx, CriticalSection; lpCriticalSection
0x1801f2c4a  call    cs:__imp_TryEnterCriticalSection
0x1801f2c50  test    eax, eax
0x1801f2c52  jz      loc_1801F2CDD
0x1801f2c58  call    ?DestroyContextAndEntryForCurrentThread@ThreadBoundThreadContextManager@@SAXXZ; ThreadBoundThreadContextManager::DestroyContextAndEntryForCurrentThread(void)
0x1801f2c5d  lea     rcx, CriticalSection; lpCriticalSection
0x1801f2c64  call    cs:__imp_LeaveCriticalSection
0x1801f2c6a  jmp     short loc_1801F2CDD
0x1801f2c6c  xor     edx, edx; lpTlsValue
0x1801f2c6e  mov     ecx, cs:?s_tlsSlot@ThreadContextTLSEntry@@2KA; dwTlsIndex
0x1801f2c74  call    cs:__imp_TlsSetValue
0x1801f2c7a  jmp     short loc_1801F2CDD
0x1801f2c7c  movzx   ecx, cs:?lockedDll@@3GA; nAtom
0x1801f2c83  call    cs:__imp_DeleteAtom
0x1801f2c89  mov     cs:?lockedDll@@3GA, ax; ushort lockedDll
0x1801f2c90  lea     rcx, BERP_IE_Context
0x1801f2c97  call    McGenEventUnregister_EventUnregister
0x1801f2c9c  lea     rcx, PROVIDER_JSCRIPT9_Context
0x1801f2ca3  call    McGenEventUnregister_EventUnregister
0x1801f2ca8  lea     rcx, PROVIDER_JSCRIPT9_INTERNAL_Context
0x1801f2caf  call    McGenEventUnregister_EventUnregister
0x1801f2cb4  cmp     [rsp+38h+arg_10], 0
0x1801f2cba  jnz     short loc_1801F2CDD
0x1801f2cbc  mov     rcx, cs:g_pTraceLoggingClient; this
0x1801f2cc3  test    rcx, rcx
0x1801f2cc6  jz      short loc_1801F2CD8
0x1801f2cc8  call    ??_GTraceLoggingClient@@QEAAPEAXI@Z; TraceLoggingClient::`scalar deleting destructor'(uint)
0x1801f2ccd  mov     cs:g_pTraceLoggingClient, 0
0x1801f2cd8  call    ?DetachProcess@@YAXXZ; DetachProcess(void)
0x1801f2cdd  mov     eax, 1
0x1801f2ce2  add     rsp, 30h
0x1801f2ce6  pop     rbx
0x1801f2ce7  retn
```
