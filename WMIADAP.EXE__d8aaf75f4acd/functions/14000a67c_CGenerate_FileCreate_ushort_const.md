# CGenerate::FileCreate(ushort const *)

- ea: `0x14000a67c`
- end: `0x14000a821`
- name: `?FileCreate@CGenerate@@AEAAJPEBG@Z`
- size: `421`
- prototype: `__int64 __fastcall(CGenerate *this, wchar_t *)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callers

- `0x14000b9c8`
- `0x14000c5b0`

## callees

- `0x140006284`
- `0x140006df0`
- `0x1400075f8`
- `0x14000a67c`

## import_xrefs

- `msvcrt!wcslen` at `0x14000a6cd`
- `msvcrt!wcslen` at `0x14000a6d9`
- `msvcrt!wcslen` at `0x14000a6cd`
- `msvcrt!wcslen` at `0x14000a6d9`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x14000a7f9`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x14000a802`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x14000a7f9`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x14000a802`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x14000a6fc`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x14000a6fc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000a762`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000a76f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000a7bf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000a762`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000a76f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000a7bf`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x14000a758`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x14000a758`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x14000a7af`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x14000a7af`

## pseudocode

```c
__int64 __fastcall CGenerate::FileCreate(CGenerate *this, wchar_t *a2)
{
  signed int v4; // ebx
  unsigned __int16 *WbemDirectory; // rax
  unsigned __int16 *v6; // rsi
  int v7; // r15d
  unsigned int v8; // r12d
  unsigned __int64 v9; // rax
  unsigned __int16 *v10; // rax
  unsigned __int16 *v11; // rdi
  signed int LastError; // eax
  HANDLE FileW; // rax
  signed int v14; // eax
  unsigned __int16 *v16; // [rsp+90h] [rbp+18h]
  unsigned __int16 *v17; // [rsp+98h] [rbp+20h]

  if ( a2 )
  {
    v4 = -2147024882;
    WbemDirectory = GetWbemDirectory(1, (HKEY)a2);
    v6 = WbemDirectory;
    v17 = WbemDirectory;
    if ( WbemDirectory )
    {
      v7 = wcslen(WbemDirectory);
      v8 = v7 + wcslen(a2) + 1;
      v9 = 2LL * v8;
      if ( !is_mul_ok(v8, 2u) )
        v9 = -1;
      try
      {
        v10 = (unsigned __int16 *)CWin32DefaultArena::WbemMemAlloc(v9);
        v11 = v10;
        v16 = v10;
        if ( v10 )
        {
          v4 = StringCchCopyW(v10, (unsigned int)(v7 + 1), v6);
          if ( v4 >= 0 )
          {
            v4 = StringCchCatW(v11, v8, a2);
            if ( v4 >= 0 )
              v4 = 1;
          }
        }
      }
      catch ( ... )
      {
        v4 = -2147467259;
        v11 = v16;
        v6 = v17;
        goto LABEL_20;
      }
      if ( v4 >= 0 )
      {
        if ( CreateDirectoryW(v6, 0) || GetLastError() == 183 )
          goto LABEL_16;
        LastError = GetLastError();
        v4 = LastError;
        if ( LastError > 0 )
          v4 = (unsigned __int16)LastError | 0x80070000;
        if ( v4 >= 0 )
        {
LABEL_16:
          FileW = CreateFileW(v11, 0x40000000u, 1u, 0, 2u, 0x80u, 0);
          *((_QWORD *)this + 13) = FileW;
          if ( FileW == (HANDLE)-1LL )
          {
            v14 = GetLastError();
            v4 = v14;
            if ( v14 > 0 )
              v4 = (unsigned __int16)v14 | 0x80070000;
          }
          else
          {
            v4 = 0;
          }
        }
      }
LABEL_20:
      if ( v11 )
        CWin32DefaultArena::WbemMemFree(v11);
      CWin32DefaultArena::WbemMemFree(v6);
    }
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x14000a67c  push    rbx
0x14000a67e  push    rsi
0x14000a67f  push    rdi
0x14000a680  push    r12
0x14000a682  push    r13
0x14000a684  push    r14
0x14000a686  push    r15
0x14000a688  sub     rsp, 40h
0x14000a68c  mov     r14, rdx
0x14000a68f  mov     r13, rcx
0x14000a692  test    rdx, rdx
0x14000a695  jz      loc_14000A80A
0x14000a69b  mov     ebx, 8007000Eh
0x14000a6a0  mov     [rsp+78h+arg_10], 0
0x14000a6ac  mov     ecx, 1; int
0x14000a6b1  call    ?GetWbemDirectory@@YAPEAGH@Z; GetWbemDirectory(int)
0x14000a6b6  mov     rsi, rax
0x14000a6b9  mov     [rsp+78h+arg_18], rax
0x14000a6c1  test    rax, rax
0x14000a6c4  jz      loc_14000A80F
0x14000a6ca  mov     rcx, rax; String
0x14000a6cd  call    cs:__imp_wcslen
0x14000a6d3  mov     r15, rax
0x14000a6d6  mov     rcx, r14; String
0x14000a6d9  call    cs:__imp_wcslen
0x14000a6df  lea     r12d, [rax+1]
0x14000a6e3  add     r12d, r15d
0x14000a6e6  mov     eax, 2
0x14000a6eb  mul     r12
0x14000a6ee  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x14000a6f5  cmovb   rax, rcx
0x14000a6f9  mov     rcx, rax
0x14000a6fc  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x14000a702  mov     rdi, rax
0x14000a705  mov     [rsp+78h+arg_10], rax
0x14000a70d  test    rax, rax
0x14000a710  jz      short loc_14000A745
0x14000a712  lea     edx, [r15+1]; unsigned __int64
0x14000a716  mov     r8, rsi; unsigned __int16 *
0x14000a719  mov     rcx, rax; unsigned __int16 *
0x14000a71c  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x14000a721  mov     ebx, eax
0x14000a723  test    eax, eax
0x14000a725  js      short loc_14000A745
0x14000a727  mov     r8, r14; unsigned __int16 *
0x14000a72a  mov     edx, r12d; unsigned __int64
0x14000a72d  mov     rcx, rdi; unsigned __int16 *
0x14000a730  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x14000a735  mov     ebx, eax
0x14000a737  test    eax, eax
0x14000a739  mov     r14d, 1
0x14000a73f  cmovns  ebx, r14d
0x14000a743  jmp     short loc_14000A74B
0x14000a745  mov     r14d, 1
0x14000a74b  test    ebx, ebx
0x14000a74d  js      loc_14000A7F1
0x14000a753  xor     edx, edx; lpSecurityAttributes
0x14000a755  mov     rcx, rsi; lpPathName
0x14000a758  call    cs:__imp_CreateDirectoryW
0x14000a75e  test    eax, eax
0x14000a760  jnz     short loc_14000A788
0x14000a762  call    cs:__imp_GetLastError
0x14000a768  cmp     eax, 0B7h
0x14000a76d  jz      short loc_14000A788
0x14000a76f  call    cs:__imp_GetLastError
0x14000a775  mov     ebx, eax
0x14000a777  test    eax, eax
0x14000a779  jle     short loc_14000A784
0x14000a77b  movzx   ebx, ax
0x14000a77e  or      ebx, 80070000h
0x14000a784  test    ebx, ebx
0x14000a786  js      short loc_14000A7F1
0x14000a788  mov     [rsp+78h+hTemplateFile], 0; hTemplateFile
0x14000a791  mov     [rsp+78h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x14000a799  mov     [rsp+78h+dwCreationDisposition], 2; dwCreationDisposition
0x14000a7a1  xor     r9d, r9d; lpSecurityAttributes
0x14000a7a4  mov     r8d, r14d; dwShareMode
0x14000a7a7  mov     edx, 40000000h; dwDesiredAccess
0x14000a7ac  mov     rcx, rdi; lpFileName
0x14000a7af  call    cs:__imp_CreateFileW
0x14000a7b5  mov     [r13+68h], rax
0x14000a7b9  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14000a7bd  jnz     short loc_14000A7D6
0x14000a7bf  call    cs:__imp_GetLastError
0x14000a7c5  mov     ebx, eax
0x14000a7c7  test    eax, eax
0x14000a7c9  jle     short loc_14000A7F1
0x14000a7cb  movzx   ebx, ax
0x14000a7ce  or      ebx, 80070000h
0x14000a7d4  jmp     short loc_14000A7F1
0x14000a7d6  xor     ebx, ebx
0x14000a7d8  jmp     short loc_14000A7F1
0x14000a7da  mov     ebx, [rsp+78h+arg_8]
0x14000a7e1  mov     rdi, [rsp+78h+arg_10]
0x14000a7e9  mov     rsi, [rsp+78h+arg_18]
0x14000a7f1  test    rdi, rdi
0x14000a7f4  jz      short loc_14000A7FF
0x14000a7f6  mov     rcx, rdi
0x14000a7f9  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x14000a7ff  mov     rcx, rsi
0x14000a802  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x14000a808  jmp     short loc_14000A80F
0x14000a80a  mov     ebx, 80070057h
0x14000a80f  mov     eax, ebx
0x14000a811  add     rsp, 40h
0x14000a815  pop     r15
0x14000a817  pop     r14
0x14000a819  pop     r13
0x14000a81b  pop     r12
0x14000a81d  pop     rdi
0x14000a81e  pop     rsi
0x14000a81f  pop     rbx
0x14000a820  retn
```
