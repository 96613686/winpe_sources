# try_get_function(`anonymous namespace'::function_id,char const * const,A0x14174aea::module_id const * const,A0x14174aea::module_id const * const)

- ea: `0x140002438`
- end: `0x140002587`
- name: `?try_get_function@@YAPEAXW4function_id@?A0x14174aea@@QEBDQEBW4module_id@2@2@Z`
- size: `335`
- prototype: `void *__high(enum _anonymous_namespace_::function_id, const char *const, const enum A0x14174aea::module_id *const, const enum A0x14174aea::module_id *const)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x140002588`
- `0x1400025d0`
- `0x140002618`
- `0x140002660`
- `0x1400026b4`

## callees

- `0x140002438`
- `0x140005b80`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1400024cb`
- `KERNEL32!GetLastError` at `0x1400024cb`
- `KERNEL32!GetProcAddress` at `0x14000256f`
- `KERNEL32!GetProcAddress` at `0x14000256f`
- `KERNEL32!FreeLibrary` at `0x140002563`
- `KERNEL32!FreeLibrary` at `0x140002563`
- `KERNEL32!LoadLibraryExW` at `0x1400024bd`
- `KERNEL32!LoadLibraryExW` at `0x1400024f5`
- `KERNEL32!LoadLibraryExW` at `0x1400024bd`
- `KERNEL32!LoadLibraryExW` at `0x1400024f5`

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
  result = (FARPROC)qword_14001A1B8[a1];
  if ( result == (FARPROC)-1LL )
    return 0;
  if ( !result )
  {
    if ( a3 == a4 )
      goto LABEL_13;
    while ( 1 )
    {
      v9 = *v6;
      Library = (HMODULE)qword_14001A1A0[v9];
      if ( Library )
      {
        if ( Library != (HMODULE)-1LL )
          goto LABEL_18;
      }
      else
      {
        v11 = off_140010238[v9];
        Library = LoadLibraryExW(v11, 0, 0x800u);
        if ( Library
          || GetLastError() == 87
          && (unsigned int)sub_140005B80(v11, L"api-ms-", 7)
          && (Library = LoadLibraryExW(v11, 0, 0)) != 0 )
        {
          if ( _InterlockedExchange64(&qword_14001A1A0[v9], (__int64)Library) )
            FreeLibrary(Library);
LABEL_18:
          result = GetProcAddress(Library, a2);
          if ( result )
          {
            _InterlockedExchange64(&qword_14001A1B8[v4], (__int64)result);
            return result;
          }
LABEL_13:
          _InterlockedExchange64(&qword_14001A1B8[v4], -1);
          return 0;
        }
        _InterlockedExchange64(&qword_14001A1A0[v9], -1);
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
0x140002438  mov     [rsp+arg_0], rbx
0x14000243d  mov     [rsp+arg_8], rbp
0x140002442  mov     [rsp+arg_10], rsi
0x140002447  push    rdi
0x140002448  push    r12
0x14000244a  push    r13
0x14000244c  push    r14
0x14000244e  push    r15
0x140002450  sub     rsp, 20h
0x140002454  mov     edi, ecx
0x140002456  lea     r15, cs:140000000h
0x14000245d  or      r14, 0FFFFFFFFFFFFFFFFh
0x140002461  mov     r12, r9
0x140002464  mov     rbp, r8
0x140002467  mov     r13, rdx
0x14000246a  mov     rax, rva qword_14001A1B8[r15+rdi*8]
0x140002472  nop
0x140002473  cmp     rax, r14
0x140002476  jz      loc_14000252A
0x14000247c  test    rax, rax
0x14000247f  jnz     loc_14000252C
0x140002485  cmp     r8, r9
0x140002488  jz      loc_140002522
0x14000248e  mov     esi, [rbp+0]
0x140002491  mov     rbx, rva qword_14001A1A0[r15+rsi*8]
0x140002499  nop
0x14000249a  test    rbx, rbx
0x14000249d  jz      short loc_1400024AA
0x14000249f  cmp     rbx, r14
0x1400024a2  jnz     loc_140002569
0x1400024a8  jmp     short loc_140002515
0x1400024aa  mov     r15, ds:rva off_140010238[r15+rsi*8]
0x1400024b2  xor     edx, edx; hFile
0x1400024b4  mov     rcx, r15; lpLibFileName
0x1400024b7  mov     r8d, 800h; dwFlags
0x1400024bd  call    cs:LoadLibraryExW
0x1400024c3  mov     rbx, rax
0x1400024c6  test    rax, rax
0x1400024c9  jnz     short loc_140002549
0x1400024cb  call    cs:GetLastError
0x1400024d1  cmp     eax, 57h ; 'W'
0x1400024d4  jnz     short loc_140002503
0x1400024d6  lea     r8d, [rbx+7]
0x1400024da  mov     rcx, r15
0x1400024dd  lea     rdx, aApiMs
0x1400024e4  call    sub_140005B80
0x1400024e9  test    eax, eax
0x1400024eb  jz      short loc_140002503
0x1400024ed  xor     r8d, r8d; dwFlags
0x1400024f0  xor     edx, edx; hFile
0x1400024f2  mov     rcx, r15; lpLibFileName
0x1400024f5  call    cs:LoadLibraryExW
0x1400024fb  mov     rbx, rax
0x1400024fe  test    rax, rax
0x140002501  jnz     short loc_140002549
0x140002503  mov     rax, r14
0x140002506  lea     r15, cs:140000000h
0x14000250d  xchg    rax, rva qword_14001A1A0[r15+rsi*8]
0x140002515  add     rbp, 4
0x140002519  cmp     rbp, r12
0x14000251c  jnz     loc_14000248E
0x140002522  xchg    r14, rva qword_14001A1B8[r15+rdi*8]
0x14000252a  xor     eax, eax
0x14000252c  mov     rbx, [rsp+48h+arg_0]
0x140002531  mov     rbp, [rsp+48h+arg_8]
0x140002536  mov     rsi, [rsp+48h+arg_10]
0x14000253b  add     rsp, 20h
0x14000253f  pop     r15
0x140002541  pop     r14
0x140002543  pop     r13
0x140002545  pop     r12
0x140002547  pop     rdi
0x140002548  retn
0x140002549  mov     rax, rbx
0x14000254c  lea     r15, cs:140000000h
0x140002553  xchg    rax, rva qword_14001A1A0[r15+rsi*8]
0x14000255b  test    rax, rax
0x14000255e  jz      short loc_140002569
0x140002560  mov     rcx, rbx; hLibModule
0x140002563  call    cs:FreeLibrary
0x140002569  mov     rdx, r13; lpProcName
0x14000256c  mov     rcx, rbx; hModule
0x14000256f  call    cs:GetProcAddress
0x140002575  test    rax, rax
0x140002578  jz      short loc_140002522
0x14000257a  mov     rcx, rax
0x14000257d  xchg    rcx, rva qword_14001A1B8[r15+rdi*8]
0x140002585  jmp     short loc_14000252C
```
