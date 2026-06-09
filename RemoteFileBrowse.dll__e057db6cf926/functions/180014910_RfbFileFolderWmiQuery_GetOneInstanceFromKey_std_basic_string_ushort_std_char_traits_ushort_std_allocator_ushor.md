# RfbFileFolderWmiQuery::GetOneInstanceFromKey(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,wistd::unique_ptr<_ITEMID_CHILD,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>> &)

- ea: `0x180014910`
- end: `0x180014990`
- name: `?GetOneInstanceFromKey@RfbFileFolderWmiQuery@@UEAAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV?$unique_ptr@U_ITEMID_CHILD@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@Z`
- size: `128`
- prototype: `__int64 __fastcall(__int64, _QWORD *, __int64)`
- caller_count: `0`
- callee_count: `6`
- tags: `service_task`

## callees

- `0x180002030`
- `0x18000591c`
- `0x18000762c`
- `0x1800092f0`
- `0x18000937c`
- `0x180010e20`

## pseudocode

```c
__int64 __fastcall RfbFileFolderWmiQuery::GetOneInstanceFromKey(__int64 a1, _QWORD *a2, __int64 a3)
{
  char *Src[4]; // [rsp+20h] [rbp-48h] BYREF

  std::wstring::wstring((__int64)Src, a1 + 192);
  std::wstring::append(Src, L"\\\\");
  std::wstring::append(Src, a2);
  RfbWmiQuery::GetOneInstanceFromKey(a1, Src, a3);
  return std::wstring::~wstring(Src);
}

```

## disassembly

```asm
0x180014910  push    rbx
0x180014912  push    rsi
0x180014913  push    rdi
0x180014914  sub     rsp, 50h
0x180014918  mov     rax, cs:__security_cookie
0x18001491f  xor     rax, rsp
0x180014922  mov     [rsp+68h+var_28], rax
0x180014927  mov     rsi, r8
0x18001492a  mov     rbx, rdx
0x18001492d  mov     rdi, rcx
0x180014930  lea     rdx, [rcx+0C0h]
0x180014937  lea     rcx, [rsp+68h+Src]
0x18001493c  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180014941  nop
0x180014942  lea     rdx, String2; "\\\\"
0x180014949  lea     rcx, [rsp+68h+Src]; Src
0x18001494e  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x180014953  mov     rdx, rbx
0x180014956  lea     rcx, [rsp+68h+Src]; Src
0x18001495b  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@@Z; std::wstring::append(std::wstring const &)
0x180014960  mov     r8, rsi
0x180014963  lea     rdx, [rsp+68h+Src]
0x180014968  mov     rcx, rdi
0x18001496b  call    ?GetOneInstanceFromKey@RfbWmiQuery@@UEAAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV?$unique_ptr@U_ITEMID_CHILD@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@Z; RfbWmiQuery::GetOneInstanceFromKey(std::wstring const &,wistd::unique_ptr<_ITEMID_CHILD,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>> &)
0x180014970  nop
0x180014971  lea     rcx, [rsp+68h+Src]
0x180014976  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001497b  mov     rcx, [rsp+68h+var_28]
0x180014980  xor     rcx, rsp; StackCookie
0x180014983  call    __security_check_cookie
0x180014988  add     rsp, 50h
0x18001498c  pop     rdi
0x18001498d  pop     rsi
0x18001498e  pop     rbx
0x18001498f  retn
```
