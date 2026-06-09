# CInterceptor_IWbemServices_RestrictingInterceptor::DeleteClass(ushort * const,long,IWbemContext *,IWbemCallResult * *)

- ea: `0x140032100`
- end: `0x140032297`
- name: `?DeleteClass@CInterceptor_IWbemServices_RestrictingInterceptor@@UEAAJQEAGJPEAUIWbemContext@@PEAPEAUIWbemCallResult@@@Z`
- size: `407`
- prototype: `__int64 __fastcall(CInterceptor_IWbemServices_RestrictingInterceptor *this, unsigned __int16 *const, unsigned int, struct IWbemContext *, struct IWbemCallResult **)`
- caller_count: `0`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callees

- `0x1400234b8`
- `0x1400310f0`
- `0x140032100`
- `0x140032b60`
- `0x140035c5c`
- `0x140048010`

## import_xrefs

- `wbemcomn!GetMemLogObject` at `0x140032238`
- `wbemcomn!GetMemLogObject` at `0x140032238`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x140032243`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x140032243`

## pseudocode

```c
__int64 __fastcall CInterceptor_IWbemServices_RestrictingInterceptor::DeleteClass(
        CInterceptor_IWbemServices_RestrictingInterceptor *this,
        unsigned __int16 *const a2,
        unsigned int a3,
        struct IWbemContext *a4,
        struct IWbemCallResult **a5)
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
    WPP_SF_Sdq(*((_QWORD *)WPP_GLOBAL_Control + 2), 85, a3, (_DWORD)a2, a3, (char)a4);
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
            + 10))(
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
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 86, WPP_2ef91c586edc35547bed035b48d4f238_Traceguids, (unsigned int)v9);
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x140032100  mov     [rsp-28h+arg_8], rbx
0x140032105  mov     [rsp-28h+arg_10], rsi
0x14003210a  push    rbp
0x14003210b  push    rdi
0x14003210c  push    r13
0x14003210e  push    r14
0x140032110  push    r15
0x140032112  mov     rbp, rsp
0x140032115  sub     rsp, 80h
0x14003211c  mov     rsi, r9
0x14003211f  mov     r14d, r8d
0x140032122  mov     r15, rdx
0x140032125  mov     rdi, rcx
0x140032128  mov     rcx, cs:WPP_GLOBAL_Control
0x14003212f  lea     r13, WPP_GLOBAL_Control
0x140032136  cmp     rcx, r13
0x140032139  jz      short loc_140032162
0x14003213b  test    byte ptr [rcx+1Ch], 4
0x14003213f  jz      short loc_140032162
0x140032141  cmp     byte ptr [rcx+19h], 5
0x140032145  jb      short loc_140032162
0x140032147  mov     rcx, [rcx+10h]
0x14003214b  mov     edx, 55h ; 'U'
0x140032150  mov     [rsp+80h+var_58], r9
0x140032155  mov     r9, r15
0x140032158  mov     dword ptr [rsp+80h+var_60], r8d
0x14003215d  call    WPP_SF_Sdq
0x140032162  lock inc dword ptr [rdi+20h]
0x140032166  cmp     dword ptr [rdi+1Ch], 1
0x14003216a  jnz     short loc_140032176
0x14003216c  mov     ebx, 80041033h
0x140032171  jmp     loc_140032230
0x140032176  lea     rax, [rbp+var_20]
0x14003217a  mov     [rbp+var_30], 0
0x140032181  mov     [rsp+80h+var_48], rax; struct IUnknown **
0x140032186  lea     r9, [rbp+var_18]; struct IServerSecurity **
0x14003218a  lea     rax, [rbp+arg_0]
0x14003218e  mov     [rbp+var_10], 0
0x140032196  mov     [rsp+80h+var_50], rax; int *
0x14003219b  lea     r8, [rbp+var_10]; struct IUnknown **
0x14003219f  lea     rax, [rbp+var_28]
0x1400321a3  mov     [rbp+var_18], 0
0x1400321ab  mov     [rsp+80h+var_58], rax; struct IWbemServices *
0x1400321b0  lea     rdx, [rbp+var_30]; int *
0x1400321b4  lea     rax, [rbp+var_2C]
0x1400321b8  mov     [rbp+var_2C], 0
0x1400321bf  mov     rcx, rdi; this
0x1400321c2  mov     [rsp+80h+var_60], rax; int *
0x1400321c7  mov     [rbp+var_28.lpVtbl], 0
0x1400321cf  mov     [rbp+arg_0], 0
0x1400321d6  mov     [rbp+var_20], 0
0x1400321de  call    ?Begin_IWbemServices@CInterceptor_IWbemServices_RestrictingInterceptor@@AEAAJAEAHAEAPEAUIUnknown@@AEAPEAUIServerSecurity@@0AEAPEAUIWbemServices@@01PEAUIWbemContext@@@Z; CInterceptor_IWbemServices_RestrictingInterceptor::Begin_IWbemServices(int &,IUnknown * &,IServerSecurity * &,int &,IWbemServices * &,int &,IUnknown * &,IWbemContext *)
0x1400321e3  mov     ebx, eax
0x1400321e5  test    eax, eax
0x1400321e7  js      short loc_140032230
0x1400321e9  mov     rcx, [rbp+var_28.lpVtbl]
0x1400321ed  mov     r9, rsi
0x1400321f0  mov     rdx, [rbp+arg_20]
0x1400321f4  mov     r8d, r14d
0x1400321f7  mov     [rsp+80h+var_60], rdx; int
0x1400321fc  mov     rdx, r15
0x1400321ff  mov     rax, [rcx]
0x140032202  mov     rax, [rax+50h]
0x140032206  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003220b  mov     r9, [rbp+var_18]; struct IServerSecurity *
0x14003220f  mov     ebx, eax
0x140032211  mov     rax, [rbp+var_20]
0x140032215  mov     rcx, rdi; this
0x140032218  mov     r8, [rbp+var_10]; struct IUnknown *
0x14003221c  mov     edx, [rbp+var_30]; int
0x14003221f  mov     [rsp+80h+var_48], rax; struct IUnknown *
0x140032224  mov     eax, [rbp+arg_0]
0x140032227  mov     dword ptr [rsp+80h+var_50], eax; int
0x14003222b  call    ?End_IWbemServices@CInterceptor_IWbemServices_RestrictingInterceptor@@AEAAJHPEAUIUnknown@@PEAUIServerSecurity@@HPEAUIWbemServices@@H0@Z; CInterceptor_IWbemServices_RestrictingInterceptor::End_IWbemServices(int,IUnknown *,IServerSecurity *,int,IWbemServices *,int,IUnknown *)
0x140032230  lock dec dword ptr [rdi+20h]
0x140032234  test    ebx, ebx
0x140032236  jns     short loc_140032249
0x140032238  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x14003223e  mov     rcx, rax
0x140032241  mov     edx, ebx
0x140032243  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x140032249  mov     rcx, cs:WPP_GLOBAL_Control
0x140032250  cmp     rcx, r13
0x140032253  jz      short loc_140032279
0x140032255  test    byte ptr [rcx+1Ch], 4
0x140032259  jz      short loc_140032279
0x14003225b  cmp     byte ptr [rcx+19h], 2
0x14003225f  jb      short loc_140032279
0x140032261  mov     rcx, [rcx+10h]
0x140032265  lea     r8, WPP_2ef91c586edc35547bed035b48d4f238_Traceguids
0x14003226c  mov     edx, 56h ; 'V'
0x140032271  mov     r9d, ebx
0x140032274  call    WPP_SF_d
0x140032279  lea     r11, [rsp+80h+var_s0]
0x140032281  mov     eax, ebx
0x140032283  mov     rbx, [r11+38h]
0x140032287  mov     rsi, [r11+40h]
0x14003228b  mov     rsp, r11
0x14003228e  pop     r15
0x140032290  pop     r14
0x140032292  pop     r13
0x140032294  pop     rdi
0x140032295  pop     rbp
0x140032296  retn
```
