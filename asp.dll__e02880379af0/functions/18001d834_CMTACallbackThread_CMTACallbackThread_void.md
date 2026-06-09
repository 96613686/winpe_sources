# CMTACallbackThread::~CMTACallbackThread(void)

- ea: `0x18001d834`
- end: `0x18001d870`
- name: `??1CMTACallbackThread@@QEAA@XZ`
- size: `60`
- prototype: `void __fastcall(CMTACallbackThread *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800245a0`

## callees

- `0x18001d834`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x18001d855`
- `KERNEL32!CloseHandle` at `0x18001d864`
- `KERNEL32!CloseHandle` at `0x18001d855`
- `KERNEL32!CloseHandle` at `0x18001d864`
- `KERNEL32!DeleteCriticalSection` at `0x18001d846`
- `KERNEL32!DeleteCriticalSection` at `0x18001d846`

## pseudocode

```c
void __fastcall CMTACallbackThread::~CMTACallbackThread(CMTACallbackThread *this)
{
  void *v2; // rcx
  void *v3; // rcx

  if ( (*(_BYTE *)this & 2) != 0 )
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
  v2 = (void *)*((_QWORD *)this + 6);
  if ( v2 )
    CloseHandle(v2);
  v3 = (void *)*((_QWORD *)this + 7);
  if ( v3 )
    CloseHandle(v3);
}

```

## disassembly

```asm
0x18001d834  push    rbx
0x18001d836  sub     rsp, 20h
0x18001d83a  test    byte ptr [rcx], 2
0x18001d83d  mov     rbx, rcx
0x18001d840  jz      short loc_18001D84C
0x18001d842  add     rcx, 8; lpCriticalSection
0x18001d846  call    cs:__imp_DeleteCriticalSection
0x18001d84c  mov     rcx, [rbx+30h]; hObject
0x18001d850  test    rcx, rcx
0x18001d853  jz      short loc_18001D85B
0x18001d855  call    cs:__imp_CloseHandle
0x18001d85b  mov     rcx, [rbx+38h]; hObject
0x18001d85f  test    rcx, rcx
0x18001d862  jz      short loc_18001D86A
0x18001d864  call    cs:__imp_CloseHandle
0x18001d86a  add     rsp, 20h
0x18001d86e  pop     rbx
0x18001d86f  retn
```
