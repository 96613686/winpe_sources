# SafeCreateFile(void * *,ulong,wchar_t const *,ulong,ulong,_SECURITY_ATTRIBUTES *,ulong,ulong,void *)

- ea: `0x1400122f0`
- end: `0x1400124cd`
- name: `?SafeCreateFile@@YAJPEAPEAXKPEB_WKKPEAU_SECURITY_ATTRIBUTES@@KKPEAX@Z`
- size: `477`
- prototype: `__int64 __fastcall(void **, int, const wchar_t *, DWORD, DWORD dwShareMode, struct _SECURITY_ATTRIBUTES *, DWORD, unsigned int)`
- caller_count: `7`
- callee_count: `7`
- tags: `file_ops, broker_com_uri`

## callers

- `0x14000f39c`
- `0x14000fab0`
- `0x14000fc20`
- `0x14000fd94`
- `0x14002c6e0`
- `0x1400320b4`
- `0x1400323a0`

## callees

- `0x140008de4`
- `0x140011f60`
- `0x1400120c0`
- `0x14001220c`
- `0x140012294`
- `0x1400122f0`
- `0x1400154b4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140012404`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140012404`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400124ad`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400124ad`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1400123f5`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1400123f5`
- `api-ms-win-core-file-l1-1-0!GetFileType` at `0x140012478`
- `api-ms-win-core-file-l1-1-0!GetFileType` at `0x140012478`

## string_xrefs

- `0x140012439`: `%ws (Access: %lu, Share: %lu)`
- `0x140012445`: `SafeCreateFile`

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
  __int64 dwCreationDisposition; // [rsp+20h] [rbp-88h]
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
              LODWORD(dwCreationDisposition) = v13;
              WUTrace("SafeCreateFile", 470, 32, 3, dwCreationDisposition, L"%ws (Access: %lu, Share: %lu)");
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
0x1400122f0  push    rbx
0x1400122f2  push    rbp
0x1400122f3  push    rsi
0x1400122f4  push    rdi
0x1400122f5  push    r12
0x1400122f7  push    r13
0x1400122f9  push    r14
0x1400122fb  push    r15
0x1400122fd  sub     rsp, 68h
0x140012301  mov     r12d, [rsp+0A8h+dwShareMode]
0x140012309  or      rax, 0FFFFFFFFFFFFFFFFh
0x14001230d  mov     r13d, [rsp+0A8h+arg_30]
0x140012315  mov     r15d, r9d
0x140012318  mov     ebp, [rsp+0A8h+arg_38]
0x14001231f  mov     rsi, r8
0x140012322  mov     edi, edx
0x140012324  mov     r14, rcx
0x140012327  mov     rbx, rax
0x14001232a  test    r8, r8
0x14001232d  jnz     short loc_140012336
0x14001232f  mov     edx, 1ABh
0x140012334  jmp     short loc_14001234F
0x140012336  test    r14, r14
0x140012339  jnz     short loc_140012342
0x14001233b  mov     edx, 1ACh
0x140012340  jmp     short loc_14001234F
0x140012342  test    edi, 0FFFFFFFCh
0x140012348  jz      short loc_140012359
0x14001234a  mov     edx, 1ADh
0x14001234f  mov     edi, 80070057h
0x140012354  jmp     loc_14001248D
0x140012359  mov     [rcx], rax
0x14001235c  xor     edx, edx
0x14001235e  mov     rcx, rsi
0x140012361  call    SkipPathDrivePart
0x140012366  test    eax, eax
0x140012368  jnz     short loc_140012379
0x14001236a  mov     edi, 80070003h
0x14001236f  mov     edx, 1B2h
0x140012374  jmp     loc_14001248D
0x140012379  mov     rcx, rsi
0x14001237c  call    DoesPathContainDotDot
0x140012381  test    eax, eax
0x140012383  jz      short loc_140012394
0x140012385  mov     edi, 800700A1h
0x14001238a  mov     edx, 1B5h
0x14001238f  jmp     loc_14001248D
0x140012394  mov     rcx, rsi
0x140012397  call    DoesPathContainStreamSyntax
0x14001239c  test    eax, eax
0x14001239e  jz      short loc_1400123AF
0x1400123a0  mov     edi, 8007007Bh
0x1400123a5  mov     edx, 1B8h
0x1400123aa  jmp     loc_14001248D
0x1400123af  mov     r8d, edi
0x1400123b2  mov     rcx, rsi; lpszFileName
0x1400123b5  and     edi, 1
0x1400123b8  and     r8d, 2
0x1400123bc  mov     edx, edi
0x1400123be  call    CheckValidDriveType
0x1400123c3  mov     edi, eax
0x1400123c5  test    eax, eax
0x1400123c7  jns     short loc_1400123D3
0x1400123c9  mov     edx, 1BDh
0x1400123ce  jmp     loc_14001248D
0x1400123d3  mov     [rsp+0A8h+hTemplateFile], 0; hTemplateFile
0x1400123dc  bts     ebp, 14h
0x1400123e0  mov     [rsp+0A8h+dwFlagsAndAttributes], ebp; dwFlagsAndAttributes
0x1400123e4  xor     r9d, r9d; lpSecurityAttributes
0x1400123e7  mov     r8d, r12d; dwShareMode
0x1400123ea  mov     dword ptr [rsp+0A8h+dwCreationDisposition], r13d; int
0x1400123ef  mov     edx, r15d; dwDesiredAccess
0x1400123f2  mov     rcx, rsi; lpFileName
0x1400123f5  call    cs:__imp_CreateFileW
0x1400123fb  mov     rbx, rax
0x1400123fe  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x140012402  jnz     short loc_140012475
0x140012404  call    cs:__imp_GetLastError
0x14001240a  movzx   edi, ax
0x14001240d  or      edi, 80070000h
0x140012413  test    eax, eax
0x140012415  cmovle  edi, eax
0x140012418  test    edi, edi
0x14001241a  js      short loc_140012423
0x14001241c  mov     edi, 8000FFFFh
0x140012421  jmp     short loc_14001246E
0x140012423  mov     eax, edi
0x140012425  cmp     edi, 80070005h
0x14001242b  jz      short loc_140012434
0x14001242d  cmp     eax, 80070020h
0x140012432  jnz     short loc_14001246E
0x140012434  mov     [rsp+0A8h+var_68], r12d
0x140012439  lea     rax, aWsAccessLuShar; "%ws (Access: %lu, Share: %lu)"
0x140012440  mov     [rsp+0A8h+var_70], r15d
0x140012445  lea     rcx, aSafecreatefile; "SafeCreateFile"
0x14001244c  mov     r9d, 3
0x140012452  mov     [rsp+0A8h+hTemplateFile], rsi
0x140012457  mov     qword ptr [rsp+0A8h+dwFlagsAndAttributes], rax
0x14001245c  mov     edx, 1D6h
0x140012461  mov     dword ptr [rsp+0A8h+dwCreationDisposition], edi
0x140012465  lea     r8d, [r9+1Dh]
0x140012469  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x14001246e  mov     edx, 1D9h
0x140012473  jmp     short loc_14001248D
0x140012475  mov     rcx, rbx; hFile
0x140012478  call    cs:__imp_GetFileType
0x14001247e  cmp     eax, 1
0x140012481  jz      short loc_1400124B5
0x140012483  mov     edi, 8007006Eh
0x140012488  mov     edx, 1DDh; void *
0x14001248d  mov     rcx, [rsp+0A8h]; this
0x140012495  lea     r8, aCW1SSrcClientL_13; "C:\\__w\\1\\s\\src\\Client\\lib\\wusafe"...
0x14001249c  mov     r9d, edi; char *
0x14001249f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400124a4  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x1400124a8  jz      short loc_1400124BA
0x1400124aa  mov     rcx, rbx; hObject
0x1400124ad  call    cs:__imp_CloseHandle
0x1400124b3  jmp     short loc_1400124BA
0x1400124b5  mov     [r14], rbx
0x1400124b8  xor     edi, edi
0x1400124ba  mov     eax, edi
0x1400124bc  add     rsp, 68h
0x1400124c0  pop     r15
0x1400124c2  pop     r14
0x1400124c4  pop     r13
0x1400124c6  pop     r12
0x1400124c8  pop     rdi
0x1400124c9  pop     rsi
0x1400124ca  pop     rbp
0x1400124cb  pop     rbx
0x1400124cc  retn
```
