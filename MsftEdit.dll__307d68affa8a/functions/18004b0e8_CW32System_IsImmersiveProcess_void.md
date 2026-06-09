# CW32System::IsImmersiveProcess(void *)

- ea: `0x18004b0e8`
- end: `0x18004b180`
- name: `?IsImmersiveProcess@CW32System@@SAHPEAX@Z`
- size: `152`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x18004ba58`

## callees

- `0x18002ab44`
- `0x18002abb0`
- `0x18004b0e8`
- `0x18027a010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18004b14a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18004b14a`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18004b12e`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18004b12e`

## string_xrefs

- `0x18004b121`: `user32.dll`

## pseudocode

```c
__int64 (__fastcall *__fastcall CW32System::IsImmersiveProcess(void *a1))(void *)
{
  __int64 (__fastcall *result)(void *); // rax
  HMODULE Library; // rax
  unsigned int v4; // [rsp+38h] [rbp+10h] BYREF

  result = (__int64 (__fastcall *)(void *))qword_1802DF1F8;
  if ( qword_1802DF1F8 )
    return (__int64 (__fastcall *)(void *))result(a1);
  CWriteLock::CWriteLock(&v4, 0);
  if ( !qword_1802DF1F8 )
  {
    Library = qword_1802DF248;
    if ( qword_1802DF248 || (Library = LoadLibraryExW(L"user32.dll", 0, 0x800u), (qword_1802DF248 = Library) != 0) )
      qword_1802DF1F8 = (__int64)GetProcAddress(Library, "IsImmersiveProcess");
  }
  CWriteLock::~CWriteLock((CWriteLock *)&v4);
  result = (__int64 (__fastcall *)(void *))qword_1802DF1F8;
  if ( qword_1802DF1F8 )
    return (__int64 (__fastcall *)(void *))result(a1);
  return result;
}

```

## disassembly

```asm
0x18004b0e8  push    rbx
0x18004b0ea  sub     rsp, 20h
0x18004b0ee  mov     rax, cs:qword_1802DF1F8
0x18004b0f5  mov     rbx, rcx
0x18004b0f8  test    rax, rax
0x18004b0fb  jnz     short loc_18004B173
0x18004b0fd  xor     edx, edx
0x18004b0ff  lea     rcx, [rsp+28h+arg_8]
0x18004b104  call    ??0CWriteLock@@QEAA@W4LOCK_TYPE@@@Z; CWriteLock::CWriteLock(LOCK_TYPE)
0x18004b109  cmp     cs:qword_1802DF1F8, 0
0x18004b111  jnz     short loc_18004B157
0x18004b113  mov     rax, cs:qword_1802DF248
0x18004b11a  test    rax, rax
0x18004b11d  jnz     short loc_18004B140
0x18004b11f  xor     edx, edx; hFile
0x18004b121  lea     rcx, aUser32Dll; "user32.dll"
0x18004b128  mov     r8d, 800h; dwFlags
0x18004b12e  call    cs:__imp_LoadLibraryExW
0x18004b134  mov     cs:qword_1802DF248, rax
0x18004b13b  test    rax, rax
0x18004b13e  jz      short loc_18004B157
0x18004b140  lea     rdx, aIsimmersivepro; "IsImmersiveProcess"
0x18004b147  mov     rcx, rax; hModule
0x18004b14a  call    cs:__imp_GetProcAddress
0x18004b150  mov     cs:qword_1802DF1F8, rax
0x18004b157  lea     rcx, [rsp+28h+arg_8]; this
0x18004b15c  call    ??1CWriteLock@@QEAA@XZ; CWriteLock::~CWriteLock(void)
0x18004b161  mov     rax, cs:qword_1802DF1F8
0x18004b168  test    rax, rax
0x18004b16b  jnz     short loc_18004B173
0x18004b16d  add     rsp, 20h
0x18004b171  pop     rbx
0x18004b172  retn
0x18004b173  mov     rcx, rbx
0x18004b176  add     rsp, 20h
0x18004b17a  pop     rbx
0x18004b17b  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
