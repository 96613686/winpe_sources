# AddOrReferencePackageEntryForRoutingRule

- ea: `0x1400016a0`
- end: `0x1400018c5`
- name: `AddOrReferencePackageEntryForRoutingRule`
- size: `549`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, authz_impersonation, registry_config`

## callers

- `0x1400015fc`

## callees

- `0x140001008`
- `0x1400010b0`
- `0x14000116c`
- `0x1400016a0`
- `0x140001aac`
- `0x14000242c`
- `0x140002590`
- `0x14000a780`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x1400016ef`
- `ntoskrnl!ExAllocatePool2` at `0x1400017ac`
- `ntoskrnl!ExAllocatePool2` at `0x1400016ef`
- `ntoskrnl!ExAllocatePool2` at `0x1400017ac`

## string_xrefs

- `0x140001822`: `Failed to copy AppId`

## pseudocode

```c
__int64 __fastcall AddOrReferencePackageEntryForRoutingRule(__int64 a1)
{
  PVOID *i; // rbx
  int v3; // ecx
  int v4; // r8d
  int v5; // r9d
  __int64 v6; // rcx
  const char **Pool2; // rbx
  __int64 v8; // r8
  __int64 v9; // r9
  unsigned int v10; // edi
  char *v12; // rax
  __int64 v13; // rcx
  __int64 v14; // r8
  __int64 v15; // r9
  const char *v16; // rax
  unsigned __int8 *v17; // rdx
  __int64 v18; // r8
  int v19; // r9d
  int v20; // eax
  int v21; // ecx
  const char ***v22; // rax
  int v23; // [rsp+40h] [rbp-28h] BYREF
  const char *v24; // [rsp+48h] [rbp-20h] BYREF
  _QWORD v25[3]; // [rsp+50h] [rbp-18h] BYREF

  for ( i = (PVOID *)g_packageListHead; i != &g_packageListHead; i = (PVOID *)*i )
  {
    if ( NPDoStringParametersMatch((PCWSTR)i[3], (PCWSTR)(a1 + 4), 1) )
    {
      ++*((_DWORD *)i + 8);
      if ( (unsigned int)dword_140012050 > 4 )
      {
        v23 = *((_DWORD *)i + 8);
        v25[0] = i[2];
        v24 = (const char *)i[3];
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapSid<_SID>,_tlgWrapperByVal<4>>(
          v3,
          (unsigned int)&unk_14000E320,
          v4,
          v5,
          (__int64)&v24,
          (__int64)v25,
          (__int64)&v23);
      }
      return 0;
    }
  }
  Pool2 = (const char **)ExAllocatePool2(64, 40, 1684435058);
  if ( !Pool2 )
  {
    v10 = -1073741670;
    if ( (unsigned int)dword_140012050 > 2 )
    {
      v23 = -1073741670;
      v24 = "Failed to allocate package entry";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        v6,
        (unsigned __int8 *)&dword_14000E634,
        v8,
        v9,
        (int **)&v24,
        (__int64)&v23);
    }
    return v10;
  }
  v12 = (char *)ExAllocatePool2(64, *(unsigned int *)(a1 + 468), 1684435058);
  Pool2[2] = v12;
  if ( !v12 )
  {
    v10 = -1073741670;
    if ( (unsigned int)dword_140012050 > 2 )
    {
      v23 = -1073741670;
      v16 = "Failed to allocate PackageId";
      v17 = (unsigned __int8 *)&unk_14000E250;
LABEL_17:
      v24 = v16;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        v13,
        v17,
        v14,
        v15,
        (int **)&v24,
        (__int64)&v23);
      goto LABEL_18;
    }
    goto LABEL_18;
  }
  memmove(v12, (const void *)(a1 + 472), *(unsigned int *)(a1 + 468));
  v20 = RoutePolicyCache::AllocateAndCopyStringParameter(Pool2 + 3, (unsigned __int16 **)(a1 + 4), v18, v19);
  v10 = v20;
  if ( v20 < 0 )
  {
    v13 = (unsigned int)dword_140012050;
    if ( (unsigned int)dword_140012050 > 2 )
    {
      v23 = v20;
      v17 = (unsigned __int8 *)&unk_14000E4F0;
      v16 = "Failed to copy AppId";
      goto LABEL_17;
    }
LABEL_18:
    FreePackageEntry(Pool2);
    return v10;
  }
  *((_DWORD *)Pool2 + 8) = 1;
  if ( (unsigned int)dword_140012050 > 4 )
  {
    v24 = Pool2[2];
    v25[0] = Pool2[3];
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapSid<_SID>>(
      v21,
      (unsigned int)&unk_14000E438,
      v14,
      v15,
      (__int64)v25,
      (__int64)&v24);
  }
  v22 = (const char ***)qword_1400123C8;
  if ( *(PVOID **)qword_1400123C8 != &g_packageListHead )
    __fastfail(3u);
  *Pool2 = (const char *)&g_packageListHead;
  Pool2[1] = (const char *)v22;
  *v22 = Pool2;
  qword_1400123C8 = (__int64)Pool2;
  return 0;
}

```

## disassembly

```asm
0x1400016a0  push    rbp
0x1400016a2  push    rbx
0x1400016a3  push    rsi
0x1400016a4  push    rdi
0x1400016a5  push    r14
0x1400016a7  push    r15
0x1400016a9  mov     rbp, rsp
0x1400016ac  sub     rsp, 68h
0x1400016b0  mov     rbx, cs:?g_packageListHead@@3U_LIST_ENTRY@@A; _LIST_ENTRY g_packageListHead
0x1400016b7  lea     r15, ?g_packageListHead@@3U_LIST_ENTRY@@A; _LIST_ENTRY g_packageListHead
0x1400016be  mov     rdi, rcx
0x1400016c1  jmp     short loc_1400016DA
0x1400016c3  mov     rcx, [rbx+18h]; SourceString
0x1400016c7  lea     rdx, [rdi+4]; PCWSTR
0x1400016cb  mov     r8b, 1; bool
0x1400016ce  call    ?NPDoStringParametersMatch@@YA_NPEBG0_N@Z; NPDoStringParametersMatch(ushort const *,ushort const *,bool)
0x1400016d3  test    al, al
0x1400016d5  jnz     short loc_14000174A
0x1400016d7  mov     rbx, [rbx]
0x1400016da  cmp     rbx, r15
0x1400016dd  jnz     short loc_1400016C3
0x1400016df  mov     edx, 28h ; '('
0x1400016e4  mov     esi, 64667072h
0x1400016e9  mov     r8d, esi
0x1400016ec  lea     ecx, [rdx+18h]
0x1400016ef  call    cs:__imp_ExAllocatePool2
0x1400016f6  nop     dword ptr [rax+rax+00h]
0x1400016fb  mov     rbx, rax
0x1400016fe  test    rax, rax
0x140001701  jnz     loc_14000179E
0x140001707  mov     eax, cs:dword_140012050
0x14000170d  mov     edi, 0C000009Ah
0x140001712  cmp     eax, 2
0x140001715  jbe     short loc_140001743
0x140001717  lea     rax, aFailedToAlloca_6; "Failed to allocate package entry"
0x14000171e  mov     [rbp+var_28], edi
0x140001721  mov     [rbp+var_20], rax
0x140001725  lea     rdx, dword_14000E634
0x14000172c  lea     rax, [rbp+var_28]
0x140001730  mov     [rsp+68h+var_40], rax
0x140001735  lea     rax, [rbp+var_20]
0x140001739  mov     [rsp+68h+var_48], rax
0x14000173e  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x140001743  mov     eax, edi
0x140001745  jmp     loc_1400018B7
0x14000174a  inc     dword ptr [rbx+20h]
0x14000174d  mov     eax, cs:dword_140012050
0x140001753  cmp     eax, 4
0x140001756  jbe     loc_1400018B5
0x14000175c  mov     eax, [rbx+20h]
0x14000175f  lea     rdx, unk_14000E320
0x140001766  mov     [rbp+var_28], eax
0x140001769  mov     rax, [rbx+10h]
0x14000176d  mov     [rbp+var_18], rax
0x140001771  mov     rax, [rbx+18h]
0x140001775  mov     [rbp+var_20], rax
0x140001779  lea     rax, [rbp+var_28]
0x14000177d  mov     [rsp+68h+var_38], rax
0x140001782  lea     rax, [rbp+var_18]
0x140001786  mov     [rsp+68h+var_40], rax
0x14000178b  lea     rax, [rbp+var_20]
0x14000178f  mov     [rsp+68h+var_48], rax
0x140001794  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapSid@U_SID@@@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapSid@U_SID@@@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapSid<_SID>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapSid<_SID> const &,_tlgWrapperByVal<4> const &)
0x140001799  jmp     loc_1400018B5
0x14000179e  mov     edx, [rdi+1D4h]
0x1400017a4  mov     r8d, esi
0x1400017a7  mov     ecx, 40h ; '@'
0x1400017ac  call    cs:__imp_ExAllocatePool2
0x1400017b3  nop     dword ptr [rax+rax+00h]
0x1400017b8  mov     [rbx+10h], rax
0x1400017bc  test    rax, rax
0x1400017bf  jnz     short loc_1400017E4
0x1400017c1  mov     eax, cs:dword_140012050
0x1400017c7  mov     edi, 0C000009Ah
0x1400017cc  cmp     eax, 2
0x1400017cf  jbe     short loc_140001844
0x1400017d1  mov     [rbp+var_28], edi
0x1400017d4  lea     rax, aFailedToAlloca_4; "Failed to allocate PackageId"
0x1400017db  lea     rdx, unk_14000E250
0x1400017e2  jmp     short loc_140001829
0x1400017e4  mov     r8d, [rdi+1D4h]; Size
0x1400017eb  lea     rdx, [rdi+1D8h]; Src
0x1400017f2  mov     rcx, rax; void *
0x1400017f5  call    memmove
0x1400017fa  lea     rdx, [rdi+4]; unsigned __int16 **
0x1400017fe  lea     rcx, [rbx+18h]; this
0x140001802  call    ?AllocateAndCopyStringParameter@RoutePolicyCache@@YAJPEAPEAGPEBG@Z; RoutePolicyCache::AllocateAndCopyStringParameter(ushort * *,ushort const *)
0x140001807  mov     edi, eax
0x140001809  test    eax, eax
0x14000180b  jns     short loc_140001851
0x14000180d  mov     ecx, cs:dword_140012050
0x140001813  cmp     ecx, 2
0x140001816  jbe     short loc_140001844
0x140001818  mov     [rbp+var_28], eax
0x14000181b  lea     rdx, unk_14000E4F0
0x140001822  lea     rax, aFailedToCopyAp; "Failed to copy AppId"
0x140001829  mov     [rbp+var_20], rax
0x14000182d  lea     rax, [rbp+var_28]
0x140001831  mov     [rsp+68h+var_40], rax
0x140001836  lea     rax, [rbp+var_20]
0x14000183a  mov     [rsp+68h+var_48], rax
0x14000183f  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x140001844  mov     rcx, rbx; P
0x140001847  call    FreePackageEntry
0x14000184c  jmp     loc_140001743
0x140001851  mov     dword ptr [rbx+20h], 1
0x140001858  mov     eax, cs:dword_140012050
0x14000185e  cmp     eax, 4
0x140001861  jbe     short loc_140001891
0x140001863  mov     rax, [rbx+10h]
0x140001867  lea     rdx, unk_14000E438
0x14000186e  mov     [rbp+var_20], rax
0x140001872  mov     rax, [rbx+18h]
0x140001876  mov     [rbp+var_18], rax
0x14000187a  lea     rax, [rbp+var_20]
0x14000187e  mov     [rsp+68h+var_40], rax
0x140001883  lea     rax, [rbp+var_18]
0x140001887  mov     [rsp+68h+var_48], rax
0x14000188c  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapSid@U_SID@@@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapSid@U_SID@@@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapSid<_SID>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapSid<_SID> const &)
0x140001891  mov     rax, cs:qword_1400123C8
0x140001898  cmp     [rax], r15
0x14000189b  jz      short loc_1400018A4
0x14000189d  mov     ecx, 3
0x1400018a2  int     29h; Win8: RtlFailFast(ecx)
0x1400018a4  mov     [rbx], r15
0x1400018a7  mov     [rbx+8], rax
0x1400018ab  mov     [rax], rbx
0x1400018ae  mov     cs:qword_1400123C8, rbx
0x1400018b5  xor     eax, eax
0x1400018b7  add     rsp, 68h
0x1400018bb  pop     r15
0x1400018bd  pop     r14
0x1400018bf  pop     rdi
0x1400018c0  pop     rsi
0x1400018c1  pop     rbx
0x1400018c2  pop     rbp
0x1400018c3  retn
```
