# CBcdObject::FillInProperties(IWbemClassObject *)

- ea: `0x18000b094`
- end: `0x18000b2af`
- name: `?FillInProperties@CBcdObject@@IEAAJPEAUIWbemClassObject@@@Z`
- size: `539`
- prototype: `__int64 __fastcall(CBcdObject *__hidden this, struct IWbemClassObject *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18000a4f0`

## callees

- `0x1800015c4`
- `0x180006bbc`
- `0x18000b094`
- `0x180015010`

## import_xrefs

- `OLEAUT32!__imp_SysStringLen` at `0x18000b195`
- `OLEAUT32!__imp_SysStringLen` at `0x18000b23d`
- `OLEAUT32!__imp_SysStringLen` at `0x18000b195`
- `OLEAUT32!__imp_SysStringLen` at `0x18000b23d`
- `OLEAUT32!__imp_VariantInit` at `0x18000b0d0`
- `OLEAUT32!__imp_VariantInit` at `0x18000b0db`
- `OLEAUT32!__imp_VariantInit` at `0x18000b0e6`
- `OLEAUT32!__imp_VariantInit` at `0x18000b0d0`
- `OLEAUT32!__imp_VariantInit` at `0x18000b0db`
- `OLEAUT32!__imp_VariantInit` at `0x18000b0e6`
- `OLEAUT32!__imp_VariantClear` at `0x18000b284`
- `OLEAUT32!__imp_VariantClear` at `0x18000b28f`
- `OLEAUT32!__imp_VariantClear` at `0x18000b29a`
- `OLEAUT32!__imp_VariantClear` at `0x180013c68`
- `OLEAUT32!__imp_VariantClear` at `0x180013c72`
- `OLEAUT32!__imp_VariantClear` at `0x180013c7c`
- `OLEAUT32!__imp_VariantClear` at `0x18000b284`
- `OLEAUT32!__imp_VariantClear` at `0x18000b28f`
- `OLEAUT32!__imp_VariantClear` at `0x18000b29a`
- `OLEAUT32!__imp_VariantClear` at `0x180013c68`
- `OLEAUT32!__imp_VariantClear` at `0x180013c72`
- `OLEAUT32!__imp_VariantClear` at `0x180013c7c`

## string_xrefs

- `0x18000b15c`: `StoreFilePath`

## pseudocode

```c
__int64 __fastcall CBcdObject::FillInProperties(CBcdObject *this, struct IWbemClassObject *a2)
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
    *((_DWORD *)this + 14) = v14.lVal;
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
    *((_QWORD *)this + 5) = v7;
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
             L"Id",
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
          *((_QWORD *)this + 6) = v10;
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
0x18000b094  mov     r11, rsp
0x18000b097  push    rbx
0x18000b098  push    rsi
0x18000b099  push    rdi
0x18000b09a  push    r12
0x18000b09c  sub     rsp, 98h
0x18000b0a3  mov     rdi, rdx
0x18000b0a6  mov     rsi, rcx
0x18000b0a9  xorps   xmm0, xmm0
0x18000b0ac  xor     eax, eax
0x18000b0ae  movups  xmmword ptr [rsp+0B8h+var_48], xmm0
0x18000b0b3  mov     [r11-38h], rax
0x18000b0b7  xorps   xmm1, xmm1
0x18000b0ba  movups  xmmword ptr [rsp+0B8h+pvarg], xmm1
0x18000b0bf  mov     [r11-50h], rax
0x18000b0c3  movups  xmmword ptr [rsp+0B8h+var_78], xmm0
0x18000b0c8  mov     [r11-68h], rax
0x18000b0cc  lea     rcx, [r11-48h]; pvarg
0x18000b0d0  call    cs:__imp_VariantInit
0x18000b0d6  lea     rcx, [rsp+0B8h+pvarg]; pvarg
0x18000b0db  call    cs:__imp_VariantInit
0x18000b0e1  lea     rcx, [rsp+0B8h+var_78]; pvarg
0x18000b0e6  call    cs:__imp_VariantInit
0x18000b0ec  mov     rax, [rdi]
0x18000b0ef  mov     [rsp+0B8h+var_90], 0
0x18000b0f8  mov     [rsp+0B8h+var_98], 0
0x18000b101  lea     r9, [rsp+0B8h+var_48]
0x18000b106  xor     r8d, r8d
0x18000b109  lea     rdx, aType; "Type"
0x18000b110  mov     rcx, rdi
0x18000b113  mov     rax, [rax+20h]
0x18000b117  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b11c  mov     ebx, eax
0x18000b11e  test    eax, eax
0x18000b120  js      loc_18000B27F
0x18000b126  cmp     word ptr [rsp+0B8h+var_48], 3
0x18000b12c  jz      short loc_18000B138
0x18000b12e  mov     ebx, 0C0A0001Bh
0x18000b133  jmp     loc_18000B27F
0x18000b138  mov     eax, dword ptr [rsp+0B8h+var_48+8]
0x18000b13c  mov     [rsi+38h], eax
0x18000b13f  mov     rax, [rdi]
0x18000b142  mov     [rsp+0B8h+var_90], 0
0x18000b14b  mov     [rsp+0B8h+var_98], 0
0x18000b154  lea     r9, [rsp+0B8h+pvarg]
0x18000b159  xor     r8d, r8d
0x18000b15c  lea     rdx, aStorefilepath; "StoreFilePath"
0x18000b163  mov     rcx, rdi
0x18000b166  mov     rax, [rax+20h]
0x18000b16a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b16f  mov     ebx, eax
0x18000b171  test    eax, eax
0x18000b173  js      loc_18000B27F
0x18000b179  cmp     word ptr [rsp+0B8h+pvarg], 8
0x18000b17f  jnz     short loc_18000B12E
0x18000b181  mov     rcx, qword ptr [rsp+0B8h+pvarg+8]; pbstr
0x18000b186  test    rcx, rcx
0x18000b189  jnz     short loc_18000B195
0x18000b18b  mov     ebx, 80004003h
0x18000b190  jmp     loc_18000B27F
0x18000b195  call    cs:__imp_SysStringLen
0x18000b19b  lea     ebx, [rax+1]
0x18000b19e  mov     eax, 2
0x18000b1a3  mul     rbx
0x18000b1a6  mov     r12, 0FFFFFFFFFFFFFFFFh
0x18000b1ad  cmovb   rax, r12
0x18000b1b1  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000b1b8  mov     rcx, rax; unsigned __int64
0x18000b1bb  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000b1c0  mov     [rsi+28h], rax
0x18000b1c4  test    rax, rax
0x18000b1c7  jnz     short loc_18000B1D3
0x18000b1c9  mov     ebx, 8007000Eh
0x18000b1ce  jmp     loc_18000B27F
0x18000b1d3  mov     r8, qword ptr [rsp+0B8h+pvarg+8]; unsigned __int16 *
0x18000b1d8  mov     rdx, rbx; unsigned __int64
0x18000b1db  mov     rcx, rax; unsigned __int16 *
0x18000b1de  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000b1e3  mov     ebx, eax
0x18000b1e5  test    eax, eax
0x18000b1e7  js      loc_18000B27F
0x18000b1ed  mov     rax, [rdi]
0x18000b1f0  mov     [rsp+0B8h+var_90], 0
0x18000b1f9  mov     [rsp+0B8h+var_98], 0
0x18000b202  lea     r9, [rsp+0B8h+var_78]
0x18000b207  xor     r8d, r8d
0x18000b20a  lea     rdx, aId; "Id"
0x18000b211  mov     rcx, rdi
0x18000b214  mov     rax, [rax+20h]
0x18000b218  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b21d  mov     ebx, eax
0x18000b21f  test    eax, eax
0x18000b221  js      short loc_18000B27F
0x18000b223  cmp     word ptr [rsp+0B8h+var_78], 8
0x18000b229  jnz     loc_18000B12E
0x18000b22f  mov     rcx, qword ptr [rsp+0B8h+var_78+8]; pbstr
0x18000b234  test    rcx, rcx
0x18000b237  jz      loc_18000B18B
0x18000b23d  call    cs:__imp_SysStringLen
0x18000b243  lea     ebx, [rax+1]
0x18000b246  mov     eax, 2
0x18000b24b  mul     rbx
0x18000b24e  cmovb   rax, r12
0x18000b252  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000b259  mov     rcx, rax; unsigned __int64
0x18000b25c  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000b261  mov     [rsi+30h], rax
0x18000b265  test    rax, rax
0x18000b268  jz      loc_18000B1C9
0x18000b26e  mov     r8, qword ptr [rsp+0B8h+var_78+8]; unsigned __int16 *
0x18000b273  mov     edx, ebx; unsigned __int64
0x18000b275  mov     rcx, rax; unsigned __int16 *
0x18000b278  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000b27d  mov     ebx, eax
0x18000b27f  lea     rcx, [rsp+0B8h+var_78]; pvarg
0x18000b284  call    cs:__imp_VariantClear
0x18000b28a  lea     rcx, [rsp+0B8h+pvarg]; pvarg
0x18000b28f  call    cs:__imp_VariantClear
0x18000b295  lea     rcx, [rsp+0B8h+var_48]; pvarg
0x18000b29a  call    cs:__imp_VariantClear
0x18000b2a0  mov     eax, ebx
0x18000b2a2  add     rsp, 98h
0x18000b2a9  pop     r12
0x18000b2ab  pop     rdi
0x18000b2ac  pop     rsi
0x18000b2ad  pop     rbx
0x18000b2ae  retn
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
