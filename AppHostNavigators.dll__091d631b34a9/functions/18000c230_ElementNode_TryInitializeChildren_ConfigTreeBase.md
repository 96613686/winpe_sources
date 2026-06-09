# ElementNode::TryInitializeChildren(ConfigTreeBase *)

- ea: `0x18000c230`
- end: `0x18000c3a8`
- name: `?TryInitializeChildren@ElementNode@@EEAA_NPEAVConfigTreeBase@@@Z`
- size: `376`
- prototype: `bool __fastcall(ElementNode *__hidden this, struct ConfigTreeBase *)`
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x1800021a4`
- `0x180007aac`
- `0x18000a60c`
- `0x18000b8ec`
- `0x18000ba8c`
- `0x18000c230`
- `0x180012f3c`
- `0x180014010`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
char __fastcall ElementNode::TryInitializeChildren(ElementNode *this, ConfigSystemContext **a2)
{
  __int64 v4; // rax
  bool v5; // si
  int v6; // eax
  int v7; // eax
  __int64 v8; // rcx
  __int64 v10[2]; // [rsp+20h] [rbp-10h] BYREF
  int pExceptionObject; // [rsp+50h] [rbp+20h] BYREF
  struct IUnknown *v12; // [rsp+60h] [rbp+30h] BYREF
  struct IUnknown *v13; // [rsp+68h] [rbp+38h] BYREF

  v4 = *((_QWORD *)this + 4);
  if ( v4 && *(_DWORD *)(*(_QWORD *)(v4 + 48) - 32LL) != -1 )
    return 0;
  v10[0] = 0;
  (*(void (__fastcall **)(ElementNode *, ConfigSystemContext **, __int64 *))(*(_QWORD *)this + 112LL))(this, a2, v10);
  v5 = Helpers::IsAppHostObjectBackedByExtension<IAppHostElementSchema,ATL::CComPtr<IAppHostElement>>(v10);
  v13 = 0;
  v6 = (*(__int64 (__fastcall **)(__int64, struct IUnknown **))(*(_QWORD *)v10[0] + 48LL))(v10[0], &v13);
  if ( v6 >= 0 )
    goto LABEL_7;
  if ( !v5 )
  {
    pExceptionObject = v6;
    throw (long *)&pExceptionObject;
  }
  if ( v13 )
  {
    ATL::AtlComPtrAssign(&v13, 0);
LABEL_7:
    if ( v13 )
      ElementNode::InitializeChildElements(this, a2, (struct IAppHostChildElementCollection *)v13);
  }
  v12 = 0;
  v7 = (*(__int64 (__fastcall **)(__int64, struct IUnknown **))(*(_QWORD *)v10[0] + 32LL))(v10[0], &v12);
  if ( v7 < 0 )
  {
    if ( !v5 )
    {
      pExceptionObject = v7;
      throw (long *)&pExceptionObject;
    }
    if ( !v12 )
      goto LABEL_15;
    ATL::AtlComPtrAssign(&v12, 0);
  }
  if ( v12 )
    ElementNode::InitializeCollectionElements(
      this,
      (struct ConfigTreeBase *)a2,
      (struct IAppHostElementCollection *)v12);
LABEL_15:
  v8 = *((_QWORD *)this + 4);
  if ( v8 && *(_DWORD *)(*(_QWORD *)(v8 + 48) - 32LL) != -1 )
  {
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v12);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v13);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(v10);
    return 1;
  }
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v12);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v13);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(v10);
  return 0;
}

```

## disassembly

```asm
0x18000c230  mov     [rsp-18h+arg_8], rbx
0x18000c235  push    rbp
0x18000c236  push    rsi
0x18000c237  push    rdi
0x18000c238  mov     rbp, rsp
0x18000c23b  sub     rsp, 30h
0x18000c23f  mov     rdi, rdx
0x18000c242  mov     rbx, rcx
0x18000c245  mov     rax, [rcx+20h]
0x18000c249  test    rax, rax
0x18000c24c  jz      short loc_18000C260
0x18000c24e  mov     rax, [rax+30h]
0x18000c252  mov     r8d, [rax-20h]
0x18000c256  add     r8d, 1
0x18000c25a  jnz     loc_18000C399
0x18000c260  mov     [rbp+var_10], 0
0x18000c268  mov     rax, [rcx]
0x18000c26b  lea     r8, [rbp+var_10]
0x18000c26f  mov     rax, [rax+70h]
0x18000c273  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c278  lea     rcx, [rbp+var_10]
0x18000c27c  call    ??$IsAppHostObjectBackedByExtension@UIAppHostElementSchema@@V?$CComPtr@UIAppHostElement@@@ATL@@@Helpers@@SA_NAEAV?$CComPtr@UIAppHostElement@@@ATL@@@Z; Helpers::IsAppHostObjectBackedByExtension<IAppHostElementSchema,ATL::CComPtr<IAppHostElement>>(ATL::CComPtr<IAppHostElement> &)
0x18000c281  mov     sil, al
0x18000c284  mov     [rbp+arg_18], 0
0x18000c28c  mov     rcx, [rbp+var_10]
0x18000c290  mov     rax, [rcx]
0x18000c293  lea     rdx, [rbp+arg_18]
0x18000c297  mov     rax, [rax+30h]
0x18000c29b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c2a0  test    eax, eax
0x18000c2a2  jns     short loc_18000C2BF
0x18000c2a4  test    sil, sil
0x18000c2a7  jz      loc_18000C354
0x18000c2ad  cmp     [rbp+arg_18], 0
0x18000c2b2  jz      short loc_18000C2D3
0x18000c2b4  xor     edx, edx; struct IUnknown *
0x18000c2b6  lea     rcx, [rbp+arg_18]; struct IUnknown **
0x18000c2ba  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x18000c2bf  mov     r8, [rbp+arg_18]; struct IAppHostChildElementCollection *
0x18000c2c3  test    r8, r8
0x18000c2c6  jz      short loc_18000C2D3
0x18000c2c8  mov     rdx, rdi; struct ConfigTreeBase *
0x18000c2cb  mov     rcx, rbx; this
0x18000c2ce  call    ?InitializeChildElements@ElementNode@@AEAAXPEAVConfigTreeBase@@PEAUIAppHostChildElementCollection@@@Z; ElementNode::InitializeChildElements(ConfigTreeBase *,IAppHostChildElementCollection *)
0x18000c2d3  mov     [rbp+arg_10], 0
0x18000c2db  mov     rcx, [rbp+var_10]
0x18000c2df  mov     rax, [rcx]
0x18000c2e2  lea     rdx, [rbp+arg_10]
0x18000c2e6  mov     rax, [rax+20h]
0x18000c2ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c2ef  test    eax, eax
0x18000c2f1  jns     short loc_18000C30A
0x18000c2f3  test    sil, sil
0x18000c2f6  jz      short loc_18000C368
0x18000c2f8  cmp     [rbp+arg_10], 0
0x18000c2fd  jz      short loc_18000C31E
0x18000c2ff  xor     edx, edx; struct IUnknown *
0x18000c301  lea     rcx, [rbp+arg_10]; struct IUnknown **
0x18000c305  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x18000c30a  mov     r8, [rbp+arg_10]; struct IAppHostElementCollection *
0x18000c30e  test    r8, r8
0x18000c311  jz      short loc_18000C31E
0x18000c313  mov     rdx, rdi; struct ConfigTreeBase *
0x18000c316  mov     rcx, rbx; this
0x18000c319  call    ?InitializeCollectionElements@ElementNode@@AEAAXPEAVConfigTreeBase@@PEAUIAppHostElementCollection@@@Z; ElementNode::InitializeCollectionElements(ConfigTreeBase *,IAppHostElementCollection *)
0x18000c31e  mov     rcx, [rbx+20h]
0x18000c322  test    rcx, rcx
0x18000c325  jz      short loc_18000C37C
0x18000c327  mov     rcx, [rcx+30h]
0x18000c32b  mov     edx, [rcx-20h]
0x18000c32e  add     edx, 1
0x18000c331  jz      short loc_18000C37C
0x18000c333  lea     rcx, [rbp+arg_10]
0x18000c337  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18000c33c  nop
0x18000c33d  lea     rcx, [rbp+arg_18]
0x18000c341  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18000c346  nop
0x18000c347  lea     rcx, [rbp+var_10]
0x18000c34b  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18000c350  mov     al, 1
0x18000c352  jmp     short loc_18000C39B
0x18000c354  mov     [rbp+pExceptionObject], eax
0x18000c357  lea     rdx, _TI1J; pThrowInfo
0x18000c35e  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18000c362  call    _CxxThrowException_0
0x18000c368  mov     [rbp+pExceptionObject], eax
0x18000c36b  lea     rdx, _TI1J; pThrowInfo
0x18000c372  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18000c376  call    _CxxThrowException_0
0x18000c37c  lea     rcx, [rbp+arg_10]
0x18000c380  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18000c385  nop
0x18000c386  lea     rcx, [rbp+arg_18]
0x18000c38a  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18000c38f  nop
0x18000c390  lea     rcx, [rbp+var_10]
0x18000c394  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18000c399  xor     al, al
0x18000c39b  mov     rbx, [rsp+30h+arg_8]
0x18000c3a0  add     rsp, 30h
0x18000c3a4  pop     rdi
0x18000c3a5  pop     rsi
0x18000c3a6  pop     rbp
0x18000c3a7  retn
```
