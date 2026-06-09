# CInterceptor_IWbemSyncProvider::SetRegistrationObject(long,IWbemClassObject *)

- ea: `0x14003be80`
- end: `0x14003c04b`
- name: `?SetRegistrationObject@CInterceptor_IWbemSyncProvider@@UEAAJJPEAUIWbemClassObject@@@Z`
- size: `459`
- prototype: `__int64 __fastcall(CInterceptor_IWbemSyncProvider *__hidden this, int, struct IWbemClassObject *)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x14001b638`
- `0x14001c6d8`
- `0x1400234b8`
- `0x14003be80`
- `0x140048010`

## import_xrefs

- `wbemcomn!GetMemLogObject` at `0x14003bfa8`
- `wbemcomn!GetMemLogObject` at `0x14003bfe2`
- `wbemcomn!GetMemLogObject` at `0x14003bfa8`
- `wbemcomn!GetMemLogObject` at `0x14003bfe2`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x14003bfb3`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x14003bff2`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x14003bfb3`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x14003bff2`

## pseudocode

```c
__int64 __fastcall CInterceptor_IWbemSyncProvider::SetRegistrationObject(
        CInterceptor_IWbemSyncProvider *this,
        unsigned int a2,
        struct IWbemClassObject *a3)
{
  struct IUnknown *v5; // r8
  int v7; // ebx
  struct IUnknown *v8; // rcx
  struct IUnknown *v9; // rdx
  const struct _GUID *v10; // r8
  CMemoryLog *MemLogObject; // rax
  _QWORD *v12; // rcx
  __int64 v13; // rdx
  __int64 v14; // r9
  CMemoryLog *v15; // rax
  int v17; // [rsp+40h] [rbp-21h]
  struct IUnknown *v18; // [rsp+48h] [rbp-19h]
  int v19; // [rsp+68h] [rbp+7h] BYREF
  struct IUnknown *v20; // [rsp+70h] [rbp+Fh] BYREF
  struct IUnknown *v21; // [rsp+78h] [rbp+17h] BYREF
  struct IServerSecurity *v22; // [rsp+80h] [rbp+1Fh] BYREF
  struct IUnknown *v23; // [rsp+88h] [rbp+27h] BYREF
  int v24; // [rsp+C8h] [rbp+67h] BYREF
  int v25; // [rsp+E0h] [rbp+7Fh] BYREF

  v5 = (struct IUnknown *)*((_QWORD *)this + 42);
  if ( v5 )
  {
    v25 = 0;
    v23 = 0;
    v22 = 0;
    v20 = 0;
    v24 = 0;
    v21 = 0;
    v7 = CInterceptor_IWbemSyncProvider::Begin_Interface_Events(
           (CInterceptor_IWbemSyncProvider *)((char *)this - 40),
           0,
           v5,
           &IID_IWbemProviderIdentity,
           6u,
           &v25,
           &v23,
           &v22,
           &v19,
           &v20,
           &v24,
           &v21);
    if ( v7 < 0 )
      goto LABEL_6;
    if ( ProviderSubSystem_Globals::s_SharedCounters )
      ++*((_QWORD *)ProviderSubSystem_Globals::s_SharedCounters + 38);
    v8 = v20;
    ++*((_QWORD *)this + 101);
    v7 = ((__int64 (__fastcall *)(struct IUnknown *, _QWORD, struct IWbemClassObject *))v8->lpVtbl[1].QueryInterface)(
           v8,
           a2,
           a3);
    CInterceptor_IWbemSyncProvider::End_Interface_Events(
      (CInterceptor_IWbemSyncProvider *)((char *)this - 40),
      v9,
      v10,
      6u,
      v25,
      v23,
      v22,
      v17,
      v18,
      v24,
      v21);
    if ( v7 < 0 )
    {
LABEL_6:
      MemLogObject = GetMemLogObject();
      CMemoryLog::Write(MemLogObject, v7);
    }
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v13 = 145;
      v14 = (unsigned int)v7;
LABEL_15:
      WPP_SF_d(v12[2], v13, WPP_8fe8ac2c7c0037f5bee7c55b6a976ec1_Traceguids, v14);
    }
  }
  else
  {
    v15 = GetMemLogObject();
    v7 = -2147217372;
    CMemoryLog::Write(v15, -2147217372);
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v13 = 146;
      v14 = 2147749924LL;
      goto LABEL_15;
    }
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x14003be80  mov     r11, rsp
0x14003be83  mov     [r11+10h], rbx
0x14003be87  push    rbp
0x14003be88  push    rsi
0x14003be89  push    rdi
0x14003be8a  push    r14
0x14003be8c  push    r15
0x14003be8e  lea     rbp, [r11-5Fh]
0x14003be92  sub     rsp, 90h
0x14003be99  mov     r14, r8
0x14003be9c  mov     r15d, edx
0x14003be9f  mov     r8, [rcx+150h]; struct IUnknown *
0x14003bea6  mov     rsi, rcx
0x14003bea9  test    r8, r8
0x14003beac  jz      loc_14003BFE2
0x14003beb2  lea     rax, [rbp+57h+var_40]
0x14003beb6  mov     [rbp+57h+arg_18], 0
0x14003bebd  mov     [r11-60h], rax
0x14003bec1  lea     r9, IID_IWbemProviderIdentity; struct _GUID *
0x14003bec8  lea     rax, [rbp+57h+arg_0]
0x14003becc  mov     [rbp+57h+var_30], 0
0x14003bed4  mov     [r11-68h], rax
0x14003bed8  xor     edx, edx; bool
0x14003beda  lea     rax, [rbp+57h+var_48]
0x14003bede  mov     [rbp+57h+var_38], 0
0x14003bee6  mov     [r11-70h], rax
0x14003beea  add     rcx, 0FFFFFFFFFFFFFFD8h; this
0x14003beee  lea     rax, [rbp+57h+var_50]
0x14003bef2  mov     [rbp+57h+var_48], 0
0x14003befa  mov     [r11-78h], rax
0x14003befe  lea     rax, [rbp+57h+var_38]
0x14003bf02  mov     [r11-80h], rax
0x14003bf06  lea     rax, [rbp+57h+var_30]
0x14003bf0a  mov     [rsp+30h], rax; struct IUnknown **
0x14003bf0f  lea     rax, [rbp+57h+arg_18]
0x14003bf13  mov     [rsp+0B0h+var_88], rax; int *
0x14003bf18  mov     [rsp+0B0h+var_90], 6; unsigned int
0x14003bf20  mov     [rbp+57h+arg_0], 0
0x14003bf27  mov     [rbp+57h+var_40], 0
0x14003bf2f  call    ?Begin_Interface_Events@CInterceptor_IWbemSyncProvider@@AEAAJ_NPEAUIUnknown@@AEBU_GUID@@KAEAHAEAPEAU2@AEAPEAUIServerSecurity@@3434@Z; CInterceptor_IWbemSyncProvider::Begin_Interface_Events(bool,IUnknown *,_GUID const &,ulong,int &,IUnknown * &,IServerSecurity * &,int &,IUnknown * &,int &,IUnknown * &)
0x14003bf34  mov     ebx, eax
0x14003bf36  test    eax, eax
0x14003bf38  js      short loc_14003BFA8
0x14003bf3a  mov     rax, cs:?s_SharedCounters@ProviderSubSystem_Globals@@2PEAVCServerObject_ProviderSubsystem_Counters@@EA; CServerObject_ProviderSubsystem_Counters * ProviderSubSystem_Globals::s_SharedCounters
0x14003bf41  test    rax, rax
0x14003bf44  jz      short loc_14003BF4D
0x14003bf46  inc     qword ptr [rax+130h]
0x14003bf4d  mov     rcx, [rbp+57h+var_48]
0x14003bf51  mov     r8, r14
0x14003bf54  inc     qword ptr [rsi+328h]
0x14003bf5b  mov     edx, r15d
0x14003bf5e  mov     rax, [rcx]
0x14003bf61  mov     rax, [rax+18h]
0x14003bf65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003bf6a  mov     ebx, eax
0x14003bf6c  lea     rcx, [rsi-28h]; this
0x14003bf70  mov     rax, [rbp+57h+var_40]
0x14003bf74  mov     r9d, 6; unsigned int
0x14003bf7a  mov     [rsp+50h], rax; struct IUnknown *
0x14003bf7f  mov     eax, [rbp+57h+arg_0]
0x14003bf82  mov     [rsp+0B0h+var_68], eax; int
0x14003bf86  mov     rax, [rbp+57h+var_38]
0x14003bf8a  mov     [rsp+30h], rax; struct IServerSecurity *
0x14003bf8f  mov     rax, [rbp+57h+var_30]
0x14003bf93  mov     [rsp+0B0h+var_88], rax; struct IUnknown *
0x14003bf98  mov     eax, [rbp+57h+arg_18]
0x14003bf9b  mov     [rsp+0B0h+var_90], eax; int
0x14003bf9f  call    ?End_Interface_Events@CInterceptor_IWbemSyncProvider@@AEAAJPEAUIUnknown@@AEBU_GUID@@KH0PEAUIServerSecurity@@H0H0@Z; CInterceptor_IWbemSyncProvider::End_Interface_Events(IUnknown *,_GUID const &,ulong,int,IUnknown *,IServerSecurity *,int,IUnknown *,int,IUnknown *)
0x14003bfa4  test    ebx, ebx
0x14003bfa6  jns     short loc_14003BFB9
0x14003bfa8  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x14003bfae  mov     rcx, rax
0x14003bfb1  mov     edx, ebx
0x14003bfb3  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x14003bfb9  mov     rcx, cs:WPP_GLOBAL_Control
0x14003bfc0  lea     rax, WPP_GLOBAL_Control
0x14003bfc7  cmp     rcx, rax
0x14003bfca  jz      short loc_14003C032
0x14003bfcc  test    byte ptr [rcx+1Ch], 4
0x14003bfd0  jz      short loc_14003C032
0x14003bfd2  cmp     byte ptr [rcx+19h], 2
0x14003bfd6  jb      short loc_14003C032
0x14003bfd8  mov     edx, 91h
0x14003bfdd  mov     r9d, ebx
0x14003bfe0  jmp     short loc_14003C022
0x14003bfe2  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x14003bfe8  mov     ebx, 80041024h
0x14003bfed  mov     rcx, rax
0x14003bff0  mov     edx, ebx
0x14003bff2  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x14003bff8  mov     rcx, cs:WPP_GLOBAL_Control
0x14003bfff  lea     rax, WPP_GLOBAL_Control
0x14003c006  cmp     rcx, rax
0x14003c009  jz      short loc_14003C032
0x14003c00b  test    byte ptr [rcx+1Ch], 4
0x14003c00f  jz      short loc_14003C032
0x14003c011  cmp     byte ptr [rcx+19h], 2
0x14003c015  jb      short loc_14003C032
0x14003c017  mov     edx, 92h
0x14003c01c  mov     r9d, 80041024h
0x14003c022  mov     rcx, [rcx+10h]
0x14003c026  lea     r8, WPP_8fe8ac2c7c0037f5bee7c55b6a976ec1_Traceguids
0x14003c02d  call    WPP_SF_d
0x14003c032  mov     eax, ebx
0x14003c034  mov     rbx, [rsp+0B0h+arg_8]
0x14003c03c  add     rsp, 90h
0x14003c043  pop     r15
0x14003c045  pop     r14
0x14003c047  pop     rdi
0x14003c048  pop     rsi
0x14003c049  pop     rbp
0x14003c04a  retn
```
