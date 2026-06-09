# HwndUtils::HwndSetFocus(HWND__ *,std::optional<_GUID> const &)

- ea: `0x18024d490`
- end: `0x18024d61c`
- name: `?HwndSetFocus@HwndUtils@@SAHPEAUHWND__@@AEBV?$optional@U_GUID@@@std@@@Z`
- size: `396`
- prototype: `__int64 __fastcall(HWND, struct _GUID *)`
- caller_count: `2`
- callee_count: `9`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1801c5888`
- `0x180288130`

## callees

- `0x180006e18`
- `0x18000b790`
- `0x180036198`
- `0x180037cfc`
- `0x18003a9d4`
- `0x180080cc0`
- `0x18024d230`
- `0x18024d490`
- `0x1802c0368`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18024d577`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18024d577`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18024d5bf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18024d5bf`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!GetWindowLongW` at `0x18024d4e7`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!GetWindowLongW` at `0x18024d4e7`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!SetFocus` at `0x18024d5ad`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!SetFocus` at `0x18024d5e7`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!SetFocus` at `0x18024d5ad`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!SetFocus` at `0x18024d5e7`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!GetWindowThreadProcessId` at `0x18024d587`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!GetWindowThreadProcessId` at `0x18024d594`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!GetWindowThreadProcessId` at `0x18024d587`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!GetWindowThreadProcessId` at `0x18024d594`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!GetPropW` at `0x18024d4d6`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!GetPropW` at `0x18024d4d6`
- `ext-ms-win-ntuser-misc-l1-2-0!AttachThreadInput` at `0x18024d5da`
- `ext-ms-win-ntuser-misc-l1-2-0!AttachThreadInput` at `0x18024d5f7`
- `ext-ms-win-ntuser-misc-l1-2-0!AttachThreadInput` at `0x18024d5da`
- `ext-ms-win-ntuser-misc-l1-2-0!AttachThreadInput` at `0x18024d5f7`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall HwndUtils::HwndSetFocus(HWND a1, struct _GUID *a2)
{
  unsigned int PropW; // ebx
  LONG WindowLongW; // eax
  bool v6; // bl
  HWND FocusedWindow; // rbx
  DWORD CurrentThreadId; // esi
  DWORD WindowThreadProcessId; // ebp
  DWORD v10; // eax
  DWORD v11; // r14d
  HWND v12; // rbx
  bool v13; // [rsp+58h] [rbp+10h] BYREF
  DWORD dwProcessId; // [rsp+60h] [rbp+18h] BYREF
  struct ProviderEntryPoint *v15; // [rsp+68h] [rbp+20h] BYREF

  if ( LOBYTE(a2[1].Data1) )
    return (int)HwndUtils::CrossMachineSetFocus(a2, a1) >= 0;
  if ( !BasicUiaUtils::IsDesktop() )
    return 0;
  PropW = (unsigned int)GetPropW(a1, L"UIA_WindowPatternEnabled");
  WindowLongW = GetWindowLongW(a1, -16);
  if ( WindowLongW < 0
    && ((WindowLongW & 0x800000) == 0 || (WindowLongW & 0x400000) == 0)
    && PropW != 1
    && !UiaUtils::IsRailWindow(a1) )
  {
    v6 = 0;
    v13 = 0;
    v15 = 0;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v15);
    if ( (int)ProviderEntryPoint::CreateUsingHwnd(a1, &v15) >= 0 )
    {
      UiaUtils::IsComponentViewRoot(v15, &v13);
      v6 = v13;
    }
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v15);
    if ( !v6 )
      return 1;
  }
  FocusedWindow = HwndUtils::GetFocusedWindow();
  if ( FocusedWindow == a1 )
    return 1;
  dwProcessId = 0;
  CurrentThreadId = GetCurrentThreadId();
  WindowThreadProcessId = GetWindowThreadProcessId(a1, &dwProcessId);
  v10 = GetWindowThreadProcessId(FocusedWindow, 0);
  v11 = v10;
  if ( CurrentThreadId == WindowThreadProcessId && FocusedWindow && CurrentThreadId == v10 )
    return SetFocus(a1) != 0;
  if ( dwProcessId == GetCurrentProcessId()
    && WindowThreadProcessId == v11
    && AttachThreadInput(CurrentThreadId, WindowThreadProcessId, 1)
    && (v12 = SetFocus(a1), AttachThreadInput(CurrentThreadId, WindowThreadProcessId, 0), v12) )
  {
    return 1;
  }
  else
  {
    return BasicHwndUtils::HwndSetFocus(a1);
  }
}

```

## disassembly

```asm
0x18024d490  push    rbx
0x18024d492  push    rbp
0x18024d493  push    rsi
0x18024d494  push    rdi
0x18024d495  push    r14
0x18024d497  sub     rsp, 20h
0x18024d49b  mov     rax, rdx
0x18024d49e  mov     rdi, rcx
0x18024d4a1  cmp     byte ptr [rdx+10h], 0
0x18024d4a5  jz      short loc_18024D4BC
0x18024d4a7  mov     rdx, rcx; HWND
0x18024d4aa  mov     rcx, rax; struct _GUID *
0x18024d4ad  call    ?CrossMachineSetFocus@HwndUtils@@CAJAEBU_GUID@@PEAUHWND__@@@Z; HwndUtils::CrossMachineSetFocus(_GUID const &,HWND__ *)
0x18024d4b2  not     eax
0x18024d4b4  shr     eax, 1Fh
0x18024d4b7  jmp     loc_18024D611
0x18024d4bc  call    ?IsDesktop@BasicUiaUtils@@SA_NXZ; BasicUiaUtils::IsDesktop(void)
0x18024d4c1  test    al, al
0x18024d4c3  jnz     short loc_18024D4CC
0x18024d4c5  xor     eax, eax
0x18024d4c7  jmp     loc_18024D611
0x18024d4cc  lea     rdx, aUiaWindowpatte; "UIA_WindowPatternEnabled"
0x18024d4d3  mov     rcx, rdi; hWnd
0x18024d4d6  call    cs:__imp_GetPropW
0x18024d4dc  mov     rbx, rax
0x18024d4df  mov     edx, 0FFFFFFF0h; nIndex
0x18024d4e4  mov     rcx, rdi; hWnd
0x18024d4e7  call    cs:__imp_GetWindowLongW
0x18024d4ed  test    eax, eax
0x18024d4ef  jns     short loc_18024D55E
0x18024d4f1  bt      eax, 17h
0x18024d4f5  jnb     short loc_18024D4FD
0x18024d4f7  bt      eax, 16h
0x18024d4fb  jb      short loc_18024D55E
0x18024d4fd  cmp     ebx, 1
0x18024d500  jz      short loc_18024D55E
0x18024d502  mov     rcx, rdi; HWND
0x18024d505  call    ?IsRailWindow@UiaUtils@@SA_NPEAUHWND__@@@Z; UiaUtils::IsRailWindow(HWND__ *)
0x18024d50a  test    al, al
0x18024d50c  jnz     short loc_18024D55E
0x18024d50e  xor     bl, bl
0x18024d510  mov     [rsp+48h+arg_8], bl
0x18024d514  mov     [rsp+48h+arg_18], 0
0x18024d51d  lea     rcx, [rsp+48h+arg_18]
0x18024d522  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18024d527  lea     rdx, [rsp+48h+arg_18]; struct ProviderEntryPoint **
0x18024d52c  mov     rcx, rdi; HWND
0x18024d52f  call    ?CreateUsingHwnd@ProviderEntryPoint@@SAJPEAUHWND__@@PEAPEAV1@@Z; ProviderEntryPoint::CreateUsingHwnd(HWND__ *,ProviderEntryPoint * *)
0x18024d534  test    eax, eax
0x18024d536  js      short loc_18024D54B
0x18024d538  lea     rdx, [rsp+48h+arg_8]; bool *
0x18024d53d  mov     rcx, [rsp+48h+arg_18]; struct ProviderEntryPoint *
0x18024d542  call    ?IsComponentViewRoot@UiaUtils@@SAJPEAVProviderEntryPoint@@PEA_N@Z; UiaUtils::IsComponentViewRoot(ProviderEntryPoint *,bool *)
0x18024d547  mov     bl, [rsp+48h+arg_8]
0x18024d54b  lea     rcx, [rsp+48h+arg_18]
0x18024d550  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18024d555  nop
0x18024d556  test    bl, bl
0x18024d558  jz      loc_18024D60C
0x18024d55e  call    ?GetFocusedWindow@HwndUtils@@SAPEAUHWND__@@XZ; HwndUtils::GetFocusedWindow(void)
0x18024d563  mov     rbx, rax
0x18024d566  cmp     rax, rdi
0x18024d569  jz      loc_18024D60C
0x18024d56f  mov     [rsp+48h+dwProcessId], 0
0x18024d577  call    cs:__imp_GetCurrentThreadId
0x18024d57d  mov     esi, eax
0x18024d57f  lea     rdx, [rsp+48h+dwProcessId]; lpdwProcessId
0x18024d584  mov     rcx, rdi; hWnd
0x18024d587  call    cs:__imp_GetWindowThreadProcessId
0x18024d58d  mov     ebp, eax
0x18024d58f  xor     edx, edx; lpdwProcessId
0x18024d591  mov     rcx, rbx; hWnd
0x18024d594  call    cs:__imp_GetWindowThreadProcessId
0x18024d59a  mov     r14d, eax
0x18024d59d  cmp     esi, ebp
0x18024d59f  jnz     short loc_18024D5BF
0x18024d5a1  test    rbx, rbx
0x18024d5a4  jz      short loc_18024D5BF
0x18024d5a6  cmp     esi, eax
0x18024d5a8  jnz     short loc_18024D5BF
0x18024d5aa  mov     rcx, rdi; hWnd
0x18024d5ad  call    cs:__imp_SetFocus
0x18024d5b3  xor     ecx, ecx
0x18024d5b5  test    rax, rax
0x18024d5b8  setnz   cl
0x18024d5bb  mov     eax, ecx
0x18024d5bd  jmp     short loc_18024D611
0x18024d5bf  call    cs:__imp_GetCurrentProcessId
0x18024d5c5  cmp     [rsp+48h+dwProcessId], eax
0x18024d5c9  jnz     short loc_18024D602
0x18024d5cb  cmp     ebp, r14d
0x18024d5ce  jnz     short loc_18024D602
0x18024d5d0  mov     r8d, 1; fAttach
0x18024d5d6  mov     edx, ebp; idAttachTo
0x18024d5d8  mov     ecx, esi; idAttach
0x18024d5da  call    cs:__imp_AttachThreadInput
0x18024d5e0  test    eax, eax
0x18024d5e2  jz      short loc_18024D602
0x18024d5e4  mov     rcx, rdi; hWnd
0x18024d5e7  call    cs:__imp_SetFocus
0x18024d5ed  mov     rbx, rax
0x18024d5f0  xor     r8d, r8d; fAttach
0x18024d5f3  mov     edx, ebp; idAttachTo
0x18024d5f5  mov     ecx, esi; idAttach
0x18024d5f7  call    cs:__imp_AttachThreadInput
0x18024d5fd  test    rbx, rbx
0x18024d600  jnz     short loc_18024D60C
0x18024d602  mov     rcx, rdi; HWND
0x18024d605  call    ?HwndSetFocus@BasicHwndUtils@@SAHPEAUHWND__@@@Z; BasicHwndUtils::HwndSetFocus(HWND__ *)
0x18024d60a  jmp     short loc_18024D611
0x18024d60c  mov     eax, 1
0x18024d611  add     rsp, 20h
0x18024d615  pop     r14
0x18024d617  pop     rdi
0x18024d618  pop     rsi
0x18024d619  pop     rbp
0x18024d61a  pop     rbx
0x18024d61b  retn
```
