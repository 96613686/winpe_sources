# IsInMachineOOBEOrLogonUI(void)

- ea: `0x180025c78`
- end: `0x180025cb5`
- name: `?IsInMachineOOBEOrLogonUI@@YA_NXZ`
- size: `61`
- prototype: `bool(void)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180025eb4`
- `0x180025fdc`

## callees

- `0x180025c78`
- `0x180025cbc`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180025ca7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180025ca7`
- `KERNEL32!OpenMutexW` at `0x180025c97`
- `KERNEL32!OpenMutexW` at `0x180025c97`

## pseudocode

```c
char IsInMachineOOBEOrLogonUI(void)
{
  char v0; // bl
  HANDLE v1; // rax

  v0 = IsLogonUI();
  if ( !v0 )
  {
    v1 = OpenMutexW(0x100000u, 0, L"Global\\Windows.Machine.OOBE");
    if ( v1 )
    {
      v0 = 1;
      CloseHandle(v1);
    }
  }
  return v0;
}

```

## disassembly

```asm
0x180025c78  push    rbx
0x180025c7a  sub     rsp, 20h
0x180025c7e  call    ?IsLogonUI@@YA_NXZ; IsLogonUI(void)
0x180025c83  mov     bl, al
0x180025c85  test    al, al
0x180025c87  jnz     short loc_180025CAD
0x180025c89  lea     r8, aGlobalWindowsM; "Global\\Windows.Machine.OOBE"
0x180025c90  xor     edx, edx; bInheritHandle
0x180025c92  mov     ecx, 100000h; dwDesiredAccess
0x180025c97  call    cs:__imp_OpenMutexW
0x180025c9d  test    rax, rax
0x180025ca0  jz      short loc_180025CAD
0x180025ca2  mov     rcx, rax; hObject
0x180025ca5  mov     bl, 1
0x180025ca7  call    cs:__imp_CloseHandle
0x180025cad  mov     al, bl
0x180025caf  add     rsp, 20h
0x180025cb3  pop     rbx
0x180025cb4  retn
```
