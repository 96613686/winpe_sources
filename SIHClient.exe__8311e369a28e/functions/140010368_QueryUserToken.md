# QueryUserToken

- ea: `0x140010368`
- end: `0x140010483`
- name: `QueryUserToken`
- size: `283`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x1400101e8`
- `0x14003870c`
- `0x140039010`

## callees

- `0x140008de4`
- `0x14000e4d0`
- `0x140010368`
- `0x1400154b4`
- `0x14001912c`
- `0x140045dc0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400103c8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400103c8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14001045e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14001045e`

## string_xrefs

- `0x1400103af`: `C:\__w\1\s\src\Client\lib\util\SecurityUtil.cpp`
- `0x14001040a`: `C:\__w\1\s\src\Client\lib\util\SecurityUtil.cpp`

## pseudocode

```c
__int64 __fastcall QueryUserToken(WUSystemInterfaceHelper *a1, _QWORD *a2, __int64 a3, int *a4)
{
  unsigned int v4; // ebx
  int v6; // eax
  int v7; // edi
  DWORD LastError; // eax
  char *v9; // rcx
  HANDLE v10; // rdx
  unsigned int v12; // [rsp+20h] [rbp-58h]
  HANDLE hObject; // [rsp+40h] [rbp-38h] BYREF
  void *v14; // [rsp+48h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  v4 = 0;
  *a2 = 0;
  LODWORD(v14) = 0;
  hObject = 0;
  v6 = WUSystemInterfaceHelper::QueryUserToken(a1, (unsigned int)&hObject, &v14, a4);
  v7 = v6;
  if ( v6 >= 0 )
  {
    LastError = GetLastError();
    v9 = (char *)hObject;
    v10 = hObject;
    if ( hObject && hObject != (HANDLE)-1LL )
    {
      v9 = 0;
      hObject = 0;
      *a2 = v10;
      goto LABEL_13;
    }
    if ( LastError == 1008 || LastError == 7022 || LastError == 2 )
    {
      WUTrace(0, 0, 32, 5, 0, L"IsUserSession: Session %d does not exist or is not a user session");
      v7 = -2147023888;
    }
    else
    {
      if ( !LastError )
        goto LABEL_13;
      v7 = wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)0x148,
             (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\SecurityUtil.cpp",
             (const char *)LastError,
             v12);
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x12D,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\SecurityUtil.cpp",
      (const char *)(unsigned int)v6,
      v12);
  }
  v9 = (char *)hObject;
  v4 = v7;
LABEL_13:
  if ( (unsigned __int64)(v9 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(v9);
  return v4;
}

```

## disassembly

```asm
0x140010368  mov     r11, rsp
0x14001036b  mov     [r11+18h], rbx
0x14001036f  push    rbp
0x140010370  push    rsi
0x140010371  push    rdi
0x140010372  sub     rsp, 60h
0x140010376  mov     rax, cs:__security_cookie
0x14001037d  xor     rax, rsp
0x140010380  mov     [rsp+78h+var_28], rax
0x140010385  xor     ebx, ebx
0x140010387  lea     r8, [r11-30h]; void **
0x14001038b  mov     [rdx], rbx
0x14001038e  mov     rsi, rdx
0x140010391  lea     rdx, [r11-38h]; unsigned int
0x140010395  mov     dword ptr [rsp+78h+var_30], ebx
0x140010399  mov     ebp, ecx
0x14001039b  mov     [r11-38h], rbx
0x14001039f  call    ?QueryUserToken@WUSystemInterfaceHelper@@YAJKPEAPEAXPEAH@Z; WUSystemInterfaceHelper::QueryUserToken(ulong,void * *,int *)
0x1400103a4  mov     edi, eax
0x1400103a6  test    eax, eax
0x1400103a8  jns     short loc_1400103C8
0x1400103aa  mov     rcx, [rsp+78h]; this
0x1400103af  lea     r8, aCW1SSrcClientL_23; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x1400103b6  mov     r9d, eax; char *
0x1400103b9  mov     edx, 12Dh; void *
0x1400103be  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400103c3  jmp     loc_14001044D
0x1400103c8  call    cs:__imp_GetLastError
0x1400103ce  mov     rcx, [rsp+78h+hObject]
0x1400103d3  mov     rdx, rcx
0x1400103d6  test    rcx, rcx
0x1400103d9  jz      short loc_1400103EE
0x1400103db  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1400103df  jz      short loc_1400103EE
0x1400103e1  mov     rcx, rbx
0x1400103e4  mov     [rsp+78h+hObject], rbx
0x1400103e9  mov     [rsi], rdx
0x1400103ec  jmp     short loc_140010454
0x1400103ee  cmp     eax, 3F0h
0x1400103f3  jz      short loc_140010422
0x1400103f5  cmp     eax, 1B6Eh
0x1400103fa  jz      short loc_140010422
0x1400103fc  cmp     eax, 2
0x1400103ff  jz      short loc_140010422
0x140010401  test    eax, eax
0x140010403  jz      short loc_140010454
0x140010405  mov     rcx, [rsp+78h]; this
0x14001040a  lea     r8, aCW1SSrcClientL_23; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x140010411  mov     r9d, eax; char *
0x140010414  mov     edx, 148h; void *
0x140010419  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x14001041e  mov     edi, eax
0x140010420  jmp     short loc_14001044D
0x140010422  xor     edx, edx
0x140010424  mov     [rsp+78h+var_48], ebp
0x140010428  lea     rax, aIsusersessionS; "IsUserSession: Session %d does not exis"...
0x14001042f  xor     ecx, ecx
0x140010431  mov     [rsp+78h+var_50], rax
0x140010436  mov     [rsp+78h+var_58], rbx
0x14001043b  lea     r9d, [rdx+5]
0x14001043f  lea     r8d, [rdx+20h]
0x140010443  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x140010448  mov     edi, 800703F0h
0x14001044d  mov     rcx, [rsp+78h+hObject]; hObject
0x140010452  mov     ebx, edi
0x140010454  lea     rdx, [rcx-1]
0x140010458  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x14001045c  ja      short loc_140010464
0x14001045e  call    cs:__imp_CloseHandle
0x140010464  mov     eax, ebx
0x140010466  mov     rcx, [rsp+78h+var_28]
0x14001046b  xor     rcx, rsp; StackCookie
0x14001046e  call    __security_check_cookie
0x140010473  mov     rbx, [rsp+78h+arg_10]
0x14001047b  add     rsp, 60h
0x14001047f  pop     rdi
0x140010480  pop     rsi
0x140010481  pop     rbp
0x140010482  retn
```
