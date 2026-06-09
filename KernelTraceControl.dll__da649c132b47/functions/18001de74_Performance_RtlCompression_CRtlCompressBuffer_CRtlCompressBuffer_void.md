# Performance::RtlCompression::CRtlCompressBuffer::CRtlCompressBuffer(void)

- ea: `0x18001de74`
- end: `0x18001defc`
- name: `??0CRtlCompressBuffer@RtlCompression@Performance@@QEAA@XZ`
- size: `136`
- prototype: `__int64 __fastcall(Performance::RtlCompression::CRtlCompressBuffer *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001c3dc`
- `0x18001defc`

## callees

- `0x18001de74`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x18001de94`
- `KERNEL32!GetModuleHandleW` at `0x18001dec0`
- `KERNEL32!GetModuleHandleW` at `0x18001de94`
- `KERNEL32!GetModuleHandleW` at `0x18001dec0`
- `KERNEL32!GetProcAddress` at `0x18001dee2`
- `KERNEL32!GetProcAddress` at `0x18001dee2`

## string_xrefs

- `0x18001de8d`: `ntdll.dll`
- `0x18001deb9`: `ntdll.dll`
- `0x18001dedb`: `RtlCompressBuffer`

## pseudocode

```c
Performance::RtlCompression::CRtlCompressBuffer *__fastcall Performance::RtlCompression::CRtlCompressBuffer::CRtlCompressBuffer(
        Performance::RtlCompression::CRtlCompressBuffer *this)
{
  char v1; // al
  FARPROC ProcAddress; // rbx
  HMODULE v4; // rcx

  v1 = Performance::RtlCompression::g_hNtDllModule;
  ProcAddress = 0;
  if ( !Performance::RtlCompression::g_hNtDllModule )
  {
    hModule = GetModuleHandleW(L"ntdll.dll");
    v1 = 1;
    Performance::RtlCompression::g_hNtDllModule = 1;
  }
  v4 = hModule;
  if ( hModule )
  {
    if ( !v1 )
    {
      hModule = GetModuleHandleW(L"ntdll.dll");
      v4 = hModule;
      Performance::RtlCompression::g_hNtDllModule = 1;
    }
    ProcAddress = GetProcAddress(v4, "RtlCompressBuffer");
  }
  *(_QWORD *)this = ProcAddress;
  return this;
}

```

## disassembly

```asm
0x18001de74  mov     [rsp+arg_0], rbx
0x18001de79  push    rdi
0x18001de7a  sub     rsp, 20h
0x18001de7e  mov     al, cs:?g_hNtDllModule@RtlCompression@Performance@@3VCNtDllModuleHandle@12@A; Performance::RtlCompression::CNtDllModuleHandle Performance::RtlCompression::g_hNtDllModule
0x18001de84  xor     ebx, ebx
0x18001de86  mov     rdi, rcx
0x18001de89  test    al, al
0x18001de8b  jnz     short loc_18001DEA9
0x18001de8d  lea     rcx, LibFileName; "ntdll.dll"
0x18001de94  call    cs:__imp_GetModuleHandleW
0x18001de9a  mov     cs:hModule, rax
0x18001dea1  mov     al, 1
0x18001dea3  mov     cs:?g_hNtDllModule@RtlCompression@Performance@@3VCNtDllModuleHandle@12@A, al; Performance::RtlCompression::CNtDllModuleHandle Performance::RtlCompression::g_hNtDllModule
0x18001dea9  mov     rcx, cs:hModule
0x18001deb0  test    rcx, rcx
0x18001deb3  jz      short loc_18001DEEB
0x18001deb5  test    al, al
0x18001deb7  jnz     short loc_18001DEDB
0x18001deb9  lea     rcx, LibFileName; "ntdll.dll"
0x18001dec0  call    cs:__imp_GetModuleHandleW
0x18001dec6  mov     cs:hModule, rax
0x18001decd  mov     rcx, cs:hModule; hModule
0x18001ded4  mov     cs:?g_hNtDllModule@RtlCompression@Performance@@3VCNtDllModuleHandle@12@A, 1; Performance::RtlCompression::CNtDllModuleHandle Performance::RtlCompression::g_hNtDllModule
0x18001dedb  lea     rdx, aRtlcompressbuf; "RtlCompressBuffer"
0x18001dee2  call    cs:__imp_GetProcAddress
0x18001dee8  mov     rbx, rax
0x18001deeb  mov     [rdi], rbx
0x18001deee  mov     rax, rdi
0x18001def1  mov     rbx, [rsp+28h+arg_0]
0x18001def6  add     rsp, 20h
0x18001defa  pop     rdi
0x18001defb  retn
```
