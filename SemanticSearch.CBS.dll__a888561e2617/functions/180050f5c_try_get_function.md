# try_get_function

- ea: `0x180050f5c`
- end: `0x1800510ab`
- name: `try_get_function`
- size: `335`
- prototype: `FARPROC __fastcall(unsigned int, const CHAR *, unsigned int *, unsigned int *)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800510ac`
- `0x1800510f4`
- `0x18005113c`
- `0x180051184`
- `0x1800511d8`

## callees

- `0x180050f5c`
- `0x180051433`

## import_xrefs

- `KERNEL32!LoadLibraryExW` at `0x180050fe1`
- `KERNEL32!LoadLibraryExW` at `0x180051019`
- `KERNEL32!LoadLibraryExW` at `0x180050fe1`
- `KERNEL32!LoadLibraryExW` at `0x180051019`
- `KERNEL32!FreeLibrary` at `0x180051087`
- `KERNEL32!FreeLibrary` at `0x180051087`
- `KERNEL32!GetLastError` at `0x180050fef`
- `KERNEL32!GetLastError` at `0x180050fef`
- `KERNEL32!GetProcAddress` at `0x180051093`
- `KERNEL32!GetProcAddress` at `0x180051093`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
  result = (FARPROC)qword_180086480[a1];
  if ( result == (FARPROC)-1LL )
    return 0;
  if ( !result )
  {
    if ( a3 == a4 )
      goto LABEL_13;
    while ( 1 )
    {
      v9 = *v6;
      Library = (HMODULE)qword_180086468[v9];
      if ( Library )
      {
        if ( Library != (HMODULE)-1LL )
          goto LABEL_18;
      }
      else
      {
        v11 = off_18006CF68[v9];
        Library = LoadLibraryExW(v11, 0, 0x800u);
        if ( Library
          || GetLastError() == 87 && wcsncmp_0(v11, L"api-ms-", 7u) && (Library = LoadLibraryExW(v11, 0, 0)) != 0 )
        {
          if ( _InterlockedExchange64(&qword_180086468[v9], (__int64)Library) )
            FreeLibrary(Library);
LABEL_18:
          result = GetProcAddress(Library, a2);
          if ( result )
          {
            _InterlockedExchange64(&qword_180086480[v4], (__int64)result);
            return result;
          }
LABEL_13:
          _InterlockedExchange64(&qword_180086480[v4], -1);
          return 0;
        }
        _InterlockedExchange64(&qword_180086468[v9], -1);
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
0x180050f5c  mov     [rsp+arg_0], rbx
0x180050f61  mov     [rsp+arg_8], rbp
0x180050f66  mov     [rsp+arg_10], rsi
0x180050f6b  push    rdi
0x180050f6c  push    r12
0x180050f6e  push    r13
0x180050f70  push    r14
0x180050f72  push    r15
0x180050f74  sub     rsp, 20h
0x180050f78  mov     edi, ecx
0x180050f7a  lea     r15, cs:180000000h
0x180050f81  or      r14, 0FFFFFFFFFFFFFFFFh
0x180050f85  mov     r12, r9
0x180050f88  mov     rbp, r8
0x180050f8b  mov     r13, rdx
0x180050f8e  mov     rax, rva qword_180086480[r15+rdi*8]
0x180050f96  nop
0x180050f97  cmp     rax, r14
0x180050f9a  jz      loc_18005104E
0x180050fa0  test    rax, rax
0x180050fa3  jnz     loc_180051050
0x180050fa9  cmp     r8, r9
0x180050fac  jz      loc_180051046
0x180050fb2  mov     esi, [rbp+0]
0x180050fb5  mov     rbx, rva qword_180086468[r15+rsi*8]
0x180050fbd  nop
0x180050fbe  test    rbx, rbx
0x180050fc1  jz      short loc_180050FCE
0x180050fc3  cmp     rbx, r14
0x180050fc6  jnz     loc_18005108D
0x180050fcc  jmp     short loc_180051039
0x180050fce  mov     r15, ds:rva off_18006CF68[r15+rsi*8]; "api-ms-win-core-fibers-l1-1-1" ...
0x180050fd6  xor     edx, edx; hFile
0x180050fd8  mov     rcx, r15; lpLibFileName
0x180050fdb  mov     r8d, 800h; dwFlags
0x180050fe1  call    cs:__imp_LoadLibraryExW
0x180050fe7  mov     rbx, rax
0x180050fea  test    rax, rax
0x180050fed  jnz     short loc_18005106D
0x180050fef  call    cs:__imp_GetLastError
0x180050ff5  cmp     eax, 57h ; 'W'
0x180050ff8  jnz     short loc_180051027
0x180050ffa  lea     r8d, [rbx+7]; MaxCount
0x180050ffe  mov     rcx, r15; String1
0x180051001  lea     rdx, aApiMs; "api-ms-"
0x180051008  call    wcsncmp_0
0x18005100d  test    eax, eax
0x18005100f  jz      short loc_180051027
0x180051011  xor     r8d, r8d; dwFlags
0x180051014  xor     edx, edx; hFile
0x180051016  mov     rcx, r15; lpLibFileName
0x180051019  call    cs:__imp_LoadLibraryExW
0x18005101f  mov     rbx, rax
0x180051022  test    rax, rax
0x180051025  jnz     short loc_18005106D
0x180051027  mov     rax, r14
0x18005102a  lea     r15, cs:180000000h
0x180051031  xchg    rax, rva qword_180086468[r15+rsi*8]
0x180051039  add     rbp, 4
0x18005103d  cmp     rbp, r12
0x180051040  jnz     loc_180050FB2
0x180051046  xchg    r14, rva qword_180086480[r15+rdi*8]
0x18005104e  xor     eax, eax
0x180051050  mov     rbx, [rsp+48h+arg_0]
0x180051055  mov     rbp, [rsp+48h+arg_8]
0x18005105a  mov     rsi, [rsp+48h+arg_10]
0x18005105f  add     rsp, 20h
0x180051063  pop     r15
0x180051065  pop     r14
0x180051067  pop     r13
0x180051069  pop     r12
0x18005106b  pop     rdi
0x18005106c  retn
0x18005106d  mov     rax, rbx
0x180051070  lea     r15, cs:180000000h
0x180051077  xchg    rax, rva qword_180086468[r15+rsi*8]
0x18005107f  test    rax, rax
0x180051082  jz      short loc_18005108D
0x180051084  mov     rcx, rbx; hLibModule
0x180051087  call    cs:__imp_FreeLibrary
0x18005108d  mov     rdx, r13; lpProcName
0x180051090  mov     rcx, rbx; hModule
0x180051093  call    cs:__imp_GetProcAddress
0x180051099  test    rax, rax
0x18005109c  jz      short loc_180051046
0x18005109e  mov     rcx, rax
0x1800510a1  xchg    rcx, rva qword_180086480[r15+rdi*8]
0x1800510a9  jmp     short loc_180051050
```
