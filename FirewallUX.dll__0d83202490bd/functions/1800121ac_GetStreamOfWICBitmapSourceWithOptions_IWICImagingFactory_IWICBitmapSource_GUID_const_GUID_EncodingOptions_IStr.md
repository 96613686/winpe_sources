# GetStreamOfWICBitmapSourceWithOptions(IWICImagingFactory *,IWICBitmapSource *,_GUID const &,_GUID,EncodingOptions,IStream * *)

- ea: `0x1800121ac`
- end: `0x18001238f`
- name: `?GetStreamOfWICBitmapSourceWithOptions@@YAJPEAUIWICImagingFactory@@PEAUIWICBitmapSource@@AEBU_GUID@@U3@W4EncodingOptions@@PEAPEAUIStream@@@Z`
- size: `483`
- prototype: `__int64 __fastcall(void *, __int64, IStream *, __int128 *, __int64, IStream **)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800104e8`

## callees

- `0x18000fa9c`
- `0x1800121ac`
- `0x18002d010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180012212`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180012212`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateMemStream` at `0x18001222e`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateMemStream` at `0x18001222e`

## pseudocode

```c
__int64 __fastcall GetStreamOfWICBitmapSourceWithOptions(
        void *a1,
        __int64 a2,
        IStream *a3,
        __int128 *a4,
        __int64 a5,
        IStream **a6)
{
  IStream **v8; // rdi
  HRESULT v9; // ebx
  IStream *v10; // rcx
  IStream **v11; // rdx
  LPVOID v12; // rcx
  __int128 v14; // [rsp+30h] [rbp-10h] BYREF
  LPVOID ppv; // [rsp+60h] [rbp+20h] BYREF
  IStream *v16; // [rsp+70h] [rbp+30h]

  v16 = a3;
  v8 = a6;
  *a6 = 0;
  ppv = a1;
  if ( a1 )
  {
    (*(void (__fastcall **)(void *))(*(_QWORD *)a1 + 8LL))(a1);
    a1 = ppv;
  }
  if ( a1
    || (v9 = CoCreateInstance(&CLSID_WICImagingFactory2, 0, 1u, &GUID_ec5ec8a9_c395_4314_9c77_54d7a935ff70, &ppv),
        v9 >= 0) )
  {
    v16 = 0;
    v10 = SHCreateMemStream(0, 0);
    v16 = v10;
    if ( v10 )
    {
      a6 = 0;
      v9 = (*(__int64 (__fastcall **)(LPVOID, GUID *, GUID *, IStream ***))(*(_QWORD *)ppv + 64LL))(
             ppv,
             &GUID_ContainerFormatBmp,
             &GUID_VendorMicrosoft,
             &a6);
      if ( v9 < 0
        || (v9 = (*((__int64 (__fastcall **)(IStream **, IStream *, __int64))*a6 + 3))(a6, v16, 2), v9 < 0)
        || (v14 = *a4, v9 = AddFrameToWICBitmap(ppv, a6, a2, &v14), v9 < 0)
        || (v9 = (*((__int64 (__fastcall **)(IStream **))*a6 + 11))(a6), v9 < 0)
        || (v9 = (*(__int64 (__fastcall **)(IStream *, __int64, _QWORD, _QWORD))(*(_QWORD *)v16 + 40LL))(
                   v16,
                   `GetStreamOfWICBitmapSourceWithOptions'::`23'::lnBeginning,
                   0,
                   0),
            v9 < 0) )
      {
        v10 = v16;
      }
      else
      {
        v10 = v16;
        if ( v16 )
        {
          (*(void (__fastcall **)(IStream *))(*(_QWORD *)v16 + 8LL))(v16);
          v10 = v16;
        }
        *v8 = v10;
        v9 = 0;
      }
      v11 = a6;
      if ( a6 )
      {
        a6 = 0;
        (*((void (__fastcall **)(IStream **))*v11 + 2))(v11);
        v10 = v16;
      }
    }
    else
    {
      v9 = -2147024882;
    }
    if ( v10 )
    {
      v16 = 0;
      (*(void (__fastcall **)(IStream *))(*(_QWORD *)v10 + 16LL))(v10);
    }
  }
  v12 = ppv;
  if ( ppv )
  {
    ppv = 0;
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v12 + 16LL))(v12);
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x1800121ac  mov     [rsp-18h+arg_8], rbx
0x1800121b1  mov     [rsp-18h+arg_18], rsi
0x1800121b6  mov     [rsp-18h+arg_10], r8
0x1800121bb  push    rbp
0x1800121bc  push    rdi
0x1800121bd  push    r14
0x1800121bf  mov     rbp, rsp
0x1800121c2  sub     rsp, 40h
0x1800121c6  mov     rsi, r9
0x1800121c9  mov     r14, rdx
0x1800121cc  mov     rdi, [rbp+arg_28]
0x1800121d0  mov     qword ptr [rdi], 0
0x1800121d7  mov     [rbp+arg_0], rcx
0x1800121db  test    rcx, rcx
0x1800121de  jz      short loc_1800121F0
0x1800121e0  mov     rax, [rcx]
0x1800121e3  mov     rax, [rax+8]
0x1800121e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800121ec  mov     rcx, [rbp+arg_0]
0x1800121f0  test    rcx, rcx
0x1800121f3  jnz     short loc_180012222
0x1800121f5  lea     rax, [rbp+arg_0]
0x1800121f9  mov     [rsp+40h+ppv], rax; ppv
0x1800121fe  lea     r9, _GUID_ec5ec8a9_c395_4314_9c77_54d7a935ff70; riid
0x180012205  xor     edx, edx; pUnkOuter
0x180012207  lea     r8d, [rcx+1]; dwClsContext
0x18001220b  lea     rcx, CLSID_WICImagingFactory2; rclsid
0x180012212  call    cs:__imp_CoCreateInstance
0x180012218  mov     ebx, eax
0x18001221a  test    eax, eax
0x18001221c  js      loc_18001235C
0x180012222  mov     [rbp+arg_10], 0
0x18001222a  xor     edx, edx; cbInit
0x18001222c  xor     ecx, ecx; pInit
0x18001222e  call    cs:__imp_SHCreateMemStream
0x180012234  mov     rcx, rax
0x180012237  mov     [rbp+arg_10], rax
0x18001223b  test    rax, rax
0x18001223e  jz      loc_18001233D
0x180012244  mov     [rbp+arg_28], 0
0x18001224c  mov     rcx, [rbp+arg_0]
0x180012250  mov     rax, [rcx]
0x180012253  lea     r9, [rbp+arg_28]
0x180012257  lea     r8, GUID_VendorMicrosoft
0x18001225e  lea     rdx, GUID_ContainerFormatBmp
0x180012265  mov     rax, [rax+40h]
0x180012269  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001226e  mov     ebx, eax
0x180012270  test    eax, eax
0x180012272  js      loc_180012313
0x180012278  mov     rcx, [rbp+arg_28]
0x18001227c  mov     rax, [rcx]
0x18001227f  mov     r8d, 2
0x180012285  mov     rdx, [rbp+arg_10]
0x180012289  mov     rax, [rax+18h]
0x18001228d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012292  mov     ebx, eax
0x180012294  test    eax, eax
0x180012296  js      short loc_180012313
0x180012298  movaps  xmm0, xmmword ptr [rsi]
0x18001229b  movdqa  [rbp+var_10], xmm0
0x1800122a0  lea     r9, [rbp+var_10]
0x1800122a4  mov     r8, r14
0x1800122a7  mov     rdx, [rbp+arg_28]
0x1800122ab  mov     rcx, [rbp+arg_0]
0x1800122af  call    ?AddFrameToWICBitmap@@YAJPEAUIWICImagingFactory@@PEAUIWICBitmapEncoder@@PEAUIWICBitmapSource@@U_GUID@@W4EncodingOptions@@@Z; AddFrameToWICBitmap(IWICImagingFactory *,IWICBitmapEncoder *,IWICBitmapSource *,_GUID,EncodingOptions)
0x1800122b4  mov     ebx, eax
0x1800122b6  test    eax, eax
0x1800122b8  js      short loc_180012313
0x1800122ba  mov     rcx, [rbp+arg_28]
0x1800122be  mov     rax, [rcx]
0x1800122c1  mov     rax, [rax+58h]
0x1800122c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800122ca  mov     ebx, eax
0x1800122cc  test    eax, eax
0x1800122ce  js      short loc_180012313
0x1800122d0  mov     rcx, [rbp+arg_10]
0x1800122d4  mov     rax, [rcx]
0x1800122d7  xor     r9d, r9d
0x1800122da  xor     r8d, r8d
0x1800122dd  mov     rdx, cs:?lnBeginning@?BH@??GetStreamOfWICBitmapSourceWithOptions@@YAJPEAUIWICImagingFactory@@PEAUIWICBitmapSource@@AEBU_GUID@@U4@W4EncodingOptions@@PEAPEAUIStream@@@Z@4T_LARGE_INTEGER@@B; _LARGE_INTEGER const `GetStreamOfWICBitmapSourceWithOptions(IWICImagingFactory *,IWICBitmapSource *,_GUID const &,_GUID,EncodingOptions,IStream * *)'::`23'::lnBeginning
0x1800122e4  mov     rax, [rax+28h]
0x1800122e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800122ed  mov     ebx, eax
0x1800122ef  test    eax, eax
0x1800122f1  js      short loc_180012313
0x1800122f3  mov     rcx, [rbp+arg_10]
0x1800122f7  test    rcx, rcx
0x1800122fa  jz      short loc_18001230C
0x1800122fc  mov     rax, [rcx]
0x1800122ff  mov     rax, [rax+8]
0x180012303  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012308  mov     rcx, [rbp+arg_10]
0x18001230c  mov     [rdi], rcx
0x18001230f  xor     ebx, ebx
0x180012311  jmp     short loc_180012317
0x180012313  mov     rcx, [rbp+arg_10]
0x180012317  mov     rdx, [rbp+arg_28]
0x18001231b  test    rdx, rdx
0x18001231e  jz      short loc_18001233B
0x180012320  mov     [rbp+arg_28], 0
0x180012328  mov     rax, [rdx]
0x18001232b  mov     rcx, rdx
0x18001232e  mov     rax, [rax+10h]
0x180012332  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012337  mov     rcx, [rbp+arg_10]
0x18001233b  jmp     short loc_180012342
0x18001233d  mov     ebx, 8007000Eh
0x180012342  test    rcx, rcx
0x180012345  jz      short loc_18001235C
0x180012347  mov     [rbp+arg_10], 0
0x18001234f  mov     rax, [rcx]
0x180012352  mov     rax, [rax+10h]
0x180012356  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001235b  nop
0x18001235c  mov     rcx, [rbp+arg_0]
0x180012360  test    rcx, rcx
0x180012363  jz      short loc_18001237A
0x180012365  mov     [rbp+arg_0], 0
0x18001236d  mov     rax, [rcx]
0x180012370  mov     rax, [rax+10h]
0x180012374  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012379  nop
0x18001237a  mov     eax, ebx
0x18001237c  mov     rbx, [rsp+40h+arg_8]
0x180012381  mov     rsi, [rsp+40h+arg_18]
0x180012386  add     rsp, 40h
0x18001238a  pop     r14
0x18001238c  pop     rdi
0x18001238d  pop     rbp
0x18001238e  retn
```
