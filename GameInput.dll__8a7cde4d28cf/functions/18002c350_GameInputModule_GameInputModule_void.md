# GameInputModule::~GameInputModule(void)

- ea: `0x18002c350`
- end: `0x18002c3ad`
- name: `??1GameInputModule@@QEAA@XZ`
- size: `93`
- prototype: `void __fastcall(GameInputModule *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18004c990`

## callees

- `0x18002c350`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002c388`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002c388`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002c3a1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002c364`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002c364`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18002c379`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18002c379`

## pseudocode

```c
void __fastcall GameInputModule::~GameInputModule(struct _RTL_CRITICAL_SECTION *this)
{
  struct _RTL_CRITICAL_SECTION *v1; // rdi
  HMODULE SpinCount; // rcx

  v1 = this + 1;
  EnterCriticalSection(this + 1);
  SpinCount = (HMODULE)this->SpinCount;
  if ( SpinCount )
    FreeLibrary(SpinCount);
  LeaveCriticalSection(v1);
  DeleteCriticalSection(v1);
}

```

## disassembly

```asm
0x18002c350  mov     [rsp+arg_0], rbx
0x18002c355  push    rdi
0x18002c356  sub     rsp, 20h
0x18002c35a  lea     rdi, [rcx+28h]
0x18002c35e  mov     rbx, rcx
0x18002c361  mov     rcx, rdi; lpCriticalSection
0x18002c364  call    cs:__imp_EnterCriticalSection
0x18002c36b  nop     dword ptr [rax+rax+00h]
0x18002c370  mov     rcx, [rbx+20h]; hLibModule
0x18002c374  test    rcx, rcx
0x18002c377  jz      short loc_18002C385
0x18002c379  call    cs:__imp_FreeLibrary
0x18002c380  nop     dword ptr [rax+rax+00h]
0x18002c385  mov     rcx, rdi; lpCriticalSection
0x18002c388  call    cs:__imp_LeaveCriticalSection
0x18002c38f  nop     dword ptr [rax+rax+00h]
0x18002c394  mov     rcx, rdi
0x18002c397  mov     rbx, [rsp+28h+arg_0]
0x18002c39c  add     rsp, 20h
0x18002c3a0  pop     rdi
0x18002c3a1  jmp     cs:__imp_DeleteCriticalSection
```
