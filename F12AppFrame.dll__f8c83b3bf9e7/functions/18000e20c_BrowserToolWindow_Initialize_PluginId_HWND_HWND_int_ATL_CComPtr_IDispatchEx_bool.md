# BrowserToolWindow::Initialize(PluginId,HWND__ *,HWND__ *,int,ATL::CComPtr<IDispatchEx> &,bool)

- ea: `0x18000e20c`
- end: `0x18000e450`
- name: `?Initialize@BrowserToolWindow@@QEAAJW4PluginId@@PEAUHWND__@@1HAEAV?$CComPtr@UIDispatchEx@@@ATL@@_N@Z`
- size: `580`
- prototype: `__int64 __usercall@<rax>(HMENU hMenu@<rcx>, int, LPCWSTR lpWindowName, char)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x18000bddc`

## callees

- `0x180003c38`
- `0x180005e44`
- `0x180006e00`
- `0x180008efc`
- `0x18000dfac`
- `0x18000e20c`
- `0x18002d408`
- `0x18002d524`
- `0x180035010`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x18000e38d`
- `KERNEL32!EnterCriticalSection` at `0x18000e38d`
- `KERNEL32!LeaveCriticalSection` at `0x18000e3ac`
- `KERNEL32!LeaveCriticalSection` at `0x18000e3ac`
- `KERNEL32!GetCurrentThreadId` at `0x18000e37d`
- `KERNEL32!GetCurrentThreadId` at `0x18000e37d`
- `KERNEL32!SetLastError` at `0x18000e31f`
- `KERNEL32!SetLastError` at `0x18000e31f`
- `USER32!CreateWindowExW` at `0x18000e40f`
- `USER32!CreateWindowExW` at `0x18000e40f`

## string_xrefs

- `0x18000e2ba`: `PluginId %d`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall BrowserToolWindow::Initialize(
        HMENU hMenu,
        int a2,
        HWND a3,
        __int64 a4,
        int a5,
        LPCWSTR lpWindowName,
        char a7)
{
  __int64 v9; // rdi
  __int64 v10; // rcx
  const WCHAR *v11; // rsi
  WNDCLASSEXW *WndClassInfo; // rax
  const WCHAR *v13; // rbp
  AtlThunkData_t *Data; // rax
  unsigned int Error; // ebx
  int v17; // edx
  unsigned int v18; // r8d

  *((_DWORD *)hMenu + 46) = a2;
  *((_QWORD *)hMenu + 24) = a4;
  v9 = *(_QWORD *)lpWindowName;
  if ( *((_QWORD *)hMenu + 21) != *(_QWORD *)lpWindowName )
  {
    if ( v9 )
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v9 + 8LL))(*(_QWORD *)lpWindowName);
    v10 = *((_QWORD *)hMenu + 21);
    if ( v10 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
    *((_QWORD *)hMenu + 21) = v9;
  }
  *((_BYTE *)hMenu + 201) = a7;
  *((_DWORD *)hMenu + 52) = a5;
  lpWindowName = (LPCWSTR)(((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Format(
    (wchar_t *const *)&lpWindowName,
    L"PluginId %d",
    *((unsigned int *)hMenu + 46));
  v11 = lpWindowName;
  if ( !*((_QWORD *)BrowserToolWindow::GetWndClassInfo() + 10) )
    *((_QWORD *)BrowserToolWindow::GetWndClassInfo() + 10) = L"AtlAxWinLic80";
  WndClassInfo = (WNDCLASSEXW *)BrowserToolWindow::GetWndClassInfo();
  v13 = (const WCHAR *)ATL::_ATL_WNDCLASSINFOW::Register(
                         WndClassInfo,
                         (__int64 (**)(HWND, unsigned int, unsigned __int64, __int64))hMenu + 8);
  Data = (AtlThunkData_t *)*((_QWORD *)hMenu + 5);
  if ( !Data )
  {
    Data = AtlThunk_AllocateData();
    *((_QWORD *)hMenu + 5) = Data;
    if ( !Data )
    {
      SetLastError(0xEu);
LABEL_12:
      Error = ATL::AtlHresultFromLastError();
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)v11 - 2, 0xFFFFFFFF) <= 1 )
        (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v11 - 3) + 8LL))(*((_QWORD *)v11 - 3));
      return Error;
    }
  }
  AtlThunk_InitData(Data, 0, 0);
  if ( !(_WORD)v13 )
    goto LABEL_12;
  if ( hMenu == (HMENU)-16LL )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)0xC0000005LL, v17, v18);
    JUMPOUT(0x18000E44FLL);
  }
  *((_QWORD *)hMenu + 2) = hMenu;
  *((_DWORD *)hMenu + 6) = GetCurrentThreadId();
  EnterCriticalSection(&stru_1800503B8);
  *((_QWORD *)hMenu + 4) = qword_1800503E0;
  qword_1800503E0 = (__int64)(hMenu + 4);
  LeaveCriticalSection(&stru_1800503B8);
  if ( !CreateWindowExW(
          0,
          v13,
          v11,
          0x5E000000u,
          ATL::CWindow::rcDefault,
          Y,
          dword_180050340 - ATL::CWindow::rcDefault,
          dword_180050344 - Y,
          a3,
          hMenu,
          hInst,
          0) )
    goto LABEL_12;
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)v11 - 2, 0xFFFFFFFF) <= 1 )
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v11 - 3) + 8LL))(*((_QWORD *)v11 - 3));
  return 0;
}

```

## disassembly

```asm
0x18000e20c  push    rbx
0x18000e20e  push    rbp
0x18000e20f  push    rsi
0x18000e210  push    rdi
0x18000e211  push    r14
0x18000e213  push    r15
0x18000e215  sub     rsp, 68h
0x18000e219  mov     r14, r8
0x18000e21c  mov     rbx, rcx
0x18000e21f  mov     [rcx+0B8h], edx
0x18000e225  mov     [rcx+0C0h], r9
0x18000e22c  mov     rax, [rsp+98h+lpWindowName]
0x18000e234  mov     rdi, [rax]
0x18000e237  xor     r15d, r15d
0x18000e23a  cmp     [rcx+0A8h], rdi
0x18000e241  jz      short loc_18000E276
0x18000e243  test    rdi, rdi
0x18000e246  jz      short loc_18000E257
0x18000e248  mov     rax, [rdi]
0x18000e24b  mov     rcx, rdi
0x18000e24e  mov     rax, [rax+8]
0x18000e252  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e257  mov     rcx, [rbx+0A8h]
0x18000e25e  test    rcx, rcx
0x18000e261  jz      short loc_18000E26F
0x18000e263  mov     rax, [rcx]
0x18000e266  mov     rax, [rax+10h]
0x18000e26a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e26f  mov     [rbx+0A8h], rdi
0x18000e276  mov     al, [rsp+98h+arg_30]
0x18000e27d  mov     [rbx+0C9h], al
0x18000e283  mov     eax, [rsp+98h+arg_20]
0x18000e28a  mov     [rbx+0D0h], eax
0x18000e290  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x18000e297  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x18000e29e  mov     rax, [rax+18h]
0x18000e2a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e2a7  add     rax, 18h
0x18000e2ab  mov     [rsp+98h+lpWindowName], rax
0x18000e2b3  mov     r8d, [rbx+0B8h]
0x18000e2ba  lea     rdx, aPluginidD; "PluginId %d"
0x18000e2c1  lea     rcx, [rsp+98h+lpWindowName]
0x18000e2c9  call    ?Format@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Format(ushort const *,...)
0x18000e2ce  mov     rsi, [rsp+98h+lpWindowName]
0x18000e2d6  call    ?GetWndClassInfo@BrowserToolWindow@@SAAEAU_ATL_WNDCLASSINFOW@ATL@@XZ; BrowserToolWindow::GetWndClassInfo(void)
0x18000e2db  cmp     [rax+50h], r15
0x18000e2df  jnz     short loc_18000E2F1
0x18000e2e1  call    ?GetWndClassInfo@BrowserToolWindow@@SAAEAU_ATL_WNDCLASSINFOW@ATL@@XZ; BrowserToolWindow::GetWndClassInfo(void)
0x18000e2e6  lea     rcx, aAtlaxwinlic80; "AtlAxWinLic80"
0x18000e2ed  mov     [rax+50h], rcx
0x18000e2f1  call    ?GetWndClassInfo@BrowserToolWindow@@SAAEAU_ATL_WNDCLASSINFOW@ATL@@XZ; BrowserToolWindow::GetWndClassInfo(void)
0x18000e2f6  lea     rdx, [rbx+40h]; __int64 (**)(HWND, unsigned int, unsigned __int64, __int64)
0x18000e2fa  mov     rcx, rax; this
0x18000e2fd  call    ?Register@_ATL_WNDCLASSINFOW@ATL@@QEAAGPEAP6A_JPEAUHWND__@@I_K_J@Z@Z; ATL::_ATL_WNDCLASSINFOW::Register(__int64 (**)(HWND__ *,uint,unsigned __int64,__int64))
0x18000e302  movzx   ebp, ax
0x18000e305  mov     rax, [rbx+28h]
0x18000e309  test    rax, rax
0x18000e30c  jnz     short loc_18000E35B
0x18000e30e  call    AtlThunk_AllocateData
0x18000e313  mov     [rbx+28h], rax
0x18000e317  test    rax, rax
0x18000e31a  jnz     short loc_18000E35B
0x18000e31c  lea     ecx, [rax+0Eh]; dwErrCode
0x18000e31f  call    cs:__imp_SetLastError
0x18000e325  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x18000e32a  mov     ebx, eax
0x18000e32c  lea     rdx, [rsi-18h]
0x18000e330  or      ecx, 0FFFFFFFFh
0x18000e333  lock xadd [rdx+10h], ecx
0x18000e338  sub     ecx, 1
0x18000e33b  jg      short loc_18000E34C
0x18000e33d  mov     rcx, [rdx]
0x18000e340  mov     r8, [rcx]
0x18000e343  mov     rax, [r8+8]
0x18000e347  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e34c  mov     eax, ebx
0x18000e34e  add     rsp, 68h
0x18000e352  pop     r15
0x18000e354  pop     r14
0x18000e356  pop     rdi
0x18000e357  pop     rsi
0x18000e358  pop     rbp
0x18000e359  pop     rbx
0x18000e35a  retn
0x18000e35b  xor     r8d, r8d; FirstParameter
0x18000e35e  xor     edx, edx; Proc
0x18000e360  mov     rcx, rax; Thunk
0x18000e363  call    AtlThunk_InitData
0x18000e368  test    bp, bp
0x18000e36b  jz      short loc_18000E325
0x18000e36d  lea     rdi, [rbx+10h]
0x18000e371  test    rdi, rdi
0x18000e374  jz      loc_18000E445
0x18000e37a  mov     [rdi], rbx
0x18000e37d  call    cs:__imp_GetCurrentThreadId
0x18000e383  mov     [rdi+8], eax
0x18000e386  lea     rcx, stru_1800503B8; lpCriticalSection
0x18000e38d  call    cs:__imp_EnterCriticalSection
0x18000e393  mov     rax, cs:qword_1800503E0
0x18000e39a  mov     [rdi+10h], rax
0x18000e39e  mov     cs:qword_1800503E0, rdi
0x18000e3a5  lea     rcx, stru_1800503B8; lpCriticalSection
0x18000e3ac  call    cs:__imp_LeaveCriticalSection
0x18000e3b2  mov     rcx, cs:hInst
0x18000e3b9  mov     r9d, cs:Y
0x18000e3c0  mov     r10d, cs:?rcDefault@CWindow@ATL@@2UtagRECT@@A; tagRECT ATL::CWindow::rcDefault
0x18000e3c7  mov     r8d, cs:dword_180050344
0x18000e3ce  sub     r8d, r9d
0x18000e3d1  mov     eax, cs:dword_180050340
0x18000e3d7  sub     eax, r10d
0x18000e3da  mov     rdx, rbp; lpClassName
0x18000e3dd  mov     [rsp+98h+lpParam], r15; lpParam
0x18000e3e2  mov     [rsp+98h+hInstance], rcx; hInstance
0x18000e3e7  mov     [rsp+98h+hMenu], rbx; hMenu
0x18000e3ec  mov     [rsp+98h+hWndParent], r14; hWndParent
0x18000e3f1  mov     [rsp+98h+nHeight], r8d; nHeight
0x18000e3f6  mov     [rsp+98h+nWidth], eax; nWidth
0x18000e3fa  mov     [rsp+98h+Y], r9d; Y
0x18000e3ff  mov     [rsp+98h+X], r10d; X
0x18000e404  mov     r9d, 5E000000h; dwStyle
0x18000e40a  mov     r8, rsi; lpWindowName
0x18000e40d  xor     ecx, ecx; dwExStyle
0x18000e40f  call    cs:__imp_CreateWindowExW
0x18000e415  test    rax, rax
0x18000e418  jz      loc_18000E325
0x18000e41e  lea     rdx, [rsi-18h]
0x18000e422  or      eax, 0FFFFFFFFh
0x18000e425  lock xadd [rdx+10h], eax
0x18000e42a  sub     eax, 1
0x18000e42d  jg      short loc_18000E43E
0x18000e42f  mov     rcx, [rdx]
0x18000e432  mov     rax, [rcx]
0x18000e435  mov     rax, [rax+8]
0x18000e439  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e43e  xor     eax, eax
0x18000e440  jmp     loc_18000E34E
0x18000e445  mov     ecx, 0C0000005h; this
0x18000e44a  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
```
