# KnowledgeServices::CreateFeedClockVectorElement(ulong,unsigned __int64,_SYNC_TIME,uchar,IFeedClockVectorElement * *)

- ea: `0x1800828a0`
- end: `0x1800829ba`
- name: `?CreateFeedClockVectorElement@KnowledgeServices@@SAJK_KU_SYNC_TIME@@EPEAPEAUIFeedClockVectorElement@@@Z`
- size: `282`
- prototype: `__int64 __fastcall(int, __int64, struct _SYNC_TIME, unsigned __int8, struct IFeedClockVectorElement **)`
- caller_count: `1`
- callee_count: `9`
- tags: `service_task`

## callers

- `0x18002b6e0`

## callees

- `0x180005e8c`
- `0x18000a0f0`
- `0x18000c9a0`
- `0x18000ebb0`
- `0x18001cda0`
- `0x18001df64`
- `0x1800828a0`
- `0x1800930f8`
- `0x180094010`

## string_xrefs

- `0x1800828be`: `KnowledgeServices::CreateFeedClockVectorElement`
- `0x18008298e`: `KnowledgeServices::CreateFeedClockVectorElement`

## pseudocode

```c
__int64 __fastcall KnowledgeServices::CreateFeedClockVectorElement(
        int a1,
        __int64 a2,
        struct _SYNC_TIME a3,
        unsigned __int8 a4,
        struct IFeedClockVectorElement **a5)
{
  unsigned int v9; // edi
  ClockVectorElement *v10; // rax
  __int64 v11; // rcx
  int v12; // eax
  struct IFeedClockVectorElement **v13; // r8
  __int64 v15; // [rsp+20h] [rbp-28h] BYREF
  __int16 v16; // [rsp+29h] [rbp-1Fh]
  char v17; // [rsp+2Bh] [rbp-1Dh]
  _SYNC_TIME v18; // [rsp+60h] [rbp+18h] BYREF

  v18 = a3;
  TraceKnowledgeFunctionEnter("KnowledgeServices::CreateFeedClockVectorElement");
  if ( a5 )
  {
    v15 = 0;
    if ( (unsigned int)IsSyncTimeAcceptable(&v18) )
    {
      if ( a4 <= 3u )
      {
        v10 = (ClockVectorElement *)SeAlloc(0x40u);
        if ( v10 )
          v10 = ClockVectorElement::ClockVectorElement(v10);
        v9 = ScopedPtrBase<ReplicaKeyMap,ScopedRefPtr<ReplicaKeyMap>>::Attach(&v15, (__int64)v10);
        if ( !v9 )
        {
          v11 = v15;
          v12 = HIDWORD(v15);
          v13 = a5;
          *(_DWORD *)(v15 + 28) |= 3u;
          *(_DWORD *)(v11 + 36) = v12;
          *(_WORD *)(v11 + 57) = v16;
          *(_BYTE *)(v11 + 59) = v17;
          *(_DWORD *)(v11 + 32) = a1;
          *(_QWORD *)(v11 + 40) = a2;
          *(struct _SYNC_TIME *)(v11 + 48) = a3;
          *(_BYTE *)(v11 + 56) = a4;
          v9 = (**(__int64 (__fastcall ***)(__int64, GUID *, struct IFeedClockVectorElement **))v11)(
                 v11,
                 &IID_IFeedClockVectorElement,
                 v13);
        }
      }
      else
      {
        v9 = -2147024809;
      }
    }
    else
    {
      v9 = -2147217384;
    }
  }
  else
  {
    v9 = -2147467261;
    v15 = 0;
  }
  TraceKnowledgeFunctionLeaveHR("KnowledgeServices::CreateFeedClockVectorElement", v9);
  SharedRefPtr<ICoreFragmentInspector>::~SharedRefPtr<ICoreFragmentInspector>(&v15);
  return v9;
}

```

## disassembly

```asm
0x1800828a0  mov     [rsp+arg_0], rbx
0x1800828a5  mov     [rsp+arg_8], rsi
0x1800828aa  mov     qword ptr [rsp+arg_10.dwDate], r8
0x1800828af  push    rdi
0x1800828b0  push    r14
0x1800828b2  push    r15
0x1800828b4  sub     rsp, 30h
0x1800828b8  mov     r15d, ecx
0x1800828bb  mov     sil, r9b
0x1800828be  lea     rcx, aKnowledgeservi_2; "KnowledgeServices::CreateFeedClockVecto"...
0x1800828c5  mov     rbx, r8
0x1800828c8  mov     r14, rdx
0x1800828cb  call    ?TraceKnowledgeFunctionEnter@@YAXPEBD@Z; TraceKnowledgeFunctionEnter(char const *)
0x1800828d0  cmp     [rsp+48h+arg_20], 0
0x1800828d6  jnz     short loc_1800828EB
0x1800828d8  mov     edi, 80004003h
0x1800828dd  mov     [rsp+48h+var_28], 0
0x1800828e6  jmp     loc_18008298C
0x1800828eb  lea     rcx, [rsp+48h+arg_10]; struct _SYNC_TIME *
0x1800828f0  call    ?IsSyncTimeAcceptable@@YAHAEBU_SYNC_TIME@@@Z; IsSyncTimeAcceptable(_SYNC_TIME const &)
0x1800828f5  mov     [rsp+48h+var_28], 0
0x1800828fe  test    eax, eax
0x180082900  jnz     short loc_18008290C
0x180082902  mov     edi, 80041018h
0x180082907  jmp     loc_18008298C
0x18008290c  cmp     sil, 3
0x180082910  jbe     short loc_180082919
0x180082912  mov     edi, 80070057h
0x180082917  jmp     short loc_18008298C
0x180082919  mov     ecx, 40h ; '@'; unsigned __int64
0x18008291e  call    ?SeAlloc@@YAPEAX_K@Z; SeAlloc(unsigned __int64)
0x180082923  test    rax, rax
0x180082926  jz      short loc_180082930
0x180082928  mov     rcx, rax; this
0x18008292b  call    ??0ClockVectorElement@@QEAA@XZ; ClockVectorElement::ClockVectorElement(void)
0x180082930  mov     rdx, rax
0x180082933  lea     rcx, [rsp+48h+var_28]
0x180082938  call    ?Attach@?$ScopedPtrBase@VReplicaKeyMap@@V?$ScopedRefPtr@VReplicaKeyMap@@@@@@QEAAJPEAVReplicaKeyMap@@@Z; ScopedPtrBase<ReplicaKeyMap,ScopedRefPtr<ReplicaKeyMap>>::Attach(ReplicaKeyMap *)
0x18008293d  mov     edi, eax
0x18008293f  test    eax, eax
0x180082941  jnz     short loc_18008298C
0x180082943  mov     rcx, [rsp+48h+var_28]
0x180082948  lea     rdx, IID_IFeedClockVectorElement
0x18008294f  mov     eax, dword ptr [rsp+48h+var_28+4]
0x180082953  mov     r8, [rsp+48h+arg_20]
0x180082958  or      dword ptr [rcx+1Ch], 3
0x18008295c  mov     [rcx+24h], eax
0x18008295f  movzx   eax, [rsp+48h+var_1F]
0x180082964  mov     [rcx+39h], ax
0x180082968  mov     al, [rsp+48h+var_1D]
0x18008296c  mov     [rcx+3Bh], al
0x18008296f  mov     [rcx+20h], r15d
0x180082973  mov     [rcx+28h], r14
0x180082977  mov     [rcx+30h], rbx
0x18008297b  mov     [rcx+38h], sil
0x18008297f  mov     rax, [rcx]
0x180082982  mov     rax, [rax]
0x180082985  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008298a  mov     edi, eax
0x18008298c  mov     edx, edi; int
0x18008298e  lea     rcx, aKnowledgeservi_2; "KnowledgeServices::CreateFeedClockVecto"...
0x180082995  call    ?TraceKnowledgeFunctionLeaveHR@@YAXPEBDJ@Z; TraceKnowledgeFunctionLeaveHR(char const *,long)
0x18008299a  lea     rcx, [rsp+48h+var_28]
0x18008299f  call    ??1?$SharedRefPtr@UICoreFragmentInspector@@@@QEAA@XZ; SharedRefPtr<ICoreFragmentInspector>::~SharedRefPtr<ICoreFragmentInspector>(void)
0x1800829a4  mov     rbx, [rsp+48h+arg_0]
0x1800829a9  mov     eax, edi
0x1800829ab  mov     rsi, [rsp+48h+arg_8]
0x1800829b0  add     rsp, 30h
0x1800829b4  pop     r15
0x1800829b6  pop     r14
0x1800829b8  pop     rdi
0x1800829b9  retn
```
