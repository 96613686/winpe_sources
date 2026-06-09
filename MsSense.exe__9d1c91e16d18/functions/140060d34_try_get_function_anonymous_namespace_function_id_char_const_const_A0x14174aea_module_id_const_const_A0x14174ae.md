# try_get_function(`anonymous namespace'::function_id,char const * const,A0x14174aea::module_id const * const,A0x14174aea::module_id const * const)

- ea: `0x140060d34`
- end: `0x140060e83`
- name: `?try_get_function@@YAPEAXW4function_id@?A0x14174aea@@QEBDQEBW4module_id@2@2@Z`
- size: `335`
- prototype: `FARPROC __fastcall(unsigned int, const CHAR *, unsigned int *, unsigned int *)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x140060e84`
- `0x140060ecc`
- `0x140060f14`
- `0x140060f5c`
- `0x140060fb0`

## callees

- `0x140060d34`
- `0x14006b6a0`

## import_xrefs

- `KERNEL32!LoadLibraryExW` at `0x140060db9`
- `KERNEL32!LoadLibraryExW` at `0x140060df1`
- `KERNEL32!LoadLibraryExW` at `0x140060db9`
- `KERNEL32!LoadLibraryExW` at `0x140060df1`
- `KERNEL32!FreeLibrary` at `0x140060e5f`
- `KERNEL32!FreeLibrary` at `0x140060e5f`
- `KERNEL32!GetProcAddress` at `0x140060e6b`
- `KERNEL32!GetProcAddress` at `0x140060e6b`
- `KERNEL32!GetLastError` at `0x140060dc7`
- `KERNEL32!GetLastError` at `0x140060dc7`

## pseudocode

```c
FARPROC __fastcall try_get_function(unsigned int a1, const CHAR *a2, unsigned int *a3, unsigned int *a4)
{
  __int64 v4; // rdi
  unsigned int *v6; // rbp
  FARPROC result; // rax
  __int64 v9; // rsi
  HMODULE Library; // rbx
  const WCHAR *v11; // r15

  v4 = a1;
  v6 = a3;
  result = (FARPROC)qword_1400C4380[a1];
  if ( result == (FARPROC)-1LL )
    return 0;
  if ( !result )
  {
    if ( a3 == a4 )
      goto LABEL_13;
    while ( 1 )
    {
      v9 = *v6;
      Library = (HMODULE)qword_1400C4368[v9];
      if ( Library )
      {
        if ( Library != (HMODULE)-1LL )
          goto LABEL_18;
      }
      else
      {
        v11 = off_14009D730[v9];
        Library = LoadLibraryExW(v11, 0, 0x800u);
        if ( Library
          || GetLastError() == 87
          && (unsigned int)sub_14006B6A0(v11, L"api-ms-", 7)
          && (Library = LoadLibraryExW(v11, 0, 0)) != 0 )
        {
          if ( _InterlockedExchange64(&qword_1400C4368[v9], (__int64)Library) )
            FreeLibrary(Library);
LABEL_18:
          result = GetProcAddress(Library, a2);
          if ( result )
          {
            _InterlockedExchange64(&qword_1400C4380[v4], (__int64)result);
            return result;
          }
LABEL_13:
          _InterlockedExchange64(&qword_1400C4380[v4], -1);
          return 0;
        }
        _InterlockedExchange64(&qword_1400C4368[v9], -1);
      }
      if ( ++v6 == a4 )
        goto LABEL_13;
    }
  }
  return result;
}

```

## disassembly

```asm
0x140060d34  mov     [rsp+arg_0], rbx
0x140060d39  mov     [rsp+arg_8], rbp
0x140060d3e  mov     [rsp+arg_10], rsi
0x140060d43  push    rdi
0x140060d44  push    r12
0x140060d46  push    r13
0x140060d48  push    r14
0x140060d4a  push    r15
0x140060d4c  sub     rsp, 20h
0x140060d50  mov     edi, ecx
0x140060d52  lea     r15, __ImageBase
0x140060d59  or      r14, 0FFFFFFFFFFFFFFFFh
0x140060d5d  mov     r12, r9
0x140060d60  mov     rbp, r8
0x140060d63  mov     r13, rdx
0x140060d66  mov     rax, rva qword_1400C4380[r15+rdi*8]
0x140060d6e  nop
0x140060d6f  cmp     rax, r14
0x140060d72  jz      loc_140060E26
0x140060d78  test    rax, rax
0x140060d7b  jnz     loc_140060E28
0x140060d81  cmp     r8, r9
0x140060d84  jz      loc_140060E1E
0x140060d8a  mov     esi, [rbp+0]
0x140060d8d  mov     rbx, rva qword_1400C4368[r15+rsi*8]
0x140060d95  nop
0x140060d96  test    rbx, rbx
0x140060d99  jz      short loc_140060DA6
0x140060d9b  cmp     rbx, r14
0x140060d9e  jnz     loc_140060E65
0x140060da4  jmp     short loc_140060E11
0x140060da6  mov     r15, ds:rva off_14009D730[r15+rsi*8]
0x140060dae  xor     edx, edx; hFile
0x140060db0  mov     rcx, r15; lpLibFileName
0x140060db3  mov     r8d, 800h; dwFlags
0x140060db9  call    cs:LoadLibraryExW
0x140060dbf  mov     rbx, rax
0x140060dc2  test    rax, rax
0x140060dc5  jnz     short loc_140060E45
0x140060dc7  call    cs:GetLastError
0x140060dcd  cmp     eax, 57h ; 'W'
0x140060dd0  jnz     short loc_140060DFF
0x140060dd2  lea     r8d, [rbx+7]
0x140060dd6  mov     rcx, r15
0x140060dd9  lea     rdx, aApiMs
0x140060de0  call    sub_14006B6A0
0x140060de5  test    eax, eax
0x140060de7  jz      short loc_140060DFF
0x140060de9  xor     r8d, r8d; dwFlags
0x140060dec  xor     edx, edx; hFile
0x140060dee  mov     rcx, r15; lpLibFileName
0x140060df1  call    cs:LoadLibraryExW
0x140060df7  mov     rbx, rax
0x140060dfa  test    rax, rax
0x140060dfd  jnz     short loc_140060E45
0x140060dff  mov     rax, r14
0x140060e02  lea     r15, __ImageBase
0x140060e09  xchg    rax, rva qword_1400C4368[r15+rsi*8]
0x140060e11  add     rbp, 4
0x140060e15  cmp     rbp, r12
0x140060e18  jnz     loc_140060D8A
0x140060e1e  xchg    r14, rva qword_1400C4380[r15+rdi*8]
0x140060e26  xor     eax, eax
0x140060e28  mov     rbx, [rsp+48h+arg_0]
0x140060e2d  mov     rbp, [rsp+48h+arg_8]
0x140060e32  mov     rsi, [rsp+48h+arg_10]
0x140060e37  add     rsp, 20h
0x140060e3b  pop     r15
0x140060e3d  pop     r14
0x140060e3f  pop     r13
0x140060e41  pop     r12
0x140060e43  pop     rdi
0x140060e44  retn
0x140060e45  mov     rax, rbx
0x140060e48  lea     r15, __ImageBase
0x140060e4f  xchg    rax, rva qword_1400C4368[r15+rsi*8]
0x140060e57  test    rax, rax
0x140060e5a  jz      short loc_140060E65
0x140060e5c  mov     rcx, rbx; hLibModule
0x140060e5f  call    cs:FreeLibrary
0x140060e65  mov     rdx, r13; lpProcName
0x140060e68  mov     rcx, rbx; hModule
0x140060e6b  call    cs:GetProcAddress
0x140060e71  test    rax, rax
0x140060e74  jz      short loc_140060E1E
0x140060e76  mov     rcx, rax
0x140060e79  xchg    rcx, rva qword_1400C4380[r15+rdi*8]
0x140060e81  jmp     short loc_140060E28
```
