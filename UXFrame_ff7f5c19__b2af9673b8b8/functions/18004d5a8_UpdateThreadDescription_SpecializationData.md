# UpdateThreadDescription(SpecializationData *)

- ea: `0x18004d5a8`
- end: `0x18004d69b`
- name: `?UpdateThreadDescription@@YAXPEAUSpecializationData@@@Z`
- size: `243`
- prototype: `void __fastcall(struct SpecializationData *)`
- caller_count: `2`
- callee_count: `9`
- tags: `installer_update`

## callers

- `0x18004488c`
- `0x18004a43c`

## callees

- `0x180002b20`
- `0x180008968`
- `0x180021310`
- `0x180022078`
- `0x180039404`
- `0x18003ca90`
- `0x18003cae4`
- `0x18003cb60`
- `0x18004d5a8`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18004d647`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18004d647`
- `api-ms-win-core-processthreads-l1-1-3!SetThreadDescription` at `0x18004d653`
- `api-ms-win-core-processthreads-l1-1-3!SetThreadDescription` at `0x18004d653`

## string_xrefs

- `0x18004d5d5`: `UXFrame UI thread: `

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall UpdateThreadDescription(struct SpecializationData *a1, __int64 a2)
{
  _QWORD *v2; // r8
  int v3; // r9d
  __int64 v4; // rax
  const WCHAR *v5; // rbx
  HANDLE CurrentThread; // rax
  PCWSTR *v7; // rax
  const wchar_t *v8; // [rsp+40h] [rbp+7h] BYREF
  _BYTE v9[32]; // [rsp+48h] [rbp+Fh] BYREF
  PCWSTR lpThreadDescription[3]; // [rsp+68h] [rbp+2Fh] BYREF
  unsigned __int64 v11; // [rsp+80h] [rbp+47h]

  std::wstring::wstring(lpThreadDescription, a2, a1);
  v8 = L"UXFrame UI thread: ";
  if ( v2 )
  {
    if ( *v2 )
      v4 = wil::str_concat<std::wstring,wchar_t const *,winrt::hstring &>(v9, &v8);
    else
      v4 = wil::str_concat<std::wstring,wchar_t const *,winrt::hstring &,wchar_t const (&)[2],winrt::hstring &,wchar_t const (&)[2],winrt::hstring &>(
             (unsigned int)v9,
             (unsigned int)&v8,
             (int)v2 + 8,
             v3,
             (winrt::hstring *)(v2 + 2));
  }
  else
  {
    v4 = wil::str_concat<std::wstring,wchar_t const *,wchar_t const (&)[10]>(v9, &v8);
  }
  std::wstring::operator=(lpThreadDescription, v4);
  std::wstring::_Tidy_deallocate(v9);
  v5 = (const WCHAR *)lpThreadDescription;
  if ( v11 > 7 )
    v5 = lpThreadDescription[0];
  CurrentThread = GetCurrentThread();
  SetThreadDescription(CurrentThread, v5);
  v7 = lpThreadDescription;
  if ( v11 > 7 )
    v7 = (PCWSTR *)lpThreadDescription[0];
  v8 = (const wchar_t *)v7;
  UXFrameTelemetry::ThreadDescriptionChanged<wchar_t const *>(&v8);
  std::wstring::_Tidy_deallocate(lpThreadDescription);
}

```

## disassembly

```asm
0x18004d5a8  mov     [rsp-8+arg_8], rbx
0x18004d5ad  push    rbp
0x18004d5ae  lea     rbp, [rsp-57h]
0x18004d5b3  sub     rsp, 90h
0x18004d5ba  mov     rax, cs:__security_cookie
0x18004d5c1  xor     rax, rsp
0x18004d5c4  mov     [rbp+57h+var_8], rax
0x18004d5c8  mov     r8, rcx
0x18004d5cb  lea     rcx, [rbp+57h+lpThreadDescription]
0x18004d5cf  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18004d5d4  nop
0x18004d5d5  lea     rax, aUxframeUiThrea; "UXFrame UI thread: "
0x18004d5dc  lea     rdx, [rbp+57h+var_50]
0x18004d5e0  mov     [rbp+57h+var_50], rax
0x18004d5e4  test    r8, r8
0x18004d5e7  jnz     short loc_18004D5F4
0x18004d5e9  lea     rcx, [rbp+57h+var_48]
0x18004d5ed  call    ??$str_concat@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEB_WAEAY09$$CB_W@wil@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@$$QEAPEB_WAEAY09$$CB_W@Z; wil::str_concat<std::wstring,wchar_t const *,wchar_t const (&)[10]>(wchar_t const * &&,wchar_t const (&)[10])
0x18004d5f2  jmp     short loc_18004D624
0x18004d5f4  cmp     qword ptr [r8], 0
0x18004d5f8  jz      short loc_18004D605
0x18004d5fa  lea     rcx, [rbp+57h+var_48]
0x18004d5fe  call    ??$str_concat@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEB_WAEAUhstring@winrt@@@wil@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@$$QEAPEB_WAEAUhstring@winrt@@@Z; wil::str_concat<std::wstring,wchar_t const *,winrt::hstring &>(wchar_t const * &&,winrt::hstring &)
0x18004d603  jmp     short loc_18004D624
0x18004d605  lea     rax, [r8+18h]
0x18004d609  lea     rcx, [r8+10h]
0x18004d60d  add     r8, 8
0x18004d611  mov     [rsp+90h+var_60], rax
0x18004d616  mov     [rsp+90h+var_70], rcx
0x18004d61b  lea     rcx, [rbp+57h+var_48]
0x18004d61f  call    ??$str_concat@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEB_WAEAUhstring@winrt@@AEAY01$$CB_WAEAU34@AEAY01$$CB_WAEAU34@@wil@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@$$QEAPEB_WAEAUhstring@winrt@@AEAY01$$CB_W121@Z; wil::str_concat<std::wstring,wchar_t const *,winrt::hstring &,wchar_t const (&)[2],winrt::hstring &,wchar_t const (&)[2],winrt::hstring &>(wchar_t const * &&,winrt::hstring &,wchar_t const (&)[2],winrt::hstring &,wchar_t const (&)[2],winrt::hstring &)
0x18004d624  mov     rdx, rax
0x18004d627  lea     rcx, [rbp+57h+lpThreadDescription]
0x18004d62b  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18004d630  lea     rcx, [rbp+57h+var_48]
0x18004d634  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18004d639  lea     rbx, [rbp+57h+lpThreadDescription]
0x18004d63d  cmp     [rbp+57h+var_10], 7
0x18004d642  cmova   rbx, [rbp+57h+lpThreadDescription]
0x18004d647  call    cs:__imp_GetCurrentThread
0x18004d64d  mov     rdx, rbx; lpThreadDescription
0x18004d650  mov     rcx, rax; hThread
0x18004d653  call    cs:__imp_SetThreadDescription
0x18004d659  lea     rax, [rbp+57h+lpThreadDescription]
0x18004d65d  cmp     [rbp+57h+var_10], 7
0x18004d662  cmova   rax, [rbp+57h+lpThreadDescription]
0x18004d667  mov     [rbp+57h+var_50], rax
0x18004d66b  lea     rcx, [rbp+57h+var_50]
0x18004d66f  call    ??$ThreadDescriptionChanged@PEB_W@UXFrameTelemetry@@SAX$$QEAPEB_W@Z; UXFrameTelemetry::ThreadDescriptionChanged<wchar_t const *>(wchar_t const * &&)
0x18004d674  nop
0x18004d675  lea     rcx, [rbp+57h+lpThreadDescription]
0x18004d679  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18004d67e  mov     rcx, [rbp+57h+var_8]
0x18004d682  xor     rcx, rsp; StackCookie
0x18004d685  call    __security_check_cookie
0x18004d68a  mov     rbx, [rsp+90h+arg_8]
0x18004d692  add     rsp, 90h
0x18004d699  pop     rbp
0x18004d69a  retn
```
