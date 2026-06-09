# BaseSrvExitDOSTask

- ea: `0x180009e9c`
- end: `0x180009fab`
- name: `BaseSrvExitDOSTask`
- size: `271`
- prototype: `__int64 __fastcall(_QWORD *, int)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, service_task`

## callers

- `0x180009fc0`

## callees

- `0x180009e9c`
- `0x18000a54c`
- `0x18000a8fc`

## import_xrefs

- `ntdll!NtClose` at `0x180009efb`
- `ntdll!NtClose` at `0x180009f35`
- `ntdll!NtClose` at `0x180009f52`
- `ntdll!NtClose` at `0x180009efb`
- `ntdll!NtClose` at `0x180009f35`
- `ntdll!NtClose` at `0x180009f52`
- `ntdll!RtlEnterCriticalSection` at `0x180009ec1`
- `ntdll!RtlEnterCriticalSection` at `0x180009ec1`
- `ntdll!RtlLeaveCriticalSection` at `0x180009f6d`
- `ntdll!RtlLeaveCriticalSection` at `0x180009f84`
- `ntdll!RtlLeaveCriticalSection` at `0x180009f6d`
- `ntdll!RtlLeaveCriticalSection` at `0x180009f84`
- `ntdll!NtSetEvent` at `0x180009f25`
- `ntdll!NtSetEvent` at `0x180009f25`

## pseudocode

```c
__int64 __fastcall BaseSrvExitDOSTask(_QWORD *a1, int a2)
{
  int ConsoleRecord; // ebp
  PVOID v5; // rdi
  void *v6; // rcx
  __int64 **i; // rbx
  __int64 *v8; // rcx
  PVOID P; // [rsp+30h] [rbp+8h] BYREF

  P = 0;
  RtlEnterCriticalSection(&BaseSrvVDMCriticalSection);
  ConsoleRecord = BaseSrvGetConsoleRecord(*a1, &P);
  if ( ConsoleRecord >= 0 && (v5 = P, a2 == *((_DWORD *)P + 11)) )
  {
    v6 = (void *)*((_QWORD *)P + 4);
    if ( v6 )
    {
      NtClose(v6);
      *((_QWORD *)v5 + 4) = 0;
      a1[2] = *((_QWORD *)v5 + 3);
    }
    for ( i = (__int64 **)*((_QWORD *)v5 + 9); i; i = (__int64 **)*i )
    {
      v8 = i[3];
      if ( v8 )
      {
        NtSetEvent(v8, 0);
        NtClose(i[3]);
        i[3] = 0;
      }
    }
    NtClose(*((HANDLE *)v5 + 2));
    BaseSrvFreeConsoleRecord(v5);
    RtlLeaveCriticalSection(&BaseSrvVDMCriticalSection);
    return (unsigned int)ConsoleRecord;
  }
  else
  {
    RtlLeaveCriticalSection(&BaseSrvVDMCriticalSection);
    return 3221225485LL;
  }
}

```

## disassembly

```asm
0x180009e9c  mov     rax, rsp
0x180009e9f  mov     [rax+10h], rbx
0x180009ea3  mov     [rax+18h], rbp
0x180009ea7  mov     [rax+20h], rsi
0x180009eab  push    rdi
0x180009eac  sub     rsp, 20h
0x180009eb0  and     qword ptr [rax+8], 0
0x180009eb5  mov     rsi, rcx
0x180009eb8  lea     rcx, BaseSrvVDMCriticalSection; CriticalSection
0x180009ebf  mov     ebx, edx
0x180009ec1  call    cs:__imp_RtlEnterCriticalSection
0x180009ec8  nop     dword ptr [rax+rax+00h]
0x180009ecd  mov     rcx, [rsi]
0x180009ed0  lea     rdx, [rsp+28h+P]
0x180009ed5  call    BaseSrvGetConsoleRecord
0x180009eda  mov     ebp, eax
0x180009edc  test    eax, eax
0x180009ede  js      loc_180009F7D
0x180009ee4  mov     rdi, [rsp+28h+P]
0x180009ee9  cmp     ebx, [rdi+2Ch]
0x180009eec  jnz     loc_180009F7D
0x180009ef2  mov     rcx, [rdi+20h]; Handle
0x180009ef6  test    rcx, rcx
0x180009ef9  jz      short loc_180009F14
0x180009efb  call    cs:__imp_NtClose
0x180009f02  nop     dword ptr [rax+rax+00h]
0x180009f07  and     qword ptr [rdi+20h], 0
0x180009f0c  mov     rax, [rdi+18h]
0x180009f10  mov     [rsi+10h], rax
0x180009f14  mov     rbx, [rdi+48h]
0x180009f18  jmp     short loc_180009F49
0x180009f1a  mov     rcx, [rbx+18h]; EventHandle
0x180009f1e  test    rcx, rcx
0x180009f21  jz      short loc_180009F46
0x180009f23  xor     edx, edx; PreviousState
0x180009f25  call    cs:__imp_NtSetEvent
0x180009f2c  nop     dword ptr [rax+rax+00h]
0x180009f31  mov     rcx, [rbx+18h]; Handle
0x180009f35  call    cs:__imp_NtClose
0x180009f3c  nop     dword ptr [rax+rax+00h]
0x180009f41  and     qword ptr [rbx+18h], 0
0x180009f46  mov     rbx, [rbx]
0x180009f49  test    rbx, rbx
0x180009f4c  jnz     short loc_180009F1A
0x180009f4e  mov     rcx, [rdi+10h]; Handle
0x180009f52  call    cs:__imp_NtClose
0x180009f59  nop     dword ptr [rax+rax+00h]
0x180009f5e  mov     rcx, rdi; P
0x180009f61  call    BaseSrvFreeConsoleRecord
0x180009f66  lea     rcx, BaseSrvVDMCriticalSection; CriticalSection
0x180009f6d  call    cs:__imp_RtlLeaveCriticalSection
0x180009f74  nop     dword ptr [rax+rax+00h]
0x180009f79  mov     eax, ebp
0x180009f7b  jmp     short loc_180009F95
0x180009f7d  lea     rcx, BaseSrvVDMCriticalSection; CriticalSection
0x180009f84  call    cs:__imp_RtlLeaveCriticalSection
0x180009f8b  nop     dword ptr [rax+rax+00h]
0x180009f90  mov     eax, 0C000000Dh
0x180009f95  mov     rbx, [rsp+28h+arg_8]
0x180009f9a  mov     rbp, [rsp+28h+arg_10]
0x180009f9f  mov     rsi, [rsp+28h+arg_18]
0x180009fa4  add     rsp, 20h
0x180009fa8  pop     rdi
0x180009fa9  retn
```
