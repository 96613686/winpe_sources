# _GetDefaultUserContextToken(unsigned __int64 *)

- ea: `0x180034734`
- end: `0x180034855`
- name: `?_GetDefaultUserContextToken@@YAJPEA_K@Z`
- size: `289`
- prototype: `__int64 __fastcall(unsigned __int64 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180034270`

## callees

- `0x180010b84`
- `0x180034734`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180034793`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180034793`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800347a6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800347a6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003479e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800347d9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003481c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180034834`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003479e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800347d9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003481c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180034834`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryDefaultAccountToken` at `0x180034770`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryDefaultAccountToken` at `0x180034770`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserContext` at `0x1800347ea`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserContext` at `0x1800347ea`

## string_xrefs

- `0x1800347b7`: `onecoreuap\private\base\inc\createwpnsystemplatform.h`
- `0x1800347fa`: `onecoreuap\private\base\inc\createwpnsystemplatform.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
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
0x180034734  mov     [rsp-28h+arg_0], rbx
0x180034739  mov     [rsp-28h+arg_10], rsi
0x18003473e  push    rbp
0x18003473f  push    rdi
0x180034740  push    r12
0x180034742  push    r14
0x180034744  push    r15
0x180034746  mov     rbp, rsp
0x180034749  sub     rsp, 40h
0x18003474d  mov     r12, rcx
0x180034750  mov     [rbp+hObject], 0
0x180034758  lea     rax, [rbp+hObject]
0x18003475c  mov     [rbp+var_18], 0
0x180034764  lea     rcx, [rbp+var_18]
0x180034768  mov     [rbp+var_20], rax
0x18003476c  mov     [rbp+var_10], 1
0x180034770  call    cs:__imp_UMgrQueryDefaultAccountToken
0x180034776  cmp     [rbp+var_10], 0
0x18003477a  mov     edi, eax
0x18003477c  jz      short loc_1800347AF
0x18003477e  mov     rsi, [rbp+var_20]
0x180034782  mov     r15, [rbp+var_18]
0x180034786  mov     r14, [rsi]
0x180034789  lea     rdx, [r14-1]
0x18003478d  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x180034791  ja      short loc_1800347AC
0x180034793  call    cs:__imp_GetLastError
0x180034799  mov     rcx, r14; hObject
0x18003479c  mov     ebx, eax
0x18003479e  call    cs:__imp_CloseHandle
0x1800347a4  mov     ecx, ebx; dwErrCode
0x1800347a6  call    cs:__imp_SetLastError
0x1800347ac  mov     [rsi], r15
0x1800347af  test    edi, edi
0x1800347b1  jns     short loc_1800347E3
0x1800347b3  mov     rcx, [rbp+28h]; this
0x1800347b7  lea     r8, aOnecoreuapPriv; "onecoreuap\\private\\base\\inc\\createw"...
0x1800347be  mov     r9d, edi; char *
0x1800347c1  mov     edx, 10h; void *
0x1800347c6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800347cb  mov     rcx, [rbp+hObject]; hObject
0x1800347cf  lea     rax, [rcx-1]
0x1800347d3  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800347d7  ja      short loc_1800347DF
0x1800347d9  call    cs:__imp_CloseHandle
0x1800347df  mov     eax, edi
0x1800347e1  jmp     short loc_18003483C
0x1800347e3  mov     rcx, [rbp+hObject]
0x1800347e7  mov     rdx, r12
0x1800347ea  call    cs:__imp_UMgrQueryUserContext
0x1800347f0  mov     ebx, eax
0x1800347f2  test    eax, eax
0x1800347f4  jns     short loc_180034826
0x1800347f6  mov     rcx, [rbp+28h]; this
0x1800347fa  lea     r8, aOnecoreuapPriv; "onecoreuap\\private\\base\\inc\\createw"...
0x180034801  mov     r9d, eax; char *
0x180034804  mov     edx, 11h; void *
0x180034809  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003480e  mov     rcx, [rbp+hObject]; hObject
0x180034812  lea     rdx, [rcx-1]
0x180034816  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x18003481a  ja      short loc_180034822
0x18003481c  call    cs:__imp_CloseHandle
0x180034822  mov     eax, ebx
0x180034824  jmp     short loc_18003483C
0x180034826  mov     rcx, [rbp+hObject]; hObject
0x18003482a  lea     rax, [rcx-1]
0x18003482e  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180034832  ja      short loc_18003483A
0x180034834  call    cs:__imp_CloseHandle
0x18003483a  xor     eax, eax
0x18003483c  lea     r11, [rsp+40h+var_s0]
0x180034841  mov     rbx, [r11+30h]
0x180034845  mov     rsi, [r11+40h]
0x180034849  mov     rsp, r11
0x18003484c  pop     r15
0x18003484e  pop     r14
0x180034850  pop     r12
0x180034852  pop     rdi
0x180034853  pop     rbp
0x180034854  retn
```
