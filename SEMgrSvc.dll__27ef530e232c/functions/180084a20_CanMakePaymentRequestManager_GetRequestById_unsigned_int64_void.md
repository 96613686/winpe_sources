# CanMakePaymentRequestManager::GetRequestById(unsigned __int64,void *)

- ea: `0x180084a20`
- end: `0x180084c9e`
- name: `?GetRequestById@CanMakePaymentRequestManager@@QEAA?AV?$shared_ptr@VCanMakePaymentRequest@@@std@@_KPEAX@Z`
- size: `638`
- prototype: `__int64 __fastcall(LPCRITICAL_SECTION lpCriticalSection)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18007df64`
- `0x18007e660`

## callees

- `0x180007aac`
- `0x18002daa4`
- `0x180084a20`
- `0x180085900`
- `0x18009d010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180084c19`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180084c19`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180084a4d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180084a4d`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180084b85`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180084b85`

## string_xrefs

- `0x180084c3c`: `onecoreuap\ds\nfc\product\payment\service\lib\canmakepaymentrequestmanager.cpp`
- `0x180084c57`: `onecoreuap\ds\nfc\product\payment\service\lib\canmakepaymentrequestmanager.cpp`
- `0x180084c8c`: `onecoreuap\ds\nfc\product\payment\service\lib\canmakepaymentrequestmanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
struct _LIST_ENTRY **__fastcall CanMakePaymentRequestManager::GetRequestById(
        LPCRITICAL_SECTION lpCriticalSection,
        struct _LIST_ENTRY **a2,
        struct _LIST_ENTRY *a3,
        void *a4)
{
  __int64 v8; // rdx
  unsigned __int64 i; // r8
  __int64 v10; // rax
  _QWORD *OwningThread; // rcx
  PRTL_CRITICAL_SECTION_DEBUG DebugInfo; // rdx
  __int64 v13; // r8
  signed __int32 v14; // eax
  signed __int32 v15; // ett
  struct _LIST_ENTRY *v16; // rdi
  struct _LIST_ENTRY *Flink; // rax
  struct _LIST_ENTRY *Blink; // rbx
  volatile signed __int32 *v19; // rdi
  struct _LIST_ENTRY *v20; // rax
  void **p_Flink; // rax
  volatile signed __int32 *v22; // rbx
  void *v23; // rdx
  unsigned int v25; // eax
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]
  struct _LIST_ENTRY *v27; // [rsp+90h] [rbp+18h] BYREF

  v27 = a3;
  EnterCriticalSection(lpCriticalSection);
  v8 = 0xCBF29CE484222325uLL;
  for ( i = 0; i < 8; ++i )
    v8 = 0x100000001B3LL * (*((unsigned __int8 *)&v27 + i) ^ (unsigned __int64)v8);
  v10 = 2 * (v8 & (__int64)lpCriticalSection[4].DebugInfo);
  OwningThread = lpCriticalSection[3].OwningThread;
  DebugInfo = (PRTL_CRITICAL_SECTION_DEBUG)OwningThread[2 * (v8 & (__int64)lpCriticalSection[4].DebugInfo) + 1];
  if ( DebugInfo == lpCriticalSection[3].DebugInfo )
  {
LABEL_7:
    DebugInfo = 0;
  }
  else
  {
    while ( a3 != DebugInfo->ProcessLocksList.Flink )
    {
      if ( DebugInfo == (PRTL_CRITICAL_SECTION_DEBUG)OwningThread[v10] )
        goto LABEL_7;
      DebugInfo = (PRTL_CRITICAL_SECTION_DEBUG)DebugInfo->CriticalSection;
    }
  }
  if ( !DebugInfo )
    DebugInfo = lpCriticalSection[3].DebugInfo;
  if ( DebugInfo == lpCriticalSection[3].DebugInfo )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x17,
      (unsigned int)"onecoreuap\\ds\\nfc\\product\\payment\\service\\lib\\canmakepaymentrequestmanager.cpp",
      (const char *)0x80004004LL,
      0);
  *a2 = 0;
  a2[1] = 0;
  v13 = *(_QWORD *)&DebugInfo->EntryCount;
  if ( v13 )
  {
    v14 = *(_DWORD *)(v13 + 8);
    while ( v14 )
    {
      v15 = v14;
      v14 = _InterlockedCompareExchange((volatile signed __int32 *)(v13 + 8), v14 + 1, v14);
      if ( v15 == v14 )
      {
        *a2 = DebugInfo->ProcessLocksList.Blink;
        a2[1] = *(struct _LIST_ENTRY **)&DebugInfo->EntryCount;
        break;
      }
    }
  }
  v16 = *a2;
  if ( !*a2 )
  {
    std::_Hash<std::_Umap_traits<unsigned __int64,std::weak_ptr<CanMakePaymentRequest>,std::_Uhash_compare<unsigned __int64,std::hash<unsigned __int64>,std::equal_to<unsigned __int64>>,std::allocator<std::pair<unsigned __int64 const,std::weak_ptr<CanMakePaymentRequest>>>,0>>::erase(
      &lpCriticalSection[2].SpinCount,
      &v27);
    v25 = wil::verify_hresult<long>(2147500036LL);
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x21,
      (unsigned int)"onecoreuap\\ds\\nfc\\product\\payment\\service\\lib\\canmakepaymentrequestmanager.cpp",
      (const char *)v25,
      1);
  }
  Flink = v16[15].Flink;
  if ( Flink )
    _InterlockedIncrement((volatile signed __int32 *)&Flink->Blink);
  Blink = v16[14].Blink;
  v19 = (volatile signed __int32 *)v16[15].Flink;
  v20 = Blink[3].Flink;
  if ( v20 )
    _InterlockedIncrement((volatile signed __int32 *)&v20->Blink);
  p_Flink = (void **)&Blink[2].Blink->Flink;
  v22 = (volatile signed __int32 *)Blink[3].Flink;
  if ( p_Flink )
    v23 = *p_Flink;
  else
    v23 = 0;
  if ( !EqualSid(a4, v23) )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x25,
      (unsigned int)"onecoreuap\\ds\\nfc\\product\\payment\\service\\lib\\canmakepaymentrequestmanager.cpp",
      (const char *)0x80070005LL,
      1);
  if ( v22 )
  {
    if ( _InterlockedExchangeAdd(v22 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v22)(v22);
      if ( _InterlockedExchangeAdd(v22 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v22 + 8LL))(v22);
    }
  }
  if ( v19 )
  {
    if ( _InterlockedExchangeAdd(v19 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v19)(v19);
      if ( _InterlockedExchangeAdd(v19 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v19 + 8LL))(v19);
    }
  }
  if ( lpCriticalSection )
    LeaveCriticalSection(lpCriticalSection);
  return a2;
}

```

## disassembly

```asm
0x180084a20  mov     rax, rsp
0x180084a23  mov     [rax+20h], rbx
0x180084a27  mov     [rax+18h], r8
0x180084a2b  mov     [rax+10h], rdx
0x180084a2f  push    rbp
0x180084a30  push    rsi
0x180084a31  push    rdi
0x180084a32  push    r14
0x180084a34  push    r15
0x180084a36  sub     rsp, 50h
0x180084a3a  mov     r15, r9
0x180084a3d  mov     rbx, r8
0x180084a40  mov     rsi, rdx
0x180084a43  mov     rbp, rcx
0x180084a46  mov     dword ptr [rax-58h], 0
0x180084a4d  call    cs:__imp_EnterCriticalSection
0x180084a53  mov     [rsp+78h+arg_0], rbp
0x180084a5b  mov     rdx, 0CBF29CE484222325h
0x180084a65  xor     r8d, r8d
0x180084a68  movzx   eax, byte ptr [rsp+r8+78h+arg_10]
0x180084a71  xor     rdx, rax
0x180084a74  mov     rcx, 100000001B3h
0x180084a7e  imul    rdx, rcx
0x180084a82  inc     r8
0x180084a85  cmp     r8, 8
0x180084a89  jb      short loc_180084A68
0x180084a8b  mov     rax, [rbp+0A0h]
0x180084a92  and     rax, rdx
0x180084a95  add     rax, rax
0x180084a98  mov     rcx, [rbp+88h]
0x180084a9f  mov     rdx, [rcx+rax*8+8]
0x180084aa4  cmp     rdx, [rbp+78h]
0x180084aa8  jz      short loc_180084ABF
0x180084aaa  mov     r8, [rcx+rax*8]
0x180084aae  cmp     rbx, [rdx+10h]
0x180084ab2  jz      short loc_180084AC1
0x180084ab4  cmp     rdx, r8
0x180084ab7  jz      short loc_180084ABF
0x180084ab9  mov     rdx, [rdx+8]
0x180084abd  jmp     short loc_180084AAE
0x180084abf  xor     edx, edx
0x180084ac1  test    rdx, rdx
0x180084ac4  cmovz   rdx, [rbp+78h]
0x180084ac9  mov     rcx, [rsp+78h]; this
0x180084ace  cmp     rdx, [rbp+78h]
0x180084ad2  jz      loc_180084C51
0x180084ad8  mov     qword ptr [rsi], 0
0x180084adf  mov     qword ptr [rsi+8], 0
0x180084ae7  mov     r8, [rdx+20h]
0x180084aeb  test    r8, r8
0x180084aee  jz      short loc_180084B16
0x180084af0  mov     eax, [r8+8]
0x180084af4  jmp     short loc_180084B01
0x180084af6  lea     ecx, [rax+1]
0x180084af9  lock cmpxchg [r8+8], ecx
0x180084aff  jz      short loc_180084B07
0x180084b01  test    eax, eax
0x180084b03  jnz     short loc_180084AF6
0x180084b05  jmp     short loc_180084B16
0x180084b07  mov     rax, [rdx+18h]
0x180084b0b  mov     [rsi], rax
0x180084b0e  mov     rax, [rdx+20h]
0x180084b12  mov     [rsi+8], rax
0x180084b16  mov     [rsp+78h+var_58], 1; int
0x180084b1e  mov     rdi, [rsi]
0x180084b21  test    rdi, rdi
0x180084b24  jz      loc_180084C69
0x180084b2a  mov     rax, [rdi+0F0h]
0x180084b31  test    rax, rax
0x180084b34  jz      short loc_180084B3A
0x180084b36  lock inc dword ptr [rax+8]
0x180084b3a  mov     rbx, [rdi+0E8h]
0x180084b41  mov     [rsp+78h+var_50], rbx
0x180084b46  mov     rdi, [rdi+0F0h]
0x180084b4d  mov     [rsp+78h+var_48], rdi
0x180084b52  mov     rax, [rbx+30h]
0x180084b56  test    rax, rax
0x180084b59  jz      short loc_180084B5F
0x180084b5b  lock inc dword ptr [rax+8]
0x180084b5f  mov     rax, [rbx+28h]
0x180084b63  mov     [rsp+78h+var_40], rax
0x180084b68  mov     rbx, [rbx+30h]
0x180084b6c  mov     [rsp+78h+var_38], rbx
0x180084b71  test    rax, rax
0x180084b74  jz      short loc_180084B7B
0x180084b76  mov     rdx, [rax]
0x180084b79  jmp     short loc_180084B7D
0x180084b7b  xor     edx, edx; pSid2
0x180084b7d  mov     r14, [rsp+78h]
0x180084b82  mov     rcx, r15; pSid1
0x180084b85  call    cs:__imp_EqualSid
0x180084b8b  test    eax, eax
0x180084b8d  jz      loc_180084C36
0x180084b93  or      r14d, 0FFFFFFFFh
0x180084b97  test    rbx, rbx
0x180084b9a  jz      short loc_180084BD4
0x180084b9c  mov     eax, r14d
0x180084b9f  lock xadd [rbx+8], eax
0x180084ba4  add     eax, r14d
0x180084ba7  jnz     short loc_180084BD4
0x180084ba9  mov     rax, [rbx]
0x180084bac  mov     rcx, rbx
0x180084baf  mov     rax, [rax]
0x180084bb2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180084bb7  mov     eax, r14d
0x180084bba  lock xadd [rbx+0Ch], eax
0x180084bbf  add     eax, r14d
0x180084bc2  jnz     short loc_180084BD4
0x180084bc4  mov     rax, [rbx]
0x180084bc7  mov     rcx, rbx
0x180084bca  mov     rax, [rax+8]
0x180084bce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180084bd3  nop
0x180084bd4  test    rdi, rdi
0x180084bd7  jz      short loc_180084C11
0x180084bd9  mov     eax, r14d
0x180084bdc  lock xadd [rdi+8], eax
0x180084be1  add     eax, r14d
0x180084be4  jnz     short loc_180084C11
0x180084be6  mov     rax, [rdi]
0x180084be9  mov     rcx, rdi
0x180084bec  mov     rax, [rax]
0x180084bef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180084bf4  mov     eax, r14d
0x180084bf7  lock xadd [rdi+0Ch], eax
0x180084bfc  add     eax, r14d
0x180084bff  jnz     short loc_180084C11
0x180084c01  mov     rax, [rdi]
0x180084c04  mov     rcx, rdi
0x180084c07  mov     rax, [rax+8]
0x180084c0b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180084c10  nop
0x180084c11  test    rbp, rbp
0x180084c14  jz      short loc_180084C1F
0x180084c16  mov     rcx, rbp; lpCriticalSection
0x180084c19  call    cs:__imp_LeaveCriticalSection
0x180084c1f  mov     rax, rsi
0x180084c22  mov     rbx, [rsp+78h+arg_18]
0x180084c2a  add     rsp, 50h
0x180084c2e  pop     r15
0x180084c30  pop     r14
0x180084c32  pop     rdi
0x180084c33  pop     rsi
0x180084c34  pop     rbp
0x180084c35  retn
0x180084c36  mov     r9d, 80070005h; char *
0x180084c3c  lea     r8, aOnecoreuapDsNf_42; "onecoreuap\\ds\\nfc\\product\\payment\\"...
0x180084c43  mov     edx, 25h ; '%'; void *
0x180084c48  mov     rcx, r14; this
0x180084c4b  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180084c51  mov     r9d, 80004004h; char *
0x180084c57  lea     r8, aOnecoreuapDsNf_42; "onecoreuap\\ds\\nfc\\product\\payment\\"...
0x180084c5e  mov     edx, 17h; void *
0x180084c63  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180084c69  lea     rcx, [rbp+70h]
0x180084c6d  lea     rdx, [rsp+78h+arg_10]
0x180084c75  call    ?erase@?$_Hash@V?$_Umap_traits@_KV?$weak_ptr@VCanMakePaymentRequest@@@std@@V?$_Uhash_compare@_KU?$hash@_K@std@@U?$equal_to@_K@2@@2@V?$allocator@U?$pair@$$CB_KV?$weak_ptr@VCanMakePaymentRequest@@@std@@@std@@@2@$0A@@std@@@std@@QEAA_KAEB_K@Z; std::_Hash<std::_Umap_traits<unsigned __int64,std::weak_ptr<CanMakePaymentRequest>,std::_Uhash_compare<unsigned __int64,std::hash<unsigned __int64>,std::equal_to<unsigned __int64>>,std::allocator<std::pair<unsigned __int64 const,std::weak_ptr<CanMakePaymentRequest>>>,0>>::erase(unsigned __int64 const &)
0x180084c7a  mov     ecx, 80004004h
0x180084c7f  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x180084c84  mov     r9d, eax; char *
0x180084c87  mov     rcx, [rsp+78h]; this
0x180084c8c  lea     r8, aOnecoreuapDsNf_42; "onecoreuap\\ds\\nfc\\product\\payment\\"...
0x180084c93  mov     edx, 21h ; '!'; void *
0x180084c98  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
