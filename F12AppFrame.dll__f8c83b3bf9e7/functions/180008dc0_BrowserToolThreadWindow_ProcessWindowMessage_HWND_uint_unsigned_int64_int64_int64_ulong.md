# BrowserToolThreadWindow::ProcessWindowMessage(HWND__ *,uint,unsigned __int64,__int64,__int64 &,ulong)

- ea: `0x180008dc0`
- end: `0x180008ef6`
- name: `?ProcessWindowMessage@BrowserToolThreadWindow@@UEAAHPEAUHWND__@@I_K_JAEA_JK@Z`
- size: `310`
- prototype: `__int64 __fastcall(BrowserToolThreadWindow *__hidden this, HWND, unsigned int, unsigned __int64, struct PluginMessageInfo *, BrowserToolThreadWindow *, unsigned int)`
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting`

## callees

- `0x180008520`
- `0x18000869c`
- `0x180008990`
- `0x180008dc0`
- `0x180035010`

## import_xrefs

- `USER32!IsWindow` at `0x180008ea2`
- `USER32!IsWindow` at `0x180008ea2`
- `USER32!DestroyWindow` at `0x180008eb4`
- `USER32!DestroyWindow` at `0x180008eb4`
- `USER32!PostQuitMessage` at `0x180008ebe`
- `USER32!PostQuitMessage` at `0x180008ebe`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_BOOL8 __fastcall BrowserToolThreadWindow::ProcessWindowMessage(
        HWND *this,
        __int64 a2,
        unsigned __int64 a3,
        __int64 a4,
        struct PluginMessageInfo *a5,
        BrowserToolThreadWindow *a6,
        unsigned int a7)
{
  __int64 BrowserTool; // rax
  __int64 v10; // rcx
  HWND v11; // rcx
  int *v12; // [rsp+20h] [rbp-28h]

  if ( a7 )
    return 0;
  switch ( (_DWORD)a3 )
  {
    case 0x798:
      BrowserTool = BrowserToolThreadWindow::OnCreateBrowserTool(this, a2, a3, (__int64 *)a5);
LABEL_4:
      *(_QWORD *)a6 = BrowserTool;
      return 1;
    case 0x58B:
      BrowserTool = BrowserToolThreadWindow::OnTapMessage((BrowserToolThreadWindow *)this, a2, a3, (__int64)a5, v12);
      goto LABEL_4;
    case 0x79B:
      if ( (unsigned int)BrowserToolThreadWindow::ProcessPluginMessage((BrowserToolThreadWindow *)this, a5) )
      {
        if ( a5 )
          (**(void (__fastcall ***)(struct PluginMessageInfo *, __int64))a5)(a5, 1);
        v10 = -1;
      }
      else
      {
        if ( a5 )
          (**(void (__fastcall ***)(struct PluginMessageInfo *, __int64))a5)(a5, 1);
        v10 = 0;
      }
      *(_QWORD *)a6 = v10;
      return 1;
  }
  if ( (_DWORD)a3 != 130 )
    return 0;
  *((_DWORD *)this[6] + 13) = 1;
  *((_BYTE *)this + 136) = 1;
  v11 = this[13];
  if ( v11 && IsWindow(*((HWND *)v11 + 1)) )
    DestroyWindow(*((HWND *)this[13] + 1));
  else
    PostQuitMessage(0);
  *((_DWORD *)this[6] + 13) = 0;
  *(_QWORD *)a6 = 0;
  return *((_DWORD *)this[6] + 13) != 0;
}

```

## disassembly

```asm
0x180008dc0  mov     [rsp+arg_0], rbx
0x180008dc5  push    rdi
0x180008dc6  sub     rsp, 40h
0x180008dca  mov     rbx, rcx
0x180008dcd  cmp     [rsp+48h+arg_30], 0
0x180008dd5  jnz     loc_180008EE9
0x180008ddb  cmp     r8d, 798h
0x180008de2  jnz     short loc_180008E00
0x180008de4  mov     r9, [rsp+48h+arg_20]; __int64
0x180008de9  call    ?OnCreateBrowserTool@BrowserToolThreadWindow@@QEAA_JI_K_JAEAH@Z; BrowserToolThreadWindow::OnCreateBrowserTool(uint,unsigned __int64,__int64,int &)
0x180008dee  mov     rcx, [rsp+48h+arg_28]; this
0x180008df3  mov     [rcx], rax
0x180008df6  mov     eax, 1
0x180008dfb  jmp     loc_180008EEB
0x180008e00  cmp     r8d, 58Bh
0x180008e07  jnz     short loc_180008E15
0x180008e09  mov     r9, [rsp+48h+arg_20]; __int64
0x180008e0e  call    ?OnTapMessage@BrowserToolThreadWindow@@QEAA_JI_K_JAEAH@Z; BrowserToolThreadWindow::OnTapMessage(uint,unsigned __int64,__int64,int &)
0x180008e13  jmp     short loc_180008DEE
0x180008e15  cmp     r8d, 79Bh
0x180008e1c  jnz     short loc_180008E7A
0x180008e1e  mov     rdi, [rsp+48h+arg_20]
0x180008e23  mov     [rsp+48h+var_18], rdi
0x180008e28  mov     rdx, rdi; struct PluginMessageInfo *
0x180008e2b  call    ?ProcessPluginMessage@BrowserToolThreadWindow@@AEAAJPEBUPluginMessageInfo@@@Z; BrowserToolThreadWindow::ProcessPluginMessage(PluginMessageInfo const *)
0x180008e30  nop
0x180008e31  test    eax, eax
0x180008e33  jz      short loc_180008E53
0x180008e35  test    rdi, rdi
0x180008e38  jz      short loc_180008E4D
0x180008e3a  mov     rax, [rdi]
0x180008e3d  mov     edx, 1
0x180008e42  mov     rcx, rdi
0x180008e45  mov     rax, [rax]
0x180008e48  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008e4d  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180008e51  jmp     short loc_180008E6D
0x180008e53  test    rdi, rdi
0x180008e56  jz      short loc_180008E6B
0x180008e58  mov     rax, [rdi]
0x180008e5b  mov     edx, 1
0x180008e60  mov     rcx, rdi
0x180008e63  mov     rax, [rax]
0x180008e66  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008e6b  xor     ecx, ecx
0x180008e6d  mov     rax, [rsp+48h+arg_28]
0x180008e72  mov     [rax], rcx
0x180008e75  jmp     loc_180008DF6
0x180008e7a  cmp     r8d, 82h
0x180008e81  jnz     short loc_180008EE9
0x180008e83  mov     rax, [rcx+30h]
0x180008e87  mov     dword ptr [rax+34h], 1
0x180008e8e  mov     byte ptr [rcx+88h], 1
0x180008e95  mov     rcx, [rcx+68h]
0x180008e99  test    rcx, rcx
0x180008e9c  jz      short loc_180008EBC
0x180008e9e  mov     rcx, [rcx+8]; hWnd
0x180008ea2  call    cs:__imp_IsWindow
0x180008ea8  test    eax, eax
0x180008eaa  jz      short loc_180008EBC
0x180008eac  mov     rcx, [rbx+68h]
0x180008eb0  mov     rcx, [rcx+8]; hWnd
0x180008eb4  call    cs:__imp_DestroyWindow
0x180008eba  jmp     short loc_180008EC4
0x180008ebc  xor     ecx, ecx; nExitCode
0x180008ebe  call    cs:__imp_PostQuitMessage
0x180008ec4  mov     rax, [rbx+30h]
0x180008ec8  mov     dword ptr [rax+34h], 0
0x180008ecf  mov     rax, [rsp+48h+arg_28]
0x180008ed4  mov     qword ptr [rax], 0
0x180008edb  mov     rcx, [rbx+30h]
0x180008edf  xor     eax, eax
0x180008ee1  cmp     [rcx+34h], eax
0x180008ee4  setnz   al
0x180008ee7  jmp     short loc_180008EEB
0x180008ee9  xor     eax, eax
0x180008eeb  mov     rbx, [rsp+48h+arg_0]
0x180008ef0  add     rsp, 40h
0x180008ef4  pop     rdi
0x180008ef5  retn
```
