# Service::~Service(void)

- ea: `0x180007e80`
- end: `0x180007eb2`
- name: `??1Service@@QEAA@XZ`
- size: `50`
- prototype: `void __fastcall(Service *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x180009ae0`

## callees

- `0x180007e80`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180007e92`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180007e92`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007ea6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007ea6`

## pseudocode

```c
void __fastcall Service::~Service(Service *this)
{
  HMODULE v2; // rcx
  char *v3; // rcx

  v2 = (HMODULE)*((_QWORD *)this + 2);
  if ( v2 )
    FreeLibrary(v2);
  v3 = (char *)*((_QWORD *)this + 1);
  if ( (unsigned __int64)(v3 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(v3);
}

```

## disassembly

```asm
0x180007e80  push    rbx
0x180007e82  sub     rsp, 20h
0x180007e86  mov     rbx, rcx
0x180007e89  mov     rcx, [rcx+10h]; hLibModule
0x180007e8d  test    rcx, rcx
0x180007e90  jz      short loc_180007E98
0x180007e92  call    cs:__imp_FreeLibrary
0x180007e98  mov     rcx, [rbx+8]; hObject
0x180007e9c  lea     rax, [rcx-1]
0x180007ea0  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180007ea4  ja      short loc_180007EAC
0x180007ea6  call    cs:__imp_CloseHandle
0x180007eac  add     rsp, 20h
0x180007eb0  pop     rbx
0x180007eb1  retn
```
