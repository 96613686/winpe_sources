# _invoke_watson

- ea: `0x18000bebc`
- end: `0x18000bf03`
- name: `_invoke_watson`
- size: `71`
- prototype: `void __cdecl __noreturn(const wchar_t *Expression, const wchar_t *FunctionName, const wchar_t *FileName, unsigned int LineNo, uintptr_t Reserved)`
- caller_count: `10`
- callee_count: `2`
- tags: ``

## callers

- `0x18000bdec`
- `0x18000df94`
- `0x1800111c8`
- `0x180011764`
- `0x180012448`
- `0x180012654`
- `0x18001550c`
- `0x18001fd18`
- `0x18001fd54`
- `0x180023a94`

## callees

- `0x18000bc88`
- `0x18000bebc`

## import_xrefs

- `KERNEL32!GetCurrentProcess` at `0x18000beea`
- `KERNEL32!GetCurrentProcess` at `0x18000beea`
- `KERNEL32!TerminateProcess` at `0x18000befc`
- `KERNEL32!IsProcessorFeaturePresent` at `0x18000bec5`
- `KERNEL32!IsProcessorFeaturePresent` at `0x18000bec5`

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
  _acrt_call_reportfault(2, 3221226519LL);
  CurrentProcess = GetCurrentProcess();
  TerminateProcess(CurrentProcess, 0xC0000417);
}

```

## disassembly

```asm
0x18000bebc  sub     rsp, 28h
0x18000bec0  mov     ecx, 17h; ProcessorFeature
0x18000bec5  call    cs:__imp_IsProcessorFeaturePresent
0x18000becb  test    eax, eax
0x18000becd  jz      short loc_18000BED6
0x18000becf  mov     ecx, 5
0x18000bed4  int     29h; Win8: RtlFailFast(ecx)
0x18000bed6  mov     r8d, 1
0x18000bedc  mov     edx, 0C0000417h
0x18000bee1  lea     ecx, [r8+1]
0x18000bee5  call    __acrt_call_reportfault
0x18000beea  call    cs:__imp_GetCurrentProcess
0x18000bef0  mov     rcx, rax
0x18000bef3  mov     edx, 0C0000417h
0x18000bef8  add     rsp, 28h
0x18000befc  jmp     cs:__imp_TerminateProcess
```
