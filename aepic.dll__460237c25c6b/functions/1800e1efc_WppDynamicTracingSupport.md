# WppDynamicTracingSupport

- ea: `0x1800e1efc`
- end: `0x1800e1f9e`
- name: `WppDynamicTracingSupport`
- size: `162`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800e1fb0`

## callees

- `0x1800e1efc`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800e1f75`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800e1f21`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800e1f4d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800e1f21`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800e1f4d`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x1800e1f09`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x1800e1f09`

## pseudocode

```c
int WppDynamicTracingSupport()
{
  HMODULE LibraryW; // rax
  HMODULE v1; // rbx
  __int64 (__usercall *v2)@<rax>(TRACEHANDLE@<rcx>, __int64); // rax

  LibraryW = LoadLibraryW(L"advapi32");
  v1 = LibraryW;
  if ( !LibraryW )
  {
    v2 = TraceMessageW2kVa;
    pfnWppTraceMessage = (__int64 (__fastcall *)(int, int, int, int, char))TraceMessageW2k;
    pfnWppTraceMessageVa = TraceMessageW2kVa;
    return (int)v2;
  }
  pfnWppTraceMessage = (__int64 (__fastcall *)(int, int, int, int, char))GetProcAddress(LibraryW, "TraceMessage");
  if ( !pfnWppTraceMessage )
  {
    pfnWppTraceMessage = (__int64 (__fastcall *)(int, int, int, int, char))TraceMessageW2k;
LABEL_5:
    pfnWppTraceMessageVa = TraceMessageW2kVa;
    goto LABEL_6;
  }
  pfnWppTraceMessageVa = (__int64 (__usercall *)@<rax>(TRACEHANDLE@<rcx>, __int64))GetProcAddress(v1, "TraceMessageVa");
  if ( !pfnWppTraceMessageVa )
    goto LABEL_5;
LABEL_6:
  LODWORD(v2) = FreeLibrary(v1);
  return (int)v2;
}

```

## disassembly

```asm
0x1800e1efc  push    rbx
0x1800e1efe  sub     rsp, 20h
0x1800e1f02  lea     rcx, aAdvapi32; "advapi32"
0x1800e1f09  call    cs:__imp_LoadLibraryW
0x1800e1f0f  mov     rbx, rax
0x1800e1f12  test    rax, rax
0x1800e1f15  jz      short loc_1800E1F7C
0x1800e1f17  lea     rdx, aTracemessage; "TraceMessage"
0x1800e1f1e  mov     rcx, rax; hModule
0x1800e1f21  call    cs:__imp_GetProcAddress
0x1800e1f27  mov     cs:pfnWppTraceMessage, rax
0x1800e1f2e  test    rax, rax
0x1800e1f31  jnz     short loc_1800E1F43
0x1800e1f33  lea     rcx, TraceMessageW2k
0x1800e1f3a  mov     cs:pfnWppTraceMessage, rcx
0x1800e1f41  jmp     short loc_1800E1F5F
0x1800e1f43  lea     rdx, aTracemessageva; "TraceMessageVa"
0x1800e1f4a  mov     rcx, rbx; hModule
0x1800e1f4d  call    cs:__imp_GetProcAddress
0x1800e1f53  mov     cs:pfnWppTraceMessageVa, rax
0x1800e1f5a  test    rax, rax
0x1800e1f5d  jnz     short loc_1800E1F6D
0x1800e1f5f  lea     rax, TraceMessageW2kVa
0x1800e1f66  mov     cs:pfnWppTraceMessageVa, rax
0x1800e1f6d  mov     rcx, rbx
0x1800e1f70  add     rsp, 20h
0x1800e1f74  pop     rbx
0x1800e1f75  jmp     cs:__imp_FreeLibrary
0x1800e1f7c  lea     rcx, TraceMessageW2k
0x1800e1f83  lea     rax, TraceMessageW2kVa
0x1800e1f8a  mov     cs:pfnWppTraceMessage, rcx
0x1800e1f91  mov     cs:pfnWppTraceMessageVa, rax
0x1800e1f98  add     rsp, 20h
0x1800e1f9c  pop     rbx
0x1800e1f9d  retn
```
