# Appx::Packaging::Production::ProcessInParallel__lambda_23e8b1edb175e3d2b228e1a6bfa2f527___lambda_c32d057266adf508bbc79fb00cb0b29d___

- ea: `0x1800f1c30`
- end: `0x1800f1e0b`
- name: `Appx::Packaging::Production::ProcessInParallel__lambda_23e8b1edb175e3d2b228e1a6bfa2f527___lambda_c32d057266adf508bbc79fb00cb0b29d___`
- size: `475`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x1800f23ac`

## callees

- `0x1800133fc`
- `0x18006a900`
- `0x1800f1c30`
- `0x1800f202c`
- `0x1800f2534`
- `0x1800f2574`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolCleanupGroup` at `0x1800f1c94`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolCleanupGroup` at `0x1800f1c94`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroupMembers` at `0x1800f1d38`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroupMembers` at `0x1800f1dc8`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroupMembers` at `0x1800f1d38`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroupMembers` at `0x1800f1dc8`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800f1d03`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800f1d03`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800f1d17`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800f1d17`

## pseudocode

```c
__int64 __fastcall Appx::Packaging::Production::ProcessInParallel__lambda_23e8b1edb175e3d2b228e1a6bfa2f527___lambda_c32d057266adf508bbc79fb00cb0b29d___(
        __int64 a1,
        __int64 a2)
{
  PTP_CLEANUP_GROUP ThreadpoolCleanupGroup; // rax
  const char *v5; // r9
  unsigned int v6; // ebx
  PTP_CALLBACK_ENVIRON v7; // r14
  _QWORD *v8; // rax
  __int64 v9; // rsi
  struct _TP_WORK *ThreadpoolWork; // rax
  const char *v11; // r9
  _QWORD *v12; // r8
  __int64 v13; // rdx
  int LastError; // eax
  _QWORD v16[4]; // [rsp+20h] [rbp-50h] BYREF
  __int128 v17; // [rsp+40h] [rbp-30h]
  __int64 v18; // [rsp+50h] [rbp-20h]
  int v19; // [rsp+58h] [rbp-18h]
  int v20; // [rsp+5Ch] [rbp-14h]
  __int64 v21; // [rsp+60h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+28h]
  PTP_CLEANUP_GROUP ptpcg; // [rsp+B0h] [rbp+40h] BYREF
  PTP_CALLBACK_ENVIRON pcbe; // [rsp+B8h] [rbp+48h] BYREF

  v16[0] = 3;
  memset(&v16[1], 0, 24);
  v17 = 0;
  v18 = 0;
  v19 = 0;
  pcbe = 0;
  v21 = 72;
  v20 = 1;
  wil::details::unique_storage<wil::details::resource_policy<_TP_CALLBACK_ENVIRON_V3 *,void (_TP_CALLBACK_ENVIRON_V3 *),&void DestroyThreadpoolEnvironment(_TP_CALLBACK_ENVIRON_V3 *),wistd::integral_constant<unsigned __int64,0>,_TP_CALLBACK_ENVIRON_V3 *,_TP_CALLBACK_ENVIRON_V3 *,0,std::nullptr_t>>::reset(
    &pcbe,
    v16);
  ptpcg = 0;
  ThreadpoolCleanupGroup = CreateThreadpoolCleanupGroup();
  wil::details::unique_storage<wil::details::resource_policy<_TP_CLEANUP_GROUP *,void (_TP_CLEANUP_GROUP *),&void CloseThreadpoolCleanupGroup(_TP_CLEANUP_GROUP *),wistd::integral_constant<unsigned __int64,0>,_TP_CLEANUP_GROUP *,_TP_CLEANUP_GROUP *,0,std::nullptr_t>>::reset(
    &ptpcg,
    ThreadpoolCleanupGroup);
  if ( ptpcg )
  {
    v7 = pcbe;
    pcbe->CleanupGroup = ptpcg;
    v7->CleanupGroupCancelCallback = 0;
    v8 = *(_QWORD **)a1;
    if ( !*(_QWORD *)(*(_QWORD *)a1 + 16LL) )
      goto LABEL_7;
    v9 = 0;
    while ( 1 )
    {
      ThreadpoolWork = CreateThreadpoolWork(
                         Appx::Packaging::Production::GenerateHashForBlock,
                         *(PVOID *)(*v8 + 8 * v9),
                         v7);
      if ( !ThreadpoolWork )
        break;
      SubmitThreadpoolWork(ThreadpoolWork);
      v8 = *(_QWORD **)a1;
      if ( (unsigned __int64)++v9 >= *(_QWORD *)(*(_QWORD *)a1 + 16LL) )
        goto LABEL_7;
    }
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0xAD,
                  (unsigned int)"onecore\\printscan\\appxpackaging\\production\\src\\util.cpp",
                  v11);
    v6 = LastError;
    if ( LastError < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x7B,
        (unsigned int)"onecore\\printscan\\appxpackaging\\production\\src\\Util.hpp",
        (const char *)(unsigned int)LastError,
        v16[0]);
      CloseThreadpoolCleanupGroupMembers(ptpcg, 1, 0);
    }
    else
    {
LABEL_7:
      CloseThreadpoolCleanupGroupMembers(ptpcg, 0, 0);
      v12 = *(_QWORD **)a2;
      v13 = 0;
      if ( *(_QWORD *)(*(_QWORD *)a2 + 16LL) )
      {
        while ( 1 )
        {
          v6 = *(_DWORD *)(*(_QWORD *)(*v12 + 8 * v13) + 72LL);
          if ( (v6 & 0x80000000) != 0 )
            break;
          if ( (unsigned __int64)++v13 >= v12[2] )
            goto LABEL_10;
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xAD,
          (unsigned int)"onecore\\printscan\\appxpackaging\\production\\src\\util.cpp",
          (const char *)v6,
          v16[0]);
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x87,
          (unsigned int)"onecore\\printscan\\appxpackaging\\production\\src\\Util.hpp",
          (const char *)v6,
          v16[0]);
      }
      else
      {
LABEL_10:
        v6 = 0;
      }
    }
  }
  else
  {
    v6 = wil::details::in1diag3::Return_GetLastError(
           retaddr,
           (void *)0x6A,
           (unsigned int)"onecore\\printscan\\appxpackaging\\production\\src\\Util.hpp",
           v5);
  }
  wil::details::unique_storage<wil::details::resource_policy<_TP_CLEANUP_GROUP *,void (_TP_CLEANUP_GROUP *),&void CloseThreadpoolCleanupGroup(_TP_CLEANUP_GROUP *),wistd::integral_constant<unsigned __int64,0>,_TP_CLEANUP_GROUP *,_TP_CLEANUP_GROUP *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_TP_CLEANUP_GROUP *,void (_TP_CLEANUP_GROUP *),&void CloseThreadpoolCleanupGroup(_TP_CLEANUP_GROUP *),wistd::integral_constant<unsigned __int64,0>,_TP_CLEANUP_GROUP *,_TP_CLEANUP_GROUP *,0,std::nullptr_t>>(&ptpcg);
  return v6;
}

```

## disassembly

```asm
0x1800f1c30  mov     [rsp-28h+arg_0], rbx
0x1800f1c35  push    rbp
0x1800f1c36  push    rsi
0x1800f1c37  push    rdi
0x1800f1c38  push    r14
0x1800f1c3a  push    r15
0x1800f1c3c  mov     rbp, rsp
0x1800f1c3f  sub     rsp, 70h
0x1800f1c43  xor     r15d, r15d
0x1800f1c46  mov     [rbp+var_50], 3
0x1800f1c4e  mov     rdi, rdx
0x1800f1c51  mov     [rbp+var_48], r15
0x1800f1c55  mov     rbx, rcx
0x1800f1c58  mov     [rbp+var_40], r15
0x1800f1c5c  xorps   xmm0, xmm0
0x1800f1c5f  mov     [rbp+var_38], r15
0x1800f1c63  lea     rdx, [rbp+var_50]
0x1800f1c67  movdqa  [rbp+var_30], xmm0
0x1800f1c6c  lea     rcx, [rbp+pcbe]
0x1800f1c70  mov     [rbp+var_20], r15
0x1800f1c74  mov     [rbp+var_18], r15d
0x1800f1c78  mov     [rbp+pcbe], r15
0x1800f1c7c  mov     [rbp+var_10], 48h ; 'H'
0x1800f1c84  mov     [rbp+var_14], 1
0x1800f1c8b  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_CALLBACK_ENVIRON_V3@@$$A6AXPEAU1@@Z$1?DestroyThreadpoolEnvironment@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_CALLBACK_ENVIRON_V3@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_CALLBACK_ENVIRON_V3 *,void (_TP_CALLBACK_ENVIRON_V3 *),&DestroyThreadpoolEnvironment(_TP_CALLBACK_ENVIRON_V3 *),wistd::integral_constant<unsigned __int64,0>,_TP_CALLBACK_ENVIRON_V3 *,_TP_CALLBACK_ENVIRON_V3 *,0,std::nullptr_t>>::reset(_TP_CALLBACK_ENVIRON_V3 *)
0x1800f1c90  mov     [rbp+ptpcg], r15
0x1800f1c94  call    cs:__imp_CreateThreadpoolCleanupGroup
0x1800f1c9b  nop     dword ptr [rax+rax+00h]
0x1800f1ca0  mov     rdx, rax
0x1800f1ca3  lea     rcx, [rbp+ptpcg]
0x1800f1ca7  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_CLEANUP_GROUP@@$$A6AXPEAU1@@Z$1?CloseThreadpoolCleanupGroup@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_CLEANUP_GROUP@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_CLEANUP_GROUP *,void (_TP_CLEANUP_GROUP *),&CloseThreadpoolCleanupGroup(_TP_CLEANUP_GROUP *),wistd::integral_constant<unsigned __int64,0>,_TP_CLEANUP_GROUP *,_TP_CLEANUP_GROUP *,0,std::nullptr_t>>::reset(_TP_CLEANUP_GROUP *)
0x1800f1cac  mov     rax, [rbp+ptpcg]
0x1800f1cb0  test    rax, rax
0x1800f1cb3  jnz     short loc_1800F1CCF
0x1800f1cb5  mov     rcx, [rbp+28h]; this
0x1800f1cb9  lea     r8, aOnecorePrintsc_187; "onecore\\printscan\\appxpackaging\\prod"...
0x1800f1cc0  lea     edx, [rax+6Ah]; void *
0x1800f1cc3  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800f1cc8  mov     ebx, eax
0x1800f1cca  jmp     loc_1800F1D6A
0x1800f1ccf  mov     r14, [rbp+pcbe]
0x1800f1cd3  mov     [r14+10h], rax
0x1800f1cd7  mov     [r14+18h], r15
0x1800f1cdb  mov     rax, [rbx]
0x1800f1cde  cmp     [rax+10h], r15
0x1800f1ce2  jbe     short loc_1800F1D2F
0x1800f1ce4  mov     rsi, r15
0x1800f1ce7  cmp     r15, [rax+10h]
0x1800f1ceb  jb      short loc_1800F1CF2
0x1800f1ced  mov     rdx, r15
0x1800f1cf0  jmp     short loc_1800F1CF9
0x1800f1cf2  mov     rax, [rax]
0x1800f1cf5  mov     rdx, [rax+rsi*8]; pv
0x1800f1cf9  mov     r8, r14; pcbe
0x1800f1cfc  lea     rcx, ?GenerateHashForBlock@Production@Packaging@Appx@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x1800f1d03  call    cs:__imp_CreateThreadpoolWork
0x1800f1d0a  nop     dword ptr [rax+rax+00h]
0x1800f1d0f  test    rax, rax
0x1800f1d12  jz      short loc_1800F1D8A
0x1800f1d14  mov     rcx, rax; pwk
0x1800f1d17  call    cs:__imp_SubmitThreadpoolWork
0x1800f1d1e  nop     dword ptr [rax+rax+00h]
0x1800f1d23  mov     rax, [rbx]
0x1800f1d26  inc     rsi
0x1800f1d29  cmp     rsi, [rax+10h]
0x1800f1d2d  jb      short loc_1800F1CF2
0x1800f1d2f  mov     rcx, [rbp+ptpcg]; ptpcg
0x1800f1d33  xor     r8d, r8d; pvCleanupContext
0x1800f1d36  xor     edx, edx; fCancelPendingCallbacks
0x1800f1d38  call    cs:__imp_CloseThreadpoolCleanupGroupMembers
0x1800f1d3f  nop     dword ptr [rax+rax+00h]
0x1800f1d44  mov     r8, [rdi]
0x1800f1d47  mov     rdx, r15
0x1800f1d4a  cmp     [r8+10h], r15
0x1800f1d4e  jbe     short loc_1800F1D67
0x1800f1d50  mov     rax, [r8]
0x1800f1d53  mov     rcx, [rax+rdx*8]
0x1800f1d57  mov     ebx, [rcx+48h]
0x1800f1d5a  test    ebx, ebx
0x1800f1d5c  js      short loc_1800F1DD6
0x1800f1d5e  inc     rdx
0x1800f1d61  cmp     rdx, [r8+10h]
0x1800f1d65  jb      short loc_1800F1D50
0x1800f1d67  mov     ebx, r15d
0x1800f1d6a  lea     rcx, [rbp+ptpcg]
0x1800f1d6e  call    ??1?$unique_storage@U?$resource_policy@PEAU_TP_CLEANUP_GROUP@@$$A6AXPEAU1@@Z$1?CloseThreadpoolCleanupGroup@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_TP_CLEANUP_GROUP *,void (_TP_CLEANUP_GROUP *),&CloseThreadpoolCleanupGroup(_TP_CLEANUP_GROUP *),wistd::integral_constant<unsigned __int64,0>,_TP_CLEANUP_GROUP *,_TP_CLEANUP_GROUP *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_TP_CLEANUP_GROUP *,void (_TP_CLEANUP_GROUP *),&CloseThreadpoolCleanupGroup(_TP_CLEANUP_GROUP *),wistd::integral_constant<unsigned __int64,0>,_TP_CLEANUP_GROUP *,_TP_CLEANUP_GROUP *,0,std::nullptr_t>>(void)
0x1800f1d73  mov     eax, ebx
0x1800f1d75  mov     rbx, [rsp+70h+arg_0]
0x1800f1d7d  add     rsp, 70h
0x1800f1d81  pop     r15
0x1800f1d83  pop     r14
0x1800f1d85  pop     rdi
0x1800f1d86  pop     rsi
0x1800f1d87  pop     rbp
0x1800f1d88  retn
0x1800f1d8a  mov     rcx, [rbp+28h]; this
0x1800f1d8e  lea     r8, aOnecorePrintsc_50; "onecore\\printscan\\appxpackaging\\prod"...
0x1800f1d95  mov     edx, 0ADh; void *
0x1800f1d9a  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800f1d9f  mov     ebx, eax
0x1800f1da1  test    eax, eax
0x1800f1da3  jns     short loc_1800F1D2F
0x1800f1da5  mov     rcx, [rbp+28h]; this
0x1800f1da9  lea     r8, aOnecorePrintsc_187; "onecore\\printscan\\appxpackaging\\prod"...
0x1800f1db0  mov     r9d, eax; char *
0x1800f1db3  mov     edx, 7Bh ; '{'; void *
0x1800f1db8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800f1dbd  mov     rcx, [rbp+ptpcg]; ptpcg
0x1800f1dc1  xor     r8d, r8d; pvCleanupContext
0x1800f1dc4  lea     edx, [r8+1]; fCancelPendingCallbacks
0x1800f1dc8  call    cs:__imp_CloseThreadpoolCleanupGroupMembers
0x1800f1dcf  nop     dword ptr [rax+rax+00h]
0x1800f1dd4  jmp     short loc_1800F1D6A
0x1800f1dd6  mov     rcx, [rbp+28h]; this
0x1800f1dda  lea     r8, aOnecorePrintsc_50; "onecore\\printscan\\appxpackaging\\prod"...
0x1800f1de1  mov     r9d, ebx; char *
0x1800f1de4  mov     edx, 0ADh; void *
0x1800f1de9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800f1dee  mov     rcx, [rbp+28h]; this
0x1800f1df2  lea     r8, aOnecorePrintsc_187; "onecore\\printscan\\appxpackaging\\prod"...
0x1800f1df9  mov     r9d, ebx; char *
0x1800f1dfc  mov     edx, 87h; void *
0x1800f1e01  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800f1e06  jmp     loc_1800F1D6A
```
