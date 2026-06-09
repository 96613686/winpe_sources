# CInterceptor_IWbemSyncProvider::CreateRefreshableObject(IWbemServices *,IWbemObjectAccess *,IWbemRefresher *,long,IWbemContext *,IWbemObjectAccess * *,long *)

- ea: `0x140036ac0`
- end: `0x140036c89`
- name: `?CreateRefreshableObject@CInterceptor_IWbemSyncProvider@@UEAAJPEAUIWbemServices@@PEAUIWbemObjectAccess@@PEAUIWbemRefresher@@JPEAUIWbemContext@@PEAPEAU3@PEAJ@Z`
- size: `457`
- prototype: `__int64 __fastcall(CInterceptor_IWbemSyncProvider *__hidden this, struct IWbemServices *, struct IWbemObjectAccess *, struct IWbemRefresher *, int, struct IWbemContext *, struct IWbemObjectAccess **, int *)`
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x140006c64`
- `0x14001ca74`
- `0x1400234b8`
- `0x140036ac0`
- `0x14003c5b0`
- `0x140048010`

## import_xrefs

- `wbemcomn!GetMemLogObject` at `0x140036bf0`
- `wbemcomn!GetMemLogObject` at `0x140036c2a`
- `wbemcomn!GetMemLogObject` at `0x140036bf0`
- `wbemcomn!GetMemLogObject` at `0x140036c2a`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x140036bfb`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x140036c3a`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x140036bfb`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x140036c3a`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x140036bcf`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x140036bcf`

## pseudocode

```c
__int64 __fastcall CInterceptor_IWbemSyncProvider::CreateRefreshableObject(
        CInterceptor_IWbemSyncProvider *this,
        struct IWbemServices *a2,
        struct IWbemObjectAccess *a3,
        struct IWbemRefresher *a4,
        int a5,
        struct IWbemContext *a6,
        struct IWbemObjectAccess **a7,
        int *a8)
{
  struct IWbemContext *v12; // r14
  int v13; // r15d
  int v14; // ebx
  CMemoryLog *MemLogObject; // rax
  _QWORD *v16; // rcx
  __int64 v17; // rdx
  __int64 v18; // r9
  CMemoryLog *v19; // rax
  struct IServerSecurity *v21; // [rsp+50h] [rbp-48h] BYREF
  struct IUnknown *ppInterface; // [rsp+58h] [rbp-40h] BYREF
  int v23; // [rsp+A0h] [rbp+8h] BYREF

  v12 = a6;
  v13 = a5;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_qqqdq(*((_QWORD *)WPP_GLOBAL_Control + 2), a2, a3, a2, a3, a4, a5, a6);
  }
  if ( *((_QWORD *)this + 35)
    && (v23 = 0,
        ppInterface = 0,
        v21 = 0,
        (int)ProviderSubSystem_Common_Globals::BeginImpersonation(&ppInterface, &v21, &v23, 0) >= 0) )
  {
    if ( ProviderSubSystem_Globals::s_SharedCounters )
      ++*((_QWORD *)ProviderSubSystem_Globals::s_SharedCounters + 28);
    ++*((_QWORD *)this + 88);
    v14 = (*(__int64 (__fastcall **)(_QWORD, struct IWbemServices *, struct IWbemObjectAccess *, struct IWbemRefresher *, int, struct IWbemContext *, struct IWbemObjectAccess **, int *))(**((_QWORD **)this + 35) + 40LL))(
            *((_QWORD *)this + 35),
            a2,
            a3,
            a4,
            v13,
            v12,
            a7,
            a8);
    CoRevertToSelf();
    ProviderSubSystem_Common_Globals::EndImpersonation(ppInterface, v21, v23);
    if ( v14 < 0 )
    {
      MemLogObject = GetMemLogObject();
      CMemoryLog::Write(MemLogObject, v14);
    }
    v16 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v17 = 159;
      v18 = (unsigned int)v14;
LABEL_19:
      WPP_SF_d(v16[2], v17, WPP_8fe8ac2c7c0037f5bee7c55b6a976ec1_Traceguids, v18);
    }
  }
  else
  {
    v19 = GetMemLogObject();
    v14 = -2147217372;
    CMemoryLog::Write(v19, -2147217372);
    v16 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v17 = 160;
      v18 = 2147749924LL;
      goto LABEL_19;
    }
  }
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x140036ac0  mov     r11, rsp
0x140036ac3  push    rbx
0x140036ac4  push    rbp
0x140036ac5  push    rsi
0x140036ac6  push    rdi
0x140036ac7  push    r14
0x140036ac9  push    r15
0x140036acb  sub     rsp, 68h
0x140036acf  mov     rdi, r9
0x140036ad2  mov     rsi, r8
0x140036ad5  mov     rbp, rdx
0x140036ad8  mov     rbx, rcx
0x140036adb  mov     rcx, cs:WPP_GLOBAL_Control
0x140036ae2  lea     rax, WPP_GLOBAL_Control
0x140036ae9  mov     r14, [rsp+98h+arg_28]
0x140036af1  mov     r15d, [rsp+98h+arg_20]
0x140036af9  cmp     rcx, rax
0x140036afc  jz      short loc_140036B26
0x140036afe  test    byte ptr [rcx+1Ch], 4
0x140036b02  jz      short loc_140036B26
0x140036b04  cmp     byte ptr [rcx+19h], 5
0x140036b08  jb      short loc_140036B26
0x140036b0a  mov     rcx, [rcx+10h]
0x140036b0e  mov     [r11-60h], r14
0x140036b12  mov     [r11-68h], r15d
0x140036b16  mov     [r11-70h], r9
0x140036b1a  mov     r9, rdx
0x140036b1d  mov     [r11-78h], r8
0x140036b21  call    WPP_SF_qqqdq
0x140036b26  cmp     qword ptr [rbx+118h], 0
0x140036b2e  jz      loc_140036C2A
0x140036b34  xor     r9d, r9d; unsigned int *
0x140036b37  mov     [rsp+98h+arg_0], 0
0x140036b42  lea     r8, [rsp+98h+arg_0]; int *
0x140036b4a  mov     [rsp+98h+ppInterface], 0
0x140036b53  lea     rdx, [rsp+98h+var_48]; struct IServerSecurity **
0x140036b58  mov     [rsp+98h+var_48], 0
0x140036b61  lea     rcx, [rsp+98h+ppInterface]; ppInterface
0x140036b66  call    ?BeginImpersonation@ProviderSubSystem_Common_Globals@@SAJAEAPEAUIUnknown@@AEAPEAUIServerSecurity@@AEAHPEAK@Z; ProviderSubSystem_Common_Globals::BeginImpersonation(IUnknown * &,IServerSecurity * &,int &,ulong *)
0x140036b6b  test    eax, eax
0x140036b6d  js      loc_140036C2A
0x140036b73  mov     rax, cs:?s_SharedCounters@ProviderSubSystem_Globals@@2PEAVCServerObject_ProviderSubsystem_Counters@@EA; CServerObject_ProviderSubsystem_Counters * ProviderSubSystem_Globals::s_SharedCounters
0x140036b7a  test    rax, rax
0x140036b7d  jz      short loc_140036B86
0x140036b7f  inc     qword ptr [rax+0E0h]
0x140036b86  inc     qword ptr [rbx+2C0h]
0x140036b8d  mov     r9, rdi
0x140036b90  mov     rcx, [rbx+118h]
0x140036b97  mov     r8, rsi
0x140036b9a  mov     rdx, [rsp+98h+arg_38]
0x140036ba2  mov     [rsp+98h+var_60], rdx
0x140036ba7  mov     rdx, [rsp+98h+arg_30]
0x140036baf  mov     rax, [rcx]
0x140036bb2  mov     [rsp+98h+var_68], rdx
0x140036bb7  mov     rdx, rbp
0x140036bba  mov     [rsp+98h+var_70], r14
0x140036bbf  mov     [rsp+98h+var_78], r15d
0x140036bc4  mov     rax, [rax+28h]
0x140036bc8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140036bcd  mov     ebx, eax
0x140036bcf  call    cs:__imp_CoRevertToSelf
0x140036bd5  mov     r8d, [rsp+98h+arg_0]; int
0x140036bdd  mov     rdx, [rsp+98h+var_48]; struct IServerSecurity *
0x140036be2  mov     rcx, [rsp+98h+ppInterface]; struct IUnknown *
0x140036be7  call    ?EndImpersonation@ProviderSubSystem_Common_Globals@@SAJPEAUIUnknown@@PEAUIServerSecurity@@H@Z; ProviderSubSystem_Common_Globals::EndImpersonation(IUnknown *,IServerSecurity *,int)
0x140036bec  test    ebx, ebx
0x140036bee  jns     short loc_140036C01
0x140036bf0  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x140036bf6  mov     rcx, rax
0x140036bf9  mov     edx, ebx
0x140036bfb  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x140036c01  mov     rcx, cs:WPP_GLOBAL_Control
0x140036c08  lea     rax, WPP_GLOBAL_Control
0x140036c0f  cmp     rcx, rax
0x140036c12  jz      short loc_140036C7A
0x140036c14  test    byte ptr [rcx+1Ch], 4
0x140036c18  jz      short loc_140036C7A
0x140036c1a  cmp     byte ptr [rcx+19h], 2
0x140036c1e  jb      short loc_140036C7A
0x140036c20  mov     edx, 9Fh
0x140036c25  mov     r9d, ebx
0x140036c28  jmp     short loc_140036C6A
0x140036c2a  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x140036c30  mov     ebx, 80041024h
0x140036c35  mov     rcx, rax
0x140036c38  mov     edx, ebx
0x140036c3a  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x140036c40  mov     rcx, cs:WPP_GLOBAL_Control
0x140036c47  lea     rax, WPP_GLOBAL_Control
0x140036c4e  cmp     rcx, rax
0x140036c51  jz      short loc_140036C7A
0x140036c53  test    byte ptr [rcx+1Ch], 4
0x140036c57  jz      short loc_140036C7A
0x140036c59  cmp     byte ptr [rcx+19h], 2
0x140036c5d  jb      short loc_140036C7A
0x140036c5f  mov     edx, 0A0h
0x140036c64  mov     r9d, 80041024h
0x140036c6a  mov     rcx, [rcx+10h]
0x140036c6e  lea     r8, WPP_8fe8ac2c7c0037f5bee7c55b6a976ec1_Traceguids
0x140036c75  call    WPP_SF_d
0x140036c7a  mov     eax, ebx
0x140036c7c  add     rsp, 68h
0x140036c80  pop     r15
0x140036c82  pop     r14
0x140036c84  pop     rdi
0x140036c85  pop     rsi
0x140036c86  pop     rbp
0x140036c87  pop     rbx
0x140036c88  retn
```
