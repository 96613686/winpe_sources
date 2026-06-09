# StateRepositoryDoMaintenanceTasks

- ea: `0x180019250`
- end: `0x18001939a`
- name: `StateRepositoryDoMaintenanceTasks`
- size: `330`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `service_task`

## callees

- `0x18000182c`
- `0x180001858`
- `0x180002980`
- `0x18000719c`
- `0x18000c58c`
- `0x180018468`
- `0x1800191a4`
- `0x180019250`

## import_xrefs

- `api-ms-win-core-winrt-l1-1-0!RoInitialize` at `0x180019275`
- `api-ms-win-core-winrt-l1-1-0!RoInitialize` at `0x180019275`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x18001935e`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x18001935e`

## string_xrefs

- `0x180019385`: `onecore\internal\sdk\inc\wil\opensource/wil/resource.h`
- `0x180019296`: `onecore\base\appmodel\staterepository\winrt\inproc\lib\maintenancetasks.cpp`

## pseudocode

```c
__int64 StateRepositoryDoMaintenanceTasks()
{
  int v0; // eax
  int v1; // eax
  int v2; // ebx
  const struct _tlgProvider_t *v3; // rax
  __int64 v4; // r10
  unsigned __int8 *v5; // rdx
  __int64 v6; // rcx
  const struct _tlgProvider_t *v7; // rax
  int v9; // [rsp+20h] [rbp-19h]
  ULONG v10; // [rsp+20h] [rbp-19h]
  int v11; // [rsp+30h] [rbp-9h] BYREF
  __int64 v12; // [rsp+38h] [rbp-1h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v13; // [rsp+40h] [rbp+7h] BYREF
  __int64 *v14; // [rsp+60h] [rbp+27h]
  __int64 v15; // [rsp+68h] [rbp+2Fh]
  __int64 *v16; // [rsp+70h] [rbp+37h]
  __int64 v17; // [rsp+78h] [rbp+3Fh]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+5Fh]

  v0 = RoInitialize(1);
  if ( v0 < 0 )
    wil::details::in1diag3::_FailFast_Hr(
      retaddr,
      (void *)0x14E9,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/resource.h",
      (const char *)(unsigned int)v0,
      v9);
  v1 = DoMaintenanceTasks();
  v2 = v1;
  if ( v1 >= 0 )
  {
    v7 = StateRepository::Tracing::Client::Provider();
    if ( *(_DWORD *)v7 > 5u )
    {
      v15 = 8;
      v14 = &v12;
      v5 = (unsigned __int8 *)&unk_1800307C9;
      v6 = (__int64)v7;
      v10 = 3;
      goto LABEL_8;
    }
  }
  else
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x35,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\winrt\\inproc\\lib\\maintenancetasks.cpp",
      (const char *)(unsigned int)v1,
      v9);
    v3 = StateRepository::Tracing::Client::Provider();
    if ( *(_DWORD *)v3 > 2u && (unsigned __int8)tlgKeywordOn(v3, 0x200000000000LL) )
    {
      v11 = v2;
      v15 = 4;
      v16 = &v12;
      v5 = (unsigned __int8 *)&unk_180030774;
      v17 = 8;
      v14 = (__int64 *)&v11;
      v10 = 4;
      v6 = v4;
LABEL_8:
      v12 = 0x1000000;
      tlgWriteTransfer_EventWriteTransfer(v6, v5, 0, 0, v10, &v13);
    }
  }
  return RoUninitialize();
}

```

## disassembly

```asm
0x180019250  mov     [rsp-8+arg_0], rbx
0x180019255  push    rbp
0x180019256  lea     rbp, [rsp-57h]
0x18001925b  sub     rsp, 90h
0x180019262  mov     rax, cs:__security_cookie
0x180019269  xor     rax, rsp
0x18001926c  mov     [rbp+57h+var_10], rax
0x180019270  mov     ecx, 1
0x180019275  call    cs:__imp_RoInitialize
0x18001927b  test    eax, eax
0x18001927d  js      loc_180019381
0x180019283  call    DoMaintenanceTasks
0x180019288  mov     ebx, eax
0x18001928a  test    eax, eax
0x18001928c  jns     loc_180019314
0x180019292  mov     rcx, [rbp+5Fh]; this
0x180019296  lea     r8, aOnecoreBaseApp_12; "onecore\\base\\appmodel\\staterepositor"...
0x18001929d  mov     r9d, eax; char *
0x1800192a0  mov     edx, 35h ; '5'; void *
0x1800192a5  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800192aa  call    ?Provider@Client@Tracing@StateRepository@@SAPEBU_tlgProvider_t@@XZ; StateRepository::Tracing::Client::Provider(void)
0x1800192af  mov     r10, rax
0x1800192b2  mov     ecx, [rax]
0x1800192b4  cmp     ecx, 2
0x1800192b7  jbe     loc_18001935E
0x1800192bd  mov     rdx, 200000000000h
0x1800192c7  mov     rcx, rax
0x1800192ca  call    _tlgKeywordOn
0x1800192cf  test    al, al
0x1800192d1  jz      loc_18001935E
0x1800192d7  mov     ecx, 4
0x1800192dc  mov     [rbp+57h+var_60], ebx
0x1800192df  lea     rax, [rbp+57h+var_58]
0x1800192e3  mov     [rbp+57h+var_28], rcx
0x1800192e7  mov     [rbp+57h+var_20], rax
0x1800192eb  lea     rdx, unk_180030774
0x1800192f2  lea     rax, [rbp+57h+var_60]
0x1800192f6  mov     [rbp+57h+var_18], 8
0x1800192fe  mov     [rbp+57h+var_30], rax
0x180019302  lea     rax, [rbp+57h+var_50]
0x180019306  mov     [rsp+90h+var_68], rax
0x18001930b  mov     [rsp+90h+var_70], ecx
0x18001930f  mov     rcx, r10
0x180019312  jmp     short loc_18001934B
0x180019314  call    ?Provider@Client@Tracing@StateRepository@@SAPEBU_tlgProvider_t@@XZ; StateRepository::Tracing::Client::Provider(void)
0x180019319  mov     ecx, [rax]
0x18001931b  cmp     ecx, 5
0x18001931e  jbe     short loc_18001935E
0x180019320  lea     rcx, [rbp+57h+var_58]
0x180019324  mov     [rbp+57h+var_28], 8
0x18001932c  mov     [rbp+57h+var_30], rcx
0x180019330  lea     rdx, unk_1800307C9
0x180019337  lea     rcx, [rbp+57h+var_50]
0x18001933b  mov     [rsp+90h+var_68], rcx
0x180019340  mov     rcx, rax
0x180019343  mov     [rsp+90h+var_70], 3
0x18001934b  xor     r9d, r9d
0x18001934e  mov     [rbp+57h+var_58], 1000000h
0x180019356  xor     r8d, r8d
0x180019359  call    _tlgWriteTransfer_EventWriteTransfer
0x18001935e  call    cs:__imp_RoUninitialize
0x180019364  mov     rcx, [rbp+57h+var_10]
0x180019368  xor     rcx, rsp; StackCookie
0x18001936b  call    __security_check_cookie
0x180019370  mov     rbx, [rsp+90h+arg_0]
0x180019378  add     rsp, 90h
0x18001937f  pop     rbp
0x180019380  retn
0x180019381  mov     rcx, [rbp+5Fh]; this
0x180019385  lea     r8, aOnecoreInterna_2; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18001938c  mov     r9d, eax; char *
0x18001938f  mov     edx, 14E9h; void *
0x180019394  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
```
