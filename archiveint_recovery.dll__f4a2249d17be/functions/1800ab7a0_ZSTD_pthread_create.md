# ZSTD_pthread_create

- ea: `0x1800ab7a0`
- end: `0x1800ab88e`
- name: `ZSTD_pthread_create`
- size: `238`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1800ab170`
- `0x1800ab450`

## callees

- `0x1800ab7a0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800ab82a`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800ab82a`
- `api-ms-win-crt-private-l1-1-0!_o__beginthreadex` at `0x1800ab809`
- `api-ms-win-crt-private-l1-1-0!_o__beginthreadex` at `0x1800ab809`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1800ab7ea`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1800ab7ea`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800ab872`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800ab872`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800ab83b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800ab83b`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800ab824`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800ab87d`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800ab824`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800ab87d`
- `api-ms-win-core-synch-l1-2-0!InitializeConditionVariable` at `0x1800ab7df`
- `api-ms-win-core-synch-l1-2-0!InitializeConditionVariable` at `0x1800ab7df`
- `api-ms-win-core-synch-l1-2-0!SleepConditionVariableCS` at `0x1800ab860`
- `api-ms-win-core-synch-l1-2-0!SleepConditionVariableCS` at `0x1800ab860`

## pseudocode

```c
__int64 __fastcall ZSTD_pthread_create(__int64 *a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v6; // rax
  _QWORD v7[2]; // [rsp+30h] [rbp-58h] BYREF
  int v8; // [rsp+40h] [rbp-48h]
  RTL_CONDITION_VARIABLE ConditionVariable; // [rsp+48h] [rbp-40h] BYREF
  _RTL_CRITICAL_SECTION CriticalSection; // [rsp+50h] [rbp-38h] BYREF

  if ( !a1 )
    return 0xFFFFFFFFLL;
  *a1 = 0;
  v7[0] = a3;
  v7[1] = a4;
  v8 = 0;
  InitializeConditionVariable(&ConditionVariable);
  InitializeCriticalSection(&CriticalSection);
  v6 = ((__int64 (__fastcall *)(_QWORD, _QWORD, __int64 (__fastcall *)(), _QWORD *, _DWORD, _QWORD))_o__beginthreadex)(
         0,
         0,
         worker,
         v7,
         0,
         0);
  *a1 = v6;
  if ( v6 )
  {
    EnterCriticalSection(&CriticalSection);
    while ( !v8 )
      SleepConditionVariableCS(&ConditionVariable, &CriticalSection, 0xFFFFFFFF);
    LeaveCriticalSection(&CriticalSection);
    DeleteCriticalSection(&CriticalSection);
    return 0;
  }
  else
  {
    DeleteCriticalSection(&CriticalSection);
    return *(unsigned int *)_o__errno();
  }
}

```

## disassembly

```asm
0x1800ab7a0  push    rbx
0x1800ab7a2  sub     rsp, 80h
0x1800ab7a9  mov     rbx, rcx
0x1800ab7ac  test    rcx, rcx
0x1800ab7af  jnz     short loc_1800AB7BF
0x1800ab7b1  mov     eax, 0FFFFFFFFh
0x1800ab7b6  add     rsp, 80h
0x1800ab7bd  pop     rbx
0x1800ab7be  retn
0x1800ab7bf  mov     [rsp+88h+arg_0], rdi
0x1800ab7c7  xor     edi, edi
0x1800ab7c9  mov     [rcx], rdi
0x1800ab7cc  lea     rcx, [rsp+88h+ConditionVariable]; ConditionVariable
0x1800ab7d1  mov     [rsp+88h+var_58], r8
0x1800ab7d6  mov     [rsp+88h+var_50], r9
0x1800ab7db  mov     [rsp+88h+var_48], edi
0x1800ab7df  call    cs:__imp_InitializeConditionVariable
0x1800ab7e5  lea     rcx, [rsp+88h+CriticalSection]; lpCriticalSection
0x1800ab7ea  call    cs:__imp_InitializeCriticalSection
0x1800ab7f0  lea     r9, [rsp+88h+var_58]
0x1800ab7f5  mov     [rsp+88h+var_60], rdi
0x1800ab7fa  lea     r8, worker
0x1800ab801  mov     [rsp+88h+var_68], edi
0x1800ab805  xor     edx, edx
0x1800ab807  xor     ecx, ecx
0x1800ab809  call    cs:__imp__o__beginthreadex
0x1800ab80f  mov     rdi, [rsp+88h+arg_0]
0x1800ab817  lea     rcx, [rsp+88h+CriticalSection]; lpCriticalSection
0x1800ab81c  mov     [rbx], rax
0x1800ab81f  test    rax, rax
0x1800ab822  jnz     short loc_1800AB83B
0x1800ab824  call    cs:__imp_DeleteCriticalSection
0x1800ab82a  call    cs:__imp__o__errno
0x1800ab830  mov     eax, [rax]
0x1800ab832  add     rsp, 80h
0x1800ab839  pop     rbx
0x1800ab83a  retn
0x1800ab83b  call    cs:__imp_EnterCriticalSection
0x1800ab841  cmp     [rsp+88h+var_48], 0
0x1800ab846  jnz     short loc_1800AB86D
0x1800ab848  nop     dword ptr [rax+rax+00000000h]
0x1800ab850  mov     r8d, 0FFFFFFFFh; dwMilliseconds
0x1800ab856  lea     rdx, [rsp+88h+CriticalSection]; CriticalSection
0x1800ab85b  lea     rcx, [rsp+88h+ConditionVariable]; ConditionVariable
0x1800ab860  call    cs:__imp_SleepConditionVariableCS
0x1800ab866  cmp     [rsp+88h+var_48], 0
0x1800ab86b  jz      short loc_1800AB850
0x1800ab86d  lea     rcx, [rsp+88h+CriticalSection]; lpCriticalSection
0x1800ab872  call    cs:__imp_LeaveCriticalSection
0x1800ab878  lea     rcx, [rsp+88h+CriticalSection]; lpCriticalSection
0x1800ab87d  call    cs:__imp_DeleteCriticalSection
0x1800ab883  xor     eax, eax
0x1800ab885  add     rsp, 80h
0x1800ab88c  pop     rbx
0x1800ab88d  retn
```
