# _GetDefaultUserContextToken(unsigned __int64 *)

- ea: `0x18007b7f4`
- end: `0x18007b915`
- name: `?_GetDefaultUserContextToken@@YAJPEA_K@Z`
- size: `289`
- prototype: `__int64 __fastcall(unsigned __int64 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18007b49c`

## callees

- `0x18000c964`
- `0x18007b7f4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007b853`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007b853`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18007b866`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18007b866`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007b85e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007b899`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007b8dc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007b8f4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007b85e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007b899`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007b8dc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007b8f4`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryDefaultAccountToken` at `0x18007b830`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryDefaultAccountToken` at `0x18007b830`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserContext` at `0x18007b8aa`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserContext` at `0x18007b8aa`

## string_xrefs

- `0x18007b877`: `onecoreuap\private\base\inc\createwpnsystemplatform.h`
- `0x18007b8ba`: `onecoreuap\private\base\inc\createwpnsystemplatform.h`

## pseudocode

```c
__int64 __fastcall _GetDefaultUserContextToken(unsigned __int64 *a1)
{
  int v2; // edi
  void *v3; // r15
  HANDLE v4; // r14
  DWORD LastError; // ebx
  int UserContext; // eax
  unsigned int v8; // ebx
  void *v9; // [rsp+28h] [rbp-18h] BYREF
  char v10; // [rsp+30h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+28h]
  HANDLE hObject; // [rsp+78h] [rbp+38h] BYREF

  hObject = 0;
  v9 = 0;
  v10 = 1;
  v2 = UMgrQueryDefaultAccountToken(&v9);
  if ( v10 )
  {
    v3 = v9;
    v4 = hObject;
    if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    {
      LastError = GetLastError();
      CloseHandle(v4);
      SetLastError(LastError);
    }
    hObject = v3;
  }
  if ( v2 >= 0 )
  {
    UserContext = UMgrQueryUserContext(hObject, a1);
    v8 = UserContext;
    if ( UserContext >= 0 )
    {
      if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
        CloseHandle(hObject);
      return 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x11,
        (unsigned int)"onecoreuap\\private\\base\\inc\\createwpnsystemplatform.h",
        (const char *)(unsigned int)UserContext,
        (int)&hObject);
      if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
        CloseHandle(hObject);
      return v8;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x10,
      (unsigned int)"onecoreuap\\private\\base\\inc\\createwpnsystemplatform.h",
      (const char *)(unsigned int)v2,
      (int)&hObject);
    if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      CloseHandle(hObject);
    return (unsigned int)v2;
  }
}

```

## disassembly

```asm
0x18007b7f4  mov     [rsp-28h+arg_0], rbx
0x18007b7f9  mov     [rsp-28h+arg_10], rsi
0x18007b7fe  push    rbp
0x18007b7ff  push    rdi
0x18007b800  push    r12
0x18007b802  push    r14
0x18007b804  push    r15
0x18007b806  mov     rbp, rsp
0x18007b809  sub     rsp, 40h
0x18007b80d  mov     r12, rcx
0x18007b810  mov     [rbp+hObject], 0
0x18007b818  lea     rax, [rbp+hObject]
0x18007b81c  mov     [rbp+var_18], 0
0x18007b824  lea     rcx, [rbp+var_18]
0x18007b828  mov     [rbp+var_20], rax
0x18007b82c  mov     [rbp+var_10], 1
0x18007b830  call    cs:__imp_UMgrQueryDefaultAccountToken
0x18007b836  cmp     [rbp+var_10], 0
0x18007b83a  mov     edi, eax
0x18007b83c  jz      short loc_18007B86F
0x18007b83e  mov     rsi, [rbp+var_20]
0x18007b842  mov     r15, [rbp+var_18]
0x18007b846  mov     r14, [rsi]
0x18007b849  lea     rdx, [r14-1]
0x18007b84d  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x18007b851  ja      short loc_18007B86C
0x18007b853  call    cs:__imp_GetLastError
0x18007b859  mov     rcx, r14; hObject
0x18007b85c  mov     ebx, eax
0x18007b85e  call    cs:__imp_CloseHandle
0x18007b864  mov     ecx, ebx; dwErrCode
0x18007b866  call    cs:__imp_SetLastError
0x18007b86c  mov     [rsi], r15
0x18007b86f  test    edi, edi
0x18007b871  jns     short loc_18007B8A3
0x18007b873  mov     rcx, [rbp+28h]; this
0x18007b877  lea     r8, aOnecoreuapPriv; "onecoreuap\\private\\base\\inc\\createw"...
0x18007b87e  mov     r9d, edi; char *
0x18007b881  mov     edx, 10h; void *
0x18007b886  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007b88b  mov     rcx, [rbp+hObject]; hObject
0x18007b88f  lea     rax, [rcx-1]
0x18007b893  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18007b897  ja      short loc_18007B89F
0x18007b899  call    cs:__imp_CloseHandle
0x18007b89f  mov     eax, edi
0x18007b8a1  jmp     short loc_18007B8FC
0x18007b8a3  mov     rcx, [rbp+hObject]
0x18007b8a7  mov     rdx, r12
0x18007b8aa  call    cs:__imp_UMgrQueryUserContext
0x18007b8b0  mov     ebx, eax
0x18007b8b2  test    eax, eax
0x18007b8b4  jns     short loc_18007B8E6
0x18007b8b6  mov     rcx, [rbp+28h]; this
0x18007b8ba  lea     r8, aOnecoreuapPriv; "onecoreuap\\private\\base\\inc\\createw"...
0x18007b8c1  mov     r9d, eax; char *
0x18007b8c4  mov     edx, 11h; void *
0x18007b8c9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007b8ce  mov     rcx, [rbp+hObject]; hObject
0x18007b8d2  lea     rdx, [rcx-1]
0x18007b8d6  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x18007b8da  ja      short loc_18007B8E2
0x18007b8dc  call    cs:__imp_CloseHandle
0x18007b8e2  mov     eax, ebx
0x18007b8e4  jmp     short loc_18007B8FC
0x18007b8e6  mov     rcx, [rbp+hObject]; hObject
0x18007b8ea  lea     rax, [rcx-1]
0x18007b8ee  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18007b8f2  ja      short loc_18007B8FA
0x18007b8f4  call    cs:__imp_CloseHandle
0x18007b8fa  xor     eax, eax
0x18007b8fc  lea     r11, [rsp+40h+var_s0]
0x18007b901  mov     rbx, [r11+30h]
0x18007b905  mov     rsi, [r11+40h]
0x18007b909  mov     rsp, r11
0x18007b90c  pop     r15
0x18007b90e  pop     r14
0x18007b910  pop     r12
0x18007b912  pop     rdi
0x18007b913  pop     rbp
0x18007b914  retn
```
