# PCPStorageProvider::GetCallerToken(ulong,void * *)

- ea: `0x1800223c0`
- end: `0x1800224fb`
- name: `?GetCallerToken@PCPStorageProvider@@QEAAJKPEAPEAX@Z`
- size: `315`
- prototype: `__int64 __fastcall(PCPStorageProvider *this, __int64, void **)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x1800222b4`

## callees

- `0x180015660`
- `0x1800157c0`
- `0x1800223c0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022427`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800224b8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022427`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800224b8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180022456`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180022456`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180022417`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180022417`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800223fa`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800223fa`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18002246f`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18002246f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800224da`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800224da`

## string_xrefs

- `0x1800223e1`: `PCPStorageProvider::GetCallerToken`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall PCPStorageProvider::GetCallerToken(PCPStorageProvider *this, __int64 a2, void **a3)
{
  HANDLE CurrentThread; // rax
  signed int LastError; // eax
  unsigned int v6; // ebx
  HANDLE CurrentProcess; // rax
  void *v8; // rcx
  signed int v10; // eax
  _BYTE v11[40]; // [rsp+20h] [rbp-28h] BYREF
  void *TokenHandle; // [rsp+50h] [rbp+8h] BYREF
  unsigned int v13; // [rsp+58h] [rbp+10h] BYREF

  TokenHandle = this;
  v13 = -2146893792;
  KspFunctionLogger::KspFunctionLogger(
    (KspFunctionLogger *)v11,
    L"PCPStorageProvider::GetCallerToken",
    (const int *)&v13);
  TokenHandle = 0;
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 0xAu, 1, &TokenHandle) )
    goto LABEL_6;
  LastError = GetLastError();
  v6 = LastError;
  if ( LastError > 0 )
    v6 = (unsigned __int16)LastError | 0x80070000;
  v13 = v6;
  if ( v6 == -2147023888 )
  {
    v13 = 0;
    CurrentProcess = GetCurrentProcess();
    if ( !OpenProcessToken(CurrentProcess, 0xAu, &TokenHandle) )
    {
      v10 = GetLastError();
      v6 = v10;
      if ( v10 > 0 )
        v6 = (unsigned __int16)v10 | 0x80070000;
      v8 = TokenHandle;
      goto LABEL_7;
    }
LABEL_6:
    v6 = 0;
    *a3 = TokenHandle;
    v8 = 0;
    TokenHandle = 0;
LABEL_7:
    v13 = v6;
    goto LABEL_8;
  }
  v8 = TokenHandle;
LABEL_8:
  if ( v8 )
  {
    CloseHandle(v8);
    TokenHandle = 0;
    v6 = v13;
  }
  KspFunctionLogger::~KspFunctionLogger((KspFunctionLogger *)v11);
  return v6;
}

```

## disassembly

```asm
0x1800223c0  mov     rax, rsp
0x1800223c3  mov     [rax+18h], rbx
0x1800223c7  mov     [rax+10h], edx
0x1800223ca  mov     [rax+8], rcx
0x1800223ce  push    rdi
0x1800223cf  sub     rsp, 40h
0x1800223d3  mov     rdi, r8
0x1800223d6  mov     dword ptr [rax+10h], 80090020h
0x1800223dd  lea     r8, [rax+10h]; int *
0x1800223e1  lea     rdx, aPcpstorageprov; "PCPStorageProvider::GetCallerToken"
0x1800223e8  lea     rcx, [rax-28h]; this
0x1800223ec  call    ??0KspFunctionLogger@@QEAA@QEBGAEBJ@Z; KspFunctionLogger::KspFunctionLogger(ushort const * const,long const &)
0x1800223f1  mov     [rsp+48h+TokenHandle], 0
0x1800223fa  call    cs:__imp_GetCurrentThread
0x180022401  nop     dword ptr [rax+rax+00h]
0x180022406  mov     rcx, rax; ThreadHandle
0x180022409  lea     r9, [rsp+48h+TokenHandle]; TokenHandle
0x18002240e  mov     edx, 0Ah; DesiredAccess
0x180022413  lea     r8d, [rdx-9]; OpenAsSelf
0x180022417  call    cs:__imp_OpenThreadToken
0x18002241e  nop     dword ptr [rax+rax+00h]
0x180022423  test    eax, eax
0x180022425  jnz     short loc_18002247F
0x180022427  call    cs:__imp_GetLastError
0x18002242e  nop     dword ptr [rax+rax+00h]
0x180022433  mov     ebx, eax
0x180022435  test    eax, eax
0x180022437  jle     short loc_180022442
0x180022439  movzx   ebx, ax
0x18002243c  or      ebx, 80070000h
0x180022442  mov     [rsp+48h+arg_8], ebx
0x180022446  cmp     ebx, 800703F0h
0x18002244c  jnz     short loc_1800224B1
0x18002244e  mov     [rsp+48h+arg_8], 0
0x180022456  call    cs:__imp_GetCurrentProcess
0x18002245d  nop     dword ptr [rax+rax+00h]
0x180022462  mov     rcx, rax; ProcessHandle
0x180022465  lea     r8, [rsp+48h+TokenHandle]; TokenHandle
0x18002246a  mov     edx, 0Ah; DesiredAccess
0x18002246f  call    cs:__imp_OpenProcessToken
0x180022476  nop     dword ptr [rax+rax+00h]
0x18002247b  test    eax, eax
0x18002247d  jz      short loc_1800224B8
0x18002247f  xor     ebx, ebx
0x180022481  mov     rax, [rsp+48h+TokenHandle]
0x180022486  mov     [rdi], rax
0x180022489  xor     ecx, ecx; hObject
0x18002248b  mov     [rsp+48h+TokenHandle], rcx
0x180022490  mov     [rsp+48h+arg_8], ebx
0x180022494  test    rcx, rcx
0x180022497  jnz     short loc_1800224DA
0x180022499  lea     rcx, [rsp+48h+var_28]; this
0x18002249e  call    ??1KspFunctionLogger@@QEAA@XZ; KspFunctionLogger::~KspFunctionLogger(void)
0x1800224a3  mov     eax, ebx
0x1800224a5  mov     rbx, [rsp+48h+arg_10]
0x1800224aa  add     rsp, 40h
0x1800224ae  pop     rdi
0x1800224af  retn
0x1800224b1  mov     rcx, [rsp+48h+TokenHandle]
0x1800224b6  jmp     short loc_180022494
0x1800224b8  call    cs:__imp_GetLastError
0x1800224bf  nop     dword ptr [rax+rax+00h]
0x1800224c4  mov     ebx, eax
0x1800224c6  test    eax, eax
0x1800224c8  jle     short loc_1800224D3
0x1800224ca  movzx   ebx, ax
0x1800224cd  or      ebx, 80070000h
0x1800224d3  mov     rcx, [rsp+48h+TokenHandle]
0x1800224d8  jmp     short loc_180022490
0x1800224da  call    cs:__imp_CloseHandle
0x1800224e1  nop     dword ptr [rax+rax+00h]
0x1800224e6  mov     [rsp+48h+TokenHandle], 0
0x1800224ef  mov     ebx, [rsp+48h+arg_8]
0x1800224f3  jmp     short loc_180022499
0x1800224f5  mov     eax, [rsp+48h+arg_8]
0x1800224f9  jmp     short loc_1800224A5
```
