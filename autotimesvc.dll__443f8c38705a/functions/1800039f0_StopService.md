# StopService

- ea: `0x1800039f0`
- end: `0x180003a5e`
- name: `StopService`
- size: `110`
- prototype: `void()`
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, installer_update`

## callees

- `0x1800039f0`
- `0x180003a64`
- `0x180003b00`
- `0x180012010`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003a07`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003a07`

## pseudocode

```c
void StopService()
{
  UninitializeService(0);
  if ( hObject )
  {
    CloseHandle(hObject);
    hObject = 0;
  }
  if ( qword_18001C2F8 )
  {
    (*(void (**)(void))(qword_18001C300 + 216))();
    qword_18001C2F8 = 0;
  }
  qword_18001C300 = 0;
  SvcFrameworkUpdateServiceStatus(1, 0, 0);
}

```

## disassembly

```asm
0x1800039f0  sub     rsp, 28h
0x1800039f4  xor     ecx, ecx; int
0x1800039f6  call    ?UninitializeService@@YAXJ@Z; UninitializeService(long)
0x1800039fb  mov     rcx, cs:hObject; hObject
0x180003a02  test    rcx, rcx
0x180003a05  jz      short loc_180003A18
0x180003a07  call    cs:__imp_CloseHandle
0x180003a0d  mov     cs:hObject, 0
0x180003a18  mov     rcx, cs:qword_18001C2F8
0x180003a1f  test    rcx, rcx
0x180003a22  jz      short loc_180003A42
0x180003a24  mov     rax, cs:qword_18001C300
0x180003a2b  mov     rax, [rax+0D8h]
0x180003a32  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003a37  mov     cs:qword_18001C2F8, 0
0x180003a42  xor     edx, edx; unsigned int
0x180003a44  mov     cs:qword_18001C300, 0
0x180003a4f  xor     r8d, r8d; unsigned int
0x180003a52  lea     ecx, [rdx+1]; unsigned int
0x180003a55  add     rsp, 28h
0x180003a59  jmp     ?SvcFrameworkUpdateServiceStatus@@YAXKKK@Z; SvcFrameworkUpdateServiceStatus(ulong,ulong,ulong)
```
