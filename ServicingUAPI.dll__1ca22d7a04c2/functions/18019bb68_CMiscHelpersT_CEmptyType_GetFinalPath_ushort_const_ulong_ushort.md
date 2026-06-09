# CMiscHelpersT<CEmptyType>::GetFinalPath(ushort const *,ulong,ushort * *)

- ea: `0x18019bb68`
- end: `0x18019bd59`
- name: `?GetFinalPath@?$CMiscHelpersT@VCEmptyType@@@@SAJPEBGKPEAPEAG@Z`
- size: `497`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName)`
- caller_count: `2`
- callee_count: `7`
- tags: `file_ops, reparse_path, registry_config`

## callers

- `0x180199068`
- `0x18019da38`

## callees

- `0x1800031d0`
- `0x180003c64`
- `0x180068c4c`
- `0x18006fab0`
- `0x1801961c4`
- `0x180198e84`
- `0x18019bb68`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18019bc08`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18019bc57`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18019bc08`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18019bc57`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18019bd1b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18019bd1b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18019bd06`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18019bd06`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18019bcf5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18019bcf5`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18019bbee`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18019bbee`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x18019bc47`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x18019bc47`

## pseudocode

```c
__int64 __fastcall CMiscHelpersT<CEmptyType>::GetFinalPath(LPCWSTR lpFileName, __int64 a2, _QWORD *a3)
{
  __int64 v3; // rsi
  __int64 v4; // rbx
  __int64 v7; // rcx
  unsigned int v8; // edi
  HANDLE FileW; // rbp
  signed int LastError; // eax
  signed int v11; // eax
  int StringCch; // eax
  int Internal; // eax
  __int64 v14; // rax
  HANDLE ProcessHeap; // rax
  int v17; // [rsp+40h] [rbp-858h] BYREF
  __int64 v18; // [rsp+48h] [rbp-850h]
  WCHAR szFilePath[1040]; // [rsp+50h] [rbp-848h] BYREF

  v3 = 0;
  v4 = -1;
  v18 = 0;
  if ( !lpFileName || !a3 )
  {
    v7 = 2147942487LL;
    v8 = -2147024809;
LABEL_3:
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v7);
    goto LABEL_25;
  }
  memset_0(szFilePath, 0, sizeof(szFilePath));
  FileW = CreateFileW(lpFileName, 0, 7u, 0, 3u, 0x2000000u, 0);
  if ( (((unsigned __int64)FileW + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
  {
    LastError = GetLastError();
    v8 = LastError;
    if ( LastError )
    {
      if ( LastError > 0 )
        v8 = (unsigned __int16)LastError | 0x80070000;
    }
    else
    {
      v8 = -2147467259;
    }
    v7 = v8;
    goto LABEL_3;
  }
  if ( GetFinalPathNameByHandleW(FileW, szFilePath, 0x410u, 1u) )
  {
    v17 = 0;
    StringCch = CGlobalHelpersT<CEmptyType>::GetStringCchLength<unsigned long>(szFilePath, &v17);
    v8 = StringCch;
    if ( StringCch >= 0 )
    {
      Internal = CImmutableStringsT<unsigned short,CImmutableStringsPolicyDefault>::CreateInternal(szFilePath);
      v8 = Internal;
      if ( Internal < 0 )
        CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)Internal);
      v3 = v18;
    }
    else
    {
      CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)StringCch);
    }
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v8);
    if ( (v8 & 0x80000000) == 0 )
    {
      v14 = v3;
      v3 = 0;
      *a3 = v14;
      goto LABEL_24;
    }
  }
  else
  {
    v11 = GetLastError();
    v8 = v11;
    if ( v11 )
    {
      if ( v11 > 0 )
        v8 = (unsigned __int16)v11 | 0x80070000;
    }
    else
    {
      v8 = -2147467259;
    }
  }
  CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v8);
LABEL_24:
  v4 = (__int64)FileW;
LABEL_25:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v8);
  if ( (unsigned __int64)(v4 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle((HANDLE)v4);
  if ( v3 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, (LPVOID)(v3 - 4));
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  }
  return v8;
}

```

## disassembly

```asm
0x18019bb68  mov     [rsp+arg_8], rbx
0x18019bb6d  mov     [rsp+arg_18], rbp
0x18019bb72  push    rsi
0x18019bb73  push    rdi
0x18019bb74  push    r14
0x18019bb76  sub     rsp, 880h
0x18019bb7d  mov     rax, cs:__security_cookie
0x18019bb84  xor     rax, rsp
0x18019bb87  mov     [rsp+898h+var_28], rax
0x18019bb8f  xor     esi, esi
0x18019bb91  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18019bb95  mov     [rsp+898h+var_850], rsi
0x18019bb9a  mov     r14, r8
0x18019bb9d  mov     rdi, rcx
0x18019bba0  test    rcx, rcx
0x18019bba3  jnz     short loc_18019BBB6
0x18019bba5  mov     ecx, 80070057h
0x18019bbaa  mov     edi, ecx
0x18019bbac  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18019bbb1  jmp     loc_18019BCE1
0x18019bbb6  test    r14, r14
0x18019bbb9  jz      short loc_18019BBA5
0x18019bbbb  xor     edx, edx; Val
0x18019bbbd  lea     rcx, [rsp+898h+szFilePath]; void *
0x18019bbc2  mov     r8d, 820h; Size
0x18019bbc8  call    memset_0
0x18019bbcd  xor     r9d, r9d; lpSecurityAttributes
0x18019bbd0  mov     [rsp+898h+hTemplateFile], rsi; hTemplateFile
0x18019bbd5  mov     [rsp+898h+dwFlagsAndAttributes], 2000000h; dwFlagsAndAttributes
0x18019bbdd  xor     edx, edx; dwDesiredAccess
0x18019bbdf  mov     rcx, rdi; lpFileName
0x18019bbe2  mov     [rsp+898h+dwCreationDisposition], 3; dwCreationDisposition
0x18019bbea  lea     r8d, [r9+7]; dwShareMode
0x18019bbee  call    cs:__imp_CreateFileW
0x18019bbf5  nop     dword ptr [rax+rax+00h]
0x18019bbfa  mov     rbp, rax
0x18019bbfd  inc     rax
0x18019bc00  test    rax, 0FFFFFFFFFFFFFFFEh
0x18019bc06  jnz     short loc_18019BC33
0x18019bc08  call    cs:__imp_GetLastError
0x18019bc0f  nop     dword ptr [rax+rax+00h]
0x18019bc14  mov     edi, eax
0x18019bc16  test    eax, eax
0x18019bc18  jnz     short loc_18019BC21
0x18019bc1a  mov     edi, 80004005h
0x18019bc1f  jmp     short loc_18019BC2C
0x18019bc21  jle     short loc_18019BC2C
0x18019bc23  movzx   edi, ax
0x18019bc26  or      edi, 80070000h
0x18019bc2c  mov     ecx, edi
0x18019bc2e  jmp     loc_18019BBAC
0x18019bc33  mov     rcx, rbp; hFile
0x18019bc36  lea     rdx, [rsp+898h+szFilePath]; lpszFilePath
0x18019bc3b  mov     r9d, 1; dwFlags
0x18019bc41  mov     r8d, 410h; cchFilePath
0x18019bc47  call    cs:__imp_GetFinalPathNameByHandleW
0x18019bc4e  nop     dword ptr [rax+rax+00h]
0x18019bc53  test    eax, eax
0x18019bc55  jnz     short loc_18019BC84
0x18019bc57  call    cs:__imp_GetLastError
0x18019bc5e  nop     dword ptr [rax+rax+00h]
0x18019bc63  mov     edi, eax
0x18019bc65  test    eax, eax
0x18019bc67  jnz     short loc_18019BC70
0x18019bc69  mov     edi, 80004005h
0x18019bc6e  jmp     short loc_18019BC7B
0x18019bc70  jle     short loc_18019BC7B
0x18019bc72  movzx   edi, ax
0x18019bc75  or      edi, 80070000h
0x18019bc7b  mov     ecx, edi
0x18019bc7d  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18019bc82  jmp     short loc_18019BCDE
0x18019bc84  lea     rdx, [rsp+898h+var_858]
0x18019bc89  mov     [rsp+898h+var_858], esi
0x18019bc8d  lea     rcx, [rsp+898h+szFilePath]
0x18019bc92  call    ??$GetStringCchLength@K@?$CGlobalHelpersT@VCEmptyType@@@@SAJPEBGPEAKK@Z; CGlobalHelpersT<CEmptyType>::GetStringCchLength<ulong>(ushort const *,ulong *,ulong)
0x18019bc97  mov     edi, eax
0x18019bc99  test    eax, eax
0x18019bc9b  jns     short loc_18019BCA6
0x18019bc9d  mov     ecx, eax
0x18019bc9f  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18019bca4  jmp     short loc_18019BCCB
0x18019bca6  mov     edx, [rsp+898h+var_858]
0x18019bcaa  lea     r8, [rsp+898h+var_850]
0x18019bcaf  lea     rcx, [rsp+898h+szFilePath]; Src
0x18019bcb4  call    ?CreateInternal@?$CImmutableStringsT@GVCImmutableStringsPolicyDefault@@@@KAJPEBGKPEAPEAG@Z; CImmutableStringsT<ushort,CImmutableStringsPolicyDefault>::CreateInternal(ushort const *,ulong,ushort * *)
0x18019bcb9  mov     edi, eax
0x18019bcbb  test    eax, eax
0x18019bcbd  jns     short loc_18019BCC6
0x18019bcbf  mov     ecx, eax
0x18019bcc1  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18019bcc6  mov     rsi, [rsp+898h+var_850]
0x18019bccb  mov     ecx, edi
0x18019bccd  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18019bcd2  test    edi, edi
0x18019bcd4  js      short loc_18019BC7B
0x18019bcd6  mov     rax, rsi
0x18019bcd9  xor     esi, esi
0x18019bcdb  mov     [r14], rax
0x18019bcde  mov     rbx, rbp
0x18019bce1  mov     ecx, edi
0x18019bce3  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18019bce8  lea     rax, [rbx-1]
0x18019bcec  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18019bcf0  ja      short loc_18019BD01
0x18019bcf2  mov     rcx, rbx; hObject
0x18019bcf5  call    cs:__imp_CloseHandle
0x18019bcfc  nop     dword ptr [rax+rax+00h]
0x18019bd01  test    rsi, rsi
0x18019bd04  jz      short loc_18019BD2E
0x18019bd06  call    cs:__imp_GetProcessHeap
0x18019bd0d  nop     dword ptr [rax+rax+00h]
0x18019bd12  lea     r8, [rsi-4]; lpMem
0x18019bd16  xor     edx, edx; dwFlags
0x18019bd18  mov     rcx, rax; hHeap
0x18019bd1b  call    cs:__imp_HeapFree
0x18019bd22  nop     dword ptr [rax+rax+00h]
0x18019bd27  xor     ecx, ecx
0x18019bd29  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18019bd2e  mov     eax, edi
0x18019bd30  mov     rcx, [rsp+898h+var_28]
0x18019bd38  xor     rcx, rsp; StackCookie
0x18019bd3b  call    __security_check_cookie
0x18019bd40  lea     r11, [rsp+898h+var_18]
0x18019bd48  mov     rbx, [r11+28h]
0x18019bd4c  mov     rbp, [r11+38h]
0x18019bd50  mov     rsp, r11
0x18019bd53  pop     r14
0x18019bd55  pop     rdi
0x18019bd56  pop     rsi
0x18019bd57  retn
```
