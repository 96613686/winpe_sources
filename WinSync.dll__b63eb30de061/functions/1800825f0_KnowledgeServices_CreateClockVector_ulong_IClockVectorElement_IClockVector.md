# KnowledgeServices::CreateClockVector(ulong,IClockVectorElement * *,IClockVector * *)

- ea: `0x1800825f0`
- end: `0x1800826d5`
- name: `?CreateClockVector@KnowledgeServices@@SAJKPEAPEAUIClockVectorElement@@PEAPEAUIClockVector@@@Z`
- size: `229`
- prototype: `__int64 __fastcall(unsigned int, struct IClockVectorElement **, struct IClockVector **)`
- caller_count: `1`
- callee_count: `10`
- tags: `service_task`

## callers

- `0x18002b390`

## callees

- `0x18000a0f0`
- `0x18000c9a0`
- `0x18000ebb0`
- `0x1800164e4`
- `0x180017d50`
- `0x180019ed8`
- `0x18001dea0`
- `0x1800825f0`
- `0x180087a50`
- `0x180094010`

## string_xrefs

- `0x1800825fe`: `KnowledgeServices::CreateClockVector`
- `0x1800826b4`: `KnowledgeServices::CreateClockVector`

## pseudocode

```c
__int64 __fastcall KnowledgeServices::CreateClockVector(
        unsigned int a1,
        struct IClockVectorElement **a2,
        struct IClockVector **a3)
{
  unsigned int v6; // ebx
  ClockVector *v7; // rax
  ClockVector *v8; // rdi
  _BYTE v10[56]; // [rsp+20h] [rbp-38h] BYREF
  ClockVector *v11; // [rsp+70h] [rbp+18h] BYREF

  TraceKnowledgeFunctionEnter("KnowledgeServices::CreateClockVector");
  if ( a3 && (a2 || !a1) )
  {
    v11 = 0;
    v7 = (ClockVector *)SeAlloc(0x40u);
    if ( v7 )
      v7 = ClockVector::ClockVector(v7);
    v6 = ScopedPtrBase<SyncKnowledge,ScopedRefPtr<SyncKnowledge>>::Attach((__int64 *)&v11, (__int64)v7);
    if ( !v6 )
    {
      if ( a1 )
      {
        ArraySegment<SyncId>::ArraySegment<SyncId>(v10, a2, a1);
        v8 = v11;
        v6 = ClockVector::InitializeWithExternalDataInstances(v11);
        if ( v6 )
          goto LABEL_13;
      }
      else
      {
        v8 = v11;
        *((_DWORD *)v11 + 9) |= 1u;
      }
      v6 = (**(__int64 (__fastcall ***)(ClockVector *, GUID *, struct IClockVector **))v8)(v8, &IID_IClockVector, a3);
    }
  }
  else
  {
    v6 = -2147467261;
    v11 = 0;
  }
LABEL_13:
  TraceKnowledgeFunctionLeaveHR("KnowledgeServices::CreateClockVector", v6);
  SharedRefPtr<ClockVector>::~SharedRefPtr<ClockVector>((__int64 *)&v11);
  return v6;
}

```

## disassembly

```asm
0x1800825f0  push    rbx
0x1800825f2  push    rbp
0x1800825f3  push    rsi
0x1800825f4  push    rdi
0x1800825f5  sub     rsp, 38h
0x1800825f9  mov     edi, ecx
0x1800825fb  mov     rbp, r8
0x1800825fe  lea     rcx, aKnowledgeservi_3; "KnowledgeServices::CreateClockVector"
0x180082605  mov     rsi, rdx
0x180082608  call    ?TraceKnowledgeFunctionEnter@@YAXPEBD@Z; TraceKnowledgeFunctionEnter(char const *)
0x18008260d  test    rbp, rbp
0x180082610  jnz     short loc_180082625
0x180082612  mov     ebx, 80004003h
0x180082617  mov     [rsp+58h+arg_10], 0
0x180082620  jmp     loc_1800826B2
0x180082625  test    rsi, rsi
0x180082628  jnz     short loc_18008262E
0x18008262a  test    edi, edi
0x18008262c  jnz     short loc_180082612
0x18008262e  mov     ecx, 40h ; '@'; unsigned __int64
0x180082633  mov     [rsp+58h+arg_10], 0
0x18008263c  call    ?SeAlloc@@YAPEAX_K@Z; SeAlloc(unsigned __int64)
0x180082641  test    rax, rax
0x180082644  jz      short loc_18008264E
0x180082646  mov     rcx, rax; this
0x180082649  call    ??0ClockVector@@QEAA@XZ; ClockVector::ClockVector(void)
0x18008264e  mov     rdx, rax
0x180082651  lea     rcx, [rsp+58h+arg_10]
0x180082656  call    ?Attach@?$ScopedPtrBase@VSyncKnowledge@@V?$ScopedRefPtr@VSyncKnowledge@@@@@@QEAAJPEAVSyncKnowledge@@@Z; ScopedPtrBase<SyncKnowledge,ScopedRefPtr<SyncKnowledge>>::Attach(SyncKnowledge *)
0x18008265b  mov     ebx, eax
0x18008265d  test    eax, eax
0x18008265f  jnz     short loc_1800826B2
0x180082661  test    edi, edi
0x180082663  jz      short loc_18008268F
0x180082665  mov     r8d, edi
0x180082668  lea     rcx, [rsp+58h+var_38]
0x18008266d  mov     rdx, rsi
0x180082670  call    ??0?$ArraySegment@VSyncId@@@@QEAA@PEBVSyncId@@K@Z; ArraySegment<SyncId>::ArraySegment<SyncId>(SyncId const *,ulong)
0x180082675  mov     rdi, [rsp+58h+arg_10]
0x18008267a  lea     rdx, [rsp+58h+var_38]
0x18008267f  mov     rcx, rdi; this
0x180082682  call    ?InitializeWithExternalDataInstances@ClockVector@@QEAAJAEBV?$ArraySegment@PEAUIClockVectorElement@@@@@Z; ClockVector::InitializeWithExternalDataInstances(ArraySegment<IClockVectorElement *> const &)
0x180082687  mov     ebx, eax
0x180082689  test    eax, eax
0x18008268b  jz      short loc_180082698
0x18008268d  jmp     short loc_1800826B2
0x18008268f  mov     rdi, [rsp+58h+arg_10]
0x180082694  or      dword ptr [rdi+24h], 1
0x180082698  mov     rax, [rdi]
0x18008269b  lea     rdx, IID_IClockVector
0x1800826a2  mov     r8, rbp
0x1800826a5  mov     rcx, rdi
0x1800826a8  mov     rax, [rax]
0x1800826ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800826b0  mov     ebx, eax
0x1800826b2  mov     edx, ebx; int
0x1800826b4  lea     rcx, aKnowledgeservi_3; "KnowledgeServices::CreateClockVector"
0x1800826bb  call    ?TraceKnowledgeFunctionLeaveHR@@YAXPEBDJ@Z; TraceKnowledgeFunctionLeaveHR(char const *,long)
0x1800826c0  lea     rcx, [rsp+58h+arg_10]
0x1800826c5  call    ??1?$SharedRefPtr@VClockVector@@@@QEAA@XZ; SharedRefPtr<ClockVector>::~SharedRefPtr<ClockVector>(void)
0x1800826ca  mov     eax, ebx
0x1800826cc  add     rsp, 38h
0x1800826d0  pop     rdi
0x1800826d1  pop     rsi
0x1800826d2  pop     rbp
0x1800826d3  pop     rbx
0x1800826d4  retn
```
