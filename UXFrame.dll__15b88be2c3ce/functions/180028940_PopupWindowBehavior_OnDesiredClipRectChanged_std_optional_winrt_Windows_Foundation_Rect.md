# PopupWindowBehavior::OnDesiredClipRectChanged(std::optional<winrt::Windows::Foundation::Rect>)

- ea: `0x180028940`
- end: `0x180028a32`
- name: `?OnDesiredClipRectChanged@PopupWindowBehavior@@UEAAXV?$optional@URect@Foundation@Windows@winrt@@@std@@@Z`
- size: `242`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config`

## callees

- `0x180002ae8`
- `0x180002b20`
- `0x180021eb0`
- `0x180028940`

## import_xrefs

- `USER32!SetWindowRgn` at `0x1800289e1`
- `USER32!SetWindowRgn` at `0x180028a0a`
- `USER32!SetWindowRgn` at `0x1800289e1`
- `USER32!SetWindowRgn` at `0x180028a0a`
- `GDI32!CreateRectRgnIndirect` at `0x1800289cb`
- `GDI32!CreateRectRgnIndirect` at `0x1800289cb`

## pseudocode

```c
int __fastcall PopupWindowBehavior::OnDesiredClipRectChanged(__int64 a1, __int64 a2)
{
  HRGN v3; // rbx
  HRGN v5; // [rsp+20h] [rbp-48h] BYREF
  RECT rect; // [rsp+28h] [rbp-40h] BYREF

  if ( !*(_BYTE *)(a2 + 16) )
    return SetWindowRgn(*(HWND *)(a1 + 40), 0, 1);
  rect.left = (int)o_roundf_0();
  rect.top = (int)o_roundf_0();
  rect.right = (int)o_roundf_0();
  rect.bottom = (int)o_roundf_0();
  v3 = CreateRectRgnIndirect(&rect);
  if ( SetWindowRgn(*(HWND *)(a1 + 40), v3, 1) )
    v3 = 0;
  v5 = v3;
  return wil::details::unique_storage<wil::details::resource_policy<HRGN__ *,int (*)(void *),&int DeleteObject(void *),wistd::integral_constant<unsigned __int64,0>,HRGN__ *,HRGN__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HRGN__ *,int (*)(void *),&int DeleteObject(void *),wistd::integral_constant<unsigned __int64,0>,HRGN__ *,HRGN__ *,0,std::nullptr_t>>((void **)&v5);
}

```

## disassembly

```asm
0x180028940  mov     [rsp+arg_8], rbx
0x180028945  push    rdi
0x180028946  sub     rsp, 60h
0x18002894a  movaps  [rsp+68h+var_18], xmm6
0x18002894f  movaps  [rsp+68h+var_28], xmm7
0x180028954  mov     rax, cs:__security_cookie
0x18002895b  xor     rax, rsp
0x18002895e  mov     [rsp+68h+var_30], rax
0x180028963  cmp     byte ptr [rdx+10h], 0
0x180028967  mov     rbx, rdx
0x18002896a  mov     rdi, rcx
0x18002896d  jz      loc_180028A00
0x180028973  movss   xmm6, dword ptr [rdx]
0x180028977  movaps  xmm0, xmm6
0x18002897a  call    _o_roundf_0
0x18002897f  movss   xmm7, dword ptr [rbx+4]
0x180028984  cvttss2si eax, xmm0
0x180028988  movaps  xmm0, xmm7
0x18002898b  mov     [rsp+68h+rect.left], eax
0x18002898f  call    _o_roundf_0
0x180028994  addss   xmm6, dword ptr [rbx+8]
0x180028999  cvttss2si eax, xmm0
0x18002899d  movaps  xmm0, xmm6
0x1800289a0  mov     [rsp+68h+rect.top], eax
0x1800289a4  call    _o_roundf_0
0x1800289a9  addss   xmm7, dword ptr [rbx+0Ch]
0x1800289ae  cvttss2si eax, xmm0
0x1800289b2  movaps  xmm0, xmm7
0x1800289b5  mov     [rsp+68h+rect.right], eax
0x1800289b9  call    _o_roundf_0
0x1800289be  cvttss2si eax, xmm0
0x1800289c2  lea     rcx, [rsp+68h+rect]; lprect
0x1800289c7  mov     [rsp+68h+rect.bottom], eax
0x1800289cb  call    cs:__imp_CreateRectRgnIndirect
0x1800289d1  mov     rcx, [rdi+28h]; hWnd
0x1800289d5  mov     r8d, 1; bRedraw
0x1800289db  mov     rdx, rax; hRgn
0x1800289de  mov     rbx, rax
0x1800289e1  call    cs:__imp_SetWindowRgn
0x1800289e7  xor     ecx, ecx
0x1800289e9  test    eax, eax
0x1800289eb  cmovnz  rbx, rcx
0x1800289ef  lea     rcx, [rsp+68h+var_48]
0x1800289f4  mov     [rsp+68h+var_48], rbx
0x1800289f9  call    ??1?$unique_storage@U?$resource_policy@PEAUHRGN__@@P6AHPEAX@Z$1?DeleteObject@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HRGN__ *,int (*)(void *),&DeleteObject(void *),wistd::integral_constant<unsigned __int64,0>,HRGN__ *,HRGN__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HRGN__ *,int (*)(void *),&DeleteObject(void *),wistd::integral_constant<unsigned __int64,0>,HRGN__ *,HRGN__ *,0,std::nullptr_t>>(void)
0x1800289fe  jmp     short loc_180028A10
0x180028a00  mov     rcx, [rcx+28h]; hWnd
0x180028a04  xor     edx, edx; hRgn
0x180028a06  lea     r8d, [rdx+1]; bRedraw
0x180028a0a  call    cs:__imp_SetWindowRgn
0x180028a10  mov     rcx, [rsp+68h+var_30]
0x180028a15  xor     rcx, rsp; StackCookie
0x180028a18  call    __security_check_cookie
0x180028a1d  mov     rbx, [rsp+68h+arg_8]
0x180028a22  movaps  xmm6, [rsp+68h+var_18]
0x180028a27  movaps  xmm7, [rsp+68h+var_28]
0x180028a2c  add     rsp, 60h
0x180028a30  pop     rdi
0x180028a31  retn
```
