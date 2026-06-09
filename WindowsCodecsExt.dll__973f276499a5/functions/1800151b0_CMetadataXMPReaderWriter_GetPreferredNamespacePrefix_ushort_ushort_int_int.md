# CMetadataXMPReaderWriter::GetPreferredNamespacePrefix(ushort *,ushort * *,int,int *)

- ea: `0x1800151b0`
- end: `0x1800153b0`
- name: `?GetPreferredNamespacePrefix@CMetadataXMPReaderWriter@@MEAAJPEAGPEAPEAGHPEAH@Z`
- size: `512`
- prototype: `__int64 __usercall@<rax>(CMetadataXMPReaderWriter *__hidden this@<rcx>, unsigned __int16 *@<rdx>, unsigned __int16 **@<r8>, int@<r9d>, int *)`
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180004500`
- `0x18000e82c`
- `0x1800108fc`
- `0x1800151b0`
- `0x1800153b8`
- `0x180015440`
- `0x1800171c4`
- `0x180033010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x1800152de`
- `OLEAUT32!__imp_SysAllocString` at `0x180015314`
- `OLEAUT32!__imp_SysAllocString` at `0x1800152de`
- `OLEAUT32!__imp_SysAllocString` at `0x180015314`
- `OLEAUT32!__imp_SysStringLen` at `0x1800151ea`
- `OLEAUT32!__imp_SysStringLen` at `0x180015245`
- `OLEAUT32!__imp_SysStringLen` at `0x1800151ea`
- `OLEAUT32!__imp_SysStringLen` at `0x180015245`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180015265`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180015265`

## pseudocode

```c
__int64 __fastcall CMetadataXMPReaderWriter::GetPreferredNamespacePrefix(
        CMetadataXMPReaderWriter *this,
        unsigned __int16 *a2,
        unsigned __int16 **a3,
        __int64 a4,
        int *a5)
{
  struct XMLItem *v6; // rdi
  CMetadataRDFReaderWriter *v9; // rcx
  __int64 i; // rsi
  __int64 v11; // r15
  int ValueAsBSTR; // eax
  unsigned int v13; // ebx
  UINT v14; // eax
  OLECHAR *v15; // rsi
  int PreferredNamespacePrefix; // eax
  BSTR v17; // rax
  int v18; // eax
  int v19; // ecx
  BSTR v20; // rax
  struct XMLItem *v22; // [rsp+30h] [rbp-20h] BYREF
  OLECHAR *psz; // [rsp+38h] [rbp-18h] BYREF
  BSTR pbstr; // [rsp+40h] [rbp-10h] BYREF
  int v25; // [rsp+90h] [rbp+40h]
  UINT cchCount2; // [rsp+B0h] [rbp+60h]

  v6 = 0;
  v22 = 0;
  psz = 0;
  v25 = 0;
  *a5 = 0;
  cchCount2 = SysStringLen(a2);
  for ( i = 0; ; i = (unsigned int)(i + 1) )
  {
    if ( (unsigned int)i >= *((_DWORD *)this + 72) )
      goto LABEL_10;
    v9 = (CMetadataRDFReaderWriter *)*((_QWORD *)this + 33);
    v11 = *((_QWORD *)v9 + i);
    if ( (*(_BYTE *)(v11 + 8) & 1) != 0 )
    {
      pbstr = 0;
      ValueAsBSTR = Item::GetValueAsBSTR((Item *)v11, &pbstr, 0);
      v13 = ValueAsBSTR;
      if ( ValueAsBSTR < 0 )
      {
        if ( !g_doStackCaptures )
          goto LABEL_28;
        goto LABEL_23;
      }
      v14 = SysStringLen(pbstr);
      if ( CompareStringW(0x400u, 0, pbstr, v14, a2, cchCount2) == 2 )
        break;
    }
  }
  v15 = *(OLECHAR **)(v11 + 40);
  psz = v15;
  if ( v15 )
  {
LABEL_27:
    psz = 0;
    *a3 = v15;
    goto LABEL_28;
  }
LABEL_10:
  PreferredNamespacePrefix = CMetadataRDFReaderWriter::CreateXmlItem(v9, &v22);
  v13 = PreferredNamespacePrefix;
  if ( PreferredNamespacePrefix < 0
    || (PreferredNamespacePrefix = CMetadataRDFReaderWriter::GetPreferredNamespacePrefix(this, a2, &psz, 1, a5),
        v13 = PreferredNamespacePrefix,
        PreferredNamespacePrefix < 0) )
  {
    if ( g_doStackCaptures )
      DoStackCapture(PreferredNamespacePrefix);
    v6 = v22;
  }
  else
  {
    v15 = psz;
    v6 = v22;
    v25 = 1;
    v17 = SysAllocString(psz);
    *((_QWORD *)v6 + 5) = v17;
    v13 = -2147024882;
    if ( v17 )
    {
      v20 = SysAllocString(a2);
      *((_QWORD *)v6 + 4) = v20;
      if ( v20 )
      {
        *((_DWORD *)v6 + 2) = 1;
        ValueAsBSTR = CMILObjectArray<RDFItem *>::Add((char *)this + 264, &v22);
        v13 = ValueAsBSTR;
        if ( ValueAsBSTR < 0 )
        {
          if ( !g_doStackCaptures )
            goto LABEL_28;
LABEL_23:
          v19 = ValueAsBSTR;
LABEL_24:
          DoStackCapture(v19);
          goto LABEL_28;
        }
        v6 = 0;
        *a5 = 1;
        goto LABEL_27;
      }
    }
    v18 = g_doStackCaptures;
    if ( g_doStackCaptures )
    {
      DoStackCapture(-2147024882);
      v18 = g_doStackCaptures;
    }
    if ( v18 )
    {
      v19 = -2147024882;
      goto LABEL_24;
    }
  }
LABEL_28:
  if ( v6 )
    (**(void (__fastcall ***)(struct XMLItem *, __int64))v6)(v6, 1);
  if ( v25 )
    FreeBSTR(&psz);
  return v13;
}

```

## disassembly

```asm
0x1800151b0  mov     [rsp-38h+arg_8], rbx
0x1800151b5  mov     [rsp-38h+arg_10], r8
0x1800151ba  push    rbp
0x1800151bb  push    rsi
0x1800151bc  push    rdi
0x1800151bd  push    r12
0x1800151bf  push    r13
0x1800151c1  push    r14
0x1800151c3  push    r15
0x1800151c5  mov     rbp, rsp
0x1800151c8  sub     rsp, 50h
0x1800151cc  mov     r13, [rbp+arg_20]
0x1800151d0  xor     edi, edi
0x1800151d2  mov     r14, rcx
0x1800151d5  mov     [rbp+var_20], rdi
0x1800151d9  mov     rcx, rdx; pbstr
0x1800151dc  mov     [rbp+psz], rdi
0x1800151e0  mov     r12, rdx
0x1800151e3  mov     [rbp+arg_0], edi
0x1800151e6  mov     [r13+0], edi
0x1800151ea  call    cs:__imp_SysStringLen
0x1800151f0  mov     dword ptr [rbp+arg_20], eax
0x1800151f3  xor     esi, esi
0x1800151f5  cmp     esi, [r14+120h]
0x1800151fc  jnb     loc_180015285
0x180015202  mov     rcx, [r14+108h]
0x180015209  mov     r15, [rcx+rsi*8]
0x18001520d  test    byte ptr [r15+8], 1
0x180015212  jz      short loc_180015270
0x180015214  xor     r8d, r8d; int
0x180015217  mov     [rbp+pbstr], rdi
0x18001521b  lea     rdx, [rbp+pbstr]; unsigned __int16 **
0x18001521f  mov     rcx, r15; this
0x180015222  call    ?GetValueAsBSTR@Item@@QEAAJPEAPEAGH@Z; Item::GetValueAsBSTR(ushort * *,int)
0x180015227  mov     ebx, eax
0x180015229  test    eax, eax
0x18001522b  jns     short loc_180015241
0x18001522d  cmp     cs:?g_doStackCaptures@@3HA, edi; int g_doStackCaptures
0x180015233  jnz     loc_180015349
0x180015239  test    eax, eax
0x18001523b  js      loc_18001536F
0x180015241  mov     rcx, [rbp+pbstr]; pbstr
0x180015245  call    cs:__imp_SysStringLen
0x18001524b  mov     ecx, dword ptr [rbp+arg_20]
0x18001524e  xor     edx, edx; dwCmpFlags
0x180015250  mov     r8, [rbp+pbstr]; lpString1
0x180015254  mov     r9d, eax; cchCount1
0x180015257  mov     [rsp+50h+cchCount2], ecx; cchCount2
0x18001525b  mov     ecx, 400h; Locale
0x180015260  mov     [rsp+50h+lpString2], r12; lpString2
0x180015265  call    cs:__imp_CompareStringW
0x18001526b  cmp     eax, 2
0x18001526e  jz      short loc_180015274
0x180015270  inc     esi
0x180015272  jmp     short loc_1800151F5
0x180015274  mov     rsi, [r15+28h]
0x180015278  mov     [rbp+psz], rsi
0x18001527c  test    rsi, rsi
0x18001527f  jnz     loc_180015360
0x180015285  lea     rdx, [rbp+var_20]; struct XMLItem **
0x180015289  call    ?CreateXmlItem@CMetadataRDFReaderWriter@@IEBAJPEAPEAVXMLItem@@@Z; CMetadataRDFReaderWriter::CreateXmlItem(XMLItem * *)
0x18001528e  mov     ebx, eax
0x180015290  test    eax, eax
0x180015292  jns     short loc_1800152AC
0x180015294  cmp     cs:?g_doStackCaptures@@3HA, edi; int g_doStackCaptures
0x18001529a  jz      short loc_1800152A3
0x18001529c  mov     ecx, eax; int
0x18001529e  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1800152a3  mov     rdi, [rbp+var_20]
0x1800152a7  jmp     loc_18001536F
0x1800152ac  mov     r9d, 1; int
0x1800152b2  mov     [rsp+50h+lpString2], r13; int *
0x1800152b7  lea     r8, [rbp+psz]; unsigned __int16 **
0x1800152bb  mov     rdx, r12; unsigned __int16 *
0x1800152be  mov     rcx, r14; this
0x1800152c1  call    ?GetPreferredNamespacePrefix@CMetadataRDFReaderWriter@@MEAAJPEAGPEAPEAGHPEAH@Z; CMetadataRDFReaderWriter::GetPreferredNamespacePrefix(ushort *,ushort * *,int,int *)
0x1800152c6  mov     ebx, eax
0x1800152c8  test    eax, eax
0x1800152ca  js      short loc_180015294
0x1800152cc  mov     rsi, [rbp+psz]
0x1800152d0  mov     rdi, [rbp+var_20]
0x1800152d4  mov     rcx, rsi; psz
0x1800152d7  mov     [rbp+arg_0], 1
0x1800152de  call    cs:__imp_SysAllocString
0x1800152e4  mov     [rdi+28h], rax
0x1800152e8  mov     ebx, 8007000Eh
0x1800152ed  test    rax, rax
0x1800152f0  jnz     short loc_180015311
0x1800152f2  mov     eax, cs:?g_doStackCaptures@@3HA; int g_doStackCaptures
0x1800152f8  test    eax, eax
0x1800152fa  jz      short loc_180015309
0x1800152fc  mov     ecx, ebx; int
0x1800152fe  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x180015303  mov     eax, cs:?g_doStackCaptures@@3HA; int g_doStackCaptures
0x180015309  test    eax, eax
0x18001530b  jz      short loc_18001536F
0x18001530d  mov     ecx, ebx
0x18001530f  jmp     short loc_18001534B
0x180015311  mov     rcx, r12; psz
0x180015314  call    cs:__imp_SysAllocString
0x18001531a  mov     [rdi+20h], rax
0x18001531e  test    rax, rax
0x180015321  jz      short loc_1800152F2
0x180015323  lea     rcx, [r14+108h]
0x18001532a  mov     dword ptr [rdi+8], 1
0x180015331  lea     rdx, [rbp+var_20]
0x180015335  call    ?Add@?$CMILObjectArray@PEAVRDFItem@@@@QEAAJAEAPEAVRDFItem@@@Z; CMILObjectArray<RDFItem *>::Add(RDFItem * &)
0x18001533a  mov     ebx, eax
0x18001533c  test    eax, eax
0x18001533e  jns     short loc_180015356
0x180015340  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x180015347  jz      short loc_180015352
0x180015349  mov     ecx, eax; int
0x18001534b  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x180015350  jmp     short loc_18001536F
0x180015352  test    eax, eax
0x180015354  js      short loc_18001536F
0x180015356  xor     edi, edi
0x180015358  mov     dword ptr [r13+0], 1
0x180015360  mov     rax, [rbp+arg_10]
0x180015364  mov     [rbp+psz], 0
0x18001536c  mov     [rax], rsi
0x18001536f  test    rdi, rdi
0x180015372  jz      short loc_180015387
0x180015374  mov     rax, [rdi]
0x180015377  mov     edx, 1
0x18001537c  mov     rcx, rdi
0x18001537f  mov     rax, [rax]
0x180015382  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015387  cmp     [rbp+arg_0], 0
0x18001538b  jz      short loc_180015396
0x18001538d  lea     rcx, [rbp+psz]; unsigned __int16 **
0x180015391  call    ?FreeBSTR@@YAXAEAPEAG@Z; FreeBSTR(ushort * &)
0x180015396  mov     eax, ebx
0x180015398  mov     rbx, [rsp+50h+arg_8]
0x1800153a0  add     rsp, 50h
0x1800153a4  pop     r15
0x1800153a6  pop     r14
0x1800153a8  pop     r13
0x1800153aa  pop     r12
0x1800153ac  pop     rdi
0x1800153ad  pop     rsi
0x1800153ae  pop     rbp
0x1800153af  retn
```
