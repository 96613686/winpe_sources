# _lambda_1c7b36b977d94aa6517d4dc160f9388b_::operator()(ICreateObject * *)

- ea: `0x18000ab24`
- end: `0x18000ac4c`
- name: `??R_lambda_1c7b36b977d94aa6517d4dc160f9388b_@@QEBA@PEAPEAUICreateObject@@@Z`
- size: `296`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180009308`

## callees

- `0x18000ab24`
- `0x18000e270`
- `0x18000e2a0`
- `0x18000e2bc`
- `0x18002d3e8`
- `0x18004e010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000abe6`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000abe6`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18000ab76`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18000ab76`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18000abfa`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18000abfa`

## string_xrefs

- `0x18000aba1`: `shell\oobe\user\dll\oobebrokermanager.cpp`
- `0x18000ac13`: `shell\oobe\user\dll\oobebrokermanager.cpp`
- `0x18000ac25`: `shell\oobe\user\dll\oobebrokermanager.cpp`
- `0x18000ac3a`: `shell\oobe\user\dll\oobebrokermanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
HRESULT __fastcall _lambda_1c7b36b977d94aa6517d4dc160f9388b_::operator()(__int64 *a1, bool *a2)
{
  DWORD v4; // ebx
  __int64 v5; // rcx
  int v6; // eax
  const char *v7; // r9
  int IsCurrentProcessStronglyNamed; // eax
  __int64 v9; // rdi
  HRESULT result; // eax
  int ppv; // [rsp+20h] [rbp-28h]
  int ppva; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  HANDLE hToken; // [rsp+50h] [rbp+8h] BYREF

  v4 = 1048580;
  LOBYTE(hToken) = 0;
  v5 = *a1;
  if ( v5 )
  {
    hToken = 0;
    v6 = (*(__int64 (__fastcall **)(__int64, HANDLE *))(*(_QWORD *)v5 + 24LL))(v5, &hToken);
    if ( v6 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xDB,
        (unsigned int)"shell\\oobe\\user\\dll\\oobebrokermanager.cpp",
        (const char *)(unsigned int)v6,
        ppv);
    if ( !ImpersonateLoggedOnUser(hToken) )
      wil::details::in1diag3::_Throw_GetLastError(
        retaddr,
        (void *)0xDC,
        (unsigned int)"shell\\oobe\\user\\dll\\oobebrokermanager.cpp",
        v7);
  }
  else
  {
    IsCurrentProcessStronglyNamed = CallerIdentity::IsCurrentProcessStronglyNamed((CallerIdentity *)&hToken, a2);
    if ( IsCurrentProcessStronglyNamed >= 0 )
    {
      if ( (_BYTE)hToken )
        v4 = 9437188;
    }
    else
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0xDE,
        (unsigned int)"shell\\oobe\\user\\dll\\oobebrokermanager.cpp",
        (const char *)(unsigned int)IsCurrentProcessStronglyNamed,
        ppv);
    }
  }
  v9 = *a1;
  result = CoCreateInstance(
             &GUID_5f7f3f7b_1177_4d4b_b1db_bc6f671b8f25,
             0,
             v4,
             &GUID_75121952_e0d0_43e5_9380_1d80483acf72,
             (LPVOID *)a2);
  if ( result < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xEA,
      (unsigned int)"shell\\oobe\\user\\dll\\oobebrokermanager.cpp",
      (const char *)(unsigned int)result,
      ppva);
  if ( v9 )
    return RevertToSelf();
  return result;
}

```

## disassembly

```asm
0x18000ab24  mov     rax, rsp
0x18000ab27  mov     [rax+10h], rbx
0x18000ab2b  mov     [rax+18h], rsi
0x18000ab2f  push    rdi
0x18000ab30  sub     rsp, 40h
0x18000ab34  mov     rsi, rdx
0x18000ab37  mov     rdi, rcx
0x18000ab3a  mov     ebx, 100004h
0x18000ab3f  mov     byte ptr [rax+8], 0
0x18000ab43  mov     rcx, [rcx]
0x18000ab46  test    rcx, rcx
0x18000ab49  jz      short loc_18000AB8B
0x18000ab4b  mov     qword ptr [rax+8], 0
0x18000ab53  mov     rax, [rcx]
0x18000ab56  lea     rdx, [rsp+48h+hToken]
0x18000ab5b  mov     rax, [rax+18h]
0x18000ab5f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ab64  mov     rcx, [rsp+48h]; this
0x18000ab69  test    eax, eax
0x18000ab6b  js      loc_18000AC37
0x18000ab71  mov     rcx, [rsp+48h+hToken]; hToken
0x18000ab76  call    cs:__imp_ImpersonateLoggedOnUser
0x18000ab7c  mov     rcx, [rsp+48h]; this
0x18000ab81  test    eax, eax
0x18000ab83  jz      loc_18000AC25
0x18000ab89  jmp     short loc_18000ABC1
0x18000ab8b  lea     rcx, [rsp+48h+hToken]; this
0x18000ab90  call    ?IsCurrentProcessStronglyNamed@CallerIdentity@@YAJPEA_N@Z; CallerIdentity::IsCurrentProcessStronglyNamed(bool *)
0x18000ab95  mov     rcx, [rsp+48h]; this
0x18000ab9a  test    eax, eax
0x18000ab9c  jns     short loc_18000ABB4
0x18000ab9e  mov     r9d, eax; char *
0x18000aba1  lea     r8, aShellOobeUserD; "shell\\oobe\\user\\dll\\oobebrokermanag"...
0x18000aba8  mov     edx, 0DEh; void *
0x18000abad  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18000abb2  jmp     short loc_18000ABC1
0x18000abb4  mov     eax, 900004h
0x18000abb9  cmp     byte ptr [rsp+48h+hToken], 0
0x18000abbe  cmovnz  ebx, eax
0x18000abc1  mov     rdi, [rdi]
0x18000abc4  mov     [rsp+48h+var_18], rdi
0x18000abc9  mov     [rsp+48h+var_10], 1
0x18000abce  mov     qword ptr [rsp+48h+ppv], rsi; int
0x18000abd3  lea     r9, _GUID_75121952_e0d0_43e5_9380_1d80483acf72; riid
0x18000abda  mov     r8d, ebx; dwClsContext
0x18000abdd  xor     edx, edx; pUnkOuter
0x18000abdf  lea     rcx, _GUID_5f7f3f7b_1177_4d4b_b1db_bc6f671b8f25; rclsid
0x18000abe6  call    cs:__imp_CoCreateInstance
0x18000abec  mov     rcx, [rsp+48h]; this
0x18000abf1  test    eax, eax
0x18000abf3  js      short loc_18000AC10
0x18000abf5  test    rdi, rdi
0x18000abf8  jz      short loc_18000AC00
0x18000abfa  call    cs:__imp_RevertToSelf
0x18000ac00  mov     rbx, [rsp+48h+arg_8]
0x18000ac05  mov     rsi, [rsp+48h+arg_10]
0x18000ac0a  add     rsp, 40h
0x18000ac0e  pop     rdi
0x18000ac0f  retn
0x18000ac10  mov     r9d, eax; char *
0x18000ac13  lea     r8, aShellOobeUserD; "shell\\oobe\\user\\dll\\oobebrokermanag"...
0x18000ac1a  mov     edx, 0EAh; void *
0x18000ac1f  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18000ac25  lea     r8, aShellOobeUserD; "shell\\oobe\\user\\dll\\oobebrokermanag"...
0x18000ac2c  mov     edx, 0DCh; void *
0x18000ac31  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x18000ac37  mov     r9d, eax; char *
0x18000ac3a  lea     r8, aShellOobeUserD; "shell\\oobe\\user\\dll\\oobebrokermanag"...
0x18000ac41  mov     edx, 0DBh; void *
0x18000ac46  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
