# CodecUtilPrivate::CopyImageWithRotationInternal(IWICImagingFactory *,Base::Path const &,Base::Path const &,WICBitmapTransformOptions,bool,bool *)

- ea: `0x180078a18`
- end: `0x180078cc9`
- name: `?CopyImageWithRotationInternal@CodecUtilPrivate@@YAJPEAUIWICImagingFactory@@AEBVPath@Base@@1W4WICBitmapTransformOptions@@_NPEA_N@Z`
- size: `689`
- prototype: `__int64 __usercall@<rax>(CodecUtilPrivate *__hidden this@<rcx>, struct IWICImagingFactory *@<rdx>, const struct Path *@<r8>, const struct Path *@<r9>, enum WICBitmapTransformOptions, bool, bool *)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180078950`

## callees

- `0x18000cb74`
- `0x180030b10`
- `0x180038b30`
- `0x18003f800`
- `0x180078a18`
- `0x180080010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180078afe`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180078afe`
- `SHLWAPI!SHCreateStreamOnFileEx` at `0x180078a7c`
- `SHLWAPI!SHCreateStreamOnFileEx` at `0x180078b30`
- `SHLWAPI!SHCreateStreamOnFileEx` at `0x180078a7c`
- `SHLWAPI!SHCreateStreamOnFileEx` at `0x180078b30`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x180078a4c`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x180078a88`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x180078ae9`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x180078b3c`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x180078b6d`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x180078b8f`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x180078bf4`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x180078c55`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x180078c72`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x180078a4c`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x180078a88`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x180078ae9`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x180078b3c`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x180078b6d`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x180078b8f`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x180078bf4`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x180078c55`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x180078c72`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall CodecUtilPrivate::CopyImageWithRotationInternal(
        CodecUtilPrivate *this,
        struct IWICImagingFactory *a2,
        LPCWSTR *a3,
        const struct Path *a4,
        enum WICBitmapTransformOptions a5)
{
  unsigned int v5; // r15d
  HRESULT v9; // eax
  int v10; // edx
  int v11; // ebx
  int v12; // eax
  int v13; // edx
  char v14; // si
  HRESULT v15; // eax
  int v16; // edx
  int v17; // eax
  int v18; // edx
  int v19; // eax
  int v20; // edx
  int v21; // eax
  int v22; // edx
  __int64 v23; // rdx
  int v24; // eax
  int v25; // edx
  int v26; // eax
  int v27; // edx
  enum WICBitmapTransformOptions pstmTemplate; // [rsp+20h] [rbp-88h]
  struct IWICBitmapDecoder *v30; // [rsp+30h] [rbp-78h] BYREF
  IStream *v31; // [rsp+38h] [rbp-70h] BYREF
  struct IWICImagingFactory *v32; // [rsp+40h] [rbp-68h] BYREF
  IStream *ppstm; // [rsp+48h] [rbp-60h] BYREF
  __int64 v34; // [rsp+50h] [rbp-58h] BYREF
  _BYTE v35[16]; // [rsp+58h] [rbp-50h] BYREF
  __int128 v36; // [rsp+68h] [rbp-40h] BYREF

  try
  {
    v5 = (unsigned int)a4;
    if ( !this )
      Base::Throw((Base *)0x80004003LL, (_DWORD)a2);
    ppstm = 0;
    v9 = SHCreateStreamOnFileEx((LPCWSTR)a2->lpVtbl, 2u, 0x80u, 0, 0, &ppstm);
    if ( v9 < 0 )
      Base::Throw((Base *)(unsigned int)v9, v10);
    v32 = 0;
    v11 = (*(__int64 (__fastcall **)(CodecUtilPrivate *, IStream *, _QWORD, _QWORD, struct IWICImagingFactory **))(*(_QWORD *)this + 32LL))(
            this,
            ppstm,
            0,
            0,
            &v32);
    if ( v11 < 0 )
      goto LABEL_26;
    v36 = 0;
    v12 = ((__int64 (__fastcall *)(struct IWICImagingFactory *, __int128 *))v32->lpVtbl->CreateDecoderFromFileHandle)(
            v32,
            &v36);
    if ( v12 < 0 )
      Base::Throw((Base *)(unsigned int)v12, v13);
    v31 = 0;
    if ( (unsigned int)_o__wcsicmp(a2->lpVtbl, *a3) )
    {
      v14 = 0;
      v15 = SHCreateStreamOnFileEx(*a3, 0x1001u, 0x80u, 1, 0, &v31);
      if ( v15 >= 0 )
        goto LABEL_17;
      Base::Throw((Base *)(unsigned int)v15, v16);
    }
    v34 = 0;
    v17 = ((__int64 (__fastcall *)(IStream *, GUID *, __int64 *))ppstm->lpVtbl->QueryInterface)(
            ppstm,
            &GUID_8a87781b_39a7_4a1f_aab3_a39b9c34a7d9,
            &v34);
    if ( v17 < 0 )
      Base::Throw((Base *)(unsigned int)v17, v18);
    v19 = (*(__int64 (__fastcall **)(__int64, IStream **))(*(_QWORD *)v34 + 24LL))(v34, &v31);
    if ( v19 < 0 )
      Base::Throw((Base *)(unsigned int)v19, v20);
    v14 = 1;
    ATL::CComPtrBase<IFreeThreadedItemContainer>::~CComPtrBase<IFreeThreadedItemContainer>(&v34);
LABEL_17:
    v30 = 0;
    v11 = (*(__int64 (__fastcall **)(CodecUtilPrivate *, __int128 *, _QWORD, struct IWICBitmapDecoder **))(*(_QWORD *)this + 64LL))(
            this,
            &v36,
            0,
            &v30);
    if ( v11 >= 0 )
    {
      v21 = ((__int64 (__fastcall *)(struct IWICBitmapDecoder *, IStream *, __int64))v30->lpVtbl->QueryCapability)(
              v30,
              v31,
              2);
      if ( v21 < 0 )
        Base::Throw((Base *)(unsigned int)v21, v22);
      LOBYTE(pstmTemplate) = a5;
      CodecUtil::CopyImageWithRotation(this, v32, v30, (struct IWICBitmapEncoder *)v5, pstmTemplate, 0, (bool *)v30);
      ATL::CComPtrBase<IWICBitmapDecoder>::Release(&v32);
      ATL::CComPtrBase<IWICBitmapDecoder>::Release(&v30);
      v23 = 0;
      if ( !v14 )
        goto LABEL_23;
      v24 = ((__int64 (__fastcall *)(IStream *, _QWORD))ppstm->lpVtbl->Commit)(ppstm, 0);
      if ( v24 < 0 )
      {
        Base::Throw((Base *)(unsigned int)v24, v25);
LABEL_23:
        v26 = ((__int64 (__fastcall *)(IStream *, __int64))v31->lpVtbl->Commit)(v31, v23);
        if ( v26 < 0 )
          Base::Throw((Base *)(unsigned int)v26, v27);
      }
    }
    ATL::CComPtrBase<IFreeThreadedItemContainer>::~CComPtrBase<IFreeThreadedItemContainer>(&v30);
    ATL::CComPtrBase<IFreeThreadedItemContainer>::~CComPtrBase<IFreeThreadedItemContainer>(&v31);
LABEL_26:
    ATL::CComPtrBase<IFreeThreadedItemContainer>::~CComPtrBase<IFreeThreadedItemContainer>(&v32);
    ATL::CComPtrBase<IFreeThreadedItemContainer>::~CComPtrBase<IFreeThreadedItemContainer>(&ppstm);
  }
  catch ( Base::Exception v35 )
  {
    LODWORD(v30) = Base::Exception::operator long(v35);
    Base::Exception::~Exception((Base::Exception *)v35);
    return (unsigned int)v30;
  }
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x180078a18  push    rbx
0x180078a1a  push    rsi
0x180078a1b  push    rdi
0x180078a1c  push    r14
0x180078a1e  push    r15
0x180078a20  sub     rsp, 80h
0x180078a27  mov     rax, cs:__security_cookie
0x180078a2e  xor     rax, rsp
0x180078a31  mov     [rsp+0A8h+var_30], rax
0x180078a36  mov     r15d, r9d
0x180078a39  mov     r14, r8
0x180078a3c  mov     rsi, rdx
0x180078a3f  mov     rdi, rcx
0x180078a42  test    rcx, rcx
0x180078a45  jnz     short loc_180078A52
0x180078a47  mov     ecx, 80004003h
0x180078a4c  call    cs:__imp_?Throw@Base@@YAXJ@Z; Base::Throw(long)
0x180078a52  mov     [rsp+0A8h+var_60], 0
0x180078a5b  lea     rax, [rsp+0A8h+var_60]
0x180078a60  mov     [rsp+0A8h+ppstm], rax; ppstm
0x180078a65  mov     [rsp+0A8h+pstmTemplate], 0; pstmTemplate
0x180078a6e  xor     r9d, r9d; fCreate
0x180078a71  lea     edx, [r9+2]; grfMode
0x180078a75  lea     r8d, [rdx+7Eh]; dwAttributes
0x180078a79  mov     rcx, [rsi]; pszFile
0x180078a7c  call    cs:__imp_SHCreateStreamOnFileEx
0x180078a82  test    eax, eax
0x180078a84  jns     short loc_180078A8E
0x180078a86  mov     ecx, eax
0x180078a88  call    cs:__imp_?Throw@Base@@YAXJ@Z; Base::Throw(long)
0x180078a8e  mov     [rsp+0A8h+var_68], 0
0x180078a97  mov     rax, [rdi]
0x180078a9a  lea     rcx, [rsp+0A8h+var_68]
0x180078a9f  mov     [rsp+0A8h+pstmTemplate], rcx
0x180078aa4  xor     r9d, r9d
0x180078aa7  xor     r8d, r8d
0x180078aaa  mov     rdx, [rsp+0A8h+var_60]
0x180078aaf  mov     rcx, rdi
0x180078ab2  mov     rax, [rax+20h]
0x180078ab6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180078abb  mov     ebx, eax
0x180078abd  test    eax, eax
0x180078abf  js      loc_180078C8F
0x180078ac5  xorps   xmm0, xmm0
0x180078ac8  movups  [rsp+0A8h+var_40], xmm0
0x180078acd  mov     rcx, [rsp+0A8h+var_68]
0x180078ad2  mov     rax, [rcx]
0x180078ad5  lea     rdx, [rsp+0A8h+var_40]
0x180078ada  mov     rax, [rax+28h]
0x180078ade  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180078ae3  test    eax, eax
0x180078ae5  jns     short loc_180078AEF
0x180078ae7  mov     ecx, eax
0x180078ae9  call    cs:__imp_?Throw@Base@@YAXJ@Z; Base::Throw(long)
0x180078aef  mov     [rsp+0A8h+var_70], 0
0x180078af8  mov     rdx, [r14]
0x180078afb  mov     rcx, [rsi]
0x180078afe  call    cs:__imp__o__wcsicmp
0x180078b04  test    eax, eax
0x180078b06  jz      short loc_180078B42
0x180078b08  xor     sil, sil
0x180078b0b  lea     rax, [rsp+0A8h+var_70]
0x180078b10  mov     [rsp+0A8h+ppstm], rax; ppstm
0x180078b15  mov     [rsp+0A8h+pstmTemplate], 0; pstmTemplate
0x180078b1e  mov     edx, 1001h; grfMode
0x180078b23  mov     r9d, 1; fCreate
0x180078b29  lea     r8d, [r9+7Fh]; dwAttributes
0x180078b2d  mov     rcx, [r14]; pszFile
0x180078b30  call    cs:__imp_SHCreateStreamOnFileEx
0x180078b36  test    eax, eax
0x180078b38  jns     short loc_180078BA3
0x180078b3a  mov     ecx, eax
0x180078b3c  call    cs:__imp_?Throw@Base@@YAXJ@Z; Base::Throw(long)
0x180078b42  mov     [rsp+0A8h+var_58], 0
0x180078b4b  mov     rcx, [rsp+0A8h+var_60]
0x180078b50  mov     rax, [rcx]
0x180078b53  lea     r8, [rsp+0A8h+var_58]
0x180078b58  lea     rdx, _GUID_8a87781b_39a7_4a1f_aab3_a39b9c34a7d9
0x180078b5f  mov     rax, [rax]
0x180078b62  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180078b67  test    eax, eax
0x180078b69  jns     short loc_180078B73
0x180078b6b  mov     ecx, eax
0x180078b6d  call    cs:__imp_?Throw@Base@@YAXJ@Z; Base::Throw(long)
0x180078b73  mov     rcx, [rsp+0A8h+var_58]
0x180078b78  mov     rax, [rcx]
0x180078b7b  lea     rdx, [rsp+0A8h+var_70]
0x180078b80  mov     rax, [rax+18h]
0x180078b84  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180078b89  test    eax, eax
0x180078b8b  jns     short loc_180078B96
0x180078b8d  mov     ecx, eax
0x180078b8f  call    cs:__imp_?Throw@Base@@YAXJ@Z; Base::Throw(long)
0x180078b95  nop
0x180078b96  mov     sil, 1
0x180078b99  lea     rcx, [rsp+0A8h+var_58]
0x180078b9e  call    ??1?$CComPtrBase@UIFreeThreadedItemContainer@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IFreeThreadedItemContainer>::~CComPtrBase<IFreeThreadedItemContainer>(void)
0x180078ba3  mov     [rsp+0A8h+var_78], 0; bool *
0x180078bac  mov     rax, [rdi]
0x180078baf  lea     r9, [rsp+0A8h+var_78]
0x180078bb4  xor     r8d, r8d
0x180078bb7  lea     rdx, [rsp+0A8h+var_40]
0x180078bbc  mov     rcx, rdi
0x180078bbf  mov     rax, [rax+40h]
0x180078bc3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180078bc8  mov     ebx, eax
0x180078bca  test    eax, eax
0x180078bcc  js      loc_180078C79
0x180078bd2  mov     rcx, [rsp+0A8h+var_78]
0x180078bd7  mov     rax, [rcx]
0x180078bda  mov     r8d, 2
0x180078be0  mov     rdx, [rsp+0A8h+var_70]
0x180078be5  mov     rax, [rax+18h]
0x180078be9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180078bee  test    eax, eax
0x180078bf0  jns     short loc_180078BFA
0x180078bf2  mov     ecx, eax
0x180078bf4  call    cs:__imp_?Throw@Base@@YAXJ@Z; Base::Throw(long)
0x180078bfa  mov     [rsp+0A8h+ppstm], 0; bool
0x180078c03  mov     al, byte ptr [rsp+0A8h+arg_20]
0x180078c0a  mov     byte ptr [rsp+0A8h+pstmTemplate], al; enum WICBitmapTransformOptions
0x180078c0e  mov     r9d, r15d; struct IWICBitmapEncoder *
0x180078c11  mov     r8, [rsp+0A8h+var_78]; struct IWICBitmapDecoder *
0x180078c16  mov     rdx, [rsp+0A8h+var_68]; struct IWICImagingFactory *
0x180078c1b  mov     rcx, rdi; this
0x180078c1e  call    ?CopyImageWithRotation@CodecUtil@@YAXPEAUIWICImagingFactory@@PEAUIWICBitmapDecoder@@PEAUIWICBitmapEncoder@@W4WICBitmapTransformOptions@@_NPEA_N@Z; CodecUtil::CopyImageWithRotation(IWICImagingFactory *,IWICBitmapDecoder *,IWICBitmapEncoder *,WICBitmapTransformOptions,bool,bool *)
0x180078c23  lea     rcx, [rsp+0A8h+var_68]
0x180078c28  call    ?Release@?$CComPtrBase@UIWICBitmapDecoder@@@ATL@@QEAAXXZ; ATL::CComPtrBase<IWICBitmapDecoder>::Release(void)
0x180078c2d  lea     rcx, [rsp+0A8h+var_78]
0x180078c32  call    ?Release@?$CComPtrBase@UIWICBitmapDecoder@@@ATL@@QEAAXXZ; ATL::CComPtrBase<IWICBitmapDecoder>::Release(void)
0x180078c37  xor     edx, edx
0x180078c39  test    sil, sil
0x180078c3c  jz      short loc_180078C5B
0x180078c3e  mov     rcx, [rsp+0A8h+var_60]
0x180078c43  mov     rax, [rcx]
0x180078c46  mov     rax, [rax+40h]
0x180078c4a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180078c4f  test    eax, eax
0x180078c51  jns     short loc_180078C79
0x180078c53  mov     ecx, eax
0x180078c55  call    cs:__imp_?Throw@Base@@YAXJ@Z; Base::Throw(long)
0x180078c5b  mov     rcx, [rsp+0A8h+var_70]
0x180078c60  mov     rax, [rcx]
0x180078c63  mov     rax, [rax+40h]
0x180078c67  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180078c6c  test    eax, eax
0x180078c6e  jns     short loc_180078C79
0x180078c70  mov     ecx, eax
0x180078c72  call    cs:__imp_?Throw@Base@@YAXJ@Z; Base::Throw(long)
0x180078c78  nop
0x180078c79  lea     rcx, [rsp+0A8h+var_78]
0x180078c7e  call    ??1?$CComPtrBase@UIFreeThreadedItemContainer@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IFreeThreadedItemContainer>::~CComPtrBase<IFreeThreadedItemContainer>(void)
0x180078c83  nop
0x180078c84  lea     rcx, [rsp+0A8h+var_70]
0x180078c89  call    ??1?$CComPtrBase@UIFreeThreadedItemContainer@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IFreeThreadedItemContainer>::~CComPtrBase<IFreeThreadedItemContainer>(void)
0x180078c8e  nop
0x180078c8f  lea     rcx, [rsp+0A8h+var_68]
0x180078c94  call    ??1?$CComPtrBase@UIFreeThreadedItemContainer@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IFreeThreadedItemContainer>::~CComPtrBase<IFreeThreadedItemContainer>(void)
0x180078c99  nop
0x180078c9a  lea     rcx, [rsp+0A8h+var_60]
0x180078c9f  call    ??1?$CComPtrBase@UIFreeThreadedItemContainer@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IFreeThreadedItemContainer>::~CComPtrBase<IFreeThreadedItemContainer>(void)
0x180078ca4  nop
0x180078ca5  jmp     short loc_180078CAB
0x180078ca7  mov     ebx, dword ptr [rsp+0A8h+var_78]
0x180078cab  mov     eax, ebx
0x180078cad  mov     rcx, [rsp+0A8h+var_30]
0x180078cb2  xor     rcx, rsp; StackCookie
0x180078cb5  call    __security_check_cookie
0x180078cba  add     rsp, 80h
0x180078cc1  pop     r15
0x180078cc3  pop     r14
0x180078cc5  pop     rdi
0x180078cc6  pop     rsi
0x180078cc7  pop     rbx
0x180078cc8  retn
```
