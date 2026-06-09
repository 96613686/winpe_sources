# GetLocalAppDataPath(ushort *,ushort const *,ushort const *,bool)

- ea: `0x180115b68`
- end: `0x180115c67`
- name: `?GetLocalAppDataPath@@YAKPEAGPEBG1_N@Z`
- size: `255`
- prototype: `__int64 __fastcall(unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x180115608`
- `0x180115aec`

## callees

- `0x1800024f0`
- `0x180008290`
- `0x180114ae0`
- `0x180115b68`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180115bd2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180115be3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180115bd2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180115be3`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180115bc8`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180115bc8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180115bef`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180115c4d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180115bef`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180115c4d`
- `profapi!__imp_GetBasicProfileFolderPath` at `0x180115b8f`
- `profapi!__imp_GetBasicProfileFolderPath` at `0x180115b8f`

## pseudocode

```c
__int64 __fastcall GetLocalAppDataPath(unsigned __int16 *a1, const unsigned __int16 *a2, const unsigned __int16 *a3)
{
  int BasicProfileFolderPath; // esi
  unsigned int i; // ebx
  const unsigned __int16 *v8; // rdx
  DWORD LastError; // ebx

  *a1 = 0;
  BasicProfileFolderPath = GetBasicProfileFolderPath(6, 0, a1, 260);
  if ( BasicProfileFolderPath >= 0 && *a1 )
  {
    for ( i = 0; i < 2; ++i )
    {
      v8 = a2;
      if ( i )
        v8 = a3;
      if ( !v8 )
        break;
      if ( !AppendFilePath(a1, v8) && !CreateDirectoryW(a1, 0) && GetLastError() != 183 )
      {
        LastError = GetLastError();
        goto LABEL_20;
      }
    }
    LocalFree(0);
    operator delete(0);
    return 0;
  }
  else
  {
    if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x2000000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 105) )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 12),
        13,
        WPP_0273058363483181bbb6bbedc1b853d5_Traceguids,
        (unsigned int)BasicProfileFolderPath);
    }
    LastError = 87;
    if ( BasicProfileFolderPath != -2147024809 )
      LastError = 3;
LABEL_20:
    LocalFree(0);
    operator delete(0);
    return LastError;
  }
}

```

## disassembly

```asm
0x180115b68  push    rbx
0x180115b6a  push    rbp
0x180115b6b  push    rsi
0x180115b6c  push    rdi
0x180115b6d  push    r14
0x180115b6f  sub     rsp, 20h
0x180115b73  xor     eax, eax
0x180115b75  mov     rbp, r8
0x180115b78  mov     r14, rdx
0x180115b7b  mov     [rcx], ax
0x180115b7e  mov     rdi, rcx
0x180115b81  mov     r8, rcx
0x180115b84  mov     r9d, 104h
0x180115b8a  xor     edx, edx
0x180115b8c  lea     ecx, [rax+6]
0x180115b8f  call    cs:__imp_GetBasicProfileFolderPath
0x180115b95  mov     esi, eax
0x180115b97  test    eax, eax
0x180115b99  js      short loc_180115C00
0x180115b9b  xor     edx, edx
0x180115b9d  cmp     dx, [rdi]
0x180115ba0  jz      short loc_180115C00
0x180115ba2  xor     ebx, ebx
0x180115ba4  cmp     ebx, 2
0x180115ba7  jnb     short loc_180115BED
0x180115ba9  test    ebx, ebx
0x180115bab  mov     rdx, r14
0x180115bae  cmovnz  rdx, rbp; unsigned __int16 *
0x180115bb2  test    rdx, rdx
0x180115bb5  jz      short loc_180115BED
0x180115bb7  mov     rcx, rdi; unsigned __int16 *
0x180115bba  call    ?AppendFilePath@@YAKPEAGPEBG@Z; AppendFilePath(ushort *,ushort const *)
0x180115bbf  test    eax, eax
0x180115bc1  jnz     short loc_180115BDF
0x180115bc3  xor     edx, edx; lpSecurityAttributes
0x180115bc5  mov     rcx, rdi; lpPathName
0x180115bc8  call    cs:__imp_CreateDirectoryW
0x180115bce  test    eax, eax
0x180115bd0  jnz     short loc_180115BDF
0x180115bd2  call    cs:__imp_GetLastError
0x180115bd8  cmp     eax, 0B7h
0x180115bdd  jnz     short loc_180115BE3
0x180115bdf  inc     ebx
0x180115be1  jmp     short loc_180115BA4
0x180115be3  call    cs:__imp_GetLastError
0x180115be9  mov     ebx, eax
0x180115beb  jmp     short loc_180115C4B
0x180115bed  xor     ecx, ecx; hMem
0x180115bef  call    cs:__imp_LocalFree
0x180115bf5  xor     ecx, ecx; Block
0x180115bf7  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180115bfc  xor     eax, eax
0x180115bfe  jmp     short loc_180115C5C
0x180115c00  mov     rcx, cs:WPP_GLOBAL_Control
0x180115c07  lea     rax, WPP_GLOBAL_Control
0x180115c0e  cmp     rcx, rax
0x180115c11  jz      short loc_180115C3A
0x180115c13  test    dword ptr [rcx+6Ch], 2000000h
0x180115c1a  jz      short loc_180115C3A
0x180115c1c  cmp     byte ptr [rcx+69h], 1
0x180115c20  jb      short loc_180115C3A
0x180115c22  mov     rcx, [rcx+60h]
0x180115c26  lea     r8, WPP_0273058363483181bbb6bbedc1b853d5_Traceguids
0x180115c2d  mov     edx, 0Dh
0x180115c32  mov     r9d, esi
0x180115c35  call    WPP_SF_d
0x180115c3a  mov     ebx, 57h ; 'W'
0x180115c3f  cmp     esi, 80070057h
0x180115c45  lea     eax, [rbx-54h]
0x180115c48  cmovnz  ebx, eax
0x180115c4b  xor     ecx, ecx; hMem
0x180115c4d  call    cs:__imp_LocalFree
0x180115c53  xor     ecx, ecx; Block
0x180115c55  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180115c5a  mov     eax, ebx
0x180115c5c  add     rsp, 20h
0x180115c60  pop     r14
0x180115c62  pop     rdi
0x180115c63  pop     rsi
0x180115c64  pop     rbp
0x180115c65  pop     rbx
0x180115c66  retn
```
