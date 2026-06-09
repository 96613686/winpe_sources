# Windows::UI::Input::InjectionBrokerImpl::InitializeTouchInjection(uint,uint,unsigned __int64 *)

- ea: `0x180006a30`
- end: `0x180006a84`
- name: `?InitializeTouchInjection@InjectionBrokerImpl@Input@UI@Windows@@UEAAJIIPEA_K@Z`
- size: `84`
- prototype: `signed int __fastcall(Windows::UI::Input::InjectionBrokerImpl *this, __int64, unsigned int, unsigned __int64 *)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180006a30`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006a60`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006a60`
- `ext-ms-win-ntuser-rim-l1-1-0!InitializePointerDeviceInjection` at `0x180006a56`
- `ext-ms-win-ntuser-rim-l1-1-0!InitializePointerDeviceInjection` at `0x180006a56`

## pseudocode

```c
signed int __fastcall Windows::UI::Input::InjectionBrokerImpl::InitializeTouchInjection(
        Windows::UI::Input::InjectionBrokerImpl *this,
        __int64 a2,
        unsigned int a3,
        unsigned __int64 *a4)
{
  signed int result; // eax
  unsigned __int64 v6[3]; // [rsp+30h] [rbp-18h] BYREF

  v6[0] = 0;
  if ( (unsigned int)InitializePointerDeviceInjection(2, a2, 0, a3, v6) )
  {
    *a4 = v6[0];
    return 0;
  }
  else
  {
    result = GetLastError();
    if ( result > 0 )
      return (unsigned __int16)result | 0x80070000;
  }
  return result;
}

```

## disassembly

```asm
0x180006a30  push    rbx
0x180006a32  sub     rsp, 40h
0x180006a36  mov     rbx, r9
0x180006a39  mov     [rsp+48h+var_18], 0
0x180006a42  mov     r9d, r8d
0x180006a45  lea     rax, [rsp+48h+var_18]
0x180006a4a  xor     r8d, r8d
0x180006a4d  mov     [rsp+48h+var_28], rax
0x180006a52  lea     ecx, [r8+2]
0x180006a56  call    cs:__imp_InitializePointerDeviceInjection
0x180006a5c  test    eax, eax
0x180006a5e  jnz     short loc_180006A74
0x180006a60  call    cs:__imp_GetLastError
0x180006a66  test    eax, eax
0x180006a68  jle     short loc_180006A7E
0x180006a6a  movzx   eax, ax
0x180006a6d  or      eax, 80070000h
0x180006a72  jmp     short loc_180006A7E
0x180006a74  mov     rax, [rsp+48h+var_18]
0x180006a79  mov     [rbx], rax
0x180006a7c  xor     eax, eax
0x180006a7e  add     rsp, 40h
0x180006a82  pop     rbx
0x180006a83  retn
```
