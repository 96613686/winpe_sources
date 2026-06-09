# Microsoft::CoreUI::Dispatch::Timeout::get_TimerHandle(void)

- ea: `0x18006568c`
- end: `0x1800656db`
- name: `?get_TimerHandle@Timeout@Dispatch@CoreUI@Microsoft@@QEAA?AUWin32Handle@Support@34@XZ`
- size: `79`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800654ec`
- `0x1800a9824`

## callees

- `0x18006568c`
- `0x18008f584`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateWaitableTimerExW` at `0x1800656c4`
- `api-ms-win-core-synch-l1-1-0!CreateWaitableTimerExW` at `0x1800656c4`

## pseudocode

```c
_QWORD *__fastcall Microsoft::CoreUI::Dispatch::Timeout::get_TimerHandle(__int64 a1, _QWORD *a2)
{
  HANDLE WaitableTimer; // rax

  WaitableTimer = *(HANDLE *)(a1 + 56);
  if ( !WaitableTimer )
  {
    WaitableTimer = CreateWaitableTimerExW(0, 0, 1u, 0x1F0003u);
    if ( !WaitableTimer )
      Cn::FailFast::ForWin32();
    *(_QWORD *)(a1 + 56) = WaitableTimer;
  }
  *a2 = WaitableTimer;
  return a2;
}

```

## disassembly

```asm
0x18006568c  mov     [rsp+arg_0], rbx
0x180065691  push    rdi
0x180065692  sub     rsp, 20h
0x180065696  mov     rax, [rcx+38h]
0x18006569a  mov     rbx, rdx
0x18006569d  mov     rdi, rcx
0x1800656a0  test    rax, rax
0x1800656a3  jz      short loc_1800656B6
0x1800656a5  mov     [rbx], rax
0x1800656a8  mov     rax, rbx
0x1800656ab  mov     rbx, [rsp+28h+arg_0]
0x1800656b0  add     rsp, 20h
0x1800656b4  pop     rdi
0x1800656b5  retn
0x1800656b6  xor     edx, edx; lpTimerName
0x1800656b8  xor     ecx, ecx; lpTimerAttributes
0x1800656ba  mov     r9d, 1F0003h; dwDesiredAccess
0x1800656c0  lea     r8d, [rdx+1]; dwFlags
0x1800656c4  call    cs:__imp_CreateWaitableTimerExW
0x1800656ca  test    rax, rax
0x1800656cd  jnz     short loc_1800656D5
0x1800656cf  call    ?ForWin32@FailFast@Cn@@SAXXZ; Cn::FailFast::ForWin32(void)
0x1800656d5  mov     [rdi+38h], rax
0x1800656d9  jmp     short loc_1800656A5
```
