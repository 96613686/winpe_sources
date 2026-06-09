# CInterceptor_IWbemSyncProvider::CreateRefresher(IWbemServices *,long,IWbemRefresher * *)

- ea: `0x140036c90`
- end: `0x140036e18`
- name: `?CreateRefresher@CInterceptor_IWbemSyncProvider@@UEAAJPEAUIWbemServices@@JPEAPEAUIWbemRefresher@@@Z`
- size: `392`
- prototype: `__int64 __fastcall(CInterceptor_IWbemSyncProvider *this, struct IWbemServices *, unsigned int, struct IWbemRefresher **)`
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x140006c64`
- `0x14001ca74`
- `0x1400234b8`
- `0x140030478`
- `0x140036c90`
- `0x140048010`

## import_xrefs

- `wbemcomn!GetMemLogObject` at `0x140036d87`
- `wbemcomn!GetMemLogObject` at `0x140036dba`
- `wbemcomn!GetMemLogObject` at `0x140036d87`
- `wbemcomn!GetMemLogObject` at `0x140036dba`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x140036d92`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x140036dca`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x140036d92`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x140036dca`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x140036d69`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x140036d69`

## pseudocode

```c
__int64 __fastcall CInterceptor_IWbemSyncProvider::CreateRefresher(
        CInterceptor_IWbemSyncProvider *this,
        struct IWbemServices *a2,
        unsigned int a3,
        struct IWbemRefresher **a4)
{
  int v8; // ebx
  CMemoryLog *MemLogObject; // rax
  _QWORD *v10; // rcx
  __int64 v11; // rdx
  __int64 v12; // r9
  CMemoryLog *v13; // rax
  struct IServerSecurity *v15; // [rsp+30h] [rbp-28h] BYREF
  struct IUnknown *ppInterface; // [rsp+38h] [rbp-20h] BYREF
  int v17; // [rsp+60h] [rbp+8h] BYREF

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_qd(*((_QWORD *)WPP_GLOBAL_Control + 2), 155, WPP_8fe8ac2c7c0037f5bee7c55b6a976ec1_Traceguids, a2, a3);
  }
  if ( *((_QWORD *)this + 35)
    && (v17 = 0,
        ppInterface = 0,
        v15 = 0,
        (int)ProviderSubSystem_Common_Globals::BeginImpersonation(&ppInterface, &v15, &v17, 0) >= 0) )
  {
    if ( ProviderSubSystem_Globals::s_SharedCounters )
      ++*((_QWORD *)ProviderSubSystem_Globals::s_SharedCounters + 27);
    ++*((_QWORD *)this + 87);
    v8 = (*(__int64 (__fastcall **)(_QWORD, struct IWbemServices *, _QWORD, struct IWbemRefresher **))(**((_QWORD **)this + 35) + 32LL))(
           *((_QWORD *)this + 35),
           a2,
           a3,
           a4);
    CoRevertToSelf();
    ProviderSubSystem_Common_Globals::EndImpersonation(ppInterface, v15, v17);
    if ( v8 < 0 )
    {
      MemLogObject = GetMemLogObject();
      CMemoryLog::Write(MemLogObject, v8);
    }
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v11 = 156;
      v12 = (unsigned int)v8;
LABEL_19:
      WPP_SF_d(v10[2], v11, WPP_8fe8ac2c7c0037f5bee7c55b6a976ec1_Traceguids, v12);
    }
  }
  else
  {
    v13 = GetMemLogObject();
    v8 = -2147217372;
    CMemoryLog::Write(v13, -2147217372);
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v11 = 157;
      v12 = 2147749924LL;
      goto LABEL_19;
    }
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x140036c90  mov     [rsp+arg_8], rbx
0x140036c95  mov     [rsp+arg_10], rbp
0x140036c9a  push    rsi
0x140036c9b  push    rdi
0x140036c9c  push    r13
0x140036c9e  sub     rsp, 40h
0x140036ca2  mov     rbp, r9
0x140036ca5  mov     edi, r8d
0x140036ca8  mov     rsi, rdx
0x140036cab  mov     rbx, rcx
0x140036cae  mov     rcx, cs:WPP_GLOBAL_Control
0x140036cb5  lea     r13, WPP_GLOBAL_Control
0x140036cbc  cmp     rcx, r13
0x140036cbf  jz      short loc_140036CEA
0x140036cc1  test    byte ptr [rcx+1Ch], 4
0x140036cc5  jz      short loc_140036CEA
0x140036cc7  cmp     byte ptr [rcx+19h], 5
0x140036ccb  jb      short loc_140036CEA
0x140036ccd  mov     rcx, [rcx+10h]
0x140036cd1  mov     edx, 9Bh
0x140036cd6  mov     [rsp+58h+var_38], r8d
0x140036cdb  mov     r9, rsi
0x140036cde  lea     r8, WPP_8fe8ac2c7c0037f5bee7c55b6a976ec1_Traceguids
0x140036ce5  call    WPP_SF_qd
0x140036cea  cmp     qword ptr [rbx+118h], 0
0x140036cf2  jz      loc_140036DBA
0x140036cf8  xor     r9d, r9d; unsigned int *
0x140036cfb  mov     [rsp+58h+arg_0], 0
0x140036d03  lea     r8, [rsp+58h+arg_0]; int *
0x140036d08  mov     [rsp+58h+ppInterface], 0
0x140036d11  lea     rdx, [rsp+58h+var_28]; struct IServerSecurity **
0x140036d16  mov     [rsp+58h+var_28], 0
0x140036d1f  lea     rcx, [rsp+58h+ppInterface]; ppInterface
0x140036d24  call    ?BeginImpersonation@ProviderSubSystem_Common_Globals@@SAJAEAPEAUIUnknown@@AEAPEAUIServerSecurity@@AEAHPEAK@Z; ProviderSubSystem_Common_Globals::BeginImpersonation(IUnknown * &,IServerSecurity * &,int &,ulong *)
0x140036d29  test    eax, eax
0x140036d2b  js      loc_140036DBA
0x140036d31  mov     rax, cs:?s_SharedCounters@ProviderSubSystem_Globals@@2PEAVCServerObject_ProviderSubsystem_Counters@@EA; CServerObject_ProviderSubsystem_Counters * ProviderSubSystem_Globals::s_SharedCounters
0x140036d38  test    rax, rax
0x140036d3b  jz      short loc_140036D44
0x140036d3d  inc     qword ptr [rax+0D8h]
0x140036d44  inc     qword ptr [rbx+2B8h]
0x140036d4b  mov     r9, rbp
0x140036d4e  mov     rcx, [rbx+118h]
0x140036d55  mov     r8d, edi
0x140036d58  mov     rdx, rsi
0x140036d5b  mov     rax, [rcx]
0x140036d5e  mov     rax, [rax+20h]
0x140036d62  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140036d67  mov     ebx, eax
0x140036d69  call    cs:__imp_CoRevertToSelf
0x140036d6f  mov     r8d, [rsp+58h+arg_0]; int
0x140036d74  mov     rdx, [rsp+58h+var_28]; struct IServerSecurity *
0x140036d79  mov     rcx, [rsp+58h+ppInterface]; struct IUnknown *
0x140036d7e  call    ?EndImpersonation@ProviderSubSystem_Common_Globals@@SAJPEAUIUnknown@@PEAUIServerSecurity@@H@Z; ProviderSubSystem_Common_Globals::EndImpersonation(IUnknown *,IServerSecurity *,int)
0x140036d83  test    ebx, ebx
0x140036d85  jns     short loc_140036D98
0x140036d87  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x140036d8d  mov     rcx, rax
0x140036d90  mov     edx, ebx
0x140036d92  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x140036d98  mov     rcx, cs:WPP_GLOBAL_Control
0x140036d9f  cmp     rcx, r13
0x140036da2  jz      short loc_140036E03
0x140036da4  test    byte ptr [rcx+1Ch], 4
0x140036da8  jz      short loc_140036E03
0x140036daa  cmp     byte ptr [rcx+19h], 2
0x140036dae  jb      short loc_140036E03
0x140036db0  mov     edx, 9Ch
0x140036db5  mov     r9d, ebx
0x140036db8  jmp     short loc_140036DF3
0x140036dba  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x140036dc0  mov     ebx, 80041024h
0x140036dc5  mov     rcx, rax
0x140036dc8  mov     edx, ebx
0x140036dca  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x140036dd0  mov     rcx, cs:WPP_GLOBAL_Control
0x140036dd7  cmp     rcx, r13
0x140036dda  jz      short loc_140036E03
0x140036ddc  test    byte ptr [rcx+1Ch], 4
0x140036de0  jz      short loc_140036E03
0x140036de2  cmp     byte ptr [rcx+19h], 2
0x140036de6  jb      short loc_140036E03
0x140036de8  mov     edx, 9Dh
0x140036ded  mov     r9d, 80041024h
0x140036df3  mov     rcx, [rcx+10h]
0x140036df7  lea     r8, WPP_8fe8ac2c7c0037f5bee7c55b6a976ec1_Traceguids
0x140036dfe  call    WPP_SF_d
0x140036e03  mov     rbp, [rsp+58h+arg_10]
0x140036e08  mov     eax, ebx
0x140036e0a  mov     rbx, [rsp+58h+arg_8]
0x140036e0f  add     rsp, 40h
0x140036e13  pop     r13
0x140036e15  pop     rdi
0x140036e16  pop     rsi
0x140036e17  retn
```
