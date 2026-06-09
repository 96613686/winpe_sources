# BrowserToolWindow::DocumentComplete(IHTMLWindow2 *,IUri *)

- ea: `0x18000cd70`
- end: `0x18000cf42`
- name: `?DocumentComplete@BrowserToolWindow@@UEAAJPEAUIHTMLWindow2@@PEAUIUri@@@Z`
- size: `466`
- prototype: `__int64 __fastcall(BrowserToolWindow *__hidden this, struct IHTMLWindow2 *, struct IUri *)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x18000cd70`
- `0x18000e800`
- `0x180010dac`
- `0x180032aa4`
- `0x180035010`

## import_xrefs

- `GDI32!GetDeviceCaps` at `0x18000ce95`
- `GDI32!GetDeviceCaps` at `0x18000ce95`
- `OLEAUT32!__imp_SysFreeString` at `0x18000cf23`
- `OLEAUT32!__imp_SysFreeString` at `0x18000cf23`
- `USER32!ReleaseDC` at `0x18000ce65`
- `USER32!ReleaseDC` at `0x18000cec6`
- `USER32!ReleaseDC` at `0x18000ceff`
- `USER32!ReleaseDC` at `0x18000ce65`
- `USER32!ReleaseDC` at `0x18000cec6`
- `USER32!ReleaseDC` at `0x18000ceff`
- `USER32!GetDC` at `0x18000ce53`
- `USER32!GetDC` at `0x18000ce53`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall BrowserToolWindow::DocumentComplete(
        BrowserToolWindow *this,
        struct IHTMLWindow2 *a2,
        struct IUri *a3)
{
  int v5; // ebx
  void (__fastcall ***v6)(_QWORD, GUID *, __int64 *); // r9
  __int64 v7; // rcx
  HDC DC; // rax
  HDC v9; // rbx
  double v10; // xmm0_8
  int v11; // edx
  __int64 v13; // [rsp+38h] [rbp+10h] BYREF
  wchar_t *String1; // [rsp+48h] [rbp+20h] BYREF

  if ( a2 && a3 )
  {
    String1 = 0;
    v5 = ((__int64 (__fastcall *)(struct IUri *, wchar_t **))a3->lpVtbl->GetRawUri)(a3, &String1);
    if ( v5 )
    {
      if ( v5 >= 0 )
        v5 = -2147467259;
      goto LABEL_28;
    }
    if ( wcscmp_0(String1, L"about:internet")
      && (unsigned __int8)ATL::CComPtrBase<IHTMLWindow2>::IsEqualObject((char *)this + 80, a2) )
    {
      *((_BYTE *)this + 128) = 1;
      v6 = (void (__fastcall ***)(_QWORD, GUID *, __int64 *))*((_QWORD *)this + 12);
      v7 = 0;
      v13 = 0;
      if ( v6 )
      {
        (**v6)(v6, &GUID_c2704fa0_2f26_45a6_9e28_4136ff3fb583, &v13);
        v7 = v13;
      }
      if ( v7 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 48LL))(v7);
        v7 = v13;
      }
      if ( !*((_DWORD *)this + 33) )
      {
        DC = GetDC(0);
        v9 = DC;
        if ( !DC )
        {
          ReleaseDC(0, 0);
          if ( v13 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
LABEL_17:
          v5 = -2147467259;
LABEL_28:
          SysFreeString(String1);
          return (unsigned int)v5;
        }
        v10 = (double)GetDeviceCaps(DC, 88) / 96.0 * 100.0;
        *((_DWORD *)this + 33) = (int)v10;
        if ( !(int)v10 )
        {
          ReleaseDC(0, v9);
          if ( v13 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
          goto LABEL_17;
        }
        v11 = *((_DWORD *)this + 34);
        if ( v11 != 100 )
          BrowserToolWindow::SetCurrentZoomLevel((BrowserToolWindow *)((char *)this - 72), v11);
        ReleaseDC(0, v9);
        v7 = v13;
      }
      if ( v7 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
    }
    v5 = 0;
    goto LABEL_28;
  }
  return 2147942487LL;
}

```

## disassembly

```asm
0x18000cd70  mov     r11, rsp
0x18000cd73  mov     [r11+8], rbx
0x18000cd77  mov     [r11+18h], rsi
0x18000cd7b  push    rdi
0x18000cd7c  sub     rsp, 20h
0x18000cd80  mov     rsi, rdx
0x18000cd83  mov     rdi, rcx
0x18000cd86  test    rdx, rdx
0x18000cd89  jz      loc_18000CF2D
0x18000cd8f  test    r8, r8
0x18000cd92  jz      loc_18000CF2D
0x18000cd98  mov     qword ptr [r11+20h], 0
0x18000cda0  mov     rax, [r8]
0x18000cda3  lea     rdx, [r11+20h]
0x18000cda7  mov     rcx, r8
0x18000cdaa  mov     rax, [rax+90h]
0x18000cdb1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cdb6  mov     ebx, eax
0x18000cdb8  test    eax, eax
0x18000cdba  jz      short loc_18000CDCB
0x18000cdbc  mov     eax, 80004005h
0x18000cdc1  test    ebx, ebx
0x18000cdc3  cmovns  ebx, eax
0x18000cdc6  jmp     loc_18000CF1E
0x18000cdcb  lea     rdx, aAboutInternet; "about:internet"
0x18000cdd2  mov     rcx, [rsp+28h+String1]; String1
0x18000cdd7  call    wcscmp_0
0x18000cddc  test    eax, eax
0x18000cdde  jz      loc_18000CF1C
0x18000cde4  lea     rcx, [rdi+50h]
0x18000cde8  mov     rdx, rsi
0x18000cdeb  call    ?IsEqualObject@?$CComPtrBase@UIHTMLWindow2@@@ATL@@QEAA_NPEAUIUnknown@@@Z; ATL::CComPtrBase<IHTMLWindow2>::IsEqualObject(IUnknown *)
0x18000cdf0  test    al, al
0x18000cdf2  jz      loc_18000CF1C
0x18000cdf8  mov     byte ptr [rdi+80h], 1
0x18000cdff  mov     r9, [rdi+60h]
0x18000ce03  xor     ecx, ecx
0x18000ce05  mov     [rsp+28h+arg_8], rcx
0x18000ce0a  test    r9, r9
0x18000ce0d  jz      short loc_18000CE2E
0x18000ce0f  mov     rax, [r9]
0x18000ce12  lea     r8, [rsp+28h+arg_8]
0x18000ce17  lea     rdx, _GUID_c2704fa0_2f26_45a6_9e28_4136ff3fb583
0x18000ce1e  mov     rcx, r9
0x18000ce21  mov     rax, [rax]
0x18000ce24  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ce29  mov     rcx, [rsp+28h+arg_8]
0x18000ce2e  test    rcx, rcx
0x18000ce31  jz      short loc_18000CE44
0x18000ce33  mov     rax, [rcx]
0x18000ce36  mov     rax, [rax+30h]
0x18000ce3a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ce3f  mov     rcx, [rsp+28h+arg_8]
0x18000ce44  cmp     dword ptr [rdi+84h], 0
0x18000ce4b  jnz     loc_18000CF0A
0x18000ce51  xor     ecx, ecx; hWnd
0x18000ce53  call    cs:__imp_GetDC
0x18000ce59  mov     rbx, rax
0x18000ce5c  test    rax, rax
0x18000ce5f  jnz     short loc_18000CE8D
0x18000ce61  xor     edx, edx; hDC
0x18000ce63  xor     ecx, ecx; hWnd
0x18000ce65  call    cs:__imp_ReleaseDC
0x18000ce6b  nop
0x18000ce6c  mov     rcx, [rsp+28h+arg_8]
0x18000ce71  test    rcx, rcx
0x18000ce74  jz      short loc_18000CE83
0x18000ce76  mov     rax, [rcx]
0x18000ce79  mov     rax, [rax+10h]
0x18000ce7d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ce82  nop
0x18000ce83  mov     ebx, 80004005h
0x18000ce88  jmp     loc_18000CF1E
0x18000ce8d  mov     edx, 58h ; 'X'; index
0x18000ce92  mov     rcx, rbx; hdc
0x18000ce95  call    cs:__imp_GetDeviceCaps
0x18000ce9b  movd    xmm0, eax
0x18000ce9f  cvtdq2pd xmm0, xmm0
0x18000cea3  divsd   xmm0, cs:__real@4058000000000000
0x18000ceab  mulsd   xmm0, cs:__real@4059000000000000
0x18000ceb3  cvttsd2si eax, xmm0
0x18000ceb7  mov     [rdi+84h], eax
0x18000cebd  test    eax, eax
0x18000cebf  jnz     short loc_18000CEE6
0x18000cec1  mov     rdx, rbx; hDC
0x18000cec4  xor     ecx, ecx; hWnd
0x18000cec6  call    cs:__imp_ReleaseDC
0x18000cecc  nop
0x18000cecd  mov     rcx, [rsp+28h+arg_8]
0x18000ced2  test    rcx, rcx
0x18000ced5  jz      short loc_18000CEE4
0x18000ced7  mov     rax, [rcx]
0x18000ceda  mov     rax, [rax+10h]
0x18000cede  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cee3  nop
0x18000cee4  jmp     short loc_18000CE83
0x18000cee6  mov     edx, [rdi+88h]; int
0x18000ceec  cmp     edx, 64h ; 'd'
0x18000ceef  jz      short loc_18000CEFA
0x18000cef1  lea     rcx, [rdi-48h]; this
0x18000cef5  call    ?SetCurrentZoomLevel@BrowserToolWindow@@QEAAJH@Z; BrowserToolWindow::SetCurrentZoomLevel(int)
0x18000cefa  mov     rdx, rbx; hDC
0x18000cefd  xor     ecx, ecx; hWnd
0x18000ceff  call    cs:__imp_ReleaseDC
0x18000cf05  mov     rcx, [rsp+28h+arg_8]
0x18000cf0a  test    rcx, rcx
0x18000cf0d  jz      short loc_18000CF1C
0x18000cf0f  mov     rax, [rcx]
0x18000cf12  mov     rax, [rax+10h]
0x18000cf16  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cf1b  nop
0x18000cf1c  xor     ebx, ebx
0x18000cf1e  mov     rcx, [rsp+28h+String1]; bstrString
0x18000cf23  call    cs:__imp_SysFreeString
0x18000cf29  mov     eax, ebx
0x18000cf2b  jmp     short loc_18000CF32
0x18000cf2d  mov     eax, 80070057h
0x18000cf32  mov     rbx, [rsp+28h+arg_0]
0x18000cf37  mov     rsi, [rsp+28h+arg_10]
0x18000cf3c  add     rsp, 20h
0x18000cf40  pop     rdi
0x18000cf41  retn
```
