# CWMIBroker::SetBaseClassQualifiers(IWbemClassObject *,int,ushort const *)

- ea: `0x1400034cc`
- end: `0x140003690`
- name: `?SetBaseClassQualifiers@CWMIBroker@@AEAAJPEAUIWbemClassObject@@HPEBG@Z`
- size: `452`
- prototype: `__int64 __fastcall(CWMIBroker *this, struct IWbemClassObject *, int, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1400037f0`

## callees

- `0x140002f30`
- `0x140002fa8`
- `0x140003028`
- `0x1400034cc`
- `0x140017010`

## import_xrefs

- `api-ms-win-core-localization-obsolete-l1-2-0!GetSystemDefaultUILanguage` at `0x140003621`
- `api-ms-win-core-localization-obsolete-l1-2-0!GetSystemDefaultUILanguage` at `0x140003621`
- `OLEAUT32!__imp_SysAllocString` at `0x14000357b`
- `OLEAUT32!__imp_SysAllocString` at `0x14000357b`
- `OLEAUT32!__imp_VariantInit` at `0x1400034ed`
- `OLEAUT32!__imp_VariantInit` at `0x140003569`
- `OLEAUT32!__imp_VariantInit` at `0x1400034ed`
- `OLEAUT32!__imp_VariantInit` at `0x140003569`
- `OLEAUT32!__imp_VariantClear` at `0x1400035cf`
- `OLEAUT32!__imp_VariantClear` at `0x1400035cf`

## pseudocode

```c
__int64 __fastcall CWMIBroker::SetBaseClassQualifiers(
        CWMIBroker *this,
        struct IWbemClassObject *a2,
        int a3,
        const unsigned __int16 *a4)
{
  CWMIBroker *v7; // rbx
  int v8; // edi
  VARIANTARG pvarg; // [rsp+30h] [rbp-30h] BYREF
  VARIANTARG v11; // [rsp+48h] [rbp-18h] BYREF
  CWMIBroker *v12; // [rsp+80h] [rbp+20h] BYREF
  CWMIBroker *v13; // [rsp+88h] [rbp+28h]

  v12 = this;
  VariantInit(&pvarg);
  v12 = 0;
  ((void (__fastcall *)(struct IWbemClassObject *, CWMIBroker **))a2->lpVtbl->GetQualifierSet)(a2, &v12);
  v7 = v12;
  v13 = v12;
  if ( a3 )
  {
    _variant_t::operator=(&pvarg);
    v8 = (*(__int64 (__fastcall **)(CWMIBroker *, const wchar_t *, VARIANTARG *, _QWORD))(*(_QWORD *)v12 + 32LL))(
           v12,
           L"abstract",
           &pvarg,
           0);
    if ( v8 < 0 )
      goto LABEL_14;
    pvarg.lVal = 1033;
    goto LABEL_13;
  }
  memset(&v11, 0, sizeof(v11));
  VariantInit(&v11);
  v11.vt = 8;
  v11.llVal = (LONGLONG)SysAllocString(a4);
  if ( !v11.llVal )
  {
    if ( v7 )
      (*(void (__fastcall **)(CWMIBroker *))(*(_QWORD *)v7 + 16LL))(v7);
    v8 = -2147217402;
    goto LABEL_16;
  }
  v8 = (*(__int64 (__fastcall **)(CWMIBroker *, const wchar_t *, VARIANTARG *, __int64))(*(_QWORD *)v12 + 32LL))(
         v12,
         L"Description",
         &v11,
         130);
  VariantClear(&v11);
  if ( v8 < 0 )
  {
    if ( v7 )
      goto LABEL_15;
    goto LABEL_16;
  }
  _variant_t::operator=(&pvarg);
  v8 = (*(__int64 (__fastcall **)(CWMIBroker *, const wchar_t *, VARIANTARG *, _QWORD))(*(_QWORD *)v12 + 32LL))(
         v12,
         L"AMENDMENT",
         &pvarg,
         0);
  _variant_t::Clear((_variant_t *)&pvarg);
  if ( v8 >= 0 )
  {
    pvarg.lVal = GetSystemDefaultUILanguage();
LABEL_13:
    pvarg.vt = 3;
    v8 = (*(__int64 (__fastcall **)(CWMIBroker *, const wchar_t *, VARIANTARG *, __int64))(*(_QWORD *)v12 + 32LL))(
           v12,
           L"Locale",
           &pvarg,
           1);
  }
LABEL_14:
  if ( v7 )
LABEL_15:
    (*(void (__fastcall **)(CWMIBroker *))(*(_QWORD *)v7 + 16LL))(v7);
LABEL_16:
  v13 = 0;
  _variant_t::~_variant_t(&pvarg);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x1400034cc  mov     [rsp-18h+arg_10], rbx
0x1400034d1  mov     [rsp-18h+arg_0], rcx
0x1400034d6  push    rbp
0x1400034d7  push    rsi
0x1400034d8  push    rdi
0x1400034d9  mov     rbp, rsp
0x1400034dc  sub     rsp, 60h
0x1400034e0  mov     rsi, r9
0x1400034e3  mov     edi, r8d
0x1400034e6  mov     rbx, rdx
0x1400034e9  lea     rcx, [rbp+pvarg]; pvarg
0x1400034ed  call    cs:__imp_VariantInit
0x1400034f3  nop
0x1400034f4  mov     [rbp+arg_0], 0
0x1400034fc  mov     rax, [rbx]
0x1400034ff  lea     rdx, [rbp+arg_0]
0x140003503  mov     rcx, rbx
0x140003506  mov     rax, [rax+18h]
0x14000350a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000350f  mov     rbx, [rbp+arg_0]
0x140003513  mov     [rbp+arg_8], rbx
0x140003517  test    edi, edi
0x140003519  jz      short loc_140003558
0x14000351b  lea     rcx, [rbp+pvarg]
0x14000351f  call    ??4_variant_t@@QEAAAEAV0@_N@Z; _variant_t::operator=(bool)
0x140003524  mov     rcx, [rbp+arg_0]
0x140003528  mov     rax, [rcx]
0x14000352b  xor     r9d, r9d
0x14000352e  lea     r8, [rbp+pvarg]
0x140003532  lea     rdx, aAbstract_0; "abstract"
0x140003539  mov     rax, [rax+20h]
0x14000353d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003542  mov     edi, eax
0x140003544  test    eax, eax
0x140003546  js      loc_140003659
0x14000354c  mov     dword ptr [rbp+pvarg+8], 409h
0x140003553  jmp     loc_14000362D
0x140003558  xorps   xmm0, xmm0
0x14000355b  xor     eax, eax
0x14000355d  movups  xmmword ptr [rbp+var_18], xmm0
0x140003561  mov     qword ptr [rbp+var_18+10h], rax
0x140003565  lea     rcx, [rbp+var_18]; pvarg
0x140003569  call    cs:__imp_VariantInit
0x14000356f  mov     eax, 8
0x140003574  mov     word ptr [rbp+var_18], ax
0x140003578  mov     rcx, rsi; psz
0x14000357b  call    cs:__imp_SysAllocString
0x140003581  mov     qword ptr [rbp+var_18+8], rax
0x140003585  test    rax, rax
0x140003588  jnz     short loc_1400035A8
0x14000358a  test    rbx, rbx
0x14000358d  jz      short loc_14000359E
0x14000358f  mov     rax, [rbx]
0x140003592  mov     rcx, rbx
0x140003595  mov     rax, [rax+10h]
0x140003599  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000359e  mov     edi, 80041006h
0x1400035a3  jmp     loc_14000366D
0x1400035a8  mov     rcx, [rbp+arg_0]
0x1400035ac  mov     rax, [rcx]
0x1400035af  mov     r9d, 82h
0x1400035b5  lea     r8, [rbp+var_18]
0x1400035b9  lea     rdx, aDescription; "Description"
0x1400035c0  mov     rax, [rax+20h]
0x1400035c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400035c9  mov     edi, eax
0x1400035cb  lea     rcx, [rbp+var_18]; pvarg
0x1400035cf  call    cs:__imp_VariantClear
0x1400035d5  test    edi, edi
0x1400035d7  jns     short loc_1400035EB
0x1400035d9  test    rbx, rbx
0x1400035dc  jz      loc_14000366D
0x1400035e2  mov     rcx, [rbx]
0x1400035e5  mov     rax, [rcx+10h]
0x1400035e9  jmp     short loc_140003665
0x1400035eb  lea     rcx, [rbp+pvarg]
0x1400035ef  call    ??4_variant_t@@QEAAAEAV0@_N@Z; _variant_t::operator=(bool)
0x1400035f4  mov     rcx, [rbp+arg_0]
0x1400035f8  mov     rax, [rcx]
0x1400035fb  xor     r9d, r9d
0x1400035fe  lea     r8, [rbp+pvarg]
0x140003602  lea     rdx, aAmendment; "AMENDMENT"
0x140003609  mov     rax, [rax+20h]
0x14000360d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003612  mov     edi, eax
0x140003614  lea     rcx, [rbp+pvarg]; this
0x140003618  call    ?Clear@_variant_t@@QEAAXXZ; _variant_t::Clear(void)
0x14000361d  test    edi, edi
0x14000361f  js      short loc_140003659
0x140003621  call    cs:__imp_GetSystemDefaultUILanguage
0x140003627  movzx   eax, ax
0x14000362a  mov     dword ptr [rbp+pvarg+8], eax
0x14000362d  mov     ecx, 3
0x140003632  mov     word ptr [rbp+pvarg], cx
0x140003636  mov     rcx, [rbp+arg_0]
0x14000363a  mov     rax, [rcx]
0x14000363d  mov     r9d, 1
0x140003643  lea     r8, [rbp+pvarg]
0x140003647  lea     rdx, aLocale; "Locale"
0x14000364e  mov     rax, [rax+20h]
0x140003652  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003657  mov     edi, eax
0x140003659  test    rbx, rbx
0x14000365c  jz      short loc_14000366D
0x14000365e  mov     rax, [rbx]
0x140003661  mov     rax, [rax+10h]
0x140003665  mov     rcx, rbx
0x140003668  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000366d  mov     [rbp+arg_8], 0
0x140003675  lea     rcx, [rbp+pvarg]; this
0x140003679  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x14000367e  mov     eax, edi
0x140003680  mov     rbx, [rsp+60h+arg_10]
0x140003688  add     rsp, 60h
0x14000368c  pop     rdi
0x14000368d  pop     rsi
0x14000368e  pop     rbp
0x14000368f  retn
```
