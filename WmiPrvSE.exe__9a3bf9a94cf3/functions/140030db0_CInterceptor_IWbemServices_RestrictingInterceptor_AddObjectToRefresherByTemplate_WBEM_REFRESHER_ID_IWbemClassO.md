# CInterceptor_IWbemServices_RestrictingInterceptor::AddObjectToRefresherByTemplate(_WBEM_REFRESHER_ID *,IWbemClassObject *,long,IWbemContext *,ulong,_WBEM_REFRESH_INFO *,ulong *)

- ea: `0x140030db0`
- end: `0x140030f67`
- name: `?AddObjectToRefresherByTemplate@CInterceptor_IWbemServices_RestrictingInterceptor@@UEAAJPEAU_WBEM_REFRESHER_ID@@PEAUIWbemClassObject@@JPEAUIWbemContext@@KPEAU_WBEM_REFRESH_INFO@@PEAK@Z`
- size: `439`
- prototype: `__int64 __fastcall(CInterceptor_IWbemServices_RestrictingInterceptor *this, struct _WBEM_REFRESHER_ID *, struct IWbemClassObject *, unsigned int, struct IWbemContext *, struct IWbemRefreshingServices *)`
- caller_count: `0`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callees

- `0x1400234b8`
- `0x140030db0`
- `0x140030f90`
- `0x140032b04`
- `0x140035f24`
- `0x140048010`

## import_xrefs

- `wbemcomn!GetMemLogObject` at `0x140030f02`
- `wbemcomn!GetMemLogObject` at `0x140030f02`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x140030f0d`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x140030f0d`

## pseudocode

```c
__int64 __fastcall CInterceptor_IWbemServices_RestrictingInterceptor::AddObjectToRefresherByTemplate(
        CInterceptor_IWbemServices_RestrictingInterceptor *this,
        struct _WBEM_REFRESHER_ID *a2,
        struct IWbemClassObject *a3,
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
    WPP_SF_qdqd(*((_QWORD *)WPP_GLOBAL_Control + 2), 122, a3, a3, a4, a5, (_DWORD)a6);
  }
  _InterlockedIncrement((volatile signed __int32 *)this + 6);
  if ( *((_DWORD *)this + 5) == 1 )
  {
    v11 = -2147217357;
  }
  else
  {
    v11 = 0;
    if ( *((_QWORD *)this + 12) )
    {
      v16 = 0;
      v21 = 0;
      v20 = 0;
      v17 = 0;
      v18 = 0;
      v22 = 0;
      v19 = 0;
      if ( CInterceptor_IWbemServices_RestrictingInterceptor::Begin_IWbemRefreshingServices(
             (CInterceptor_IWbemServices_RestrictingInterceptor *)((char *)this - 8),
             &v16,
             &v21,
             &v20,
             &v17,
             &v18,
             &v22,
             &v19,
             v15) < 0 )
      {
        v11 = -2147217399;
      }
      else
      {
        LODWORD(v14) = v9;
        v11 = (*(__int64 (__fastcall **)(struct IWbemRefreshingServices *, struct _WBEM_REFRESHER_ID *, struct IWbemClassObject *, _QWORD))(*(_QWORD *)v18 + 32LL))(
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
      123,
      WPP_2ef91c586edc35547bed035b48d4f238_Traceguids,
      (unsigned int)v11);
  }
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x140030db0  mov     [rsp-38h+arg_10], rbx
0x140030db5  mov     [rsp-38h+arg_8], rdx
0x140030dba  push    rbp
0x140030dbb  push    rsi
0x140030dbc  push    rdi
0x140030dbd  push    r12
0x140030dbf  push    r13
0x140030dc1  push    r14
0x140030dc3  push    r15
0x140030dc5  mov     rbp, rsp
0x140030dc8  sub     rsp, 80h
0x140030dcf  mov     r14d, r9d
0x140030dd2  mov     r15, r8
0x140030dd5  mov     rdi, rcx
0x140030dd8  mov     rcx, cs:WPP_GLOBAL_Control
0x140030ddf  lea     rax, WPP_GLOBAL_Control
0x140030de6  mov     r12d, dword ptr [rbp+arg_28]
0x140030dea  mov     r13, [rbp+arg_20]
0x140030dee  cmp     rcx, rax
0x140030df1  jz      short loc_140030E1F
0x140030df3  test    byte ptr [rcx+1Ch], 4
0x140030df7  jz      short loc_140030E1F
0x140030df9  cmp     byte ptr [rcx+19h], 5
0x140030dfd  jb      short loc_140030E1F
0x140030dff  mov     rcx, [rcx+10h]
0x140030e03  mov     edx, 7Ah ; 'z'
0x140030e08  mov     dword ptr [rsp+80h+var_50], r12d
0x140030e0d  mov     [rsp+80h+var_58], r13
0x140030e12  mov     dword ptr [rsp+80h+var_60], r9d
0x140030e17  mov     r9, r8
0x140030e1a  call    WPP_SF_qdqd
0x140030e1f  lock inc dword ptr [rdi+18h]
0x140030e23  xor     eax, eax
0x140030e25  cmp     dword ptr [rdi+14h], 1
0x140030e29  jnz     short loc_140030E35
0x140030e2b  mov     ebx, 80041033h
0x140030e30  jmp     loc_140030EFA
0x140030e35  mov     ebx, eax
0x140030e37  cmp     [rdi+60h], rax
0x140030e3b  jz      loc_140030EFA
0x140030e41  mov     [rbp+var_30], eax
0x140030e44  lea     r9, [rbp+var_18]; struct IServerSecurity **
0x140030e48  mov     [rbp+var_10], rax
0x140030e4c  lea     r8, [rbp+var_10]; struct IUnknown **
0x140030e50  mov     [rbp+var_18], rax
0x140030e54  lea     rdx, [rbp+var_30]; int *
0x140030e58  mov     [rbp+var_2C], eax
0x140030e5b  lea     rcx, [rdi-8]; this
0x140030e5f  mov     [rbp+var_28], rax
0x140030e63  mov     [rbp+arg_0], eax
0x140030e66  mov     [rbp+var_20], rax
0x140030e6a  lea     rax, [rbp+var_20]
0x140030e6e  mov     [rsp+80h+var_48], rax; struct IUnknown **
0x140030e73  lea     rax, [rbp+arg_0]
0x140030e77  mov     [rsp+80h+var_50], rax; int *
0x140030e7c  lea     rax, [rbp+var_28]
0x140030e80  mov     [rsp+80h+var_58], rax; struct IWbemRefreshingServices **
0x140030e85  lea     rax, [rbp+var_2C]
0x140030e89  mov     [rsp+80h+var_60], rax; int *
0x140030e8e  call    ?Begin_IWbemRefreshingServices@CInterceptor_IWbemServices_RestrictingInterceptor@@AEAAJAEAHAEAPEAUIUnknown@@AEAPEAUIServerSecurity@@0AEAPEAUIWbemRefreshingServices@@01PEAUIWbemContext@@@Z; CInterceptor_IWbemServices_RestrictingInterceptor::Begin_IWbemRefreshingServices(int &,IUnknown * &,IServerSecurity * &,int &,IWbemRefreshingServices * &,int &,IUnknown * &,IWbemContext *)
0x140030e93  test    eax, eax
0x140030e95  js      short loc_140030EF5
0x140030e97  mov     rcx, [rbp+var_28]
0x140030e9b  mov     r9d, r14d
0x140030e9e  mov     rdx, [rbp+arg_38]
0x140030ea2  mov     r8, r15
0x140030ea5  mov     [rsp+80h+var_48], rdx
0x140030eaa  mov     rdx, [rbp+arg_30]
0x140030eae  mov     rax, [rcx]
0x140030eb1  mov     [rsp+80h+var_50], rdx
0x140030eb6  mov     rdx, [rbp+arg_8]
0x140030eba  mov     dword ptr [rsp+80h+var_58], r12d; struct IWbemRefreshingServices *
0x140030ebf  mov     rax, [rax+20h]
0x140030ec3  mov     [rsp+80h+var_60], r13; int
0x140030ec8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140030ecd  mov     rdx, [rbp+var_20]
0x140030ed1  lea     rcx, [rdi-8]; this
0x140030ed5  mov     r9, [rbp+var_18]; struct IServerSecurity *
0x140030ed9  mov     ebx, eax
0x140030edb  mov     r8, [rbp+var_10]; struct IUnknown *
0x140030edf  mov     [rsp+80h+var_48], rdx; struct IUnknown *
0x140030ee4  mov     edx, [rbp+arg_0]
0x140030ee7  mov     dword ptr [rsp+80h+var_50], edx; int
0x140030eeb  mov     edx, [rbp+var_30]; int
0x140030eee  call    ?End_IWbemRefreshingServices@CInterceptor_IWbemServices_RestrictingInterceptor@@AEAAJHPEAUIUnknown@@PEAUIServerSecurity@@HPEAUIWbemRefreshingServices@@H0@Z; CInterceptor_IWbemServices_RestrictingInterceptor::End_IWbemRefreshingServices(int,IUnknown *,IServerSecurity *,int,IWbemRefreshingServices *,int,IUnknown *)
0x140030ef3  jmp     short loc_140030EFA
0x140030ef5  mov     ebx, 80041009h
0x140030efa  lock dec dword ptr [rdi+18h]
0x140030efe  test    ebx, ebx
0x140030f00  jns     short loc_140030F13
0x140030f02  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x140030f08  mov     rcx, rax
0x140030f0b  mov     edx, ebx
0x140030f0d  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x140030f13  mov     rcx, cs:WPP_GLOBAL_Control
0x140030f1a  lea     rax, WPP_GLOBAL_Control
0x140030f21  cmp     rcx, rax
0x140030f24  jz      short loc_140030F4A
0x140030f26  test    byte ptr [rcx+1Ch], 4
0x140030f2a  jz      short loc_140030F4A
0x140030f2c  cmp     byte ptr [rcx+19h], 2
0x140030f30  jb      short loc_140030F4A
0x140030f32  mov     rcx, [rcx+10h]
0x140030f36  lea     r8, WPP_2ef91c586edc35547bed035b48d4f238_Traceguids
0x140030f3d  mov     edx, 7Bh ; '{'
0x140030f42  mov     r9d, ebx
0x140030f45  call    WPP_SF_d
0x140030f4a  mov     eax, ebx
0x140030f4c  mov     rbx, [rsp+80h+arg_10]
0x140030f54  add     rsp, 80h
0x140030f5b  pop     r15
0x140030f5d  pop     r14
0x140030f5f  pop     r13
0x140030f61  pop     r12
0x140030f63  pop     rdi
0x140030f64  pop     rsi
0x140030f65  pop     rbp
0x140030f66  retn
```
