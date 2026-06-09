# sub_18001CBFC

- ea: `0x18001cbfc`
- end: `0x18001cd29`
- name: `sub_18001CBFC`
- size: `301`
- prototype: `__int64 __fastcall(DWORD dwExStyle, LPCWSTR lpClassName, LPCWSTR lpWindowName, DWORD dwStyle, int, int, int, int, HWND, HMENU, HINSTANCE, ULONG_PTR ulCookie)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180024574`

## callees

- `0x180002558`
- `0x180002738`
- `0x18001cbfc`

## import_xrefs

- `KERNEL32!SetLastError` at `0x18001cd1a`
- `KERNEL32!SetLastError` at `0x1804c879e`
- `KERNEL32!SetLastError` at `0x18001cd1a`
- `KERNEL32!SetLastError` at `0x1804c879e`
- `KERNEL32!GetLastError` at `0x18001ccf9`
- `KERNEL32!GetLastError` at `0x1804c877e`
- `KERNEL32!GetLastError` at `0x18001ccf9`
- `KERNEL32!GetLastError` at `0x1804c877e`
- `USER32!CreateWindowExW` at `0x18001cccd`
- `USER32!CreateWindowExW` at `0x18001cccd`

## pseudocode

```c
HWND __fastcall sub_18001CBFC(
        DWORD dwExStyle,
        LPCWSTR lpClassName,
        LPCWSTR lpWindowName,
        DWORD dwStyle,
        int X,
        int Y,
        int nWidth,
        int nHeight,
        HWND hWndParent,
        HMENU hMenu,
        HINSTANCE hInstance,
        ULONG_PTR ulCookie)
{
  HWND Window; // rax
  HWND v18; // rsi
  BOOL v19; // ebx
  DWORD LastError; // edi

  ulCookie = 0;
  if ( !dword_1806FF1E8 && !dword_1806FF208 && !(unsigned int)sub_180002738(&ulCookie) )
    return 0;
  Window = CreateWindowExW(
             dwExStyle,
             lpClassName,
             lpWindowName,
             dwStyle,
             X,
             Y,
             nWidth,
             nHeight,
             hWndParent,
             hMenu,
             hInstance,
             0);
  v18 = Window;
  if ( !dword_1806FF1E8 || !dword_1806FF208 )
  {
    v19 = Window == 0;
    if ( Window )
      LastError = 0;
    else
      LastError = GetLastError();
    DeactivateActCtx(0, ulCookie);
    if ( v19 )
      SetLastError(LastError);
  }
  return v18;
}

```

## disassembly

```asm
0x18001cbfc  mov     rax, rsp
0x18001cbff  mov     [rax+8], rbx
0x18001cc03  mov     [rax+10h], rsi
0x18001cc07  mov     [rax+18h], rdi
0x18001cc0b  push    r14
0x18001cc0d  sub     rsp, 70h
0x18001cc11  mov     ebx, r9d
0x18001cc14  mov     rdi, r8
0x18001cc17  mov     rsi, rdx
0x18001cc1a  mov     r14d, ecx
0x18001cc1d  mov     qword ptr [rax-18h], 0
0x18001cc25  mov     qword ptr [rax+60h], 0
0x18001cc2d  cmp     cs:dword_1806FF1E8, 0
0x18001cc34  jnz     short loc_18001CC65
0x18001cc36  cmp     cs:dword_1806FF208, 0
0x18001cc3d  jnz     short loc_18001CC65
0x18001cc3f  lea     rcx, [rax+60h]; lpCookie
0x18001cc43  call    sub_180002738
0x18001cc48  test    eax, eax
0x18001cc4a  jnz     short loc_18001CC65
0x18001cc4c  xor     eax, eax
0x18001cc4e  lea     r11, [rsp+78h+var_8]
0x18001cc53  mov     rbx, [r11+10h]
0x18001cc57  mov     rsi, [r11+18h]
0x18001cc5b  mov     rdi, [r11+20h]
0x18001cc5f  mov     rsp, r11
0x18001cc62  pop     r14
0x18001cc64  retn
0x18001cc65  mov     [rsp+78h+lpParam], 0; lpParam
0x18001cc6e  mov     rax, [rsp+78h+arg_50]
0x18001cc76  mov     [rsp+78h+hInstance], rax; hInstance
0x18001cc7b  mov     rax, [rsp+78h+arg_48]
0x18001cc83  mov     [rsp+78h+hMenu], rax; hMenu
0x18001cc88  mov     rax, [rsp+78h+arg_40]
0x18001cc90  mov     [rsp+78h+hWndParent], rax; hWndParent
0x18001cc95  mov     eax, [rsp+78h+arg_38]
0x18001cc9c  mov     [rsp+78h+nHeight], eax; nHeight
0x18001cca0  mov     eax, [rsp+78h+arg_30]
0x18001cca7  mov     [rsp+78h+nWidth], eax; nWidth
0x18001ccab  mov     eax, [rsp+78h+arg_28]
0x18001ccb2  mov     [rsp+78h+Y], eax; Y
0x18001ccb6  mov     eax, [rsp+78h+arg_20]
0x18001ccbd  mov     [rsp+78h+X], eax; X
0x18001ccc1  mov     r9d, ebx; dwStyle
0x18001ccc4  mov     r8, rdi; lpWindowName
0x18001ccc7  mov     rdx, rsi; lpClassName
0x18001ccca  mov     ecx, r14d; dwExStyle
0x18001cccd  call    cs:CreateWindowExW
0x18001ccd3  mov     rsi, rax
0x18001ccd6  mov     [rsp+78h+var_18], rax
0x18001ccdb  cmp     cs:dword_1806FF1E8, 0
0x18001cce2  jz      short loc_18001CCED
0x18001cce4  cmp     cs:dword_1806FF208, 0
0x18001cceb  jnz     short loc_18001CD20
0x18001cced  xor     ebx, ebx
0x18001ccef  test    rsi, rsi
0x18001ccf2  setz    bl
0x18001ccf5  test    ebx, ebx
0x18001ccf7  jz      short loc_18001CD03
0x18001ccf9  call    cs:GetLastError
0x18001ccff  mov     edi, eax
0x18001cd01  jmp     short loc_18001CD05
0x18001cd03  xor     edi, edi
0x18001cd05  mov     rdx, [rsp+78h+ulCookie]; ulCookie
0x18001cd0d  xor     ecx, ecx; dwFlags
0x18001cd0f  call    DeactivateActCtx
0x18001cd14  test    ebx, ebx
0x18001cd16  jz      short loc_18001CD20
0x18001cd18  mov     ecx, edi; dwErrCode
0x18001cd1a  call    cs:SetLastError
0x18001cd20  mov     rax, rsi
0x18001cd23  jmp     loc_18001CC4E
0x1804c8754  push    rbx
0x1804c8756  push    rbp
0x1804c8757  push    rdi
0x1804c8758  sub     rsp, 60h
0x1804c875c  mov     rbp, rdx
0x1804c875f  cmp     cs:dword_1806FF1E8, 0
0x1804c8766  jz      short loc_1804C8771
0x1804c8768  cmp     cs:dword_1806FF208, 0
0x1804c876f  jnz     short loc_1804C87A5
0x1804c8771  xor     ebx, ebx
0x1804c8773  cmp     [rbp+60h], rbx
0x1804c8777  setz    bl
0x1804c877a  test    ebx, ebx
0x1804c877c  jz      short loc_1804C8788
0x1804c877e  call    cs:GetLastError
0x1804c8784  mov     edi, eax
0x1804c8786  jmp     short loc_1804C878A
0x1804c8788  xor     edi, edi
0x1804c878a  mov     rdx, [rbp+0D8h]; ulCookie
0x1804c8791  xor     ecx, ecx; dwFlags
0x1804c8793  call    DeactivateActCtx
0x1804c8798  test    ebx, ebx
0x1804c879a  jz      short loc_1804C87A5
0x1804c879c  mov     ecx, edi; dwErrCode
0x1804c879e  call    cs:SetLastError
0x1804c87a4  nop
0x1804c87a5  add     rsp, 60h
0x1804c87a9  pop     rdi
0x1804c87aa  pop     rbp
0x1804c87ab  pop     rbx
0x1804c87ac  retn
```
