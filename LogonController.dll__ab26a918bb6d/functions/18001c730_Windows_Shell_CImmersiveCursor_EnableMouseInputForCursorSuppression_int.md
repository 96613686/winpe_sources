# Windows::Shell::CImmersiveCursor::_EnableMouseInputForCursorSuppression(int)

- ea: `0x18001c730`
- end: `0x18001c7ba`
- name: `?_EnableMouseInputForCursorSuppression@CImmersiveCursor@Shell@Windows@@AEAA_NH@Z`
- size: `138`
- prototype: `bool __fastcall(Windows::Shell::CImmersiveCursor *__hidden this, int)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18001ac90`

## callees

- `0x18001c730`
- `0x18009d010`

## import_xrefs

- `KERNEL32!LoadLibraryW` at `0x18001c758`
- `KERNEL32!LoadLibraryW` at `0x18001c758`
- `KERNEL32!GetProcAddress` at `0x18001c76f`
- `KERNEL32!GetProcAddress` at `0x18001c781`
- `KERNEL32!GetProcAddress` at `0x18001c76f`
- `KERNEL32!GetProcAddress` at `0x18001c781`

## string_xrefs

- `0x18001c751`: `user32.dll`

## pseudocode

```c
bool __fastcall Windows::Shell::CImmersiveCursor::_EnableMouseInputForCursorSuppression(
        Windows::Shell::CImmersiveCursor *this,
        unsigned int a2)
{
  HMODULE LibraryW; // rax
  FARPROC ProcAddress; // rax
  HMODULE v6; // rcx
  unsigned int (__fastcall *v7)(_QWORD); // rax

  if ( (!*(_QWORD *)this || !*((_QWORD *)this + 1)) && !*((_QWORD *)this + 2) )
  {
    LibraryW = LoadLibraryW(L"user32.dll");
    *((_QWORD *)this + 2) = LibraryW;
    if ( LibraryW )
    {
      ProcAddress = GetProcAddress(LibraryW, (LPCSTR)0x9D7);
      v6 = (HMODULE)*((_QWORD *)this + 2);
      *(_QWORD *)this = ProcAddress;
      *((_QWORD *)this + 1) = GetProcAddress(v6, (LPCSTR)0x9D8);
    }
  }
  v7 = *(unsigned int (__fastcall **)(_QWORD))this;
  if ( *(_QWORD *)this )
    LOBYTE(v7) = v7(a2) != 0;
  return (char)v7;
}

```

## disassembly

```asm
0x18001c730  mov     [rsp+arg_0], rbx
0x18001c735  mov     [rsp+arg_8], rsi
0x18001c73a  push    rdi
0x18001c73b  sub     rsp, 20h
0x18001c73f  cmp     qword ptr [rcx], 0
0x18001c743  mov     esi, edx
0x18001c745  mov     rbx, rcx
0x18001c748  jnz     short loc_18001C7AF
0x18001c74a  cmp     qword ptr [rcx+10h], 0
0x18001c74f  jnz     short loc_18001C78B
0x18001c751  lea     rcx, aUser32Dll_0; "user32.dll"
0x18001c758  call    cs:__imp_LoadLibraryW
0x18001c75e  mov     [rbx+10h], rax
0x18001c762  test    rax, rax
0x18001c765  jz      short loc_18001C78B
0x18001c767  mov     edx, 9D7h; lpProcName
0x18001c76c  mov     rcx, rax; hModule
0x18001c76f  call    cs:__imp_GetProcAddress
0x18001c775  mov     rcx, [rbx+10h]; hModule
0x18001c779  mov     edx, 9D8h; lpProcName
0x18001c77e  mov     [rbx], rax
0x18001c781  call    cs:__imp_GetProcAddress
0x18001c787  mov     [rbx+8], rax
0x18001c78b  mov     rax, [rbx]
0x18001c78e  test    rax, rax
0x18001c791  jz      short loc_18001C7B8
0x18001c793  mov     ecx, esi
0x18001c795  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c79a  test    eax, eax
0x18001c79c  setnz   al
0x18001c79f  mov     rbx, [rsp+28h+arg_0]
0x18001c7a4  mov     rsi, [rsp+28h+arg_8]
0x18001c7a9  add     rsp, 20h
0x18001c7ad  pop     rdi
0x18001c7ae  retn
0x18001c7af  cmp     qword ptr [rcx+8], 0
0x18001c7b4  jnz     short loc_18001C78B
0x18001c7b6  jmp     short loc_18001C74A
0x18001c7b8  jmp     short loc_18001C79F
```
