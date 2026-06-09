# UXFrame::CreateFrameWindow(ulong,ulong,HWND__ *,tagRECT const &,ZBID)

- ea: `0x180040ba4`
- end: `0x180040cf3`
- name: `?CreateFrameWindow@UXFrame@@AEAAXKKPEAUHWND__@@AEBUtagRECT@@W4ZBID@@@Z`
- size: `335`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180040cfc`

## callees

- `0x180002b20`
- `0x180003cf6`
- `0x180017024`
- `0x180037eb4`
- `0x180040ba4`

## import_xrefs

- `USER32!SetPropW` at `0x180040c9d`
- `USER32!SetPropW` at `0x180040c9d`
- `USER32!RegisterClassW` at `0x180040c1f`
- `USER32!RegisterClassW` at `0x180040c1f`
- `USER32!CreateWindowInBand` at `0x180040c7d`
- `USER32!CreateWindowInBand` at `0x180040c7d`

## string_xrefs

- `0x180040cdb`: `pcshell\shell\uxframe\dll\UXFrame.cpp`

## pseudocode

```c
__int64 __fastcall UXFrame::CreateFrameWindow(__int64 a1, unsigned int a2, unsigned int a3, __int64 a4, int *a5)
{
  HWND WindowInBand; // rax
  int v10; // [rsp+20h] [rbp-A9h]
  __int64 v11; // [rsp+70h] [rbp-59h] BYREF
  WNDCLASSW WndClass; // [rsp+80h] [rbp-49h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+118h] [rbp+4Fh]

  memset_0(&WndClass, 0, sizeof(WndClass));
  WndClass.cbWndExtra = 8;
  WndClass.lpfnWndProc = (WNDPROC)UXFrame::s_WndProc;
  WndClass.hbrBackground = (HBRUSH)6;
  WndClass.hInstance = &_ImageBase;
  WndClass.lpszClassName = L"ShellUXFrameWindowClass";
  RegisterClassW(&WndClass);
  v10 = *a5;
  WindowInBand = (HWND)CreateWindowInBand(a3, WndClass.lpszClassName, &qword_18005F148, a2);
  *(_QWORD *)(a1 + 296) = WindowInBand;
  SetPropW(WindowInBand, L"Microsoft.Windows.ImmersiveZBIDWindowAsClassic", HANDLE_FLAG_INHERIT);
  if ( !*(_QWORD *)(a1 + 296) )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x40E,
      (unsigned int)"pcshell\\shell\\uxframe\\dll\\UXFrame.cpp",
      (const char *)0x8007000ELL,
      v10);
  v11 = a1;
  return UXFrameTelemetry::FrameWindowCreated<UXFrame *,HWND__ * &>(&v11, a1 + 296);
}

```

## disassembly

```asm
0x180040ba4  push    rbp
0x180040ba6  push    rbx
0x180040ba7  push    rsi
0x180040ba8  push    rdi
0x180040ba9  push    r13
0x180040bab  push    r14
0x180040bad  push    r15
0x180040baf  lea     rbp, [rsp-17h]
0x180040bb4  sub     rsp, 0E0h
0x180040bbb  mov     rax, cs:__security_cookie
0x180040bc2  xor     rax, rsp
0x180040bc5  mov     [rbp+47h+var_40], rax
0x180040bc9  mov     rdi, [rbp+47h+arg_20]
0x180040bcd  mov     r14d, edx
0x180040bd0  mov     ebx, [rbp+47h+arg_28]
0x180040bd3  xor     edx, edx; Val
0x180040bd5  mov     r15d, r8d
0x180040bd8  mov     r13, rcx
0x180040bdb  lea     rcx, [rbp+47h+WndClass]; void *
0x180040bdf  mov     rsi, r9
0x180040be2  lea     r8d, [rdx+48h]; Size
0x180040be6  call    memset_0
0x180040beb  lea     rax, ?s_WndProc@UXFrame@@CA_JPEAUHWND__@@I_K_J@Z; UXFrame::s_WndProc(HWND__ *,uint,unsigned __int64,__int64)
0x180040bf2  mov     [rbp+47h+WndClass.cbWndExtra], 8
0x180040bf9  mov     [rbp+47h+WndClass.lpfnWndProc], rax
0x180040bfd  lea     rcx, [rbp+47h+WndClass]; lpWndClass
0x180040c01  lea     rax, __ImageBase
0x180040c08  mov     [rbp+47h+WndClass.hbrBackground], 6
0x180040c10  mov     [rbp+47h+WndClass.hInstance], rax
0x180040c14  lea     rax, aShelluxframewi; "ShellUXFrameWindowClass"
0x180040c1b  mov     [rbp+47h+WndClass.lpszClassName], rax
0x180040c1f  call    cs:__imp_RegisterClassW
0x180040c25  mov     r8d, [rdi+0Ch]
0x180040c29  mov     r9d, r14d
0x180040c2c  mov     r10d, [rdi+4]
0x180040c30  mov     ecx, r15d
0x180040c33  mov     edx, [rdi+8]
0x180040c36  sub     r8d, r10d
0x180040c39  mov     r11d, [rdi]
0x180040c3c  sub     edx, r11d
0x180040c3f  mov     rax, [rbp+47h+WndClass.hInstance]
0x180040c43  mov     [rsp+110h+var_B0], ebx
0x180040c47  mov     [rsp+110h+var_B8], r13
0x180040c4c  mov     [rsp+110h+var_C0], rax
0x180040c51  mov     [rsp+110h+var_C8], 0
0x180040c5a  mov     [rsp+110h+var_D0], rsi
0x180040c5f  mov     [rsp+110h+var_D8], r8d
0x180040c64  lea     r8, qword_18005F148
0x180040c6b  mov     [rsp+110h+var_E0], edx
0x180040c6f  mov     rdx, [rbp+47h+WndClass.lpszClassName]
0x180040c73  mov     [rsp+110h+var_E8], r10d
0x180040c78  mov     [rsp+110h+var_F0], r11d; int
0x180040c7d  call    cs:__imp_CreateWindowInBand
0x180040c83  lea     rbx, [r13+128h]
0x180040c8a  mov     r8d, 1; hData
0x180040c90  mov     rcx, rax; hWnd
0x180040c93  mov     [rbx], rax
0x180040c96  lea     rdx, aMicrosoftWindo_0; "Microsoft.Windows.ImmersiveZBIDWindowAs"...
0x180040c9d  call    cs:__imp_SetPropW
0x180040ca3  cmp     qword ptr [rbx], 0
0x180040ca7  jz      short loc_180040CD7
0x180040ca9  mov     rdx, rbx
0x180040cac  mov     [rbp+47h+var_A0], r13
0x180040cb0  lea     rcx, [rbp+47h+var_A0]
0x180040cb4  call    ??$FrameWindowCreated@PEAVUXFrame@@AEAPEAUHWND__@@@UXFrameTelemetry@@SAX$$QEAPEAVUXFrame@@AEAPEAUHWND__@@@Z; UXFrameTelemetry::FrameWindowCreated<UXFrame *,HWND__ * &>(UXFrame * &&,HWND__ * &)
0x180040cb9  mov     rcx, [rbp+47h+var_40]
0x180040cbd  xor     rcx, rsp; StackCookie
0x180040cc0  call    __security_check_cookie
0x180040cc5  add     rsp, 0E0h
0x180040ccc  pop     r15
0x180040cce  pop     r14
0x180040cd0  pop     r13
0x180040cd2  pop     rdi
0x180040cd3  pop     rsi
0x180040cd4  pop     rbx
0x180040cd5  pop     rbp
0x180040cd6  retn
0x180040cd7  mov     rcx, [rbp+4Fh]; this
0x180040cdb  lea     r8, aPcshellShellUx_2; "pcshell\\shell\\uxframe\\dll\\UXFrame.c"...
0x180040ce2  mov     r9d, 8007000Eh; char *
0x180040ce8  mov     edx, 40Eh; void *
0x180040ced  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
