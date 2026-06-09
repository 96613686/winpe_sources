# SusCreateFileRetryIfSharingViolation(wchar_t const *,ulong,ulong,_SECURITY_ATTRIBUTES *,ulong,ulong,void *,ulong,void *,int,ulong)

- ea: `0x14000fab0`
- end: `0x14000fc18`
- name: `?SusCreateFileRetryIfSharingViolation@@YAPEAXPEB_WKKPEAU_SECURITY_ATTRIBUTES@@KKPEAXK2HK@Z`
- size: `360`
- prototype: `void *__fastcall(LPCWSTR lpFileName, DWORD dwDesiredAccess, DWORD dwShareMode, struct _SECURITY_ATTRIBUTES *, DWORD, DWORD, void *, unsigned int, void *, int, unsigned int)`
- caller_count: `4`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x14000efd0`
- `0x14002a8b4`
- `0x14002f510`
- `0x14003b2a0`

## callees

- `0x14000fab0`
- `0x1400122f0`
- `0x1400154b4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000fb29`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000fb29`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000fb73`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000fb73`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x14000fbec`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x14000fbec`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x14000fb58`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x14000fb58`

## string_xrefs

- `0x14000fba5`: `CreateFile %ws (Access = %lu, Share = %lu)(retry %u ...)`
- `0x14000fbb0`: `SusCreateFileRetryIfSharingViolation`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
  DWORD v13; // r13d
  int v16; // esi
  signed int v17; // ebx
  void *v18; // rdi
  signed int LastError; // eax
  int v20; // eax
  __int64 dwCreationDisposition; // [rsp+20h] [rbp-58h]
  struct _SECURITY_ATTRIBUTES *dwFlagsAndAttributes; // [rsp+28h] [rbp-50h]
  void *FileW; // [rsp+98h] [rbp+20h] BYREF

  v11 = a6;
  v13 = a5;
  FileW = (void *)-1LL;
  v16 = 0;
  while ( 1 )
  {
    if ( a10 )
    {
      v17 = SafeCreateFile(&FileW, a11, lpFileName, dwDesiredAccess, dwShareMode, dwFlagsAndAttributes, v13, v11);
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
0x14000fab0  mov     rax, rsp
0x14000fab3  mov     [rax+8], rbx
0x14000fab7  mov     [rax+10h], rbp
0x14000fabb  mov     [rax+18h], rsi
0x14000fabf  mov     [rax+20h], r9
0x14000fac3  push    rdi
0x14000fac4  push    r12
0x14000fac6  push    r13
0x14000fac8  push    r14
0x14000faca  push    r15
0x14000facc  sub     rsp, 50h
0x14000fad0  mov     r12d, [rsp+78h+arg_28]
0x14000fad8  mov     ebp, r8d
0x14000fadb  mov     r13d, [rsp+78h+arg_20]
0x14000fae3  mov     r14d, edx
0x14000fae6  mov     r15, rcx
0x14000fae9  mov     qword ptr [rax+20h], 0FFFFFFFFFFFFFFFFh
0x14000faf1  xor     esi, esi
0x14000faf3  cmp     [rsp+78h+arg_48], 0
0x14000fafb  jz      short loc_14000FB39
0x14000fafd  mov     edx, [rsp+78h+arg_50]; unsigned int
0x14000fb04  lea     rcx, [rsp+78h+arg_18]; void **
0x14000fb0c  mov     [rsp+78h+var_40], r12d; unsigned int
0x14000fb11  mov     r9d, r14d; unsigned int
0x14000fb14  mov     dword ptr [rsp+78h+hTemplateFile], r13d; unsigned int
0x14000fb19  mov     r8, r15; wchar_t *
0x14000fb1c  mov     dword ptr [rsp+78h+dwCreationDisposition], ebp; unsigned int
0x14000fb20  call    ?SafeCreateFile@@YAJPEAPEAXKPEB_WKKPEAU_SECURITY_ATTRIBUTES@@KKPEAX@Z; SafeCreateFile(void * *,ulong,wchar_t const *,ulong,ulong,_SECURITY_ATTRIBUTES *,ulong,ulong,void *)
0x14000fb25  mov     ecx, eax; dwErrCode
0x14000fb27  mov     ebx, eax
0x14000fb29  call    cs:__imp_SetLastError
0x14000fb2f  mov     rdi, [rsp+78h+arg_18]
0x14000fb37  jmp     short loc_14000FB91
0x14000fb39  mov     [rsp+78h+hTemplateFile], 0; hTemplateFile
0x14000fb42  xor     r9d, r9d; lpSecurityAttributes
0x14000fb45  mov     [rsp+78h+dwFlagsAndAttributes], r12d; dwFlagsAndAttributes
0x14000fb4a  mov     r8d, ebp; dwShareMode
0x14000fb4d  mov     edx, r14d; dwDesiredAccess
0x14000fb50  mov     dword ptr [rsp+78h+dwCreationDisposition], r13d; dwCreationDisposition
0x14000fb55  mov     rcx, r15; lpFileName
0x14000fb58  call    cs:__imp_CreateFileW
0x14000fb5e  mov     [rsp+78h+arg_18], rax
0x14000fb66  mov     rdi, rax
0x14000fb69  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14000fb6d  jnz     loc_14000FBF7
0x14000fb73  call    cs:__imp_GetLastError
0x14000fb79  movzx   ebx, ax
0x14000fb7c  or      ebx, 80070000h
0x14000fb82  test    eax, eax
0x14000fb84  cmovle  ebx, eax
0x14000fb87  mov     eax, 8000FFFFh
0x14000fb8c  test    ebx, ebx
0x14000fb8e  cmovns  ebx, eax
0x14000fb91  cmp     ebx, 80070005h
0x14000fb97  jz      short loc_14000FBA1
0x14000fb99  cmp     ebx, 80070020h
0x14000fb9f  jnz     short loc_14000FBF7
0x14000fba1  mov     [rsp+78h+var_30], esi
0x14000fba5  lea     rax, aCreatefileWsAc; "CreateFile %ws (Access = %lu, Share = %"...
0x14000fbac  mov     [rsp+78h+var_38], ebp
0x14000fbb0  lea     rcx, aSuscreatefiler; "SusCreateFileRetryIfSharingViolation"
0x14000fbb7  mov     [rsp+78h+var_40], r14d
0x14000fbbc  mov     r9d, 3
0x14000fbc2  mov     [rsp+78h+hTemplateFile], r15
0x14000fbc7  mov     edx, 781h
0x14000fbcc  mov     qword ptr [rsp+78h+dwFlagsAndAttributes], rax
0x14000fbd1  mov     dword ptr [rsp+78h+dwCreationDisposition], ebx
0x14000fbd5  lea     r8d, [r9+1Dh]
0x14000fbd9  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x14000fbde  mov     eax, esi
0x14000fbe0  inc     esi
0x14000fbe2  cmp     eax, 0Ah
0x14000fbe5  jz      short loc_14000FBF7
0x14000fbe7  mov     ecx, 1F4h; dwMilliseconds
0x14000fbec  call    cs:__imp_Sleep
0x14000fbf2  jmp     loc_14000FAF3
0x14000fbf7  lea     r11, [rsp+78h+var_28]
0x14000fbfc  mov     rax, rdi
0x14000fbff  mov     rbx, [r11+30h]
0x14000fc03  mov     rbp, [r11+38h]
0x14000fc07  mov     rsi, [r11+40h]
0x14000fc0b  mov     rsp, r11
0x14000fc0e  pop     r15
0x14000fc10  pop     r14
0x14000fc12  pop     r13
0x14000fc14  pop     r12
0x14000fc16  pop     rdi
0x14000fc17  retn
```
