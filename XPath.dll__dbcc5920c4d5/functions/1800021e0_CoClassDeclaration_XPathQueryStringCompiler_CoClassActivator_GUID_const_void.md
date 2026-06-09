# CoClassDeclaration<XPathQueryStringCompiler>::CoClassActivator(_GUID const &,void * *)

- ea: `0x1800021e0`
- end: `0x1800022a7`
- name: `?CoClassActivator@?$CoClassDeclaration@VXPathQueryStringCompiler@@@@CAJAEBU_GUID@@PEAPEAX@Z`
- size: `199`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x180001078`
- `0x1800020b4`
- `0x1800021a4`
- `0x1800021e0`
- `0x18001180a`
- `0x180012010`

## pseudocode

```c
__int64 __fastcall CoClassDeclaration<XPathQueryStringCompiler>::CoClassActivator(__int64 a1, __int64 a2)
{
  _DWORD *v4; // rax
  _DWORD *v5; // rbx
  unsigned int v6; // ebx
  _DWORD *v8; // [rsp+40h] [rbp+18h] BYREF

  v4 = operator new(0x40u);
  v5 = v4;
  if ( v4 )
  {
    memset_0(v4, 0, 0x40u);
    *(_QWORD *)v5 = &SimpleIUnknownImpl<IXPathQueryStringCompiler>::`vftable';
    v5[2] = 1;
    ModuleRefCounter::AddRef();
    v8 = v5;
    *(_QWORD *)v5 = &XPathQueryStringCompiler::`vftable';
    *((_QWORD *)v5 + 2) = 0;
    *((_QWORD *)v5 + 3) = 0;
    v5[8] = 0;
    *((_QWORD *)v5 + 5) = 0;
    v5[12] = 0;
    *((_QWORD *)v5 + 7) = 0;
    v6 = ((__int64 (__fastcall *)(_DWORD *, __int64, __int64))XPathQueryStringCompiler::`vftable')(v5, a1, a2);
  }
  else
  {
    v8 = 0;
    v6 = -2147024882;
  }
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v8);
  return v6;
}

```

## disassembly

```asm
0x1800021e0  mov     [rsp+arg_0], rbx
0x1800021e5  mov     [rsp+arg_8], rsi
0x1800021ea  push    rdi
0x1800021eb  sub     rsp, 20h
0x1800021ef  mov     rsi, rcx
0x1800021f2  mov     rdi, rdx
0x1800021f5  mov     ecx, 40h ; '@'; Size
0x1800021fa  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800021ff  mov     rbx, rax
0x180002202  test    rax, rax
0x180002205  jz      short loc_18000227D
0x180002207  xor     edx, edx; Val
0x180002209  mov     rcx, rax; void *
0x18000220c  lea     r8d, [rdx+40h]; Size
0x180002210  call    memset_0
0x180002215  lea     rax, ??_7?$SimpleIUnknownImpl@UIXPathQueryStringCompiler@@@@6B@; const SimpleIUnknownImpl<IXPathQueryStringCompiler>::`vftable'
0x18000221c  mov     [rbx], rax
0x18000221f  mov     dword ptr [rbx+8], 1
0x180002226  call    ?AddRef@ModuleRefCounter@@SAXXZ; ModuleRefCounter::AddRef(void)
0x18000222b  lea     rax, ??_7XPathQueryStringCompiler@@6B@; const XPathQueryStringCompiler::`vftable'
0x180002232  mov     [rsp+28h+arg_10], rbx
0x180002237  mov     [rbx], rax
0x18000223a  mov     r8, rdi
0x18000223d  mov     rax, [rax]
0x180002240  mov     rdx, rsi
0x180002243  mov     qword ptr [rbx+10h], 0
0x18000224b  mov     rcx, rbx
0x18000224e  mov     qword ptr [rbx+18h], 0
0x180002256  mov     dword ptr [rbx+20h], 0
0x18000225d  mov     qword ptr [rbx+28h], 0
0x180002265  mov     dword ptr [rbx+30h], 0
0x18000226c  mov     qword ptr [rbx+38h], 0
0x180002274  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002279  mov     ebx, eax
0x18000227b  jmp     short loc_18000228B
0x18000227d  mov     [rsp+28h+arg_10], 0
0x180002286  mov     ebx, 8007000Eh
0x18000228b  lea     rcx, [rsp+28h+arg_10]
0x180002290  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180002295  mov     rsi, [rsp+28h+arg_8]
0x18000229a  mov     eax, ebx
0x18000229c  mov     rbx, [rsp+28h+arg_0]
0x1800022a1  add     rsp, 20h
0x1800022a5  pop     rdi
0x1800022a6  retn
```
