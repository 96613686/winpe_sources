# _AfxBindHost::MonikerBindToStorage(IMoniker *,IBindCtx *,IBindStatusCallback *,_GUID const &,void * *)

- ea: `0x1800a2080`
- end: `0x1800a2187`
- name: `?MonikerBindToStorage@_AfxBindHost@@UEAAJPEAUIMoniker@@PEAUIBindCtx@@PEAUIBindStatusCallback@@AEBU_GUID@@PEAPEAX@Z`
- size: `263`
- prototype: `int(_AfxBindHost *__hidden this, struct IMoniker *, struct IBindCtx *, struct IBindStatusCallback *, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `8`
- tags: `broker_com_uri`

## callees

- `0x18002e5f0`
- `0x1800a1b1c`
- `0x1800a1b50`
- `0x1800a1bd8`
- `0x1800a1c40`
- `0x1800a1c50`
- `0x1800a2080`
- `0x1800d7010`

## import_xrefs

- `OLE32!CreateBindCtx` at `0x1800a2124`
- `OLE32!CreateBindCtx` at `0x1800a2124`
- `urlmon!RegisterBindStatusCallback` at `0x1800a20ea`
- `urlmon!RegisterBindStatusCallback` at `0x1800a20ea`
- `urlmon!CreateAsyncBindCtx` at `0x1800a2119`
- `urlmon!CreateAsyncBindCtx` at `0x1800a2119`

## pseudocode

```c
__int64 __fastcall _AfxBindHost::MonikerBindToStorage(
        _AfxBindHost *this,
        struct IMoniker *a2,
        struct IBindCtx *a3,
        struct IBindStatusCallback *a4,
        const struct _GUID *a5,
        void **a6)
{
  void **v8; // rdi
  __int64 v9; // r8
  IBindCtx *InterfacePtr; // rax
  HRESULT v11; // ebx
  IBindCtx **v13; // rax
  HRESULT AsyncBindCtx; // eax
  __int64 v15; // rax
  __int64 v16; // r8
  char v17; // [rsp+48h] [rbp+10h] BYREF

  if ( a2 )
  {
    v8 = a6;
    if ( a6 )
    {
      *a6 = 0;
      CIP<IBindCtx,&_GUID const IID_IBindCtx>::CIP<IBindCtx,&_GUID const IID_IBindCtx>(&v17, a2, a3);
      if ( v9 )
      {
        CIP<IBindHost,&_GUID const IID_IBindHost>::operator=(&v17, v9);
        if ( a4 )
        {
          InterfacePtr = (IBindCtx *)_CIP<IBindHost,&_GUID const IID_IBindHost>::GetInterfacePtr(&v17);
          v11 = RegisterBindStatusCallback(InterfacePtr, a4, 0, 0);
          if ( v11 < 0 )
            goto LABEL_6;
        }
      }
      else
      {
        v13 = (IBindCtx **)_CIP<IBindCtx,&_GUID const IID_IBindCtx>::operator&(&v17);
        if ( a4 )
          AsyncBindCtx = CreateAsyncBindCtx(0, a4, 0, v13);
        else
          AsyncBindCtx = CreateBindCtx(0, v13);
        v11 = AsyncBindCtx;
        if ( AsyncBindCtx < 0 )
          goto LABEL_6;
        if ( (unsigned int)_CIP<IBindCtx,&_GUID const IID_IBindCtx>::operator!(&v17) )
        {
          v11 = -2147467259;
LABEL_6:
          CIP<IBindCtx,&_GUID const IID_IBindCtx>::~CIP<IBindCtx,&_GUID const IID_IBindCtx>(&v17);
          return (unsigned int)v11;
        }
      }
      v15 = _CIP<IBindHost,&_GUID const IID_IBindHost>::GetInterfacePtr(&v17);
      v11 = (*(__int64 (__fastcall **)(struct IMoniker *, __int64, _QWORD, const struct _GUID *, void **))(v16 + 72))(
              a2,
              v15,
              0,
              a5,
              v8);
      goto LABEL_6;
    }
  }
  return 2147500035LL;
}

```

## disassembly

```asm
0x1800a2080  mov     [rsp+arg_0], rbx
0x1800a2085  mov     [rsp+arg_10], rsi
0x1800a208a  push    rdi
0x1800a208b  sub     rsp, 30h
0x1800a208f  mov     rbx, r9
0x1800a2092  mov     rsi, rdx
0x1800a2095  test    rdx, rdx
0x1800a2098  jz      loc_1800A2172
0x1800a209e  mov     rdi, [rsp+38h+arg_28]
0x1800a20a3  test    rdi, rdi
0x1800a20a6  jz      loc_1800A2172
0x1800a20ac  lea     rcx, [rsp+38h+arg_8]
0x1800a20b1  mov     qword ptr [rdi], 0
0x1800a20b8  call    ??0?$CIP@UIBindCtx@@$1?IID_IBindCtx@@3U_GUID@@B@@QEAA@XZ; CIP<IBindCtx,&_GUID const IID_IBindCtx>::CIP<IBindCtx,&_GUID const IID_IBindCtx>(void)
0x1800a20bd  lea     rcx, [rsp+38h+arg_8]
0x1800a20c2  test    r8, r8
0x1800a20c5  jz      short loc_1800A2104
0x1800a20c7  mov     rdx, r8
0x1800a20ca  call    ??4?$CIP@UIBindHost@@$1?IID_IBindHost@@3U_GUID@@B@@QEAAAEAV0@PEAUIBindHost@@@Z; CIP<IBindHost,&_GUID const IID_IBindHost>::operator=(IBindHost *)
0x1800a20cf  test    rbx, rbx
0x1800a20d2  jz      short loc_1800A2145
0x1800a20d4  lea     rcx, [rsp+38h+arg_8]
0x1800a20d9  call    ?GetInterfacePtr@?$_CIP@UIBindHost@@$1?IID_IBindHost@@3U_GUID@@B@@QEBAPEAUIBindHost@@XZ; _CIP<IBindHost,&_GUID const IID_IBindHost>::GetInterfacePtr(void)
0x1800a20de  mov     rcx, rax; pBC
0x1800a20e1  xor     r9d, r9d; dwReserved
0x1800a20e4  xor     r8d, r8d; ppBSCBPrev
0x1800a20e7  mov     rdx, rbx; pBSCb
0x1800a20ea  call    cs:__imp_RegisterBindStatusCallback
0x1800a20f0  mov     ebx, eax
0x1800a20f2  test    eax, eax
0x1800a20f4  jns     short loc_1800A2145
0x1800a20f6  lea     rcx, [rsp+38h+arg_8]
0x1800a20fb  call    ??1?$CIP@UIBindCtx@@$1?IID_IBindCtx@@3U_GUID@@B@@QEAA@XZ; CIP<IBindCtx,&_GUID const IID_IBindCtx>::~CIP<IBindCtx,&_GUID const IID_IBindCtx>(void)
0x1800a2100  mov     eax, ebx
0x1800a2102  jmp     short loc_1800A2177
0x1800a2104  call    ??I?$_CIP@UIBindCtx@@$1?IID_IBindCtx@@3U_GUID@@B@@QEAAPEAPEAUIBindCtx@@XZ; _CIP<IBindCtx,&_GUID const IID_IBindCtx>::operator&(void)
0x1800a2109  xor     ecx, ecx; reserved
0x1800a210b  test    rbx, rbx
0x1800a210e  jz      short loc_1800A2121
0x1800a2110  mov     r9, rax; ppBC
0x1800a2113  xor     r8d, r8d; pEFetc
0x1800a2116  mov     rdx, rbx; pBSCb
0x1800a2119  call    cs:__imp_CreateAsyncBindCtx
0x1800a211f  jmp     short loc_1800A212A
0x1800a2121  mov     rdx, rax; ppbc
0x1800a2124  call    cs:__imp_CreateBindCtx
0x1800a212a  mov     ebx, eax
0x1800a212c  test    eax, eax
0x1800a212e  js      short loc_1800A20F6
0x1800a2130  lea     rcx, [rsp+38h+arg_8]
0x1800a2135  call    ??7?$_CIP@UIBindCtx@@$1?IID_IBindCtx@@3U_GUID@@B@@QEAAHXZ; _CIP<IBindCtx,&_GUID const IID_IBindCtx>::operator!(void)
0x1800a213a  test    eax, eax
0x1800a213c  jz      short loc_1800A2145
0x1800a213e  mov     ebx, 80004005h
0x1800a2143  jmp     short loc_1800A20F6
0x1800a2145  mov     r8, [rsi]
0x1800a2148  lea     rcx, [rsp+38h+arg_8]
0x1800a214d  call    ?GetInterfacePtr@?$_CIP@UIBindHost@@$1?IID_IBindHost@@3U_GUID@@B@@QEBAPEAUIBindHost@@XZ; _CIP<IBindHost,&_GUID const IID_IBindHost>::GetInterfacePtr(void)
0x1800a2152  mov     r9, [rsp+38h+arg_20]
0x1800a2157  mov     rdx, rax
0x1800a215a  mov     rax, [r8+48h]
0x1800a215e  mov     rcx, rsi
0x1800a2161  xor     r8d, r8d
0x1800a2164  mov     [rsp+38h+var_18], rdi
0x1800a2169  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a216e  mov     ebx, eax
0x1800a2170  jmp     short loc_1800A20F6
0x1800a2172  mov     eax, 80004003h
0x1800a2177  mov     rbx, [rsp+38h+arg_0]
0x1800a217c  mov     rsi, [rsp+38h+arg_10]
0x1800a2181  add     rsp, 30h
0x1800a2185  pop     rdi
0x1800a2186  retn
```
