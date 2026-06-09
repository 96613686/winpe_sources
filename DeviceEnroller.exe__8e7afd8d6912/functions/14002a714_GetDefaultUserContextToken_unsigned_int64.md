# _GetDefaultUserContextToken(unsigned __int64 *)

- ea: `0x14002a714`
- end: `0x14002a835`
- name: `?_GetDefaultUserContextToken@@YAJPEA_K@Z`
- size: `289`
- prototype: `__int64 __fastcall(unsigned __int64 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1400261c0`

## callees

- `0x1400095b4`
- `0x14002a714`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002a773`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002a773`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14002a786`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14002a786`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14002a77e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14002a7b9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14002a7fc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14002a814`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14002a77e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14002a7b9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14002a7fc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14002a814`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserContext` at `0x14002a7ca`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserContext` at `0x14002a7ca`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryDefaultAccountToken` at `0x14002a750`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryDefaultAccountToken` at `0x14002a750`

## string_xrefs

- `0x14002a797`: `onecoreuap\private\base\inc\createwpnsystemplatform.h`
- `0x14002a7da`: `onecoreuap\private\base\inc\createwpnsystemplatform.h`

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
0x14002a714  mov     [rsp-28h+arg_0], rbx
0x14002a719  mov     [rsp-28h+arg_10], rsi
0x14002a71e  push    rbp
0x14002a71f  push    rdi
0x14002a720  push    r12
0x14002a722  push    r14
0x14002a724  push    r15
0x14002a726  mov     rbp, rsp
0x14002a729  sub     rsp, 40h
0x14002a72d  mov     r12, rcx
0x14002a730  mov     [rbp+hObject], 0
0x14002a738  lea     rax, [rbp+hObject]
0x14002a73c  mov     [rbp+var_18], 0
0x14002a744  lea     rcx, [rbp+var_18]
0x14002a748  mov     [rbp+var_20], rax
0x14002a74c  mov     [rbp+var_10], 1
0x14002a750  call    cs:__imp_UMgrQueryDefaultAccountToken
0x14002a756  cmp     [rbp+var_10], 0
0x14002a75a  mov     edi, eax
0x14002a75c  jz      short loc_14002A78F
0x14002a75e  mov     rsi, [rbp+var_20]
0x14002a762  mov     r15, [rbp+var_18]
0x14002a766  mov     r14, [rsi]
0x14002a769  lea     rdx, [r14-1]
0x14002a76d  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x14002a771  ja      short loc_14002A78C
0x14002a773  call    cs:__imp_GetLastError
0x14002a779  mov     rcx, r14; hObject
0x14002a77c  mov     ebx, eax
0x14002a77e  call    cs:__imp_CloseHandle
0x14002a784  mov     ecx, ebx; dwErrCode
0x14002a786  call    cs:__imp_SetLastError
0x14002a78c  mov     [rsi], r15
0x14002a78f  test    edi, edi
0x14002a791  jns     short loc_14002A7C3
0x14002a793  mov     rcx, [rbp+28h]; this
0x14002a797  lea     r8, aOnecoreuapPriv; "onecoreuap\\private\\base\\inc\\createw"...
0x14002a79e  mov     r9d, edi; char *
0x14002a7a1  mov     edx, 10h; void *
0x14002a7a6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14002a7ab  mov     rcx, [rbp+hObject]; hObject
0x14002a7af  lea     rax, [rcx-1]
0x14002a7b3  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x14002a7b7  ja      short loc_14002A7BF
0x14002a7b9  call    cs:__imp_CloseHandle
0x14002a7bf  mov     eax, edi
0x14002a7c1  jmp     short loc_14002A81C
0x14002a7c3  mov     rcx, [rbp+hObject]
0x14002a7c7  mov     rdx, r12
0x14002a7ca  call    cs:__imp_UMgrQueryUserContext
0x14002a7d0  mov     ebx, eax
0x14002a7d2  test    eax, eax
0x14002a7d4  jns     short loc_14002A806
0x14002a7d6  mov     rcx, [rbp+28h]; this
0x14002a7da  lea     r8, aOnecoreuapPriv; "onecoreuap\\private\\base\\inc\\createw"...
0x14002a7e1  mov     r9d, eax; char *
0x14002a7e4  mov     edx, 11h; void *
0x14002a7e9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14002a7ee  mov     rcx, [rbp+hObject]; hObject
0x14002a7f2  lea     rdx, [rcx-1]
0x14002a7f6  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x14002a7fa  ja      short loc_14002A802
0x14002a7fc  call    cs:__imp_CloseHandle
0x14002a802  mov     eax, ebx
0x14002a804  jmp     short loc_14002A81C
0x14002a806  mov     rcx, [rbp+hObject]; hObject
0x14002a80a  lea     rax, [rcx-1]
0x14002a80e  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x14002a812  ja      short loc_14002A81A
0x14002a814  call    cs:__imp_CloseHandle
0x14002a81a  xor     eax, eax
0x14002a81c  lea     r11, [rsp+40h+var_s0]
0x14002a821  mov     rbx, [r11+30h]
0x14002a825  mov     rsi, [r11+40h]
0x14002a829  mov     rsp, r11
0x14002a82c  pop     r15
0x14002a82e  pop     r14
0x14002a830  pop     r12
0x14002a832  pop     rdi
0x14002a833  pop     rbp
0x14002a834  retn
```
