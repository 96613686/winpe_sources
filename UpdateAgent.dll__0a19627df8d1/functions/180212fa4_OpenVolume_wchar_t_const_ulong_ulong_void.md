# OpenVolume(wchar_t const *,ulong,ulong,void * *)

- ea: `0x180212fa4`
- end: `0x18021315d`
- name: `?OpenVolume@@YAJPEB_WKKPEAPEAX@Z`
- size: `441`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName, unsigned int, unsigned int, void **)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x180212990`

## callees

- `0x1800692fc`
- `0x180211f8c`
- `0x180212118`
- `0x180212fa4`

## import_xrefs

- `ntdll!NtClose` at `0x180213128`
- `ntdll!NtClose` at `0x180213128`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180213016`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1802130af`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180213016`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1802130af`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18021307b`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18021307b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180213035`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180213046`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18021305f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1802130da`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180213035`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180213046`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18021305f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1802130da`

## string_xrefs

- `0x180212fc8`: `OpenVolume`
- `0x180213109`: `OpenVolume`
- `0x180213102`: `CreateFile`

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
      JUMPOUT(0x18021315CLL);
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
0x180212fa4  push    rbx
0x180212fa6  push    rbp
0x180212fa7  push    rsi
0x180212fa8  push    rdi
0x180212fa9  sub     rsp, 48h
0x180212fad  mov     rsi, r9
0x180212fb0  mov     rbp, rcx
0x180212fb3  test    r9, r9
0x180212fb6  jnz     short loc_180212FE5
0x180212fb8  test    cs:Microsoft_WindowsPhone_StorageHelperEnableBits, 4
0x180212fbf  jz      short loc_180212FDB
0x180212fc1  lea     r9, aPhvolume; "phVolume"
0x180212fc8  lea     r8, aOpenvolume; "OpenVolume"
0x180212fcf  lea     rdx, NullParameter
0x180212fd6  call    McTemplateU0zz_EventWriteTransfer
0x180212fdb  mov     edi, 80070057h
0x180212fe0  jmp     loc_180213146
0x180212fe5  mov     qword ptr [r9], 0FFFFFFFFFFFFFFFFh
0x180212fec  mov     edi, 64h ; 'd'
0x180212ff1  mov     [rsp+68h+hTemplateFile], 0; hTemplateFile
0x180212ffa  xor     r9d, r9d; lpSecurityAttributes
0x180212ffd  mov     [rsp+68h+dwFlagsAndAttributes], 28000080h; dwFlagsAndAttributes
0x180213005  mov     edx, 80000000h; dwDesiredAccess
0x18021300a  mov     [rsp+68h+dwCreationDisposition], 3; dwCreationDisposition
0x180213012  lea     r8d, [rdi-5Dh]; dwShareMode
0x180213016  call    cs:__imp_CreateFileW
0x18021301d  nop     dword ptr [rax+rax+00h]
0x180213022  mov     rbx, rax
0x180213025  lea     rax, [rax+1]
0x180213029  test    rax, 0FFFFFFFFFFFFFFFEh
0x18021302f  jnz     loc_180213141
0x180213035  call    cs:__imp_GetLastError
0x18021303c  nop     dword ptr [rax+rax+00h]
0x180213041  cmp     eax, 15h
0x180213044  jz      short loc_180213076
0x180213046  call    cs:__imp_GetLastError
0x18021304d  nop     dword ptr [rax+rax+00h]
0x180213052  cmp     eax, 2
0x180213055  jnz     short loc_18021305F
0x180213057  mov     eax, edi
0x180213059  dec     edi
0x18021305b  test    eax, eax
0x18021305d  jnz     short loc_180213076
0x18021305f  call    cs:__imp_GetLastError
0x180213066  nop     dword ptr [rax+rax+00h]
0x18021306b  cmp     eax, 5
0x18021306e  jnz     short loc_1802130D0
0x180213070  test    edi, edi
0x180213072  jz      short loc_1802130D0
0x180213074  dec     edi
0x180213076  mov     ecx, 64h ; 'd'; dwMilliseconds
0x18021307b  call    cs:__imp_Sleep
0x180213082  nop     dword ptr [rax+rax+00h]
0x180213087  xor     r9d, r9d; lpSecurityAttributes
0x18021308a  mov     [rsp+68h+hTemplateFile], 0; hTemplateFile
0x180213093  mov     [rsp+68h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x18021309b  mov     edx, 80000000h; dwDesiredAccess
0x1802130a0  mov     rcx, rbp; lpFileName
0x1802130a3  mov     [rsp+68h+dwCreationDisposition], 3; dwCreationDisposition
0x1802130ab  lea     r8d, [r9+7]; dwShareMode
0x1802130af  call    cs:__imp_CreateFileW
0x1802130b6  nop     dword ptr [rax+rax+00h]
0x1802130bb  inc     rbx
0x1802130be  test    rbx, 0FFFFFFFFFFFFFFFEh
0x1802130c5  jnz     loc_180213152
0x1802130cb  jmp     loc_180213022
0x1802130d0  lea     rax, [rbx-1]
0x1802130d4  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1802130d8  jbe     short loc_180213141
0x1802130da  call    cs:__imp_GetLastError
0x1802130e1  nop     dword ptr [rax+rax+00h]
0x1802130e6  mov     edi, eax
0x1802130e8  test    eax, eax
0x1802130ea  jle     short loc_1802130F5
0x1802130ec  movzx   edi, ax
0x1802130ef  or      edi, 80070000h
0x1802130f5  test    cs:Microsoft_WindowsPhone_StorageHelperEnableBits, 4
0x1802130fc  jz      short loc_18021311A
0x1802130fe  mov     [rsp+68h+dwFlagsAndAttributes], edi
0x180213102  lea     r9, aCreatefile; "CreateFile"
0x180213109  lea     r8, aOpenvolume; "OpenVolume"
0x180213110  mov     qword ptr [rsp+68h+dwCreationDisposition], rbp
0x180213115  call    McTemplateU0zzzq_EventWriteTransfer
0x18021311a  test    rbx, rbx
0x18021311d  jz      short loc_180213146
0x18021311f  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x180213123  jz      short loc_180213146
0x180213125  mov     rcx, rbx; Handle
0x180213128  call    cs:__imp_NtClose
0x18021312f  nop     dword ptr [rax+rax+00h]
0x180213134  test    eax, eax
0x180213136  jns     short loc_180213146
0x180213138  mov     ecx, 7
0x18021313d  int     29h; Win8: RtlFailFast(ecx)
0x18021313f  jmp     short loc_180213146
0x180213141  xor     edi, edi
0x180213143  mov     [rsi], rbx
0x180213146  mov     eax, edi
0x180213148  add     rsp, 48h
0x18021314c  pop     rdi
0x18021314d  pop     rsi
0x18021314e  pop     rbp
0x18021314f  pop     rbx
0x180213150  retn
0x180213152  mov     ecx, 0C00000E5h; int
0x180213157  call    ?INTERNAL_ERROR_ACTION@@YAXJ@Z; INTERNAL_ERROR_ACTION(long)
```
