# KnowledgeServices::CreateClockVectorElement(ulong,unsigned __int64,IClockVectorElement * *)

- ea: `0x1800826dc`
- end: `0x180082790`
- name: `?CreateClockVectorElement@KnowledgeServices@@SAJK_KPEAPEAUIClockVectorElement@@@Z`
- size: `180`
- prototype: `__int64 __fastcall(int, __int64, struct IClockVectorElement **)`
- caller_count: `1`
- callee_count: `8`
- tags: `service_task`

## callers

- `0x18002b3b0`

## callees

- `0x180005e8c`
- `0x18000a0f0`
- `0x18000c9a0`
- `0x18000ebb0`
- `0x18001cda0`
- `0x18001df64`
- `0x1800826dc`
- `0x180094010`

## string_xrefs

- `0x1800826ea`: `KnowledgeServices::CreateClockVectorElement`
- `0x18008276f`: `KnowledgeServices::CreateClockVectorElement`

## pseudocode

```c
__int64 __fastcall KnowledgeServices::CreateClockVectorElement(int a1, __int64 a2, struct IClockVectorElement **a3)
{
  __int64 v6; // rcx
  unsigned int v7; // ebx
  ClockVectorElement *v8; // rax
  unsigned int v9; // eax
  int v11; // [rsp+24h] [rbp-34h]
  __int64 v12; // [rsp+70h] [rbp+18h] BYREF

  TraceKnowledgeFunctionEnter("KnowledgeServices::CreateClockVectorElement");
  v6 = 0;
  v12 = 0;
  v7 = a3 == 0 ? 0x80004003 : 0;
  if ( a3 )
  {
    v8 = (ClockVectorElement *)SeAlloc(0x40u);
    if ( v8 )
      v8 = ClockVectorElement::ClockVectorElement(v8);
    v9 = ScopedPtrBase<ReplicaKeyMap,ScopedRefPtr<ReplicaKeyMap>>::Attach(&v12, (__int64)v8);
    v6 = v12;
    v7 = v9;
  }
  if ( !v7 )
  {
    *(_DWORD *)(v6 + 28) |= 2u;
    *(_DWORD *)(v6 + 36) = v11;
    *(_DWORD *)(v6 + 32) = a1;
    *(_QWORD *)(v6 + 40) = a2;
    v7 = (**(__int64 (__fastcall ***)(__int64, GUID *, struct IClockVectorElement **))v6)(
           v6,
           &IID_IClockVectorElement,
           a3);
  }
  TraceKnowledgeFunctionLeaveHR("KnowledgeServices::CreateClockVectorElement", v7);
  SharedRefPtr<ICoreFragmentInspector>::~SharedRefPtr<ICoreFragmentInspector>(&v12);
  return v7;
}

```

## disassembly

```asm
0x1800826dc  push    rbx
0x1800826de  push    rbp
0x1800826df  push    rsi
0x1800826e0  push    rdi
0x1800826e1  sub     rsp, 38h
0x1800826e5  mov     ebp, ecx
0x1800826e7  mov     rdi, r8
0x1800826ea  lea     rcx, aKnowledgeservi; "KnowledgeServices::CreateClockVectorEle"...
0x1800826f1  mov     rsi, rdx
0x1800826f4  call    ?TraceKnowledgeFunctionEnter@@YAXPEBD@Z; TraceKnowledgeFunctionEnter(char const *)
0x1800826f9  mov     rax, rdi
0x1800826fc  neg     rax
0x1800826ff  sbb     ebx, ebx
0x180082701  xor     ecx, ecx
0x180082703  not     ebx
0x180082705  mov     [rsp+58h+arg_10], rcx
0x18008270a  and     ebx, 80004003h
0x180082710  test    rdi, rdi
0x180082713  jz      short loc_180082740
0x180082715  mov     ecx, 40h ; '@'; unsigned __int64
0x18008271a  call    ?SeAlloc@@YAPEAX_K@Z; SeAlloc(unsigned __int64)
0x18008271f  test    rax, rax
0x180082722  jz      short loc_18008272C
0x180082724  mov     rcx, rax; this
0x180082727  call    ??0ClockVectorElement@@QEAA@XZ; ClockVectorElement::ClockVectorElement(void)
0x18008272c  mov     rdx, rax
0x18008272f  lea     rcx, [rsp+58h+arg_10]
0x180082734  call    ?Attach@?$ScopedPtrBase@VReplicaKeyMap@@V?$ScopedRefPtr@VReplicaKeyMap@@@@@@QEAAJPEAVReplicaKeyMap@@@Z; ScopedPtrBase<ReplicaKeyMap,ScopedRefPtr<ReplicaKeyMap>>::Attach(ReplicaKeyMap *)
0x180082739  mov     rcx, [rsp+58h+arg_10]
0x18008273e  mov     ebx, eax
0x180082740  test    ebx, ebx
0x180082742  jnz     short loc_18008276D
0x180082744  mov     eax, [rsp+58h+var_34]
0x180082748  lea     rdx, IID_IClockVectorElement
0x18008274f  or      dword ptr [rcx+1Ch], 2
0x180082753  mov     r8, rdi
0x180082756  mov     [rcx+24h], eax
0x180082759  mov     [rcx+20h], ebp
0x18008275c  mov     [rcx+28h], rsi
0x180082760  mov     rax, [rcx]
0x180082763  mov     rax, [rax]
0x180082766  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008276b  mov     ebx, eax
0x18008276d  mov     edx, ebx; int
0x18008276f  lea     rcx, aKnowledgeservi; "KnowledgeServices::CreateClockVectorEle"...
0x180082776  call    ?TraceKnowledgeFunctionLeaveHR@@YAXPEBDJ@Z; TraceKnowledgeFunctionLeaveHR(char const *,long)
0x18008277b  lea     rcx, [rsp+58h+arg_10]
0x180082780  call    ??1?$SharedRefPtr@UICoreFragmentInspector@@@@QEAA@XZ; SharedRefPtr<ICoreFragmentInspector>::~SharedRefPtr<ICoreFragmentInspector>(void)
0x180082785  mov     eax, ebx
0x180082787  add     rsp, 38h
0x18008278b  pop     rdi
0x18008278c  pop     rsi
0x18008278d  pop     rbp
0x18008278e  pop     rbx
0x18008278f  retn
```
