# CRequestManager::FinishRequest(HINSTANCE__ *,ulong)

- ea: `0x1800122a8`
- end: `0x1800122c9`
- name: `?FinishRequest@CRequestManager@@QEAAXPEAUHINSTANCE__@@K@Z`
- size: `33`
- prototype: `void __fastcall __noreturn(CRequestManager *this, HINSTANCE, DWORD)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18001256c`

## callees

- `0x1800122d0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibraryAndExitThread` at `0x1800122c2`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibraryAndExitThread` at `0x1800122c2`

## pseudocode

```c
void __fastcall __noreturn CRequestManager::FinishRequest(CRequestManager *this, HINSTANCE a2, DWORD a3)
{
  CRequestManager::ReleaseRequest(this, a2);
  FreeLibraryAndExitThread(a2, a3);
}

```

## disassembly

```asm
0x1800122a8  mov     [rsp+arg_0], rbx
0x1800122ad  push    rdi
0x1800122ae  sub     rsp, 20h
0x1800122b2  mov     ebx, r8d
0x1800122b5  mov     rdi, rdx
0x1800122b8  call    ?ReleaseRequest@CRequestManager@@AEAAXPEAUHINSTANCE__@@@Z; CRequestManager::ReleaseRequest(HINSTANCE__ *)
0x1800122bd  mov     edx, ebx; dwExitCode
0x1800122bf  mov     rcx, rdi; hLibModule
0x1800122c2  call    cs:__imp_FreeLibraryAndExitThread
```
