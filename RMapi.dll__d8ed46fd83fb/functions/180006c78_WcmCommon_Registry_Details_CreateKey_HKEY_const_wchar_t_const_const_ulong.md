# WcmCommon::Registry::Details::CreateKey(HKEY__ * const,wchar_t const * const,ulong)

- ea: `0x180006c78`
- end: `0x180006d52`
- name: `?CreateKey@Details@Registry@WcmCommon@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAUHKEY__@@QEB_WK@Z`
- size: `218`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180006c2c`
- `0x18000a9c0`

## callees

- `0x180006c78`
- `0x180006d58`
- `0x18000d2a0`
- `0x180016418`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180006cfa`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180006cfa`

## string_xrefs

- `0x180006d1b`: `onecore\private\net\inc\wcm\wcm_registry_details.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_QWORD *__fastcall WcmCommon::Registry::Details::CreateKey(_QWORD *a1, __int64 a2, const WCHAR *a3, REGSAM a4)
{
  unsigned int v5; // edi
  DWORD dwOptions; // [rsp+20h] [rbp-78h]
  _QWORD *v8; // [rsp+58h] [rbp-40h] BYREF
  HKEY v9; // [rsp+60h] [rbp-38h] BYREF
  char v10; // [rsp+68h] [rbp-30h]
  _QWORD *v11; // [rsp+70h] [rbp-28h]
  DWORD v12; // [rsp+78h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+0h]

  v11 = a1;
  *a1 = 0;
  v12 = 0;
  v8 = a1;
  v9 = 0;
  v10 = 1;
  v5 = RegCreateKeyExW(HKEY_LOCAL_MACHINE, a3, 0, 0, 0, a4, 0, &v9, &v12);
  wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(&v8);
  if ( v5 )
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0x45,
      (unsigned int)"onecore\\private\\net\\inc\\wcm\\wcm_registry_details.h",
      (const char *)v5,
      dwOptions);
  return a1;
}

```

## disassembly

```asm
0x180006c78  mov     r11, rsp
0x180006c7b  mov     [r11+10h], rbx
0x180006c7f  push    rdi
0x180006c80  sub     rsp, 90h
0x180006c87  mov     rax, cs:__security_cookie
0x180006c8e  xor     rax, rsp
0x180006c91  mov     [rsp+98h+var_18], rax
0x180006c99  mov     rdx, r8; lpSubKey
0x180006c9c  mov     rbx, rcx
0x180006c9f  mov     [r11-28h], rcx
0x180006ca3  mov     [rsp+98h+var_48], 0
0x180006cab  xor     ecx, ecx
0x180006cad  mov     [rbx], rcx
0x180006cb0  mov     [rsp+98h+var_48], 1
0x180006cb8  mov     [rsp+98h+var_20], ecx
0x180006cbc  mov     [r11-40h], rbx
0x180006cc0  mov     [r11-38h], rcx
0x180006cc4  mov     [rsp+98h+var_30], 1
0x180006cc9  lea     rcx, [r11-20h]
0x180006ccd  mov     [r11-58h], rcx
0x180006cd1  lea     rcx, [r11-38h]
0x180006cd5  mov     [r11-60h], rcx
0x180006cd9  mov     qword ptr [r11-68h], 0
0x180006ce1  mov     [r11-70h], r9d
0x180006ce5  mov     [rsp+98h+dwOptions], 0; unsigned int
0x180006ced  xor     r9d, r9d; lpClass
0x180006cf0  xor     r8d, r8d; Reserved
0x180006cf3  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180006cfa  call    cs:__imp_RegCreateKeyExW
0x180006d00  mov     edi, eax
0x180006d02  lea     rcx, [rsp+98h+var_40]
0x180006d07  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(void)
0x180006d0c  test    edi, edi
0x180006d0e  jz      short loc_180006D2D
0x180006d10  mov     rcx, [rsp+98h]; this
0x180006d18  mov     r9d, edi; char *
0x180006d1b  lea     r8, aOnecorePrivate_1; "onecore\\private\\net\\inc\\wcm\\wcm_re"...
0x180006d22  mov     edx, 45h ; 'E'; void *
0x180006d27  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x180006d2d  mov     rax, rbx
0x180006d30  mov     rcx, [rsp+98h+var_18]
0x180006d38  xor     rcx, rsp; StackCookie
0x180006d3b  call    __security_check_cookie
0x180006d40  mov     rbx, [rsp+98h+arg_8]
0x180006d48  add     rsp, 90h
0x180006d4f  pop     rdi
0x180006d50  retn
```
