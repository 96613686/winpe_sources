# CWinTaskHandler::WorkerThreadProc(void *)

- ea: `0x18000cff0`
- end: `0x18000d05b`
- name: `?WorkerThreadProc@CWinTaskHandler@@CAKPEAX@Z`
- size: `107`
- prototype: `__int64 __fastcall(_DWORD *Parameter)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callees

- `0x18000cff0`
- `0x18001c010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibraryAndExitThread` at `0x18000d049`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibraryAndExitThread` at `0x18000d049`

## pseudocode

```c
__int64 __fastcall CWinTaskHandler::WorkerThreadProc(_DWORD *Parameter)
{
  int v2; // ebp
  HMODULE v3; // rsi
  __int64 v4; // rdi

  v2 = Parameter[4];
  v3 = 0;
  v4 = (*(unsigned int (__fastcall **)(_DWORD *))(*(_QWORD *)Parameter + 64LL))(Parameter);
  (*(void (__fastcall **)(_QWORD, __int64))(**((_QWORD **)Parameter + 6) + 32LL))(*((_QWORD *)Parameter + 6), v4);
  if ( v2 )
  {
    v3 = (HMODULE)*((_QWORD *)Parameter + 3);
    *((_QWORD *)Parameter + 3) = 0;
  }
  (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)Parameter + 16LL))(Parameter);
  if ( v2 )
    FreeLibraryAndExitThread(v3, v4);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18000cff0  push    rbx
0x18000cff2  push    rbp
0x18000cff3  push    rsi
0x18000cff4  push    rdi
0x18000cff5  sub     rsp, 28h
0x18000cff9  mov     rax, [rcx]
0x18000cffc  mov     rbx, rcx
0x18000cfff  mov     ebp, [rcx+10h]
0x18000d002  xor     esi, esi
0x18000d004  mov     rax, [rax+40h]
0x18000d008  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d00d  mov     rcx, [rbx+30h]
0x18000d011  mov     edi, eax
0x18000d013  mov     rdx, [rcx]
0x18000d016  mov     rax, [rdx+20h]
0x18000d01a  mov     edx, edi
0x18000d01c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d021  test    ebp, ebp
0x18000d023  jz      short loc_18000D031
0x18000d025  mov     rsi, [rbx+18h]
0x18000d029  mov     qword ptr [rbx+18h], 0
0x18000d031  mov     rax, [rbx]
0x18000d034  mov     rcx, rbx
0x18000d037  mov     rax, [rax+10h]
0x18000d03b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d040  test    ebp, ebp
0x18000d042  jz      short loc_18000D050
0x18000d044  mov     edx, edi; dwExitCode
0x18000d046  mov     rcx, rsi; hLibModule
0x18000d049  call    cs:__imp_FreeLibraryAndExitThread
0x18000d04f  int     3; Trap to Debugger
0x18000d050  mov     eax, edi
0x18000d052  add     rsp, 28h
0x18000d056  pop     rdi
0x18000d057  pop     rsi
0x18000d058  pop     rbp
0x18000d059  pop     rbx
0x18000d05a  retn
```
