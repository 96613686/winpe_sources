# CInterceptor_IWbemSyncProvider::InternalEx_ValidateSubscription(bool,IWbemClassObject *)

- ea: `0x140038fa4`
- end: `0x140039158`
- name: `?InternalEx_ValidateSubscription@CInterceptor_IWbemSyncProvider@@AEAAJ_NPEAUIWbemClassObject@@@Z`
- size: `436`
- prototype: `__int64 __fastcall(CInterceptor_IWbemSyncProvider *__hidden this, bool, struct IWbemClassObject *)`
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x14003b300`
- `0x14003c1f0`

## callees

- `0x14001b638`
- `0x14001c6d8`
- `0x1400234b8`
- `0x140038fa4`
- `0x140048010`

## import_xrefs

- `wbemcomn!GetMemLogObject` at `0x1400390b9`
- `wbemcomn!GetMemLogObject` at `0x1400390f3`
- `wbemcomn!GetMemLogObject` at `0x1400390b9`
- `wbemcomn!GetMemLogObject` at `0x1400390f3`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1400390c4`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x140039103`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1400390c4`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x140039103`

## pseudocode

```c
__int64 __fastcall CInterceptor_IWbemSyncProvider::InternalEx_ValidateSubscription(
        CInterceptor_IWbemSyncProvider *this,
        char a2,
        struct IWbemClassObject *a3)
{
  struct IUnknown *v5; // r8
  int v6; // ebx
  struct IUnknown *v7; // rcx
  struct IUnknown *v8; // rdx
  const struct _GUID *v9; // r8
  CMemoryLog *MemLogObject; // rax
  _QWORD *v11; // rcx
  __int64 v12; // rdx
  __int64 v13; // r9
  CMemoryLog *v14; // rax
  int v16; // [rsp+40h] [rbp-11h]
  struct IUnknown *v17; // [rsp+48h] [rbp-9h]
  int v18; // [rsp+68h] [rbp+17h] BYREF
  struct IUnknown *v19; // [rsp+70h] [rbp+1Fh] BYREF
  struct IUnknown *v20; // [rsp+78h] [rbp+27h] BYREF
  struct IServerSecurity *v21; // [rsp+80h] [rbp+2Fh] BYREF
  struct IUnknown *v22; // [rsp+88h] [rbp+37h] BYREF
  int v23; // [rsp+B8h] [rbp+67h] BYREF
  int v24; // [rsp+D0h] [rbp+7Fh] BYREF

  v5 = (struct IUnknown *)*((_QWORD *)this + 49);
  if ( v5 )
  {
    v24 = 0;
    v22 = 0;
    v21 = 0;
    v19 = 0;
    v23 = 0;
    v20 = 0;
    v6 = CInterceptor_IWbemSyncProvider::Begin_Interface_Events(
           this,
           a2,
           v5,
           &IID_IWbemEventConsumerProviderEx,
           8u,
           &v24,
           &v22,
           &v21,
           &v18,
           &v19,
           &v23,
           &v20);
    if ( v6 < 0 )
      goto LABEL_6;
    if ( ProviderSubSystem_Globals::s_SharedCounters )
      ++*((_QWORD *)ProviderSubSystem_Globals::s_SharedCounters + 40);
    v7 = v19;
    ++*((_QWORD *)this + 108);
    v6 = ((__int64 (__fastcall *)(struct IUnknown *, struct IWbemClassObject *))v7->lpVtbl[1].AddRef)(v7, a3);
    CInterceptor_IWbemSyncProvider::End_Interface_Events(this, v8, v9, 8u, v24, v22, v21, v16, v17, v23, v20);
    if ( v6 < 0 )
    {
LABEL_6:
      MemLogObject = GetMemLogObject();
      CMemoryLog::Write(MemLogObject, v6);
    }
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v12 = 149;
      v13 = (unsigned int)v6;
LABEL_15:
      WPP_SF_d(v11[2], v12, WPP_8fe8ac2c7c0037f5bee7c55b6a976ec1_Traceguids, v13);
    }
  }
  else
  {
    v14 = GetMemLogObject();
    v6 = -2147217372;
    CMemoryLog::Write(v14, -2147217372);
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v12 = 150;
      v13 = 2147749924LL;
      goto LABEL_15;
    }
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x140038fa4  mov     r11, rsp
0x140038fa7  mov     [r11+10h], rbx
0x140038fab  push    rbp
0x140038fac  push    rsi
0x140038fad  push    rdi
0x140038fae  lea     rbp, [r11-5Fh]
0x140038fb2  sub     rsp, 90h
0x140038fb9  mov     rsi, r8
0x140038fbc  mov     rdi, rcx
0x140038fbf  mov     r8, [rcx+188h]; struct IUnknown *
0x140038fc6  test    r8, r8
0x140038fc9  jz      loc_1400390F3
0x140038fcf  lea     rax, [rbp+57h+var_30]
0x140038fd3  mov     [rbp+57h+arg_18], 0
0x140038fda  mov     [r11-50h], rax
0x140038fde  lea     r9, IID_IWbemEventConsumerProviderEx; struct _GUID *
0x140038fe5  lea     rax, [rbp+57h+arg_0]
0x140038fe9  mov     [rbp+57h+var_20], 0
0x140038ff1  mov     [r11-58h], rax
0x140038ff5  lea     rax, [rbp+57h+var_38]
0x140038ff9  mov     [r11-60h], rax
0x140038ffd  lea     rax, [rbp+57h+var_40]
0x140039001  mov     [r11-68h], rax
0x140039005  lea     rax, [rbp+57h+var_28]
0x140039009  mov     [r11-70h], rax
0x14003900d  lea     rax, [rbp+57h+var_20]
0x140039011  mov     [r11-78h], rax
0x140039015  lea     rax, [rbp+57h+arg_18]
0x140039019  mov     [r11-80h], rax
0x14003901d  mov     [rsp+0A0h+var_80], 8; unsigned int
0x140039025  mov     [rbp+57h+var_28], 0
0x14003902d  mov     [rbp+57h+var_38], 0
0x140039035  mov     [rbp+57h+arg_0], 0
0x14003903c  mov     [rbp+57h+var_30], 0
0x140039044  call    ?Begin_Interface_Events@CInterceptor_IWbemSyncProvider@@AEAAJ_NPEAUIUnknown@@AEBU_GUID@@KAEAHAEAPEAU2@AEAPEAUIServerSecurity@@3434@Z; CInterceptor_IWbemSyncProvider::Begin_Interface_Events(bool,IUnknown *,_GUID const &,ulong,int &,IUnknown * &,IServerSecurity * &,int &,IUnknown * &,int &,IUnknown * &)
0x140039049  mov     ebx, eax
0x14003904b  test    eax, eax
0x14003904d  js      short loc_1400390B9
0x14003904f  mov     rax, cs:?s_SharedCounters@ProviderSubSystem_Globals@@2PEAVCServerObject_ProviderSubsystem_Counters@@EA; CServerObject_ProviderSubsystem_Counters * ProviderSubSystem_Globals::s_SharedCounters
0x140039056  test    rax, rax
0x140039059  jz      short loc_140039062
0x14003905b  inc     qword ptr [rax+140h]
0x140039062  mov     rcx, [rbp+57h+var_38]
0x140039066  mov     rdx, rsi
0x140039069  inc     qword ptr [rdi+360h]
0x140039070  mov     rax, [rcx]
0x140039073  mov     rax, [rax+20h]
0x140039077  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003907c  mov     ebx, eax
0x14003907e  mov     r9d, 8; unsigned int
0x140039084  mov     rax, [rbp+57h+var_30]
0x140039088  mov     rcx, rdi; this
0x14003908b  mov     [rsp+50h], rax; struct IUnknown *
0x140039090  mov     eax, [rbp+57h+arg_0]
0x140039093  mov     [rsp+0A0h+var_58], eax; int
0x140039097  mov     rax, [rbp+57h+var_28]
0x14003909b  mov     [rsp+30h], rax; struct IServerSecurity *
0x1400390a0  mov     rax, [rbp+57h+var_20]
0x1400390a4  mov     [rsp+0A0h+var_78], rax; struct IUnknown *
0x1400390a9  mov     eax, [rbp+57h+arg_18]
0x1400390ac  mov     [rsp+0A0h+var_80], eax; int
0x1400390b0  call    ?End_Interface_Events@CInterceptor_IWbemSyncProvider@@AEAAJPEAUIUnknown@@AEBU_GUID@@KH0PEAUIServerSecurity@@H0H0@Z; CInterceptor_IWbemSyncProvider::End_Interface_Events(IUnknown *,_GUID const &,ulong,int,IUnknown *,IServerSecurity *,int,IUnknown *,int,IUnknown *)
0x1400390b5  test    ebx, ebx
0x1400390b7  jns     short loc_1400390CA
0x1400390b9  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1400390bf  mov     rcx, rax
0x1400390c2  mov     edx, ebx
0x1400390c4  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1400390ca  mov     rcx, cs:WPP_GLOBAL_Control
0x1400390d1  lea     rax, WPP_GLOBAL_Control
0x1400390d8  cmp     rcx, rax
0x1400390db  jz      short loc_140039143
0x1400390dd  test    byte ptr [rcx+1Ch], 4
0x1400390e1  jz      short loc_140039143
0x1400390e3  cmp     byte ptr [rcx+19h], 2
0x1400390e7  jb      short loc_140039143
0x1400390e9  mov     edx, 95h
0x1400390ee  mov     r9d, ebx
0x1400390f1  jmp     short loc_140039133
0x1400390f3  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1400390f9  mov     ebx, 80041024h
0x1400390fe  mov     rcx, rax
0x140039101  mov     edx, ebx
0x140039103  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x140039109  mov     rcx, cs:WPP_GLOBAL_Control
0x140039110  lea     rax, WPP_GLOBAL_Control
0x140039117  cmp     rcx, rax
0x14003911a  jz      short loc_140039143
0x14003911c  test    byte ptr [rcx+1Ch], 4
0x140039120  jz      short loc_140039143
0x140039122  cmp     byte ptr [rcx+19h], 2
0x140039126  jb      short loc_140039143
0x140039128  mov     edx, 96h
0x14003912d  mov     r9d, 80041024h
0x140039133  mov     rcx, [rcx+10h]
0x140039137  lea     r8, WPP_8fe8ac2c7c0037f5bee7c55b6a976ec1_Traceguids
0x14003913e  call    WPP_SF_d
0x140039143  mov     eax, ebx
0x140039145  mov     rbx, [rsp+0A0h+arg_8]
0x14003914d  add     rsp, 90h
0x140039154  pop     rdi
0x140039155  pop     rsi
0x140039156  pop     rbp
0x140039157  retn
```
