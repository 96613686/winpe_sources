# Performance::RtlCompression::CNtDllModuleHandle::operator HINSTANCE__ *(void)

- ea: `0x18007e890`
- end: `0x18007e8c5`
- name: `??BCNtDllModuleHandle@RtlCompression@Performance@@QEAAPEAUHINSTANCE__@@XZ`
- size: `53`
- prototype: `__int64(void)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18007e650`
- `0x18007e68c`

## callees

- `0x18007e890`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleW` at `0x18007e8a4`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleW` at `0x18007e8a4`

## string_xrefs

- `0x18007e89d`: `ntdll.dll`

## pseudocode

```c
__int64 Performance::RtlCompression::CNtDllModuleHandle::operator HINSTANCE__ *()
{
  if ( !Performance::RtlCompression::g_hNtDllModule )
  {
    qword_1800BEA88 = (__int64)GetModuleHandleW(L"ntdll.dll");
    Performance::RtlCompression::g_hNtDllModule = 1;
  }
  return qword_1800BEA88;
}

```

## disassembly

```asm
0x18007e890  sub     rsp, 28h
0x18007e894  cmp     cs:?g_hNtDllModule@RtlCompression@Performance@@3VCNtDllModuleHandle@12@A, 0; Performance::RtlCompression::CNtDllModuleHandle Performance::RtlCompression::g_hNtDllModule
0x18007e89b  jnz     short loc_18007E8B9
0x18007e89d  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x18007e8a4  call    cs:__imp_GetModuleHandleW
0x18007e8aa  mov     cs:qword_1800BEA88, rax
0x18007e8b1  nop
0x18007e8b2  mov     cs:?g_hNtDllModule@RtlCompression@Performance@@3VCNtDllModuleHandle@12@A, 1; Performance::RtlCompression::CNtDllModuleHandle Performance::RtlCompression::g_hNtDllModule
0x18007e8b9  mov     rax, cs:qword_1800BEA88
0x18007e8c0  add     rsp, 28h
0x18007e8c4  retn
```
