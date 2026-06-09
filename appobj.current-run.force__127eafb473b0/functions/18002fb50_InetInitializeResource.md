# InetInitializeResource

- ea: `0x18002fb50`
- end: `0x18002fc24`
- name: `InetInitializeResource`
- size: `212`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180001db0`
- `0x180001f90`

## callees

- `0x18002fb50`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x18002fb62`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x18002fb62`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x18002fbb1`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x18002fbe4`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x18002fbb1`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x18002fbe4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002fbf7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002fbf7`

## pseudocode

```c
__int64 __fastcall InetInitializeResource(__int64 a1)
{
  HANDLE Semaphore; // rax
  HANDLE v3; // rax
  __int64 result; // rax

  if ( !InitializeCriticalSectionAndSpinCount((LPCRITICAL_SECTION)a1, 0x3E8u) )
    return 0;
  if ( (unsigned __int64)(*(_QWORD *)a1 - 1LL) <= 0xFFFFFFFFFFFFFFFDuLL )
    **(_WORD **)a1 = 1;
  *(_QWORD *)(a1 + 88) = 0;
  *(_DWORD *)(a1 + 80) = 0;
  Semaphore = CreateSemaphoreExW(0, 0, 0x7FFFFFFF, 0, 0, 0x1F0003u);
  *(_QWORD *)(a1 + 40) = Semaphore;
  if ( !Semaphore )
    return 0;
  *(_DWORD *)(a1 + 48) = 0;
  v3 = CreateSemaphoreExW(0, 0, 0x7FFFFFFF, 0, 0, 0x1F0003u);
  *(_QWORD *)(a1 + 56) = v3;
  if ( !v3 )
  {
    CloseHandle(*(HANDLE *)(a1 + 40));
    return 0;
  }
  *(_DWORD *)(a1 + 64) = 0;
  result = 1;
  *(_DWORD *)(a1 + 68) = 0;
  *(_QWORD *)(a1 + 72) = 0;
  return result;
}

```

## disassembly

```asm
0x18002fb50  mov     [rsp+arg_0], rbx
0x18002fb55  push    rsi
0x18002fb56  sub     rsp, 30h
0x18002fb5a  mov     edx, 3E8h; dwSpinCount
0x18002fb5f  mov     rbx, rcx
0x18002fb62  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x18002fb68  test    eax, eax
0x18002fb6a  jz      loc_18002FBFD
0x18002fb70  mov     rcx, [rbx]
0x18002fb73  mov     esi, 1
0x18002fb78  lea     rax, [rcx-1]
0x18002fb7c  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18002fb80  ja      short loc_18002FB85
0x18002fb82  mov     [rcx], si
0x18002fb85  mov     [rsp+38h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x18002fb8d  xor     r9d, r9d; lpName
0x18002fb90  xor     edx, edx; lInitialCount
0x18002fb92  mov     [rsp+38h+dwFlags], 0; dwFlags
0x18002fb9a  xor     ecx, ecx; lpSemaphoreAttributes
0x18002fb9c  mov     qword ptr [rbx+58h], 0
0x18002fba4  mov     r8d, 7FFFFFFFh; lMaximumCount
0x18002fbaa  mov     dword ptr [rbx+50h], 0
0x18002fbb1  call    cs:__imp_CreateSemaphoreExW
0x18002fbb7  mov     [rbx+28h], rax
0x18002fbbb  test    rax, rax
0x18002fbbe  jz      short loc_18002FBFD
0x18002fbc0  mov     [rsp+38h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x18002fbc8  xor     r9d, r9d; lpName
0x18002fbcb  xor     edx, edx; lInitialCount
0x18002fbcd  mov     [rsp+38h+dwFlags], 0; dwFlags
0x18002fbd5  xor     ecx, ecx; lpSemaphoreAttributes
0x18002fbd7  mov     dword ptr [rbx+30h], 0
0x18002fbde  mov     r8d, 7FFFFFFFh; lMaximumCount
0x18002fbe4  call    cs:__imp_CreateSemaphoreExW
0x18002fbea  mov     [rbx+38h], rax
0x18002fbee  test    rax, rax
0x18002fbf1  jnz     short loc_18002FC0A
0x18002fbf3  mov     rcx, [rbx+28h]; hObject
0x18002fbf7  call    cs:__imp_CloseHandle
0x18002fbfd  xor     eax, eax
0x18002fbff  mov     rbx, [rsp+38h+arg_0]
0x18002fc04  add     rsp, 30h
0x18002fc08  pop     rsi
0x18002fc09  retn
0x18002fc0a  mov     dword ptr [rbx+40h], 0
0x18002fc11  mov     eax, esi
0x18002fc13  mov     dword ptr [rbx+44h], 0
0x18002fc1a  mov     qword ptr [rbx+48h], 0
0x18002fc22  jmp     short loc_18002FBFF
```
