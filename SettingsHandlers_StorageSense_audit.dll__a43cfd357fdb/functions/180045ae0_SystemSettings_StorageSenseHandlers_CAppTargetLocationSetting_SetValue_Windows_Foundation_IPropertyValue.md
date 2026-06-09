# SystemSettings::StorageSenseHandlers::CAppTargetLocationSetting::SetValue(Windows::Foundation::IPropertyValue *)

- ea: `0x180045ae0`
- end: `0x180045b69`
- name: `?SetValue@CAppTargetLocationSetting@StorageSenseHandlers@SystemSettings@@UEAAJPEAUIPropertyValue@Foundation@Windows@@@Z`
- size: `137`
- prototype: `__int64 __fastcall(SystemSettings::StorageSenseHandlers::CAppTargetLocationSetting *__hidden this, struct Windows::Foundation::IPropertyValue *)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting`

## callees

- `0x1800e3010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180045b45`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180045b45`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180045b0a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180045b51`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180045b0a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180045b51`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180045b30`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180045b30`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall SystemSettings::StorageSenseHandlers::CAppTargetLocationSetting::SetValue(
        SystemSettings::StorageSenseHandlers::CAppTargetLocationSetting *this,
        struct Windows::Foundation::IPropertyValue *a2)
{
  void (__fastcall *v4)(struct Windows::Foundation::IPropertyValue *, HSTRING *); // rbx
  HSTRING string; // [rsp+30h] [rbp+8h] BYREF

  string = 0;
  v4 = *(void (__fastcall **)(struct Windows::Foundation::IPropertyValue *, HSTRING *))(*(_QWORD *)a2 + 152LL);
  WindowsDeleteString(0);
  string = 0;
  v4(a2, &string);
  WindowsGetStringRawBuffer(string, 0);
  _o_wcscpy_s((char *)this + 240, 260);
  WindowsDeleteString(string);
  return 0;
}

```

## disassembly

```asm
0x180045ae0  mov     [rsp+arg_8], rbx
0x180045ae5  mov     [rsp+arg_10], rsi
0x180045aea  push    rdi
0x180045aeb  sub     rsp, 20h
0x180045aef  mov     rdi, rdx
0x180045af2  mov     rsi, rcx
0x180045af5  mov     [rsp+28h+string], 0
0x180045afe  mov     rax, [rdx]
0x180045b01  mov     rbx, [rax+98h]
0x180045b08  xor     ecx, ecx; string
0x180045b0a  call    cs:__imp_WindowsDeleteString
0x180045b10  mov     [rsp+28h+string], 0
0x180045b19  lea     rdx, [rsp+28h+string]
0x180045b1e  mov     rcx, rdi
0x180045b21  mov     rax, rbx
0x180045b24  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045b29  xor     edx, edx; length
0x180045b2b  mov     rcx, [rsp+28h+string]; string
0x180045b30  call    cs:__imp_WindowsGetStringRawBuffer
0x180045b36  lea     rcx, [rsi+0F0h]
0x180045b3d  mov     r8, rax
0x180045b40  mov     edx, 104h
0x180045b45  call    cs:__imp__o_wcscpy_s
0x180045b4b  nop
0x180045b4c  mov     rcx, [rsp+28h+string]; string
0x180045b51  call    cs:__imp_WindowsDeleteString
0x180045b57  xor     eax, eax
0x180045b59  mov     rbx, [rsp+28h+arg_8]
0x180045b5e  mov     rsi, [rsp+28h+arg_10]
0x180045b63  add     rsp, 20h
0x180045b67  pop     rdi
0x180045b68  retn
```
