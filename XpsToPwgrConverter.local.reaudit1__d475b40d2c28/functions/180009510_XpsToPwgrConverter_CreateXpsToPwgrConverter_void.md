# XpsToPwgrConverter::CreateXpsToPwgrConverter(void * *)

- ea: `0x180009510`
- end: `0x180009531`
- name: `?CreateXpsToPwgrConverter@XpsToPwgrConverter@@YAJPEAPEAX@Z`
- size: `33`
- prototype: `__int64 __fastcall(XpsToPwgrConverter *__hidden this, void **)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180008d60`

## pseudocode

```c
__int64 __fastcall XpsToPwgrConverter::CreateXpsToPwgrConverter(XpsToPwgrConverter *this, void **a2)
{
  XpsToPwgrConverter *v3; // [rsp+30h] [rbp+8h] BYREF
  XpsToPwgrConverter **v4; // [rsp+38h] [rbp+10h] BYREF

  v3 = this;
  v4 = &v3;
  return PrintCore::CaptureAndConvertExceptionToHR__lambda_f875aa78a1bc3291fee2044814ab3208___(&v4, a2);
}

```

## disassembly

```asm
0x180009510  mov     r11, rsp
0x180009513  mov     [r11+8], rcx
0x180009517  sub     rsp, 28h
0x18000951b  lea     rax, [r11+8]
0x18000951f  lea     rcx, [r11+10h]
0x180009523  mov     [r11+10h], rax
0x180009527  call    PrintCore__CaptureAndConvertExceptionToHR__lambda_f875aa78a1bc3291fee2044814ab3208___
0x18000952c  add     rsp, 28h
0x180009530  retn
```
