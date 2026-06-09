# DeleteExpressFiles

- ea: `0x18004f14c`
- end: `0x18004f233`
- name: `DeleteExpressFiles`
- size: `231`
- prototype: `void __fastcall(wchar_t *lpFileName)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x18004fd88`

## callees

- `0x18000bab8`
- `0x18002c6c8`
- `0x18004f14c`
- `0x18004ff64`
- `0x1800d6e56`
- `0x1800d6ea0`

## import_xrefs

- `KERNEL32!FindClose` at `0x18004f211`
- `KERNEL32!FindClose` at `0x18004f211`
- `KERNEL32!FindFirstFileW` at `0x18004f1cf`
- `KERNEL32!FindFirstFileW` at `0x18004f1cf`
- `KERNEL32!FindNextFileW` at `0x18004f204`
- `KERNEL32!FindNextFileW` at `0x18004f204`
- `KERNEL32!DeleteFileW` at `0x18004f1f2`
- `KERNEL32!DeleteFileW` at `0x18004f1f2`

## pseudocode

```c
void __fastcall DeleteExpressFiles(wchar_t *lpFileName)
{
  wchar_t *v2; // rdi
  __int64 v3; // rdx
  unsigned __int64 v4; // rbp
  HANDLE FirstFileW; // rsi
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+20h] [rbp-288h] BYREF

  v2 = PathSuffix(lpFileName);
  v3 = v2 - lpFileName;
  if ( (unsigned int)v3 <= 0x104 )
  {
    v4 = (unsigned int)(260 - v3);
    StringCchCopyW(v2, v4, L"*.mq");
    memset_0(&FindFileData, 0, sizeof(FindFileData));
    FirstFileW = FindFirstFileW(lpFileName, &FindFileData);
    if ( FirstFileW != (HANDLE)-1LL )
    {
      do
        StringCchCopyW(v2 - 1, v4, FindFileData.cFileName);
      while ( DeleteFileW(lpFileName) && FindNextFileW(FirstFileW, &FindFileData) );
      FindClose(FirstFileW);
    }
  }
  else
  {
    LogMsgNTStatus(534, (wchar_t *)L"recovery", 0x462u);
  }
}

```

## disassembly

```asm
0x18004f14c  push    rbx
0x18004f14e  push    rbp
0x18004f14f  push    rsi
0x18004f150  push    rdi
0x18004f151  sub     rsp, 288h
0x18004f158  mov     rax, cs:__security_cookie
0x18004f15f  xor     rax, rsp
0x18004f162  mov     [rsp+2A8h+var_38], rax
0x18004f16a  mov     rbx, rcx
0x18004f16d  call    ?PathSuffix@@YAPEA_WPEA_W@Z; PathSuffix(wchar_t *)
0x18004f172  mov     rdx, rax
0x18004f175  mov     rdi, rax
0x18004f178  sub     rdx, rbx
0x18004f17b  mov     eax, 104h
0x18004f180  sar     rdx, 1
0x18004f183  cmp     edx, eax
0x18004f185  jbe     short loc_18004F1A0
0x18004f187  mov     r8d, 462h; unsigned __int16
0x18004f18d  lea     rdx, aRecovery; "recovery"
0x18004f194  mov     ecx, 216h; int
0x18004f199  call    ?LogMsgNTStatus@@YAXJPEA_WG@Z; LogMsgNTStatus(long,wchar_t *,ushort)
0x18004f19e  jmp     short loc_18004F217
0x18004f1a0  sub     eax, edx
0x18004f1a2  lea     r8, aMq; "*.mq"
0x18004f1a9  mov     edx, eax; unsigned __int64
0x18004f1ab  mov     rcx, rdi; wchar_t *
0x18004f1ae  mov     ebp, eax
0x18004f1b0  call    ?StringCchCopyW@@YAJPEA_W_KPEB_W@Z; StringCchCopyW(wchar_t *,unsigned __int64,wchar_t const *)
0x18004f1b5  xor     edx, edx; Val
0x18004f1b7  lea     rcx, [rsp+2A8h+FindFileData]; void *
0x18004f1bc  mov     r8d, 250h; Size
0x18004f1c2  call    memset_0
0x18004f1c7  lea     rdx, [rsp+2A8h+FindFileData]; lpFindFileData
0x18004f1cc  mov     rcx, rbx; lpFileName
0x18004f1cf  call    cs:__imp_FindFirstFileW
0x18004f1d5  mov     rsi, rax
0x18004f1d8  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18004f1dc  jz      short loc_18004F217
0x18004f1de  lea     r8, [rsp+2A8h+FindFileData.cFileName]; wchar_t *
0x18004f1e3  mov     rdx, rbp; unsigned __int64
0x18004f1e6  lea     rcx, [rdi-2]; wchar_t *
0x18004f1ea  call    ?StringCchCopyW@@YAJPEA_W_KPEB_W@Z; StringCchCopyW(wchar_t *,unsigned __int64,wchar_t const *)
0x18004f1ef  mov     rcx, rbx; lpFileName
0x18004f1f2  call    cs:__imp_DeleteFileW
0x18004f1f8  test    eax, eax
0x18004f1fa  jz      short loc_18004F20E
0x18004f1fc  lea     rdx, [rsp+2A8h+FindFileData]; lpFindFileData
0x18004f201  mov     rcx, rsi; hFindFile
0x18004f204  call    cs:__imp_FindNextFileW
0x18004f20a  test    eax, eax
0x18004f20c  jnz     short loc_18004F1DE
0x18004f20e  mov     rcx, rsi; hFindFile
0x18004f211  call    cs:__imp_FindClose
0x18004f217  mov     rcx, [rsp+2A8h+var_38]
0x18004f21f  xor     rcx, rsp; StackCookie
0x18004f222  call    __security_check_cookie
0x18004f227  add     rsp, 288h
0x18004f22e  pop     rdi
0x18004f22f  pop     rsi
0x18004f230  pop     rbp
0x18004f231  pop     rbx
0x18004f232  retn
```
