# StartAddress

- ea: `0x18005dfa0`
- end: `0x18005e005`
- name: `StartAddress`
- size: `101`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `7`
- tags: ``

## callees

- `0x18005dfa0`
- `0x18005e1b0`
- `0x1800600f4`
- `0x180061288`
- `0x180066bbc`
- `0x18006abc0`
- `0x180125960`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18005dfae`
- `KERNEL32!GetLastError` at `0x18005dfae`
- `KERNEL32!ExitThread` at `0x18005dfb6`
- `KERNEL32!ExitThread` at `0x18005dfb6`

## pseudocode

```c
void __fastcall __noreturn StartAddress(_BYTE *Parameter)
{
  DWORD LastError; // eax
  unsigned int v3; // eax

  if ( !Parameter )
  {
    LastError = GetLastError();
    ExitThread(LastError);
  }
  *(_QWORD *)(sub_180061288() + 960) = Parameter;
  if ( (unsigned int)sub_18006ABC0() == 2 )
    Parameter[32] = (unsigned int)sub_180066BBC(1) == 0;
  v3 = (*(__int64 (__fastcall **)(_QWORD))Parameter)(*((_QWORD *)Parameter + 1));
  sub_18005E1B0(v3);
}

```

## disassembly

```asm
0x18005dfa0  push    rbx
0x18005dfa2  sub     rsp, 20h
0x18005dfa6  mov     rbx, rcx
0x18005dfa9  test    rcx, rcx
0x18005dfac  jnz     short loc_18005DFBD
0x18005dfae  call    cs:GetLastError
0x18005dfb4  mov     ecx, eax; dwExitCode
0x18005dfb6  call    cs:ExitThread
0x18005dfbd  call    sub_180061288
0x18005dfc2  mov     [rax+3C0h], rbx
0x18005dfc9  call    sub_18006ABC0
0x18005dfce  cmp     eax, 2
0x18005dfd1  jnz     short loc_18005DFE3
0x18005dfd3  lea     ecx, [rax-1]
0x18005dfd6  call    sub_180066BBC
0x18005dfdb  test    eax, eax
0x18005dfdd  setz    al
0x18005dfe0  mov     [rbx+20h], al
0x18005dfe3  mov     rcx, [rbx+8]
0x18005dfe7  mov     rax, [rbx]
0x18005dfea  call    j__guard_dispatch_icall_nop
0x18005dfef  mov     ecx, eax
0x18005dff1  call    sub_18005E1B0
0x18005dff7  mov     ecx, eax
0x18005dff9  call    sub_1800600F4
0x18005dffe  nop
0x18005dfff  add     rsp, 20h
0x18005e003  pop     rbx
0x18005e004  retn
```
