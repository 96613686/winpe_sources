# CInterceptor_IWbemServices_RestrictingInterceptor::AddObjectToRefresher(_WBEM_REFRESHER_ID *,ushort const *,long,IWbemContext *,ulong,_WBEM_REFRESH_INFO *,ulong *)

- ea: `0x140030ac0`
- end: `0x140030c77`
- name: `?AddObjectToRefresher@CInterceptor_IWbemServices_RestrictingInterceptor@@UEAAJPEAU_WBEM_REFRESHER_ID@@PEBGJPEAUIWbemContext@@KPEAU_WBEM_REFRESH_INFO@@PEAK@Z`
- size: `439`
- prototype: `__int64 __fastcall(CInterceptor_IWbemServices_RestrictingInterceptor *this, struct _WBEM_REFRESHER_ID *, const unsigned __int16 *, unsigned int, struct IWbemContext *, struct IWbemRefreshingServices *)`
- caller_count: `0`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callees

- `0x1400234b8`
- `0x140030ac0`
- `0x140030f90`
- `0x140032b04`
- `0x140035cf0`
- `0x140048010`

## import_xrefs

- `wbemcomn!GetMemLogObject` at `0x140030c12`
- `wbemcomn!GetMemLogObject` at `0x140030c12`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x140030c1d`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x140030c1d`

## pseudocode

```c
__int64 __fastcall CInterceptor_IWbemServices_RestrictingInterceptor::AddObjectToRefresher(
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
    WPP_SF_Sdqd(*((_QWORD *)WPP_GLOBAL_Control + 2), 120, (_DWORD)a3, (_DWORD)a3, a4, (char)a5, (char)a6);
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
      v11 = (*(__int64 (__fastcall **)(struct IWbemRefreshingServices *, struct _WBEM_REFRESHER_ID *, const unsigned __int16 *, _QWORD))(*(_QWORD *)v18 + 24LL))(
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
      121,
      WPP_2ef91c586edc35547bed035b48d4f238_Traceguids,
      (unsigned int)v11);
  }
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x140030ac0  mov     [rsp-38h+arg_10], rbx
0x140030ac5  mov     [rsp-38h+arg_8], rdx
0x140030aca  push    rbp
0x140030acb  push    rsi
0x140030acc  push    rdi
0x140030acd  push    r12
0x140030acf  push    r13
0x140030ad1  push    r14
0x140030ad3  push    r15
0x140030ad5  mov     rbp, rsp
0x140030ad8  sub     rsp, 80h
0x140030adf  mov     r14d, r9d
0x140030ae2  mov     r15, r8
0x140030ae5  mov     rdi, rcx
0x140030ae8  mov     rcx, cs:WPP_GLOBAL_Control
0x140030aef  lea     rax, WPP_GLOBAL_Control
0x140030af6  mov     r12d, dword ptr [rbp+arg_28]
0x140030afa  mov     r13, [rbp+arg_20]
0x140030afe  cmp     rcx, rax
0x140030b01  jz      short loc_140030B2F
0x140030b03  test    byte ptr [rcx+1Ch], 4
0x140030b07  jz      short loc_140030B2F
0x140030b09  cmp     byte ptr [rcx+19h], 5
0x140030b0d  jb      short loc_140030B2F
0x140030b0f  mov     rcx, [rcx+10h]
0x140030b13  mov     edx, 78h ; 'x'
0x140030b18  mov     dword ptr [rsp+80h+var_50], r12d
0x140030b1d  mov     [rsp+80h+var_58], r13
0x140030b22  mov     dword ptr [rsp+80h+var_60], r9d
0x140030b27  mov     r9, r8
0x140030b2a  call    WPP_SF_Sdqd
0x140030b2f  lock inc dword ptr [rdi+18h]
0x140030b33  xor     ebx, ebx
0x140030b35  cmp     dword ptr [rdi+14h], 1
0x140030b39  jnz     short loc_140030B45
0x140030b3b  mov     ebx, 80041033h
0x140030b40  jmp     loc_140030C0A
0x140030b45  cmp     [rdi+60h], rbx
0x140030b49  jz      loc_140030C05
0x140030b4f  lea     rax, [rbp+var_20]
0x140030b53  mov     [rbp+var_30], ebx
0x140030b56  mov     [rsp+80h+var_48], rax; struct IUnknown **
0x140030b5b  lea     r9, [rbp+var_18]; struct IServerSecurity **
0x140030b5f  lea     rax, [rbp+arg_0]
0x140030b63  mov     [rbp+var_10], rbx
0x140030b67  mov     [rsp+80h+var_50], rax; int *
0x140030b6c  lea     r8, [rbp+var_10]; struct IUnknown **
0x140030b70  lea     rax, [rbp+var_28]
0x140030b74  mov     [rbp+var_18], rbx
0x140030b78  mov     [rsp+80h+var_58], rax; struct IWbemRefreshingServices **
0x140030b7d  lea     rdx, [rbp+var_30]; int *
0x140030b81  lea     rax, [rbp+var_2C]
0x140030b85  mov     [rbp+var_2C], ebx
0x140030b88  lea     rcx, [rdi-8]; this
0x140030b8c  mov     [rsp+80h+var_60], rax; int *
0x140030b91  mov     [rbp+var_28], rbx
0x140030b95  mov     [rbp+arg_0], ebx
0x140030b98  mov     [rbp+var_20], rbx
0x140030b9c  call    ?Begin_IWbemRefreshingServices@CInterceptor_IWbemServices_RestrictingInterceptor@@AEAAJAEAHAEAPEAUIUnknown@@AEAPEAUIServerSecurity@@0AEAPEAUIWbemRefreshingServices@@01PEAUIWbemContext@@@Z; CInterceptor_IWbemServices_RestrictingInterceptor::Begin_IWbemRefreshingServices(int &,IUnknown * &,IServerSecurity * &,int &,IWbemRefreshingServices * &,int &,IUnknown * &,IWbemContext *)
0x140030ba1  mov     ebx, eax
0x140030ba3  test    eax, eax
0x140030ba5  js      short loc_140030C0A
0x140030ba7  mov     rcx, [rbp+var_28]
0x140030bab  mov     r9d, r14d
0x140030bae  mov     rdx, [rbp+arg_38]
0x140030bb2  mov     r8, r15
0x140030bb5  mov     [rsp+80h+var_48], rdx
0x140030bba  mov     rdx, [rbp+arg_30]
0x140030bbe  mov     rax, [rcx]
0x140030bc1  mov     [rsp+80h+var_50], rdx
0x140030bc6  mov     rdx, [rbp+arg_8]
0x140030bca  mov     dword ptr [rsp+80h+var_58], r12d; struct IWbemRefreshingServices *
0x140030bcf  mov     rax, [rax+18h]
0x140030bd3  mov     [rsp+80h+var_60], r13; int
0x140030bd8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140030bdd  mov     r9, [rbp+var_18]; struct IServerSecurity *
0x140030be1  lea     rcx, [rdi-8]; this
0x140030be5  mov     r8, [rbp+var_10]; struct IUnknown *
0x140030be9  mov     ebx, eax
0x140030beb  mov     rax, [rbp+var_20]
0x140030bef  mov     edx, [rbp+var_30]; int
0x140030bf2  mov     [rsp+80h+var_48], rax; struct IUnknown *
0x140030bf7  mov     eax, [rbp+arg_0]
0x140030bfa  mov     dword ptr [rsp+80h+var_50], eax; int
0x140030bfe  call    ?End_IWbemRefreshingServices@CInterceptor_IWbemServices_RestrictingInterceptor@@AEAAJHPEAUIUnknown@@PEAUIServerSecurity@@HPEAUIWbemRefreshingServices@@H0@Z; CInterceptor_IWbemServices_RestrictingInterceptor::End_IWbemRefreshingServices(int,IUnknown *,IServerSecurity *,int,IWbemRefreshingServices *,int,IUnknown *)
0x140030c03  jmp     short loc_140030C0A
0x140030c05  mov     ebx, 80041009h
0x140030c0a  lock dec dword ptr [rdi+18h]
0x140030c0e  test    ebx, ebx
0x140030c10  jns     short loc_140030C23
0x140030c12  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x140030c18  mov     rcx, rax
0x140030c1b  mov     edx, ebx
0x140030c1d  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x140030c23  mov     rcx, cs:WPP_GLOBAL_Control
0x140030c2a  lea     rax, WPP_GLOBAL_Control
0x140030c31  cmp     rcx, rax
0x140030c34  jz      short loc_140030C5A
0x140030c36  test    byte ptr [rcx+1Ch], 4
0x140030c3a  jz      short loc_140030C5A
0x140030c3c  cmp     byte ptr [rcx+19h], 2
0x140030c40  jb      short loc_140030C5A
0x140030c42  mov     rcx, [rcx+10h]
0x140030c46  lea     r8, WPP_2ef91c586edc35547bed035b48d4f238_Traceguids
0x140030c4d  mov     edx, 79h ; 'y'
0x140030c52  mov     r9d, ebx
0x140030c55  call    WPP_SF_d
0x140030c5a  mov     eax, ebx
0x140030c5c  mov     rbx, [rsp+80h+arg_10]
0x140030c64  add     rsp, 80h
0x140030c6b  pop     r15
0x140030c6d  pop     r14
0x140030c6f  pop     r13
0x140030c71  pop     r12
0x140030c73  pop     rdi
0x140030c74  pop     rsi
0x140030c75  pop     rbp
0x140030c76  retn
```
