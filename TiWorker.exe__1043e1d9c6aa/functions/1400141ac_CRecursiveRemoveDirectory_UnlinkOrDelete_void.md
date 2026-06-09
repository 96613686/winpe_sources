# CRecursiveRemoveDirectory::UnlinkOrDelete(void *)

- ea: `0x1400141ac`
- end: `0x14001428a`
- name: `?UnlinkOrDelete@CRecursiveRemoveDirectory@@AEAAJPEAX@Z`
- size: `222`
- prototype: `int __fastcall(CRecursiveRemoveDirectory *this, void *, unsigned __int16)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x140012c58`
- `0x140013a18`

## callees

- `0x140002310`
- `0x14000e034`
- `0x1400125a0`
- `0x1400141ac`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001421d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140014276`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001421d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140014276`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x140014213`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x140014252`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x140014213`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x140014252`

## pseudocode

```c
int __fastcall CRecursiveRemoveDirectory::UnlinkOrDelete(
        CRecursiveRemoveDirectory *this,
        void *a2,
        unsigned __int16 a3)
{
  unsigned __int16 v5; // dx
  unsigned __int16 v6; // cx
  unsigned __int16 v7; // r8
  int result; // eax
  char v9[4]; // [rsp+20h] [rbp-18h] BYREF
  int FileInformation; // [rsp+24h] [rbp-14h] BYREF

  if ( !*((_BYTE *)this + 16) )
  {
LABEL_9:
    v9[0] = 1;
    if ( SetFileInformationByHandle(a2, FileDispositionInfo, v9, 1u) )
      return 0;
    goto LABEL_12;
  }
  FileInformation = 1;
  if ( IsWindowsVersionOrGreaterEx((unsigned __int16)this, (unsigned __int16)a2, a3, 0x383Au) )
    FileInformation |= 2u;
  if ( IsWindowsVersionOrGreaterEx(v6, v5, v7, 0x4563u) )
    FileInformation |= 0x10u;
  if ( SetFileInformationByHandle(a2, FileRenameInfoEx|FileDispositionInfo, &FileInformation, 4u) )
    return 0;
  if ( GetLastError() == 87 )
  {
    LogAdapter::TraceAtLevel<>(
      1,
      "FileDispositionInfoEx is not supported, falling back to using FileDispositionInfo for deletion");
    *((_BYTE *)this + 16) = 0;
    goto LABEL_9;
  }
LABEL_12:
  result = GetLastError();
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x1400141ac  mov     [rsp+arg_10], rbx
0x1400141b1  push    rdi
0x1400141b2  sub     rsp, 30h
0x1400141b6  mov     rax, cs:__security_cookie
0x1400141bd  xor     rax, rsp
0x1400141c0  mov     [rsp+38h+var_10], rax
0x1400141c5  cmp     byte ptr [rcx+10h], 0
0x1400141c9  mov     rdi, rdx
0x1400141cc  mov     rbx, rcx
0x1400141cf  jz      short loc_14001423B
0x1400141d1  mov     r9d, 383Ah; unsigned __int16
0x1400141d7  mov     [rsp+38h+FileInformation], 1
0x1400141df  call    ?IsWindowsVersionOrGreaterEx@@YA_NGGGG@Z; IsWindowsVersionOrGreaterEx(ushort,ushort,ushort,ushort)
0x1400141e4  test    al, al
0x1400141e6  jz      short loc_1400141ED
0x1400141e8  or      [rsp+38h+FileInformation], 2
0x1400141ed  mov     r9d, 4563h; unsigned __int16
0x1400141f3  call    ?IsWindowsVersionOrGreaterEx@@YA_NGGGG@Z; IsWindowsVersionOrGreaterEx(ushort,ushort,ushort,ushort)
0x1400141f8  test    al, al
0x1400141fa  jz      short loc_140014201
0x1400141fc  or      [rsp+38h+FileInformation], 10h
0x140014201  mov     r9d, 4; dwBufferSize
0x140014207  lea     r8, [rsp+38h+FileInformation]; lpFileInformation
0x14001420c  mov     rcx, rdi; hFile
0x14001420f  lea     edx, [r9+11h]; FileInformationClass
0x140014213  call    cs:__imp_SetFileInformationByHandle
0x140014219  test    eax, eax
0x14001421b  jnz     short loc_14001425C
0x14001421d  call    cs:__imp_GetLastError
0x140014223  cmp     eax, 57h ; 'W'
0x140014226  jnz     short loc_140014276
0x140014228  lea     rdx, aFiledispositio; "FileDispositionInfoEx is not supported,"...
0x14001422f  lea     ecx, [rax-56h]
0x140014232  call    ??$TraceAtLevel@$$V@LogAdapter@@YAXW4LogLevel@0@QEBD@Z; LogAdapter::TraceAtLevel<>(LogAdapter::LogLevel,char const * const)
0x140014237  mov     byte ptr [rbx+10h], 0
0x14001423b  mov     r9d, 1; dwBufferSize
0x140014241  mov     [rsp+38h+var_18], 1
0x140014246  lea     r8, [rsp+38h+var_18]; lpFileInformation
0x14001424b  mov     rcx, rdi; hFile
0x14001424e  lea     edx, [r9+3]; FileInformationClass
0x140014252  call    cs:__imp_SetFileInformationByHandle
0x140014258  test    eax, eax
0x14001425a  jz      short loc_140014276
0x14001425c  xor     eax, eax
0x14001425e  mov     rcx, [rsp+38h+var_10]
0x140014263  xor     rcx, rsp; StackCookie
0x140014266  call    __security_check_cookie
0x14001426b  mov     rbx, [rsp+38h+arg_10]
0x140014270  add     rsp, 30h
0x140014274  pop     rdi
0x140014275  retn
0x140014276  call    cs:__imp_GetLastError
0x14001427c  test    eax, eax
0x14001427e  jle     short loc_14001425E
0x140014280  movzx   eax, ax
0x140014283  or      eax, 80070000h
0x140014288  jmp     short loc_14001425E
```
