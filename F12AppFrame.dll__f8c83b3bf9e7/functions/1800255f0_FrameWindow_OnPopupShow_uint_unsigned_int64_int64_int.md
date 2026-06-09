# FrameWindow::OnPopupShow(uint,unsigned __int64,__int64,int &)

- ea: `0x1800255f0`
- end: `0x1800256b9`
- name: `?OnPopupShow@FrameWindow@@QEAA_JI_K_JAEAH@Z`
- size: `201`
- prototype: `__int64 __fastcall(FrameWindow *__hidden this, unsigned int, unsigned __int64, __int64, int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18002b910`

## callees

- `0x180020528`
- `0x1800255f0`

## import_xrefs

- `USER32!MoveWindow` at `0x180025657`
- `USER32!MoveWindow` at `0x180025657`
- `USER32!GetParent` at `0x180025625`
- `USER32!GetParent` at `0x180025625`
- `USER32!SetWindowPos` at `0x180025684`
- `USER32!SetWindowPos` at `0x180025684`
- `USER32!ShowWindow` at `0x18002569a`
- `USER32!ShowWindow` at `0x18002569a`
- `USER32!SetForegroundWindow` at `0x1800256a8`
- `USER32!SetForegroundWindow` at `0x1800256a8`

## pseudocode

```c
__int64 __fastcall FrameWindow::OnPopupShow(FrameWindow *this, __int64 a2, __int64 a3)
{
  HWND v5; // rbx
  HWND Parent; // rbp
  int v8; // [rsp+78h] [rbp+10h] BYREF

  v8 = 8;
  v5 = *(HWND *)(*(_QWORD *)std::map<enum PluginId,std::shared_ptr<BrowserToolThreadInfo>>::operator[](
                              (__int64 *)this + 56,
                              &v8)
               + 16LL);
  Parent = GetParent(v5);
  MoveWindow(
    Parent,
    *((_DWORD *)this + 173),
    *((_DWORD *)this + 174),
    *((_DWORD *)this + 175),
    *((_DWORD *)this + 176),
    1);
  SetWindowPos(v5, 0, 0, 0, *((_DWORD *)this + 175), *((_DWORD *)this + 176), 0x16u);
  ShowWindow(Parent, (a3 != 0) + 4);
  if ( a3 )
    SetForegroundWindow(Parent);
  return 0;
}

```

## disassembly

```asm
0x1800255f0  mov     [rsp+arg_8], edx
0x1800255f4  push    rbx
0x1800255f5  push    rbp
0x1800255f6  push    rsi
0x1800255f7  push    rdi
0x1800255f8  sub     rsp, 48h
0x1800255fc  mov     rdi, rcx
0x1800255ff  mov     [rsp+68h+arg_8], 8
0x180025607  add     rcx, 1C0h
0x18002560e  lea     rdx, [rsp+68h+arg_8]
0x180025613  mov     rsi, r8
0x180025616  call    ??A?$map@W4PluginId@@V?$shared_ptr@UBrowserToolThreadInfo@@@std@@U?$less@W4PluginId@@@3@V?$allocator@U?$pair@$$CBW4PluginId@@V?$shared_ptr@UBrowserToolThreadInfo@@@std@@@std@@@3@@std@@QEAAAEAV?$shared_ptr@UBrowserToolThreadInfo@@@1@AEBW4PluginId@@@Z; std::map<PluginId,std::shared_ptr<BrowserToolThreadInfo>>::operator[](PluginId const &)
0x18002561b  mov     rdx, [rax]
0x18002561e  mov     rbx, [rdx+10h]
0x180025622  mov     rcx, rbx; hWnd
0x180025625  call    cs:__imp_GetParent
0x18002562b  mov     edx, [rdi+2C0h]
0x180025631  mov     rcx, rax; hWnd
0x180025634  mov     r9d, [rdi+2BCh]; nWidth
0x18002563b  mov     rbp, rax
0x18002563e  mov     r8d, [rdi+2B8h]; Y
0x180025645  mov     [rsp+68h+bRepaint], 1; bRepaint
0x18002564d  mov     [rsp+68h+nHeight], edx; nHeight
0x180025651  mov     edx, [rdi+2B4h]; X
0x180025657  call    cs:__imp_MoveWindow
0x18002565d  mov     edx, [rdi+2C0h]
0x180025663  xor     r9d, r9d; Y
0x180025666  mov     [rsp+68h+uFlags], 16h; uFlags
0x18002566e  xor     r8d, r8d; X
0x180025671  mov     [rsp+68h+bRepaint], edx; cy
0x180025675  mov     rcx, rbx; hWnd
0x180025678  mov     edx, [rdi+2BCh]
0x18002567e  mov     [rsp+68h+nHeight], edx; cx
0x180025682  xor     edx, edx; hWndInsertAfter
0x180025684  call    cs:__imp_SetWindowPos
0x18002568a  mov     rax, rsi
0x18002568d  mov     rcx, rbp; hWnd
0x180025690  neg     rax
0x180025693  sbb     edx, edx
0x180025695  neg     edx
0x180025697  add     edx, 4; nCmdShow
0x18002569a  call    cs:__imp_ShowWindow
0x1800256a0  test    rsi, rsi
0x1800256a3  jz      short loc_1800256AE
0x1800256a5  mov     rcx, rbp; hWnd
0x1800256a8  call    cs:__imp_SetForegroundWindow
0x1800256ae  xor     eax, eax
0x1800256b0  add     rsp, 48h
0x1800256b4  pop     rdi
0x1800256b5  pop     rsi
0x1800256b6  pop     rbp
0x1800256b7  pop     rbx
0x1800256b8  retn
```
