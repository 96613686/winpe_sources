# UiaManagerCrossMachineStub::GetHwndClassName(HWND__ *,ushort * *)

- ea: `0x180065e90`
- end: `0x180065f7f`
- name: `?GetHwndClassName@UiaManagerCrossMachineStub@@UEAAJPEAUHWND__@@PEAPEAG@Z`
- size: `239`
- prototype: `int(UiaManagerCrossMachineStub *__hidden this, HWND, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, loader_planting`

## callees

- `0x1800109bc`
- `0x180012484`
- `0x18002a514`
- `0x180031540`
- `0x180043680`
- `0x1800441ac`
- `0x180065e90`

## import_xrefs

- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetClassNameW` at `0x180065f0d`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetClassNameW` at `0x180065f0d`

## string_xrefs

- `0x180065ed4`: `onecore\windows\accessibletech\uiamanager\dll\uiamanagercrossmachinestub.cpp`
- `0x180065f17`: `onecore\windows\accessibletech\uiamanager\dll\uiamanagercrossmachinestub.cpp`

## pseudocode

```c
// Hidden C++ exception states: #try_helpers=1
__int64 __fastcall UiaManagerCrossMachineStub::GetHwndClassName(
        UiaManagerCrossMachineStub *this,
        HWND a2,
        unsigned __int16 **a3)
{
  const char *v5; // r9
  unsigned __int16 **bstr; // rax
  unsigned __int16 *v7; // rcx
  int v9[4]; // [rsp+20h] [rbp-238h] BYREF
  WCHAR ClassName[264]; // [rsp+30h] [rbp-228h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+258h] [rbp+0h]

  *a3 = 0;
  if ( !a2 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x545,
      (unsigned int)"onecore\\windows\\accessibletech\\uiamanager\\dll\\uiamanagercrossmachinestub.cpp",
      (const char *)0x80070057LL,
      v9[0]);
  memset_0(ClassName, 0, 0x208u);
  if ( !GetClassNameW(a2, ClassName, 260) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x547,
      (unsigned int)"onecore\\windows\\accessibletech\\uiamanager\\dll\\uiamanagercrossmachinestub.cpp",
      v5);
  bstr = (unsigned __int16 **)wil::make_bstr(v9, ClassName);
  v7 = *bstr;
  *bstr = 0;
  *a3 = v7;
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(v9);
  return 0;
}

```

## disassembly

```asm
0x180065e90  mov     [rsp+arg_0], rbx
0x180065e95  mov     [rsp+arg_18], rsi
0x180065e9a  push    rdi
0x180065e9b  sub     rsp, 250h
0x180065ea2  mov     rax, cs:__security_cookie
0x180065ea9  xor     rax, rsp
0x180065eac  mov     [rsp+258h+var_18], rax
0x180065eb4  mov     rbx, r8
0x180065eb7  mov     rdi, rdx
0x180065eba  mov     qword ptr [r8], 0
0x180065ec1  mov     rcx, [rsp+258h]; this
0x180065ec9  test    rdx, rdx
0x180065ecc  jnz     short loc_180065EE5
0x180065ece  mov     r9d, 80070057h; char *
0x180065ed4  lea     r8, aOnecoreWindows_31; "onecore\\windows\\accessibletech\\uiama"...
0x180065edb  mov     edx, 545h; void *
0x180065ee0  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180065ee5  xor     edx, edx; Val
0x180065ee7  mov     r8d, 208h; Size
0x180065eed  lea     rcx, [rsp+258h+ClassName]; void *
0x180065ef2  call    memset_0
0x180065ef7  mov     rsi, [rsp+258h]
0x180065eff  mov     r8d, 104h; nMaxCount
0x180065f05  lea     rdx, [rsp+258h+ClassName]; lpClassName
0x180065f0a  mov     rcx, rdi; hWnd
0x180065f0d  call    cs:__imp_GetClassNameW
0x180065f13  test    eax, eax
0x180065f15  jnz     short loc_180065F2B
0x180065f17  lea     r8, aOnecoreWindows_31; "onecore\\windows\\accessibletech\\uiama"...
0x180065f1e  mov     edx, 547h; void *
0x180065f23  mov     rcx, rsi; this
0x180065f26  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x180065f2b  lea     rdx, [rsp+258h+ClassName]
0x180065f30  lea     rcx, [rsp+258h+var_238]
0x180065f35  call    ?make_bstr@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@1@PEBG@Z; wil::make_bstr(ushort const *)
0x180065f3a  mov     rcx, [rax]
0x180065f3d  mov     qword ptr [rax], 0
0x180065f44  mov     [rbx], rcx
0x180065f47  lea     rcx, [rsp+258h+var_238]
0x180065f4c  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180065f51  xor     eax, eax
0x180065f53  jmp     short loc_180065F59
0x180065f55  mov     eax, [rsp+258h+var_238]
0x180065f59  mov     rcx, [rsp+258h+var_18]
0x180065f61  xor     rcx, rsp; StackCookie
0x180065f64  call    __security_check_cookie
0x180065f69  lea     r11, [rsp+258h+var_8]
0x180065f71  mov     rbx, [r11+10h]
0x180065f75  mov     rsi, [r11+28h]
0x180065f79  mov     rsp, r11
0x180065f7c  pop     rdi
0x180065f7d  retn
```
