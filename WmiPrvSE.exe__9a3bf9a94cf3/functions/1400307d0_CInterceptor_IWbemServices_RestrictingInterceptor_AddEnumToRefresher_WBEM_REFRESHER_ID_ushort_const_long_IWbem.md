# CInterceptor_IWbemServices_RestrictingInterceptor::AddEnumToRefresher(_WBEM_REFRESHER_ID *,ushort const *,long,IWbemContext *,ulong,_WBEM_REFRESH_INFO *,ulong *)

- ea: `0x1400307d0`
- end: `0x140030987`
- name: `?AddEnumToRefresher@CInterceptor_IWbemServices_RestrictingInterceptor@@UEAAJPEAU_WBEM_REFRESHER_ID@@PEBGJPEAUIWbemContext@@KPEAU_WBEM_REFRESH_INFO@@PEAK@Z`
- size: `439`
- prototype: `__int64 __fastcall(CInterceptor_IWbemServices_RestrictingInterceptor *this, struct _WBEM_REFRESHER_ID *, const unsigned __int16 *, unsigned int, struct IWbemContext *, struct IWbemRefreshingServices *)`
- caller_count: `0`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callees

- `0x1400234b8`
- `0x1400307d0`
- `0x140030f90`
- `0x140032b04`
- `0x140035cf0`
- `0x140048010`

## import_xrefs

- `wbemcomn!GetMemLogObject` at `0x140030922`
- `wbemcomn!GetMemLogObject` at `0x140030922`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x14003092d`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x14003092d`

## pseudocode

```c
__int64 __fastcall CInterceptor_IWbemServices_RestrictingInterceptor::AddEnumToRefresher(
        CInterceptor_IWbemServices_RestrictingInterceptor *this,
        struct _WBEM_REFRESHER_ID *a2,
        const unsigned __int16 *a3,
        unsigned int a4,
        struct IWbemContext *a5,
        struct IWbemRefreshingServices *a6)
{
  int v9; // r12d
  int v10; // r13d
  int v11; // ebx
  CMemoryLog *MemLogObject; // rax
  struct IWbemRefreshingServices **v14; // [rsp+28h] [rbp-58h]
  struct IWbemContext *v15; // [rsp+40h] [rbp-40h]
  int v16; // [rsp+50h] [rbp-30h] BYREF
  int v17; // [rsp+54h] [rbp-2Ch] BYREF
  struct IWbemRefreshingServices *v18; // [rsp+58h] [rbp-28h] BYREF
  struct IUnknown *v19; // [rsp+60h] [rbp-20h] BYREF
  struct IServerSecurity *v20; // [rsp+68h] [rbp-18h] BYREF
  struct IUnknown *v21; // [rsp+70h] [rbp-10h] BYREF
  int v22; // [rsp+C0h] [rbp+40h] BYREF
  struct _WBEM_REFRESHER_ID *v23; // [rsp+C8h] [rbp+48h]

  v23 = a2;
  v9 = (int)a6;
  v10 = (int)a5;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_Sdqd(*((_QWORD *)WPP_GLOBAL_Control + 2), 124, (_DWORD)a3, (_DWORD)a3, a4, (char)a5, (char)a6);
  }
  _InterlockedIncrement((volatile signed __int32 *)this + 6);
  if ( *((_DWORD *)this + 5) == 1 )
  {
    v11 = -2147217357;
  }
  else if ( *((_QWORD *)this + 12) )
  {
    v16 = 0;
    v21 = 0;
    v20 = 0;
    v17 = 0;
    v18 = 0;
    v22 = 0;
    v19 = 0;
    v11 = CInterceptor_IWbemServices_RestrictingInterceptor::Begin_IWbemRefreshingServices(
            (CInterceptor_IWbemServices_RestrictingInterceptor *)((char *)this - 8),
            &v16,
            &v21,
            &v20,
            &v17,
            &v18,
            &v22,
            &v19,
            v15);
    if ( v11 >= 0 )
    {
      LODWORD(v14) = v9;
      v11 = (*(__int64 (__fastcall **)(struct IWbemRefreshingServices *, struct _WBEM_REFRESHER_ID *, const unsigned __int16 *, _QWORD))(*(_QWORD *)v18 + 40LL))(
              v18,
              v23,
              a3,
              a4);
      CInterceptor_IWbemServices_RestrictingInterceptor::End_IWbemRefreshingServices(
        (CInterceptor_IWbemServices_RestrictingInterceptor *)((char *)this - 8),
        v16,
        v21,
        v20,
        v10,
        (struct IWbemRefreshingServices *)v14,
        v22,
        v19);
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
      125,
      WPP_2ef91c586edc35547bed035b48d4f238_Traceguids,
      (unsigned int)v11);
  }
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x1400307d0  mov     [rsp-38h+arg_10], rbx
0x1400307d5  mov     [rsp-38h+arg_8], rdx
0x1400307da  push    rbp
0x1400307db  push    rsi
0x1400307dc  push    rdi
0x1400307dd  push    r12
0x1400307df  push    r13
0x1400307e1  push    r14
0x1400307e3  push    r15
0x1400307e5  mov     rbp, rsp
0x1400307e8  sub     rsp, 80h
0x1400307ef  mov     r14d, r9d
0x1400307f2  mov     r15, r8
0x1400307f5  mov     rdi, rcx
0x1400307f8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400307ff  lea     rax, WPP_GLOBAL_Control
0x140030806  mov     r12d, dword ptr [rbp+arg_28]
0x14003080a  mov     r13, [rbp+arg_20]
0x14003080e  cmp     rcx, rax
0x140030811  jz      short loc_14003083F
0x140030813  test    byte ptr [rcx+1Ch], 4
0x140030817  jz      short loc_14003083F
0x140030819  cmp     byte ptr [rcx+19h], 5
0x14003081d  jb      short loc_14003083F
0x14003081f  mov     rcx, [rcx+10h]
0x140030823  mov     edx, 7Ch ; '|'
0x140030828  mov     dword ptr [rsp+80h+var_50], r12d
0x14003082d  mov     [rsp+80h+var_58], r13
0x140030832  mov     dword ptr [rsp+80h+var_60], r9d
0x140030837  mov     r9, r8
0x14003083a  call    WPP_SF_Sdqd
0x14003083f  lock inc dword ptr [rdi+18h]
0x140030843  xor     ebx, ebx
0x140030845  cmp     dword ptr [rdi+14h], 1
0x140030849  jnz     short loc_140030855
0x14003084b  mov     ebx, 80041033h
0x140030850  jmp     loc_14003091A
0x140030855  cmp     [rdi+60h], rbx
0x140030859  jz      loc_140030915
0x14003085f  lea     rax, [rbp+var_20]
0x140030863  mov     [rbp+var_30], ebx
0x140030866  mov     [rsp+80h+var_48], rax; struct IUnknown **
0x14003086b  lea     r9, [rbp+var_18]; struct IServerSecurity **
0x14003086f  lea     rax, [rbp+arg_0]
0x140030873  mov     [rbp+var_10], rbx
0x140030877  mov     [rsp+80h+var_50], rax; int *
0x14003087c  lea     r8, [rbp+var_10]; struct IUnknown **
0x140030880  lea     rax, [rbp+var_28]
0x140030884  mov     [rbp+var_18], rbx
0x140030888  mov     [rsp+80h+var_58], rax; struct IWbemRefreshingServices **
0x14003088d  lea     rdx, [rbp+var_30]; int *
0x140030891  lea     rax, [rbp+var_2C]
0x140030895  mov     [rbp+var_2C], ebx
0x140030898  lea     rcx, [rdi-8]; this
0x14003089c  mov     [rsp+80h+var_60], rax; int *
0x1400308a1  mov     [rbp+var_28], rbx
0x1400308a5  mov     [rbp+arg_0], ebx
0x1400308a8  mov     [rbp+var_20], rbx
0x1400308ac  call    ?Begin_IWbemRefreshingServices@CInterceptor_IWbemServices_RestrictingInterceptor@@AEAAJAEAHAEAPEAUIUnknown@@AEAPEAUIServerSecurity@@0AEAPEAUIWbemRefreshingServices@@01PEAUIWbemContext@@@Z; CInterceptor_IWbemServices_RestrictingInterceptor::Begin_IWbemRefreshingServices(int &,IUnknown * &,IServerSecurity * &,int &,IWbemRefreshingServices * &,int &,IUnknown * &,IWbemContext *)
0x1400308b1  mov     ebx, eax
0x1400308b3  test    eax, eax
0x1400308b5  js      short loc_14003091A
0x1400308b7  mov     rcx, [rbp+var_28]
0x1400308bb  mov     r9d, r14d
0x1400308be  mov     rdx, [rbp+arg_38]
0x1400308c2  mov     r8, r15
0x1400308c5  mov     [rsp+80h+var_48], rdx
0x1400308ca  mov     rdx, [rbp+arg_30]
0x1400308ce  mov     rax, [rcx]
0x1400308d1  mov     [rsp+80h+var_50], rdx
0x1400308d6  mov     rdx, [rbp+arg_8]
0x1400308da  mov     dword ptr [rsp+80h+var_58], r12d; struct IWbemRefreshingServices *
0x1400308df  mov     rax, [rax+28h]
0x1400308e3  mov     [rsp+80h+var_60], r13; int
0x1400308e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400308ed  mov     r9, [rbp+var_18]; struct IServerSecurity *
0x1400308f1  lea     rcx, [rdi-8]; this
0x1400308f5  mov     r8, [rbp+var_10]; struct IUnknown *
0x1400308f9  mov     ebx, eax
0x1400308fb  mov     rax, [rbp+var_20]
0x1400308ff  mov     edx, [rbp+var_30]; int
0x140030902  mov     [rsp+80h+var_48], rax; struct IUnknown *
0x140030907  mov     eax, [rbp+arg_0]
0x14003090a  mov     dword ptr [rsp+80h+var_50], eax; int
0x14003090e  call    ?End_IWbemRefreshingServices@CInterceptor_IWbemServices_RestrictingInterceptor@@AEAAJHPEAUIUnknown@@PEAUIServerSecurity@@HPEAUIWbemRefreshingServices@@H0@Z; CInterceptor_IWbemServices_RestrictingInterceptor::End_IWbemRefreshingServices(int,IUnknown *,IServerSecurity *,int,IWbemRefreshingServices *,int,IUnknown *)
0x140030913  jmp     short loc_14003091A
0x140030915  mov     ebx, 80041009h
0x14003091a  lock dec dword ptr [rdi+18h]
0x14003091e  test    ebx, ebx
0x140030920  jns     short loc_140030933
0x140030922  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x140030928  mov     rcx, rax
0x14003092b  mov     edx, ebx
0x14003092d  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x140030933  mov     rcx, cs:WPP_GLOBAL_Control
0x14003093a  lea     rax, WPP_GLOBAL_Control
0x140030941  cmp     rcx, rax
0x140030944  jz      short loc_14003096A
0x140030946  test    byte ptr [rcx+1Ch], 4
0x14003094a  jz      short loc_14003096A
0x14003094c  cmp     byte ptr [rcx+19h], 2
0x140030950  jb      short loc_14003096A
0x140030952  mov     rcx, [rcx+10h]
0x140030956  lea     r8, WPP_2ef91c586edc35547bed035b48d4f238_Traceguids
0x14003095d  mov     edx, 7Dh ; '}'
0x140030962  mov     r9d, ebx
0x140030965  call    WPP_SF_d
0x14003096a  mov     eax, ebx
0x14003096c  mov     rbx, [rsp+80h+arg_10]
0x140030974  add     rsp, 80h
0x14003097b  pop     r15
0x14003097d  pop     r14
0x14003097f  pop     r13
0x140030981  pop     r12
0x140030983  pop     rdi
0x140030984  pop     rsi
0x140030985  pop     rbp
0x140030986  retn
```
