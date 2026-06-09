# CBdeCfgConsole::~CBdeCfgConsole(void)

- ea: `0x140001a28`
- end: `0x140001a9c`
- name: `??1CBdeCfgConsole@@QEAA@XZ`
- size: `116`
- prototype: `void __fastcall(CBdeCfgConsole *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x140001bf4`

## callees

- `0x140001a28`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x140001a7c`
- `KERNEL32!DeleteCriticalSection` at `0x140001a7c`
- `KERNEL32!CloseHandle` at `0x140001a47`
- `KERNEL32!CloseHandle` at `0x140001a64`
- `KERNEL32!CloseHandle` at `0x140001a47`
- `KERNEL32!CloseHandle` at `0x140001a64`
- `BDEHDCFGLIB!??1CDriveConfiguration@@QEAA@XZ` at `0x140001a86`
- `BDEHDCFGLIB!??1CDriveConfiguration@@QEAA@XZ` at `0x140001a86`
- `BDEHDCFGLIB!??1CBdeCfgLibraryLoader@@QEAA@XZ` at `0x140001a95`

## pseudocode

```c
void __fastcall CBdeCfgConsole::~CBdeCfgConsole(CBdeCfgConsole *this)
{
  void *v2; // rcx
  void *v3; // rcx

  *(_QWORD *)this = &CBdeCfgConsole::`vftable';
  v2 = (void *)*((_QWORD *)this + 180);
  if ( v2 )
  {
    CloseHandle(v2);
    *((_QWORD *)this + 180) = 0;
  }
  v3 = (void *)*((_QWORD *)this + 181);
  if ( v3 )
  {
    CloseHandle(v3);
    *((_QWORD *)this + 181) = 0;
  }
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 1456));
  CDriveConfiguration::~CDriveConfiguration((CBdeCfgConsole *)((char *)this + 72));
  CBdeCfgLibraryLoader::~CBdeCfgLibraryLoader((CBdeCfgConsole *)((char *)this + 8));
}

```

## disassembly

```asm
0x140001a28  push    rbx
0x140001a2a  sub     rsp, 20h
0x140001a2e  lea     rax, ??_7CBdeCfgConsole@@6B@; const CBdeCfgConsole::`vftable'
0x140001a35  mov     rbx, rcx
0x140001a38  mov     [rcx], rax
0x140001a3b  mov     rcx, [rcx+5A0h]; hObject
0x140001a42  test    rcx, rcx
0x140001a45  jz      short loc_140001A58
0x140001a47  call    cs:__imp_CloseHandle
0x140001a4d  mov     qword ptr [rbx+5A0h], 0
0x140001a58  mov     rcx, [rbx+5A8h]; hObject
0x140001a5f  test    rcx, rcx
0x140001a62  jz      short loc_140001A75
0x140001a64  call    cs:__imp_CloseHandle
0x140001a6a  mov     qword ptr [rbx+5A8h], 0
0x140001a75  lea     rcx, [rbx+5B0h]; lpCriticalSection
0x140001a7c  call    cs:__imp_DeleteCriticalSection
0x140001a82  lea     rcx, [rbx+48h]
0x140001a86  call    cs:__imp_??1CDriveConfiguration@@QEAA@XZ; CDriveConfiguration::~CDriveConfiguration(void)
0x140001a8c  lea     rcx, [rbx+8]
0x140001a90  add     rsp, 20h
0x140001a94  pop     rbx
0x140001a95  jmp     cs:__imp_??1CBdeCfgLibraryLoader@@QEAA@XZ; CBdeCfgLibraryLoader::~CBdeCfgLibraryLoader(void)
```
