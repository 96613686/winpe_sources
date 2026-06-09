# pSpSignIsDriverFileBlocked

- ea: `0x14002f244`
- end: `0x14002f3ef`
- name: `pSpSignIsDriverFileBlocked`
- size: `427`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName, HANDLE TokenHandle)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x14002f084`

## callees

- `0x14000bcbc`
- `0x14002f244`
- `0x140030008`
- `0x1400301e4`
- `0x140035320`
- `0x140036448`
- `0x140045f30`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002f2c9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002f2c9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14002f3c0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14002f3c0`
- `api-ms-win-core-processthreads-l1-1-1!IsProcessorFeaturePresent` at `0x14002f337`
- `api-ms-win-core-processthreads-l1-1-1!IsProcessorFeaturePresent` at `0x14002f337`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x14002f3a3`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x14002f3a3`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x14002f2ba`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x14002f2ba`
- `DEVRTL!DevRtlWriteTextLog` at `0x14002f360`
- `DEVRTL!DevRtlWriteTextLog` at `0x14002f360`
- `DEVRTL!DevRtlGetThreadLogToken` at `0x14002f291`
- `DEVRTL!DevRtlGetThreadLogToken` at `0x14002f291`

## string_xrefs

- `0x14002f341`: `An incompatible driver %ls was blocked`

## pseudocode

```c
__int64 __fastcall pSpSignIsDriverFileBlocked(LPCWSTR lpFileName, HANDLE TokenHandle, __int64 a3)
{
  unsigned int v3; // ebx
  __int64 ThreadLogToken; // r13
  HANDLE FileW; // rsi
  __int64 FileTitle; // rax
  __int64 v10; // r8
  unsigned int DatabaseMatch; // r14d
  int v13; // [rsp+40h] [rbp-40h] BYREF
  unsigned int v14; // [rsp+44h] [rbp-3Ch] BYREF
  int v15; // [rsp+48h] [rbp-38h] BYREF
  int v16; // [rsp+4Ch] [rbp-34h] BYREF
  DWORD ReturnLength; // [rsp+50h] [rbp-30h] BYREF
  int TokenInformation; // [rsp+54h] [rbp-2Ch] BYREF
  __int64 v19; // [rsp+58h] [rbp-28h] BYREF
  GUID v20; // [rsp+60h] [rbp-20h] BYREF

  v3 = 0;
  v16 = 0;
  v13 = 0;
  v20 = 0;
  v14 = 0;
  v19 = 0;
  TokenInformation = 0;
  ReturnLength = 0;
  ThreadLogToken = DevRtlGetThreadLogToken();
  FileW = CreateFileW(lpFileName, 0x80000000, 1u, 0, 3u, 0, 0);
  if ( FileW == (HANDLE)-1LL )
  {
    return GetLastError();
  }
  else
  {
    FileTitle = pSetupGetFileTitle(lpFileName);
    DatabaseMatch = SdbGetDatabaseMatch(a3, FileTitle, FileW);
    if ( DatabaseMatch )
    {
      v13 = 0;
      v15 = 4;
      SdbQueryDataEx(a3, DatabaseMatch, v10, &v16, &v13, &v15);
      if ( (v13 & 0x12) == 0 && ((v13 & 4) == 0 || IsProcessorFeaturePresent(9u)) )
      {
        v3 = 1275;
        DevRtlWriteTextLog(ThreadLogToken, 0x4000000, 1, "An incompatible driver %ls was blocked", lpFileName);
        v20 = GUID_DRVMAIN_SDB;
        if ( (unsigned int)SdbTagRefToTagID(a3, DatabaseMatch, &v19, &v14)
          && GetTokenInformation(TokenHandle, TokenSessionId, &TokenInformation, 4u, &ReturnLength) )
        {
          SdbApphelpNotifyEx(lpFileName, &v20, v14);
        }
      }
    }
    CloseHandle(FileW);
  }
  return v3;
}

```

## disassembly

```asm
0x14002f244  mov     [rsp-38h+arg_18], rbx
0x14002f249  push    rbp
0x14002f24a  push    rsi
0x14002f24b  push    rdi
0x14002f24c  push    r12
0x14002f24e  push    r13
0x14002f250  push    r14
0x14002f252  push    r15
0x14002f254  mov     rbp, rsp
0x14002f257  sub     rsp, 80h
0x14002f25e  mov     rax, cs:__security_cookie
0x14002f265  xor     rax, rsp
0x14002f268  mov     [rbp+var_10], rax
0x14002f26c  xor     ebx, ebx
0x14002f26e  xorps   xmm0, xmm0
0x14002f271  mov     [rbp+var_34], ebx
0x14002f274  mov     r15, r8
0x14002f277  mov     [rbp+var_40], ebx
0x14002f27a  mov     r12, rdx
0x14002f27d  movups  [rbp+var_20], xmm0
0x14002f281  mov     [rbp+var_3C], ebx
0x14002f284  mov     rdi, rcx
0x14002f287  mov     [rbp+var_28], rbx
0x14002f28b  mov     [rbp+TokenInformation], ebx
0x14002f28e  mov     [rbp+ReturnLength], ebx
0x14002f291  call    cs:__imp_DevRtlGetThreadLogToken
0x14002f297  mov     [rsp+80h+hTemplateFile], rbx; hTemplateFile
0x14002f29c  lea     r8d, [rbx+1]; dwShareMode
0x14002f2a0  mov     [rsp+80h+dwFlagsAndAttributes], ebx; dwFlagsAndAttributes
0x14002f2a4  xor     r9d, r9d; lpSecurityAttributes
0x14002f2a7  mov     edx, 80000000h; dwDesiredAccess
0x14002f2ac  mov     [rsp+80h+dwCreationDisposition], 3; dwCreationDisposition
0x14002f2b4  mov     rcx, rdi; lpFileName
0x14002f2b7  mov     r13, rax
0x14002f2ba  call    cs:__imp_CreateFileW
0x14002f2c0  mov     rsi, rax
0x14002f2c3  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14002f2c7  jnz     short loc_14002F2D6
0x14002f2c9  call    cs:__imp_GetLastError
0x14002f2cf  mov     ebx, eax
0x14002f2d1  jmp     loc_14002F3C6
0x14002f2d6  mov     rcx, rdi
0x14002f2d9  call    pSetupGetFileTitle
0x14002f2de  mov     rdx, rax
0x14002f2e1  mov     rcx, r15
0x14002f2e4  mov     r8, rsi
0x14002f2e7  call    SdbGetDatabaseMatch
0x14002f2ec  mov     r14d, eax
0x14002f2ef  test    eax, eax
0x14002f2f1  jz      loc_14002F3BD
0x14002f2f7  lea     rax, [rbp+var_38]
0x14002f2fb  mov     [rbp+var_40], ebx
0x14002f2fe  mov     qword ptr [rsp+80h+dwFlagsAndAttributes], rax
0x14002f303  lea     r9, [rbp+var_34]
0x14002f307  lea     rax, [rbp+var_40]
0x14002f30b  mov     [rbp+var_38], 4
0x14002f312  mov     edx, r14d
0x14002f315  mov     qword ptr [rsp+80h+dwCreationDisposition], rax
0x14002f31a  mov     rcx, r15
0x14002f31d  call    SdbQueryDataEx
0x14002f322  test    byte ptr [rbp+var_40], 12h
0x14002f326  jnz     loc_14002F3BD
0x14002f32c  test    byte ptr [rbp+var_40], 4
0x14002f330  jz      short loc_14002F341
0x14002f332  mov     ecx, 9; ProcessorFeature
0x14002f337  call    cs:__imp_IsProcessorFeaturePresent
0x14002f33d  test    eax, eax
0x14002f33f  jz      short loc_14002F3BD
0x14002f341  lea     r9, aAnIncompatible; "An incompatible driver %ls was blocked"
0x14002f348  mov     qword ptr [rsp+80h+dwCreationDisposition], rdi
0x14002f34d  mov     edx, 4000000h
0x14002f352  mov     r8d, 1
0x14002f358  mov     rcx, r13
0x14002f35b  mov     ebx, 4FBh
0x14002f360  call    cs:__imp_DevRtlWriteTextLog
0x14002f366  movups  xmm0, xmmword ptr cs:GUID_DRVMAIN_SDB.Data1
0x14002f36d  lea     r9, [rbp+var_3C]
0x14002f371  mov     edx, r14d
0x14002f374  lea     r8, [rbp+var_28]
0x14002f378  mov     rcx, r15
0x14002f37b  movdqu  [rbp+var_20], xmm0
0x14002f380  call    SdbTagRefToTagID
0x14002f385  test    eax, eax
0x14002f387  jz      short loc_14002F3BD
0x14002f389  mov     r9d, 4; TokenInformationLength
0x14002f38f  lea     rax, [rbp+ReturnLength]
0x14002f393  lea     r8, [rbp+TokenInformation]; TokenInformation
0x14002f397  mov     qword ptr [rsp+80h+dwCreationDisposition], rax; ReturnLength
0x14002f39c  mov     rcx, r12; TokenHandle
0x14002f39f  lea     edx, [r9+8]; TokenInformationClass
0x14002f3a3  call    cs:__imp_GetTokenInformation
0x14002f3a9  test    eax, eax
0x14002f3ab  jz      short loc_14002F3BD
0x14002f3ad  mov     r8d, [rbp+var_3C]
0x14002f3b1  lea     rdx, [rbp+var_20]
0x14002f3b5  mov     rcx, rdi
0x14002f3b8  call    SdbApphelpNotifyEx
0x14002f3bd  mov     rcx, rsi; hObject
0x14002f3c0  call    cs:__imp_CloseHandle
0x14002f3c6  mov     eax, ebx
0x14002f3c8  mov     rcx, [rbp+var_10]
0x14002f3cc  xor     rcx, rsp; StackCookie
0x14002f3cf  call    __security_check_cookie
0x14002f3d4  mov     rbx, [rsp+80h+arg_18]
0x14002f3dc  add     rsp, 80h
0x14002f3e3  pop     r15
0x14002f3e5  pop     r14
0x14002f3e7  pop     r13
0x14002f3e9  pop     r12
0x14002f3eb  pop     rdi
0x14002f3ec  pop     rsi
0x14002f3ed  pop     rbp
0x14002f3ee  retn
```
