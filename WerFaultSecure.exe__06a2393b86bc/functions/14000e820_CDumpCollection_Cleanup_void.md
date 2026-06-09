# CDumpCollection::Cleanup(void)

- ea: `0x14000e820`
- end: `0x14000e8bb`
- name: `?Cleanup@CDumpCollection@@QEAAXXZ`
- size: `155`
- prototype: `void __fastcall(struct _RTL_CRITICAL_SECTION *this)`
- caller_count: `3`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x1400060a4`
- `0x14000e750`
- `0x14000f334`

## callees

- `0x1400023f4`
- `0x14000e820`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x14000e846`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x14000e846`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000e8a6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000e8a6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14000e829`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14000e829`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14000e8b4`

## pseudocode

```c
void __fastcall CDumpCollection::Cleanup(struct _RTL_CRITICAL_SECTION *this)
{
  HMODULE DebugInfo; // rcx
  HANDLE *LockSemaphore; // rcx
  HANDLE OwningThread; // rcx

  EnterCriticalSection(this);
  DebugInfo = (HMODULE)this[28].DebugInfo;
  this[28].DebugInfo = 0;
  if ( DebugInfo )
    FreeLibrary(DebugInfo);
  while ( 1 )
  {
    LockSemaphore = (HANDLE *)this[28].LockSemaphore;
    if ( LockSemaphore == (HANDLE *)-1LL )
      break;
    this[28].LockSemaphore = *LockSemaphore;
    operator delete(LockSemaphore, (const struct std::nothrow_t *)&std::nothrow);
  }
  OwningThread = this[27].OwningThread;
  *(_QWORD *)&this[60].LockCount = this[60].DebugInfo;
  this[27].LockSemaphore = 0;
  this[27].OwningThread = 0;
  if ( (unsigned __int64)OwningThread + 1 > 1 )
    CloseHandle(OwningThread);
  LeaveCriticalSection(this);
}

```

## disassembly

```asm
0x14000e820  push    rbx
0x14000e822  sub     rsp, 20h
0x14000e826  mov     rbx, rcx
0x14000e829  call    cs:__imp_EnterCriticalSection
0x14000e82f  mov     rcx, [rbx+460h]; hLibModule
0x14000e836  mov     qword ptr [rbx+460h], 0
0x14000e841  test    rcx, rcx
0x14000e844  jz      short loc_14000E84C
0x14000e846  call    cs:__imp_FreeLibrary
0x14000e84c  mov     rcx, [rbx+478h]; void *
0x14000e853  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x14000e857  jz      short loc_14000E871
0x14000e859  mov     rax, [rcx]
0x14000e85c  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14000e863  mov     [rbx+478h], rax
0x14000e86a  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14000e86f  jmp     short loc_14000E84C
0x14000e871  mov     rcx, [rbx+448h]; hObject
0x14000e878  mov     rax, [rbx+960h]
0x14000e87f  mov     [rbx+968h], rax
0x14000e886  mov     qword ptr [rbx+450h], 0
0x14000e891  lea     rax, [rcx+1]
0x14000e895  mov     qword ptr [rbx+448h], 0
0x14000e8a0  cmp     rax, 1
0x14000e8a4  jbe     short loc_14000E8AC
0x14000e8a6  call    cs:__imp_CloseHandle
0x14000e8ac  mov     rcx, rbx
0x14000e8af  add     rsp, 20h
0x14000e8b3  pop     rbx
0x14000e8b4  jmp     cs:__imp_LeaveCriticalSection
```
