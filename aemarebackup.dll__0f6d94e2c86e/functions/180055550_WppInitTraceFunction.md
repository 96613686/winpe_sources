# WppInitTraceFunction

- ea: `0x180055550`
- end: `0x180055636`
- name: `WppInitTraceFunction`
- size: `230`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x180055550`
- `0x1800ec010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18005558e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800555ba`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18005558e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800555ba`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800555dd`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800555dd`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x180055576`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x180055576`

## pseudocode

```c
__int64 WppInitTraceFunction(__int64 a1, unsigned int a2, __int64 a3, unsigned __int16 a4, ...)
{
  HMODULE LibraryW; // rax
  HMODULE v8; // rbx
  va_list va; // [rsp+90h] [rbp+28h] BYREF

  va_start(va, a4);
  LibraryW = LoadLibraryW(L"advapi32");
  v8 = LibraryW;
  if ( !LibraryW )
  {
    pfnWppTraceMessage = (__int64 (__fastcall *)(int, int, int, int, char))TraceMessageW2k;
    pfnWppTraceMessageVa = TraceMessageW2kVa;
    ((void (__fastcall *)(__int64, _QWORD, __int64, _QWORD, char *))TraceMessageW2kVa)(a1, a2, a3, a4, va);
    return 0;
  }
  pfnWppTraceMessage = (__int64 (__fastcall *)(int, int, int, int, char))GetProcAddress(LibraryW, "TraceMessage");
  if ( !pfnWppTraceMessage )
  {
    pfnWppTraceMessage = (__int64 (__fastcall *)(int, int, int, int, char))TraceMessageW2k;
LABEL_5:
    pfnWppTraceMessageVa = TraceMessageW2kVa;
    goto LABEL_6;
  }
  pfnWppTraceMessageVa = (__int64 (__usercall *)@<rax>(TRACEHANDLE@<rcx>, __int64))GetProcAddress(v8, "TraceMessageVa");
  if ( !pfnWppTraceMessageVa )
    goto LABEL_5;
LABEL_6:
  FreeLibrary(v8);
  ((void (__fastcall *)(__int64, _QWORD, __int64, _QWORD, char *))pfnWppTraceMessageVa)(a1, a2, a3, a4, va);
  return 0;
}

```

## disassembly

```asm
0x180055550  mov     [rsp+arg_18], r9w
0x180055556  push    rbx
0x180055557  push    rbp
0x180055558  push    rsi
0x180055559  push    rdi
0x18005555a  sub     rsp, 48h
0x18005555e  mov     rbp, rcx
0x180055561  mov     [rsp+68h+var_38], 0
0x18005556a  lea     rcx, aAdvapi32; "advapi32"
0x180055571  mov     rdi, r8
0x180055574  mov     esi, edx
0x180055576  call    cs:__imp_LoadLibraryW
0x18005557c  mov     rbx, rax
0x18005557f  test    rax, rax
0x180055582  jz      short loc_1800555EC
0x180055584  lea     rdx, aTracemessage; "TraceMessage"
0x18005558b  mov     rcx, rax; hModule
0x18005558e  call    cs:__imp_GetProcAddress
0x180055594  mov     cs:pfnWppTraceMessage, rax
0x18005559b  test    rax, rax
0x18005559e  jnz     short loc_1800555B0
0x1800555a0  lea     rcx, TraceMessageW2k
0x1800555a7  mov     cs:pfnWppTraceMessage, rcx
0x1800555ae  jmp     short loc_1800555CC
0x1800555b0  lea     rdx, aTracemessageva; "TraceMessageVa"
0x1800555b7  mov     rcx, rbx; hModule
0x1800555ba  call    cs:__imp_GetProcAddress
0x1800555c0  mov     cs:pfnWppTraceMessageVa, rax
0x1800555c7  test    rax, rax
0x1800555ca  jnz     short loc_1800555DA
0x1800555cc  lea     rax, TraceMessageW2kVa
0x1800555d3  mov     cs:pfnWppTraceMessageVa, rax
0x1800555da  mov     rcx, rbx; hLibModule
0x1800555dd  call    cs:__imp_FreeLibrary
0x1800555e3  mov     rax, cs:pfnWppTraceMessageVa
0x1800555ea  jmp     short loc_180055608
0x1800555ec  lea     rcx, TraceMessageW2k
0x1800555f3  lea     rax, TraceMessageW2kVa
0x1800555fa  mov     cs:pfnWppTraceMessage, rcx
0x180055601  mov     cs:pfnWppTraceMessageVa, rax
0x180055608  movzx   r9d, [rsp+68h+arg_18]
0x180055611  lea     rcx, [rsp+68h+arg_20]
0x180055619  mov     [rsp+68h+var_48], rcx
0x18005561e  mov     r8, rdi
0x180055621  mov     rcx, rbp
0x180055624  mov     edx, esi
0x180055626  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005562b  xor     eax, eax
0x18005562d  add     rsp, 48h
0x180055631  pop     rdi
0x180055632  pop     rsi
0x180055633  pop     rbp
0x180055634  pop     rbx
0x180055635  retn
```
