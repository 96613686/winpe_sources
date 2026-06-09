# Concurrency::details::Etw::Etw(void)

- ea: `0x1803201e8`
- end: `0x180320308`
- name: `??0Etw@details@Concurrency@@AEAA@XZ`
- size: `288`
- prototype: `__int64 __fastcall(Concurrency::details::Etw *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1803205dc`

## callees

- `0x18030fec8`
- `0x1803201e8`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18032021d`
- `KERNEL32!GetLastError` at `0x18032021d`
- `KERNEL32!GetProcAddress` at `0x180320251`
- `KERNEL32!GetProcAddress` at `0x18032026e`
- `KERNEL32!GetProcAddress` at `0x18032028c`
- `KERNEL32!GetProcAddress` at `0x1803202aa`
- `KERNEL32!GetProcAddress` at `0x1803202c8`
- `KERNEL32!GetProcAddress` at `0x1803202e6`
- `KERNEL32!GetProcAddress` at `0x180320251`
- `KERNEL32!GetProcAddress` at `0x18032026e`
- `KERNEL32!GetProcAddress` at `0x18032028c`
- `KERNEL32!GetProcAddress` at `0x1803202aa`
- `KERNEL32!GetProcAddress` at `0x1803202c8`
- `KERNEL32!GetProcAddress` at `0x1803202e6`
- `KERNEL32!LoadLibraryExW` at `0x18032020e`
- `KERNEL32!LoadLibraryExW` at `0x18032020e`
- `KERNEL32!LoadLibraryW` at `0x180320234`
- `KERNEL32!LoadLibraryW` at `0x180320234`

## string_xrefs

- `0x180320207`: `advapi32.dll`
- `0x18032022d`: `advapi32.dll`

## pseudocode

```c
Concurrency::details::Etw *__fastcall Concurrency::details::Etw::Etw(Concurrency::details::Etw *this)
{
  HMODULE Library; // rbx
  FARPROC ProcAddress; // rcx
  FARPROC v4; // rax
  FARPROC v5; // rax
  FARPROC v6; // rax
  FARPROC v7; // rax
  FARPROC v8; // rax

  Library = LoadLibraryExW(L"advapi32.dll", 0, 0x800u);
  if ( Library || GetLastError() == 87 && (Library = LoadLibraryW(L"advapi32.dll")) != 0 )
  {
    ProcAddress = GetProcAddress(Library, "RegisterTraceGuidsW");
    *(_QWORD *)this = Concurrency::details::Security::EncodePointer(ProcAddress);
    v4 = GetProcAddress(Library, "UnregisterTraceGuids");
    *((_QWORD *)this + 1) = Concurrency::details::Security::EncodePointer(v4);
    v5 = GetProcAddress(Library, "TraceEvent");
    *((_QWORD *)this + 2) = Concurrency::details::Security::EncodePointer(v5);
    v6 = GetProcAddress(Library, "GetTraceLoggerHandle");
    *((_QWORD *)this + 3) = Concurrency::details::Security::EncodePointer(v6);
    v7 = GetProcAddress(Library, "GetTraceEnableLevel");
    *((_QWORD *)this + 4) = Concurrency::details::Security::EncodePointer(v7);
    v8 = GetProcAddress(Library, "GetTraceEnableFlags");
    *((_QWORD *)this + 5) = Concurrency::details::Security::EncodePointer(v8);
  }
  return this;
}

```

## disassembly

```asm
0x1803201e8  push    rdi
0x1803201ea  sub     rsp, 30h
0x1803201ee  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x1803201f7  mov     [rsp+38h+arg_0], rbx
0x1803201fc  mov     rdi, rcx
0x1803201ff  xor     edx, edx; hFile
0x180320201  mov     r8d, 800h; dwFlags
0x180320207  lea     rcx, aAdvapi32Dll; "advapi32.dll"
0x18032020e  call    cs:__imp_LoadLibraryExW
0x180320214  nop
0x180320215  mov     rbx, rax
0x180320218  test    rax, rax
0x18032021b  jnz     short loc_180320247
0x18032021d  call    cs:__imp_GetLastError
0x180320223  nop
0x180320224  cmp     eax, 57h ; 'W'
0x180320227  jnz     loc_1803202FA
0x18032022d  lea     rcx, aAdvapi32Dll; "advapi32.dll"
0x180320234  call    cs:__imp_LoadLibraryW
0x18032023a  nop
0x18032023b  mov     rbx, rax
0x18032023e  test    rax, rax
0x180320241  jz      loc_1803202FA
0x180320247  lea     rdx, aRegistertraceg; "RegisterTraceGuidsW"
0x18032024e  mov     rcx, rbx; hModule
0x180320251  call    cs:__imp_GetProcAddress
0x180320257  nop
0x180320258  mov     rcx, rax; void *
0x18032025b  call    ?EncodePointer@Security@details@Concurrency@@SAPEAXPEAX@Z; Concurrency::details::Security::EncodePointer(void *)
0x180320260  nop
0x180320261  mov     [rdi], rax
0x180320264  lea     rdx, aUnregistertrac; "UnregisterTraceGuids"
0x18032026b  mov     rcx, rbx; hModule
0x18032026e  call    cs:__imp_GetProcAddress
0x180320274  nop
0x180320275  mov     rcx, rax; void *
0x180320278  call    ?EncodePointer@Security@details@Concurrency@@SAPEAXPEAX@Z; Concurrency::details::Security::EncodePointer(void *)
0x18032027d  nop
0x18032027e  mov     [rdi+8], rax
0x180320282  lea     rdx, aTraceevent; "TraceEvent"
0x180320289  mov     rcx, rbx; hModule
0x18032028c  call    cs:__imp_GetProcAddress
0x180320292  nop
0x180320293  mov     rcx, rax; void *
0x180320296  call    ?EncodePointer@Security@details@Concurrency@@SAPEAXPEAX@Z; Concurrency::details::Security::EncodePointer(void *)
0x18032029b  nop
0x18032029c  mov     [rdi+10h], rax
0x1803202a0  lea     rdx, aGettracelogger; "GetTraceLoggerHandle"
0x1803202a7  mov     rcx, rbx; hModule
0x1803202aa  call    cs:__imp_GetProcAddress
0x1803202b0  nop
0x1803202b1  mov     rcx, rax; void *
0x1803202b4  call    ?EncodePointer@Security@details@Concurrency@@SAPEAXPEAX@Z; Concurrency::details::Security::EncodePointer(void *)
0x1803202b9  nop
0x1803202ba  mov     [rdi+18h], rax
0x1803202be  lea     rdx, aGettraceenable; "GetTraceEnableLevel"
0x1803202c5  mov     rcx, rbx; hModule
0x1803202c8  call    cs:__imp_GetProcAddress
0x1803202ce  nop
0x1803202cf  mov     rcx, rax; void *
0x1803202d2  call    ?EncodePointer@Security@details@Concurrency@@SAPEAXPEAX@Z; Concurrency::details::Security::EncodePointer(void *)
0x1803202d7  nop
0x1803202d8  mov     [rdi+20h], rax
0x1803202dc  lea     rdx, aGettraceenable_0; "GetTraceEnableFlags"
0x1803202e3  mov     rcx, rbx; hModule
0x1803202e6  call    cs:__imp_GetProcAddress
0x1803202ec  nop
0x1803202ed  mov     rcx, rax; void *
0x1803202f0  call    ?EncodePointer@Security@details@Concurrency@@SAPEAXPEAX@Z; Concurrency::details::Security::EncodePointer(void *)
0x1803202f5  nop
0x1803202f6  mov     [rdi+28h], rax
0x1803202fa  mov     rax, rdi
0x1803202fd  mov     rbx, [rsp+38h+arg_0]
0x180320302  add     rsp, 30h
0x180320306  pop     rdi
0x180320307  retn
```
