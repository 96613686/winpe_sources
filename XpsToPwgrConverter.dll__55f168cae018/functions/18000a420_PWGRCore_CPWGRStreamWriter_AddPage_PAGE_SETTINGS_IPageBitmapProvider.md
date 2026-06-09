# PWGRCore::CPWGRStreamWriter::AddPage(_PAGE_SETTINGS,IPageBitmapProvider *)

- ea: `0x18000a420`
- end: `0x18000a449`
- name: `?AddPage@CPWGRStreamWriter@PWGRCore@@UEAAJU_PAGE_SETTINGS@@PEAUIPageBitmapProvider@@@Z`
- size: `41`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x180009e3c`

## pseudocode

```c
__int64 __fastcall PWGRCore::CPWGRStreamWriter::AddPage(__int64 a1, __int64 a2, __int64 a3)
{
  _QWORD v4[5]; // [rsp+20h] [rbp-28h] BYREF
  __int64 v5; // [rsp+60h] [rbp+18h] BYREF

  v5 = a3;
  v4[1] = a1;
  v4[2] = &v5;
  v4[0] = a2;
  return PrintCore::CaptureAndConvertExceptionToHR__lambda_15a8deb8db5b9364ac518ff8bab5a595___((__int64)v4);
}

```

## disassembly

```asm
0x18000a420  mov     r11, rsp
0x18000a423  mov     [r11+18h], r8
0x18000a427  sub     rsp, 48h
0x18000a42b  mov     [r11-20h], rcx
0x18000a42f  lea     rax, [r11+18h]
0x18000a433  lea     rcx, [r11-28h]
0x18000a437  mov     [r11-18h], rax
0x18000a43b  mov     [r11-28h], rdx
0x18000a43f  call    PrintCore__CaptureAndConvertExceptionToHR__lambda_15a8deb8db5b9364ac518ff8bab5a595___
0x18000a444  add     rsp, 48h
0x18000a448  retn
```
