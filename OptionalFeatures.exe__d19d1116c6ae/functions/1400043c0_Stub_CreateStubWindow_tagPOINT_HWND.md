# Stub_CreateStubWindow(tagPOINT,HWND__ *)

- ea: `0x1400043c0`
- end: `0x140004567`
- name: `?Stub_CreateStubWindow@@YAPEAUHWND__@@UtagPOINT@@PEAU1@@Z`
- size: `423`
- prototype: `HWND __fastcall(struct tagPOINT X, HWND)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140004958`

## callees

- `0x14000187f`
- `0x1400043c0`

## import_xrefs

- `KERNEL32!GetUserDefaultUILanguage` at `0x140004458`
- `KERNEL32!GetUserDefaultUILanguage` at `0x140004458`
- `KERNEL32!GetLocaleInfoW` at `0x14000447e`
- `KERNEL32!GetLocaleInfoW` at `0x14000447e`
- `KERNEL32!GetLastError` at `0x1400044f8`
- `KERNEL32!GetLastError` at `0x1400044f8`
- `GDI32!GetStockObject` at `0x14000441d`
- `GDI32!GetStockObject` at `0x14000441d`
- `USER32!LoadCursorW` at `0x140004411`
- `USER32!LoadCursorW` at `0x140004411`
- `USER32!RegisterClassW` at `0x140004441`
- `USER32!RegisterClassW` at `0x140004441`
- `USER32!CreateWindowExW` at `0x1400044ea`
- `USER32!CreateWindowExW` at `0x14000453f`
- `USER32!CreateWindowExW` at `0x1400044ea`
- `USER32!CreateWindowExW` at `0x14000453f`

## pseudocode

```c
HWND __fastcall Stub_CreateStubWindow(struct tagPOINT X, HWND a2)
{
  LONG v2; // ebx
  int v3; // eax
  __int32 v4; // edi
  LANGID UserDefaultUILanguage; // ax
  DWORD v6; // esi
  HWND Window; // rdi
  WNDCLASSW WndClass; // [rsp+68h] [rbp-19h] BYREF
  LONG Y; // [rsp+ECh] [rbp+6Bh]
  HWND LCData; // [rsp+F0h] [rbp+6Fh] BYREF

  LCData = a2;
  Y = X.y;
  v2 = X.x;
  memset_0(&WndClass, 0, sizeof(WndClass));
  WndClass.cbWndExtra = 8;
  WndClass.lpfnWndProc = (WNDPROC)StubWndProc;
  WndClass.hCursor = LoadCursorW(0, (LPCWSTR)0x7F00);
  WndClass.hbrBackground = (HBRUSH)GetStockObject(0);
  WndClass.lpszClassName = L"StubWindow32";
  WndClass.hInstance = (HINSTANCE)0x140000000LL;
  RegisterClassW(&WndClass);
  v3 = `IsBiDiLocalizedSystemEx'::`2'::s_tbBiDi;
  if ( `IsBiDiLocalizedSystemEx'::`2'::s_tbBiDi == -1 )
  {
    v4 = 0;
    UserDefaultUILanguage = GetUserDefaultUILanguage();
    `IsBiDiLocalizedSystemEx'::`2'::s_langID = UserDefaultUILanguage;
    if ( UserDefaultUILanguage )
    {
      LODWORD(LCData) = 0;
      if ( GetLocaleInfoW(UserDefaultUILanguage, 0x20000070u, (LPWSTR)&LCData, 2) > 0 )
        LOBYTE(v4) = (_DWORD)LCData == 1;
    }
    _InterlockedExchange(&`IsBiDiLocalizedSystemEx'::`2'::s_tbBiDi, v4);
    v3 = `IsBiDiLocalizedSystemEx'::`2'::s_tbBiDi;
  }
  v6 = 0x40000;
  if ( v3 == 1 )
    v6 = 4456448;
  Window = CreateWindowExW(v6, L"StubWindow32", &WindowName, 0, v2, Y, 0, 0, 0, 0, WndClass.hInstance, 0);
  if ( !Window && GetLastError() == 1400 )
    return CreateWindowExW(v6, L"StubWindow32", &WindowName, 0, v2, Y, 0, 0, 0, 0, WndClass.hInstance, 0);
  return Window;
}

```

## disassembly

```asm
0x1400043c0  mov     rax, rsp
0x1400043c3  mov     [rax+18h], rbx
0x1400043c7  mov     [rax+20h], rsi
0x1400043cb  mov     [rax+10h], rdx
0x1400043cf  mov     [rax+8], rcx
0x1400043d3  push    rbp
0x1400043d4  push    rdi
0x1400043d5  push    r12
0x1400043d7  push    r14
0x1400043d9  push    r15
0x1400043db  lea     rbp, [rax-5Fh]
0x1400043df  sub     rsp, 0B0h
0x1400043e6  xor     edx, edx; Val
0x1400043e8  mov     rbx, rcx
0x1400043eb  lea     rcx, [rbp+57h+WndClass]; void *
0x1400043ef  lea     r8d, [rdx+48h]; Size
0x1400043f3  call    memset_0
0x1400043f8  lea     rax, ?StubWndProc@@YA_JPEAUHWND__@@I_K_J@Z; StubWndProc(HWND__ *,uint,unsigned __int64,__int64)
0x1400043ff  mov     [rbp+57h+WndClass.cbWndExtra], 8
0x140004406  mov     edx, 7F00h; lpCursorName
0x14000440b  mov     [rbp+57h+WndClass.lpfnWndProc], rax
0x14000440f  xor     ecx, ecx; hInstance
0x140004411  call    cs:__imp_LoadCursorW
0x140004417  xor     ecx, ecx; i
0x140004419  mov     [rbp+57h+WndClass.hCursor], rax
0x14000441d  call    cs:__imp_GetStockObject
0x140004423  mov     [rbp+57h+WndClass.hbrBackground], rax
0x140004427  lea     r12, ClassName; "StubWindow32"
0x14000442e  lea     rax, cs:140000000h
0x140004435  mov     [rbp+57h+WndClass.lpszClassName], r12
0x140004439  lea     rcx, [rbp+57h+WndClass]; lpWndClass
0x14000443d  mov     [rbp+57h+WndClass.hInstance], rax
0x140004441  call    cs:__imp_RegisterClassW
0x140004447  mov     eax, cs:?s_tbBiDi@?1??IsBiDiLocalizedSystemEx@@YAHPEAG@Z@4JA; long `IsBiDiLocalizedSystemEx(ushort *)'::`2'::s_tbBiDi
0x14000444d  xor     r15d, r15d
0x140004450  cmp     eax, 0FFFFFFFFh
0x140004453  jnz     short loc_14000449C
0x140004455  mov     edi, r15d
0x140004458  call    cs:__imp_GetUserDefaultUILanguage
0x14000445e  mov     cs:?s_langID@?1??IsBiDiLocalizedSystemEx@@YAHPEAG@Z@4GA, ax; ushort `IsBiDiLocalizedSystemEx(ushort *)'::`2'::s_langID
0x140004465  test    ax, ax
0x140004468  jz      short loc_140004490
0x14000446a  movzx   ecx, ax; Locale
0x14000446d  lea     r9d, [r15+2]; cchData
0x140004471  lea     r8, [rbp+57h+LCData]; lpLCData
0x140004475  mov     dword ptr [rbp+57h+LCData], r15d
0x140004479  mov     edx, 20000070h; LCType
0x14000447e  call    cs:__imp_GetLocaleInfoW
0x140004484  test    eax, eax
0x140004486  jle     short loc_140004490
0x140004488  cmp     dword ptr [rbp+57h+LCData], 1
0x14000448c  setz    dil
0x140004490  xchg    edi, cs:?s_tbBiDi@?1??IsBiDiLocalizedSystemEx@@YAHPEAG@Z@4JA; long `IsBiDiLocalizedSystemEx(ushort *)'::`2'::s_tbBiDi
0x140004496  mov     eax, cs:?s_tbBiDi@?1??IsBiDiLocalizedSystemEx@@YAHPEAG@Z@4JA; long `IsBiDiLocalizedSystemEx(ushort *)'::`2'::s_tbBiDi
0x14000449c  mov     r14d, [rbp+57h+arg_4]
0x1400044a0  lea     r8, WindowName; lpWindowName
0x1400044a7  mov     [rsp+0D0h+lpParam], r15; lpParam
0x1400044ac  cmp     eax, 1
0x1400044af  mov     rax, [rbp+57h+WndClass.hInstance]
0x1400044b3  mov     ecx, 440000h
0x1400044b8  mov     [rsp+0D0h+hInstance], rax; hInstance
0x1400044bd  mov     esi, 40000h
0x1400044c2  mov     [rsp+0D0h+hMenu], r15; hMenu
0x1400044c7  cmovz   esi, ecx
0x1400044ca  mov     [rsp+0D0h+hWndParent], r15; hWndParent
0x1400044cf  xor     r9d, r9d; dwStyle
0x1400044d2  mov     [rsp+0D0h+nHeight], r15d; nHeight
0x1400044d7  mov     rdx, r12; lpClassName
0x1400044da  mov     [rsp+0D0h+nWidth], r15d; nWidth
0x1400044df  mov     ecx, esi; dwExStyle
0x1400044e1  mov     [rsp+0D0h+Y], r14d; Y
0x1400044e6  mov     [rsp+0D0h+X], ebx; X
0x1400044ea  call    cs:__imp_CreateWindowExW
0x1400044f0  mov     rdi, rax
0x1400044f3  test    rax, rax
0x1400044f6  jnz     short loc_140004548
0x1400044f8  call    cs:__imp_GetLastError
0x1400044fe  cmp     eax, 578h
0x140004503  jnz     short loc_140004548
0x140004505  mov     rax, [rbp+57h+WndClass.hInstance]
0x140004509  lea     r8, WindowName; lpWindowName
0x140004510  mov     [rsp+0D0h+lpParam], r15; lpParam
0x140004515  xor     r9d, r9d; dwStyle
0x140004518  mov     [rsp+0D0h+hInstance], rax; hInstance
0x14000451d  mov     rdx, r12; lpClassName
0x140004520  mov     [rsp+0D0h+hMenu], r15; hMenu
0x140004525  mov     ecx, esi; dwExStyle
0x140004527  mov     [rsp+0D0h+hWndParent], r15; hWndParent
0x14000452c  mov     [rsp+0D0h+nHeight], r15d; nHeight
0x140004531  mov     [rsp+0D0h+nWidth], r15d; nWidth
0x140004536  mov     [rsp+0D0h+Y], r14d; Y
0x14000453b  mov     [rsp+0D0h+X], ebx; X
0x14000453f  call    cs:__imp_CreateWindowExW
0x140004545  mov     rdi, rax
0x140004548  lea     r11, [rsp+0D0h+var_20]
0x140004550  mov     rax, rdi
0x140004553  mov     rbx, [r11+40h]
0x140004557  mov     rsi, [r11+48h]
0x14000455b  mov     rsp, r11
0x14000455e  pop     r15
0x140004560  pop     r14
0x140004562  pop     r12
0x140004564  pop     rdi
0x140004565  pop     rbp
0x140004566  retn
```
