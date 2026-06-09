# Performance::RtlCompression::CRtlCompressBuffer::CRtlCompressBuffer(void)

- ea: `0x18007e650`
- end: `0x18007e684`
- name: `??0CRtlCompressBuffer@RtlCompression@Performance@@QEAA@XZ`
- size: `52`
- prototype: `Performance::RtlCompression::CRtlCompressBuffer *__fastcall(Performance::RtlCompression::CRtlCompressBuffer *this)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18007e4dc`
- `0x18007f7b0`

## callees

- `0x18007e650`
- `0x18007e890`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18007e672`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18007e672`

## string_xrefs

- `0x18007e66b`: `RtlCompressBuffer`

## pseudocode

```c
Performance::RtlCompression::CRtlCompressBuffer *__fastcall Performance::RtlCompression::CRtlCompressBuffer::CRtlCompressBuffer(
        Performance::RtlCompression::CRtlCompressBuffer *this)
{
  FARPROC ProcAddress; // rax
  HMODULE v3; // rax

  ProcAddress = (FARPROC)Performance::RtlCompression::CNtDllModuleHandle::operator HINSTANCE__ *();
  if ( ProcAddress )
  {
    v3 = (HMODULE)Performance::RtlCompression::CNtDllModuleHandle::operator HINSTANCE__ *();
    ProcAddress = GetProcAddress(v3, "RtlCompressBuffer");
  }
  *(_QWORD *)this = ProcAddress;
  return this;
}

```

## disassembly

```asm
0x18007e650  push    rbx
0x18007e652  sub     rsp, 20h
0x18007e656  mov     rbx, rcx
0x18007e659  call    ??BCNtDllModuleHandle@RtlCompression@Performance@@QEAAPEAUHINSTANCE__@@XZ; Performance::RtlCompression::CNtDllModuleHandle::operator HINSTANCE__ *(void)
0x18007e65e  test    rax, rax
0x18007e661  jz      short loc_18007E678
0x18007e663  call    ??BCNtDllModuleHandle@RtlCompression@Performance@@QEAAPEAUHINSTANCE__@@XZ; Performance::RtlCompression::CNtDllModuleHandle::operator HINSTANCE__ *(void)
0x18007e668  mov     rcx, rax; hModule
0x18007e66b  lea     rdx, aRtlcompressbuf; "RtlCompressBuffer"
0x18007e672  call    cs:__imp_GetProcAddress
0x18007e678  mov     [rbx], rax
0x18007e67b  mov     rax, rbx
0x18007e67e  add     rsp, 20h
0x18007e682  pop     rbx
0x18007e683  retn
```
