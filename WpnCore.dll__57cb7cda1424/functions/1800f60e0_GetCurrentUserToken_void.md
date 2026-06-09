# GetCurrentUserToken(void * *)

- ea: `0x1800f60e0`
- end: `0x1800f6197`
- name: `?GetCurrentUserToken@@YAJPEAPEAX@Z`
- size: `183`
- prototype: `__int64 __fastcall(PHANDLE TokenHandle)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800f59ec`

## callees

- `0x180011618`
- `0x18009abf8`
- `0x1800f60e0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f6131`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f6131`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800f6159`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800f6159`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800f616a`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800f616a`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800f6127`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800f6127`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800f6112`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800f6112`

## string_xrefs

- `0x1800f60ff`: `onecoreuap\base\diagnosis\platform\notifications\common\wpnusermgrutil.cpp`
- `0x1800f6179`: `onecoreuap\base\diagnosis\platform\notifications\common\wpnusermgrutil.cpp`

## pseudocode

```c
__int64 __fastcall GetCurrentUserToken(PHANDLE TokenHandle)
{
  unsigned int v2; // ebx
  __int64 v3; // rdx
  HANDLE CurrentThread; // rax
  signed int LastError; // eax
  HANDLE CurrentProcess; // rax
  const char *v8; // r9
  int v9; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  if ( !TokenHandle )
  {
    v2 = -2147024809;
    v3 = 18;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v3,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\common\\wpnusermgrutil.cpp",
      (const char *)v2,
      v9);
    return v2;
  }
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 8u, 1, TokenHandle) )
    return 0;
  LastError = GetLastError();
  v2 = LastError;
  if ( LastError > 0 )
    v2 = (unsigned __int16)LastError | 0x80070000;
  if ( v2 != -2147023888 && (v2 & 0x80000000) != 0 )
  {
    v3 = 31;
    goto LABEL_3;
  }
  CurrentProcess = GetCurrentProcess();
  if ( OpenProcessToken(CurrentProcess, 8u, TokenHandle) )
    return 0;
  else
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)0x25,
             (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\common\\wpnusermgrutil.cpp",
             v8);
}

```

## disassembly

```asm
0x1800f60e0  mov     [rsp+arg_0], rbx
0x1800f60e5  push    rdi; int
0x1800f60e6  sub     rsp, 20h
0x1800f60ea  mov     rdi, rcx
0x1800f60ed  test    rcx, rcx
0x1800f60f0  jnz     short loc_1800F6112
0x1800f60f2  mov     ebx, 80070057h
0x1800f60f7  lea     edx, [rcx+12h]; void *
0x1800f60fa  mov     rcx, [rsp+28h]; this
0x1800f60ff  lea     r8, aOnecoreuapBase_105; "onecoreuap\\base\\diagnosis\\platform\\"...
0x1800f6106  mov     r9d, ebx; char *
0x1800f6109  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800f610e  mov     eax, ebx
0x1800f6110  jmp     short loc_1800F618C
0x1800f6112  call    cs:__imp_GetCurrentThread
0x1800f6118  mov     edx, 8; DesiredAccess
0x1800f611d  mov     r9, rdi; TokenHandle
0x1800f6120  mov     rcx, rax; ThreadHandle
0x1800f6123  lea     r8d, [rdx-7]; OpenAsSelf
0x1800f6127  call    cs:__imp_OpenThreadToken
0x1800f612d  test    eax, eax
0x1800f612f  jnz     short loc_1800F618A
0x1800f6131  call    cs:__imp_GetLastError
0x1800f6137  mov     ebx, eax
0x1800f6139  test    eax, eax
0x1800f613b  jle     short loc_1800F6146
0x1800f613d  movzx   ebx, ax
0x1800f6140  or      ebx, 80070000h
0x1800f6146  cmp     ebx, 800703F0h
0x1800f614c  jz      short loc_1800F6159
0x1800f614e  test    ebx, ebx
0x1800f6150  jns     short loc_1800F6159
0x1800f6152  mov     edx, 1Fh
0x1800f6157  jmp     short loc_1800F60FA
0x1800f6159  call    cs:__imp_GetCurrentProcess
0x1800f615f  mov     r8, rdi; TokenHandle
0x1800f6162  mov     edx, 8; DesiredAccess
0x1800f6167  mov     rcx, rax; ProcessHandle
0x1800f616a  call    cs:__imp_OpenProcessToken
0x1800f6170  test    eax, eax
0x1800f6172  jnz     short loc_1800F618A
0x1800f6174  mov     rcx, [rsp+28h]; this
0x1800f6179  lea     r8, aOnecoreuapBase_105; "onecoreuap\\base\\diagnosis\\platform\\"...
0x1800f6180  lea     edx, [rax+25h]; void *
0x1800f6183  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800f6188  jmp     short loc_1800F618C
0x1800f618a  xor     eax, eax
0x1800f618c  mov     rbx, [rsp+28h+arg_0]
0x1800f6191  add     rsp, 20h
0x1800f6195  pop     rdi
0x1800f6196  retn
```
