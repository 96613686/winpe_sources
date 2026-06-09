# CPimcManager::InstallWindowHookApcCore(unsigned __int64)

- ea: `0x18000b360`
- end: `0x18000b399`
- name: `?InstallWindowHookApcCore@CPimcManager@@SAX_K@Z`
- size: `57`
- prototype: `void __stdcall(ULONG_PTR Parameter)`
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update`

## callees

- `0x18000b360`

## import_xrefs

- `KERNEL32!SetEvent` at `0x18000b38d`
- `KERNEL32!SetEvent` at `0x18000b38d`
- `USER32!SetWindowsHookExW` at `0x18000b37b`
- `USER32!SetWindowsHookExW` at `0x18000b37b`

## pseudocode

```c
void __fastcall CPimcManager::InstallWindowHookApcCore(ULONG_PTR Parameter)
{
  HHOOK v2; // rax
  void *v3; // rcx

  v2 = SetWindowsHookExW(4, (HOOKPROC)CPimcManager::HookProc, 0, *(_DWORD *)(Parameter + 8));
  v3 = *(void **)Parameter;
  *(_QWORD *)(Parameter + 24) = v2;
  if ( v3 )
    SetEvent(v3);
}

```

## disassembly

```asm
0x18000b360  push    rbx
0x18000b362  sub     rsp, 20h
0x18000b366  mov     r9d, [rcx+8]; dwThreadId
0x18000b36a  lea     rdx, ?HookProc@CPimcManager@@SA_JH_K_J@Z; lpfn
0x18000b371  xor     r8d, r8d; hmod
0x18000b374  mov     rbx, rcx
0x18000b377  lea     ecx, [r8+4]; idHook
0x18000b37b  call    cs:__imp_SetWindowsHookExW
0x18000b381  mov     rcx, [rbx]; hEvent
0x18000b384  mov     [rbx+18h], rax
0x18000b388  test    rcx, rcx
0x18000b38b  jz      short loc_18000B393
0x18000b38d  call    cs:__imp_SetEvent
0x18000b393  add     rsp, 20h
0x18000b397  pop     rbx
0x18000b398  retn
```
