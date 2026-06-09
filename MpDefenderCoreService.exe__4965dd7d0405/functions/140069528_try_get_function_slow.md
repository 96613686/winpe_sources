# try_get_function_slow

- ea: `0x140069528`
- end: `0x1400696da`
- name: `try_get_function_slow`
- size: `434`
- prototype: ``
- caller_count: `18`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x1400694f0`
- `0x1400696dc`
- `0x140069738`
- `0x140069794`
- `0x1400698a4`
- `0x140069974`
- `0x140069a3c`
- `0x140069ad0`
- `0x140069b88`
- `0x140069c00`
- `0x140069c68`
- `0x140069cf0`
- `0x140069de4`
- `0x140069e48`
- `0x140069e98`
- `0x140069edc`
- `0x140069f50`
- `0x14006a130`

## callees

- `0x14004f9a8`
- `0x14005d2d0`
- `0x140064ad8`
- `0x140064b38`
- `0x140069528`

## import_xrefs

- `KERNEL32!LoadLibraryExW` at `0x140069595`
- `KERNEL32!LoadLibraryExW` at `0x1400695e9`
- `KERNEL32!LoadLibraryExW` at `0x140069595`
- `KERNEL32!LoadLibraryExW` at `0x1400695e9`
- `KERNEL32!GetLastError` at `0x1400695a7`
- `KERNEL32!GetLastError` at `0x1400695a7`
- `KERNEL32!FreeLibrary` at `0x1400696ba`
- `KERNEL32!FreeLibrary` at `0x1400696ba`
- `KERNEL32!GetProcAddress` at `0x1400696c6`
- `KERNEL32!GetProcAddress` at `0x1400696c6`
- `KERNEL32!VirtualProtect` at `0x140069645`
- `KERNEL32!VirtualProtect` at `0x140069676`
- `KERNEL32!VirtualProtect` at `0x140069645`
- `KERNEL32!VirtualProtect` at `0x140069676`

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
  DWORD flOldProtect; // [rsp+60h] [rbp+18h] BYREF

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
    Library = (HMODULE)qword_1401E5830[v8];
    if ( !Library )
      break;
    if ( Library != (HMODULE)-1LL )
      goto LABEL_20;
LABEL_11:
    if ( ++v6 == a4 )
      goto LABEL_12;
  }
  v10 = off_1401818D0[v8];
  Library = LoadLibraryExW(v10, 0, 0x800u);
  if ( !Library
    && (GetLastError() != 87
     || !wcsncmp(v10, L"api-ms-", 7u)
     || !wcsncmp(v10, L"ext-ms-", 7u)
     || (Library = LoadLibraryExW(v10, 0, 0)) == 0) )
  {
    _InterlockedExchange64(&qword_1401E5830[v8], -1);
    goto LABEL_11;
  }
  if ( _InterlockedExchange64(&qword_1401E5830[v8], (__int64)Library) )
    FreeLibrary(Library);
LABEL_20:
  ProcAddress = GetProcAddress(Library, a2);
LABEL_13:
  _acrt_lock(14);
  flOldProtect = 0;
  if ( !VirtualProtect(qword_1401F8000, 0x100u, 4u, &flOldProtect) )
    goto LABEL_21;
  v12 = (__int64)ProcAddress;
  if ( !ProcAddress )
    v12 = -1;
  _InterlockedExchange64(&qword_1401F8000[v4], v12);
  if ( !VirtualProtect(qword_1401F8000, 0x100u, 2u, &flOldProtect) )
LABEL_21:
    abort();
  _acrt_unlock(14);
  return ProcAddress;
}

```

## disassembly

```asm
0x140069528  mov     [rsp+arg_0], rbx
0x14006952d  mov     [rsp+arg_8], rbp
0x140069532  mov     [rsp+arg_18], rsi
0x140069537  push    rdi
0x140069538  push    r12
0x14006953a  push    r13
0x14006953c  push    r14
0x14006953e  push    r15
0x140069540  sub     rsp, 20h
0x140069544  or      rax, 0FFFFFFFFFFFFFFFFh
0x140069548  mov     r12d, ecx
0x14006954b  mov     r14, r9
0x14006954e  mov     rsi, r8
0x140069551  mov     r15, rdx
0x140069554  cmp     r8, r9
0x140069557  jz      loc_140069618
0x14006955d  lea     r13, cs:140000000h
0x140069564  mov     edi, [rsi]
0x140069566  mov     rbx, rva qword_1401E5830[r13+rdi*8]
0x14006956e  nop
0x14006956f  test    rbx, rbx
0x140069572  jz      short loc_140069582
0x140069574  cmp     rbx, rax
0x140069577  jnz     loc_1400696C0
0x14006957d  jmp     loc_14006960B
0x140069582  mov     rbp, ds:rva off_1401818D0[r13+rdi*8]; "api-ms-win-core-datetime-l1-1-1" ...
0x14006958a  xor     edx, edx; hFile
0x14006958c  mov     rcx, rbp; lpLibFileName
0x14006958f  mov     r8d, 800h; dwFlags
0x140069595  call    cs:__imp_LoadLibraryExW
0x14006959b  mov     rbx, rax
0x14006959e  test    rax, rax
0x1400695a1  jnz     loc_1400696A7
0x1400695a7  call    cs:__imp_GetLastError
0x1400695ad  cmp     eax, 57h ; 'W'
0x1400695b0  jnz     short loc_1400695FB
0x1400695b2  lea     ebx, [rax-50h]
0x1400695b5  mov     rcx, rbp; String1
0x1400695b8  mov     r8d, ebx; MaxCount
0x1400695bb  lea     rdx, aApiMs; "api-ms-"
0x1400695c2  call    wcsncmp
0x1400695c7  test    eax, eax
0x1400695c9  jz      short loc_1400695FB
0x1400695cb  mov     r8d, ebx; MaxCount
0x1400695ce  lea     rdx, aExtMs; "ext-ms-"
0x1400695d5  mov     rcx, rbp; String1
0x1400695d8  call    wcsncmp
0x1400695dd  test    eax, eax
0x1400695df  jz      short loc_1400695FB
0x1400695e1  xor     r8d, r8d; dwFlags
0x1400695e4  xor     edx, edx; hFile
0x1400695e6  mov     rcx, rbp; lpLibFileName
0x1400695e9  call    cs:__imp_LoadLibraryExW
0x1400695ef  mov     rbx, rax
0x1400695f2  test    rax, rax
0x1400695f5  jnz     loc_1400696A7
0x1400695fb  or      rax, 0FFFFFFFFFFFFFFFFh
0x1400695ff  xchg    rax, rva qword_1401E5830[r13+rdi*8]
0x140069607  or      rax, 0FFFFFFFFFFFFFFFFh
0x14006960b  add     rsi, 4
0x14006960f  cmp     rsi, r14
0x140069612  jnz     loc_140069564
0x140069618  xor     ebx, ebx
0x14006961a  mov     edi, 0Eh
0x14006961f  mov     ecx, edi
0x140069621  call    __acrt_lock
0x140069626  and     [rsp+48h+flOldProtect], 0
0x14006962b  lea     rsi, qword_1401F8000
0x140069632  mov     ebp, 100h
0x140069637  lea     r9, [rsp+48h+flOldProtect]; lpflOldProtect
0x14006963c  mov     edx, ebp; dwSize
0x14006963e  lea     r8d, [rdi-0Ah]; flNewProtect
0x140069642  mov     rcx, rsi; lpAddress
0x140069645  call    cs:__imp_VirtualProtect
0x14006964b  test    eax, eax
0x14006964d  jz      loc_1400696D4
0x140069653  test    rbx, rbx
0x140069656  mov     rax, rbx
0x140069659  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x140069660  cmovz   rax, rcx
0x140069664  xchg    rax, [rsi+r12*8]
0x140069668  lea     r9, [rsp+48h+flOldProtect]; lpflOldProtect
0x14006966d  mov     edx, ebp; dwSize
0x14006966f  lea     r8d, [rdi-0Ch]; flNewProtect
0x140069673  mov     rcx, rsi; lpAddress
0x140069676  call    cs:__imp_VirtualProtect
0x14006967c  test    eax, eax
0x14006967e  jz      short loc_1400696D4
0x140069680  mov     ecx, edi
0x140069682  call    __acrt_unlock
0x140069687  mov     rbp, [rsp+48h+arg_8]
0x14006968c  mov     rax, rbx
0x14006968f  mov     rbx, [rsp+48h+arg_0]
0x140069694  mov     rsi, [rsp+48h+arg_18]
0x140069699  add     rsp, 20h
0x14006969d  pop     r15
0x14006969f  pop     r14
0x1400696a1  pop     r13
0x1400696a3  pop     r12
0x1400696a5  pop     rdi
0x1400696a6  retn
0x1400696a7  mov     rax, rbx
0x1400696aa  xchg    rax, rva qword_1401E5830[r13+rdi*8]
0x1400696b2  test    rax, rax
0x1400696b5  jz      short loc_1400696C0
0x1400696b7  mov     rcx, rbx; hLibModule
0x1400696ba  call    cs:__imp_FreeLibrary
0x1400696c0  mov     rdx, r15; lpProcName
0x1400696c3  mov     rcx, rbx; hModule
0x1400696c6  call    cs:__imp_GetProcAddress
0x1400696cc  mov     rbx, rax
0x1400696cf  jmp     loc_14006961A
0x1400696d4  call    abort
```
