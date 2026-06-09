# WicIsProcessAppContainer

- ea: `0x180062a44`
- end: `0x180062bea`
- name: `WicIsProcessAppContainer`
- size: `422`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180062718`

## callees

- `0x180062a44`
- `0x1800635f4`
- `0x1800bd9d4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180062b90`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180062b90`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180062a5a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180062b13`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180062a5a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180062b13`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180062bad`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180062bad`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180062ae0`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180062bd4`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180062ae0`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180062bd4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180062ab1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180062af0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180062b6c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180062ab1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180062af0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180062b6c`

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
0x180062a44  mov     [rsp+arg_0], rbx
0x180062a49  push    rdi
0x180062a4a  sub     rsp, 20h
0x180062a4e  mov     rdi, rcx
0x180062a51  mov     [rsp+28h+TokenHandle], 0
0x180062a5a  call    cs:__imp_GetCurrentProcess
0x180062a61  nop     dword ptr [rax+rax+00h]
0x180062a66  mov     rcx, rax; this
0x180062a69  mov     rdx, rdi; void *
0x180062a6c  call    ?IsProcessAppContainer@CallerIdentity@@YAJPEAXPEA_N@Z; CallerIdentity::IsProcessAppContainer(void *,bool *)
0x180062a71  mov     ebx, eax
0x180062a73  cmp     eax, 80070005h
0x180062a78  jz      loc_180062B90
0x180062a7e  mov     eax, cs:?g_doStackCaptures@@3HA; int g_doStackCaptures
0x180062a84  test    ebx, ebx
0x180062a86  js      short loc_180062AA4
0x180062a88  mov     rdx, [rsp+28h+TokenHandle]; Token
0x180062a8d  test    rdx, rdx
0x180062a90  jnz     loc_180062BD2
0x180062a96  mov     eax, ebx
0x180062a98  mov     rbx, [rsp+28h+arg_0]
0x180062a9d  add     rsp, 20h
0x180062aa1  pop     rdi
0x180062aa2  retn
0x180062aa4  test    eax, eax
0x180062aa6  jz      short loc_180062A88
0x180062aa8  mov     ecx, ebx; int
0x180062aaa  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x180062aaf  jmp     short loc_180062A88
0x180062ab1  call    cs:__imp_GetLastError
0x180062ab8  nop     dword ptr [rax+rax+00h]
0x180062abd  mov     ebx, eax
0x180062abf  test    eax, eax
0x180062ac1  jle     short loc_180062ACC
0x180062ac3  movzx   ebx, ax
0x180062ac6  or      ebx, 80070000h
0x180062acc  cmp     ebx, 800703F0h
0x180062ad2  jz      short loc_180062B4F
0x180062ad4  test    ebx, ebx
0x180062ad6  js      loc_180062BC6
0x180062adc  xor     edx, edx; Token
0x180062ade  xor     ecx, ecx; Thread
0x180062ae0  call    cs:__imp_SetThreadToken
0x180062ae7  nop     dword ptr [rax+rax+00h]
0x180062aec  test    eax, eax
0x180062aee  jnz     short loc_180062B13
0x180062af0  call    cs:__imp_GetLastError
0x180062af7  nop     dword ptr [rax+rax+00h]
0x180062afc  mov     ebx, eax
0x180062afe  test    eax, eax
0x180062b00  jle     short loc_180062B0B
0x180062b02  movzx   ebx, ax
0x180062b05  or      ebx, 80070000h
0x180062b0b  test    ebx, ebx
0x180062b0d  js      loc_180062BC6
0x180062b13  call    cs:__imp_GetCurrentProcess
0x180062b1a  nop     dword ptr [rax+rax+00h]
0x180062b1f  mov     rcx, rax; this
0x180062b22  mov     rdx, rdi; void *
0x180062b25  call    ?IsProcessAppContainer@CallerIdentity@@YAJPEAXPEA_N@Z; CallerIdentity::IsProcessAppContainer(void *,bool *)
0x180062b2a  mov     ebx, eax
0x180062b2c  mov     eax, cs:?g_doStackCaptures@@3HA; int g_doStackCaptures
0x180062b32  test    ebx, ebx
0x180062b34  jns     loc_180062A88
0x180062b3a  test    eax, eax
0x180062b3c  jnz     loc_180062AA8
0x180062b42  test    ebx, ebx
0x180062b44  js      loc_180062A88
0x180062b4a  jmp     loc_180062A84
0x180062b4f  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x180062b56  jz      short loc_180062B62
0x180062b58  mov     ecx, 80070005h; int
0x180062b5d  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x180062b62  mov     ebx, 80070005h
0x180062b67  jmp     loc_180062A88
0x180062b6c  call    cs:__imp_GetLastError
0x180062b73  nop     dword ptr [rax+rax+00h]
0x180062b78  mov     ebx, eax
0x180062b7a  test    eax, eax
0x180062b7c  jle     loc_180062A96
0x180062b82  movzx   ebx, ax
0x180062b85  or      ebx, 80070000h
0x180062b8b  jmp     loc_180062A96
0x180062b90  call    cs:__imp_GetCurrentThread
0x180062b97  nop     dword ptr [rax+rax+00h]
0x180062b9c  mov     edx, 4; DesiredAccess
0x180062ba1  lea     r9, [rsp+28h+TokenHandle]; TokenHandle
0x180062ba6  mov     rcx, rax; ThreadHandle
0x180062ba9  lea     r8d, [rdx-3]; OpenAsSelf
0x180062bad  call    cs:__imp_OpenThreadToken
0x180062bb4  nop     dword ptr [rax+rax+00h]
0x180062bb9  test    eax, eax
0x180062bbb  jnz     loc_180062ADC
0x180062bc1  jmp     loc_180062AB1
0x180062bc6  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x180062bcd  jmp     loc_180062AA6
0x180062bd2  xor     ecx, ecx; Thread
0x180062bd4  call    cs:__imp_SetThreadToken
0x180062bdb  nop     dword ptr [rax+rax+00h]
0x180062be0  test    eax, eax
0x180062be2  jnz     loc_180062A96
0x180062be8  jmp     short loc_180062B6C
```
