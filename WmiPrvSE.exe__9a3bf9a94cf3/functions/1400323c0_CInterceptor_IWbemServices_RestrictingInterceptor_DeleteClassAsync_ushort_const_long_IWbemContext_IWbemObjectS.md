# CInterceptor_IWbemServices_RestrictingInterceptor::DeleteClassAsync(ushort * const,long,IWbemContext *,IWbemObjectSink *)

- ea: `0x1400323c0`
- end: `0x140032569`
- name: `?DeleteClassAsync@CInterceptor_IWbemServices_RestrictingInterceptor@@UEAAJQEAGJPEAUIWbemContext@@PEAUIWbemObjectSink@@@Z`
- size: `425`
- prototype: `__int64 __fastcall(CInterceptor_IWbemServices_RestrictingInterceptor *this, unsigned __int16 *const, unsigned int, struct IWbemContext *, struct IWbemObjectSink *)`
- caller_count: `0`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callees

- `0x1400234b8`
- `0x140028cfc`
- `0x1400310f0`
- `0x1400323c0`
- `0x140032b60`
- `0x140048010`

## import_xrefs

- `wbemcomn!GetMemLogObject` at `0x140032503`
- `wbemcomn!GetMemLogObject` at `0x140032503`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x14003250e`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x14003250e`

## pseudocode

```c
__int64 __fastcall CInterceptor_IWbemServices_RestrictingInterceptor::DeleteClassAsync(
        CInterceptor_IWbemServices_RestrictingInterceptor *this,
        unsigned __int16 *const a2,
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
    WPP_SF_Sdqq(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      87,
      (unsigned int)WPP_2ef91c586edc35547bed035b48d4f238_Traceguids,
      (_DWORD)a2,
      a3,
      (char)a4,
      (char)a5);
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
      v10 = (*((__int64 (__fastcall **)(struct IWbemServicesVtbl *, unsigned __int16 *const, _QWORD, struct IWbemContext *))v16.lpVtbl->QueryInterface
             + 11))(
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
      88,
      WPP_2ef91c586edc35547bed035b48d4f238_Traceguids,
      (unsigned int)v10);
  }
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x1400323c0  mov     r11, rsp
0x1400323c3  mov     [r11+10h], rbx
0x1400323c7  mov     [r11+18h], rsi
0x1400323cb  push    rbp
0x1400323cc  push    rdi
0x1400323cd  push    r12
0x1400323cf  push    r14
0x1400323d1  push    r15
0x1400323d3  mov     rbp, rsp
0x1400323d6  sub     rsp, 80h
0x1400323dd  mov     rsi, r9
0x1400323e0  mov     r14d, r8d
0x1400323e3  mov     r15, rdx
0x1400323e6  mov     rdi, rcx
0x1400323e9  mov     rcx, cs:WPP_GLOBAL_Control
0x1400323f0  lea     rax, WPP_GLOBAL_Control
0x1400323f7  mov     r12, [rbp+arg_20]
0x1400323fb  cmp     rcx, rax
0x1400323fe  jz      short loc_140032431
0x140032400  test    byte ptr [rcx+1Ch], 4
0x140032404  jz      short loc_140032431
0x140032406  cmp     byte ptr [rcx+19h], 5
0x14003240a  jb      short loc_140032431
0x14003240c  mov     rcx, [rcx+10h]
0x140032410  mov     edx, 57h ; 'W'
0x140032415  mov     [r11-78h], r12
0x140032419  mov     [r11-80h], r9
0x14003241d  mov     r9, r15
0x140032420  mov     dword ptr [rsp+80h+var_60], r8d
0x140032425  lea     r8, WPP_2ef91c586edc35547bed035b48d4f238_Traceguids
0x14003242c  call    WPP_SF_Sdqq
0x140032431  lock inc dword ptr [rdi+20h]
0x140032435  cmp     dword ptr [rdi+1Ch], 1
0x140032439  jnz     short loc_140032445
0x14003243b  mov     ebx, 80041033h
0x140032440  jmp     loc_1400324FB
0x140032445  lea     rax, [rbp+var_20]
0x140032449  mov     [rbp+var_30], 0
0x140032450  mov     [rsp+80h+var_48], rax; struct IUnknown **
0x140032455  lea     r9, [rbp+var_18]; struct IServerSecurity **
0x140032459  lea     rax, [rbp+arg_0]
0x14003245d  mov     [rbp+var_10], 0
0x140032465  mov     [rsp+80h+var_50], rax; int *
0x14003246a  lea     r8, [rbp+var_10]; struct IUnknown **
0x14003246e  lea     rax, [rbp+var_28]
0x140032472  mov     [rbp+var_18], 0
0x14003247a  mov     [rsp+80h+var_58], rax; struct IWbemServices *
0x14003247f  lea     rdx, [rbp+var_30]; int *
0x140032483  lea     rax, [rbp+var_2C]
0x140032487  mov     [rbp+var_2C], 0
0x14003248e  mov     rcx, rdi; this
0x140032491  mov     [rsp+80h+var_60], rax; int *
0x140032496  mov     [rbp+var_28.lpVtbl], 0
0x14003249e  mov     [rbp+arg_0], 0
0x1400324a5  mov     [rbp+var_20], 0
0x1400324ad  call    ?Begin_IWbemServices@CInterceptor_IWbemServices_RestrictingInterceptor@@AEAAJAEAHAEAPEAUIUnknown@@AEAPEAUIServerSecurity@@0AEAPEAUIWbemServices@@01PEAUIWbemContext@@@Z; CInterceptor_IWbemServices_RestrictingInterceptor::Begin_IWbemServices(int &,IUnknown * &,IServerSecurity * &,int &,IWbemServices * &,int &,IUnknown * &,IWbemContext *)
0x1400324b2  mov     ebx, eax
0x1400324b4  test    eax, eax
0x1400324b6  js      short loc_1400324FB
0x1400324b8  mov     rcx, [rbp+var_28.lpVtbl]
0x1400324bc  mov     r9, rsi
0x1400324bf  mov     r8d, r14d
0x1400324c2  mov     [rsp+80h+var_60], r12; int
0x1400324c7  mov     rdx, r15
0x1400324ca  mov     rax, [rcx]
0x1400324cd  mov     rax, [rax+58h]
0x1400324d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400324d6  mov     r9, [rbp+var_18]; struct IServerSecurity *
0x1400324da  mov     ebx, eax
0x1400324dc  mov     rax, [rbp+var_20]
0x1400324e0  mov     rcx, rdi; this
0x1400324e3  mov     r8, [rbp+var_10]; struct IUnknown *
0x1400324e7  mov     edx, [rbp+var_30]; int
0x1400324ea  mov     [rsp+80h+var_48], rax; struct IUnknown *
0x1400324ef  mov     eax, [rbp+arg_0]
0x1400324f2  mov     dword ptr [rsp+80h+var_50], eax; int
0x1400324f6  call    ?End_IWbemServices@CInterceptor_IWbemServices_RestrictingInterceptor@@AEAAJHPEAUIUnknown@@PEAUIServerSecurity@@HPEAUIWbemServices@@H0@Z; CInterceptor_IWbemServices_RestrictingInterceptor::End_IWbemServices(int,IUnknown *,IServerSecurity *,int,IWbemServices *,int,IUnknown *)
0x1400324fb  lock dec dword ptr [rdi+20h]
0x1400324ff  test    ebx, ebx
0x140032501  jns     short loc_140032514
0x140032503  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x140032509  mov     rcx, rax
0x14003250c  mov     edx, ebx
0x14003250e  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x140032514  mov     rcx, cs:WPP_GLOBAL_Control
0x14003251b  lea     rax, WPP_GLOBAL_Control
0x140032522  cmp     rcx, rax
0x140032525  jz      short loc_14003254B
0x140032527  test    byte ptr [rcx+1Ch], 4
0x14003252b  jz      short loc_14003254B
0x14003252d  cmp     byte ptr [rcx+19h], 2
0x140032531  jb      short loc_14003254B
0x140032533  mov     rcx, [rcx+10h]
0x140032537  lea     r8, WPP_2ef91c586edc35547bed035b48d4f238_Traceguids
0x14003253e  mov     edx, 58h ; 'X'
0x140032543  mov     r9d, ebx
0x140032546  call    WPP_SF_d
0x14003254b  lea     r11, [rsp+80h+var_s0]
0x140032553  mov     eax, ebx
0x140032555  mov     rbx, [r11+38h]
0x140032559  mov     rsi, [r11+40h]
0x14003255d  mov     rsp, r11
0x140032560  pop     r15
0x140032562  pop     r14
0x140032564  pop     r12
0x140032566  pop     rdi
0x140032567  pop     rbp
0x140032568  retn
```
