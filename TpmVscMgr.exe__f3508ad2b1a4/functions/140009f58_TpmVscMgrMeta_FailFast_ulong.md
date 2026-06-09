# TpmVscMgrMeta::FailFast(ulong)

- ea: `0x140009f58`
- end: `0x140009f82`
- name: `?FailFast@TpmVscMgrMeta@@YAXK@Z`
- size: `42`
- prototype: `void __fastcall(TpmVscMgrMeta *__hidden this, unsigned int)`
- caller_count: `12`
- callee_count: `1`
- tags: ``

## callers

- `0x140005e68`
- `0x140006164`
- `0x140006298`
- `0x14000764c`
- `0x1400076e8`
- `0x140008454`
- `0x140008728`
- `0x140008784`
- `0x140009434`
- `0x1400098b0`
- `0x14000a388`
- `0x14000bb70`

## callees

- `0x140009f58`

## import_xrefs

- `KERNEL32!RaiseFailFastException` at `0x140011e6f`
- `KERNEL32!RaiseFailFastException` at `0x140011e6f`
- `KERNEL32!RaiseException` at `0x140009f75`
- `KERNEL32!RaiseException` at `0x140009f75`

## pseudocode

```c
void __fastcall TpmVscMgrMeta::FailFast(TpmVscMgrMeta *this)
{
  ULONG_PTR Arguments; // [rsp+48h] [rbp+10h] BYREF

  Arguments = (unsigned int)this;
  RaiseException(0xC0000420, 1u, 1u, &Arguments);
}

```

## disassembly

```asm
0x140009f58  sub     rsp, 38h
0x140009f5c  mov     eax, ecx
0x140009f5e  mov     [rsp+38h+Arguments], rax
0x140009f63  lea     r9, [rsp+38h+Arguments]; lpArguments
0x140009f68  mov     edx, 1; dwExceptionFlags
0x140009f6d  mov     r8d, edx; nNumberOfArguments
0x140009f70  mov     ecx, 0C0000420h; dwExceptionCode
0x140009f75  call    cs:__imp_RaiseException
0x140009f7b  jmp     short $+2
0x140009f7d  add     rsp, 38h
0x140009f81  retn
0x140011e50  push    rbp
0x140011e52  sub     rsp, 20h
0x140011e56  mov     rbp, rdx
0x140011e59  mov     [rbp+28h], rcx
0x140011e5d  mov     rax, [rbp+28h]
0x140011e61  mov     rdx, [rax+8]; pContextRecord
0x140011e65  mov     rcx, [rbp+28h]
0x140011e69  xor     r8d, r8d; dwFlags
0x140011e6c  mov     rcx, [rcx]; pExceptionRecord
0x140011e6f  call    cs:__imp_RaiseFailFastException
0x140011e75  mov     dword ptr [rbp+20h], 0FFFFFFFFh
0x140011e7c  mov     eax, [rbp+20h]
0x140011e7f  add     rsp, 20h
0x140011e83  pop     rbp
0x140011e84  retn
```
