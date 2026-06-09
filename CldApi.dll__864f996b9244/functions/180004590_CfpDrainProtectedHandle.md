# CfpDrainProtectedHandle

- ea: `0x180004590`
- end: `0x180004620`
- name: `CfpDrainProtectedHandle`
- size: `144`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180003b90`
- `0x180003be0`
- `0x180004720`

## callees

- `0x180004590`
- `0x18001ba6c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004606`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004606`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004614`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004614`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800045cf`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800045cf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800045e4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004600`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800045e4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004600`

## pseudocode

```c
signed __int32 __fastcall CfpDrainProtectedHandle(__int64 a1)
{
  unsigned __int64 i; // rbx
  signed __int64 v3; // rax
  unsigned __int64 v4; // rcx
  __int64 v5; // rtt
  void *v6; // rcx
  signed __int32 result; // eax
  void *v8; // rcx
  HANDLE ProcessHeap; // rax

  if ( (a1 & 1) != 0 )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  for ( i = a1 & 0xFFFFFFFFFFFFFFFEuLL; ; WaitForSingleObject(*(HANDLE *)(i + 8), 0xFFFFFFFF) )
  {
    do
    {
      v3 = *(_QWORD *)(i + 16);
      v4 = v3 & 0xFFFFFFFFFFFFFFFEuLL;
      if ( (v3 & 1) == 0 )
        break;
      v5 = *(_QWORD *)(i + 16);
      if ( v5 == _InterlockedCompareExchange64((volatile signed __int64 *)(i + 16), v4, v3) )
        break;
    }
    while ( v4 );
    if ( !v4 )
      break;
  }
  v6 = (void *)_InterlockedExchange64((volatile __int64 *)i, -1);
  if ( v6 != (void *)-1LL )
    CloseHandle(v6);
  result = _InterlockedExchangeAdd((volatile signed __int32 *)(i + 24), 0xFFFFFFFF);
  if ( result == 1 )
  {
    v8 = *(void **)(i + 8);
    if ( v8 )
      CloseHandle(v8);
    ProcessHeap = GetProcessHeap();
    return HeapFree(ProcessHeap, 0, (LPVOID)i);
  }
  return result;
}

```

## disassembly

```asm
0x180004590  push    rbx
0x180004592  sub     rsp, 20h
0x180004596  mov     rbx, rcx
0x180004599  test    cl, 1
0x18000459c  jz      short loc_1800045A3
0x18000459e  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800045a3  and     rbx, 0FFFFFFFFFFFFFFFEh
0x1800045a7  mov     rax, [rbx+10h]
0x1800045ab  mov     rcx, rax
0x1800045ae  and     rcx, 0FFFFFFFFFFFFFFFEh
0x1800045b2  test    al, 1
0x1800045b4  jz      short loc_1800045C3
0x1800045b6  lock cmpxchg [rbx+10h], rcx
0x1800045bc  jz      short loc_1800045C3
0x1800045be  test    rcx, rcx
0x1800045c1  jnz     short loc_1800045A7
0x1800045c3  test    rcx, rcx
0x1800045c6  jz      short loc_1800045D7
0x1800045c8  mov     rcx, [rbx+8]; hHandle
0x1800045cc  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800045cf  call    cs:__imp_WaitForSingleObject
0x1800045d5  jmp     short loc_1800045A7
0x1800045d7  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1800045db  xchg    rcx, [rbx]; hObject
0x1800045de  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1800045e2  jz      short loc_1800045EA
0x1800045e4  call    cs:__imp_CloseHandle
0x1800045ea  or      eax, 0FFFFFFFFh
0x1800045ed  lock xadd [rbx+18h], eax
0x1800045f2  cmp     eax, 1
0x1800045f5  jnz     short loc_18000461A
0x1800045f7  mov     rcx, [rbx+8]; hObject
0x1800045fb  test    rcx, rcx
0x1800045fe  jz      short loc_180004606
0x180004600  call    cs:__imp_CloseHandle
0x180004606  call    cs:__imp_GetProcessHeap
0x18000460c  mov     r8, rbx; lpMem
0x18000460f  xor     edx, edx; dwFlags
0x180004611  mov     rcx, rax; hHeap
0x180004614  call    cs:__imp_HeapFree
0x18000461a  add     rsp, 20h
0x18000461e  pop     rbx
0x18000461f  retn
```
