# GetNodeValue

- ea: `0x18005f548`
- end: `0x18005fbea`
- name: `GetNodeValue`
- size: `1698`
- prototype: ``
- caller_count: `2`
- callee_count: `12`
- tags: `service_task, broker_com_uri`

## callers

- `0x18005fbf0`
- `0x1800605f4`

## callees

- `0x18000865c`
- `0x18000dd14`
- `0x180012b30`
- `0x18004ba54`
- `0x18005f2e0`
- `0x18005f468`
- `0x18005f548`
- `0x180061008`
- `0x180061960`
- `0x180068ea0`
- `0x180068f20`
- `0x1800692e0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18005fa40`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18005fa40`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005fb84`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005fb84`
- `RPCRT4!UuidFromStringW` at `0x18005f93c`
- `RPCRT4!UuidFromStringW` at `0x18005f93c`
- `OLEAUT32!__imp_SysStringLen` at `0x18005f8f6`
- `OLEAUT32!__imp_SysStringLen` at `0x18005fa2e`
- `OLEAUT32!__imp_SysStringLen` at `0x18005fb26`
- `OLEAUT32!__imp_SysStringLen` at `0x18005f8f6`
- `OLEAUT32!__imp_SysStringLen` at `0x18005fa2e`
- `OLEAUT32!__imp_SysStringLen` at `0x18005fb26`
- `OLEAUT32!__imp_VariantInit` at `0x18005f5a1`
- `OLEAUT32!__imp_VariantInit` at `0x18005f5a1`
- `OLEAUT32!__imp_VariantClear` at `0x18005fba7`
- `OLEAUT32!__imp_VariantClear` at `0x18005fba7`
- `OLEAUT32!__imp_VariantChangeType` at `0x18005f727`
- `OLEAUT32!__imp_VariantChangeType` at `0x18005f727`
- `OLEAUT32!__imp_SysStringByteLen` at `0x18005fadd`
- `OLEAUT32!__imp_SysStringByteLen` at `0x18005fadd`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall GetNodeValue(
        __int64 (__fastcall ***a1)(_QWORD, GUID *, __int64 *),
        __int64 a2,
        __int64 a3,
        int a4,
        __int64 a5)
{
  unsigned int v9; // eax
  UUID *v10; // rsi
  __int64 (__fastcall *v11)(_QWORD, GUID *, __int64 *); // rdi
  HRESULT v12; // ebx
  int v13; // r8d
  VARTYPE v14; // r9
  OLECHAR *bstrVal; // rdi
  HRESULT v16; // eax
  int v17; // ecx
  int v18; // ecx
  int v19; // ecx
  int v20; // ecx
  int v21; // ecx
  int v22; // ecx
  int v23; // ecx
  int v24; // ecx
  int v25; // ecx
  int v26; // ecx
  int v27; // ecx
  int v28; // ecx
  int v29; // ecx
  int v30; // ecx
  int v31; // ecx
  int v32; // ecx
  int v33; // ecx
  size_t v34; // r14
  unsigned int v35; // r15d
  int v36; // ecx
  int v37; // ecx
  int v38; // ecx
  int v39; // ecx
  int v40; // ecx
  int v41; // ecx
  int v42; // ecx
  bool v43; // zf
  size_t v44; // r14
  const WCHAR *v45; // r15
  unsigned int i; // edi
  UINT v47; // eax
  LONG lVal; // eax
  int v49; // ecx
  int v50; // ecx
  int v51; // ecx
  int v52; // ecx
  int v53; // ecx
  int v54; // ecx
  int v55; // ecx
  int v56; // ecx
  OLECHAR *v57; // r15
  SIZE_T v58; // r14
  OLECHAR *v59; // rax
  UINT v60; // r15d
  int v61; // ecx
  unsigned __int8 *v62; // r15
  UINT v63; // eax
  int v64; // r13d
  OLECHAR *v65; // r8
  OLECHAR *v66; // r9
  __int64 v67; // r10
  unsigned __int8 *v68; // rax
  BSTR pbstr; // [rsp+30h] [rbp-30h] BYREF
  VARIANTARG pvarg; // [rsp+38h] [rbp-28h] BYREF
  __int64 v72; // [rsp+50h] [rbp-10h] BYREF

  v9 = 0;
  memset(&pvarg, 0, sizeof(pvarg));
  if ( !*(_BYTE *)(a2 + 33) )
    v9 = *(_DWORD *)(a2 + 28);
  v10 = (UUID *)(a3 + v9);
  v72 = 0;
  VariantInit(&pvarg);
  v11 = **a1;
  if ( v72 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v72 + 16LL))(v72);
    v72 = 0;
  }
  v12 = v11(a1, &GUID_2933bf80_7b36_11d2_b20e_00c04f983e60, &v72);
  if ( v12 < 0 )
    goto LABEL_136;
  if ( *(int *)(a2 + 24) <= 4 )
  {
LABEL_7:
    v12 = 0;
    goto LABEL_136;
  }
  if ( *(int *)(a2 + 24) >= 20 )
  {
    if ( *(_DWORD *)(a2 + 24) == 24 )
    {
      pbstr = 0;
      v12 = (*(__int64 (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v72 + 272LL))(v72, &pbstr);
      if ( v12 >= 0 )
      {
LABEL_11:
        pvarg.vt = 8;
        bstrVal = pbstr;
        pvarg.llVal = (LONGLONG)pbstr;
        goto LABEL_17;
      }
    }
  }
  else
  {
    if ( a4 )
    {
      pbstr = 0;
      v12 = (*(__int64 (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v72 + 208LL))(v72, &pbstr);
      if ( v12 < 0 )
        goto LABEL_136;
      goto LABEL_11;
    }
    v12 = (*(__int64 (__fastcall **)(__int64, VARIANTARG *))(*(_QWORD *)v72 + 64LL))(v72, &pvarg);
    if ( v12 < 0 )
      goto LABEL_136;
  }
  bstrVal = pvarg.bstrVal;
LABEL_17:
  if ( v12 == 1 )
  {
    if ( *(_BYTE *)(a2 + 32) )
    {
      v12 = -2145124339;
      goto LABEL_136;
    }
    if ( !*(_BYTE *)(a2 + 34) )
      goto LABEL_7;
    v16 = SetNodeDefaultValue(a2, a3);
    goto LABEL_118;
  }
  v17 = *(_DWORD *)(a2 + 24);
  if ( v17 > 14 )
  {
    v36 = v17 - 15;
    if ( !v36 )
      goto LABEL_32;
    v37 = v36 - 1;
    if ( !v37 )
      goto LABEL_32;
    v38 = v37 - 1;
    if ( !v38 )
      goto LABEL_32;
    v39 = v38 - 1;
    if ( !v39 )
      goto LABEL_32;
    v40 = v39 - 1;
    if ( v40 )
    {
      v41 = v40 - 2;
      if ( !v41 )
        goto LABEL_36;
      v42 = v41 - 1;
      if ( !v42 || (unsigned int)(v42 - 1) < 2 )
        goto LABEL_36;
      goto LABEL_63;
    }
  }
  else
  {
    if ( v17 == 14 )
      goto LABEL_32;
    v18 = v17 - 5;
    if ( !v18 )
    {
      v14 = 3;
      goto LABEL_33;
    }
    v19 = v18 - 1;
    if ( !v19 )
    {
      v14 = 19;
      goto LABEL_33;
    }
    v20 = v19 - 1;
    if ( !v20 )
    {
      v14 = 21;
      goto LABEL_33;
    }
    v21 = v20 - 1;
    if ( !v21 )
    {
LABEL_32:
      v14 = 8;
      goto LABEL_33;
    }
    v22 = v21 - 1;
    if ( v22 )
    {
      v23 = v22 - 1;
      if ( !v23 )
        goto LABEL_32;
      v24 = v23 - 1;
      if ( !v24 || (unsigned int)(v24 - 1) <= 1 )
        goto LABEL_32;
LABEL_63:
      v12 = -2147024809;
      goto LABEL_136;
    }
  }
  v14 = 11;
LABEL_33:
  if ( pvarg.vt != v14 )
  {
    v12 = VariantChangeType(&pvarg, &pvarg, 0, v14);
    if ( v12 < 0 )
      goto LABEL_136;
    bstrVal = pvarg.bstrVal;
  }
LABEL_36:
  v25 = *(_DWORD *)(a2 + 24);
  if ( v25 > 14 )
  {
    v49 = v25 - 15;
    if ( !v49 )
      goto LABEL_110;
    v50 = v49 - 1;
    if ( !v50 )
    {
      v61 = 0;
      v62 = 0;
      if ( bstrVal )
      {
        v63 = SysStringLen(bstrVal);
        v64 = v63;
        v65 = bstrVal;
        v66 = bstrVal;
        v67 = v63 + 1;
        do
        {
          *(_BYTE *)v66 = *(_BYTE *)v65++;
          v66 = (OLECHAR *)((char *)v66 + 1);
          --v67;
        }
        while ( v67 );
        LODWORD(pbstr) = 3 * ((v63 >> 2) + 1);
        v68 = (unsigned __int8 *)SafeSusComAlloc((int)pbstr, 1);
        v62 = v68;
        if ( !v68 )
          goto LABEL_135;
        if ( !(unsigned int)ATL::Base64Decode((const char *)bstrVal, v64, v68, (int *)&pbstr) )
        {
          CoTaskMemFree(v62);
          goto LABEL_88;
        }
        v61 = (int)pbstr;
      }
      *(_DWORD *)(a3 + *(_QWORD *)a2) = v61;
      *(_QWORD *)&v10->Data1 = v62;
      goto LABEL_136;
    }
    v51 = v50 - 1;
    if ( !v51 )
    {
      v60 = SysStringByteLen(bstrVal) + 2;
      memset(v10, 0, *(_QWORD *)a2);
      if ( !bstrVal )
        goto LABEL_78;
      if ( (unsigned __int64)v60 > *(_QWORD *)a2 )
        goto LABEL_88;
      memmove(v10, bstrVal, v60);
      goto LABEL_136;
    }
    v52 = v51 - 1;
    if ( !v52 )
    {
      if ( !bstrVal )
        goto LABEL_78;
      v12 = ConvertStringVerToFileVerW(bstrVal, (unsigned __int64 *)&v10->Data1, v13, v14);
      if ( v12 < 0 )
        goto LABEL_88;
      goto LABEL_136;
    }
    v53 = v52 - 1;
    if ( !v53 )
    {
      if ( pvarg.iVal )
        v10->Data1 |= *(_DWORD *)a2;
      goto LABEL_136;
    }
    v54 = v53 - 2;
    if ( v54 )
    {
      v55 = v54 - 1;
      if ( v55 )
      {
        v56 = v55 - 1;
        if ( v56 )
        {
          if ( v56 != 1 )
            goto LABEL_136;
LABEL_110:
          v57 = (OLECHAR *)&dword_1800937AC;
          if ( bstrVal )
            v57 = bstrVal;
          v58 = 2 * SysStringLen(v57) + 2;
          v59 = (OLECHAR *)CoTaskMemAlloc(v58);
          bstrVal = v59;
          if ( v59 )
          {
            memmove(v59, v57, (unsigned int)v58);
            goto LABEL_114;
          }
LABEL_135:
          v12 = -2147024882;
          goto LABEL_136;
        }
        v16 = DspParseSpecialData(v72, (_DWORD)v10, (int)a3 + *(_DWORD *)a2, a5, 0);
      }
      else
      {
        v16 = DspParseSpecialData(v72, (int)v10 + 8, (_DWORD)v10, a5, 1);
      }
    }
    else
    {
      v16 = DspParseSpecialData(v72, (_DWORD)v10, (int)a3 + *(_DWORD *)a2, a5, 1);
    }
LABEL_118:
    v12 = v16;
    goto LABEL_136;
  }
  if ( v25 == 14 )
  {
    v34 = *(_QWORD *)a2;
    if ( bstrVal )
    {
      v35 = 0;
      if ( *(_DWORD *)(v34 + 8) )
      {
        while ( (unsigned int)AsciiStringCompareI(bstrVal, *(PCNZWCH *)(*(_QWORD *)v34 + 16LL * v35)) )
        {
          if ( ++v35 >= *(_DWORD *)(v34 + 8) )
            goto LABEL_67;
        }
        if ( *(_DWORD *)(*(_QWORD *)v34 + 16LL * v35 + 8) == 2 )
          v10->Data1 |= 0x1000u;
      }
      goto LABEL_67;
    }
LABEL_88:
    v12 = -2145124338;
    goto LABEL_136;
  }
  v26 = v25 - 5;
  if ( !v26 || (v27 = v26 - 1) == 0 )
  {
    lVal = pvarg.lVal;
    goto LABEL_93;
  }
  v28 = v27 - 1;
  if ( !v28 )
  {
LABEL_114:
    *(_QWORD *)&v10->Data1 = bstrVal;
    goto LABEL_136;
  }
  v29 = v28 - 1;
  if ( !v29 )
  {
    if ( bstrVal )
    {
      v12 = StringToFileTime(bstrVal, v10, 0);
      v43 = v12 == -2147024809;
LABEL_68:
      if ( !v43 )
        goto LABEL_136;
      goto LABEL_88;
    }
    goto LABEL_88;
  }
  v30 = v29 - 1;
  if ( !v30 )
  {
    lVal = pvarg.iVal != 0;
LABEL_93:
    v10->Data1 = lVal;
    goto LABEL_136;
  }
  v31 = v30 - 1;
  if ( v31 )
  {
    v32 = v31 - 1;
    if ( v32 )
    {
      v33 = v32 - 1;
      if ( !v33 )
      {
        v44 = *(_QWORD *)a2;
        v45 = (const WCHAR *)&dword_1800937AC;
        if ( bstrVal )
          v45 = bstrVal;
        for ( i = 0; i < *(_DWORD *)(v44 + 8); ++i )
        {
          if ( !(unsigned int)AsciiStringCompareI(v45, *(PCNZWCH *)(*(_QWORD *)v44 + 16LL * i)) )
            break;
        }
        if ( i != *(_DWORD *)(v44 + 8) )
        {
          v10->Data1 = *(_DWORD *)(*(_QWORD *)v44 + 16LL * i + 8);
          goto LABEL_136;
        }
        goto LABEL_88;
      }
      if ( v33 != 1 )
        goto LABEL_136;
      v34 = *(_QWORD *)a2;
      if ( bstrVal )
      {
        v35 = 0;
        if ( *(_DWORD *)(v34 + 8) )
        {
          while ( (unsigned int)AsciiStringCompareI(bstrVal, *(PCNZWCH *)(*(_QWORD *)v34 + 16LL * v35)) )
          {
            if ( ++v35 >= *(_DWORD *)(v34 + 8) )
              goto LABEL_67;
          }
          if ( *(_DWORD *)(*(_QWORD *)v34 + 16LL * v35 + 8) == 1 )
            v10->Data1 |= 0x800u;
        }
LABEL_67:
        v43 = v35 == *(_DWORD *)(v34 + 8);
        goto LABEL_68;
      }
      goto LABEL_88;
    }
  }
  if ( !bstrVal )
  {
LABEL_78:
    v12 = *(_BYTE *)(a2 + 32) != 0 ? 0x8024000D : 0;
    goto LABEL_136;
  }
  v47 = SysStringLen(bstrVal);
  if ( *(_DWORD *)(a2 + 24) == 11 )
  {
    if ( v47 == 38 && *bstrVal == 123 && bstrVal[37] == 125 )
    {
      bstrVal[37] = 0;
      ++bstrVal;
    }
    else
    {
      v12 = -2145124338;
    }
  }
  else if ( v47 != 36 )
  {
    goto LABEL_88;
  }
  if ( v12 >= 0 && UuidFromStringW(bstrVal, v10) )
    goto LABEL_88;
LABEL_136:
  VariantClear(&pvarg);
  if ( v72 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v72 + 16LL))(v72);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x18005f548  mov     [rsp-38h+arg_18], rbx
0x18005f54d  push    rbp
0x18005f54e  push    rsi
0x18005f54f  push    rdi
0x18005f550  push    r12
0x18005f552  push    r13
0x18005f554  push    r14
0x18005f556  push    r15
0x18005f558  mov     rbp, rsp
0x18005f55b  sub     rsp, 60h
0x18005f55f  mov     rax, cs:__security_cookie
0x18005f566  xor     rax, rsp
0x18005f569  mov     [rbp+var_8], rax
0x18005f56d  mov     r15d, r9d
0x18005f570  mov     r12, r8
0x18005f573  mov     r14, rdx
0x18005f576  mov     rbx, rcx
0x18005f579  mov     r13, [rbp+arg_20]
0x18005f57d  xorps   xmm0, xmm0
0x18005f580  xor     eax, eax
0x18005f582  movups  xmmword ptr [rbp+pvarg], xmm0
0x18005f586  mov     qword ptr [rbp+pvarg+10h], rax
0x18005f58a  xor     ecx, ecx
0x18005f58c  cmp     [rdx+21h], cl
0x18005f58f  jnz     short loc_18005F594
0x18005f591  mov     eax, [rdx+1Ch]
0x18005f594  mov     esi, eax
0x18005f596  add     rsi, r12
0x18005f599  mov     [rbp+var_10], rcx
0x18005f59d  lea     rcx, [rbp+pvarg]; pvarg
0x18005f5a1  call    cs:__imp_VariantInit
0x18005f5a7  mov     rax, [rbx]
0x18005f5aa  mov     rdi, [rax]
0x18005f5ad  mov     rcx, [rbp+var_10]
0x18005f5b1  test    rcx, rcx
0x18005f5b4  jz      short loc_18005F5C8
0x18005f5b6  mov     rax, [rcx]
0x18005f5b9  mov     rax, [rax+10h]
0x18005f5bd  call    _guard_dispatch_icall
0x18005f5c2  xor     eax, eax
0x18005f5c4  mov     [rbp+var_10], rax
0x18005f5c8  lea     r8, [rbp+var_10]
0x18005f5cc  lea     rdx, _GUID_2933bf80_7b36_11d2_b20e_00c04f983e60
0x18005f5d3  mov     rcx, rbx
0x18005f5d6  mov     rax, rdi
0x18005f5d9  call    _guard_dispatch_icall
0x18005f5de  mov     ebx, eax
0x18005f5e0  xor     edx, edx
0x18005f5e2  test    eax, eax
0x18005f5e4  js      loc_18005FBA3
0x18005f5ea  cmp     dword ptr [r14+18h], 4
0x18005f5ef  jg      short loc_18005F5F8
0x18005f5f1  mov     ebx, edx
0x18005f5f3  jmp     loc_18005FBA3
0x18005f5f8  mov     edi, 8
0x18005f5fd  cmp     dword ptr [r14+18h], 14h
0x18005f602  jge     short loc_18005F65C
0x18005f604  mov     rcx, [rbp+var_10]
0x18005f608  test    r15d, r15d
0x18005f60b  jz      short loc_18005F63E
0x18005f60d  mov     [rbp+pbstr], rdx
0x18005f611  mov     rax, [rcx]
0x18005f614  lea     rdx, [rbp+pbstr]
0x18005f618  mov     rax, [rax+0D0h]
0x18005f61f  call    _guard_dispatch_icall
0x18005f624  mov     ebx, eax
0x18005f626  xor     edx, edx
0x18005f628  test    eax, eax
0x18005f62a  js      loc_18005FBA3
0x18005f630  mov     word ptr [rbp+pvarg], di
0x18005f634  mov     rdi, [rbp+pbstr]
0x18005f638  mov     qword ptr [rbp+pvarg+8], rdi
0x18005f63c  jmp     short loc_18005F68A
0x18005f63e  mov     rax, [rcx]
0x18005f641  lea     rdx, [rbp+pvarg]
0x18005f645  mov     rax, [rax+40h]
0x18005f649  call    _guard_dispatch_icall
0x18005f64e  mov     ebx, eax
0x18005f650  xor     edx, edx
0x18005f652  test    eax, eax
0x18005f654  js      loc_18005FBA3
0x18005f65a  jmp     short loc_18005F686
0x18005f65c  cmp     dword ptr [r14+18h], 18h
0x18005f661  jnz     short loc_18005F686
0x18005f663  mov     [rbp+pbstr], rdx
0x18005f667  mov     rcx, [rbp+var_10]
0x18005f66b  mov     rax, [rcx]
0x18005f66e  lea     rdx, [rbp+pbstr]
0x18005f672  mov     rax, [rax+110h]
0x18005f679  call    _guard_dispatch_icall
0x18005f67e  mov     ebx, eax
0x18005f680  xor     edx, edx
0x18005f682  test    eax, eax
0x18005f684  jns     short loc_18005F630
0x18005f686  mov     rdi, qword ptr [rbp+pvarg+8]
0x18005f68a  cmp     ebx, 1
0x18005f68d  jnz     short loc_18005F6B9
0x18005f68f  cmp     [r14+20h], dl
0x18005f693  jz      short loc_18005F69F
0x18005f695  mov     ebx, 8024000Dh
0x18005f69a  jmp     loc_18005FBA3
0x18005f69f  cmp     [r14+22h], dl
0x18005f6a3  jz      loc_18005F5F1
0x18005f6a9  mov     rdx, r12
0x18005f6ac  mov     rcx, r14
0x18005f6af  call    SetNodeDefaultValue
0x18005f6b4  jmp     loc_18005FA9C
0x18005f6b9  mov     ecx, [r14+18h]
0x18005f6bd  mov     r15d, 0Bh
0x18005f6c3  cmp     ecx, 0Eh
0x18005f6c6  jg      loc_18005F806
0x18005f6cc  jz      short loc_18005F70F
0x18005f6ce  sub     ecx, 5
0x18005f6d1  jz      loc_18005F7FB
0x18005f6d7  sub     ecx, 1
0x18005f6da  jz      loc_18005F7F0
0x18005f6e0  sub     ecx, 1
0x18005f6e3  jz      loc_18005F7E5
0x18005f6e9  sub     ecx, 1
0x18005f6ec  jz      short loc_18005F70F
0x18005f6ee  sub     ecx, 1
0x18005f6f1  jz      loc_18005F85D
0x18005f6f7  sub     ecx, 1
0x18005f6fa  jz      short loc_18005F70F
0x18005f6fc  sub     ecx, 1
0x18005f6ff  jz      short loc_18005F70F
0x18005f701  sub     ecx, 1
0x18005f704  jz      short loc_18005F70F
0x18005f706  cmp     ecx, 1
0x18005f709  jnz     loc_18005F853
0x18005f70f  mov     r9d, 8; vt
0x18005f715  cmp     word ptr [rbp+pvarg], r9w
0x18005f71a  jz      short loc_18005F73D
0x18005f71c  xor     r8d, r8d; wFlags
0x18005f71f  lea     rdx, [rbp+pvarg]; pvarSrc
0x18005f723  lea     rcx, [rbp+pvarg]; pvargDest
0x18005f727  call    cs:__imp_VariantChangeType
0x18005f72d  mov     ebx, eax
0x18005f72f  xor     edx, edx
0x18005f731  test    eax, eax
0x18005f733  js      loc_18005FBA3
0x18005f739  mov     rdi, qword ptr [rbp+pvarg+8]
0x18005f73d  mov     ecx, [r14+18h]
0x18005f741  cmp     ecx, 0Eh
0x18005f744  jg      loc_18005F9DC
0x18005f74a  jz      loc_18005F988
0x18005f750  sub     ecx, 5
0x18005f753  jz      loc_18005F97E
0x18005f759  sub     ecx, 1
0x18005f75c  jz      loc_18005F97E
0x18005f762  sub     ecx, 1
0x18005f765  jz      loc_18005FA60
0x18005f76b  sub     ecx, 1
0x18005f76e  jz      loc_18005F95F
0x18005f774  sub     ecx, 1
0x18005f777  jz      loc_18005F954
0x18005f77d  sub     ecx, 1
0x18005f780  jz      loc_18005F8DA
0x18005f786  sub     ecx, 1
0x18005f789  jz      loc_18005F8DA
0x18005f78f  sub     ecx, 1
0x18005f792  jz      loc_18005F884
0x18005f798  cmp     ecx, 1
0x18005f79b  jnz     loc_18005FBA3
0x18005f7a1  mov     r14, [r14]
0x18005f7a4  test    rdi, rdi
0x18005f7a7  jz      loc_18005F94A
0x18005f7ad  mov     r15d, edx
0x18005f7b0  cmp     [r14+8], edx
0x18005f7b4  jbe     loc_18005F875
0x18005f7ba  mov     r12d, r15d
0x18005f7bd  add     r12, r12
0x18005f7c0  mov     rdx, [r14]
0x18005f7c3  mov     rdx, [rdx+r12*8]; lpString2
0x18005f7c7  mov     rcx, rdi; lpString1
0x18005f7ca  call    ?AsciiStringCompareI@@YAJPEB_W0@Z; AsciiStringCompareI(wchar_t const *,wchar_t const *)
0x18005f7cf  test    eax, eax
0x18005f7d1  jz      loc_18005F866
0x18005f7d7  inc     r15d
0x18005f7da  cmp     r15d, [r14+8]
0x18005f7de  jb      short loc_18005F7BA
0x18005f7e0  jmp     loc_18005F875
0x18005f7e5  mov     r9d, 15h
0x18005f7eb  jmp     loc_18005F715
0x18005f7f0  mov     r9d, 13h
0x18005f7f6  jmp     loc_18005F715
0x18005f7fb  mov     r9d, 3
0x18005f801  jmp     loc_18005F715
0x18005f806  sub     ecx, 0Fh
0x18005f809  jz      loc_18005F70F
0x18005f80f  sub     ecx, 1
0x18005f812  jz      loc_18005F70F
0x18005f818  sub     ecx, 1
0x18005f81b  jz      loc_18005F70F
0x18005f821  sub     ecx, 1
0x18005f824  jz      loc_18005F70F
0x18005f82a  sub     ecx, 1
0x18005f82d  jz      short loc_18005F85D
0x18005f82f  sub     ecx, 2
0x18005f832  jz      loc_18005F73D
0x18005f838  sub     ecx, 1
0x18005f83b  jz      loc_18005F73D
0x18005f841  sub     ecx, 1
0x18005f844  jz      loc_18005F73D
0x18005f84a  cmp     ecx, 1
0x18005f84d  jz      loc_18005F73D
0x18005f853  mov     ebx, 80070057h
0x18005f858  jmp     loc_18005FBA3
0x18005f85d  movzx   r9d, r15w
0x18005f861  jmp     loc_18005F715
0x18005f866  mov     rax, [r14]
0x18005f869  cmp     dword ptr [rax+r12*8+8], 1
0x18005f86f  jnz     short loc_18005F875
0x18005f871  bts     dword ptr [rsi], 0Bh
0x18005f875  cmp     r15d, [r14+8]
0x18005f879  jnz     loc_18005FBA3
0x18005f87f  jmp     loc_18005F94A
0x18005f884  mov     r14, [r14]
0x18005f887  lea     r15, dword_1800937AC
0x18005f88e  test    rdi, rdi
0x18005f891  cmovnz  r15, rdi
0x18005f895  mov     edi, edx
0x18005f897  cmp     [r14+8], edx
0x18005f89b  jbe     short loc_18005F8BD
0x18005f89d  mov     eax, edi
0x18005f89f  add     rax, rax
0x18005f8a2  mov     rdx, [r14]
0x18005f8a5  mov     rdx, [rdx+rax*8]; lpString2
0x18005f8a9  mov     rcx, r15; lpString1
0x18005f8ac  call    ?AsciiStringCompareI@@YAJPEB_W0@Z; AsciiStringCompareI(wchar_t const *,wchar_t const *)
0x18005f8b1  test    eax, eax
0x18005f8b3  jz      short loc_18005F8BD
0x18005f8b5  inc     edi
0x18005f8b7  cmp     edi, [r14+8]
0x18005f8bb  jb      short loc_18005F89D
0x18005f8bd  cmp     edi, [r14+8]
0x18005f8c1  jz      loc_18005F94A
0x18005f8c7  mov     ecx, edi
0x18005f8c9  add     rcx, rcx
0x18005f8cc  mov     rax, [r14]
0x18005f8cf  mov     ecx, [rax+rcx*8+8]
0x18005f8d3  mov     [rsi], ecx
0x18005f8d5  jmp     loc_18005FBA3
0x18005f8da  test    rdi, rdi
0x18005f8dd  jnz     short loc_18005F8F3
0x18005f8df  mov     al, [r14+20h]
0x18005f8e3  neg     al
0x18005f8e5  sbb     ecx, ecx
0x18005f8e7  mov     ebx, 8024000Dh
0x18005f8ec  and     ebx, ecx
0x18005f8ee  jmp     loc_18005FBA3
0x18005f8f3  mov     rcx, rdi; pbstr
0x18005f8f6  call    cs:__imp_SysStringLen
0x18005f8fc  cmp     [r14+18h], r15d
0x18005f900  jnz     short loc_18005F929
0x18005f902  cmp     eax, 26h ; '&'
0x18005f905  jnz     short loc_18005F922
0x18005f907  cmp     word ptr [rdi], 7Bh ; '{'
0x18005f90b  jnz     short loc_18005F922
0x18005f90d  cmp     word ptr [rdi+4Ah], 7Dh ; '}'
0x18005f912  jnz     short loc_18005F922
0x18005f914  xor     r13d, r13d
0x18005f917  mov     [rdi+4Ah], r13w
0x18005f91c  add     rdi, 2
0x18005f920  jmp     short loc_18005F92E
0x18005f922  mov     ebx, 8024000Eh
0x18005f927  jmp     short loc_18005F92E
0x18005f929  cmp     eax, 24h ; '$'
0x18005f92c  jnz     short loc_18005F94A
0x18005f92e  test    ebx, ebx
0x18005f930  js      loc_18005FBA3
0x18005f936  mov     rdx, rsi; Uuid
0x18005f939  mov     rcx, rdi; StringUuid
0x18005f93c  call    cs:__imp_UuidFromStringW
0x18005f942  test    eax, eax
0x18005f944  jz      loc_18005FBA3
0x18005f94a  mov     ebx, 8024000Eh
0x18005f94f  jmp     loc_18005FBA3
0x18005f954  mov     eax, edx
0x18005f956  cmp     word ptr [rbp+pvarg+8], dx
0x18005f95a  setnz   al
0x18005f95d  jmp     short loc_18005F981
0x18005f95f  test    rdi, rdi
0x18005f962  jz      short loc_18005F94A
0x18005f964  xor     r8d, r8d
0x18005f967  mov     rdx, rsi
0x18005f96a  mov     rcx, rdi
0x18005f96d  call    StringToFileTime
0x18005f972  mov     ebx, eax
0x18005f974  cmp     eax, 80070057h
0x18005f979  jmp     loc_18005F879
0x18005f97e  mov     eax, dword ptr [rbp+pvarg+8]
0x18005f981  mov     [rsi], eax
0x18005f983  jmp     loc_18005FBA3
0x18005f988  mov     r14, [r14]
0x18005f98b  test    rdi, rdi
0x18005f98e  jz      short loc_18005F94A
0x18005f990  mov     r15d, edx
0x18005f993  cmp     [r14+8], edx
0x18005f997  jbe     loc_18005F875
  ... truncated ...
```
