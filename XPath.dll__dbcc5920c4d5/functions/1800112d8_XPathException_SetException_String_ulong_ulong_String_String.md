# XPathException::SetException(String &,ulong,ulong,String &,String &)

- ea: `0x1800112d8`
- end: `0x1800113d4`
- name: `?SetException@XPathException@@SAJAEAVString@@KK00@Z`
- size: `252`
- prototype: `__int64 __fastcall(struct String *, unsigned int, unsigned int, struct String *, struct String *)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18000a3a8`

## callees

- `0x180001078`
- `0x1800020b4`
- `0x1800021a4`
- `0x1800112d8`
- `0x180012010`

## import_xrefs

- `OLEAUT32!__imp_GetErrorInfo` at `0x180011301`
- `OLEAUT32!__imp_GetErrorInfo` at `0x180011301`
- `OLEAUT32!__imp_SetErrorInfo` at `0x1800113a3`
- `OLEAUT32!__imp_SetErrorInfo` at `0x1800113a3`

## pseudocode

```c
__int64 __fastcall XPathException::SetException(
        struct IErrorInfoVtbl **a1,
        int a2,
        int a3,
        struct IErrorInfoVtbl **a4,
        struct IErrorInfoVtbl **a5)
{
  HRESULT ErrorInfo; // ebx
  IErrorInfo *v10; // rbx
  IErrorInfo *v11; // rdi
  struct IErrorInfoVtbl *v12; // rax
  struct IErrorInfoVtbl *v13; // rax
  struct IErrorInfoVtbl *v14; // rcx
  IErrorInfo *pperrinfo; // [rsp+20h] [rbp-48h] BYREF
  IErrorInfo *v17; // [rsp+28h] [rbp-40h] BYREF

  pperrinfo = 0;
  ErrorInfo = GetErrorInfo(0, &pperrinfo);
  if ( ErrorInfo >= 0 )
  {
    v10 = (IErrorInfo *)operator new(0x38u);
    if ( v10 )
    {
      v11 = pperrinfo;
      ModuleRefCounter::AddRef();
      v10->lpVtbl = (struct IErrorInfoVtbl *)&XPathException::`vftable';
      LODWORD(v10[1].lpVtbl) = 1;
      v10[2].lpVtbl = (struct IErrorInfoVtbl *)v11;
      if ( v11 )
        ((void (__fastcall *)(IErrorInfo *))v11->lpVtbl->AddRef)(v11);
      LODWORD(v10[3].lpVtbl) = a2;
      HIDWORD(v10[3].lpVtbl) = a3;
      v12 = *a1;
      v10[4].lpVtbl = *a1;
      if ( v12 )
        _InterlockedIncrement((volatile signed __int32 *)&v12[-1].GetHelpContext);
      v13 = *a4;
      v10[5].lpVtbl = *a4;
      if ( v13 )
        _InterlockedIncrement((volatile signed __int32 *)&v13[-1].GetHelpContext);
      v14 = *a5;
      v10[6].lpVtbl = *a5;
      if ( v14 )
        _InterlockedIncrement((volatile signed __int32 *)&v14[-1].GetHelpContext);
    }
    else
    {
      v10 = 0;
    }
    v17 = v10;
    ErrorInfo = SetErrorInfo(0, v10);
    if ( ErrorInfo >= 0 )
      ErrorInfo = 0;
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v17);
  }
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&pperrinfo);
  return (unsigned int)ErrorInfo;
}

```

## disassembly

```asm
0x1800112d8  push    rbx
0x1800112da  push    rbp
0x1800112db  push    rsi
0x1800112dc  push    rdi
0x1800112dd  push    r14
0x1800112df  push    r15
0x1800112e1  sub     rsp, 38h
0x1800112e5  mov     r14d, edx
0x1800112e8  mov     [rsp+68h+pperrinfo], 0
0x1800112f1  mov     r15, rcx
0x1800112f4  lea     rdx, [rsp+68h+pperrinfo]; pperrinfo
0x1800112f9  xor     ecx, ecx; dwReserved
0x1800112fb  mov     rsi, r9
0x1800112fe  mov     ebp, r8d
0x180011301  call    cs:__imp_GetErrorInfo
0x180011307  mov     ebx, eax
0x180011309  test    eax, eax
0x18001130b  js      loc_1800113BB
0x180011311  mov     ecx, 38h ; '8'; Size
0x180011316  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001131b  mov     rbx, rax
0x18001131e  test    rax, rax
0x180011321  jz      short loc_180011397
0x180011323  mov     rdi, [rsp+68h+pperrinfo]
0x180011328  call    ?AddRef@ModuleRefCounter@@SAXXZ; ModuleRefCounter::AddRef(void)
0x18001132d  lea     rax, ??_7XPathException@@6B@; const XPathException::`vftable'
0x180011334  mov     [rbx], rax
0x180011337  mov     dword ptr [rbx+8], 1
0x18001133e  mov     [rbx+10h], rdi
0x180011342  test    rdi, rdi
0x180011345  jz      short loc_180011356
0x180011347  mov     rax, [rdi]
0x18001134a  mov     rcx, rdi
0x18001134d  mov     rax, [rax+8]
0x180011351  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011356  mov     [rbx+18h], r14d
0x18001135a  mov     [rbx+1Ch], ebp
0x18001135d  mov     rax, [r15]
0x180011360  mov     [rbx+20h], rax
0x180011364  test    rax, rax
0x180011367  jz      short loc_18001136D
0x180011369  lock inc dword ptr [rax-8]
0x18001136d  mov     rax, [rsi]
0x180011370  mov     [rbx+28h], rax
0x180011374  test    rax, rax
0x180011377  jz      short loc_18001137D
0x180011379  lock inc dword ptr [rax-8]
0x18001137d  mov     rax, [rsp+68h+arg_20]
0x180011385  mov     rcx, [rax]
0x180011388  mov     [rbx+30h], rcx
0x18001138c  test    rcx, rcx
0x18001138f  jz      short loc_180011399
0x180011391  lock inc dword ptr [rcx-8]
0x180011395  jmp     short loc_180011399
0x180011397  xor     ebx, ebx
0x180011399  mov     rdx, rbx; perrinfo
0x18001139c  mov     [rsp+68h+var_40], rbx
0x1800113a1  xor     ecx, ecx; dwReserved
0x1800113a3  call    cs:__imp_SetErrorInfo
0x1800113a9  mov     ebx, eax
0x1800113ab  test    eax, eax
0x1800113ad  js      short loc_1800113B1
0x1800113af  xor     ebx, ebx
0x1800113b1  lea     rcx, [rsp+68h+var_40]
0x1800113b6  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800113bb  lea     rcx, [rsp+68h+pperrinfo]
0x1800113c0  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800113c5  mov     eax, ebx
0x1800113c7  add     rsp, 38h
0x1800113cb  pop     r15
0x1800113cd  pop     r14
0x1800113cf  pop     rdi
0x1800113d0  pop     rsi
0x1800113d1  pop     rbp
0x1800113d2  pop     rbx
0x1800113d3  retn
```
