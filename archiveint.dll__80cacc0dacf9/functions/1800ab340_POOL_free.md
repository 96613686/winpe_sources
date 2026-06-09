# POOL_free

- ea: `0x1800ab340`
- end: `0x1800ab444`
- name: `POOL_free`
- size: `260`
- prototype: `__int64 __fastcall(void *Block)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x1800a4630`
- `0x1800ab170`

## callees

- `0x1800ab340`
- `0x1800ab8a0`
- `0x18011a010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800ab3ea`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800ab415`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800ab438`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800ab3ea`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800ab415`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800ab438`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800ab378`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800ab378`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800ab364`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800ab364`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800ab3ba`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800ab3ba`
- `api-ms-win-core-synch-l1-2-0!WakeAllConditionVariable` at `0x1800ab385`
- `api-ms-win-core-synch-l1-2-0!WakeAllConditionVariable` at `0x1800ab392`
- `api-ms-win-core-synch-l1-2-0!WakeAllConditionVariable` at `0x1800ab385`
- `api-ms-win-core-synch-l1-2-0!WakeAllConditionVariable` at `0x1800ab392`

## pseudocode

```c
void __fastcall POOL_free(char *Block)
{
  unsigned __int64 i; // rdi
  void *v3; // rcx
  void (__fastcall *v4)(_QWORD, _QWORD); // rax
  void *v5; // rcx
  void (__fastcall *v6)(_QWORD, _QWORD); // rax
  void (__fastcall *v7)(_QWORD, char *); // rax

  if ( Block )
  {
    EnterCriticalSection((LPCRITICAL_SECTION)(Block + 96));
    *((_DWORD *)Block + 38) = 1;
    LeaveCriticalSection((LPCRITICAL_SECTION)(Block + 96));
    WakeAllConditionVariable((PCONDITION_VARIABLE)Block + 17);
    WakeAllConditionVariable((PCONDITION_VARIABLE)Block + 18);
    for ( i = 0; i < *((_QWORD *)Block + 4); ++i )
      ZSTD_pthread_join(*(HANDLE *)(*((_QWORD *)Block + 3) + 8 * i));
    DeleteCriticalSection((LPCRITICAL_SECTION)(Block + 96));
    v3 = (void *)*((_QWORD *)Block + 6);
    if ( v3 )
    {
      v4 = (void (__fastcall *)(_QWORD, _QWORD))*((_QWORD *)Block + 1);
      if ( v4 )
        v4(*((_QWORD *)Block + 2), *((_QWORD *)Block + 6));
      else
        free(v3);
    }
    v5 = (void *)*((_QWORD *)Block + 3);
    if ( v5 )
    {
      v6 = (void (__fastcall *)(_QWORD, _QWORD))*((_QWORD *)Block + 1);
      if ( v6 )
        v6(*((_QWORD *)Block + 2), *((_QWORD *)Block + 3));
      else
        free(v5);
    }
    v7 = (void (__fastcall *)(_QWORD, char *))*((_QWORD *)Block + 1);
    if ( v7 )
      v7(*((_QWORD *)Block + 2), Block);
    else
      free(Block);
  }
}

```

## disassembly

```asm
0x1800ab340  test    rcx, rcx
0x1800ab343  jz      locret_1800AB443
0x1800ab349  push    rbx
0x1800ab34a  sub     rsp, 20h
0x1800ab34e  mov     rbx, rcx
0x1800ab351  mov     [rsp+28h+arg_0], rbp
0x1800ab356  mov     [rsp+28h+arg_8], rsi
0x1800ab35b  add     rcx, 60h ; '`'; lpCriticalSection
0x1800ab35f  mov     [rsp+28h+arg_10], rdi
0x1800ab364  call    cs:__imp_EnterCriticalSection
0x1800ab36a  lea     rcx, [rbx+60h]; lpCriticalSection
0x1800ab36e  mov     dword ptr [rbx+98h], 1
0x1800ab378  call    cs:__imp_LeaveCriticalSection
0x1800ab37e  lea     rcx, [rbx+88h]; ConditionVariable
0x1800ab385  call    cs:__imp_WakeAllConditionVariable
0x1800ab38b  lea     rcx, [rbx+90h]; ConditionVariable
0x1800ab392  call    cs:__imp_WakeAllConditionVariable
0x1800ab398  xor     edi, edi
0x1800ab39a  cmp     [rbx+20h], rdi
0x1800ab39e  jbe     short loc_1800AB3B6
0x1800ab3a0  mov     rcx, [rbx+18h]
0x1800ab3a4  mov     rcx, [rcx+rdi*8]; hObject
0x1800ab3a8  call    ZSTD_pthread_join
0x1800ab3ad  inc     rdi
0x1800ab3b0  cmp     rdi, [rbx+20h]
0x1800ab3b4  jb      short loc_1800AB3A0
0x1800ab3b6  lea     rcx, [rbx+60h]; lpCriticalSection
0x1800ab3ba  call    cs:__imp_DeleteCriticalSection
0x1800ab3c0  mov     rcx, [rbx+30h]; Block
0x1800ab3c4  mov     rdi, [rsp+28h+arg_10]
0x1800ab3c9  mov     rbp, [rsp+28h+arg_0]
0x1800ab3ce  test    rcx, rcx
0x1800ab3d1  jz      short loc_1800AB3F0
0x1800ab3d3  mov     rax, [rbx+8]
0x1800ab3d7  test    rax, rax
0x1800ab3da  jz      short loc_1800AB3EA
0x1800ab3dc  mov     rdx, rcx
0x1800ab3df  mov     rcx, [rbx+10h]
0x1800ab3e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ab3e8  jmp     short loc_1800AB3F0
0x1800ab3ea  call    cs:__imp_free
0x1800ab3f0  mov     rcx, [rbx+18h]; Block
0x1800ab3f4  mov     rsi, [rsp+28h+arg_8]
0x1800ab3f9  test    rcx, rcx
0x1800ab3fc  jz      short loc_1800AB41B
0x1800ab3fe  mov     rax, [rbx+8]
0x1800ab402  test    rax, rax
0x1800ab405  jz      short loc_1800AB415
0x1800ab407  mov     rdx, rcx
0x1800ab40a  mov     rcx, [rbx+10h]
0x1800ab40e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ab413  jmp     short loc_1800AB41B
0x1800ab415  call    cs:__imp_free
0x1800ab41b  mov     rax, [rbx+8]
0x1800ab41f  test    rax, rax
0x1800ab422  jz      short loc_1800AB435
0x1800ab424  mov     rcx, [rbx+10h]
0x1800ab428  mov     rdx, rbx
0x1800ab42b  add     rsp, 20h
0x1800ab42f  pop     rbx
0x1800ab430  jmp     _guard_dispatch_icall$thunk$10345483385596137414
0x1800ab435  mov     rcx, rbx; Block
0x1800ab438  call    cs:__imp_free
0x1800ab43e  add     rsp, 20h
0x1800ab442  pop     rbx
0x1800ab443  retn
```
