# CPropsetPropExchange::ExchangePersistentProp(ushort const *,IUnknown * *,_GUID const &,IUnknown *)

- ea: `0x1800c2f00`
- end: `0x1800c30f4`
- name: `?ExchangePersistentProp@CPropsetPropExchange@@UEAAHPEBGPEAPEAUIUnknown@@AEBU_GUID@@PEAU2@@Z`
- size: `500`
- prototype: `int(CPropsetPropExchange *__hidden this, const unsigned __int16 *, struct IUnknown **, const struct _GUID *, struct IUnknown *)`
- caller_count: `0`
- callee_count: `10`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x18000a150`
- `0x18002feac`
- `0x1800bd2ec`
- `0x1800c2f00`
- `0x1800c3e30`
- `0x1800c3ecc`
- `0x1800c7a00`
- `0x1800d1f6e`
- `0x1800d1fe0`
- `0x1800d7010`

## import_xrefs

- `OLEAUT32!__imp_OleLoadPicture` at `0x1800c3046`
- `OLEAUT32!__imp_OleLoadPicture` at `0x1800c3046`
- `OLE32!OleLoadFromStream` at `0x1800c3015`
- `OLE32!OleLoadFromStream` at `0x1800c3015`
- `api-ms-win-core-com-l2-1-1!ReadClassStm` at `0x1800c2fa6`
- `api-ms-win-core-com-l2-1-1!ReadClassStm` at `0x1800c302c`
- `api-ms-win-core-com-l2-1-1!ReadClassStm` at `0x1800c2fa6`
- `api-ms-win-core-com-l2-1-1!ReadClassStm` at `0x1800c302c`

## pseudocode

```c
_BOOL8 __fastcall CPropsetPropExchange::ExchangePersistentProp(
        CPropsetPropExchange *this,
        const unsigned __int16 *a2,
        struct IUnknown **a3,
        struct _GUID *a4,
        struct IUnknown *a5)
{
  BOOL v9; // ebx
  struct CPropertySection *v10; // rcx
  IStream *StreamFromPropset; // rax
  IStream *v12; // rdi
  unsigned int v14[2]; // [rsp+30h] [rbp-58h] BYREF
  CLSID pclsid; // [rsp+38h] [rbp-50h] BYREF

  if ( *((_DWORD *)this + 2) )
  {
    v9 = 0;
    _AfxRelease(a3);
    *a3 = 0;
    v10 = (struct CPropertySection *)*((_QWORD *)this + 3);
    v14[0] = 0;
    StreamFromPropset = _AfxLoadStreamFromPropset(v10, a2, v14);
    v12 = StreamFromPropset;
    if ( !StreamFromPropset )
      goto LABEL_16;
    pclsid = 0;
    if ( v14[0] == 65 )
    {
      *(_QWORD *)v14 = -16;
      if ( ReadClassStm(StreamFromPropset, &pclsid) >= 0
        && ((int (__fastcall *)(IStream *, _QWORD, __int64))v12->lpVtbl->Seek)(v12, *(_QWORD *)v14, 1) >= 0 )
      {
        if ( !memcmp_0(&pclsid, &CLSID_StdPicture, 0x10u) || !memcmp_0(&pclsid, &_afx_CLSID_StdPicture_V1, 0x10u) )
          v9 = ReadClassStm(v12, &pclsid) >= 0 && OleLoadPicture(v12, 0, 0, a4, (LPVOID *)a3) >= 0;
        else
          v9 = OleLoadFromStream(v12, a4, (LPVOID *)a3) >= 0;
      }
    }
    else if ( v14[0] == 75 )
    {
      *a3 = _AfxCreateObjectFromStreamedPropset(StreamFromPropset, a4);
    }
    ((void (__fastcall *)(IStream *))v12->lpVtbl->Release)(v12);
    if ( !v9 )
    {
LABEL_16:
      if ( a5 )
        return ((__int64 (__fastcall *)(struct IUnknown *, struct _GUID *, struct IUnknown **))a5->lpVtbl->QueryInterface)(
                 a5,
                 a4,
                 a3) >= 0;
    }
  }
  else
  {
    v9 = 1;
    if ( *a3 )
    {
      if ( !(unsigned int)_AfxIsSameUnknownObject(a4, *a3, a5)
        && (!CPropertySection::SetName(*((CPropertySection **)this + 3), ++*((_DWORD *)this + 10), a2)
         || !_AfxSaveObjectInPropset(*a3, *((struct CPropertySection **)this + 3), *((_DWORD *)this + 10))) )
      {
        return 0;
      }
    }
  }
  return v9;
}

```

## disassembly

```asm
0x1800c2f00  push    rbx
0x1800c2f02  push    rbp
0x1800c2f03  push    rsi
0x1800c2f04  push    rdi
0x1800c2f05  push    r14
0x1800c2f07  push    r15
0x1800c2f09  sub     rsp, 58h
0x1800c2f0d  mov     rax, cs:__security_cookie
0x1800c2f14  xor     rax, rsp
0x1800c2f17  mov     [rsp+88h+var_40], rax
0x1800c2f1c  cmp     dword ptr [rcx+8], 0
0x1800c2f20  mov     rbp, r9
0x1800c2f23  mov     r14, [rsp+88h+arg_20]
0x1800c2f2b  mov     rsi, r8
0x1800c2f2e  mov     r15, rdx
0x1800c2f31  mov     rdi, rcx
0x1800c2f34  jz      loc_1800C308E
0x1800c2f3a  mov     rcx, r8; struct IUnknown **
0x1800c2f3d  xor     ebx, ebx
0x1800c2f3f  call    ?_AfxRelease@@YAKPEAPEAUIUnknown@@@Z; _AfxRelease(IUnknown * *)
0x1800c2f44  mov     [rsi], rbx
0x1800c2f47  lea     r8, [rsp+88h+var_58]; unsigned int *
0x1800c2f4c  mov     rcx, [rdi+18h]; this
0x1800c2f50  mov     rdx, r15; unsigned __int16 *
0x1800c2f53  mov     [rsp+88h+var_58], ebx
0x1800c2f57  call    ?_AfxLoadStreamFromPropset@@YAPEAUIStream@@AEAVCPropertySection@@PEBGAEAK@Z; _AfxLoadStreamFromPropset(CPropertySection &,ushort const *,ulong &)
0x1800c2f5c  mov     rdi, rax
0x1800c2f5f  test    rax, rax
0x1800c2f62  jz      loc_1800C306C
0x1800c2f68  cmp     [rsp+88h+var_58], 41h ; 'A'
0x1800c2f6d  xorps   xmm0, xmm0
0x1800c2f70  movups  xmmword ptr [rsp+88h+pclsid.Data1], xmm0
0x1800c2f75  jz      short loc_1800C2F95
0x1800c2f77  cmp     [rsp+88h+var_58], 4Bh ; 'K'
0x1800c2f7c  jnz     loc_1800C3059
0x1800c2f82  mov     rdx, rbp; riid
0x1800c2f85  mov     rcx, rax; struct IStream *
0x1800c2f88  call    ?_AfxCreateObjectFromStreamedPropset@@YAPEAUIUnknown@@PEAUIStream@@AEBU_GUID@@@Z; _AfxCreateObjectFromStreamedPropset(IStream *,_GUID const &)
0x1800c2f8d  mov     [rsi], rax
0x1800c2f90  jmp     loc_1800C3059
0x1800c2f95  lea     rdx, [rsp+88h+pclsid]; pclsid
0x1800c2f9a  mov     qword ptr [rsp+88h+var_58], 0FFFFFFFFFFFFFFF0h
0x1800c2fa3  mov     rcx, rdi; pStm
0x1800c2fa6  call    cs:__imp_ReadClassStm
0x1800c2fac  test    eax, eax
0x1800c2fae  js      loc_1800C3059
0x1800c2fb4  mov     rax, [rdi]
0x1800c2fb7  xor     r9d, r9d
0x1800c2fba  mov     rdx, qword ptr [rsp+88h+var_58]
0x1800c2fbf  mov     rcx, rdi
0x1800c2fc2  mov     rax, [rax+28h]
0x1800c2fc6  lea     r8d, [r9+1]
0x1800c2fca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c2fcf  test    eax, eax
0x1800c2fd1  js      loc_1800C3059
0x1800c2fd7  mov     ebx, 10h
0x1800c2fdc  lea     rdx, CLSID_StdPicture; Buf2
0x1800c2fe3  mov     r8d, ebx; Size
0x1800c2fe6  lea     rcx, [rsp+88h+pclsid]; Buf1
0x1800c2feb  call    memcmp_0
0x1800c2ff0  test    eax, eax
0x1800c2ff2  jz      short loc_1800C3024
0x1800c2ff4  mov     r8d, ebx; Size
0x1800c2ff7  lea     rdx, ?_afx_CLSID_StdPicture_V1@@3U_GUID@@B; Buf2
0x1800c2ffe  lea     rcx, [rsp+88h+pclsid]; Buf1
0x1800c3003  call    memcmp_0
0x1800c3008  test    eax, eax
0x1800c300a  jz      short loc_1800C3024
0x1800c300c  mov     r8, rsi; ppvObj
0x1800c300f  mov     rdx, rbp; iidInterface
0x1800c3012  mov     rcx, rdi; pStm
0x1800c3015  call    cs:__imp_OleLoadFromStream
0x1800c301b  mov     ebx, eax
0x1800c301d  not     ebx
0x1800c301f  shr     ebx, 1Fh
0x1800c3022  jmp     short loc_1800C3059
0x1800c3024  lea     rdx, [rsp+88h+pclsid]; pclsid
0x1800c3029  mov     rcx, rdi; pStm
0x1800c302c  call    cs:__imp_ReadClassStm
0x1800c3032  test    eax, eax
0x1800c3034  js      short loc_1800C3057
0x1800c3036  mov     r9, rbp; riid
0x1800c3039  mov     [rsp+88h+lplpvObj], rsi; lplpvObj
0x1800c303e  xor     r8d, r8d; fRunmode
0x1800c3041  xor     edx, edx; lSize
0x1800c3043  mov     rcx, rdi; lpstream
0x1800c3046  call    cs:__imp_OleLoadPicture
0x1800c304c  test    eax, eax
0x1800c304e  js      short loc_1800C3057
0x1800c3050  mov     ebx, 1
0x1800c3055  jmp     short loc_1800C3059
0x1800c3057  xor     ebx, ebx
0x1800c3059  mov     rax, [rdi]
0x1800c305c  mov     rcx, rdi
0x1800c305f  mov     rax, [rax+10h]
0x1800c3063  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c3068  test    ebx, ebx
0x1800c306a  jnz     short loc_1800C30D8
0x1800c306c  test    r14, r14
0x1800c306f  jz      short loc_1800C30D8
0x1800c3071  mov     rax, [r14]
0x1800c3074  mov     r8, rsi
0x1800c3077  mov     rdx, rbp
0x1800c307a  mov     rcx, r14
0x1800c307d  mov     rax, [rax]
0x1800c3080  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c3085  xor     ebx, ebx
0x1800c3087  test    eax, eax
0x1800c3089  setns   bl
0x1800c308c  jmp     short loc_1800C30D8
0x1800c308e  mov     rdx, [r8]; struct IUnknown *
0x1800c3091  test    rdx, rdx
0x1800c3094  jz      short loc_1800C30D3
0x1800c3096  mov     r8, r14; struct IUnknown *
0x1800c3099  mov     rcx, rbp; struct _GUID *
0x1800c309c  call    ?_AfxIsSameUnknownObject@@YAHAEBU_GUID@@PEAUIUnknown@@1@Z; _AfxIsSameUnknownObject(_GUID const &,IUnknown *,IUnknown *)
0x1800c30a1  test    eax, eax
0x1800c30a3  jnz     short loc_1800C30D3
0x1800c30a5  inc     dword ptr [rdi+28h]
0x1800c30a8  mov     r8, r15; unsigned __int16 *
0x1800c30ab  mov     edx, [rdi+28h]; unsigned int
0x1800c30ae  mov     rcx, [rdi+18h]; this
0x1800c30b2  call    ?SetName@CPropertySection@@QEAAHKPEBG@Z; CPropertySection::SetName(ulong,ushort const *)
0x1800c30b7  test    eax, eax
0x1800c30b9  jz      short loc_1800C30CF
0x1800c30bb  mov     r8d, [rdi+28h]; unsigned int
0x1800c30bf  mov     rdx, [rdi+18h]; struct CPropertySection *
0x1800c30c3  mov     rcx, [rsi]; struct IUnknown *
0x1800c30c6  call    ?_AfxSaveObjectInPropset@@YAHPEAUIUnknown@@AEAVCPropertySection@@K@Z; _AfxSaveObjectInPropset(IUnknown *,CPropertySection &,ulong)
0x1800c30cb  test    eax, eax
0x1800c30cd  jnz     short loc_1800C30D3
0x1800c30cf  xor     ebx, ebx
0x1800c30d1  jmp     short loc_1800C30D8
0x1800c30d3  mov     ebx, 1
0x1800c30d8  mov     eax, ebx
0x1800c30da  mov     rcx, [rsp+88h+var_40]
0x1800c30df  xor     rcx, rsp; StackCookie
0x1800c30e2  call    __security_check_cookie
0x1800c30e7  add     rsp, 58h
0x1800c30eb  pop     r15
0x1800c30ed  pop     r14
0x1800c30ef  pop     rdi
0x1800c30f0  pop     rsi
0x1800c30f1  pop     rbp
0x1800c30f2  pop     rbx
0x1800c30f3  retn
```
