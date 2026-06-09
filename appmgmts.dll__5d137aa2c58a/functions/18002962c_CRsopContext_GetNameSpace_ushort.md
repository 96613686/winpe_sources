# CRsopContext::GetNameSpace(ushort * *)

- ea: `0x18002962c`
- end: `0x1800297ae`
- name: `?GetNameSpace@CRsopContext@@QEAAJPEAPEAG@Z`
- size: `386`
- prototype: `__int64 __fastcall(CRsopContext *__hidden this, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180011fc0`

## callees

- `0x180002aa0`
- `0x18002962c`
- `0x18002c010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x180029700`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x180029700`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180029738`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180029738`
- `OLEAUT32!__imp_SysAllocString` at `0x18002965e`
- `OLEAUT32!__imp_SysAllocString` at `0x18002966e`
- `OLEAUT32!__imp_SysAllocString` at `0x18002965e`
- `OLEAUT32!__imp_SysAllocString` at `0x18002966e`
- `OLEAUT32!__imp_SysFreeString` at `0x180029763`
- `OLEAUT32!__imp_SysFreeString` at `0x18002976c`
- `OLEAUT32!__imp_SysFreeString` at `0x180029783`
- `OLEAUT32!__imp_SysFreeString` at `0x18002978c`
- `OLEAUT32!__imp_SysFreeString` at `0x180029763`
- `OLEAUT32!__imp_SysFreeString` at `0x18002976c`
- `OLEAUT32!__imp_SysFreeString` at `0x180029783`
- `OLEAUT32!__imp_SysFreeString` at `0x18002978c`
- `OLEAUT32!__imp_VariantInit` at `0x18002964d`
- `OLEAUT32!__imp_VariantInit` at `0x18002964d`
- `OLEAUT32!__imp_VariantClear` at `0x180029776`
- `OLEAUT32!__imp_VariantClear` at `0x180029796`
- `OLEAUT32!__imp_VariantClear` at `0x180029776`
- `OLEAUT32!__imp_VariantClear` at `0x180029796`

## string_xrefs

- `0x180029653`: `__PATH`

## pseudocode

```c
__int64 __fastcall CRsopContext::GetNameSpace(CRsopContext *this, unsigned __int16 **a2)
{
  OLECHAR *v4; // rdi
  OLECHAR *v5; // rax
  OLECHAR *v6; // rbx
  __int64 v7; // rcx
  int v8; // esi
  wchar_t *v9; // rax
  __int64 v10; // rax
  unsigned int v11; // esi
  SIZE_T v12; // rax
  unsigned __int64 v13; // kr00_8
  unsigned __int16 *v14; // rax
  unsigned __int16 *v15; // r11
  VARIANTARG pvarg; // [rsp+40h] [rbp-28h] BYREF
  __int64 v18; // [rsp+58h] [rbp-10h]
  __int64 v19; // [rsp+B0h] [rbp+48h] BYREF

  v18 = 0;
  VariantInit(&pvarg);
  v19 = 0;
  v4 = SysAllocString(L"__PATH");
  v5 = SysAllocString(L"RSOP_PolicySetting");
  v6 = v5;
  if ( v4 && v5 )
  {
    v7 = *((_QWORD *)this + 1);
    v19 = 0;
    v8 = (*(__int64 (__fastcall **)(__int64, OLECHAR *, _QWORD, _QWORD, __int64 *, _QWORD))(*(_QWORD *)v7 + 48LL))(
           v7,
           v5,
           0,
           0,
           &v19,
           0);
    if ( v8 >= 0 )
    {
      v8 = (*(__int64 (__fastcall **)(__int64, OLECHAR *, _QWORD, VARIANTARG *, _QWORD, _QWORD))(*(_QWORD *)v19 + 32LL))(
             v19,
             v4,
             0,
             &pvarg,
             0,
             0);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
      if ( v8 >= 0 )
      {
        v9 = wcschr(pvarg.bstrVal, 0x3Au);
        if ( v9 )
          *v9 = 0;
        v10 = -1;
        do
          ++v10;
        while ( *(_WORD *)(pvarg.llVal + 2 * v10) );
        v11 = v10 + 1;
        v13 = (unsigned int)(v10 + 1);
        v12 = 2 * v13;
        if ( !is_mul_ok(v13, 2u) )
          v12 = -1;
        v14 = (unsigned __int16 *)LocalAlloc(0, v12);
        if ( v14 )
        {
          v8 = StringCchCopyW(v14, v11, pvarg.bstrVal);
          *a2 = v15;
        }
        else
        {
          v8 = -2147024882;
        }
      }
    }
    SysFreeString(v6);
    SysFreeString(v4);
    VariantClear(&pvarg);
    return (unsigned int)v8;
  }
  else
  {
    SysFreeString(v5);
    SysFreeString(v4);
    VariantClear(&pvarg);
    return 2147942414LL;
  }
}

```

## disassembly

```asm
0x18002962c  push    rbp
0x18002962e  push    rbx
0x18002962f  push    rsi
0x180029630  push    rdi
0x180029631  push    r14
0x180029633  push    r15
0x180029635  mov     rbp, rsp
0x180029638  sub     rsp, 68h
0x18002963c  mov     rsi, rcx
0x18002963f  xor     r15d, r15d
0x180029642  lea     rcx, [rbp+pvarg]; pvarg
0x180029646  mov     [rbp+var_10], r15
0x18002964a  mov     r14, rdx
0x18002964d  call    cs:__imp_VariantInit
0x180029653  lea     rcx, psz; "__PATH"
0x18002965a  mov     [rbp+arg_10], r15
0x18002965e  call    cs:__imp_SysAllocString
0x180029664  lea     rcx, aRsopPolicysett; "RSOP_PolicySetting"
0x18002966b  mov     rdi, rax
0x18002966e  call    cs:__imp_SysAllocString
0x180029674  mov     rbx, rax
0x180029677  test    rdi, rdi
0x18002967a  jz      loc_180029780
0x180029680  test    rax, rax
0x180029683  jz      loc_180029780
0x180029689  mov     rcx, [rsi+8]
0x18002968d  lea     rdx, [rbp+arg_10]
0x180029691  mov     [rbp+arg_10], r15
0x180029695  xor     r9d, r9d
0x180029698  mov     [rsp+68h+var_40], r15
0x18002969d  xor     r8d, r8d
0x1800296a0  mov     [rsp+68h+var_48], rdx
0x1800296a5  mov     rdx, rbx
0x1800296a8  mov     rax, [rcx]
0x1800296ab  mov     rax, [rax+30h]
0x1800296af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800296b4  mov     esi, eax
0x1800296b6  test    eax, eax
0x1800296b8  js      loc_180029760
0x1800296be  mov     rcx, [rbp+arg_10]
0x1800296c2  lea     r9, [rbp+pvarg]
0x1800296c6  mov     [rsp+68h+var_40], r15
0x1800296cb  xor     r8d, r8d
0x1800296ce  mov     rdx, rdi
0x1800296d1  mov     [rsp+68h+var_48], r15
0x1800296d6  mov     rax, [rcx]
0x1800296d9  mov     rax, [rax+20h]
0x1800296dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800296e2  mov     rcx, [rbp+arg_10]
0x1800296e6  mov     esi, eax
0x1800296e8  mov     rax, [rcx]
0x1800296eb  mov     rax, [rax+10h]
0x1800296ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800296f4  test    esi, esi
0x1800296f6  js      short loc_180029760
0x1800296f8  mov     rcx, qword ptr [rbp+pvarg+8]; Str
0x1800296fc  lea     edx, [r15+3Ah]; Ch
0x180029700  call    cs:__imp_wcschr
0x180029706  test    rax, rax
0x180029709  jz      short loc_18002970F
0x18002970b  mov     [rax], r15w
0x18002970f  mov     rcx, qword ptr [rbp+pvarg+8]
0x180029713  or      r8, 0FFFFFFFFFFFFFFFFh
0x180029717  mov     rax, r8
0x18002971a  inc     rax
0x18002971d  cmp     [rcx+rax*2], r15w
0x180029722  jnz     short loc_18002971A
0x180029724  lea     esi, [rax+1]
0x180029727  mov     eax, 2
0x18002972c  mul     rsi
0x18002972f  cmovb   rax, r8
0x180029733  xor     ecx, ecx; uFlags
0x180029735  mov     rdx, rax; uBytes
0x180029738  call    cs:__imp_LocalAlloc
0x18002973e  mov     r11, rax
0x180029741  test    rax, rax
0x180029744  jz      short loc_18002975B
0x180029746  mov     r8, qword ptr [rbp+pvarg+8]; unsigned __int16 *
0x18002974a  mov     edx, esi; unsigned __int64
0x18002974c  mov     rcx, rax; unsigned __int16 *
0x18002974f  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180029754  mov     esi, eax
0x180029756  mov     [r14], r11
0x180029759  jmp     short loc_180029760
0x18002975b  mov     esi, 8007000Eh
0x180029760  mov     rcx, rbx; bstrString
0x180029763  call    cs:__imp_SysFreeString
0x180029769  mov     rcx, rdi; bstrString
0x18002976c  call    cs:__imp_SysFreeString
0x180029772  lea     rcx, [rbp+pvarg]; pvarg
0x180029776  call    cs:__imp_VariantClear
0x18002977c  mov     eax, esi
0x18002977e  jmp     short loc_1800297A1
0x180029780  mov     rcx, rbx; bstrString
0x180029783  call    cs:__imp_SysFreeString
0x180029789  mov     rcx, rdi; bstrString
0x18002978c  call    cs:__imp_SysFreeString
0x180029792  lea     rcx, [rbp+pvarg]; pvarg
0x180029796  call    cs:__imp_VariantClear
0x18002979c  mov     eax, 8007000Eh
0x1800297a1  add     rsp, 68h
0x1800297a5  pop     r15
0x1800297a7  pop     r14
0x1800297a9  pop     rdi
0x1800297aa  pop     rsi
0x1800297ab  pop     rbx
0x1800297ac  pop     rbp
0x1800297ad  retn
```
