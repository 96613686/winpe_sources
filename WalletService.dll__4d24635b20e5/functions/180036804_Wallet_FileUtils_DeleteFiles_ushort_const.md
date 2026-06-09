# Wallet::FileUtils::DeleteFiles(ushort const *)

- ea: `0x180036804`
- end: `0x180036941`
- name: `?DeleteFiles@FileUtils@Wallet@@YAHPEBG@Z`
- size: `317`
- prototype: `__int64 __fastcall(Wallet::FileUtils *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x18000fab0`

## callees

- `0x18000acac`
- `0x1800367e4`
- `0x180036804`
- `0x180043052`
- `0x180043090`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800368f2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800368f2`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x1800368de`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x1800368de`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800368ce`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800368ce`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x18003687a`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x18003687a`

## pseudocode

```c
__int64 __fastcall Wallet::FileUtils::DeleteFiles(Wallet::FileUtils *this, const unsigned __int16 *a2)
{
  HANDLE FirstFileW; // r14
  unsigned int v4; // edi
  int v5; // esi
  signed int v6; // ebx
  int v7; // eax
  signed int LastError; // eax
  __int64 v10; // [rsp+30h] [rbp-D0h] BYREF
  _WIN32_FIND_DATAW FindFileData; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR FileName[264]; // [rsp+290h] [rbp+190h] BYREF
  WCHAR v13[264]; // [rsp+4A0h] [rbp+3A0h] BYREF

  memset_0(&FindFileData, 0, sizeof(FindFileData));
  v10 = -1;
  if ( (int)StringCchPrintfW(FileName, 0x104u, L"%s\\*", this) < 0 )
    goto LABEL_17;
  FirstFileW = FindFirstFileW(FileName, &FindFileData);
  v10 = (__int64)FirstFileW;
  v4 = 1;
  if ( FirstFileW == (HANDLE)-1LL )
  {
    LastError = GetLastError();
    v6 = LastError;
    if ( LastError )
    {
      if ( LastError > 0 )
        v6 = (unsigned __int16)LastError | 0x80070000;
    }
    else
    {
      v6 = -2143748092;
    }
    goto LABEL_16;
  }
  v5 = 1;
  v6 = 0;
  while ( (FindFileData.dwFileAttributes & 0x10) != 0 )
  {
LABEL_7:
    if ( !FindNextFileW(FirstFileW, &FindFileData) )
      goto LABEL_10;
  }
  v7 = StringCchPrintfW(v13, 0x104u, L"%s\\%s", this, FindFileData.cFileName);
  if ( v7 >= 0 )
  {
    v5 &= DeleteFileW(v13);
    goto LABEL_7;
  }
  v6 = v7;
LABEL_10:
  if ( !v5 )
  {
LABEL_17:
    v4 = 0;
    goto LABEL_18;
  }
LABEL_16:
  if ( v6 < 0 )
    goto LABEL_17;
LABEL_18:
  tlx::unique_any<tlx::find_handle_traits>::~unique_any<tlx::find_handle_traits>(&v10);
  return v4;
}

```

## disassembly

```asm
0x180036804  push    rbp
0x180036806  push    rbx
0x180036807  push    rsi
0x180036808  push    rdi
0x180036809  push    r14
0x18003680b  push    r15
0x18003680d  lea     rbp, [rsp-5C8h]
0x180036815  sub     rsp, 6C8h
0x18003681c  mov     rax, cs:__security_cookie
0x180036823  xor     rax, rsp
0x180036826  mov     [rbp+5F0h+var_40], rax
0x18003682d  mov     r15, rcx
0x180036830  xor     edx, edx; Val
0x180036832  mov     r8d, 250h; Size
0x180036838  lea     rcx, [rsp+6F0h+FindFileData]; void *
0x18003683d  call    memset_0
0x180036842  mov     [rsp+6F0h+var_6C0], 0FFFFFFFFFFFFFFFFh
0x18003684b  mov     r9, r15
0x18003684e  lea     r8, aS_1; "%s\\*"
0x180036855  mov     edx, 104h; unsigned __int64
0x18003685a  lea     rcx, [rbp+5F0h+FileName]; unsigned __int16 *
0x180036861  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180036866  test    eax, eax
0x180036868  js      loc_180036914
0x18003686e  lea     rdx, [rsp+6F0h+FindFileData]; lpFindFileData
0x180036873  lea     rcx, [rbp+5F0h+FileName]; lpFileName
0x18003687a  call    cs:__imp_FindFirstFileW
0x180036880  mov     r14, rax
0x180036883  mov     [rsp+6F0h+var_6C0], rax
0x180036888  mov     edi, 1
0x18003688d  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180036891  jz      short loc_1800368F2
0x180036893  mov     esi, edi
0x180036895  xor     ebx, ebx
0x180036897  test    byte ptr [rsp+6F0h+FindFileData.dwFileAttributes], 10h
0x18003689c  jnz     short loc_1800368D6
0x18003689e  lea     rax, [rsp+6F0h+FindFileData.cFileName]
0x1800368a3  mov     [rsp+6F0h+var_6D0], rax
0x1800368a8  mov     r9, r15
0x1800368ab  lea     r8, aSS_0; "%s\\%s"
0x1800368b2  mov     edx, 104h; unsigned __int64
0x1800368b7  lea     rcx, [rbp+5F0h+var_250]; unsigned __int16 *
0x1800368be  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800368c3  test    eax, eax
0x1800368c5  js      short loc_1800368EA
0x1800368c7  lea     rcx, [rbp+5F0h+var_250]; lpFileName
0x1800368ce  call    cs:__imp_DeleteFileW
0x1800368d4  and     esi, eax
0x1800368d6  lea     rdx, [rsp+6F0h+FindFileData]; lpFindFileData
0x1800368db  mov     rcx, r14; hFindFile
0x1800368de  call    cs:__imp_FindNextFileW
0x1800368e4  test    eax, eax
0x1800368e6  jnz     short loc_180036897
0x1800368e8  jmp     short loc_1800368EC
0x1800368ea  mov     ebx, eax
0x1800368ec  test    esi, esi
0x1800368ee  jz      short loc_180036914
0x1800368f0  jmp     short loc_180036910
0x1800368f2  call    cs:__imp_GetLastError
0x1800368f8  mov     ebx, eax
0x1800368fa  test    eax, eax
0x1800368fc  jz      short loc_18003690B
0x1800368fe  jle     short loc_180036910
0x180036900  movzx   ebx, ax
0x180036903  or      ebx, 80070000h
0x180036909  jmp     short loc_180036910
0x18003690b  mov     ebx, 80390004h
0x180036910  test    ebx, ebx
0x180036912  jns     short loc_180036916
0x180036914  xor     edi, edi
0x180036916  lea     rcx, [rsp+6F0h+var_6C0]
0x18003691b  call    ??1?$unique_any@Ufind_handle_traits@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::find_handle_traits>::~unique_any<tlx::find_handle_traits>(void)
0x180036920  mov     eax, edi
0x180036922  mov     rcx, [rbp+5F0h+var_40]
0x180036929  xor     rcx, rsp; StackCookie
0x18003692c  call    __security_check_cookie
0x180036931  add     rsp, 6C8h
0x180036938  pop     r15
0x18003693a  pop     r14
0x18003693c  pop     rdi
0x18003693d  pop     rsi
0x18003693e  pop     rbx
0x18003693f  pop     rbp
0x180036940  retn
```
