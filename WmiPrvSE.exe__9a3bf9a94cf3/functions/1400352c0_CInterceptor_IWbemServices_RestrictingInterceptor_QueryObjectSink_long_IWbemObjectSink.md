# CInterceptor_IWbemServices_RestrictingInterceptor::QueryObjectSink(long,IWbemObjectSink * *)

- ea: `0x1400352c0`
- end: `0x140035433`
- name: `?QueryObjectSink@CInterceptor_IWbemServices_RestrictingInterceptor@@UEAAJJPEAPEAUIWbemObjectSink@@@Z`
- size: `371`
- prototype: `__int64 __fastcall(CInterceptor_IWbemServices_RestrictingInterceptor *__hidden this, int, struct IWbemObjectSink **)`
- caller_count: `0`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callees

- `0x1400234b8`
- `0x1400310f0`
- `0x140032b60`
- `0x1400352c0`
- `0x140035df8`
- `0x140048010`

## import_xrefs

- `wbemcomn!GetMemLogObject` at `0x1400353d9`
- `wbemcomn!GetMemLogObject` at `0x1400353d9`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1400353e4`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1400353e4`

## pseudocode

```c
__int64 __fastcall CInterceptor_IWbemServices_RestrictingInterceptor::QueryObjectSink(
        CInterceptor_IWbemServices_RestrictingInterceptor *this,
        __int64 a2,
        struct IWbemObjectSink **a3)
{
  unsigned int v4; // r14d
  int v6; // ebx
  CMemoryLog *MemLogObject; // rax
  int v9; // [rsp+20h] [rbp-60h]
  struct IWbemServices **v10; // [rsp+28h] [rbp-58h]
  int v11; // [rsp+50h] [rbp-30h] BYREF
  struct IWbemServices v12; // [rsp+58h] [rbp-28h] BYREF
  struct IUnknown *v13; // [rsp+60h] [rbp-20h] BYREF
  struct IServerSecurity *v14; // [rsp+68h] [rbp-18h] BYREF
  struct IUnknown *v15; // [rsp+70h] [rbp-10h] BYREF
  int v16; // [rsp+B0h] [rbp+30h] BYREF
  int v17; // [rsp+C8h] [rbp+48h] BYREF

  v4 = a2;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_dq(*((_QWORD *)WPP_GLOBAL_Control + 2), a2, a3, (unsigned int)a2, a3);
  }
  _InterlockedIncrement((volatile signed __int32 *)this + 8);
  if ( *((_DWORD *)this + 7) == 1 )
  {
    v6 = -2147217357;
  }
  else
  {
    v17 = 0;
    v15 = 0;
    v14 = 0;
    v11 = 0;
    v12.lpVtbl = 0;
    v16 = 0;
    v13 = 0;
    v6 = CInterceptor_IWbemServices_RestrictingInterceptor::Begin_IWbemServices(
           (struct IUnknown **)this,
           &v17,
           &v15,
           &v14,
           &v11,
           (struct IWbemServices **)&v12,
           &v16,
           &v13);
    if ( v6 >= 0 )
    {
      v6 = (*((__int64 (__fastcall **)(struct IWbemServicesVtbl *, _QWORD, struct IWbemObjectSink **))v12.lpVtbl->QueryInterface
            + 5))(
             v12.lpVtbl,
             v4,
             a3);
      CInterceptor_IWbemServices_RestrictingInterceptor::End_IWbemServices(
        this,
        v17,
        v15,
        v14,
        v9,
        (struct IWbemServices *)v10,
        v16,
        v13);
    }
  }
  _InterlockedDecrement((volatile signed __int32 *)this + 8);
  if ( v6 < 0 )
  {
    MemLogObject = GetMemLogObject();
    CMemoryLog::Write(MemLogObject, v6);
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 76, WPP_2ef91c586edc35547bed035b48d4f238_Traceguids, (unsigned int)v6);
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1400352c0  mov     [rsp-28h+arg_8], rbx
0x1400352c5  push    rbp
0x1400352c6  push    rsi
0x1400352c7  push    rdi
0x1400352c8  push    r12
0x1400352ca  push    r14
0x1400352cc  mov     rbp, rsp
0x1400352cf  sub     rsp, 80h
0x1400352d6  mov     rsi, r8
0x1400352d9  mov     r14d, edx
0x1400352dc  mov     rdi, rcx
0x1400352df  mov     rcx, cs:WPP_GLOBAL_Control
0x1400352e6  lea     r12, WPP_GLOBAL_Control
0x1400352ed  cmp     rcx, r12
0x1400352f0  jz      short loc_14003530F
0x1400352f2  test    byte ptr [rcx+1Ch], 4
0x1400352f6  jz      short loc_14003530F
0x1400352f8  cmp     byte ptr [rcx+19h], 5
0x1400352fc  jb      short loc_14003530F
0x1400352fe  mov     rcx, [rcx+10h]
0x140035302  mov     r9d, edx
0x140035305  mov     [rsp+80h+var_60], r8
0x14003530a  call    WPP_SF_dq
0x14003530f  lock inc dword ptr [rdi+20h]
0x140035313  cmp     dword ptr [rdi+1Ch], 1
0x140035317  jnz     short loc_140035323
0x140035319  mov     ebx, 80041033h
0x14003531e  jmp     loc_1400353D1
0x140035323  lea     rax, [rbp+var_20]
0x140035327  mov     [rbp+arg_18], 0
0x14003532e  mov     [rsp+80h+var_48], rax; struct IUnknown **
0x140035333  lea     r9, [rbp+var_18]; struct IServerSecurity **
0x140035337  lea     rax, [rbp+arg_0]
0x14003533b  mov     [rbp+var_10], 0
0x140035343  mov     [rsp+80h+var_50], rax; int *
0x140035348  lea     r8, [rbp+var_10]; struct IUnknown **
0x14003534c  lea     rax, [rbp+var_28]
0x140035350  mov     [rbp+var_18], 0
0x140035358  mov     [rsp+80h+var_58], rax; struct IWbemServices *
0x14003535d  lea     rdx, [rbp+arg_18]; int *
0x140035361  lea     rax, [rbp+var_30]
0x140035365  mov     [rbp+var_30], 0
0x14003536c  mov     rcx, rdi; this
0x14003536f  mov     [rsp+80h+var_60], rax; int
0x140035374  mov     [rbp+var_28.lpVtbl], 0
0x14003537c  mov     [rbp+arg_0], 0
0x140035383  mov     [rbp+var_20], 0
0x14003538b  call    ?Begin_IWbemServices@CInterceptor_IWbemServices_RestrictingInterceptor@@AEAAJAEAHAEAPEAUIUnknown@@AEAPEAUIServerSecurity@@0AEAPEAUIWbemServices@@01PEAUIWbemContext@@@Z; CInterceptor_IWbemServices_RestrictingInterceptor::Begin_IWbemServices(int &,IUnknown * &,IServerSecurity * &,int &,IWbemServices * &,int &,IUnknown * &,IWbemContext *)
0x140035390  mov     ebx, eax
0x140035392  test    eax, eax
0x140035394  js      short loc_1400353D1
0x140035396  mov     rcx, [rbp+var_28.lpVtbl]
0x14003539a  mov     r8, rsi
0x14003539d  mov     edx, r14d
0x1400353a0  mov     rax, [rcx]
0x1400353a3  mov     rax, [rax+28h]
0x1400353a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400353ac  mov     r9, [rbp+var_18]; struct IServerSecurity *
0x1400353b0  mov     ebx, eax
0x1400353b2  mov     rax, [rbp+var_20]
0x1400353b6  mov     rcx, rdi; this
0x1400353b9  mov     r8, [rbp+var_10]; struct IUnknown *
0x1400353bd  mov     edx, [rbp+arg_18]; int
0x1400353c0  mov     [rsp+80h+var_48], rax; struct IUnknown *
0x1400353c5  mov     eax, [rbp+arg_0]
0x1400353c8  mov     dword ptr [rsp+80h+var_50], eax; int
0x1400353cc  call    ?End_IWbemServices@CInterceptor_IWbemServices_RestrictingInterceptor@@AEAAJHPEAUIUnknown@@PEAUIServerSecurity@@HPEAUIWbemServices@@H0@Z; CInterceptor_IWbemServices_RestrictingInterceptor::End_IWbemServices(int,IUnknown *,IServerSecurity *,int,IWbemServices *,int,IUnknown *)
0x1400353d1  lock dec dword ptr [rdi+20h]
0x1400353d5  test    ebx, ebx
0x1400353d7  jns     short loc_1400353EA
0x1400353d9  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1400353df  mov     rcx, rax
0x1400353e2  mov     edx, ebx
0x1400353e4  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1400353ea  mov     rcx, cs:WPP_GLOBAL_Control
0x1400353f1  cmp     rcx, r12
0x1400353f4  jz      short loc_14003541A
0x1400353f6  test    byte ptr [rcx+1Ch], 4
0x1400353fa  jz      short loc_14003541A
0x1400353fc  cmp     byte ptr [rcx+19h], 2
0x140035400  jb      short loc_14003541A
0x140035402  mov     rcx, [rcx+10h]
0x140035406  lea     r8, WPP_2ef91c586edc35547bed035b48d4f238_Traceguids
0x14003540d  mov     edx, 4Ch ; 'L'
0x140035412  mov     r9d, ebx
0x140035415  call    WPP_SF_d
0x14003541a  mov     eax, ebx
0x14003541c  mov     rbx, [rsp+80h+arg_8]
0x140035424  add     rsp, 80h
0x14003542b  pop     r14
0x14003542d  pop     r12
0x14003542f  pop     rdi
0x140035430  pop     rsi
0x140035431  pop     rbp
0x140035432  retn
```
