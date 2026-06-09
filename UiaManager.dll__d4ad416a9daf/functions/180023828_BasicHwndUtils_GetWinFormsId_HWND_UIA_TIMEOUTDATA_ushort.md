# BasicHwndUtils::GetWinFormsId(HWND__ *,UIA_TIMEOUTDATA &,ushort * *)

- ea: `0x180023828`
- end: `0x18002392b`
- name: `?GetWinFormsId@BasicHwndUtils@@SAJPEAUHWND__@@AEAUUIA_TIMEOUTDATA@@PEAPEAG@Z`
- size: `259`
- prototype: `__int64 __fastcall(HWND, struct UIA_TIMEOUTDATA *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x1800234f0`

## callees

- `0x1800109bc`
- `0x180012484`
- `0x180023828`
- `0x180023934`
- `0x18002a514`
- `0x180031540`
- `0x180043680`

## import_xrefs

- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!RegisterWindowMessageW` at `0x180023860`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!RegisterWindowMessageW` at `0x180023860`

## string_xrefs

- `0x180023874`: `onecore\windows\accessibletech\common\basichwndutils.cpp`
- `0x1800238af`: `onecore\windows\accessibletech\common\basichwndutils.cpp`

## pseudocode

```c
// Hidden C++ exception states: #try_helpers=1
__int64 __fastcall BasicHwndUtils::GetWinFormsId(HWND a1, struct UIA_TIMEOUTDATA *a2, unsigned __int16 **a3)
{
  UINT v6; // edx
  __int64 v7; // r8
  const char *v8; // r9
  int v9; // eax
  unsigned __int16 *v11; // rax
  int v12; // [rsp+20h] [rbp-FE8h]
  _QWORD v13[2]; // [rsp+30h] [rbp-FD8h] BYREF
  _WORD v14[1999]; // [rsp+40h] [rbp-FC8h] BYREF
  __int16 v15; // [rsp+FDEh] [rbp-2Ah]
  wil::details::in1diag3 *retaddr; // [rsp+1008h] [rbp+0h]

  *a3 = 0;
  v6 = RegisterWindowMessageW(L"WM_GETCONTROLNAME");
  if ( !v6 )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x2C6,
      (unsigned int)"onecore\\windows\\accessibletech\\common\\basichwndutils.cpp",
      v8);
  v14[0] = 0;
  v9 = BasicHwndUtils::SendMessageWithSharedBuffer(a1, v6, v7, a2, v14);
  if ( v9 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x2CC,
      (unsigned int)"onecore\\windows\\accessibletech\\common\\basichwndutils.cpp",
      (const char *)(unsigned int)v9,
      v12);
  v15 = 0;
  if ( v14[0] )
  {
    wil::make_bstr(v13, v14);
    v11 = (unsigned __int16 *)v13[0];
    v13[0] = 0;
    *a3 = v11;
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(v13);
  }
  else
  {
    *a3 = 0;
  }
  return 0;
}

```

## disassembly

```asm
0x180023828  mov     [rsp+arg_18], rbx
0x18002382d  push    rsi
0x18002382e  push    rdi
0x18002382f  push    r14
0x180023831  sub     rsp, 0FF0h
0x180023838  mov     rax, cs:__security_cookie
0x18002383f  xor     rax, rsp
0x180023842  mov     [rsp+1008h+var_28], rax
0x18002384a  mov     rbx, r8
0x18002384d  mov     rsi, rdx
0x180023850  mov     rdi, rcx
0x180023853  xor     r14d, r14d
0x180023856  mov     [r8], r14
0x180023859  lea     rcx, aWmGetcontrolna; "WM_GETCONTROLNAME"
0x180023860  call    cs:__imp_RegisterWindowMessageW
0x180023866  mov     edx, eax; unsigned int
0x180023868  mov     rcx, [rsp+1008h]; this
0x180023870  test    eax, eax
0x180023872  jnz     short loc_180023885
0x180023874  lea     r8, aOnecoreWindows_10; "onecore\\windows\\accessibletech\\commo"...
0x18002387b  mov     edx, 2C6h; void *
0x180023880  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x180023885  mov     [rsp+1008h+var_FC8], r14w
0x18002388b  lea     rax, [rsp+1008h+var_FC8]
0x180023890  mov     qword ptr [rsp+1008h+var_FE8], rax; int
0x180023895  mov     r9, rsi; struct UIA_TIMEOUTDATA *
0x180023898  mov     rcx, rdi; HWND
0x18002389b  call    ?SendMessageWithSharedBuffer@BasicHwndUtils@@SAJPEAUHWND__@@I_KAEAUUIA_TIMEOUTDATA@@PEAXK@Z; BasicHwndUtils::SendMessageWithSharedBuffer(HWND__ *,uint,unsigned __int64,UIA_TIMEOUTDATA &,void *,ulong)
0x1800238a0  mov     rcx, [rsp+1008h]; this
0x1800238a8  test    eax, eax
0x1800238aa  jns     short loc_1800238C0
0x1800238ac  mov     r9d, eax; char *
0x1800238af  lea     r8, aOnecoreWindows_10; "onecore\\windows\\accessibletech\\commo"...
0x1800238b6  mov     edx, 2CCh; void *
0x1800238bb  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800238c0  mov     [rsp+1008h+var_2A], r14w
0x1800238c9  cmp     [rsp+1008h+var_FC8], r14w
0x1800238cf  jnz     short loc_1800238D8
0x1800238d1  mov     [rbx], r14
0x1800238d4  xor     eax, eax
0x1800238d6  jmp     short loc_180023906
0x1800238d8  lea     rdx, [rsp+1008h+var_FC8]
0x1800238dd  lea     rcx, [rsp+1008h+var_FD8]
0x1800238e2  call    ?make_bstr@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@1@PEBG@Z; wil::make_bstr(ushort const *)
0x1800238e7  mov     rax, [rsp+1008h+var_FD8]
0x1800238ec  mov     [rsp+1008h+var_FD8], r14
0x1800238f1  mov     [rbx], rax
0x1800238f4  lea     rcx, [rsp+1008h+var_FD8]
0x1800238f9  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800238fe  xor     eax, eax
0x180023900  jmp     short loc_180023906
0x180023902  mov     eax, dword ptr [rsp+1008h+var_FD8]
0x180023906  mov     rcx, [rsp+1008h+var_28]
0x18002390e  xor     rcx, rsp; StackCookie
0x180023911  call    __security_check_cookie
0x180023916  mov     rbx, [rsp+1008h+arg_18]
0x18002391e  add     rsp, 0FF0h
0x180023925  pop     r14
0x180023927  pop     rdi
0x180023928  pop     rsi
0x180023929  retn
```
