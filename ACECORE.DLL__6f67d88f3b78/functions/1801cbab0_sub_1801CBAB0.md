# sub_1801CBAB0

- ea: `0x1801cbab0`
- end: `0x1801cbba7`
- name: `sub_1801CBAB0`
- size: `247`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1800691f0`

## callees

- `0x1801cb5a0`
- `0x1801cbab0`
- `0x1801d6c50`

## import_xrefs

- `KERNEL32!FreeLibrary` at `0x1801cbb8f`
- `KERNEL32!FreeLibrary` at `0x1801cbb8f`
- `KERNEL32!DeleteCriticalSection` at `0x1801cbb9c`
- `KERNEL32!DeleteCriticalSection` at `0x1801cbb9c`
- `KERNEL32!CloseHandle` at `0x1801cbb42`
- `KERNEL32!CloseHandle` at `0x1801cbb5a`
- `KERNEL32!CloseHandle` at `0x1801cbb72`
- `KERNEL32!CloseHandle` at `0x1801cbb42`
- `KERNEL32!CloseHandle` at `0x1801cbb5a`
- `KERNEL32!CloseHandle` at `0x1801cbb72`
- `KERNEL32!Sleep` at `0x1801cbb1c`
- `KERNEL32!Sleep` at `0x1801cbb1c`
- `KERNEL32!WaitForSingleObject` at `0x1801cbb2e`
- `KERNEL32!WaitForSingleObject` at `0x1801cbb2e`

## pseudocode

```c
void sub_1801CBAB0()
{
  if ( qword_18025EC78 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)qword_18025EC78 + 16LL))(qword_18025EC78);
    qword_18025EC78 = 0;
  }
  if ( qword_18025EC88 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)qword_18025EC88 + 16LL))(qword_18025EC88);
    qword_18025EC88 = 0;
  }
  if ( dword_18025EC48 )
  {
    sub_1801CB5A0(999, 99);
    while ( WaitForSingleObject(qword_18025EC40, 0x1F4u) == 258 )
      Sleep(0);
    CloseHandle(qword_18025EC40);
    qword_18025EC40 = 0;
    CloseHandle(hHandle);
    hHandle = 0;
    CloseHandle(qword_18025EC58);
    qword_18025EC58 = 0;
    if ( hLibModule )
      FreeLibrary(hLibModule);
    DeleteCriticalSection(&CriticalSection);
  }
}

```

## disassembly

```asm
0x1801cbab0  sub     rsp, 28h
0x1801cbab4  mov     rcx, cs:qword_18025EC78
0x1801cbabb  test    rcx, rcx
0x1801cbabe  jz      short loc_1801CBAD8
0x1801cbac0  mov     rax, [rcx]
0x1801cbac3  mov     rax, [rax+10h]
0x1801cbac7  call    cs:__guard_dispatch_icall_fptr
0x1801cbacd  mov     cs:qword_18025EC78, 0
0x1801cbad8  mov     rcx, cs:qword_18025EC88
0x1801cbadf  test    rcx, rcx
0x1801cbae2  jz      short loc_1801CBAFC
0x1801cbae4  mov     rax, [rcx]
0x1801cbae7  mov     rax, [rax+10h]
0x1801cbaeb  call    cs:__guard_dispatch_icall_fptr
0x1801cbaf1  mov     cs:qword_18025EC88, 0
0x1801cbafc  cmp     cs:dword_18025EC48, 0
0x1801cbb03  jz      loc_1801CBBA2
0x1801cbb09  mov     edx, 63h ; 'c'
0x1801cbb0e  mov     ecx, 3E7h
0x1801cbb13  call    sub_1801CB5A0
0x1801cbb18  jmp     short loc_1801CBB22
0x1801cbb1a  xor     ecx, ecx; dwMilliseconds
0x1801cbb1c  call    cs:__imp_Sleep
0x1801cbb22  mov     rcx, cs:qword_18025EC40; hHandle
0x1801cbb29  mov     edx, 1F4h; dwMilliseconds
0x1801cbb2e  call    cs:WaitForSingleObject
0x1801cbb34  cmp     eax, 102h
0x1801cbb39  jz      short loc_1801CBB1A
0x1801cbb3b  mov     rcx, cs:qword_18025EC40; hObject
0x1801cbb42  call    cs:CloseHandle
0x1801cbb48  mov     rcx, cs:hHandle; hObject
0x1801cbb4f  mov     cs:qword_18025EC40, 0
0x1801cbb5a  call    cs:CloseHandle
0x1801cbb60  mov     rcx, cs:qword_18025EC58; hObject
0x1801cbb67  mov     cs:hHandle, 0
0x1801cbb72  call    cs:CloseHandle
0x1801cbb78  mov     rcx, cs:hLibModule; hLibModule
0x1801cbb7f  mov     cs:qword_18025EC58, 0
0x1801cbb8a  test    rcx, rcx
0x1801cbb8d  jz      short loc_1801CBB95
0x1801cbb8f  call    cs:FreeLibrary
0x1801cbb95  lea     rcx, CriticalSection; lpCriticalSection
0x1801cbb9c  call    cs:__imp_DeleteCriticalSection
0x1801cbba2  add     rsp, 28h
0x1801cbba6  retn
```
