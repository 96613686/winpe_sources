# InitializeTaskEventsLib(void * *)

- ea: `0x180032d90`
- end: `0x180032e68`
- name: `?InitializeTaskEventsLib@@YAKPEAPEAX@Z`
- size: `216`
- prototype: `unsigned int __fastcall(void **)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, service_task`

## callers

- `0x180032d3c`

## callees

- `0x180007e9c`
- `0x18001d0ec`
- `0x180032d90`
- `0x1800349d8`
- `0x180039314`

## import_xrefs

- `ntdll!EtwEventRegister` at `0x180032de5`
- `ntdll!EtwEventRegister` at `0x180032de5`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x180032dc5`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x180032dc5`

## string_xrefs

- `0x180032e4d`: `InitializeTaskEventsLib() --> (handle=0x%x, ret=%d)`

## pseudocode

```c
__int64 __fastcall InitializeTaskEventsLib(void **a1)
{
  char *v1; // rax
  EventManager *v2; // rbx
  int v3; // eax
  EventManager *v4; // rcx
  signed int v5; // edi
  unsigned int v6; // edx
  bool v7; // sf
  __int64 v8; // r8
  unsigned int v9; // r8d

  v1 = (char *)operator new(0x30u);
  v2 = (EventManager *)v1;
  if ( !v1 )
  {
    LOWORD(v5) = 14;
    goto LABEL_10;
  }
  *(_QWORD *)v1 = 0;
  InitializeCriticalSectionEx((LPCRITICAL_SECTION)(v1 + 8), 0, 0);
  v3 = EtwEventRegister(TASKSCHED, 0, 0, v2);
  v5 = v3;
  if ( !*(_QWORD *)v2 || v3 )
  {
    EventManager::LogIt(v4, L"EventRegister error", v3);
    *(_QWORD *)v2 = 0;
    v7 = v5 < 0;
    if ( v5 > 0 )
    {
      v5 = (unsigned __int16)v5 | 0x80070000;
      v7 = v5 < 0;
    }
    if ( v7 )
    {
      EventManager::`scalar deleting destructor'(v2, v6);
LABEL_10:
      v2 = g_hTaskEventManager;
      v8 = (unsigned __int16)v5;
      goto LABEL_11;
    }
  }
  v8 = 0;
  g_hTaskEventManager = v2;
LABEL_11:
  TaskEventTrace(L"InitializeTaskEventsLib() --> (handle=0x%x, ret=%d)", v2, v8);
  return v9;
}

```

## disassembly

```asm
0x180032d90  mov     [rsp+arg_8], rbx
0x180032d95  push    rdi
0x180032d96  sub     rsp, 20h
0x180032d9a  mov     ecx, 30h ; '0'; Size
0x180032d9f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180032da4  mov     [rsp+28h+arg_0], rax
0x180032da9  mov     rbx, rax
0x180032dac  test    rax, rax
0x180032daf  jz      loc_180032E3A
0x180032db5  lea     rcx, [rax+8]; lpCriticalSection
0x180032db9  mov     qword ptr [rax], 0
0x180032dc0  xor     r8d, r8d; Flags
0x180032dc3  xor     edx, edx; dwSpinCount
0x180032dc5  call    cs:__imp_InitializeCriticalSectionEx
0x180032dcc  nop     dword ptr [rax+rax+00h]
0x180032dd1  test    rbx, rbx
0x180032dd4  jz      short loc_180032E3A
0x180032dd6  mov     r9, rbx
0x180032dd9  lea     rcx, TASKSCHED
0x180032de0  xor     r8d, r8d
0x180032de3  xor     edx, edx
0x180032de5  call    cs:__imp_EtwEventRegister
0x180032dec  nop     dword ptr [rax+rax+00h]
0x180032df1  cmp     qword ptr [rbx], 0
0x180032df5  mov     edi, eax
0x180032df7  jz      short loc_180032DFD
0x180032df9  test    eax, eax
0x180032dfb  jz      short loc_180032E24
0x180032dfd  mov     r8d, edi; unsigned int
0x180032e00  lea     rdx, aEventregisterE; "EventRegister error"
0x180032e07  call    ?LogIt@EventManager@@AEAAKPEBGK@Z; EventManager::LogIt(ushort const *,ulong)
0x180032e0c  mov     qword ptr [rbx], 0
0x180032e13  test    edi, edi
0x180032e15  jle     short loc_180032E22
0x180032e17  movzx   edi, di
0x180032e1a  or      edi, 80070000h
0x180032e20  test    edi, edi
0x180032e22  js      short loc_180032E30
0x180032e24  xor     r8d, r8d
0x180032e27  mov     cs:g_hTaskEventManager, rbx
0x180032e2e  jmp     short loc_180032E4A
0x180032e30  mov     rcx, rbx; this
0x180032e33  call    ??_GEventManager@@QEAAPEAXI@Z; EventManager::`scalar deleting destructor'(uint)
0x180032e38  jmp     short loc_180032E3F
0x180032e3a  mov     edi, 8007000Eh
0x180032e3f  mov     rbx, cs:g_hTaskEventManager
0x180032e46  movzx   r8d, di
0x180032e4a  mov     rdx, rbx
0x180032e4d  lea     rcx, aInitializetask; "InitializeTaskEventsLib() --> (handle=0"...
0x180032e54  call    TaskEventTrace
0x180032e59  mov     rbx, [rsp+28h+arg_8]
0x180032e5e  mov     eax, r8d
0x180032e61  add     rsp, 20h
0x180032e65  pop     rdi
0x180032e66  retn
```
