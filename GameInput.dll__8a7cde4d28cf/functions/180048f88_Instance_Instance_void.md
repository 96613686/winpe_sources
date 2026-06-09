# Instance::~Instance(void)

- ea: `0x180048f88`
- end: `0x1800490e4`
- name: `??1Instance@@UEAA@XZ`
- size: `348`
- prototype: `void __fastcall(Instance *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, loader_planting, service_task`

## callers

- `0x180049340`

## callees

- `0x18000c11c`
- `0x180048f88`
- `0x1800490ec`
- `0x180049198`
- `0x180049288`
- `0x18004d010`

## import_xrefs

- `ntdll!RtlUnsubscribeWnfStateChangeNotification` at `0x180048fb7`
- `ntdll!RtlUnsubscribeWnfStateChangeNotification` at `0x180048fb7`
- `ext-ms-win-ntuser-windowclass-l1-1-0!UnregisterClassW` at `0x1800490a4`
- `ext-ms-win-ntuser-windowclass-l1-1-0!UnregisterClassW` at `0x1800490a4`

## string_xrefs

- `0x18004909d`: `GameInputServiceWindow`

## pseudocode

```c
void __fastcall Instance::~Instance(Instance *this, const struct std::nothrow_t *a2)
{
  void *v3; // rdi
  const struct std::nothrow_t *v4; // rdx
  void *v5; // rdi
  const struct std::nothrow_t *v6; // rdx
  Instance *i; // rdi
  RawInputWatcher *v8; // rdi
  const struct std::nothrow_t *v9; // rdx
  _QWORD *v10; // rcx
  void *v11; // rdi
  const struct std::nothrow_t *v12; // rdx

  *(_QWORD *)this = &Instance::`vftable'{for `IGameInputServerInputRouter'};
  *((_QWORD *)this + 1) = &Instance::`vftable'{for `IGameInputServerInputRouterDownlevel'};
  if ( *((_QWORD *)this + 18) )
    RtlUnsubscribeWnfStateChangeNotification();
  v3 = (void *)*((_QWORD *)this + 8);
  if ( v3 )
  {
    MessageWindow::~MessageWindow(*((HANDLE **)this + 8));
    operator delete(v3, v4);
    *((_QWORD *)this + 8) = 0;
  }
  v5 = (void *)*((_QWORD *)this + 7);
  if ( v5 )
  {
    MessageWindow::~MessageWindow(*((HANDLE **)this + 7));
    operator delete(v5, v6);
    *((_QWORD *)this + 7) = 0;
  }
  for ( i = (Instance *)((char *)this + 112); i != (Instance *)((char *)this + 136); i = (Instance *)((char *)i + 8) )
  {
    if ( *(_QWORD *)i )
      (***(void (__fastcall ****)(_QWORD, __int64))i)(*(_QWORD *)i, 1);
  }
  v8 = (RawInputWatcher *)*((_QWORD *)this + 10);
  *((_QWORD *)this + 12) = 0;
  *((_QWORD *)this + 13) = 0;
  if ( v8 )
  {
    RawInputWatcher::~RawInputWatcher(v8);
    operator delete(v8, v9);
    *((_QWORD *)this + 10) = 0;
  }
  v10 = (_QWORD *)*((_QWORD *)this + 9);
  if ( v10 )
  {
    FocusWatcher::s_singleton = 0;
    *v10 = &MessageWindowClient::`vftable';
    operator delete(v10, a2);
    *((_QWORD *)this + 9) = 0;
  }
  v11 = (void *)*((_QWORD *)this + 11);
  if ( v11 )
  {
    KeyboardLayoutWatcher::~KeyboardLayoutWatcher(*((KeyboardLayoutWatcher **)this + 11));
    operator delete(v11, v12);
    *((_QWORD *)this + 11) = 0;
  }
  if ( MessageWindow::s_wndClassAtom )
    UnregisterClassW(L"GameInputServiceWindow", MessageWindow::s_moduleHandle);
  MessageWindow::s_instance = 0;
  *(_QWORD *)this = &RefCountedObjectBase<IGameInputServerInputRouter,IGameInputServerInputRouterDownlevel,MarkerInterface<IAgileObject>,MarkerInterface<INoMarshal>>::`vftable'{for `IGameInputServerInputRouter'};
  *((_QWORD *)this + 1) = &RefCountedObjectBase<IGameInputServerInputRouter,IGameInputServerInputRouterDownlevel,MarkerInterface<IAgileObject>,MarkerInterface<INoMarshal>>::`vftable'{for `IGameInputServerInputRouterDownlevel'};
  MessageWindow::s_wndClassAtom = 0;
  MessageWindow::s_moduleHandle = 0;
}

```

## disassembly

```asm
0x180048f88  push    rbx
0x180048f8a  push    rbp
0x180048f8b  push    rsi
0x180048f8c  push    rdi
0x180048f8d  sub     rsp, 28h
0x180048f91  lea     rax, ??_7Instance@@6BIGameInputServerInputRouter@@@; const Instance::`vftable'{for `IGameInputServerInputRouter'}
0x180048f98  mov     rbx, rcx
0x180048f9b  mov     [rcx], rax
0x180048f9e  xor     ebp, ebp
0x180048fa0  lea     rax, ??_7Instance@@6BIGameInputServerInputRouterDownlevel@@@; const Instance::`vftable'{for `IGameInputServerInputRouterDownlevel'}
0x180048fa7  mov     [rcx+8], rax
0x180048fab  mov     rcx, [rcx+90h]
0x180048fb2  test    rcx, rcx
0x180048fb5  jz      short loc_180048FC3
0x180048fb7  call    cs:__imp_RtlUnsubscribeWnfStateChangeNotification
0x180048fbe  nop     dword ptr [rax+rax+00h]
0x180048fc3  mov     rdi, [rbx+40h]
0x180048fc7  test    rdi, rdi
0x180048fca  jz      short loc_180048FE0
0x180048fcc  mov     rcx, rdi; this
0x180048fcf  call    ??1MessageWindow@@QEAA@XZ; MessageWindow::~MessageWindow(void)
0x180048fd4  mov     rcx, rdi; P
0x180048fd7  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180048fdc  mov     [rbx+40h], rbp
0x180048fe0  mov     rdi, [rbx+38h]
0x180048fe4  test    rdi, rdi
0x180048fe7  jz      short loc_180048FFD
0x180048fe9  mov     rcx, rdi; this
0x180048fec  call    ??1MessageWindow@@QEAA@XZ; MessageWindow::~MessageWindow(void)
0x180048ff1  mov     rcx, rdi; P
0x180048ff4  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180048ff9  mov     [rbx+38h], rbp
0x180048ffd  lea     rdi, [rbx+70h]
0x180049001  lea     rsi, [rdi+18h]
0x180049005  jmp     short loc_180049023
0x180049007  mov     rcx, [rdi]
0x18004900a  test    rcx, rcx
0x18004900d  jz      short loc_18004901F
0x18004900f  mov     rax, [rcx]
0x180049012  mov     edx, 1
0x180049017  mov     rax, [rax]
0x18004901a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004901f  add     rdi, 8
0x180049023  cmp     rdi, rsi
0x180049026  jnz     short loc_180049007
0x180049028  mov     rdi, [rbx+50h]
0x18004902c  mov     [rbx+60h], rbp
0x180049030  mov     [rbx+68h], rbp
0x180049034  test    rdi, rdi
0x180049037  jz      short loc_18004904D
0x180049039  mov     rcx, rdi; this
0x18004903c  call    ??1RawInputWatcher@@UEAA@XZ; RawInputWatcher::~RawInputWatcher(void)
0x180049041  mov     rcx, rdi; P
0x180049044  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180049049  mov     [rbx+50h], rbp
0x18004904d  mov     rcx, [rbx+48h]; P
0x180049051  test    rcx, rcx
0x180049054  jz      short loc_180049070
0x180049056  lea     rax, ??_7MessageWindowClient@@6B@; const MessageWindowClient::`vftable'
0x18004905d  mov     cs:?s_singleton@FocusWatcher@@0PEAV1@EA, rbp; FocusWatcher * FocusWatcher::s_singleton
0x180049064  mov     [rcx], rax
0x180049067  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18004906c  mov     [rbx+48h], rbp
0x180049070  mov     rdi, [rbx+58h]
0x180049074  test    rdi, rdi
0x180049077  jz      short loc_18004908D
0x180049079  mov     rcx, rdi; this
0x18004907c  call    ??1KeyboardLayoutWatcher@@UEAA@XZ; KeyboardLayoutWatcher::~KeyboardLayoutWatcher(void)
0x180049081  mov     rcx, rdi; P
0x180049084  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180049089  mov     [rbx+58h], rbp
0x18004908d  cmp     cs:?s_wndClassAtom@MessageWindow@@0GA, bp; ushort MessageWindow::s_wndClassAtom
0x180049094  jz      short loc_1800490B0
0x180049096  mov     rdx, cs:?s_moduleHandle@MessageWindow@@0PEAUHINSTANCE__@@EA; hInstance
0x18004909d  lea     rcx, ClassName; "GameInputServiceWindow"
0x1800490a4  call    cs:__imp_UnregisterClassW
0x1800490ab  nop     dword ptr [rax+rax+00h]
0x1800490b0  lea     rax, ??_7?$RefCountedObjectBase@UIGameInputServerInputRouter@@UIGameInputServerInputRouterDownlevel@@U?$MarkerInterface@UIAgileObject@@@@U?$MarkerInterface@UINoMarshal@@@@@@6BIGameInputServerInputRouter@@@; const RefCountedObjectBase<IGameInputServerInputRouter,IGameInputServerInputRouterDownlevel,MarkerInterface<IAgileObject>,MarkerInterface<INoMarshal>>::`vftable'{for `IGameInputServerInputRouter'}
0x1800490b7  mov     cs:?s_instance@MessageWindow@@0PEAVInstance@@EA, rbp; Instance * MessageWindow::s_instance
0x1800490be  mov     [rbx], rax
0x1800490c1  lea     rax, ??_7?$RefCountedObjectBase@UIGameInputServerInputRouter@@UIGameInputServerInputRouterDownlevel@@U?$MarkerInterface@UIAgileObject@@@@U?$MarkerInterface@UINoMarshal@@@@@@6BIGameInputServerInputRouterDownlevel@@@; const RefCountedObjectBase<IGameInputServerInputRouter,IGameInputServerInputRouterDownlevel,MarkerInterface<IAgileObject>,MarkerInterface<INoMarshal>>::`vftable'{for `IGameInputServerInputRouterDownlevel'}
0x1800490c8  mov     [rbx+8], rax
0x1800490cc  mov     cs:?s_wndClassAtom@MessageWindow@@0GA, bp; ushort MessageWindow::s_wndClassAtom
0x1800490d3  mov     cs:?s_moduleHandle@MessageWindow@@0PEAUHINSTANCE__@@EA, rbp; HINSTANCE__ * MessageWindow::s_moduleHandle
0x1800490da  add     rsp, 28h
0x1800490de  pop     rdi
0x1800490df  pop     rsi
0x1800490e0  pop     rbp
0x1800490e1  pop     rbx
0x1800490e2  retn
```
