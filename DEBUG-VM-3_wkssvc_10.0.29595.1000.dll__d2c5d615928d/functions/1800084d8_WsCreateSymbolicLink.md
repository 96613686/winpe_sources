# WsCreateSymbolicLink

- ea: `0x1800084d8`
- end: `0x18000863f`
- name: `WsCreateSymbolicLink`
- size: `359`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `reparse_path, authz_impersonation`

## callers

- `0x180001710`
- `0x18002a644`

## callees

- `0x180008484`
- `0x1800084d8`
- `0x180008650`
- `0x180008950`
- `0x1800089d0`
- `0x18001e420`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008525`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008565`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800085a2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008601`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008525`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008565`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800085a2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008601`
- `api-ms-win-core-file-l1-1-0!DefineDosDeviceW` at `0x1800085f7`
- `api-ms-win-core-file-l1-1-0!DefineDosDeviceW` at `0x1800085f7`
- `api-ms-win-core-file-l1-1-0!QueryDosDeviceW` at `0x180008598`
- `api-ms-win-core-file-l1-1-0!QueryDosDeviceW` at `0x180008598`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180008546`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180008546`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18000855b`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18000855b`

## pseudocode

```c
DWORD __fastcall WsCreateSymbolicLink(
        __int64 a1,
        int a2,
        const WCHAR *a3,
        __int64 a4,
        LPCWSTR *a5,
        PHANDLE TokenHandle)
{
  __int64 v10; // rax
  DWORD result; // eax
  HANDLE CurrentThread; // rax
  DWORD LastError; // ebx
  DWORD v14; // eax
  bool v15; // zf
  __int64 v16; // [rsp+20h] [rbp-C8h] BYREF
  __int64 v17; // [rsp+28h] [rbp-C0h] BYREF
  WCHAR TargetPath[64]; // [rsp+30h] [rbp-B8h] BYREF

  v10 = WsReturnSessionPath();
  *a5 = (LPCWSTR)v10;
  if ( !v10 )
    return GetLastError();
  result = WsImpersonateClient2(0, 0);
  if ( !result )
  {
    if ( TokenHandle )
    {
      CurrentThread = GetCurrentThread();
      if ( !OpenThreadToken(CurrentThread, 4u, 1, TokenHandle) )
      {
        LastError = GetLastError();
        WsRevertToSelf2(0, 0);
        *TokenHandle = (void *)-1LL;
        return LastError;
      }
    }
    if ( (unsigned int)(a2 - 1) <= 1 )
    {
      v16 = 0;
      v17 = 0;
      WsFindLocal(a4, a1, &v16, &v17);
      v15 = v16 == 0;
    }
    else
    {
      if ( QueryDosDeviceW(*a5, TargetPath, 0x40u) )
      {
LABEL_13:
        LastError = 85;
        goto LABEL_17;
      }
      v14 = GetLastError();
      LastError = 5;
      if ( v14 == 5 )
      {
LABEL_17:
        WsRevertToSelf2(0, 0);
        return LastError;
      }
      v15 = v14 == 2;
    }
    if ( v15 )
    {
      if ( DefineDosDeviceW(9u, *a5, a3) )
        LastError = 0;
      else
        LastError = GetLastError();
      goto LABEL_17;
    }
    goto LABEL_13;
  }
  return result;
}

```

## disassembly

```asm
0x1800084d8  mov     [rsp+arg_8], rbx
0x1800084dd  push    rbp
0x1800084de  push    rsi
0x1800084df  push    rdi
0x1800084e0  push    r14
0x1800084e2  push    r15
0x1800084e4  sub     rsp, 0C0h
0x1800084eb  mov     rax, cs:__security_cookie
0x1800084f2  xor     rax, rsp
0x1800084f5  mov     [rsp+0E8h+var_38], rax
0x1800084fd  mov     rsi, [rsp+0E8h+arg_20]
0x180008505  mov     r14, r9
0x180008508  mov     rdi, [rsp+0E8h+TokenHandle]
0x180008510  mov     r15, r8
0x180008513  mov     ebp, edx
0x180008515  mov     rbx, rcx
0x180008518  call    WsReturnSessionPath
0x18000851d  mov     [rsi], rax
0x180008520  test    rax, rax
0x180008523  jnz     short loc_180008530
0x180008525  call    cs:__imp_GetLastError
0x18000852b  jmp     loc_180008618
0x180008530  xor     edx, edx
0x180008532  xor     ecx, ecx
0x180008534  call    WsImpersonateClient2
0x180008539  test    eax, eax
0x18000853b  jnz     loc_180008618
0x180008541  test    rdi, rdi
0x180008544  jz      short loc_180008582
0x180008546  call    cs:__imp_GetCurrentThread
0x18000854c  mov     edx, 4; DesiredAccess
0x180008551  mov     r9, rdi; TokenHandle
0x180008554  mov     rcx, rax; ThreadHandle
0x180008557  lea     r8d, [rdx-3]; OpenAsSelf
0x18000855b  call    cs:__imp_OpenThreadToken
0x180008561  test    eax, eax
0x180008563  jnz     short loc_180008582
0x180008565  call    cs:__imp_GetLastError
0x18000856b  xor     edx, edx
0x18000856d  xor     ecx, ecx
0x18000856f  mov     ebx, eax
0x180008571  call    WsRevertToSelf2
0x180008576  mov     qword ptr [rdi], 0FFFFFFFFFFFFFFFFh
0x18000857d  jmp     loc_180008616
0x180008582  lea     eax, [rbp-1]
0x180008585  cmp     eax, 1
0x180008588  jbe     short loc_1800085B6
0x18000858a  mov     rcx, [rsi]; lpDeviceName
0x18000858d  lea     rdx, [rsp+0E8h+TargetPath]; lpTargetPath
0x180008592  mov     r8d, 40h ; '@'; ucchMax
0x180008598  call    cs:__imp_QueryDosDeviceW
0x18000859e  test    eax, eax
0x1800085a0  jnz     short loc_1800085E5
0x1800085a2  call    cs:__imp_GetLastError
0x1800085a8  mov     ebx, 5
0x1800085ad  cmp     eax, ebx
0x1800085af  jz      short loc_18000860D
0x1800085b1  cmp     eax, 2
0x1800085b4  jmp     short loc_1800085E3
0x1800085b6  lea     r9, [rsp+0E8h+var_C0]
0x1800085bb  mov     [rsp+0E8h+var_C8], 0
0x1800085c4  lea     r8, [rsp+0E8h+var_C8]
0x1800085c9  mov     [rsp+0E8h+var_C0], 0
0x1800085d2  mov     rdx, rbx
0x1800085d5  mov     rcx, r14
0x1800085d8  call    WsFindLocal
0x1800085dd  cmp     [rsp+0E8h+var_C8], 0
0x1800085e3  jz      short loc_1800085EC
0x1800085e5  mov     ebx, 55h ; 'U'
0x1800085ea  jmp     short loc_18000860D
0x1800085ec  mov     rdx, [rsi]; lpDeviceName
0x1800085ef  mov     r8, r15; lpTargetPath
0x1800085f2  mov     ecx, 9; dwFlags
0x1800085f7  call    cs:__imp_DefineDosDeviceW
0x1800085fd  test    eax, eax
0x1800085ff  jnz     short loc_18000860B
0x180008601  call    cs:__imp_GetLastError
0x180008607  mov     ebx, eax
0x180008609  jmp     short loc_18000860D
0x18000860b  xor     ebx, ebx
0x18000860d  xor     edx, edx
0x18000860f  xor     ecx, ecx
0x180008611  call    WsRevertToSelf2
0x180008616  mov     eax, ebx
0x180008618  mov     rcx, [rsp+0E8h+var_38]
0x180008620  xor     rcx, rsp; StackCookie
0x180008623  call    __security_check_cookie
0x180008628  mov     rbx, [rsp+0E8h+arg_8]
0x180008630  add     rsp, 0C0h
0x180008637  pop     r15
0x180008639  pop     r14
0x18000863b  pop     rdi
0x18000863c  pop     rsi
0x18000863d  pop     rbp
0x18000863e  retn
```
