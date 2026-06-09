# CInterceptor_IWbemServices_RestrictingInterceptor::CreateInstanceEnumAsync(ushort * const,long,IWbemContext *,IWbemObjectSink *)

- ea: `0x140031e20`
- end: `0x140031fcc`
- name: `?CreateInstanceEnumAsync@CInterceptor_IWbemServices_RestrictingInterceptor@@UEAAJQEAGJPEAUIWbemContext@@PEAUIWbemObjectSink@@@Z`
- size: `428`
- prototype: `__int64 __fastcall(CInterceptor_IWbemServices_RestrictingInterceptor *this, unsigned __int16 *const, unsigned int, struct IWbemContext *, struct IWbemObjectSink *)`
- caller_count: `0`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callees

- `0x1400234b8`
- `0x140028cfc`
- `0x1400310f0`
- `0x140031e20`
- `0x140032b60`
- `0x140048010`

## import_xrefs

- `wbemcomn!GetMemLogObject` at `0x140031f66`
- `wbemcomn!GetMemLogObject` at `0x140031f66`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x140031f71`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x140031f71`

## pseudocode

```c
__int64 __fastcall CInterceptor_IWbemServices_RestrictingInterceptor::CreateInstanceEnumAsync(
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
      103,
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
             + 19))(
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
      104,
      WPP_2ef91c586edc35547bed035b48d4f238_Traceguids,
      (unsigned int)v10);
  }
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x140031e20  mov     r11, rsp
0x140031e23  mov     [r11+10h], rbx
0x140031e27  mov     [r11+18h], rsi
0x140031e2b  push    rbp
0x140031e2c  push    rdi
0x140031e2d  push    r12
0x140031e2f  push    r14
0x140031e31  push    r15
0x140031e33  mov     rbp, rsp
0x140031e36  sub     rsp, 80h
0x140031e3d  mov     rsi, r9
0x140031e40  mov     r14d, r8d
0x140031e43  mov     r15, rdx
0x140031e46  mov     rdi, rcx
0x140031e49  mov     rcx, cs:WPP_GLOBAL_Control
0x140031e50  lea     rax, WPP_GLOBAL_Control
0x140031e57  mov     r12, [rbp+arg_20]
0x140031e5b  cmp     rcx, rax
0x140031e5e  jz      short loc_140031E91
0x140031e60  test    byte ptr [rcx+1Ch], 4
0x140031e64  jz      short loc_140031E91
0x140031e66  cmp     byte ptr [rcx+19h], 5
0x140031e6a  jb      short loc_140031E91
0x140031e6c  mov     rcx, [rcx+10h]
0x140031e70  mov     edx, 67h ; 'g'
0x140031e75  mov     [r11-78h], r12
0x140031e79  mov     [r11-80h], r9
0x140031e7d  mov     r9, r15
0x140031e80  mov     dword ptr [rsp+80h+var_60], r8d
0x140031e85  lea     r8, WPP_2ef91c586edc35547bed035b48d4f238_Traceguids
0x140031e8c  call    WPP_SF_Sdqq
0x140031e91  lock inc dword ptr [rdi+20h]
0x140031e95  cmp     dword ptr [rdi+1Ch], 1
0x140031e99  jnz     short loc_140031EA5
0x140031e9b  mov     ebx, 80041033h
0x140031ea0  jmp     loc_140031F5E
0x140031ea5  lea     rax, [rbp+var_20]
0x140031ea9  mov     [rbp+var_30], 0
0x140031eb0  mov     [rsp+80h+var_48], rax; struct IUnknown **
0x140031eb5  lea     r9, [rbp+var_18]; struct IServerSecurity **
0x140031eb9  lea     rax, [rbp+arg_0]
0x140031ebd  mov     [rbp+var_10], 0
0x140031ec5  mov     [rsp+80h+var_50], rax; int *
0x140031eca  lea     r8, [rbp+var_10]; struct IUnknown **
0x140031ece  lea     rax, [rbp+var_28]
0x140031ed2  mov     [rbp+var_18], 0
0x140031eda  mov     [rsp+80h+var_58], rax; struct IWbemServices *
0x140031edf  lea     rdx, [rbp+var_30]; int *
0x140031ee3  lea     rax, [rbp+var_2C]
0x140031ee7  mov     [rbp+var_2C], 0
0x140031eee  mov     rcx, rdi; this
0x140031ef1  mov     [rsp+80h+var_60], rax; int *
0x140031ef6  mov     [rbp+var_28.lpVtbl], 0
0x140031efe  mov     [rbp+arg_0], 0
0x140031f05  mov     [rbp+var_20], 0
0x140031f0d  call    ?Begin_IWbemServices@CInterceptor_IWbemServices_RestrictingInterceptor@@AEAAJAEAHAEAPEAUIUnknown@@AEAPEAUIServerSecurity@@0AEAPEAUIWbemServices@@01PEAUIWbemContext@@@Z; CInterceptor_IWbemServices_RestrictingInterceptor::Begin_IWbemServices(int &,IUnknown * &,IServerSecurity * &,int &,IWbemServices * &,int &,IUnknown * &,IWbemContext *)
0x140031f12  mov     ebx, eax
0x140031f14  test    eax, eax
0x140031f16  js      short loc_140031F5E
0x140031f18  mov     rcx, [rbp+var_28.lpVtbl]
0x140031f1c  mov     r9, rsi
0x140031f1f  mov     r8d, r14d
0x140031f22  mov     [rsp+80h+var_60], r12; int
0x140031f27  mov     rdx, r15
0x140031f2a  mov     rax, [rcx]
0x140031f2d  mov     rax, [rax+98h]
0x140031f34  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140031f39  mov     r9, [rbp+var_18]; struct IServerSecurity *
0x140031f3d  mov     ebx, eax
0x140031f3f  mov     rax, [rbp+var_20]
0x140031f43  mov     rcx, rdi; this
0x140031f46  mov     r8, [rbp+var_10]; struct IUnknown *
0x140031f4a  mov     edx, [rbp+var_30]; int
0x140031f4d  mov     [rsp+80h+var_48], rax; struct IUnknown *
0x140031f52  mov     eax, [rbp+arg_0]
0x140031f55  mov     dword ptr [rsp+80h+var_50], eax; int
0x140031f59  call    ?End_IWbemServices@CInterceptor_IWbemServices_RestrictingInterceptor@@AEAAJHPEAUIUnknown@@PEAUIServerSecurity@@HPEAUIWbemServices@@H0@Z; CInterceptor_IWbemServices_RestrictingInterceptor::End_IWbemServices(int,IUnknown *,IServerSecurity *,int,IWbemServices *,int,IUnknown *)
0x140031f5e  lock dec dword ptr [rdi+20h]
0x140031f62  test    ebx, ebx
0x140031f64  jns     short loc_140031F77
0x140031f66  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x140031f6c  mov     rcx, rax
0x140031f6f  mov     edx, ebx
0x140031f71  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x140031f77  mov     rcx, cs:WPP_GLOBAL_Control
0x140031f7e  lea     rax, WPP_GLOBAL_Control
0x140031f85  cmp     rcx, rax
0x140031f88  jz      short loc_140031FAE
0x140031f8a  test    byte ptr [rcx+1Ch], 4
0x140031f8e  jz      short loc_140031FAE
0x140031f90  cmp     byte ptr [rcx+19h], 2
0x140031f94  jb      short loc_140031FAE
0x140031f96  mov     rcx, [rcx+10h]
0x140031f9a  lea     r8, WPP_2ef91c586edc35547bed035b48d4f238_Traceguids
0x140031fa1  mov     edx, 68h ; 'h'
0x140031fa6  mov     r9d, ebx
0x140031fa9  call    WPP_SF_d
0x140031fae  lea     r11, [rsp+80h+var_s0]
0x140031fb6  mov     eax, ebx
0x140031fb8  mov     rbx, [r11+38h]
0x140031fbc  mov     rsi, [r11+40h]
0x140031fc0  mov     rsp, r11
0x140031fc3  pop     r15
0x140031fc5  pop     r14
0x140031fc7  pop     r12
0x140031fc9  pop     rdi
0x140031fca  pop     rbp
0x140031fcb  retn
```
