# CInterceptor_IWbemServices_RestrictingInterceptor::PutClass(IWbemClassObject *,long,IWbemContext *,IWbemCallResult * *)

- ea: `0x1400347b0`
- end: `0x140034947`
- name: `?PutClass@CInterceptor_IWbemServices_RestrictingInterceptor@@UEAAJPEAUIWbemClassObject@@JPEAUIWbemContext@@PEAPEAUIWbemCallResult@@@Z`
- size: `407`
- prototype: `__int64 __usercall@<rax>(CInterceptor_IWbemServices_RestrictingInterceptor *__hidden this@<rcx>, struct IWbemClassObject *@<rdx>, int@<r8d>, struct IWbemContext *@<r9>, struct IWbemCallResult **)`
- caller_count: `0`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callees

- `0x1400234b8`
- `0x1400310f0`
- `0x140032b60`
- `0x1400347b0`
- `0x140035ec0`
- `0x140048010`

## import_xrefs

- `wbemcomn!GetMemLogObject` at `0x1400348e8`
- `wbemcomn!GetMemLogObject` at `0x1400348e8`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1400348f3`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1400348f3`

## pseudocode

```c
__int64 __fastcall CInterceptor_IWbemServices_RestrictingInterceptor::PutClass(
        CInterceptor_IWbemServices_RestrictingInterceptor *this,
        struct IWbemClassObject *a2,
        __int64 a3,
        struct IWbemContext *a4,
        struct IWbemCallResult **a5)
{
  unsigned int v6; // r14d
  int v9; // ebx
  CMemoryLog *MemLogObject; // rax
  int v12; // [rsp+20h] [rbp-60h]
  struct IWbemServices **v13; // [rsp+28h] [rbp-58h]
  int v14; // [rsp+50h] [rbp-30h] BYREF
  int v15; // [rsp+54h] [rbp-2Ch] BYREF
  struct IWbemServices v16; // [rsp+58h] [rbp-28h] BYREF
  struct IUnknown *v17; // [rsp+60h] [rbp-20h] BYREF
  struct IServerSecurity *v18; // [rsp+68h] [rbp-18h] BYREF
  struct IUnknown *v19; // [rsp+70h] [rbp-10h] BYREF
  int v20; // [rsp+B0h] [rbp+30h] BYREF

  v6 = a3;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_qdq(*((_QWORD *)WPP_GLOBAL_Control + 2), 81, a3, a2, a3, a4);
  }
  _InterlockedIncrement((volatile signed __int32 *)this + 8);
  if ( *((_DWORD *)this + 7) == 1 )
  {
    v9 = -2147217357;
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
    v9 = CInterceptor_IWbemServices_RestrictingInterceptor::Begin_IWbemServices(
           (struct IUnknown **)this,
           &v14,
           &v19,
           &v18,
           &v15,
           (struct IWbemServices **)&v16,
           &v20,
           &v17);
    if ( v9 >= 0 )
    {
      v12 = (int)a5;
      v9 = (*((__int64 (__fastcall **)(struct IWbemServicesVtbl *, struct IWbemClassObject *, _QWORD, struct IWbemContext *))v16.lpVtbl->QueryInterface
            + 8))(
             v16.lpVtbl,
             a2,
             v6,
             a4);
      CInterceptor_IWbemServices_RestrictingInterceptor::End_IWbemServices(
        this,
        v14,
        v19,
        v18,
        v12,
        (struct IWbemServices *)v13,
        v20,
        v17);
    }
  }
  _InterlockedDecrement((volatile signed __int32 *)this + 8);
  if ( v9 < 0 )
  {
    MemLogObject = GetMemLogObject();
    CMemoryLog::Write(MemLogObject, v9);
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 82, WPP_2ef91c586edc35547bed035b48d4f238_Traceguids, (unsigned int)v9);
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x1400347b0  mov     [rsp-28h+arg_8], rbx
0x1400347b5  mov     [rsp-28h+arg_10], rsi
0x1400347ba  push    rbp
0x1400347bb  push    rdi
0x1400347bc  push    r13
0x1400347be  push    r14
0x1400347c0  push    r15
0x1400347c2  mov     rbp, rsp
0x1400347c5  sub     rsp, 80h
0x1400347cc  mov     rsi, r9
0x1400347cf  mov     r14d, r8d
0x1400347d2  mov     r15, rdx
0x1400347d5  mov     rdi, rcx
0x1400347d8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400347df  lea     r13, WPP_GLOBAL_Control
0x1400347e6  cmp     rcx, r13
0x1400347e9  jz      short loc_140034812
0x1400347eb  test    byte ptr [rcx+1Ch], 4
0x1400347ef  jz      short loc_140034812
0x1400347f1  cmp     byte ptr [rcx+19h], 5
0x1400347f5  jb      short loc_140034812
0x1400347f7  mov     rcx, [rcx+10h]
0x1400347fb  mov     edx, 51h ; 'Q'
0x140034800  mov     [rsp+80h+var_58], r9
0x140034805  mov     r9, r15
0x140034808  mov     dword ptr [rsp+80h+var_60], r8d
0x14003480d  call    WPP_SF_qdq
0x140034812  lock inc dword ptr [rdi+20h]
0x140034816  cmp     dword ptr [rdi+1Ch], 1
0x14003481a  jnz     short loc_140034826
0x14003481c  mov     ebx, 80041033h
0x140034821  jmp     loc_1400348E0
0x140034826  lea     rax, [rbp+var_20]
0x14003482a  mov     [rbp+var_30], 0
0x140034831  mov     [rsp+80h+var_48], rax; struct IUnknown **
0x140034836  lea     r9, [rbp+var_18]; struct IServerSecurity **
0x14003483a  lea     rax, [rbp+arg_0]
0x14003483e  mov     [rbp+var_10], 0
0x140034846  mov     [rsp+80h+var_50], rax; int *
0x14003484b  lea     r8, [rbp+var_10]; struct IUnknown **
0x14003484f  lea     rax, [rbp+var_28]
0x140034853  mov     [rbp+var_18], 0
0x14003485b  mov     [rsp+80h+var_58], rax; struct IWbemServices *
0x140034860  lea     rdx, [rbp+var_30]; int *
0x140034864  lea     rax, [rbp+var_2C]
0x140034868  mov     [rbp+var_2C], 0
0x14003486f  mov     rcx, rdi; this
0x140034872  mov     [rsp+80h+var_60], rax; int *
0x140034877  mov     [rbp+var_28.lpVtbl], 0
0x14003487f  mov     [rbp+arg_0], 0
0x140034886  mov     [rbp+var_20], 0
0x14003488e  call    ?Begin_IWbemServices@CInterceptor_IWbemServices_RestrictingInterceptor@@AEAAJAEAHAEAPEAUIUnknown@@AEAPEAUIServerSecurity@@0AEAPEAUIWbemServices@@01PEAUIWbemContext@@@Z; CInterceptor_IWbemServices_RestrictingInterceptor::Begin_IWbemServices(int &,IUnknown * &,IServerSecurity * &,int &,IWbemServices * &,int &,IUnknown * &,IWbemContext *)
0x140034893  mov     ebx, eax
0x140034895  test    eax, eax
0x140034897  js      short loc_1400348E0
0x140034899  mov     rcx, [rbp+var_28.lpVtbl]
0x14003489d  mov     r9, rsi
0x1400348a0  mov     rdx, [rbp+arg_20]
0x1400348a4  mov     r8d, r14d
0x1400348a7  mov     [rsp+80h+var_60], rdx; int
0x1400348ac  mov     rdx, r15
0x1400348af  mov     rax, [rcx]
0x1400348b2  mov     rax, [rax+40h]
0x1400348b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400348bb  mov     r9, [rbp+var_18]; struct IServerSecurity *
0x1400348bf  mov     ebx, eax
0x1400348c1  mov     rax, [rbp+var_20]
0x1400348c5  mov     rcx, rdi; this
0x1400348c8  mov     r8, [rbp+var_10]; struct IUnknown *
0x1400348cc  mov     edx, [rbp+var_30]; int
0x1400348cf  mov     [rsp+80h+var_48], rax; struct IUnknown *
0x1400348d4  mov     eax, [rbp+arg_0]
0x1400348d7  mov     dword ptr [rsp+80h+var_50], eax; int
0x1400348db  call    ?End_IWbemServices@CInterceptor_IWbemServices_RestrictingInterceptor@@AEAAJHPEAUIUnknown@@PEAUIServerSecurity@@HPEAUIWbemServices@@H0@Z; CInterceptor_IWbemServices_RestrictingInterceptor::End_IWbemServices(int,IUnknown *,IServerSecurity *,int,IWbemServices *,int,IUnknown *)
0x1400348e0  lock dec dword ptr [rdi+20h]
0x1400348e4  test    ebx, ebx
0x1400348e6  jns     short loc_1400348F9
0x1400348e8  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1400348ee  mov     rcx, rax
0x1400348f1  mov     edx, ebx
0x1400348f3  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1400348f9  mov     rcx, cs:WPP_GLOBAL_Control
0x140034900  cmp     rcx, r13
0x140034903  jz      short loc_140034929
0x140034905  test    byte ptr [rcx+1Ch], 4
0x140034909  jz      short loc_140034929
0x14003490b  cmp     byte ptr [rcx+19h], 2
0x14003490f  jb      short loc_140034929
0x140034911  mov     rcx, [rcx+10h]
0x140034915  lea     r8, WPP_2ef91c586edc35547bed035b48d4f238_Traceguids
0x14003491c  mov     edx, 52h ; 'R'
0x140034921  mov     r9d, ebx
0x140034924  call    WPP_SF_d
0x140034929  lea     r11, [rsp+80h+var_s0]
0x140034931  mov     eax, ebx
0x140034933  mov     rbx, [r11+38h]
0x140034937  mov     rsi, [r11+40h]
0x14003493b  mov     rsp, r11
0x14003493e  pop     r15
0x140034940  pop     r14
0x140034942  pop     r13
0x140034944  pop     rdi
0x140034945  pop     rbp
0x140034946  retn
```
