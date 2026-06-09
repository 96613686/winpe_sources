# CInterceptor_IWbemServices_RestrictingInterceptor::PutInstanceAsync(IWbemClassObject *,long,IWbemContext *,IWbemObjectSink *)

- ea: `0x140035000`
- end: `0x1400351a9`
- name: `?PutInstanceAsync@CInterceptor_IWbemServices_RestrictingInterceptor@@UEAAJPEAUIWbemClassObject@@JPEAUIWbemContext@@PEAUIWbemObjectSink@@@Z`
- size: `425`
- prototype: `__int64 __usercall@<rax>(CInterceptor_IWbemServices_RestrictingInterceptor *__hidden this@<rcx>, struct IWbemClassObject *@<rdx>, int@<r8d>, struct IWbemContext *@<r9>, struct IWbemObjectSink *)`
- caller_count: `0`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callees

- `0x1400234b8`
- `0x1400304c8`
- `0x1400310f0`
- `0x140032b60`
- `0x140035000`
- `0x140048010`

## import_xrefs

- `wbemcomn!GetMemLogObject` at `0x140035143`
- `wbemcomn!GetMemLogObject` at `0x140035143`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x14003514e`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x14003514e`

## pseudocode

```c
__int64 __fastcall CInterceptor_IWbemServices_RestrictingInterceptor::PutInstanceAsync(
        CInterceptor_IWbemServices_RestrictingInterceptor *this,
        struct IWbemClassObject *a2,
        unsigned int a3,
        struct IWbemContext *a4,
        struct IWbemObjectSink *a5)
{
  int v9; // r12d
  int v10; // ebx
  CMemoryLog *MemLogObject; // rax
  struct IWbemServices **v13; // [rsp+28h] [rbp-58h]
  int v14; // [rsp+50h] [rbp-30h] BYREF
  int v15; // [rsp+54h] [rbp-2Ch] BYREF
  struct IWbemServices v16; // [rsp+58h] [rbp-28h] BYREF
  struct IUnknown *v17; // [rsp+60h] [rbp-20h] BYREF
  struct IServerSecurity *v18; // [rsp+68h] [rbp-18h] BYREF
  struct IUnknown *v19; // [rsp+70h] [rbp-10h] BYREF
  int v20; // [rsp+B0h] [rbp+30h] BYREF

  v9 = (int)a5;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_qdqq(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      95,
      WPP_2ef91c586edc35547bed035b48d4f238_Traceguids,
      a2,
      a3,
      a4,
      a5);
  }
  _InterlockedIncrement((volatile signed __int32 *)this + 8);
  if ( *((_DWORD *)this + 7) == 1 )
  {
    v10 = -2147217357;
  }
  else
  {
    v14 = 0;
    v19 = 0;
    v18 = 0;
    v15 = 0;
    v16.lpVtbl = 0;
    v20 = 0;
    v17 = 0;
    v10 = CInterceptor_IWbemServices_RestrictingInterceptor::Begin_IWbemServices(
            (struct IUnknown **)this,
            &v14,
            &v19,
            &v18,
            &v15,
            (struct IWbemServices **)&v16,
            &v20,
            &v17);
    if ( v10 >= 0 )
    {
      v10 = (*((__int64 (__fastcall **)(struct IWbemServicesVtbl *, struct IWbemClassObject *, _QWORD, struct IWbemContext *))v16.lpVtbl->QueryInterface
             + 15))(
              v16.lpVtbl,
              a2,
              a3,
              a4);
      CInterceptor_IWbemServices_RestrictingInterceptor::End_IWbemServices(
        this,
        v14,
        v19,
        v18,
        v9,
        (struct IWbemServices *)v13,
        v20,
        v17);
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
      96,
      WPP_2ef91c586edc35547bed035b48d4f238_Traceguids,
      (unsigned int)v10);
  }
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x140035000  mov     r11, rsp
0x140035003  mov     [r11+10h], rbx
0x140035007  mov     [r11+18h], rsi
0x14003500b  push    rbp
0x14003500c  push    rdi
0x14003500d  push    r12
0x14003500f  push    r14
0x140035011  push    r15
0x140035013  mov     rbp, rsp
0x140035016  sub     rsp, 80h
0x14003501d  mov     rsi, r9
0x140035020  mov     r14d, r8d
0x140035023  mov     r15, rdx
0x140035026  mov     rdi, rcx
0x140035029  mov     rcx, cs:WPP_GLOBAL_Control
0x140035030  lea     rax, WPP_GLOBAL_Control
0x140035037  mov     r12, [rbp+arg_20]
0x14003503b  cmp     rcx, rax
0x14003503e  jz      short loc_140035071
0x140035040  test    byte ptr [rcx+1Ch], 4
0x140035044  jz      short loc_140035071
0x140035046  cmp     byte ptr [rcx+19h], 5
0x14003504a  jb      short loc_140035071
0x14003504c  mov     rcx, [rcx+10h]
0x140035050  mov     edx, 5Fh ; '_'
0x140035055  mov     [r11-78h], r12
0x140035059  mov     [r11-80h], r9
0x14003505d  mov     r9, r15
0x140035060  mov     dword ptr [rsp+80h+var_60], r8d
0x140035065  lea     r8, WPP_2ef91c586edc35547bed035b48d4f238_Traceguids
0x14003506c  call    WPP_SF_qdqq
0x140035071  lock inc dword ptr [rdi+20h]
0x140035075  cmp     dword ptr [rdi+1Ch], 1
0x140035079  jnz     short loc_140035085
0x14003507b  mov     ebx, 80041033h
0x140035080  jmp     loc_14003513B
0x140035085  lea     rax, [rbp+var_20]
0x140035089  mov     [rbp+var_30], 0
0x140035090  mov     [rsp+80h+var_48], rax; struct IUnknown **
0x140035095  lea     r9, [rbp+var_18]; struct IServerSecurity **
0x140035099  lea     rax, [rbp+arg_0]
0x14003509d  mov     [rbp+var_10], 0
0x1400350a5  mov     [rsp+80h+var_50], rax; int *
0x1400350aa  lea     r8, [rbp+var_10]; struct IUnknown **
0x1400350ae  lea     rax, [rbp+var_28]
0x1400350b2  mov     [rbp+var_18], 0
0x1400350ba  mov     [rsp+80h+var_58], rax; struct IWbemServices *
0x1400350bf  lea     rdx, [rbp+var_30]; int *
0x1400350c3  lea     rax, [rbp+var_2C]
0x1400350c7  mov     [rbp+var_2C], 0
0x1400350ce  mov     rcx, rdi; this
0x1400350d1  mov     [rsp+80h+var_60], rax; int *
0x1400350d6  mov     [rbp+var_28.lpVtbl], 0
0x1400350de  mov     [rbp+arg_0], 0
0x1400350e5  mov     [rbp+var_20], 0
0x1400350ed  call    ?Begin_IWbemServices@CInterceptor_IWbemServices_RestrictingInterceptor@@AEAAJAEAHAEAPEAUIUnknown@@AEAPEAUIServerSecurity@@0AEAPEAUIWbemServices@@01PEAUIWbemContext@@@Z; CInterceptor_IWbemServices_RestrictingInterceptor::Begin_IWbemServices(int &,IUnknown * &,IServerSecurity * &,int &,IWbemServices * &,int &,IUnknown * &,IWbemContext *)
0x1400350f2  mov     ebx, eax
0x1400350f4  test    eax, eax
0x1400350f6  js      short loc_14003513B
0x1400350f8  mov     rcx, [rbp+var_28.lpVtbl]
0x1400350fc  mov     r9, rsi
0x1400350ff  mov     r8d, r14d
0x140035102  mov     [rsp+80h+var_60], r12; int
0x140035107  mov     rdx, r15
0x14003510a  mov     rax, [rcx]
0x14003510d  mov     rax, [rax+78h]
0x140035111  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140035116  mov     r9, [rbp+var_18]; struct IServerSecurity *
0x14003511a  mov     ebx, eax
0x14003511c  mov     rax, [rbp+var_20]
0x140035120  mov     rcx, rdi; this
0x140035123  mov     r8, [rbp+var_10]; struct IUnknown *
0x140035127  mov     edx, [rbp+var_30]; int
0x14003512a  mov     [rsp+80h+var_48], rax; struct IUnknown *
0x14003512f  mov     eax, [rbp+arg_0]
0x140035132  mov     dword ptr [rsp+80h+var_50], eax; int
0x140035136  call    ?End_IWbemServices@CInterceptor_IWbemServices_RestrictingInterceptor@@AEAAJHPEAUIUnknown@@PEAUIServerSecurity@@HPEAUIWbemServices@@H0@Z; CInterceptor_IWbemServices_RestrictingInterceptor::End_IWbemServices(int,IUnknown *,IServerSecurity *,int,IWbemServices *,int,IUnknown *)
0x14003513b  lock dec dword ptr [rdi+20h]
0x14003513f  test    ebx, ebx
0x140035141  jns     short loc_140035154
0x140035143  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x140035149  mov     rcx, rax
0x14003514c  mov     edx, ebx
0x14003514e  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x140035154  mov     rcx, cs:WPP_GLOBAL_Control
0x14003515b  lea     rax, WPP_GLOBAL_Control
0x140035162  cmp     rcx, rax
0x140035165  jz      short loc_14003518B
0x140035167  test    byte ptr [rcx+1Ch], 4
0x14003516b  jz      short loc_14003518B
0x14003516d  cmp     byte ptr [rcx+19h], 2
0x140035171  jb      short loc_14003518B
0x140035173  mov     rcx, [rcx+10h]
0x140035177  lea     r8, WPP_2ef91c586edc35547bed035b48d4f238_Traceguids
0x14003517e  mov     edx, 60h ; '`'
0x140035183  mov     r9d, ebx
0x140035186  call    WPP_SF_d
0x14003518b  lea     r11, [rsp+80h+var_s0]
0x140035193  mov     eax, ebx
0x140035195  mov     rbx, [r11+38h]
0x140035199  mov     rsi, [r11+40h]
0x14003519d  mov     rsp, r11
0x1400351a0  pop     r15
0x1400351a2  pop     r14
0x1400351a4  pop     r12
0x1400351a6  pop     rdi
0x1400351a7  pop     rbp
0x1400351a8  retn
```
