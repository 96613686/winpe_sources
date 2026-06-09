# CopySdbToNewLocation(_SavedSdbInfo *,ushort const *,ushort const *,ushort *,unsigned __int64)

- ea: `0x180038200`
- end: `0x1800382e3`
- name: `?CopySdbToNewLocation@@YAJPEAU_SavedSdbInfo@@PEBG1PEAG_K@Z`
- size: `227`
- prototype: `int(struct _SavedSdbInfo *, const unsigned __int16 *, const unsigned __int16 *, unsigned __int16 *, unsigned __int64)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops, reparse_path, broker_com_uri`

## callers

- `0x180037c64`
- `0x180038b90`

## callees

- `0x180001cf0`
- `0x180038200`
- `0x18004fec8`
- `0x1800543c0`

## import_xrefs

- `KERNEL32!CopyFileW` at `0x180038270`
- `KERNEL32!CopyFileW` at `0x180038270`
- `KERNEL32!GetLastError` at `0x18003827a`
- `KERNEL32!GetLastError` at `0x18003827a`
- `SHLWAPI!PathFindFileNameW` at `0x180038246`
- `SHLWAPI!PathFindFileNameW` at `0x180038246`

## string_xrefs

- `0x1800382a2`: `Failed to copy sdb file to new location: 0x%x`
- `0x1800382b3`: `CopySdbToNewLocation`

## pseudocode

```c
__int64 __fastcall CopySdbToNewLocation(
        PCWSTR *a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        unsigned __int16 *a4)
{
  int v7; // ebx
  const WCHAR *FileNameW; // rax
  size_t v9; // rdx
  signed int LastError; // eax
  ULONG v12; // [rsp+20h] [rbp-258h]
  ULONG v13; // [rsp+20h] [rbp-258h]
  WCHAR pszPathOut[264]; // [rsp+30h] [rbp-248h] BYREF

  v7 = PathCchCombineEx(pszPathOut, (size_t)a2, a2, a1[4], v12);
  if ( v7 >= 0 )
  {
    FileNameW = PathFindFileNameW(a1[4]);
    v7 = PathCchCombineEx(a4, v9, a3, FileNameW, v13);
    if ( v7 >= 0 )
    {
      if ( !CopyFileW(pszPathOut, a4, 1) )
      {
        LastError = GetLastError();
        v7 = LastError;
        if ( LastError > 0 )
          v7 = (unsigned __int16)LastError | 0x80070000;
        if ( v7 >= 0 )
        {
          v7 = -2147467259;
LABEL_9:
          AslLogCallPrintf(1, "CopySdbToNewLocation", 1114, "Failed to copy sdb file to new location: 0x%x", v7);
          return (unsigned int)v7;
        }
        if ( v7 != -2147024816 )
          goto LABEL_9;
      }
      return 0;
    }
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180038200  push    rbx
0x180038202  push    rbp
0x180038203  push    rsi
0x180038204  push    rdi
0x180038205  sub     rsp, 258h
0x18003820c  mov     rax, cs:__security_cookie
0x180038213  xor     rax, rsp
0x180038216  mov     [rsp+278h+var_38], rax
0x18003821e  mov     rdi, r9
0x180038221  mov     rbp, r8
0x180038224  mov     r9, [rcx+20h]; pszMore
0x180038228  mov     rsi, rcx
0x18003822b  lea     rcx, [rsp+278h+pszPathOut]; pszPathOut
0x180038230  mov     r8, rdx; pszPathIn
0x180038233  call    PathCchCombineEx
0x180038238  mov     ebx, eax
0x18003823a  test    eax, eax
0x18003823c  js      loc_1800382C5
0x180038242  mov     rcx, [rsi+20h]; pszPath
0x180038246  call    cs:__imp_PathFindFileNameW
0x18003824c  mov     r8, rbp; pszPathIn
0x18003824f  mov     rcx, rdi; pszPathOut
0x180038252  mov     r9, rax; pszMore
0x180038255  call    PathCchCombineEx
0x18003825a  mov     ebx, eax
0x18003825c  test    eax, eax
0x18003825e  js      short loc_1800382C5
0x180038260  mov     esi, 1
0x180038265  lea     rcx, [rsp+278h+pszPathOut]; lpExistingFileName
0x18003826a  mov     r8d, esi; bFailIfExists
0x18003826d  mov     rdx, rdi; lpNewFileName
0x180038270  call    cs:__imp_CopyFileW
0x180038276  test    eax, eax
0x180038278  jnz     short loc_1800382C3
0x18003827a  call    cs:__imp_GetLastError
0x180038280  mov     ebx, eax
0x180038282  test    eax, eax
0x180038284  jle     short loc_18003828F
0x180038286  movzx   ebx, ax
0x180038289  or      ebx, 80070000h
0x18003828f  test    ebx, ebx
0x180038291  js      short loc_18003829A
0x180038293  mov     ebx, 80004005h
0x180038298  jmp     short loc_1800382A2
0x18003829a  cmp     ebx, 80070050h
0x1800382a0  jz      short loc_1800382C3
0x1800382a2  lea     r9, aFailedToCopySd; "Failed to copy sdb file to new location"...
0x1800382a9  mov     [rsp+278h+var_258], ebx
0x1800382ad  mov     r8d, 45Ah
0x1800382b3  lea     rdx, aCopysdbtonewlo; "CopySdbToNewLocation"
0x1800382ba  mov     ecx, esi
0x1800382bc  call    AslLogCallPrintf
0x1800382c1  jmp     short loc_1800382C5
0x1800382c3  xor     ebx, ebx
0x1800382c5  mov     eax, ebx
0x1800382c7  mov     rcx, [rsp+278h+var_38]
0x1800382cf  xor     rcx, rsp; StackCookie
0x1800382d2  call    __security_check_cookie
0x1800382d7  add     rsp, 258h
0x1800382de  pop     rdi
0x1800382df  pop     rsi
0x1800382e0  pop     rbp
0x1800382e1  pop     rbx
0x1800382e2  retn
```
