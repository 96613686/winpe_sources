# Performance::RtlCompression::CRtlCompressBuffer::CRtlCompressBuffer(void)

- ea: `0x18002ef9c`
- end: `0x18002f02f`
- name: `??0CRtlCompressBuffer@RtlCompression@Performance@@QEAA@XZ`
- size: `147`
- prototype: `__int64 __fastcall(Performance::RtlCompression::CRtlCompressBuffer *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18002edd0`
- `0x1800304d0`

## callees

- `0x18002ef9c`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18002efb6`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18002efe9`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18002efb6`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18002efe9`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002f012`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002f012`

## string_xrefs

- `0x18002efaf`: `ntdll.dll`
- `0x18002efe2`: `ntdll.dll`
- `0x18002f00b`: `RtlCompressBuffer`

## pseudocode

```c
Performance::RtlCompression::CRtlCompressBuffer *__fastcall Performance::RtlCompression::CRtlCompressBuffer::CRtlCompressBuffer(
        Performance::RtlCompression::CRtlCompressBuffer *this)
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
    ProcAddress = GetProcAddress(v3, "RtlCompressBuffer");
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
0x18002ef9c  push    rbx
0x18002ef9e  sub     rsp, 20h
0x18002efa2  mov     al, cs:?g_hNtDllModule@RtlCompression@Performance@@3VCNtDllModuleHandle@12@A; Performance::RtlCompression::CNtDllModuleHandle Performance::RtlCompression::g_hNtDllModule
0x18002efa8  mov     rbx, rcx
0x18002efab  test    al, al
0x18002efad  jnz     short loc_18002EFD2
0x18002efaf  lea     rcx, ModuleName; "ntdll.dll"
0x18002efb6  call    cs:__imp_GetModuleHandleW
0x18002efbd  nop     dword ptr [rax+rax+00h]
0x18002efc2  mov     cs:hModule, rax
0x18002efc9  mov     al, 1
0x18002efcb  nop
0x18002efcc  mov     cs:?g_hNtDllModule@RtlCompression@Performance@@3VCNtDllModuleHandle@12@A, al; Performance::RtlCompression::CNtDllModuleHandle Performance::RtlCompression::g_hNtDllModule
0x18002efd2  mov     rcx, cs:hModule
0x18002efd9  test    rcx, rcx
0x18002efdc  jz      short loc_18002F020
0x18002efde  test    al, al
0x18002efe0  jnz     short loc_18002F00B
0x18002efe2  lea     rcx, ModuleName; "ntdll.dll"
0x18002efe9  call    cs:__imp_GetModuleHandleW
0x18002eff0  nop     dword ptr [rax+rax+00h]
0x18002eff5  mov     cs:hModule, rax
0x18002effc  nop
0x18002effd  mov     rcx, cs:hModule; hModule
0x18002f004  mov     cs:?g_hNtDllModule@RtlCompression@Performance@@3VCNtDllModuleHandle@12@A, 1; Performance::RtlCompression::CNtDllModuleHandle Performance::RtlCompression::g_hNtDllModule
0x18002f00b  lea     rdx, aRtlcompressbuf; "RtlCompressBuffer"
0x18002f012  call    cs:__imp_GetProcAddress
0x18002f019  nop     dword ptr [rax+rax+00h]
0x18002f01e  jmp     short loc_18002F022
0x18002f020  xor     eax, eax
0x18002f022  mov     [rbx], rax
0x18002f025  mov     rax, rbx
0x18002f028  add     rsp, 20h
0x18002f02c  pop     rbx
0x18002f02d  retn
```
