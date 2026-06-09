# CSMBHelperClass::Repair(tagRepairInfo *,long *,tagREPAIR_STATUS *)

- ea: `0x180008140`
- end: `0x18000820b`
- name: `?Repair@CSMBHelperClass@@UEAAJPEAUtagRepairInfo@@PEAJPEAW4tagREPAIR_STATUS@@@Z`
- size: `203`
- prototype: `__int64 __fastcall(CSMBHelperClass *__hidden this, struct tagRepairInfo *, int *, enum tagREPAIR_STATUS *)`
- caller_count: `0`
- callee_count: `5`
- tags: `installer_update`

## callees

- `0x180008140`
- `0x18000c3c8`
- `0x18000dd04`
- `0x18000f624`
- `0x180012010`

## pseudocode

```c
__int64 __fastcall CSMBHelperClass::Repair(
        CSMBHelperClass *this,
        struct tagRepairInfo *a2,
        int *a3,
        enum tagREPAIR_STATUS *a4)
{
  char *v8; // rsi
  char *v9; // rcx
  __int64 Attribute; // rax
  struct RootCause *RootCause; // rdi
  _QWORD *v12; // rbx
  void **v13; // rax
  __int64 result; // rax
  CSMBHelperClass *v15; // rdi
  _BYTE v16[24]; // [rsp+30h] [rbp-88h] BYREF
  _QWORD v17[5]; // [rsp+48h] [rbp-70h] BYREF
  int v18; // [rsp+70h] [rbp-48h]
  CSMBHelperClass *v19; // [rsp+C0h] [rbp+8h] BYREF

  v19 = this;
  v8 = (char *)this + 208;
  v9 = (char *)this + 208;
  try
  {
    Attribute = AttributeList::getAttribute(v9, v16, L"RootCause", 2);
    RootCause = RootCauseList::getRootCause((CSMBHelperClass *)((char *)this + 184), *(_DWORD *)(Attribute + 8));
    v13 = &NDFRepairExecutionClosure::`vftable';
    v17[0] = &NDFRepairExecutionClosure::`vftable';
    v17[4] = v8;
    v17[1] = a2;
    v17[2] = a3;
    v17[3] = a4;
    v18 = 0;
    v12 = (_QWORD *)*((_QWORD *)RootCause + 3);
    while ( 1 )
    {
      v12 = (_QWORD *)*v12;
      if ( v12 == *((_QWORD **)RootCause + 3)
        || !((unsigned int (__fastcall *)(_QWORD *, _QWORD *))v13[1])(v17, v12 + 2) )
      {
        break;
      }
      v13 = (void **)v17[0];
    }
    NDFRepairExecutionClosure::~NDFRepairExecutionClosure((NDFRepairExecutionClosure *)v17);
    result = 0;
  }
  catch ( enum TestException )
  {
    v15 = v19;
    if ( *((_QWORD *)v19 + 22) )
    {
      v19 = (CSMBHelperClass *)(((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24);
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Format(
        &v19,
        L"CSMBHelperClass::Repair Failed ");
      (*(void (__fastcall **)(_QWORD, __int64, _QWORD, const unsigned __int16 *, CSMBHelperClass *))(**((_QWORD **)v15 + 22) + 24LL))(
        *((_QWORD *)v15 + 22),
        2,
        0,
        L"SMBHelperClass",
        v19);
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)v19 - 2, 0xFFFFFFFF) <= 1 )
        (*(void (__fastcall **)(_QWORD, __int64))(**((_QWORD **)v19 - 3) + 8LL))(
          *((_QWORD *)v19 - 3),
          (__int64)v19 - 24);
    }
    return 2147500037LL;
  }
  Attribute = AttributeList::getAttribute(v9, v16, L"RootCause", 2);
}

```

## disassembly

```asm
0x180008140  mov     [rsp+arg_0], rcx
0x180008145  push    rbx
0x180008146  push    rsi
0x180008147  push    rdi
0x180008148  push    r12
0x18000814a  push    r14
0x18000814c  push    r15
0x18000814e  sub     rsp, 88h
0x180008155  mov     r14, r9
0x180008158  mov     r15, r8
0x18000815b  mov     r12, rdx
0x18000815e  mov     rbx, rcx
0x180008161  lea     rsi, [rcx+0D0h]
0x180008168  mov     r9d, 2
0x18000816e  lea     r8, aRootcause; "RootCause"
0x180008175  lea     rdx, [rsp+0B8h+var_88]
0x18000817a  mov     rcx, rsi
0x18000817d  call    ?getAttribute@AttributeList@@QEAA?AUAttribute@@PEAGW4AttributeType@@@Z; AttributeList::getAttribute(ushort *,AttributeType)
0x180008182  lea     rcx, [rbx+0B8h]; this
0x180008189  mov     edx, [rax+8]; unsigned int
0x18000818c  call    ?getRootCause@RootCauseList@@QEAAPEAVRootCause@@K@Z; RootCauseList::getRootCause(ulong)
0x180008191  mov     rdi, rax
0x180008194  lea     rax, ??_7NDFRepairExecutionClosure@@6B@; const NDFRepairExecutionClosure::`vftable'
0x18000819b  mov     [rsp+0B8h+var_70], rax
0x1800081a0  mov     [rsp+0B8h+var_50], rsi
0x1800081a5  mov     [rsp+0B8h+var_68], r12
0x1800081aa  mov     [rsp+0B8h+var_60], r15
0x1800081af  mov     [rsp+0B8h+var_58], r14
0x1800081b4  mov     [rsp+0B8h+var_48], 0
0x1800081bc  mov     rbx, [rdi+18h]
0x1800081c0  mov     rbx, [rbx]
0x1800081c3  cmp     rbx, [rdi+18h]
0x1800081c7  jz      short loc_1800081E6
0x1800081c9  lea     rdx, [rbx+10h]
0x1800081cd  lea     rcx, [rsp+0B8h+var_70]
0x1800081d2  mov     rax, [rax+8]
0x1800081d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800081db  test    eax, eax
0x1800081dd  jz      short loc_1800081E6
0x1800081df  mov     rax, [rsp+0B8h+var_70]
0x1800081e4  jmp     short loc_1800081C0
0x1800081e6  lea     rcx, [rsp+0B8h+var_70]; this
0x1800081eb  call    ??1NDFRepairExecutionClosure@@UEAA@XZ; NDFRepairExecutionClosure::~NDFRepairExecutionClosure(void)
0x1800081f0  nop
0x1800081f1  xor     eax, eax
0x1800081f3  jmp     short loc_1800081FA
0x1800081f5  mov     eax, 80004005h
0x1800081fa  add     rsp, 88h
0x180008201  pop     r15
0x180008203  pop     r14
0x180008205  pop     r12
0x180008207  pop     rdi
0x180008208  pop     rsi
0x180008209  pop     rbx
0x18000820a  retn
```
