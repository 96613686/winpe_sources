# AppMon::AppPrinterEndPoint::GetAppCmdlineTemplate(void)

- ea: `0x18000eb20`
- end: `0x18000eb41`
- name: `?GetAppCmdlineTemplate@AppPrinterEndPoint@AppMon@@UEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ`
- size: `33`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180006308`

## pseudocode

```c
__int64 __fastcall AppMon::AppPrinterEndPoint::GetAppCmdlineTemplate(__int64 a1, __int64 a2)
{
  std::wstring::wstring(a2, a1 + 2676);
  return a2;
}

```

## disassembly

```asm
0x18000eb20  push    rbx
0x18000eb22  sub     rsp, 30h
0x18000eb26  mov     rbx, rdx
0x18000eb29  lea     rdx, [rcx+0A74h]
0x18000eb30  mov     rcx, rbx
0x18000eb33  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18000eb38  mov     rax, rbx
0x18000eb3b  add     rsp, 30h
0x18000eb3f  pop     rbx
0x18000eb40  retn
```
