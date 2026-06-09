# GameInputModule::~GameInputModule(void)

- ea: `0x14000652c`
- end: `0x140006572`
- name: `??1GameInputModule@@QEAA@XZ`
- size: `70`
- prototype: `void __fastcall(struct _RTL_CRITICAL_SECTION *this)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x140001718`
- `0x14000199c`

## callees

- `0x14000652c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140006558`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140006558`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x14000656b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140006540`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140006540`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x14000654f`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x14000654f`

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
0x14000652c  mov     [rsp+arg_0], rbx
0x140006531  push    rdi
0x140006532  sub     rsp, 20h
0x140006536  lea     rdi, [rcx+28h]
0x14000653a  mov     rbx, rcx
0x14000653d  mov     rcx, rdi; lpCriticalSection
0x140006540  call    cs:__imp_EnterCriticalSection
0x140006546  mov     rcx, [rbx+20h]; hLibModule
0x14000654a  test    rcx, rcx
0x14000654d  jz      short loc_140006555
0x14000654f  call    cs:__imp_FreeLibrary
0x140006555  mov     rcx, rdi; lpCriticalSection
0x140006558  call    cs:__imp_LeaveCriticalSection
0x14000655e  mov     rcx, rdi
0x140006561  mov     rbx, [rsp+28h+arg_0]
0x140006566  add     rsp, 20h
0x14000656a  pop     rdi
0x14000656b  jmp     cs:__imp_DeleteCriticalSection
```
