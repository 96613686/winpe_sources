# CNTService::IsInstalled(void)

- ea: `0x1400055d0`
- end: `0x14000563a`
- name: `?IsInstalled@CNTService@@QEAAHXZ`
- size: `106`
- prototype: `__int64 __fastcall(const WCHAR *this)`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, installer_update`

## callers

- `0x140005790`

## callees

- `0x1400055d0`

## import_xrefs

- `ADVAPI32!OpenServiceW` at `0x140005609`
- `ADVAPI32!OpenServiceW` at `0x140005609`
- `ADVAPI32!CloseServiceHandle` at `0x140005617`
- `ADVAPI32!CloseServiceHandle` at `0x140005622`
- `ADVAPI32!CloseServiceHandle` at `0x140005617`
- `ADVAPI32!CloseServiceHandle` at `0x140005622`
- `ADVAPI32!OpenSCManagerW` at `0x1400055ee`
- `ADVAPI32!OpenSCManagerW` at `0x1400055ee`

## pseudocode

```c
__int64 __fastcall CNTService::IsInstalled(const WCHAR *this)
{
  unsigned int v2; // ebx
  SC_HANDLE v3; // rax
  SC_HANDLE v4; // rdi
  SC_HANDLE v5; // rax

  v2 = 0;
  v3 = OpenSCManagerW(0, 0, 0xF003Fu);
  v4 = v3;
  if ( v3 )
  {
    v5 = OpenServiceW(v3, this + 4, 1u);
    if ( v5 )
    {
      CloseServiceHandle(v5);
      v2 = 1;
    }
    CloseServiceHandle(v4);
  }
  return v2;
}

```

## disassembly

```asm
0x1400055d0  mov     [rsp+arg_0], rbx
0x1400055d5  mov     [rsp+arg_8], rsi
0x1400055da  push    rdi
0x1400055db  sub     rsp, 20h
0x1400055df  mov     rsi, rcx
0x1400055e2  xor     edx, edx; lpDatabaseName
0x1400055e4  xor     ecx, ecx; lpMachineName
0x1400055e6  mov     r8d, 0F003Fh; dwDesiredAccess
0x1400055ec  xor     ebx, ebx
0x1400055ee  call    cs:__imp_OpenSCManagerW
0x1400055f4  mov     rdi, rax
0x1400055f7  test    rax, rax
0x1400055fa  jz      short loc_140005628
0x1400055fc  lea     rdx, [rsi+8]; lpServiceName
0x140005600  mov     rcx, rax; hSCManager
0x140005603  lea     esi, [rbx+1]
0x140005606  mov     r8d, esi; dwDesiredAccess
0x140005609  call    cs:__imp_OpenServiceW
0x14000560f  test    rax, rax
0x140005612  jz      short loc_14000561F
0x140005614  mov     rcx, rax; hSCObject
0x140005617  call    cs:__imp_CloseServiceHandle
0x14000561d  mov     ebx, esi
0x14000561f  mov     rcx, rdi; hSCObject
0x140005622  call    cs:__imp_CloseServiceHandle
0x140005628  mov     rsi, [rsp+28h+arg_8]
0x14000562d  mov     eax, ebx
0x14000562f  mov     rbx, [rsp+28h+arg_0]
0x140005634  add     rsp, 20h
0x140005638  pop     rdi
0x140005639  retn
```
