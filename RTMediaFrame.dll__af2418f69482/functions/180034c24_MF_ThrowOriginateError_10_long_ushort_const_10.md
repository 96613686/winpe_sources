# MF::ThrowOriginateError<10>(long,ushort const (&)[10])

- ea: `0x180034c24`
- end: `0x180034c6f`
- name: `??$ThrowOriginateError@$09@MF@@YAXJAEAY09$$CBG@Z`
- size: `75`
- prototype: `void __noreturn(void)`
- caller_count: `13`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180004880`
- `0x18000a100`
- `0x18000dfc8`
- `0x18000e178`
- `0x18001a6e0`
- `0x18001a840`
- `0x18001a960`
- `0x18001aa80`
- `0x18001e07c`
- `0x18002449c`
- `0x180024a7c`
- `0x180024c88`
- `0x180025358`

## callees

- `0x18002749c`

## import_xrefs

- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateErrorW` at `0x180034c39`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateErrorW` at `0x180034c39`

## string_xrefs

- `0x180034c28`: `Read only`

## pseudocode

```c
void __noreturn MF::ThrowOriginateError<10>()
{
  void **pExceptionObject; // [rsp+20h] [rbp-28h] BYREF
  int v1; // [rsp+28h] [rbp-20h]
  __int128 v2; // [rsp+30h] [rbp-18h]

  RoOriginateErrorW(2147942405LL, 9, L"Read only");
  pExceptionObject = &_com_error::`vftable';
  v1 = -2147024891;
  v2 = 0;
  throw (_com_error *)&pExceptionObject;
}

```

## disassembly

```asm
0x180034c24  sub     rsp, 48h
0x180034c28  lea     r8, aReadOnly; "Read only"
0x180034c2f  mov     edx, 9
0x180034c34  mov     ecx, 80070005h
0x180034c39  call    cs:__imp_RoOriginateErrorW
0x180034c3f  nop
0x180034c40  lea     rax, ??_7_com_error@@6B@; const _com_error::`vftable'
0x180034c47  mov     [rsp+48h+pExceptionObject], rax
0x180034c4c  mov     [rsp+48h+var_20], 80070005h
0x180034c54  xorps   xmm0, xmm0
0x180034c57  movdqu  [rsp+48h+var_18], xmm0
0x180034c5d  lea     rdx, _TI1?AV_com_error@@; pThrowInfo
0x180034c64  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x180034c69  call    _CxxThrowException_0
```
