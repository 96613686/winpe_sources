# CInterceptor_IWbemServices_RestrictingInterceptor::ExecNotificationQuery(ushort * const,ushort * const,long,IWbemContext *,IEnumWbemClassObject * *)

- ea: `0x140033310`
- end: `0x1400334bf`
- name: `?ExecNotificationQuery@CInterceptor_IWbemServices_RestrictingInterceptor@@UEAAJQEAG0JPEAUIWbemContext@@PEAPEAUIEnumWbemClassObject@@@Z`
- size: `431`
- prototype: `__int64 __usercall@<rax>(CInterceptor_IWbemServices_RestrictingInterceptor *__hidden this@<rcx>, unsigned __int16 *const@<rdx>, unsigned __int16 *const@<r8>, int@<r9d>, struct IWbemContext *, struct IEnumWbemClassObject **)`
- caller_count: `0`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callees

- `0x1400234b8`
- `0x1400310f0`
- `0x140032b60`
- `0x140033310`
- `0x140035b84`
- `0x140048010`

## import_xrefs

- `wbemcomn!GetMemLogObject` at `0x140033459`
- `wbemcomn!GetMemLogObject` at `0x140033459`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x140033464`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x140033464`

## pseudocode

```c
__int64 __fastcall CInterceptor_IWbemServices_RestrictingInterceptor::ExecNotificationQuery(
        CInterceptor_IWbemServices_RestrictingInterceptor *this,
        unsigned __int16 *const a2,
        unsigned __int16 *const a3,
        unsigned int a4,
        struct IWbemContext *a5,
        struct IWbemServices **a6)
{
  int v10; // r12d
  int v11; // ebx
  CMemoryLog *MemLogObject; // rax
  struct IWbemServices **v14; // [rsp+28h] [rbp-58h]
  int v15; // [rsp+50h] [rbp-30h] BYREF
  int v16; // [rsp+54h] [rbp-2Ch] BYREF
  struct IWbemServices *v17; // [rsp+58h] [rbp-28h] BYREF
  struct IUnknown *v18; // [rsp+60h] [rbp-20h] BYREF
  struct IServerSecurity *v19; // [rsp+68h] [rbp-18h] BYREF
  struct IUnknown *v20; // [rsp+70h] [rbp-10h] BYREF
  int v21; // [rsp+B0h] [rbp+30h] BYREF

  v10 = (int)a5;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_SSdq(*((_QWORD *)WPP_GLOBAL_Control + 2), 109, (_DWORD)a3, (_DWORD)a2, (__int64)a3, a4, (char)a5);
  }
  _InterlockedIncrement((volatile signed __int32 *)this + 8);
  if ( *((_DWORD *)this + 7) == 1 )
  {
    v11 = -2147217357;
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
    v11 = CInterceptor_IWbemServices_RestrictingInterceptor::Begin_IWbemServices(
            (struct IUnknown **)this,
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
      v11 = ((__int64 (__fastcall *)(struct IWbemServices *, unsigned __int16 *const, unsigned __int16 *const, _QWORD))v17->lpVtbl->ExecNotificationQuery)(
              v17,
              a2,
              a3,
              a4);
      CInterceptor_IWbemServices_RestrictingInterceptor::End_IWbemServices(
        this,
        v15,
        v20,
        v19,
        v10,
        (struct IWbemServices *)v14,
        v21,
        v18);
    }
  }
  _InterlockedDecrement((volatile signed __int32 *)this + 8);
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
      110,
      WPP_2ef91c586edc35547bed035b48d4f238_Traceguids,
      (unsigned int)v11);
  }
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x140033310  mov     [rsp-28h+arg_8], rbx
0x140033315  mov     [rsp-28h+arg_10], rsi
0x14003331a  push    rbp
0x14003331b  push    rdi
0x14003331c  push    r12
0x14003331e  push    r14
0x140033320  push    r15
0x140033322  mov     rbp, rsp
0x140033325  sub     rsp, 80h
0x14003332c  mov     esi, r9d
0x14003332f  mov     r14, r8
0x140033332  mov     r15, rdx
0x140033335  mov     rdi, rcx
0x140033338  mov     rcx, cs:WPP_GLOBAL_Control
0x14003333f  lea     rax, WPP_GLOBAL_Control
0x140033346  mov     r12, [rbp+arg_20]
0x14003334a  cmp     rcx, rax
0x14003334d  jz      short loc_14003337B
0x14003334f  test    byte ptr [rcx+1Ch], 4
0x140033353  jz      short loc_14003337B
0x140033355  cmp     byte ptr [rcx+19h], 5
0x140033359  jb      short loc_14003337B
0x14003335b  mov     rcx, [rcx+10h]
0x14003335f  mov     edx, 6Dh ; 'm'
0x140033364  mov     [rsp+80h+var_50], r12
0x140033369  mov     dword ptr [rsp+80h+var_58], r9d
0x14003336e  mov     r9, r15
0x140033371  mov     [rsp+80h+var_60], r8
0x140033376  call    WPP_SF_SSdq
0x14003337b  lock inc dword ptr [rdi+20h]
0x14003337f  cmp     dword ptr [rdi+1Ch], 1
0x140033383  jnz     short loc_14003338F
0x140033385  mov     ebx, 80041033h
0x14003338a  jmp     loc_140033451
0x14003338f  lea     rax, [rbp+var_20]
0x140033393  mov     [rbp+var_30], 0
0x14003339a  mov     [rsp+80h+var_48], rax; struct IUnknown **
0x14003339f  lea     r9, [rbp+var_18]; struct IServerSecurity **
0x1400333a3  lea     rax, [rbp+arg_0]
0x1400333a7  mov     [rbp+var_10], 0
0x1400333af  mov     [rsp+80h+var_50], rax; int *
0x1400333b4  lea     r8, [rbp+var_10]; struct IUnknown **
0x1400333b8  lea     rax, [rbp+var_28]
0x1400333bc  mov     [rbp+var_18], 0
0x1400333c4  mov     [rsp+80h+var_58], rax; struct IWbemServices **
0x1400333c9  lea     rdx, [rbp+var_30]; int *
0x1400333cd  lea     rax, [rbp+var_2C]
0x1400333d1  mov     [rbp+var_2C], 0
0x1400333d8  mov     rcx, rdi; this
0x1400333db  mov     [rsp+80h+var_60], rax; int *
0x1400333e0  mov     [rbp+var_28], 0
0x1400333e8  mov     [rbp+arg_0], 0
0x1400333ef  mov     [rbp+var_20], 0
0x1400333f7  call    ?Begin_IWbemServices@CInterceptor_IWbemServices_RestrictingInterceptor@@AEAAJAEAHAEAPEAUIUnknown@@AEAPEAUIServerSecurity@@0AEAPEAUIWbemServices@@01PEAUIWbemContext@@@Z; CInterceptor_IWbemServices_RestrictingInterceptor::Begin_IWbemServices(int &,IUnknown * &,IServerSecurity * &,int &,IWbemServices * &,int &,IUnknown * &,IWbemContext *)
0x1400333fc  mov     ebx, eax
0x1400333fe  test    eax, eax
0x140033400  js      short loc_140033451
0x140033402  mov     rcx, [rbp+var_28]
0x140033406  mov     r9d, esi
0x140033409  mov     rdx, [rbp+arg_28]
0x14003340d  mov     r8, r14
0x140033410  mov     [rsp+80h+var_58], rdx; struct IWbemServices *
0x140033415  mov     rdx, r15
0x140033418  mov     [rsp+80h+var_60], r12; int
0x14003341d  mov     rax, [rcx]
0x140033420  mov     rax, [rax+0B0h]
0x140033427  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003342c  mov     r9, [rbp+var_18]; struct IServerSecurity *
0x140033430  mov     ebx, eax
0x140033432  mov     rax, [rbp+var_20]
0x140033436  mov     rcx, rdi; this
0x140033439  mov     r8, [rbp+var_10]; struct IUnknown *
0x14003343d  mov     edx, [rbp+var_30]; int
0x140033440  mov     [rsp+80h+var_48], rax; struct IUnknown *
0x140033445  mov     eax, [rbp+arg_0]
0x140033448  mov     dword ptr [rsp+80h+var_50], eax; int
0x14003344c  call    ?End_IWbemServices@CInterceptor_IWbemServices_RestrictingInterceptor@@AEAAJHPEAUIUnknown@@PEAUIServerSecurity@@HPEAUIWbemServices@@H0@Z; CInterceptor_IWbemServices_RestrictingInterceptor::End_IWbemServices(int,IUnknown *,IServerSecurity *,int,IWbemServices *,int,IUnknown *)
0x140033451  lock dec dword ptr [rdi+20h]
0x140033455  test    ebx, ebx
0x140033457  jns     short loc_14003346A
0x140033459  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x14003345f  mov     rcx, rax
0x140033462  mov     edx, ebx
0x140033464  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x14003346a  mov     rcx, cs:WPP_GLOBAL_Control
0x140033471  lea     rax, WPP_GLOBAL_Control
0x140033478  cmp     rcx, rax
0x14003347b  jz      short loc_1400334A1
0x14003347d  test    byte ptr [rcx+1Ch], 4
0x140033481  jz      short loc_1400334A1
0x140033483  cmp     byte ptr [rcx+19h], 2
0x140033487  jb      short loc_1400334A1
0x140033489  mov     rcx, [rcx+10h]
0x14003348d  lea     r8, WPP_2ef91c586edc35547bed035b48d4f238_Traceguids
0x140033494  mov     edx, 6Eh ; 'n'
0x140033499  mov     r9d, ebx
0x14003349c  call    WPP_SF_d
0x1400334a1  lea     r11, [rsp+80h+var_s0]
0x1400334a9  mov     eax, ebx
0x1400334ab  mov     rbx, [r11+38h]
0x1400334af  mov     rsi, [r11+40h]
0x1400334b3  mov     rsp, r11
0x1400334b6  pop     r15
0x1400334b8  pop     r14
0x1400334ba  pop     r12
0x1400334bc  pop     rdi
0x1400334bd  pop     rbp
0x1400334be  retn
```
