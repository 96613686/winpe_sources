# BaseSrvExitDOSTask

- ea: `0x18000a194`
- end: `0x18000a296`
- name: `BaseSrvExitDOSTask`
- size: `258`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, service_task`

## callers

- `0x18000a2a0`

## callees

- `0x18000a194`
- `0x18000a7d0`
- `0x18000ab84`

## import_xrefs

- `ntdll!NtClose` at `0x18000a1ec`
- `ntdll!NtClose` at `0x18000a229`
- `ntdll!NtClose` at `0x18000a249`
- `ntdll!NtClose` at `0x18000a1ec`
- `ntdll!NtClose` at `0x18000a229`
- `ntdll!NtClose` at `0x18000a249`
- `ntdll!RtlEnterCriticalSection` at `0x18000a1b2`
- `ntdll!RtlEnterCriticalSection` at `0x18000a1b2`
- `ntdll!RtlLeaveCriticalSection` at `0x18000a264`
- `ntdll!RtlLeaveCriticalSection` at `0x18000a27b`
- `ntdll!RtlLeaveCriticalSection` at `0x18000a264`
- `ntdll!RtlLeaveCriticalSection` at `0x18000a27b`
- `ntdll!NtSetEvent` at `0x18000a219`
- `ntdll!NtSetEvent` at `0x18000a219`

## pseudocode

```c
__int64 __fastcall BaseSrvExitDOSTask(_QWORD *a1, int a2)
{
  int ConsoleRecord; // ebp
  PVOID v5; // rdi
  void *v6; // rcx
  __int64 **i; // rbx
  __int64 *v8; // rcx
  PVOID P; // [rsp+50h] [rbp+8h] BYREF

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
0x18000a194  push    rbx
0x18000a196  push    rbp
0x18000a197  push    rsi
0x18000a198  push    rdi
0x18000a199  sub     rsp, 28h
0x18000a19d  mov     rsi, rcx
0x18000a1a0  mov     [rsp+48h+P], 0
0x18000a1a9  lea     rcx, BaseSrvVDMCriticalSection; CriticalSection
0x18000a1b0  mov     ebx, edx
0x18000a1b2  call    cs:__imp_RtlEnterCriticalSection
0x18000a1b9  nop     dword ptr [rax+rax+00h]
0x18000a1be  mov     rcx, [rsi]
0x18000a1c1  lea     rdx, [rsp+48h+P]
0x18000a1c6  call    BaseSrvGetConsoleRecord
0x18000a1cb  mov     ebp, eax
0x18000a1cd  test    eax, eax
0x18000a1cf  js      loc_18000A274
0x18000a1d5  mov     rdi, [rsp+48h+P]
0x18000a1da  cmp     ebx, [rdi+2Ch]
0x18000a1dd  jnz     loc_18000A274
0x18000a1e3  mov     rcx, [rdi+20h]; Handle
0x18000a1e7  test    rcx, rcx
0x18000a1ea  jz      short loc_18000A208
0x18000a1ec  call    cs:__imp_NtClose
0x18000a1f3  nop     dword ptr [rax+rax+00h]
0x18000a1f8  mov     qword ptr [rdi+20h], 0
0x18000a200  mov     rax, [rdi+18h]
0x18000a204  mov     [rsi+10h], rax
0x18000a208  mov     rbx, [rdi+48h]
0x18000a20c  jmp     short loc_18000A240
0x18000a20e  mov     rcx, [rbx+18h]; EventHandle
0x18000a212  test    rcx, rcx
0x18000a215  jz      short loc_18000A23D
0x18000a217  xor     edx, edx; PreviousState
0x18000a219  call    cs:__imp_NtSetEvent
0x18000a220  nop     dword ptr [rax+rax+00h]
0x18000a225  mov     rcx, [rbx+18h]; Handle
0x18000a229  call    cs:__imp_NtClose
0x18000a230  nop     dword ptr [rax+rax+00h]
0x18000a235  mov     qword ptr [rbx+18h], 0
0x18000a23d  mov     rbx, [rbx]
0x18000a240  test    rbx, rbx
0x18000a243  jnz     short loc_18000A20E
0x18000a245  mov     rcx, [rdi+10h]; Handle
0x18000a249  call    cs:__imp_NtClose
0x18000a250  nop     dword ptr [rax+rax+00h]
0x18000a255  mov     rcx, rdi; P
0x18000a258  call    BaseSrvFreeConsoleRecord
0x18000a25d  lea     rcx, BaseSrvVDMCriticalSection; CriticalSection
0x18000a264  call    cs:__imp_RtlLeaveCriticalSection
0x18000a26b  nop     dword ptr [rax+rax+00h]
0x18000a270  mov     eax, ebp
0x18000a272  jmp     short loc_18000A28C
0x18000a274  lea     rcx, BaseSrvVDMCriticalSection; CriticalSection
0x18000a27b  call    cs:__imp_RtlLeaveCriticalSection
0x18000a282  nop     dword ptr [rax+rax+00h]
0x18000a287  mov     eax, 0C000000Dh
0x18000a28c  add     rsp, 28h
0x18000a290  pop     rdi
0x18000a291  pop     rsi
0x18000a292  pop     rbp
0x18000a293  pop     rbx
0x18000a294  retn
```
