# Windows::Internal::DialogWindowTrait::CreatePopupWindow(ulong,ushort const *,ulong,HWND__ *,HMONITOR__ *,POPUP_OPTIONS,XamlPopupOptions)

- ea: `0x1800a85a0`
- end: `0x1800a8947`
- name: `?CreatePopupWindow@DialogWindowTrait@Internal@Windows@@UEAAPEAUHWND__@@KPEBGKPEAU4@PEAUHMONITOR__@@W4POPUP_OPTIONS@@W4XamlPopupOptions@@@Z`
- size: `935`
- prototype: ``
- caller_count: `0`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180027d9c`
- `0x18002ebe0`
- `0x18004da70`
- `0x180050ba0`
- `0x180051524`
- `0x1800a85a0`
- `0x1800a8e54`
- `0x1800a8f54`
- `0x1800a9adc`
- `0x1800d8268`
- `0x1800e5010`

## import_xrefs

- `USER32!CreateWindowInBandEx` at `0x1800a8861`
- `USER32!CreateWindowInBandEx` at `0x1800a8861`
- `USER32!GetWindowBand` at `0x1800a86cd`
- `USER32!GetWindowBand` at `0x1800a86cd`
- `USER32!SetPropW` at `0x1800a88f4`
- `USER32!SetPropW` at `0x1800a88f4`
- `USER32!RegisterClassW` at `0x1800a8690`
- `USER32!RegisterClassW` at `0x1800a8690`
- `USER32!GetAncestor` at `0x1800a86e9`
- `USER32!GetAncestor` at `0x1800a86e9`
- `USER32!LoadCursorW` at `0x1800a865d`
- `USER32!LoadCursorW` at `0x1800a865d`
- `USER32!GetWindowRect` at `0x1800a87ee`
- `USER32!GetWindowRect` at `0x1800a87ee`
- `USER32!GetWindow` at `0x1800a8752`
- `USER32!GetWindow` at `0x1800a88da`
- `USER32!GetWindow` at `0x1800a8752`
- `USER32!GetWindow` at `0x1800a88da`
- `USER32!SendMessageW` at `0x1800a891e`
- `USER32!SendMessageW` at `0x1800a891e`
- `USER32!DefWindowProcW` at `0x1800a8640`
- `USER32!__imp_IsShellFrameWindow` at `0x1800a86f5`
- `USER32!__imp_IsShellFrameWindow` at `0x1800a86f5`
- `USER32!__imp_IsShellManagedWindow` at `0x1800a8699`
- `USER32!__imp_IsShellManagedWindow` at `0x1800a8699`
- `ext-ms-win-rtcore-ntuser-dpi-l1-2-0!GetThreadDpiAwarenessContext` at `0x1800a879e`
- `ext-ms-win-rtcore-ntuser-dpi-l1-2-0!GetThreadDpiAwarenessContext` at `0x1800a879e`
- `ext-ms-win-rtcore-ntuser-dpi-l1-2-0!SetThreadDpiAwarenessContext` at `0x1800a87bf`
- `ext-ms-win-rtcore-ntuser-dpi-l1-2-0!SetThreadDpiAwarenessContext` at `0x1800a8876`
- `ext-ms-win-rtcore-ntuser-dpi-l1-2-0!SetThreadDpiAwarenessContext` at `0x1800a87bf`
- `ext-ms-win-rtcore-ntuser-dpi-l1-2-0!SetThreadDpiAwarenessContext` at `0x1800a8876`
- `ext-ms-win-rtcore-ntuser-dpi-l1-2-0!AreDpiAwarenessContextsEqual` at `0x1800a87ae`
- `ext-ms-win-rtcore-ntuser-dpi-l1-2-0!AreDpiAwarenessContextsEqual` at `0x1800a87ae`

## pseudocode

```c
HWND __fastcall Windows::Internal::DialogWindowTrait::CreatePopupWindow(
        __int64 a1,
        unsigned int a2,
        __int64 a3,
        int a4,
        HWND hwnd,
        __int64 a6,
        int a7,
        int a8)
{
  bool *v9; // r8
  HCURSOR CursorW; // rax
  bool v11; // zf
  const wchar_t *v12; // r13
  const WCHAR *v13; // rax
  int v14; // eax
  __int64 v15; // r15
  int v16; // ecx
  int WindowBand; // eax
  HWND Ancestor; // rdi
  int v19; // eax
  HWND WindowInBand; // rdi
  unsigned int v21; // eax
  __int64 v22; // rsi
  unsigned int v23; // edi
  __int64 ThreadDpiAwarenessContext; // rax
  LONG left; // ecx
  LONG top; // r9d
  int v27; // edx
  int v28; // r8d
  HWND v29; // rsi
  bool v31; // [rsp+70h] [rbp-90h]
  CallerIdentity *v32; // [rsp+78h] [rbp-88h] BYREF
  int v33; // [rsp+80h] [rbp-80h] BYREF
  unsigned int v34; // [rsp+84h] [rbp-7Ch]
  int v35; // [rsp+88h] [rbp-78h]
  __int64 v36; // [rsp+90h] [rbp-70h]
  WNDCLASSW WndClass; // [rsp+A0h] [rbp-60h] BYREF
  struct tagRECT Rect; // [rsp+F0h] [rbp-10h] BYREF

  *(_QWORD *)&Rect.left = a6;
  v36 = a3;
  v34 = a2;
  *(_DWORD *)(a1 + 20) = a8;
  v35 = a4;
  *(_DWORD *)(a1 + 16) = a7;
  v32 = 0;
  if ( (int)CallerIdentity::GetCallingProcessHandle(a1, 0, &v32) >= 0 )
    CallerIdentity::IsProcessAppContainer(v32, (void *)(a1 + 32), v9);
  CAutoHandle<void *>::~CAutoHandle<void *>(&v32);
  memset_0(&WndClass, 0, sizeof(WndClass));
  WndClass.lpfnWndProc = DefWindowProcW;
  WndClass.hInstance = &_ImageBase;
  CursorW = LoadCursorW(0, (LPCWSTR)0x7F00);
  v11 = *(_BYTE *)(a1 + 60) == 0;
  WndClass.hCursor = CursorW;
  v12 = L"Shell_HostingContainer";
  v13 = L"Shell_HostingContainer";
  WndClass.hbrBackground = (HBRUSH)6;
  if ( v11 )
    v13 = L"Shell_Dialog";
  WndClass.lpszClassName = v13;
  RegisterClassW(&WndClass);
  v14 = IsShellManagedWindow(hwnd);
  v15 = (__int64)hwnd;
  v31 = v14 != 0;
  v16 = 0;
  LODWORD(v32) = 0;
  v33 = 0;
  if ( v14 )
  {
    if ( *(_BYTE *)(a1 + 32) )
    {
      LODWORD(v32) = 1;
      v15 = 0;
      WindowBand = GetWindowBand(hwnd, &v33);
      v16 = (int)v32;
      if ( !WindowBand )
        v33 = 1;
    }
    else
    {
      Ancestor = GetAncestor(hwnd, 1u);
      v19 = IsShellFrameWindow(Ancestor);
      v16 = (int)v32;
      if ( v19 )
      {
        v15 = (__int64)Ancestor;
        v31 = 0;
      }
    }
  }
  if ( (a7 & 8) != 0 )
  {
    if ( !*(_BYTE *)(a1 + 60) )
      v12 = L"Shell_Dialog";
    WindowInBand = (HWND)Windows::Internal::_anonymous_namespace_::CDimmingWindow::CreateOnDesktop(
                           v34,
                           (_DWORD)v12,
                           v36,
                           v35,
                           v15,
                           v16,
                           *(__int64 *)&Rect.left);
    *(_QWORD *)(a1 + 48) = GetWindow(WindowInBand, 4u);
  }
  else
  {
    v21 = 0x80000000;
    if ( !*(_BYTE *)(a1 + 61) && (a7 & 0x200000) == 0 )
    {
      v21 = -2134900736;
      if ( *(_BYTE *)(a1 + 60) )
        v21 = -2134376448;
    }
    v22 = 0;
    v23 = v21 | 0xCA0000;
    if ( (a7 & 0x20000000) == 0 )
      v23 = v21;
    ThreadDpiAwarenessContext = GetThreadDpiAwarenessContext();
    if ( (unsigned int)AreDpiAwarenessContextsEqual(ThreadDpiAwarenessContext, -3) )
      v22 = SetThreadDpiAwarenessContext(-4);
    left = 0x80000000;
    top = 0x80000000;
    v27 = 0x80000000;
    v28 = 0x80000000;
    if ( hwnd && *(_BYTE *)(a1 + 62) )
    {
      Rect = 0;
      GetWindowRect(hwnd, &Rect);
      left = Rect.left;
      v27 = Rect.right - Rect.left;
      top = Rect.top;
      v28 = Rect.bottom - Rect.top;
    }
    if ( !*(_BYTE *)(a1 + 60) )
      v12 = L"Shell_Dialog";
    WindowInBand = (HWND)CreateWindowInBandEx(
                           v34,
                           v12,
                           v36,
                           v23,
                           left,
                           top,
                           v27,
                           v28,
                           v15,
                           0,
                           &_ImageBase,
                           0,
                           v33,
                           (_DWORD)v32);
    if ( v22 )
      SetThreadDpiAwarenessContext(-3);
    if ( *(_BYTE *)(a1 + 61) )
      Windows::Internal::DialogWindowTrait::_SetWindowVisualPolicy(WindowInBand, 1);
  }
  if ( WindowInBand )
  {
    *(_QWORD *)(a1 + 8) = v15;
    if ( v31 )
    {
      v29 = WindowInBand;
      if ( *(_QWORD *)(a1 + 48) )
        v29 = *(HWND *)(a1 + 48);
      if ( (int)Windows::Internal::DialogWindowTrait::_EnsureBroker((Windows::Internal::DialogWindowTrait *)a1) >= 0
        && (*(int (__fastcall **)(_QWORD, HWND, HWND))(**(_QWORD **)(a1 + 40) + 24LL))(*(_QWORD *)(a1 + 40), v29, hwnd) >= 0 )
      {
        *(_QWORD *)(a1 + 8) = GetWindow(v29, 4u);
      }
    }
    SetPropW(WindowInBand, L"Shell_Dialog_Window_Prop", HANDLE_FLAG_INHERIT);
    if ( (*(_DWORD *)(a1 + 16) & 0x4000) != 0 )
      SetIhmRequireTouchInEditField(1, WindowInBand);
    SendMessageW(WindowInBand, 0x127u, 0x30001u, 0);
  }
  return WindowInBand;
}

```

## disassembly

```asm
0x1800a85a0  push    rbp
0x1800a85a2  push    rbx
0x1800a85a3  push    rsi
0x1800a85a4  push    rdi
0x1800a85a5  push    r12
0x1800a85a7  push    r13
0x1800a85a9  push    r14
0x1800a85ab  push    r15
0x1800a85ad  lea     rbp, [rsp-18h]
0x1800a85b2  sub     rsp, 118h
0x1800a85b9  mov     rax, cs:__security_cookie
0x1800a85c0  xor     rax, rsp
0x1800a85c3  mov     [rbp+50h+var_50], rax
0x1800a85c7  mov     rax, [rbp+50h+arg_28]
0x1800a85ce  mov     rbx, rcx
0x1800a85d1  mov     esi, [rbp+50h+arg_30]
0x1800a85d7  mov     r12d, esi
0x1800a85da  mov     r14, [rbp+50h+hwnd]
0x1800a85e1  and     r12d, 8
0x1800a85e5  mov     qword ptr [rbp+50h+Rect.left], rax
0x1800a85e9  mov     eax, [rbp+50h+arg_38]
0x1800a85ef  mov     [rbp+50h+var_C0], r8
0x1800a85f3  lea     r8, [rsp+150h+var_D8]
0x1800a85f8  mov     [rbp+50h+var_CC], edx
0x1800a85fb  xor     edx, edx
0x1800a85fd  mov     [rcx+14h], eax
0x1800a8600  mov     [rbp+50h+var_C8], r9d
0x1800a8604  mov     [rcx+10h], esi
0x1800a8607  mov     [rsp+150h+var_D8], 0
0x1800a8610  call    ?GetCallingProcessHandle@CallerIdentity@@YAJKW4RUNTIMEBROKER_CALLERIDENTITY_CHECK@@PEAPEAX@Z; CallerIdentity::GetCallingProcessHandle(ulong,RUNTIMEBROKER_CALLERIDENTITY_CHECK,void * *)
0x1800a8615  test    eax, eax
0x1800a8617  js      short loc_1800A8627
0x1800a8619  mov     rcx, [rsp+150h+var_D8]; this
0x1800a861e  lea     rdx, [rbx+20h]; void *
0x1800a8622  call    ?IsProcessAppContainer@CallerIdentity@@YAJPEAXPEA_N@Z; CallerIdentity::IsProcessAppContainer(void *,bool *)
0x1800a8627  lea     rcx, [rsp+150h+var_D8]
0x1800a862c  call    ??1?$CAutoHandle@PEAX@@QEAA@XZ; CAutoHandle<void *>::~CAutoHandle<void *>(void)
0x1800a8631  xor     edx, edx; Val
0x1800a8633  lea     rcx, [rbp+50h+WndClass]; void *
0x1800a8637  lea     r8d, [rdx+48h]; Size
0x1800a863b  call    memset_0
0x1800a8640  mov     rax, cs:__imp_DefWindowProcW
0x1800a8647  mov     edx, 7F00h; lpCursorName
0x1800a864c  mov     [rbp+50h+WndClass.lpfnWndProc], rax
0x1800a8650  xor     ecx, ecx; hInstance
0x1800a8652  lea     rax, __ImageBase
0x1800a8659  mov     [rbp+50h+WndClass.hInstance], rax
0x1800a865d  call    cs:__imp_LoadCursorW
0x1800a8663  cmp     byte ptr [rbx+3Ch], 0
0x1800a8667  lea     rcx, aShellDialog; "Shell_Dialog"
0x1800a866e  mov     [rbp+50h+WndClass.hCursor], rax
0x1800a8672  lea     r13, aShellHostingco_0; "Shell_HostingContainer"
0x1800a8679  mov     rax, r13
0x1800a867c  mov     [rbp+50h+WndClass.hbrBackground], 6
0x1800a8684  cmovz   rax, rcx
0x1800a8688  lea     rcx, [rbp+50h+WndClass]; lpWndClass
0x1800a868c  mov     [rbp+50h+WndClass.lpszClassName], rax
0x1800a8690  call    cs:__imp_RegisterClassW
0x1800a8696  mov     rcx, r14
0x1800a8699  call    cs:__imp_IsShellManagedWindow
0x1800a869f  test    eax, eax
0x1800a86a1  mov     r15, r14
0x1800a86a4  setnz   [rsp+150h+var_E0]
0x1800a86a9  xor     ecx, ecx
0x1800a86ab  mov     dword ptr [rsp+150h+var_D8], ecx
0x1800a86af  mov     [rbp+50h+var_D0], ecx
0x1800a86b2  test    eax, eax
0x1800a86b4  jz      short loc_1800A870B
0x1800a86b6  cmp     [rbx+20h], cl
0x1800a86b9  mov     rcx, r14; hwnd
0x1800a86bc  jz      short loc_1800A86E4
0x1800a86be  lea     rdx, [rbp+50h+var_D0]
0x1800a86c2  mov     dword ptr [rsp+150h+var_D8], 1
0x1800a86ca  xor     r15d, r15d
0x1800a86cd  call    cs:__imp_GetWindowBand
0x1800a86d3  mov     ecx, dword ptr [rsp+150h+var_D8]
0x1800a86d7  test    eax, eax
0x1800a86d9  jnz     short loc_1800A870B
0x1800a86db  mov     [rbp+50h+var_D0], 1
0x1800a86e2  jmp     short loc_1800A870B
0x1800a86e4  mov     edx, 1; gaFlags
0x1800a86e9  call    cs:__imp_GetAncestor
0x1800a86ef  mov     rcx, rax
0x1800a86f2  mov     rdi, rax
0x1800a86f5  call    cs:__imp_IsShellFrameWindow
0x1800a86fb  mov     ecx, dword ptr [rsp+150h+var_D8]
0x1800a86ff  test    eax, eax
0x1800a8701  jz      short loc_1800A870B
0x1800a8703  mov     r15, rdi
0x1800a8706  mov     [rsp+150h+var_E0], 0
0x1800a870b  test    r12d, r12d
0x1800a870e  jz      short loc_1800A8761
0x1800a8710  mov     rax, qword ptr [rbp+50h+Rect.left]
0x1800a8714  lea     r10, aShellDialog; "Shell_Dialog"
0x1800a871b  mov     r9d, [rbp+50h+var_C8]
0x1800a871f  xor     r12d, r12d
0x1800a8722  cmp     [rbx+3Ch], r12b
0x1800a8726  mov     r8, [rbp+50h+var_C0]
0x1800a872a  mov     [rsp+150h+var_120], rax
0x1800a872f  cmovz   r13, r10
0x1800a8733  mov     [rsp+150h+var_128], ecx
0x1800a8737  mov     rdx, r13
0x1800a873a  mov     ecx, [rbp+50h+var_CC]
0x1800a873d  mov     [rsp+150h+var_130], r15
0x1800a8742  call    Windows__Internal___anonymous_namespace___CDimmingWindow__CreateOnDesktop
0x1800a8747  lea     edx, [r12+4]; uCmd
0x1800a874c  mov     rcx, rax; hWnd
0x1800a874f  mov     rdi, rax
0x1800a8752  call    cs:__imp_GetWindow
0x1800a8758  mov     [rbx+30h], rax
0x1800a875c  jmp     loc_1800A888C
0x1800a8761  mov     ecx, esi
0x1800a8763  xor     r12d, r12d
0x1800a8766  and     ecx, 20000000h
0x1800a876c  mov     eax, 80000000h
0x1800a8771  cmp     [rbx+3Dh], r12b
0x1800a8775  jnz     short loc_1800A878E
0x1800a8777  bt      esi, 15h
0x1800a877b  jb      short loc_1800A878E
0x1800a877d  cmp     [rbx+3Ch], r12b
0x1800a8781  mov     eax, 80C00000h
0x1800a8786  mov     edx, 80C80000h
0x1800a878b  cmovnz  eax, edx
0x1800a878e  mov     edi, eax
0x1800a8790  mov     rsi, r12
0x1800a8793  or      edi, 0CA0000h
0x1800a8799  test    ecx, ecx
0x1800a879b  cmovz   edi, eax
0x1800a879e  call    cs:__imp_GetThreadDpiAwarenessContext
0x1800a87a4  mov     rcx, rax
0x1800a87a7  mov     rdx, 0FFFFFFFFFFFFFFFDh
0x1800a87ae  call    cs:__imp_AreDpiAwarenessContextsEqual
0x1800a87b4  test    eax, eax
0x1800a87b6  jz      short loc_1800A87C8
0x1800a87b8  mov     rcx, 0FFFFFFFFFFFFFFFCh
0x1800a87bf  call    cs:__imp_SetThreadDpiAwarenessContext
0x1800a87c5  mov     rsi, rax
0x1800a87c8  mov     ecx, 80000000h
0x1800a87cd  mov     r9d, ecx
0x1800a87d0  mov     edx, ecx
0x1800a87d2  mov     r8d, ecx
0x1800a87d5  test    r14, r14
0x1800a87d8  jz      short loc_1800A8807
0x1800a87da  cmp     [rbx+3Eh], r12b
0x1800a87de  jz      short loc_1800A8807
0x1800a87e0  xorps   xmm0, xmm0
0x1800a87e3  lea     rdx, [rbp+50h+Rect]; lpRect
0x1800a87e7  mov     rcx, r14; hWnd
0x1800a87ea  movups  xmmword ptr [rbp+50h+Rect.left], xmm0
0x1800a87ee  call    cs:__imp_GetWindowRect
0x1800a87f4  mov     edx, [rbp+50h+Rect.right]
0x1800a87f7  mov     ecx, [rbp+50h+Rect.left]
0x1800a87fa  sub     edx, ecx
0x1800a87fc  mov     r8d, [rbp+50h+Rect.bottom]
0x1800a8800  mov     r9d, [rbp+50h+Rect.top]
0x1800a8804  sub     r8d, r9d
0x1800a8807  mov     eax, [rbp+50h+var_D0]
0x1800a880a  lea     r10, aShellDialog; "Shell_Dialog"
0x1800a8811  cmp     [rbx+3Ch], r12b
0x1800a8815  cmovz   r13, r10
0x1800a8819  mov     r10d, dword ptr [rsp+150h+var_D8]
0x1800a881e  mov     [rsp+150h+var_E8], r10d
0x1800a8823  mov     [rsp+150h+var_F0], eax
0x1800a8827  lea     rax, __ImageBase
0x1800a882e  mov     [rsp+150h+var_F8], r12
0x1800a8833  mov     [rsp+150h+var_100], rax
0x1800a8838  mov     [rsp+150h+var_108], r12
0x1800a883d  mov     [rsp+150h+var_110], r15
0x1800a8842  mov     [rsp+150h+var_118], r8d
0x1800a8847  mov     r8, [rbp+50h+var_C0]
0x1800a884b  mov     dword ptr [rsp+150h+var_120], edx
0x1800a884f  mov     rdx, r13
0x1800a8852  mov     [rsp+150h+var_128], r9d
0x1800a8857  mov     r9d, edi
0x1800a885a  mov     dword ptr [rsp+150h+var_130], ecx
0x1800a885e  mov     ecx, [rbp+50h+var_CC]
0x1800a8861  call    cs:__imp_CreateWindowInBandEx
0x1800a8867  mov     rdi, rax
0x1800a886a  test    rsi, rsi
0x1800a886d  jz      short loc_1800A887C
0x1800a886f  mov     rcx, 0FFFFFFFFFFFFFFFDh
0x1800a8876  call    cs:__imp_SetThreadDpiAwarenessContext
0x1800a887c  cmp     [rbx+3Dh], r12b
0x1800a8880  jz      short loc_1800A888C
0x1800a8882  mov     dl, 1; bool
0x1800a8884  mov     rcx, rdi; HWND
0x1800a8887  call    ?_SetWindowVisualPolicy@DialogWindowTrait@Internal@Windows@@CAXPEAUHWND__@@_N@Z; Windows::Internal::DialogWindowTrait::_SetWindowVisualPolicy(HWND__ *,bool)
0x1800a888c  test    rdi, rdi
0x1800a888f  jz      loc_1800A8924
0x1800a8895  mov     [rbx+8], r15
0x1800a8899  cmp     [rsp+150h+var_E0], r12b
0x1800a889e  jz      short loc_1800A88E4
0x1800a88a0  cmp     [rbx+30h], r12
0x1800a88a4  mov     rsi, rdi
0x1800a88a7  mov     rcx, rbx; this
0x1800a88aa  cmovnz  rsi, [rbx+30h]
0x1800a88af  call    ?_EnsureBroker@DialogWindowTrait@Internal@Windows@@AEAAJXZ; Windows::Internal::DialogWindowTrait::_EnsureBroker(void)
0x1800a88b4  test    eax, eax
0x1800a88b6  js      short loc_1800A88E4
0x1800a88b8  mov     rcx, [rbx+28h]
0x1800a88bc  mov     r8, r14
0x1800a88bf  mov     rdx, rsi
0x1800a88c2  mov     rax, [rcx]
0x1800a88c5  mov     rax, [rax+18h]
0x1800a88c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a88ce  test    eax, eax
0x1800a88d0  js      short loc_1800A88E4
0x1800a88d2  mov     edx, 4; uCmd
0x1800a88d7  mov     rcx, rsi; hWnd
0x1800a88da  call    cs:__imp_GetWindow
0x1800a88e0  mov     [rbx+8], rax
0x1800a88e4  mov     r8d, 1; hData
0x1800a88ea  lea     rdx, aShellDialogWin; "Shell_Dialog_Window_Prop"
0x1800a88f1  mov     rcx, rdi; hWnd
0x1800a88f4  call    cs:__imp_SetPropW
0x1800a88fa  test    dword ptr [rbx+10h], 4000h
0x1800a8901  jz      short loc_1800A890D
0x1800a8903  mov     rdx, rdi; HWND
0x1800a8906  mov     cl, 1; bool
0x1800a8908  call    ?SetIhmRequireTouchInEditField@@YA_N_NPEAUHWND__@@@Z; SetIhmRequireTouchInEditField(bool,HWND__ *)
0x1800a890d  xor     r9d, r9d; lParam
0x1800a8910  mov     edx, 127h; Msg
0x1800a8915  mov     r8d, 30001h; wParam
0x1800a891b  mov     rcx, rdi; hWnd
0x1800a891e  call    cs:__imp_SendMessageW
0x1800a8924  mov     rax, rdi
0x1800a8927  mov     rcx, [rbp+50h+var_50]
0x1800a892b  xor     rcx, rsp; StackCookie
0x1800a892e  call    __security_check_cookie
0x1800a8933  add     rsp, 118h
0x1800a893a  pop     r15
0x1800a893c  pop     r14
0x1800a893e  pop     r13
0x1800a8940  pop     r12
0x1800a8942  pop     rdi
0x1800a8943  pop     rsi
0x1800a8944  pop     rbx
0x1800a8945  pop     rbp
0x1800a8946  retn
```
