# try_get_function(`anonymous namespace'::function_id,char const * const,A0x14174aea::module_id const * const,A0x14174aea::module_id const * const)

- ea: `0x140045674`
- end: `0x1400457c3`
- name: `?try_get_function@@YAPEAXW4function_id@?A0x14174aea@@QEBDQEBW4module_id@2@2@Z`
- size: `335`
- prototype: `void *__high(enum _anonymous_namespace_::function_id, const char *const, const enum A0x14174aea::module_id *const, const enum A0x14174aea::module_id *const)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1400457c4`
- `0x14004580c`
- `0x140045854`
- `0x14004589c`
- `0x1400458f0`

## callees

- `0x140045674`
- `0x14005d950`

## import_xrefs

- `KERNEL32!GetLastError` at `0x140045707`
- `KERNEL32!GetLastError` at `0x140045707`
- `KERNEL32!FreeLibrary` at `0x14004579f`
- `KERNEL32!FreeLibrary` at `0x14004579f`
- `KERNEL32!LoadLibraryExW` at `0x1400456f9`
- `KERNEL32!LoadLibraryExW` at `0x140045731`
- `KERNEL32!LoadLibraryExW` at `0x1400456f9`
- `KERNEL32!LoadLibraryExW` at `0x140045731`
- `KERNEL32!GetProcAddress` at `0x1400457ab`
- `KERNEL32!GetProcAddress` at `0x1400457ab`

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
  result = (FARPROC)qword_140194C90[a1];
  if ( result == (FARPROC)-1LL )
    return 0;
  if ( !result )
  {
    if ( a3 == a4 )
      goto LABEL_13;
    while ( 1 )
    {
      v9 = *v6;
      Library = (HMODULE)qword_140194C78[v9];
      if ( Library )
      {
        if ( Library != (HMODULE)-1LL )
          goto LABEL_18;
      }
      else
      {
        v11 = off_140134B80[v9];
        Library = LoadLibraryExW(v11, 0, 0x800u);
        if ( Library
          || GetLastError() == 87
          && (unsigned int)sub_14005D950(v11, L"api-ms-", 7)
          && (Library = LoadLibraryExW(v11, 0, 0)) != 0 )
        {
          if ( _InterlockedExchange64(&qword_140194C78[v9], (__int64)Library) )
            FreeLibrary(Library);
LABEL_18:
          result = GetProcAddress(Library, a2);
          if ( result )
          {
            _InterlockedExchange64(&qword_140194C90[v4], (__int64)result);
            return result;
          }
LABEL_13:
          _InterlockedExchange64(&qword_140194C90[v4], -1);
          return 0;
        }
        _InterlockedExchange64(&qword_140194C78[v9], -1);
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
0x140045674  mov     [rsp+arg_0], rbx
0x140045679  mov     [rsp+arg_8], rbp
0x14004567e  mov     [rsp+arg_10], rsi
0x140045683  push    rdi
0x140045684  push    r12
0x140045686  push    r13
0x140045688  push    r14
0x14004568a  push    r15
0x14004568c  sub     rsp, 20h
0x140045690  mov     edi, ecx
0x140045692  lea     r15, __ImageBase
0x140045699  or      r14, 0FFFFFFFFFFFFFFFFh
0x14004569d  mov     r12, r9
0x1400456a0  mov     rbp, r8
0x1400456a3  mov     r13, rdx
0x1400456a6  mov     rax, rva qword_140194C90[r15+rdi*8]
0x1400456ae  nop
0x1400456af  cmp     rax, r14
0x1400456b2  jz      loc_140045766
0x1400456b8  test    rax, rax
0x1400456bb  jnz     loc_140045768
0x1400456c1  cmp     r8, r9
0x1400456c4  jz      loc_14004575E
0x1400456ca  mov     esi, [rbp+0]
0x1400456cd  mov     rbx, rva qword_140194C78[r15+rsi*8]
0x1400456d5  nop
0x1400456d6  test    rbx, rbx
0x1400456d9  jz      short loc_1400456E6
0x1400456db  cmp     rbx, r14
0x1400456de  jnz     loc_1400457A5
0x1400456e4  jmp     short loc_140045751
0x1400456e6  mov     r15, ds:rva off_140134B80[r15+rsi*8]
0x1400456ee  xor     edx, edx; hFile
0x1400456f0  mov     rcx, r15; lpLibFileName
0x1400456f3  mov     r8d, 800h; dwFlags
0x1400456f9  call    cs:LoadLibraryExW
0x1400456ff  mov     rbx, rax
0x140045702  test    rax, rax
0x140045705  jnz     short loc_140045785
0x140045707  call    cs:GetLastError
0x14004570d  cmp     eax, 57h ; 'W'
0x140045710  jnz     short loc_14004573F
0x140045712  lea     r8d, [rbx+7]
0x140045716  mov     rcx, r15
0x140045719  lea     rdx, aApiMs
0x140045720  call    sub_14005D950
0x140045725  test    eax, eax
0x140045727  jz      short loc_14004573F
0x140045729  xor     r8d, r8d; dwFlags
0x14004572c  xor     edx, edx; hFile
0x14004572e  mov     rcx, r15; lpLibFileName
0x140045731  call    cs:LoadLibraryExW
0x140045737  mov     rbx, rax
0x14004573a  test    rax, rax
0x14004573d  jnz     short loc_140045785
0x14004573f  mov     rax, r14
0x140045742  lea     r15, __ImageBase
0x140045749  xchg    rax, rva qword_140194C78[r15+rsi*8]
0x140045751  add     rbp, 4
0x140045755  cmp     rbp, r12
0x140045758  jnz     loc_1400456CA
0x14004575e  xchg    r14, rva qword_140194C90[r15+rdi*8]
0x140045766  xor     eax, eax
0x140045768  mov     rbx, [rsp+48h+arg_0]
0x14004576d  mov     rbp, [rsp+48h+arg_8]
0x140045772  mov     rsi, [rsp+48h+arg_10]
0x140045777  add     rsp, 20h
0x14004577b  pop     r15
0x14004577d  pop     r14
0x14004577f  pop     r13
0x140045781  pop     r12
0x140045783  pop     rdi
0x140045784  retn
0x140045785  mov     rax, rbx
0x140045788  lea     r15, __ImageBase
0x14004578f  xchg    rax, rva qword_140194C78[r15+rsi*8]
0x140045797  test    rax, rax
0x14004579a  jz      short loc_1400457A5
0x14004579c  mov     rcx, rbx; hLibModule
0x14004579f  call    cs:FreeLibrary
0x1400457a5  mov     rdx, r13; lpProcName
0x1400457a8  mov     rcx, rbx; hModule
0x1400457ab  call    cs:GetProcAddress
0x1400457b1  test    rax, rax
0x1400457b4  jz      short loc_14004575E
0x1400457b6  mov     rcx, rax
0x1400457b9  xchg    rcx, rva qword_140194C90[r15+rdi*8]
0x1400457c1  jmp     short loc_140045768
```
