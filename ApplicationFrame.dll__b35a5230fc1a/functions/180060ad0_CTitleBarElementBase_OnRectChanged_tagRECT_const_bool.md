# CTitleBarElementBase::OnRectChanged(tagRECT const &,bool)

- ea: `0x180060ad0`
- end: `0x180060cf8`
- name: `?OnRectChanged@CTitleBarElementBase@@UEAAXAEBUtagRECT@@_N@Z`
- size: `552`
- prototype: `void(CTitleBarElementBase *__hidden this, const struct tagRECT *, bool)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180031a20`
- `0x180043c30`
- `0x18005be70`
- `0x180060ad0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180060c18`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180060c18`
- `PROPSYS!InitVariantFromDoubleArray` at `0x180060beb`
- `PROPSYS!InitVariantFromDoubleArray` at `0x180060bff`
- `PROPSYS!InitVariantFromDoubleArray` at `0x180060beb`
- `PROPSYS!InitVariantFromDoubleArray` at `0x180060bff`
- `OLEAUT32!__imp_VariantInit` at `0x180060b0b`
- `OLEAUT32!__imp_VariantInit` at `0x180060b15`
- `OLEAUT32!__imp_VariantInit` at `0x180060b0b`
- `OLEAUT32!__imp_VariantInit` at `0x180060b15`
- `OLEAUT32!__imp_VariantClear` at `0x180060cc0`
- `OLEAUT32!__imp_VariantClear` at `0x180060cca`
- `OLEAUT32!__imp_VariantClear` at `0x180060cc0`
- `OLEAUT32!__imp_VariantClear` at `0x180060cca`
- `api-ms-win-ntuser-rectangle-l1-1-0!EqualRect` at `0x180060b73`
- `api-ms-win-ntuser-rectangle-l1-1-0!EqualRect` at `0x180060b73`
- `UIAutomationCore!UiaClientsAreListening` at `0x180060c37`
- `UIAutomationCore!UiaClientsAreListening` at `0x180060c73`
- `UIAutomationCore!UiaClientsAreListening` at `0x180060c37`
- `UIAutomationCore!UiaClientsAreListening` at `0x180060c73`
- `UIAutomationCore!UiaRaiseAutomationPropertyChangedEvent` at `0x180060cb6`
- `UIAutomationCore!UiaRaiseAutomationPropertyChangedEvent` at `0x180060cb6`

## pseudocode

```c
void __fastcall CTitleBarElementBase::OnRectChanged(CTitleBarElementBase *this, const struct tagRECT *a2, char a3)
{
  bool v6; // bl
  LONG *v7; // rdi
  unsigned int v8; // eax
  __m128i v9; // xmm0
  int v10; // eax
  LONG top; // ecx
  LONG right; // edx
  LONG bottom; // r8d
  unsigned int v14; // eax
  DOUBLE v15; // xmm1_8
  __m128i v16; // xmm0
  int v17; // eax
  VARIANT *v18; // r9
  VARIANT *p_prgn; // r8
  VARIANTARG pvar; // [rsp+20h] [rbp-59h] BYREF
  VARIANTARG pvarg; // [rsp+38h] [rbp-41h] BYREF
  PSRWLOCK SRWLock[2]; // [rsp+50h] [rbp-29h] BYREF
  VARIANTARG v23; // [rsp+60h] [rbp-19h] BYREF
  double v24; // [rsp+78h] [rbp-1h]
  VARIANTARG prgn; // [rsp+80h] [rbp+7h] BYREF
  double v26; // [rsp+98h] [rbp+1Fh]

  v6 = 0;
  VariantInit(&pvarg);
  VariantInit(&pvar);
  Microsoft::WRL::Wrappers::SRWLock::LockExclusive(SRWLock, (char *)this + 112);
  v7 = (LONG *)((char *)this + 40);
  v8 = *((_DWORD *)this + 12) - *((_DWORD *)this + 10);
  *(double *)&prgn.vt = (double)*((int *)this + 10);
  prgn.dblVal = (double)*((int *)this + 11);
  v9 = _mm_cvtsi32_si128(v8);
  v10 = *((_DWORD *)this + 13) - *((_DWORD *)this + 11);
  prgn.pRecInfo = (IRecordInfo *)*(_OWORD *)&_mm_cvtepi32_pd(v9);
  v26 = (double)v10;
  if ( !EqualRect((const RECT *)((char *)this + 40), a2) )
  {
    top = a2->top;
    right = a2->right;
    bottom = a2->bottom;
    *v7 = a2->left;
    *((_DWORD *)this + 11) = top;
    *((_DWORD *)this + 12) = right;
    *((_DWORD *)this + 13) = bottom;
    v14 = *((_DWORD *)this + 12) - *v7;
    v15 = (double)*((int *)this + 11);
    *(double *)&v23.vt = (double)*v7;
    v16 = _mm_cvtsi32_si128(v14);
    v17 = *((_DWORD *)this + 13) - *((_DWORD *)this + 11);
    v23.dblVal = v15;
    v23.pRecInfo = (IRecordInfo *)*(_OWORD *)&_mm_cvtepi32_pd(v16);
    v24 = (double)v17;
    v6 = InitVariantFromDoubleArray((const DOUBLE *)&prgn.vt, 4u, &pvarg) >= 0
      && InitVariantFromDoubleArray((const DOUBLE *)&v23.vt, 4u, &pvar) >= 0;
  }
  if ( SRWLock[0] )
    ReleaseSRWLockExclusive(SRWLock[0]);
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_SuppressUIANotificationsInQuietMode>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_SuppressUIANotificationsInQuietMode>::GetImpl'::`2'::impl) )
  {
    if ( a3 && UiaClientsAreListening() && v6 )
    {
      v18 = &v23;
      p_prgn = &prgn;
      v23 = pvar;
      prgn = pvarg;
LABEL_16:
      UiaRaiseAutomationPropertyChangedEvent((IRawElementProviderSimple *)this - 2, 30001, p_prgn, v18);
    }
  }
  else if ( UiaClientsAreListening() && v6 )
  {
    v18 = &prgn;
    p_prgn = &v23;
    prgn = pvar;
    v23 = pvarg;
    goto LABEL_16;
  }
  VariantClear(&pvar);
  VariantClear(&pvarg);
}

```

## disassembly

```asm
0x180060ad0  mov     [rsp-8+arg_10], rbx
0x180060ad5  mov     [rsp-8+arg_18], rsi
0x180060ada  push    rbp
0x180060adb  push    rdi
0x180060adc  push    r12
0x180060ade  push    r14
0x180060ae0  push    r15
0x180060ae2  lea     rbp, [rsp-37h]
0x180060ae7  sub     rsp, 0B0h
0x180060aee  mov     rax, cs:__security_cookie
0x180060af5  xor     rax, rsp
0x180060af8  mov     [rbp+57h+var_30], rax
0x180060afc  mov     rsi, rcx
0x180060aff  mov     r12b, r8b
0x180060b02  lea     rcx, [rbp+57h+pvarg]; pvarg
0x180060b06  mov     r14, rdx
0x180060b09  xor     bl, bl
0x180060b0b  call    cs:__imp_VariantInit
0x180060b11  lea     rcx, [rbp+57h+pvar]; pvarg
0x180060b15  call    cs:__imp_VariantInit
0x180060b1b  lea     rdx, [rsi+70h]
0x180060b1f  lea     rcx, [rbp+57h+SRWLock]
0x180060b23  call    ?LockExclusive@SRWLock@Wrappers@WRL@Microsoft@@SA?AVSyncLockExclusive@Details@234@PEAU_RTL_SRWLOCK@@@Z; Microsoft::WRL::Wrappers::SRWLock::LockExclusive(_RTL_SRWLOCK *)
0x180060b28  movd    xmm0, dword ptr [rsi+28h]
0x180060b2d  lea     rdi, [rsi+28h]
0x180060b31  mov     eax, [rdi+8]
0x180060b34  mov     rdx, r14; lprc2
0x180060b37  sub     eax, [rdi]
0x180060b39  mov     rcx, rdi; lprc1
0x180060b3c  cvtdq2pd xmm0, xmm0
0x180060b40  movsd   [rbp+57h+prgn], xmm0
0x180060b45  movd    xmm0, dword ptr [rsi+2Ch]
0x180060b4a  cvtdq2pd xmm0, xmm0
0x180060b4e  movsd   [rbp+57h+prgn+8], xmm0
0x180060b53  movd    xmm0, eax
0x180060b57  mov     eax, [rsi+34h]
0x180060b5a  sub     eax, [rsi+2Ch]
0x180060b5d  cvtdq2pd xmm0, xmm0
0x180060b61  movsd   [rbp+57h+var_40], xmm0
0x180060b66  movd    xmm0, eax
0x180060b6a  cvtdq2pd xmm0, xmm0
0x180060b6e  movsd   [rbp+57h+var_38], xmm0
0x180060b73  call    cs:__imp_EqualRect
0x180060b79  test    eax, eax
0x180060b7b  jnz     loc_180060C0F
0x180060b81  mov     ecx, [r14+4]
0x180060b85  mov     ebx, 4
0x180060b8a  mov     edx, [r14+8]
0x180060b8e  mov     r8d, [r14+0Ch]
0x180060b92  mov     eax, [r14]
0x180060b95  mov     [rdi], eax
0x180060b97  mov     [rdi+4], ecx
0x180060b9a  lea     rcx, [rbp+57h+prgn]; prgn
0x180060b9e  mov     [rdi+8], edx
0x180060ba1  mov     edx, ebx; cElems
0x180060ba3  mov     [rdi+0Ch], r8d
0x180060ba7  lea     r8, [rbp+57h+pvarg]; pvar
0x180060bab  movd    xmm0, dword ptr [rdi]
0x180060baf  mov     eax, [rsi+30h]
0x180060bb2  sub     eax, [rdi]
0x180060bb4  movd    xmm1, dword ptr [rsi+2Ch]
0x180060bb9  cvtdq2pd xmm0, xmm0
0x180060bbd  cvtdq2pd xmm1, xmm1
0x180060bc1  movsd   [rbp+57h+var_70], xmm0
0x180060bc6  movd    xmm0, eax
0x180060bca  mov     eax, [rsi+34h]
0x180060bcd  sub     eax, [rsi+2Ch]
0x180060bd0  cvtdq2pd xmm0, xmm0
0x180060bd4  movsd   [rbp+57h+var_70+8], xmm1
0x180060bd9  movsd   [rbp+57h+var_60], xmm0
0x180060bde  movd    xmm0, eax
0x180060be2  cvtdq2pd xmm0, xmm0
0x180060be6  movsd   [rbp+57h+var_58], xmm0
0x180060beb  call    cs:__imp_InitVariantFromDoubleArray
0x180060bf1  test    eax, eax
0x180060bf3  js      short loc_180060C0D
0x180060bf5  lea     r8, [rbp+57h+pvar]; pvar
0x180060bf9  mov     edx, ebx; cElems
0x180060bfb  lea     rcx, [rbp+57h+var_70]; prgn
0x180060bff  call    cs:__imp_InitVariantFromDoubleArray
0x180060c05  test    eax, eax
0x180060c07  js      short loc_180060C0D
0x180060c09  mov     bl, 1
0x180060c0b  jmp     short loc_180060C0F
0x180060c0d  xor     bl, bl
0x180060c0f  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x180060c13  test    rcx, rcx
0x180060c16  jz      short loc_180060C1E
0x180060c18  call    cs:__imp_ReleaseSRWLockExclusive
0x180060c1e  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_SuppressUIANotificationsInQuietMode@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_SuppressUIANotificationsInQuietMode@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_SuppressUIANotificationsInQuietMode> `wil::Feature<__WilFeatureTraits_Feature_SuppressUIANotificationsInQuietMode>::GetImpl(void)'::`2'::impl
0x180060c25  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_SuppressUIANotificationsInQuietMode@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_SuppressUIANotificationsInQuietMode>::__private_IsEnabled(void)
0x180060c2a  test    al, al
0x180060c2c  jz      short loc_180060C73
0x180060c2e  test    r12b, r12b
0x180060c31  jz      loc_180060CBC
0x180060c37  call    cs:__imp_UiaClientsAreListening
0x180060c3d  test    eax, eax
0x180060c3f  jz      short loc_180060CBC
0x180060c41  test    bl, bl
0x180060c43  jz      short loc_180060CBC
0x180060c45  movups  xmm0, xmmword ptr [rbp+57h+pvar]
0x180060c49  lea     r9, [rbp+57h+var_70]
0x180060c4d  movups  xmm2, xmmword ptr [rbp+57h+pvarg]
0x180060c51  lea     r8, [rbp+57h+prgn]
0x180060c55  movsd   xmm1, qword ptr [rbp+57h+pvar+10h]
0x180060c5a  movsd   xmm3, qword ptr [rbp+57h+pvarg+10h]
0x180060c5f  movaps  xmmword ptr [rbp+57h+var_70], xmm0
0x180060c63  movaps  xmmword ptr [rbp+57h+prgn], xmm2
0x180060c67  movsd   [rbp+57h+var_60], xmm1
0x180060c6c  movsd   [rbp+57h+var_40], xmm3
0x180060c71  jmp     short loc_180060CAD
0x180060c73  call    cs:__imp_UiaClientsAreListening
0x180060c79  test    eax, eax
0x180060c7b  jz      short loc_180060CBC
0x180060c7d  test    bl, bl
0x180060c7f  jz      short loc_180060CBC
0x180060c81  movups  xmm0, xmmword ptr [rbp+57h+pvar]
0x180060c85  lea     r9, [rbp+57h+prgn]; newValue
0x180060c89  movups  xmm2, xmmword ptr [rbp+57h+pvarg]
0x180060c8d  lea     r8, [rbp+57h+var_70]; oldValue
0x180060c91  movsd   xmm1, qword ptr [rbp+57h+pvar+10h]
0x180060c96  movsd   xmm3, qword ptr [rbp+57h+pvarg+10h]
0x180060c9b  movaps  xmmword ptr [rbp+57h+prgn], xmm0
0x180060c9f  movaps  xmmword ptr [rbp+57h+var_70], xmm2
0x180060ca3  movsd   [rbp+57h+var_40], xmm1
0x180060ca8  movsd   [rbp+57h+var_60], xmm3
0x180060cad  mov     edx, 7531h; id
0x180060cb2  lea     rcx, [rsi-10h]; pProvider
0x180060cb6  call    cs:__imp_UiaRaiseAutomationPropertyChangedEvent
0x180060cbc  lea     rcx, [rbp+57h+pvar]; pvarg
0x180060cc0  call    cs:__imp_VariantClear
0x180060cc6  lea     rcx, [rbp+57h+pvarg]; pvarg
0x180060cca  call    cs:__imp_VariantClear
0x180060cd0  mov     rcx, [rbp+57h+var_30]
0x180060cd4  xor     rcx, rsp; StackCookie
0x180060cd7  call    __security_check_cookie
0x180060cdc  lea     r11, [rsp+0D0h+var_20]
0x180060ce4  mov     rbx, [r11+40h]
0x180060ce8  mov     rsi, [r11+48h]
0x180060cec  mov     rsp, r11
0x180060cef  pop     r15
0x180060cf1  pop     r14
0x180060cf3  pop     r12
0x180060cf5  pop     rdi
0x180060cf6  pop     rbp
0x180060cf7  retn
```
