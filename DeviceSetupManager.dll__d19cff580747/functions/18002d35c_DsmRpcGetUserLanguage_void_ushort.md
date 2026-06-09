# DsmRpcGetUserLanguage(void *,ushort * *)

- ea: `0x18002d35c`
- end: `0x18002d45d`
- name: `?DsmRpcGetUserLanguage@@YAJPEAXPEAPEAG@Z`
- size: `257`
- prototype: `__int64 __fastcall(void *, unsigned __int16 **)`
- caller_count: `3`
- callee_count: `1`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18002dde0`
- `0x18002e000`
- `0x18002e0d0`

## callees

- `0x18002d35c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d3c9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d41e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d3c9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d41e`
- `api-ms-win-core-localization-l1-2-0!GetThreadPreferredUILanguages` at `0x18002d3bf`
- `api-ms-win-core-localization-l1-2-0!GetThreadPreferredUILanguages` at `0x18002d410`
- `api-ms-win-core-localization-l1-2-0!GetThreadPreferredUILanguages` at `0x18002d3bf`
- `api-ms-win-core-localization-l1-2-0!GetThreadPreferredUILanguages` at `0x18002d410`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002d3e9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002d3e9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002d43f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002d43f`
- `RPCRT4!I_RpcMapWin32Status` at `0x18002d381`
- `RPCRT4!I_RpcMapWin32Status` at `0x18002d381`
- `RPCRT4!RpcImpersonateClient` at `0x18002d375`
- `RPCRT4!RpcImpersonateClient` at `0x18002d375`
- `RPCRT4!RpcRevertToSelf` at `0x18002d445`
- `RPCRT4!RpcRevertToSelf` at `0x18002d445`

## pseudocode

```c
__int64 __fastcall DsmRpcGetUserLanguage(void *a1, unsigned __int16 **a2)
{
  RPC_STATUS v3; // eax
  int v4; // eax
  signed int v5; // ebx
  signed int LastError; // eax
  WCHAR *v7; // rax
  WCHAR *v8; // rdi
  signed int v9; // eax
  ULONG pcchLanguagesBuffer; // [rsp+38h] [rbp+10h] BYREF
  ULONG pulNumLanguages; // [rsp+40h] [rbp+18h] BYREF

  *a2 = 0;
  v3 = RpcImpersonateClient(a1);
  if ( !v3 )
    goto LABEL_5;
  v4 = I_RpcMapWin32Status(v3);
  v5 = v4;
  if ( v4 > 0 )
    v5 = (unsigned __int16)v4 | 0x80070000;
  if ( v5 >= 0 )
  {
LABEL_5:
    pulNumLanguages = 0;
    pcchLanguagesBuffer = 0;
    if ( !GetThreadPreferredUILanguages(0x38u, &pulNumLanguages, 0, &pcchLanguagesBuffer) )
    {
      LastError = GetLastError();
      v5 = LastError;
      if ( LastError > 0 )
        v5 = (unsigned __int16)LastError | 0x80070000;
      if ( v5 < 0 )
        goto LABEL_18;
    }
    v7 = (WCHAR *)CoTaskMemAlloc(2LL * pcchLanguagesBuffer);
    v8 = v7;
    if ( v7 )
    {
      if ( GetThreadPreferredUILanguages(0x38u, &pulNumLanguages, v7, &pcchLanguagesBuffer) )
      {
        v5 = 0;
      }
      else
      {
        v9 = GetLastError();
        v5 = v9;
        if ( v9 > 0 )
          v5 = (unsigned __int16)v9 | 0x80070000;
        if ( v5 < 0 )
        {
          CoTaskMemFree(v8);
          goto LABEL_18;
        }
      }
      *a2 = v8;
    }
    else
    {
      v5 = -2147024882;
    }
LABEL_18:
    RpcRevertToSelf();
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18002d35c  mov     [rsp+arg_0], rbx
0x18002d361  mov     [rsp+arg_18], rsi
0x18002d366  push    rdi
0x18002d367  sub     rsp, 20h
0x18002d36b  mov     rsi, rdx
0x18002d36e  mov     qword ptr [rdx], 0
0x18002d375  call    cs:__imp_RpcImpersonateClient
0x18002d37b  test    eax, eax
0x18002d37d  jz      short loc_18002D39E
0x18002d37f  mov     ecx, eax; Status
0x18002d381  call    cs:__imp_I_RpcMapWin32Status
0x18002d387  mov     ebx, eax
0x18002d389  test    eax, eax
0x18002d38b  jle     short loc_18002D396
0x18002d38d  movzx   ebx, ax
0x18002d390  or      ebx, 80070000h
0x18002d396  test    ebx, ebx
0x18002d398  js      loc_18002D44B
0x18002d39e  xor     r8d, r8d; pwszLanguagesBuffer
0x18002d3a1  mov     [rsp+28h+pulNumLanguages], 0
0x18002d3a9  lea     r9, [rsp+28h+pcchLanguagesBuffer]; pcchLanguagesBuffer
0x18002d3ae  mov     [rsp+28h+pcchLanguagesBuffer], 0
0x18002d3b6  lea     rdx, [rsp+28h+pulNumLanguages]; pulNumLanguages
0x18002d3bb  lea     ecx, [r8+38h]; dwFlags
0x18002d3bf  call    cs:__imp_GetThreadPreferredUILanguages
0x18002d3c5  test    eax, eax
0x18002d3c7  jnz     short loc_18002D3E2
0x18002d3c9  call    cs:__imp_GetLastError
0x18002d3cf  mov     ebx, eax
0x18002d3d1  test    eax, eax
0x18002d3d3  jle     short loc_18002D3DE
0x18002d3d5  movzx   ebx, ax
0x18002d3d8  or      ebx, 80070000h
0x18002d3de  test    ebx, ebx
0x18002d3e0  js      short loc_18002D445
0x18002d3e2  mov     ecx, [rsp+28h+pcchLanguagesBuffer]
0x18002d3e6  add     rcx, rcx; cb
0x18002d3e9  call    cs:__imp_CoTaskMemAlloc
0x18002d3ef  mov     rdi, rax
0x18002d3f2  test    rax, rax
0x18002d3f5  jnz     short loc_18002D3FE
0x18002d3f7  mov     ebx, 8007000Eh
0x18002d3fc  jmp     short loc_18002D445
0x18002d3fe  lea     r9, [rsp+28h+pcchLanguagesBuffer]; pcchLanguagesBuffer
0x18002d403  mov     r8, rdi; pwszLanguagesBuffer
0x18002d406  lea     rdx, [rsp+28h+pulNumLanguages]; pulNumLanguages
0x18002d40b  mov     ecx, 38h ; '8'; dwFlags
0x18002d410  call    cs:__imp_GetThreadPreferredUILanguages
0x18002d416  test    eax, eax
0x18002d418  jz      short loc_18002D41E
0x18002d41a  xor     ebx, ebx
0x18002d41c  jmp     short loc_18002D437
0x18002d41e  call    cs:__imp_GetLastError
0x18002d424  mov     ebx, eax
0x18002d426  test    eax, eax
0x18002d428  jle     short loc_18002D433
0x18002d42a  movzx   ebx, ax
0x18002d42d  or      ebx, 80070000h
0x18002d433  test    ebx, ebx
0x18002d435  js      short loc_18002D43C
0x18002d437  mov     [rsi], rdi
0x18002d43a  jmp     short loc_18002D445
0x18002d43c  mov     rcx, rdi; pv
0x18002d43f  call    cs:__imp_CoTaskMemFree
0x18002d445  call    cs:__imp_RpcRevertToSelf
0x18002d44b  mov     rsi, [rsp+28h+arg_18]
0x18002d450  mov     eax, ebx
0x18002d452  mov     rbx, [rsp+28h+arg_0]
0x18002d457  add     rsp, 20h
0x18002d45b  pop     rdi
0x18002d45c  retn
```
