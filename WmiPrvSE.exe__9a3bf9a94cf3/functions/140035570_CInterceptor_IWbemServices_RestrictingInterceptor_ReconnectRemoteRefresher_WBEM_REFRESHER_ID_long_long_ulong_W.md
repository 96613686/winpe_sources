# CInterceptor_IWbemServices_RestrictingInterceptor::ReconnectRemoteRefresher(_WBEM_REFRESHER_ID *,long,long,ulong,_WBEM_RECONNECT_INFO *,_WBEM_RECONNECT_RESULTS *,ulong *)

- ea: `0x140035570`
- end: `0x14003571f`
- name: `?ReconnectRemoteRefresher@CInterceptor_IWbemServices_RestrictingInterceptor@@UEAAJPEAU_WBEM_REFRESHER_ID@@JJKPEAU_WBEM_RECONNECT_INFO@@PEAU_WBEM_RECONNECT_RESULTS@@PEAK@Z`
- size: `431`
- prototype: `__int64 __fastcall(CInterceptor_IWbemServices_RestrictingInterceptor *__hidden this, struct _WBEM_REFRESHER_ID *, int, int, unsigned int, struct _WBEM_RECONNECT_INFO *, struct _WBEM_RECONNECT_RESULTS *, unsigned int *)`
- caller_count: `0`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callees

- `0x1400234b8`
- `0x140030f90`
- `0x140032b04`
- `0x140035570`
- `0x140035e50`
- `0x140048010`

## import_xrefs

- `wbemcomn!GetMemLogObject` at `0x1400356c1`
- `wbemcomn!GetMemLogObject` at `0x1400356c1`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1400356cc`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1400356cc`

## pseudocode

```c
__int64 __fastcall CInterceptor_IWbemServices_RestrictingInterceptor::ReconnectRemoteRefresher(
        CInterceptor_IWbemServices_RestrictingInterceptor *this,
        struct _WBEM_REFRESHER_ID *a2,
        __int64 a3,
        unsigned int a4,
        unsigned int a5,
        struct _WBEM_RECONNECT_INFO *a6)
{
  unsigned int v7; // r15d
  int v10; // r13d
  int v11; // ebx
  CMemoryLog *MemLogObject; // rax
  struct IWbemRefreshingServices *v14; // [rsp+28h] [rbp-59h]
  int v15; // [rsp+50h] [rbp-31h] BYREF
  int v16; // [rsp+54h] [rbp-2Dh] BYREF
  struct IWbemRefreshingServices *v17; // [rsp+58h] [rbp-29h] BYREF
  struct IUnknown *v18; // [rsp+60h] [rbp-21h] BYREF
  struct IServerSecurity *v19; // [rsp+68h] [rbp-19h] BYREF
  struct IUnknown *v20; // [rsp+70h] [rbp-11h] BYREF
  int v21; // [rsp+D0h] [rbp+4Fh] BYREF

  v7 = a3;
  v10 = a5;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_qddd(*((_QWORD *)WPP_GLOBAL_Control + 2), 130, a3, a2, a3, a4, a5);
  }
  _InterlockedIncrement((volatile signed __int32 *)this + 6);
  if ( *((_DWORD *)this + 5) == 1 )
  {
    v11 = -2147217357;
  }
  else if ( *((_QWORD *)this + 12) )
  {
    v15 = 0;
    v20 = 0;
    v19 = 0;
    v16 = 0;
    v17 = 0;
    v21 = 0;
    v18 = 0;
    v11 = CInterceptor_IWbemServices_RestrictingInterceptor::Begin_IWbemRefreshingServices(
            (struct IUnknown **)this - 1,
            &v15,
            &v20,
            &v19,
            &v16,
            &v17,
            &v21,
            &v18);
    if ( v11 >= 0 )
    {
      v14 = a6;
      v11 = (*(__int64 (__fastcall **)(struct IWbemRefreshingServices *, struct _WBEM_REFRESHER_ID *, _QWORD, _QWORD))(*(_QWORD *)v17 + 64LL))(
              v17,
              a2,
              v7,
              a4);
      CInterceptor_IWbemServices_RestrictingInterceptor::End_IWbemRefreshingServices(
        (CInterceptor_IWbemServices_RestrictingInterceptor *)((char *)this - 8),
        v15,
        v20,
        v19,
        v10,
        v14,
        v21,
        v18);
    }
  }
  else
  {
    v11 = -2147217399;
  }
  _InterlockedDecrement((volatile signed __int32 *)this + 6);
  if ( v11 < 0 )
  {
    MemLogObject = GetMemLogObject();
    CMemoryLog::Write(MemLogObject, v11);
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      131,
      WPP_2ef91c586edc35547bed035b48d4f238_Traceguids,
      (unsigned int)v11);
  }
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x140035570  push    rbp
0x140035572  push    rbx
0x140035573  push    rsi
0x140035574  push    rdi
0x140035575  push    r12
0x140035577  push    r13
0x140035579  push    r14
0x14003557b  push    r15
0x14003557d  lea     rbp, [rsp-7]
0x140035582  sub     rsp, 88h
0x140035589  mov     r14d, r9d
0x14003558c  mov     r15d, r8d
0x14003558f  mov     r12, rdx
0x140035592  mov     rdi, rcx
0x140035595  mov     rcx, cs:WPP_GLOBAL_Control
0x14003559c  lea     rax, WPP_GLOBAL_Control
0x1400355a3  mov     r13d, [rbp+3Fh+arg_20]
0x1400355a7  cmp     rcx, rax
0x1400355aa  jz      short loc_1400355D8
0x1400355ac  test    byte ptr [rcx+1Ch], 4
0x1400355b0  jz      short loc_1400355D8
0x1400355b2  cmp     byte ptr [rcx+19h], 5
0x1400355b6  jb      short loc_1400355D8
0x1400355b8  mov     rcx, [rcx+10h]
0x1400355bc  mov     edx, 82h
0x1400355c1  mov     dword ptr [rsp+0C0h+var_90], r13d
0x1400355c6  mov     dword ptr [rsp+0C0h+var_98], r9d
0x1400355cb  mov     r9, r12
0x1400355ce  mov     dword ptr [rsp+0C0h+var_A0], r8d
0x1400355d3  call    WPP_SF_qddd
0x1400355d8  lock inc dword ptr [rdi+18h]
0x1400355dc  xor     ebx, ebx
0x1400355de  cmp     dword ptr [rdi+14h], 1
0x1400355e2  jnz     short loc_1400355EE
0x1400355e4  mov     ebx, 80041033h
0x1400355e9  jmp     loc_1400356B9
0x1400355ee  cmp     [rdi+60h], rbx
0x1400355f2  jz      loc_1400356B4
0x1400355f8  lea     rax, [rbp+3Fh+var_60]
0x1400355fc  mov     [rbp+3Fh+var_70], ebx
0x1400355ff  mov     [rsp+0C0h+var_88], rax; struct IUnknown **
0x140035604  lea     r9, [rbp+3Fh+var_58]; struct IServerSecurity **
0x140035608  lea     rax, [rbp+3Fh+arg_0]
0x14003560c  mov     [rbp+3Fh+var_50], rbx
0x140035610  mov     [rsp+0C0h+var_90], rax; int *
0x140035615  lea     r8, [rbp+3Fh+var_50]; struct IUnknown **
0x140035619  lea     rax, [rbp+3Fh+var_68]
0x14003561d  mov     [rbp+3Fh+var_58], rbx
0x140035621  mov     [rsp+0C0h+var_98], rax; struct IWbemRefreshingServices **
0x140035626  lea     rdx, [rbp+3Fh+var_70]; int *
0x14003562a  lea     rax, [rbp+3Fh+var_6C]
0x14003562e  mov     [rbp+3Fh+var_6C], ebx
0x140035631  lea     rcx, [rdi-8]; this
0x140035635  mov     [rsp+0C0h+var_A0], rax; int *
0x14003563a  mov     [rbp+3Fh+var_68], rbx
0x14003563e  mov     [rbp+3Fh+arg_0], ebx
0x140035641  mov     [rbp+3Fh+var_60], rbx
0x140035645  call    ?Begin_IWbemRefreshingServices@CInterceptor_IWbemServices_RestrictingInterceptor@@AEAAJAEAHAEAPEAUIUnknown@@AEAPEAUIServerSecurity@@0AEAPEAUIWbemRefreshingServices@@01PEAUIWbemContext@@@Z; CInterceptor_IWbemServices_RestrictingInterceptor::Begin_IWbemRefreshingServices(int &,IUnknown * &,IServerSecurity * &,int &,IWbemRefreshingServices * &,int &,IUnknown * &,IWbemContext *)
0x14003564a  mov     ebx, eax
0x14003564c  test    eax, eax
0x14003564e  js      short loc_1400356B9
0x140035650  mov     rcx, [rbp+3Fh+var_68]
0x140035654  mov     r9d, r14d
0x140035657  mov     rdx, [rbp+3Fh+arg_38]
0x14003565e  mov     r8d, r15d
0x140035661  mov     [rsp+0C0h+var_88], rdx
0x140035666  mov     rdx, [rbp+3Fh+arg_30]
0x14003566a  mov     rax, [rcx]
0x14003566d  mov     [rsp+0C0h+var_90], rdx
0x140035672  mov     rdx, [rbp+3Fh+arg_28]
0x140035676  mov     [rsp+0C0h+var_98], rdx; struct IWbemRefreshingServices *
0x14003567b  mov     rdx, r12
0x14003567e  mov     rax, [rax+40h]
0x140035682  mov     dword ptr [rsp+0C0h+var_A0], r13d; int
0x140035687  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003568c  mov     r9, [rbp+3Fh+var_58]; struct IServerSecurity *
0x140035690  lea     rcx, [rdi-8]; this
0x140035694  mov     r8, [rbp+3Fh+var_50]; struct IUnknown *
0x140035698  mov     ebx, eax
0x14003569a  mov     rax, [rbp+3Fh+var_60]
0x14003569e  mov     edx, [rbp+3Fh+var_70]; int
0x1400356a1  mov     [rsp+0C0h+var_88], rax; struct IUnknown *
0x1400356a6  mov     eax, [rbp+3Fh+arg_0]
0x1400356a9  mov     dword ptr [rsp+0C0h+var_90], eax; int
0x1400356ad  call    ?End_IWbemRefreshingServices@CInterceptor_IWbemServices_RestrictingInterceptor@@AEAAJHPEAUIUnknown@@PEAUIServerSecurity@@HPEAUIWbemRefreshingServices@@H0@Z; CInterceptor_IWbemServices_RestrictingInterceptor::End_IWbemRefreshingServices(int,IUnknown *,IServerSecurity *,int,IWbemRefreshingServices *,int,IUnknown *)
0x1400356b2  jmp     short loc_1400356B9
0x1400356b4  mov     ebx, 80041009h
0x1400356b9  lock dec dword ptr [rdi+18h]
0x1400356bd  test    ebx, ebx
0x1400356bf  jns     short loc_1400356D2
0x1400356c1  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1400356c7  mov     rcx, rax
0x1400356ca  mov     edx, ebx
0x1400356cc  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1400356d2  mov     rcx, cs:WPP_GLOBAL_Control
0x1400356d9  lea     rax, WPP_GLOBAL_Control
0x1400356e0  cmp     rcx, rax
0x1400356e3  jz      short loc_140035709
0x1400356e5  test    byte ptr [rcx+1Ch], 4
0x1400356e9  jz      short loc_140035709
0x1400356eb  cmp     byte ptr [rcx+19h], 2
0x1400356ef  jb      short loc_140035709
0x1400356f1  mov     rcx, [rcx+10h]
0x1400356f5  lea     r8, WPP_2ef91c586edc35547bed035b48d4f238_Traceguids
0x1400356fc  mov     edx, 83h
0x140035701  mov     r9d, ebx
0x140035704  call    WPP_SF_d
0x140035709  mov     eax, ebx
0x14003570b  add     rsp, 88h
0x140035712  pop     r15
0x140035714  pop     r14
0x140035716  pop     r13
0x140035718  pop     r12
0x14003571a  pop     rdi
0x14003571b  pop     rsi
0x14003571c  pop     rbx
0x14003571d  pop     rbp
0x14003571e  retn
```
