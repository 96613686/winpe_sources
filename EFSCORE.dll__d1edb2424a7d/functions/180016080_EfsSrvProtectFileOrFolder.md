# EfsSrvProtectFileOrFolder

- ea: `0x180016080`
- end: `0x1800163f8`
- name: `EfsSrvProtectFileOrFolder`
- size: `888`
- prototype: `__int64 __fastcall(PCWSTR SourceString, PCWSTR)`
- caller_count: `0`
- callee_count: `12`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180005045`
- `0x180010bf0`
- `0x180016080`
- `0x180016588`
- `0x180016e58`
- `0x180017304`
- `0x1800254d4`
- `0x180025694`
- `0x180063698`
- `0x180063730`
- `0x1800637e8`
- `0x1800dca3c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016146`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016193`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016146`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016193`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180016189`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180016189`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180016171`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180016171`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1800161b9`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1800162d8`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1800163ad`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1800161b9`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1800162d8`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1800163ad`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800162e2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180016371`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800163b7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800162e2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180016371`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800163b7`
- `ntdll!RtlInitUnicodeString` at `0x1800161c6`
- `ntdll!RtlInitUnicodeString` at `0x1800162f7`
- `ntdll!RtlInitUnicodeString` at `0x1800161c6`
- `ntdll!RtlInitUnicodeString` at `0x1800162f7`
- `ntdll!RtlNtStatusToDosError` at `0x180016270`
- `ntdll!RtlNtStatusToDosError` at `0x180016270`

## pseudocode

```c
__int64 __fastcall EfsSrvProtectFileOrFolder(PCWSTR SourceString, PCWSTR a2)
{
  int v4; // r15d
  unsigned int v5; // ebx
  int v6; // r8d
  unsigned __int8 UserInfo; // al
  signed int LastError; // eax
  HANDLE CurrentThread; // rax
  signed int v10; // eax
  int v11; // ecx
  int VolumeRoot; // eax
  int v13; // ecx
  NTSTATUS LogFile; // eax
  __int64 v15; // rcx
  NTSTATUS v16; // r14d
  signed int v17; // eax
  int v18; // ecx
  int v19; // eax
  char v21; // [rsp+20h] [rbp-89h]
  LPVOID lpMem[2]; // [rsp+40h] [rbp-69h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+50h] [rbp-59h] BYREF
  struct _UNICODE_STRING v24; // [rsp+60h] [rbp-49h] BYREF
  _BYTE v25[144]; // [rsp+70h] [rbp-39h] BYREF
  void *TokenHandle; // [rsp+110h] [rbp+67h] BYREF
  HANDLE hObject; // [rsp+120h] [rbp+77h] BYREF

  TokenHandle = 0;
  memset_0(v25, 0, 0x70u);
  v4 = 0;
  hObject = 0;
  DestinationString = 0;
  *(_OWORD *)lpMem = 0;
  v24 = 0;
  if ( !SourceString )
  {
    v21 = -63;
LABEL_3:
    v5 = -2147024809;
    v6 = -2147024809;
LABEL_4:
    fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_TRACE_ERROR, v6, 4, v21);
    goto LABEL_31;
  }
  if ( !a2 )
  {
    v21 = -62;
    goto LABEL_3;
  }
  if ( !NtCurrentTeb()->IsImpersonating )
  {
    v5 = -2147023888;
    v21 = -54;
    v6 = -2147023888;
    goto LABEL_4;
  }
  UserInfo = EfsGetUserInfo((struct _EFS_USER_INFO *)v25);
  v4 = UserInfo;
  if ( !UserInfo )
  {
    LastError = GetLastError();
    v5 = LastError;
    if ( LastError > 0 )
      v5 = (unsigned __int16)LastError | 0x80070000;
    v21 = -43;
LABEL_13:
    v6 = v5;
    goto LABEL_4;
  }
  CurrentThread = GetCurrentThread();
  if ( !OpenThreadToken(CurrentThread, 4u, 1, &TokenHandle) )
  {
    v10 = GetLastError();
    v5 = v10;
    if ( v10 > 0 )
      v5 = (unsigned __int16)v10 | 0x80070000;
    v21 = -31;
    goto LABEL_13;
  }
  SetThreadToken(0, 0);
  RtlInitUnicodeString(&DestinationString, SourceString);
  fnEfsLogTrace1Strings(v11, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 4, 240);
  VolumeRoot = GetVolumeRoot(&DestinationString, lpMem);
  v5 = VolumeRoot;
  if ( VolumeRoot > 0 )
    v5 = (unsigned __int16)VolumeRoot | 0x80070000;
  if ( (int)fnEfsLogTrace1String1Dword(
              g_hPublisher,
              (unsigned int)EFS_TRACE_COMPLETE_EVENT,
              (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
              (unsigned int)&sourceString,
              v5,
              4,
              240) >= 0 )
  {
    fnEfsLogTrace1Strings(v13, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 4, 242);
    LogFile = GetLogFile(lpMem, &hObject);
    v5 = 0;
    v16 = LogFile;
    if ( LogFile < 0 )
    {
      v17 = RtlNtStatusToDosError(LogFile);
      v5 = v17;
      if ( v17 )
      {
        if ( v17 != 317 )
        {
          if ( v17 > 0 )
            v5 = (unsigned __int16)v17 | 0x80070000;
          goto LABEL_25;
        }
      }
      else
      {
        MicrosoftTelemetryAssertTriggeredNoArgs(v15);
      }
      v5 = v16 | 0x10000000;
    }
LABEL_25:
    if ( ((v5 ^ v16) & 0x80000000) != 0 )
      MicrosoftTelemetryAssertTriggeredNoArgs(v15);
    if ( (int)fnEfsLogTrace1String1Dword(
                g_hPublisher,
                (unsigned int)EFS_TRACE_COMPLETE_EVENT,
                (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
                (unsigned int)&sourceString,
                v5,
                4,
                242) >= 0 )
    {
      SetThreadToken(0, TokenHandle);
      CloseHandle(TokenHandle);
      TokenHandle = 0;
      RtlInitUnicodeString(&v24, a2);
      fnEfsLogTrace1Strings(v18, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 4, 6);
      v19 = EncryptFileSrv(v25, &DestinationString, &v24, hObject);
      v5 = v19;
      if ( v19 > 0 )
        v5 = (unsigned __int16)v19 | 0x80070000;
      fnEfsLogTrace1String1Dword(
        g_hPublisher,
        (unsigned int)EFS_TRACE_COMPLETE_EVENT,
        (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
        (unsigned int)&sourceString,
        v5,
        4,
        6);
    }
  }
LABEL_31:
  if ( hObject )
  {
    CloseHandle(hObject);
    hObject = 0;
  }
  if ( lpMem[1] )
  {
    EfsFreeHeap(lpMem[1]);
    *(_OWORD *)lpMem = 0;
  }
  if ( v4 )
    EfsFreeUserInfo(v25);
  if ( TokenHandle )
  {
    SetThreadToken(0, TokenHandle);
    CloseHandle(TokenHandle);
  }
  return v5;
}

```

## disassembly

```asm
0x180016080  mov     [rsp-8+arg_8], rbx
0x180016085  push    rbp
0x180016086  push    rdi
0x180016087  push    r12
0x180016089  push    r14
0x18001608b  push    r15
0x18001608d  lea     rbp, [rsp-37h]
0x180016092  sub     rsp, 0E0h
0x180016099  mov     r12, rdx
0x18001609c  mov     [rbp+57h+TokenHandle], 0
0x1800160a4  xor     edx, edx; Val
0x1800160a6  mov     rbx, rcx
0x1800160a9  lea     rcx, [rbp+57h+var_90]; void *
0x1800160ad  lea     r8d, [rdx+70h]; Size
0x1800160b1  call    memset_0
0x1800160b6  xor     r15d, r15d
0x1800160b9  xorps   xmm0, xmm0
0x1800160bc  mov     [rbp+57h+hObject], r15
0x1800160c0  xorps   xmm1, xmm1
0x1800160c3  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x1800160c7  movups  xmmword ptr [rbp+57h+lpMem], xmm1
0x1800160cb  movups  xmmword ptr [rbp+57h+var_A0.Length], xmm0
0x1800160cf  test    rbx, rbx
0x1800160d2  jnz     short loc_180016105
0x1800160d4  mov     dword ptr [rsp+100h+var_E0], 10C1h
0x1800160dc  mov     ebx, 80070057h
0x1800160e1  mov     r8d, 80070057h
0x1800160e7  mov     r9d, 4
0x1800160ed  mov     rcx, cs:g_hPublisher
0x1800160f4  lea     rdx, EFS_TRACE_ERROR
0x1800160fb  call    fnEfsLogTrace1
0x180016100  jmp     loc_180016368
0x180016105  test    r12, r12
0x180016108  jnz     short loc_180016114
0x18001610a  mov     dword ptr [rsp+100h+var_E0], 10C2h
0x180016112  jmp     short loc_1800160DC
0x180016114  mov     eax, gs:179Ch
0x18001611c  test    eax, eax
0x18001611e  jnz     short loc_180016135
0x180016120  mov     ebx, 800703F0h
0x180016125  mov     dword ptr [rsp+100h+var_E0], 10CAh
0x18001612d  mov     r8d, 800703F0h
0x180016133  jmp     short loc_1800160E7
0x180016135  lea     rcx, [rbp+57h+var_90]
0x180016139  call    EfsGetUserInfo
0x18001613e  movzx   r15d, al
0x180016142  test    al, al
0x180016144  jnz     short loc_180016171
0x180016146  call    cs:__imp_GetLastError
0x18001614c  mov     ebx, eax
0x18001614e  test    eax, eax
0x180016150  jle     short loc_18001615B
0x180016152  movzx   ebx, ax
0x180016155  or      ebx, 80070000h
0x18001615b  mov     dword ptr [rsp+100h+var_E0], 10D5h
0x180016163  mov     r9d, 4
0x180016169  mov     r8d, ebx
0x18001616c  jmp     loc_1800160ED
0x180016171  call    cs:__imp_GetCurrentThread
0x180016177  mov     edi, 4
0x18001617c  lea     r9, [rbp+57h+TokenHandle]; TokenHandle
0x180016180  mov     rcx, rax; ThreadHandle
0x180016183  mov     edx, edi; DesiredAccess
0x180016185  lea     r8d, [rdi-3]; OpenAsSelf
0x180016189  call    cs:__imp_OpenThreadToken
0x18001618f  test    eax, eax
0x180016191  jnz     short loc_1800161B5
0x180016193  call    cs:__imp_GetLastError
0x180016199  mov     ebx, eax
0x18001619b  test    eax, eax
0x18001619d  jle     short loc_1800161A8
0x18001619f  movzx   ebx, ax
0x1800161a2  or      ebx, 80070000h
0x1800161a8  mov     dword ptr [rsp+100h+var_E0], 10E1h
0x1800161b0  mov     r9d, edi
0x1800161b3  jmp     short loc_180016169
0x1800161b5  xor     edx, edx; Token
0x1800161b7  xor     ecx, ecx; Thread
0x1800161b9  call    cs:__imp_SetThreadToken
0x1800161bf  mov     rdx, rbx; SourceString
0x1800161c2  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x1800161c6  call    cs:__imp_RtlInitUnicodeString
0x1800161cc  lea     r14, sourceString
0x1800161d3  mov     dword ptr [rsp+100h+var_E0], 10F0h
0x1800161db  mov     r8, r14
0x1800161de  lea     rdx, EFS_TRACE_START_EVENT
0x1800161e5  mov     r9d, edi
0x1800161e8  call    fnEfsLogTrace1Strings
0x1800161ed  lea     rdx, [rbp+57h+lpMem]
0x1800161f1  lea     rcx, [rbp+57h+DestinationString]
0x1800161f5  call    GetVolumeRoot
0x1800161fa  mov     ebx, eax
0x1800161fc  test    eax, eax
0x1800161fe  jle     short loc_180016209
0x180016200  movzx   ebx, ax
0x180016203  or      ebx, 80070000h
0x180016209  mov     rcx, cs:g_hPublisher
0x180016210  lea     r8, EFS_TRACE_COMPLETE_EVENT_ERROR
0x180016217  mov     [rsp+100h+var_D0], 10F0h
0x18001621f  lea     rdx, EFS_TRACE_COMPLETE_EVENT
0x180016226  mov     [rsp+100h+var_D8], edi
0x18001622a  mov     r9, r14
0x18001622d  mov     dword ptr [rsp+100h+var_E0], ebx
0x180016231  call    fnEfsLogTrace1String1Dword
0x180016236  test    eax, eax
0x180016238  js      loc_180016368
0x18001623e  mov     r9d, edi
0x180016241  mov     dword ptr [rsp+100h+var_E0], 10F2h
0x180016249  mov     r8, r14
0x18001624c  lea     rdx, EFS_TRACE_START_EVENT
0x180016253  call    fnEfsLogTrace1Strings
0x180016258  lea     rdx, [rbp+57h+hObject]
0x18001625c  lea     rcx, [rbp+57h+lpMem]
0x180016260  call    GetLogFile
0x180016265  xor     ebx, ebx
0x180016267  mov     r14d, eax
0x18001626a  test    eax, eax
0x18001626c  jns     short loc_18001628C
0x18001626e  mov     ecx, eax; Status
0x180016270  call    cs:__imp_RtlNtStatusToDosError
0x180016276  mov     ebx, eax
0x180016278  test    eax, eax
0x18001627a  jnz     loc_1800163D7
0x180016280  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "dwError != ERROR_SUCCESS")
0x180016285  mov     ebx, r14d
0x180016288  bts     ebx, 1Ch
0x18001628c  xor     r14d, ebx
0x18001628f  jns     short loc_180016296
0x180016291  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "!!(SUCCEEDED(hr)) == !!(NT_SUCCESS(ntStatus))")
0x180016296  mov     rcx, cs:g_hPublisher
0x18001629d  lea     r14, sourceString
0x1800162a4  mov     [rsp+100h+var_D0], 10F2h
0x1800162ac  lea     r8, EFS_TRACE_COMPLETE_EVENT_ERROR
0x1800162b3  mov     r9, r14
0x1800162b6  mov     [rsp+100h+var_D8], edi
0x1800162ba  lea     rdx, EFS_TRACE_COMPLETE_EVENT
0x1800162c1  mov     dword ptr [rsp+100h+var_E0], ebx
0x1800162c5  call    fnEfsLogTrace1String1Dword
0x1800162ca  test    eax, eax
0x1800162cc  js      loc_180016368
0x1800162d2  mov     rdx, [rbp+57h+TokenHandle]; Token
0x1800162d6  xor     ecx, ecx; Thread
0x1800162d8  call    cs:__imp_SetThreadToken
0x1800162de  mov     rcx, [rbp+57h+TokenHandle]; hObject
0x1800162e2  call    cs:__imp_CloseHandle
0x1800162e8  mov     rdx, r12; SourceString
0x1800162eb  mov     [rbp+57h+TokenHandle], 0
0x1800162f3  lea     rcx, [rbp+57h+var_A0]; DestinationString
0x1800162f7  call    cs:__imp_RtlInitUnicodeString
0x1800162fd  mov     r12d, 1106h
0x180016303  lea     rdx, EFS_TRACE_START_EVENT
0x18001630a  mov     r9d, edi
0x18001630d  mov     dword ptr [rsp+100h+var_E0], r12d
0x180016312  mov     r8, r14
0x180016315  call    fnEfsLogTrace1Strings
0x18001631a  mov     r9, [rbp+57h+hObject]
0x18001631e  lea     r8, [rbp+57h+var_A0]
0x180016322  lea     rdx, [rbp+57h+DestinationString]
0x180016326  lea     rcx, [rbp+57h+var_90]
0x18001632a  call    EncryptFileSrv
0x18001632f  mov     ebx, eax
0x180016331  test    eax, eax
0x180016333  jle     short loc_18001633E
0x180016335  movzx   ebx, ax
0x180016338  or      ebx, 80070000h
0x18001633e  mov     rcx, cs:g_hPublisher
0x180016345  lea     r8, EFS_TRACE_COMPLETE_EVENT_ERROR
0x18001634c  mov     [rsp+100h+var_D0], r12d
0x180016351  lea     rdx, EFS_TRACE_COMPLETE_EVENT
0x180016358  mov     [rsp+100h+var_D8], edi
0x18001635c  mov     r9, r14
0x18001635f  mov     dword ptr [rsp+100h+var_E0], ebx
0x180016363  call    fnEfsLogTrace1String1Dword
0x180016368  mov     rcx, [rbp+57h+hObject]; hObject
0x18001636c  test    rcx, rcx
0x18001636f  jz      short loc_18001637F
0x180016371  call    cs:__imp_CloseHandle
0x180016377  mov     [rbp+57h+hObject], 0
0x18001637f  mov     rcx, [rbp+57h+lpMem+8]; lpMem
0x180016383  test    rcx, rcx
0x180016386  jz      short loc_180016394
0x180016388  call    EfsFreeHeap
0x18001638d  xorps   xmm0, xmm0
0x180016390  movups  xmmword ptr [rbp+57h+lpMem], xmm0
0x180016394  test    r15d, r15d
0x180016397  jz      short loc_1800163A2
0x180016399  lea     rcx, [rbp+57h+var_90]
0x18001639d  call    EfsFreeUserInfo
0x1800163a2  mov     rdx, [rbp+57h+TokenHandle]; Token
0x1800163a6  test    rdx, rdx
0x1800163a9  jz      short loc_1800163BD
0x1800163ab  xor     ecx, ecx; Thread
0x1800163ad  call    cs:__imp_SetThreadToken
0x1800163b3  mov     rcx, [rbp+57h+TokenHandle]; hObject
0x1800163b7  call    cs:__imp_CloseHandle
0x1800163bd  mov     eax, ebx
0x1800163bf  mov     rbx, [rsp+100h+arg_8]
0x1800163c7  add     rsp, 0E0h
0x1800163ce  pop     r15
0x1800163d0  pop     r14
0x1800163d2  pop     r12
0x1800163d4  pop     rdi
0x1800163d5  pop     rbp
0x1800163d6  retn
0x1800163d7  cmp     eax, 13Dh
0x1800163dc  jz      loc_180016285
0x1800163e2  test    eax, eax
0x1800163e4  jle     loc_18001628C
0x1800163ea  movzx   ebx, ax
0x1800163ed  or      ebx, 80070000h
0x1800163f3  jmp     loc_18001628C
```
