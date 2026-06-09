# __invoke_watson

- ea: `0x40de81`
- end: `0x40deb5`
- name: `__invoke_watson`
- size: `52`
- prototype: `void __cdecl __noreturn(const wchar_t *Expression, const wchar_t *FunctionName, const wchar_t *FileName, unsigned int LineNo, uintptr_t Reserved)`
- caller_count: `7`
- callee_count: `2`
- tags: ``

## callers

- `0x407e6d`
- `0x407ef0`
- `0x40ddf0`
- `0x40de64`
- `0x40e812`
- `0x410078`
- `0x4102a0`

## callees

- `0x40dca8`
- `0x40de81`

## import_xrefs

- `KERNEL32!GetCurrentProcess` at `0x40dea6`
- `KERNEL32!GetCurrentProcess` at `0x40dea6`
- `KERNEL32!TerminateProcess` at `0x40dead`
- `KERNEL32!TerminateProcess` at `0x40dead`
- `KERNEL32!IsProcessorFeaturePresent` at `0x40de83`
- `KERNEL32!IsProcessorFeaturePresent` at `0x40de83`

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
0x40de81  push    17h; ProcessorFeature
0x40de83  call    ds:IsProcessorFeaturePresent
0x40de89  test    eax, eax
0x40de8b  jz      short loc_40DE92
0x40de8d  push    5
0x40de8f  pop     ecx
0x40de90  int     29h; Win8: RtlFailFast(ecx)
0x40de92  push    esi
0x40de93  push    1
0x40de95  mov     esi, 0C0000417h
0x40de9a  push    esi
0x40de9b  push    2
0x40de9d  call    ___acrt_call_reportfault
0x40dea2  add     esp, 0Ch
0x40dea5  push    esi; uExitCode
0x40dea6  call    ds:GetCurrentProcess
0x40deac  push    eax; hProcess
0x40dead  call    ds:TerminateProcess
0x40deb3  pop     esi
0x40deb4  retn
```
