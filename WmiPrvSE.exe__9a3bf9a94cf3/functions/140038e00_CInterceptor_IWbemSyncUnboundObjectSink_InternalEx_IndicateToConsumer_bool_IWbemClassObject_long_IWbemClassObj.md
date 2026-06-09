# CInterceptor_IWbemSyncUnboundObjectSink::InternalEx_IndicateToConsumer(bool,IWbemClassObject *,long,IWbemClassObject * *)

- ea: `0x140038e00`
- end: `0x140038f9c`
- name: `?InternalEx_IndicateToConsumer@CInterceptor_IWbemSyncUnboundObjectSink@@IEAAJ_NPEAUIWbemClassObject@@JPEAPEAU2@@Z`
- size: `412`
- prototype: `__int64 __fastcall(CInterceptor_IWbemSyncUnboundObjectSink *__hidden this, bool, struct IWbemClassObject *, int, struct IWbemClassObject **)`
- caller_count: `2`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140038350`
- `0x14003a660`

## callees

- `0x1400054a0`
- `0x140006c64`
- `0x1400234b8`
- `0x140036450`
- `0x140038e00`
- `0x140048010`

## import_xrefs

- `wbemcomn!GetMemLogObject` at `0x140038f00`
- `wbemcomn!GetMemLogObject` at `0x140038f3a`
- `wbemcomn!GetMemLogObject` at `0x140038f00`
- `wbemcomn!GetMemLogObject` at `0x140038f3a`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x140038f0b`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x140038f4a`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x140038f0b`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x140038f4a`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x140038ed0`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x140038ed0`

## pseudocode

```c
__int64 __fastcall CInterceptor_IWbemSyncUnboundObjectSink::InternalEx_IndicateToConsumer(
        CInterceptor_IWbemSyncUnboundObjectSink *this,
        char a2,
        struct IWbemClassObject *a3,
        struct _GUID *a4,
        struct IWbemClassObject **a5)
{
  unsigned int v6; // esi
  struct IUnknown *v7; // r8
  int v9; // ebx
  int v10; // eax
  struct IUnknown *v11; // rsi
  struct IServerSecurity *v12; // r14
  struct IUnknown *v13; // r15
  CMemoryLog *MemLogObject; // rax
  _QWORD *v15; // rcx
  __int64 v16; // rdx
  __int64 v17; // r9
  CMemoryLog *v18; // rax
  unsigned int v20; // [rsp+28h] [rbp-51h]
  int v21; // [rsp+68h] [rbp-11h] BYREF
  int v22; // [rsp+6Ch] [rbp-Dh] BYREF
  struct IUnknown *v23; // [rsp+70h] [rbp-9h] BYREF
  struct IUnknown *v24; // [rsp+78h] [rbp-1h] BYREF
  struct IServerSecurity *v25; // [rsp+80h] [rbp+7h] BYREF
  struct IUnknown *v26; // [rsp+88h] [rbp+Fh] BYREF
  int v27; // [rsp+D8h] [rbp+5Fh] BYREF

  v6 = (unsigned int)a4;
  v7 = (struct IUnknown *)*((_QWORD *)this + 13);
  if ( v7 )
  {
    v21 = 0;
    v26 = 0;
    v25 = 0;
    v22 = 0;
    v23 = 0;
    v27 = 0;
    v24 = 0;
    v9 = CInterceptor_IWbemSyncUnboundObjectSink::Begin_Interface_Consumer(
           this,
           a2,
           v7,
           a4,
           v20,
           &v21,
           &v26,
           &v25,
           &v22,
           &v23,
           &v27,
           &v24);
    if ( v9 < 0 )
      goto LABEL_6;
    v10 = ((__int64 (__fastcall *)(struct IUnknown *, struct IWbemClassObject *, _QWORD, struct IWbemClassObject **))v23->lpVtbl[1].QueryInterface)(
            v23,
            a3,
            v6,
            a5);
    v11 = v24;
    v9 = v10;
    v12 = v25;
    v13 = v26;
    CoRevertToSelf();
    if ( v11 )
      ProviderSubSystem_Common_Globals::RevertProxyState(
        (CInterceptor_IWbemSyncUnboundObjectSink *)((char *)this + 112),
        0,
        v11,
        v27);
    ProviderSubSystem_Common_Globals::EndImpersonation(v13, v12, v21);
    if ( v9 < 0 )
    {
LABEL_6:
      MemLogObject = GetMemLogObject();
      CMemoryLog::Write(MemLogObject, v9);
    }
    v15 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v16 = 14;
      v17 = (unsigned int)v9;
LABEL_15:
      WPP_SF_d(v15[2], v16, WPP_8fe8ac2c7c0037f5bee7c55b6a976ec1_Traceguids, v17);
    }
  }
  else
  {
    v18 = GetMemLogObject();
    v9 = -2147217372;
    CMemoryLog::Write(v18, -2147217372);
    v15 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v16 = 15;
      v17 = 2147749924LL;
      goto LABEL_15;
    }
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x140038e00  mov     r11, rsp
0x140038e03  push    rbp
0x140038e04  push    rbx
0x140038e05  push    rsi
0x140038e06  push    rdi
0x140038e07  push    r14
0x140038e09  push    r15
0x140038e0b  lea     rbp, [r11-57h]
0x140038e0f  sub     rsp, 98h
0x140038e16  mov     r14, r8
0x140038e19  mov     esi, r9d
0x140038e1c  mov     r8, [rcx+68h]; struct IUnknown *
0x140038e20  mov     rdi, rcx
0x140038e23  test    r8, r8
0x140038e26  jz      loc_140038F3A
0x140038e2c  lea     rax, [rbp+4Fh+var_50]
0x140038e30  mov     [rbp+4Fh+var_60], 0
0x140038e37  mov     [r11-70h], rax
0x140038e3b  lea     rax, [rbp+4Fh+arg_0]
0x140038e3f  mov     [r11-78h], rax
0x140038e43  lea     rax, [rbp+4Fh+var_58]
0x140038e47  mov     [r11-80h], rax
0x140038e4b  lea     rax, [rbp+4Fh+var_5C]
0x140038e4f  mov     [rsp+40h], rax; int *
0x140038e54  lea     rax, [rbp+4Fh+var_48]
0x140038e58  mov     [rsp+0C0h+var_88], rax; struct IServerSecurity **
0x140038e5d  lea     rax, [rbp+4Fh+var_40]
0x140038e61  mov     [rsp+0C0h+var_90], rax; struct IUnknown **
0x140038e66  lea     rax, [rbp+4Fh+var_60]
0x140038e6a  mov     [rsp+0C0h+var_98], rax; int *
0x140038e6f  mov     [rbp+4Fh+var_40], 0
0x140038e77  mov     [rbp+4Fh+var_48], 0
0x140038e7f  mov     [rbp+4Fh+var_5C], 0
0x140038e86  mov     [rbp+4Fh+var_58], 0
0x140038e8e  mov     [rbp+4Fh+arg_0], 0
0x140038e95  mov     [rbp+4Fh+var_50], 0
0x140038e9d  call    ?Begin_Interface_Consumer@CInterceptor_IWbemSyncUnboundObjectSink@@IEAAJ_NPEAUIUnknown@@AEBU_GUID@@KAEAHAEAPEAU2@AEAPEAUIServerSecurity@@3434@Z; CInterceptor_IWbemSyncUnboundObjectSink::Begin_Interface_Consumer(bool,IUnknown *,_GUID const &,ulong,int &,IUnknown * &,IServerSecurity * &,int &,IUnknown * &,int &,IUnknown * &)
0x140038ea2  mov     ebx, eax
0x140038ea4  test    eax, eax
0x140038ea6  js      short loc_140038F00
0x140038ea8  mov     rcx, [rbp+4Fh+var_58]
0x140038eac  mov     r8d, esi
0x140038eaf  mov     r9, [rbp+4Fh+arg_20]
0x140038eb3  mov     rdx, r14
0x140038eb6  mov     rax, [rcx]
0x140038eb9  mov     rax, [rax+18h]
0x140038ebd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140038ec2  mov     rsi, [rbp+4Fh+var_50]
0x140038ec6  mov     ebx, eax
0x140038ec8  mov     r14, [rbp+4Fh+var_48]
0x140038ecc  mov     r15, [rbp+4Fh+var_40]
0x140038ed0  call    cs:__imp_CoRevertToSelf
0x140038ed6  test    rsi, rsi
0x140038ed9  jz      short loc_140038EED
0x140038edb  mov     r9d, [rbp+4Fh+arg_0]; int
0x140038edf  lea     rcx, [rdi+70h]; struct ProxyContainer *
0x140038ee3  mov     r8, rsi; struct IUnknown *
0x140038ee6  xor     edx, edx; unsigned int
0x140038ee8  call    ?RevertProxyState@ProviderSubSystem_Common_Globals@@SAJAEAVProxyContainer@@KPEAUIUnknown@@H@Z; ProviderSubSystem_Common_Globals::RevertProxyState(ProxyContainer &,ulong,IUnknown *,int)
0x140038eed  mov     r8d, [rbp+4Fh+var_60]; int
0x140038ef1  mov     rdx, r14; struct IServerSecurity *
0x140038ef4  mov     rcx, r15; struct IUnknown *
0x140038ef7  call    ?EndImpersonation@ProviderSubSystem_Common_Globals@@SAJPEAUIUnknown@@PEAUIServerSecurity@@H@Z; ProviderSubSystem_Common_Globals::EndImpersonation(IUnknown *,IServerSecurity *,int)
0x140038efc  test    ebx, ebx
0x140038efe  jns     short loc_140038F11
0x140038f00  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x140038f06  mov     rcx, rax
0x140038f09  mov     edx, ebx
0x140038f0b  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x140038f11  mov     rcx, cs:WPP_GLOBAL_Control
0x140038f18  lea     rax, WPP_GLOBAL_Control
0x140038f1f  cmp     rcx, rax
0x140038f22  jz      short loc_140038F8A
0x140038f24  test    byte ptr [rcx+1Ch], 4
0x140038f28  jz      short loc_140038F8A
0x140038f2a  cmp     byte ptr [rcx+19h], 2
0x140038f2e  jb      short loc_140038F8A
0x140038f30  mov     edx, 0Eh
0x140038f35  mov     r9d, ebx
0x140038f38  jmp     short loc_140038F7A
0x140038f3a  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x140038f40  mov     ebx, 80041024h
0x140038f45  mov     rcx, rax
0x140038f48  mov     edx, ebx
0x140038f4a  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x140038f50  mov     rcx, cs:WPP_GLOBAL_Control
0x140038f57  lea     rax, WPP_GLOBAL_Control
0x140038f5e  cmp     rcx, rax
0x140038f61  jz      short loc_140038F8A
0x140038f63  test    byte ptr [rcx+1Ch], 4
0x140038f67  jz      short loc_140038F8A
0x140038f69  cmp     byte ptr [rcx+19h], 2
0x140038f6d  jb      short loc_140038F8A
0x140038f6f  mov     edx, 0Fh
0x140038f74  mov     r9d, 80041024h
0x140038f7a  mov     rcx, [rcx+10h]
0x140038f7e  lea     r8, WPP_8fe8ac2c7c0037f5bee7c55b6a976ec1_Traceguids
0x140038f85  call    WPP_SF_d
0x140038f8a  mov     eax, ebx
0x140038f8c  add     rsp, 98h
0x140038f93  pop     r15
0x140038f95  pop     r14
0x140038f97  pop     rdi
0x140038f98  pop     rsi
0x140038f99  pop     rbx
0x140038f9a  pop     rbp
0x140038f9b  retn
```
