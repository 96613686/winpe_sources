# FrameProvider::~FrameProvider(void)

- ea: `0x18002b34c`
- end: `0x18002b3fd`
- name: `??1FrameProvider@@MEAA@XZ`
- size: `177`
- prototype: `void __fastcall(FrameProvider *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x18002b410`

## callees

- `0x18002b34c`
- `0x18002e010`

## import_xrefs

- `DUI70!??1XProvider@DirectUI@@UEAA@XZ` at `0x18002b3f6`
- `DUI70!UnInitProcessPriv` at `0x18002b3e1`
- `DUI70!UnInitProcessPriv` at `0x18002b3e1`
- `DUI70!UnInitThread` at `0x18002b3d4`
- `DUI70!UnInitThread` at `0x18002b3d4`

## pseudocode

```c
void __fastcall FrameProvider::~FrameProvider(FrameProvider *this)
{
  __int64 v2; // rcx
  __int64 v3; // rcx

  *(_QWORD *)this = &FrameProvider::`vftable'{for `DirectUI::XProvider'};
  *((_QWORD *)this + 5) = &FrameProvider::`vftable'{for `IDUIElementProviderInit'};
  *((_QWORD *)this + 6) = &FrameProvider::`vftable'{for `IFrameNotificationClient'};
  *((_QWORD *)this + 7) = &FrameProvider::`vftable'{for `IFrameShellViewClient'};
  *((_QWORD *)this + 8) = &FrameProvider::`vftable'{for `IObjectWithSite'};
  *((_QWORD *)this + 9) = &FrameProvider::`vftable'{for `IServiceProvider'};
  v2 = *((_QWORD *)this + 10);
  *((_QWORD *)this + 10) = 0;
  if ( v2 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
  v3 = *((_QWORD *)this + 78);
  if ( v3 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
  if ( *((int *)this + 154) >= 0 )
  {
    UnInitThread();
    UnInitProcessPriv(&_ImageBase);
  }
  _InterlockedDecrement(&g_cLocks);
  DirectUI::XProvider::~XProvider(this);
}

```

## disassembly

```asm
0x18002b34c  push    rbx
0x18002b34e  sub     rsp, 20h
0x18002b352  lea     rax, ??_7FrameProvider@@6BXProvider@DirectUI@@@; const FrameProvider::`vftable'{for `DirectUI::XProvider'}
0x18002b359  mov     rbx, rcx
0x18002b35c  mov     [rcx], rax
0x18002b35f  lea     rax, ??_7FrameProvider@@6BIDUIElementProviderInit@@@; const FrameProvider::`vftable'{for `IDUIElementProviderInit'}
0x18002b366  mov     [rcx+28h], rax
0x18002b36a  lea     rax, ??_7FrameProvider@@6BIFrameNotificationClient@@@; const FrameProvider::`vftable'{for `IFrameNotificationClient'}
0x18002b371  mov     [rcx+30h], rax
0x18002b375  lea     rax, ??_7FrameProvider@@6BIFrameShellViewClient@@@; const FrameProvider::`vftable'{for `IFrameShellViewClient'}
0x18002b37c  mov     [rcx+38h], rax
0x18002b380  lea     rax, ??_7FrameProvider@@6BIObjectWithSite@@@; const FrameProvider::`vftable'{for `IObjectWithSite'}
0x18002b387  mov     [rcx+40h], rax
0x18002b38b  lea     rax, ??_7FrameProvider@@6BIServiceProvider@@@; const FrameProvider::`vftable'{for `IServiceProvider'}
0x18002b392  mov     [rcx+48h], rax
0x18002b396  mov     rcx, [rcx+50h]
0x18002b39a  mov     qword ptr [rbx+50h], 0
0x18002b3a2  test    rcx, rcx
0x18002b3a5  jz      short loc_18002B3B3
0x18002b3a7  mov     rax, [rcx]
0x18002b3aa  mov     rax, [rax+10h]
0x18002b3ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b3b3  mov     rcx, [rbx+270h]
0x18002b3ba  test    rcx, rcx
0x18002b3bd  jz      short loc_18002B3CB
0x18002b3bf  mov     rax, [rcx]
0x18002b3c2  mov     rax, [rax+10h]
0x18002b3c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b3cb  cmp     dword ptr [rbx+268h], 0
0x18002b3d2  jl      short loc_18002B3E7
0x18002b3d4  call    cs:__imp_UnInitThread
0x18002b3da  lea     rcx, __ImageBase
0x18002b3e1  call    cs:__imp_UnInitProcessPriv
0x18002b3e7  lock dec cs:?g_cLocks@@3JA; long g_cLocks
0x18002b3ee  mov     rcx, rbx
0x18002b3f1  add     rsp, 20h
0x18002b3f5  pop     rbx
0x18002b3f6  jmp     cs:__imp_??1XProvider@DirectUI@@UEAA@XZ; DirectUI::XProvider::~XProvider(void)
```
