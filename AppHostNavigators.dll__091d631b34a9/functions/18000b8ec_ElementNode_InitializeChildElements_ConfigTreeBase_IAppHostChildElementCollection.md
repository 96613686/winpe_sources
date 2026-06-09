# ElementNode::InitializeChildElements(ConfigTreeBase *,IAppHostChildElementCollection *)

- ea: `0x18000b8ec`
- end: `0x18000ba83`
- name: `?InitializeChildElements@ElementNode@@AEAAXPEAVConfigTreeBase@@PEAUIAppHostChildElementCollection@@@Z`
- size: `407`
- prototype: `void __fastcall(ElementNode *__hidden this, struct ConfigTreeBase *, struct IAppHostChildElementCollection *)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18000c230`

## callees

- `0x180001194`
- `0x1800021a4`
- `0x180009cb8`
- `0x18000a60c`
- `0x18000b860`
- `0x18000b8ec`
- `0x18000dc48`
- `0x180012f3c`
- `0x18001306e`
- `0x180014010`

## import_xrefs

- `OLEAUT32!__imp_VariantClear` at `0x18000b98b`
- `OLEAUT32!__imp_VariantClear` at `0x18000b98b`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall ElementNode::InitializeChildElements(
        ElementNode *this,
        ConfigSystemContext **a2,
        struct IAppHostChildElementCollection *a3)
{
  int v6; // eax
  unsigned int i; // edi
  struct IAppHostChildElementCollectionVtbl *lpVtbl; // rax
  int v9; // ebx
  _DWORD *v10; // rax
  _DWORD *v11; // rbx
  struct IAppHostElement *v12; // [rsp+20h] [rbp-40h] BYREF
  VARIANTARG pvarg; // [rsp+28h] [rbp-38h] BYREF
  VARIANTARG v14; // [rsp+40h] [rbp-20h] BYREF
  unsigned int v15; // [rsp+A0h] [rbp+40h] BYREF
  void *pExceptionObject; // [rsp+A8h] [rbp+48h] BYREF

  v15 = 0;
  v6 = ((__int64 (__fastcall *)(struct IAppHostChildElementCollection *, unsigned int *))a3->lpVtbl->get_Count)(
         a3,
         &v15);
  if ( v6 < 0 )
  {
    LODWORD(pExceptionObject) = v6;
    throw (long *)&pExceptionObject;
  }
  for ( i = 0; i < v15; ++i )
  {
    v12 = 0;
    lpVtbl = a3->lpVtbl;
    pvarg.vt = 19;
    pvarg.lVal = i;
    v14 = pvarg;
    v9 = ((__int64 (__fastcall *)(struct IAppHostChildElementCollection *, VARIANTARG *, struct IAppHostElement **))lpVtbl->get_Item)(
           a3,
           &v14,
           &v12);
    VariantClear(&pvarg);
    if ( v9 < 0 )
    {
      LODWORD(pExceptionObject) = v9;
      throw (long *)&pExceptionObject;
    }
    if ( !Helpers::IsAppHostObjectBackedByExtension<IAppHostElementSchema,ATL::CComPtr<IAppHostElement>>(&v12)
      || !ConfigSystemContext::IsWritableConfigSystem(a2[3]) )
    {
      v10 = operator new(0x68u);
      v11 = v10;
      pExceptionObject = v10;
      if ( v10 )
      {
        memset_0(v10, 0, 0x68u);
        v11[2] = -1;
        v11[3] = 0;
        *((_QWORD *)v11 + 2) = 0;
        *((_QWORD *)v11 + 3) = 0;
        *((_QWORD *)v11 + 4) = 0;
        *((_QWORD *)v11 + 6) = v11 + 10;
        *((_QWORD *)v11 + 5) = v11 + 10;
        *((_QWORD *)v11 + 8) = 0;
        *((_QWORD *)v11 + 7) = 0;
        *((_QWORD *)v11 + 9) = 0;
        *((_QWORD *)v11 + 10) = 0;
        *((_QWORD *)v11 + 11) = 0;
        *((_QWORD *)v11 + 12) = 0;
        *(_QWORD *)v11 = &ChildElement::`vftable';
      }
      else
      {
        v11 = 0;
      }
      pExceptionObject = v11;
      NonSectionElementNode::Initialize((NonSectionElementNode *)v11, (struct ConfigTreeBase *)a2, this, v12);
      TagNavigationNode<FileSystemTagNode,FileSystemNode,FileSystemTree>::AddChild(this, v11);
    }
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v12);
  }
}

```

## disassembly

```asm
0x18000b8ec  mov     [rsp-28h+arg_0], rbx
0x18000b8f1  mov     [rsp-28h+arg_8], rsi
0x18000b8f6  push    rbp
0x18000b8f7  push    rdi
0x18000b8f8  push    r12
0x18000b8fa  push    r14
0x18000b8fc  push    r15
0x18000b8fe  mov     rbp, rsp
0x18000b901  sub     rsp, 60h
0x18000b905  mov     r14, r8
0x18000b908  mov     rsi, rdx
0x18000b90b  mov     r15, rcx
0x18000b90e  xor     r12d, r12d
0x18000b911  mov     [rbp+arg_10], r12d
0x18000b915  mov     rax, [r8]
0x18000b918  lea     rdx, [rbp+arg_10]
0x18000b91c  mov     rcx, r8
0x18000b91f  mov     rax, [rax+18h]
0x18000b923  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b928  test    eax, eax
0x18000b92a  jns     short loc_18000B940
0x18000b92c  mov     dword ptr [rbp+pExceptionObject], eax
0x18000b92f  lea     rdx, _TI1J; pThrowInfo
0x18000b936  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18000b93a  call    _CxxThrowException_0
0x18000b940  mov     edi, r12d
0x18000b943  cmp     edi, [rbp+arg_10]
0x18000b946  jnb     loc_18000BA6A
0x18000b94c  mov     [rbp+var_40], r12
0x18000b950  mov     rax, [r14]
0x18000b953  mov     ecx, 13h
0x18000b958  mov     word ptr [rbp+pvarg], cx
0x18000b95c  mov     dword ptr [rbp+pvarg+8], edi
0x18000b95f  movups  xmm0, xmmword ptr [rbp+pvarg]
0x18000b963  movaps  [rbp+var_20], xmm0
0x18000b967  movsd   xmm1, qword ptr [rbp+pvarg+10h]
0x18000b96c  movsd   [rbp+var_10], xmm1
0x18000b971  lea     r8, [rbp+var_40]
0x18000b975  lea     rdx, [rbp+var_20]
0x18000b979  mov     rcx, r14
0x18000b97c  mov     rax, [rax+20h]
0x18000b980  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b985  mov     ebx, eax
0x18000b987  lea     rcx, [rbp+pvarg]; pvarg
0x18000b98b  call    cs:__imp_VariantClear
0x18000b991  test    ebx, ebx
0x18000b993  js      loc_18000BA56
0x18000b999  lea     rcx, [rbp+var_40]
0x18000b99d  call    ??$IsAppHostObjectBackedByExtension@UIAppHostElementSchema@@V?$CComPtr@UIAppHostElement@@@ATL@@@Helpers@@SA_NAEAV?$CComPtr@UIAppHostElement@@@ATL@@@Z; Helpers::IsAppHostObjectBackedByExtension<IAppHostElementSchema,ATL::CComPtr<IAppHostElement>>(ATL::CComPtr<IAppHostElement> &)
0x18000b9a2  test    al, al
0x18000b9a4  jz      short loc_18000B9B7
0x18000b9a6  mov     rcx, [rsi+18h]; this
0x18000b9aa  call    ?IsWritableConfigSystem@ConfigSystemContext@@QEAA_NXZ; ConfigSystemContext::IsWritableConfigSystem(void)
0x18000b9af  test    al, al
0x18000b9b1  jnz     loc_18000BA46
0x18000b9b7  mov     ecx, 68h ; 'h'; Size
0x18000b9bc  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000b9c1  mov     rbx, rax
0x18000b9c4  mov     [rbp+pExceptionObject], rax
0x18000b9c8  test    rax, rax
0x18000b9cb  jz      short loc_18000BA21
0x18000b9cd  xor     edx, edx; Val
0x18000b9cf  lea     r8d, [rdx+68h]; Size
0x18000b9d3  mov     rcx, rax; void *
0x18000b9d6  call    memset_0
0x18000b9db  mov     dword ptr [rbx+8], 0FFFFFFFFh
0x18000b9e2  mov     [rbx+0Ch], r12d
0x18000b9e6  mov     [rbx+10h], r12
0x18000b9ea  mov     [rbx+18h], r12
0x18000b9ee  mov     [rbx+20h], r12
0x18000b9f2  lea     rax, [rbx+28h]
0x18000b9f6  mov     [rbx+30h], rax
0x18000b9fa  mov     [rax], rax
0x18000b9fd  mov     [rbx+40h], r12
0x18000ba01  mov     [rbx+38h], r12
0x18000ba05  mov     [rbx+48h], r12
0x18000ba09  mov     [rbx+50h], r12
0x18000ba0d  mov     [rbx+58h], r12
0x18000ba11  mov     [rbx+60h], r12
0x18000ba15  lea     rax, ??_7ChildElement@@6B@; const ChildElement::`vftable'
0x18000ba1c  mov     [rbx], rax
0x18000ba1f  jmp     short loc_18000BA24
0x18000ba21  mov     rbx, r12
0x18000ba24  mov     [rbp+pExceptionObject], rbx
0x18000ba28  mov     r9, [rbp+var_40]; struct IAppHostElement *
0x18000ba2c  mov     r8, r15; struct ConfigTagNode *
0x18000ba2f  mov     rdx, rsi; struct ConfigTreeBase *
0x18000ba32  mov     rcx, rbx; this
0x18000ba35  call    ?Initialize@NonSectionElementNode@@QEAAXPEAVConfigTreeBase@@PEAVConfigTagNode@@PEAUIAppHostElement@@@Z; NonSectionElementNode::Initialize(ConfigTreeBase *,ConfigTagNode *,IAppHostElement *)
0x18000ba3a  mov     rdx, rbx
0x18000ba3d  mov     rcx, r15
0x18000ba40  call    ?AddChild@?$TagNavigationNode@VFileSystemTagNode@@VFileSystemNode@@VFileSystemTree@@@@QEAAXPEAVFileSystemTagNode@@@Z; TagNavigationNode<FileSystemTagNode,FileSystemNode,FileSystemTree>::AddChild(FileSystemTagNode *)
0x18000ba45  nop
0x18000ba46  lea     rcx, [rbp+var_40]
0x18000ba4a  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18000ba4f  inc     edi
0x18000ba51  jmp     loc_18000B943
0x18000ba56  mov     dword ptr [rbp+pExceptionObject], ebx
0x18000ba59  lea     rdx, _TI1J; pThrowInfo
0x18000ba60  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18000ba64  call    _CxxThrowException_0
0x18000ba6a  lea     r11, [rsp+60h+var_s0]
0x18000ba6f  mov     rbx, [r11+30h]
0x18000ba73  mov     rsi, [r11+38h]
0x18000ba77  mov     rsp, r11
0x18000ba7a  pop     r15
0x18000ba7c  pop     r14
0x18000ba7e  pop     r12
0x18000ba80  pop     rdi
0x18000ba81  pop     rbp
0x18000ba82  retn
```
