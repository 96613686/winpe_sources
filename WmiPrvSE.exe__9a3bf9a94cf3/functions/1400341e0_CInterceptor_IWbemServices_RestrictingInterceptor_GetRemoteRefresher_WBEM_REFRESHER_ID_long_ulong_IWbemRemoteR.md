# CInterceptor_IWbemServices_RestrictingInterceptor::GetRemoteRefresher(_WBEM_REFRESHER_ID *,long,ulong,IWbemRemoteRefresher * *,_GUID *,ulong *)

- ea: `0x1400341e0`
- end: `0x1400343a6`
- name: `?GetRemoteRefresher@CInterceptor_IWbemServices_RestrictingInterceptor@@UEAAJPEAU_WBEM_REFRESHER_ID@@JKPEAPEAUIWbemRemoteRefresher@@PEAU_GUID@@PEAK@Z`
- size: `454`
- prototype: `__int64 __fastcall(CInterceptor_IWbemServices_RestrictingInterceptor *__hidden this, struct _WBEM_REFRESHER_ID *, int, unsigned int, struct IWbemRemoteRefresher **, struct _GUID *, unsigned int *)`
- caller_count: `0`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callees

- `0x1400234b8`
- `0x140029c48`
- `0x140030f90`
- `0x140032b04`
- `0x1400341e0`
- `0x140048010`

## import_xrefs

- `wbemcomn!GetMemLogObject` at `0x140034340`
- `wbemcomn!GetMemLogObject` at `0x140034340`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x14003434b`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x14003434b`

## pseudocode

```c
__int64 __fastcall CInterceptor_IWbemServices_RestrictingInterceptor::GetRemoteRefresher(
        CInterceptor_IWbemServices_RestrictingInterceptor *this,
        struct _WBEM_REFRESHER_ID *a2,
        unsigned int a3,
        unsigned int a4,
        struct IWbemRemoteRefresher **a5,
        struct _GUID *a6)
{
  int v10; // ebx
  CMemoryLog *MemLogObject; // rax
  int v13; // [rsp+20h] [rbp-60h]
  struct IWbemRefreshingServices **v14; // [rsp+28h] [rbp-58h]
  int v15; // [rsp+50h] [rbp-30h] BYREF
  int v16; // [rsp+54h] [rbp-2Ch] BYREF
  struct IWbemRefreshingServices *v17; // [rsp+58h] [rbp-28h] BYREF
  struct IUnknown *v18; // [rsp+60h] [rbp-20h] BYREF
  struct IServerSecurity *v19; // [rsp+68h] [rbp-18h] BYREF
  struct IUnknown *v20; // [rsp+70h] [rbp-10h] BYREF
  int v21; // [rsp+B0h] [rbp+30h] BYREF

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 128, WPP_2ef91c586edc35547bed035b48d4f238_Traceguids, a3, a4);
  }
  _InterlockedIncrement((volatile signed __int32 *)this + 6);
  if ( *((_DWORD *)this + 5) == 1 )
  {
    v10 = -2147217357;
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
    v10 = CInterceptor_IWbemServices_RestrictingInterceptor::Begin_IWbemRefreshingServices(
            (struct IUnknown **)this - 1,
            &v15,
            &v20,
            &v19,
            &v16,
            &v17,
            &v21,
            &v18);
    if ( v10 >= 0 )
    {
      v14 = (struct IWbemRefreshingServices **)a6;
      v13 = (int)a5;
      v10 = (*(__int64 (__fastcall **)(struct IWbemRefreshingServices *, struct _WBEM_REFRESHER_ID *, _QWORD, _QWORD))(*(_QWORD *)v17 + 56LL))(
              v17,
              a2,
              a3,
              a4);
      CInterceptor_IWbemServices_RestrictingInterceptor::End_IWbemRefreshingServices(
        (CInterceptor_IWbemServices_RestrictingInterceptor *)((char *)this - 8),
        v15,
        v20,
        v19,
        v13,
        (struct IWbemRefreshingServices *)v14,
        v21,
        v18);
    }
  }
  else
  {
    v10 = -2147217399;
  }
  _InterlockedDecrement((volatile signed __int32 *)this + 6);
  if ( v10 < 0 )
  {
    MemLogObject = GetMemLogObject();
    CMemoryLog::Write(MemLogObject, v10);
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      129,
      WPP_2ef91c586edc35547bed035b48d4f238_Traceguids,
      (unsigned int)v10);
  }
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x1400341e0  mov     [rsp-28h+arg_8], rbx
0x1400341e5  mov     [rsp-28h+arg_10], rsi
0x1400341ea  push    rbp
0x1400341eb  push    rdi
0x1400341ec  push    r12
0x1400341ee  push    r14
0x1400341f0  push    r15
0x1400341f2  mov     rbp, rsp
0x1400341f5  sub     rsp, 80h
0x1400341fc  mov     r14d, r9d
0x1400341ff  mov     r15d, r8d
0x140034202  mov     r12, rdx
0x140034205  mov     rdi, rcx
0x140034208  mov     rcx, cs:WPP_GLOBAL_Control
0x14003420f  lea     rax, WPP_GLOBAL_Control
0x140034216  cmp     rcx, rax
0x140034219  jz      short loc_140034244
0x14003421b  test    byte ptr [rcx+1Ch], 4
0x14003421f  jz      short loc_140034244
0x140034221  cmp     byte ptr [rcx+19h], 5
0x140034225  jb      short loc_140034244
0x140034227  mov     rcx, [rcx+10h]
0x14003422b  mov     edx, 80h
0x140034230  mov     dword ptr [rsp+80h+var_60], r9d
0x140034235  mov     r9d, r8d
0x140034238  lea     r8, WPP_2ef91c586edc35547bed035b48d4f238_Traceguids
0x14003423f  call    WPP_SF_dd
0x140034244  lock inc dword ptr [rdi+18h]
0x140034248  cmp     dword ptr [rdi+14h], 1
0x14003424c  jnz     short loc_140034258
0x14003424e  mov     ebx, 80041033h
0x140034253  jmp     loc_140034338
0x140034258  cmp     qword ptr [rdi+60h], 0
0x14003425d  jz      loc_140034333
0x140034263  lea     rax, [rbp+var_20]
0x140034267  mov     [rbp+var_30], 0
0x14003426e  mov     [rsp+80h+var_48], rax; struct IUnknown **
0x140034273  lea     r9, [rbp+var_18]; struct IServerSecurity **
0x140034277  lea     rax, [rbp+arg_0]
0x14003427b  mov     [rbp+var_10], 0
0x140034283  mov     [rsp+80h+var_50], rax; int *
0x140034288  lea     r8, [rbp+var_10]; struct IUnknown **
0x14003428c  lea     rax, [rbp+var_28]
0x140034290  mov     [rbp+var_18], 0
0x140034298  mov     [rsp+80h+var_58], rax; struct IWbemRefreshingServices **
0x14003429d  lea     rdx, [rbp+var_30]; int *
0x1400342a1  lea     rax, [rbp+var_2C]
0x1400342a5  mov     [rbp+var_2C], 0
0x1400342ac  lea     rcx, [rdi-8]; this
0x1400342b0  mov     [rsp+80h+var_60], rax; int *
0x1400342b5  mov     [rbp+var_28], 0
0x1400342bd  mov     [rbp+arg_0], 0
0x1400342c4  mov     [rbp+var_20], 0
0x1400342cc  call    ?Begin_IWbemRefreshingServices@CInterceptor_IWbemServices_RestrictingInterceptor@@AEAAJAEAHAEAPEAUIUnknown@@AEAPEAUIServerSecurity@@0AEAPEAUIWbemRefreshingServices@@01PEAUIWbemContext@@@Z; CInterceptor_IWbemServices_RestrictingInterceptor::Begin_IWbemRefreshingServices(int &,IUnknown * &,IServerSecurity * &,int &,IWbemRefreshingServices * &,int &,IUnknown * &,IWbemContext *)
0x1400342d1  mov     ebx, eax
0x1400342d3  test    eax, eax
0x1400342d5  js      short loc_140034338
0x1400342d7  mov     rcx, [rbp+var_28]
0x1400342db  mov     r9d, r14d
0x1400342de  mov     rdx, [rbp+arg_30]
0x1400342e2  mov     r8d, r15d
0x1400342e5  mov     [rsp+80h+var_50], rdx
0x1400342ea  mov     rdx, [rbp+arg_28]
0x1400342ee  mov     rax, [rcx]
0x1400342f1  mov     [rsp+80h+var_58], rdx; struct IWbemRefreshingServices *
0x1400342f6  mov     rdx, [rbp+arg_20]
0x1400342fa  mov     [rsp+80h+var_60], rdx; int
0x1400342ff  mov     rdx, r12
0x140034302  mov     rax, [rax+38h]
0x140034306  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003430b  mov     r9, [rbp+var_18]; struct IServerSecurity *
0x14003430f  lea     rcx, [rdi-8]; this
0x140034313  mov     r8, [rbp+var_10]; struct IUnknown *
0x140034317  mov     ebx, eax
0x140034319  mov     rax, [rbp+var_20]
0x14003431d  mov     edx, [rbp+var_30]; int
0x140034320  mov     [rsp+80h+var_48], rax; struct IUnknown *
0x140034325  mov     eax, [rbp+arg_0]
0x140034328  mov     dword ptr [rsp+80h+var_50], eax; int
0x14003432c  call    ?End_IWbemRefreshingServices@CInterceptor_IWbemServices_RestrictingInterceptor@@AEAAJHPEAUIUnknown@@PEAUIServerSecurity@@HPEAUIWbemRefreshingServices@@H0@Z; CInterceptor_IWbemServices_RestrictingInterceptor::End_IWbemRefreshingServices(int,IUnknown *,IServerSecurity *,int,IWbemRefreshingServices *,int,IUnknown *)
0x140034331  jmp     short loc_140034338
0x140034333  mov     ebx, 80041009h
0x140034338  lock dec dword ptr [rdi+18h]
0x14003433c  test    ebx, ebx
0x14003433e  jns     short loc_140034351
0x140034340  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x140034346  mov     rcx, rax
0x140034349  mov     edx, ebx
0x14003434b  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x140034351  mov     rcx, cs:WPP_GLOBAL_Control
0x140034358  lea     rax, WPP_GLOBAL_Control
0x14003435f  cmp     rcx, rax
0x140034362  jz      short loc_140034388
0x140034364  test    byte ptr [rcx+1Ch], 4
0x140034368  jz      short loc_140034388
0x14003436a  cmp     byte ptr [rcx+19h], 2
0x14003436e  jb      short loc_140034388
0x140034370  mov     rcx, [rcx+10h]
0x140034374  lea     r8, WPP_2ef91c586edc35547bed035b48d4f238_Traceguids
0x14003437b  mov     edx, 81h
0x140034380  mov     r9d, ebx
0x140034383  call    WPP_SF_d
0x140034388  lea     r11, [rsp+80h+var_s0]
0x140034390  mov     eax, ebx
0x140034392  mov     rbx, [r11+38h]
0x140034396  mov     rsi, [r11+40h]
0x14003439a  mov     rsp, r11
0x14003439d  pop     r15
0x14003439f  pop     r14
0x1400343a1  pop     r12
0x1400343a3  pop     rdi
0x1400343a4  pop     rbp
0x1400343a5  retn
```
