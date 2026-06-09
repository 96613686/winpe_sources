# SafeCreateFile(void * *,ulong,wchar_t const *,ulong,ulong,_SECURITY_ATTRIBUTES *,ulong,ulong,void *)

- ea: `0x18004c938`
- end: `0x18004cb15`
- name: `?SafeCreateFile@@YAJPEAPEAXKPEB_WKKPEAU_SECURITY_ATTRIBUTES@@KKPEAX@Z`
- size: `477`
- prototype: `int(void **, unsigned int, const wchar_t *, unsigned int, unsigned int, struct _SECURITY_ATTRIBUTES *, unsigned int, unsigned int, void *)`
- caller_count: `2`
- callee_count: `7`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800496c4`
- `0x180049e88`

## callees

- `0x180003180`
- `0x1800110fc`
- `0x18004c5a8`
- `0x18004c708`
- `0x18004c854`
- `0x18004c8dc`
- `0x18004c938`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004ca4c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004ca4c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004caf5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004caf5`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18004ca3d`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18004ca3d`
- `api-ms-win-core-file-l1-1-0!GetFileType` at `0x18004cac0`
- `api-ms-win-core-file-l1-1-0!GetFileType` at `0x18004cac0`

## string_xrefs

- `0x18004ca8d`: `SafeCreateFile`
- `0x18004ca81`: `%ws (Access: %lu, Share: %lu)`

## pseudocode

```c
__int64 __fastcall SafeCreateFile(
        void **a1,
        int a2,
        const wchar_t *a3,
        DWORD a4,
        DWORD dwShareMode,
        struct _SECURITY_ATTRIBUTES *a6,
        DWORD a7,
        unsigned int a8)
{
  __int64 v11; // rbx
  __int64 v12; // rdx
  signed int v13; // edi
  HANDLE FileW; // rax
  signed int LastError; // eax
  DWORD dwCreationDisposition; // [rsp+20h] [rbp-88h]
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+0h]

  v11 = -1;
  if ( !a3 )
  {
    v12 = 427;
LABEL_7:
    v13 = -2147024809;
    goto LABEL_27;
  }
  if ( !a1 )
  {
    v12 = 428;
    goto LABEL_7;
  }
  if ( (a2 & 0xFFFFFFFC) != 0 )
  {
    v12 = 429;
    goto LABEL_7;
  }
  *a1 = (void *)-1LL;
  if ( (unsigned int)SkipPathDrivePart(a3, 0) )
  {
    if ( (unsigned int)DoesPathContainDotDot(a3) )
    {
      v13 = -2147024735;
      v12 = 437;
    }
    else if ( (unsigned int)DoesPathContainStreamSyntax(a3) )
    {
      v13 = -2147024773;
      v12 = 440;
    }
    else
    {
      v13 = CheckValidDriveType(a3);
      if ( v13 >= 0 )
      {
        FileW = CreateFileW(a3, a4, dwShareMode, 0, a7, a8 | 0x100000, 0);
        v11 = (__int64)FileW;
        if ( FileW == (HANDLE)-1LL )
        {
          LastError = GetLastError();
          v13 = (unsigned __int16)LastError | 0x80070000;
          if ( LastError <= 0 )
            v13 = LastError;
          if ( v13 < 0 )
          {
            if ( v13 == -2147024891 || v13 == -2147024864 )
            {
              dwCreationDisposition = v13;
              WUTrace("SafeCreateFile", 470, 32, 3);
            }
          }
          else
          {
            v13 = -2147418113;
          }
          v12 = 473;
        }
        else
        {
          if ( GetFileType(FileW) == 1 )
          {
            *a1 = (void *)v11;
            return 0;
          }
          v13 = -2147024786;
          v12 = 477;
        }
      }
      else
      {
        v12 = 445;
      }
    }
  }
  else
  {
    v13 = -2147024893;
    v12 = 434;
  }
LABEL_27:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v12,
    (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\wusafefn\\SafeFile.cpp",
    (const char *)(unsigned int)v13,
    dwCreationDisposition);
  if ( v11 != -1 )
    CloseHandle((HANDLE)v11);
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x18004c938  push    rbx
0x18004c93a  push    rbp
0x18004c93b  push    rsi
0x18004c93c  push    rdi
0x18004c93d  push    r12
0x18004c93f  push    r13
0x18004c941  push    r14
0x18004c943  push    r15
0x18004c945  sub     rsp, 68h
0x18004c949  mov     r12d, [rsp+0A8h+dwShareMode]
0x18004c951  or      rax, 0FFFFFFFFFFFFFFFFh
0x18004c955  mov     r13d, [rsp+0A8h+arg_30]
0x18004c95d  mov     r15d, r9d
0x18004c960  mov     ebp, [rsp+0A8h+arg_38]
0x18004c967  mov     rsi, r8
0x18004c96a  mov     edi, edx
0x18004c96c  mov     r14, rcx
0x18004c96f  mov     rbx, rax
0x18004c972  test    r8, r8
0x18004c975  jnz     short loc_18004C97E
0x18004c977  mov     edx, 1ABh
0x18004c97c  jmp     short loc_18004C997
0x18004c97e  test    r14, r14
0x18004c981  jnz     short loc_18004C98A
0x18004c983  mov     edx, 1ACh
0x18004c988  jmp     short loc_18004C997
0x18004c98a  test    edi, 0FFFFFFFCh
0x18004c990  jz      short loc_18004C9A1
0x18004c992  mov     edx, 1ADh
0x18004c997  mov     edi, 80070057h
0x18004c99c  jmp     loc_18004CAD5
0x18004c9a1  mov     [rcx], rax
0x18004c9a4  xor     edx, edx
0x18004c9a6  mov     rcx, rsi
0x18004c9a9  call    SkipPathDrivePart
0x18004c9ae  test    eax, eax
0x18004c9b0  jnz     short loc_18004C9C1
0x18004c9b2  mov     edi, 80070003h
0x18004c9b7  mov     edx, 1B2h
0x18004c9bc  jmp     loc_18004CAD5
0x18004c9c1  mov     rcx, rsi
0x18004c9c4  call    DoesPathContainDotDot
0x18004c9c9  test    eax, eax
0x18004c9cb  jz      short loc_18004C9DC
0x18004c9cd  mov     edi, 800700A1h
0x18004c9d2  mov     edx, 1B5h
0x18004c9d7  jmp     loc_18004CAD5
0x18004c9dc  mov     rcx, rsi
0x18004c9df  call    DoesPathContainStreamSyntax
0x18004c9e4  test    eax, eax
0x18004c9e6  jz      short loc_18004C9F7
0x18004c9e8  mov     edi, 8007007Bh
0x18004c9ed  mov     edx, 1B8h
0x18004c9f2  jmp     loc_18004CAD5
0x18004c9f7  mov     r8d, edi
0x18004c9fa  mov     rcx, rsi; lpszFileName
0x18004c9fd  and     edi, 1
0x18004ca00  and     r8d, 2
0x18004ca04  mov     edx, edi
0x18004ca06  call    CheckValidDriveType
0x18004ca0b  mov     edi, eax
0x18004ca0d  test    eax, eax
0x18004ca0f  jns     short loc_18004CA1B
0x18004ca11  mov     edx, 1BDh
0x18004ca16  jmp     loc_18004CAD5
0x18004ca1b  mov     [rsp+0A8h+hTemplateFile], 0; hTemplateFile
0x18004ca24  bts     ebp, 14h
0x18004ca28  mov     [rsp+0A8h+dwFlagsAndAttributes], ebp; dwFlagsAndAttributes
0x18004ca2c  xor     r9d, r9d; lpSecurityAttributes
0x18004ca2f  mov     r8d, r12d; dwShareMode
0x18004ca32  mov     [rsp+0A8h+dwCreationDisposition], r13d; int
0x18004ca37  mov     edx, r15d; dwDesiredAccess
0x18004ca3a  mov     rcx, rsi; lpFileName
0x18004ca3d  call    cs:__imp_CreateFileW
0x18004ca43  mov     rbx, rax
0x18004ca46  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18004ca4a  jnz     short loc_18004CABD
0x18004ca4c  call    cs:__imp_GetLastError
0x18004ca52  movzx   edi, ax
0x18004ca55  or      edi, 80070000h
0x18004ca5b  test    eax, eax
0x18004ca5d  cmovle  edi, eax
0x18004ca60  test    edi, edi
0x18004ca62  js      short loc_18004CA6B
0x18004ca64  mov     edi, 8000FFFFh
0x18004ca69  jmp     short loc_18004CAB6
0x18004ca6b  mov     eax, edi
0x18004ca6d  cmp     edi, 80070005h
0x18004ca73  jz      short loc_18004CA7C
0x18004ca75  cmp     eax, 80070020h
0x18004ca7a  jnz     short loc_18004CAB6
0x18004ca7c  mov     [rsp+0A8h+var_68], r12d
0x18004ca81  lea     rax, aWsAccessLuShar; "%ws (Access: %lu, Share: %lu)"
0x18004ca88  mov     [rsp+0A8h+var_70], r15d
0x18004ca8d  lea     rcx, aSafecreatefile; "SafeCreateFile"
0x18004ca94  mov     r9d, 3
0x18004ca9a  mov     [rsp+0A8h+hTemplateFile], rsi
0x18004ca9f  mov     qword ptr [rsp+0A8h+dwFlagsAndAttributes], rax
0x18004caa4  mov     edx, 1D6h
0x18004caa9  mov     [rsp+0A8h+dwCreationDisposition], edi
0x18004caad  lea     r8d, [r9+1Dh]
0x18004cab1  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x18004cab6  mov     edx, 1D9h
0x18004cabb  jmp     short loc_18004CAD5
0x18004cabd  mov     rcx, rbx; hFile
0x18004cac0  call    cs:__imp_GetFileType
0x18004cac6  cmp     eax, 1
0x18004cac9  jz      short loc_18004CAFD
0x18004cacb  mov     edi, 8007006Eh
0x18004cad0  mov     edx, 1DDh; void *
0x18004cad5  mov     rcx, [rsp+0A8h]; this
0x18004cadd  lea     r8, aCW1SSrcClientL_10; "C:\\__w\\1\\s\\src\\Client\\lib\\wusafe"...
0x18004cae4  mov     r9d, edi; char *
0x18004cae7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004caec  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x18004caf0  jz      short loc_18004CB02
0x18004caf2  mov     rcx, rbx; hObject
0x18004caf5  call    cs:__imp_CloseHandle
0x18004cafb  jmp     short loc_18004CB02
0x18004cafd  mov     [r14], rbx
0x18004cb00  xor     edi, edi
0x18004cb02  mov     eax, edi
0x18004cb04  add     rsp, 68h
0x18004cb08  pop     r15
0x18004cb0a  pop     r14
0x18004cb0c  pop     r13
0x18004cb0e  pop     r12
0x18004cb10  pop     rdi
0x18004cb11  pop     rsi
0x18004cb12  pop     rbp
0x18004cb13  pop     rbx
0x18004cb14  retn
```
