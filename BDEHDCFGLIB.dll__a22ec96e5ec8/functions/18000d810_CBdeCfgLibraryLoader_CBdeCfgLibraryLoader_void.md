# CBdeCfgLibraryLoader::~CBdeCfgLibraryLoader(void)

- ea: `0x18000d810`
- end: `0x18000d863`
- name: `??1CBdeCfgLibraryLoader@@QEAA@XZ`
- size: `83`
- prototype: `void __fastcall(CBdeCfgLibraryLoader *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18000d810`
- `0x18000da80`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x18000d85c`
- `KERNEL32!CloseHandle` at `0x18000d82b`
- `KERNEL32!CloseHandle` at `0x18000d846`
- `KERNEL32!CloseHandle` at `0x18000d82b`
- `KERNEL32!CloseHandle` at `0x18000d846`

## pseudocode

```c
void __fastcall CBdeCfgLibraryLoader::~CBdeCfgLibraryLoader(CBdeCfgLibraryLoader *this)
{
  CBdeCfgLibraryLoader::Unload((LPCRITICAL_SECTION)this);
  if ( *((_QWORD *)this + 5) )
  {
    CloseHandle(*((HANDLE *)this + 5));
    *((_QWORD *)this + 5) = 0;
  }
  if ( *((_QWORD *)this + 6) )
  {
    CloseHandle(*((HANDLE *)this + 6));
    *((_QWORD *)this + 6) = 0;
  }
  DeleteCriticalSection((LPCRITICAL_SECTION)this);
}

```

## disassembly

```asm
0x18000d810  push    rbx
0x18000d812  sub     rsp, 20h
0x18000d816  mov     rbx, rcx
0x18000d819  call    ?Unload@CBdeCfgLibraryLoader@@QEAAXXZ; CBdeCfgLibraryLoader::Unload(void)
0x18000d81e  mov     rax, [rbx+28h]
0x18000d822  test    rax, rax
0x18000d825  jz      short loc_18000D839
0x18000d827  mov     rcx, [rbx+28h]; hObject
0x18000d82b  call    cs:__imp_CloseHandle
0x18000d831  mov     qword ptr [rbx+28h], 0
0x18000d839  mov     rax, [rbx+30h]
0x18000d83d  test    rax, rax
0x18000d840  jz      short loc_18000D854
0x18000d842  mov     rcx, [rbx+30h]; hObject
0x18000d846  call    cs:__imp_CloseHandle
0x18000d84c  mov     qword ptr [rbx+30h], 0
0x18000d854  mov     rcx, rbx
0x18000d857  add     rsp, 20h
0x18000d85b  pop     rbx
0x18000d85c  jmp     cs:__imp_DeleteCriticalSection
```
