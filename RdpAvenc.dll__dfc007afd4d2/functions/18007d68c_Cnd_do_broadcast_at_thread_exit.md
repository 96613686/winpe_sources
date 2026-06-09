# _Cnd_do_broadcast_at_thread_exit

- ea: `0x18007d68c`
- end: `0x18007d79e`
- name: `_Cnd_do_broadcast_at_thread_exit`
- size: `274`
- prototype: `void __cdecl()`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x180021d70`
- `0x180047ad0`
- `0x180047b10`

## callees

- `0x1800103c0`
- `0x180010bc8`
- `0x18007d68c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18007d714`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18007d76e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18007d714`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18007d76e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18007d695`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18007d695`
- `api-ms-win-core-synch-l1-2-0!WakeAllConditionVariable` at `0x18007d723`
- `api-ms-win-core-synch-l1-2-0!WakeAllConditionVariable` at `0x18007d723`

## pseudocode

```c
void __cdecl Cnd_do_broadcast_at_thread_exit()
{
  DWORD CurrentThreadId; // ebp
  __int64 *v1; // rbx
  int v2; // ecx
  int v3; // esi
  _DWORD *v4; // rax
  __int64 v5; // rcx

  CurrentThreadId = GetCurrentThreadId();
  if ( (unsigned int)mtx_do_lock(qword_1800C1CA0) )
    std::_Throw_Cpp_error(5);
  if ( dword_1800C1CEC == 0x7FFFFFFF )
  {
    dword_1800C1CEC = 2147483646;
    std::_Throw_Cpp_error(6);
  }
  v1 = qword_1800C2390;
  do
  {
    v2 = *((_DWORD *)v1 + 200);
    if ( v2 )
    {
      v3 = 0;
      do
      {
        if ( v3 >= 20 )
          break;
        if ( v1[5 * v3 + 2] && LODWORD(v1[5 * v3 + 1]) == CurrentThreadId )
        {
          v4 = (_DWORD *)v1[5 * v3 + 4];
          if ( v4 )
            *v4 = 1;
          v5 = v1[5 * v3 + 2];
          if ( (*(_DWORD *)(v5 + 76))-- == 1 )
          {
            *(_DWORD *)(v5 + 72) = -1;
            ReleaseSRWLockExclusive((PSRWLOCK)(v5 + 16));
          }
          WakeAllConditionVariable((PCONDITION_VARIABLE)(v1[5 * v3 + 3] + 8));
          v1[5 * v3 + 2] = 0;
          v2 = --*((_DWORD *)v1 + 200);
        }
        ++v3;
      }
      while ( v2 );
    }
    v1 = (__int64 *)v1[101];
  }
  while ( v1 );
  if ( !--dword_1800C1CEC )
  {
    dword_1800C1CE8 = -1;
    ReleaseSRWLockExclusive(&stru_1800C1CB0);
  }
}

```

## disassembly

```asm
0x18007d68c  push    rbx
0x18007d68e  push    rbp
0x18007d68f  push    rsi
0x18007d690  push    rdi
0x18007d691  sub     rsp, 28h
0x18007d695  call    cs:__imp_GetCurrentThreadId
0x18007d69b  mov     ebp, eax
0x18007d69d  lea     rcx, qword_1800C1CA0
0x18007d6a4  call    mtx_do_lock
0x18007d6a9  test    eax, eax
0x18007d6ab  jnz     loc_18007D793
0x18007d6b1  cmp     cs:dword_1800C1CEC, 7FFFFFFFh
0x18007d6bb  jz      loc_18007D77E
0x18007d6c1  lea     rbx, qword_1800C2390
0x18007d6c8  mov     ecx, [rbx+320h]
0x18007d6ce  test    ecx, ecx
0x18007d6d0  jz      short loc_18007D744
0x18007d6d2  xor     esi, esi
0x18007d6d4  cmp     esi, 14h
0x18007d6d7  jge     short loc_18007D744
0x18007d6d9  movsxd  rax, esi
0x18007d6dc  lea     rdi, [rax+rax*4]
0x18007d6e0  cmp     qword ptr [rbx+rdi*8+10h], 0
0x18007d6e6  jz      short loc_18007D73E
0x18007d6e8  cmp     [rbx+rdi*8+8], ebp
0x18007d6ec  jnz     short loc_18007D73E
0x18007d6ee  mov     rax, [rbx+rdi*8+20h]
0x18007d6f3  test    rax, rax
0x18007d6f6  jz      short loc_18007D6FE
0x18007d6f8  mov     dword ptr [rax], 1
0x18007d6fe  mov     rcx, [rbx+rdi*8+10h]
0x18007d703  sub     dword ptr [rcx+4Ch], 1
0x18007d707  jnz     short loc_18007D71A
0x18007d709  mov     dword ptr [rcx+48h], 0FFFFFFFFh
0x18007d710  add     rcx, 10h; SRWLock
0x18007d714  call    cs:__imp_ReleaseSRWLockExclusive
0x18007d71a  mov     rcx, [rbx+rdi*8+18h]
0x18007d71f  add     rcx, 8; ConditionVariable
0x18007d723  call    cs:__imp_WakeAllConditionVariable
0x18007d729  mov     qword ptr [rbx+rdi*8+10h], 0
0x18007d732  dec     dword ptr [rbx+320h]
0x18007d738  mov     ecx, [rbx+320h]
0x18007d73e  inc     esi
0x18007d740  test    ecx, ecx
0x18007d742  jnz     short loc_18007D6D4
0x18007d744  mov     rbx, [rbx+328h]
0x18007d74b  test    rbx, rbx
0x18007d74e  jnz     loc_18007D6C8
0x18007d754  sub     cs:dword_1800C1CEC, 1
0x18007d75b  jnz     short loc_18007D775
0x18007d75d  mov     cs:dword_1800C1CE8, 0FFFFFFFFh
0x18007d767  lea     rcx, stru_1800C1CB0; SRWLock
0x18007d76e  call    cs:__imp_ReleaseSRWLockExclusive
0x18007d774  nop
0x18007d775  add     rsp, 28h
0x18007d779  pop     rdi
0x18007d77a  pop     rsi
0x18007d77b  pop     rbp
0x18007d77c  pop     rbx
0x18007d77d  retn
0x18007d77e  mov     cs:dword_1800C1CEC, 7FFFFFFEh
0x18007d788  mov     ecx, 6; int
0x18007d78d  call    ?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x18007d793  mov     ecx, 5; int
0x18007d798  call    ?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
```
