# CInterceptor_IWbemServices_RestrictingInterceptor::CreateClassEnum(ushort * const,long,IWbemContext *,IEnumWbemClassObject * *)

- ea: `0x1400315d0`
- end: `0x140031767`
- name: `?CreateClassEnum@CInterceptor_IWbemServices_RestrictingInterceptor@@UEAAJQEAGJPEAUIWbemContext@@PEAPEAUIEnumWbemClassObject@@@Z`
- size: `407`
- prototype: `__int64 __fastcall(CInterceptor_IWbemServices_RestrictingInterceptor *this, unsigned __int16 *const, unsigned int, struct IWbemContext *, struct IEnumWbemClassObject **)`
- caller_count: `0`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callees

- `0x1400234b8`
- `0x1400310f0`
- `0x1400315d0`
- `0x140032b60`
- `0x140035c5c`
- `0x140048010`

## import_xrefs

- `wbemcomn!GetMemLogObject` at `0x140031708`
- `wbemcomn!GetMemLogObject` at `0x140031708`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x140031713`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x140031713`

## pseudocode

```c
__int64 __fastcall CInterceptor_IWbemServices_RestrictingInterceptor::CreateClassEnum(
        CInterceptor_IWbemServices_RestrictingInterceptor *this,
        unsigned __int16 *const a2,
        unsigned int a3,
        struct IWbemContext *a4,
        struct IEnumWbemClassObject **a5)
{
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

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_Sdq(*((_QWORD *)WPP_GLOBAL_Control + 2), 89, a3, (_DWORD)a2, a3, (char)a4);
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
      v9 = (*((__int64 (__fastcall **)(struct IWbemServicesVtbl *, unsigned __int16 *const, _QWORD, struct IWbemContext *))v16.lpVtbl->QueryInterface
            + 12))(
             v16.lpVtbl,
             a2,
             a3,
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
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 90, WPP_2ef91c586edc35547bed035b48d4f238_Traceguids, (unsigned int)v9);
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x1400315d0  mov     [rsp-28h+arg_8], rbx
0x1400315d5  mov     [rsp-28h+arg_10], rsi
0x1400315da  push    rbp
0x1400315db  push    rdi
0x1400315dc  push    r13
0x1400315de  push    r14
0x1400315e0  push    r15
0x1400315e2  mov     rbp, rsp
0x1400315e5  sub     rsp, 80h
0x1400315ec  mov     rsi, r9
0x1400315ef  mov     r14d, r8d
0x1400315f2  mov     r15, rdx
0x1400315f5  mov     rdi, rcx
0x1400315f8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400315ff  lea     r13, WPP_GLOBAL_Control
0x140031606  cmp     rcx, r13
0x140031609  jz      short loc_140031632
0x14003160b  test    byte ptr [rcx+1Ch], 4
0x14003160f  jz      short loc_140031632
0x140031611  cmp     byte ptr [rcx+19h], 5
0x140031615  jb      short loc_140031632
0x140031617  mov     rcx, [rcx+10h]
0x14003161b  mov     edx, 59h ; 'Y'
0x140031620  mov     [rsp+80h+var_58], r9
0x140031625  mov     r9, r15
0x140031628  mov     dword ptr [rsp+80h+var_60], r8d
0x14003162d  call    WPP_SF_Sdq
0x140031632  lock inc dword ptr [rdi+20h]
0x140031636  cmp     dword ptr [rdi+1Ch], 1
0x14003163a  jnz     short loc_140031646
0x14003163c  mov     ebx, 80041033h
0x140031641  jmp     loc_140031700
0x140031646  lea     rax, [rbp+var_20]
0x14003164a  mov     [rbp+var_30], 0
0x140031651  mov     [rsp+80h+var_48], rax; struct IUnknown **
0x140031656  lea     r9, [rbp+var_18]; struct IServerSecurity **
0x14003165a  lea     rax, [rbp+arg_0]
0x14003165e  mov     [rbp+var_10], 0
0x140031666  mov     [rsp+80h+var_50], rax; int *
0x14003166b  lea     r8, [rbp+var_10]; struct IUnknown **
0x14003166f  lea     rax, [rbp+var_28]
0x140031673  mov     [rbp+var_18], 0
0x14003167b  mov     [rsp+80h+var_58], rax; struct IWbemServices *
0x140031680  lea     rdx, [rbp+var_30]; int *
0x140031684  lea     rax, [rbp+var_2C]
0x140031688  mov     [rbp+var_2C], 0
0x14003168f  mov     rcx, rdi; this
0x140031692  mov     [rsp+80h+var_60], rax; int *
0x140031697  mov     [rbp+var_28.lpVtbl], 0
0x14003169f  mov     [rbp+arg_0], 0
0x1400316a6  mov     [rbp+var_20], 0
0x1400316ae  call    ?Begin_IWbemServices@CInterceptor_IWbemServices_RestrictingInterceptor@@AEAAJAEAHAEAPEAUIUnknown@@AEAPEAUIServerSecurity@@0AEAPEAUIWbemServices@@01PEAUIWbemContext@@@Z; CInterceptor_IWbemServices_RestrictingInterceptor::Begin_IWbemServices(int &,IUnknown * &,IServerSecurity * &,int &,IWbemServices * &,int &,IUnknown * &,IWbemContext *)
0x1400316b3  mov     ebx, eax
0x1400316b5  test    eax, eax
0x1400316b7  js      short loc_140031700
0x1400316b9  mov     rcx, [rbp+var_28.lpVtbl]
0x1400316bd  mov     r9, rsi
0x1400316c0  mov     rdx, [rbp+arg_20]
0x1400316c4  mov     r8d, r14d
0x1400316c7  mov     [rsp+80h+var_60], rdx; int
0x1400316cc  mov     rdx, r15
0x1400316cf  mov     rax, [rcx]
0x1400316d2  mov     rax, [rax+60h]
0x1400316d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400316db  mov     r9, [rbp+var_18]; struct IServerSecurity *
0x1400316df  mov     ebx, eax
0x1400316e1  mov     rax, [rbp+var_20]
0x1400316e5  mov     rcx, rdi; this
0x1400316e8  mov     r8, [rbp+var_10]; struct IUnknown *
0x1400316ec  mov     edx, [rbp+var_30]; int
0x1400316ef  mov     [rsp+80h+var_48], rax; struct IUnknown *
0x1400316f4  mov     eax, [rbp+arg_0]
0x1400316f7  mov     dword ptr [rsp+80h+var_50], eax; int
0x1400316fb  call    ?End_IWbemServices@CInterceptor_IWbemServices_RestrictingInterceptor@@AEAAJHPEAUIUnknown@@PEAUIServerSecurity@@HPEAUIWbemServices@@H0@Z; CInterceptor_IWbemServices_RestrictingInterceptor::End_IWbemServices(int,IUnknown *,IServerSecurity *,int,IWbemServices *,int,IUnknown *)
0x140031700  lock dec dword ptr [rdi+20h]
0x140031704  test    ebx, ebx
0x140031706  jns     short loc_140031719
0x140031708  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x14003170e  mov     rcx, rax
0x140031711  mov     edx, ebx
0x140031713  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x140031719  mov     rcx, cs:WPP_GLOBAL_Control
0x140031720  cmp     rcx, r13
0x140031723  jz      short loc_140031749
0x140031725  test    byte ptr [rcx+1Ch], 4
0x140031729  jz      short loc_140031749
0x14003172b  cmp     byte ptr [rcx+19h], 2
0x14003172f  jb      short loc_140031749
0x140031731  mov     rcx, [rcx+10h]
0x140031735  lea     r8, WPP_2ef91c586edc35547bed035b48d4f238_Traceguids
0x14003173c  mov     edx, 5Ah ; 'Z'
0x140031741  mov     r9d, ebx
0x140031744  call    WPP_SF_d
0x140031749  lea     r11, [rsp+80h+var_s0]
0x140031751  mov     eax, ebx
0x140031753  mov     rbx, [r11+38h]
0x140031757  mov     rsi, [r11+40h]
0x14003175b  mov     rsp, r11
0x14003175e  pop     r15
0x140031760  pop     r14
0x140031762  pop     r13
0x140031764  pop     rdi
0x140031765  pop     rbp
0x140031766  retn
```
