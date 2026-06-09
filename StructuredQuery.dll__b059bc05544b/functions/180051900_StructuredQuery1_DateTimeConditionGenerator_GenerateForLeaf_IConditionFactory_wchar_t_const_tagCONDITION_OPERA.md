# StructuredQuery1::DateTimeConditionGenerator::GenerateForLeaf(IConditionFactory *,wchar_t const *,tagCONDITION_OPERATION,wchar_t const *,wchar_t const *,wchar_t const *,IRichChunk *,IRichChunk *,IRichChunk *,int,int *,ICondition * *)

- ea: `0x180051900`
- end: `0x180051a47`
- name: `?GenerateForLeaf@DateTimeConditionGenerator@StructuredQuery1@@UEAAJPEAUIConditionFactory@@PEB_WW4tagCONDITION_OPERATION@@111PEAUIRichChunk@@33HPEAHPEAPEAUICondition@@@Z`
- size: `327`
- prototype: `__int64 __fastcall(StructuredQuery1::DateTimeConditionGenerator *__hidden this, struct IConditionFactory *, const wchar_t *, enum tagCONDITION_OPERATION, const wchar_t *, const wchar_t *, const wchar_t *, struct IRichChunk *, struct IRichChunk *, struct IRichChunk *, int, SIZE_T cb, struct ICondition **pv)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180015a40`
- `0x18003bed0`
- `0x180051900`
- `0x18008b010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180051a06`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008abb0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008abc0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180051a06`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008abb0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008abc0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18008ab37`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18008ab37`

## pseudocode

```c
__int64 __fastcall StructuredQuery1::DateTimeConditionGenerator::GenerateForLeaf(
        StructuredQuery1::DateTimeConditionGenerator *this,
        struct IConditionFactory *a2,
        const wchar_t *a3,
        unsigned int a4,
        const wchar_t *a5,
        const wchar_t *a6,
        const wchar_t *a7,
        struct IRichChunk *a8,
        struct IRichChunk *a9,
        struct IRichChunk *a10,
        int a11,
        _DWORD *cb,
        struct ICondition **pv)
{
  _DWORD *v13; // rsi
  struct ICondition **v15; // rdi
  __int64 v18; // rdx
  __int64 v19; // rcx
  int v20; // ebx
  struct ICondition **v21; // r14
  struct IConditionFactoryVtbl *lpVtbl; // rax
  int v24; // eax
  struct ICondition **v25; // r12
  _QWORD *v26; // rax
  struct ICondition *v27; // [rsp+60h] [rbp-21h] BYREF
  LPVOID v28[11]; // [rsp+68h] [rbp-19h] BYREF

  v13 = cb;
  v15 = pv;
  v27 = 0;
  if ( cb && pv )
  {
    if ( a3 )
    {
      pv = 0;
      v20 = _AllocString<CTCoAllocPolicy>((__int64)this, (__int64)a2, (const size_t *)a6, &pv);
      if ( v20 >= 0 )
      {
        v21 = pv;
        if ( a7 )
        {
          pv = 0;
          v20 = _AllocString<CTCoAllocPolicy>(v19, v18, (const size_t *)a7, &pv);
          if ( v20 >= 0 )
          {
            LOWORD(v28[0]) = 4127;
            memset((char *)v28 + 2, 0, 22);
            cb = 0;
            LODWORD(v28[1]) = 2;
            v24 = ULongLongMult(2u, 8u, (unsigned __int64 *)&cb);
            v25 = pv;
            v20 = v24;
            if ( v24 >= 0 )
            {
              v26 = CoTaskMemAlloc((SIZE_T)cb);
              v28[2] = v26;
              if ( v26 )
              {
                *v26 = v21;
                *((_QWORD *)v28[2] + 1) = v25;
                v20 = ((__int64 (__fastcall *)(struct IConditionFactory *, const wchar_t *, _QWORD, const wchar_t *, LPVOID *, struct IRichChunk *, struct IRichChunk *, struct IRichChunk *, int, struct ICondition **))a2->lpVtbl->MakeLeaf)(
                        a2,
                        a3,
                        a4,
                        a5,
                        v28,
                        a8,
                        a9,
                        a10,
                        1,
                        &v27);
                CoTaskMemFree(v28[2]);
              }
              else
              {
                v20 = -2147024882;
              }
            }
            CoTaskMemFree(v25);
          }
        }
        else
        {
          LOWORD(v28[0]) = 31;
          *(_OWORD *)((char *)v28 + 2) = 0;
          lpVtbl = a2->lpVtbl;
          *(_OWORD *)&v28[1] = (unsigned __int64)pv;
          v20 = ((__int64 (__fastcall *)(struct IConditionFactory *, const wchar_t *, _QWORD, const wchar_t *, LPVOID *, struct IRichChunk *, struct IRichChunk *, struct IRichChunk *, int, struct ICondition **))lpVtbl->MakeLeaf)(
                  a2,
                  a3,
                  a4,
                  a5,
                  v28,
                  a8,
                  a9,
                  a10,
                  1,
                  &v27);
        }
        CoTaskMemFree(v21);
      }
    }
    else
    {
      v20 = 1;
    }
  }
  else
  {
    v20 = -2147467261;
    if ( !cb )
      goto LABEL_10;
  }
  *v13 = 0;
LABEL_10:
  if ( v15 )
    *v15 = v27;
  return (unsigned int)v20;
}

```

## disassembly

```asm
0x180051900  mov     [rsp-8+arg_18], r9d
0x180051905  push    rbp
0x180051906  push    rbx
0x180051907  push    rsi
0x180051908  push    rdi
0x180051909  push    r12
0x18005190b  push    r13
0x18005190d  push    r14
0x18005190f  push    r15
0x180051911  lea     rbp, [rsp-7]
0x180051916  sub     rsp, 88h
0x18005191d  mov     rsi, [rbp+3Fh+cb]
0x180051924  mov     r12d, r9d
0x180051927  mov     rdi, [rbp+3Fh+pv]
0x18005192e  mov     r15, r8
0x180051931  mov     [rbp+3Fh+var_60], 0
0x180051939  mov     r13, rdx
0x18005193c  test    rsi, rsi
0x18005193f  jz      loc_180051A0E
0x180051945  test    rdi, rdi
0x180051948  jz      loc_180051A0E
0x18005194e  test    r8, r8
0x180051951  jz      loc_180051A40
0x180051957  mov     r8, [rbp+3Fh+arg_28]
0x18005195b  lea     r9, [rbp+3Fh+pv]
0x180051962  mov     [rbp+3Fh+pv], 0
0x18005196d  call    ??$_AllocString@VCTCoAllocPolicy@@@@YAJPEAXKPEB_WPEAPEA_W@Z; _AllocString<CTCoAllocPolicy>(void *,ulong,wchar_t const *,wchar_t * *)
0x180051972  mov     ebx, eax
0x180051974  test    eax, eax
0x180051976  js      loc_180051A18
0x18005197c  mov     r8, [rbp+3Fh+arg_30]
0x180051980  mov     r14, [rbp+3Fh+pv]
0x180051987  test    r8, r8
0x18005198a  jnz     loc_18008AACC
0x180051990  mov     rdx, [rbp+3Fh+arg_40]
0x180051997  lea     eax, [r8+1Fh]
0x18005199b  mov     r9, [rbp+3Fh+arg_20]
0x18005199f  lea     rcx, [rbp+3Fh+var_60]
0x1800519a3  mov     [rsp+0C0h+var_78], rcx
0x1800519a8  xorps   xmm0, xmm0
0x1800519ab  mov     rcx, [rbp+3Fh+arg_48]
0x1800519b2  mov     r8d, r12d
0x1800519b5  mov     [rbp+3Fh+var_58], ax
0x1800519b9  xor     eax, eax
0x1800519bb  mov     [rsp+0C0h+var_80], 1
0x1800519c3  mov     [rsp+0C0h+var_88], rcx
0x1800519c8  mov     rcx, r13
0x1800519cb  mov     [rsp+0C0h+var_90], rdx
0x1800519d0  mov     rdx, [rbp+3Fh+arg_38]
0x1800519d7  mov     [rsp+0C0h+var_98], rdx
0x1800519dc  lea     rdx, [rbp+3Fh+var_58]
0x1800519e0  movups  xmmword ptr [rbp+3Fh+var_56], xmm0
0x1800519e4  mov     qword ptr [rbp+3Fh+var_56+0Eh], rax
0x1800519e8  mov     rax, [r13+0]
0x1800519ec  mov     [rsp+0C0h+var_A0], rdx
0x1800519f1  mov     rdx, r15
0x1800519f4  mov     qword ptr [rbp+3Fh+var_56+6], r14
0x1800519f8  mov     rax, [rax+28h]
0x1800519fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051a01  mov     ebx, eax
0x180051a03  mov     rcx, r14; pv
0x180051a06  call    cs:__imp_CoTaskMemFree
0x180051a0c  jmp     short loc_180051A18
0x180051a0e  mov     ebx, 80004003h
0x180051a13  test    rsi, rsi
0x180051a16  jz      short loc_180051A1E
0x180051a18  mov     dword ptr [rsi], 0
0x180051a1e  test    rdi, rdi
0x180051a21  jz      short loc_180051A2A
0x180051a23  mov     rax, [rbp+3Fh+var_60]
0x180051a27  mov     [rdi], rax
0x180051a2a  mov     eax, ebx
0x180051a2c  add     rsp, 88h
0x180051a33  pop     r15
0x180051a35  pop     r14
0x180051a37  pop     r13
0x180051a39  pop     r12
0x180051a3b  pop     rdi
0x180051a3c  pop     rsi
0x180051a3d  pop     rbx
0x180051a3e  pop     rbp
0x180051a3f  retn
0x180051a40  mov     ebx, 1
0x180051a45  jmp     short loc_180051A18
0x18008aacc  lea     r9, [rbp+3Fh+pv]
0x18008aad3  mov     [rbp+3Fh+pv], 0
0x18008aade  call    ??$_AllocString@VCTCoAllocPolicy@@@@YAJPEAXKPEB_WPEAPEA_W@Z; _AllocString<CTCoAllocPolicy>(void *,ulong,wchar_t const *,wchar_t * *)
0x18008aae3  mov     ebx, eax
0x18008aae5  test    eax, eax
0x18008aae7  js      loc_180051A03
0x18008aaed  mov     eax, 101Fh
0x18008aaf2  lea     r8, [rbp+3Fh+cb]; unsigned __int64 *
0x18008aaf9  mov     [rbp+3Fh+var_58], ax
0x18008aafd  xorps   xmm0, xmm0
0x18008ab00  xor     eax, eax
0x18008ab02  movups  xmmword ptr [rbp+3Fh+var_56], xmm0
0x18008ab06  mov     qword ptr [rbp+3Fh+var_56+0Eh], rax
0x18008ab0a  mov     [rbp+3Fh+cb], rax
0x18008ab11  lea     ecx, [rax+2]; unsigned __int64
0x18008ab14  lea     edx, [rax+8]; unsigned __int64
0x18008ab17  mov     dword ptr [rbp+3Fh+var_56+6], ecx
0x18008ab1a  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x18008ab1f  mov     r12, [rbp+3Fh+pv]
0x18008ab26  mov     ebx, eax
0x18008ab28  test    eax, eax
0x18008ab2a  js      loc_18008ABBD
0x18008ab30  mov     rcx, [rbp+3Fh+cb]; cb
0x18008ab37  call    cs:__imp_CoTaskMemAlloc
0x18008ab3d  mov     qword ptr [rbp+3Fh+var_56+0Eh], rax
0x18008ab41  test    rax, rax
0x18008ab44  jz      short loc_18008ABB8
0x18008ab46  mov     r9, [rbp+3Fh+arg_20]
0x18008ab4a  lea     rcx, [rbp+3Fh+var_60]
0x18008ab4e  mov     r8d, [rbp+3Fh+arg_18]
0x18008ab52  mov     rdx, r15
0x18008ab55  mov     [rsp+0C0h+var_78], rcx
0x18008ab5a  mov     rcx, [rbp+3Fh+arg_48]
0x18008ab61  mov     [rax], r14
0x18008ab64  mov     rax, qword ptr [rbp+3Fh+var_56+0Eh]
0x18008ab68  mov     [rsp+0C0h+var_80], 1
0x18008ab70  mov     [rsp+0C0h+var_88], rcx
0x18008ab75  mov     rcx, [rbp+3Fh+arg_40]
0x18008ab7c  mov     [rsp+0C0h+var_90], rcx
0x18008ab81  mov     rcx, [rbp+3Fh+arg_38]
0x18008ab88  mov     [rsp+0C0h+var_98], rcx
0x18008ab8d  lea     rcx, [rbp+3Fh+var_58]
0x18008ab91  mov     [rax+8], r12
0x18008ab95  mov     rax, [r13+0]
0x18008ab99  mov     [rsp+0C0h+var_A0], rcx
0x18008ab9e  mov     rcx, r13
0x18008aba1  mov     rax, [rax+28h]
0x18008aba5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008abaa  mov     rcx, qword ptr [rbp+3Fh+var_56+0Eh]; pv
0x18008abae  mov     ebx, eax
0x18008abb0  call    cs:__imp_CoTaskMemFree
0x18008abb6  jmp     short loc_18008ABBD
0x18008abb8  mov     ebx, 8007000Eh
0x18008abbd  mov     rcx, r12; pv
0x18008abc0  call    cs:__imp_CoTaskMemFree
0x18008abc6  nop
0x18008abc7  jmp     loc_180051A03
```
