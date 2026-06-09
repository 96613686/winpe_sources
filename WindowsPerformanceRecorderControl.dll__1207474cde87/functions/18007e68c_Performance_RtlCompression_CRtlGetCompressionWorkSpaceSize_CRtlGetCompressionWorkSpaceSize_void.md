# Performance::RtlCompression::CRtlGetCompressionWorkSpaceSize::CRtlGetCompressionWorkSpaceSize(void)

- ea: `0x18007e68c`
- end: `0x18007e6c0`
- name: `??0CRtlGetCompressionWorkSpaceSize@RtlCompression@Performance@@QEAA@XZ`
- size: `52`
- prototype: `Performance::RtlCompression::CRtlGetCompressionWorkSpaceSize *__fastcall(Performance::RtlCompression::CRtlGetCompressionWorkSpaceSize *this)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18007e4dc`
- `0x18007f7b0`

## callees

- `0x18007e68c`
- `0x18007e890`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18007e6ae`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18007e6ae`

## string_xrefs

- `0x18007e6a7`: `RtlGetCompressionWorkSpaceSize`

## pseudocode

```c
Performance::RtlCompression::CRtlGetCompressionWorkSpaceSize *__fastcall Performance::RtlCompression::CRtlGetCompressionWorkSpaceSize::CRtlGetCompressionWorkSpaceSize(
        Performance::RtlCompression::CRtlGetCompressionWorkSpaceSize *this)
{
  FARPROC ProcAddress; // rax
  HMODULE v3; // rax

  ProcAddress = (FARPROC)Performance::RtlCompression::CNtDllModuleHandle::operator HINSTANCE__ *();
  if ( ProcAddress )
  {
    v3 = (HMODULE)Performance::RtlCompression::CNtDllModuleHandle::operator HINSTANCE__ *();
    ProcAddress = GetProcAddress(v3, "RtlGetCompressionWorkSpaceSize");
  }
  *(_QWORD *)this = ProcAddress;
  return this;
}

```

## disassembly

```asm
0x18007e68c  push    rbx
0x18007e68e  sub     rsp, 20h
0x18007e692  mov     rbx, rcx
0x18007e695  call    ??BCNtDllModuleHandle@RtlCompression@Performance@@QEAAPEAUHINSTANCE__@@XZ; Performance::RtlCompression::CNtDllModuleHandle::operator HINSTANCE__ *(void)
0x18007e69a  test    rax, rax
0x18007e69d  jz      short loc_18007E6B4
0x18007e69f  call    ??BCNtDllModuleHandle@RtlCompression@Performance@@QEAAPEAUHINSTANCE__@@XZ; Performance::RtlCompression::CNtDllModuleHandle::operator HINSTANCE__ *(void)
0x18007e6a4  mov     rcx, rax; hModule
0x18007e6a7  lea     rdx, aRtlgetcompress; "RtlGetCompressionWorkSpaceSize"
0x18007e6ae  call    cs:__imp_GetProcAddress
0x18007e6b4  mov     [rbx], rax
0x18007e6b7  mov     rax, rbx
0x18007e6ba  add     rsp, 20h
0x18007e6be  pop     rbx
0x18007e6bf  retn
```
