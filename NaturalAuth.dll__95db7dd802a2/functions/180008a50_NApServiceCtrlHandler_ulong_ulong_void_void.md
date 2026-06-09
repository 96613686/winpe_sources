# NApServiceCtrlHandler(ulong,ulong,void *,void *)

- ea: `0x180008a50`
- end: `0x180008b17`
- name: `?NApServiceCtrlHandler@@YAKKKPEAX0@Z`
- size: `199`
- prototype: `DWORD __stdcall(DWORD dwControl, DWORD dwEventType, LPVOID lpEventData, LPVOID lpContext)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callees

- `0x180008a50`
- `0x180046010`

## import_xrefs

- `ntdll!RtlAcquireSRWLockShared` at `0x180008a76`
- `ntdll!RtlAcquireSRWLockShared` at `0x180008a76`
- `ntdll!RtlReleaseSRWLockShared` at `0x180008ac2`
- `ntdll!RtlReleaseSRWLockShared` at `0x180008ac2`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180008afe`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180008afe`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180008af5`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180008af5`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall NApServiceCtrlHandler(DWORD dwControl, DWORD dwEventType, LPVOID lpEventData, LPVOID lpContext)
{
  unsigned int v8; // esi
  __int64 i; // rdi
  void (__fastcall *v10)(_QWORD, _QWORD, _QWORD, LPVOID); // rax
  DWORD v11; // ebx

  v8 = 120;
  RtlAcquireSRWLockShared(&stru_18005FAE0);
  if ( byte_18005FC59 )
  {
    for ( i = 0; i != 6; ++i )
    {
      v10 = (void (__fastcall *)(_QWORD, _QWORD, _QWORD, LPVOID))*(&off_18005C000 + 29 * i + 3);
      if ( v10 )
        v10(*(&off_18005C000 + 29 * i + 10), dwControl, dwEventType, lpEventData);
    }
  }
  RtlReleaseSRWLockShared(&stru_18005FAE0);
  v11 = dwControl - 1;
  if ( !v11 || v11 == 4 )
  {
    g_ssService.dwCurrentState = 3;
    *(_QWORD *)&g_ssService.dwCheckPoint = 0;
    SetServiceStatus(g_hssService, &g_ssService);
    SetEvent(lpContext);
    return 0;
  }
  return v8;
}

```

## disassembly

```asm
0x180008a50  push    rbx
0x180008a52  push    rbp
0x180008a53  push    rsi
0x180008a54  push    rdi
0x180008a55  push    r13
0x180008a57  push    r14
0x180008a59  push    r15
0x180008a5b  sub     rsp, 40h
0x180008a5f  mov     rbp, r9
0x180008a62  mov     r14, r8
0x180008a65  mov     r15d, edx
0x180008a68  mov     ebx, ecx
0x180008a6a  mov     esi, 78h ; 'x'
0x180008a6f  lea     rcx, stru_18005FAE0
0x180008a76  call    cs:__imp_RtlAcquireSRWLockShared
0x180008a7c  nop
0x180008a7d  cmp     cs:byte_18005FC59, 0
0x180008a84  jz      short loc_180008ABB
0x180008a86  xor     edi, edi
0x180008a88  lea     r13, off_18005C000
0x180008a8f  imul    rcx, rdi, 0E8h
0x180008a96  mov     rax, [rcx+r13+18h]
0x180008a9b  test    rax, rax
0x180008a9e  jz      short loc_180008AB2
0x180008aa0  mov     r9, r14
0x180008aa3  mov     r8d, r15d
0x180008aa6  mov     edx, ebx
0x180008aa8  mov     rcx, [rcx+r13+50h]
0x180008aad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008ab2  inc     rdi
0x180008ab5  cmp     rdi, 6
0x180008ab9  jnz     short loc_180008A8F
0x180008abb  lea     rcx, stru_18005FAE0
0x180008ac2  call    cs:__imp_RtlReleaseSRWLockShared
0x180008ac8  sub     ebx, 1
0x180008acb  jz      short loc_180008AD2
0x180008acd  cmp     ebx, 4
0x180008ad0  jnz     short loc_180008B06
0x180008ad2  mov     cs:?g_ssService@@3U_SERVICE_STATUS@@A.dwCurrentState, 3; _SERVICE_STATUS g_ssService ...
0x180008adc  mov     qword ptr cs:?g_ssService@@3U_SERVICE_STATUS@@A.dwCheckPoint, 0; _SERVICE_STATUS g_ssService ...
0x180008ae7  lea     rdx, ?g_ssService@@3U_SERVICE_STATUS@@A; lpServiceStatus
0x180008aee  mov     rcx, cs:?g_hssService@@3PEAUSERVICE_STATUS_HANDLE__@@EA; hServiceStatus
0x180008af5  call    cs:__imp_SetServiceStatus
0x180008afb  mov     rcx, rbp; hEvent
0x180008afe  call    cs:__imp_SetEvent
0x180008b04  xor     esi, esi
0x180008b06  mov     eax, esi
0x180008b08  add     rsp, 40h
0x180008b0c  pop     r15
0x180008b0e  pop     r14
0x180008b10  pop     r13
0x180008b12  pop     rdi
0x180008b13  pop     rsi
0x180008b14  pop     rbp
0x180008b15  pop     rbx
0x180008b16  retn
```
