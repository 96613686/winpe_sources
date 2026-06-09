# XpsToPwgrConverter::XpsToPwgrConverter::WritePage(IXpsOMPage *)

- ea: `0x180009730`
- end: `0x180009755`
- name: `?WritePage@XpsToPwgrConverter@1@UEAAJPEAUIXpsOMPage@@@Z`
- size: `37`
- prototype: `__int64 __fastcall(XpsToPwgrConverter::XpsToPwgrConverter *__hidden this, struct IXpsOMPage *)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180008d30`

## pseudocode

```c
__int64 __fastcall XpsToPwgrConverter::XpsToPwgrConverter::WritePage(
        XpsToPwgrConverter::XpsToPwgrConverter *this,
        struct IXpsOMPage *a2)
{
  _QWORD v3[3]; // [rsp+20h] [rbp-18h] BYREF
  struct IXpsOMPage *v4; // [rsp+48h] [rbp+10h] BYREF

  v4 = a2;
  v3[0] = this;
  v3[1] = &v4;
  return PrintCore::CaptureAndConvertExceptionToHR__lambda_b8f3a0af17a6902109e04270954bca09___(v3);
}

```

## disassembly

```asm
0x180009730  mov     r11, rsp
0x180009733  mov     [r11+10h], rdx
0x180009737  sub     rsp, 38h
0x18000973b  mov     [r11-18h], rcx
0x18000973f  lea     rax, [r11+10h]
0x180009743  lea     rcx, [r11-18h]
0x180009747  mov     [r11-10h], rax
0x18000974b  call    PrintCore__CaptureAndConvertExceptionToHR__lambda_b8f3a0af17a6902109e04270954bca09___
0x180009750  add     rsp, 38h
0x180009754  retn
```
