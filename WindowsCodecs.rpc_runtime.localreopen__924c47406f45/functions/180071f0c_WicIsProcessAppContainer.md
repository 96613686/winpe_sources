# WicIsProcessAppContainer

- ea: `0x180071f0c`
- end: `0x180072077`
- name: `WicIsProcessAppContainer`
- size: `363`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180071c14`

## callees

- `0x180071f0c`
- `0x1800721e0`
- `0x1800bb784`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18007202f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18007202f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180071f22`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180071fc2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180071f22`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180071fc2`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180072046`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180072046`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180071f9b`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180072067`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180071f9b`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180072067`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180071f72`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180071fa5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180072011`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180071f72`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180071fa5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180072011`

## pseudocode

```c
__int64 __fastcall WicIsProcessAppContainer(void *a1)
{
  CallerIdentity *CurrentProcess; // rax
  bool *v3; // r8
  signed int IsProcessAppContainer; // ebx
  bool v6; // zf
  signed int LastError; // eax
  signed int v8; // eax
  CallerIdentity *v9; // rax
  bool *v10; // r8
  signed int v11; // eax
  HANDLE CurrentThread; // rax
  void *TokenHandle; // [rsp+38h] [rbp+10h] BYREF

  TokenHandle = 0;
  CurrentProcess = (CallerIdentity *)GetCurrentProcess();
  IsProcessAppContainer = CallerIdentity::IsProcessAppContainer(CurrentProcess, a1, v3);
  if ( IsProcessAppContainer != -2147024891 )
  {
    if ( IsProcessAppContainer >= 0 )
      goto LABEL_3;
    v6 = (_DWORD)g_doStackCaptures == 0;
    goto LABEL_6;
  }
  CurrentThread = GetCurrentThread();
  if ( !OpenThreadToken(CurrentThread, 4u, 1, &TokenHandle) )
  {
    LastError = GetLastError();
    IsProcessAppContainer = LastError;
    if ( LastError > 0 )
      IsProcessAppContainer = (unsigned __int16)LastError | 0x80070000;
    if ( IsProcessAppContainer == -2147023888 )
    {
      if ( (_DWORD)g_doStackCaptures )
        DoStackCapture(-2147024891);
      IsProcessAppContainer = -2147024891;
      goto LABEL_3;
    }
    if ( IsProcessAppContainer < 0 )
      goto LABEL_26;
  }
  if ( !SetThreadToken(0, 0) )
  {
    v8 = GetLastError();
    IsProcessAppContainer = v8;
    if ( v8 > 0 )
      IsProcessAppContainer = (unsigned __int16)v8 | 0x80070000;
    if ( IsProcessAppContainer < 0 )
    {
LABEL_26:
      v6 = (_DWORD)g_doStackCaptures == 0;
LABEL_6:
      if ( v6 )
        goto LABEL_3;
LABEL_7:
      DoStackCapture(IsProcessAppContainer);
      goto LABEL_3;
    }
  }
  v9 = (CallerIdentity *)GetCurrentProcess();
  IsProcessAppContainer = CallerIdentity::IsProcessAppContainer(v9, a1, v10);
  if ( IsProcessAppContainer < 0 && (_DWORD)g_doStackCaptures )
    goto LABEL_7;
LABEL_3:
  if ( TokenHandle )
  {
    if ( !SetThreadToken(0, TokenHandle) )
    {
      v11 = GetLastError();
      IsProcessAppContainer = v11;
      if ( v11 > 0 )
        return (unsigned __int16)v11 | 0x80070000;
    }
  }
  return (unsigned int)IsProcessAppContainer;
}

```

## disassembly

```asm
0x180071f0c  mov     [rsp+arg_0], rbx
0x180071f11  push    rdi
0x180071f12  sub     rsp, 20h
0x180071f16  mov     rdi, rcx
0x180071f19  mov     [rsp+28h+TokenHandle], 0
0x180071f22  call    cs:__imp_GetCurrentProcess
0x180071f28  mov     rcx, rax; this
0x180071f2b  mov     rdx, rdi; void *
0x180071f2e  call    ?IsProcessAppContainer@CallerIdentity@@YAJPEAXPEA_N@Z; CallerIdentity::IsProcessAppContainer(void *,bool *)
0x180071f33  mov     ebx, eax
0x180071f35  cmp     eax, 80070005h
0x180071f3a  jz      loc_18007202F
0x180071f40  mov     eax, cs:?g_doStackCaptures@@3HA; int g_doStackCaptures
0x180071f46  test    ebx, ebx
0x180071f48  js      short loc_180071F65
0x180071f4a  mov     rdx, [rsp+28h+TokenHandle]; Token
0x180071f4f  test    rdx, rdx
0x180071f52  jnz     loc_180072065
0x180071f58  mov     eax, ebx
0x180071f5a  mov     rbx, [rsp+28h+arg_0]
0x180071f5f  add     rsp, 20h
0x180071f63  pop     rdi
0x180071f64  retn
0x180071f65  test    eax, eax
0x180071f67  jz      short loc_180071F4A
0x180071f69  mov     ecx, ebx; int
0x180071f6b  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x180071f70  jmp     short loc_180071F4A
0x180071f72  call    cs:__imp_GetLastError
0x180071f78  mov     ebx, eax
0x180071f7a  test    eax, eax
0x180071f7c  jle     short loc_180071F87
0x180071f7e  movzx   ebx, ax
0x180071f81  or      ebx, 80070000h
0x180071f87  cmp     ebx, 800703F0h
0x180071f8d  jz      short loc_180071FF4
0x180071f8f  test    ebx, ebx
0x180071f91  js      loc_180072059
0x180071f97  xor     edx, edx; Token
0x180071f99  xor     ecx, ecx; Thread
0x180071f9b  call    cs:__imp_SetThreadToken
0x180071fa1  test    eax, eax
0x180071fa3  jnz     short loc_180071FC2
0x180071fa5  call    cs:__imp_GetLastError
0x180071fab  mov     ebx, eax
0x180071fad  test    eax, eax
0x180071faf  jle     short loc_180071FBA
0x180071fb1  movzx   ebx, ax
0x180071fb4  or      ebx, 80070000h
0x180071fba  test    ebx, ebx
0x180071fbc  js      loc_180072059
0x180071fc2  call    cs:__imp_GetCurrentProcess
0x180071fc8  mov     rcx, rax; this
0x180071fcb  mov     rdx, rdi; void *
0x180071fce  call    ?IsProcessAppContainer@CallerIdentity@@YAJPEAXPEA_N@Z; CallerIdentity::IsProcessAppContainer(void *,bool *)
0x180071fd3  mov     ebx, eax
0x180071fd5  mov     eax, cs:?g_doStackCaptures@@3HA; int g_doStackCaptures
0x180071fdb  test    ebx, ebx
0x180071fdd  jns     loc_180071F4A
0x180071fe3  test    eax, eax
0x180071fe5  jnz     short loc_180071F69
0x180071fe7  test    ebx, ebx
0x180071fe9  js      loc_180071F4A
0x180071fef  jmp     loc_180071F46
0x180071ff4  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x180071ffb  jz      short loc_180072007
0x180071ffd  mov     ecx, 80070005h; int
0x180072002  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x180072007  mov     ebx, 80070005h
0x18007200c  jmp     loc_180071F4A
0x180072011  call    cs:__imp_GetLastError
0x180072017  mov     ebx, eax
0x180072019  test    eax, eax
0x18007201b  jle     loc_180071F58
0x180072021  movzx   ebx, ax
0x180072024  or      ebx, 80070000h
0x18007202a  jmp     loc_180071F58
0x18007202f  call    cs:__imp_GetCurrentThread
0x180072035  mov     edx, 4; DesiredAccess
0x18007203a  lea     r9, [rsp+28h+TokenHandle]; TokenHandle
0x18007203f  mov     rcx, rax; ThreadHandle
0x180072042  lea     r8d, [rdx-3]; OpenAsSelf
0x180072046  call    cs:__imp_OpenThreadToken
0x18007204c  test    eax, eax
0x18007204e  jnz     loc_180071F97
0x180072054  jmp     loc_180071F72
0x180072059  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x180072060  jmp     loc_180071F67
0x180072065  xor     ecx, ecx; Thread
0x180072067  call    cs:__imp_SetThreadToken
0x18007206d  test    eax, eax
0x18007206f  jnz     loc_180071F58
0x180072075  jmp     short loc_180072011
```
