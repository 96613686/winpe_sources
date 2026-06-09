# CServerObject_Host::GetObjectW(_GUID const &,long,IWbemContext *,_GUID const &,void * *)

- ea: `0x140023dd0`
- end: `0x140023f76`
- name: `?GetObjectW@CServerObject_Host@@UEAAJAEBU_GUID@@JPEAUIWbemContext@@0PEAPEAX@Z`
- size: `422`
- prototype: `__int64 __fastcall(CServerObject_Host *__hidden this, const struct _GUID *, int, struct IWbemContext *, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `7`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callees

- `0x14000a0f0`
- `0x14000a530`
- `0x1400234b8`
- `0x140023dd0`
- `0x140023f7c`
- `0x140023fdc`
- `0x140048010`

## import_xrefs

- `wbemcomn!GetMemLogObject` at `0x140023f31`
- `wbemcomn!GetMemLogObject` at `0x140023f60`
- `wbemcomn!GetMemLogObject` at `0x140023f31`
- `wbemcomn!GetMemLogObject` at `0x140023f60`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x140023f3c`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x140023f6b`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x140023f3c`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x140023f6b`

## pseudocode

```c
__int64 __fastcall CServerObject_Host::GetObjectW(
        CServerObject_Host *this,
        const struct _GUID *a2,
        __int64 a3,
        struct IWbemContext *a4,
        const struct _GUID *a5,
        void **a6)
{
  __int64 v6; // rax
  CServerObject_RawFactory *v7; // rax
  struct WmiAllocator *v8; // rdx
  CServerObject_RawFactory *v10; // rax
  CServerObject_RawFactory *v11; // rdi
  int v12; // ebx
  _QWORD *v13; // rcx
  __int64 v14; // rax
  CServerObject_ProviderRefresherManager *v15; // rax
  struct WmiAllocator *v16; // rdx
  CServerObject_ProviderRefresherManager *v17; // rax
  CServerObject_ProviderRefresherManager *v18; // rdi
  __int64 v19; // rdx
  CMemoryLog *MemLogObject; // rax
  CMemoryLog *v21; // rax

  v6 = *(_QWORD *)&a2->Data1 - *(_QWORD *)&CLSID_WmiProviderHostedInProcFactory.Data1;
  if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&CLSID_WmiProviderHostedInProcFactory.Data1 )
    v6 = *(_QWORD *)a2->Data4 - *(_QWORD *)CLSID_WmiProviderHostedInProcFactory.Data4;
  if ( !v6 )
  {
    v7 = (CServerObject_RawFactory *)operator new(0x50u);
    if ( v7 )
    {
      v10 = CServerObject_RawFactory::CServerObject_RawFactory(v7, v8);
      v11 = v10;
      if ( v10 )
      {
        v12 = (**(__int64 (__fastcall ***)(CServerObject_RawFactory *, const struct _GUID *, void **))v10)(v10, a5, a6);
        if ( v12 < 0 )
        {
          operator delete(v11);
          MemLogObject = GetMemLogObject();
          CMemoryLog::Write(MemLogObject, v12);
        }
        v13 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          return (unsigned int)v12;
        }
        v19 = 56;
LABEL_23:
        WPP_SF_d(v13[2], v19, WPP_d8170f1873f8382224c8577312ab9d30_Traceguids, (unsigned int)v12);
        return (unsigned int)v12;
      }
    }
    return 2147942414LL;
  }
  v14 = *(_QWORD *)&a2->Data1 - *(_QWORD *)&CLSID__WbemHostedRefresherMgr.Data1;
  if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&CLSID__WbemHostedRefresherMgr.Data1 )
    v14 = *(_QWORD *)a2->Data4 - *(_QWORD *)CLSID__WbemHostedRefresherMgr.Data4;
  if ( !v14 )
  {
    v15 = (CServerObject_ProviderRefresherManager *)operator new(0x30u);
    if ( v15 )
    {
      v17 = CServerObject_ProviderRefresherManager::CServerObject_ProviderRefresherManager(v15, v16);
      v18 = v17;
      if ( v17 )
      {
        v12 = (**(__int64 (__fastcall ***)(CServerObject_ProviderRefresherManager *, const struct _GUID *, void **))v17)(
                v17,
                a5,
                a6);
        if ( v12 < 0 )
        {
          operator delete(v18);
          v21 = GetMemLogObject();
          CMemoryLog::Write(v21, v12);
        }
        v13 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          return (unsigned int)v12;
        }
        v19 = 57;
        goto LABEL_23;
      }
    }
    return 2147942414LL;
  }
  return 2147746065LL;
}

```

## disassembly

```asm
0x140023dd0  mov     [rsp+arg_0], rbx
0x140023dd5  push    rdi
0x140023dd6  sub     rsp, 30h
0x140023dda  mov     rax, [rdx]
0x140023ddd  sub     rax, qword ptr cs:CLSID_WmiProviderHostedInProcFactory.Data1
0x140023de4  jnz     short loc_140023DF1
0x140023de6  mov     rax, [rdx+8]
0x140023dea  sub     rax, qword ptr cs:CLSID_WmiProviderHostedInProcFactory.Data4
0x140023df1  test    rax, rax
0x140023df4  jnz     short loc_140023E6B
0x140023df6  lea     ecx, [rax+50h]; dwBytes
0x140023df9  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140023dfe  mov     [rsp+38h+var_18], rax
0x140023e03  test    rax, rax
0x140023e06  jnz     short loc_140023E0F
0x140023e08  mov     eax, 8007000Eh
0x140023e0d  jmp     short loc_140023E60
0x140023e0f  mov     rcx, rax; this
0x140023e12  call    ??0CServerObject_RawFactory@@QEAA@AEAVWmiAllocator@@@Z; CServerObject_RawFactory::CServerObject_RawFactory(WmiAllocator &)
0x140023e17  mov     rdi, rax
0x140023e1a  test    rax, rax
0x140023e1d  jz      short loc_140023E08
0x140023e1f  mov     rcx, [rax]
0x140023e22  mov     r8, [rsp+38h+arg_28]
0x140023e27  mov     rdx, [rsp+38h+arg_20]
0x140023e2c  mov     rax, [rcx]
0x140023e2f  mov     rcx, rdi
0x140023e32  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140023e37  mov     ebx, eax
0x140023e39  test    eax, eax
0x140023e3b  js      loc_140023F29
0x140023e41  mov     rcx, cs:WPP_GLOBAL_Control
0x140023e48  lea     rdx, WPP_GLOBAL_Control
0x140023e4f  cmp     rcx, rdx
0x140023e52  jz      short loc_140023E5E
0x140023e54  test    byte ptr [rcx+1Ch], 4
0x140023e58  jnz     loc_140023F47
0x140023e5e  mov     eax, ebx
0x140023e60  mov     rbx, [rsp+38h+arg_0]
0x140023e65  add     rsp, 30h
0x140023e69  pop     rdi
0x140023e6a  retn
0x140023e6b  mov     rax, [rdx]
0x140023e6e  sub     rax, qword ptr cs:CLSID__WbemHostedRefresherMgr.Data1
0x140023e75  jnz     short loc_140023E82
0x140023e77  mov     rax, [rdx+8]
0x140023e7b  sub     rax, qword ptr cs:CLSID__WbemHostedRefresherMgr.Data4
0x140023e82  test    rax, rax
0x140023e85  jnz     loc_140023F1F
0x140023e8b  lea     ecx, [rax+30h]; dwBytes
0x140023e8e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140023e93  mov     [rsp+38h+var_18], rax
0x140023e98  test    rax, rax
0x140023e9b  jz      loc_140023E08
0x140023ea1  mov     rcx, rax; this
0x140023ea4  call    ??0CServerObject_ProviderRefresherManager@@QEAA@AEAVWmiAllocator@@@Z; CServerObject_ProviderRefresherManager::CServerObject_ProviderRefresherManager(WmiAllocator &)
0x140023ea9  mov     rdi, rax
0x140023eac  test    rax, rax
0x140023eaf  jz      loc_140023E08
0x140023eb5  mov     rcx, [rax]
0x140023eb8  mov     r8, [rsp+38h+arg_28]
0x140023ebd  mov     rdx, [rsp+38h+arg_20]
0x140023ec2  mov     rax, [rcx]
0x140023ec5  mov     rcx, rdi
0x140023ec8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140023ecd  mov     ebx, eax
0x140023ecf  test    eax, eax
0x140023ed1  js      loc_140023F58
0x140023ed7  mov     rcx, cs:WPP_GLOBAL_Control
0x140023ede  lea     rdx, WPP_GLOBAL_Control
0x140023ee5  cmp     rcx, rdx
0x140023ee8  jz      loc_140023E5E
0x140023eee  test    byte ptr [rcx+1Ch], 4
0x140023ef2  jz      loc_140023E5E
0x140023ef8  cmp     byte ptr [rcx+19h], 2
0x140023efc  jb      loc_140023E5E
0x140023f02  mov     edx, 39h ; '9'
0x140023f07  mov     rcx, [rcx+10h]
0x140023f0b  lea     r8, WPP_d8170f1873f8382224c8577312ab9d30_Traceguids
0x140023f12  mov     r9d, ebx
0x140023f15  call    WPP_SF_d
0x140023f1a  jmp     loc_140023E5E
0x140023f1f  mov     eax, 80040111h
0x140023f24  jmp     loc_140023E60
0x140023f29  mov     rcx, rdi; lpMem
0x140023f2c  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140023f31  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x140023f37  mov     rcx, rax
0x140023f3a  mov     edx, ebx
0x140023f3c  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x140023f42  jmp     loc_140023E41
0x140023f47  cmp     byte ptr [rcx+19h], 2
0x140023f4b  jb      loc_140023E5E
0x140023f51  mov     edx, 38h ; '8'
0x140023f56  jmp     short loc_140023F07
0x140023f58  mov     rcx, rdi; lpMem
0x140023f5b  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140023f60  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x140023f66  mov     rcx, rax
0x140023f69  mov     edx, ebx
0x140023f6b  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x140023f71  jmp     loc_140023ED7
```
