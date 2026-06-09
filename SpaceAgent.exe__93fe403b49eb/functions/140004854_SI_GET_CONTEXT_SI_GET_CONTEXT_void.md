# SI_GET_CONTEXT::~SI_GET_CONTEXT(void)

- ea: `0x140004854`
- end: `0x14000488a`
- name: `??1SI_GET_CONTEXT@@QEAA@XZ`
- size: `54`
- prototype: `void __fastcall(struct _RTL_CRITICAL_SECTION *this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140007de4`

## callees

- `0x140004854`

## import_xrefs

- `KERNEL32!LocalFree` at `0x140004866`
- `KERNEL32!LocalFree` at `0x140004866`
- `KERNEL32!DeleteCriticalSection` at `0x140004883`
- `KERNEL32!CloseHandle` at `0x140004875`
- `KERNEL32!CloseHandle` at `0x140004875`

## pseudocode

```c
void __fastcall SI_GET_CONTEXT::~SI_GET_CONTEXT(struct _RTL_CRITICAL_SECTION *this)
{
  void *v2; // rcx
  PRTL_CRITICAL_SECTION_DEBUG DebugInfo; // rcx

  v2 = *(void **)&this[1].LockCount;
  if ( v2 )
    LocalFree(v2);
  DebugInfo = this[1].DebugInfo;
  if ( DebugInfo )
    CloseHandle(DebugInfo);
  DeleteCriticalSection(this);
}

```

## disassembly

```asm
0x140004854  push    rbx
0x140004856  sub     rsp, 20h
0x14000485a  mov     rbx, rcx
0x14000485d  mov     rcx, [rcx+30h]; hMem
0x140004861  test    rcx, rcx
0x140004864  jz      short loc_14000486C
0x140004866  call    cs:__imp_LocalFree
0x14000486c  mov     rcx, [rbx+28h]; hObject
0x140004870  test    rcx, rcx
0x140004873  jz      short loc_14000487B
0x140004875  call    cs:__imp_CloseHandle
0x14000487b  mov     rcx, rbx
0x14000487e  add     rsp, 20h
0x140004882  pop     rbx
0x140004883  jmp     cs:__imp_DeleteCriticalSection
```
