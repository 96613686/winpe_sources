# CInterceptor_IWbemServices_RestrictingInterceptor::DeleteInstanceAsync(ushort * const,long,IWbemContext *,IWbemObjectSink *)

- ea: `0x140032950`
- end: `0x140032afc`
- name: `?DeleteInstanceAsync@CInterceptor_IWbemServices_RestrictingInterceptor@@UEAAJQEAGJPEAUIWbemContext@@PEAUIWbemObjectSink@@@Z`
- size: `428`
- prototype: `__int64 __fastcall(CInterceptor_IWbemServices_RestrictingInterceptor *this, unsigned __int16 *const, unsigned int, struct IWbemContext *, struct IWbemObjectSink *)`
- caller_count: `0`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callees

- `0x1400234b8`
- `0x140028cfc`
- `0x1400310f0`
- `0x140032950`
- `0x140032b60`
- `0x140048010`

## import_xrefs

- `wbemcomn!GetMemLogObject` at `0x140032a96`
- `wbemcomn!GetMemLogObject` at `0x140032a96`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x140032aa1`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x140032aa1`

## pseudocode

```c
__int64 __fastcall CInterceptor_IWbemServices_RestrictingInterceptor::DeleteInstanceAsync(
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
      99,
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
             + 17))(
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
      100,
      WPP_2ef91c586edc35547bed035b48d4f238_Traceguids,
      (unsigned int)v10);
  }
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x140032950  mov     r11, rsp
0x140032953  mov     [r11+10h], rbx
0x140032957  mov     [r11+18h], rsi
0x14003295b  push    rbp
0x14003295c  push    rdi
0x14003295d  push    r12
0x14003295f  push    r14
0x140032961  push    r15
0x140032963  mov     rbp, rsp
0x140032966  sub     rsp, 80h
0x14003296d  mov     rsi, r9
0x140032970  mov     r14d, r8d
0x140032973  mov     r15, rdx
0x140032976  mov     rdi, rcx
0x140032979  mov     rcx, cs:WPP_GLOBAL_Control
0x140032980  lea     rax, WPP_GLOBAL_Control
0x140032987  mov     r12, [rbp+arg_20]
0x14003298b  cmp     rcx, rax
0x14003298e  jz      short loc_1400329C1
0x140032990  test    byte ptr [rcx+1Ch], 4
0x140032994  jz      short loc_1400329C1
0x140032996  cmp     byte ptr [rcx+19h], 5
0x14003299a  jb      short loc_1400329C1
0x14003299c  mov     rcx, [rcx+10h]
0x1400329a0  mov     edx, 63h ; 'c'
0x1400329a5  mov     [r11-78h], r12
0x1400329a9  mov     [r11-80h], r9
0x1400329ad  mov     r9, r15
0x1400329b0  mov     dword ptr [rsp+80h+var_60], r8d
0x1400329b5  lea     r8, WPP_2ef91c586edc35547bed035b48d4f238_Traceguids
0x1400329bc  call    WPP_SF_Sdqq
0x1400329c1  lock inc dword ptr [rdi+20h]
0x1400329c5  cmp     dword ptr [rdi+1Ch], 1
0x1400329c9  jnz     short loc_1400329D5
0x1400329cb  mov     ebx, 80041033h
0x1400329d0  jmp     loc_140032A8E
0x1400329d5  lea     rax, [rbp+var_20]
0x1400329d9  mov     [rbp+var_30], 0
0x1400329e0  mov     [rsp+80h+var_48], rax; struct IUnknown **
0x1400329e5  lea     r9, [rbp+var_18]; struct IServerSecurity **
0x1400329e9  lea     rax, [rbp+arg_0]
0x1400329ed  mov     [rbp+var_10], 0
0x1400329f5  mov     [rsp+80h+var_50], rax; int *
0x1400329fa  lea     r8, [rbp+var_10]; struct IUnknown **
0x1400329fe  lea     rax, [rbp+var_28]
0x140032a02  mov     [rbp+var_18], 0
0x140032a0a  mov     [rsp+80h+var_58], rax; struct IWbemServices *
0x140032a0f  lea     rdx, [rbp+var_30]; int *
0x140032a13  lea     rax, [rbp+var_2C]
0x140032a17  mov     [rbp+var_2C], 0
0x140032a1e  mov     rcx, rdi; this
0x140032a21  mov     [rsp+80h+var_60], rax; int *
0x140032a26  mov     [rbp+var_28.lpVtbl], 0
0x140032a2e  mov     [rbp+arg_0], 0
0x140032a35  mov     [rbp+var_20], 0
0x140032a3d  call    ?Begin_IWbemServices@CInterceptor_IWbemServices_RestrictingInterceptor@@AEAAJAEAHAEAPEAUIUnknown@@AEAPEAUIServerSecurity@@0AEAPEAUIWbemServices@@01PEAUIWbemContext@@@Z; CInterceptor_IWbemServices_RestrictingInterceptor::Begin_IWbemServices(int &,IUnknown * &,IServerSecurity * &,int &,IWbemServices * &,int &,IUnknown * &,IWbemContext *)
0x140032a42  mov     ebx, eax
0x140032a44  test    eax, eax
0x140032a46  js      short loc_140032A8E
0x140032a48  mov     rcx, [rbp+var_28.lpVtbl]
0x140032a4c  mov     r9, rsi
0x140032a4f  mov     r8d, r14d
0x140032a52  mov     [rsp+80h+var_60], r12; int
0x140032a57  mov     rdx, r15
0x140032a5a  mov     rax, [rcx]
0x140032a5d  mov     rax, [rax+88h]
0x140032a64  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140032a69  mov     r9, [rbp+var_18]; struct IServerSecurity *
0x140032a6d  mov     ebx, eax
0x140032a6f  mov     rax, [rbp+var_20]
0x140032a73  mov     rcx, rdi; this
0x140032a76  mov     r8, [rbp+var_10]; struct IUnknown *
0x140032a7a  mov     edx, [rbp+var_30]; int
0x140032a7d  mov     [rsp+80h+var_48], rax; struct IUnknown *
0x140032a82  mov     eax, [rbp+arg_0]
0x140032a85  mov     dword ptr [rsp+80h+var_50], eax; int
0x140032a89  call    ?End_IWbemServices@CInterceptor_IWbemServices_RestrictingInterceptor@@AEAAJHPEAUIUnknown@@PEAUIServerSecurity@@HPEAUIWbemServices@@H0@Z; CInterceptor_IWbemServices_RestrictingInterceptor::End_IWbemServices(int,IUnknown *,IServerSecurity *,int,IWbemServices *,int,IUnknown *)
0x140032a8e  lock dec dword ptr [rdi+20h]
0x140032a92  test    ebx, ebx
0x140032a94  jns     short loc_140032AA7
0x140032a96  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x140032a9c  mov     rcx, rax
0x140032a9f  mov     edx, ebx
0x140032aa1  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x140032aa7  mov     rcx, cs:WPP_GLOBAL_Control
0x140032aae  lea     rax, WPP_GLOBAL_Control
0x140032ab5  cmp     rcx, rax
0x140032ab8  jz      short loc_140032ADE
0x140032aba  test    byte ptr [rcx+1Ch], 4
0x140032abe  jz      short loc_140032ADE
0x140032ac0  cmp     byte ptr [rcx+19h], 2
0x140032ac4  jb      short loc_140032ADE
0x140032ac6  mov     rcx, [rcx+10h]
0x140032aca  lea     r8, WPP_2ef91c586edc35547bed035b48d4f238_Traceguids
0x140032ad1  mov     edx, 64h ; 'd'
0x140032ad6  mov     r9d, ebx
0x140032ad9  call    WPP_SF_d
0x140032ade  lea     r11, [rsp+80h+var_s0]
0x140032ae6  mov     eax, ebx
0x140032ae8  mov     rbx, [r11+38h]
0x140032aec  mov     rsi, [r11+40h]
0x140032af0  mov     rsp, r11
0x140032af3  pop     r15
0x140032af5  pop     r14
0x140032af7  pop     r12
0x140032af9  pop     rdi
0x140032afa  pop     rbp
0x140032afb  retn
```
