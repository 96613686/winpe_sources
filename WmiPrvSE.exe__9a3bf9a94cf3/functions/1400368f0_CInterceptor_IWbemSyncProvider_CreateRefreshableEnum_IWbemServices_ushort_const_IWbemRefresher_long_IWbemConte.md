# CInterceptor_IWbemSyncProvider::CreateRefreshableEnum(IWbemServices *,ushort const *,IWbemRefresher *,long,IWbemContext *,IWbemHiPerfEnum *,long *)

- ea: `0x1400368f0`
- end: `0x140036ab9`
- name: `?CreateRefreshableEnum@CInterceptor_IWbemSyncProvider@@UEAAJPEAUIWbemServices@@PEBGPEAUIWbemRefresher@@JPEAUIWbemContext@@PEAUIWbemHiPerfEnum@@PEAJ@Z`
- size: `457`
- prototype: `__int64 __fastcall(CInterceptor_IWbemSyncProvider *__hidden this, struct IWbemServices *, const unsigned __int16 *, struct IWbemRefresher *, int, struct IWbemContext *, struct IWbemHiPerfEnum *, int *)`
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x140006c64`
- `0x14001ca74`
- `0x1400234b8`
- `0x1400368f0`
- `0x14003c47c`
- `0x140048010`

## import_xrefs

- `wbemcomn!GetMemLogObject` at `0x140036a20`
- `wbemcomn!GetMemLogObject` at `0x140036a5a`
- `wbemcomn!GetMemLogObject` at `0x140036a20`
- `wbemcomn!GetMemLogObject` at `0x140036a5a`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x140036a2b`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x140036a6a`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x140036a2b`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x140036a6a`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x1400369ff`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x1400369ff`

## pseudocode

```c
__int64 __fastcall CInterceptor_IWbemSyncProvider::CreateRefreshableEnum(
        CInterceptor_IWbemSyncProvider *this,
        struct IWbemServices *a2,
        const unsigned __int16 *a3,
        struct IWbemRefresher *a4,
        int a5,
        struct IWbemContext *a6,
        struct IWbemHiPerfEnum *a7,
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
    WPP_SF_qSqdq(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      (_DWORD)a2,
      (_DWORD)a3,
      (_DWORD)a2,
      (__int64)a3,
      (char)a4,
      a5,
      (char)a6);
  }
  if ( *((_QWORD *)this + 35)
    && (v23 = 0,
        ppInterface = 0,
        v21 = 0,
        (int)ProviderSubSystem_Common_Globals::BeginImpersonation(&ppInterface, &v21, &v23, 0) >= 0) )
  {
    if ( ProviderSubSystem_Globals::s_SharedCounters )
      ++*((_QWORD *)ProviderSubSystem_Globals::s_SharedCounters + 30);
    ++*((_QWORD *)this + 90);
    v14 = (*(__int64 (__fastcall **)(_QWORD, struct IWbemServices *, const unsigned __int16 *, struct IWbemRefresher *, int, struct IWbemContext *, struct IWbemHiPerfEnum *, int *))(**((_QWORD **)this + 35) + 56LL))(
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
      v17 = 165;
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
      v17 = 166;
      v18 = 2147749924LL;
      goto LABEL_19;
    }
  }
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x1400368f0  mov     r11, rsp
0x1400368f3  push    rbx
0x1400368f4  push    rbp
0x1400368f5  push    rsi
0x1400368f6  push    rdi
0x1400368f7  push    r14
0x1400368f9  push    r15
0x1400368fb  sub     rsp, 68h
0x1400368ff  mov     rdi, r9
0x140036902  mov     rsi, r8
0x140036905  mov     rbp, rdx
0x140036908  mov     rbx, rcx
0x14003690b  mov     rcx, cs:WPP_GLOBAL_Control
0x140036912  lea     rax, WPP_GLOBAL_Control
0x140036919  mov     r14, [rsp+98h+arg_28]
0x140036921  mov     r15d, [rsp+98h+arg_20]
0x140036929  cmp     rcx, rax
0x14003692c  jz      short loc_140036956
0x14003692e  test    byte ptr [rcx+1Ch], 4
0x140036932  jz      short loc_140036956
0x140036934  cmp     byte ptr [rcx+19h], 5
0x140036938  jb      short loc_140036956
0x14003693a  mov     rcx, [rcx+10h]
0x14003693e  mov     [r11-60h], r14
0x140036942  mov     [r11-68h], r15d
0x140036946  mov     [r11-70h], r9
0x14003694a  mov     r9, rdx
0x14003694d  mov     [r11-78h], r8
0x140036951  call    WPP_SF_qSqdq
0x140036956  cmp     qword ptr [rbx+118h], 0
0x14003695e  jz      loc_140036A5A
0x140036964  xor     r9d, r9d; unsigned int *
0x140036967  mov     [rsp+98h+arg_0], 0
0x140036972  lea     r8, [rsp+98h+arg_0]; int *
0x14003697a  mov     [rsp+98h+ppInterface], 0
0x140036983  lea     rdx, [rsp+98h+var_48]; struct IServerSecurity **
0x140036988  mov     [rsp+98h+var_48], 0
0x140036991  lea     rcx, [rsp+98h+ppInterface]; ppInterface
0x140036996  call    ?BeginImpersonation@ProviderSubSystem_Common_Globals@@SAJAEAPEAUIUnknown@@AEAPEAUIServerSecurity@@AEAHPEAK@Z; ProviderSubSystem_Common_Globals::BeginImpersonation(IUnknown * &,IServerSecurity * &,int &,ulong *)
0x14003699b  test    eax, eax
0x14003699d  js      loc_140036A5A
0x1400369a3  mov     rax, cs:?s_SharedCounters@ProviderSubSystem_Globals@@2PEAVCServerObject_ProviderSubsystem_Counters@@EA; CServerObject_ProviderSubsystem_Counters * ProviderSubSystem_Globals::s_SharedCounters
0x1400369aa  test    rax, rax
0x1400369ad  jz      short loc_1400369B6
0x1400369af  inc     qword ptr [rax+0F0h]
0x1400369b6  inc     qword ptr [rbx+2D0h]
0x1400369bd  mov     r9, rdi
0x1400369c0  mov     rcx, [rbx+118h]
0x1400369c7  mov     r8, rsi
0x1400369ca  mov     rdx, [rsp+98h+arg_38]
0x1400369d2  mov     [rsp+98h+var_60], rdx
0x1400369d7  mov     rdx, [rsp+98h+arg_30]
0x1400369df  mov     rax, [rcx]
0x1400369e2  mov     [rsp+98h+var_68], rdx
0x1400369e7  mov     rdx, rbp
0x1400369ea  mov     [rsp+98h+var_70], r14
0x1400369ef  mov     [rsp+98h+var_78], r15d
0x1400369f4  mov     rax, [rax+38h]
0x1400369f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400369fd  mov     ebx, eax
0x1400369ff  call    cs:__imp_CoRevertToSelf
0x140036a05  mov     r8d, [rsp+98h+arg_0]; int
0x140036a0d  mov     rdx, [rsp+98h+var_48]; struct IServerSecurity *
0x140036a12  mov     rcx, [rsp+98h+ppInterface]; struct IUnknown *
0x140036a17  call    ?EndImpersonation@ProviderSubSystem_Common_Globals@@SAJPEAUIUnknown@@PEAUIServerSecurity@@H@Z; ProviderSubSystem_Common_Globals::EndImpersonation(IUnknown *,IServerSecurity *,int)
0x140036a1c  test    ebx, ebx
0x140036a1e  jns     short loc_140036A31
0x140036a20  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x140036a26  mov     rcx, rax
0x140036a29  mov     edx, ebx
0x140036a2b  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x140036a31  mov     rcx, cs:WPP_GLOBAL_Control
0x140036a38  lea     rax, WPP_GLOBAL_Control
0x140036a3f  cmp     rcx, rax
0x140036a42  jz      short loc_140036AAA
0x140036a44  test    byte ptr [rcx+1Ch], 4
0x140036a48  jz      short loc_140036AAA
0x140036a4a  cmp     byte ptr [rcx+19h], 2
0x140036a4e  jb      short loc_140036AAA
0x140036a50  mov     edx, 0A5h
0x140036a55  mov     r9d, ebx
0x140036a58  jmp     short loc_140036A9A
0x140036a5a  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x140036a60  mov     ebx, 80041024h
0x140036a65  mov     rcx, rax
0x140036a68  mov     edx, ebx
0x140036a6a  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x140036a70  mov     rcx, cs:WPP_GLOBAL_Control
0x140036a77  lea     rax, WPP_GLOBAL_Control
0x140036a7e  cmp     rcx, rax
0x140036a81  jz      short loc_140036AAA
0x140036a83  test    byte ptr [rcx+1Ch], 4
0x140036a87  jz      short loc_140036AAA
0x140036a89  cmp     byte ptr [rcx+19h], 2
0x140036a8d  jb      short loc_140036AAA
0x140036a8f  mov     edx, 0A6h
0x140036a94  mov     r9d, 80041024h
0x140036a9a  mov     rcx, [rcx+10h]
0x140036a9e  lea     r8, WPP_8fe8ac2c7c0037f5bee7c55b6a976ec1_Traceguids
0x140036aa5  call    WPP_SF_d
0x140036aaa  mov     eax, ebx
0x140036aac  add     rsp, 68h
0x140036ab0  pop     r15
0x140036ab2  pop     r14
0x140036ab4  pop     rdi
0x140036ab5  pop     rsi
0x140036ab6  pop     rbp
0x140036ab7  pop     rbx
0x140036ab8  retn
```
