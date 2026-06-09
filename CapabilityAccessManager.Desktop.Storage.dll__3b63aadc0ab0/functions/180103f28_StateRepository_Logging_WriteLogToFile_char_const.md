# StateRepository::Logging::WriteLogToFile(char const *)

- ea: `0x180103f28`
- end: `0x1801040f8`
- name: `?WriteLogToFile@Logging@StateRepository@@YAXPEBD@Z`
- size: `464`
- prototype: `void __fastcall(_BYTE *lpBuffer, const char *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops`

## callers

- `0x180103488`

## callees

- `0x180003060`
- `0x1800ec608`
- `0x1800edb2c`
- `0x180102320`
- `0x180102a7c`
- `0x180103f28`
- `0x18010d010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180103f64`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180103f64`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180103fd1`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180103fd1`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180104077`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180104077`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180103f84`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18010402f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180104046`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180103f84`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18010402f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180104046`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18010409d`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18010409d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180104069`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801040af`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180104069`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801040af`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180104025`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180104025`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180104000`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180104000`

## string_xrefs

- `0x1801040e6`: `onecore\base\appmodel\staterepository\dataaccesslayer\logging.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall StateRepository::Logging::WriteLogToFile(_BYTE *lpBuffer, const char *a2)
{
  int i; // ebp
  unsigned __int64 v4; // rdx
  const wchar_t *v5; // r8
  signed int v6; // eax
  signed int v7; // edi
  int v8; // eax
  __int64 v9; // rsi
  char *FileW; // rbx
  signed int v11; // eax
  signed int LastError; // eax
  HANDLE v13; // rbx
  wil::details::in1diag3 *v14; // rcx
  int dwCreationDisposition; // [rsp+20h] [rbp-268h]
  HANDLE Token[2]; // [rsp+40h] [rbp-248h] BYREF
  WCHAR FileName[264]; // [rsp+50h] [rbp-238h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+288h] [rbp+0h]

  wil::run_as_self_failfast(Token, a2);
  for ( i = 0; i < 100; ++i )
  {
    if ( i )
      Sleep(0);
    if ( (unsigned int)((__int64 (__fastcall *)(__int64, WCHAR *))qword_1801403C8)(260, FileName) )
    {
      v8 = StringCchCatW(FileName, v4, v5);
      if ( v8 < 0 )
        wil::details::in1diag3::_FailFast_Hr(
          retaddr,
          (void *)0x119,
          (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\logging.cpp",
          (const char *)(unsigned int)v8,
          dwCreationDisposition);
      v9 = -1;
      do
        ++v9;
      while ( lpBuffer[v9] );
      AcquireSRWLockExclusive(&stru_180140420);
      FileW = (char *)CreateFileW(FileName, 4u, 1u, 0, 4u, 0x80u, 0);
      if ( (unsigned __int64)(FileW - 1) > 0xFFFFFFFFFFFFFFFDuLL )
      {
        LastError = GetLastError();
        v7 = LastError;
        if ( LastError > 0 )
          v7 = (unsigned __int16)LastError | 0x80070000;
        if ( !FileW || FileW == (char *)-1LL )
          goto LABEL_19;
      }
      else
      {
        v7 = 0;
        if ( !WriteFile(FileW, lpBuffer, v9, 0, 0) )
        {
          v11 = GetLastError();
          v7 = v11;
          if ( v11 > 0 )
            v7 = (unsigned __int16)v11 | 0x80070000;
        }
      }
      CloseHandle(FileW);
LABEL_19:
      ReleaseSRWLockExclusive(&stru_180140420);
      goto LABEL_20;
    }
    v6 = GetLastError();
    v7 = v6;
    if ( v6 > 0 )
      v7 = (unsigned __int16)v6 | 0x80070000;
LABEL_20:
    if ( v7 >= 0 )
      break;
  }
  v13 = Token[0];
  if ( Token[0] != (HANDLE)-1LL )
  {
    if ( !SetThreadToken(0, Token[0]) )
      wil::details::in1diag3::_FailFastImmediate_Unexpected(v14);
    if ( v13 )
      CloseHandle(v13);
  }
}

```

## disassembly

```asm
0x180103f28  mov     [rsp+arg_8], rbx
0x180103f2d  mov     [rsp+arg_10], rbp
0x180103f32  push    rsi
0x180103f33  push    rdi
0x180103f34  push    r14
0x180103f36  sub     rsp, 270h
0x180103f3d  mov     rax, cs:__security_cookie
0x180103f44  xor     rax, rsp
0x180103f47  mov     [rsp+288h+var_28], rax
0x180103f4f  mov     r14, rcx
0x180103f52  lea     rcx, [rsp+288h+Token]
0x180103f57  call    ?run_as_self_failfast@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@@1@XZ; wil::run_as_self_failfast(void)
0x180103f5c  xor     ebp, ebp
0x180103f5e  test    ebp, ebp
0x180103f60  jz      short loc_180103F6A
0x180103f62  xor     ecx, ecx; dwMilliseconds
0x180103f64  call    cs:__imp_Sleep
0x180103f6a  lea     rdx, [rsp+288h+FileName]
0x180103f6f  mov     ecx, 104h
0x180103f74  mov     rax, cs:qword_1801403C8
0x180103f7b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180103f80  test    eax, eax
0x180103f82  jnz     short loc_180103FA2
0x180103f84  call    cs:__imp_GetLastError
0x180103f8a  mov     edi, eax
0x180103f8c  test    eax, eax
0x180103f8e  jle     loc_18010407E
0x180103f94  movzx   edi, ax
0x180103f97  or      edi, 80070000h
0x180103f9d  jmp     loc_18010407E
0x180103fa2  lea     rcx, [rsp+288h+FileName]; wchar_t *
0x180103fa7  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x180103fac  mov     rcx, [rsp+288h]; this
0x180103fb4  test    eax, eax
0x180103fb6  js      loc_1801040E3
0x180103fbc  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180103fc0  inc     rsi
0x180103fc3  cmp     byte ptr [r14+rsi], 0
0x180103fc8  jnz     short loc_180103FC0
0x180103fca  lea     rcx, stru_180140420; SRWLock
0x180103fd1  call    cs:__imp_AcquireSRWLockExclusive
0x180103fd7  mov     [rsp+288h+hTemplateFile], 0; hTemplateFile
0x180103fe0  mov     [rsp+288h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x180103fe8  mov     [rsp+288h+dwCreationDisposition], 4; dwCreationDisposition
0x180103ff0  xor     r9d, r9d; lpSecurityAttributes
0x180103ff3  lea     edx, [r9+4]; dwDesiredAccess
0x180103ff7  lea     r8d, [r9+1]; dwShareMode
0x180103ffb  lea     rcx, [rsp+288h+FileName]; lpFileName
0x180104000  call    cs:__imp_CreateFileW
0x180104006  mov     rbx, rax
0x180104009  dec     rax
0x18010400c  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180104010  ja      short loc_180104046
0x180104012  xor     edi, edi
0x180104014  mov     r8d, esi; nNumberOfBytesToWrite
0x180104017  mov     qword ptr [rsp+288h+dwCreationDisposition], rdi; lpOverlapped
0x18010401c  xor     r9d, r9d; lpNumberOfBytesWritten
0x18010401f  mov     rdx, r14; lpBuffer
0x180104022  mov     rcx, rbx; hFile
0x180104025  call    cs:__imp_WriteFile
0x18010402b  test    eax, eax
0x18010402d  jnz     short loc_180104066
0x18010402f  call    cs:__imp_GetLastError
0x180104035  mov     edi, eax
0x180104037  test    eax, eax
0x180104039  jle     short loc_180104066
0x18010403b  movzx   edi, ax
0x18010403e  or      edi, 80070000h
0x180104044  jmp     short loc_180104066
0x180104046  call    cs:__imp_GetLastError
0x18010404c  mov     edi, eax
0x18010404e  test    eax, eax
0x180104050  jle     short loc_18010405B
0x180104052  movzx   edi, ax
0x180104055  or      edi, 80070000h
0x18010405b  test    rbx, rbx
0x18010405e  jz      short loc_180104070
0x180104060  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x180104064  jz      short loc_180104070
0x180104066  mov     rcx, rbx; hObject
0x180104069  call    cs:__imp_CloseHandle
0x18010406f  nop
0x180104070  lea     rcx, stru_180140420; SRWLock
0x180104077  call    cs:__imp_ReleaseSRWLockExclusive
0x18010407d  nop
0x18010407e  test    edi, edi
0x180104080  jns     short loc_18010408D
0x180104082  inc     ebp
0x180104084  cmp     ebp, 64h ; 'd'
0x180104087  jl      loc_180103F5E
0x18010408d  mov     rbx, [rsp+288h+Token]
0x180104092  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x180104096  jz      short loc_1801040B5
0x180104098  mov     rdx, rbx; Token
0x18010409b  xor     ecx, ecx; Thread
0x18010409d  call    cs:__imp_SetThreadToken
0x1801040a3  test    eax, eax
0x1801040a5  jz      short loc_1801040DD
0x1801040a7  test    rbx, rbx
0x1801040aa  jz      short loc_1801040B5
0x1801040ac  mov     rcx, rbx; hObject
0x1801040af  call    cs:__imp_CloseHandle
0x1801040b5  mov     rcx, [rsp+288h+var_28]
0x1801040bd  xor     rcx, rsp; StackCookie
0x1801040c0  call    __security_check_cookie
0x1801040c5  lea     r11, [rsp+288h+var_18]
0x1801040cd  mov     rbx, [r11+28h]
0x1801040d1  mov     rbp, [r11+30h]
0x1801040d5  mov     rsp, r11
0x1801040d8  pop     r14
0x1801040da  pop     rdi
0x1801040db  pop     rsi
0x1801040dc  retn
0x1801040dd  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x1801040e3  mov     r9d, eax; char *
0x1801040e6  lea     r8, aOnecoreBaseApp_7; "onecore\\base\\appmodel\\staterepositor"...
0x1801040ed  mov     edx, 119h; void *
0x1801040f2  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
```
