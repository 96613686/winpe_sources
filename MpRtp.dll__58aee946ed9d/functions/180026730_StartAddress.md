# StartAddress

- ea: `0x180026730`
- end: `0x180026795`
- name: `StartAddress`
- size: `101`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `7`
- tags: ``

## callees

- `0x180026730`
- `0x180026940`
- `0x180028bb4`
- `0x180029e28`
- `0x18002e67c`
- `0x18002e994`
- `0x1800d4260`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18002673e`
- `KERNEL32!GetLastError` at `0x18002673e`
- `KERNEL32!ExitThread` at `0x180026746`
- `KERNEL32!ExitThread` at `0x180026746`

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
  *(_QWORD *)(sub_180029E28() + 960) = Parameter;
  if ( (unsigned int)sub_18002E994() == 2 )
    Parameter[32] = (unsigned int)sub_18002E67C(1) == 0;
  v3 = (*(__int64 (__fastcall **)(_QWORD))Parameter)(*((_QWORD *)Parameter + 1));
  sub_180026940(v3);
}

```

## disassembly

```asm
0x180026730  push    rbx
0x180026732  sub     rsp, 20h
0x180026736  mov     rbx, rcx
0x180026739  test    rcx, rcx
0x18002673c  jnz     short loc_18002674D
0x18002673e  call    cs:GetLastError
0x180026744  mov     ecx, eax; dwExitCode
0x180026746  call    cs:ExitThread
0x18002674d  call    sub_180029E28
0x180026752  mov     [rax+3C0h], rbx
0x180026759  call    sub_18002E994
0x18002675e  cmp     eax, 2
0x180026761  jnz     short loc_180026773
0x180026763  lea     ecx, [rax-1]
0x180026766  call    sub_18002E67C
0x18002676b  test    eax, eax
0x18002676d  setz    al
0x180026770  mov     [rbx+20h], al
0x180026773  mov     rcx, [rbx+8]
0x180026777  mov     rax, [rbx]
0x18002677a  call    j__guard_dispatch_icall_nop
0x18002677f  mov     ecx, eax
0x180026781  call    sub_180026940
0x180026787  mov     ecx, eax
0x180026789  call    sub_180028BB4
0x18002678e  nop
0x18002678f  add     rsp, 20h
0x180026793  pop     rbx
0x180026794  retn
```
