# ServiceHandle::~ServiceHandle(void)

- ea: `0x140003554`
- end: `0x14000356b`
- name: `??1ServiceHandle@@QEAA@XZ`
- size: `23`
- prototype: `void __fastcall(ServiceHandle *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x140014d93`

## callees

- `0x140003554`

## import_xrefs

- `ADVAPI32!CloseServiceHandle` at `0x140003560`
- `ADVAPI32!CloseServiceHandle` at `0x140003560`

## pseudocode

```c
void __fastcall ServiceHandle::~ServiceHandle(SC_HANDLE *this)
{
  SC_HANDLE v1; // rcx

  v1 = *this;
  if ( v1 )
    CloseServiceHandle(v1);
}

```

## disassembly

```asm
0x140003554  sub     rsp, 28h
0x140003558  mov     rcx, [rcx]; hSCObject
0x14000355b  test    rcx, rcx
0x14000355e  jz      short loc_140003566
0x140003560  call    cs:__imp_CloseServiceHandle
0x140003566  add     rsp, 28h
0x14000356a  retn
```
