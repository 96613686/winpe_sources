# AppMon::AppPrinterEndPoint::GetAppSid(void)

- ea: `0x18000eb80`
- end: `0x18000eba1`
- name: `?GetAppSid@AppPrinterEndPoint@AppMon@@UEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ`
- size: `33`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation`

## callees

- `0x180006308`

## pseudocode

```c
__int64 __fastcall AppMon::AppPrinterEndPoint::GetAppSid(__int64 a1, __int64 a2)
{
  std::wstring::wstring(a2, a1 + 1116);
  return a2;
}

```

## disassembly

```asm
0x18000eb80  push    rbx
0x18000eb82  sub     rsp, 30h
0x18000eb86  mov     rbx, rdx
0x18000eb89  lea     rdx, [rcx+45Ch]
0x18000eb90  mov     rcx, rbx
0x18000eb93  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18000eb98  mov     rax, rbx
0x18000eb9b  add     rsp, 30h
0x18000eb9f  pop     rbx
0x18000eba0  retn
```
