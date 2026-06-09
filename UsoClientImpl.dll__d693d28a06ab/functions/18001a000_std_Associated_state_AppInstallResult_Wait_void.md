# std::_Associated_state<AppInstallResult>::_Wait(void)

- ea: `0x18001a000`
- end: `0x18001a121`
- name: `?_Wait@?$_Associated_state@UAppInstallResult@@@std@@UEAAXXZ`
- size: `289`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `installer_update`

## callees

- `0x18001a000`
- `0x180036d78`
- `0x180036ed8`
- `0x1800563c8`
- `0x180056500`
- `0x18005c5e0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001a0db`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001a0db`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001a0a9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001a0a9`
- `api-ms-win-core-synch-l1-2-0!SleepConditionVariableSRW` at `0x18001a09f`
- `api-ms-win-core-synch-l1-2-0!SleepConditionVariableSRW` at `0x18001a09f`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall std::_Associated_state<AppInstallResult>::_Wait(__int64 a1)
{
  __int64 v2; // rdi
  __int64 v3; // rdi
  __int64 v4; // rcx
  __int128 v6; // [rsp+28h] [rbp-20h] BYREF

  v2 = a1 + 56;
  v6 = (unsigned __int64)(a1 + 56);
  if ( (unsigned int)mtx_do_lock(a1 + 56) )
    std::_Throw_Cpp_error(5);
  if ( *(_DWORD *)(v2 + 76) == 0x7FFFFFFF )
  {
    *(_DWORD *)(v2 + 76) = 2147483646;
    std::_Throw_Cpp_error(6);
  }
  BYTE8(v6) = 1;
  if ( !*(_BYTE *)(a1 + 218) )
  {
    *(_BYTE *)(a1 + 218) = 1;
    (*(void (__fastcall **)(__int64, __int128 *))(*(_QWORD *)a1 + 32LL))(a1, &v6);
  }
  while ( !*(_DWORD *)(a1 + 212) )
  {
    v3 = v6;
    *(_DWORD *)(v6 + 72) = -1;
    --*(_DWORD *)(v3 + 76);
    if ( !SleepConditionVariableSRW((PCONDITION_VARIABLE)(a1 + 144), (PSRWLOCK)(v3 + 16), 0xFFFFFFFF, 0) )
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
0x18001a000  mov     [rsp+arg_8], rbx
0x18001a005  mov     [rsp+arg_10], rsi
0x18001a00a  push    rdi
0x18001a00b  sub     rsp, 40h
0x18001a00f  mov     rax, cs:__security_cookie
0x18001a016  xor     rax, rsp
0x18001a019  mov     [rsp+48h+var_10], rax
0x18001a01e  mov     rbx, rcx
0x18001a021  xorps   xmm0, xmm0
0x18001a024  movups  [rsp+48h+var_20], xmm0
0x18001a029  lea     rdi, [rcx+38h]
0x18001a02d  mov     qword ptr [rsp+48h+var_20], rdi
0x18001a032  mov     byte ptr [rsp+48h+var_20+8], 0
0x18001a037  mov     rcx, rdi
0x18001a03a  call    mtx_do_lock
0x18001a03f  test    eax, eax
0x18001a041  jnz     loc_18001A116
0x18001a047  cmp     dword ptr [rdi+4Ch], 7FFFFFFFh
0x18001a04e  jz      loc_18001A0FE
0x18001a054  mov     byte ptr [rsp+48h+var_20+8], 1
0x18001a059  cmp     [rbx+0DAh], al
0x18001a05f  jnz     short loc_18001A0B5
0x18001a061  mov     byte ptr [rbx+0DAh], 1
0x18001a068  mov     rax, [rbx]
0x18001a06b  lea     rdx, [rsp+48h+var_20]
0x18001a070  mov     rcx, rbx
0x18001a073  mov     rax, [rax+20h]
0x18001a077  call    _guard_dispatch_icall
0x18001a07c  jmp     short loc_18001A0B5
0x18001a07e  mov     rdi, qword ptr [rsp+48h+var_20]
0x18001a083  mov     dword ptr [rdi+48h], 0FFFFFFFFh
0x18001a08a  dec     dword ptr [rdi+4Ch]
0x18001a08d  lea     rdx, [rdi+10h]; SRWLock
0x18001a091  xor     r9d, r9d; Flags
0x18001a094  or      r8d, 0FFFFFFFFh; dwMilliseconds
0x18001a098  lea     rcx, [rbx+90h]; ConditionVariable
0x18001a09f  call    cs:__imp_SleepConditionVariableSRW
0x18001a0a5  test    eax, eax
0x18001a0a7  jz      short loc_18001A110
0x18001a0a9  call    cs:__imp_GetCurrentThreadId
0x18001a0af  mov     [rdi+48h], eax
0x18001a0b2  inc     dword ptr [rdi+4Ch]
0x18001a0b5  cmp     dword ptr [rbx+0D4h], 0
0x18001a0bc  jz      short loc_18001A07E
0x18001a0be  cmp     byte ptr [rsp+48h+var_20+8], 0
0x18001a0c3  jz      short loc_18001A0E1
0x18001a0c5  mov     rcx, qword ptr [rsp+48h+var_20]
0x18001a0ca  sub     dword ptr [rcx+4Ch], 1
0x18001a0ce  jnz     short loc_18001A0E1
0x18001a0d0  mov     dword ptr [rcx+48h], 0FFFFFFFFh
0x18001a0d7  add     rcx, 10h; SRWLock
0x18001a0db  call    cs:__imp_ReleaseSRWLockExclusive
0x18001a0e1  mov     rcx, [rsp+48h+var_10]
0x18001a0e6  xor     rcx, rsp; StackCookie
0x18001a0e9  call    __security_check_cookie
0x18001a0ee  mov     rbx, [rsp+48h+arg_8]
0x18001a0f3  mov     rsi, [rsp+48h+arg_10]
0x18001a0f8  add     rsp, 40h
0x18001a0fc  pop     rdi
0x18001a0fd  retn
0x18001a0fe  mov     dword ptr [rdi+4Ch], 7FFFFFFEh
0x18001a105  mov     ecx, 6; int
0x18001a10a  call    ?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x18001a110  call    abort
0x18001a116  mov     ecx, 5; int
0x18001a11b  call    ?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
```
