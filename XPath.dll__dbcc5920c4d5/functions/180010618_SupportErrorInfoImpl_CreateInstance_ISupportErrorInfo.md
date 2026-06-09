# SupportErrorInfoImpl::CreateInstance(ISupportErrorInfo * *)

- ea: `0x180010618`
- end: `0x18001068b`
- name: `?CreateInstance@SupportErrorInfoImpl@@SAJPEAPEAUISupportErrorInfo@@@Z`
- size: `115`
- prototype: `__int64 __fastcall(struct ISupportErrorInfo **)`
- caller_count: `5`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1800022b0`
- `0x1800052e0`
- `0x180005390`
- `0x1800106d0`
- `0x180010780`

## callees

- `0x180001078`
- `0x1800020b4`
- `0x1800021a4`
- `0x180010618`

## pseudocode

```c
__int64 __fastcall SupportErrorInfoImpl::CreateInstance(struct ISupportErrorInfo **a1)
{
  struct ISupportErrorInfo *v2; // rax
  struct ISupportErrorInfo *v3; // rbx
  unsigned int v4; // ebx
  __int64 v6; // [rsp+38h] [rbp+10h] BYREF

  v2 = (struct ISupportErrorInfo *)operator new(0x10u);
  v3 = v2;
  if ( v2 )
  {
    v2[1].lpVtbl = 0;
    v2->lpVtbl = (struct ISupportErrorInfoVtbl *)&SimpleIUnknownImpl<ISupportErrorInfo>::`vftable';
    LODWORD(v2[1].lpVtbl) = 1;
    ModuleRefCounter::AddRef();
    v3->lpVtbl = (struct ISupportErrorInfoVtbl *)&SupportErrorInfoImpl::`vftable';
    *a1 = v3;
    v4 = 0;
  }
  else
  {
    v4 = -2147024882;
  }
  v6 = 0;
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v6);
  return v4;
}

```

## disassembly

```asm
0x180010618  mov     [rsp+arg_0], rbx
0x18001061d  push    rdi
0x18001061e  sub     rsp, 20h
0x180010622  mov     rdi, rcx
0x180010625  mov     ecx, 10h; Size
0x18001062a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001062f  mov     rbx, rax
0x180010632  test    rax, rax
0x180010635  jz      short loc_180010666
0x180010637  mov     qword ptr [rax+8], 0
0x18001063f  lea     rax, ??_7?$SimpleIUnknownImpl@UISupportErrorInfo@@@@6B@; const SimpleIUnknownImpl<ISupportErrorInfo>::`vftable'
0x180010646  mov     [rbx], rax
0x180010649  mov     dword ptr [rbx+8], 1
0x180010650  call    ?AddRef@ModuleRefCounter@@SAXXZ; ModuleRefCounter::AddRef(void)
0x180010655  lea     rax, ??_7SupportErrorInfoImpl@@6B@; const SupportErrorInfoImpl::`vftable'
0x18001065c  mov     [rbx], rax
0x18001065f  mov     [rdi], rbx
0x180010662  xor     ebx, ebx
0x180010664  jmp     short loc_18001066B
0x180010666  mov     ebx, 8007000Eh
0x18001066b  lea     rcx, [rsp+28h+arg_8]
0x180010670  mov     [rsp+28h+arg_8], 0
0x180010679  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18001067e  mov     eax, ebx
0x180010680  mov     rbx, [rsp+28h+arg_0]
0x180010685  add     rsp, 20h
0x180010689  pop     rdi
0x18001068a  retn
```
