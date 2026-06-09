# _invoke_watson

- ea: `0x140006564`
- end: `0x1400065ab`
- name: `_invoke_watson`
- size: `71`
- prototype: `void __cdecl __noreturn(const wchar_t *Expression, const wchar_t *FunctionName, const wchar_t *FileName, unsigned int LineNo, uintptr_t Reserved)`
- caller_count: `6`
- callee_count: `2`
- tags: ``

## callers

- `0x140004b34`
- `0x14000648c`
- `0x1400069b4`
- `0x140006db4`
- `0x140007d40`
- `0x1400080a4`

## callees

- `0x140006278`
- `0x140006564`

## import_xrefs

- `KERNEL32!IsProcessorFeaturePresent` at `0x14000656d`
- `KERNEL32!IsProcessorFeaturePresent` at `0x14000656d`
- `KERNEL32!GetCurrentProcess` at `0x140006592`
- `KERNEL32!GetCurrentProcess` at `0x140006592`
- `KERNEL32!TerminateProcess` at `0x1400065a4`

## pseudocode

```c
void __cdecl __noreturn invoke_watson(
        const wchar_t *Expression,
        const wchar_t *FunctionName,
        const wchar_t *FileName,
        unsigned int LineNo,
        uintptr_t Reserved)
{
  HANDLE CurrentProcess; // rax

  if ( IsProcessorFeaturePresent(0x17u) )
    __fastfail(5u);
  sub_140006278(2, 3221226519LL);
  CurrentProcess = GetCurrentProcess();
  TerminateProcess(CurrentProcess, 0xC0000417);
}

```

## disassembly

```asm
0x140006564  sub     rsp, 28h
0x140006568  mov     ecx, 17h; ProcessorFeature
0x14000656d  call    cs:IsProcessorFeaturePresent
0x140006573  test    eax, eax
0x140006575  jz      short loc_14000657E
0x140006577  mov     ecx, 5
0x14000657c  int     29h; Win8: RtlFailFast(ecx)
0x14000657e  mov     r8d, 1
0x140006584  mov     edx, 0C0000417h
0x140006589  lea     ecx, [r8+1]
0x14000658d  call    sub_140006278
0x140006592  call    cs:GetCurrentProcess
0x140006598  mov     rcx, rax
0x14000659b  mov     edx, 0C0000417h
0x1400065a0  add     rsp, 28h
0x1400065a4  jmp     cs:TerminateProcess
```
