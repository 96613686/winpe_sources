# CChangeApplier::SaveKnowledgeCompleteHandler(void)

- ea: `0x180045df0`
- end: `0x180045f56`
- name: `?SaveKnowledgeCompleteHandler@CChangeApplier@@AEAAJXZ`
- size: `358`
- prototype: `__int64 __fastcall(CChangeApplier *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180039f60`

## callees

- `0x18001a038`
- `0x18001ae20`
- `0x180035724`
- `0x180036898`
- `0x180045df0`
- `0x180046160`
- `0x1800650bc`
- `0x180094010`

## string_xrefs

- `0x180045e20`: `CChangeApplier::SaveKnowledgeCompleteHandler`
- `0x180045f14`: `CChangeApplier::SaveKnowledgeCompleteHandler`

## pseudocode

```c
__int64 __fastcall CChangeApplier::SaveKnowledgeCompleteHandler(CChangeApplier *this)
{
  int v2; // eax
  int WorkEstimateForBatch; // ebx
  CSyncChangeBatchWrapper *v4; // rcx
  unsigned int v5; // r9d
  __int64 v6; // rcx
  int v7; // edx
  unsigned int v9; // [rsp+60h] [rbp+8h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      180,
      &WPP_4afb552cd4e9336475e7a5400d2892b5_Traceguids,
      "CChangeApplier::SaveKnowledgeCompleteHandler");
  }
  v2 = CChangeApplier::ChangeState((__int64)this, 16);
  WorkEstimateForBatch = v2;
  if ( *((_QWORD *)this + 50) )
  {
    v4 = (CSyncChangeBatchWrapper *)*((_QWORD *)this + 62);
    v9 = 0;
    WorkEstimateForBatch = CSyncChangeBatchWrapper::GetWorkEstimateForBatch(v4, &v9);
    if ( WorkEstimateForBatch < 0 )
      goto LABEL_14;
    v5 = v9;
    if ( v9 > *((_DWORD *)this + 119) )
    {
      v5 = *((_DWORD *)this + 119);
      v9 = v5;
    }
    v6 = *((_QWORD *)this + 50);
    *((_DWORD *)this + 118) = v5;
    (*(void (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v6 + 24LL))(v6, 1, 2);
  }
  else if ( v2 < 0 )
  {
    goto LABEL_14;
  }
  v7 = 20;
  if ( !*((_DWORD *)this + 170) )
    v7 = 17;
  WorkEstimateForBatch = CChangeApplier::ChangeState((__int64)this, v7);
LABEL_14:
  if ( WorkEstimateForBatch == -2147467260 )
  {
    if ( *((_DWORD *)this + 170) )
    {
      WorkEstimateForBatch = 0;
      goto LABEL_17;
    }
LABEL_25:
    WorkEstimateForBatch = CChangeApplier::SetError(this, *((struct ISyncCallback **)this + 50), WorkEstimateForBatch);
    goto LABEL_19;
  }
  if ( WorkEstimateForBatch < 0 )
    goto LABEL_25;
LABEL_17:
  if ( (unsigned int)CChangeApplier::CheckForSessionCompletion(this) )
    WorkEstimateForBatch = 1;
LABEL_19:
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_sD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      181,
      (unsigned int)&WPP_4afb552cd4e9336475e7a5400d2892b5_Traceguids,
      (unsigned int)"CChangeApplier::SaveKnowledgeCompleteHandler",
      WorkEstimateForBatch);
  }
  return (unsigned int)WorkEstimateForBatch;
}

```

## disassembly

```asm
0x180045df0  push    rbx
0x180045df2  push    rbp
0x180045df3  push    rdi
0x180045df4  push    r14
0x180045df6  sub     rsp, 38h
0x180045dfa  mov     rdi, rcx
0x180045dfd  mov     rcx, cs:WPP_GLOBAL_Control
0x180045e04  lea     rbp, WPP_GLOBAL_Control
0x180045e0b  cmp     rcx, rbp
0x180045e0e  jz      short loc_180045E38
0x180045e10  test    byte ptr [rcx+1Ch], 8
0x180045e14  jz      short loc_180045E38
0x180045e16  cmp     byte ptr [rcx+19h], 5
0x180045e1a  jb      short loc_180045E38
0x180045e1c  mov     rcx, [rcx+10h]
0x180045e20  lea     r9, aCchangeapplier_90; "CChangeApplier::SaveKnowledgeCompleteHa"...
0x180045e27  mov     edx, 0B4h
0x180045e2c  lea     r8, WPP_4afb552cd4e9336475e7a5400d2892b5_Traceguids
0x180045e33  call    WPP_SF_s
0x180045e38  mov     edx, 10h
0x180045e3d  mov     rcx, rdi
0x180045e40  call    ?ChangeState@CChangeApplier@@AEAAJW4ChangeApplierState@@@Z; CChangeApplier::ChangeState(ChangeApplierState)
0x180045e45  cmp     qword ptr [rdi+190h], 0
0x180045e4d  mov     ebx, eax
0x180045e4f  mov     r14d, 1
0x180045e55  jz      short loc_180045EB6
0x180045e57  mov     rcx, [rdi+1F0h]; this
0x180045e5e  lea     rdx, [rsp+58h+arg_0]; unsigned int *
0x180045e63  mov     [rsp+58h+arg_0], 0
0x180045e6b  call    ?GetWorkEstimateForBatch@CSyncChangeBatchWrapper@@QEAAJPEAK@Z; CSyncChangeBatchWrapper::GetWorkEstimateForBatch(ulong *)
0x180045e70  mov     ebx, eax
0x180045e72  test    eax, eax
0x180045e74  js      short loc_180045ED7
0x180045e76  mov     edx, [rdi+1DCh]
0x180045e7c  mov     r9d, [rsp+58h+arg_0]
0x180045e81  cmp     r9d, edx
0x180045e84  jbe     short loc_180045E8D
0x180045e86  mov     r9d, edx
0x180045e89  mov     [rsp+58h+arg_0], edx
0x180045e8d  mov     rcx, [rdi+190h]
0x180045e94  mov     r8d, 2
0x180045e9a  mov     [rdi+1D8h], r9d
0x180045ea1  mov     [rsp+58h+var_38], edx
0x180045ea5  mov     edx, r14d
0x180045ea8  mov     rax, [rcx]
0x180045eab  mov     rax, [rax+18h]
0x180045eaf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045eb4  jmp     short loc_180045EBA
0x180045eb6  test    eax, eax
0x180045eb8  js      short loc_180045ED7
0x180045eba  cmp     dword ptr [rdi+2A8h], 0
0x180045ec1  mov     rcx, rdi
0x180045ec4  mov     edx, 14h
0x180045ec9  jnz     short loc_180045ED0
0x180045ecb  mov     edx, 11h
0x180045ed0  call    ?ChangeState@CChangeApplier@@AEAAJW4ChangeApplierState@@@Z; CChangeApplier::ChangeState(ChangeApplierState)
0x180045ed5  mov     ebx, eax
0x180045ed7  cmp     ebx, 80004004h
0x180045edd  jnz     short loc_180045F3C
0x180045edf  cmp     dword ptr [rdi+2A8h], 0
0x180045ee6  jz      short loc_180045F40
0x180045ee8  xor     ebx, ebx
0x180045eea  mov     rcx, rdi; this
0x180045eed  call    ?CheckForSessionCompletion@CChangeApplier@@AEAAHXZ; CChangeApplier::CheckForSessionCompletion(void)
0x180045ef2  test    eax, eax
0x180045ef4  cmovnz  ebx, r14d
0x180045ef8  mov     rcx, cs:WPP_GLOBAL_Control
0x180045eff  cmp     rcx, rbp
0x180045f02  jz      short loc_180045F30
0x180045f04  test    byte ptr [rcx+1Ch], 8
0x180045f08  jz      short loc_180045F30
0x180045f0a  cmp     byte ptr [rcx+19h], 5
0x180045f0e  jb      short loc_180045F30
0x180045f10  mov     rcx, [rcx+10h]
0x180045f14  lea     r9, aCchangeapplier_90; "CChangeApplier::SaveKnowledgeCompleteHa"...
0x180045f1b  mov     edx, 0B5h
0x180045f20  mov     [rsp+58h+var_38], ebx
0x180045f24  lea     r8, WPP_4afb552cd4e9336475e7a5400d2892b5_Traceguids
0x180045f2b  call    WPP_SF_sD
0x180045f30  mov     eax, ebx
0x180045f32  add     rsp, 38h
0x180045f36  pop     r14
0x180045f38  pop     rdi
0x180045f39  pop     rbp
0x180045f3a  pop     rbx
0x180045f3b  retn
0x180045f3c  test    ebx, ebx
0x180045f3e  jns     short loc_180045EEA
0x180045f40  mov     rdx, [rdi+190h]; struct ISyncCallback *
0x180045f47  mov     r8d, ebx; int
0x180045f4a  mov     rcx, rdi; this
0x180045f4d  call    ?SetError@CChangeApplier@@AEAAJPEAUISyncCallback@@J@Z; CChangeApplier::SetError(ISyncCallback *,long)
0x180045f52  mov     ebx, eax
0x180045f54  jmp     short loc_180045EF8
```
