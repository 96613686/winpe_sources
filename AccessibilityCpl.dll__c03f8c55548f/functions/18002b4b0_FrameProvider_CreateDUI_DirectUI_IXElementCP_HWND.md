# FrameProvider::CreateDUI(DirectUI::IXElementCP *,HWND__ * *)

- ea: `0x18002b4b0`
- end: `0x18002b516`
- name: `?CreateDUI@FrameProvider@@UEAAJPEAVIXElementCP@DirectUI@@PEAPEAUHWND__@@@Z`
- size: `102`
- prototype: `__int64 __fastcall(FrameProvider *__hidden this, struct DirectUI::IXElementCP *, HWND *)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x18002a084`
- `0x18002a0f4`
- `0x18002b4b0`

## import_xrefs

- `DUI70!?SetHandleEnterKey@XProvider@DirectUI@@IEAAX_N@Z` at `0x18002b4f4`
- `DUI70!?SetHandleEnterKey@XProvider@DirectUI@@IEAAX_N@Z` at `0x18002b4f4`
- `DUI70!?CreateDUI@XProvider@DirectUI@@UEAAJPEAVIXElementCP@2@PEAPEAUHWND__@@@Z` at `0x18002b4e3`
- `DUI70!?CreateDUI@XProvider@DirectUI@@UEAAJPEAVIXElementCP@2@PEAPEAUHWND__@@@Z` at `0x18002b4e3`

## pseudocode

```c
__int64 __fastcall FrameProvider::CreateDUI(FrameProvider *this, struct DirectUI::IXElementCP *a2, HWND *a3)
{
  int DUI; // ebx
  ULONG_PTR ulCookie; // [rsp+48h] [rbp+20h] BYREF

  ulCookie = 0;
  SHActivateContext(&ulCookie);
  DUI = DirectUI::XProvider::CreateDUI(this, a2, a3);
  if ( DUI >= 0 )
    DirectUI::XProvider::SetHandleEnterKey(this, 1);
  SHDeactivateContext(ulCookie);
  return (unsigned int)DUI;
}

```

## disassembly

```asm
0x18002b4b0  mov     rax, rsp
0x18002b4b3  mov     [rax+8], rbx
0x18002b4b7  mov     [rax+10h], rsi
0x18002b4bb  push    rdi
0x18002b4bc  sub     rsp, 20h
0x18002b4c0  mov     rsi, rcx
0x18002b4c3  mov     qword ptr [rax+20h], 0
0x18002b4cb  lea     rcx, [rax+20h]
0x18002b4cf  mov     rbx, r8
0x18002b4d2  mov     rdi, rdx
0x18002b4d5  call    SHActivateContext
0x18002b4da  mov     r8, rbx
0x18002b4dd  mov     rdx, rdi
0x18002b4e0  mov     rcx, rsi
0x18002b4e3  call    cs:__imp_?CreateDUI@XProvider@DirectUI@@UEAAJPEAVIXElementCP@2@PEAPEAUHWND__@@@Z; DirectUI::XProvider::CreateDUI(DirectUI::IXElementCP *,HWND__ * *)
0x18002b4e9  mov     ebx, eax
0x18002b4eb  test    eax, eax
0x18002b4ed  js      short loc_18002B4FA
0x18002b4ef  mov     dl, 1
0x18002b4f1  mov     rcx, rsi
0x18002b4f4  call    cs:__imp_?SetHandleEnterKey@XProvider@DirectUI@@IEAAX_N@Z; DirectUI::XProvider::SetHandleEnterKey(bool)
0x18002b4fa  mov     rcx, [rsp+28h+ulCookie]; ulCookie
0x18002b4ff  call    SHDeactivateContext
0x18002b504  mov     rsi, [rsp+28h+arg_8]
0x18002b509  mov     eax, ebx
0x18002b50b  mov     rbx, [rsp+28h+arg_0]
0x18002b510  add     rsp, 20h
0x18002b514  pop     rdi
0x18002b515  retn
```
