# CompletionHandler::Invoke(Windows::Foundation::IAsyncOperationWithProgress<Windows::Management::Deployment::DeploymentResult *,Windows::Management::Deployment::DeploymentProgress> *,ABI::Windows::Foundation::AsyncStatus)

- ea: `0x18004cf20`
- end: `0x18004d022`
- name: `?Invoke@CompletionHandler@@UEAAJPEAU?$IAsyncOperationWithProgress@PEAVDeploymentResult@Deployment@Management@Windows@@UDeploymentProgress@234@@Foundation@Windows@@W4AsyncStatus@34ABI@@@Z`
- size: `258`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x180003a00`
- `0x18000a008`
- `0x18000a024`
- `0x18004cf20`
- `0x18006a010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18004cfc2`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18004cfc2`

## string_xrefs

- `0x18004d010`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x18004cf6e`: `onecore\base\languageoverlay\services\languageoverlayservice\lib\lxplanguageresourcesprovider.cpp`
- `0x18004cfab`: `onecore\base\languageoverlay\services\languageoverlayservice\lib\lxplanguageresourcesprovider.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CompletionHandler::Invoke(__int64 a1, __int64 a2)
{
  int v3; // eax
  int v4; // ebx
  int *v5; // rdi
  int v6; // eax
  const char *v7; // r9
  __int64 v8; // rcx
  __int64 v10; // [rsp+20h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  v10 = 0;
  v3 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)a2 + 80LL))(a2, &v10);
  v4 = v3;
  if ( v3 >= 0 )
  {
    v5 = (int *)(a1 + 24);
    v6 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v10 + 64LL))(v10, a1 + 24);
    v4 = v6;
    if ( v6 >= 0 )
      goto LABEL_6;
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0xD5,
      (unsigned int)"onecore\\base\\languageoverlay\\services\\languageoverlayservice\\lib\\lxplanguageresourcesprovider.cpp",
      (const char *)(unsigned int)v6,
      v10);
  }
  else
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0xD1,
      (unsigned int)"onecore\\base\\languageoverlay\\services\\languageoverlayservice\\lib\\lxplanguageresourcesprovider.cpp",
      (const char *)(unsigned int)v3,
      v10);
    v5 = (int *)(a1 + 24);
  }
  *v5 = v4;
LABEL_6:
  if ( !SetEvent(*(HANDLE *)(a1 + 16)) )
    wil::details::in1diag3::_FailFast_GetLastError(
      retaddr,
      (void *)0xA01,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
      v7);
  v8 = v10;
  if ( v10 )
  {
    v10 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
  }
  return 0;
}

```

## disassembly

```asm
0x18004cf20  mov     r11, rsp
0x18004cf23  mov     [r11+18h], rbx
0x18004cf27  mov     [r11+20h], rsi
0x18004cf2b  push    rdi
0x18004cf2c  sub     rsp, 30h
0x18004cf30  mov     rax, cs:__security_cookie
0x18004cf37  xor     rax, rsp
0x18004cf3a  mov     [rsp+38h+var_10], rax
0x18004cf3f  mov     r8, rdx
0x18004cf42  mov     rsi, rcx
0x18004cf45  mov     qword ptr [r11-18h], 0
0x18004cf4d  mov     rax, [rdx]
0x18004cf50  lea     rdx, [r11-18h]
0x18004cf54  mov     rcx, r8
0x18004cf57  mov     rax, [rax+50h]
0x18004cf5b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004cf60  mov     ebx, eax
0x18004cf62  mov     rcx, [rsp+38h]; this
0x18004cf67  test    eax, eax
0x18004cf69  jns     short loc_18004CF85
0x18004cf6b  mov     r9d, eax; char *
0x18004cf6e  lea     r8, aOnecoreBaseLan; "onecore\\base\\languageoverlay\\service"...
0x18004cf75  mov     edx, 0D1h; void *
0x18004cf7a  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18004cf7f  lea     rdi, [rsi+18h]
0x18004cf83  jmp     short loc_18004CFBC
0x18004cf85  mov     rcx, [rsp+38h+var_18]
0x18004cf8a  lea     rdi, [rsi+18h]
0x18004cf8e  mov     rax, [rcx]
0x18004cf91  mov     rdx, rdi
0x18004cf94  mov     rax, [rax+40h]
0x18004cf98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004cf9d  mov     ebx, eax
0x18004cf9f  mov     rcx, [rsp+38h]; this
0x18004cfa4  test    eax, eax
0x18004cfa6  jns     short loc_18004CFBE
0x18004cfa8  mov     r9d, eax; char *
0x18004cfab  lea     r8, aOnecoreBaseLan; "onecore\\base\\languageoverlay\\service"...
0x18004cfb2  mov     edx, 0D5h; void *
0x18004cfb7  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18004cfbc  mov     [rdi], ebx
0x18004cfbe  mov     rcx, [rsi+10h]; hEvent
0x18004cfc2  call    cs:__imp_SetEvent
0x18004cfc8  mov     rcx, [rsp+38h]; this
0x18004cfcd  test    eax, eax
0x18004cfcf  jz      short loc_18004D010
0x18004cfd1  mov     rcx, [rsp+38h+var_18]
0x18004cfd6  test    rcx, rcx
0x18004cfd9  jz      short loc_18004CFF1
0x18004cfdb  mov     [rsp+38h+var_18], 0
0x18004cfe4  mov     rax, [rcx]
0x18004cfe7  mov     rax, [rax+10h]
0x18004cfeb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004cff0  nop
0x18004cff1  xor     eax, eax
0x18004cff3  mov     rcx, [rsp+38h+var_10]
0x18004cff8  xor     rcx, rsp; StackCookie
0x18004cffb  call    __security_check_cookie
0x18004d000  mov     rbx, [rsp+38h+arg_10]
0x18004d005  mov     rsi, [rsp+38h+arg_18]
0x18004d00a  add     rsp, 30h
0x18004d00e  pop     rdi
0x18004d00f  retn
0x18004d010  lea     r8, aOnecoreInterna_2; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18004d017  mov     edx, 0A01h; void *
0x18004d01c  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
