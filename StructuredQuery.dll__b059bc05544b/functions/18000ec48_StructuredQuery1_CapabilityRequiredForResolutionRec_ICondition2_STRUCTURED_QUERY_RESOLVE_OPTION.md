# StructuredQuery1::_CapabilityRequiredForResolutionRec(ICondition2 *,STRUCTURED_QUERY_RESOLVE_OPTION)

- ea: `0x18000ec48`
- end: `0x18000ef33`
- name: `?_CapabilityRequiredForResolutionRec@StructuredQuery1@@YA?AW4CONDITION_FACTORY_CAPABILITY@1@PEAUICondition2@@W4STRUCTURED_QUERY_RESOLVE_OPTION@@@Z`
- size: `747`
- prototype: `__int64 __fastcall(__int64 *, unsigned int)`
- caller_count: `2`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000ec48`
- `0x18001089c`

## callees

- `0x18000ec48`
- `0x18000f5b8`
- `0x18000f680`
- `0x18005daf0`
- `0x18008b010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000eef2`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000ef20`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000eef2`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000ef20`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000ed98`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000ed98`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000eda2`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000eda2`

## pseudocode

```c
__int64 __fastcall StructuredQuery1::_CapabilityRequiredForResolutionRec(__int64 *a1, unsigned int a2)
{
  __int64 v2; // rax
  unsigned int v5; // edi
  __int64 v6; // rax
  int (__fastcall *v7)(__int64 *, __int128 *, _QWORD, PROPVARIANT *); // rax
  __int64 v8; // rax
  __int64 v9; // rax
  struct IRichChunk *v10; // rdx
  const struct _tagpropertykey *v11; // rdx
  StructuredQuery1 *v12; // rcx
  __int64 v14; // rax
  unsigned int v15; // ebx
  void (*v16)(void); // rax
  __int64 v17; // rax
  const WCHAR *v18; // rbx
  LPVOID pv; // [rsp+30h] [rbp-19h] BYREF
  StructuredQuery1 *v20; // [rsp+38h] [rbp-11h] BYREF
  unsigned int v21; // [rsp+40h] [rbp-9h] BYREF
  __int64 v22; // [rsp+48h] [rbp-1h] BYREF
  PROPVARIANT pvar[2]; // [rsp+50h] [rbp+7h] BYREF
  __int64 v24; // [rsp+60h] [rbp+17h]
  __int128 v25; // [rsp+68h] [rbp+1Fh] BYREF
  int v26; // [rsp+78h] [rbp+2Fh]

  v2 = *a1;
  v21 = 0;
  v5 = 2;
  if ( (*(int (__fastcall **)(__int64 *, unsigned int *))(v2 + 64))(a1, &v21) < 0 )
    return v5;
  if ( v21 < 2 )
  {
    v14 = *a1;
    pv = 0;
    if ( (*(int (__fastcall **)(__int64 *, GUID *, LPVOID *))(v14 + 72))(
           a1,
           &GUID_92ca9dcd_5622_4bba_a805_5e9f541bd8c9,
           &pv) < 0 )
      return v5;
    LODWORD(v20) = 0;
    if ( (*(int (__fastcall **)(LPVOID, StructuredQuery1 **))(*(_QWORD *)pv + 24LL))(pv, &v20) >= 0 )
    {
      v5 = 1;
      v15 = 0;
      do
      {
        if ( v15 >= (unsigned int)v20 )
          break;
        v22 = 0;
        v5 = 2;
        if ( (*(int (__fastcall **)(LPVOID, _QWORD, GUID *, __int64 *))(*(_QWORD *)pv + 32LL))(
               pv,
               v15,
               &GUID_0db8851d_2e5b_47eb_9208_d28c325a01d7,
               &v22) >= 0 )
        {
          v5 = StructuredQuery1::_CapabilityRequiredForResolutionRec(v22, a2);
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
        }
        ++v15;
      }
      while ( v5 != 2 );
    }
    v16 = *(void (**)(void))(*(_QWORD *)pv + 16LL);
LABEL_26:
    v16();
    return v5;
  }
  if ( v21 == 2 )
  {
    v17 = *a1;
    pv = 0;
    if ( (*(int (__fastcall **)(__int64 *, GUID *, LPVOID *))(v17 + 72))(
           a1,
           &GUID_0db8851d_2e5b_47eb_9208_d28c325a01d7,
           &pv) < 0 )
      return v5;
    v5 = StructuredQuery1::_CapabilityRequiredForResolutionRec(pv, a2);
    v16 = *(void (**)(void))(*(_QWORD *)pv + 16LL);
    goto LABEL_26;
  }
  if ( v21 == 3 )
  {
    v26 = 0;
    v24 = 0;
    v6 = *a1;
    v25 = 0;
    v7 = *(int (__fastcall **)(__int64 *, __int128 *, _QWORD, PROPVARIANT *))(v6 + 128);
    *(_OWORD *)pvar = 0;
    if ( v7(a1, &v25, 0, pvar) >= 0 )
    {
      v8 = *a1;
      pv = 0;
      if ( (*(int (__fastcall **)(__int64 *, LPVOID *))(v8 + 88))(a1, &pv) >= 0 )
      {
        v9 = *a1;
        v20 = 0;
        if ( (*(int (__fastcall **)(__int64 *, _QWORD, _QWORD, StructuredQuery1 **))(v9 + 104))(a1, 0, 0, &v20) >= 0 )
        {
          if ( (StructuredQuery1::GetQuotePrefixStatus(v20, v10) & 0x40) == 0
            && (((LOWORD(pvar[0]) - 31) & 0xEFFF) != 0
             || (v18 = (const WCHAR *)pv) == 0
             || CompareStringW(0x7Fu, 0, (PCNZWCH)pv, -1, L"System.StructuredQueryType.String", -1) == 2
             || CompareStringW(0x7Fu, 0, v18, -1, L"System.StructuredQueryType.DateTime", -1) == 2)
            && ((a2 & 8) != 0
             || (unsigned int)StructuredQuery1::_PropertyCannotRequireMapping((StructuredQuery1 *)&v25, v11)) )
          {
            v5 = 1;
          }
          v12 = v20;
          if ( v20 )
          {
            v20 = 0;
            (*(void (__fastcall **)(StructuredQuery1 *))(*(_QWORD *)v12 + 16LL))(v12);
          }
        }
        CoTaskMemFree(pv);
      }
      PropVariantClear(pvar);
    }
  }
  return v5;
}

```

## disassembly

```asm
0x18000ec48  mov     [rsp-8+arg_10], rbx
0x18000ec4d  push    rbp
0x18000ec4e  push    rsi
0x18000ec4f  push    rdi
0x18000ec50  lea     rbp, [rsp-47h]
0x18000ec55  sub     rsp, 90h
0x18000ec5c  mov     rax, cs:__security_cookie
0x18000ec63  xor     rax, rsp
0x18000ec66  mov     [rbp+57h+var_20], rax
0x18000ec6a  mov     rax, [rcx]
0x18000ec6d  mov     esi, edx
0x18000ec6f  lea     rdx, [rbp+57h+var_60]
0x18000ec73  mov     [rbp+57h+var_60], 0
0x18000ec7a  mov     rbx, rcx
0x18000ec7d  mov     edi, 2
0x18000ec82  mov     rax, [rax+40h]
0x18000ec86  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ec8b  test    eax, eax
0x18000ec8d  js      loc_18000EDA8
0x18000ec93  mov     ecx, [rbp+57h+var_60]
0x18000ec96  test    ecx, ecx
0x18000ec98  jz      loc_18000EDC9
0x18000ec9e  sub     ecx, 1
0x18000eca1  jz      loc_18000EDC9
0x18000eca7  sub     ecx, 1
0x18000ecaa  jz      loc_18000EE81
0x18000ecb0  cmp     ecx, 1
0x18000ecb3  jnz     loc_18000EDA8
0x18000ecb9  xor     eax, eax
0x18000ecbb  lea     r9, [rbp+57h+pvar]
0x18000ecbf  mov     [rbp+57h+var_28], eax
0x18000ecc2  lea     rdx, [rbp+57h+var_38]
0x18000ecc6  mov     [rbp+57h+var_40], rax
0x18000ecca  xorps   xmm0, xmm0
0x18000eccd  mov     rax, [rbx]
0x18000ecd0  xorps   xmm1, xmm1
0x18000ecd3  xor     r8d, r8d
0x18000ecd6  mov     rcx, rbx
0x18000ecd9  movups  [rbp+57h+var_38], xmm0
0x18000ecdd  mov     rax, [rax+80h]
0x18000ece4  movups  xmmword ptr [rbp+57h+pvar], xmm1
0x18000ece8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000eced  test    eax, eax
0x18000ecef  js      loc_18000EDA8
0x18000ecf5  mov     rax, [rbx]
0x18000ecf8  lea     rdx, [rbp+57h+pv]
0x18000ecfc  mov     rcx, rbx
0x18000ecff  mov     [rbp+57h+pv], 0
0x18000ed07  mov     rax, [rax+58h]
0x18000ed0b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ed10  test    eax, eax
0x18000ed12  js      loc_18000ED9E
0x18000ed18  mov     rax, [rbx]
0x18000ed1b  lea     r9, [rbp+57h+var_68]
0x18000ed1f  xor     r8d, r8d
0x18000ed22  mov     [rbp+57h+var_68], 0
0x18000ed2a  xor     edx, edx
0x18000ed2c  mov     rcx, rbx
0x18000ed2f  mov     rax, [rax+68h]
0x18000ed33  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ed38  test    eax, eax
0x18000ed3a  js      short loc_18000ED94
0x18000ed3c  mov     rcx, [rbp+57h+var_68]; this
0x18000ed40  call    ?GetQuotePrefixStatus@StructuredQuery1@@YAHPEAUIRichChunk@@@Z; StructuredQuery1::GetQuotePrefixStatus(IRichChunk *)
0x18000ed45  test    al, 40h
0x18000ed47  jnz     short loc_18000ED77
0x18000ed49  movzx   eax, word ptr [rbp+57h+pvar]
0x18000ed4d  mov     ecx, 0EFFFh
0x18000ed52  sub     ax, 1Fh
0x18000ed56  test    cx, ax
0x18000ed59  jz      loc_18000EEC5
0x18000ed5f  test    sil, 8
0x18000ed63  jnz     short loc_18000ED72
0x18000ed65  lea     rcx, [rbp+57h+var_38]; this
0x18000ed69  call    ?_PropertyCannotRequireMapping@StructuredQuery1@@YAHAEBU_tagpropertykey@@@Z; StructuredQuery1::_PropertyCannotRequireMapping(_tagpropertykey const &)
0x18000ed6e  test    eax, eax
0x18000ed70  jz      short loc_18000ED77
0x18000ed72  mov     edi, 1
0x18000ed77  mov     rcx, [rbp+57h+var_68]
0x18000ed7b  test    rcx, rcx
0x18000ed7e  jz      short loc_18000ED94
0x18000ed80  mov     [rbp+57h+var_68], 0
0x18000ed88  mov     rax, [rcx]
0x18000ed8b  mov     rax, [rax+10h]
0x18000ed8f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ed94  mov     rcx, [rbp+57h+pv]; pv
0x18000ed98  call    cs:__imp_CoTaskMemFree
0x18000ed9e  lea     rcx, [rbp+57h+pvar]; pvar
0x18000eda2  call    cs:__imp_PropVariantClear
0x18000eda8  mov     eax, edi
0x18000edaa  mov     rcx, [rbp+57h+var_20]
0x18000edae  xor     rcx, rsp; StackCookie
0x18000edb1  call    __security_check_cookie
0x18000edb6  mov     rbx, [rsp+0A0h+arg_10]
0x18000edbe  add     rsp, 90h
0x18000edc5  pop     rdi
0x18000edc6  pop     rsi
0x18000edc7  pop     rbp
0x18000edc8  retn
0x18000edc9  mov     rax, [rbx]
0x18000edcc  lea     r8, [rbp+57h+pv]
0x18000edd0  lea     rdx, _GUID_92ca9dcd_5622_4bba_a805_5e9f541bd8c9
0x18000edd7  mov     [rbp+57h+pv], 0
0x18000eddf  mov     rcx, rbx
0x18000ede2  mov     rax, [rax+48h]
0x18000ede6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000edeb  test    eax, eax
0x18000eded  js      short loc_18000EDA8
0x18000edef  mov     rcx, [rbp+57h+pv]
0x18000edf3  lea     rdx, [rbp+57h+var_68]
0x18000edf7  mov     dword ptr [rbp+57h+var_68], 0
0x18000edfe  mov     rax, [rcx]
0x18000ee01  mov     rax, [rax+18h]
0x18000ee05  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ee0a  test    eax, eax
0x18000ee0c  js      short loc_18000EE6C
0x18000ee0e  mov     edi, 1
0x18000ee13  xor     ebx, ebx
0x18000ee15  cmp     ebx, dword ptr [rbp+57h+var_68]
0x18000ee18  jnb     short loc_18000EE6C
0x18000ee1a  mov     rcx, [rbp+57h+pv]
0x18000ee1e  lea     r9, [rbp+57h+var_58]
0x18000ee22  mov     [rbp+57h+var_58], 0
0x18000ee2a  lea     r8, _GUID_0db8851d_2e5b_47eb_9208_d28c325a01d7
0x18000ee31  mov     edx, ebx
0x18000ee33  mov     edi, 2
0x18000ee38  mov     rax, [rcx]
0x18000ee3b  mov     rax, [rax+20h]
0x18000ee3f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ee44  test    eax, eax
0x18000ee46  js      short loc_18000EE65
0x18000ee48  mov     rcx, [rbp+57h+var_58]
0x18000ee4c  mov     edx, esi
0x18000ee4e  call    ?_CapabilityRequiredForResolutionRec@StructuredQuery1@@YA?AW4CONDITION_FACTORY_CAPABILITY@1@PEAUICondition2@@W4STRUCTURED_QUERY_RESOLVE_OPTION@@@Z; StructuredQuery1::_CapabilityRequiredForResolutionRec(ICondition2 *,STRUCTURED_QUERY_RESOLVE_OPTION)
0x18000ee53  mov     rcx, [rbp+57h+var_58]
0x18000ee57  mov     edi, eax
0x18000ee59  mov     rax, [rcx]
0x18000ee5c  mov     rax, [rax+10h]
0x18000ee60  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ee65  inc     ebx
0x18000ee67  cmp     edi, 2
0x18000ee6a  jnz     short loc_18000EE15
0x18000ee6c  mov     rcx, [rbp+57h+pv]
0x18000ee70  mov     rax, [rcx]
0x18000ee73  mov     rax, [rax+10h]
0x18000ee77  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ee7c  jmp     loc_18000EDA8
0x18000ee81  mov     rax, [rbx]
0x18000ee84  lea     r8, [rbp+57h+pv]
0x18000ee88  lea     rdx, _GUID_0db8851d_2e5b_47eb_9208_d28c325a01d7
0x18000ee8f  mov     [rbp+57h+pv], 0
0x18000ee97  mov     rcx, rbx
0x18000ee9a  mov     rax, [rax+48h]
0x18000ee9e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000eea3  test    eax, eax
0x18000eea5  js      loc_18000EDA8
0x18000eeab  mov     rcx, [rbp+57h+pv]
0x18000eeaf  mov     edx, esi
0x18000eeb1  call    ?_CapabilityRequiredForResolutionRec@StructuredQuery1@@YA?AW4CONDITION_FACTORY_CAPABILITY@1@PEAUICondition2@@W4STRUCTURED_QUERY_RESOLVE_OPTION@@@Z; StructuredQuery1::_CapabilityRequiredForResolutionRec(ICondition2 *,STRUCTURED_QUERY_RESOLVE_OPTION)
0x18000eeb6  mov     rcx, [rbp+57h+pv]
0x18000eeba  mov     edi, eax
0x18000eebc  mov     rdx, [rcx]
0x18000eebf  mov     rax, [rdx+10h]
0x18000eec3  jmp     short loc_18000EE77
0x18000eec5  mov     rbx, [rbp+57h+pv]
0x18000eec9  test    rbx, rbx
0x18000eecc  jz      loc_18000ED5F
0x18000eed2  xor     edx, edx; dwCmpFlags
0x18000eed4  mov     [rsp+0A0h+cchCount2], 0FFFFFFFFh; cchCount2
0x18000eedc  lea     rax, aSystemStructur_24; "System.StructuredQueryType.String"
0x18000eee3  or      r9d, 0FFFFFFFFh; cchCount1
0x18000eee7  mov     r8, rbx; lpString1
0x18000eeea  mov     [rsp+0A0h+lpString2], rax; lpString2
0x18000eeef  lea     ecx, [rdx+7Fh]; Locale
0x18000eef2  call    cs:__imp_CompareStringW
0x18000eef8  cmp     eax, edi
0x18000eefa  jz      loc_18000ED5F
0x18000ef00  xor     edx, edx; dwCmpFlags
0x18000ef02  mov     [rsp+0A0h+cchCount2], 0FFFFFFFFh; cchCount2
0x18000ef0a  lea     rax, aSystemStructur_17; "System.StructuredQueryType.DateTime"
0x18000ef11  or      r9d, 0FFFFFFFFh; cchCount1
0x18000ef15  mov     r8, rbx; lpString1
0x18000ef18  mov     [rsp+0A0h+lpString2], rax; lpString2
0x18000ef1d  lea     ecx, [rdx+7Fh]; Locale
0x18000ef20  call    cs:__imp_CompareStringW
0x18000ef26  cmp     eax, edi
0x18000ef28  jz      loc_18000ED5F
0x18000ef2e  jmp     loc_18000ED77
```
