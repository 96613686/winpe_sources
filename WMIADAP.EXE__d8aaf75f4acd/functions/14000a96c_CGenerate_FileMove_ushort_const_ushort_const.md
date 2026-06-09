# CGenerate::FileMove(ushort const *,ushort const *)

- ea: `0x14000a96c`
- end: `0x14000ab88`
- name: `?FileMove@CGenerate@@AEAAJPEBG0@Z`
- size: `540`
- prototype: `__int64 __fastcall(CGenerate *this, wchar_t *, const unsigned __int16 *)`
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
- `0x14000a96c`

## import_xrefs

- `msvcrt!wcslen` at `0x14000a9dd`
- `msvcrt!wcslen` at `0x14000a9e9`
- `msvcrt!wcslen` at `0x14000aa72`
- `msvcrt!wcslen` at `0x14000aa7e`
- `msvcrt!wcslen` at `0x14000a9dd`
- `msvcrt!wcslen` at `0x14000a9e9`
- `msvcrt!wcslen` at `0x14000aa72`
- `msvcrt!wcslen` at `0x14000aa7e`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x14000ab3f`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x14000ab60`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x14000ab69`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x14000ab3f`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x14000ab60`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x14000ab69`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x14000aa0c`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x14000aaa1`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x14000aa0c`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x14000aaa1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000a98e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000a98e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000ab06`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000ab06`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x14000aaed`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x14000aaed`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x14000aafc`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x14000aafc`

## pseudocode

```c
__int64 __fastcall CGenerate::FileMove(CGenerate *this, wchar_t *a2, const unsigned __int16 *a3)
{
  void *v6; // rcx
  signed int v7; // ebx
  unsigned __int16 *WbemDirectory; // rax
  unsigned __int16 *v9; // r14
  int v10; // r12d
  unsigned int v11; // r13d
  unsigned __int16 *v12; // rax
  unsigned __int16 *v13; // rdi
  int v14; // ebx
  unsigned int v15; // r12d
  unsigned __int64 v16; // rax
  unsigned __int16 *v17; // rax
  unsigned __int16 *v18; // rsi
  signed int LastError; // eax
  unsigned __int16 *v21; // [rsp+20h] [rbp-48h]
  unsigned __int16 *v22; // [rsp+78h] [rbp+10h]
  unsigned __int16 *v23; // [rsp+78h] [rbp+10h]
  unsigned __int16 *v24; // [rsp+88h] [rbp+20h]

  v6 = (void *)*((_QWORD *)this + 13);
  if ( v6 )
  {
    CloseHandle(v6);
    *((_QWORD *)this + 13) = 0;
  }
  if ( a2 && a3 )
  {
    v7 = -2147024882;
    WbemDirectory = GetWbemDirectory(1, (HKEY)a2);
    v9 = WbemDirectory;
    v24 = WbemDirectory;
    if ( WbemDirectory )
    {
      try
      {
        v10 = wcslen(WbemDirectory);
        v11 = v10 + wcslen(a2) + 1;
        v12 = (unsigned __int16 *)CWin32DefaultArena::WbemMemAlloc(saturated_mul(v11, 2u));
        v13 = v12;
        v22 = v12;
        v21 = v12;
        if ( v12 )
        {
          v7 = StringCchCopyW(v12, (unsigned int)(v10 + 1), v9);
          if ( v7 >= 0 )
          {
            v7 = StringCchCatW(v13, v11, a2);
            if ( v7 >= 0 )
              v7 = 1;
          }
        }
      }
      catch ( ... )
      {
        v7 = -2147467259;
        v13 = v22;
        v9 = v24;
        goto LABEL_27;
      }
      if ( v7 >= 0 )
      {
        v14 = wcslen(v9);
        v15 = v14 + wcslen(a3) + 1;
        v16 = 2LL * v15;
        if ( !is_mul_ok(v15, 2u) )
          v16 = -1;
        try
        {
          v17 = (unsigned __int16 *)CWin32DefaultArena::WbemMemAlloc(v16);
          v18 = v17;
          v23 = v17;
          if ( v17 )
          {
            v7 = StringCchCopyW(v17, (unsigned int)(v14 + 1), v9);
            if ( v7 >= 0 )
            {
              v7 = StringCchCatW(v18, v15, a3);
              if ( v7 >= 0 )
                v7 = 1;
            }
          }
          else
          {
            v7 = -2147024882;
          }
        }
        catch ( ... )
        {
          v7 = -2147467259;
          v18 = v23;
          v9 = v24;
          v13 = v21;
          goto LABEL_25;
        }
        if ( v7 >= 0 )
        {
          DeleteFileW(v18);
          if ( MoveFileExW(v13, v18, 1u) )
          {
            v7 = 0;
          }
          else
          {
            LastError = GetLastError();
            v7 = LastError;
            if ( LastError > 0 )
              v7 = (unsigned __int16)LastError | 0x80070000;
          }
        }
LABEL_25:
        if ( v18 )
          CWin32DefaultArena::WbemMemFree(v18);
      }
LABEL_27:
      if ( v13 )
        CWin32DefaultArena::WbemMemFree(v13);
      CWin32DefaultArena::WbemMemFree(v9);
    }
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x14000a96c  push    rbx
0x14000a96e  push    rsi
0x14000a96f  push    rdi
0x14000a970  push    r12
0x14000a972  push    r13
0x14000a974  push    r14
0x14000a976  push    r15
0x14000a978  sub     rsp, 30h
0x14000a97c  mov     r15, r8
0x14000a97f  mov     rsi, rdx
0x14000a982  mov     rbx, rcx
0x14000a985  mov     rcx, [rcx+68h]; hObject
0x14000a989  test    rcx, rcx
0x14000a98c  jz      short loc_14000A99C
0x14000a98e  call    cs:__imp_CloseHandle
0x14000a994  mov     qword ptr [rbx+68h], 0
0x14000a99c  test    rsi, rsi
0x14000a99f  jz      loc_14000AB71
0x14000a9a5  test    r15, r15
0x14000a9a8  jz      loc_14000AB71
0x14000a9ae  mov     ebx, 8007000Eh
0x14000a9b3  mov     [rsp+68h+arg_8], 0
0x14000a9bc  mov     ecx, 1; int
0x14000a9c1  call    ?GetWbemDirectory@@YAPEAGH@Z; GetWbemDirectory(int)
0x14000a9c6  mov     r14, rax
0x14000a9c9  mov     [rsp+68h+arg_18], rax
0x14000a9d1  test    rax, rax
0x14000a9d4  jz      loc_14000AB76
0x14000a9da  mov     rcx, rax; String
0x14000a9dd  call    cs:__imp_wcslen
0x14000a9e3  mov     r12, rax
0x14000a9e6  mov     rcx, rsi; String
0x14000a9e9  call    cs:__imp_wcslen
0x14000a9ef  lea     r13d, [rax+1]
0x14000a9f3  add     r13d, r12d
0x14000a9f6  mov     eax, 2
0x14000a9fb  mul     r13
0x14000a9fe  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x14000aa05  cmovb   rax, rcx
0x14000aa09  mov     rcx, rax
0x14000aa0c  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x14000aa12  mov     rdi, rax
0x14000aa15  mov     [rsp+68h+arg_8], rax
0x14000aa1a  mov     [rsp+68h+var_48], rax
0x14000aa1f  test    rax, rax
0x14000aa22  jz      short loc_14000AA58
0x14000aa24  lea     edx, [r12+1]; unsigned __int64
0x14000aa29  mov     r8, r14; unsigned __int16 *
0x14000aa2c  mov     rcx, rax; unsigned __int16 *
0x14000aa2f  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x14000aa34  mov     ebx, eax
0x14000aa36  test    eax, eax
0x14000aa38  js      short loc_14000AA58
0x14000aa3a  mov     r8, rsi; unsigned __int16 *
0x14000aa3d  mov     edx, r13d; unsigned __int64
0x14000aa40  mov     rcx, rdi; unsigned __int16 *
0x14000aa43  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x14000aa48  mov     ebx, eax
0x14000aa4a  test    eax, eax
0x14000aa4c  mov     r13d, 1
0x14000aa52  cmovns  ebx, r13d
0x14000aa56  jmp     short loc_14000AA5E
0x14000aa58  mov     r13d, 1
0x14000aa5e  mov     [rsp+68h+arg_8], 0
0x14000aa67  test    ebx, ebx
0x14000aa69  js      loc_14000AB58
0x14000aa6f  mov     rcx, r14; String
0x14000aa72  call    cs:__imp_wcslen
0x14000aa78  mov     rbx, rax
0x14000aa7b  mov     rcx, r15; String
0x14000aa7e  call    cs:__imp_wcslen
0x14000aa84  lea     r12d, [rax+1]
0x14000aa88  add     r12d, ebx
0x14000aa8b  mov     eax, 2
0x14000aa90  mul     r12
0x14000aa93  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x14000aa9a  cmovb   rax, rcx
0x14000aa9e  mov     rcx, rax
0x14000aaa1  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x14000aaa7  mov     rsi, rax
0x14000aaaa  mov     [rsp+68h+arg_8], rax
0x14000aaaf  test    rax, rax
0x14000aab2  jz      short loc_14000AAE1
0x14000aab4  lea     edx, [rbx+1]; unsigned __int64
0x14000aab7  mov     r8, r14; unsigned __int16 *
0x14000aaba  mov     rcx, rax; unsigned __int16 *
0x14000aabd  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x14000aac2  mov     ebx, eax
0x14000aac4  test    eax, eax
0x14000aac6  js      short loc_14000AAE6
0x14000aac8  mov     r8, r15; unsigned __int16 *
0x14000aacb  mov     edx, r12d; unsigned __int64
0x14000aace  mov     rcx, rsi; unsigned __int16 *
0x14000aad1  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x14000aad6  mov     ebx, eax
0x14000aad8  test    eax, eax
0x14000aada  js      short loc_14000AAE6
0x14000aadc  mov     ebx, r13d
0x14000aadf  jmp     short loc_14000AAE6
0x14000aae1  mov     ebx, 8007000Eh
0x14000aae6  test    ebx, ebx
0x14000aae8  js      short loc_14000AB37
0x14000aaea  mov     rcx, rsi; lpFileName
0x14000aaed  call    cs:__imp_DeleteFileW
0x14000aaf3  mov     r8d, r13d; dwFlags
0x14000aaf6  mov     rdx, rsi; lpNewFileName
0x14000aaf9  mov     rcx, rdi; lpExistingFileName
0x14000aafc  call    cs:__imp_MoveFileExW
0x14000ab02  test    eax, eax
0x14000ab04  jnz     short loc_14000AB1D
0x14000ab06  call    cs:__imp_GetLastError
0x14000ab0c  mov     ebx, eax
0x14000ab0e  test    eax, eax
0x14000ab10  jle     short loc_14000AB37
0x14000ab12  movzx   ebx, ax
0x14000ab15  or      ebx, 80070000h
0x14000ab1b  jmp     short loc_14000AB37
0x14000ab1d  xor     ebx, ebx
0x14000ab1f  jmp     short loc_14000AB37
0x14000ab21  mov     ebx, [rsp+68h+arg_0]
0x14000ab25  mov     rsi, [rsp+68h+arg_8]
0x14000ab2a  mov     r14, [rsp+68h+arg_18]
0x14000ab32  mov     rdi, [rsp+68h+var_48]
0x14000ab37  test    rsi, rsi
0x14000ab3a  jz      short loc_14000AB58
0x14000ab3c  mov     rcx, rsi
0x14000ab3f  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x14000ab45  jmp     short loc_14000AB58
0x14000ab47  mov     ebx, [rsp+68h+arg_0]
0x14000ab4b  mov     rdi, [rsp+68h+arg_8]
0x14000ab50  mov     r14, [rsp+68h+arg_18]
0x14000ab58  test    rdi, rdi
0x14000ab5b  jz      short loc_14000AB66
0x14000ab5d  mov     rcx, rdi
0x14000ab60  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x14000ab66  mov     rcx, r14
0x14000ab69  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x14000ab6f  jmp     short loc_14000AB76
0x14000ab71  mov     ebx, 80070057h
0x14000ab76  mov     eax, ebx
0x14000ab78  add     rsp, 30h
0x14000ab7c  pop     r15
0x14000ab7e  pop     r14
0x14000ab80  pop     r13
0x14000ab82  pop     r12
0x14000ab84  pop     rdi
0x14000ab85  pop     rsi
0x14000ab86  pop     rbx
0x14000ab87  retn
```
