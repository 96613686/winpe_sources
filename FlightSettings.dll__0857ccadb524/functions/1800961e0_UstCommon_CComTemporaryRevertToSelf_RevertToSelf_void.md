# UstCommon::CComTemporaryRevertToSelf::RevertToSelf(void)

- ea: `0x1800961e0`
- end: `0x18009626f`
- name: `?RevertToSelf@CComTemporaryRevertToSelf@UstCommon@@QEAAJXZ`
- size: `143`
- prototype: `__int64 __fastcall(PHANDLE TokenHandle)`
- caller_count: `3`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800b19ec`
- `0x1800b2934`
- `0x1800b53f8`

## callees

- `0x1800961e0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009621a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009623d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009621a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009623d`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180096210`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180096210`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800961fd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800961fd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180096255`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180096255`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180096233`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180096233`

## pseudocode

```c
__int64 __fastcall UstCommon::CComTemporaryRevertToSelf::RevertToSelf(PHANDLE TokenHandle)
{
  signed int v2; // ebx
  HANDLE CurrentThread; // rax
  signed int LastError; // eax
  signed int v5; // eax

  v2 = -2147467259;
  if ( !*TokenHandle )
  {
    v2 = 0;
    *TokenHandle = 0;
    CurrentThread = GetCurrentThread();
    if ( !OpenThreadToken(CurrentThread, 0xEu, 1, TokenHandle) )
    {
      LastError = GetLastError();
      v2 = LastError;
      if ( LastError > 0 )
        v2 = (unsigned __int16)LastError | 0x80070000;
    }
    if ( v2 >= 0 && !RevertToSelf() )
    {
      v5 = GetLastError();
      v2 = v5;
      if ( v5 > 0 )
        v2 = (unsigned __int16)v5 | 0x80070000;
      CloseHandle(*TokenHandle);
      *TokenHandle = 0;
    }
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x1800961e0  mov     [rsp+arg_0], rbx
0x1800961e5  push    rdi
0x1800961e6  sub     rsp, 20h
0x1800961ea  cmp     qword ptr [rcx], 0
0x1800961ee  mov     rdi, rcx
0x1800961f1  mov     ebx, 80004005h
0x1800961f6  jnz     short loc_180096262
0x1800961f8  xor     ebx, ebx
0x1800961fa  mov     [rcx], rbx
0x1800961fd  call    cs:__imp_GetCurrentThread
0x180096203  mov     r9, rdi; TokenHandle
0x180096206  lea     edx, [rbx+0Eh]; DesiredAccess
0x180096209  mov     rcx, rax; ThreadHandle
0x18009620c  lea     r8d, [rbx+1]; OpenAsSelf
0x180096210  call    cs:__imp_OpenThreadToken
0x180096216  test    eax, eax
0x180096218  jnz     short loc_18009622F
0x18009621a  call    cs:__imp_GetLastError
0x180096220  mov     ebx, eax
0x180096222  test    eax, eax
0x180096224  jle     short loc_18009622F
0x180096226  movzx   ebx, ax
0x180096229  or      ebx, 80070000h
0x18009622f  test    ebx, ebx
0x180096231  js      short loc_180096262
0x180096233  call    cs:__imp_RevertToSelf
0x180096239  test    eax, eax
0x18009623b  jnz     short loc_180096262
0x18009623d  call    cs:__imp_GetLastError
0x180096243  mov     ebx, eax
0x180096245  test    eax, eax
0x180096247  jle     short loc_180096252
0x180096249  movzx   ebx, ax
0x18009624c  or      ebx, 80070000h
0x180096252  mov     rcx, [rdi]; hObject
0x180096255  call    cs:__imp_CloseHandle
0x18009625b  mov     qword ptr [rdi], 0
0x180096262  mov     eax, ebx
0x180096264  mov     rbx, [rsp+28h+arg_0]
0x180096269  add     rsp, 20h
0x18009626d  pop     rdi
0x18009626e  retn
```
