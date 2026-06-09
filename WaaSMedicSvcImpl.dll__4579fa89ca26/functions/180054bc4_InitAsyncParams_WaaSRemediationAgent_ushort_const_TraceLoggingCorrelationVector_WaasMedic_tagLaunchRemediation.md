# InitAsyncParams(WaaSRemediationAgent *,ushort const *,TraceLoggingCorrelationVector *,WaasMedic::tagLaunchRemediationAsyncParams &)

- ea: `0x180054bc4`
- end: `0x180054c7a`
- name: `?InitAsyncParams@@YAJPEAVWaaSRemediationAgent@@PEBGPEAVTraceLoggingCorrelationVector@@AEAUtagLaunchRemediationAsyncParams@WaasMedic@@@Z`
- size: `182`
- prototype: `__int64 __fastcall(struct WaaSRemediationAgent *, const unsigned __int16 *, struct TraceLoggingCorrelationVector *, struct WaasMedic::tagLaunchRemediationAsyncParams *)`
- caller_count: `2`
- callee_count: `3`
- tags: `service_task, installer_update`

## callers

- `0x180055f40`
- `0x180062290`

## callees

- `0x18002e81c`
- `0x180054bc4`
- `0x18006f010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180054be5`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180054be5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180054c12`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180054c12`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180054bfc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180054bfc`

## string_xrefs

- `0x180054c2a`: `Failed to create thread inited event for WaasRemediation. hr = 0x%08x`
- `0x180054c5c`: `Failed to QI on Waas Remediation agent to populate task thread proc params. hr = 0x%08x`

## pseudocode

```c
__int64 __fastcall InitAsyncParams(
        struct WaaSRemediationAgent *a1,
        const unsigned __int16 *a2,
        struct TraceLoggingCorrelationVector *a3,
        struct WaasMedic::tagLaunchRemediationAsyncParams *a4)
{
  HANDLE EventW; // rax
  char *v9; // rcx
  HANDLE v10; // rdi
  signed int LastError; // eax
  unsigned int v12; // ebx
  int v13; // eax

  EventW = CreateEventW(0, 0, 0, 0);
  v9 = (char *)*((_QWORD *)a4 + 2);
  v10 = EventW;
  if ( (unsigned __int64)(v9 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(v9);
  *((_QWORD *)a4 + 2) = v10;
  if ( (((unsigned __int64)v10 + 1) & 0xFFFFFFFFFFFFFFFEuLL) != 0 )
  {
    *((_QWORD *)a4 + 1) = a3;
    *((_QWORD *)a4 + 3) = a2;
    v13 = (**(__int64 (__fastcall ***)(struct WaaSRemediationAgent *, GUID *, struct WaasMedic::tagLaunchRemediationAsyncParams *))a1)(
            a1,
            &IID_IUnknown,
            a4);
    v12 = v13;
    if ( v13 < 0 )
      LogLevelW(
        2u,
        L"Failed to QI on Waas Remediation agent to populate task thread proc params. hr = 0x%08x",
        (unsigned int)v13);
  }
  else
  {
    LastError = GetLastError();
    v12 = LastError;
    if ( LastError > 0 )
      v12 = (unsigned __int16)LastError | 0x80070000;
    LogLevelW(2u, L"Failed to create thread inited event for WaasRemediation. hr = 0x%08x", v12);
  }
  return v12;
}

```

## disassembly

```asm
0x180054bc4  push    rbx
0x180054bc6  push    rbp
0x180054bc7  push    rsi
0x180054bc8  push    rdi
0x180054bc9  push    r14
0x180054bcb  sub     rsp, 20h
0x180054bcf  mov     rbx, r9
0x180054bd2  mov     rbp, r8
0x180054bd5  mov     r14, rdx
0x180054bd8  mov     rsi, rcx
0x180054bdb  xor     r9d, r9d; lpName
0x180054bde  xor     r8d, r8d; bInitialState
0x180054be1  xor     edx, edx; bManualReset
0x180054be3  xor     ecx, ecx; lpEventAttributes
0x180054be5  call    cs:__imp_CreateEventW
0x180054beb  mov     rcx, [rbx+10h]; hObject
0x180054bef  mov     rdi, rax
0x180054bf2  lea     r10, [rcx-1]
0x180054bf6  cmp     r10, 0FFFFFFFFFFFFFFFDh
0x180054bfa  ja      short loc_180054C02
0x180054bfc  call    cs:__imp_CloseHandle
0x180054c02  lea     rax, [rdi+1]
0x180054c06  mov     [rbx+10h], rdi
0x180054c0a  test    rax, 0FFFFFFFFFFFFFFFEh
0x180054c10  jnz     short loc_180054C33
0x180054c12  call    cs:__imp_GetLastError
0x180054c18  mov     ebx, eax
0x180054c1a  test    eax, eax
0x180054c1c  jle     short loc_180054C27
0x180054c1e  movzx   ebx, ax
0x180054c21  or      ebx, 80070000h
0x180054c27  mov     r8d, ebx
0x180054c2a  lea     rdx, aFailedToCreate_7; "Failed to create thread inited event fo"...
0x180054c31  jmp     short loc_180054C63
0x180054c33  mov     [rbx+8], rbp
0x180054c37  lea     rdx, IID_IUnknown
0x180054c3e  mov     [rbx+18h], r14
0x180054c42  mov     r8, rbx
0x180054c45  mov     rax, [rsi]
0x180054c48  mov     rcx, rsi
0x180054c4b  mov     rax, [rax]
0x180054c4e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054c53  mov     ebx, eax
0x180054c55  test    eax, eax
0x180054c57  jns     short loc_180054C6D
0x180054c59  mov     r8d, eax
0x180054c5c  lea     rdx, aFailedToQiOnWa; "Failed to QI on Waas Remediation agent "...
0x180054c63  mov     ecx, 2; unsigned __int8
0x180054c68  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x180054c6d  mov     eax, ebx
0x180054c6f  add     rsp, 20h
0x180054c73  pop     r14
0x180054c75  pop     rdi
0x180054c76  pop     rsi
0x180054c77  pop     rbp
0x180054c78  pop     rbx
0x180054c79  retn
```
