# XMLNode_GetAttributeValue

- ea: `0x180011550`
- end: `0x1800116af`
- name: `XMLNode_GetAttributeValue`
- size: `351`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config`

## callees

- `0x180001c50`
- `0x180011550`
- `0x180014010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18001158a`
- `OLEAUT32!__imp_SysAllocString` at `0x180011645`
- `OLEAUT32!__imp_SysAllocString` at `0x18001158a`
- `OLEAUT32!__imp_SysAllocString` at `0x180011645`
- `OLEAUT32!__imp_SysFreeString` at `0x18001168c`
- `OLEAUT32!__imp_SysFreeString` at `0x18001168c`
- `OLEAUT32!__imp_VariantClear` at `0x18001165d`
- `OLEAUT32!__imp_VariantClear` at `0x18001165d`

## pseudocode

```c
__int64 __fastcall XMLNode_GetAttributeValue(__int64 *a1, const OLECHAR *a2, BSTR *a3)
{
  OLECHAR *v5; // rsi
  __int64 v6; // rcx
  int v7; // eax
  int v8; // ebx
  BSTR v9; // rax
  __int64 v10; // rcx
  VARIANTARG psz; // [rsp+20h] [rbp-20h] BYREF
  __int64 v13; // [rsp+60h] [rbp+20h] BYREF
  __int64 v14; // [rsp+78h] [rbp+38h] BYREF

  if ( !a1 || !a2 || !a3 )
    return 2147942487LL;
  *a3 = 0;
  v5 = SysAllocString(a2);
  if ( v5 )
  {
    v6 = *a1;
    v13 = 0;
    v7 = (*(__int64 (__fastcall **)(__int64 *, __int64 *))(v6 + 136))(a1, &v13);
    v8 = v7;
    if ( v7 == 1 )
    {
      v8 = -2147467259;
    }
    else if ( v7 >= 0 )
    {
      v14 = 0;
      v8 = (*(__int64 (__fastcall **)(__int64, OLECHAR *, __int64 *))(*(_QWORD *)v13 + 56LL))(v13, v5, &v14);
      if ( v8 == 1 )
        v8 = -2147023728;
      if ( v8 >= 0 )
      {
        memset(&psz, 0, sizeof(psz));
        v8 = (*(__int64 (__fastcall **)(__int64, VARIANTARG *))(*(_QWORD *)v14 + 64LL))(v14, &psz);
        if ( v8 == 1 )
        {
          v8 = -2147467259;
        }
        else if ( v8 >= 0 && psz.vt == 8 )
        {
          v9 = SysAllocString(psz.bstrVal);
          *a3 = v9;
          if ( !v9 )
            v8 = -2147024882;
        }
        VariantClear(&psz);
        OE_SafeReleaseAndNullPtr<CFileStream>(&v14);
      }
      v10 = v13;
      if ( v13 )
      {
        v13 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
      }
    }
    SysFreeString(v5);
  }
  else
  {
    return (unsigned int)-2147024882;
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180011550  mov     [rsp-18h+arg_8], rbx
0x180011555  push    rbp
0x180011556  push    rsi
0x180011557  push    rdi
0x180011558  mov     rbp, rsp
0x18001155b  sub     rsp, 40h
0x18001155f  mov     rdi, r8
0x180011562  mov     rbx, rcx
0x180011565  test    rcx, rcx
0x180011568  jz      loc_18001169D
0x18001156e  test    rdx, rdx
0x180011571  jz      loc_18001169D
0x180011577  test    r8, r8
0x18001157a  jz      loc_18001169D
0x180011580  mov     rcx, rdx; psz
0x180011583  mov     qword ptr [r8], 0
0x18001158a  call    cs:__imp_SysAllocString
0x180011590  mov     rsi, rax
0x180011593  test    rax, rax
0x180011596  jz      loc_180011694
0x18001159c  mov     rcx, [rbx]
0x18001159f  lea     rdx, [rbp+arg_0]
0x1800115a3  mov     [rbp+arg_0], 0
0x1800115ab  mov     rax, [rcx+88h]
0x1800115b2  mov     rcx, rbx
0x1800115b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800115ba  mov     ebx, eax
0x1800115bc  cmp     eax, 1
0x1800115bf  jnz     short loc_1800115CB
0x1800115c1  mov     ebx, 80004005h
0x1800115c6  jmp     loc_180011689
0x1800115cb  test    eax, eax
0x1800115cd  js      loc_180011689
0x1800115d3  mov     rcx, [rbp+arg_0]
0x1800115d7  lea     r8, [rbp+arg_18]
0x1800115db  mov     [rbp+arg_18], 0
0x1800115e3  mov     rdx, rsi
0x1800115e6  mov     rax, [rcx]
0x1800115e9  mov     rax, [rax+38h]
0x1800115ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800115f2  mov     ebx, eax
0x1800115f4  mov     eax, 80070490h
0x1800115f9  cmp     ebx, 1
0x1800115fc  cmovz   ebx, eax
0x1800115ff  test    ebx, ebx
0x180011601  js      short loc_18001166C
0x180011603  mov     rcx, [rbp+arg_18]
0x180011607  lea     rdx, [rbp+psz]
0x18001160b  xor     eax, eax
0x18001160d  xorps   xmm0, xmm0
0x180011610  mov     [rbp+var_10], rax
0x180011614  movups  xmmword ptr [rbp+psz], xmm0
0x180011618  mov     rax, [rcx]
0x18001161b  mov     rax, [rax+40h]
0x18001161f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011624  mov     ebx, eax
0x180011626  cmp     eax, 1
0x180011629  jnz     short loc_180011632
0x18001162b  mov     ebx, 80004005h
0x180011630  jmp     short loc_180011659
0x180011632  test    ebx, ebx
0x180011634  js      short loc_180011659
0x180011636  mov     eax, 8
0x18001163b  cmp     ax, word ptr [rbp+psz]
0x18001163f  jnz     short loc_180011659
0x180011641  mov     rcx, [rbp+psz+8]; psz
0x180011645  call    cs:__imp_SysAllocString
0x18001164b  test    rax, rax
0x18001164e  mov     [rdi], rax
0x180011651  mov     ecx, 8007000Eh
0x180011656  cmovz   ebx, ecx
0x180011659  lea     rcx, [rbp+psz]; pvarg
0x18001165d  call    cs:__imp_VariantClear
0x180011663  lea     rcx, [rbp+arg_18]
0x180011667  call    ??$OE_SafeReleaseAndNullPtr@VCFileStream@@@@YAXAEAPEAVCFileStream@@@Z; OE_SafeReleaseAndNullPtr<CFileStream>(CFileStream * &)
0x18001166c  mov     rcx, [rbp+arg_0]
0x180011670  test    rcx, rcx
0x180011673  jz      short loc_180011689
0x180011675  mov     [rbp+arg_0], 0
0x18001167d  mov     rax, [rcx]
0x180011680  mov     rax, [rax+10h]
0x180011684  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011689  mov     rcx, rsi; bstrString
0x18001168c  call    cs:__imp_SysFreeString
0x180011692  jmp     short loc_180011699
0x180011694  mov     ebx, 8007000Eh
0x180011699  mov     eax, ebx
0x18001169b  jmp     short loc_1800116A2
0x18001169d  mov     eax, 80070057h
0x1800116a2  mov     rbx, [rsp+40h+arg_8]
0x1800116a7  add     rsp, 40h
0x1800116ab  pop     rdi
0x1800116ac  pop     rsi
0x1800116ad  pop     rbp
0x1800116ae  retn
```
