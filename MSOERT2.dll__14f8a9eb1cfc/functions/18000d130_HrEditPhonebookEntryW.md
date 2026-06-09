# HrEditPhonebookEntryW

- ea: `0x18000d130`
- end: `0x18000d20d`
- name: `HrEditPhonebookEntryW`
- size: `221`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x18000d130`
- `0x180012f8e`
- `0x180012fc0`
- `0x180014010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18000d1c0`
- `KERNEL32!GetLastError` at `0x18000d1d3`
- `KERNEL32!GetLastError` at `0x18000d1c0`
- `KERNEL32!GetLastError` at `0x18000d1d3`
- `KERNEL32!LoadLibraryA` at `0x18000d160`
- `KERNEL32!LoadLibraryA` at `0x18000d160`
- `KERNEL32!GetProcAddress` at `0x18000d178`
- `KERNEL32!GetProcAddress` at `0x18000d178`
- `KERNEL32!FreeLibrary` at `0x18000d1cb`
- `KERNEL32!FreeLibrary` at `0x18000d1cb`

## string_xrefs

- `0x18000d156`: `rasdlg.dll`

## pseudocode

```c
__int64 __fastcall HrEditPhonebookEntryW(__int64 a1, __int64 a2, DWORD *a3)
{
  HMODULE LibraryA; // rax
  HMODULE v7; // rdi
  FARPROC ProcAddress; // rbx
  DWORD LastError; // ebx
  int v11; // [rsp+20h] [rbp-268h] BYREF
  __int64 v12; // [rsp+24h] [rbp-264h]
  _BYTE v13[528]; // [rsp+2Ch] [rbp-25Ch] BYREF
  DWORD v14; // [rsp+23Ch] [rbp-4Ch]

  LibraryA = LoadLibraryA("rasdlg.dll");
  v7 = LibraryA;
  if ( LibraryA )
  {
    ProcAddress = GetProcAddress(LibraryA, "RasEntryDlgW");
    if ( ProcAddress )
    {
      memset_0(v13, 0, 0x224u);
      v11 = 560;
      v12 = a1;
      ((void (__fastcall *)(_QWORD, __int64, int *))ProcAddress)(0, a2, &v11);
      LastError = v14;
    }
    else
    {
      LastError = GetLastError();
    }
    FreeLibrary(v7);
  }
  else
  {
    LastError = GetLastError();
  }
  if ( !LastError )
    return 0;
  if ( a3 )
    *a3 = LastError;
  return 2148322500LL;
}

```

## disassembly

```asm
0x18000d130  push    rbx
0x18000d132  push    rbp
0x18000d133  push    rsi
0x18000d134  push    rdi
0x18000d135  push    r14
0x18000d137  sub     rsp, 260h
0x18000d13e  mov     rax, cs:__security_cookie
0x18000d145  xor     rax, rsp
0x18000d148  mov     [rsp+288h+var_38], rax
0x18000d150  mov     rbp, rcx
0x18000d153  mov     rsi, r8
0x18000d156  lea     rcx, aRasdlgDll; "rasdlg.dll"
0x18000d15d  mov     r14, rdx
0x18000d160  call    cs:__imp_LoadLibraryA
0x18000d166  mov     rdi, rax
0x18000d169  test    rax, rax
0x18000d16c  jz      short loc_18000D1D3
0x18000d16e  lea     rdx, ProcName; "RasEntryDlgW"
0x18000d175  mov     rcx, rax; hModule
0x18000d178  call    cs:__imp_GetProcAddress
0x18000d17e  mov     rbx, rax
0x18000d181  test    rax, rax
0x18000d184  jz      short loc_18000D1C0
0x18000d186  xor     edx, edx; Val
0x18000d188  lea     rcx, [rsp+288h+var_25C]; void *
0x18000d18d  mov     r8d, 224h; Size
0x18000d193  call    memset_0
0x18000d198  lea     r8, [rsp+288h+var_268]
0x18000d19d  mov     [rsp+288h+var_268], 230h
0x18000d1a5  mov     rdx, r14
0x18000d1a8  mov     [rsp+288h+var_264], rbp
0x18000d1ad  xor     ecx, ecx
0x18000d1af  mov     rax, rbx
0x18000d1b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d1b7  mov     ebx, [rsp+288h+var_4C]
0x18000d1be  jmp     short loc_18000D1C8
0x18000d1c0  call    cs:__imp_GetLastError
0x18000d1c6  mov     ebx, eax
0x18000d1c8  mov     rcx, rdi; hLibModule
0x18000d1cb  call    cs:__imp_FreeLibrary
0x18000d1d1  jmp     short loc_18000D1DB
0x18000d1d3  call    cs:__imp_GetLastError
0x18000d1d9  mov     ebx, eax
0x18000d1db  test    ebx, ebx
0x18000d1dd  jz      short loc_18000D1ED
0x18000d1df  test    rsi, rsi
0x18000d1e2  jz      short loc_18000D1E6
0x18000d1e4  mov     [rsi], ebx
0x18000d1e6  mov     eax, 800CCCC4h
0x18000d1eb  jmp     short loc_18000D1EF
0x18000d1ed  xor     eax, eax
0x18000d1ef  mov     rcx, [rsp+288h+var_38]
0x18000d1f7  xor     rcx, rsp; StackCookie
0x18000d1fa  call    __security_check_cookie
0x18000d1ff  add     rsp, 260h
0x18000d206  pop     r14
0x18000d208  pop     rdi
0x18000d209  pop     rsi
0x18000d20a  pop     rbp
0x18000d20b  pop     rbx
0x18000d20c  retn
```
