# CGenerate::FileDelete(ushort const *)

- ea: `0x14000a828`
- end: `0x14000a964`
- name: `?FileDelete@CGenerate@@AEAAJPEBG@Z`
- size: `316`
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
- `0x14000a828`

## import_xrefs

- `msvcrt!wcslen` at `0x14000a88e`
- `msvcrt!wcslen` at `0x14000a89a`
- `msvcrt!wcslen` at `0x14000a88e`
- `msvcrt!wcslen` at `0x14000a89a`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x14000a93c`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x14000a945`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x14000a93c`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x14000a945`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x14000a8bc`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x14000a8bc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000a847`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000a847`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000a90b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000a90b`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x14000a901`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x14000a901`

## pseudocode

```c
__int64 __fastcall CGenerate::FileDelete(CGenerate *this, wchar_t *a2)
{
  void *v4; // rcx
  signed int v5; // ebx
  unsigned __int16 *WbemDirectory; // rax
  unsigned __int16 *v7; // rsi
  int v8; // r15d
  unsigned int v9; // r12d
  unsigned __int16 *v10; // rax
  unsigned __int16 *v11; // rdi
  signed int LastError; // eax
  unsigned __int16 *v14; // [rsp+68h] [rbp+10h]
  unsigned __int16 *v15; // [rsp+70h] [rbp+18h]

  v4 = (void *)*((_QWORD *)this + 13);
  if ( v4 )
  {
    CloseHandle(v4);
    *((_QWORD *)this + 13) = 0;
  }
  if ( a2 )
  {
    v5 = -2147024882;
    WbemDirectory = GetWbemDirectory(1, (HKEY)a2);
    v7 = WbemDirectory;
    v15 = WbemDirectory;
    if ( WbemDirectory )
    {
      try
      {
        v8 = wcslen(WbemDirectory);
        v9 = v8 + wcslen(a2) + 1;
        v10 = (unsigned __int16 *)CWin32DefaultArena::WbemMemAlloc(saturated_mul(v9, 2u));
        v11 = v10;
        v14 = v10;
        if ( v10 )
        {
          v5 = StringCchCopyW(v10, (unsigned int)(v8 + 1), v7);
          if ( v5 >= 0 )
          {
            v5 = StringCchCatW(v11, v9, a2);
            if ( v5 >= 0 )
              v5 = 1;
          }
        }
      }
      catch ( ... )
      {
        v5 = -2147467259;
        v11 = v14;
        v7 = v15;
        goto LABEL_15;
      }
      if ( v5 >= 0 )
      {
        if ( DeleteFileW(v11) )
        {
          v5 = 0;
        }
        else
        {
          LastError = GetLastError();
          v5 = LastError;
          if ( LastError > 0 )
            v5 = (unsigned __int16)LastError | 0x80070000;
        }
      }
LABEL_15:
      if ( v11 )
        CWin32DefaultArena::WbemMemFree(v11);
      CWin32DefaultArena::WbemMemFree(v7);
    }
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x14000a828  push    rbx
0x14000a82a  push    rsi
0x14000a82b  push    rdi
0x14000a82c  push    r12
0x14000a82e  push    r13
0x14000a830  push    r14
0x14000a832  push    r15
0x14000a834  sub     rsp, 20h
0x14000a838  mov     r14, rdx
0x14000a83b  mov     rbx, rcx
0x14000a83e  mov     rcx, [rcx+68h]; hObject
0x14000a842  test    rcx, rcx
0x14000a845  jz      short loc_14000A855
0x14000a847  call    cs:__imp_CloseHandle
0x14000a84d  mov     qword ptr [rbx+68h], 0
0x14000a855  test    r14, r14
0x14000a858  jz      loc_14000A94D
0x14000a85e  mov     ebx, 8007000Eh
0x14000a863  mov     [rsp+58h+arg_8], 0
0x14000a86c  mov     r13d, 1
0x14000a872  mov     ecx, r13d; int
0x14000a875  call    ?GetWbemDirectory@@YAPEAGH@Z; GetWbemDirectory(int)
0x14000a87a  mov     rsi, rax
0x14000a87d  mov     [rsp+58h+arg_10], rax
0x14000a882  test    rax, rax
0x14000a885  jz      loc_14000A952
0x14000a88b  mov     rcx, rax; String
0x14000a88e  call    cs:__imp_wcslen
0x14000a894  mov     r15, rax
0x14000a897  mov     rcx, r14; String
0x14000a89a  call    cs:__imp_wcslen
0x14000a8a0  lea     r12d, [rax+1]
0x14000a8a4  add     r12d, r15d
0x14000a8a7  lea     eax, [r13+1]
0x14000a8ab  mul     r12
0x14000a8ae  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x14000a8b5  cmovb   rax, rcx
0x14000a8b9  mov     rcx, rax
0x14000a8bc  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x14000a8c2  mov     rdi, rax
0x14000a8c5  mov     [rsp+58h+arg_8], rax
0x14000a8ca  test    rax, rax
0x14000a8cd  jz      short loc_14000A8FA
0x14000a8cf  lea     edx, [r15+1]; unsigned __int64
0x14000a8d3  mov     r8, rsi; unsigned __int16 *
0x14000a8d6  mov     rcx, rax; unsigned __int16 *
0x14000a8d9  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x14000a8de  mov     ebx, eax
0x14000a8e0  test    eax, eax
0x14000a8e2  js      short loc_14000A8FA
0x14000a8e4  mov     r8, r14; unsigned __int16 *
0x14000a8e7  mov     edx, r12d; unsigned __int64
0x14000a8ea  mov     rcx, rdi; unsigned __int16 *
0x14000a8ed  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x14000a8f2  mov     ebx, eax
0x14000a8f4  test    eax, eax
0x14000a8f6  cmovns  ebx, r13d
0x14000a8fa  test    ebx, ebx
0x14000a8fc  js      short loc_14000A934
0x14000a8fe  mov     rcx, rdi; lpFileName
0x14000a901  call    cs:__imp_DeleteFileW
0x14000a907  test    eax, eax
0x14000a909  jnz     short loc_14000A922
0x14000a90b  call    cs:__imp_GetLastError
0x14000a911  mov     ebx, eax
0x14000a913  test    eax, eax
0x14000a915  jle     short loc_14000A934
0x14000a917  movzx   ebx, ax
0x14000a91a  or      ebx, 80070000h
0x14000a920  jmp     short loc_14000A934
0x14000a922  xor     ebx, ebx
0x14000a924  jmp     short loc_14000A934
0x14000a926  mov     ebx, [rsp+58h+arg_0]
0x14000a92a  mov     rdi, [rsp+58h+arg_8]
0x14000a92f  mov     rsi, [rsp+58h+arg_10]
0x14000a934  test    rdi, rdi
0x14000a937  jz      short loc_14000A942
0x14000a939  mov     rcx, rdi
0x14000a93c  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x14000a942  mov     rcx, rsi
0x14000a945  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x14000a94b  jmp     short loc_14000A952
0x14000a94d  mov     ebx, 80070057h
0x14000a952  mov     eax, ebx
0x14000a954  add     rsp, 20h
0x14000a958  pop     r15
0x14000a95a  pop     r14
0x14000a95c  pop     r13
0x14000a95e  pop     r12
0x14000a960  pop     rdi
0x14000a961  pop     rsi
0x14000a962  pop     rbx
0x14000a963  retn
```
