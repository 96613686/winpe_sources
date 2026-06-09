# UIItem::`scalar deleting destructor'(uint)

- ea: `0x18002e220`
- end: `0x18002e482`
- name: `??_GUIItem@@UEAAPEAXI@Z`
- size: `610`
- prototype: `void *__fastcall(UIItem *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `9`
- tags: `file_ops, registry_config, broker_com_uri`

## callees

- `0x18001a1e0`
- `0x18001b8d0`
- `0x18002ce20`
- `0x18002e220`
- `0x18002f35c`
- `0x1800340a0`
- `0x18013fc70`
- `0x1801e4538`
- `0x180210010`

## import_xrefs

- `SHCORE!SHCreateThread` at `0x18002e45a`
- `SHCORE!SHCreateThread` at `0x18002e45a`
- `SHLWAPI!SHRegGetBoolUSValueW` at `0x18002e35c`
- `SHLWAPI!SHRegGetBoolUSValueW` at `0x18002e35c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002e332`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002e332`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18002e3e2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18002e3e2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18002e3d9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18002e3eb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18002e3d9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18002e3eb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002e465`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002e465`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18002e417`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18002e417`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18002e3ca`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18002e3ca`
- `DUI70!??1Element@DirectUI@@UEAA@XZ` at `0x18002e308`
- `DUI70!??1Element@DirectUI@@UEAA@XZ` at `0x18002e308`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
UIItem *__fastcall UIItem::`scalar deleting destructor'(UIItem *this, char a2)
{
  _QWORD *v4; // rdi
  struct DirectUI::IClassInfo *v5; // rbx
  __int64 v6; // rcx
  int v7; // eax
  HANDLE CurrentProcess; // rdi
  HANDLE CurrentThread; // rbx
  HANDLE v11; // rax
  int lpData; // [rsp+20h] [rbp-48h]
  _QWORD pData[2]; // [rsp+40h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]
  HANDLE TargetHandle; // [rsp+70h] [rbp+8h] BYREF
  int Data; // [rsp+78h] [rbp+10h] BYREF

  *(_QWORD *)this = &UIItem::`vftable';
  *((_DWORD *)this + 64) = 0;
  if ( *((_DWORD *)this + 62) )
  {
    g_dwReentrantThreadId = GetCurrentThreadId();
    g_ReentrantCheck = 5;
    if ( !SHRegGetBoolUSValueW(
            L"Software\\Microsoft\\Windows\\CurrentVersion\\Explorer\\Advanced",
            L"ShellViewReentered",
            0,
            0) )
    {
      Data = 1;
      RegSetKeyValueW(
        HKEY_CURRENT_USER,
        L"Software\\Microsoft\\Windows\\CurrentVersion\\Explorer\\Advanced",
        L"ShellViewReentered",
        4u,
        &Data,
        4u);
      TargetHandle = 0;
      CurrentProcess = GetCurrentProcess();
      CurrentThread = GetCurrentThread();
      v11 = GetCurrentProcess();
      if ( DuplicateHandle(v11, CurrentThread, CurrentProcess, &TargetHandle, 0x1FFFFFu, 1, 0) )
      {
        pData[0] = TargetHandle;
        pData[1] = ComputeStackHash();
        SHCreateThread(
          DirectUI::PatternProvider<UIItemsViewScrollProvider,IScrollProvider,5>::GetProxyCreator,
          pData,
          0x200u,
          s_SendWERForReentrancy);
        CloseHandle(TargetHandle);
      }
    }
    *((_DWORD *)this + 63) = 1;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x18E,
      (unsigned int)"shell\\explorerframe\\itemsview\\uiitem.cpp",
      (const char *)0x8000FFFFLL,
      lpData);
    v4 = (_QWORD *)((char *)this + 216);
  }
  else
  {
    *((_DWORD *)this + 62) = 1;
    v4 = (_QWORD *)((char *)this + 216);
    if ( *((_QWORD *)this + 27) )
    {
      v5 = UIGroupItem::Class;
      if ( (struct DirectUI::IClassInfo *)DirectUI::ClassInfo<UIGroupItem,UIItemCollectionBase,DirectUI::StandardCreator<UIGroupItem>>::GetBaseClass() != v5 )
      {
        v6 = *((_QWORD *)this + 28);
        if ( v6 )
        {
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 40LL))(v6);
          *((_QWORD *)this + 28) = 0;
        }
      }
      ATL::CComPtr<IShellSearchTarget>::operator=(v4, 0);
      if ( *v4 )
      {
        v7 = (*(__int64 (__fastcall **)(UIItem *, __int64))(*(_QWORD *)this + 472LL))(this, 1);
        if ( v7 < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x1B7,
            (unsigned int)"shell\\explorerframe\\itemsview\\uiitem.cpp",
            (const char *)(unsigned int)v7,
            lpData);
      }
    }
    *((_DWORD *)this + 62) = 0;
  }
  ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>(v4);
  *(_QWORD *)this = &UIBase::`vftable';
  DirectUI::Element::~Element(this);
  if ( (a2 & 1) != 0 )
    operator delete(this, (const struct std::nothrow_t *)0x108);
  return this;
}

```

## disassembly

```asm
0x18002e220  mov     [rsp+arg_10], rbx
0x18002e225  mov     [rsp+arg_18], rsi
0x18002e22a  push    rdi
0x18002e22b  push    r14
0x18002e22d  push    r15
0x18002e22f  sub     rsp, 50h
0x18002e233  mov     r15d, edx
0x18002e236  mov     rsi, rcx
0x18002e239  lea     rax, ??_7UIItem@@6B@; const UIItem::`vftable'
0x18002e240  mov     [rcx], rax
0x18002e243  mov     dword ptr [rcx+100h], 0
0x18002e24d  mov     r14d, [rcx+0F8h]
0x18002e254  test    r14d, r14d
0x18002e257  jnz     loc_18002E332
0x18002e25d  mov     dword ptr [rcx+0F8h], 1
0x18002e267  lea     rdi, [rcx+0D8h]
0x18002e26e  cmp     qword ptr [rdi], 0
0x18002e272  jz      short loc_18002E2EC
0x18002e274  mov     rbx, cs:?Class@UIGroupItem@@2PEAUIClassInfo@DirectUI@@EA; DirectUI::IClassInfo * UIGroupItem::Class
0x18002e27b  call    ?GetBaseClass@?$ClassInfo@VUIGroupItem@@VUIItemCollectionBase@@V?$StandardCreator@VUIGroupItem@@@DirectUI@@@DirectUI@@UEBAPEAUIClassInfo@2@XZ; DirectUI::ClassInfo<UIGroupItem,UIItemCollectionBase,DirectUI::StandardCreator<UIGroupItem>>::GetBaseClass(void)
0x18002e280  cmp     rax, rbx
0x18002e283  jz      short loc_18002E2A8
0x18002e285  mov     rcx, [rsi+0E0h]
0x18002e28c  test    rcx, rcx
0x18002e28f  jz      short loc_18002E2A8
0x18002e291  mov     rax, [rcx]
0x18002e294  mov     rax, [rax+28h]
0x18002e298  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e29d  mov     qword ptr [rsi+0E0h], 0
0x18002e2a8  xor     edx, edx
0x18002e2aa  mov     rcx, rdi
0x18002e2ad  call    ??4?$CComPtr@UIShellSearchTarget@@@ATL@@QEAAPEAUIShellSearchTarget@@PEAU2@@Z; ATL::CComPtr<IShellSearchTarget>::operator=(IShellSearchTarget *)
0x18002e2b2  cmp     qword ptr [rdi], 0
0x18002e2b6  jz      short loc_18002E2EC
0x18002e2b8  mov     rax, [rsi]
0x18002e2bb  mov     edx, 1
0x18002e2c0  mov     rcx, rsi
0x18002e2c3  mov     rax, [rax+1D8h]
0x18002e2ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e2cf  mov     rcx, [rsp+68h]; this
0x18002e2d4  test    eax, eax
0x18002e2d6  jns     short loc_18002E2EC
0x18002e2d8  mov     r9d, eax; char *
0x18002e2db  lea     r8, aShellExplorerf_8; "shell\\explorerframe\\itemsview\\uiitem"...
0x18002e2e2  mov     edx, 1B7h; void *
0x18002e2e7  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18002e2ec  mov     [rsi+0F8h], r14d
0x18002e2f3  mov     rcx, rdi; void *
0x18002e2f6  call    ??1?$CComPtr@UIQueryParser2@@@ATL@@QEAA@XZ; ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>(void)
0x18002e2fb  lea     rax, ??_7UIBase@@6B@; const UIBase::`vftable'
0x18002e302  mov     [rsi], rax
0x18002e305  mov     rcx, rsi
0x18002e308  call    cs:__imp_??1Element@DirectUI@@UEAA@XZ; DirectUI::Element::~Element(void)
0x18002e30e  nop
0x18002e30f  test    r15b, 1
0x18002e313  jnz     loc_18002E470
0x18002e319  mov     rax, rsi
0x18002e31c  lea     r11, [rsp+68h+var_18]
0x18002e321  mov     rbx, [r11+30h]
0x18002e325  mov     rsi, [r11+38h]
0x18002e329  mov     rsp, r11
0x18002e32c  pop     r15
0x18002e32e  pop     r14
0x18002e330  pop     rdi
0x18002e331  retn
0x18002e332  call    cs:__imp_GetCurrentThreadId
0x18002e338  mov     cs:?g_dwReentrantThreadId@@3KC, eax; ulong volatile g_dwReentrantThreadId
0x18002e33e  mov     cs:?g_ReentrantCheck@@3W4REENTRANCYCHECKTHATFAILED@@C, 5; REENTRANCYCHECKTHATFAILED volatile g_ReentrantCheck
0x18002e348  xor     r9d, r9d; fDefault
0x18002e34b  xor     r8d, r8d; fIgnoreHKCU
0x18002e34e  lea     rdx, ValueName; "ShellViewReentered"
0x18002e355  lea     rcx, SubKey; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18002e35c  call    cs:__imp_SHRegGetBoolUSValueW
0x18002e362  test    eax, eax
0x18002e364  jz      short loc_18002E398
0x18002e366  mov     dword ptr [rsi+0FCh], 1
0x18002e370  mov     rcx, [rsp+68h]; this
0x18002e375  mov     r9d, 8000FFFFh; char *
0x18002e37b  lea     r8, aShellExplorerf_8; "shell\\explorerframe\\itemsview\\uiitem"...
0x18002e382  mov     edx, 18Eh; void *
0x18002e387  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002e38c  lea     rdi, [rsi+0D8h]
0x18002e393  jmp     loc_18002E2F3
0x18002e398  mov     [rsp+68h+Data], 1
0x18002e3a0  mov     r9d, 4; dwType
0x18002e3a6  mov     [rsp+68h+cbData], r9d; cbData
0x18002e3ab  lea     rax, [rsp+68h+Data]
0x18002e3b0  mov     [rsp+68h+lpData], rax; lpData
0x18002e3b5  lea     r8, ValueName; "ShellViewReentered"
0x18002e3bc  lea     rdx, SubKey; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18002e3c3  mov     rcx, 0FFFFFFFF80000001h; hKey
0x18002e3ca  call    cs:__imp_RegSetKeyValueW
0x18002e3d0  mov     [rsp+68h+TargetHandle], 0
0x18002e3d9  call    cs:__imp_GetCurrentProcess
0x18002e3df  mov     rdi, rax
0x18002e3e2  call    cs:__imp_GetCurrentThread
0x18002e3e8  mov     rbx, rax
0x18002e3eb  call    cs:__imp_GetCurrentProcess
0x18002e3f1  mov     [rsp+68h+dwOptions], 0; dwOptions
0x18002e3f9  mov     [rsp+68h+cbData], 1; bInheritHandle
0x18002e401  mov     dword ptr [rsp+68h+lpData], 1FFFFFh; dwDesiredAccess
0x18002e409  lea     r9, [rsp+68h+TargetHandle]; lpTargetHandle
0x18002e40e  mov     r8, rdi; hTargetProcessHandle
0x18002e411  mov     rdx, rbx; hSourceHandle
0x18002e414  mov     rcx, rax; hSourceProcessHandle
0x18002e417  call    cs:__imp_DuplicateHandle
0x18002e41d  test    eax, eax
0x18002e41f  jz      loc_18002E366
0x18002e425  mov     [rsp+68h+var_20], 0
0x18002e42e  mov     rax, [rsp+68h+TargetHandle]
0x18002e433  mov     [rsp+68h+pData], rax
0x18002e438  call    ?ComputeStackHash@@YAKXZ; ComputeStackHash(void)
0x18002e43d  mov     dword ptr [rsp+68h+var_20], eax
0x18002e441  lea     r9, ?s_SendWERForReentrancy@@YAKPEAX@Z; pfnCallback
0x18002e448  mov     r8d, 200h; flags
0x18002e44e  lea     rdx, [rsp+68h+pData]; pData
0x18002e453  lea     rcx, ?GetProxyCreator@?$PatternProvider@VUIItemsViewScrollProvider@@UIScrollProvider@@$04@DirectUI@@UEAAP6APEAVProviderProxy@2@PEAVElement@2@@ZXZ; pfnThreadProc
0x18002e45a  call    cs:__imp_SHCreateThread
0x18002e460  mov     rcx, [rsp+68h+TargetHandle]; hObject
0x18002e465  call    cs:__imp_CloseHandle
0x18002e46b  jmp     loc_18002E366
0x18002e470  mov     edx, 108h; struct std::nothrow_t *
0x18002e475  mov     rcx, rsi; void *
0x18002e478  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18002e47d  jmp     loc_18002E319
```
