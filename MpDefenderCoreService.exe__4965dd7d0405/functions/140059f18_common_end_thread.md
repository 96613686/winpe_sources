# common_end_thread

- ea: `0x140059f18`
- end: `0x140059f79`
- name: `common_end_thread`
- size: `97`
- prototype: `void __fastcall __noreturn(DWORD dwExitCode)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x14005a0c0`

## callees

- `0x140059f18`
- `0x1400672d8`
- `0x140069e98`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x140059f53`
- `KERNEL32!CloseHandle` at `0x140059f53`
- `KERNEL32!FreeLibraryAndExitThread` at `0x140059f69`
- `KERNEL32!FreeLibraryAndExitThread` at `0x140059f69`
- `KERNEL32!ExitThread` at `0x140059f72`
- `KERNEL32!ExitThread` at `0x140059f72`

## pseudocode

```c
void __fastcall __noreturn common_end_thread(DWORD dwExitCode)
{
  __int64 v2; // rax
  __int64 v3; // rbx
  char *v4; // rcx
  HMODULE v5; // rcx

  v2 = _acrt_getptd_noexit();
  if ( v2 )
  {
    v3 = *(_QWORD *)(v2 + 960);
    if ( v3 )
    {
      if ( *(_BYTE *)(v3 + 32) )
        _acrt_RoUninitialize();
      v4 = *(char **)(v3 + 16);
      if ( (unsigned __int64)(v4 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
        CloseHandle(v4);
      v5 = *(HMODULE *)(v3 + 24);
      if ( (unsigned __int64)v5 - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
        FreeLibraryAndExitThread(v5, dwExitCode);
    }
  }
  ExitThread(dwExitCode);
}

```

## disassembly

```asm
0x140059f18  mov     [rsp+arg_0], rbx
0x140059f1d  push    rdi
0x140059f1e  sub     rsp, 20h
0x140059f22  mov     edi, ecx
0x140059f24  call    __acrt_getptd_noexit
0x140059f29  test    rax, rax
0x140059f2c  jz      short loc_140059F70
0x140059f2e  mov     rbx, [rax+3C0h]
0x140059f35  test    rbx, rbx
0x140059f38  jz      short loc_140059F70
0x140059f3a  cmp     byte ptr [rbx+20h], 0
0x140059f3e  jz      short loc_140059F45
0x140059f40  call    __acrt_RoUninitialize
0x140059f45  mov     rcx, [rbx+10h]; hObject
0x140059f49  lea     rax, [rcx-1]
0x140059f4d  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x140059f51  ja      short loc_140059F59
0x140059f53  call    cs:__imp_CloseHandle
0x140059f59  mov     rcx, [rbx+18h]; hLibModule
0x140059f5d  lea     rax, [rcx-1]
0x140059f61  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x140059f65  ja      short loc_140059F70
0x140059f67  mov     edx, edi; dwExitCode
0x140059f69  call    cs:__imp_FreeLibraryAndExitThread
0x140059f70  mov     ecx, edi; dwExitCode
0x140059f72  call    cs:__imp_ExitThread
```
