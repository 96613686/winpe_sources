# XGCTelemetry::InverseMatrixFailed<wchar_t const (&)[25],float &,float &,float &,float &,float &,float &>(wchar_t const (&)[25],float &,float &,float &,float &,float &,float &)

- ea: `0x180018314`
- end: `0x18001840d`
- name: `??$InverseMatrixFailed@AEAY0BJ@$$CB_WAEAMAEAMAEAMAEAMAEAMAEAM@XGCTelemetry@@SAXAEAY0BJ@$$CB_WAEAM11111@Z`
- size: `249`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180047db6`

## callees

- `0x180001010`
- `0x18000182c`
- `0x180011fc8`
- `0x180018314`

## string_xrefs

- `0x18001839e`: `Image brush for XPS path`

## pseudocode

```c
__int64 __fastcall XGCTelemetry::InverseMatrixFailed<wchar_t const (&)[25],float &,float &,float &,float &,float &,float &>(
        __int64 a1,
        int *a2,
        int *a3,
        int *a4,
        int *a5,
        float *a6,
        float *a7)
{
  unsigned int *v10; // r10
  __int64 result; // rax
  int v12; // r8d
  int v13; // r9d
  int v14; // r10d
  int v15; // ecx
  int v16; // ecx
  int v17; // xmm0_4
  int v18; // xmm0_4
  int v19; // [rsp+60h] [rbp-1h] BYREF
  int v20; // [rsp+64h] [rbp+3h] BYREF
  int v21; // [rsp+68h] [rbp+7h] BYREF
  int v22; // [rsp+6Ch] [rbp+Bh] BYREF
  int v23; // [rsp+70h] [rbp+Fh] BYREF
  const wchar_t *v24; // [rsp+78h] [rbp+17h] BYREF
  __int64 v25; // [rsp+B0h] [rbp+4Fh] BYREF

  v25 = a1;
  v10 = *(unsigned int **)(wil::details::static_lazy<XGCLogging>::get(
                             a1,
                             _lambda_5f1e604aa072c864f05a710fd772c3c6_::_lambda_invoker_cdecl_)
                         + 8);
  result = *v10;
  if ( (unsigned int)result > 5 )
  {
    result = tlgKeywordOn(v10, 0x200000000000LL);
    if ( (_BYTE)result )
    {
      v21 = *a4;
      v15 = (int)*a7;
      v23 = *a2;
      LODWORD(v25) = v15;
      v16 = (int)*a6;
      v17 = *a5;
      v24 = L"Image brush for XPS path";
      v20 = v17;
      v18 = *a3;
      v19 = v16;
      v22 = v18;
      return _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
               v14,
               (unsigned int)word_18004EEF2,
               v12,
               v13,
               (__int64)&v24,
               (__int64)&v23,
               (__int64)&v22,
               (__int64)&v21,
               (__int64)&v20,
               (__int64)&v19,
               (__int64)&v25);
    }
  }
  return result;
}

```

## disassembly

```asm
0x180018314  mov     [rsp-8+arg_0], rcx
0x180018319  push    rbp
0x18001831a  push    rbx
0x18001831b  push    rsi
0x18001831c  push    rdi
0x18001831d  lea     rbp, [rsp-27h]
0x180018322  sub     rsp, 88h
0x180018329  mov     rsi, rdx
0x18001832c  mov     rbx, r9
0x18001832f  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_5f1e604aa072c864f05a710fd772c3c6_@@CA@XZ; _lambda_5f1e604aa072c864f05a710fd772c3c6_::_lambda_invoker_cdecl_(void)
0x180018336  mov     rdi, r8
0x180018339  call    ?get@?$static_lazy@VXGCLogging@@@details@wil@@QEAAPEAVXGCLogging@@P6AXXZ@Z; wil::details::static_lazy<XGCLogging>::get(void (*)(void))
0x18001833e  mov     r10, [rax+8]
0x180018342  mov     eax, [r10]
0x180018345  cmp     eax, 5
0x180018348  jbe     loc_180018401
0x18001834e  mov     rdx, 200000000000h
0x180018358  mov     rcx, r10
0x18001835b  call    _tlgKeywordOn
0x180018360  test    al, al
0x180018362  jz      loc_180018401
0x180018368  mov     rax, [rbp+3Fh+arg_30]
0x18001836c  lea     rdx, word_18004EEF2
0x180018373  movss   xmm1, dword ptr [rbx]
0x180018377  movss   [rbp+3Fh+var_38], xmm1
0x18001837c  movss   xmm1, dword ptr [rsi]
0x180018380  cvttss2si rcx, dword ptr [rax]
0x180018385  mov     rax, [rbp+3Fh+arg_28]
0x180018389  movss   [rbp+3Fh+var_30], xmm1
0x18001838e  mov     dword ptr [rbp+3Fh+arg_0], ecx
0x180018391  cvttss2si rcx, dword ptr [rax]
0x180018396  mov     rax, [rbp+3Fh+arg_20]
0x18001839a  movss   xmm0, dword ptr [rax]
0x18001839e  lea     rax, aImageBrushForX; "Image brush for XPS path"
0x1800183a5  mov     [rbp+3Fh+var_28], rax
0x1800183a9  lea     rax, [rbp+3Fh+arg_0]
0x1800183ad  mov     [rsp+0A0h+var_50], rax
0x1800183b2  lea     rax, [rbp+3Fh+var_40]
0x1800183b6  mov     [rsp+0A0h+var_58], rax
0x1800183bb  lea     rax, [rbp+3Fh+var_3C]
0x1800183bf  mov     [rsp+0A0h+var_60], rax
0x1800183c4  lea     rax, [rbp+3Fh+var_38]
0x1800183c8  mov     [rsp+0A0h+var_68], rax
0x1800183cd  lea     rax, [rbp+3Fh+var_34]
0x1800183d1  mov     [rsp+0A0h+var_70], rax
0x1800183d6  lea     rax, [rbp+3Fh+var_30]
0x1800183da  mov     [rsp+0A0h+var_78], rax
0x1800183df  lea     rax, [rbp+3Fh+var_28]
0x1800183e3  movss   [rbp+3Fh+var_3C], xmm0
0x1800183e8  movss   xmm0, dword ptr [rdi]
0x1800183ec  mov     [rbp+3Fh+var_40], ecx
0x1800183ef  mov     rcx, r10
0x1800183f2  mov     [rsp+0A0h+var_80], rax
0x1800183f7  movss   [rbp+3Fh+var_34], xmm0
0x1800183fc  call    ??$Write@U?$_tlgWrapSz@_W@@U?$_tlgWrapperByVal@$03@@U2@U2@U2@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@_W@@AEBU?$_tlgWrapperByVal@$03@@44444@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180018401  add     rsp, 88h
0x180018408  pop     rdi
0x180018409  pop     rsi
0x18001840a  pop     rbx
0x18001840b  pop     rbp
0x18001840c  retn
```
