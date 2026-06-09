# Windows::UI::Input::InjectionBrokerImpl::InitializePenInjection(uint,unsigned __int64 *)

- ea: `0x1800069d0`
- end: `0x180006a27`
- name: `?InitializePenInjection@InjectionBrokerImpl@Input@UI@Windows@@UEAAJIPEA_K@Z`
- size: `87`
- prototype: `signed int __fastcall(Windows::UI::Input::InjectionBrokerImpl *this, unsigned int, unsigned __int64 *)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1800069d0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006a03`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006a03`
- `ext-ms-win-ntuser-rim-l1-1-0!InitializePointerDeviceInjection` at `0x1800069f9`
- `ext-ms-win-ntuser-rim-l1-1-0!InitializePointerDeviceInjection` at `0x1800069f9`

## pseudocode

```c
signed int __fastcall Windows::UI::Input::InjectionBrokerImpl::InitializePenInjection(
        Windows::UI::Input::InjectionBrokerImpl *this,
        unsigned int a2,
        unsigned __int64 *a3)
{
  signed int result; // eax
  unsigned __int64 v5; // [rsp+58h] [rbp+20h] BYREF

  v5 = 0;
  if ( (unsigned int)InitializePointerDeviceInjection(3, 1, 0, a2, &v5) )
  {
    *a3 = v5;
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
0x1800069d0  push    rbx
0x1800069d2  sub     rsp, 30h
0x1800069d6  mov     rbx, r8
0x1800069d9  mov     [rsp+38h+arg_18], 0
0x1800069e2  xor     r8d, r8d
0x1800069e5  lea     rax, [rsp+38h+arg_18]
0x1800069ea  mov     r9d, edx
0x1800069ed  mov     [rsp+38h+var_18], rax
0x1800069f2  lea     edx, [r8+1]
0x1800069f6  lea     ecx, [rdx+2]
0x1800069f9  call    cs:__imp_InitializePointerDeviceInjection
0x1800069ff  test    eax, eax
0x180006a01  jnz     short loc_180006A17
0x180006a03  call    cs:__imp_GetLastError
0x180006a09  test    eax, eax
0x180006a0b  jle     short loc_180006A21
0x180006a0d  movzx   eax, ax
0x180006a10  or      eax, 80070000h
0x180006a15  jmp     short loc_180006A21
0x180006a17  mov     rax, [rsp+38h+arg_18]
0x180006a1c  mov     [rbx], rax
0x180006a1f  xor     eax, eax
0x180006a21  add     rsp, 30h
0x180006a25  pop     rbx
0x180006a26  retn
```
