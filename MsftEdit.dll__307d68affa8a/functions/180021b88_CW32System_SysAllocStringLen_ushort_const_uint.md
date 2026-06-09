# CW32System::SysAllocStringLen(ushort const *,uint)

- ea: `0x180021b88`
- end: `0x180021c31`
- name: `?SysAllocStringLen@CW32System@@SAPEAGPEBGI@Z`
- size: `169`
- prototype: `unsigned __int16 *__fastcall(const unsigned __int16 *, unsigned int)`
- caller_count: `28`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x1800080dc`
- `0x180021dc4`
- `0x1800719a0`
- `0x180074980`
- `0x18007786c`
- `0x1800ccbac`
- `0x1800e62d0`
- `0x1800e7e10`
- `0x18010cb90`
- `0x1801375a8`
- `0x180176cf8`
- `0x1801778f0`
- `0x180187a60`
- `0x1801947c4`
- `0x180195310`
- `0x180196170`
- `0x1801a0390`
- `0x1801ae490`
- `0x1801ae608`
- `0x1801af2f0`
- `0x1801be6dc`
- `0x1801d2b98`
- `0x1801d7b60`
- `0x1801dcc80`
- `0x1801e7940`
- `0x1801e8a4c`
- `0x1801ee790`
- `0x1801f0da0`

## callees

- `0x180021b88`
- `0x18002ab44`
- `0x18002abb0`
- `0x18027a010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180021c05`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180021c05`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180021be9`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180021be9`

## string_xrefs

- `0x180021bdc`: `oleaut32.dll`

## pseudocode

```c
unsigned __int16 *__fastcall CW32System::SysAllocStringLen(const unsigned __int16 *a1, unsigned int a2)
{
  unsigned __int16 *result; // rax
  HMODULE Library; // rax
  unsigned int v6; // [rsp+40h] [rbp+18h] BYREF

  result = (unsigned __int16 *)qword_1802DD6E8;
  if ( qword_1802DD6E8 )
    return (unsigned __int16 *)((__int64 (__fastcall *)(const unsigned __int16 *, _QWORD))result)(a1, a2);
  CWriteLock::CWriteLock(&v6, 0);
  if ( !qword_1802DD6E8 )
  {
    Library = hModule;
    if ( hModule || (Library = LoadLibraryExW(L"oleaut32.dll", 0, 0x800u), (hModule = Library) != 0) )
      qword_1802DD6E8 = (__int64)GetProcAddress(Library, "SysAllocStringLen");
  }
  CWriteLock::~CWriteLock((CWriteLock *)&v6);
  result = (unsigned __int16 *)qword_1802DD6E8;
  if ( qword_1802DD6E8 )
    return (unsigned __int16 *)((__int64 (__fastcall *)(const unsigned __int16 *, _QWORD))result)(a1, a2);
  return result;
}

```

## disassembly

```asm
0x180021b88  mov     [rsp+arg_0], rbx
0x180021b8d  push    rdi
0x180021b8e  sub     rsp, 20h
0x180021b92  mov     rax, cs:qword_1802DD6E8
0x180021b99  mov     ebx, edx
0x180021b9b  mov     rdi, rcx
0x180021b9e  test    rax, rax
0x180021ba1  jz      short loc_180021BB8
0x180021ba3  mov     edx, ebx
0x180021ba5  mov     rcx, rdi
0x180021ba8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021bad  mov     rbx, [rsp+28h+arg_0]
0x180021bb2  add     rsp, 20h
0x180021bb6  pop     rdi
0x180021bb7  retn
0x180021bb8  xor     edx, edx
0x180021bba  lea     rcx, [rsp+28h+arg_10]
0x180021bbf  call    ??0CWriteLock@@QEAA@W4LOCK_TYPE@@@Z; CWriteLock::CWriteLock(LOCK_TYPE)
0x180021bc4  cmp     cs:qword_1802DD6E8, 0
0x180021bcc  jnz     short loc_180021C12
0x180021bce  mov     rax, cs:hModule
0x180021bd5  test    rax, rax
0x180021bd8  jnz     short loc_180021BFB
0x180021bda  xor     edx, edx; hFile
0x180021bdc  lea     rcx, LibFileName; "oleaut32.dll"
0x180021be3  mov     r8d, 800h; dwFlags
0x180021be9  call    cs:__imp_LoadLibraryExW
0x180021bef  mov     cs:hModule, rax
0x180021bf6  test    rax, rax
0x180021bf9  jz      short loc_180021C12
0x180021bfb  lea     rdx, aSysallocstring_0; "SysAllocStringLen"
0x180021c02  mov     rcx, rax; hModule
0x180021c05  call    cs:__imp_GetProcAddress
0x180021c0b  mov     cs:qword_1802DD6E8, rax
0x180021c12  lea     rcx, [rsp+28h+arg_10]; this
0x180021c17  call    ??1CWriteLock@@QEAA@XZ; CWriteLock::~CWriteLock(void)
0x180021c1c  mov     rax, cs:qword_1802DD6E8
0x180021c23  test    rax, rax
0x180021c26  jnz     loc_180021BA3
0x180021c2c  jmp     loc_180021BAD
```
