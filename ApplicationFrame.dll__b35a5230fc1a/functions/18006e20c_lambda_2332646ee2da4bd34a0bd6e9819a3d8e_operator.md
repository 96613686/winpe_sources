# _lambda_2332646ee2da4bd34a0bd6e9819a3d8e_::operator()

- ea: `0x18006e20c`
- end: `0x18006e3e0`
- name: `_lambda_2332646ee2da4bd34a0bd6e9819a3d8e_::operator()`
- size: `468`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x18006e110`

## callees

- `0x180030aec`
- `0x180043c30`
- `0x1800446fc`
- `0x18006e20c`
- `0x18006e648`
- `0x18006e6f0`

## import_xrefs

- `ext-ms-win-ntuser-window-l1-1-5!GetDpiForWindow` at `0x18006e2e9`
- `ext-ms-win-ntuser-window-l1-1-5!GetDpiForWindow` at `0x18006e2e9`
- `GDI32!GetCurrentObject` at `0x18006e24c`
- `GDI32!GetCurrentObject` at `0x18006e24c`
- `GDI32!CreateFontIndirectW` at `0x18006e35c`
- `GDI32!CreateFontIndirectW` at `0x18006e35c`
- `GDI32!GetObjectW` at `0x18006e27c`
- `GDI32!GetObjectW` at `0x18006e27c`
- `GDI32!SelectObject` at `0x18006e372`
- `GDI32!SelectObject` at `0x18006e3a7`
- `GDI32!SelectObject` at `0x18006e372`
- `GDI32!SelectObject` at `0x18006e3a7`
- `USER32!AreDpiAwarenessContextsEqual` at `0x18006e2dc`
- `USER32!AreDpiAwarenessContextsEqual` at `0x18006e2dc`
- `USER32!DrawTextExW` at `0x18006e34d`
- `USER32!DrawTextExW` at `0x18006e39b`
- `USER32!DrawTextExW` at `0x18006e34d`
- `USER32!DrawTextExW` at `0x18006e39b`
- `USER32!GetWindowDpiAwarenessContext` at `0x18006e2cc`
- `USER32!GetWindowDpiAwarenessContext` at `0x18006e2cc`
- `USER32!GetDpiForSystem` at `0x18006e2f1`
- `USER32!GetDpiForSystem` at `0x18006e2f1`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall lambda_2332646ee2da4bd34a0bd6e9819a3d8e_::operator()(
        int **a1,
        HDC a2,
        WCHAR *a3,
        int a4,
        struct tagRECT *lprc,
        UINT format)
{
  HGDIOBJ CurrentObject; // rdi
  int v11; // ecx
  int v12; // eax
  unsigned int *v13; // rdx
  __int64 v14; // rdi
  unsigned int v15; // ebp
  __int64 WindowDpiAwarenessContext; // rax
  unsigned int DpiForWindow; // eax
  __int64 v18; // rdx
  __int64 v19; // rcx
  int *v20; // r11
  int v21; // r10d
  HFONT FontIndirectW; // rax
  HGDIOBJ v23; // rbx
  HFONT v25; // [rsp+30h] [rbp-B8h] BYREF
  _DWORD pv[24]; // [rsp+40h] [rbp-A8h] BYREF

  CurrentObject = GetCurrentObject(a2, 6u);
  if ( !CurrentObject )
    return 1;
  memset_0(pv, 0, 0x5Cu);
  if ( GetObjectW(CurrentObject, 92, pv) <= 0 )
    return 1;
  v11 = **a1;
  if ( v11 == 1 )
  {
    v12 = DPIToPPIHelpers::ScaleByPPI((unsigned int)*a1[2], *(_QWORD *)a1[3], 1);
LABEL_13:
    *a1[1] = v12;
    goto LABEL_14;
  }
  if ( !v11 )
  {
    v13 = *(unsigned int **)a1[4];
    if ( v13 )
    {
      v18 = *v13;
      v19 = (unsigned int)*a1[2];
    }
    else
    {
      v14 = *(_QWORD *)a1[3];
      v15 = *a1[2];
      WindowDpiAwarenessContext = GetWindowDpiAwarenessContext(v14);
      if ( (unsigned int)AreDpiAwarenessContextsEqual(WindowDpiAwarenessContext, -4) )
        DpiForWindow = GetDpiForWindow(v14);
      else
        DpiForWindow = GetDpiForSystem();
      v18 = DpiForWindow;
      v19 = v15;
    }
    v12 = DPIToPPIHelpers::ScaleBySpecificDPI(v19, v18, 1);
    goto LABEL_13;
  }
LABEL_14:
  v20 = a1[2];
  v21 = *a1[1];
  if ( v21 == *v20 && v21 == pv[0] )
  {
    DrawTextExW(a2, a3, a4, lprc, format, 0);
  }
  else
  {
    *v20 = v21;
    FontIndirectW = CreateFontIndirectW((const LOGFONTW *)a1[2]);
    v25 = FontIndirectW;
    if ( FontIndirectW )
    {
      v23 = SelectObject(a2, FontIndirectW);
      DrawTextExW(a2, a3, a4, lprc, format, 0);
      SelectObject(a2, v23);
    }
    CAutoHandle<HBITMAP__ *>::~CAutoHandle<HBITMAP__ *>((void **)&v25);
  }
  return 1;
}

```

## disassembly

```asm
0x18006e20c  push    rbx
0x18006e20e  push    rbp
0x18006e20f  push    rsi
0x18006e210  push    rdi
0x18006e211  push    r12
0x18006e213  push    r14
0x18006e215  push    r15
0x18006e217  sub     rsp, 0B0h
0x18006e21e  mov     rax, cs:__security_cookie
0x18006e225  xor     rax, rsp
0x18006e228  mov     [rsp+0E8h+var_48], rax
0x18006e230  mov     r15d, r9d
0x18006e233  mov     r14, r8
0x18006e236  mov     rsi, rdx
0x18006e239  mov     rbx, rcx
0x18006e23c  mov     r12, [rsp+0E8h+lprc]
0x18006e244  mov     edx, 6; type
0x18006e249  mov     rcx, rsi; hdc
0x18006e24c  call    cs:__imp_GetCurrentObject
0x18006e252  mov     rdi, rax
0x18006e255  test    rax, rax
0x18006e258  jz      loc_18006E3B9
0x18006e25e  mov     ebp, 5Ch ; '\'
0x18006e263  mov     r8d, ebp; Size
0x18006e266  xor     edx, edx; Val
0x18006e268  lea     rcx, [rsp+0E8h+pv]; void *
0x18006e26d  call    memset_0
0x18006e272  lea     r8, [rsp+0E8h+pv]; pv
0x18006e277  mov     edx, ebp; c
0x18006e279  mov     rcx, rdi; h
0x18006e27c  call    cs:__imp_GetObjectW
0x18006e282  test    eax, eax
0x18006e284  jle     loc_18006E3B9
0x18006e28a  mov     rax, [rbx]
0x18006e28d  mov     ecx, [rax]
0x18006e28f  cmp     ecx, 1
0x18006e292  jnz     short loc_18006E2AC
0x18006e294  mov     rdx, [rbx+18h]
0x18006e298  mov     rcx, [rbx+10h]
0x18006e29c  lea     r8d, [rbp-5Bh]
0x18006e2a0  mov     rdx, [rdx]
0x18006e2a3  mov     ecx, [rcx]
0x18006e2a5  call    ?ScaleByPPI@DPIToPPIHelpers@@YAHHPEAUHWND__@@W4ScaleModifier@1@@Z; DPIToPPIHelpers::ScaleByPPI(int,HWND__ *,DPIToPPIHelpers::ScaleModifier)
0x18006e2aa  jmp     short loc_18006E310
0x18006e2ac  test    ecx, ecx
0x18006e2ae  jnz     short loc_18006E316
0x18006e2b0  mov     rax, [rbx+20h]
0x18006e2b4  mov     rdx, [rax]
0x18006e2b7  test    rdx, rdx
0x18006e2ba  jnz     short loc_18006E2FD
0x18006e2bc  mov     rax, [rbx+18h]
0x18006e2c0  mov     rdi, [rax]
0x18006e2c3  mov     rax, [rbx+10h]
0x18006e2c7  mov     ebp, [rax]
0x18006e2c9  mov     rcx, rdi
0x18006e2cc  call    cs:__imp_GetWindowDpiAwarenessContext
0x18006e2d2  mov     rcx, rax
0x18006e2d5  mov     rdx, 0FFFFFFFFFFFFFFFCh
0x18006e2dc  call    cs:__imp_AreDpiAwarenessContextsEqual
0x18006e2e2  test    eax, eax
0x18006e2e4  jz      short loc_18006E2F1
0x18006e2e6  mov     rcx, rdi
0x18006e2e9  call    cs:__imp_GetDpiForWindow
0x18006e2ef  jmp     short loc_18006E2F7
0x18006e2f1  call    cs:__imp_GetDpiForSystem
0x18006e2f7  mov     edx, eax
0x18006e2f9  mov     ecx, ebp
0x18006e2fb  jmp     short loc_18006E305
0x18006e2fd  mov     rcx, [rbx+10h]
0x18006e301  mov     edx, [rdx]
0x18006e303  mov     ecx, [rcx]
0x18006e305  mov     r8d, 1
0x18006e30b  call    ?ScaleBySpecificDPI@DPIToPPIHelpers@@YAHHHW4ScaleModifier@1@@Z; DPIToPPIHelpers::ScaleBySpecificDPI(int,int,DPIToPPIHelpers::ScaleModifier)
0x18006e310  mov     rcx, [rbx+8]
0x18006e314  mov     [rcx], eax
0x18006e316  mov     r11, [rbx+10h]
0x18006e31a  mov     rax, [rbx+8]
0x18006e31e  mov     r10d, [rax]
0x18006e321  cmp     r10d, [r11]
0x18006e324  jnz     short loc_18006E355
0x18006e326  cmp     r10d, [rsp+0E8h+pv]
0x18006e32b  jnz     short loc_18006E355
0x18006e32d  mov     [rsp+0E8h+lpdtp], 0; lpdtp
0x18006e336  mov     eax, [rsp+0E8h+arg_28]
0x18006e33d  mov     [rsp+0E8h+format], eax; format
0x18006e341  mov     r9, r12; lprc
0x18006e344  mov     r8d, r15d; cchText
0x18006e347  mov     rdx, r14; lpchText
0x18006e34a  mov     rcx, rsi; hdc
0x18006e34d  call    cs:__imp_DrawTextExW
0x18006e353  jmp     short loc_18006E3B9
0x18006e355  mov     [r11], r10d
0x18006e358  mov     rcx, [rbx+10h]; lplf
0x18006e35c  call    cs:__imp_CreateFontIndirectW
0x18006e362  mov     [rsp+0E8h+var_B8], rax
0x18006e367  test    rax, rax
0x18006e36a  jz      short loc_18006E3AE
0x18006e36c  mov     rdx, rax; h
0x18006e36f  mov     rcx, rsi; hdc
0x18006e372  call    cs:__imp_SelectObject
0x18006e378  mov     rbx, rax
0x18006e37b  mov     [rsp+0E8h+lpdtp], 0; lpdtp
0x18006e384  mov     ecx, [rsp+0E8h+arg_28]
0x18006e38b  mov     [rsp+0E8h+format], ecx; format
0x18006e38f  mov     r9, r12; lprc
0x18006e392  mov     r8d, r15d; cchText
0x18006e395  mov     rdx, r14; lpchText
0x18006e398  mov     rcx, rsi; hdc
0x18006e39b  call    cs:__imp_DrawTextExW
0x18006e3a1  mov     rdx, rbx; h
0x18006e3a4  mov     rcx, rsi; hdc
0x18006e3a7  call    cs:__imp_SelectObject
0x18006e3ad  nop
0x18006e3ae  lea     rcx, [rsp+0E8h+var_B8]
0x18006e3b3  call    ??1?$CAutoHandle@PEAUHBITMAP__@@@@QEAA@XZ; CAutoHandle<HBITMAP__ *>::~CAutoHandle<HBITMAP__ *>(void)
0x18006e3b8  nop
0x18006e3b9  mov     eax, 1
0x18006e3be  mov     rcx, [rsp+0E8h+var_48]
0x18006e3c6  xor     rcx, rsp; StackCookie
0x18006e3c9  call    __security_check_cookie
0x18006e3ce  add     rsp, 0B0h
0x18006e3d5  pop     r15
0x18006e3d7  pop     r14
0x18006e3d9  pop     r12
0x18006e3db  pop     rdi
0x18006e3dc  pop     rsi
0x18006e3dd  pop     rbp
0x18006e3de  pop     rbx
0x18006e3df  retn
```
