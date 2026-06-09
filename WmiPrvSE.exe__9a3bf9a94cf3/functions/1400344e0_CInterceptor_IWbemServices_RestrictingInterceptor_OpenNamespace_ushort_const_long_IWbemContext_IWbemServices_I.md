# CInterceptor_IWbemServices_RestrictingInterceptor::OpenNamespace(ushort * const,long,IWbemContext *,IWbemServices * *,IWbemCallResult * *)

- ea: `0x1400344e0`
- end: `0x140034680`
- name: `?OpenNamespace@CInterceptor_IWbemServices_RestrictingInterceptor@@UEAAJQEAGJPEAUIWbemContext@@PEAPEAUIWbemServices@@PEAPEAUIWbemCallResult@@@Z`
- size: `416`
- prototype: `__int64 __usercall@<rax>(CInterceptor_IWbemServices_RestrictingInterceptor *__hidden this@<rcx>, unsigned __int16 *const@<rdx>, int@<r8d>, struct IWbemContext *@<r9>, struct IWbemServices **, struct IWbemCallResult **)`
- caller_count: `0`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callees

- `0x1400234b8`
- `0x1400310f0`
- `0x140032b60`
- `0x1400344e0`
- `0x140035c5c`
- `0x140048010`

## import_xrefs

- `wbemcomn!GetMemLogObject` at `0x140034621`
- `wbemcomn!GetMemLogObject` at `0x140034621`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x14003462c`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x14003462c`

## pseudocode

```c
__int64 __fastcall CInterceptor_IWbemServices_RestrictingInterceptor::OpenNamespace(
        CInterceptor_IWbemServices_RestrictingInterceptor *this,
        unsigned __int16 *const a2,
        unsigned int a3,
        struct IWbemContext *a4,
        struct IWbemServices **a5,
        struct IWbemServices **a6)
{
  int v10; // ebx
  CMemoryLog *MemLogObject; // rax
  int v13; // [rsp+20h] [rbp-60h]
  struct IWbemServices **v14; // [rsp+28h] [rbp-58h]
  int v15; // [rsp+50h] [rbp-30h] BYREF
  int v16; // [rsp+54h] [rbp-2Ch] BYREF
  struct IWbemServices *v17; // [rsp+58h] [rbp-28h] BYREF
  struct IUnknown *v18; // [rsp+60h] [rbp-20h] BYREF
  struct IServerSecurity *v19; // [rsp+68h] [rbp-18h] BYREF
  struct IUnknown *v20; // [rsp+70h] [rbp-10h] BYREF
  int v21; // [rsp+B0h] [rbp+30h] BYREF

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_Sdq(*((_QWORD *)WPP_GLOBAL_Control + 2), 71, a3, (_DWORD)a2, a3, (char)a4);
  }
  _InterlockedIncrement((volatile signed __int32 *)this + 8);
  if ( *((_DWORD *)this + 7) == 1 )
  {
    v10 = -2147217357;
  }
  else
  {
    v15 = 0;
    v20 = 0;
    v19 = 0;
    v16 = 0;
    v17 = 0;
    v21 = 0;
    v18 = 0;
    v10 = CInterceptor_IWbemServices_RestrictingInterceptor::Begin_IWbemServices(
            (struct IUnknown **)this,
            &v15,
            &v20,
            &v19,
            &v16,
            &v17,
            &v21,
            &v18);
    if ( v10 >= 0 )
    {
      v14 = a6;
      v13 = (int)a5;
      v10 = ((__int64 (__fastcall *)(struct IWbemServices *, unsigned __int16 *const, _QWORD, struct IWbemContext *))v17->lpVtbl->OpenNamespace)(
              v17,
              a2,
              a3,
              a4);
      CInterceptor_IWbemServices_RestrictingInterceptor::End_IWbemServices(
        this,
        v15,
        v20,
        v19,
        v13,
        (struct IWbemServices *)v14,
        v21,
        v18);
    }
  }
  _InterlockedDecrement((volatile signed __int32 *)this + 8);
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
      72,
      WPP_2ef91c586edc35547bed035b48d4f238_Traceguids,
      (unsigned int)v10);
  }
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x1400344e0  mov     [rsp-28h+arg_8], rbx
0x1400344e5  mov     [rsp-28h+arg_10], rsi
0x1400344ea  push    rbp
0x1400344eb  push    rdi
0x1400344ec  push    r13
0x1400344ee  push    r14
0x1400344f0  push    r15
0x1400344f2  mov     rbp, rsp
0x1400344f5  sub     rsp, 80h
0x1400344fc  mov     rsi, r9
0x1400344ff  mov     r14d, r8d
0x140034502  mov     r15, rdx
0x140034505  mov     rdi, rcx
0x140034508  mov     rcx, cs:WPP_GLOBAL_Control
0x14003450f  lea     r13, WPP_GLOBAL_Control
0x140034516  cmp     rcx, r13
0x140034519  jz      short loc_140034542
0x14003451b  test    byte ptr [rcx+1Ch], 4
0x14003451f  jz      short loc_140034542
0x140034521  cmp     byte ptr [rcx+19h], 5
0x140034525  jb      short loc_140034542
0x140034527  mov     rcx, [rcx+10h]
0x14003452b  mov     edx, 47h ; 'G'
0x140034530  mov     [rsp+80h+var_58], r9
0x140034535  mov     r9, r15
0x140034538  mov     dword ptr [rsp+80h+var_60], r8d
0x14003453d  call    WPP_SF_Sdq
0x140034542  lock inc dword ptr [rdi+20h]
0x140034546  cmp     dword ptr [rdi+1Ch], 1
0x14003454a  jnz     short loc_140034556
0x14003454c  mov     ebx, 80041033h
0x140034551  jmp     loc_140034619
0x140034556  lea     rax, [rbp+var_20]
0x14003455a  mov     [rbp+var_30], 0
0x140034561  mov     [rsp+80h+var_48], rax; struct IUnknown **
0x140034566  lea     r9, [rbp+var_18]; struct IServerSecurity **
0x14003456a  lea     rax, [rbp+arg_0]
0x14003456e  mov     [rbp+var_10], 0
0x140034576  mov     [rsp+80h+var_50], rax; int *
0x14003457b  lea     r8, [rbp+var_10]; struct IUnknown **
0x14003457f  lea     rax, [rbp+var_28]
0x140034583  mov     [rbp+var_18], 0
0x14003458b  mov     [rsp+80h+var_58], rax; struct IWbemServices **
0x140034590  lea     rdx, [rbp+var_30]; int *
0x140034594  lea     rax, [rbp+var_2C]
0x140034598  mov     [rbp+var_2C], 0
0x14003459f  mov     rcx, rdi; this
0x1400345a2  mov     [rsp+80h+var_60], rax; int *
0x1400345a7  mov     [rbp+var_28], 0
0x1400345af  mov     [rbp+arg_0], 0
0x1400345b6  mov     [rbp+var_20], 0
0x1400345be  call    ?Begin_IWbemServices@CInterceptor_IWbemServices_RestrictingInterceptor@@AEAAJAEAHAEAPEAUIUnknown@@AEAPEAUIServerSecurity@@0AEAPEAUIWbemServices@@01PEAUIWbemContext@@@Z; CInterceptor_IWbemServices_RestrictingInterceptor::Begin_IWbemServices(int &,IUnknown * &,IServerSecurity * &,int &,IWbemServices * &,int &,IUnknown * &,IWbemContext *)
0x1400345c3  mov     ebx, eax
0x1400345c5  test    eax, eax
0x1400345c7  js      short loc_140034619
0x1400345c9  mov     rcx, [rbp+var_28]
0x1400345cd  mov     r9, rsi
0x1400345d0  mov     rdx, [rbp+arg_28]
0x1400345d4  mov     r8d, r14d
0x1400345d7  mov     [rsp+80h+var_58], rdx; struct IWbemServices *
0x1400345dc  mov     rdx, [rbp+arg_20]
0x1400345e0  mov     rax, [rcx]
0x1400345e3  mov     [rsp+80h+var_60], rdx; int
0x1400345e8  mov     rdx, r15
0x1400345eb  mov     rax, [rax+18h]
0x1400345ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400345f4  mov     r9, [rbp+var_18]; struct IServerSecurity *
0x1400345f8  mov     ebx, eax
0x1400345fa  mov     rax, [rbp+var_20]
0x1400345fe  mov     rcx, rdi; this
0x140034601  mov     r8, [rbp+var_10]; struct IUnknown *
0x140034605  mov     edx, [rbp+var_30]; int
0x140034608  mov     [rsp+80h+var_48], rax; struct IUnknown *
0x14003460d  mov     eax, [rbp+arg_0]
0x140034610  mov     dword ptr [rsp+80h+var_50], eax; int
0x140034614  call    ?End_IWbemServices@CInterceptor_IWbemServices_RestrictingInterceptor@@AEAAJHPEAUIUnknown@@PEAUIServerSecurity@@HPEAUIWbemServices@@H0@Z; CInterceptor_IWbemServices_RestrictingInterceptor::End_IWbemServices(int,IUnknown *,IServerSecurity *,int,IWbemServices *,int,IUnknown *)
0x140034619  lock dec dword ptr [rdi+20h]
0x14003461d  test    ebx, ebx
0x14003461f  jns     short loc_140034632
0x140034621  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x140034627  mov     rcx, rax
0x14003462a  mov     edx, ebx
0x14003462c  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x140034632  mov     rcx, cs:WPP_GLOBAL_Control
0x140034639  cmp     rcx, r13
0x14003463c  jz      short loc_140034662
0x14003463e  test    byte ptr [rcx+1Ch], 4
0x140034642  jz      short loc_140034662
0x140034644  cmp     byte ptr [rcx+19h], 2
0x140034648  jb      short loc_140034662
0x14003464a  mov     rcx, [rcx+10h]
0x14003464e  lea     r8, WPP_2ef91c586edc35547bed035b48d4f238_Traceguids
0x140034655  mov     edx, 48h ; 'H'
0x14003465a  mov     r9d, ebx
0x14003465d  call    WPP_SF_d
0x140034662  lea     r11, [rsp+80h+var_s0]
0x14003466a  mov     eax, ebx
0x14003466c  mov     rbx, [r11+38h]
0x140034670  mov     rsi, [r11+40h]
0x140034674  mov     rsp, r11
0x140034677  pop     r15
0x140034679  pop     r14
0x14003467b  pop     r13
0x14003467d  pop     rdi
0x14003467e  pop     rbp
0x14003467f  retn
```
