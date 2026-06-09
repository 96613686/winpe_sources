# common_end_thread

- ea: `0x18020c298`
- end: `0x18020c2f9`
- name: `common_end_thread`
- size: `97`
- prototype: `void __fastcall __noreturn(DWORD dwExitCode)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18020c440`

## callees

- `0x18020c298`
- `0x180212428`
- `0x18021bba8`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x18020c2d3`
- `KERNEL32!CloseHandle` at `0x18020c2d3`
- `KERNEL32!ExitThread` at `0x18020c2f2`
- `KERNEL32!ExitThread` at `0x18020c2f2`
- `KERNEL32!FreeLibraryAndExitThread` at `0x18020c2e9`
- `KERNEL32!FreeLibraryAndExitThread` at `0x18020c2e9`

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
0x18020c298  mov     [rsp+arg_0], rbx
0x18020c29d  push    rdi
0x18020c29e  sub     rsp, 20h
0x18020c2a2  mov     edi, ecx
0x18020c2a4  call    __acrt_getptd_noexit
0x18020c2a9  test    rax, rax
0x18020c2ac  jz      short loc_18020C2F0
0x18020c2ae  mov     rbx, [rax+3C0h]
0x18020c2b5  test    rbx, rbx
0x18020c2b8  jz      short loc_18020C2F0
0x18020c2ba  cmp     byte ptr [rbx+20h], 0
0x18020c2be  jz      short loc_18020C2C5
0x18020c2c0  call    __acrt_RoUninitialize
0x18020c2c5  mov     rcx, [rbx+10h]; hObject
0x18020c2c9  lea     rax, [rcx-1]
0x18020c2cd  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18020c2d1  ja      short loc_18020C2D9
0x18020c2d3  call    cs:__imp_CloseHandle
0x18020c2d9  mov     rcx, [rbx+18h]; hLibModule
0x18020c2dd  lea     rax, [rcx-1]
0x18020c2e1  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18020c2e5  ja      short loc_18020C2F0
0x18020c2e7  mov     edx, edi; dwExitCode
0x18020c2e9  call    cs:__imp_FreeLibraryAndExitThread
0x18020c2f0  mov     ecx, edi; dwExitCode
0x18020c2f2  call    cs:__imp_ExitThread
```
