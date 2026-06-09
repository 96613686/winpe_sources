# KnowledgeServices::CreateFeedClockVector(ulong,IFeedClockVectorElement * *,ulong,int,IFeedClockVector * *)

- ea: `0x180082798`
- end: `0x180082897`
- name: `?CreateFeedClockVector@KnowledgeServices@@SAJKPEAPEAUIFeedClockVectorElement@@KHPEAPEAUIFeedClockVector@@@Z`
- size: `255`
- prototype: `__int64 __fastcall(unsigned int, struct IFeedClockVectorElement **, __int64, __int64, struct IFeedClockVector **)`
- caller_count: `1`
- callee_count: `10`
- tags: `service_task`

## callers

- `0x18002b6b0`

## callees

- `0x18000a0f0`
- `0x18000c9a0`
- `0x18000ebb0`
- `0x1800164e4`
- `0x180017d50`
- `0x180019ed8`
- `0x18001dea0`
- `0x180082798`
- `0x180087bdc`
- `0x180094010`

## string_xrefs

- `0x1800827a9`: `KnowledgeServices::CreateFeedClockVector`
- `0x180082873`: `KnowledgeServices::CreateFeedClockVector`

## pseudocode

```c
__int64 __fastcall KnowledgeServices::CreateFeedClockVector(
        unsigned int a1,
        struct IFeedClockVectorElement **a2,
        __int64 a3,
        __int64 a4,
        struct IFeedClockVector **a5)
{
  unsigned int v7; // ebx
  ClockVector *v8; // rax
  ClockVector *v9; // rdi
  ClockVector *v11; // [rsp+20h] [rbp-48h] BYREF
  _BYTE v12[64]; // [rsp+28h] [rbp-40h] BYREF

  TraceKnowledgeFunctionEnter("KnowledgeServices::CreateFeedClockVector");
  if ( a5 && (a2 || !a1) )
  {
    v11 = 0;
    v8 = (ClockVector *)SeAlloc(0x40u);
    if ( v8 )
      v8 = ClockVector::ClockVector(v8);
    v7 = ScopedPtrBase<SyncKnowledge,ScopedRefPtr<SyncKnowledge>>::Attach((__int64 *)&v11, (__int64)v8);
    if ( !v7 )
    {
      if ( a1 )
      {
        ArraySegment<SyncId>::ArraySegment<SyncId>(v12, a2, a1);
        v9 = v11;
        v7 = ClockVector::InitializeWithExternalDataInstances(v11);
        if ( v7 )
          goto LABEL_13;
      }
      else
      {
        v9 = v11;
        *((_DWORD *)v11 + 9) |= 3u;
      }
      v7 = (**(__int64 (__fastcall ***)(ClockVector *, GUID *, struct IFeedClockVector **))v9)(
             v9,
             &IID_IFeedClockVector,
             a5);
    }
  }
  else
  {
    v7 = -2147467261;
    v11 = 0;
  }
LABEL_13:
  TraceKnowledgeFunctionLeaveHR("KnowledgeServices::CreateFeedClockVector", v7);
  SharedRefPtr<ClockVector>::~SharedRefPtr<ClockVector>((__int64 *)&v11);
  return v7;
}

```

## disassembly

```asm
0x180082798  push    rbx
0x18008279a  push    rsi
0x18008279b  push    rdi
0x18008279c  push    r14
0x18008279e  push    r15
0x1800827a0  sub     rsp, 40h
0x1800827a4  mov     edi, ecx
0x1800827a6  mov     r14d, r9d
0x1800827a9  lea     rcx, aKnowledgeservi_6; "KnowledgeServices::CreateFeedClockVecto"...
0x1800827b0  mov     r15d, r8d
0x1800827b3  mov     rsi, rdx
0x1800827b6  call    ?TraceKnowledgeFunctionEnter@@YAXPEBD@Z; TraceKnowledgeFunctionEnter(char const *)
0x1800827bb  cmp     [rsp+68h+arg_20], 0
0x1800827c4  jnz     short loc_1800827D9
0x1800827c6  mov     ebx, 80004003h
0x1800827cb  mov     [rsp+68h+var_48], 0
0x1800827d4  jmp     loc_180082871
0x1800827d9  test    rsi, rsi
0x1800827dc  jnz     short loc_1800827E2
0x1800827de  test    edi, edi
0x1800827e0  jnz     short loc_1800827C6
0x1800827e2  mov     ecx, 40h ; '@'; unsigned __int64
0x1800827e7  mov     [rsp+68h+var_48], 0
0x1800827f0  call    ?SeAlloc@@YAPEAX_K@Z; SeAlloc(unsigned __int64)
0x1800827f5  test    rax, rax
0x1800827f8  jz      short loc_180082802
0x1800827fa  mov     rcx, rax; this
0x1800827fd  call    ??0ClockVector@@QEAA@XZ; ClockVector::ClockVector(void)
0x180082802  mov     rdx, rax
0x180082805  lea     rcx, [rsp+68h+var_48]
0x18008280a  call    ?Attach@?$ScopedPtrBase@VSyncKnowledge@@V?$ScopedRefPtr@VSyncKnowledge@@@@@@QEAAJPEAVSyncKnowledge@@@Z; ScopedPtrBase<SyncKnowledge,ScopedRefPtr<SyncKnowledge>>::Attach(SyncKnowledge *)
0x18008280f  mov     ebx, eax
0x180082811  test    eax, eax
0x180082813  jnz     short loc_180082871
0x180082815  test    edi, edi
0x180082817  jz      short loc_180082849
0x180082819  mov     r8d, edi
0x18008281c  lea     rcx, [rsp+68h+var_40]
0x180082821  mov     rdx, rsi
0x180082824  call    ??0?$ArraySegment@VSyncId@@@@QEAA@PEBVSyncId@@K@Z; ArraySegment<SyncId>::ArraySegment<SyncId>(SyncId const *,ulong)
0x180082829  mov     rdi, [rsp+68h+var_48]
0x18008282e  lea     r9, [rsp+68h+var_40]
0x180082833  mov     rcx, rdi; this
0x180082836  mov     r8d, r14d
0x180082839  mov     edx, r15d
0x18008283c  call    ?InitializeWithExternalDataInstances@ClockVector@@QEAAJKHAEBV?$ArraySegment@PEAUIFeedClockVectorElement@@@@@Z; ClockVector::InitializeWithExternalDataInstances(ulong,int,ArraySegment<IFeedClockVectorElement *> const &)
0x180082841  mov     ebx, eax
0x180082843  test    eax, eax
0x180082845  jz      short loc_180082852
0x180082847  jmp     short loc_180082871
0x180082849  mov     rdi, [rsp+68h+var_48]
0x18008284e  or      dword ptr [rdi+24h], 3
0x180082852  mov     rax, [rdi]
0x180082855  lea     rdx, IID_IFeedClockVector
0x18008285c  mov     r8, [rsp+68h+arg_20]
0x180082864  mov     rcx, rdi
0x180082867  mov     rax, [rax]
0x18008286a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008286f  mov     ebx, eax
0x180082871  mov     edx, ebx; int
0x180082873  lea     rcx, aKnowledgeservi_6; "KnowledgeServices::CreateFeedClockVecto"...
0x18008287a  call    ?TraceKnowledgeFunctionLeaveHR@@YAXPEBDJ@Z; TraceKnowledgeFunctionLeaveHR(char const *,long)
0x18008287f  lea     rcx, [rsp+68h+var_48]
0x180082884  call    ??1?$SharedRefPtr@VClockVector@@@@QEAA@XZ; SharedRefPtr<ClockVector>::~SharedRefPtr<ClockVector>(void)
0x180082889  mov     eax, ebx
0x18008288b  add     rsp, 40h
0x18008288f  pop     r15
0x180082891  pop     r14
0x180082893  pop     rdi
0x180082894  pop     rsi
0x180082895  pop     rbx
0x180082896  retn
```
