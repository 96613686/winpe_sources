# ConnectedStorage::SimpleHStringWrapper::operator=(ConnectedStorage::SimpleHStringWrapper const &)

- ea: `0x180012ed8`
- end: `0x180012f38`
- name: `??4SimpleHStringWrapper@ConnectedStorage@@QEAAAEAV01@AEBV01@@Z`
- size: `96`
- prototype: `__int64 __fastcall(HSTRING *newString)`
- caller_count: `51`
- callee_count: `2`
- tags: ``

## callers

- `0x18000d99c`
- `0x180012f40`
- `0x180016df0`
- `0x180021dd0`
- `0x180022210`
- `0x180022630`
- `0x180022e30`
- `0x1800238b0`
- `0x180023e80`
- `0x180025610`
- `0x180029824`
- `0x18002d264`
- `0x18002da8c`
- `0x18002e268`
- `0x18002e2f0`
- `0x180040da8`
- `0x180042800`
- `0x1800467c8`
- `0x18004afd0`
- `0x18004b970`
- `0x18004b9d8`
- `0x18004c208`
- `0x18004d838`
- `0x1800510a0`
- `0x180053470`
- `0x1800558c0`
- `0x180056474`
- `0x180063cb8`
- `0x180063cf0`
- `0x180064134`
- `0x180064d14`
- `0x180064e88`
- `0x180064fdc`
- `0x180065774`
- `0x180065ffc`
- `0x180066044`
- `0x1800661cc`
- `0x18006d13c`
- `0x18006d2a0`
- `0x18006d4ec`
- `0x18006d74c`
- `0x18006d9b0`
- `0x18006dbf0`
- `0x1800713d8`
- `0x180071b1c`
- `0x180073ae0`
- `0x180077a54`
- `0x180078078`
- `0x180079fbc`
- `0x18007a4c0`

## callees

- `0x18000aae4`
- `0x180012ed8`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180012eeb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180012eeb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x180012f11`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x180012f11`

## string_xrefs

- `0x180012ef5`: `WindowsDeleteString(_hstring)`

## pseudocode

```c
HSTRING *__fastcall ConnectedStorage::SimpleHStringWrapper::operator=(HSTRING *newString, HSTRING *a2)
{
  HRESULT v4; // eax
  const unsigned __int16 *v5; // r8
  HRESULT v6; // eax
  const unsigned __int16 *v7; // r8

  v4 = WindowsDeleteString(*newString);
  if ( v4 < 0 )
    ConnectedStorage::ReportErrorAndThrow(
      (ConnectedStorage *)(unsigned int)v4,
      (int)L"WindowsDeleteString(_hstring)",
      v5);
  *newString = 0;
  v6 = WindowsDuplicateString(*a2, newString);
  if ( v6 < 0 )
    ConnectedStorage::ReportErrorAndThrow(
      (ConnectedStorage *)(unsigned int)v6,
      (int)L"WindowsDuplicateString(other._hstring, &_hstring)",
      v7);
  return newString;
}

```

## disassembly

```asm
0x180012ed8  mov     [rsp+arg_0], rbx
0x180012edd  push    rdi
0x180012ede  sub     rsp, 20h
0x180012ee2  mov     rbx, rcx
0x180012ee5  mov     rdi, rdx
0x180012ee8  mov     rcx, [rcx]; string
0x180012eeb  call    cs:__imp_WindowsDeleteString
0x180012ef1  test    eax, eax
0x180012ef3  jns     short loc_180012F04
0x180012ef5  lea     rdx, aWindowsdeletes; "WindowsDeleteString(_hstring)"
0x180012efc  mov     ecx, eax; this
0x180012efe  call    ?ReportErrorAndThrow@ConnectedStorage@@YAXJPEBG@Z; ConnectedStorage::ReportErrorAndThrow(long,ushort const *)
0x180012f04  mov     qword ptr [rbx], 0
0x180012f0b  mov     rdx, rbx; newString
0x180012f0e  mov     rcx, [rdi]; string
0x180012f11  call    cs:__imp_WindowsDuplicateString
0x180012f17  test    eax, eax
0x180012f19  jns     short loc_180012F2A
0x180012f1b  lea     rdx, aWindowsduplica_4; "WindowsDuplicateString(other._hstring, "...
0x180012f22  mov     ecx, eax; this
0x180012f24  call    ?ReportErrorAndThrow@ConnectedStorage@@YAXJPEBG@Z; ConnectedStorage::ReportErrorAndThrow(long,ushort const *)
0x180012f2a  mov     rax, rbx
0x180012f2d  mov     rbx, [rsp+28h+arg_0]
0x180012f32  add     rsp, 20h
0x180012f36  pop     rdi
0x180012f37  retn
```
