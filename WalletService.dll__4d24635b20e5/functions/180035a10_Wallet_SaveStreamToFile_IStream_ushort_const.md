# Wallet::SaveStreamToFile(IStream *,ushort const *)

- ea: `0x180035a10`
- end: `0x180035b5a`
- name: `?SaveStreamToFile@Wallet@@YAJPEAUIStream@@PEBG@Z`
- size: `330`
- prototype: `__int64 __fastcall(Wallet *this, const WCHAR *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x180035260`

## callees

- `0x180002e48`
- `0x1800056c0`
- `0x18000bcd4`
- `0x18001b458`
- `0x180035a10`
- `0x180045010`

## import_xrefs

- `msvcrt!??_V@YAXPEAX@Z` at `0x180035a69`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180035b3e`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180035a69`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180035b3e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180035b0b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180035b0b`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180035aa3`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180035aa3`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180035b01`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180035b01`

## pseudocode

```c
__int64 __fastcall Wallet::SaveStreamToFile(Wallet *this, const WCHAR *a2, const unsigned __int16 *a3)
{
  void *v3; // rbx
  HANDLE FileW; // rax
  HANDLE v7; // rdi
  signed int v8; // esi
  signed int LastError; // eax
  void *v11; // [rsp+40h] [rbp-10h] BYREF
  LPCVOID lpBuffer; // [rsp+48h] [rbp-8h] BYREF
  DWORD nNumberOfBytesToWrite; // [rsp+80h] [rbp+30h] BYREF
  DWORD NumberOfBytesWritten; // [rsp+90h] [rbp+40h] BYREF
  HANDLE hFile; // [rsp+98h] [rbp+48h] BYREF

  v3 = 0;
  hFile = 0;
  lpBuffer = 0;
  nNumberOfBytesToWrite = 0;
  NumberOfBytesWritten = 0;
  if ( this && a2 )
  {
    v11 = operator new[](0x104u);
    std::unique_ptr<unsigned char [0]>::operator=(&lpBuffer, &v11);
    operator delete[](v11);
    v3 = (void *)lpBuffer;
    if ( lpBuffer )
    {
      FileW = CreateFileW(a2, 0x40000000u, 0, 0, 2u, 0x80u, 0);
      tlx::unique_any<tlx::file_handle_traits>::reset(&hFile, FileW);
      v7 = hFile;
      if ( (unsigned __int64)hFile + 1 <= 1 )
      {
LABEL_8:
        LastError = GetLastError();
        v8 = LastError;
        if ( LastError )
        {
          if ( LastError > 0 )
            v8 = (unsigned __int16)LastError | 0x80070000;
        }
        else
        {
          v8 = -2143748092;
        }
      }
      else
      {
        while ( 1 )
        {
          v8 = (*(__int64 (__fastcall **)(Wallet *, void *, __int64, DWORD *))(*(_QWORD *)this + 24LL))(
                 this,
                 v3,
                 260,
                 &nNumberOfBytesToWrite);
          if ( v8 < 0 )
            break;
          if ( !nNumberOfBytesToWrite )
          {
            v8 = 0;
            break;
          }
          if ( !WriteFile(v7, v3, nNumberOfBytesToWrite, &NumberOfBytesWritten, 0) )
            goto LABEL_8;
        }
      }
    }
    else
    {
      v8 = -2147024882;
    }
  }
  else
  {
    v8 = -2147467261;
  }
  operator delete[](v3);
  tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(&hFile);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180035a10  push    rbp
0x180035a12  push    rbx
0x180035a13  push    rsi
0x180035a14  push    rdi
0x180035a15  push    r14
0x180035a17  mov     rbp, rsp
0x180035a1a  sub     rsp, 50h
0x180035a1e  xor     ebx, ebx
0x180035a20  mov     [rbp+hFile], 0
0x180035a28  mov     [rbp+lpBuffer], rbx
0x180035a2c  mov     rdi, rdx
0x180035a2f  mov     [rbp+nNumberOfBytesToWrite], ebx
0x180035a32  mov     r14, rcx
0x180035a35  mov     [rbp+NumberOfBytesWritten], ebx
0x180035a38  test    rcx, rcx
0x180035a3b  jz      loc_180035B36
0x180035a41  test    rdx, rdx
0x180035a44  jz      loc_180035B36
0x180035a4a  mov     ecx, 104h; unsigned __int64
0x180035a4f  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180035a54  lea     rdx, [rbp+var_10]
0x180035a58  mov     [rbp+var_10], rax
0x180035a5c  lea     rcx, [rbp+lpBuffer]
0x180035a60  call    ??4?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@std@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::unique_ptr<uchar [0]>::operator=(std::unique_ptr<uchar [0]> &&)
0x180035a65  mov     rcx, [rbp+var_10]
0x180035a69  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180035a6f  mov     rbx, [rbp+lpBuffer]
0x180035a73  test    rbx, rbx
0x180035a76  jz      loc_180035B2F
0x180035a7c  mov     [rsp+50h+hTemplateFile], 0; hTemplateFile
0x180035a85  xor     r9d, r9d; lpSecurityAttributes
0x180035a88  mov     [rsp+50h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x180035a90  xor     r8d, r8d; dwShareMode
0x180035a93  mov     edx, 40000000h; dwDesiredAccess
0x180035a98  mov     [rsp+50h+dwCreationDisposition], 2; dwCreationDisposition
0x180035aa0  mov     rcx, rdi; lpFileName
0x180035aa3  call    cs:__imp_CreateFileW
0x180035aa9  mov     rdx, rax
0x180035aac  lea     rcx, [rbp+hFile]
0x180035ab0  call    ?reset@?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAAXPEAX@Z; tlx::unique_any<tlx::file_handle_traits>::reset(void *)
0x180035ab5  mov     rdi, [rbp+hFile]
0x180035ab9  lea     rax, [rdi+1]
0x180035abd  cmp     rax, 1
0x180035ac1  jbe     short loc_180035B0B
0x180035ac3  mov     rax, [r14]
0x180035ac6  lea     r9, [rbp+nNumberOfBytesToWrite]
0x180035aca  mov     r8d, 104h
0x180035ad0  mov     rdx, rbx
0x180035ad3  mov     rcx, r14
0x180035ad6  mov     rax, [rax+18h]
0x180035ada  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035adf  mov     esi, eax
0x180035ae1  test    eax, eax
0x180035ae3  js      short loc_180035B3B
0x180035ae5  mov     r8d, [rbp+nNumberOfBytesToWrite]; nNumberOfBytesToWrite
0x180035ae9  test    r8d, r8d
0x180035aec  jz      short loc_180035B24
0x180035aee  lea     r9, [rbp+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x180035af2  mov     qword ptr [rsp+50h+dwCreationDisposition], 0; lpOverlapped
0x180035afb  mov     rdx, rbx; lpBuffer
0x180035afe  mov     rcx, rdi; hFile
0x180035b01  call    cs:__imp_WriteFile
0x180035b07  test    eax, eax
0x180035b09  jnz     short loc_180035AC3
0x180035b0b  call    cs:__imp_GetLastError
0x180035b11  mov     esi, eax
0x180035b13  test    eax, eax
0x180035b15  jz      short loc_180035B28
0x180035b17  jle     short loc_180035B3B
0x180035b19  movzx   esi, ax
0x180035b1c  or      esi, 80070000h
0x180035b22  jmp     short loc_180035B3B
0x180035b24  xor     esi, esi
0x180035b26  jmp     short loc_180035B3B
0x180035b28  mov     esi, 80390004h
0x180035b2d  jmp     short loc_180035B3B
0x180035b2f  mov     esi, 8007000Eh
0x180035b34  jmp     short loc_180035B3B
0x180035b36  mov     esi, 80004003h
0x180035b3b  mov     rcx, rbx
0x180035b3e  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180035b44  lea     rcx, [rbp+hFile]
0x180035b48  call    ??1?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(void)
0x180035b4d  mov     eax, esi
0x180035b4f  add     rsp, 50h
0x180035b53  pop     r14
0x180035b55  pop     rdi
0x180035b56  pop     rsi
0x180035b57  pop     rbx
0x180035b58  pop     rbp
0x180035b59  retn
```
