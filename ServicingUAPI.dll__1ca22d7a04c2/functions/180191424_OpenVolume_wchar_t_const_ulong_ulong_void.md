# OpenVolume(wchar_t const *,ulong,ulong,void * *)

- ea: `0x180191424`
- end: `0x1801915dd`
- name: `?OpenVolume@@YAJPEB_WKKPEAPEAX@Z`
- size: `441`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName, unsigned int, unsigned int, void **)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x180190e10`

## callees

- `0x18000aedc`
- `0x18019040c`
- `0x180190598`
- `0x180191424`

## import_xrefs

- `ntdll!NtClose` at `0x1801915a8`
- `ntdll!NtClose` at `0x1801915a8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801914b5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801914c6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801914df`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18019155a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801914b5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801914c6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801914df`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18019155a`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1801914fb`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1801914fb`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180191496`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18019152f`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180191496`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18019152f`

## string_xrefs

- `0x180191582`: `CreateFile`
- `0x180191448`: `OpenVolume`
- `0x180191589`: `OpenVolume`

## pseudocode

```c
__int64 __fastcall OpenVolume(LPCWSTR lpFileName, __int64 a2, __int64 a3, char **a4)
{
  unsigned int v6; // edi
  int v7; // edi
  char *FileW; // rax
  char *v9; // rbx
  signed int LastError; // eax
  int v12; // edx
  int v13; // ecx

  if ( !a4 )
  {
    if ( (Microsoft_WindowsPhone_StorageHelperEnableBits & 4) != 0 )
      McTemplateU0zz_EventWriteTransfer(lpFileName, NullParameter, L"OpenVolume", L"phVolume");
    return (unsigned int)-2147024809;
  }
  *a4 = (char *)-1LL;
  v7 = 100;
  FileW = (char *)CreateFileW(lpFileName, 0x80000000, 7u, 0, 3u, 0x28000080u, 0);
  while ( 1 )
  {
    v9 = FileW;
    if ( ((unsigned __int64)(FileW + 1) & 0xFFFFFFFFFFFFFFFEuLL) != 0 )
      goto LABEL_24;
    if ( GetLastError() != 21 )
    {
      if ( GetLastError() != 2 )
        break;
      if ( !v7-- )
        break;
    }
LABEL_13:
    Sleep(0x64u);
    FileW = (char *)CreateFileW(lpFileName, 0x80000000, 7u, 0, 3u, 0x80u, 0);
    if ( ((unsigned __int64)(v9 + 1) & 0xFFFFFFFFFFFFFFFEuLL) != 0 )
    {
      INTERNAL_ERROR_ACTION(-1073741595);
      JUMPOUT(0x1801915DCLL);
    }
  }
  if ( GetLastError() == 5 && v7 )
  {
    --v7;
    goto LABEL_13;
  }
  if ( (unsigned __int64)(v9 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
  {
LABEL_24:
    v6 = 0;
    *a4 = v9;
    return v6;
  }
  LastError = GetLastError();
  v6 = LastError;
  if ( LastError > 0 )
    v6 = (unsigned __int16)LastError | 0x80070000;
  if ( (Microsoft_WindowsPhone_StorageHelperEnableBits & 4) != 0 )
    McTemplateU0zzzq_EventWriteTransfer(
      v13,
      v12,
      (unsigned int)L"OpenVolume",
      (unsigned int)L"CreateFile",
      (__int64)lpFileName,
      v6);
  if ( v9 && v9 != (char *)-1LL && NtClose(v9) < 0 )
    __fastfail(7u);
  return v6;
}

```

## disassembly

```asm
0x180191424  push    rbx
0x180191426  push    rbp
0x180191427  push    rsi
0x180191428  push    rdi
0x180191429  sub     rsp, 48h
0x18019142d  mov     rsi, r9
0x180191430  mov     rbp, rcx
0x180191433  test    r9, r9
0x180191436  jnz     short loc_180191465
0x180191438  test    cs:Microsoft_WindowsPhone_StorageHelperEnableBits, 4
0x18019143f  jz      short loc_18019145B
0x180191441  lea     r9, aPhvolume; "phVolume"
0x180191448  lea     r8, aOpenvolume; "OpenVolume"
0x18019144f  lea     rdx, NullParameter
0x180191456  call    McTemplateU0zz_EventWriteTransfer
0x18019145b  mov     edi, 80070057h
0x180191460  jmp     loc_1801915C6
0x180191465  mov     qword ptr [r9], 0FFFFFFFFFFFFFFFFh
0x18019146c  mov     edi, 64h ; 'd'
0x180191471  mov     [rsp+68h+hTemplateFile], 0; hTemplateFile
0x18019147a  xor     r9d, r9d; lpSecurityAttributes
0x18019147d  mov     [rsp+68h+dwFlagsAndAttributes], 28000080h; dwFlagsAndAttributes
0x180191485  mov     edx, 80000000h; dwDesiredAccess
0x18019148a  mov     [rsp+68h+dwCreationDisposition], 3; dwCreationDisposition
0x180191492  lea     r8d, [rdi-5Dh]; dwShareMode
0x180191496  call    cs:__imp_CreateFileW
0x18019149d  nop     dword ptr [rax+rax+00h]
0x1801914a2  mov     rbx, rax
0x1801914a5  lea     rax, [rax+1]
0x1801914a9  test    rax, 0FFFFFFFFFFFFFFFEh
0x1801914af  jnz     loc_1801915C1
0x1801914b5  call    cs:__imp_GetLastError
0x1801914bc  nop     dword ptr [rax+rax+00h]
0x1801914c1  cmp     eax, 15h
0x1801914c4  jz      short loc_1801914F6
0x1801914c6  call    cs:__imp_GetLastError
0x1801914cd  nop     dword ptr [rax+rax+00h]
0x1801914d2  cmp     eax, 2
0x1801914d5  jnz     short loc_1801914DF
0x1801914d7  mov     eax, edi
0x1801914d9  dec     edi
0x1801914db  test    eax, eax
0x1801914dd  jnz     short loc_1801914F6
0x1801914df  call    cs:__imp_GetLastError
0x1801914e6  nop     dword ptr [rax+rax+00h]
0x1801914eb  cmp     eax, 5
0x1801914ee  jnz     short loc_180191550
0x1801914f0  test    edi, edi
0x1801914f2  jz      short loc_180191550
0x1801914f4  dec     edi
0x1801914f6  mov     ecx, 64h ; 'd'; dwMilliseconds
0x1801914fb  call    cs:__imp_Sleep
0x180191502  nop     dword ptr [rax+rax+00h]
0x180191507  xor     r9d, r9d; lpSecurityAttributes
0x18019150a  mov     [rsp+68h+hTemplateFile], 0; hTemplateFile
0x180191513  mov     [rsp+68h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x18019151b  mov     edx, 80000000h; dwDesiredAccess
0x180191520  mov     rcx, rbp; lpFileName
0x180191523  mov     [rsp+68h+dwCreationDisposition], 3; dwCreationDisposition
0x18019152b  lea     r8d, [r9+7]; dwShareMode
0x18019152f  call    cs:__imp_CreateFileW
0x180191536  nop     dword ptr [rax+rax+00h]
0x18019153b  inc     rbx
0x18019153e  test    rbx, 0FFFFFFFFFFFFFFFEh
0x180191545  jnz     loc_1801915D2
0x18019154b  jmp     loc_1801914A2
0x180191550  lea     rax, [rbx-1]
0x180191554  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180191558  jbe     short loc_1801915C1
0x18019155a  call    cs:__imp_GetLastError
0x180191561  nop     dword ptr [rax+rax+00h]
0x180191566  mov     edi, eax
0x180191568  test    eax, eax
0x18019156a  jle     short loc_180191575
0x18019156c  movzx   edi, ax
0x18019156f  or      edi, 80070000h
0x180191575  test    cs:Microsoft_WindowsPhone_StorageHelperEnableBits, 4
0x18019157c  jz      short loc_18019159A
0x18019157e  mov     [rsp+68h+dwFlagsAndAttributes], edi
0x180191582  lea     r9, aCreatefile; "CreateFile"
0x180191589  lea     r8, aOpenvolume; "OpenVolume"
0x180191590  mov     qword ptr [rsp+68h+dwCreationDisposition], rbp
0x180191595  call    McTemplateU0zzzq_EventWriteTransfer
0x18019159a  test    rbx, rbx
0x18019159d  jz      short loc_1801915C6
0x18019159f  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x1801915a3  jz      short loc_1801915C6
0x1801915a5  mov     rcx, rbx; Handle
0x1801915a8  call    cs:__imp_NtClose
0x1801915af  nop     dword ptr [rax+rax+00h]
0x1801915b4  test    eax, eax
0x1801915b6  jns     short loc_1801915C6
0x1801915b8  mov     ecx, 7
0x1801915bd  int     29h; Win8: RtlFailFast(ecx)
0x1801915bf  jmp     short loc_1801915C6
0x1801915c1  xor     edi, edi
0x1801915c3  mov     [rsi], rbx
0x1801915c6  mov     eax, edi
0x1801915c8  add     rsp, 48h
0x1801915cc  pop     rdi
0x1801915cd  pop     rsi
0x1801915ce  pop     rbp
0x1801915cf  pop     rbx
0x1801915d0  retn
0x1801915d2  mov     ecx, 0C00000E5h; int
0x1801915d7  call    ?INTERNAL_ERROR_ACTION@@YAXJ@Z; INTERNAL_ERROR_ACTION(long)
```
