# RoutePolicyCache::UpdateRoutingRulesForInterface(WcmRoutePolicy::RoutingRulesForInterface const *,ulong)

- ea: `0x140002abc`
- end: `0x140002cf8`
- name: `?UpdateRoutingRulesForInterface@RoutePolicyCache@@YAJPEBURoutingRulesForInterface@WcmRoutePolicy@@K@Z`
- size: `572`
- prototype: `__int64 __fastcall(RoutePolicyCache *__hidden this, size_t Size, unsigned int)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, installer_update`

## callers

- `0x1400089c8`

## callees

- `0x140001008`
- `0x1400015fc`
- `0x1400020a0`
- `0x140002498`
- `0x140002abc`
- `0x140007d28`
- `0x140007d7c`
- `0x14000a780`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140002b1d`
- `ntoskrnl!ExFreePoolWithTag` at `0x140002b1d`
- `ntoskrnl!ExAllocatePool2` at `0x140002b45`
- `ntoskrnl!ExAllocatePool2` at `0x140002bab`
- `ntoskrnl!ExAllocatePool2` at `0x140002b45`
- `ntoskrnl!ExAllocatePool2` at `0x140002bab`

## pseudocode

```c
__int64 __fastcall RoutePolicyCache::UpdateRoutingRulesForInterface(RoutePolicyCache *this, size_t Size)
{
  size_t v2; // rsi
  PVOID *v4; // rbx
  const struct WcmRoutePolicy::RoutingRulesForInterface **v5; // rdi
  const struct WcmRoutePolicy::RoutingRulesForInterface *v6; // rcx
  _QWORD *v7; // rbx
  __int64 Pool2; // rax
  __int64 v9; // rcx
  __int64 v10; // r8
  __int64 v11; // r9
  const struct WcmRoutePolicy::RoutingRulesForInterface *v12; // rax
  __int64 v13; // rcx
  __int64 v14; // r8
  __int64 v15; // r9
  int v17; // eax
  __int64 v18; // r8
  __int64 v19; // r9
  unsigned int v20; // esi
  _QWORD *v21; // rax
  _DWORD v22[4]; // [rsp+30h] [rbp-30h] BYREF
  __int128 v23; // [rsp+40h] [rbp-20h] BYREF
  int *v24[2]; // [rsp+50h] [rbp-10h] BYREF

  v2 = (unsigned int)Size;
  AcquireSpinLock(&v23, &g_cacheLock);
  v4 = (PVOID *)g_rulesListHead;
  v5 = 0;
  if ( g_rulesListHead != &g_rulesListHead )
  {
    while ( 1 )
    {
      v6 = (const struct WcmRoutePolicy::RoutingRulesForInterface *)v4[2];
      if ( *(_QWORD *)v6 == *(_QWORD *)this )
        break;
      v4 = (PVOID *)*v4;
      if ( v4 == &g_rulesListHead )
        goto LABEL_7;
    }
    DereferencePackageEntriesForRoutingRules(v6);
    ExFreePoolWithTag(v4[2], 0x64667072u);
    v4[2] = 0;
    v5 = (const struct WcmRoutePolicy::RoutingRulesForInterface **)v4;
  }
  v7 = 0;
  if ( !v5 )
  {
LABEL_7:
    Pool2 = ExAllocatePool2(64, 24, 1684435058);
    v7 = (_QWORD *)Pool2;
    if ( !Pool2 )
    {
      if ( (unsigned int)dword_140012050 > 2 )
      {
        v22[0] = -1073741670;
        v24[0] = (int *)"Failed to allocate rules entry";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
          v9,
          (unsigned __int8 *)&word_14000E39E,
          v10,
          v11,
          v24,
          (__int64)v22);
      }
LABEL_15:
      if ( (_QWORD)v23 )
        SpinLockAndSavedIrql::Release((const struct SpinLockAndSavedIrql *)&v23);
      return 3221225626LL;
    }
    v5 = (const struct WcmRoutePolicy::RoutingRulesForInterface **)Pool2;
  }
  v12 = (const struct WcmRoutePolicy::RoutingRulesForInterface *)ExAllocatePool2(64, v2, 1684435058);
  v5[2] = v12;
  if ( !v12 )
  {
    if ( (unsigned int)dword_140012050 > 2 )
    {
      v22[0] = -1073741670;
      v24[0] = (int *)"Failed to allocate routing rules buffer";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        v13,
        (unsigned __int8 *)&unk_14000E198,
        v14,
        v15,
        v24,
        (__int64)v22);
    }
    FreeRulesEntry(v5);
    goto LABEL_15;
  }
  memmove(v12, this, v2);
  v17 = AddOrReferencePackageEntriesForRoutingRules(v5[2]);
  v20 = v17;
  if ( v17 >= 0 )
  {
    if ( v7 )
    {
      v21 = (_QWORD *)qword_140012390;
      if ( *(PVOID **)qword_140012390 != &g_rulesListHead )
        __fastfail(3u);
      *v7 = &g_rulesListHead;
      v7[1] = v21;
      *v21 = v7;
      qword_140012390 = (__int64)v7;
    }
    if ( (_QWORD)v23 )
      SpinLockAndSavedIrql::Release((const struct SpinLockAndSavedIrql *)&v23);
    return 0;
  }
  else
  {
    if ( (unsigned int)dword_140012050 > 2 )
    {
      v22[0] = v17;
      v24[0] = (int *)"AddOrReferencePackageEntryForRoutingRules failed";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        (unsigned int)dword_140012050,
        (unsigned __int8 *)&word_14000E54E,
        v18,
        v19,
        v24,
        (__int64)v22);
    }
    FreeRulesEntry(v5);
    if ( (_QWORD)v23 )
      SpinLockAndSavedIrql::Release((const struct SpinLockAndSavedIrql *)&v23);
    return v20;
  }
}

```

## disassembly

```asm
0x140002abc  mov     [rsp-28h+arg_10], rbx
0x140002ac1  push    rbp
0x140002ac2  push    rsi
0x140002ac3  push    rdi
0x140002ac4  push    r12
0x140002ac6  push    r14
0x140002ac8  mov     rbp, rsp
0x140002acb  sub     rsp, 60h
0x140002acf  mov     esi, edx
0x140002ad1  mov     r14, rcx
0x140002ad4  lea     rdx, ?g_cacheLock@@3_KA; unsigned __int64 g_cacheLock
0x140002adb  lea     rcx, [rbp+var_20]
0x140002adf  call    ?AcquireSpinLock@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_K$$A6AXAEBUSpinLockAndSavedIrql@@@Z$1?Release@1@SAX0@ZU?$integral_constant@_K$01@wistd@@U1@PEA_K$0A@$$T@details@wil@@@details@wil@@@wil@@PEA_K@Z; AcquireSpinLock(unsigned __int64 *)
0x140002ae4  mov     rbx, cs:?g_rulesListHead@@3U_LIST_ENTRY@@A; _LIST_ENTRY g_rulesListHead
0x140002aeb  lea     r12, ?g_rulesListHead@@3U_LIST_ENTRY@@A; _LIST_ENTRY g_rulesListHead
0x140002af2  xor     edi, edi
0x140002af4  cmp     rbx, r12
0x140002af7  jz      short loc_140002B30
0x140002af9  mov     rax, [r14]
0x140002afc  mov     rcx, [rbx+10h]; struct WcmRoutePolicy::RoutingRulesForInterface *
0x140002b00  cmp     [rcx], rax
0x140002b03  jz      short loc_140002B0F
0x140002b05  mov     rbx, [rbx]
0x140002b08  cmp     rbx, r12
0x140002b0b  jnz     short loc_140002AFC
0x140002b0d  jmp     short loc_140002B37
0x140002b0f  call    ?DereferencePackageEntriesForRoutingRules@@YAXPEBURoutingRulesForInterface@WcmRoutePolicy@@@Z; DereferencePackageEntriesForRoutingRules(WcmRoutePolicy::RoutingRulesForInterface const *)
0x140002b14  mov     rcx, [rbx+10h]; P
0x140002b18  mov     edx, 64667072h; Tag
0x140002b1d  call    cs:__imp_ExFreePoolWithTag
0x140002b24  nop     dword ptr [rax+rax+00h]
0x140002b29  mov     [rbx+10h], rdi
0x140002b2d  mov     rdi, rbx
0x140002b30  xor     ebx, ebx
0x140002b32  test    rdi, rdi
0x140002b35  jnz     short loc_140002B9D
0x140002b37  mov     edx, 18h
0x140002b3c  mov     r8d, 64667072h
0x140002b42  lea     ecx, [rdx+28h]
0x140002b45  call    cs:__imp_ExAllocatePool2
0x140002b4c  nop     dword ptr [rax+rax+00h]
0x140002b51  mov     rbx, rax
0x140002b54  test    rax, rax
0x140002b57  jnz     short loc_140002B9A
0x140002b59  mov     eax, cs:dword_140012050
0x140002b5f  cmp     eax, 2
0x140002b62  jbe     loc_140002C03
0x140002b68  lea     rax, aFailedToAlloca_1; "Failed to allocate rules entry"
0x140002b6f  mov     [rbp+var_30], 0C000009Ah
0x140002b76  mov     [rbp+var_10], rax
0x140002b7a  lea     rdx, word_14000E39E
0x140002b81  lea     rax, [rbp+var_30]
0x140002b85  mov     [rsp+60h+var_38], rax
0x140002b8a  lea     rax, [rbp+var_10]
0x140002b8e  mov     [rsp+60h+var_40], rax
0x140002b93  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x140002b98  jmp     short loc_140002C03
0x140002b9a  mov     rdi, rax
0x140002b9d  mov     r8d, 64667072h
0x140002ba3  mov     rdx, rsi
0x140002ba6  mov     ecx, 40h ; '@'
0x140002bab  call    cs:__imp_ExAllocatePool2
0x140002bb2  nop     dword ptr [rax+rax+00h]
0x140002bb7  mov     [rdi+10h], rax
0x140002bbb  test    rax, rax
0x140002bbe  jnz     short loc_140002C26
0x140002bc0  mov     eax, cs:dword_140012050
0x140002bc6  cmp     eax, 2
0x140002bc9  jbe     short loc_140002BFB
0x140002bcb  lea     rax, aFailedToAlloca_7; "Failed to allocate routing rules buffer"
0x140002bd2  mov     [rbp+var_30], 0C000009Ah
0x140002bd9  mov     [rbp+var_10], rax
0x140002bdd  lea     rdx, unk_14000E198
0x140002be4  lea     rax, [rbp+var_30]
0x140002be8  mov     [rsp+60h+var_38], rax
0x140002bed  lea     rax, [rbp+var_10]
0x140002bf1  mov     [rsp+60h+var_40], rax
0x140002bf6  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x140002bfb  mov     rcx, rdi; P
0x140002bfe  call    FreeRulesEntry
0x140002c03  cmp     qword ptr [rbp+var_20], 0
0x140002c08  jz      short loc_140002C1C
0x140002c0a  movaps  xmm0, [rbp+var_20]
0x140002c0e  lea     rcx, [rbp+var_20]; struct SpinLockAndSavedIrql *
0x140002c12  movdqa  [rbp+var_20], xmm0
0x140002c17  call    ?Release@SpinLockAndSavedIrql@@SAXAEBU1@@Z; SpinLockAndSavedIrql::Release(SpinLockAndSavedIrql const &)
0x140002c1c  mov     eax, 0C000009Ah
0x140002c21  jmp     loc_140002CE3
0x140002c26  mov     r8, rsi; Size
0x140002c29  mov     rdx, r14; Src
0x140002c2c  mov     rcx, rax; void *
0x140002c2f  call    memmove
0x140002c34  mov     rcx, [rdi+10h]; struct WcmRoutePolicy::RoutingRulesForInterface *
0x140002c38  call    ?AddOrReferencePackageEntriesForRoutingRules@@YAJPEBURoutingRulesForInterface@WcmRoutePolicy@@@Z; AddOrReferencePackageEntriesForRoutingRules(WcmRoutePolicy::RoutingRulesForInterface const *)
0x140002c3d  mov     esi, eax
0x140002c3f  test    eax, eax
0x140002c41  jns     short loc_140002C9F
0x140002c43  mov     ecx, cs:dword_140012050
0x140002c49  cmp     ecx, 2
0x140002c4c  jbe     short loc_140002C7A
0x140002c4e  mov     [rbp+var_30], eax
0x140002c51  lea     rdx, word_14000E54E
0x140002c58  lea     rax, aAddorreference; "AddOrReferencePackageEntryForRoutingRul"...
0x140002c5f  mov     [rbp+var_10], rax
0x140002c63  lea     rax, [rbp+var_30]
0x140002c67  mov     [rsp+60h+var_38], rax
0x140002c6c  lea     rax, [rbp+var_10]
0x140002c70  mov     [rsp+60h+var_40], rax
0x140002c75  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x140002c7a  mov     rcx, rdi; P
0x140002c7d  call    FreeRulesEntry
0x140002c82  cmp     qword ptr [rbp+var_20], 0
0x140002c87  jz      short loc_140002C9B
0x140002c89  movaps  xmm0, [rbp+var_20]
0x140002c8d  lea     rcx, [rbp+var_20]; struct SpinLockAndSavedIrql *
0x140002c91  movdqa  [rbp+var_20], xmm0
0x140002c96  call    ?Release@SpinLockAndSavedIrql@@SAXAEBU1@@Z; SpinLockAndSavedIrql::Release(SpinLockAndSavedIrql const &)
0x140002c9b  mov     eax, esi
0x140002c9d  jmp     short loc_140002CE3
0x140002c9f  test    rbx, rbx
0x140002ca2  jz      short loc_140002CC8
0x140002ca4  mov     rax, cs:qword_140012390
0x140002cab  cmp     [rax], r12
0x140002cae  jz      short loc_140002CB7
0x140002cb0  mov     ecx, 3
0x140002cb5  int     29h; Win8: RtlFailFast(ecx)
0x140002cb7  mov     [rbx], r12
0x140002cba  mov     [rbx+8], rax
0x140002cbe  mov     [rax], rbx
0x140002cc1  mov     cs:qword_140012390, rbx
0x140002cc8  cmp     qword ptr [rbp+var_20], 0
0x140002ccd  jz      short loc_140002CE1
0x140002ccf  movaps  xmm0, [rbp+var_20]
0x140002cd3  lea     rcx, [rbp+var_20]; struct SpinLockAndSavedIrql *
0x140002cd7  movdqa  [rbp+var_20], xmm0
0x140002cdc  call    ?Release@SpinLockAndSavedIrql@@SAXAEBU1@@Z; SpinLockAndSavedIrql::Release(SpinLockAndSavedIrql const &)
0x140002ce1  xor     eax, eax
0x140002ce3  mov     rbx, [rsp+60h+arg_10]
0x140002ceb  add     rsp, 60h
0x140002cef  pop     r14
0x140002cf1  pop     r12
0x140002cf3  pop     rdi
0x140002cf4  pop     rsi
0x140002cf5  pop     rbp
0x140002cf6  retn
```
