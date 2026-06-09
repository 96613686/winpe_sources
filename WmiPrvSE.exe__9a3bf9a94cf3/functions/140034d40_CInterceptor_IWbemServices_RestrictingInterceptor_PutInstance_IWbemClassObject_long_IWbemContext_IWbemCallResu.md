# CInterceptor_IWbemServices_RestrictingInterceptor::PutInstance(IWbemClassObject *,long,IWbemContext *,IWbemCallResult * *)

- ea: `0x140034d40`
- end: `0x140034ed7`
- name: `?PutInstance@CInterceptor_IWbemServices_RestrictingInterceptor@@UEAAJPEAUIWbemClassObject@@JPEAUIWbemContext@@PEAPEAUIWbemCallResult@@@Z`
- size: `407`
- prototype: `__int64 __usercall@<rax>(CInterceptor_IWbemServices_RestrictingInterceptor *__hidden this@<rcx>, struct IWbemClassObject *@<rdx>, int@<r8d>, struct IWbemContext *@<r9>, struct IWbemCallResult **)`
- caller_count: `0`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callees

- `0x1400234b8`
- `0x1400310f0`
- `0x140032b60`
- `0x140034d40`
- `0x140035ec0`
- `0x140048010`

## import_xrefs

- `wbemcomn!GetMemLogObject` at `0x140034e78`
- `wbemcomn!GetMemLogObject` at `0x140034e78`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x140034e83`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x140034e83`

## pseudocode

```c
__int64 __fastcall CInterceptor_IWbemServices_RestrictingInterceptor::PutInstance(
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
    WPP_SF_qdq(*((_QWORD *)WPP_GLOBAL_Control + 2), 93, a3, a2, a3, a4);
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
            + 14))(
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
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 94, WPP_2ef91c586edc35547bed035b48d4f238_Traceguids, (unsigned int)v9);
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x140034d40  mov     [rsp-28h+arg_8], rbx
0x140034d45  mov     [rsp-28h+arg_10], rsi
0x140034d4a  push    rbp
0x140034d4b  push    rdi
0x140034d4c  push    r13
0x140034d4e  push    r14
0x140034d50  push    r15
0x140034d52  mov     rbp, rsp
0x140034d55  sub     rsp, 80h
0x140034d5c  mov     rsi, r9
0x140034d5f  mov     r14d, r8d
0x140034d62  mov     r15, rdx
0x140034d65  mov     rdi, rcx
0x140034d68  mov     rcx, cs:WPP_GLOBAL_Control
0x140034d6f  lea     r13, WPP_GLOBAL_Control
0x140034d76  cmp     rcx, r13
0x140034d79  jz      short loc_140034DA2
0x140034d7b  test    byte ptr [rcx+1Ch], 4
0x140034d7f  jz      short loc_140034DA2
0x140034d81  cmp     byte ptr [rcx+19h], 5
0x140034d85  jb      short loc_140034DA2
0x140034d87  mov     rcx, [rcx+10h]
0x140034d8b  mov     edx, 5Dh ; ']'
0x140034d90  mov     [rsp+80h+var_58], r9
0x140034d95  mov     r9, r15
0x140034d98  mov     dword ptr [rsp+80h+var_60], r8d
0x140034d9d  call    WPP_SF_qdq
0x140034da2  lock inc dword ptr [rdi+20h]
0x140034da6  cmp     dword ptr [rdi+1Ch], 1
0x140034daa  jnz     short loc_140034DB6
0x140034dac  mov     ebx, 80041033h
0x140034db1  jmp     loc_140034E70
0x140034db6  lea     rax, [rbp+var_20]
0x140034dba  mov     [rbp+var_30], 0
0x140034dc1  mov     [rsp+80h+var_48], rax; struct IUnknown **
0x140034dc6  lea     r9, [rbp+var_18]; struct IServerSecurity **
0x140034dca  lea     rax, [rbp+arg_0]
0x140034dce  mov     [rbp+var_10], 0
0x140034dd6  mov     [rsp+80h+var_50], rax; int *
0x140034ddb  lea     r8, [rbp+var_10]; struct IUnknown **
0x140034ddf  lea     rax, [rbp+var_28]
0x140034de3  mov     [rbp+var_18], 0
0x140034deb  mov     [rsp+80h+var_58], rax; struct IWbemServices *
0x140034df0  lea     rdx, [rbp+var_30]; int *
0x140034df4  lea     rax, [rbp+var_2C]
0x140034df8  mov     [rbp+var_2C], 0
0x140034dff  mov     rcx, rdi; this
0x140034e02  mov     [rsp+80h+var_60], rax; int *
0x140034e07  mov     [rbp+var_28.lpVtbl], 0
0x140034e0f  mov     [rbp+arg_0], 0
0x140034e16  mov     [rbp+var_20], 0
0x140034e1e  call    ?Begin_IWbemServices@CInterceptor_IWbemServices_RestrictingInterceptor@@AEAAJAEAHAEAPEAUIUnknown@@AEAPEAUIServerSecurity@@0AEAPEAUIWbemServices@@01PEAUIWbemContext@@@Z; CInterceptor_IWbemServices_RestrictingInterceptor::Begin_IWbemServices(int &,IUnknown * &,IServerSecurity * &,int &,IWbemServices * &,int &,IUnknown * &,IWbemContext *)
0x140034e23  mov     ebx, eax
0x140034e25  test    eax, eax
0x140034e27  js      short loc_140034E70
0x140034e29  mov     rcx, [rbp+var_28.lpVtbl]
0x140034e2d  mov     r9, rsi
0x140034e30  mov     rdx, [rbp+arg_20]
0x140034e34  mov     r8d, r14d
0x140034e37  mov     [rsp+80h+var_60], rdx; int
0x140034e3c  mov     rdx, r15
0x140034e3f  mov     rax, [rcx]
0x140034e42  mov     rax, [rax+70h]
0x140034e46  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140034e4b  mov     r9, [rbp+var_18]; struct IServerSecurity *
0x140034e4f  mov     ebx, eax
0x140034e51  mov     rax, [rbp+var_20]
0x140034e55  mov     rcx, rdi; this
0x140034e58  mov     r8, [rbp+var_10]; struct IUnknown *
0x140034e5c  mov     edx, [rbp+var_30]; int
0x140034e5f  mov     [rsp+80h+var_48], rax; struct IUnknown *
0x140034e64  mov     eax, [rbp+arg_0]
0x140034e67  mov     dword ptr [rsp+80h+var_50], eax; int
0x140034e6b  call    ?End_IWbemServices@CInterceptor_IWbemServices_RestrictingInterceptor@@AEAAJHPEAUIUnknown@@PEAUIServerSecurity@@HPEAUIWbemServices@@H0@Z; CInterceptor_IWbemServices_RestrictingInterceptor::End_IWbemServices(int,IUnknown *,IServerSecurity *,int,IWbemServices *,int,IUnknown *)
0x140034e70  lock dec dword ptr [rdi+20h]
0x140034e74  test    ebx, ebx
0x140034e76  jns     short loc_140034E89
0x140034e78  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x140034e7e  mov     rcx, rax
0x140034e81  mov     edx, ebx
0x140034e83  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x140034e89  mov     rcx, cs:WPP_GLOBAL_Control
0x140034e90  cmp     rcx, r13
0x140034e93  jz      short loc_140034EB9
0x140034e95  test    byte ptr [rcx+1Ch], 4
0x140034e99  jz      short loc_140034EB9
0x140034e9b  cmp     byte ptr [rcx+19h], 2
0x140034e9f  jb      short loc_140034EB9
0x140034ea1  mov     rcx, [rcx+10h]
0x140034ea5  lea     r8, WPP_2ef91c586edc35547bed035b48d4f238_Traceguids
0x140034eac  mov     edx, 5Eh ; '^'
0x140034eb1  mov     r9d, ebx
0x140034eb4  call    WPP_SF_d
0x140034eb9  lea     r11, [rsp+80h+var_s0]
0x140034ec1  mov     eax, ebx
0x140034ec3  mov     rbx, [r11+38h]
0x140034ec7  mov     rsi, [r11+40h]
0x140034ecb  mov     rsp, r11
0x140034ece  pop     r15
0x140034ed0  pop     r14
0x140034ed2  pop     r13
0x140034ed4  pop     rdi
0x140034ed5  pop     rbp
0x140034ed6  retn
```
