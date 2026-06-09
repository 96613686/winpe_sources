# KnowledgeServices::CreateKnowledgeBuilder(IKnowledgeBuilder * *)

- ea: `0x1800829c0`
- end: `0x180082a63`
- name: `?CreateKnowledgeBuilder@KnowledgeServices@@SAJPEAPEAUIKnowledgeBuilder@@@Z`
- size: `163`
- prototype: `__int64 __fastcall(struct IKnowledgeBuilder **)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task`

## callers

- `0x18002bea0`

## callees

- `0x180005e8c`
- `0x18000a0f0`
- `0x18000c9a0`
- `0x18000ebb0`
- `0x18008210c`
- `0x1800829c0`

## string_xrefs

- `0x1800829cd`: `KnowledgeServices::CreateKnowledgeBuilder`
- `0x180082a40`: `KnowledgeServices::CreateKnowledgeBuilder`

## pseudocode

```c
__int64 __fastcall KnowledgeServices::CreateKnowledgeBuilder(struct IKnowledgeBuilder **a1)
{
  unsigned int v2; // ebx
  KnowledgeBuilder *v3; // rax
  struct IKnowledgeBuilder *v4; // rcx
  struct IKnowledgeBuilder *v6; // [rsp+30h] [rbp+8h] BYREF

  TraceKnowledgeFunctionEnter("KnowledgeServices::CreateKnowledgeBuilder");
  v6 = 0;
  v2 = a1 == 0 ? 0x80004003 : 0;
  if ( a1 )
  {
    v3 = (KnowledgeBuilder *)SeAlloc(0x148u);
    if ( v3 )
      v4 = KnowledgeBuilder::KnowledgeBuilder(v3);
    else
      v4 = 0;
    v6 = v4;
    v2 = v4 == 0 ? 0x8007000E : 0;
  }
  else
  {
    v4 = 0;
  }
  if ( !v2 )
  {
    v6 = 0;
    *a1 = v4;
  }
  TraceKnowledgeFunctionLeaveHR("KnowledgeServices::CreateKnowledgeBuilder", v2);
  SharedRefPtr<ICoreFragmentInspector>::~SharedRefPtr<ICoreFragmentInspector>((__int64 *)&v6);
  return v2;
}

```

## disassembly

```asm
0x1800829c0  mov     [rsp+arg_8], rbx
0x1800829c5  push    rdi
0x1800829c6  sub     rsp, 20h
0x1800829ca  mov     rdi, rcx
0x1800829cd  lea     rcx, aKnowledgeservi_0; "KnowledgeServices::CreateKnowledgeBuild"...
0x1800829d4  call    ?TraceKnowledgeFunctionEnter@@YAXPEBD@Z; TraceKnowledgeFunctionEnter(char const *)
0x1800829d9  mov     rax, rdi
0x1800829dc  mov     [rsp+28h+arg_0], 0
0x1800829e5  neg     rax
0x1800829e8  sbb     ebx, ebx
0x1800829ea  not     ebx
0x1800829ec  and     ebx, 80004003h
0x1800829f2  test    rdi, rdi
0x1800829f5  jz      short loc_180082A2C
0x1800829f7  mov     ecx, 148h; unsigned __int64
0x1800829fc  call    ?SeAlloc@@YAPEAX_K@Z; SeAlloc(unsigned __int64)
0x180082a01  test    rax, rax
0x180082a04  jz      short loc_180082A13
0x180082a06  mov     rcx, rax; this
0x180082a09  call    ??0KnowledgeBuilder@@QEAA@XZ; KnowledgeBuilder::KnowledgeBuilder(void)
0x180082a0e  mov     rcx, rax
0x180082a11  jmp     short loc_180082A15
0x180082a13  xor     ecx, ecx
0x180082a15  mov     rax, rcx
0x180082a18  mov     [rsp+28h+arg_0], rcx
0x180082a1d  neg     rax
0x180082a20  sbb     ebx, ebx
0x180082a22  not     ebx
0x180082a24  and     ebx, 8007000Eh
0x180082a2a  jmp     short loc_180082A2E
0x180082a2c  xor     ecx, ecx
0x180082a2e  test    ebx, ebx
0x180082a30  jnz     short loc_180082A3E
0x180082a32  mov     [rsp+28h+arg_0], 0
0x180082a3b  mov     [rdi], rcx
0x180082a3e  mov     edx, ebx; int
0x180082a40  lea     rcx, aKnowledgeservi_0; "KnowledgeServices::CreateKnowledgeBuild"...
0x180082a47  call    ?TraceKnowledgeFunctionLeaveHR@@YAXPEBDJ@Z; TraceKnowledgeFunctionLeaveHR(char const *,long)
0x180082a4c  lea     rcx, [rsp+28h+arg_0]
0x180082a51  call    ??1?$SharedRefPtr@UICoreFragmentInspector@@@@QEAA@XZ; SharedRefPtr<ICoreFragmentInspector>::~SharedRefPtr<ICoreFragmentInspector>(void)
0x180082a56  mov     eax, ebx
0x180082a58  mov     rbx, [rsp+28h+arg_8]
0x180082a5d  add     rsp, 20h
0x180082a61  pop     rdi
0x180082a62  retn
```
