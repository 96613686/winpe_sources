# thread_start_unsigned_int_(__cdecl_)(void__)_1_

- ea: `0x140059eb0`
- end: `0x140059f15`
- name: `thread_start_unsigned_int_(__cdecl_)(void__)_1_`
- size: `101`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config`

## callees

- `0x140059eb0`
- `0x14005a0c0`
- `0x1400664e0`
- `0x140067278`
- `0x140069e48`
- `0x14006a1c4`
- `0x140166290`

## import_xrefs

- `KERNEL32!GetLastError` at `0x140059ebe`
- `KERNEL32!GetLastError` at `0x140059ebe`
- `KERNEL32!ExitThread` at `0x140059ec6`
- `KERNEL32!ExitThread` at `0x140059ec6`

## pseudocode

```c
void __fastcall __noreturn thread_start_unsigned_int____cdecl___void____1_(_BYTE *Parameter)
{
  DWORD LastError; // eax
  unsigned int v3; // eax

  if ( !Parameter )
  {
    LastError = GetLastError();
    ExitThread(LastError);
  }
  *(_QWORD *)(_acrt_getptd() + 960) = Parameter;
  if ( (unsigned int)_acrt_get_begin_thread_init_policy() == 2 )
    Parameter[32] = (unsigned int)_acrt_RoInitialize(1) == 0;
  v3 = (*(__int64 (__fastcall **)(_QWORD))Parameter)(*((_QWORD *)Parameter + 1));
  endthreadex(v3);
}

```

## disassembly

```asm
0x140059eb0  push    rbx
0x140059eb2  sub     rsp, 20h
0x140059eb6  mov     rbx, rcx
0x140059eb9  test    rcx, rcx
0x140059ebc  jnz     short loc_140059ECD
0x140059ebe  call    cs:__imp_GetLastError
0x140059ec4  mov     ecx, eax; dwExitCode
0x140059ec6  call    cs:__imp_ExitThread
0x140059ecd  call    __acrt_getptd
0x140059ed2  mov     [rax+3C0h], rbx
0x140059ed9  call    __acrt_get_begin_thread_init_policy
0x140059ede  cmp     eax, 2
0x140059ee1  jnz     short loc_140059EF3
0x140059ee3  lea     ecx, [rax-1]
0x140059ee6  call    __acrt_RoInitialize
0x140059eeb  test    eax, eax
0x140059eed  setz    al
0x140059ef0  mov     [rbx+20h], al
0x140059ef3  mov     rcx, [rbx+8]
0x140059ef7  mov     rax, [rbx]
0x140059efa  call    _guard_dispatch_icall
0x140059eff  mov     ecx, eax; ReturnCode
0x140059f01  call    _endthreadex
0x140059f07  mov     ecx, eax; Code
0x140059f09  call    _exit
0x140059f0f  add     rsp, 20h
0x140059f13  pop     rbx
0x140059f14  retn
```
