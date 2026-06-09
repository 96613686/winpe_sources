# std::_Associated_state<std::future_status>::_Wait(void)

- ea: `0x180019c80`
- end: `0x180019d9e`
- name: `?_Wait@?$_Associated_state@W4future_status@std@@@std@@UEAAXXZ`
- size: `286`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x180019c80`
- `0x180036d78`
- `0x180036ed8`
- `0x1800563c8`
- `0x180056500`
- `0x18005c5e0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180019d58`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180019d58`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180019d26`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180019d26`
- `api-ms-win-core-synch-l1-2-0!SleepConditionVariableSRW` at `0x180019d1c`
- `api-ms-win-core-synch-l1-2-0!SleepConditionVariableSRW` at `0x180019d1c`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall std::_Associated_state<enum std::future_status>::_Wait(__int64 a1)
{
  __int64 v2; // rdi
  __int64 v3; // rdi
  __int64 v4; // rcx
  __int128 v6; // [rsp+28h] [rbp-20h] BYREF

  v2 = a1 + 32;
  v6 = (unsigned __int64)(a1 + 32);
  if ( (unsigned int)mtx_do_lock(a1 + 32) )
    std::_Throw_Cpp_error(5);
  if ( *(_DWORD *)(v2 + 76) == 0x7FFFFFFF )
  {
    *(_DWORD *)(v2 + 76) = 2147483646;
    std::_Throw_Cpp_error(6);
  }
  BYTE8(v6) = 1;
  if ( !*(_BYTE *)(a1 + 194) )
  {
    *(_BYTE *)(a1 + 194) = 1;
    (*(void (__fastcall **)(__int64, __int128 *))(*(_QWORD *)a1 + 32LL))(a1, &v6);
  }
  while ( !*(_DWORD *)(a1 + 188) )
  {
    v3 = v6;
    *(_DWORD *)(v6 + 72) = -1;
    --*(_DWORD *)(v3 + 76);
    if ( !SleepConditionVariableSRW((PCONDITION_VARIABLE)(a1 + 120), (PSRWLOCK)(v3 + 16), 0xFFFFFFFF, 0) )
      abort();
    *(_DWORD *)(v3 + 72) = GetCurrentThreadId();
    ++*(_DWORD *)(v3 + 76);
  }
  if ( BYTE8(v6) )
  {
    v4 = v6;
    if ( (*(_DWORD *)(v6 + 76))-- == 1 )
    {
      *(_DWORD *)(v4 + 72) = -1;
      ReleaseSRWLockExclusive((PSRWLOCK)(v4 + 16));
    }
  }
}

```

## disassembly

```asm
0x180019c80  mov     [rsp+arg_8], rbx
0x180019c85  mov     [rsp+arg_10], rsi
0x180019c8a  push    rdi
0x180019c8b  sub     rsp, 40h
0x180019c8f  mov     rax, cs:__security_cookie
0x180019c96  xor     rax, rsp
0x180019c99  mov     [rsp+48h+var_10], rax
0x180019c9e  mov     rbx, rcx
0x180019ca1  xorps   xmm0, xmm0
0x180019ca4  movups  [rsp+48h+var_20], xmm0
0x180019ca9  lea     rdi, [rcx+20h]
0x180019cad  mov     qword ptr [rsp+48h+var_20], rdi
0x180019cb2  mov     byte ptr [rsp+48h+var_20+8], 0
0x180019cb7  mov     rcx, rdi
0x180019cba  call    mtx_do_lock
0x180019cbf  test    eax, eax
0x180019cc1  jnz     loc_180019D93
0x180019cc7  cmp     dword ptr [rdi+4Ch], 7FFFFFFFh
0x180019cce  jz      loc_180019D7B
0x180019cd4  mov     byte ptr [rsp+48h+var_20+8], 1
0x180019cd9  cmp     [rbx+0C2h], al
0x180019cdf  jnz     short loc_180019D32
0x180019ce1  mov     byte ptr [rbx+0C2h], 1
0x180019ce8  mov     rax, [rbx]
0x180019ceb  lea     rdx, [rsp+48h+var_20]
0x180019cf0  mov     rcx, rbx
0x180019cf3  mov     rax, [rax+20h]
0x180019cf7  call    _guard_dispatch_icall
0x180019cfc  jmp     short loc_180019D32
0x180019cfe  mov     rdi, qword ptr [rsp+48h+var_20]
0x180019d03  mov     dword ptr [rdi+48h], 0FFFFFFFFh
0x180019d0a  dec     dword ptr [rdi+4Ch]
0x180019d0d  lea     rdx, [rdi+10h]; SRWLock
0x180019d11  xor     r9d, r9d; Flags
0x180019d14  or      r8d, 0FFFFFFFFh; dwMilliseconds
0x180019d18  lea     rcx, [rbx+78h]; ConditionVariable
0x180019d1c  call    cs:__imp_SleepConditionVariableSRW
0x180019d22  test    eax, eax
0x180019d24  jz      short loc_180019D8D
0x180019d26  call    cs:__imp_GetCurrentThreadId
0x180019d2c  mov     [rdi+48h], eax
0x180019d2f  inc     dword ptr [rdi+4Ch]
0x180019d32  cmp     dword ptr [rbx+0BCh], 0
0x180019d39  jz      short loc_180019CFE
0x180019d3b  cmp     byte ptr [rsp+48h+var_20+8], 0
0x180019d40  jz      short loc_180019D5E
0x180019d42  mov     rcx, qword ptr [rsp+48h+var_20]
0x180019d47  sub     dword ptr [rcx+4Ch], 1
0x180019d4b  jnz     short loc_180019D5E
0x180019d4d  mov     dword ptr [rcx+48h], 0FFFFFFFFh
0x180019d54  add     rcx, 10h; SRWLock
0x180019d58  call    cs:__imp_ReleaseSRWLockExclusive
0x180019d5e  mov     rcx, [rsp+48h+var_10]
0x180019d63  xor     rcx, rsp; StackCookie
0x180019d66  call    __security_check_cookie
0x180019d6b  mov     rbx, [rsp+48h+arg_8]
0x180019d70  mov     rsi, [rsp+48h+arg_10]
0x180019d75  add     rsp, 40h
0x180019d79  pop     rdi
0x180019d7a  retn
0x180019d7b  mov     dword ptr [rdi+4Ch], 7FFFFFFEh
0x180019d82  mov     ecx, 6; int
0x180019d87  call    ?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x180019d8d  call    abort
0x180019d93  mov     ecx, 5; int
0x180019d98  call    ?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
```
