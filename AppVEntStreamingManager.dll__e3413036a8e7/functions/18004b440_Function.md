# Function

- ea: `0x18004b440`
- end: `0x18004b525`
- name: `Function`
- size: `229`
- prototype: `__int64 __fastcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18004b440`
- `0x18006a010`

## import_xrefs

- `KERNEL32!CloseThreadpoolCleanupGroupMembers` at `0x18004b496`
- `KERNEL32!CloseThreadpoolCleanupGroupMembers` at `0x18004b496`
- `KERNEL32!GetCurrentThreadId` at `0x18004b466`
- `KERNEL32!GetCurrentThreadId` at `0x18004b466`
- `KERNEL32!LeaveCriticalSection` at `0x18004b517`
- `KERNEL32!LeaveCriticalSection` at `0x18004b517`
- `KERNEL32!EnterCriticalSection` at `0x18004b44d`
- `KERNEL32!EnterCriticalSection` at `0x18004b44d`

## pseudocode

```c
__int64 __fastcall Function(PVOID Parameter)
{
  int v1; // eax
  volatile signed __int32 *v2; // rbx

  EnterCriticalSection(&stru_1800AA790);
  v1 = qword_1800AA7B8 + 1;
  LODWORD(qword_1800AA7B8) = v1;
  if ( v1 == 1 )
  {
    HIDWORD(qword_1800AA7B8) = GetCurrentThreadId();
    v1 = qword_1800AA7B8;
  }
  if ( qword_1800AA950 && !dword_1800AA58C )
  {
    CloseThreadpoolCleanupGroupMembers(*(PTP_CLEANUP_GROUP *)(qword_1800AA950 + 80), 0, 0);
    v2 = (volatile signed __int32 *)qword_1800AA958;
    qword_1800AA950 = 0;
    qword_1800AA958 = 0;
    if ( v2 )
    {
      if ( _InterlockedExchangeAdd(v2 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v2)(v2);
        if ( _InterlockedExchangeAdd(v2 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v2 + 8LL))(v2);
      }
    }
    v1 = qword_1800AA7B8;
  }
  LODWORD(qword_1800AA7B8) = v1 - 1;
  if ( v1 == 1 )
    qword_1800AA7B8 = 0;
  LeaveCriticalSection(&stru_1800AA790);
  return 0;
}

```

## disassembly

```asm
0x18004b440  push    rbx
0x18004b442  sub     rsp, 20h
0x18004b446  lea     rcx, stru_1800AA790; lpCriticalSection
0x18004b44d  call    cs:EnterCriticalSection
0x18004b453  mov     eax, dword ptr cs:qword_1800AA7B8
0x18004b459  inc     eax
0x18004b45b  mov     dword ptr cs:qword_1800AA7B8, eax
0x18004b461  cmp     eax, 1
0x18004b464  jnz     short loc_18004B478
0x18004b466  call    cs:GetCurrentThreadId
0x18004b46c  mov     dword ptr cs:qword_1800AA7B8+4, eax
0x18004b472  mov     eax, dword ptr cs:qword_1800AA7B8
0x18004b478  mov     rcx, cs:qword_1800AA950
0x18004b47f  test    rcx, rcx
0x18004b482  jz      short loc_18004B4FB
0x18004b484  cmp     cs:dword_1800AA58C, 0
0x18004b48b  jnz     short loc_18004B4FB
0x18004b48d  mov     rcx, [rcx+50h]; ptpcg
0x18004b491  xor     r8d, r8d; pvCleanupContext
0x18004b494  xor     edx, edx; fCancelPendingCallbacks
0x18004b496  call    cs:CloseThreadpoolCleanupGroupMembers
0x18004b49c  mov     rbx, cs:qword_1800AA958
0x18004b4a3  mov     cs:qword_1800AA950, 0
0x18004b4ae  mov     cs:qword_1800AA958, 0
0x18004b4b9  test    rbx, rbx
0x18004b4bc  jz      short loc_18004B4F5
0x18004b4be  or      eax, 0FFFFFFFFh
0x18004b4c1  lock xadd [rbx+8], eax
0x18004b4c6  cmp     eax, 1
0x18004b4c9  jnz     short loc_18004B4F5
0x18004b4cb  mov     rax, [rbx]
0x18004b4ce  mov     rcx, rbx
0x18004b4d1  mov     rax, [rax]
0x18004b4d4  call    j__guard_dispatch_icall
0x18004b4d9  or      eax, 0FFFFFFFFh
0x18004b4dc  lock xadd [rbx+0Ch], eax
0x18004b4e1  cmp     eax, 1
0x18004b4e4  jnz     short loc_18004B4F5
0x18004b4e6  mov     rax, [rbx]
0x18004b4e9  mov     rcx, rbx
0x18004b4ec  mov     rax, [rax+8]
0x18004b4f0  call    j__guard_dispatch_icall
0x18004b4f5  mov     eax, dword ptr cs:qword_1800AA7B8
0x18004b4fb  sub     eax, 1
0x18004b4fe  mov     dword ptr cs:qword_1800AA7B8, eax
0x18004b504  jnz     short loc_18004B510
0x18004b506  mov     dword ptr cs:qword_1800AA7B8+4, 0
0x18004b510  lea     rcx, stru_1800AA790; lpCriticalSection
0x18004b517  call    cs:LeaveCriticalSection
0x18004b51d  xor     eax, eax
0x18004b51f  add     rsp, 20h
0x18004b523  pop     rbx
0x18004b524  retn
```
