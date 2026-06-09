# RawConfigTree::TryInitializeRootAndDescendents(ConfigRootNode *)

- ea: `0x180011910`
- end: `0x180011a5b`
- name: `?TryInitializeRootAndDescendents@RawConfigTree@@UEAA_NPEAVConfigRootNode@@@Z`
- size: `331`
- prototype: `bool __fastcall(RawConfigTree *__hidden this, struct ConfigRootNode *)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1800021a4`
- `0x18000acd0`
- `0x180011910`
- `0x180012ea8`
- `0x180012f3c`
- `0x180014010`

## import_xrefs

- `OLEAUT32!__imp_VariantClear` at `0x1800119ff`
- `OLEAUT32!__imp_VariantClear` at `0x1800119ff`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
bool __fastcall RawConfigTree::TryInitializeRootAndDescendents(RawConfigTree *this, struct ConfigRootNode *a2)
{
  __int64 v4; // rcx
  int v6; // eax
  unsigned int i; // ebx
  __int64 v8; // rcx
  int v9; // eax
  int v10; // eax
  __int64 v11; // rax
  __int64 v12; // [rsp+20h] [rbp-40h] BYREF
  VARIANTARG pvarg; // [rsp+28h] [rbp-38h] BYREF
  VARIANTARG v14; // [rsp+40h] [rbp-20h] BYREF
  unsigned int v15; // [rsp+80h] [rbp+20h] BYREF
  int pExceptionObject; // [rsp+90h] [rbp+30h] BYREF
  unsigned __int16 *v17; // [rsp+98h] [rbp+38h] BYREF

  v4 = *((_QWORD *)this + 19);
  if ( !v4 )
    return 0;
  v15 = 0;
  v6 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v4 + 32LL))(v4, &v15);
  if ( v6 < 0 )
  {
    pExceptionObject = v6;
    throw (long *)&pExceptionObject;
  }
  for ( i = 0; i < v15; ++i )
  {
    pvarg.vt = 19;
    pvarg.lVal = i;
    v12 = 0;
    v8 = *((_QWORD *)this + 19);
    v14 = pvarg;
    v9 = (*(__int64 (__fastcall **)(__int64, VARIANTARG *, __int64 *))(*(_QWORD *)v8 + 40LL))(v8, &v14, &v12);
    if ( v9 < 0 )
    {
      pExceptionObject = v9;
      throw (long *)&pExceptionObject;
    }
    v17 = 0;
    v10 = (*(__int64 (__fastcall **)(__int64, unsigned __int16 **))(*(_QWORD *)v12 + 24LL))(v12, &v17);
    if ( v10 < 0 )
    {
      pExceptionObject = v10;
      throw (long *)&pExceptionObject;
    }
    SectionGroupNode::FindOrCreateSectionDescendantsWithName(a2, this, v17);
    ScopedBSTR::Reset((ScopedBSTR *)&v17);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v12);
    VariantClear(&pvarg);
  }
  v11 = *((_QWORD *)a2 + 4);
  if ( v11 )
    LODWORD(v11) = *(_DWORD *)(*(_QWORD *)(v11 + 48) - 32LL) + 1;
  return (_DWORD)v11 != 0;
}

```

## disassembly

```asm
0x180011910  mov     [rsp-18h+arg_8], rbx
0x180011915  push    rbp
0x180011916  push    rsi
0x180011917  push    rdi
0x180011918  mov     rbp, rsp
0x18001191b  sub     rsp, 60h
0x18001191f  mov     rsi, rdx
0x180011922  mov     rdi, rcx
0x180011925  mov     rcx, [rcx+98h]
0x18001192c  test    rcx, rcx
0x18001192f  jnz     short loc_180011938
0x180011931  xor     al, al
0x180011933  jmp     loc_180011A4B
0x180011938  mov     [rbp+arg_0], 0
0x18001193f  mov     rax, [rcx]
0x180011942  lea     rdx, [rbp+arg_0]
0x180011946  mov     rax, [rax+20h]
0x18001194a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001194f  test    eax, eax
0x180011951  jns     short loc_180011967
0x180011953  mov     [rbp+pExceptionObject], eax
0x180011956  lea     rdx, _TI1J; pThrowInfo
0x18001195d  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180011961  call    _CxxThrowException_0
0x180011967  xor     ebx, ebx
0x180011969  cmp     ebx, [rbp+arg_0]
0x18001196c  jnb     loc_180011A34
0x180011972  mov     eax, 13h
0x180011977  mov     word ptr [rbp+pvarg], ax
0x18001197b  mov     dword ptr [rbp+pvarg+8], ebx
0x18001197e  mov     [rbp+var_40], 0
0x180011986  mov     rcx, [rdi+98h]
0x18001198d  movups  xmm0, xmmword ptr [rbp+pvarg]
0x180011991  movaps  [rbp+var_20], xmm0
0x180011995  movsd   xmm1, qword ptr [rbp+pvarg+10h]
0x18001199a  movsd   [rbp+var_10], xmm1
0x18001199f  mov     rax, [rcx]
0x1800119a2  lea     r8, [rbp+var_40]
0x1800119a6  lea     rdx, [rbp+var_20]
0x1800119aa  mov     rax, [rax+28h]
0x1800119ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800119b3  test    eax, eax
0x1800119b5  js      short loc_180011A20
0x1800119b7  mov     [rbp+arg_18], 0
0x1800119bf  mov     rcx, [rbp+var_40]
0x1800119c3  mov     rax, [rcx]
0x1800119c6  lea     rdx, [rbp+arg_18]
0x1800119ca  mov     rax, [rax+18h]
0x1800119ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800119d3  test    eax, eax
0x1800119d5  js      short loc_180011A0C
0x1800119d7  mov     r8, [rbp+arg_18]; unsigned __int16 *
0x1800119db  mov     rdx, rdi; struct ConfigTreeBase *
0x1800119de  mov     rcx, rsi; this
0x1800119e1  call    ?FindOrCreateSectionDescendantsWithName@SectionGroupNode@@QEAAPEAVSectionNode@@PEAVConfigTreeBase@@PEBG@Z; SectionGroupNode::FindOrCreateSectionDescendantsWithName(ConfigTreeBase *,ushort const *)
0x1800119e6  nop
0x1800119e7  lea     rcx, [rbp+arg_18]; this
0x1800119eb  call    ?Reset@ScopedBSTR@@QEAAXXZ; ScopedBSTR::Reset(void)
0x1800119f0  nop
0x1800119f1  lea     rcx, [rbp+var_40]
0x1800119f5  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800119fa  nop
0x1800119fb  lea     rcx, [rbp+pvarg]; pvarg
0x1800119ff  call    cs:__imp_VariantClear
0x180011a05  inc     ebx
0x180011a07  jmp     loc_180011969
0x180011a0c  mov     [rbp+pExceptionObject], eax
0x180011a0f  lea     rdx, _TI1J; pThrowInfo
0x180011a16  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180011a1a  call    _CxxThrowException_0
0x180011a20  mov     [rbp+pExceptionObject], eax
0x180011a23  lea     rdx, _TI1J; pThrowInfo
0x180011a2a  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180011a2e  call    _CxxThrowException_0
0x180011a34  mov     rax, [rsi+20h]
0x180011a38  test    rax, rax
0x180011a3b  jz      short loc_180011A46
0x180011a3d  mov     rax, [rax+30h]
0x180011a41  mov     eax, [rax-20h]
0x180011a44  inc     eax
0x180011a46  test    eax, eax
0x180011a48  setnz   al
0x180011a4b  mov     rbx, [rsp+60h+arg_8]
0x180011a53  add     rsp, 60h
0x180011a57  pop     rdi
0x180011a58  pop     rsi
0x180011a59  pop     rbp
0x180011a5a  retn
```
