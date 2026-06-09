# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x180004cb4`
- end: `0x180004f79`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `709`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation`

## callers

- `0x180005918`

## callees

- `0x180004cb4`
- `0x180005094`
- `0x180005640`
- `0x1800063e0`
- `0x180007234`
- `0x180007a3c`
- `0x180007b2c`
- `0x180008068`
- `0x180009c90`

## import_xrefs

- `KERNEL32!CreateMutexExW` at `0x180004d31`
- `KERNEL32!CreateMutexExW` at `0x180004d31`
- `KERNEL32!GetCurrentProcessId` at `0x180004cef`
- `KERNEL32!GetCurrentProcessId` at `0x180004cef`
- `KERNEL32!WaitForSingleObjectEx` at `0x180004d5d`
- `KERNEL32!WaitForSingleObjectEx` at `0x180004d5d`
- `KERNEL32!ReleaseMutex` at `0x180004de4`
- `KERNEL32!ReleaseMutex` at `0x180004e67`
- `KERNEL32!ReleaseMutex` at `0x180004eaa`
- `KERNEL32!ReleaseMutex` at `0x180004de4`
- `KERNEL32!ReleaseMutex` at `0x180004e67`
- `KERNEL32!ReleaseMutex` at `0x180004eaa`
- `KERNEL32!CloseHandle` at `0x180004dfb`
- `KERNEL32!CloseHandle` at `0x180004e85`
- `KERNEL32!CloseHandle` at `0x180004ec6`
- `KERNEL32!CloseHandle` at `0x180004dfb`
- `KERNEL32!CloseHandle` at `0x180004e85`
- `KERNEL32!CloseHandle` at `0x180004ec6`

## pseudocode

```c
__int64 __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(
        __int64 a1,
        _QWORD *a2)
{
  DWORD CurrentProcessId; // eax
  HANDLE Mutex; // rax
  wil::details *v5; // rcx
  HANDLE v6; // rbx
  DWORD v8; // eax
  void *v9; // rdx
  unsigned int v10; // r8d
  char *v11; // r9
  void *v12; // rdi
  int ValueInternal; // eax
  unsigned int v14; // r8d
  unsigned int v15; // esi
  unsigned int v16; // r8d
  unsigned int v17; // r8d
  unsigned int v18; // r8d
  const char *v19; // r9
  unsigned int v20; // r8d
  const char *v21; // r9
  _DWORD *v22; // rcx
  int v23; // eax
  unsigned int v24; // r8d
  unsigned int v25; // ebx
  unsigned int v26; // r8d
  const char *v27; // r9
  unsigned int v28; // r8d
  const char *v29; // r9
  unsigned int v30; // r8d
  const char *v31; // r9
  unsigned int v32; // r8d
  const char *v33; // r9
  int v34; // [rsp+20h] [rbp-E0h]
  int v35; // [rsp+20h] [rbp-E0h]
  HANDLE hObject; // [rsp+30h] [rbp-D0h] BYREF
  unsigned __int64 v37; // [rsp+38h] [rbp-C8h] BYREF
  WCHAR Name[264]; // [rsp+40h] [rbp-C0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+178h]

  *a2 = 0;
  CurrentProcessId = GetCurrentProcessId();
  StringCchPrintfW(Name, 0x104u, L"Local\\SM0:%lu:%lu:%hs", CurrentProcessId);
  Mutex = CreateMutexExW(0, Name, 0, 0x1F0001u);
  hObject = Mutex;
  v6 = Mutex;
  if ( !Mutex )
    return wil::details::GetLastErrorFailHr(v5);
  v8 = WaitForSingleObjectEx(Mutex, 0xFFFFFFFF, 0);
  if ( v8 == 258 )
  {
    v12 = 0;
  }
  else
  {
    if ( (v8 & 0xFFFFFF7F) != 0 )
      wil::details::in1diag3::FailFast_Unexpected(retaddr, v9, v10, v11);
    v12 = v6;
  }
  v37 = 0;
  ValueInternal = wil::details_abi::SemaphoreValue::TryGetValueInternal(Name, (bool)v9, &v37, (bool *)v11);
  v15 = ValueInternal;
  if ( ValueInternal < 0 )
  {
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x66, v14, (const char *)(unsigned int)ValueInternal, 120);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x6F, v16, (const char *)v15, v34);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x12E, v17, (const char *)v15, v35);
    if ( v12 && !ReleaseMutex(v12) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v18, v19);
    if ( !CloseHandle(v6) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v20, v21);
    return v15;
  }
  v22 = (_DWORD *)(4 * v37);
  if ( 4 * v37 )
  {
    *a2 = v22;
    ++*v22;
    goto LABEL_21;
  }
  v23 = wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::MakeAndInitialize(
          Name,
          &hObject,
          a2);
  v25 = v23;
  if ( v23 >= 0 )
  {
    v6 = hObject;
LABEL_21:
    if ( v12 && !ReleaseMutex(v12) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v30, v31);
    if ( v6 && !CloseHandle(v6) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v32, v33);
    return 0;
  }
  wil::details::in1diag3::Return_Hr(retaddr, (void *)0x137, v24, (const char *)(unsigned int)v23, 120);
  if ( v12 && !ReleaseMutex(v12) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v26, v27);
  if ( hObject && !CloseHandle(hObject) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v28, v29);
  return v25;
}

```

## disassembly

```asm
0x180004cb4  mov     [rsp-8+arg_10], rbx
0x180004cb9  mov     [rsp-8+arg_18], rsi
0x180004cbe  push    rbp
0x180004cbf  push    rdi
0x180004cc0  push    r14
0x180004cc2  lea     rbp, [rsp-160h]
0x180004cca  sub     rsp, 260h
0x180004cd1  mov     rax, cs:__security_cookie
0x180004cd8  xor     rax, rsp
0x180004cdb  mov     [rbp+170h+var_20], rax
0x180004ce2  mov     r14, rdx
0x180004ce5  mov     qword ptr [rdx], 0
0x180004cec  mov     rbx, rcx
0x180004cef  call    cs:__imp_GetCurrentProcessId
0x180004cf6  nop     dword ptr [rax+rax+00h]
0x180004cfb  mov     [rsp+270h+var_248], rbx
0x180004d00  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180004d07  mov     r9d, eax
0x180004d0a  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x180004d12  mov     edx, 104h; unsigned __int64
0x180004d17  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180004d1c  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180004d21  mov     r9d, 1F0001h; dwDesiredAccess
0x180004d27  lea     rdx, [rsp+270h+Name]; lpName
0x180004d2c  xor     r8d, r8d; dwFlags
0x180004d2f  xor     ecx, ecx; lpMutexAttributes
0x180004d31  call    cs:__imp_CreateMutexExW
0x180004d38  nop     dword ptr [rax+rax+00h]
0x180004d3d  mov     [rsp+270h+hObject], rax
0x180004d42  mov     rbx, rax
0x180004d45  test    rax, rax
0x180004d48  jnz     short loc_180004D54
0x180004d4a  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180004d4f  jmp     loc_180004ED8
0x180004d54  xor     r8d, r8d; bAlertable
0x180004d57  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180004d5a  mov     rcx, rbx; hHandle
0x180004d5d  call    cs:__imp_WaitForSingleObjectEx
0x180004d64  nop     dword ptr [rax+rax+00h]
0x180004d69  cmp     eax, 102h
0x180004d6e  jz      short loc_180004D80
0x180004d70  test    eax, 0FFFFFF7Fh
0x180004d75  jnz     loc_180004F12
0x180004d7b  mov     rdi, rbx
0x180004d7e  jmp     short loc_180004D82
0x180004d80  xor     edi, edi
0x180004d82  lea     r8, [rsp+270h+var_238]; unsigned __int64 *
0x180004d87  mov     [rsp+270h+var_238], 0
0x180004d90  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180004d95  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x180004d9a  mov     esi, eax
0x180004d9c  test    eax, eax
0x180004d9e  jns     short loc_180004E16
0x180004da0  mov     rcx, [rbp+178h]; this
0x180004da7  mov     r9d, eax; char *
0x180004daa  mov     edx, 66h ; 'f'; void *
0x180004daf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004db4  mov     rcx, [rbp+178h]; this
0x180004dbb  mov     r9d, esi; char *
0x180004dbe  mov     edx, 6Fh ; 'o'; void *
0x180004dc3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004dc8  mov     rcx, [rbp+178h]; this
0x180004dcf  mov     r9d, esi; char *
0x180004dd2  mov     edx, 12Eh; void *
0x180004dd7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004ddc  test    rdi, rdi
0x180004ddf  jz      short loc_180004DF8
0x180004de1  mov     rcx, rdi; hMutex
0x180004de4  call    cs:__imp_ReleaseMutex
0x180004deb  nop     dword ptr [rax+rax+00h]
0x180004df0  test    eax, eax
0x180004df2  jz      loc_180004F1F
0x180004df8  mov     rcx, rbx; hObject
0x180004dfb  call    cs:__imp_CloseHandle
0x180004e02  nop     dword ptr [rax+rax+00h]
0x180004e07  test    eax, eax
0x180004e09  jz      loc_180004F31
0x180004e0f  mov     eax, esi
0x180004e11  jmp     loc_180004ED8
0x180004e16  mov     rax, [rsp+270h+var_238]
0x180004e1b  lea     rcx, ds:0[rax*4]
0x180004e23  test    rcx, rcx
0x180004e26  jz      short loc_180004E33
0x180004e28  mov     [r14], rcx
0x180004e2b  mov     eax, [rcx]
0x180004e2d  inc     eax
0x180004e2f  mov     [rcx], eax
0x180004e31  jmp     short loc_180004EA2
0x180004e33  mov     r8, r14
0x180004e36  lea     rdx, [rsp+270h+hObject]
0x180004e3b  lea     rcx, [rsp+270h+Name]
0x180004e40  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x180004e45  mov     ebx, eax
0x180004e47  test    eax, eax
0x180004e49  jns     short loc_180004E9D
0x180004e4b  mov     rcx, [rbp+178h]; this
0x180004e52  mov     r9d, eax; char *
0x180004e55  mov     edx, 137h; void *
0x180004e5a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004e5f  test    rdi, rdi
0x180004e62  jz      short loc_180004E7B
0x180004e64  mov     rcx, rdi; hMutex
0x180004e67  call    cs:__imp_ReleaseMutex
0x180004e6e  nop     dword ptr [rax+rax+00h]
0x180004e73  test    eax, eax
0x180004e75  jz      loc_180004F43
0x180004e7b  mov     rcx, [rsp+270h+hObject]; hObject
0x180004e80  test    rcx, rcx
0x180004e83  jz      short loc_180004E99
0x180004e85  call    cs:__imp_CloseHandle
0x180004e8c  nop     dword ptr [rax+rax+00h]
0x180004e91  test    eax, eax
0x180004e93  jz      loc_180004F55
0x180004e99  mov     eax, ebx
0x180004e9b  jmp     short loc_180004ED8
0x180004e9d  mov     rbx, [rsp+270h+hObject]
0x180004ea2  test    rdi, rdi
0x180004ea5  jz      short loc_180004EBE
0x180004ea7  mov     rcx, rdi; hMutex
0x180004eaa  call    cs:__imp_ReleaseMutex
0x180004eb1  nop     dword ptr [rax+rax+00h]
0x180004eb6  test    eax, eax
0x180004eb8  jz      loc_180004F67
0x180004ebe  test    rbx, rbx
0x180004ec1  jz      short loc_180004ED6
0x180004ec3  mov     rcx, rbx; hObject
0x180004ec6  call    cs:__imp_CloseHandle
0x180004ecd  nop     dword ptr [rax+rax+00h]
0x180004ed2  test    eax, eax
0x180004ed4  jz      short loc_180004F00
0x180004ed6  xor     eax, eax
0x180004ed8  mov     rcx, [rbp+170h+var_20]
0x180004edf  xor     rcx, rsp; StackCookie
0x180004ee2  call    __security_check_cookie
0x180004ee7  lea     r11, [rsp+270h+var_10]
0x180004eef  mov     rbx, [r11+30h]
0x180004ef3  mov     rsi, [r11+38h]
0x180004ef7  mov     rsp, r11
0x180004efa  pop     r14
0x180004efc  pop     rdi
0x180004efd  pop     rbp
0x180004efe  retn
0x180004f00  mov     rcx, [rbp+178h]; this
0x180004f07  mov     edx, 0A0Bh; void *
0x180004f0c  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180004f12  mov     rcx, [rbp+178h]; this
0x180004f19  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x180004f1f  mov     rcx, [rbp+178h]; this
0x180004f26  mov     edx, 0A15h; void *
0x180004f2b  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180004f31  mov     rcx, [rbp+178h]; this
0x180004f38  mov     edx, 0A0Bh; void *
0x180004f3d  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180004f43  mov     rcx, [rbp+178h]; this
0x180004f4a  mov     edx, 0A15h; void *
0x180004f4f  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180004f55  mov     rcx, [rbp+178h]; this
0x180004f5c  mov     edx, 0A0Bh; void *
0x180004f61  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180004f67  mov     rcx, [rbp+178h]; this
0x180004f6e  mov     edx, 0A15h; void *
0x180004f73  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
