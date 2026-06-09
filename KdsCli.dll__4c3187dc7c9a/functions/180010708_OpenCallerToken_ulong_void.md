# OpenCallerToken(ulong,void * *)

- ea: `0x180010708`
- end: `0x1800107d5`
- name: `?OpenCallerToken@@YAJKPEAPEAX@Z`
- size: `205`
- prototype: `__int64 __fastcall(DWORD DesiredAccess, void **)`
- caller_count: `3`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000f640`
- `0x180010500`
- `0x180010624`

## callees

- `0x180010708`
- `0x18001a450`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010740`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010791`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010740`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010791`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180010787`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180010787`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180010777`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180010777`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001071e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001071e`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180010732`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180010732`

## string_xrefs

- `0x180010755`: `onecore\ds\security\keyman\sidkeyprov\common\sidkeyutil.cxx`
- `0x18001079d`: `onecore\ds\security\keyman\sidkeyprov\common\sidkeyutil.cxx`

## pseudocode

```c
__int64 __fastcall OpenCallerToken(DWORD DesiredAccess, void **a2)
{
  signed int v2; // ebx
  HANDLE CurrentThread; // rax
  DWORD LastError; // eax
  int v7; // edi
  HANDLE CurrentProcess; // rax
  __int64 result; // rax
  void *TokenHandle; // [rsp+58h] [rbp+10h] BYREF

  v2 = 0;
  TokenHandle = 0;
  CurrentThread = GetCurrentThread();
  if ( !OpenThreadToken(CurrentThread, DesiredAccess, 1, &TokenHandle) )
  {
    LastError = GetLastError();
    v7 = LastError;
    if ( LastError != 1008 )
    {
      SidKeyDebugTraceError(
        LastError,
        "dwReturn",
        "onecore\\ds\\security\\keyman\\sidkeyprov\\common\\sidkeyutil.cxx",
        0x8Bu);
      if ( v7 <= 0 )
      {
        v2 = v7;
        goto LABEL_10;
      }
      v2 = (unsigned __int16)v7;
LABEL_9:
      v2 |= 0x80070000;
      goto LABEL_10;
    }
    CurrentProcess = GetCurrentProcess();
    if ( !OpenProcessToken(CurrentProcess, DesiredAccess, &TokenHandle) )
    {
      v2 = GetLastError();
      SidKeyDebugTraceError(v2, "dwReturn", "onecore\\ds\\security\\keyman\\sidkeyprov\\common\\sidkeyutil.cxx", 0x93u);
      if ( v2 > 0 )
      {
        v2 = (unsigned __int16)v2;
        goto LABEL_9;
      }
    }
  }
LABEL_10:
  result = (unsigned int)v2;
  *a2 = TokenHandle;
  return result;
}

```

## disassembly

```asm
0x180010708  push    rbx
0x18001070a  push    rsi
0x18001070b  push    rdi
0x18001070c  push    r14
0x18001070e  sub     rsp, 28h
0x180010712  xor     ebx, ebx
0x180010714  mov     r14, rdx
0x180010717  mov     [rsp+48h+TokenHandle], rbx
0x18001071c  mov     esi, ecx
0x18001071e  call    cs:__imp_GetCurrentThread
0x180010724  lea     r9, [rsp+48h+TokenHandle]; TokenHandle
0x180010729  mov     edx, esi; DesiredAccess
0x18001072b  mov     rcx, rax; ThreadHandle
0x18001072e  lea     r8d, [rbx+1]; OpenAsSelf
0x180010732  call    cs:__imp_OpenThreadToken
0x180010738  test    eax, eax
0x18001073a  jnz     loc_1800107C1
0x180010740  call    cs:__imp_GetLastError
0x180010746  mov     edi, eax
0x180010748  cmp     eax, 3F0h
0x18001074d  jz      short loc_180010777
0x18001074f  mov     r9d, 8Bh; unsigned int
0x180010755  lea     r8, aOnecoreDsSecur_9; "onecore\\ds\\security\\keyman\\sidkeypr"...
0x18001075c  lea     rdx, aDwreturn; "dwReturn"
0x180010763  mov     ecx, eax; unsigned int
0x180010765  call    ?SidKeyDebugTraceError@@YAXKPEBD0K@Z; SidKeyDebugTraceError(ulong,char const *,char const *,ulong)
0x18001076a  test    edi, edi
0x18001076c  jg      short loc_180010772
0x18001076e  mov     ebx, edi
0x180010770  jmp     short loc_1800107C1
0x180010772  movzx   ebx, di
0x180010775  jmp     short loc_1800107BB
0x180010777  call    cs:__imp_GetCurrentProcess
0x18001077d  lea     r8, [rsp+48h+TokenHandle]; TokenHandle
0x180010782  mov     edx, esi; DesiredAccess
0x180010784  mov     rcx, rax; ProcessHandle
0x180010787  call    cs:__imp_OpenProcessToken
0x18001078d  test    eax, eax
0x18001078f  jnz     short loc_1800107C1
0x180010791  call    cs:__imp_GetLastError
0x180010797  mov     r9d, 93h; unsigned int
0x18001079d  lea     r8, aOnecoreDsSecur_9; "onecore\\ds\\security\\keyman\\sidkeypr"...
0x1800107a4  mov     ecx, eax; unsigned int
0x1800107a6  lea     rdx, aDwreturn; "dwReturn"
0x1800107ad  mov     ebx, eax
0x1800107af  call    ?SidKeyDebugTraceError@@YAXKPEBD0K@Z; SidKeyDebugTraceError(ulong,char const *,char const *,ulong)
0x1800107b4  test    ebx, ebx
0x1800107b6  jle     short loc_1800107C1
0x1800107b8  movzx   ebx, bx
0x1800107bb  or      ebx, 80070000h
0x1800107c1  mov     rcx, [rsp+48h+TokenHandle]
0x1800107c6  mov     eax, ebx
0x1800107c8  mov     [r14], rcx
0x1800107cb  add     rsp, 28h
0x1800107cf  pop     r14
0x1800107d1  pop     rdi
0x1800107d2  pop     rsi
0x1800107d3  pop     rbx
0x1800107d4  retn
```
