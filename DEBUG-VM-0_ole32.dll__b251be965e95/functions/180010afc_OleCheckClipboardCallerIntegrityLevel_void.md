# OleCheckClipboardCallerIntegrityLevel(void)

- ea: `0x180010afc`
- end: `0x180010bb0`
- name: `?OleCheckClipboardCallerIntegrityLevel@@YAJXZ`
- size: `180`
- prototype: `HRESULT __fastcall()`
- caller_count: `5`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800104b0`
- `0x1800108b0`
- `0x180010950`
- `0x180011a40`
- `0x18008f600`

## callees

- `0x180010afc`
- `0x180010be8`
- `0x180019454`
- `0x180031a74`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180010b36`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180010b36`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180010b21`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180010b21`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180010b56`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180010b56`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x180010b06`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x180010b06`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x180010b68`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x180010b68`

## pseudocode

```c
__int64 __fastcall OleCheckClipboardCallerIntegrityLevel()
{
  int ThreadIntegrityLevel; // ebx
  unsigned int v1; // edi
  HANDLE CurrentThread; // rax
  _TOKEN_INFORMATION_CLASS v3; // edx
  unsigned int dwLevel; // [rsp+30h] [rbp+8h] BYREF
  void *hToken; // [rsp+38h] [rbp+10h] BYREF

  ThreadIntegrityLevel = CoImpersonateClient();
  if ( ThreadIntegrityLevel >= 0 )
  {
    v1 = 0;
    hToken = 0;
    dwLevel = 0;
    CurrentThread = GetCurrentThread();
    if ( OpenThreadToken(CurrentThread, 0x18u, 1, &hToken) )
    {
      ThreadIntegrityLevel = IsTokenBoolPresent(hToken, v3, (int *)&dwLevel);
      CloseHandle(hToken);
      if ( ThreadIntegrityLevel < 0 )
        goto LABEL_8;
      v1 = dwLevel;
    }
    if ( v1 )
    {
LABEL_6:
      CoRevertToSelf();
      return (unsigned int)ThreadIntegrityLevel;
    }
LABEL_8:
    dwLevel = 0;
    ThreadIntegrityLevel = GetThreadIntegrityLevel(&dwLevel);
    if ( ThreadIntegrityLevel >= 0 && dwLevel < 0x2000 )
    {
      ThreadIntegrityLevel = -2147024891;
      OleInternalOriginateError(-2147024891, 0x134u);
    }
    goto LABEL_6;
  }
  return (unsigned int)ThreadIntegrityLevel;
}

```

## disassembly

```asm
0x180010afc  mov     [rsp+arg_10], rbx
0x180010b01  push    rdi
0x180010b02  sub     rsp, 20h
0x180010b06  call    cs:__imp_CoImpersonateClient
0x180010b0c  mov     ebx, eax
0x180010b0e  test    eax, eax
0x180010b10  js      short loc_180010B6E
0x180010b12  xor     edi, edi
0x180010b14  mov     [rsp+28h+hToken], 0
0x180010b1d  mov     [rsp+28h+dwLevel], edi
0x180010b21  call    cs:__imp_GetCurrentThread
0x180010b27  mov     rcx, rax; ThreadHandle
0x180010b2a  lea     r9, [rsp+28h+hToken]; TokenHandle
0x180010b2f  lea     edx, [rdi+18h]; DesiredAccess
0x180010b32  lea     r8d, [rdi+1]; OpenAsSelf
0x180010b36  call    cs:__imp_OpenThreadToken
0x180010b3c  test    eax, eax
0x180010b3e  jz      short loc_180010B64
0x180010b40  mov     rcx, [rsp+28h+hToken]; hToken
0x180010b45  lea     r8, [rsp+28h+dwLevel]; hToken
0x180010b4a  call    ?IsTokenBoolPresent@@YAJPEAXW4_TOKEN_INFORMATION_CLASS@@PEAH@Z; IsTokenBoolPresent(void *,_TOKEN_INFORMATION_CLASS,int *)
0x180010b4f  mov     rcx, [rsp+28h+hToken]; hObject
0x180010b54  mov     ebx, eax
0x180010b56  call    cs:__imp_CloseHandle
0x180010b5c  test    ebx, ebx
0x180010b5e  js      short loc_180010B7B
0x180010b60  mov     edi, [rsp+28h+dwLevel]
0x180010b64  test    edi, edi
0x180010b66  jz      short loc_180010B7B
0x180010b68  call    cs:__imp_CoRevertToSelf
0x180010b6e  mov     eax, ebx
0x180010b70  mov     rbx, [rsp+28h+arg_10]
0x180010b75  add     rsp, 20h
0x180010b79  pop     rdi
0x180010b7a  retn
0x180010b7b  lea     rcx, [rsp+28h+dwLevel]; pdwIntegrityLevel
0x180010b80  mov     [rsp+28h+dwLevel], 0
0x180010b88  call    ?GetThreadIntegrityLevel@@YAJPEAK@Z; GetThreadIntegrityLevel(ulong *)
0x180010b8d  mov     ebx, eax
0x180010b8f  test    eax, eax
0x180010b91  js      short loc_180010B68
0x180010b93  cmp     [rsp+28h+dwLevel], 2000h
0x180010b9b  jnb     short loc_180010B68
0x180010b9d  mov     ebx, 80070005h
0x180010ba2  mov     edx, 134h; messageID
0x180010ba7  mov     ecx, ebx; hr
0x180010ba9  call    ?OleInternalOriginateError@@YAXJG@Z; OleInternalOriginateError(long,ushort)
0x180010bae  jmp     short loc_180010B68
```
