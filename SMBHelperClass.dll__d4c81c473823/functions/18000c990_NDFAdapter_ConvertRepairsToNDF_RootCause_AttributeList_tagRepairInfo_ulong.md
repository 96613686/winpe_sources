# NDFAdapter::ConvertRepairsToNDF(RootCause *,AttributeList *,tagRepairInfo * *,ulong *)

- ea: `0x18000c990`
- end: `0x18000ca38`
- name: `?ConvertRepairsToNDF@NDFAdapter@@SAXPEAVRootCause@@PEAVAttributeList@@PEAPEAUtagRepairInfo@@PEAK@Z`
- size: `168`
- prototype: `void __fastcall(struct RootCause *, struct AttributeList *, struct tagRepairInfo **, unsigned int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x180005830`

## callees

- `0x18000c990`
- `0x18000eddc`
- `0x180012010`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall NDFAdapter::ConvertRepairsToNDF(
        struct RootCause *a1,
        struct AttributeList *a2,
        struct tagRepairInfo **a3,
        unsigned int *a4)
{
  struct tagRepairInfo *TestMemory; // r15
  _QWORD *v9; // rbx
  FreeNDFRepairVisitor *v10; // rax
  int v11; // [rsp+20h] [rbp-58h] BYREF
  int v12; // [rsp+24h] [rbp-54h] BYREF
  __int64 v13; // [rsp+28h] [rbp-50h] BYREF
  _QWORD v14[3]; // [rsp+30h] [rbp-48h] BYREF
  unsigned int v15; // [rsp+48h] [rbp-30h]

  if ( *((_QWORD *)a1 + 4) )
  {
    TestMemory = (struct tagRepairInfo *)AllocateTestMemory(112LL * *((_QWORD *)a1 + 4));
    v14[0] = &NDFRepairConversionClosure::`vftable';
    v14[1] = TestMemory;
    v15 = 0;
    v14[2] = a2;
    v9 = (_QWORD *)*((_QWORD *)a1 + 3);
    try
    {
      do
        v9 = (_QWORD *)*v9;
      while ( v9 != *((_QWORD **)a1 + 3)
           && (*(unsigned int (__fastcall **)(_QWORD *, _QWORD *))(v14[0] + 8LL))(v14, v9 + 2) );
      *a4 = v15;
      *a3 = TestMemory;
    }
    catch ( TestException v12 )
    {
      NDFRepairConversionClosure::numConverted((NDFRepairConversionClosure *)v14);
      v13 = 0;
      v10 = FreeNDFRepairVisitor::FreeNDFRepairVisitor((FreeNDFRepairVisitor *)&v13);
      VisitArray<tagRepairInfo>(TestMemory, v10);
      FreeTestMemory(TestMemory);
      *a4 = 0;
      *a3 = 0;
      v11 = v12;
      throw (TestException *)&v11;
    }
  }
  else
  {
    *a4 = 0;
    *a3 = 0;
  }
}

```

## disassembly

```asm
0x18000c990  mov     [rsp+arg_18], r9
0x18000c995  mov     [rsp+arg_10], r8
0x18000c99a  push    rbx
0x18000c99b  push    rsi
0x18000c99c  push    rdi
0x18000c99d  push    r14
0x18000c99f  push    r15
0x18000c9a1  sub     rsp, 50h
0x18000c9a5  mov     rdi, r9
0x18000c9a8  mov     rsi, r8
0x18000c9ab  mov     rbx, rdx
0x18000c9ae  mov     r14, rcx
0x18000c9b1  cmp     qword ptr [rcx+20h], 0
0x18000c9b6  jnz     short loc_18000C9D2
0x18000c9b8  mov     dword ptr [r9], 0
0x18000c9bf  mov     qword ptr [r8], 0
0x18000c9c6  add     rsp, 50h
0x18000c9ca  pop     r15
0x18000c9cc  pop     r14
0x18000c9ce  pop     rdi
0x18000c9cf  pop     rsi
0x18000c9d0  pop     rbx
0x18000c9d1  retn
0x18000c9d2  imul    rcx, [rcx+20h], 70h ; 'p'; unsigned __int64
0x18000c9d7  call    ?AllocateTestMemory@@YAPEAX_K@Z; AllocateTestMemory(unsigned __int64)
0x18000c9dc  mov     r15, rax
0x18000c9df  mov     [rsp+78h+arg_0], rax
0x18000c9e7  lea     rax, ??_7NDFRepairConversionClosure@@6B@; const NDFRepairConversionClosure::`vftable'
0x18000c9ee  mov     [rsp+78h+var_48], rax
0x18000c9f3  mov     [rsp+78h+var_40], r15
0x18000c9f8  mov     [rsp+78h+var_30], 0
0x18000ca00  mov     [rsp+78h+var_38], rbx
0x18000ca05  mov     rbx, [r14+18h]
0x18000ca09  mov     rbx, [rbx]
0x18000ca0c  cmp     rbx, [r14+18h]
0x18000ca10  jz      short loc_18000CA2D
0x18000ca12  lea     rdx, [rbx+10h]
0x18000ca16  mov     rax, [rsp+78h+var_48]
0x18000ca1b  lea     rcx, [rsp+78h+var_48]
0x18000ca20  mov     rax, [rax+8]
0x18000ca24  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ca29  test    eax, eax
0x18000ca2b  jnz     short loc_18000CA09
0x18000ca2d  mov     eax, [rsp+78h+var_30]
0x18000ca31  mov     [rdi], eax
0x18000ca33  mov     [rsi], r15
0x18000ca36  jmp     short loc_18000C9C6
```
