# ChartE2o::HrWriteDrawingChartTag(Ofc::IWriterParams &,wchar_t *,int)

- ea: `0x18015d3f0`
- end: `0x18015d7a0`
- name: `?HrWriteDrawingChartTag@ChartE2o@@AEBAJAEAVIWriterParams@Ofc@@PEA_WH@Z`
- size: `944`
- prototype: `__int64 __fastcall(ChartE2o *__hidden this, struct Ofc::IWriterParams *, wchar_t *, int)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180156650`

## callees

- `0x1800a4300`
- `0x1800a7a90`
- `0x18015d3f0`
- `0x1801f5a30`
- `0x18026e570`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18015d55b`
- `OLEAUT32!__imp_SysAllocString` at `0x18015d62e`
- `OLEAUT32!__imp_SysAllocString` at `0x18015d6f3`
- `OLEAUT32!__imp_SysAllocString` at `0x18015d55b`
- `OLEAUT32!__imp_SysAllocString` at `0x18015d62e`
- `OLEAUT32!__imp_SysAllocString` at `0x18015d6f3`
- `OLEAUT32!__imp_SysFreeString` at `0x18015d5ab`
- `OLEAUT32!__imp_SysFreeString` at `0x18015d683`
- `OLEAUT32!__imp_SysFreeString` at `0x18015d732`
- `OLEAUT32!__imp_SysFreeString` at `0x18015d5ab`
- `OLEAUT32!__imp_SysFreeString` at `0x18015d683`
- `OLEAUT32!__imp_SysFreeString` at `0x18015d732`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x180390b90`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x180390ba7`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x180390bb5`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x180390bcc`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x180390bda`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x180390bfe`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x180390b90`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x180390ba7`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x180390bb5`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x180390bcc`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x180390bda`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x180390bfe`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x180390b9c`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x180390bc1`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x180390be6`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x180390c0a`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x180390b9c`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x180390bc1`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x180390be6`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x180390c0a`
- `mso40uiWin32Client!__imp_?EmitStartElement@CWriterEmit@Ofc@@UEAAXAEAUIMXAttributes@@@Z` at `0x18015d762`
- `mso40uiWin32Client!__imp_?EmitStartElement@CWriterEmit@Ofc@@UEAAXAEAUIMXAttributes@@@Z` at `0x18015d762`
- `mso40uiWin32Client!__imp_??0CWriterEmit@Ofc@@QEAA@AEAUISAXContentHandler@@PEB_W1@Z` at `0x18015d754`
- `mso40uiWin32Client!__imp_??0CWriterEmit@Ofc@@QEAA@AEAUISAXContentHandler@@PEB_W1@Z` at `0x18015d754`
- `mso40uiWin32Client!__imp_?EmitEndElement@CWriterEmit@Ofc@@QEAAXXZ` at `0x18015d76e`
- `mso40uiWin32Client!__imp_?EmitEndElement@CWriterEmit@Ofc@@QEAAXXZ` at `0x18015d76e`

## string_xrefs

- `0x18015d466`: `xmlns:`
- `0x18015d57f`: `http://purl.oclc.org/ooxml/drawingml/chart`
- `0x18015d575`: `http://schemas.openxmlformats.org/drawingml/2006/chart`
- `0x18015d65b`: `http://purl.oclc.org/ooxml/officeDocument/relationships`
- `0x18015d64a`: `http://schemas.openxmlformats.org/officeDocument/2006/relationships`

## pseudocode

```c
__int64 __fastcall ChartE2o::HrWriteDrawingChartTag(ChartE2o *this, struct Ofc::IWriterParams *a2, wchar_t *a3, int a4)
{
  __int64 v4; // r14
  __int64 v6; // rsi
  struct IMXAttributes *v7; // r15
  __int64 v8; // rbx
  unsigned __int64 v9; // rbx
  __int64 v10; // r12
  char *v11; // rbx
  __int64 v12; // rcx
  __int64 v13; // rdx
  _BOOL8 v14; // rax
  BOOL v15; // ecx
  unsigned __int64 v16; // r8
  unsigned __int64 v17; // rdi
  OLECHAR *v18; // rdi
  int v19; // eax
  const wchar_t *v20; // rcx
  int v21; // ebx
  OLECHAR *v22; // rdi
  char *v23; // rsi
  __int64 v24; // rdx
  unsigned __int64 v25; // r8
  unsigned __int64 v26; // rdi
  BSTR v27; // rax
  const wchar_t *v28; // rcx
  OLECHAR *v29; // rdi
  __int64 v30; // rdx
  __int64 v31; // rax
  unsigned __int64 v32; // rdi
  BSTR v33; // rax
  __int64 v35; // [rsp+40h] [rbp-C0h] BYREF
  __int64 Src; // [rsp+48h] [rbp-B8h] BYREF
  int v37; // [rsp+50h] [rbp-B0h]
  wchar_t v38; // [rsp+54h] [rbp-ACh]
  wchar_t *v39; // [rsp+58h] [rbp-A8h]
  struct ISAXContentHandler *v40; // [rsp+60h] [rbp-A0h]
  _BYTE v41[560]; // [rsp+70h] [rbp-90h] BYREF
  OLECHAR psz; // [rsp+2A0h] [rbp+1A0h] BYREF
  _WORD v43[19]; // [rsp+2A2h] [rbp+1A2h] BYREF
  __int64 v44; // [rsp+2C8h] [rbp+1C8h] BYREF
  int v45; // [rsp+2D0h] [rbp+1D0h]

  v4 = -1;
  v45 = *(_DWORD *)L"t";
  v6 = -1;
  v37 = *(_DWORD *)L"s:";
  v38 = aXmlns[6];
  v44 = *(_QWORD *)L"chart";
  v35 = 0x640069003ALL;
  v39 = a3;
  Src = *(_QWORD *)L"xmlns:";
  do
    ++v6;
  while ( *((_WORD *)&Src + v6) );
  do
    ++v4;
  while ( *((_WORD *)&v35 + v4) );
  v7 = (struct IMXAttributes *)*((_QWORD *)a2 + 2);
  v8 = (unsigned int)v6;
  v40 = (struct ISAXContentHandler *)*((_QWORD *)a2 + 1);
  if ( (unsigned int)v6 > 0x14 )
    v8 = 20;
  v9 = v8;
  if ( v9 > 20 )
    v9 = 20;
  if ( v9 * 2 )
    memcpy_0(&psz, &Src, v9 * 2);
  v10 = 1;
  v11 = (char *)&v43[v9 - 1];
  v12 = ((char *)&v44 - v11) >> 1;
  v13 = (unsigned int)v12;
  v14 = (_DWORD)v12 != 0;
  v15 = v12 != 0;
  v16 = 2 * v13;
  if ( 2 * v14 <= (unsigned __int64)(2 * v13) )
    v13 = v15;
  v17 = 2 * v13;
  if ( 2 * v13 )
  {
    if ( v11 )
    {
      if ( v16 >= v17 )
      {
        memmove_0(v11, &Mso::Xsd::Namespaces::c_wzChartE2oShort, 2 * v13);
        goto LABEL_16;
      }
      *_errno() = 34;
    }
    else
    {
      *_errno() = 22;
    }
    _invalid_parameter_noinfo();
  }
LABEL_16:
  *(_WORD *)&v11[v17] = 0;
  v18 = SysAllocString(&psz);
  v19 = -2147024882;
  if ( v18 )
  {
    v20 = L"http://purl.oclc.org/ooxml/drawingml/chart";
    if ( !a4 )
      v20 = L"http://schemas.openxmlformats.org/drawingml/2006/chart";
    v19 = ((__int64 (__fastcall *)(struct IMXAttributes *, _QWORD, _QWORD, OLECHAR *, _QWORD, const wchar_t *))v7->lpVtbl->addAttribute)(
            v7,
            0,
            0,
            v18,
            0,
            v20);
  }
  v21 = v19;
  SysFreeString(v18);
  v22 = 0;
  if ( v21 >= 0 )
  {
    v23 = (char *)&v43[(int)v6 - 1];
    v24 = (unsigned int)(((char *)&v44 - v23) >> 1);
    if ( !(unsigned int)(((char *)&v44 - v23) >> 1) )
      v10 = 0;
    v25 = 2 * v24;
    if ( 2 * v10 <= (unsigned __int64)(2 * v24) )
      v24 = (unsigned int)v10;
    v26 = 2 * v24;
    if ( !(2 * v24) )
      goto LABEL_29;
    if ( v23 )
    {
      if ( v25 >= v26 )
      {
        memcpy_0(v23, &Mso::Xsd::Namespaces::c_wzOfficeRelsShort, 2 * v24);
LABEL_29:
        *(_WORD *)&v23[v26] = 0;
        v27 = SysAllocString(&psz);
        v22 = v27;
        if ( !v27 )
          v21 = -2147024882;
        if ( v21 >= 0 )
        {
          v28 = L"http://purl.oclc.org/ooxml/officeDocument/relationships";
          if ( !a4 )
            v28 = L"http://schemas.openxmlformats.org/officeDocument/2006/relationships";
          v21 = ((__int64 (__fastcall *)(struct IMXAttributes *, _QWORD, _QWORD, BSTR, _QWORD, const wchar_t *))v7->lpVtbl->addAttribute)(
                  v7,
                  0,
                  0,
                  v27,
                  0,
                  v28);
        }
        goto LABEL_35;
      }
      *_errno() = 34;
    }
    else
    {
      *_errno() = 22;
    }
    _invalid_parameter_noinfo();
    goto LABEL_29;
  }
LABEL_35:
  SysFreeString(v22);
  v29 = 0;
  if ( v21 >= 0 )
  {
    v30 = 19;
    psz = Mso::Xsd::Namespaces::c_wzOfficeRelsShort;
    v31 = 19;
    if ( (unsigned int)v4 <= 0x13 )
      v31 = (unsigned int)v4;
    if ( (unsigned __int64)(2 * v31) <= 0x26 )
      v30 = (unsigned int)v31;
    v32 = v30;
    if ( 2 * v30 )
    {
      if ( v32 > 19 )
      {
        *_errno() = 34;
        _invalid_parameter_noinfo();
      }
      else
      {
        memcpy_0(v43, &v35, 2 * v30);
      }
    }
    v43[v32] = 0;
    v33 = SysAllocString(&psz);
    v29 = v33;
    if ( !v33 )
      v21 = -2147024882;
    if ( v21 >= 0 )
      v21 = ((__int64 (__fastcall *)(struct IMXAttributes *, _QWORD, _QWORD, BSTR, _QWORD, wchar_t *))v7->lpVtbl->addAttribute)(
              v7,
              0,
              0,
              v33,
              0,
              v39);
  }
  SysFreeString(v29);
  if ( v21 >= 0 )
  {
    Ofc::CWriterEmit::CWriterEmit(
      (Ofc::CWriterEmit *)v41,
      v40,
      (const wchar_t *)&Mso::Xsd::Namespaces::c_wzChartE2oShort,
      (const wchar_t *)&v44);
    Ofc::CWriterEmit::EmitStartElement((Ofc::CWriterEmit *)v41, v7);
    Ofc::CWriterEmit::EmitEndElement((Ofc::CWriterEmit *)v41);
  }
  return (unsigned int)v21;
}

```

## disassembly

```asm
0x18015d3f0  mov     [rsp-8+arg_0], rbx
0x18015d3f5  push    rbp
0x18015d3f6  push    rsi
0x18015d3f7  push    rdi
0x18015d3f8  push    r12
0x18015d3fa  push    r13
0x18015d3fc  push    r14
0x18015d3fe  push    r15
0x18015d400  lea     rbp, [rsp-1E0h]
0x18015d408  sub     rsp, 2E0h
0x18015d40f  mov     rax, cs:__security_cookie
0x18015d416  xor     rax, rsp
0x18015d419  mov     [rbp+210h+var_38], rax
0x18015d420  mov     eax, dword ptr cs:aChart_0+8; "t"
0x18015d426  or      r14, 0FFFFFFFFFFFFFFFFh
0x18015d42a  movsd   xmm0, qword ptr cs:aChart_0; "chart"
0x18015d432  mov     r13d, r9d
0x18015d435  mov     [rbp+210h+var_40], eax
0x18015d43b  mov     rsi, r14
0x18015d43e  mov     eax, dword ptr cs:aXmlns+8; "s:"
0x18015d444  mov     [rsp+310h+var_2C0], eax
0x18015d448  movzx   eax, word ptr cs:aXmlns+0Ch; ""
0x18015d44f  mov     [rsp+310h+var_2BC], ax
0x18015d454  mov     rax, 640069003Ah
0x18015d45e  movsd   [rbp+210h+var_48], xmm0
0x18015d466  movsd   xmm0, qword ptr cs:aXmlns; "xmlns:"
0x18015d46e  mov     [rsp+310h+var_2D0], rax
0x18015d473  lea     rax, [rsp+310h+Src]
0x18015d478  mov     [rsp+310h+var_2B8], r8
0x18015d47d  xor     r8d, r8d
0x18015d480  movsd   [rsp+310h+Src], xmm0
0x18015d486  inc     rsi
0x18015d489  cmp     [rax+rsi*2], r8w
0x18015d48e  jnz     short loc_18015D486
0x18015d490  lea     rax, [rsp+310h+var_2D0]
0x18015d495  inc     r14
0x18015d498  cmp     [rax+r14*2], r8w
0x18015d49d  jnz     short loc_18015D495
0x18015d49f  mov     rax, [rdx+8]
0x18015d4a4  mov     ecx, 14h
0x18015d4a9  mov     r15, [rdx+10h]
0x18015d4ad  cmp     esi, ecx
0x18015d4af  mov     ebx, esi
0x18015d4b1  mov     [rsp+310h+var_2B0], rax
0x18015d4b6  cmova   ebx, ecx
0x18015d4b9  add     rbx, rbx
0x18015d4bc  lea     eax, [rcx+14h]
0x18015d4bf  cmp     rbx, rax
0x18015d4c2  cmova   rbx, rax
0x18015d4c6  test    rbx, rbx
0x18015d4c9  jz      short loc_18015D4E8
0x18015d4cb  cmp     rbx, rax
0x18015d4ce  ja      loc_180390B90
0x18015d4d4  mov     r8, rbx; Size
0x18015d4d7  lea     rdx, [rsp+310h+Src]; Src
0x18015d4dc  lea     rcx, [rbp+210h+psz]; void *
0x18015d4e3  call    memcpy_0
0x18015d4e8  lea     rcx, [rbp+210h+psz]
0x18015d4ef  mov     r12d, 1
0x18015d4f5  add     rbx, rcx
0x18015d4f8  mov     eax, r12d
0x18015d4fb  lea     rcx, [rbp+210h+var_48]
0x18015d502  sub     rcx, rbx
0x18015d505  sar     rcx, 1
0x18015d508  cmp     ecx, r12d
0x18015d50b  mov     edx, ecx
0x18015d50d  cmovb   eax, ecx
0x18015d510  mov     ecx, eax
0x18015d512  add     rax, rax
0x18015d515  lea     r8, [rdx+rdx]
0x18015d519  cmp     rax, r8
0x18015d51c  cmovbe  edx, ecx
0x18015d51f  lea     rdi, [rdx+rdx]
0x18015d523  test    rdi, rdi
0x18015d526  jz      short loc_18015D54C
0x18015d528  test    rbx, rbx
0x18015d52b  jz      loc_180390BA7
0x18015d531  cmp     r8, rdi
0x18015d534  jb      loc_180390BB5
0x18015d53a  mov     r8, rdi; Size
0x18015d53d  lea     rdx, ?c_wzChartE2oShort@Namespaces@Xsd@Mso@@3QB_WB; Src
0x18015d544  mov     rcx, rbx; void *
0x18015d547  call    memmove_0
0x18015d54c  xor     r8d, r8d
0x18015d54f  lea     rcx, [rbp+210h+psz]; psz
0x18015d556  mov     [rdi+rbx], r8w
0x18015d55b  call    cs:__imp_SysAllocString
0x18015d561  mov     rdi, rax
0x18015d564  xor     r8d, r8d
0x18015d567  mov     eax, 8007000Eh
0x18015d56c  test    rdi, rdi
0x18015d56f  jz      short loc_18015D5A6
0x18015d571  mov     rax, [r15]
0x18015d575  lea     rdx, aHttpSchemasOpe_0; "http://schemas.openxmlformats.org/drawi"...
0x18015d57c  test    r13d, r13d
0x18015d57f  lea     rcx, aHttpPurlOclcOr; "http://purl.oclc.org/ooxml/drawingml/ch"...
0x18015d586  mov     r9, rdi
0x18015d589  cmovz   rcx, rdx
0x18015d58d  xor     edx, edx
0x18015d58f  mov     rax, [rax+38h]
0x18015d593  mov     [rsp+310h+var_2E8], rcx
0x18015d598  mov     rcx, r15
0x18015d59b  mov     [rsp+310h+var_2F0], r8
0x18015d5a0  call    cs:__guard_dispatch_icall_fptr
0x18015d5a6  mov     rcx, rdi; bstrString
0x18015d5a9  mov     ebx, eax
0x18015d5ab  call    cs:__imp_SysFreeString
0x18015d5b1  xor     eax, eax
0x18015d5b3  mov     edi, eax
0x18015d5b5  test    ebx, ebx
0x18015d5b7  js      loc_180390BF1
0x18015d5bd  movsxd  rcx, esi
0x18015d5c0  lea     rsi, [rbp+210h+psz]
0x18015d5c7  lea     rsi, [rsi+rcx*2]
0x18015d5cb  lea     rcx, [rbp+210h+var_48]
0x18015d5d2  sub     rcx, rsi
0x18015d5d5  sar     rcx, 1
0x18015d5d8  cmp     ecx, r12d
0x18015d5db  mov     edx, ecx
0x18015d5dd  cmovb   r12d, ecx
0x18015d5e1  mov     ecx, r12d
0x18015d5e4  lea     r8, [rdx+rdx]
0x18015d5e8  lea     rax, [r12+r12]
0x18015d5ec  cmp     rax, r8
0x18015d5ef  cmovbe  edx, ecx
0x18015d5f2  xor     r12d, r12d
0x18015d5f5  lea     rdi, [rdx+rdx]
0x18015d5f9  test    rdi, rdi
0x18015d5fc  jz      short loc_18015D622
0x18015d5fe  test    rsi, rsi
0x18015d601  jz      loc_180390BCC
0x18015d607  cmp     r8, rdi
0x18015d60a  jb      loc_180390BDA
0x18015d610  mov     r8, rdi; Size
0x18015d613  lea     rdx, ?c_wzOfficeRelsShort@Namespaces@Xsd@Mso@@3QB_WB; Src
0x18015d61a  mov     rcx, rsi; void *
0x18015d61d  call    memcpy_0
0x18015d622  lea     rcx, [rbp+210h+psz]; psz
0x18015d629  mov     [rdi+rsi], r12w
0x18015d62e  call    cs:__imp_SysAllocString
0x18015d634  test    rax, rax
0x18015d637  mov     esi, 8007000Eh
0x18015d63c  mov     rdi, rax
0x18015d63f  cmovz   ebx, esi
0x18015d642  test    ebx, ebx
0x18015d644  js      short loc_18015D680
0x18015d646  mov     rcx, [r15]
0x18015d64a  lea     rdx, aHttpSchemasOpe_1; "http://schemas.openxmlformats.org/offic"...
0x18015d651  test    r13d, r13d
0x18015d654  mov     r9, rdi
0x18015d657  mov     rax, [rcx+38h]
0x18015d65b  lea     rcx, aHttpPurlOclcOr_0; "http://purl.oclc.org/ooxml/officeDocume"...
0x18015d662  cmovz   rcx, rdx
0x18015d666  xor     r8d, r8d
0x18015d669  mov     [rsp+310h+var_2E8], rcx
0x18015d66e  xor     edx, edx
0x18015d670  mov     rcx, r15
0x18015d673  mov     [rsp+310h+var_2F0], r12
0x18015d678  call    cs:__guard_dispatch_icall_fptr
0x18015d67e  mov     ebx, eax
0x18015d680  mov     rcx, rdi; bstrString
0x18015d683  call    cs:__imp_SysFreeString
0x18015d689  mov     rdi, r12
0x18015d68c  test    ebx, ebx
0x18015d68e  js      loc_18015D72F
0x18015d694  mov     eax, cs:?c_wzOfficeRelsShort@Namespaces@Xsd@Mso@@3QB_WB; wchar_t const near * const Mso::Xsd::Namespaces::c_wzOfficeRelsShort
0x18015d69a  mov     edx, 13h
0x18015d69f  cmp     r14d, edx
0x18015d6a2  mov     [rbp+210h+psz], ax
0x18015d6a9  mov     eax, edx
0x18015d6ab  cmovbe  eax, r14d
0x18015d6af  mov     ecx, eax
0x18015d6b1  add     rax, rax
0x18015d6b4  cmp     rax, 26h ; '&'
0x18015d6b8  cmovbe  edx, ecx
0x18015d6bb  lea     rdi, [rdx+rdx]
0x18015d6bf  test    rdi, rdi
0x18015d6c2  jz      short loc_18015D6E2
0x18015d6c4  cmp     rdi, 26h ; '&'
0x18015d6c8  ja      loc_180390BFE
0x18015d6ce  mov     r8, rdi; Size
0x18015d6d1  lea     rdx, [rsp+310h+var_2D0]; Src
0x18015d6d6  lea     rcx, [rbp+210h+var_6E]; void *
0x18015d6dd  call    memcpy_0
0x18015d6e2  lea     rcx, [rbp+210h+psz]; psz
0x18015d6ea  mov     [rbp+rdi+210h+var_6E], r12w
0x18015d6f3  call    cs:__imp_SysAllocString
0x18015d6f9  test    rax, rax
0x18015d6fc  mov     rdi, rax
0x18015d6ff  cmovz   ebx, esi
0x18015d702  test    ebx, ebx
0x18015d704  js      short loc_18015D72F
0x18015d706  mov     rcx, [r15]
0x18015d709  mov     r9, rdi
0x18015d70c  xor     r8d, r8d
0x18015d70f  xor     edx, edx
0x18015d711  mov     rax, [rcx+38h]
0x18015d715  mov     rcx, [rsp+310h+var_2B8]
0x18015d71a  mov     [rsp+310h+var_2E8], rcx
0x18015d71f  mov     rcx, r15
0x18015d722  mov     [rsp+310h+var_2F0], r12
0x18015d727  call    cs:__guard_dispatch_icall_fptr
0x18015d72d  mov     ebx, eax
0x18015d72f  mov     rcx, rdi; bstrString
0x18015d732  call    cs:__imp_SysFreeString
0x18015d738  test    ebx, ebx
0x18015d73a  js      short loc_18015D774
0x18015d73c  mov     rdx, [rsp+310h+var_2B0]
0x18015d741  lea     r9, [rbp+210h+var_48]
0x18015d748  lea     r8, ?c_wzChartE2oShort@Namespaces@Xsd@Mso@@3QB_WB; wchar_t const near * const Mso::Xsd::Namespaces::c_wzChartE2oShort
0x18015d74f  lea     rcx, [rsp+310h+var_2A0]
0x18015d754  call    cs:__imp_??0CWriterEmit@Ofc@@QEAA@AEAUISAXContentHandler@@PEB_W1@Z; Ofc::CWriterEmit::CWriterEmit(ISAXContentHandler &,wchar_t const *,wchar_t const *)
0x18015d75a  mov     rdx, r15
0x18015d75d  lea     rcx, [rsp+310h+var_2A0]
0x18015d762  call    cs:__imp_?EmitStartElement@CWriterEmit@Ofc@@UEAAXAEAUIMXAttributes@@@Z; Ofc::CWriterEmit::EmitStartElement(IMXAttributes &)
0x18015d768  lea     rcx, [rsp+70h]
0x18015d76e  call    cs:__imp_?EmitEndElement@CWriterEmit@Ofc@@QEAAXXZ; Ofc::CWriterEmit::EmitEndElement(void)
0x18015d774  mov     eax, ebx
0x18015d776  mov     rcx, [rbp+210h+var_38]
0x18015d77d  xor     rcx, rsp; StackCookie
0x18015d780  call    __security_check_cookie
0x18015d785  mov     rbx, [rsp+310h+arg_0]
0x18015d78d  add     rsp, 2E0h
0x18015d794  pop     r15
0x18015d796  pop     r14
0x18015d798  pop     r13
0x18015d79a  pop     r12
0x18015d79c  pop     rdi
0x18015d79d  pop     rsi
0x18015d79e  pop     rbp
0x18015d79f  retn
0x180390b90  call    cs:__imp__errno
0x180390b96  mov     dword ptr [rax], 22h ; '"'
0x180390b9c  call    cs:__imp__invalid_parameter_noinfo
0x180390ba2  jmp     loc_18015D4E8
0x180390ba7  call    cs:__imp__errno
0x180390bad  mov     dword ptr [rax], 16h
0x180390bb3  jmp     short loc_180390BC1
0x180390bb5  call    cs:__imp__errno
0x180390bbb  mov     dword ptr [rax], 22h ; '"'
0x180390bc1  call    cs:__imp__invalid_parameter_noinfo
0x180390bc7  jmp     loc_18015D54C
0x180390bcc  call    cs:__imp__errno
0x180390bd2  mov     dword ptr [rax], 16h
0x180390bd8  jmp     short loc_180390BE6
0x180390bda  call    cs:__imp__errno
0x180390be0  mov     dword ptr [rax], 22h ; '"'
0x180390be6  call    cs:__imp__invalid_parameter_noinfo
0x180390bec  jmp     loc_18015D622
0x180390bf1  xor     r12d, r12d
0x180390bf4  mov     esi, 8007000Eh
0x180390bf9  jmp     loc_18015D680
0x180390bfe  call    cs:__imp__errno
0x180390c04  mov     dword ptr [rax], 22h ; '"'
0x180390c0a  call    cs:__imp__invalid_parameter_noinfo
0x180390c10  jmp     loc_18015D6E2
```
