# SystemSettings::BatteryUsageHandlers::AppSearchFilter2::SetValue(HSTRING__ *)

- ea: `0x1800374f0`
- end: `0x180037567`
- name: `?SetValue@AppSearchFilter2@BatteryUsageHandlers@SystemSettings@@UEAAJPEAUHSTRING__@@@Z`
- size: `119`
- prototype: `__int64 __fastcall(SystemSettings::BatteryUsageHandlers::AppSearchFilter2 *__hidden this, HSTRING)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x18002e2b0`
- `0x1800374f0`
- `0x18005a010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180037554`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180037554`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall SystemSettings::BatteryUsageHandlers::AppSearchFilter2::SetValue(HSTRING *this, HSTRING a2)
{
  HRESULT v3; // ebx
  HSTRING v5; // [rsp+38h] [rbp+10h] BYREF
  HSTRING string; // [rsp+40h] [rbp+18h] BYREF
  HSTRING v7; // [rsp+48h] [rbp+20h] BYREF

  v5 = a2;
  string = 0;
  v3 = Microsoft::WRL::Wrappers::HString::Set(&string, &v5);
  if ( v3 >= 0 )
  {
    v7 = string;
    Microsoft::WRL::Wrappers::HString::Set(this + 33, &v7);
    (*((void (__fastcall **)(HSTRING *, HSTRING *))*this + 24))(this, this);
  }
  WindowsDeleteString(string);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x1800374f0  mov     rax, rsp
0x1800374f3  mov     [rax+8], rbx
0x1800374f7  mov     [rax+10h], rdx
0x1800374fb  push    rdi
0x1800374fc  sub     rsp, 20h
0x180037500  mov     rdi, rcx
0x180037503  mov     qword ptr [rax+18h], 0
0x18003750b  lea     rdx, [rax+10h]; HSTRING *
0x18003750f  lea     rcx, [rax+18h]; newString
0x180037513  call    ?Set@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEAUHSTRING__@@@Z; Microsoft::WRL::Wrappers::HString::Set(HSTRING__ * const &)
0x180037518  mov     ebx, eax
0x18003751a  test    eax, eax
0x18003751c  js      short loc_18003754F
0x18003751e  mov     rdx, [rsp+28h+string]
0x180037523  mov     [rsp+28h+arg_18], rdx
0x180037528  lea     rcx, [rdi+108h]; newString
0x18003752f  lea     rdx, [rsp+28h+arg_18]; HSTRING *
0x180037534  call    ?Set@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEAUHSTRING__@@@Z; Microsoft::WRL::Wrappers::HString::Set(HSTRING__ * const &)
0x180037539  mov     rcx, [rdi]
0x18003753c  mov     rax, [rcx+0C0h]
0x180037543  mov     rdx, rdi
0x180037546  mov     rcx, rdi
0x180037549  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003754e  nop
0x18003754f  mov     rcx, [rsp+28h+string]; string
0x180037554  call    cs:__imp_WindowsDeleteString
0x18003755a  mov     eax, ebx
0x18003755c  mov     rbx, [rsp+28h+arg_0]
0x180037561  add     rsp, 20h
0x180037565  pop     rdi
0x180037566  retn
```
