# ShellItemWatcher::Watch(IShellItem *,IShellItemWatcherCookie * *)

- ea: `0x1800235d0`
- end: `0x1800236ea`
- name: `?Watch@ShellItemWatcher@@QEAAXPEAUIShellItem@@PEAPEAUIShellItemWatcherCookie@@@Z`
- size: `282`
- prototype: `void(ShellItemWatcher *__hidden this, struct IShellItem *, struct IShellItemWatcherCookie **)`
- caller_count: `2`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x180032210`
- `0x180039ff4`

## callees

- `0x1800235d0`
- `0x18004b710`
- `0x180080010`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x1800236d7`
- `ole32!CoTaskMemFree` at `0x1800236d7`
- `SHELL32!SHGetIDListFromObject` at `0x180023623`
- `SHELL32!SHGetIDListFromObject` at `0x180023623`
- `SHELL32!__imp_SHChangeNotifyRegister` at `0x18002366e`
- `SHELL32!__imp_SHChangeNotifyRegister` at `0x18002366e`
- `PhotoBase!?New@BasePrivate@@YAPEAX_K_N@Z` at `0x18002368d`
- `PhotoBase!?New@BasePrivate@@YAPEAX_K_N@Z` at `0x18002368d`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18002362f`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18002367f`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18002362f`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18002367f`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall ShellItemWatcher::Watch(ShellItemWatcher *this, IUnknown *a2, struct IShellItemWatcherCookie **a3)
{
  struct ShellItemWatcher::NotificationWindow *v6; // rbp
  __int64 v7; // rcx
  HRESULT v8; // eax
  int v9; // edx
  HWND v10; // rcx
  unsigned __int64 v11; // rdx
  ULONG v12; // esi
  bool v13; // r8
  struct IShellItemWatcherCookie *v14; // rax
  struct IShellItemWatcherCookie *v15; // rbx
  SHChangeNotifyEntry pshcne; // [rsp+30h] [rbp-28h] BYREF
  LPITEMIDLIST ppidl; // [rsp+60h] [rbp+8h] BYREF
  struct IShellItemWatcherCookie *v18; // [rsp+78h] [rbp+20h]

  if ( !*(_QWORD *)this )
  {
    v6 = ShellItemWatcher::NotificationWindow::Create(this);
    v7 = *(_QWORD *)this;
    if ( *(struct ShellItemWatcher::NotificationWindow **)this != v6 )
    {
      if ( v7 )
        (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v7 + 8LL))(v7, 1);
      *(_QWORD *)this = v6;
    }
  }
  ppidl = 0;
  v8 = SHGetIDListFromObject(a2, &ppidl);
  if ( v8 < 0 )
  {
    Base::Throw((Base *)(unsigned int)v8, v9);
    __debugbreak();
  }
  v10 = *(HWND *)(*(_QWORD *)this + 8LL);
  pshcne.fRecursive = 0;
  pshcne.pidl = ppidl;
  v12 = SHChangeNotifyRegister(v10, 32771, 8197, 0x401u, 1, &pshcne);
  if ( !v12 )
  {
    Base::Throw((Base *)0x80004005LL, v11);
    __debugbreak();
  }
  LOBYTE(v11) = 1;
  v14 = (struct IShellItemWatcherCookie *)BasePrivate::New((BasePrivate *)0x20, v11, v13);
  v15 = v14;
  v18 = v14;
  if ( v14 )
  {
    *((_DWORD *)v14 + 4) = 0;
    *(_QWORD *)v14 = &ShellItemWatcherCookie::`vftable'{for `IShellItemWatcherCookie'};
    *((_QWORD *)v14 + 1) = &ShellItemWatcherCookie::`vftable'{for `Base::RefCountBase'};
    *((_DWORD *)v14 + 6) = v12;
    ((void (__fastcall *)(struct IShellItemWatcherCookie *))ShellItemWatcherCookie::`vftable'{for `IShellItemWatcherCookie'})(v14);
  }
  else
  {
    v15 = 0;
  }
  *a3 = v15;
  CoTaskMemFree(ppidl);
}

```

## disassembly

```asm
0x1800235d0  mov     [rsp+arg_8], rbx
0x1800235d5  push    rbp
0x1800235d6  push    rsi
0x1800235d7  push    rdi
0x1800235d8  sub     rsp, 40h
0x1800235dc  mov     rdi, r8
0x1800235df  mov     rsi, rdx
0x1800235e2  mov     rbx, rcx
0x1800235e5  cmp     qword ptr [rcx], 0
0x1800235e9  jnz     short loc_180023614
0x1800235eb  call    ?Create@NotificationWindow@ShellItemWatcher@@SAPEAV12@PEAV2@@Z; ShellItemWatcher::NotificationWindow::Create(ShellItemWatcher *)
0x1800235f0  mov     rbp, rax
0x1800235f3  mov     rcx, [rbx]
0x1800235f6  cmp     rcx, rax
0x1800235f9  jz      short loc_180023614
0x1800235fb  test    rcx, rcx
0x1800235fe  jz      short loc_180023611
0x180023600  mov     rdx, [rcx]
0x180023603  mov     rax, [rdx+8]
0x180023607  mov     edx, 1
0x18002360c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023611  mov     [rbx], rbp
0x180023614  xor     ebp, ebp
0x180023616  mov     [rsp+58h+ppidl], rbp
0x18002361b  lea     rdx, [rsp+58h+ppidl]; ppidl
0x180023620  mov     rcx, rsi; punk
0x180023623  call    cs:__imp_SHGetIDListFromObject
0x180023629  test    eax, eax
0x18002362b  jns     short loc_180023636
0x18002362d  mov     ecx, eax
0x18002362f  call    cs:__imp_?Throw@Base@@YAXJ@Z; Base::Throw(long)
0x180023635  int     3; Trap to Debugger
0x180023636  mov     rax, [rbx]
0x180023639  mov     rcx, [rax+8]; hwnd
0x18002363d  mov     [rsp+58h+var_28.fRecursive], ebp
0x180023641  mov     rax, [rsp+58h+ppidl]
0x180023646  mov     [rsp+58h+var_28.pidl], rax
0x18002364b  lea     rax, [rsp+58h+var_28]
0x180023650  mov     [rsp+58h+pshcne], rax; pshcne
0x180023655  mov     [rsp+58h+cEntries], 1; cEntries
0x18002365d  mov     edx, 8003h; fSources
0x180023662  mov     r9d, 401h; wMsg
0x180023668  mov     r8d, 2005h; fEvents
0x18002366e  call    cs:__imp_SHChangeNotifyRegister
0x180023674  mov     esi, eax
0x180023676  test    eax, eax
0x180023678  jnz     short loc_180023686
0x18002367a  mov     ecx, 80004005h
0x18002367f  call    cs:__imp_?Throw@Base@@YAXJ@Z; Base::Throw(long)
0x180023685  int     3; Trap to Debugger
0x180023686  mov     dl, 1
0x180023688  mov     ecx, 20h ; ' '
0x18002368d  call    cs:__imp_?New@BasePrivate@@YAPEAX_K_N@Z; BasePrivate::New(unsigned __int64,bool)
0x180023693  mov     rbx, rax
0x180023696  mov     [rsp+58h+arg_18], rax
0x18002369b  test    rax, rax
0x18002369e  jz      short loc_1800236CC
0x1800236a0  mov     [rax+10h], ebp
0x1800236a3  lea     rax, ??_7ShellItemWatcherCookie@@6BIShellItemWatcherCookie@@@; const ShellItemWatcherCookie::`vftable'{for `IShellItemWatcherCookie'}
0x1800236aa  mov     [rbx], rax
0x1800236ad  lea     rax, ??_7ShellItemWatcherCookie@@6BRefCountBase@Base@@@; const ShellItemWatcherCookie::`vftable'{for `Base::RefCountBase'}
0x1800236b4  mov     [rbx+8], rax
0x1800236b8  mov     [rbx+18h], esi
0x1800236bb  mov     rcx, rbx
0x1800236be  mov     rax, cs:??_7ShellItemWatcherCookie@@6BIShellItemWatcherCookie@@@; const ShellItemWatcherCookie::`vftable'{for `IShellItemWatcherCookie'}
0x1800236c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800236ca  jmp     short loc_1800236CF
0x1800236cc  mov     rbx, rbp
0x1800236cf  mov     [rdi], rbx
0x1800236d2  mov     rcx, [rsp+58h+ppidl]; pv
0x1800236d7  call    cs:__imp_CoTaskMemFree
0x1800236dd  mov     rbx, [rsp+58h+arg_8]
0x1800236e2  add     rsp, 40h
0x1800236e6  pop     rdi
0x1800236e7  pop     rsi
0x1800236e8  pop     rbp
0x1800236e9  retn
```
