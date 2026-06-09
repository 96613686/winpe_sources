# CBcdElement::FillInProperties(IWbemClassObject *)

- ea: `0x18000ae70`
- end: `0x18000b08b`
- name: `?FillInProperties@CBcdElement@@MEAAJPEAUIWbemClassObject@@@Z`
- size: `539`
- prototype: `__int64 __fastcall(CBcdElement *__hidden this, struct IWbemClassObject *)`
- caller_count: `4`
- callee_count: `4`
- tags: ``

## callers

- `0x18000a820`
- `0x18000aa50`
- `0x18000b2c0`
- `0x18000b590`

## callees

- `0x1800015c4`
- `0x180006bbc`
- `0x18000ae70`
- `0x180015010`

## import_xrefs

- `OLEAUT32!__imp_SysStringLen` at `0x18000af71`
- `OLEAUT32!__imp_SysStringLen` at `0x18000b019`
- `OLEAUT32!__imp_SysStringLen` at `0x18000af71`
- `OLEAUT32!__imp_SysStringLen` at `0x18000b019`
- `OLEAUT32!__imp_VariantInit` at `0x18000aeac`
- `OLEAUT32!__imp_VariantInit` at `0x18000aeb7`
- `OLEAUT32!__imp_VariantInit` at `0x18000aec2`
- `OLEAUT32!__imp_VariantInit` at `0x18000aeac`
- `OLEAUT32!__imp_VariantInit` at `0x18000aeb7`
- `OLEAUT32!__imp_VariantInit` at `0x18000aec2`
- `OLEAUT32!__imp_VariantClear` at `0x18000b060`
- `OLEAUT32!__imp_VariantClear` at `0x18000b06b`
- `OLEAUT32!__imp_VariantClear` at `0x18000b076`
- `OLEAUT32!__imp_VariantClear` at `0x18000b060`
- `OLEAUT32!__imp_VariantClear` at `0x18000b06b`
- `OLEAUT32!__imp_VariantClear` at `0x18000b076`

## string_xrefs

- `0x18000af38`: `StoreFilePath`

## pseudocode

```c
__int64 __fastcall CBcdElement::FillInProperties(CBcdElement *this, struct IWbemClassObject *a2)
{
  int v4; // ebx
  unsigned __int64 v5; // rbx
  size_t v6; // rax
  unsigned __int16 *v7; // rax
  UINT v8; // ebx
  size_t v9; // rax
  unsigned __int16 *v10; // rax
  VARIANTARG v12; // [rsp+40h] [rbp-78h] BYREF
  VARIANTARG pvarg; // [rsp+58h] [rbp-60h] BYREF
  VARIANTARG v14; // [rsp+70h] [rbp-48h] BYREF

  memset(&v14, 0, sizeof(v14));
  memset(&pvarg, 0, sizeof(pvarg));
  memset(&v12, 0, sizeof(v12));
  VariantInit(&v14);
  VariantInit(&pvarg);
  VariantInit(&v12);
  v4 = ((__int64 (__fastcall *)(struct IWbemClassObject *, const wchar_t *, _QWORD, VARIANTARG *, _QWORD, _QWORD))a2->lpVtbl->Get)(
         a2,
         L"Type",
         0,
         &v14,
         0,
         0);
  if ( v4 >= 0 )
  {
    if ( v14.vt != 3 )
      goto LABEL_3;
    *((_DWORD *)this + 6) = v14.lVal;
    v4 = ((__int64 (__fastcall *)(struct IWbemClassObject *, const wchar_t *, _QWORD, VARIANTARG *, _QWORD, _QWORD))a2->lpVtbl->Get)(
           a2,
           L"StoreFilePath",
           0,
           &pvarg,
           0,
           0);
    if ( v4 < 0 )
      goto LABEL_20;
    if ( pvarg.vt != 8 )
    {
LABEL_3:
      v4 = -1063256037;
      goto LABEL_20;
    }
    if ( !pvarg.llVal )
    {
LABEL_7:
      v4 = -2147467261;
      goto LABEL_20;
    }
    v5 = SysStringLen(pvarg.bstrVal) + 1;
    v6 = 2 * v5;
    if ( !is_mul_ok(v5, 2u) )
      v6 = -1;
    v7 = (unsigned __int16 *)operator new(v6, (const struct std::nothrow_t *)&std::nothrow);
    *((_QWORD *)this + 1) = v7;
    if ( !v7 )
    {
LABEL_11:
      v4 = -2147024882;
      goto LABEL_20;
    }
    v4 = StringCchCopyW(v7, v5, pvarg.bstrVal);
    if ( v4 >= 0 )
    {
      v4 = ((__int64 (__fastcall *)(struct IWbemClassObject *, const wchar_t *, _QWORD, VARIANTARG *, _QWORD, _QWORD))a2->lpVtbl->Get)(
             a2,
             L"ObjectId",
             0,
             &v12,
             0,
             0);
      if ( v4 >= 0 )
      {
        if ( v12.vt == 8 )
        {
          if ( !v12.llVal )
            goto LABEL_7;
          v8 = SysStringLen(v12.bstrVal) + 1;
          v9 = 2LL * v8;
          if ( !is_mul_ok(v8, 2u) )
            v9 = -1;
          v10 = (unsigned __int16 *)operator new(v9, (const struct std::nothrow_t *)&std::nothrow);
          *((_QWORD *)this + 2) = v10;
          if ( v10 )
          {
            v4 = StringCchCopyW(v10, v8, v12.bstrVal);
            goto LABEL_20;
          }
          goto LABEL_11;
        }
        goto LABEL_3;
      }
    }
  }
LABEL_20:
  VariantClear(&v12);
  VariantClear(&pvarg);
  VariantClear(&v14);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18000ae70  mov     r11, rsp
0x18000ae73  push    rbx
0x18000ae74  push    rsi
0x18000ae75  push    rdi
0x18000ae76  push    r12
0x18000ae78  sub     rsp, 98h
0x18000ae7f  mov     rdi, rdx
0x18000ae82  mov     rsi, rcx
0x18000ae85  xorps   xmm0, xmm0
0x18000ae88  xor     eax, eax
0x18000ae8a  movups  xmmword ptr [rsp+0B8h+var_48], xmm0
0x18000ae8f  mov     [r11-38h], rax
0x18000ae93  xorps   xmm1, xmm1
0x18000ae96  movups  xmmword ptr [rsp+0B8h+pvarg], xmm1
0x18000ae9b  mov     [r11-50h], rax
0x18000ae9f  movups  xmmword ptr [rsp+0B8h+var_78], xmm0
0x18000aea4  mov     [r11-68h], rax
0x18000aea8  lea     rcx, [r11-48h]; pvarg
0x18000aeac  call    cs:__imp_VariantInit
0x18000aeb2  lea     rcx, [rsp+0B8h+pvarg]; pvarg
0x18000aeb7  call    cs:__imp_VariantInit
0x18000aebd  lea     rcx, [rsp+0B8h+var_78]; pvarg
0x18000aec2  call    cs:__imp_VariantInit
0x18000aec8  mov     rax, [rdi]
0x18000aecb  mov     [rsp+0B8h+var_90], 0
0x18000aed4  mov     [rsp+0B8h+var_98], 0
0x18000aedd  lea     r9, [rsp+0B8h+var_48]
0x18000aee2  xor     r8d, r8d
0x18000aee5  lea     rdx, aType; "Type"
0x18000aeec  mov     rcx, rdi
0x18000aeef  mov     rax, [rax+20h]
0x18000aef3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000aef8  mov     ebx, eax
0x18000aefa  test    eax, eax
0x18000aefc  js      loc_18000B05B
0x18000af02  cmp     word ptr [rsp+0B8h+var_48], 3
0x18000af08  jz      short loc_18000AF14
0x18000af0a  mov     ebx, 0C0A0001Bh
0x18000af0f  jmp     loc_18000B05B
0x18000af14  mov     eax, dword ptr [rsp+0B8h+var_48+8]
0x18000af18  mov     [rsi+18h], eax
0x18000af1b  mov     rax, [rdi]
0x18000af1e  mov     [rsp+0B8h+var_90], 0
0x18000af27  mov     [rsp+0B8h+var_98], 0
0x18000af30  lea     r9, [rsp+0B8h+pvarg]
0x18000af35  xor     r8d, r8d
0x18000af38  lea     rdx, aStorefilepath; "StoreFilePath"
0x18000af3f  mov     rcx, rdi
0x18000af42  mov     rax, [rax+20h]
0x18000af46  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000af4b  mov     ebx, eax
0x18000af4d  test    eax, eax
0x18000af4f  js      loc_18000B05B
0x18000af55  cmp     word ptr [rsp+0B8h+pvarg], 8
0x18000af5b  jnz     short loc_18000AF0A
0x18000af5d  mov     rcx, qword ptr [rsp+0B8h+pvarg+8]; pbstr
0x18000af62  test    rcx, rcx
0x18000af65  jnz     short loc_18000AF71
0x18000af67  mov     ebx, 80004003h
0x18000af6c  jmp     loc_18000B05B
0x18000af71  call    cs:__imp_SysStringLen
0x18000af77  lea     ebx, [rax+1]
0x18000af7a  mov     eax, 2
0x18000af7f  mul     rbx
0x18000af82  mov     r12, 0FFFFFFFFFFFFFFFFh
0x18000af89  cmovb   rax, r12
0x18000af8d  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000af94  mov     rcx, rax; unsigned __int64
0x18000af97  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000af9c  mov     [rsi+8], rax
0x18000afa0  test    rax, rax
0x18000afa3  jnz     short loc_18000AFAF
0x18000afa5  mov     ebx, 8007000Eh
0x18000afaa  jmp     loc_18000B05B
0x18000afaf  mov     r8, qword ptr [rsp+0B8h+pvarg+8]; unsigned __int16 *
0x18000afb4  mov     rdx, rbx; unsigned __int64
0x18000afb7  mov     rcx, rax; unsigned __int16 *
0x18000afba  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000afbf  mov     ebx, eax
0x18000afc1  test    eax, eax
0x18000afc3  js      loc_18000B05B
0x18000afc9  mov     rax, [rdi]
0x18000afcc  mov     [rsp+0B8h+var_90], 0
0x18000afd5  mov     [rsp+0B8h+var_98], 0
0x18000afde  lea     r9, [rsp+0B8h+var_78]
0x18000afe3  xor     r8d, r8d
0x18000afe6  lea     rdx, aObjectid; "ObjectId"
0x18000afed  mov     rcx, rdi
0x18000aff0  mov     rax, [rax+20h]
0x18000aff4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000aff9  mov     ebx, eax
0x18000affb  test    eax, eax
0x18000affd  js      short loc_18000B05B
0x18000afff  cmp     word ptr [rsp+0B8h+var_78], 8
0x18000b005  jnz     loc_18000AF0A
0x18000b00b  mov     rcx, qword ptr [rsp+0B8h+var_78+8]; pbstr
0x18000b010  test    rcx, rcx
0x18000b013  jz      loc_18000AF67
0x18000b019  call    cs:__imp_SysStringLen
0x18000b01f  lea     ebx, [rax+1]
0x18000b022  mov     eax, 2
0x18000b027  mul     rbx
0x18000b02a  cmovb   rax, r12
0x18000b02e  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000b035  mov     rcx, rax; unsigned __int64
0x18000b038  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000b03d  mov     [rsi+10h], rax
0x18000b041  test    rax, rax
0x18000b044  jz      loc_18000AFA5
0x18000b04a  mov     r8, qword ptr [rsp+0B8h+var_78+8]; unsigned __int16 *
0x18000b04f  mov     edx, ebx; unsigned __int64
0x18000b051  mov     rcx, rax; unsigned __int16 *
0x18000b054  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000b059  mov     ebx, eax
0x18000b05b  lea     rcx, [rsp+0B8h+var_78]; pvarg
0x18000b060  call    cs:__imp_VariantClear
0x18000b066  lea     rcx, [rsp+0B8h+pvarg]; pvarg
0x18000b06b  call    cs:__imp_VariantClear
0x18000b071  lea     rcx, [rsp+0B8h+var_48]; pvarg
0x18000b076  call    cs:__imp_VariantClear
0x18000b07c  mov     eax, ebx
0x18000b07e  add     rsp, 98h
0x18000b085  pop     r12
0x18000b087  pop     rdi
0x18000b088  pop     rsi
0x18000b089  pop     rbx
0x18000b08a  retn
0x180013c5b  push    rbp
0x180013c5d  sub     rsp, 40h
0x180013c61  mov     rbp, rdx
0x180013c64  lea     rcx, [rbp+40h]; pvarg
0x180013c68  call    cs:__imp_VariantClear
0x180013c6e  lea     rcx, [rbp+58h]; pvarg
0x180013c72  call    cs:__imp_VariantClear
0x180013c78  lea     rcx, [rbp+70h]; pvarg
0x180013c7c  call    cs:__imp_VariantClear
0x180013c82  nop
0x180013c83  add     rsp, 40h
0x180013c87  pop     rbp
0x180013c88  retn
```
