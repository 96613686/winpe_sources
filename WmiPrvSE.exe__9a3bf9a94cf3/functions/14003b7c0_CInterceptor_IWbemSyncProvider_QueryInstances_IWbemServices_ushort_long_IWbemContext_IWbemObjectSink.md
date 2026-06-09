# CInterceptor_IWbemSyncProvider::QueryInstances(IWbemServices *,ushort *,long,IWbemContext *,IWbemObjectSink *)

- ea: `0x14003b7c0`
- end: `0x14003b920`
- name: `?QueryInstances@CInterceptor_IWbemSyncProvider@@UEAAJPEAUIWbemServices@@PEAGJPEAUIWbemContext@@PEAUIWbemObjectSink@@@Z`
- size: `352`
- prototype: `__int64 __fastcall(CInterceptor_IWbemSyncProvider *__hidden this, struct IWbemServices *, unsigned __int16 *, int, struct IWbemContext *, struct IWbemObjectSink *)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x140006c64`
- `0x14001ca74`
- `0x1400234b8`
- `0x14003b7c0`
- `0x140048010`

## import_xrefs

- `wbemcomn!GetMemLogObject` at `0x14003b88b`
- `wbemcomn!GetMemLogObject` at `0x14003b8c5`
- `wbemcomn!GetMemLogObject` at `0x14003b88b`
- `wbemcomn!GetMemLogObject` at `0x14003b8c5`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x14003b896`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x14003b8d5`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x14003b896`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x14003b8d5`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x14003b86a`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x14003b86a`

## pseudocode

```c
__int64 __fastcall CInterceptor_IWbemSyncProvider::QueryInstances(
        CInterceptor_IWbemSyncProvider *this,
        struct IWbemServices *a2,
        unsigned __int16 *a3,
        unsigned int a4,
        struct IWbemContext *a5,
        struct IWbemObjectSink *a6)
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
      ++*((_QWORD *)ProviderSubSystem_Globals::s_SharedCounters + 26);
    ++*((_QWORD *)this + 86);
    v10 = (*(__int64 (__fastcall **)(_QWORD, struct IWbemServices *, unsigned __int16 *, _QWORD, struct IWbemContext *, struct IWbemObjectSink *))(**((_QWORD **)this + 35) + 24LL))(
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
      v13 = 153;
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
      v13 = 154;
      v14 = 2147749924LL;
      goto LABEL_15;
    }
  }
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x14003b7c0  mov     rax, rsp
0x14003b7c3  push    rbx
0x14003b7c4  push    rbp
0x14003b7c5  push    rsi
0x14003b7c6  push    rdi
0x14003b7c7  sub     rsp, 58h
0x14003b7cb  cmp     qword ptr [rcx+118h], 0
0x14003b7d3  mov     edi, r9d
0x14003b7d6  mov     rsi, r8
0x14003b7d9  mov     rbp, rdx
0x14003b7dc  mov     rbx, rcx
0x14003b7df  jz      loc_14003B8C5
0x14003b7e5  xor     r9d, r9d; unsigned int *
0x14003b7e8  mov     dword ptr [rax+8], 0
0x14003b7ef  lea     r8, [rax+8]; int *
0x14003b7f3  mov     qword ptr [rax-30h], 0
0x14003b7fb  lea     rdx, [rax-38h]; struct IServerSecurity **
0x14003b7ff  mov     qword ptr [rax-38h], 0
0x14003b807  lea     rcx, [rax-30h]; ppInterface
0x14003b80b  call    ?BeginImpersonation@ProviderSubSystem_Common_Globals@@SAJAEAPEAUIUnknown@@AEAPEAUIServerSecurity@@AEAHPEAK@Z; ProviderSubSystem_Common_Globals::BeginImpersonation(IUnknown * &,IServerSecurity * &,int &,ulong *)
0x14003b810  test    eax, eax
0x14003b812  js      loc_14003B8C5
0x14003b818  mov     rax, cs:?s_SharedCounters@ProviderSubSystem_Globals@@2PEAVCServerObject_ProviderSubsystem_Counters@@EA; CServerObject_ProviderSubsystem_Counters * ProviderSubSystem_Globals::s_SharedCounters
0x14003b81f  test    rax, rax
0x14003b822  jz      short loc_14003B82B
0x14003b824  inc     qword ptr [rax+0D0h]
0x14003b82b  inc     qword ptr [rbx+2B0h]
0x14003b832  mov     r9d, edi
0x14003b835  mov     rcx, [rbx+118h]
0x14003b83c  mov     r8, rsi
0x14003b83f  mov     rdx, [rsp+78h+arg_28]
0x14003b847  mov     [rsp+78h+var_50], rdx
0x14003b84c  mov     rdx, [rsp+78h+arg_20]
0x14003b854  mov     rax, [rcx]
0x14003b857  mov     [rsp+78h+var_58], rdx
0x14003b85c  mov     rdx, rbp
0x14003b85f  mov     rax, [rax+18h]
0x14003b863  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003b868  mov     ebx, eax
0x14003b86a  call    cs:__imp_CoRevertToSelf
0x14003b870  mov     r8d, [rsp+78h+arg_0]; int
0x14003b878  mov     rdx, [rsp+78h+var_38]; struct IServerSecurity *
0x14003b87d  mov     rcx, [rsp+78h+var_30]; struct IUnknown *
0x14003b882  call    ?EndImpersonation@ProviderSubSystem_Common_Globals@@SAJPEAUIUnknown@@PEAUIServerSecurity@@H@Z; ProviderSubSystem_Common_Globals::EndImpersonation(IUnknown *,IServerSecurity *,int)
0x14003b887  test    ebx, ebx
0x14003b889  jns     short loc_14003B89C
0x14003b88b  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x14003b891  mov     rcx, rax
0x14003b894  mov     edx, ebx
0x14003b896  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x14003b89c  mov     rcx, cs:WPP_GLOBAL_Control
0x14003b8a3  lea     rax, WPP_GLOBAL_Control
0x14003b8aa  cmp     rcx, rax
0x14003b8ad  jz      short loc_14003B915
0x14003b8af  test    byte ptr [rcx+1Ch], 4
0x14003b8b3  jz      short loc_14003B915
0x14003b8b5  cmp     byte ptr [rcx+19h], 2
0x14003b8b9  jb      short loc_14003B915
0x14003b8bb  mov     edx, 99h
0x14003b8c0  mov     r9d, ebx
0x14003b8c3  jmp     short loc_14003B905
0x14003b8c5  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x14003b8cb  mov     ebx, 80041024h
0x14003b8d0  mov     rcx, rax
0x14003b8d3  mov     edx, ebx
0x14003b8d5  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x14003b8db  mov     rcx, cs:WPP_GLOBAL_Control
0x14003b8e2  lea     rax, WPP_GLOBAL_Control
0x14003b8e9  cmp     rcx, rax
0x14003b8ec  jz      short loc_14003B915
0x14003b8ee  test    byte ptr [rcx+1Ch], 4
0x14003b8f2  jz      short loc_14003B915
0x14003b8f4  cmp     byte ptr [rcx+19h], 2
0x14003b8f8  jb      short loc_14003B915
0x14003b8fa  mov     edx, 9Ah
0x14003b8ff  mov     r9d, 80041024h
0x14003b905  mov     rcx, [rcx+10h]
0x14003b909  lea     r8, WPP_8fe8ac2c7c0037f5bee7c55b6a976ec1_Traceguids
0x14003b910  call    WPP_SF_d
0x14003b915  mov     eax, ebx
0x14003b917  add     rsp, 58h
0x14003b91b  pop     rdi
0x14003b91c  pop     rsi
0x14003b91d  pop     rbp
0x14003b91e  pop     rbx
0x14003b91f  retn
```
