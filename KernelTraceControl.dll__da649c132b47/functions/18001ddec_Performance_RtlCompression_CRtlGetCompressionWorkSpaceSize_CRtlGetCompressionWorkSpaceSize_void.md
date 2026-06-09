# Performance::RtlCompression::CRtlGetCompressionWorkSpaceSize::CRtlGetCompressionWorkSpaceSize(void)

- ea: `0x18001ddec`
- end: `0x18001de74`
- name: `??0CRtlGetCompressionWorkSpaceSize@RtlCompression@Performance@@QEAA@XZ`
- size: `136`
- prototype: `__int64 __fastcall(Performance::RtlCompression::CRtlGetCompressionWorkSpaceSize *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001c3dc`
- `0x18001defc`

## callees

- `0x18001ddec`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x18001de0c`
- `KERNEL32!GetModuleHandleW` at `0x18001de38`
- `KERNEL32!GetModuleHandleW` at `0x18001de0c`
- `KERNEL32!GetModuleHandleW` at `0x18001de38`
- `KERNEL32!GetProcAddress` at `0x18001de5a`
- `KERNEL32!GetProcAddress` at `0x18001de5a`

## string_xrefs

- `0x18001de05`: `ntdll.dll`
- `0x18001de31`: `ntdll.dll`
- `0x18001de53`: `RtlGetCompressionWorkSpaceSize`

## pseudocode

```c
Performance::RtlCompression::CRtlGetCompressionWorkSpaceSize *__fastcall Performance::RtlCompression::CRtlGetCompressionWorkSpaceSize::CRtlGetCompressionWorkSpaceSize(
        Performance::RtlCompression::CRtlGetCompressionWorkSpaceSize *this)
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
    ProcAddress = GetProcAddress(v4, "RtlGetCompressionWorkSpaceSize");
  }
  *(_QWORD *)this = ProcAddress;
  return this;
}

```

## disassembly

```asm
0x18001ddec  mov     [rsp+arg_0], rbx
0x18001ddf1  push    rdi
0x18001ddf2  sub     rsp, 20h
0x18001ddf6  mov     al, cs:?g_hNtDllModule@RtlCompression@Performance@@3VCNtDllModuleHandle@12@A; Performance::RtlCompression::CNtDllModuleHandle Performance::RtlCompression::g_hNtDllModule
0x18001ddfc  xor     ebx, ebx
0x18001ddfe  mov     rdi, rcx
0x18001de01  test    al, al
0x18001de03  jnz     short loc_18001DE21
0x18001de05  lea     rcx, LibFileName; "ntdll.dll"
0x18001de0c  call    cs:__imp_GetModuleHandleW
0x18001de12  mov     cs:hModule, rax
0x18001de19  mov     al, 1
0x18001de1b  mov     cs:?g_hNtDllModule@RtlCompression@Performance@@3VCNtDllModuleHandle@12@A, al; Performance::RtlCompression::CNtDllModuleHandle Performance::RtlCompression::g_hNtDllModule
0x18001de21  mov     rcx, cs:hModule
0x18001de28  test    rcx, rcx
0x18001de2b  jz      short loc_18001DE63
0x18001de2d  test    al, al
0x18001de2f  jnz     short loc_18001DE53
0x18001de31  lea     rcx, LibFileName; "ntdll.dll"
0x18001de38  call    cs:__imp_GetModuleHandleW
0x18001de3e  mov     cs:hModule, rax
0x18001de45  mov     rcx, cs:hModule; hModule
0x18001de4c  mov     cs:?g_hNtDllModule@RtlCompression@Performance@@3VCNtDllModuleHandle@12@A, 1; Performance::RtlCompression::CNtDllModuleHandle Performance::RtlCompression::g_hNtDllModule
0x18001de53  lea     rdx, aRtlgetcompress; "RtlGetCompressionWorkSpaceSize"
0x18001de5a  call    cs:__imp_GetProcAddress
0x18001de60  mov     rbx, rax
0x18001de63  mov     [rdi], rbx
0x18001de66  mov     rax, rdi
0x18001de69  mov     rbx, [rsp+28h+arg_0]
0x18001de6e  add     rsp, 20h
0x18001de72  pop     rdi
0x18001de73  retn
```
