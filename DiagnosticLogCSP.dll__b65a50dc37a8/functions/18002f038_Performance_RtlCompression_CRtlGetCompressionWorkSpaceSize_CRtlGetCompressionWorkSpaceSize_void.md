# Performance::RtlCompression::CRtlGetCompressionWorkSpaceSize::CRtlGetCompressionWorkSpaceSize(void)

- ea: `0x18002f038`
- end: `0x18002f0cb`
- name: `??0CRtlGetCompressionWorkSpaceSize@RtlCompression@Performance@@QEAA@XZ`
- size: `147`
- prototype: `__int64 __fastcall(Performance::RtlCompression::CRtlGetCompressionWorkSpaceSize *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18002edd0`
- `0x1800304d0`

## callees

- `0x18002f038`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18002f052`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18002f085`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18002f052`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18002f085`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002f0ae`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002f0ae`

## string_xrefs

- `0x18002f04b`: `ntdll.dll`
- `0x18002f07e`: `ntdll.dll`
- `0x18002f0a7`: `RtlGetCompressionWorkSpaceSize`

## pseudocode

```c
Performance::RtlCompression::CRtlGetCompressionWorkSpaceSize *__fastcall Performance::RtlCompression::CRtlGetCompressionWorkSpaceSize::CRtlGetCompressionWorkSpaceSize(
        Performance::RtlCompression::CRtlGetCompressionWorkSpaceSize *this)
{
  char v1; // al
  HMODULE v3; // rcx
  FARPROC ProcAddress; // rax

  v1 = Performance::RtlCompression::g_hNtDllModule;
  if ( !Performance::RtlCompression::g_hNtDllModule )
  {
    hModule = GetModuleHandleW(L"ntdll.dll");
    v1 = 1;
    Performance::RtlCompression::g_hNtDllModule = 1;
  }
  v3 = hModule;
  if ( hModule )
  {
    if ( !v1 )
    {
      hModule = GetModuleHandleW(L"ntdll.dll");
      v3 = hModule;
      Performance::RtlCompression::g_hNtDllModule = 1;
    }
    ProcAddress = GetProcAddress(v3, "RtlGetCompressionWorkSpaceSize");
  }
  else
  {
    ProcAddress = 0;
  }
  *(_QWORD *)this = ProcAddress;
  return this;
}

```

## disassembly

```asm
0x18002f038  push    rbx
0x18002f03a  sub     rsp, 20h
0x18002f03e  mov     al, cs:?g_hNtDllModule@RtlCompression@Performance@@3VCNtDllModuleHandle@12@A; Performance::RtlCompression::CNtDllModuleHandle Performance::RtlCompression::g_hNtDllModule
0x18002f044  mov     rbx, rcx
0x18002f047  test    al, al
0x18002f049  jnz     short loc_18002F06E
0x18002f04b  lea     rcx, ModuleName; "ntdll.dll"
0x18002f052  call    cs:__imp_GetModuleHandleW
0x18002f059  nop     dword ptr [rax+rax+00h]
0x18002f05e  mov     cs:hModule, rax
0x18002f065  mov     al, 1
0x18002f067  nop
0x18002f068  mov     cs:?g_hNtDllModule@RtlCompression@Performance@@3VCNtDllModuleHandle@12@A, al; Performance::RtlCompression::CNtDllModuleHandle Performance::RtlCompression::g_hNtDllModule
0x18002f06e  mov     rcx, cs:hModule
0x18002f075  test    rcx, rcx
0x18002f078  jz      short loc_18002F0BC
0x18002f07a  test    al, al
0x18002f07c  jnz     short loc_18002F0A7
0x18002f07e  lea     rcx, ModuleName; "ntdll.dll"
0x18002f085  call    cs:__imp_GetModuleHandleW
0x18002f08c  nop     dword ptr [rax+rax+00h]
0x18002f091  mov     cs:hModule, rax
0x18002f098  nop
0x18002f099  mov     rcx, cs:hModule; hModule
0x18002f0a0  mov     cs:?g_hNtDllModule@RtlCompression@Performance@@3VCNtDllModuleHandle@12@A, 1; Performance::RtlCompression::CNtDllModuleHandle Performance::RtlCompression::g_hNtDllModule
0x18002f0a7  lea     rdx, aRtlgetcompress; "RtlGetCompressionWorkSpaceSize"
0x18002f0ae  call    cs:__imp_GetProcAddress
0x18002f0b5  nop     dword ptr [rax+rax+00h]
0x18002f0ba  jmp     short loc_18002F0BE
0x18002f0bc  xor     eax, eax
0x18002f0be  mov     [rbx], rax
0x18002f0c1  mov     rax, rbx
0x18002f0c4  add     rsp, 20h
0x18002f0c8  pop     rbx
0x18002f0c9  retn
```
