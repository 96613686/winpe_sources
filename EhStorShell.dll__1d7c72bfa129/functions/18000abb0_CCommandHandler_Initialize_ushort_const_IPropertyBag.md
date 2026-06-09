# CCommandHandler::Initialize(ushort const *,IPropertyBag *)

- ea: `0x18000abb0`
- end: `0x18000ac4e`
- name: `?Initialize@CCommandHandler@@UEAAJPEBGPEAUIPropertyBag@@@Z`
- size: `158`
- prototype: `__int64 __fastcall(CCommandHandler *this, const unsigned __int16 *, struct IPropertyBag *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000abb0`
- `0x18000c010`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x18000ac06`
- `OLEAUT32!__imp_VariantInit` at `0x18000ac06`
- `OLEAUT32!__imp_VariantClear` at `0x18000ac3b`
- `OLEAUT32!__imp_VariantClear` at `0x18000ac3b`
- `SHLWAPI!__imp_StrCmpICW` at `0x18000abee`
- `SHLWAPI!__imp_StrCmpICW` at `0x18000abee`

## pseudocode

```c
__int64 __fastcall CCommandHandler::Initialize(
        CCommandHandler *this,
        const unsigned __int16 *a2,
        struct IPropertyBag *a3)
{
  unsigned int v6; // esi
  unsigned int i; // ebx
  VARIANTARG pvarg; // [rsp+30h] [rbp-48h] BYREF

  v6 = -2147418113;
  *((_DWORD *)this + 18) = 0;
  for ( i = 1; i < 3; ++i )
  {
    if ( !StrCmpICW((LPCWSTR)(&off_18000D360)[4 * i], a2) )
    {
      *((_DWORD *)this + 18) = i;
      v6 = 0;
      VariantInit(&pvarg);
      if ( ((int (__fastcall *)(struct IPropertyBag *, const wchar_t *, VARIANTARG *, _QWORD))a3->lpVtbl->Read)(
             a3,
             L"EvalSiteAsChild",
             &pvarg,
             0) >= 0 )
        *((_DWORD *)this + 8) = 1;
      VariantClear(&pvarg);
      return v6;
    }
  }
  return v6;
}

```

## disassembly

```asm
0x18000abb0  push    rbx
0x18000abb2  push    rbp
0x18000abb3  push    rsi
0x18000abb4  push    rdi
0x18000abb5  push    r14
0x18000abb7  sub     rsp, 50h
0x18000abbb  mov     r14, r8
0x18000abbe  mov     rbp, rdx
0x18000abc1  mov     rdi, rcx
0x18000abc4  mov     esi, 8000FFFFh
0x18000abc9  mov     dword ptr [rcx+48h], 0
0x18000abd0  mov     ebx, 1
0x18000abd5  cmp     ebx, 3
0x18000abd8  jnb     short loc_18000AC41
0x18000abda  mov     ecx, ebx
0x18000abdc  shl     rcx, 5
0x18000abe0  lea     rax, off_18000D360
0x18000abe7  mov     rdx, rbp; pszStr2
0x18000abea  mov     rcx, [rcx+rax]; pszStr1
0x18000abee  call    cs:__imp_StrCmpICW
0x18000abf4  test    eax, eax
0x18000abf6  jz      short loc_18000ABFC
0x18000abf8  inc     ebx
0x18000abfa  jmp     short loc_18000ABD5
0x18000abfc  mov     [rdi+48h], ebx
0x18000abff  xor     esi, esi
0x18000ac01  lea     rcx, [rsp+78h+pvarg]; pvarg
0x18000ac06  call    cs:__imp_VariantInit
0x18000ac0c  nop
0x18000ac0d  mov     rax, [r14]
0x18000ac10  xor     r9d, r9d
0x18000ac13  lea     r8, [rsp+78h+pvarg]
0x18000ac18  lea     rdx, aEvalsiteaschil; "EvalSiteAsChild"
0x18000ac1f  mov     rcx, r14
0x18000ac22  mov     rax, [rax+18h]
0x18000ac26  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ac2b  test    eax, eax
0x18000ac2d  js      short loc_18000AC36
0x18000ac2f  mov     dword ptr [rdi+20h], 1
0x18000ac36  lea     rcx, [rsp+78h+pvarg]; pvarg
0x18000ac3b  call    cs:__imp_VariantClear
0x18000ac41  mov     eax, esi
0x18000ac43  add     rsp, 50h
0x18000ac47  pop     r14
0x18000ac49  pop     rdi
0x18000ac4a  pop     rsi
0x18000ac4b  pop     rbp
0x18000ac4c  pop     rbx
0x18000ac4d  retn
```
