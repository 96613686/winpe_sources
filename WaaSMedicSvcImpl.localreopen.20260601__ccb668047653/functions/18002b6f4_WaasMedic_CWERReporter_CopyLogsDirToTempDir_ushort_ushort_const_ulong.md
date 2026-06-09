# WaasMedic::CWERReporter::CopyLogsDirToTempDir(ushort *,ushort * * const,ulong)

- ea: `0x18002b6f4`
- end: `0x18002b81d`
- name: `?CopyLogsDirToTempDir@CWERReporter@WaasMedic@@AEAAJPEAGQEAPEAGK@Z`
- size: `297`
- prototype: `__int64 __fastcall(WaasMedic::CWERReporter *this, unsigned __int16 *, unsigned __int16 **const)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, installer_update`

## callers

- `0x18002b63c`

## callees

- `0x1800050a0`
- `0x18002b6f4`
- `0x18002e81c`
- `0x180035d6c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b730`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b7c6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b730`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b7c6`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18002b76c`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18002b76c`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18002b726`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18002b726`

## string_xrefs

- `0x18002b7bd`: `Failed to expand log file share path %s due to insufficient buffer! hr = 0x%08x`
- `0x18002b7db`: `Failed to expand log file share path %s! hr = 0x%08x`
- `0x18002b7aa`: `Failed to copy directory from %s to %s! hr = 0x%08x`
- `0x18002b74f`: `Failed to create directory %s! hr=0x%08x`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall WaasMedic::CWERReporter::CopyLogsDirToTempDir(
        WaasMedic::CWERReporter *this,
        unsigned __int16 *a2,
        unsigned __int16 **const a3)
{
  signed int v5; // eax
  unsigned int v6; // ebx
  __int64 v7; // rdi
  DWORD v8; // eax
  const unsigned __int16 *v9; // r8
  int v10; // eax
  const unsigned __int16 *v11; // rdx
  signed int LastError; // eax
  int v14; // [rsp+20h] [rbp-248h]
  WCHAR Dst[264]; // [rsp+30h] [rbp-238h] BYREF

  if ( CreateDirectoryW(a2, 0) || (v5 = GetLastError(), v6 = v5, v5 == 183) )
  {
    v7 = 0;
    while ( 1 )
    {
      v8 = ExpandEnvironmentStringsW(a3[v7], Dst, 0x104u);
      if ( !v8 )
        break;
      if ( v8 > 0x104 )
      {
        v6 = -2147024774;
        v11 = L"Failed to expand log file share path %s due to insufficient buffer! hr = 0x%08x";
        goto LABEL_17;
      }
      v10 = WaasMedic::CopyDirectory((WaasMedic *)Dst, a2, v9);
      v6 = v10;
      if ( v10 < 0 )
      {
        v14 = v10;
        LogLevelW(2u, L"Failed to copy directory from %s to %s! hr = 0x%08x", Dst, a2, v14);
        return v6;
      }
      v7 = (unsigned int)(v7 + 1);
      if ( (unsigned int)v7 >= 3 )
        return v6;
    }
    LastError = GetLastError();
    v6 = LastError;
    if ( LastError > 0 )
      v6 = (unsigned __int16)LastError | 0x80070000;
    v11 = L"Failed to expand log file share path %s! hr = 0x%08x";
LABEL_17:
    LogLevelW(2u, v11, a3[v7], v6);
  }
  else
  {
    if ( v5 > 0 )
      v6 = (unsigned __int16)v5 | 0x80070000;
    LogLevelW(2u, L"Failed to create directory %s! hr=0x%08x", a2, v6);
  }
  return v6;
}

```

## disassembly

```asm
0x18002b6f4  mov     [rsp+arg_0], rbx
0x18002b6f9  mov     [rsp+arg_18], rbp
0x18002b6fe  push    rsi
0x18002b6ff  push    rdi
0x18002b700  push    r14
0x18002b702  sub     rsp, 250h
0x18002b709  mov     rax, cs:__security_cookie
0x18002b710  xor     rax, rsp
0x18002b713  mov     [rsp+268h+var_28], rax
0x18002b71b  mov     rsi, rdx
0x18002b71e  mov     r14, r8
0x18002b721  mov     rcx, rsi; lpPathName
0x18002b724  xor     edx, edx; lpSecurityAttributes
0x18002b726  call    cs:__imp_CreateDirectoryW
0x18002b72c  test    eax, eax
0x18002b72e  jnz     short loc_18002B75B
0x18002b730  call    cs:__imp_GetLastError
0x18002b736  mov     ebx, eax
0x18002b738  cmp     eax, 0B7h
0x18002b73d  jz      short loc_18002B75B
0x18002b73f  test    eax, eax
0x18002b741  jle     short loc_18002B74C
0x18002b743  movzx   ebx, ax
0x18002b746  or      ebx, 80070000h
0x18002b74c  mov     r8, rsi
0x18002b74f  lea     rdx, aFailedToCreate_2; "Failed to create directory %s! hr=0x%08"...
0x18002b756  jmp     loc_18002B7E6
0x18002b75b  xor     edi, edi
0x18002b75d  mov     rcx, [r14+rdi*8]; lpSrc
0x18002b761  lea     rdx, [rsp+268h+Dst]; lpDst
0x18002b766  mov     r8d, 104h; nSize
0x18002b76c  call    cs:__imp_ExpandEnvironmentStringsW
0x18002b772  test    eax, eax
0x18002b774  jz      short loc_18002B7C6
0x18002b776  cmp     eax, 104h
0x18002b77b  ja      short loc_18002B7B8
0x18002b77d  mov     rdx, rsi; unsigned __int16 *
0x18002b780  lea     rcx, [rsp+268h+Dst]; this
0x18002b785  call    ?CopyDirectory@WaasMedic@@YAJPEBG0@Z; WaasMedic::CopyDirectory(ushort const *,ushort const *)
0x18002b78a  mov     ebx, eax
0x18002b78c  test    eax, eax
0x18002b78e  js      short loc_18002B799
0x18002b790  inc     edi
0x18002b792  cmp     edi, 3
0x18002b795  jb      short loc_18002B75D
0x18002b797  jmp     short loc_18002B7F3
0x18002b799  mov     r9, rsi
0x18002b79c  mov     [rsp+268h+var_248], eax
0x18002b7a0  lea     r8, [rsp+268h+Dst]
0x18002b7a5  mov     ecx, 2; unsigned __int8
0x18002b7aa  lea     rdx, aFailedToCopyDi; "Failed to copy directory from %s to %s!"...
0x18002b7b1  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x18002b7b6  jmp     short loc_18002B7F3
0x18002b7b8  mov     ebx, 8007007Ah
0x18002b7bd  lea     rdx, aFailedToExpand_2; "Failed to expand log file share path %s"...
0x18002b7c4  jmp     short loc_18002B7E2
0x18002b7c6  call    cs:__imp_GetLastError
0x18002b7cc  mov     ebx, eax
0x18002b7ce  test    eax, eax
0x18002b7d0  jle     short loc_18002B7DB
0x18002b7d2  movzx   ebx, ax
0x18002b7d5  or      ebx, 80070000h
0x18002b7db  lea     rdx, aFailedToExpand_1; "Failed to expand log file share path %s"...
0x18002b7e2  mov     r8, [r14+rdi*8]
0x18002b7e6  mov     r9d, ebx
0x18002b7e9  mov     ecx, 2; unsigned __int8
0x18002b7ee  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x18002b7f3  mov     eax, ebx
0x18002b7f5  mov     rcx, [rsp+268h+var_28]
0x18002b7fd  xor     rcx, rsp; StackCookie
0x18002b800  call    __security_check_cookie
0x18002b805  lea     r11, [rsp+268h+var_18]
0x18002b80d  mov     rbx, [r11+20h]
0x18002b811  mov     rbp, [r11+38h]
0x18002b815  mov     rsp, r11
0x18002b818  pop     r14
0x18002b81a  pop     rdi
0x18002b81b  pop     rsi
0x18002b81c  retn
```
