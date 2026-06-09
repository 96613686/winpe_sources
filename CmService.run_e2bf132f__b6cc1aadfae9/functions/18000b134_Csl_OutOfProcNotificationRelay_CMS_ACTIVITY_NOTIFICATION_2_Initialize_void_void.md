# Csl::OutOfProcNotificationRelay<_CMS_ACTIVITY_NOTIFICATION,2>::Initialize(void *,void *)

- ea: `0x18000b134`
- end: `0x18000b2c2`
- name: `?Initialize@?$OutOfProcNotificationRelay@U_CMS_ACTIVITY_NOTIFICATION@@$01@Csl@@QEAAJPEAX0@Z`
- size: `398`
- prototype: `__int64 __fastcall(PVOID pv, PSID pSid, PSID)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x180017b70`

## callees

- `0x180004bd0`
- `0x180009884`
- `0x18000b134`
- `0x18000da68`
- `0x18000da88`

## import_xrefs

- `ntdll!NtDeleteWnfStateName` at `0x18000b1d0`
- `ntdll!NtDeleteWnfStateName` at `0x18000b265`
- `ntdll!NtDeleteWnfStateName` at `0x18000b287`
- `ntdll!NtDeleteWnfStateName` at `0x18000b1d0`
- `ntdll!NtDeleteWnfStateName` at `0x18000b265`
- `ntdll!NtDeleteWnfStateName` at `0x18000b287`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18000b164`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18000b164`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18000b1df`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18000b219`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18000b29b`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18000b1df`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18000b219`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18000b29b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b208`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b254`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b208`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b254`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000b227`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000b273`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000b227`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000b273`

## pseudocode

```c
__int64 __fastcall Csl::OutOfProcNotificationRelay<_CMS_ACTIVITY_NOTIFICATION,2>::Initialize(
        char *pv,
        PSID pSid,
        PSID a3)
{
  struct _TP_WORK *ThreadpoolWork; // rbx
  const char *v7; // r9
  int v9; // eax
  unsigned int v10; // edi
  struct _TP_WORK **v11; // rsi
  struct _TP_WORK *v12; // rbp
  DWORD LastError; // edi
  __int64 *v14; // r14
  __int64 v15; // rsi
  DWORD v16; // edi
  int v17; // [rsp+20h] [rbp-48h] BYREF
  __int64 v18; // [rsp+28h] [rbp-40h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  ThreadpoolWork = CreateThreadpoolWork(
                     Csl::OutOfProcNotificationRelay<_CMS_ACTIVITY_NOTIFICATION,2>::WnfPublisherThread,
                     pv,
                     0);
  if ( !ThreadpoolWork )
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)0x2B0,
             (unsigned int)"onecore\\base\\gendrv\\silos\\csl\\lib\\CslNotification.h",
             v7);
  v18 = 0;
  v9 = Csl::OutOfProcNotificationRelay<_CMS_ACTIVITY_NOTIFICATION,2>::CreateWnfStateName(pSid, a3, &v18);
  v10 = v9;
  if ( v9 >= 0 )
  {
    v11 = (struct _TP_WORK **)(pv + 96);
    if ( pv + 96 != (char *)&v17 )
    {
      v12 = *v11;
      if ( *v11 )
      {
        LastError = GetLastError();
        CloseThreadpoolWork(v12);
        SetLastError(LastError);
      }
      *v11 = ThreadpoolWork;
      ThreadpoolWork = 0;
    }
    v14 = (__int64 *)(pv + 88);
    if ( v14 != &v18 )
    {
      v15 = v18;
      v18 = 0;
      v16 = GetLastError();
      NtDeleteWnfStateName(v14);
      SetLastError(v16);
      *v14 = v15;
    }
    NtDeleteWnfStateName(&v18);
    if ( ThreadpoolWork )
      CloseThreadpoolWork(ThreadpoolWork);
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2B4,
      (unsigned int)"onecore\\base\\gendrv\\silos\\csl\\lib\\CslNotification.h",
      (const char *)(unsigned int)v9,
      v17);
    NtDeleteWnfStateName(&v18);
    CloseThreadpoolWork(ThreadpoolWork);
    return v10;
  }
}

```

## disassembly

```asm
0x18000b134  push    rbx
0x18000b136  push    rbp
0x18000b137  push    rsi
0x18000b138  push    rdi
0x18000b139  push    r14
0x18000b13b  sub     rsp, 40h
0x18000b13f  mov     rax, cs:__security_cookie
0x18000b146  xor     rax, rsp
0x18000b149  mov     [rsp+68h+var_38], rax
0x18000b14e  mov     rdi, rdx
0x18000b151  mov     rsi, r8
0x18000b154  mov     rdx, rcx; pv
0x18000b157  mov     r14, rcx
0x18000b15a  lea     rcx, ?WnfPublisherThread@?$OutOfProcNotificationRelay@U_CMS_ACTIVITY_NOTIFICATION@@$01@Csl@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x18000b161  xor     r8d, r8d; pcbe
0x18000b164  call    cs:__imp_CreateThreadpoolWork
0x18000b16b  nop     dword ptr [rax+rax+00h]
0x18000b170  mov     rbx, rax
0x18000b173  test    rax, rax
0x18000b176  jnz     short loc_18000B193
0x18000b178  mov     rcx, [rsp+68h]; this
0x18000b17d  lea     r8, aOnecoreBaseGen_5; "onecore\\base\\gendrv\\silos\\csl\\lib"...
0x18000b184  mov     edx, 2B0h; void *
0x18000b189  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000b18e  jmp     loc_18000B2A9
0x18000b193  lea     r8, [rsp+68h+var_40]
0x18000b198  mov     [rsp+68h+var_40], 0
0x18000b1a1  mov     rdx, rsi; PSID
0x18000b1a4  mov     rcx, rdi; pSid
0x18000b1a7  call    ?CreateWnfStateName@?$OutOfProcNotificationRelay@U_CMS_ACTIVITY_NOTIFICATION@@$01@Csl@@CAJPEAX0AEAV?$unique_struct@U_WNF_STATE_NAME@@P6AJPEBU1@@Z$1?NtDeleteWnfStateName@@YAJ0@Z$$T$0A@@wil@@@Z; Csl::OutOfProcNotificationRelay<_CMS_ACTIVITY_NOTIFICATION,2>::CreateWnfStateName(void *,void *,wil::unique_struct<_WNF_STATE_NAME,long (*)(_WNF_STATE_NAME const *),&NtDeleteWnfStateName(_WNF_STATE_NAME const *),std::nullptr_t,0> &)
0x18000b1ac  mov     edi, eax
0x18000b1ae  test    eax, eax
0x18000b1b0  jns     short loc_18000B1F2
0x18000b1b2  mov     rcx, [rsp+68h]; this
0x18000b1b7  lea     r8, aOnecoreBaseGen_5; "onecore\\base\\gendrv\\silos\\csl\\lib"...
0x18000b1be  mov     r9d, eax; char *
0x18000b1c1  mov     edx, 2B4h; void *
0x18000b1c6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000b1cb  lea     rcx, [rsp+68h+var_40]
0x18000b1d0  call    cs:__imp_NtDeleteWnfStateName
0x18000b1d7  nop     dword ptr [rax+rax+00h]
0x18000b1dc  mov     rcx, rbx; pwk
0x18000b1df  call    cs:__imp_CloseThreadpoolWork
0x18000b1e6  nop     dword ptr [rax+rax+00h]
0x18000b1eb  mov     eax, edi
0x18000b1ed  jmp     loc_18000B2A9
0x18000b1f2  lea     rsi, [r14+60h]
0x18000b1f6  lea     rax, [rsp+68h+var_48]
0x18000b1fb  cmp     rsi, rax
0x18000b1fe  jz      short loc_18000B238
0x18000b200  mov     rbp, [rsi]
0x18000b203  test    rbp, rbp
0x18000b206  jz      short loc_18000B233
0x18000b208  call    cs:__imp_GetLastError
0x18000b20f  nop     dword ptr [rax+rax+00h]
0x18000b214  mov     rcx, rbp; pwk
0x18000b217  mov     edi, eax
0x18000b219  call    cs:__imp_CloseThreadpoolWork
0x18000b220  nop     dword ptr [rax+rax+00h]
0x18000b225  mov     ecx, edi; dwErrCode
0x18000b227  call    cs:__imp_SetLastError
0x18000b22e  nop     dword ptr [rax+rax+00h]
0x18000b233  mov     [rsi], rbx
0x18000b236  xor     ebx, ebx
0x18000b238  add     r14, 58h ; 'X'
0x18000b23c  lea     rax, [rsp+68h+var_40]
0x18000b241  cmp     r14, rax
0x18000b244  jz      short loc_18000B282
0x18000b246  mov     rsi, [rsp+68h+var_40]
0x18000b24b  mov     [rsp+68h+var_40], 0
0x18000b254  call    cs:__imp_GetLastError
0x18000b25b  nop     dword ptr [rax+rax+00h]
0x18000b260  mov     rcx, r14
0x18000b263  mov     edi, eax
0x18000b265  call    cs:__imp_NtDeleteWnfStateName
0x18000b26c  nop     dword ptr [rax+rax+00h]
0x18000b271  mov     ecx, edi; dwErrCode
0x18000b273  call    cs:__imp_SetLastError
0x18000b27a  nop     dword ptr [rax+rax+00h]
0x18000b27f  mov     [r14], rsi
0x18000b282  lea     rcx, [rsp+68h+var_40]
0x18000b287  call    cs:__imp_NtDeleteWnfStateName
0x18000b28e  nop     dword ptr [rax+rax+00h]
0x18000b293  test    rbx, rbx
0x18000b296  jz      short loc_18000B2A7
0x18000b298  mov     rcx, rbx; pwk
0x18000b29b  call    cs:__imp_CloseThreadpoolWork
0x18000b2a2  nop     dword ptr [rax+rax+00h]
0x18000b2a7  xor     eax, eax
0x18000b2a9  mov     rcx, [rsp+68h+var_38]
0x18000b2ae  xor     rcx, rsp; StackCookie
0x18000b2b1  call    __security_check_cookie
0x18000b2b6  add     rsp, 40h
0x18000b2ba  pop     r14
0x18000b2bc  pop     rdi
0x18000b2bd  pop     rsi
0x18000b2be  pop     rbp
0x18000b2bf  pop     rbx
0x18000b2c0  retn
```
