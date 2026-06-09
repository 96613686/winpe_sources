# FltGetRequestorProcessIdEx

- ea: `0x180015840`
- end: `0x180015887`
- name: `FltGetRequestorProcessIdEx`
- size: `71`
- prototype: `HANDLE __stdcall(PFLT_CALLBACK_DATA CallbackData)`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation`

## callees

- `0x180015840`

## import_xrefs

- `ntoskrnl!IoGetCurrentProcess` at `0x180015879`
- `ntoskrnl!IoGetCurrentProcess` at `0x180015879`
- `ntoskrnl!IoGetRequestorProcess` at `0x180015851`
- `ntoskrnl!IoGetRequestorProcess` at `0x180015851`
- `ntoskrnl!PsGetProcessId` at `0x180015865`
- `ntoskrnl!PsGetProcessId` at `0x180015865`

## pseudocode

```c
HANDLE __stdcall FltGetRequestorProcessIdEx(PFLT_CALLBACK_DATA CallbackData)
{
  HANDLE result; // rax

  if ( (CallbackData->Flags & 1) != 0 )
    result = IoGetRequestorProcess(*(PIRP *)&CallbackData[-3].RequestorMode);
  else
    result = IoGetCurrentProcess();
  if ( result )
    return PsGetProcessId((PEPROCESS)result);
  return result;
}

```

## disassembly

```asm
0x180015840  sub     rsp, 28h
0x180015844  mov     eax, [rcx]
0x180015846  test    al, 1
0x180015848  jz      short loc_180015879
0x18001584a  mov     rcx, [rcx-0B8h]; Irp
0x180015851  call    cs:__imp_IoGetRequestorProcess
0x180015858  nop     dword ptr [rax+rax+00h]
0x18001585d  test    rax, rax
0x180015860  jz      short loc_180015877
0x180015862  mov     rcx, rax; Process
0x180015865  call    cs:__imp_PsGetProcessId
0x18001586c  nop     dword ptr [rax+rax+00h]
0x180015871  add     rsp, 28h
0x180015875  retn
0x180015877  jmp     short loc_180015871
0x180015879  call    cs:__imp_IoGetCurrentProcess
0x180015880  nop     dword ptr [rax+rax+00h]
0x180015885  jmp     short loc_18001585D
```
