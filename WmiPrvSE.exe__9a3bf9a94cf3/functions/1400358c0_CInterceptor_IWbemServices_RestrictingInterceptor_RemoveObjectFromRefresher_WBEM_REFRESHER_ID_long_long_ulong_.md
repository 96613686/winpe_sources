# CInterceptor_IWbemServices_RestrictingInterceptor::RemoveObjectFromRefresher(_WBEM_REFRESHER_ID *,long,long,ulong,ulong *)

- ea: `0x1400358c0`
- end: `0x140035a55`
- name: `?RemoveObjectFromRefresher@CInterceptor_IWbemServices_RestrictingInterceptor@@UEAAJPEAU_WBEM_REFRESHER_ID@@JJKPEAK@Z`
- size: `405`
- prototype: `__int64 __fastcall(CInterceptor_IWbemServices_RestrictingInterceptor *__hidden this, struct _WBEM_REFRESHER_ID *, int, int, unsigned int, struct IWbemRefreshingServices *)`
- caller_count: `0`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callees

- `0x1400234b8`
- `0x140030f90`
- `0x140032b04`
- `0x1400358c0`
- `0x140035d98`
- `0x140048010`

## import_xrefs

- `wbemcomn!GetMemLogObject` at `0x1400359f7`
- `wbemcomn!GetMemLogObject` at `0x1400359f7`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x140035a02`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x140035a02`

## pseudocode

```c
__int64 __fastcall CInterceptor_IWbemServices_RestrictingInterceptor::RemoveObjectFromRefresher(
        CInterceptor_IWbemServices_RestrictingInterceptor *this,
        struct _WBEM_REFRESHER_ID *a2,
        __int64 a3,
        unsigned int a4,
        unsigned int a5,
        struct IWbemRefreshingServices *a6)
{
  unsigned int v7; // r15d
  int v10; // r12d
  int v11; // ebx
  CMemoryLog *MemLogObject; // rax
  struct IWbemRefreshingServices *v14; // [rsp+28h] [rbp-51h]
  int v15; // [rsp+50h] [rbp-29h] BYREF
  int v16; // [rsp+54h] [rbp-25h] BYREF
  struct IWbemRefreshingServices *v17; // [rsp+58h] [rbp-21h] BYREF
  struct IUnknown *v18; // [rsp+60h] [rbp-19h] BYREF
  struct IServerSecurity *v19; // [rsp+68h] [rbp-11h] BYREF
  struct IUnknown *v20; // [rsp+70h] [rbp-9h] BYREF
  int v21; // [rsp+D0h] [rbp+57h] BYREF

  v7 = a3;
  v10 = a5;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_ddd(*((_QWORD *)WPP_GLOBAL_Control + 2), 126, a3, (unsigned int)a3, a4, a5);
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
      v11 = (*(__int64 (__fastcall **)(struct IWbemRefreshingServices *, struct _WBEM_REFRESHER_ID *, _QWORD, _QWORD))(*(_QWORD *)v17 + 48LL))(
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
      127,
      WPP_2ef91c586edc35547bed035b48d4f238_Traceguids,
      (unsigned int)v11);
  }
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x1400358c0  push    rbp
0x1400358c2  push    rbx
0x1400358c3  push    rsi
0x1400358c4  push    rdi
0x1400358c5  push    r12
0x1400358c7  push    r13
0x1400358c9  push    r14
0x1400358cb  push    r15
0x1400358cd  lea     rbp, [rsp-0Fh]
0x1400358d2  sub     rsp, 88h
0x1400358d9  mov     r14d, r9d
0x1400358dc  mov     r15d, r8d
0x1400358df  mov     r13, rdx
0x1400358e2  mov     rdi, rcx
0x1400358e5  mov     rcx, cs:WPP_GLOBAL_Control
0x1400358ec  lea     rax, WPP_GLOBAL_Control
0x1400358f3  mov     r12d, [rbp+47h+arg_20]
0x1400358f7  cmp     rcx, rax
0x1400358fa  jz      short loc_140035923
0x1400358fc  test    byte ptr [rcx+1Ch], 4
0x140035900  jz      short loc_140035923
0x140035902  cmp     byte ptr [rcx+19h], 5
0x140035906  jb      short loc_140035923
0x140035908  mov     rcx, [rcx+10h]
0x14003590c  mov     edx, 7Eh ; '~'
0x140035911  mov     dword ptr [rsp+0C0h+var_98], r12d
0x140035916  mov     dword ptr [rsp+0C0h+var_A0], r9d
0x14003591b  mov     r9d, r8d
0x14003591e  call    WPP_SF_ddd
0x140035923  lock inc dword ptr [rdi+18h]
0x140035927  xor     ebx, ebx
0x140035929  cmp     dword ptr [rdi+14h], 1
0x14003592d  jnz     short loc_140035939
0x14003592f  mov     ebx, 80041033h
0x140035934  jmp     loc_1400359EF
0x140035939  cmp     [rdi+60h], rbx
0x14003593d  jz      loc_1400359EA
0x140035943  lea     rax, [rbp+47h+var_60]
0x140035947  mov     [rbp+47h+var_70], ebx
0x14003594a  mov     [rsp+0C0h+var_88], rax; struct IUnknown **
0x14003594f  lea     r9, [rbp+47h+var_58]; struct IServerSecurity **
0x140035953  lea     rax, [rbp+47h+arg_0]
0x140035957  mov     [rbp+47h+var_50], rbx
0x14003595b  mov     [rsp+0C0h+var_90], rax; int *
0x140035960  lea     r8, [rbp+47h+var_50]; struct IUnknown **
0x140035964  lea     rax, [rbp+47h+var_68]
0x140035968  mov     [rbp+47h+var_58], rbx
0x14003596c  mov     [rsp+0C0h+var_98], rax; struct IWbemRefreshingServices **
0x140035971  lea     rdx, [rbp+47h+var_70]; int *
0x140035975  lea     rax, [rbp+47h+var_6C]
0x140035979  mov     [rbp+47h+var_6C], ebx
0x14003597c  lea     rcx, [rdi-8]; this
0x140035980  mov     [rsp+0C0h+var_A0], rax; int *
0x140035985  mov     [rbp+47h+var_68], rbx
0x140035989  mov     [rbp+47h+arg_0], ebx
0x14003598c  mov     [rbp+47h+var_60], rbx
0x140035990  call    ?Begin_IWbemRefreshingServices@CInterceptor_IWbemServices_RestrictingInterceptor@@AEAAJAEAHAEAPEAUIUnknown@@AEAPEAUIServerSecurity@@0AEAPEAUIWbemRefreshingServices@@01PEAUIWbemContext@@@Z; CInterceptor_IWbemServices_RestrictingInterceptor::Begin_IWbemRefreshingServices(int &,IUnknown * &,IServerSecurity * &,int &,IWbemRefreshingServices * &,int &,IUnknown * &,IWbemContext *)
0x140035995  mov     ebx, eax
0x140035997  test    eax, eax
0x140035999  js      short loc_1400359EF
0x14003599b  mov     rcx, [rbp+47h+var_68]
0x14003599f  mov     r9d, r14d
0x1400359a2  mov     rdx, [rbp+47h+arg_28]
0x1400359a6  mov     r8d, r15d
0x1400359a9  mov     [rsp+0C0h+var_98], rdx; struct IWbemRefreshingServices *
0x1400359ae  mov     rdx, r13
0x1400359b1  mov     dword ptr [rsp+0C0h+var_A0], r12d; int
0x1400359b6  mov     rax, [rcx]
0x1400359b9  mov     rax, [rax+30h]
0x1400359bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400359c2  mov     r9, [rbp+47h+var_58]; struct IServerSecurity *
0x1400359c6  lea     rcx, [rdi-8]; this
0x1400359ca  mov     r8, [rbp+47h+var_50]; struct IUnknown *
0x1400359ce  mov     ebx, eax
0x1400359d0  mov     rax, [rbp+47h+var_60]
0x1400359d4  mov     edx, [rbp+47h+var_70]; int
0x1400359d7  mov     [rsp+0C0h+var_88], rax; struct IUnknown *
0x1400359dc  mov     eax, [rbp+47h+arg_0]
0x1400359df  mov     dword ptr [rsp+0C0h+var_90], eax; int
0x1400359e3  call    ?End_IWbemRefreshingServices@CInterceptor_IWbemServices_RestrictingInterceptor@@AEAAJHPEAUIUnknown@@PEAUIServerSecurity@@HPEAUIWbemRefreshingServices@@H0@Z; CInterceptor_IWbemServices_RestrictingInterceptor::End_IWbemRefreshingServices(int,IUnknown *,IServerSecurity *,int,IWbemRefreshingServices *,int,IUnknown *)
0x1400359e8  jmp     short loc_1400359EF
0x1400359ea  mov     ebx, 80041009h
0x1400359ef  lock dec dword ptr [rdi+18h]
0x1400359f3  test    ebx, ebx
0x1400359f5  jns     short loc_140035A08
0x1400359f7  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1400359fd  mov     rcx, rax
0x140035a00  mov     edx, ebx
0x140035a02  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x140035a08  mov     rcx, cs:WPP_GLOBAL_Control
0x140035a0f  lea     rax, WPP_GLOBAL_Control
0x140035a16  cmp     rcx, rax
0x140035a19  jz      short loc_140035A3F
0x140035a1b  test    byte ptr [rcx+1Ch], 4
0x140035a1f  jz      short loc_140035A3F
0x140035a21  cmp     byte ptr [rcx+19h], 2
0x140035a25  jb      short loc_140035A3F
0x140035a27  mov     rcx, [rcx+10h]
0x140035a2b  lea     r8, WPP_2ef91c586edc35547bed035b48d4f238_Traceguids
0x140035a32  mov     edx, 7Fh
0x140035a37  mov     r9d, ebx
0x140035a3a  call    WPP_SF_d
0x140035a3f  mov     eax, ebx
0x140035a41  add     rsp, 88h
0x140035a48  pop     r15
0x140035a4a  pop     r14
0x140035a4c  pop     r13
0x140035a4e  pop     r12
0x140035a50  pop     rdi
0x140035a51  pop     rsi
0x140035a52  pop     rbx
0x140035a53  pop     rbp
0x140035a54  retn
```
