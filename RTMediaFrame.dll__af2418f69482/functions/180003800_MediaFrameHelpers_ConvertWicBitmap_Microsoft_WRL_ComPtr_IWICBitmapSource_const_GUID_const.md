# MediaFrameHelpers::ConvertWicBitmap(Microsoft::WRL::ComPtr<IWICBitmapSource> const &,_GUID const &)

- ea: `0x180003800`
- end: `0x1800039c9`
- name: `?ConvertWicBitmap@MediaFrameHelpers@@SA?AV?$ComPtr@UIWICBitmap@@@WRL@Microsoft@@AEBV?$ComPtr@UIWICBitmapSource@@@34@AEBU_GUID@@@Z`
- size: `457`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180002940`

## callees

- `0x180003800`
- `0x18002749c`
- `0x180052010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000384d`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000384d`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
_QWORD *__fastcall MediaFrameHelpers::ConvertWicBitmap(_QWORD *a1, _QWORD *a2, __int64 a3)
{
  HRESULT v6; // eax
  int v7; // eax
  int v8; // eax
  int v9; // eax
  __int64 v10; // rcx
  LPVOID v11; // rcx
  LPVOID ppv; // [rsp+48h] [rbp-28h] BYREF
  void **pExceptionObject; // [rsp+50h] [rbp-20h] BYREF
  HRESULT v15; // [rsp+58h] [rbp-18h]
  __int128 v16; // [rsp+60h] [rbp-10h]
  __int64 v17; // [rsp+A8h] [rbp+38h] BYREF

  ppv = 0;
  v6 = CoCreateInstance(&CLSID_WICImagingFactory2, 0, 1u, &GUID_ec5ec8a9_c395_4314_9c77_54d7a935ff70, &ppv);
  if ( v6 < 0 )
  {
    pExceptionObject = &_com_error::`vftable';
    v15 = v6;
    v16 = 0;
    throw (_com_error *)&pExceptionObject;
  }
  v17 = 0;
  v7 = (*(__int64 (__fastcall **)(LPVOID, __int64 *))(*(_QWORD *)ppv + 80LL))(ppv, &v17);
  if ( v7 < 0 )
  {
    pExceptionObject = &_com_error::`vftable';
    v15 = v7;
    v16 = 0;
    throw (_com_error *)&pExceptionObject;
  }
  v8 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64, _QWORD, _QWORD, _QWORD, _DWORD))(*(_QWORD *)v17 + 64LL))(
         v17,
         *a2,
         a3,
         0,
         0,
         0,
         0);
  if ( v8 < 0 )
  {
    pExceptionObject = &_com_error::`vftable';
    v15 = v8;
    v16 = 0;
    throw (_com_error *)&pExceptionObject;
  }
  *a1 = 0;
  v9 = (*(__int64 (__fastcall **)(LPVOID, __int64, __int64, _QWORD *))(*(_QWORD *)ppv + 144LL))(ppv, v17, 2, a1);
  if ( v9 < 0 )
  {
    pExceptionObject = &_com_error::`vftable';
    v15 = v9;
    v16 = 0;
    throw (_com_error *)&pExceptionObject;
  }
  v10 = v17;
  if ( v17 )
  {
    v17 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
  }
  v11 = ppv;
  if ( ppv )
  {
    ppv = 0;
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v11 + 16LL))(v11);
  }
  return a1;
}

```

## disassembly

```asm
0x180003800  mov     [rsp-18h+arg_8], rbx
0x180003805  mov     [rsp-18h+arg_10], rsi
0x18000380a  mov     [rsp-18h+arg_0], rcx
0x18000380f  push    rbp
0x180003810  push    rdi
0x180003811  push    r14
0x180003813  mov     rbp, rsp
0x180003816  sub     rsp, 70h
0x18000381a  mov     rdi, r8
0x18000381d  mov     rsi, rdx
0x180003820  mov     rbx, rcx
0x180003823  xor     r14d, r14d
0x180003826  mov     [rbp+var_30], r14d
0x18000382a  mov     [rbp+var_28], r14
0x18000382e  lea     rax, [rbp+var_28]
0x180003832  mov     [rsp+70h+ppv], rax; ppv
0x180003837  lea     r9, _GUID_ec5ec8a9_c395_4314_9c77_54d7a935ff70; riid
0x18000383e  xor     edx, edx; pUnkOuter
0x180003840  mov     r8d, 1; dwClsContext
0x180003846  lea     rcx, CLSID_WICImagingFactory2; rclsid
0x18000384d  call    cs:__imp_CoCreateInstance
0x180003853  test    eax, eax
0x180003855  js      loc_18000392D
0x18000385b  mov     [rbp+arg_18], r14
0x18000385f  mov     rcx, [rbp+var_28]
0x180003863  mov     rax, [rcx]
0x180003866  lea     rdx, [rbp+arg_18]
0x18000386a  mov     rax, [rax+50h]
0x18000386e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003873  test    eax, eax
0x180003875  js      loc_180003954
0x18000387b  mov     rcx, [rbp+arg_18]
0x18000387f  mov     rax, [rcx]
0x180003882  mov     [rsp+70h+var_40], r14d
0x180003887  xorps   xmm0, xmm0
0x18000388a  movsd   [rsp+70h+var_48], xmm0
0x180003890  mov     [rsp+70h+ppv], r14
0x180003895  xor     r9d, r9d
0x180003898  mov     r8, rdi
0x18000389b  mov     rdx, [rsi]
0x18000389e  mov     rax, [rax+40h]
0x1800038a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800038a7  test    eax, eax
0x1800038a9  js      loc_18000397B
0x1800038af  mov     [rbx], r14
0x1800038b2  mov     [rbp+var_30], 1
0x1800038b9  mov     rcx, [rbp+var_28]
0x1800038bd  mov     rax, [rcx]
0x1800038c0  mov     r9, rbx
0x1800038c3  mov     r8d, 2
0x1800038c9  mov     rdx, [rbp+arg_18]
0x1800038cd  mov     rax, [rax+90h]
0x1800038d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800038d9  test    eax, eax
0x1800038db  js      loc_1800039A2
0x1800038e1  mov     rcx, [rbp+arg_18]
0x1800038e5  test    rcx, rcx
0x1800038e8  jz      short loc_1800038FB
0x1800038ea  mov     [rbp+arg_18], r14
0x1800038ee  mov     rax, [rcx]
0x1800038f1  mov     rax, [rax+10h]
0x1800038f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800038fa  nop
0x1800038fb  mov     rcx, [rbp+var_28]
0x1800038ff  test    rcx, rcx
0x180003902  jz      short loc_180003915
0x180003904  mov     [rbp+var_28], r14
0x180003908  mov     rax, [rcx]
0x18000390b  mov     rax, [rax+10h]
0x18000390f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003914  nop
0x180003915  mov     rax, rbx
0x180003918  lea     r11, [rsp+70h+var_s0]
0x18000391d  mov     rbx, [r11+28h]
0x180003921  mov     rsi, [r11+30h]
0x180003925  mov     rsp, r11
0x180003928  pop     r14
0x18000392a  pop     rdi
0x18000392b  pop     rbp
0x18000392c  retn
0x18000392d  lea     rcx, ??_7_com_error@@6B@; const _com_error::`vftable'
0x180003934  mov     [rbp+pExceptionObject], rcx
0x180003938  mov     [rbp+var_18], eax
0x18000393b  xorps   xmm0, xmm0
0x18000393e  movdqu  [rbp+var_10], xmm0
0x180003943  lea     rdx, _TI1?AV_com_error@@; pThrowInfo
0x18000394a  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18000394e  call    _CxxThrowException_0
0x180003954  lea     rcx, ??_7_com_error@@6B@; const _com_error::`vftable'
0x18000395b  mov     [rbp+pExceptionObject], rcx
0x18000395f  mov     [rbp+var_18], eax
0x180003962  xorps   xmm0, xmm0
0x180003965  movdqu  [rbp+var_10], xmm0
0x18000396a  lea     rdx, _TI1?AV_com_error@@; pThrowInfo
0x180003971  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180003975  call    _CxxThrowException_0
0x18000397b  lea     rcx, ??_7_com_error@@6B@; const _com_error::`vftable'
0x180003982  mov     [rbp+pExceptionObject], rcx
0x180003986  mov     [rbp+var_18], eax
0x180003989  xorps   xmm0, xmm0
0x18000398c  movdqu  [rbp+var_10], xmm0
0x180003991  lea     rdx, _TI1?AV_com_error@@; pThrowInfo
0x180003998  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18000399c  call    _CxxThrowException_0
0x1800039a2  lea     rcx, ??_7_com_error@@6B@; const _com_error::`vftable'
0x1800039a9  mov     [rbp+pExceptionObject], rcx
0x1800039ad  mov     [rbp+var_18], eax
0x1800039b0  xorps   xmm0, xmm0
0x1800039b3  movdqu  [rbp+var_10], xmm0
0x1800039b8  lea     rdx, _TI1?AV_com_error@@; pThrowInfo
0x1800039bf  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x1800039c3  call    _CxxThrowException_0
```
