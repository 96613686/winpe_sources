# MakeLFNPath

- ea: `0x180017bcc`
- end: `0x180017d8f`
- name: `MakeLFNPath`
- size: `451`
- prototype: `int __fastcall(PCWSTR pszStart, wchar_t *pszPathIn)`
- caller_count: `1`
- callee_count: `8`
- tags: `reparse_path, broker_com_uri`

## callers

- `0x1800063c4`

## callees

- `0x180017840`
- `0x180017b9c`
- `0x180017bcc`
- `0x1800198d0`
- `0x18001a688`
- `0x18001b294`
- `0x18001b94e`
- `0x18001b980`

## import_xrefs

- `USER32!CharNextW` at `0x180017c91`
- `USER32!CharNextW` at `0x180017c91`
- `USER32!CharUpperW` at `0x180017c6c`
- `USER32!CharUpperW` at `0x180017c6c`
- `KERNEL32!FindFirstFileW` at `0x180017cb9`
- `KERNEL32!FindFirstFileW` at `0x180017cb9`
- `KERNEL32!FindClose` at `0x180017d1a`
- `KERNEL32!FindClose` at `0x180017d1a`
- `SHLWAPI!StrRChrW` at `0x180017d28`
- `SHLWAPI!StrRChrW` at `0x180017d28`
- `SHLWAPI!PathBuildRootW` at `0x180017c7b`
- `SHLWAPI!PathBuildRootW` at `0x180017c7b`

## pseudocode

```c
int __fastcall MakeLFNPath(PCWSTR pszStart, wchar_t *pszPathIn)
{
  LPWSTR PCEnd; // rax
  unsigned __int16 v5; // ax
  const WCHAR *v6; // rcx
  LPWSTR v7; // rdi
  WCHAR v8; // r15
  HANDLE FirstFileW; // r12
  WCHAR *cFileName; // rbx
  PWSTR v11; // rax
  const unsigned __int16 *v12; // rbx
  ULONG v14; // [rsp+20h] [rbp-298h]
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+30h] [rbp-288h] BYREF

  LODWORD(PCEnd) = (unsigned int)memset_0(&FindFileData, 0, sizeof(FindFileData));
  *pszPathIn = 0;
  if ( *pszStart )
  {
    if ( *(_DWORD *)pszStart == 6029404 )
    {
      LODWORD(PCEnd) = StringCchCopyW(pszPathIn, 0x208u, pszStart);
    }
    else
    {
      v5 = (unsigned __int16)CharUpperW((LPWSTR)*pszStart);
      PathBuildRootW(pszPathIn, v5 - 65);
      PCEnd = (LPWSTR)GetPCEnd(pszStart);
      if ( *PCEnd )
      {
        v6 = PCEnd;
LABEL_7:
        PCEnd = CharNextW(v6);
        v7 = PCEnd;
        while ( *v7 )
        {
          v7 = (LPWSTR)GetPCEnd(v7);
          v8 = *v7;
          *v7 = 0;
          FirstFileW = FindFirstFileW(pszStart, &FindFileData);
          if ( FirstFileW == (HANDLE)-1LL )
          {
            v11 = StrRChrW(pszStart, 0, 0x5Cu);
            v12 = v11 + 1;
            if ( v11 != (PWSTR)-2LL && !(unsigned int)PathIsUnc2(v11 + 1) && !IsExtendedLengthDosDevicePath(v12) )
            {
              while ( *v12 == 92 )
                ++v12;
            }
            LODWORD(PCEnd) = PathCchCombineEx(pszPathIn, 0x208u, pszPathIn, v12, v14);
          }
          else
          {
            cFileName = FindFileData.cFileName;
            if ( !(unsigned int)PathIsUnc2(FindFileData.cFileName)
              && !IsExtendedLengthDosDevicePath(FindFileData.cFileName)
              && FindFileData.cFileName[0] == 92 )
            {
              do
                ++cFileName;
              while ( *cFileName == 92 );
            }
            PathCchCombineEx(pszPathIn, 0x208u, pszPathIn, cFileName, v14);
            LODWORD(PCEnd) = FindClose(FirstFileW);
          }
          *v7 = v8;
          if ( v8 )
          {
            v6 = v7;
            goto LABEL_7;
          }
        }
      }
    }
  }
  return (int)PCEnd;
}

```

## disassembly

```asm
0x180017bcc  mov     [rsp+arg_10], rbx
0x180017bd1  mov     [rsp+arg_18], rsi
0x180017bd6  push    rdi
0x180017bd7  push    r12
0x180017bd9  push    r13
0x180017bdb  push    r14
0x180017bdd  push    r15
0x180017bdf  sub     rsp, 290h
0x180017be6  mov     rax, cs:__security_cookie
0x180017bed  xor     rax, rsp
0x180017bf0  mov     [rsp+2B8h+var_38], rax
0x180017bf8  mov     r14, rdx
0x180017bfb  mov     rsi, rcx
0x180017bfe  xor     edx, edx; Val
0x180017c00  lea     rcx, [rsp+2B8h+FindFileData]; void *
0x180017c05  mov     r8d, 250h; Size
0x180017c0b  call    memset_0
0x180017c10  xor     ebx, ebx
0x180017c12  mov     [r14], bx
0x180017c16  cmp     [rsi], bx
0x180017c19  jz      short loc_180017C3C
0x180017c1b  lea     r13d, [rbx+5Ch]
0x180017c1f  cmp     [rsi], r13w
0x180017c23  jnz     short loc_180017C69
0x180017c25  cmp     [rsi+2], r13w
0x180017c2a  jnz     short loc_180017C69
0x180017c2c  mov     r8, rsi; pszSrc
0x180017c2f  mov     edx, 208h; cchDest
0x180017c34  mov     rcx, r14; pszDest
0x180017c37  call    StringCchCopyW
0x180017c3c  mov     rcx, [rsp+2B8h+var_38]
0x180017c44  xor     rcx, rsp; StackCookie
0x180017c47  call    __security_check_cookie
0x180017c4c  lea     r11, [rsp+2B8h+var_28]
0x180017c54  mov     rbx, [r11+40h]
0x180017c58  mov     rsi, [r11+48h]
0x180017c5c  mov     rsp, r11
0x180017c5f  pop     r15
0x180017c61  pop     r14
0x180017c63  pop     r13
0x180017c65  pop     r12
0x180017c67  pop     rdi
0x180017c68  retn
0x180017c69  movzx   ecx, word ptr [rsi]; lpsz
0x180017c6c  call    cs:__imp_CharUpperW
0x180017c72  movzx   edx, ax
0x180017c75  mov     rcx, r14; pszRoot
0x180017c78  sub     edx, 41h ; 'A'; iDrive
0x180017c7b  call    cs:__imp_PathBuildRootW
0x180017c81  mov     rcx, rsi
0x180017c84  call    GetPCEnd
0x180017c89  cmp     [rax], bx
0x180017c8c  jz      short loc_180017C3C
0x180017c8e  mov     rcx, rax; lpsz
0x180017c91  call    cs:__imp_CharNextW
0x180017c97  mov     rdi, rax
0x180017c9a  cmp     [rdi], bx
0x180017c9d  jz      short loc_180017C3C
0x180017c9f  mov     rcx, rdi
0x180017ca2  call    GetPCEnd
0x180017ca7  lea     rdx, [rsp+2B8h+FindFileData]; lpFindFileData
0x180017cac  mov     rcx, rsi; lpFileName
0x180017caf  mov     rdi, rax
0x180017cb2  movzx   r15d, word ptr [rax]
0x180017cb6  mov     [rax], bx
0x180017cb9  call    cs:__imp_FindFirstFileW
0x180017cbf  xor     edx, edx; pszEnd
0x180017cc1  mov     r12, rax
0x180017cc4  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180017cc8  jz      short loc_180017D22
0x180017cca  lea     r8, IsBackslash
0x180017cd1  lea     rcx, [rsp+2B8h+FindFileData.cFileName]; unsigned __int16 *
0x180017cd6  lea     rbx, [rsp+2B8h+FindFileData.cFileName]
0x180017cdb  call    PathIsUnc2
0x180017ce0  test    eax, eax
0x180017ce2  jnz     short loc_180017D04
0x180017ce4  lea     rcx, [rsp+2B8h+FindFileData.cFileName]; unsigned __int16 *
0x180017ce9  call    ?IsExtendedLengthDosDevicePath@@YA_NPEBG@Z; IsExtendedLengthDosDevicePath(ushort const *)
0x180017cee  test    al, al
0x180017cf0  jnz     short loc_180017D04
0x180017cf2  cmp     [rsp+2B8h+FindFileData.cFileName], r13w
0x180017cf8  jnz     short loc_180017D04
0x180017cfa  add     rbx, 2
0x180017cfe  cmp     [rbx], r13w
0x180017d02  jz      short loc_180017CFA
0x180017d04  mov     r9, rbx; pszMore
0x180017d07  mov     r8, r14; pszPathIn
0x180017d0a  mov     edx, 208h; cchPathOut
0x180017d0f  mov     rcx, r14; pszPathOut
0x180017d12  call    PathCchCombineEx
0x180017d17  mov     rcx, r12; hFindFile
0x180017d1a  call    cs:__imp_FindClose
0x180017d20  jmp     short loc_180017D77
0x180017d22  mov     r8d, r13d; wMatch
0x180017d25  mov     rcx, rsi; pszStart
0x180017d28  call    cs:__imp_StrRChrW
0x180017d2e  mov     rbx, rax
0x180017d31  add     rbx, 2
0x180017d35  jz      short loc_180017D64
0x180017d37  lea     r8, IsBackslash
0x180017d3e  xor     edx, edx
0x180017d40  mov     rcx, rbx; unsigned __int16 *
0x180017d43  call    PathIsUnc2
0x180017d48  test    eax, eax
0x180017d4a  jnz     short loc_180017D64
0x180017d4c  mov     rcx, rbx; unsigned __int16 *
0x180017d4f  call    ?IsExtendedLengthDosDevicePath@@YA_NPEBG@Z; IsExtendedLengthDosDevicePath(ushort const *)
0x180017d54  test    al, al
0x180017d56  jnz     short loc_180017D64
0x180017d58  jmp     short loc_180017D5E
0x180017d5a  add     rbx, 2
0x180017d5e  cmp     [rbx], r13w
0x180017d62  jz      short loc_180017D5A
0x180017d64  mov     r9, rbx; pszMore
0x180017d67  mov     r8, r14; pszPathIn
0x180017d6a  mov     edx, 208h; cchPathOut
0x180017d6f  mov     rcx, r14; pszPathOut
0x180017d72  call    PathCchCombineEx
0x180017d77  xor     ebx, ebx
0x180017d79  mov     [rdi], r15w
0x180017d7d  test    r15w, r15w
0x180017d81  jz      loc_180017C9A
0x180017d87  mov     rcx, rdi
0x180017d8a  jmp     loc_180017C91
```
