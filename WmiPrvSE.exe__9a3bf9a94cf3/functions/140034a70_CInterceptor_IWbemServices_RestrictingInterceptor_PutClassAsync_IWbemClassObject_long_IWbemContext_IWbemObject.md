# CInterceptor_IWbemServices_RestrictingInterceptor::PutClassAsync(IWbemClassObject *,long,IWbemContext *,IWbemObjectSink *)

- ea: `0x140034a70`
- end: `0x140034c19`
- name: `?PutClassAsync@CInterceptor_IWbemServices_RestrictingInterceptor@@UEAAJPEAUIWbemClassObject@@JPEAUIWbemContext@@PEAUIWbemObjectSink@@@Z`
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
- `0x140034a70`
- `0x140048010`

## import_xrefs

- `wbemcomn!GetMemLogObject` at `0x140034bb3`
- `wbemcomn!GetMemLogObject` at `0x140034bb3`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x140034bbe`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x140034bbe`

## pseudocode

```c
__int64 __fastcall CInterceptor_IWbemServices_RestrictingInterceptor::PutClassAsync(
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
      83,
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
             + 9))(
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
      84,
      WPP_2ef91c586edc35547bed035b48d4f238_Traceguids,
      (unsigned int)v10);
  }
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x140034a70  mov     r11, rsp
0x140034a73  mov     [r11+10h], rbx
0x140034a77  mov     [r11+18h], rsi
0x140034a7b  push    rbp
0x140034a7c  push    rdi
0x140034a7d  push    r12
0x140034a7f  push    r14
0x140034a81  push    r15
0x140034a83  mov     rbp, rsp
0x140034a86  sub     rsp, 80h
0x140034a8d  mov     rsi, r9
0x140034a90  mov     r14d, r8d
0x140034a93  mov     r15, rdx
0x140034a96  mov     rdi, rcx
0x140034a99  mov     rcx, cs:WPP_GLOBAL_Control
0x140034aa0  lea     rax, WPP_GLOBAL_Control
0x140034aa7  mov     r12, [rbp+arg_20]
0x140034aab  cmp     rcx, rax
0x140034aae  jz      short loc_140034AE1
0x140034ab0  test    byte ptr [rcx+1Ch], 4
0x140034ab4  jz      short loc_140034AE1
0x140034ab6  cmp     byte ptr [rcx+19h], 5
0x140034aba  jb      short loc_140034AE1
0x140034abc  mov     rcx, [rcx+10h]
0x140034ac0  mov     edx, 53h ; 'S'
0x140034ac5  mov     [r11-78h], r12
0x140034ac9  mov     [r11-80h], r9
0x140034acd  mov     r9, r15
0x140034ad0  mov     dword ptr [rsp+80h+var_60], r8d
0x140034ad5  lea     r8, WPP_2ef91c586edc35547bed035b48d4f238_Traceguids
0x140034adc  call    WPP_SF_qdqq
0x140034ae1  lock inc dword ptr [rdi+20h]
0x140034ae5  cmp     dword ptr [rdi+1Ch], 1
0x140034ae9  jnz     short loc_140034AF5
0x140034aeb  mov     ebx, 80041033h
0x140034af0  jmp     loc_140034BAB
0x140034af5  lea     rax, [rbp+var_20]
0x140034af9  mov     [rbp+var_30], 0
0x140034b00  mov     [rsp+80h+var_48], rax; struct IUnknown **
0x140034b05  lea     r9, [rbp+var_18]; struct IServerSecurity **
0x140034b09  lea     rax, [rbp+arg_0]
0x140034b0d  mov     [rbp+var_10], 0
0x140034b15  mov     [rsp+80h+var_50], rax; int *
0x140034b1a  lea     r8, [rbp+var_10]; struct IUnknown **
0x140034b1e  lea     rax, [rbp+var_28]
0x140034b22  mov     [rbp+var_18], 0
0x140034b2a  mov     [rsp+80h+var_58], rax; struct IWbemServices *
0x140034b2f  lea     rdx, [rbp+var_30]; int *
0x140034b33  lea     rax, [rbp+var_2C]
0x140034b37  mov     [rbp+var_2C], 0
0x140034b3e  mov     rcx, rdi; this
0x140034b41  mov     [rsp+80h+var_60], rax; int *
0x140034b46  mov     [rbp+var_28.lpVtbl], 0
0x140034b4e  mov     [rbp+arg_0], 0
0x140034b55  mov     [rbp+var_20], 0
0x140034b5d  call    ?Begin_IWbemServices@CInterceptor_IWbemServices_RestrictingInterceptor@@AEAAJAEAHAEAPEAUIUnknown@@AEAPEAUIServerSecurity@@0AEAPEAUIWbemServices@@01PEAUIWbemContext@@@Z; CInterceptor_IWbemServices_RestrictingInterceptor::Begin_IWbemServices(int &,IUnknown * &,IServerSecurity * &,int &,IWbemServices * &,int &,IUnknown * &,IWbemContext *)
0x140034b62  mov     ebx, eax
0x140034b64  test    eax, eax
0x140034b66  js      short loc_140034BAB
0x140034b68  mov     rcx, [rbp+var_28.lpVtbl]
0x140034b6c  mov     r9, rsi
0x140034b6f  mov     r8d, r14d
0x140034b72  mov     [rsp+80h+var_60], r12; int
0x140034b77  mov     rdx, r15
0x140034b7a  mov     rax, [rcx]
0x140034b7d  mov     rax, [rax+48h]
0x140034b81  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140034b86  mov     r9, [rbp+var_18]; struct IServerSecurity *
0x140034b8a  mov     ebx, eax
0x140034b8c  mov     rax, [rbp+var_20]
0x140034b90  mov     rcx, rdi; this
0x140034b93  mov     r8, [rbp+var_10]; struct IUnknown *
0x140034b97  mov     edx, [rbp+var_30]; int
0x140034b9a  mov     [rsp+80h+var_48], rax; struct IUnknown *
0x140034b9f  mov     eax, [rbp+arg_0]
0x140034ba2  mov     dword ptr [rsp+80h+var_50], eax; int
0x140034ba6  call    ?End_IWbemServices@CInterceptor_IWbemServices_RestrictingInterceptor@@AEAAJHPEAUIUnknown@@PEAUIServerSecurity@@HPEAUIWbemServices@@H0@Z; CInterceptor_IWbemServices_RestrictingInterceptor::End_IWbemServices(int,IUnknown *,IServerSecurity *,int,IWbemServices *,int,IUnknown *)
0x140034bab  lock dec dword ptr [rdi+20h]
0x140034baf  test    ebx, ebx
0x140034bb1  jns     short loc_140034BC4
0x140034bb3  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x140034bb9  mov     rcx, rax
0x140034bbc  mov     edx, ebx
0x140034bbe  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x140034bc4  mov     rcx, cs:WPP_GLOBAL_Control
0x140034bcb  lea     rax, WPP_GLOBAL_Control
0x140034bd2  cmp     rcx, rax
0x140034bd5  jz      short loc_140034BFB
0x140034bd7  test    byte ptr [rcx+1Ch], 4
0x140034bdb  jz      short loc_140034BFB
0x140034bdd  cmp     byte ptr [rcx+19h], 2
0x140034be1  jb      short loc_140034BFB
0x140034be3  mov     rcx, [rcx+10h]
0x140034be7  lea     r8, WPP_2ef91c586edc35547bed035b48d4f238_Traceguids
0x140034bee  mov     edx, 54h ; 'T'
0x140034bf3  mov     r9d, ebx
0x140034bf6  call    WPP_SF_d
0x140034bfb  lea     r11, [rsp+80h+var_s0]
0x140034c03  mov     eax, ebx
0x140034c05  mov     rbx, [r11+38h]
0x140034c09  mov     rsi, [r11+40h]
0x140034c0d  mov     rsp, r11
0x140034c10  pop     r15
0x140034c12  pop     r14
0x140034c14  pop     r12
0x140034c16  pop     rdi
0x140034c17  pop     rbp
0x140034c18  retn
```
