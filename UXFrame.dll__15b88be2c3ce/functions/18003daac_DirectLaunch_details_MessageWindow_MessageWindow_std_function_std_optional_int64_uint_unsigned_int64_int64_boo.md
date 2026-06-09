# DirectLaunch::details::MessageWindow::MessageWindow(std::function<std::optional<__int64> (uint,unsigned __int64,__int64)> &&,bool)

- ea: `0x18003daac`
- end: `0x18003dbfb`
- name: `??0MessageWindow@details@DirectLaunch@@QEAA@$$QEAV?$function@$$A6A?AV?$optional@_J@std@@I_K_J@Z@std@@_N@Z`
- size: `335`
- prototype: `__int64 __fastcall(LONG_PTR dwNewLong)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18003d8bc`

## callees

- `0x180002b20`
- `0x180003cf6`
- `0x180017008`
- `0x18003daac`
- `0x18004e5c0`
- `0x18004fc40`

## import_xrefs

- `USER32!CreateWindowExW` at `0x18003db89`
- `USER32!CreateWindowExW` at `0x18003db89`
- `USER32!SetWindowLongPtrW` at `0x18003dbcc`
- `USER32!SetWindowLongPtrW` at `0x18003dbcc`
- `USER32!RegisterClassExW` at `0x18003db38`
- `USER32!RegisterClassExW` at `0x18003db38`

## string_xrefs

- `0x18003dbaf`: `OnecoreUAP\Internal\Shell\Inc\SrcPkg\DirectLaunch\inc\DirectLaunchCommon.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
LONG_PTR __fastcall DirectLaunch::details::MessageWindow::MessageWindow(LONG_PTR dwNewLong)
{
  HWND Window; // rax
  WNDCLASSEXW v4; // [rsp+70h] [rbp-68h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+0h]

  *(_QWORD *)dwNewLong = 0;
  *(_QWORD *)(dwNewLong + 64) = 0;
  std::_Func_class<void,winrt::Windows::Foundation::Collections::ValueSet const &,std::wstring const &>::_Reset_move();
  memset_0(&v4, 0, sizeof(v4));
  v4.cbSize = 80;
  v4.lpfnWndProc = (WNDPROC)DirectLaunch::details::MessageWindow::MessageWndProc;
  v4.hInstance = &_ImageBase;
  v4.lpszClassName = L"MessageWindowClass";
  RegisterClassExW(&v4);
  Window = CreateWindowExW(0, L"MessageWindowClass", 0, 0, 0, 0, 0, 0, HWND_MESSAGE, 0, &_ImageBase, 0);
  wil::details::unique_storage<wil::details::resource_policy<HWND__ *,int (*)(HWND__ *),&int DestroyWindow(HWND__ *),wistd::integral_constant<unsigned __int64,0>,HWND__ *,HWND__ *,0,std::nullptr_t>>::reset(
    dwNewLong,
    Window);
  if ( !*(_QWORD *)dwNewLong )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x55,
      (unsigned int)"OnecoreUAP\\Internal\\Shell\\Inc\\SrcPkg\\DirectLaunch\\inc\\DirectLaunchCommon.h",
      (const char *)retaddr);
  SetWindowLongPtrW(*(HWND *)dwNewLong, -21, dwNewLong);
  return dwNewLong;
}

```

## disassembly

```asm
0x18003daac  mov     [rsp+arg_10], rbx
0x18003dab1  mov     [rsp+arg_18], rsi
0x18003dab6  push    rdi
0x18003dab7  sub     rsp, 0D0h
0x18003dabe  mov     rax, cs:__security_cookie
0x18003dac5  xor     rax, rsp
0x18003dac8  mov     [rsp+0D8h+var_18], rax
0x18003dad0  mov     rbx, rcx
0x18003dad3  mov     [rsp+0D8h+var_78], rcx
0x18003dad8  mov     qword ptr [rcx], 0
0x18003dadf  add     rcx, 8
0x18003dae3  mov     qword ptr [rcx+38h], 0
0x18003daeb  call    ?_Reset_move@?$_Func_class@XAEBUValueSet@Collections@Foundation@Windows@winrt@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@IEAAX$$QEAV12@@Z; std::_Func_class<void,winrt::Windows::Foundation::Collections::ValueSet const &,std::wstring const &>::_Reset_move(std::_Func_class<void,winrt::Windows::Foundation::Collections::ValueSet const &,std::wstring const &> &&)
0x18003daf0  nop
0x18003daf1  mov     edi, 50h ; 'P'
0x18003daf6  mov     r8d, edi; Size
0x18003daf9  xor     edx, edx; Val
0x18003dafb  lea     rcx, [rsp+0D8h+var_68]; void *
0x18003db00  call    memset_0
0x18003db05  mov     [rsp+0D8h+var_68.cbSize], edi
0x18003db09  lea     rax, ?MessageWndProc@MessageWindow@details@DirectLaunch@@CA_JPEAUHWND__@@I_K_J@Z; DirectLaunch::details::MessageWindow::MessageWndProc(HWND__ *,uint,unsigned __int64,__int64)
0x18003db10  mov     [rsp+0D8h+var_68.lpfnWndProc], rax
0x18003db15  lea     rdi, __ImageBase
0x18003db1c  mov     [rsp+0D8h+var_68.hInstance], rdi
0x18003db24  lea     rsi, ClassName; "MessageWindowClass"
0x18003db2b  mov     [rsp+0D8h+var_68.lpszClassName], rsi
0x18003db33  lea     rcx, [rsp+0D8h+var_68]; WNDCLASSEXW *
0x18003db38  call    cs:__imp_RegisterClassExW
0x18003db3e  mov     [rsp+0D8h+lpParam], 0; lpParam
0x18003db47  mov     [rsp+0D8h+hInstance], rdi; hInstance
0x18003db4c  mov     [rsp+0D8h+hMenu], 0; hMenu
0x18003db55  mov     [rsp+0D8h+hWndParent], 0FFFFFFFFFFFFFFFDh; hWndParent
0x18003db5e  mov     [rsp+0D8h+nHeight], 0; nHeight
0x18003db66  mov     [rsp+0D8h+nWidth], 0; nWidth
0x18003db6e  mov     [rsp+0D8h+Y], 0; Y
0x18003db76  mov     [rsp+0D8h+X], 0; X
0x18003db7e  xor     r9d, r9d; dwStyle
0x18003db81  xor     r8d, r8d; lpWindowName
0x18003db84  mov     rdx, rsi; lpClassName
0x18003db87  xor     ecx, ecx; dwExStyle
0x18003db89  call    cs:__imp_CreateWindowExW
0x18003db8f  mov     rdx, rax
0x18003db92  mov     rcx, rbx
0x18003db95  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHWND__@@P6AHPEAU1@@Z$1?DestroyWindow@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHWND__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HWND__ *,int (*)(HWND__ *),&DestroyWindow(HWND__ *),wistd::integral_constant<unsigned __int64,0>,HWND__ *,HWND__ *,0,std::nullptr_t>>::reset(HWND__ *)
0x18003db9a  mov     rcx, [rbx]; hWnd
0x18003db9d  test    rcx, rcx
0x18003dba0  setz    al
0x18003dba3  mov     r9, [rsp+0D8h]; char *
0x18003dbab  test    al, al
0x18003dbad  jz      short loc_18003DBC4
0x18003dbaf  lea     r8, aOnecoreuapInte; "OnecoreUAP\\Internal\\Shell\\Inc\\SrcPk"...
0x18003dbb6  mov     edx, 55h ; 'U'; void *
0x18003dbbb  mov     rcx, r9; this
0x18003dbbe  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x18003dbc4  mov     r8, rbx; dwNewLong
0x18003dbc7  mov     edx, 0FFFFFFEBh; nIndex
0x18003dbcc  call    cs:__imp_SetWindowLongPtrW
0x18003dbd2  nop
0x18003dbd3  mov     rax, rbx
0x18003dbd6  mov     rcx, [rsp+0D8h+var_18]
0x18003dbde  xor     rcx, rsp; StackCookie
0x18003dbe1  call    __security_check_cookie
0x18003dbe6  lea     r11, [rsp+0D8h+var_8]
0x18003dbee  mov     rbx, [r11+20h]
0x18003dbf2  mov     rsi, [r11+28h]
0x18003dbf6  mov     rsp, r11
0x18003dbf9  pop     rdi
0x18003dbfa  retn
```
