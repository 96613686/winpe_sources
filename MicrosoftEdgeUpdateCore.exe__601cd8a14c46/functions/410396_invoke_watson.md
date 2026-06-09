# __invoke_watson

- ea: `0x410396`
- end: `0x4103ca`
- name: `__invoke_watson`
- size: `52`
- prototype: `void __cdecl __noreturn(const wchar_t *Expression, const wchar_t *FunctionName, const wchar_t *FileName, unsigned int LineNo, uintptr_t Reserved)`
- caller_count: `10`
- callee_count: `2`
- tags: ``

## callers

- `0x4022ed`
- `0x402370`
- `0x410305`
- `0x410379`
- `0x410c9a`
- `0x413e98`
- `0x4140c0`
- `0x4177ad`
- `0x417b48`
- `0x419c78`

## callees

- `0x4101bd`
- `0x410396`

## import_xrefs

- `KERNEL32!GetCurrentProcess` at `0x4103bb`
- `KERNEL32!GetCurrentProcess` at `0x4103bb`
- `KERNEL32!TerminateProcess` at `0x4103c2`
- `KERNEL32!TerminateProcess` at `0x4103c2`
- `KERNEL32!IsProcessorFeaturePresent` at `0x410398`
- `KERNEL32!IsProcessorFeaturePresent` at `0x410398`

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
0x410396  push    17h; ProcessorFeature
0x410398  call    ds:IsProcessorFeaturePresent
0x41039e  test    eax, eax
0x4103a0  jz      short loc_4103A7
0x4103a2  push    5
0x4103a4  pop     ecx
0x4103a5  int     29h; Win8: RtlFailFast(ecx)
0x4103a7  push    esi
0x4103a8  push    1
0x4103aa  mov     esi, 0C0000417h
0x4103af  push    esi
0x4103b0  push    2
0x4103b2  call    ___acrt_call_reportfault
0x4103b7  add     esp, 0Ch
0x4103ba  push    esi; uExitCode
0x4103bb  call    ds:GetCurrentProcess
0x4103c1  push    eax; hProcess
0x4103c2  call    ds:TerminateProcess
0x4103c8  pop     esi
0x4103c9  retn
```
