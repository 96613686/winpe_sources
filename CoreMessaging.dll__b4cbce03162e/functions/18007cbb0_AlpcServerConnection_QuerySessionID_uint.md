# AlpcServerConnection::QuerySessionID(uint &)

- ea: `0x18007cbb0`
- end: `0x18007cc43`
- name: `?QuerySessionID@AlpcServerConnection@@UEAAJAEAI@Z`
- size: `147`
- prototype: `int(AlpcServerConnection *__hidden this, unsigned int *)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x18007cbb0`
- `0x18007ccdc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007cc2c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007cc2c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007cc19`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007cc19`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18007cc03`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18007cc03`

## pseudocode

```c
__int64 __fastcall AlpcServerConnection::QuerySessionID(AlpcServerConnection *this, unsigned int *a2)
{
  int ClientToken; // ebx
  signed int LastError; // eax
  DWORD ReturnLength; // [rsp+40h] [rbp+8h] BYREF
  HANDLE TokenHandle; // [rsp+48h] [rbp+10h] BYREF

  *a2 = 0;
  TokenHandle = 0;
  ReturnLength = 0;
  ClientToken = AlpcServerConnection::GetClientToken((AlpcServerConnection *)((char *)this - 96), &TokenHandle);
  if ( ClientToken >= 0 )
  {
    if ( GetTokenInformation(TokenHandle, TokenSessionId, a2, 4u, &ReturnLength) )
    {
      ClientToken = 0;
    }
    else
    {
      LastError = GetLastError();
      ClientToken = LastError;
      if ( LastError > 0 )
        ClientToken = (unsigned __int16)LastError | 0x80070000;
    }
  }
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  return (unsigned int)ClientToken;
}

```

## disassembly

```asm
0x18007cbb0  mov     rax, rsp
0x18007cbb3  mov     [rax+18h], rbx
0x18007cbb7  push    rdi
0x18007cbb8  sub     rsp, 30h
0x18007cbbc  mov     rdi, rdx
0x18007cbbf  mov     dword ptr [rdx], 0
0x18007cbc5  lea     rdx, [rax+10h]; void **
0x18007cbc9  mov     qword ptr [rax+10h], 0
0x18007cbd1  add     rcx, 0FFFFFFFFFFFFFFA0h; this
0x18007cbd5  mov     dword ptr [rax+8], 0
0x18007cbdc  call    ?GetClientToken@AlpcServerConnection@@AEAAJPEAPEAX@Z; AlpcServerConnection::GetClientToken(void * *)
0x18007cbe1  mov     ebx, eax
0x18007cbe3  test    eax, eax
0x18007cbe5  js      short loc_18007CC0F
0x18007cbe7  mov     rcx, [rsp+38h+TokenHandle]; TokenHandle
0x18007cbec  lea     rax, [rsp+38h+arg_0]
0x18007cbf1  mov     r9d, 4; TokenInformationLength
0x18007cbf7  mov     [rsp+38h+ReturnLength], rax; ReturnLength
0x18007cbfc  mov     r8, rdi; TokenInformation
0x18007cbff  lea     edx, [r9+8]; TokenInformationClass
0x18007cc03  call    cs:__imp_GetTokenInformation
0x18007cc09  test    eax, eax
0x18007cc0b  jz      short loc_18007CC2C
0x18007cc0d  xor     ebx, ebx
0x18007cc0f  mov     rcx, [rsp+38h+TokenHandle]; hObject
0x18007cc14  test    rcx, rcx
0x18007cc17  jz      short loc_18007CC1F
0x18007cc19  call    cs:__imp_CloseHandle
0x18007cc1f  mov     eax, ebx
0x18007cc21  mov     rbx, [rsp+38h+arg_10]
0x18007cc26  add     rsp, 30h
0x18007cc2a  pop     rdi
0x18007cc2b  retn
0x18007cc2c  call    cs:__imp_GetLastError
0x18007cc32  mov     ebx, eax
0x18007cc34  test    eax, eax
0x18007cc36  jle     short loc_18007CC0F
0x18007cc38  movzx   ebx, ax
0x18007cc3b  or      ebx, 80070000h
0x18007cc41  jmp     short loc_18007CC0F
```
