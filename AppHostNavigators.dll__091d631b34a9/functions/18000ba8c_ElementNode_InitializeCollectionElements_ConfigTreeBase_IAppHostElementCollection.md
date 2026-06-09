# ElementNode::InitializeCollectionElements(ConfigTreeBase *,IAppHostElementCollection *)

- ea: `0x18000ba8c`
- end: `0x18000bc05`
- name: `?InitializeCollectionElements@ElementNode@@AEAAXPEAVConfigTreeBase@@PEAUIAppHostElementCollection@@@Z`
- size: `377`
- prototype: `void __fastcall(ElementNode *__hidden this, struct ConfigTreeBase *, struct IAppHostElementCollection *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000c230`

## callees

- `0x180001194`
- `0x1800021a4`
- `0x180009cb8`
- `0x18000b860`
- `0x18000ba8c`
- `0x180012f3c`
- `0x18001306e`
- `0x180014010`

## import_xrefs

- `OLEAUT32!__imp_VariantClear` at `0x18000bb2b`
- `OLEAUT32!__imp_VariantClear` at `0x18000bb2b`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall ElementNode::InitializeCollectionElements(
        ElementNode *this,
        struct ConfigTreeBase *a2,
        struct IAppHostElementCollection *a3)
{
  int v6; // eax
  unsigned int i; // edi
  struct IAppHostElementCollectionVtbl *lpVtbl; // rax
  int v9; // ebx
  _DWORD *v10; // rax
  _DWORD *v11; // rbx
  struct IAppHostElement *v12; // [rsp+20h] [rbp-40h] BYREF
  VARIANTARG pvarg; // [rsp+28h] [rbp-38h] BYREF
  VARIANTARG v14; // [rsp+40h] [rbp-20h] BYREF
  unsigned int v15; // [rsp+A0h] [rbp+40h] BYREF
  void *pExceptionObject; // [rsp+A8h] [rbp+48h] BYREF

  v15 = 0;
  v6 = ((__int64 (__fastcall *)(struct IAppHostElementCollection *, unsigned int *))a3->lpVtbl->get_Count)(a3, &v15);
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
    v9 = ((__int64 (__fastcall *)(struct IAppHostElementCollection *, VARIANTARG *, struct IAppHostElement **))lpVtbl->get_Item)(
           a3,
           &v14,
           &v12);
    VariantClear(&pvarg);
    if ( v9 < 0 )
    {
      LODWORD(pExceptionObject) = v9;
      throw (long *)&pExceptionObject;
    }
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
      *(_QWORD *)v11 = &CollectionElement::`vftable';
    }
    else
    {
      v11 = 0;
    }
    pExceptionObject = v11;
    NonSectionElementNode::Initialize((NonSectionElementNode *)v11, a2, this, v12);
    TagNavigationNode<FileSystemTagNode,FileSystemNode,FileSystemTree>::AddChild(this, v11);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v12);
  }
}

```

## disassembly

```asm
0x18000ba8c  mov     [rsp-28h+arg_0], rbx
0x18000ba91  mov     [rsp-28h+arg_8], rsi
0x18000ba96  push    rbp
0x18000ba97  push    rdi
0x18000ba98  push    r12
0x18000ba9a  push    r14
0x18000ba9c  push    r15
0x18000ba9e  mov     rbp, rsp
0x18000baa1  sub     rsp, 60h
0x18000baa5  mov     rsi, r8
0x18000baa8  mov     r15, rdx
0x18000baab  mov     r14, rcx
0x18000baae  xor     r12d, r12d
0x18000bab1  mov     [rbp+arg_10], r12d
0x18000bab5  mov     rax, [r8]
0x18000bab8  lea     rdx, [rbp+arg_10]
0x18000babc  mov     rcx, r8
0x18000babf  mov     rax, [rax+18h]
0x18000bac3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bac8  test    eax, eax
0x18000baca  jns     short loc_18000BAE0
0x18000bacc  mov     dword ptr [rbp+pExceptionObject], eax
0x18000bacf  lea     rdx, _TI1J; pThrowInfo
0x18000bad6  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18000bada  call    _CxxThrowException_0
0x18000bae0  mov     edi, r12d
0x18000bae3  cmp     edi, [rbp+arg_10]
0x18000bae6  jnb     loc_18000BBEC
0x18000baec  mov     [rbp+var_40], r12
0x18000baf0  mov     rax, [rsi]
0x18000baf3  mov     ecx, 13h
0x18000baf8  mov     word ptr [rbp+pvarg], cx
0x18000bafc  mov     dword ptr [rbp+pvarg+8], edi
0x18000baff  movups  xmm0, xmmword ptr [rbp+pvarg]
0x18000bb03  movaps  [rbp+var_20], xmm0
0x18000bb07  movsd   xmm1, qword ptr [rbp+pvarg+10h]
0x18000bb0c  movsd   [rbp+var_10], xmm1
0x18000bb11  lea     r8, [rbp+var_40]
0x18000bb15  lea     rdx, [rbp+var_20]
0x18000bb19  mov     rcx, rsi
0x18000bb1c  mov     rax, [rax+20h]
0x18000bb20  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bb25  mov     ebx, eax
0x18000bb27  lea     rcx, [rbp+pvarg]; pvarg
0x18000bb2b  call    cs:__imp_VariantClear
0x18000bb31  test    ebx, ebx
0x18000bb33  js      loc_18000BBD8
0x18000bb39  mov     ecx, 68h ; 'h'; Size
0x18000bb3e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000bb43  mov     rbx, rax
0x18000bb46  mov     [rbp+pExceptionObject], rax
0x18000bb4a  test    rax, rax
0x18000bb4d  jz      short loc_18000BBA3
0x18000bb4f  xor     edx, edx; Val
0x18000bb51  lea     r8d, [rdx+68h]; Size
0x18000bb55  mov     rcx, rax; void *
0x18000bb58  call    memset_0
0x18000bb5d  mov     dword ptr [rbx+8], 0FFFFFFFFh
0x18000bb64  mov     [rbx+0Ch], r12d
0x18000bb68  mov     [rbx+10h], r12
0x18000bb6c  mov     [rbx+18h], r12
0x18000bb70  mov     [rbx+20h], r12
0x18000bb74  lea     rax, [rbx+28h]
0x18000bb78  mov     [rbx+30h], rax
0x18000bb7c  mov     [rax], rax
0x18000bb7f  mov     [rbx+40h], r12
0x18000bb83  mov     [rbx+38h], r12
0x18000bb87  mov     [rbx+48h], r12
0x18000bb8b  mov     [rbx+50h], r12
0x18000bb8f  mov     [rbx+58h], r12
0x18000bb93  mov     [rbx+60h], r12
0x18000bb97  lea     rax, ??_7CollectionElement@@6B@; const CollectionElement::`vftable'
0x18000bb9e  mov     [rbx], rax
0x18000bba1  jmp     short loc_18000BBA6
0x18000bba3  mov     rbx, r12
0x18000bba6  mov     [rbp+pExceptionObject], rbx
0x18000bbaa  mov     r9, [rbp+var_40]; struct IAppHostElement *
0x18000bbae  mov     r8, r14; struct ConfigTagNode *
0x18000bbb1  mov     rdx, r15; struct ConfigTreeBase *
0x18000bbb4  mov     rcx, rbx; this
0x18000bbb7  call    ?Initialize@NonSectionElementNode@@QEAAXPEAVConfigTreeBase@@PEAVConfigTagNode@@PEAUIAppHostElement@@@Z; NonSectionElementNode::Initialize(ConfigTreeBase *,ConfigTagNode *,IAppHostElement *)
0x18000bbbc  mov     rdx, rbx
0x18000bbbf  mov     rcx, r14
0x18000bbc2  call    ?AddChild@?$TagNavigationNode@VFileSystemTagNode@@VFileSystemNode@@VFileSystemTree@@@@QEAAXPEAVFileSystemTagNode@@@Z; TagNavigationNode<FileSystemTagNode,FileSystemNode,FileSystemTree>::AddChild(FileSystemTagNode *)
0x18000bbc7  nop
0x18000bbc8  lea     rcx, [rbp+var_40]
0x18000bbcc  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18000bbd1  inc     edi
0x18000bbd3  jmp     loc_18000BAE3
0x18000bbd8  mov     dword ptr [rbp+pExceptionObject], ebx
0x18000bbdb  lea     rdx, _TI1J; pThrowInfo
0x18000bbe2  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18000bbe6  call    _CxxThrowException_0
0x18000bbec  lea     r11, [rsp+60h+var_s0]
0x18000bbf1  mov     rbx, [r11+30h]
0x18000bbf5  mov     rsi, [r11+38h]
0x18000bbf9  mov     rsp, r11
0x18000bbfc  pop     r15
0x18000bbfe  pop     r14
0x18000bc00  pop     r12
0x18000bc02  pop     rdi
0x18000bc03  pop     rbp
0x18000bc04  retn
```
