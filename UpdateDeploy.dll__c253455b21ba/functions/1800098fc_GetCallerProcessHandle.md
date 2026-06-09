# GetCallerProcessHandle

- ea: `0x1800098fc`
- end: `0x180009a77`
- name: `GetCallerProcessHandle`
- size: `379`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180039b00`
- `0x180039c90`

## callees

- `0x180002214`
- `0x180003180`
- `0x180007b6c`
- `0x1800098fc`
- `0x180061960`
- `0x180068f20`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800099bf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800099bf`
- `api-ms-win-core-com-l1-1-0!CoSwitchCallContext` at `0x180009975`
- `api-ms-win-core-com-l1-1-0!CoSwitchCallContext` at `0x180009a3c`
- `api-ms-win-core-com-l1-1-0!CoSwitchCallContext` at `0x180009975`
- `api-ms-win-core-com-l1-1-0!CoSwitchCallContext` at `0x180009a3c`
- `RPCRT4!RpcServerInqCallAttributesW` at `0x1800099b0`
- `RPCRT4!RpcServerInqCallAttributesW` at `0x1800099b0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009a4a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009a4a`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180009a00`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180009a00`

## string_xrefs

- `0x180009931`: `C:\__w\1\s\src\Client\lib\util\SecurityUtil.cpp`
- `0x18000998c`: `C:\__w\1\s\src\Client\lib\util\SecurityUtil.cpp`
- `0x1800099dd`: `C:\__w\1\s\src\Client\lib\util\SecurityUtil.cpp`
- `0x180009a12`: `C:\__w\1\s\src\Client\lib\util\SecurityUtil.cpp`

## pseudocode

```c
__int64 __fastcall GetCallerProcessHandle(__int64 a1, _QWORD *a2)
{
  HRESULT v4; // eax
  RPC_STATUS v5; // eax
  unsigned int LastError; // edi
  int CurrentProcessId; // eax
  HANDLE v8; // rax
  const char *v9; // r9
  int RpcCallAttributes[32]; // [rsp+28h] [rbp-49h] BYREF
  __int64 v11; // [rsp+A8h] [rbp+37h]
  IUnknown *ppOldObject; // [rsp+B0h] [rbp+3Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D0h] [rbp+5Fh]

  if ( !a2 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xB5,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\SecurityUtil.cpp",
      (const char *)0x80004003LL,
      RpcCallAttributes[0]);
    return 2147500035LL;
  }
  memset(&RpcCallAttributes[2], 0, 0x70u);
  v11 = 0;
  ppOldObject = 0;
  *a2 = 0;
  v4 = CoSwitchCallContext(0, &ppOldObject);
  if ( v4 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0xBF,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\SecurityUtil.cpp",
      (const char *)(unsigned int)v4,
      RpcCallAttributes[0]);
  else
    LODWORD(v11) = 1;
  RpcCallAttributes[0] = 3;
  RpcCallAttributes[1] = 112;
  v5 = RpcServerInqCallAttributesW(0, RpcCallAttributes);
  LastError = v5;
  if ( v5 == 1725 )
  {
    CurrentProcessId = GetCurrentProcessId();
  }
  else
  {
    if ( v5 >= 1 )
      LastError = (unsigned __int16)v5 | 0x80010000;
    if ( (LastError & 0x80000000) != 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xCD,
        (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\SecurityUtil.cpp",
        (const char *)LastError,
        RpcCallAttributes[0]);
      goto LABEL_16;
    }
    CurrentProcessId = RpcCallAttributes[16];
  }
  v8 = OpenProcess(0x440u, 0, CurrentProcessId);
  if ( v8 )
  {
    *a2 = v8;
    LastError = 0;
  }
  else
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0xD2,
                  (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\SecurityUtil.cpp",
                  v9);
  }
LABEL_16:
  if ( (_DWORD)v11 )
    CoSwitchCallContext(ppOldObject, &ppOldObject);
  return LastError;
}

```

## disassembly

```asm
0x1800098fc  mov     rax, rsp
0x1800098ff  mov     [rax+8], rbx
0x180009903  mov     [rax+18h], rsi
0x180009907  mov     [rax+20h], rdi
0x18000990b  push    rbp
0x18000990c  lea     rbp, [rax-5Fh]
0x180009910  sub     rsp, 0C0h
0x180009917  mov     rax, cs:__security_cookie
0x18000991e  xor     rax, rsp
0x180009921  mov     [rbp+57h+var_10], rax
0x180009925  mov     rsi, rdx
0x180009928  test    rdx, rdx
0x18000992b  jnz     short loc_180009951
0x18000992d  mov     rcx, [rbp+5Fh]; this
0x180009931  lea     r8, aCW1SSrcClientL_17; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x180009938  mov     ebx, 80004003h
0x18000993d  mov     edx, 0B5h; void *
0x180009942  mov     r9d, ebx; char *
0x180009945  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000994a  mov     eax, ebx
0x18000994c  jmp     loc_180009A52
0x180009951  xor     ebx, ebx
0x180009953  lea     rcx, [rbp+57h+var_98]; void *
0x180009957  xor     edx, edx; Val
0x180009959  lea     edi, [rbx+70h]
0x18000995c  mov     r8d, edi; Size
0x18000995f  call    memset
0x180009964  lea     rdx, [rbp+57h+ppOldObject]; ppOldObject
0x180009968  mov     [rbp+57h+var_20], rbx
0x18000996c  xor     ecx, ecx; pNewObject
0x18000996e  mov     [rbp+57h+ppOldObject], rbx
0x180009972  mov     [rsi], rbx
0x180009975  call    cs:__imp_CoSwitchCallContext
0x18000997b  test    eax, eax
0x18000997d  js      short loc_180009988
0x18000997f  mov     dword ptr [rbp+57h+var_20], 1
0x180009986  jmp     short loc_1800099A0
0x180009988  mov     rcx, [rbp+5Fh]; this
0x18000998c  lea     r8, aCW1SSrcClientL_17; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x180009993  mov     r9d, eax; char *
0x180009996  mov     edx, 0BFh; void *
0x18000999b  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800099a0  lea     rdx, [rbp+57h+RpcCallAttributes]; RpcCallAttributes
0x1800099a4  mov     [rbp+57h+RpcCallAttributes], 3
0x1800099ab  xor     ecx, ecx; ClientBinding
0x1800099ad  mov     [rbp+57h+var_9C], edi
0x1800099b0  call    cs:__imp_RpcServerInqCallAttributesW
0x1800099b6  mov     edi, eax
0x1800099b8  cmp     eax, 6BDh
0x1800099bd  jnz     short loc_1800099C7
0x1800099bf  call    cs:__imp_GetCurrentProcessId
0x1800099c5  jmp     short loc_1800099F6
0x1800099c7  cmp     eax, 1
0x1800099ca  jl      short loc_1800099D5
0x1800099cc  movzx   edi, ax
0x1800099cf  or      edi, 80010000h
0x1800099d5  test    edi, edi
0x1800099d7  jns     short loc_1800099F3
0x1800099d9  mov     rcx, [rbp+5Fh]; this
0x1800099dd  lea     r8, aCW1SSrcClientL_17; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x1800099e4  mov     r9d, edi; char *
0x1800099e7  mov     edx, 0CDh; void *
0x1800099ec  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800099f1  jmp     short loc_180009A2E
0x1800099f3  mov     eax, [rbp+57h+var_60]
0x1800099f6  mov     r8d, eax; dwProcessId
0x1800099f9  xor     edx, edx; bInheritHandle
0x1800099fb  mov     ecx, 440h; dwDesiredAccess
0x180009a00  call    cs:__imp_OpenProcess
0x180009a06  mov     rbx, rax
0x180009a09  test    rax, rax
0x180009a0c  jnz     short loc_180009A27
0x180009a0e  mov     rcx, [rbp+5Fh]; this
0x180009a12  lea     r8, aCW1SSrcClientL_17; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x180009a19  mov     edx, 0D2h; void *
0x180009a1e  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180009a23  mov     edi, eax
0x180009a25  jmp     short loc_180009A2E
0x180009a27  xor     ebx, ebx
0x180009a29  mov     [rsi], rax
0x180009a2c  xor     edi, edi
0x180009a2e  cmp     dword ptr [rbp+57h+var_20], 0
0x180009a32  jz      short loc_180009A50
0x180009a34  mov     rcx, [rbp+57h+ppOldObject]; pNewObject
0x180009a38  lea     rdx, [rbp+57h+ppOldObject]; ppOldObject
0x180009a3c  call    cs:__imp_CoSwitchCallContext
0x180009a42  test    rbx, rbx
0x180009a45  jz      short loc_180009A50
0x180009a47  mov     rcx, rbx; hObject
0x180009a4a  call    cs:__imp_CloseHandle
0x180009a50  mov     eax, edi
0x180009a52  mov     rcx, [rbp+57h+var_10]
0x180009a56  xor     rcx, rsp; StackCookie
0x180009a59  call    __security_check_cookie
0x180009a5e  lea     r11, [rsp+0C0h+var_s0]
0x180009a66  mov     rbx, [r11+10h]
0x180009a6a  mov     rsi, [r11+20h]
0x180009a6e  mov     rdi, [r11+28h]
0x180009a72  mov     rsp, r11
0x180009a75  pop     rbp
0x180009a76  retn
```
