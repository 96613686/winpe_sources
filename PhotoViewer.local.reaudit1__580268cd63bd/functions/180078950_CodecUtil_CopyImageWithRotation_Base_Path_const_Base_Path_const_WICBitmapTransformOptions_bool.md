# CodecUtil::CopyImageWithRotation(Base::Path const &,Base::Path const &,WICBitmapTransformOptions,bool *)

- ea: `0x180078950`
- end: `0x180078a11`
- name: `?CopyImageWithRotation@CodecUtil@@YAJAEBVPath@Base@@0W4WICBitmapTransformOptions@@PEA_N@Z`
- size: `193`
- prototype: `__int64 __fastcall(struct IWICImagingFactory *this, const struct Path *, const struct Path *, enum WICBitmapTransformOptions, bool *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18003110c`

## callees

- `0x18000cb74`
- `0x180078950`
- `0x180078a18`

## import_xrefs

- `ole32!CoCreateInstance` at `0x1800789a3`
- `ole32!CoCreateInstance` at `0x1800789a3`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x180078976`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x1800789af`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x180078976`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x1800789af`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CodecUtil::CopyImageWithRotation(
        struct IWICImagingFactory *this,
        LPCWSTR *a2,
        const struct Path *a3,
        CodecUtilPrivate *a4)
{
  unsigned int v4; // edi
  HRESULT Instance; // eax
  int v8; // edx
  unsigned int v9; // ebx
  enum WICBitmapTransformOptions ppv; // [rsp+20h] [rbp-38h]
  enum WICBitmapTransformOptions ppva; // [rsp+20h] [rbp-38h]
  _BYTE v13[40]; // [rsp+30h] [rbp-28h] BYREF
  unsigned int v15; // [rsp+70h] [rbp+18h]
  CodecUtilPrivate *v16; // [rsp+78h] [rbp+20h] BYREF

  v16 = a4;
  try
  {
    v4 = (unsigned int)a3;
    if ( ((unsigned __int8)a3 & 0x18) != 0 )
      Base::Throw((Base *)0x80070057LL, (_DWORD)a2);
    v16 = 0;
    Instance = CoCreateInstance(
                 &CLSID_WICImagingFactory2,
                 0,
                 1u,
                 &GUID_ec5ec8a9_c395_4314_9c77_54d7a935ff70,
                 (LPVOID *)&v16);
    if ( Instance < 0 )
      Base::Throw((Base *)(unsigned int)Instance, v8);
    LOBYTE(ppv) = 0;
    v9 = CodecUtilPrivate::CopyImageWithRotationInternal(v16, this, a2, (const struct Path *)v4, ppv);
    if ( v9 == -2003292334 )
    {
      LOBYTE(ppva) = 1;
      v9 = CodecUtilPrivate::CopyImageWithRotationInternal(v16, this, a2, (const struct Path *)v4, ppva);
    }
    ATL::CComPtrBase<IFreeThreadedItemContainer>::~CComPtrBase<IFreeThreadedItemContainer>(&v16);
  }
  catch ( Base::Exception v13 )
  {
    v15 = Base::Exception::operator long(v13);
    Base::Exception::~Exception((Base::Exception *)v13);
    return v15;
  }
  return v9;
}

```

## disassembly

```asm
0x180078950  mov     [rsp+arg_0], rbx
0x180078955  mov     [rsp+arg_18], r9
0x18007895a  push    rsi
0x18007895b  push    rdi
0x18007895c  push    r14
0x18007895e  sub     rsp, 40h
0x180078962  mov     edi, r8d
0x180078965  mov     rsi, rdx
0x180078968  mov     r14, rcx
0x18007896b  test    dil, 18h
0x18007896f  jz      short loc_18007897C
0x180078971  mov     ecx, 80070057h
0x180078976  call    cs:__imp_?Throw@Base@@YAXJ@Z; Base::Throw(long)
0x18007897c  mov     [rsp+58h+arg_18], 0
0x180078985  lea     rax, [rsp+58h+arg_18]
0x18007898a  mov     qword ptr [rsp+58h+ppv], rax; ppv
0x18007898f  lea     r9, _GUID_ec5ec8a9_c395_4314_9c77_54d7a935ff70; riid
0x180078996  xor     edx, edx; pUnkOuter
0x180078998  lea     r8d, [rdx+1]; dwClsContext
0x18007899c  lea     rcx, CLSID_WICImagingFactory2; rclsid
0x1800789a3  call    cs:__imp_CoCreateInstance
0x1800789a9  test    eax, eax
0x1800789ab  jns     short loc_1800789B5
0x1800789ad  mov     ecx, eax
0x1800789af  call    cs:__imp_?Throw@Base@@YAXJ@Z; Base::Throw(long)
0x1800789b5  mov     byte ptr [rsp+58h+ppv], 0; enum WICBitmapTransformOptions
0x1800789ba  mov     r9d, edi; struct Path *
0x1800789bd  mov     r8, rsi; struct Path *
0x1800789c0  mov     rdx, r14; struct IWICImagingFactory *
0x1800789c3  mov     rcx, [rsp+58h+arg_18]; this
0x1800789c8  call    ?CopyImageWithRotationInternal@CodecUtilPrivate@@YAJPEAUIWICImagingFactory@@AEBVPath@Base@@1W4WICBitmapTransformOptions@@_NPEA_N@Z; CodecUtilPrivate::CopyImageWithRotationInternal(IWICImagingFactory *,Base::Path const &,Base::Path const &,WICBitmapTransformOptions,bool,bool *)
0x1800789cd  mov     ebx, eax
0x1800789cf  cmp     eax, 88982F52h
0x1800789d4  jnz     short loc_1800789F0
0x1800789d6  mov     byte ptr [rsp+58h+ppv], 1; enum WICBitmapTransformOptions
0x1800789db  mov     r9d, edi; struct Path *
0x1800789de  mov     r8, rsi; struct Path *
0x1800789e1  mov     rdx, r14; struct IWICImagingFactory *
0x1800789e4  mov     rcx, [rsp+58h+arg_18]; this
0x1800789e9  call    ?CopyImageWithRotationInternal@CodecUtilPrivate@@YAJPEAUIWICImagingFactory@@AEBVPath@Base@@1W4WICBitmapTransformOptions@@_NPEA_N@Z; CodecUtilPrivate::CopyImageWithRotationInternal(IWICImagingFactory *,Base::Path const &,Base::Path const &,WICBitmapTransformOptions,bool,bool *)
0x1800789ee  mov     ebx, eax
0x1800789f0  lea     rcx, [rsp+58h+arg_18]
0x1800789f5  call    ??1?$CComPtrBase@UIFreeThreadedItemContainer@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IFreeThreadedItemContainer>::~CComPtrBase<IFreeThreadedItemContainer>(void)
0x1800789fa  nop
0x1800789fb  jmp     short loc_180078A01
0x1800789fd  mov     ebx, [rsp+58h+arg_10]
0x180078a01  mov     eax, ebx
0x180078a03  mov     rbx, [rsp+58h+arg_0]
0x180078a08  add     rsp, 40h
0x180078a0c  pop     r14
0x180078a0e  pop     rdi
0x180078a0f  pop     rsi
0x180078a10  retn
```
