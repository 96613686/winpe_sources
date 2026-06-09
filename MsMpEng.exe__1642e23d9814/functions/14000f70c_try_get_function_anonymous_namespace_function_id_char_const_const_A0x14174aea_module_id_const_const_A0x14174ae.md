# try_get_function(`anonymous namespace'::function_id,char const * const,A0x14174aea::module_id const * const,A0x14174aea::module_id const * const)

- ea: `0x14000f70c`
- end: `0x14000f85b`
- name: `?try_get_function@@YAPEAXW4function_id@?A0x14174aea@@QEBDQEBW4module_id@2@2@Z`
- size: `335`
- prototype: `FARPROC __fastcall(unsigned int, const CHAR *, unsigned int *, unsigned int *)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x14000f85c`
- `0x14000f8a4`
- `0x14000f8ec`
- `0x14000f934`
- `0x14000f988`

## callees

- `0x14000f70c`
- `0x140016aa0`

## import_xrefs

- `KERNEL32!LoadLibraryExW` at `0x14000f791`
- `KERNEL32!LoadLibraryExW` at `0x14000f7c9`
- `KERNEL32!LoadLibraryExW` at `0x14000f791`
- `KERNEL32!LoadLibraryExW` at `0x14000f7c9`
- `KERNEL32!FreeLibrary` at `0x14000f837`
- `KERNEL32!FreeLibrary` at `0x14000f837`
- `KERNEL32!GetProcAddress` at `0x14000f843`
- `KERNEL32!GetProcAddress` at `0x14000f843`
- `KERNEL32!GetLastError` at `0x14000f79f`
- `KERNEL32!GetLastError` at `0x14000f79f`

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
  result = (FARPROC)qword_14003E250[a1];
  if ( result == (FARPROC)-1LL )
    return 0;
  if ( !result )
  {
    if ( a3 == a4 )
      goto LABEL_13;
    while ( 1 )
    {
      v9 = *v6;
      Library = (HMODULE)qword_14003E238[v9];
      if ( Library )
      {
        if ( Library != (HMODULE)-1LL )
          goto LABEL_18;
      }
      else
      {
        v11 = off_14002E548[v9];
        Library = LoadLibraryExW(v11, 0, 0x800u);
        if ( Library
          || GetLastError() == 87
          && (unsigned int)sub_140016AA0(v11, L"api-ms-", 7)
          && (Library = LoadLibraryExW(v11, 0, 0)) != 0 )
        {
          if ( _InterlockedExchange64(&qword_14003E238[v9], (__int64)Library) )
            FreeLibrary(Library);
LABEL_18:
          result = GetProcAddress(Library, a2);
          if ( result )
          {
            _InterlockedExchange64(&qword_14003E250[v4], (__int64)result);
            return result;
          }
LABEL_13:
          _InterlockedExchange64(&qword_14003E250[v4], -1);
          return 0;
        }
        _InterlockedExchange64(&qword_14003E238[v9], -1);
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
0x14000f70c  mov     [rsp+arg_0], rbx
0x14000f711  mov     [rsp+arg_8], rbp
0x14000f716  mov     [rsp+arg_10], rsi
0x14000f71b  push    rdi
0x14000f71c  push    r12
0x14000f71e  push    r13
0x14000f720  push    r14
0x14000f722  push    r15
0x14000f724  sub     rsp, 20h
0x14000f728  mov     edi, ecx
0x14000f72a  lea     r15, cs:140000000h
0x14000f731  or      r14, 0FFFFFFFFFFFFFFFFh
0x14000f735  mov     r12, r9
0x14000f738  mov     rbp, r8
0x14000f73b  mov     r13, rdx
0x14000f73e  mov     rax, rva qword_14003E250[r15+rdi*8]
0x14000f746  nop
0x14000f747  cmp     rax, r14
0x14000f74a  jz      loc_14000F7FE
0x14000f750  test    rax, rax
0x14000f753  jnz     loc_14000F800
0x14000f759  cmp     r8, r9
0x14000f75c  jz      loc_14000F7F6
0x14000f762  mov     esi, [rbp+0]
0x14000f765  mov     rbx, rva qword_14003E238[r15+rsi*8]
0x14000f76d  nop
0x14000f76e  test    rbx, rbx
0x14000f771  jz      short loc_14000F77E
0x14000f773  cmp     rbx, r14
0x14000f776  jnz     loc_14000F83D
0x14000f77c  jmp     short loc_14000F7E9
0x14000f77e  mov     r15, ds:rva off_14002E548[r15+rsi*8]
0x14000f786  xor     edx, edx; hFile
0x14000f788  mov     rcx, r15; lpLibFileName
0x14000f78b  mov     r8d, 800h; dwFlags
0x14000f791  call    cs:LoadLibraryExW
0x14000f797  mov     rbx, rax
0x14000f79a  test    rax, rax
0x14000f79d  jnz     short loc_14000F81D
0x14000f79f  call    cs:GetLastError
0x14000f7a5  cmp     eax, 57h ; 'W'
0x14000f7a8  jnz     short loc_14000F7D7
0x14000f7aa  lea     r8d, [rbx+7]
0x14000f7ae  mov     rcx, r15
0x14000f7b1  lea     rdx, aApiMs
0x14000f7b8  call    sub_140016AA0
0x14000f7bd  test    eax, eax
0x14000f7bf  jz      short loc_14000F7D7
0x14000f7c1  xor     r8d, r8d; dwFlags
0x14000f7c4  xor     edx, edx; hFile
0x14000f7c6  mov     rcx, r15; lpLibFileName
0x14000f7c9  call    cs:LoadLibraryExW
0x14000f7cf  mov     rbx, rax
0x14000f7d2  test    rax, rax
0x14000f7d5  jnz     short loc_14000F81D
0x14000f7d7  mov     rax, r14
0x14000f7da  lea     r15, cs:140000000h
0x14000f7e1  xchg    rax, rva qword_14003E238[r15+rsi*8]
0x14000f7e9  add     rbp, 4
0x14000f7ed  cmp     rbp, r12
0x14000f7f0  jnz     loc_14000F762
0x14000f7f6  xchg    r14, rva qword_14003E250[r15+rdi*8]
0x14000f7fe  xor     eax, eax
0x14000f800  mov     rbx, [rsp+48h+arg_0]
0x14000f805  mov     rbp, [rsp+48h+arg_8]
0x14000f80a  mov     rsi, [rsp+48h+arg_10]
0x14000f80f  add     rsp, 20h
0x14000f813  pop     r15
0x14000f815  pop     r14
0x14000f817  pop     r13
0x14000f819  pop     r12
0x14000f81b  pop     rdi
0x14000f81c  retn
0x14000f81d  mov     rax, rbx
0x14000f820  lea     r15, cs:140000000h
0x14000f827  xchg    rax, rva qword_14003E238[r15+rsi*8]
0x14000f82f  test    rax, rax
0x14000f832  jz      short loc_14000F83D
0x14000f834  mov     rcx, rbx; hLibModule
0x14000f837  call    cs:FreeLibrary
0x14000f83d  mov     rdx, r13; lpProcName
0x14000f840  mov     rcx, rbx; hModule
0x14000f843  call    cs:GetProcAddress
0x14000f849  test    rax, rax
0x14000f84c  jz      short loc_14000F7F6
0x14000f84e  mov     rcx, rax
0x14000f851  xchg    rcx, rva qword_14003E250[r15+rdi*8]
0x14000f859  jmp     short loc_14000F800
```
