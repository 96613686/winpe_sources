# GetNlsSystemLocale(void)

- ea: `0x180015680`
- end: `0x18001570c`
- name: `?GetNlsSystemLocale@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ`
- size: `140`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x1800133d0`

## callees

- `0x180002380`
- `0x1800032dc`
- `0x18000f724`
- `0x180015680`
- `0x18001dcc0`

## import_xrefs

- `KERNELBASE!GetSystemDefaultLocaleName` at `0x1800156bf`
- `KERNELBASE!GetSystemDefaultLocaleName` at `0x1800156bf`

## string_xrefs

- `0x1800156d1`: `onecoreuap\base\globalization\coreglobconfig\src\coreglobconfig.cpp`

## pseudocode

```c
__int64 __fastcall GetNlsSystemLocale(__int64 a1)
{
  const char *v2; // r9
  WCHAR LocaleName[88]; // [rsp+30h] [rbp-C8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+0h]

  memset_0(LocaleName, 0, 0xAAu);
  if ( !GetSystemDefaultLocaleName(LocaleName, 85) )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x241,
      (unsigned int)"onecoreuap\\base\\globalization\\coreglobconfig\\src\\coreglobconfig.cpp",
      v2);
  std::wstring::wstring(a1, (__int64)LocaleName);
  return a1;
}

```

## disassembly

```asm
0x180015680  push    rbx
0x180015682  sub     rsp, 0F0h
0x180015689  mov     rax, cs:__security_cookie
0x180015690  xor     rax, rsp
0x180015693  mov     [rsp+0F8h+var_18], rax
0x18001569b  mov     rbx, rcx
0x18001569e  mov     [rsp+0F8h+var_D0], rcx
0x1800156a3  lea     rcx, [rsp+0F8h+LocaleName]; void *
0x1800156a8  xor     edx, edx; Val
0x1800156aa  mov     r8d, 0AAh; Size
0x1800156b0  call    memset_0
0x1800156b5  mov     edx, 55h ; 'U'; cchLocaleName
0x1800156ba  lea     rcx, [rsp+0F8h+LocaleName]; lpLocaleName
0x1800156bf  call    cs:__imp_GetSystemDefaultLocaleName
0x1800156c5  test    eax, eax
0x1800156c7  jnz     short loc_1800156E3
0x1800156c9  mov     rcx, [rsp+0F8h]; this
0x1800156d1  lea     r8, aOnecoreuapBase; "onecoreuap\\base\\globalization\\coregl"...
0x1800156d8  mov     edx, 241h; void *
0x1800156dd  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x1800156e3  lea     rdx, [rsp+0F8h+LocaleName]
0x1800156e8  mov     rcx, rbx
0x1800156eb  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800156f0  mov     rax, rbx
0x1800156f3  mov     rcx, [rsp+0F8h+var_18]
0x1800156fb  xor     rcx, rsp; StackCookie
0x1800156fe  call    __security_check_cookie
0x180015703  add     rsp, 0F0h
0x18001570a  pop     rbx
0x18001570b  retn
```
