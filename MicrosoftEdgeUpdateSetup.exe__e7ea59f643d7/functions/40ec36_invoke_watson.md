# __invoke_watson

- ea: `0x40ec36`
- end: `0x40ec6a`
- name: `__invoke_watson`
- size: `52`
- prototype: `void __cdecl __noreturn(const wchar_t *Expression, const wchar_t *FunctionName, const wchar_t *FileName, unsigned int LineNo, uintptr_t Reserved)`
- caller_count: `7`
- callee_count: `2`
- tags: ``

## callers

- `0x40b62e`
- `0x40ebc2`
- `0x40ef46`
- `0x40f135`
- `0x412ad9`
- `0x412e74`
- `0x415318`

## callees

- `0x40ea7a`
- `0x40ec36`

## import_xrefs

- `KERNEL32!TerminateProcess` at `0x40ec62`
- `KERNEL32!TerminateProcess` at `0x40ec62`
- `KERNEL32!GetCurrentProcess` at `0x40ec5b`
- `KERNEL32!GetCurrentProcess` at `0x40ec5b`
- `KERNEL32!IsProcessorFeaturePresent` at `0x40ec38`
- `KERNEL32!IsProcessorFeaturePresent` at `0x40ec38`

## pseudocode

```c
void __cdecl __noreturn _invoke_watson(
        const wchar_t *Expression,
        const wchar_t *FunctionName,
        const wchar_t *FileName,
        unsigned int LineNo,
        uintptr_t Reserved)
{
  HANDLE CurrentProcess; // eax

  if ( IsProcessorFeaturePresent(0x17u) )
    __fastfail(5u);
  __acrt_call_reportfault(2, -1073740777, 1);
  CurrentProcess = GetCurrentProcess();
  TerminateProcess(CurrentProcess, 0xC0000417);
}

```

## disassembly

```asm
0x40ec36  push    17h; ProcessorFeature
0x40ec38  call    ds:IsProcessorFeaturePresent
0x40ec3e  test    eax, eax
0x40ec40  jz      short loc_40EC47
0x40ec42  push    5
0x40ec44  pop     ecx
0x40ec45  int     29h; Win8: RtlFailFast(ecx)
0x40ec47  push    esi
0x40ec48  push    1
0x40ec4a  mov     esi, 0C0000417h
0x40ec4f  push    esi
0x40ec50  push    2
0x40ec52  call    ___acrt_call_reportfault
0x40ec57  add     esp, 0Ch
0x40ec5a  push    esi; uExitCode
0x40ec5b  call    ds:GetCurrentProcess
0x40ec61  push    eax; hProcess
0x40ec62  call    ds:TerminateProcess
0x40ec68  pop     esi
0x40ec69  retn
```
