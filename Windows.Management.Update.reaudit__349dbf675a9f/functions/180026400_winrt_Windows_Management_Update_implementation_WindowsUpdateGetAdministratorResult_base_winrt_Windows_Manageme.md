# winrt::Windows::Management::Update::implementation::WindowsUpdateGetAdministratorResult_base<winrt::Windows::Management::Update::implementation::WindowsUpdateGetAdministratorResult,>::GetRuntimeClassName(void)

- ea: `0x180026400`
- end: `0x180026428`
- name: `?GetRuntimeClassName@?$WindowsUpdateGetAdministratorResult_base@UWindowsUpdateGetAdministratorResult@implementation@Update@Management@Windows@winrt@@$$V@implementation@Update@Management@Windows@winrt@@UEBA?AUhstring@6@XZ`
- size: `40`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update`

## callees

- `0x180012078`

## string_xrefs

- `0x180026412`: `Windows.Management.Update.WindowsUpdateGetAdministratorResult`

## pseudocode

```c
winrt::hstring *__fastcall winrt::Windows::Management::Update::implementation::WindowsUpdateGetAdministratorResult_base<winrt::Windows::Management::Update::implementation::WindowsUpdateGetAdministratorResult,>::GetRuntimeClassName(
        __int64 a1,
        winrt::hstring *a2)
{
  winrt::hstring::hstring(a2, L"Windows.Management.Update.WindowsUpdateGetAdministratorResult", 0x3Du);
  return a2;
}

```

## disassembly

```asm
0x180026400  push    rbx
0x180026402  sub     rsp, 30h
0x180026406  mov     rbx, rdx
0x180026409  mov     r8d, 3Dh ; '='; unsigned int
0x18002640f  mov     rcx, rbx; this
0x180026412  lea     rdx, aWindowsManagem_0; "Windows.Management.Update.WindowsUpdate"...
0x180026419  call    ??0hstring@winrt@@QEAA@PEBGI@Z; winrt::hstring::hstring(ushort const *,uint)
0x18002641e  mov     rax, rbx
0x180026421  add     rsp, 30h
0x180026425  pop     rbx
0x180026426  retn
```
