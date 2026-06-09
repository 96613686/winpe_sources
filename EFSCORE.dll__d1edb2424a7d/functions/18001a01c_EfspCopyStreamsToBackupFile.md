# EfspCopyStreamsToBackupFile

- ea: `0x18001a01c`
- end: `0x18001a207`
- name: `EfspCopyStreamsToBackupFile`
- size: `491`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18001b61c`
- `0x18001c22c`

## callees

- `0x180019598`
- `0x18001a01c`
- `0x180063698`
- `0x180066828`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a07b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a0c7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a1b2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a07b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a0c7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a1b2`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18001a071`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18001a071`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001a057`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001a057`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18001a1a8`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18001a1a8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001a1e9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001a1e9`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18001a0b8`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18001a0b8`
- `ntdll!NtFsControlFile` at `0x18001a113`
- `ntdll!NtFsControlFile` at `0x18001a113`

## pseudocode

```c
__int64 __fastcall EfspCopyStreamsToBackupFile(__int64 a1, void *a2, __int64 a3, __int64 a4, _BYTE *a5, int a6)
{
  _BYTE *v6; // rsi
  HANDLE CurrentThread; // rax
  DWORD LastError; // eax
  unsigned int v12; // ebx
  char v13; // si
  int v14; // eax
  NTSTATUS v15; // eax
  unsigned int v16; // ebx
  bool v17; // cf
  unsigned int v18; // eax
  DWORD v19; // eax
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+50h] [rbp-28h] BYREF
  void *TokenHandle; // [rsp+80h] [rbp+8h] BYREF

  v6 = a5;
  TokenHandle = 0;
  IoStatusBlock = 0;
  *a5 = 0;
  CurrentThread = GetCurrentThread();
  if ( !OpenThreadToken(CurrentThread, 0xCu, 1, &TokenHandle) )
  {
    LastError = GetLastError();
    v12 = LastError;
    v13 = -110;
LABEL_3:
    v14 = fnEfsLogTrace1(g_hPublisher, (unsigned int)&EFS_API_ERROR, LastError, 10, v13);
    fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_TRACE_ERROR, v14, 10, v13);
    goto LABEL_13;
  }
  if ( !RevertToSelf() )
  {
    v12 = 1008;
    LastError = GetLastError();
    v13 = -98;
    goto LABEL_3;
  }
  v15 = NtFsControlFile(a2, 0, 0, 0, &IoStatusBlock, 0x90194u, 0, 0, 0, 0);
  v16 = v15;
  if ( v15 >= 0
    || (fnEfsLogTrace1(g_hPublisher, (unsigned int)&EFS_API_ERROR, v15, 10, 175),
        v17 = a6 != 0,
        a6 = -a6,
        (v12 = EfspMapError(v16, (unsigned int)v17 + 6000)) == 0) )
  {
    v18 = EfspCopyFile(a3, a2, a4);
    v12 = v18;
    if ( v18 )
      fnEfsLogTrace1(g_hPublisher, (unsigned int)&EFS_API_ERROR, v18, 10, 187);
    else
      *v6 = 1;
  }
  if ( !SetThreadToken(0, TokenHandle) )
  {
    v19 = GetLastError();
    fnEfsLogTrace1(g_hPublisher, (unsigned int)&EFS_API_ERROR, v19, 10, 202);
  }
LABEL_13:
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  return v12;
}

```

## disassembly

```asm
0x18001a01c  mov     rax, rsp
0x18001a01f  mov     [rax+10h], rbx
0x18001a023  mov     [rax+18h], rbp
0x18001a027  mov     [rax+8], rcx
0x18001a02b  push    rsi
0x18001a02c  push    r14
0x18001a02e  push    r15
0x18001a030  sub     rsp, 60h
0x18001a034  mov     rsi, [rsp+78h+arg_20]
0x18001a03c  xorps   xmm0, xmm0
0x18001a03f  mov     r14, r9
0x18001a042  mov     qword ptr [rax+8], 0
0x18001a04a  mov     r15, r8
0x18001a04d  mov     rbp, rdx
0x18001a050  movups  xmmword ptr [rax-28h], xmm0
0x18001a054  mov     byte ptr [rsi], 0
0x18001a057  call    cs:__imp_GetCurrentThread
0x18001a05d  mov     edx, 0Ch; DesiredAccess
0x18001a062  lea     r9, [rsp+78h+TokenHandle]; TokenHandle
0x18001a06a  mov     rcx, rax; ThreadHandle
0x18001a06d  lea     r8d, [rdx-0Bh]; OpenAsSelf
0x18001a071  call    cs:__imp_OpenThreadToken
0x18001a077  test    eax, eax
0x18001a079  jnz     short loc_18001A0B8
0x18001a07b  call    cs:__imp_GetLastError
0x18001a081  mov     ebx, eax
0x18001a083  mov     esi, 792h
0x18001a088  mov     rcx, cs:g_hPublisher
0x18001a08f  lea     rdx, EFS_API_ERROR
0x18001a096  mov     r9d, 0Ah
0x18001a09c  mov     dword ptr [rsp+78h+IoStatusBlock], esi
0x18001a0a0  mov     r8d, eax
0x18001a0a3  call    fnEfsLogTrace1
0x18001a0a8  lea     rdx, EFS_TRACE_ERROR
0x18001a0af  mov     dword ptr [rsp+78h+IoStatusBlock], esi
0x18001a0b3  jmp     loc_18001A1C7
0x18001a0b8  call    cs:__imp_RevertToSelf
0x18001a0be  test    eax, eax
0x18001a0c0  jnz     short loc_18001A0D4
0x18001a0c2  mov     ebx, 3F0h
0x18001a0c7  call    cs:__imp_GetLastError
0x18001a0cd  mov     esi, 79Eh
0x18001a0d2  jmp     short loc_18001A088
0x18001a0d4  mov     [rsp+78h+OutputBufferLength], 0; OutputBufferLength
0x18001a0dc  lea     rax, [rsp+78h+var_28]
0x18001a0e1  mov     [rsp+78h+OutputBuffer], 0; OutputBuffer
0x18001a0ea  xor     r9d, r9d; ApcContext
0x18001a0ed  mov     [rsp+78h+InputBufferLength], 0; InputBufferLength
0x18001a0f5  xor     r8d, r8d; ApcRoutine
0x18001a0f8  mov     [rsp+78h+InputBuffer], 0; InputBuffer
0x18001a101  xor     edx, edx; Event
0x18001a103  mov     [rsp+78h+FsControlCode], 90194h; FsControlCode
0x18001a10b  mov     rcx, rbp; FileHandle
0x18001a10e  mov     [rsp+78h+IoStatusBlock], rax; IoStatusBlock
0x18001a113  call    cs:__imp_NtFsControlFile
0x18001a119  mov     ebx, eax
0x18001a11b  test    eax, eax
0x18001a11d  jns     short loc_18001A161
0x18001a11f  mov     rcx, cs:g_hPublisher
0x18001a126  lea     rdx, EFS_API_ERROR
0x18001a12d  mov     r9d, 0Ah
0x18001a133  mov     dword ptr [rsp+78h+IoStatusBlock], 7AFh
0x18001a13b  mov     r8d, eax
0x18001a13e  call    fnEfsLogTrace1
0x18001a143  neg     [rsp+78h+arg_28]
0x18001a14a  mov     ecx, ebx
0x18001a14c  sbb     edx, edx
0x18001a14e  neg     edx
0x18001a150  add     edx, 1770h
0x18001a156  call    EfspMapError
0x18001a15b  mov     ebx, eax
0x18001a15d  test    eax, eax
0x18001a15f  jnz     short loc_18001A19E
0x18001a161  mov     r8, r14
0x18001a164  mov     rdx, rbp
0x18001a167  mov     rcx, r15
0x18001a16a  call    EfspCopyFile
0x18001a16f  mov     ebx, eax
0x18001a171  test    eax, eax
0x18001a173  jz      short loc_18001A19B
0x18001a175  mov     rcx, cs:g_hPublisher
0x18001a17c  lea     rdx, EFS_API_ERROR
0x18001a183  mov     r9d, 0Ah
0x18001a189  mov     dword ptr [rsp+78h+IoStatusBlock], 7BBh
0x18001a191  mov     r8d, eax
0x18001a194  call    fnEfsLogTrace1
0x18001a199  jmp     short loc_18001A19E
0x18001a19b  mov     byte ptr [rsi], 1
0x18001a19e  mov     rdx, [rsp+78h+TokenHandle]; Token
0x18001a1a6  xor     ecx, ecx; Thread
0x18001a1a8  call    cs:__imp_SetThreadToken
0x18001a1ae  test    eax, eax
0x18001a1b0  jnz     short loc_18001A1DC
0x18001a1b2  call    cs:__imp_GetLastError
0x18001a1b8  lea     rdx, EFS_API_ERROR
0x18001a1bf  mov     dword ptr [rsp+78h+IoStatusBlock], 7CAh
0x18001a1c7  mov     rcx, cs:g_hPublisher
0x18001a1ce  mov     r9d, 0Ah
0x18001a1d4  mov     r8d, eax
0x18001a1d7  call    fnEfsLogTrace1
0x18001a1dc  mov     rcx, [rsp+78h+TokenHandle]; hObject
0x18001a1e4  test    rcx, rcx
0x18001a1e7  jz      short loc_18001A1EF
0x18001a1e9  call    cs:__imp_CloseHandle
0x18001a1ef  lea     r11, [rsp+78h+var_18]
0x18001a1f4  mov     eax, ebx
0x18001a1f6  mov     rbx, [r11+28h]
0x18001a1fa  mov     rbp, [r11+30h]
0x18001a1fe  mov     rsp, r11
0x18001a201  pop     r15
0x18001a203  pop     r14
0x18001a205  pop     rsi
0x18001a206  retn
```
