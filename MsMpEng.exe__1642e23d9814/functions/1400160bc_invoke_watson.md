# _invoke_watson

- ea: `0x1400160bc`
- end: `0x140016103`
- name: `_invoke_watson`
- size: `71`
- prototype: `void __cdecl __noreturn(const wchar_t *Expression, const wchar_t *FunctionName, const wchar_t *FileName, unsigned int LineNo, uintptr_t Reserved)`
- caller_count: `15`
- callee_count: `2`
- tags: ``

## callers

- `0x140003e40`
- `0x140004198`
- `0x140004214`
- `0x140015fe4`
- `0x1400180f4`
- `0x140019e88`
- `0x14001a500`
- `0x14001d684`
- `0x14001da84`
- `0x14001de20`
- `0x14001e184`
- `0x14001f2d4`
- `0x14002213c`
- `0x1400223bc`
- `0x140028378`

## callees

- `0x140015dd0`
- `0x1400160bc`

## import_xrefs

- `KERNEL32!TerminateProcess` at `0x1400160fc`
- `KERNEL32!GetCurrentProcess` at `0x1400160ea`
- `KERNEL32!GetCurrentProcess` at `0x1400160ea`
- `KERNEL32!IsProcessorFeaturePresent` at `0x1400160c5`
- `KERNEL32!IsProcessorFeaturePresent` at `0x1400160c5`

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
  sub_140015DD0(2, 3221226519LL);
  CurrentProcess = GetCurrentProcess();
  TerminateProcess(CurrentProcess, 0xC0000417);
}

```

## disassembly

```asm
0x1400160bc  sub     rsp, 28h
0x1400160c0  mov     ecx, 17h; ProcessorFeature
0x1400160c5  call    cs:IsProcessorFeaturePresent
0x1400160cb  test    eax, eax
0x1400160cd  jz      short loc_1400160D6
0x1400160cf  mov     ecx, 5
0x1400160d4  int     29h; Win8: RtlFailFast(ecx)
0x1400160d6  mov     r8d, 1
0x1400160dc  mov     edx, 0C0000417h
0x1400160e1  lea     ecx, [r8+1]
0x1400160e5  call    sub_140015DD0
0x1400160ea  call    cs:GetCurrentProcess
0x1400160f0  mov     rcx, rax
0x1400160f3  mov     edx, 0C0000417h
0x1400160f8  add     rsp, 28h
0x1400160fc  jmp     cs:TerminateProcess
```
