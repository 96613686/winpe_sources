# PrintUsage(void)

- ea: `0x1400065ec`
- end: `0x140006630`
- name: `?PrintUsage@@YAXXZ`
- size: `68`
- prototype: `void(void)`
- caller_count: `3`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x140008150`
- `0x14001125f`
- `0x140011295`

## callees

- `0x140002d8c`

## string_xrefs

- `0x140006614`: `AppHostNameRegistrationVerifier.exe [[hostname] [packageFamilyName] [filePath]]\n`
- `0x140006620`: `Validates the specified packageFamilyName against the provided JSON file for the provided hostname\n`

## pseudocode

```c
void PrintUsage(void)
{
  wprintf(L"Usage:\n");
  wprintf(L"AppHostNameRegistrationVerifier.exe -f\n");
  wprintf(L"Force revalidation for all registered apps\n\n");
  wprintf(L"AppHostNameRegistrationVerifier.exe [[hostname] [packageFamilyName] [filePath]]\n");
  wprintf(L"Validates the specified packageFamilyName against the provided JSON file for the provided hostname\n");
}

```

## disassembly

```asm
0x1400065ec  sub     rsp, 28h
0x1400065f0  lea     rcx, aUsage; "Usage:\n"
0x1400065f7  call    wprintf
0x1400065fc  lea     rcx, aApphostnamereg; "AppHostNameRegistrationVerifier.exe -f"...
0x140006603  call    wprintf
0x140006608  lea     rcx, aForceRevalidat; "Force revalidation for all registered a"...
0x14000660f  call    wprintf
0x140006614  lea     rcx, aApphostnamereg_0; "AppHostNameRegistrationVerifier.exe [[h"...
0x14000661b  call    wprintf
0x140006620  lea     rcx, aValidatesTheSp; "Validates the specified packageFamilyNa"...
0x140006627  add     rsp, 28h
0x14000662b  jmp     wprintf
```
