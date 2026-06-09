# CSearchServices::_EnsureForegroundStagingWindow(void)

- ea: `0x180011bf0`
- end: `0x180011d3d`
- name: `?_EnsureForegroundStagingWindow@CSearchServices@@AEAAJXZ`
- size: `333`
- prototype: `__int64 __fastcall(CSearchServices *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x1800121e4`

## callees

- `0x1800030b6`
- `0x180010fd0`
- `0x180011bf0`

## import_xrefs

- `USER32!CreateWindowInBand` at `0x180011ccd`
- `USER32!CreateWindowInBand` at `0x180011ccd`
- `USER32!ShowWindow` at `0x180011d24`
- `USER32!ShowWindow` at `0x180011d24`
- `USER32!RegisterClassExW` at `0x180011c69`
- `USER32!RegisterClassExW` at `0x180011c69`
- `dwmapi!DwmSetWindowAttribute` at `0x180011d12`
- `dwmapi!DwmSetWindowAttribute` at `0x180011d12`

## string_xrefs

- `0x180011c42`: `SearchServicesForegroundStagingWindow`

## pseudocode

```c
__int64 __fastcall CSearchServices::_EnsureForegroundStagingWindow(CSearchServices *this)
{
  int Error; // ebx
  __int64 WindowInBand; // rax
  HWND v4; // rcx
  WNDCLASSEXW v6; // [rsp+70h] [rbp-58h] BYREF
  int pvAttribute; // [rsp+D0h] [rbp+8h] BYREF

  Error = 0;
  if ( !*((_QWORD *)this + 38) )
  {
    v6.cbSize = 80;
    memset_0(&v6.style, 0, 0x4Cu);
    v6.style = 512;
    v6.lpfnWndProc = (WNDPROC)s_ForegroundStagingWndProc;
    v6.hInstance = (HINSTANCE)&_ImageBase;
    v6.lpszClassName = L"SearchServicesForegroundStagingWindow";
    v6.cbWndExtra = 8;
    RegisterClassExW(&v6);
    WindowInBand = CreateWindowInBand(136314880, v6.lpszClassName, 0, 0x80000000LL, 0, 0, 0, 0, 0, 0, &_ImageBase, 0, 7);
    *((_QWORD *)this + 38) = WindowInBand;
    if ( WindowInBand )
    {
      Error = 0;
LABEL_5:
      v4 = (HWND)*((_QWORD *)this + 38);
      pvAttribute = 1;
      DwmSetWindowAttribute(v4, 0xDu, &pvAttribute, 4u);
      ShowWindow(*((HWND *)this + 38), 4);
      return (unsigned int)Error;
    }
    Error = ResultFromKnownLastError();
    if ( Error >= 0 )
      goto LABEL_5;
  }
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x180011bf0  mov     [rsp+arg_8], rbx
0x180011bf5  push    rdi
0x180011bf6  sub     rsp, 0C0h
0x180011bfd  xor     ebx, ebx
0x180011bff  mov     rdi, rcx
0x180011c02  cmp     [rcx+130h], rbx
0x180011c09  jnz     loc_180011D2A
0x180011c0f  xor     edx, edx; Val
0x180011c11  mov     [rsp+0C8h+var_58.cbSize], 50h ; 'P'
0x180011c19  lea     r8d, [rbx+4Ch]; Size
0x180011c1d  lea     rcx, [rsp+0C8h+var_58.style]; void *
0x180011c22  call    memset_0
0x180011c27  lea     rax, ?s_ForegroundStagingWndProc@@YA_JPEAUHWND__@@I_K_J@Z; s_ForegroundStagingWndProc(HWND__ *,uint,unsigned __int64,__int64)
0x180011c2e  mov     [rsp+0C8h+var_58.style], 200h
0x180011c36  mov     [rsp+0C8h+var_58.lpfnWndProc], rax
0x180011c3b  lea     rbx, __ImageBase
0x180011c42  lea     rax, aSearchservices; "SearchServicesForegroundStagingWindow"
0x180011c49  mov     [rsp+0C8h+var_58.hInstance], rbx
0x180011c51  lea     rcx, [rsp+0C8h+var_58]; WNDCLASSEXW *
0x180011c56  mov     [rsp+0C8h+var_58.lpszClassName], rax
0x180011c5e  mov     [rsp+0C8h+var_58.cbWndExtra], 8
0x180011c69  call    cs:__imp_RegisterClassExW
0x180011c6f  mov     rdx, [rsp+0C8h+var_58.lpszClassName]
0x180011c77  mov     r9d, 80000000h
0x180011c7d  mov     [rsp+0C8h+var_68], 7
0x180011c85  xor     r8d, r8d
0x180011c88  mov     [rsp+0C8h+var_70], 0
0x180011c91  mov     ecx, 8200000h
0x180011c96  mov     [rsp+0C8h+var_78], rbx
0x180011c9b  mov     [rsp+0C8h+var_80], 0
0x180011ca4  mov     [rsp+0C8h+var_88], 0
0x180011cad  mov     [rsp+0C8h+var_90], 0
0x180011cb5  mov     [rsp+0C8h+var_98], 0
0x180011cbd  mov     [rsp+0C8h+var_A0], 0
0x180011cc5  mov     [rsp+0C8h+var_A8], 0
0x180011ccd  call    cs:__imp_CreateWindowInBand
0x180011cd3  mov     [rdi+130h], rax
0x180011cda  test    rax, rax
0x180011cdd  jz      short loc_180011CE3
0x180011cdf  xor     ebx, ebx
0x180011ce1  jmp     short loc_180011CEE
0x180011ce3  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180011ce8  mov     ebx, eax
0x180011cea  test    eax, eax
0x180011cec  js      short loc_180011D2A
0x180011cee  mov     rcx, [rdi+130h]; hwnd
0x180011cf5  lea     r8, [rsp+0C8h+pvAttribute]; pvAttribute
0x180011cfd  mov     r9d, 4; cbAttribute
0x180011d03  mov     [rsp+0C8h+pvAttribute], 1
0x180011d0e  lea     edx, [r9+9]; dwAttribute
0x180011d12  call    cs:__imp_DwmSetWindowAttribute
0x180011d18  mov     rcx, [rdi+130h]; hWnd
0x180011d1f  mov     edx, 4; nCmdShow
0x180011d24  call    cs:__imp_ShowWindow
0x180011d2a  mov     eax, ebx
0x180011d2c  mov     rbx, [rsp+0C8h+arg_8]
0x180011d34  add     rsp, 0C0h
0x180011d3b  pop     rdi
0x180011d3c  retn
```
