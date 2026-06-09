# CTouchSelectionHandle::GetPostWidth(void)

- ea: `0x1801fcc7c`
- end: `0x1801fcd35`
- name: `?GetPostWidth@CTouchSelectionHandle@@IEBAHXZ`
- size: `185`
- prototype: `__int64 __fastcall(CTouchSelectionHandle *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1801fc5b4`
- `0x1801fcf44`

## callees

- `0x18013bad0`
- `0x1801fad58`

## import_xrefs

- `ext-ms-win-gdi-dc-l1-2-0!SelectObject` at `0x1801fccca`
- `ext-ms-win-gdi-dc-l1-2-0!SelectObject` at `0x1801fccfa`
- `ext-ms-win-gdi-dc-l1-2-0!SelectObject` at `0x1801fccca`
- `ext-ms-win-gdi-dc-l1-2-0!SelectObject` at `0x1801fccfa`
- `ext-ms-win-gdi-font-l1-1-1!GetCharABCWidthsW` at `0x1801fccee`
- `ext-ms-win-gdi-font-l1-1-1!GetCharABCWidthsW` at `0x1801fccee`
- `ext-ms-win-rtcore-gdi-object-l1-1-0!DeleteObject` at `0x1801fcd03`
- `ext-ms-win-rtcore-gdi-object-l1-1-0!DeleteObject` at `0x1801fcd03`
- `ext-ms-win-rtcore-ntuser-dc-access-l1-1-0!GetDC` at `0x1801fccbb`
- `ext-ms-win-rtcore-ntuser-dc-access-l1-1-0!GetDC` at `0x1801fccbb`
- `ext-ms-win-rtcore-ntuser-dc-access-l1-1-0!ReleaseDC` at `0x1801fcd0e`
- `ext-ms-win-rtcore-ntuser-dc-access-l1-1-0!ReleaseDC` at `0x1801fcd0e`

## pseudocode

```c
__int64 __fastcall CTouchSelectionHandle::GetPostWidth(CTouchSelectionHandle *this)
{
  __int64 v1; // rdx
  HFONT v2; // rsi
  HDC DC; // rdi
  HGDIOBJ v4; // rbx
  int v6; // [rsp+20h] [rbp-28h] BYREF
  _ABC ABC; // [rsp+28h] [rbp-20h] BYREF

  v1 = *((_QWORD *)this + 16);
  v6 = 0;
  v2 = CTouchSelectionHandle::CreateGripperFont(this, *(_DWORD *)(v1 + 24), &v6);
  DC = GetDC(0);
  v4 = SelectObject(DC, v2);
  *(_QWORD *)&ABC.abcA = 0;
  ABC.abcC = 0;
  GetCharABCWidthsW(DC, 0xE2A2u, 0xE2A2u, &ABC);
  SelectObject(DC, v4);
  DeleteObject(v2);
  ReleaseDC(0, DC);
  return ABC.abcB;
}

```

## disassembly

```asm
0x1801fcc7c  mov     [rsp+arg_8], rbx
0x1801fcc81  mov     [rsp+arg_10], rsi
0x1801fcc86  push    rdi
0x1801fcc87  sub     rsp, 40h
0x1801fcc8b  mov     rax, cs:__security_cookie
0x1801fcc92  xor     rax, rsp
0x1801fcc95  mov     [rsp+48h+var_10], rax
0x1801fcc9a  mov     rdx, [rcx+80h]
0x1801fcca1  lea     r8, [rsp+48h+var_28]; int *
0x1801fcca6  mov     [rsp+48h+var_28], 0
0x1801fccae  mov     edx, [rdx+18h]; int
0x1801fccb1  call    ?CreateGripperFont@CTouchSelectionHandle@@IEBAPEAUHFONT__@@HPEAH@Z; CTouchSelectionHandle::CreateGripperFont(int,int *)
0x1801fccb6  xor     ecx, ecx; hWnd
0x1801fccb8  mov     rsi, rax
0x1801fccbb  call    cs:__imp_GetDC
0x1801fccc1  mov     rcx, rax; hdc
0x1801fccc4  mov     rdx, rsi; h
0x1801fccc7  mov     rdi, rax
0x1801fccca  call    cs:__imp_SelectObject
0x1801fccd0  mov     edx, 0E2A2h; wFirst
0x1801fccd5  lea     r9, [rsp+48h+ABC]; lpABC
0x1801fccda  mov     rbx, rax
0x1801fccdd  mov     r8d, edx; wLast
0x1801fcce0  xor     eax, eax
0x1801fcce2  mov     rcx, rdi; hdc
0x1801fcce5  mov     qword ptr [rsp+48h+ABC.abcA], rax
0x1801fccea  mov     [rsp+48h+ABC.abcC], eax
0x1801fccee  call    cs:__imp_GetCharABCWidthsW
0x1801fccf4  mov     rdx, rbx; h
0x1801fccf7  mov     rcx, rdi; hdc
0x1801fccfa  call    cs:__imp_SelectObject
0x1801fcd00  mov     rcx, rsi; ho
0x1801fcd03  call    cs:__imp_DeleteObject
0x1801fcd09  mov     rdx, rdi; hDC
0x1801fcd0c  xor     ecx, ecx; hWnd
0x1801fcd0e  call    cs:__imp_ReleaseDC
0x1801fcd14  mov     eax, [rsp+48h+ABC.abcB]
0x1801fcd18  mov     rcx, [rsp+48h+var_10]
0x1801fcd1d  xor     rcx, rsp; StackCookie
0x1801fcd20  call    __security_check_cookie
0x1801fcd25  mov     rbx, [rsp+48h+arg_8]
0x1801fcd2a  mov     rsi, [rsp+48h+arg_10]
0x1801fcd2f  add     rsp, 40h
0x1801fcd33  pop     rdi
0x1801fcd34  retn
```
