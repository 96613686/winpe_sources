# _GetWholePropertyCondition(ICondition *,IConditionFactory2 *,_GUID const &,void * *)

- ea: `0x1800468c8`
- end: `0x180046b30`
- name: `?_GetWholePropertyCondition@@YAJPEAUICondition@@PEAUIConditionFactory2@@AEBU_GUID@@PEAPEAX@Z`
- size: `616`
- prototype: `int(struct ICondition *, struct IConditionFactory2 *, const struct _GUID *, void **)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x180032fc0`

## callees

- `0x180006ca8`
- `0x180033bdc`
- `0x1800468c8`
- `0x180071dc0`
- `0x180076890`
- `0x1800ea010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180046ae0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180046aea`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180046b0f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180046ae0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180046aea`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180046b0f`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180046980`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180046980`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrPBrkW` at `0x180046a0e`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrPBrkW` at `0x180046a0e`
- `PROPSYS!PropVariantToStringAlloc` at `0x1800469f3`
- `PROPSYS!PropVariantToStringAlloc` at `0x1800469f3`

## pseudocode

```c
__int64 __fastcall _GetWholePropertyCondition(
        struct ICondition *a1,
        struct IConditionFactory2 *a2,
        const struct _GUID *a3,
        void **a4)
{
  struct IConditionVtbl *lpVtbl; // rax
  HRESULT (__stdcall *QueryInterface)(ICondition *, const IID *const, void **); // rax
  HRESULT v10; // ebx
  struct ICondition *v11; // rcx
  struct IConditionVtbl *v12; // rax
  void *v13; // rcx
  LPVOID pv; // [rsp+60h] [rbp-59h] BYREF
  void *v16; // [rsp+68h] [rbp-51h] BYREF
  unsigned __int16 *v17; // [rsp+70h] [rbp-49h] BYREF
  struct IRichChunk *v18; // [rsp+78h] [rbp-41h] BYREF
  struct IRichChunk *v19; // [rsp+80h] [rbp-39h] BYREF
  struct IRichChunk *v20; // [rsp+88h] [rbp-31h] BYREF
  PWSTR ppszOut; // [rsp+90h] [rbp-29h] BYREF
  int v22; // [rsp+98h] [rbp-21h] BYREF
  struct tagPROPVARIANT pvar; // [rsp+A0h] [rbp-19h] BYREF
  struct _tagpropertykey v24; // [rsp+B8h] [rbp-1h] BYREF

  pvar.bstrblobVal.pData = 0;
  *a4 = 0;
  lpVtbl = a1->lpVtbl;
  v22 = 0;
  v16 = 0;
  pv = 0;
  QueryInterface = lpVtbl->QueryInterface;
  *(_OWORD *)&pvar.vt = 0;
  v10 = ((__int64 (__fastcall *)(struct ICondition *, GUID *, LPVOID *))QueryInterface)(
          a1,
          &GUID_0db8851d_2e5b_47eb_9208_d28c325a01d7,
          &pv);
  if ( v10 < 0 )
  {
    v22 = 0;
    memset(&pvar, 0, sizeof(pvar));
  }
  else
  {
    v10 = (*(__int64 (__fastcall **)(LPVOID, _QWORD, int *, struct tagPROPVARIANT *))(*(_QWORD *)pv + 128LL))(
            pv,
            0,
            &v22,
            &pvar);
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)pv + 16LL))(pv);
    if ( v10 >= 0 )
    {
      if ( v22 == 13 || (v10 = 1, v22 == 12) )
      {
        ppszOut = 0;
        v10 = PropVariantToStringAlloc((const PROPVARIANT *const)&pvar, &ppszOut);
        if ( v10 >= 0 )
        {
          if ( StrPBrkW(ppszOut, L"\\/_") )
          {
            pv = 0;
            v17 = 0;
            v18 = 0;
            v19 = 0;
            v20 = 0;
            memset(&v24, 0, sizeof(v24));
            v10 = SHGetComparisonInfoEx(a1, &v24, 0, 0, &pv, &v17, &v18, &v19, &v20);
            if ( v10 >= 0 )
            {
              v10 = SHCreateLeafConditionEx(
                      &v24,
                      COP_VALUE_CONTAINS,
                      &pvar,
                      (const unsigned __int16 *)pv,
                      v17,
                      v18,
                      v19,
                      v20,
                      a2,
                      &GUID_0fc988d4_c935_4b97_a973_46282ea175c8,
                      &v16);
              CoTaskMemFree(pv);
              CoTaskMemFree(v17);
              SafeRelease<IShellItemArray>((__int64 *)&v18);
              SafeRelease<IShellItemArray>((__int64 *)&v19);
              SafeRelease<IShellItemArray>((__int64 *)&v20);
            }
          }
          CoTaskMemFree(ppszOut);
        }
      }
      PropVariantClear((PROPVARIANT *)&pvar);
      if ( v10 >= 0 )
      {
        v11 = (struct ICondition *)v16;
        if ( v16 )
        {
          v12 = *(struct IConditionVtbl **)v16;
        }
        else
        {
          v12 = a1->lpVtbl;
          v11 = a1;
        }
        v10 = ((__int64 (__fastcall *)(struct ICondition *, const struct _GUID *, void **))v12->QueryInterface)(
                v11,
                a3,
                a4);
      }
    }
  }
  v13 = v16;
  v16 = 0;
  if ( v13 )
    (*(void (__fastcall **)(void *))(*(_QWORD *)v13 + 16LL))(v13);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x1800468c8  push    rbp
0x1800468ca  push    rbx
0x1800468cb  push    rsi
0x1800468cc  push    rdi
0x1800468cd  push    r12
0x1800468cf  push    r14
0x1800468d1  push    r15
0x1800468d3  lea     rbp, [rsp-27h]
0x1800468d8  sub     rsp, 0E0h
0x1800468df  mov     rax, cs:__security_cookie
0x1800468e6  xor     rax, rsp
0x1800468e9  mov     [rbp+57h+var_40], rax
0x1800468ed  xor     r12d, r12d
0x1800468f0  xor     eax, eax
0x1800468f2  mov     [rbp+57h+var_60], rax
0x1800468f6  mov     r14, r8
0x1800468f9  mov     [r9], r12
0x1800468fc  lea     r8, [rbp+57h+pv]
0x180046900  mov     rax, [rcx]
0x180046903  mov     r15, rdx
0x180046906  xorps   xmm0, xmm0
0x180046909  mov     [rbp+57h+var_78], r12d
0x18004690d  lea     rdx, _GUID_0db8851d_2e5b_47eb_9208_d28c325a01d7
0x180046914  mov     [rbp+57h+var_A8], r12
0x180046918  mov     rsi, r9
0x18004691b  mov     [rbp+57h+pv], r12
0x18004691f  mov     rax, [rax]
0x180046922  mov     rdi, rcx
0x180046925  movups  xmmword ptr [rbp+57h+pvar], xmm0
0x180046929  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004692e  mov     ebx, eax
0x180046930  test    eax, eax
0x180046932  js      loc_180046B1A
0x180046938  mov     rcx, [rbp+57h+pv]
0x18004693c  lea     r9, [rbp+57h+pvar]
0x180046940  lea     r8, [rbp+57h+var_78]
0x180046944  xor     edx, edx
0x180046946  mov     rax, [rcx]
0x180046949  mov     rax, [rax+80h]
0x180046950  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046955  mov     rcx, [rbp+57h+pv]
0x180046959  mov     ebx, eax
0x18004695b  mov     rax, [rcx]
0x18004695e  mov     rax, [rax+10h]
0x180046962  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046967  test    ebx, ebx
0x180046969  js      short loc_1800469A9
0x18004696b  cmp     [rbp+57h+var_78], 0Dh
0x18004696f  jz      short loc_1800469E7
0x180046971  cmp     [rbp+57h+var_78], 0Ch
0x180046975  lea     ebx, [r12+1]
0x18004697a  jz      short loc_1800469E7
0x18004697c  lea     rcx, [rbp+57h+pvar]; pvar
0x180046980  call    cs:__imp_PropVariantClear
0x180046986  test    ebx, ebx
0x180046988  js      short loc_1800469A9
0x18004698a  mov     rcx, [rbp+57h+var_A8]
0x18004698e  mov     r8, rsi
0x180046991  mov     rdx, r14
0x180046994  test    rcx, rcx
0x180046997  jnz     short loc_1800469E2
0x180046999  mov     rax, [rdi]
0x18004699c  mov     rcx, rdi
0x18004699f  mov     rax, [rax]
0x1800469a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800469a7  mov     ebx, eax
0x1800469a9  mov     rcx, [rbp+57h+var_A8]
0x1800469ad  mov     [rbp+57h+var_A8], r12
0x1800469b1  test    rcx, rcx
0x1800469b4  jz      short loc_1800469C2
0x1800469b6  mov     rax, [rcx]
0x1800469b9  mov     rax, [rax+10h]
0x1800469bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800469c2  mov     eax, ebx
0x1800469c4  mov     rcx, [rbp+57h+var_40]
0x1800469c8  xor     rcx, rsp; StackCookie
0x1800469cb  call    __security_check_cookie
0x1800469d0  add     rsp, 0E0h
0x1800469d7  pop     r15
0x1800469d9  pop     r14
0x1800469db  pop     r12
0x1800469dd  pop     rdi
0x1800469de  pop     rsi
0x1800469df  pop     rbx
0x1800469e0  pop     rbp
0x1800469e1  retn
0x1800469e2  mov     rax, [rcx]
0x1800469e5  jmp     short loc_18004699F
0x1800469e7  lea     rdx, [rbp+57h+ppszOut]; ppszOut
0x1800469eb  mov     [rbp+57h+ppszOut], r12
0x1800469ef  lea     rcx, [rbp+57h+pvar]; propvar
0x1800469f3  call    cs:__imp_PropVariantToStringAlloc
0x1800469f9  mov     ebx, eax
0x1800469fb  test    eax, eax
0x1800469fd  js      loc_18004697C
0x180046a03  mov     rcx, [rbp+57h+ppszOut]; psz
0x180046a07  lea     rdx, pszSet; "\\/_"
0x180046a0e  call    cs:__imp_StrPBrkW
0x180046a14  test    rax, rax
0x180046a17  jz      loc_180046B0B
0x180046a1d  xor     eax, eax
0x180046a1f  mov     [rbp+57h+pv], r12
0x180046a23  mov     [rbp+57h+var_58.pid], eax
0x180046a26  lea     rdx, [rbp+57h+var_58]
0x180046a2a  lea     rax, [rbp+57h+var_88]
0x180046a2e  mov     [rbp+57h+var_A0], r12
0x180046a32  mov     [rsp+110h+var_D0], rax
0x180046a37  xorps   xmm0, xmm0
0x180046a3a  lea     rax, [rbp+57h+var_90]
0x180046a3e  mov     [rbp+57h+var_98], r12
0x180046a42  mov     [rsp+110h+var_D8], rax
0x180046a47  xor     r9d, r9d
0x180046a4a  lea     rax, [rbp+57h+var_98]
0x180046a4e  mov     [rbp+57h+var_90], r12
0x180046a52  mov     [rsp+110h+var_E0], rax
0x180046a57  xor     r8d, r8d
0x180046a5a  lea     rax, [rbp+57h+var_A0]
0x180046a5e  mov     [rbp+57h+var_88], r12
0x180046a62  mov     [rsp+110h+var_E8], rax
0x180046a67  mov     rcx, rdi
0x180046a6a  lea     rax, [rbp+57h+pv]
0x180046a6e  mov     [rsp+110h+var_F0], rax
0x180046a73  movups  xmmword ptr [rbp+57h+var_58.fmtid.Data1], xmm0
0x180046a77  call    SHGetComparisonInfoEx
0x180046a7c  mov     ebx, eax
0x180046a7e  test    eax, eax
0x180046a80  js      loc_180046B0B
0x180046a86  mov     rcx, [rbp+57h+var_90]
0x180046a8a  lea     r9, [rbp+57h+var_A8]
0x180046a8e  mov     rdx, [rbp+57h+var_98]
0x180046a92  mov     r8, [rbp+57h+var_A0]
0x180046a96  mov     rax, [rbp+57h+var_88]
0x180046a9a  mov     [rsp+110h+var_C0], r9; void **
0x180046a9f  lea     r9, _GUID_0fc988d4_c935_4b97_a973_46282ea175c8
0x180046aa6  mov     [rsp+110h+var_C8], r9; struct _GUID *
0x180046aab  mov     r9, [rbp+57h+pv]; unsigned __int16 *
0x180046aaf  mov     [rsp+110h+var_D0], r15; struct IConditionFactory2 *
0x180046ab4  mov     [rsp+110h+var_D8], rax; struct IRichChunk *
0x180046ab9  mov     [rsp+110h+var_E0], rcx; struct IRichChunk *
0x180046abe  lea     rcx, [rbp+57h+var_58]; struct _tagpropertykey *
0x180046ac2  mov     [rsp+110h+var_E8], rdx; struct IRichChunk *
0x180046ac7  mov     edx, 9; enum tagCONDITION_OPERATION
0x180046acc  mov     [rsp+110h+var_F0], r8; unsigned __int16 *
0x180046ad1  lea     r8, [rbp+57h+pvar]; struct tagPROPVARIANT *
0x180046ad5  call    ?SHCreateLeafConditionEx@@YAJAEBU_tagpropertykey@@W4tagCONDITION_OPERATION@@AEBUtagPROPVARIANT@@PEBG3PEAUIRichChunk@@44PEAUIConditionFactory2@@AEBU_GUID@@PEAPEAX@Z; SHCreateLeafConditionEx(_tagpropertykey const &,tagCONDITION_OPERATION,tagPROPVARIANT const &,ushort const *,ushort const *,IRichChunk *,IRichChunk *,IRichChunk *,IConditionFactory2 *,_GUID const &,void * *)
0x180046ada  mov     rcx, [rbp+57h+pv]; pv
0x180046ade  mov     ebx, eax
0x180046ae0  call    cs:__imp_CoTaskMemFree
0x180046ae6  mov     rcx, [rbp+57h+var_A0]; pv
0x180046aea  call    cs:__imp_CoTaskMemFree
0x180046af0  lea     rcx, [rbp+57h+var_98]
0x180046af4  call    ??$SafeRelease@UIShellItemArray@@@@YAXPEAPEAUIShellItemArray@@@Z; SafeRelease<IShellItemArray>(IShellItemArray * *)
0x180046af9  lea     rcx, [rbp+57h+var_90]
0x180046afd  call    ??$SafeRelease@UIShellItemArray@@@@YAXPEAPEAUIShellItemArray@@@Z; SafeRelease<IShellItemArray>(IShellItemArray * *)
0x180046b02  lea     rcx, [rbp+57h+var_88]
0x180046b06  call    ??$SafeRelease@UIShellItemArray@@@@YAXPEAPEAUIShellItemArray@@@Z; SafeRelease<IShellItemArray>(IShellItemArray * *)
0x180046b0b  mov     rcx, [rbp+57h+ppszOut]; pv
0x180046b0f  call    cs:__imp_CoTaskMemFree
0x180046b15  jmp     loc_18004697C
0x180046b1a  xorps   xmm0, xmm0
0x180046b1d  mov     [rbp+57h+var_78], r12d
0x180046b21  xor     eax, eax
0x180046b23  movups  xmmword ptr [rbp+57h+pvar], xmm0
0x180046b27  mov     [rbp+57h+var_60], rax
0x180046b2b  jmp     loc_1800469A9
```
