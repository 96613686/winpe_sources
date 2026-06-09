# CInterceptor_IWbemSyncProvider::GetObjects(IWbemServices *,long,IWbemObjectAccess * *,long,IWbemContext *)

- ea: `0x140037b70`
- end: `0x140037cce`
- name: `?GetObjects@CInterceptor_IWbemSyncProvider@@UEAAJPEAUIWbemServices@@JPEAPEAUIWbemObjectAccess@@JPEAUIWbemContext@@@Z`
- size: `350`
- prototype: `__int64 __fastcall(CInterceptor_IWbemSyncProvider *__hidden this, struct IWbemServices *, int, struct IWbemObjectAccess **, int, struct IWbemContext *)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x140006c64`
- `0x14001ca74`
- `0x1400234b8`
- `0x140037b70`
- `0x140048010`

## import_xrefs

- `wbemcomn!GetMemLogObject` at `0x140037c39`
- `wbemcomn!GetMemLogObject` at `0x140037c73`
- `wbemcomn!GetMemLogObject` at `0x140037c39`
- `wbemcomn!GetMemLogObject` at `0x140037c73`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x140037c44`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x140037c83`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x140037c44`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x140037c83`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x140037c18`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x140037c18`

## pseudocode

```c
__int64 __fastcall CInterceptor_IWbemSyncProvider::GetObjects(
        CInterceptor_IWbemSyncProvider *this,
        struct IWbemServices *a2,
        unsigned int a3,
        struct IWbemObjectAccess **a4,
        int a5,
        struct IWbemContext *a6)
{
  int v10; // ebx
  CMemoryLog *MemLogObject; // rax
  _QWORD *v12; // rcx
  __int64 v13; // rdx
  __int64 v14; // r9
  CMemoryLog *v15; // rax
  struct IServerSecurity *v17; // [rsp+40h] [rbp-38h] BYREF
  struct IUnknown *v18; // [rsp+48h] [rbp-30h] BYREF
  int v19; // [rsp+80h] [rbp+8h] BYREF

  if ( *((_QWORD *)this + 35)
    && (v19 = 0, v18 = 0, v17 = 0, (int)ProviderSubSystem_Common_Globals::BeginImpersonation(&v18, &v17, &v19, 0) >= 0) )
  {
    if ( ProviderSubSystem_Globals::s_SharedCounters )
      ++*((_QWORD *)ProviderSubSystem_Globals::s_SharedCounters + 31);
    ++*((_QWORD *)this + 91);
    v10 = (*(__int64 (__fastcall **)(_QWORD, struct IWbemServices *, _QWORD, struct IWbemObjectAccess **, int, struct IWbemContext *))(**((_QWORD **)this + 35) + 64LL))(
            *((_QWORD *)this + 35),
            a2,
            a3,
            a4,
            a5,
            a6);
    CoRevertToSelf();
    ProviderSubSystem_Common_Globals::EndImpersonation(v18, v17, v19);
    if ( v10 < 0 )
    {
      MemLogObject = GetMemLogObject();
      CMemoryLog::Write(MemLogObject, v10);
    }
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v13 = 167;
      v14 = (unsigned int)v10;
LABEL_15:
      WPP_SF_d(v12[2], v13, WPP_8fe8ac2c7c0037f5bee7c55b6a976ec1_Traceguids, v14);
    }
  }
  else
  {
    v15 = GetMemLogObject();
    v10 = -2147217372;
    CMemoryLog::Write(v15, -2147217372);
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v13 = 168;
      v14 = 2147749924LL;
      goto LABEL_15;
    }
  }
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x140037b70  mov     rax, rsp
0x140037b73  push    rbx
0x140037b74  push    rbp
0x140037b75  push    rsi
0x140037b76  push    rdi
0x140037b77  sub     rsp, 58h
0x140037b7b  cmp     qword ptr [rcx+118h], 0
0x140037b83  mov     rdi, r9
0x140037b86  mov     esi, r8d
0x140037b89  mov     rbp, rdx
0x140037b8c  mov     rbx, rcx
0x140037b8f  jz      loc_140037C73
0x140037b95  xor     r9d, r9d; unsigned int *
0x140037b98  mov     dword ptr [rax+8], 0
0x140037b9f  lea     r8, [rax+8]; int *
0x140037ba3  mov     qword ptr [rax-30h], 0
0x140037bab  lea     rdx, [rax-38h]; struct IServerSecurity **
0x140037baf  mov     qword ptr [rax-38h], 0
0x140037bb7  lea     rcx, [rax-30h]; ppInterface
0x140037bbb  call    ?BeginImpersonation@ProviderSubSystem_Common_Globals@@SAJAEAPEAUIUnknown@@AEAPEAUIServerSecurity@@AEAHPEAK@Z; ProviderSubSystem_Common_Globals::BeginImpersonation(IUnknown * &,IServerSecurity * &,int &,ulong *)
0x140037bc0  test    eax, eax
0x140037bc2  js      loc_140037C73
0x140037bc8  mov     rax, cs:?s_SharedCounters@ProviderSubSystem_Globals@@2PEAVCServerObject_ProviderSubsystem_Counters@@EA; CServerObject_ProviderSubsystem_Counters * ProviderSubSystem_Globals::s_SharedCounters
0x140037bcf  test    rax, rax
0x140037bd2  jz      short loc_140037BDB
0x140037bd4  inc     qword ptr [rax+0F8h]
0x140037bdb  inc     qword ptr [rbx+2D8h]
0x140037be2  mov     r9, rdi
0x140037be5  mov     rdx, [rsp+78h+arg_28]
0x140037bed  mov     r8d, esi
0x140037bf0  mov     rcx, [rbx+118h]
0x140037bf7  mov     [rsp+78h+var_50], rdx
0x140037bfc  mov     edx, [rsp+78h+arg_20]
0x140037c03  mov     [rsp+78h+var_58], edx
0x140037c07  mov     rdx, rbp
0x140037c0a  mov     rax, [rcx]
0x140037c0d  mov     rax, [rax+40h]
0x140037c11  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140037c16  mov     ebx, eax
0x140037c18  call    cs:__imp_CoRevertToSelf
0x140037c1e  mov     r8d, [rsp+78h+arg_0]; int
0x140037c26  mov     rdx, [rsp+78h+var_38]; struct IServerSecurity *
0x140037c2b  mov     rcx, [rsp+78h+var_30]; struct IUnknown *
0x140037c30  call    ?EndImpersonation@ProviderSubSystem_Common_Globals@@SAJPEAUIUnknown@@PEAUIServerSecurity@@H@Z; ProviderSubSystem_Common_Globals::EndImpersonation(IUnknown *,IServerSecurity *,int)
0x140037c35  test    ebx, ebx
0x140037c37  jns     short loc_140037C4A
0x140037c39  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x140037c3f  mov     rcx, rax
0x140037c42  mov     edx, ebx
0x140037c44  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x140037c4a  mov     rcx, cs:WPP_GLOBAL_Control
0x140037c51  lea     rax, WPP_GLOBAL_Control
0x140037c58  cmp     rcx, rax
0x140037c5b  jz      short loc_140037CC3
0x140037c5d  test    byte ptr [rcx+1Ch], 4
0x140037c61  jz      short loc_140037CC3
0x140037c63  cmp     byte ptr [rcx+19h], 2
0x140037c67  jb      short loc_140037CC3
0x140037c69  mov     edx, 0A7h
0x140037c6e  mov     r9d, ebx
0x140037c71  jmp     short loc_140037CB3
0x140037c73  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x140037c79  mov     ebx, 80041024h
0x140037c7e  mov     rcx, rax
0x140037c81  mov     edx, ebx
0x140037c83  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x140037c89  mov     rcx, cs:WPP_GLOBAL_Control
0x140037c90  lea     rax, WPP_GLOBAL_Control
0x140037c97  cmp     rcx, rax
0x140037c9a  jz      short loc_140037CC3
0x140037c9c  test    byte ptr [rcx+1Ch], 4
0x140037ca0  jz      short loc_140037CC3
0x140037ca2  cmp     byte ptr [rcx+19h], 2
0x140037ca6  jb      short loc_140037CC3
0x140037ca8  mov     edx, 0A8h
0x140037cad  mov     r9d, 80041024h
0x140037cb3  mov     rcx, [rcx+10h]
0x140037cb7  lea     r8, WPP_8fe8ac2c7c0037f5bee7c55b6a976ec1_Traceguids
0x140037cbe  call    WPP_SF_d
0x140037cc3  mov     eax, ebx
0x140037cc5  add     rsp, 58h
0x140037cc9  pop     rdi
0x140037cca  pop     rsi
0x140037ccb  pop     rbp
0x140037ccc  pop     rbx
0x140037ccd  retn
```
