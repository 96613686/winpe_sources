# _wil::make_unique_cotaskmem_PrintJobCleanUpUtil::StalePrintJobInfo_[0]__::_1_::dtor$0

- ea: `0x1800167f7`
- end: `0x18001681d`
- name: `_wil::make_unique_cotaskmem_PrintJobCleanUpUtil::StalePrintJobInfo_[0]__::_1_::dtor$0`
- size: `38`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task`

## callees

- `0x18000a6b8`
- `0x1800167f7`

## pseudocode

```c
void __fastcall wil::make_unique_cotaskmem_PrintJobCleanUpUtil::StalePrintJobInfo__0___::_1_::dtor_0(
        __int64 a1,
        __int64 a2)
{
  if ( (*(_DWORD *)(a2 + 32) & 1) != 0 )
  {
    *(_DWORD *)(a2 + 32) &= ~1u;
    wistd::unique_ptr<PrintJobCleanUpUtil::StalePrintJobInfo [0],wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>::~unique_ptr<PrintJobCleanUpUtil::StalePrintJobInfo [0],wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>(*(void ***)(a2 + 64));
  }
}

```

## disassembly

```asm
0x1800167f7  push    rbp
0x1800167f9  sub     rsp, 20h
0x1800167fd  mov     rbp, rdx
0x180016800  mov     eax, [rbp+20h]
0x180016803  and     eax, 1
0x180016806  test    eax, eax
0x180016808  jz      short loc_180016817
0x18001680a  and     dword ptr [rbp+20h], 0FFFFFFFEh
0x18001680e  mov     rcx, [rbp+40h]
0x180016812  call    ??1?$unique_ptr@$$BY0A@UStalePrintJobInfo@PrintJobCleanUpUtil@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@QEAA@XZ
0x180016817  add     rsp, 20h
0x18001681b  pop     rbp
0x18001681c  retn
```
