# CSyncBasePropertyPage::SetItemIcon(HWND__ *,IShellItem *)

- ea: `0x18004c098`
- end: `0x18004c17c`
- name: `?SetItemIcon@CSyncBasePropertyPage@@IEAAXPEAUHWND__@@PEAUIShellItem@@@Z`
- size: `228`
- prototype: `void(CSyncBasePropertyPage *__hidden this, HWND, struct IShellItem *)`
- caller_count: `3`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18003c780`
- `0x18003d5d0`
- `0x18003e270`

## callees

- `0x180012e54`
- `0x1800133b0`
- `0x1800134dc`
- `0x18004c098`
- `0x180052950`
- `0x180053010`

## import_xrefs

- `USER32!SendMessageW` at `0x18004c148`
- `USER32!SendMessageW` at `0x18004c148`
- `USER32!GetWindowRect` at `0x18004c0ed`
- `USER32!GetWindowRect` at `0x18004c0ed`
- `GDI32!DeleteObject` at `0x18004c156`
- `GDI32!DeleteObject` at `0x18004c156`

## pseudocode

```c
void __fastcall CSyncBasePropertyPage::SetItemIcon(CSyncBasePropertyPage *this, HWND a2, struct IShellItem *a3)
{
  int (__fastcall ***v4)(__int64, GUID *, __int64 *); // r8
  __int64 v5; // r9
  void *v6; // rax
  __int64 v7; // [rsp+30h] [rbp-30h] BYREF
  __int64 v8; // [rsp+38h] [rbp-28h]
  LPARAM lParam; // [rsp+40h] [rbp-20h] BYREF
  struct tagRECT Rect; // [rsp+48h] [rbp-18h] BYREF

  ATL::CComPtr<IDefaultExtractIconInit>::CComPtr<IDefaultExtractIconInit>(&v7);
  if ( (**v4)(v5, &GUID_bcc18b79_ba16_442f_80c4_8a59c30c463b, &v7) >= 0 )
  {
    Rect = 0;
    if ( GetWindowRect(a2, &Rect) || (int)ResultFromKnownLastError() >= 0 )
    {
      LODWORD(v8) = Rect.right - Rect.left;
      HIDWORD(v8) = Rect.bottom - Rect.top;
      lParam = 0;
      if ( (*(int (__fastcall **)(__int64, __int64, _QWORD, LPARAM *))(*(_QWORD *)v7 + 24LL))(v7, v8, 0, &lParam) >= 0 )
      {
        v6 = (void *)SendMessageW(a2, 0x172u, 0, lParam);
        if ( v6 )
          DeleteObject(v6);
      }
    }
  }
  ATL::CComPtr<IDefaultExtractIconInit>::~CComPtr<IDefaultExtractIconInit>((__int64)&v7);
}

```

## disassembly

```asm
0x18004c098  mov     [rsp-8+arg_0], rbx
0x18004c09d  push    rbp
0x18004c09e  mov     rbp, rsp
0x18004c0a1  sub     rsp, 60h
0x18004c0a5  mov     rax, cs:__security_cookie
0x18004c0ac  xor     rax, rsp
0x18004c0af  mov     [rbp+var_8], rax
0x18004c0b3  lea     rcx, [rbp+var_30]; void *
0x18004c0b7  mov     r9, r8
0x18004c0ba  mov     rbx, rdx
0x18004c0bd  call    ??0?$CComPtr@UIDefaultExtractIconInit@@@ATL@@QEAA@XZ; ATL::CComPtr<IDefaultExtractIconInit>::CComPtr<IDefaultExtractIconInit>(void)
0x18004c0c2  mov     rcx, [r8]
0x18004c0c5  lea     rdx, _GUID_bcc18b79_ba16_442f_80c4_8a59c30c463b
0x18004c0cc  lea     r8, [rbp+var_30]
0x18004c0d0  mov     rax, [rcx]
0x18004c0d3  mov     rcx, r9
0x18004c0d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c0db  test    eax, eax
0x18004c0dd  js      short loc_18004C15C
0x18004c0df  xorps   xmm0, xmm0
0x18004c0e2  lea     rdx, [rbp+Rect]; lpRect
0x18004c0e6  mov     rcx, rbx; hWnd
0x18004c0e9  movups  xmmword ptr [rbp+Rect.left], xmm0
0x18004c0ed  call    cs:__imp_GetWindowRect
0x18004c0f3  test    eax, eax
0x18004c0f5  jnz     short loc_18004C100
0x18004c0f7  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18004c0fc  test    eax, eax
0x18004c0fe  js      short loc_18004C15C
0x18004c100  mov     eax, [rbp+Rect.right]
0x18004c103  lea     r9, [rbp+lParam]
0x18004c107  sub     eax, [rbp+Rect.left]
0x18004c10a  xor     r8d, r8d
0x18004c10d  mov     rcx, [rbp+var_30]
0x18004c111  mov     dword ptr [rbp+var_28], eax
0x18004c114  mov     eax, [rbp+Rect.bottom]
0x18004c117  sub     eax, [rbp+Rect.top]
0x18004c11a  mov     dword ptr [rbp+var_28+4], eax
0x18004c11d  mov     rdx, [rbp+var_28]
0x18004c121  mov     [rbp+lParam], 0
0x18004c129  mov     rax, [rcx]
0x18004c12c  mov     rax, [rax+18h]
0x18004c130  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c135  test    eax, eax
0x18004c137  js      short loc_18004C15C
0x18004c139  mov     r9, [rbp+lParam]; lParam
0x18004c13d  xor     r8d, r8d; wParam
0x18004c140  mov     edx, 172h; Msg
0x18004c145  mov     rcx, rbx; hWnd
0x18004c148  call    cs:__imp_SendMessageW
0x18004c14e  test    rax, rax
0x18004c151  jz      short loc_18004C15C
0x18004c153  mov     rcx, rax; ho
0x18004c156  call    cs:__imp_DeleteObject
0x18004c15c  lea     rcx, [rbp+var_30]
0x18004c160  call    ??1?$CComPtr@UIDefaultExtractIconInit@@@ATL@@QEAA@XZ; ATL::CComPtr<IDefaultExtractIconInit>::~CComPtr<IDefaultExtractIconInit>(void)
0x18004c165  mov     rcx, [rbp+var_8]
0x18004c169  xor     rcx, rsp; StackCookie
0x18004c16c  call    __security_check_cookie
0x18004c171  mov     rbx, [rsp+60h+arg_0]
0x18004c176  add     rsp, 60h
0x18004c17a  pop     rbp
0x18004c17b  retn
```
