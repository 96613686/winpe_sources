# try_get_function_slow

- ea: `0x18002744c`
- end: `0x1800275ef`
- name: `try_get_function_slow`
- size: `419`
- prototype: ``
- caller_count: `5`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x1800275f8`
- `0x18002765c`
- `0x18002770c`
- `0x1800277f0`
- `0x18002789c`

## callees

- `0x180024d44`
- `0x180025c10`
- `0x180025c70`
- `0x18002744c`
- `0x1800280d0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1800274c0`
- `KERNEL32!GetLastError` at `0x1800274c0`
- `KERNEL32!GetProcAddress` at `0x1800275db`
- `KERNEL32!GetProcAddress` at `0x1800275db`
- `KERNEL32!LoadLibraryExW` at `0x1800274ae`
- `KERNEL32!LoadLibraryExW` at `0x180027502`
- `KERNEL32!LoadLibraryExW` at `0x1800274ae`
- `KERNEL32!LoadLibraryExW` at `0x180027502`
- `KERNEL32!FreeLibrary` at `0x1800275cf`
- `KERNEL32!FreeLibrary` at `0x1800275cf`
- `KERNEL32!VirtualProtect` at `0x180027567`
- `KERNEL32!VirtualProtect` at `0x180027597`
- `KERNEL32!VirtualProtect` at `0x180027567`
- `KERNEL32!VirtualProtect` at `0x180027597`

## pseudocode

```c
FARPROC __fastcall try_get_function_slow(unsigned int a1, const CHAR *a2, unsigned int *a3, unsigned int *a4)
{
  __int64 v4; // r12
  unsigned int *v6; // rsi
  __int64 v8; // rdi
  HMODULE Library; // rbx
  const WCHAR *v10; // rbp
  FARPROC ProcAddress; // rbx
  __int64 v12; // rax
  DWORD flOldProtect; // [rsp+80h] [rbp+18h] BYREF

  v4 = a1;
  v6 = a3;
  if ( a3 == a4 )
  {
LABEL_12:
    ProcAddress = 0;
    goto LABEL_13;
  }
  while ( 1 )
  {
    v8 = *v6;
    Library = (HMODULE)qword_1800D3F80[v8];
    if ( !Library )
      break;
    if ( Library != (HMODULE)-1LL )
      goto LABEL_20;
LABEL_11:
    if ( ++v6 == a4 )
      goto LABEL_12;
  }
  v10 = off_1800A1610[v8];
  Library = LoadLibraryExW(v10, 0, 0x800u);
  if ( !Library
    && (GetLastError() != 87
     || !wcsncmp(v10, L"api-ms-", 7u)
     || !wcsncmp(v10, L"ext-ms-", 7u)
     || (Library = LoadLibraryExW(v10, 0, 0)) == 0) )
  {
    _InterlockedExchange64(&qword_1800D3F80[v8], -1);
    goto LABEL_11;
  }
  if ( _InterlockedExchange64(&qword_1800D3F80[v8], (__int64)Library) )
    FreeLibrary(Library);
LABEL_20:
  ProcAddress = GetProcAddress(Library, a2);
LABEL_13:
  _acrt_lock(14);
  flOldProtect = 0;
  if ( !VirtualProtect(qword_1800DD000, 0x100u, 4u, &flOldProtect) )
    goto LABEL_21;
  v12 = (__int64)ProcAddress;
  if ( !ProcAddress )
    v12 = -1;
  _InterlockedExchange64(&qword_1800DD000[v4], v12);
  if ( !VirtualProtect(qword_1800DD000, 0x100u, 2u, &flOldProtect) )
LABEL_21:
    abort();
  _acrt_unlock(14);
  return ProcAddress;
}

```

## disassembly

```asm
0x18002744c  push    rbx
0x18002744e  push    rbp
0x18002744f  push    rsi
0x180027450  push    rdi
0x180027451  push    r12
0x180027453  push    r13
0x180027455  push    r14
0x180027457  push    r15
0x180027459  sub     rsp, 28h
0x18002745d  or      rax, 0FFFFFFFFFFFFFFFFh
0x180027461  mov     r12d, ecx
0x180027464  mov     r14, r9
0x180027467  mov     rsi, r8
0x18002746a  mov     r15, rdx
0x18002746d  cmp     r8, r9
0x180027470  jz      loc_180027531
0x180027476  lea     r13, __ImageBase
0x18002747d  mov     edi, [rsi]
0x18002747f  mov     rbx, rva qword_1800D3F80[r13+rdi*8]
0x180027487  nop
0x180027488  test    rbx, rbx
0x18002748b  jz      short loc_18002749B
0x18002748d  cmp     rbx, rax
0x180027490  jnz     loc_1800275D5
0x180027496  jmp     loc_180027524
0x18002749b  mov     rbp, ds:rva off_1800A1610[r13+rdi*8]; "api-ms-win-core-datetime-l1-1-1" ...
0x1800274a3  xor     edx, edx; hFile
0x1800274a5  mov     rcx, rbp; lpLibFileName
0x1800274a8  mov     r8d, 800h; dwFlags
0x1800274ae  call    cs:__imp_LoadLibraryExW
0x1800274b4  mov     rbx, rax
0x1800274b7  test    rax, rax
0x1800274ba  jnz     loc_1800275BC
0x1800274c0  call    cs:__imp_GetLastError
0x1800274c6  cmp     eax, 57h ; 'W'
0x1800274c9  jnz     short loc_180027514
0x1800274cb  lea     ebx, [rax-50h]
0x1800274ce  mov     rcx, rbp; String1
0x1800274d1  mov     r8d, ebx; MaxCount
0x1800274d4  lea     rdx, aApiMs; "api-ms-"
0x1800274db  call    wcsncmp
0x1800274e0  test    eax, eax
0x1800274e2  jz      short loc_180027514
0x1800274e4  mov     r8d, ebx; MaxCount
0x1800274e7  lea     rdx, aExtMs; "ext-ms-"
0x1800274ee  mov     rcx, rbp; String1
0x1800274f1  call    wcsncmp
0x1800274f6  test    eax, eax
0x1800274f8  jz      short loc_180027514
0x1800274fa  xor     r8d, r8d; dwFlags
0x1800274fd  xor     edx, edx; hFile
0x1800274ff  mov     rcx, rbp; lpLibFileName
0x180027502  call    cs:__imp_LoadLibraryExW
0x180027508  mov     rbx, rax
0x18002750b  test    rax, rax
0x18002750e  jnz     loc_1800275BC
0x180027514  or      rax, 0FFFFFFFFFFFFFFFFh
0x180027518  xchg    rax, rva qword_1800D3F80[r13+rdi*8]
0x180027520  or      rax, 0FFFFFFFFFFFFFFFFh
0x180027524  add     rsi, 4
0x180027528  cmp     rsi, r14
0x18002752b  jnz     loc_18002747D
0x180027531  xor     ebx, ebx
0x180027533  mov     edi, 0Eh
0x180027538  mov     ecx, edi
0x18002753a  call    __acrt_lock
0x18002753f  mov     ebp, 100h
0x180027544  mov     [rsp+68h+flOldProtect], 0
0x18002754f  lea     rsi, qword_1800DD000
0x180027556  mov     edx, ebp; dwSize
0x180027558  mov     rcx, rsi; lpAddress
0x18002755b  lea     r9, [rsp+68h+flOldProtect]; lpflOldProtect
0x180027563  lea     r8d, [rdi-0Ah]; flNewProtect
0x180027567  call    cs:__imp_VirtualProtect
0x18002756d  test    eax, eax
0x18002756f  jz      short loc_1800275E9
0x180027571  test    rbx, rbx
0x180027574  mov     rax, rbx
0x180027577  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18002757e  cmovz   rax, rcx
0x180027582  xchg    rax, [rsi+r12*8]
0x180027586  lea     r9, [rsp+68h+flOldProtect]; lpflOldProtect
0x18002758e  mov     edx, ebp; dwSize
0x180027590  lea     r8d, [rdi-0Ch]; flNewProtect
0x180027594  mov     rcx, rsi; lpAddress
0x180027597  call    cs:__imp_VirtualProtect
0x18002759d  test    eax, eax
0x18002759f  jz      short loc_1800275E9
0x1800275a1  mov     ecx, edi
0x1800275a3  call    __acrt_unlock
0x1800275a8  mov     rax, rbx
0x1800275ab  add     rsp, 28h
0x1800275af  pop     r15
0x1800275b1  pop     r14
0x1800275b3  pop     r13
0x1800275b5  pop     r12
0x1800275b7  pop     rdi
0x1800275b8  pop     rsi
0x1800275b9  pop     rbp
0x1800275ba  pop     rbx
0x1800275bb  retn
0x1800275bc  mov     rax, rbx
0x1800275bf  xchg    rax, rva qword_1800D3F80[r13+rdi*8]
0x1800275c7  test    rax, rax
0x1800275ca  jz      short loc_1800275D5
0x1800275cc  mov     rcx, rbx; hLibModule
0x1800275cf  call    cs:__imp_FreeLibrary
0x1800275d5  mov     rdx, r15; lpProcName
0x1800275d8  mov     rcx, rbx; hModule
0x1800275db  call    cs:__imp_GetProcAddress
0x1800275e1  mov     rbx, rax
0x1800275e4  jmp     loc_180027533
0x1800275e9  call    abort
```
