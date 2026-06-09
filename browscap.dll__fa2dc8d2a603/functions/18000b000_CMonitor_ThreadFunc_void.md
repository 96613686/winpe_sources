# CMonitor::ThreadFunc(void *)

- ea: `0x18000b000`
- end: `0x18000b0b2`
- name: `?ThreadFunc@CMonitor@@CAIPEAX@Z`
- size: `178`
- prototype: `DWORD __stdcall(LPVOID lpThreadParameter)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting`

## callees

- `0x1800099f8`
- `0x18000a2e4`
- `0x18000b000`

## import_xrefs

- `msvcrt!free` at `0x18000b092`
- `msvcrt!free` at `0x18000b092`
- `KERNEL32!ExitThread` at `0x18000b0ab`
- `KERNEL32!ExitThread` at `0x18000b0ab`
- `KERNEL32!FreeLibraryAndExitThread` at `0x18000b0a2`
- `KERNEL32!FreeLibraryAndExitThread` at `0x18000b0a2`
- `KERNEL32!GetModuleFileNameA` at `0x18000b045`
- `KERNEL32!GetModuleFileNameA` at `0x18000b045`
- `KERNEL32!LoadLibraryA` at `0x18000b059`
- `KERNEL32!LoadLibraryA` at `0x18000b059`

## pseudocode

```c
// Hidden C++ exception states: #try_helpers=1
void __fastcall __noreturn CMonitor::ThreadFunc(CMonitor *lpThreadParameter)
{
  DWORD v2; // edi
  HMODULE LibraryA; // rsi
  CHAR *v4; // rax
  CHAR *v5; // rbx
  DWORD ModuleFileNameA; // eax

  v2 = -1;
  LibraryA = 0;
  v4 = (CHAR *)operator new(0x105u);
  v5 = v4;
  if ( v4 )
  {
    ModuleFileNameA = GetModuleFileNameA(g_hModuleInstance, v4, 0x104u);
    v5[260] = 0;
    if ( ModuleFileNameA )
      LibraryA = LoadLibraryA(v5);
  }
  if ( lpThreadParameter )
    v2 = CMonitor::DoMonitoring(lpThreadParameter);
  if ( v5 )
    free(v5);
  if ( LibraryA )
    FreeLibraryAndExitThread(LibraryA, v2);
  ExitThread(v2);
}

```

## disassembly

```asm
0x18000b000  mov     [rsp+arg_18], rbx
0x18000b005  push    rsi
0x18000b006  push    rdi
0x18000b007  push    r14
0x18000b009  sub     rsp, 20h
0x18000b00d  mov     r14, rcx
0x18000b010  or      edi, 0FFFFFFFFh
0x18000b013  mov     [rsp+38h+arg_0], edi
0x18000b017  xor     esi, esi
0x18000b019  mov     [rsp+38h+arg_8], rsi
0x18000b01e  mov     ecx, 105h; unsigned __int64
0x18000b023  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000b028  mov     rbx, rax
0x18000b02b  mov     [rsp+38h+arg_10], rax
0x18000b030  test    rax, rax
0x18000b033  jz      short loc_18000B067
0x18000b035  mov     r8d, 104h; nSize
0x18000b03b  mov     rdx, rax; lpFilename
0x18000b03e  mov     rcx, cs:?g_hModuleInstance@@3PEAUHINSTANCE__@@EA; hModule
0x18000b045  call    cs:__imp_GetModuleFileNameA
0x18000b04b  mov     [rbx+104h], sil
0x18000b052  test    eax, eax
0x18000b054  jz      short loc_18000B067
0x18000b056  mov     rcx, rbx; lpLibFileName
0x18000b059  call    cs:__imp_LoadLibraryA
0x18000b05f  mov     rsi, rax
0x18000b062  mov     [rsp+38h+arg_8], rax
0x18000b067  test    r14, r14
0x18000b06a  jz      short loc_18000B07A
0x18000b06c  mov     rcx, r14; this
0x18000b06f  call    ?DoMonitoring@CMonitor@@AEAAKXZ; CMonitor::DoMonitoring(void)
0x18000b074  mov     edi, eax
0x18000b076  mov     [rsp+38h+arg_0], eax
0x18000b07a  jmp     short loc_18000B08A
0x18000b07c  mov     edi, [rsp+38h+arg_0]
0x18000b080  mov     rsi, [rsp+38h+arg_8]
0x18000b085  mov     rbx, [rsp+38h+arg_10]
0x18000b08a  test    rbx, rbx
0x18000b08d  jz      short loc_18000B098
0x18000b08f  mov     rcx, rbx; Block
0x18000b092  call    cs:__imp_free
0x18000b098  test    rsi, rsi
0x18000b09b  jz      short loc_18000B0A9
0x18000b09d  mov     edx, edi; dwExitCode
0x18000b09f  mov     rcx, rsi; hLibModule
0x18000b0a2  call    cs:__imp_FreeLibraryAndExitThread
0x18000b0a9  mov     ecx, edi; dwExitCode
0x18000b0ab  call    cs:__imp_ExitThread
```
