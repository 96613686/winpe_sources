# SusCreateFileRetryIfSharingViolation(wchar_t const *,ulong,ulong,_SECURITY_ATTRIBUTES *,ulong,ulong,void *,ulong,void *,int,ulong)

- ea: `0x180049e88`
- end: `0x180049ff0`
- name: `?SusCreateFileRetryIfSharingViolation@@YAPEAXPEB_WKKPEAU_SECURITY_ATTRIBUTES@@KKPEAXK2HK@Z`
- size: `360`
- prototype: `void *__fastcall(LPCWSTR lpFileName, DWORD dwDesiredAccess, DWORD dwShareMode, struct _SECURITY_ATTRIBUTES *, DWORD, DWORD, void *, unsigned int, void *, int, unsigned int)`
- caller_count: `4`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180049414`
- `0x180055400`
- `0x1800596c0`
- `0x18005ae90`

## callees

- `0x1800110fc`
- `0x180049e88`
- `0x18004c938`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180049f01`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180049f01`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180049f4b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180049f4b`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180049fc4`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180049fc4`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180049f30`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180049f30`

## string_xrefs

- `0x180049f7d`: `CreateFile %ws (Access = %lu, Share = %lu)(retry %u ...)`
- `0x180049f88`: `SusCreateFileRetryIfSharingViolation`

## pseudocode

```c
void *__fastcall SusCreateFileRetryIfSharingViolation(
        LPCWSTR lpFileName,
        DWORD dwDesiredAccess,
        DWORD dwShareMode,
        struct _SECURITY_ATTRIBUTES *a4,
        DWORD a5,
        DWORD a6,
        void *a7,
        unsigned int a8,
        void *a9,
        int a10,
        unsigned int a11)
{
  unsigned int v11; // r12d
  unsigned int v13; // r13d
  int v16; // esi
  signed int v17; // ebx
  void *v18; // rdi
  signed int LastError; // eax
  int v20; // eax
  __int64 dwCreationDisposition; // [rsp+20h] [rbp-58h]
  struct _SECURITY_ATTRIBUTES *dwFlagsAndAttributes; // [rsp+28h] [rbp-50h]
  void *v24; // [rsp+40h] [rbp-38h]
  void *FileW; // [rsp+98h] [rbp+20h] BYREF

  v11 = a6;
  v13 = a5;
  FileW = (void *)-1LL;
  v16 = 0;
  while ( 1 )
  {
    if ( a10 )
    {
      v17 = SafeCreateFile(&FileW, a11, lpFileName, dwDesiredAccess, dwShareMode, dwFlagsAndAttributes, v13, v11, v24);
      SetLastError(v17);
      v18 = FileW;
    }
    else
    {
      FileW = CreateFileW(lpFileName, dwDesiredAccess, dwShareMode, 0, v13, v11, 0);
      v18 = FileW;
      if ( FileW != (void *)-1LL )
        return v18;
      LastError = GetLastError();
      v17 = (unsigned __int16)LastError | 0x80070000;
      if ( LastError <= 0 )
        v17 = LastError;
      if ( v17 >= 0 )
        v17 = -2147418113;
    }
    if ( v17 != -2147024891 && v17 != -2147024864 )
      break;
    LODWORD(v24) = dwShareMode;
    LODWORD(dwCreationDisposition) = v17;
    WUTrace(
      "SusCreateFileRetryIfSharingViolation",
      1921,
      32,
      3,
      dwCreationDisposition,
      L"CreateFile %ws (Access = %lu, Share = %lu)(retry %u ...)");
    v20 = v16++;
    if ( v20 == 10 )
      break;
    Sleep(0x1F4u);
  }
  return v18;
}

```

## disassembly

```asm
0x180049e88  mov     rax, rsp
0x180049e8b  mov     [rax+8], rbx
0x180049e8f  mov     [rax+10h], rbp
0x180049e93  mov     [rax+18h], rsi
0x180049e97  mov     [rax+20h], r9
0x180049e9b  push    rdi
0x180049e9c  push    r12
0x180049e9e  push    r13
0x180049ea0  push    r14
0x180049ea2  push    r15
0x180049ea4  sub     rsp, 50h
0x180049ea8  mov     r12d, [rsp+78h+arg_28]
0x180049eb0  mov     ebp, r8d
0x180049eb3  mov     r13d, [rsp+78h+arg_20]
0x180049ebb  mov     r14d, edx
0x180049ebe  mov     r15, rcx
0x180049ec1  mov     qword ptr [rax+20h], 0FFFFFFFFFFFFFFFFh
0x180049ec9  xor     esi, esi
0x180049ecb  cmp     [rsp+78h+arg_48], 0
0x180049ed3  jz      short loc_180049F11
0x180049ed5  mov     edx, [rsp+78h+arg_50]; unsigned int
0x180049edc  lea     rcx, [rsp+78h+arg_18]; void **
0x180049ee4  mov     [rsp+78h+var_40], r12d; unsigned int
0x180049ee9  mov     r9d, r14d; unsigned int
0x180049eec  mov     dword ptr [rsp+78h+hTemplateFile], r13d; unsigned int
0x180049ef1  mov     r8, r15; wchar_t *
0x180049ef4  mov     dword ptr [rsp+78h+dwCreationDisposition], ebp; unsigned int
0x180049ef8  call    ?SafeCreateFile@@YAJPEAPEAXKPEB_WKKPEAU_SECURITY_ATTRIBUTES@@KKPEAX@Z; SafeCreateFile(void * *,ulong,wchar_t const *,ulong,ulong,_SECURITY_ATTRIBUTES *,ulong,ulong,void *)
0x180049efd  mov     ecx, eax; dwErrCode
0x180049eff  mov     ebx, eax
0x180049f01  call    cs:__imp_SetLastError
0x180049f07  mov     rdi, [rsp+78h+arg_18]
0x180049f0f  jmp     short loc_180049F69
0x180049f11  mov     [rsp+78h+hTemplateFile], 0; hTemplateFile
0x180049f1a  xor     r9d, r9d; lpSecurityAttributes
0x180049f1d  mov     [rsp+78h+dwFlagsAndAttributes], r12d; dwFlagsAndAttributes
0x180049f22  mov     r8d, ebp; dwShareMode
0x180049f25  mov     edx, r14d; dwDesiredAccess
0x180049f28  mov     dword ptr [rsp+78h+dwCreationDisposition], r13d; dwCreationDisposition
0x180049f2d  mov     rcx, r15; lpFileName
0x180049f30  call    cs:__imp_CreateFileW
0x180049f36  mov     [rsp+78h+arg_18], rax
0x180049f3e  mov     rdi, rax
0x180049f41  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180049f45  jnz     loc_180049FCF
0x180049f4b  call    cs:__imp_GetLastError
0x180049f51  movzx   ebx, ax
0x180049f54  or      ebx, 80070000h
0x180049f5a  test    eax, eax
0x180049f5c  cmovle  ebx, eax
0x180049f5f  mov     eax, 8000FFFFh
0x180049f64  test    ebx, ebx
0x180049f66  cmovns  ebx, eax
0x180049f69  cmp     ebx, 80070005h
0x180049f6f  jz      short loc_180049F79
0x180049f71  cmp     ebx, 80070020h
0x180049f77  jnz     short loc_180049FCF
0x180049f79  mov     [rsp+78h+var_30], esi
0x180049f7d  lea     rax, aCreatefileWsAc; "CreateFile %ws (Access = %lu, Share = %"...
0x180049f84  mov     dword ptr [rsp+78h+var_38], ebp
0x180049f88  lea     rcx, aSuscreatefiler; "SusCreateFileRetryIfSharingViolation"
0x180049f8f  mov     [rsp+78h+var_40], r14d
0x180049f94  mov     r9d, 3
0x180049f9a  mov     [rsp+78h+hTemplateFile], r15
0x180049f9f  mov     edx, 781h
0x180049fa4  mov     qword ptr [rsp+78h+dwFlagsAndAttributes], rax
0x180049fa9  mov     dword ptr [rsp+78h+dwCreationDisposition], ebx
0x180049fad  lea     r8d, [r9+1Dh]
0x180049fb1  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x180049fb6  mov     eax, esi
0x180049fb8  inc     esi
0x180049fba  cmp     eax, 0Ah
0x180049fbd  jz      short loc_180049FCF
0x180049fbf  mov     ecx, 1F4h; dwMilliseconds
0x180049fc4  call    cs:__imp_Sleep
0x180049fca  jmp     loc_180049ECB
0x180049fcf  lea     r11, [rsp+78h+var_28]
0x180049fd4  mov     rax, rdi
0x180049fd7  mov     rbx, [r11+30h]
0x180049fdb  mov     rbp, [r11+38h]
0x180049fdf  mov     rsi, [r11+40h]
0x180049fe3  mov     rsp, r11
0x180049fe6  pop     r15
0x180049fe8  pop     r14
0x180049fea  pop     r13
0x180049fec  pop     r12
0x180049fee  pop     rdi
0x180049fef  retn
```
