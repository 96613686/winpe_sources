# ChartE2o::HrWriteDrawingChartTag(Ofc::IWriterParams &,wchar_t *,int)

- ea: `0x1802bb510`
- end: `0x1802bb8c0`
- name: `?HrWriteDrawingChartTag@ChartE2o@@AEBAJAEAVIWriterParams@Ofc@@PEA_WH@Z`
- size: `944`
- prototype: `__int64 __fastcall(ChartE2o *__hidden this, struct Ofc::IWriterParams *, wchar_t *, int)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1802ba0c0`

## callees

- `0x18010b944`
- `0x180120000`
- `0x1801296e0`
- `0x1801adb70`
- `0x1802bb510`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x1802bb67b`
- `OLEAUT32!__imp_SysAllocString` at `0x1802bb74e`
- `OLEAUT32!__imp_SysAllocString` at `0x1802bb813`
- `OLEAUT32!__imp_SysAllocString` at `0x1802bb67b`
- `OLEAUT32!__imp_SysAllocString` at `0x1802bb74e`
- `OLEAUT32!__imp_SysAllocString` at `0x1802bb813`
- `OLEAUT32!__imp_SysFreeString` at `0x1802bb6cb`
- `OLEAUT32!__imp_SysFreeString` at `0x1802bb7a3`
- `OLEAUT32!__imp_SysFreeString` at `0x1802bb852`
- `OLEAUT32!__imp_SysFreeString` at `0x1802bb6cb`
- `OLEAUT32!__imp_SysFreeString` at `0x1802bb7a3`
- `OLEAUT32!__imp_SysFreeString` at `0x1802bb852`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x1803252e4`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x1803252fb`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x180325309`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x180325320`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x18032532e`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x18032535d`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x1803252e4`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x1803252fb`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x180325309`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x180325320`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x18032532e`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x18032535d`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x1803252f0`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x180325315`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x18032533a`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x180325369`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x1803252f0`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x180325315`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x18032533a`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x180325369`
- `mso40uiWin32Client!__imp_?EmitStartElement@CWriterEmit@Ofc@@UEAAXAEAUIMXAttributes@@@Z` at `0x1802bb882`
- `mso40uiWin32Client!__imp_?EmitStartElement@CWriterEmit@Ofc@@UEAAXAEAUIMXAttributes@@@Z` at `0x1802bb882`
- `mso40uiWin32Client!__imp_??0CWriterEmit@Ofc@@QEAA@AEAUISAXContentHandler@@PEB_W1@Z` at `0x1802bb874`
- `mso40uiWin32Client!__imp_??0CWriterEmit@Ofc@@QEAA@AEAUISAXContentHandler@@PEB_W1@Z` at `0x1802bb874`
- `mso40uiWin32Client!__imp_?EmitEndElement@CWriterEmit@Ofc@@QEAAXXZ` at `0x1802bb88e`
- `mso40uiWin32Client!__imp_?EmitEndElement@CWriterEmit@Ofc@@QEAAXXZ` at `0x1802bb88e`

## string_xrefs

- `0x1802bb586`: `xmlns:`
- `0x1802bb69f`: `http://purl.oclc.org/ooxml/drawingml/chart`
- `0x1802bb695`: `http://schemas.openxmlformats.org/drawingml/2006/chart`
- `0x1802bb77b`: `http://purl.oclc.org/ooxml/officeDocument/relationships`
- `0x1802bb76a`: `http://schemas.openxmlformats.org/officeDocument/2006/relationships`

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
0x1802bb510  mov     [rsp-8+arg_0], rbx
0x1802bb515  push    rbp
0x1802bb516  push    rsi
0x1802bb517  push    rdi
0x1802bb518  push    r12
0x1802bb51a  push    r13
0x1802bb51c  push    r14
0x1802bb51e  push    r15
0x1802bb520  lea     rbp, [rsp-1E0h]
0x1802bb528  sub     rsp, 2E0h
0x1802bb52f  mov     rax, cs:__security_cookie
0x1802bb536  xor     rax, rsp
0x1802bb539  mov     [rbp+210h+var_38], rax
0x1802bb540  mov     eax, dword ptr cs:aChart_0+8; "t"
0x1802bb546  or      r14, 0FFFFFFFFFFFFFFFFh
0x1802bb54a  movsd   xmm0, qword ptr cs:aChart_0; "chart"
0x1802bb552  mov     r13d, r9d
0x1802bb555  mov     [rbp+210h+var_40], eax
0x1802bb55b  mov     rsi, r14
0x1802bb55e  mov     eax, dword ptr cs:aXmlns+8; "s:"
0x1802bb564  mov     [rsp+310h+var_2C0], eax
0x1802bb568  movzx   eax, word ptr cs:aXmlns+0Ch; ""
0x1802bb56f  mov     [rsp+310h+var_2BC], ax
0x1802bb574  mov     rax, 640069003Ah
0x1802bb57e  movsd   [rbp+210h+var_48], xmm0
0x1802bb586  movsd   xmm0, qword ptr cs:aXmlns; "xmlns:"
0x1802bb58e  mov     [rsp+310h+var_2D0], rax
0x1802bb593  lea     rax, [rsp+310h+Src]
0x1802bb598  mov     [rsp+310h+var_2B8], r8
0x1802bb59d  xor     r8d, r8d
0x1802bb5a0  movsd   [rsp+310h+Src], xmm0
0x1802bb5a6  inc     rsi
0x1802bb5a9  cmp     [rax+rsi*2], r8w
0x1802bb5ae  jnz     short loc_1802BB5A6
0x1802bb5b0  lea     rax, [rsp+310h+var_2D0]
0x1802bb5b5  inc     r14
0x1802bb5b8  cmp     [rax+r14*2], r8w
0x1802bb5bd  jnz     short loc_1802BB5B5
0x1802bb5bf  mov     rax, [rdx+8]
0x1802bb5c4  mov     ecx, 14h
0x1802bb5c9  mov     r15, [rdx+10h]
0x1802bb5cd  cmp     esi, ecx
0x1802bb5cf  mov     ebx, esi
0x1802bb5d1  mov     [rsp+310h+var_2B0], rax
0x1802bb5d6  cmova   ebx, ecx
0x1802bb5d9  add     rbx, rbx
0x1802bb5dc  lea     eax, [rcx+14h]
0x1802bb5df  cmp     rbx, rax
0x1802bb5e2  cmova   rbx, rax
0x1802bb5e6  test    rbx, rbx
0x1802bb5e9  jz      short loc_1802BB608
0x1802bb5eb  cmp     rbx, rax
0x1802bb5ee  ja      loc_1803252E4
0x1802bb5f4  mov     r8, rbx; Size
0x1802bb5f7  lea     rdx, [rsp+310h+Src]; Src
0x1802bb5fc  lea     rcx, [rbp+210h+psz]; void *
0x1802bb603  call    memcpy_0
0x1802bb608  lea     rcx, [rbp+210h+psz]
0x1802bb60f  mov     r12d, 1
0x1802bb615  add     rbx, rcx
0x1802bb618  mov     eax, r12d
0x1802bb61b  lea     rcx, [rbp+210h+var_48]
0x1802bb622  sub     rcx, rbx
0x1802bb625  sar     rcx, 1
0x1802bb628  cmp     ecx, r12d
0x1802bb62b  mov     edx, ecx
0x1802bb62d  cmovb   eax, ecx
0x1802bb630  mov     ecx, eax
0x1802bb632  add     rax, rax
0x1802bb635  lea     r8, [rdx+rdx]
0x1802bb639  cmp     rax, r8
0x1802bb63c  cmovbe  edx, ecx
0x1802bb63f  lea     rdi, [rdx+rdx]
0x1802bb643  test    rdi, rdi
0x1802bb646  jz      short loc_1802BB66C
0x1802bb648  test    rbx, rbx
0x1802bb64b  jz      loc_1803252FB
0x1802bb651  cmp     r8, rdi
0x1802bb654  jb      loc_180325309
0x1802bb65a  mov     r8, rdi; Size
0x1802bb65d  lea     rdx, ?c_wzChartE2oShort@Namespaces@Xsd@Mso@@3QB_WB; Src
0x1802bb664  mov     rcx, rbx; void *
0x1802bb667  call    memmove_0
0x1802bb66c  xor     r8d, r8d
0x1802bb66f  lea     rcx, [rbp+210h+psz]; psz
0x1802bb676  mov     [rdi+rbx], r8w
0x1802bb67b  call    cs:__imp_SysAllocString
0x1802bb681  mov     rdi, rax
0x1802bb684  xor     r8d, r8d
0x1802bb687  mov     eax, 8007000Eh
0x1802bb68c  test    rdi, rdi
0x1802bb68f  jz      short loc_1802BB6C6
0x1802bb691  mov     rax, [r15]
0x1802bb695  lea     rdx, aHttpSchemasOpe_0; "http://schemas.openxmlformats.org/drawi"...
0x1802bb69c  test    r13d, r13d
0x1802bb69f  lea     rcx, aHttpPurlOclcOr; "http://purl.oclc.org/ooxml/drawingml/ch"...
0x1802bb6a6  mov     r9, rdi
0x1802bb6a9  cmovz   rcx, rdx
0x1802bb6ad  xor     edx, edx
0x1802bb6af  mov     rax, [rax+38h]
0x1802bb6b3  mov     [rsp+310h+var_2E8], rcx
0x1802bb6b8  mov     rcx, r15
0x1802bb6bb  mov     [rsp+310h+var_2F0], r8
0x1802bb6c0  call    cs:__guard_dispatch_icall_fptr
0x1802bb6c6  mov     rcx, rdi; bstrString
0x1802bb6c9  mov     ebx, eax
0x1802bb6cb  call    cs:__imp_SysFreeString
0x1802bb6d1  xor     eax, eax
0x1802bb6d3  mov     edi, eax
0x1802bb6d5  test    ebx, ebx
0x1802bb6d7  js      loc_180325350
0x1802bb6dd  movsxd  rcx, esi
0x1802bb6e0  lea     rsi, [rbp+210h+psz]
0x1802bb6e7  lea     rsi, [rsi+rcx*2]
0x1802bb6eb  lea     rcx, [rbp+210h+var_48]
0x1802bb6f2  sub     rcx, rsi
0x1802bb6f5  sar     rcx, 1
0x1802bb6f8  cmp     ecx, r12d
0x1802bb6fb  mov     edx, ecx
0x1802bb6fd  cmovb   r12d, ecx
0x1802bb701  mov     ecx, r12d
0x1802bb704  lea     r8, [rdx+rdx]
0x1802bb708  lea     rax, [r12+r12]
0x1802bb70c  cmp     rax, r8
0x1802bb70f  cmovbe  edx, ecx
0x1802bb712  xor     r12d, r12d
0x1802bb715  lea     rdi, [rdx+rdx]
0x1802bb719  test    rdi, rdi
0x1802bb71c  jz      short loc_1802BB742
0x1802bb71e  test    rsi, rsi
0x1802bb721  jz      loc_180325320
0x1802bb727  cmp     r8, rdi
0x1802bb72a  jb      loc_18032532E
0x1802bb730  mov     r8, rdi; Size
0x1802bb733  lea     rdx, ?c_wzOfficeRelsShort@Namespaces@Xsd@Mso@@3QB_WB; Src
0x1802bb73a  mov     rcx, rsi; void *
0x1802bb73d  call    memcpy_0
0x1802bb742  lea     rcx, [rbp+210h+psz]; psz
0x1802bb749  mov     [rdi+rsi], r12w
0x1802bb74e  call    cs:__imp_SysAllocString
0x1802bb754  test    rax, rax
0x1802bb757  mov     esi, 8007000Eh
0x1802bb75c  mov     rdi, rax
0x1802bb75f  cmovz   ebx, esi
0x1802bb762  test    ebx, ebx
0x1802bb764  js      short loc_1802BB7A0
0x1802bb766  mov     rcx, [r15]
0x1802bb76a  lea     rdx, aHttpSchemasOpe_1; "http://schemas.openxmlformats.org/offic"...
0x1802bb771  test    r13d, r13d
0x1802bb774  mov     r9, rdi
0x1802bb777  mov     rax, [rcx+38h]
0x1802bb77b  lea     rcx, aHttpPurlOclcOr_0; "http://purl.oclc.org/ooxml/officeDocume"...
0x1802bb782  cmovz   rcx, rdx
0x1802bb786  xor     r8d, r8d
0x1802bb789  mov     [rsp+310h+var_2E8], rcx
0x1802bb78e  xor     edx, edx
0x1802bb790  mov     rcx, r15
0x1802bb793  mov     [rsp+310h+var_2F0], r12
0x1802bb798  call    cs:__guard_dispatch_icall_fptr
0x1802bb79e  mov     ebx, eax
0x1802bb7a0  mov     rcx, rdi; bstrString
0x1802bb7a3  call    cs:__imp_SysFreeString
0x1802bb7a9  mov     rdi, r12
0x1802bb7ac  test    ebx, ebx
0x1802bb7ae  js      loc_1802BB84F
0x1802bb7b4  mov     eax, cs:?c_wzOfficeRelsShort@Namespaces@Xsd@Mso@@3QB_WB; wchar_t const near * const Mso::Xsd::Namespaces::c_wzOfficeRelsShort
0x1802bb7ba  mov     edx, 13h
0x1802bb7bf  cmp     r14d, edx
0x1802bb7c2  mov     [rbp+210h+psz], ax
0x1802bb7c9  mov     eax, edx
0x1802bb7cb  cmovbe  eax, r14d
0x1802bb7cf  mov     ecx, eax
0x1802bb7d1  add     rax, rax
0x1802bb7d4  cmp     rax, 26h ; '&'
0x1802bb7d8  cmovbe  edx, ecx
0x1802bb7db  lea     rdi, [rdx+rdx]
0x1802bb7df  test    rdi, rdi
0x1802bb7e2  jz      short loc_1802BB802
0x1802bb7e4  cmp     rdi, 26h ; '&'
0x1802bb7e8  ja      loc_18032535D
0x1802bb7ee  mov     r8, rdi; Size
0x1802bb7f1  lea     rdx, [rsp+310h+var_2D0]; Src
0x1802bb7f6  lea     rcx, [rbp+210h+var_6E]; void *
0x1802bb7fd  call    memcpy_0
0x1802bb802  lea     rcx, [rbp+210h+psz]; psz
0x1802bb80a  mov     [rbp+rdi+210h+var_6E], r12w
0x1802bb813  call    cs:__imp_SysAllocString
0x1802bb819  test    rax, rax
0x1802bb81c  mov     rdi, rax
0x1802bb81f  cmovz   ebx, esi
0x1802bb822  test    ebx, ebx
0x1802bb824  js      short loc_1802BB84F
0x1802bb826  mov     rcx, [r15]
0x1802bb829  mov     r9, rdi
0x1802bb82c  xor     r8d, r8d
0x1802bb82f  xor     edx, edx
0x1802bb831  mov     rax, [rcx+38h]
0x1802bb835  mov     rcx, [rsp+310h+var_2B8]
0x1802bb83a  mov     [rsp+310h+var_2E8], rcx
0x1802bb83f  mov     rcx, r15
0x1802bb842  mov     [rsp+310h+var_2F0], r12
0x1802bb847  call    cs:__guard_dispatch_icall_fptr
0x1802bb84d  mov     ebx, eax
0x1802bb84f  mov     rcx, rdi; bstrString
0x1802bb852  call    cs:__imp_SysFreeString
0x1802bb858  test    ebx, ebx
0x1802bb85a  js      short loc_1802BB894
0x1802bb85c  mov     rdx, [rsp+310h+var_2B0]
0x1802bb861  lea     r9, [rbp+210h+var_48]
0x1802bb868  lea     r8, ?c_wzChartE2oShort@Namespaces@Xsd@Mso@@3QB_WB; wchar_t const near * const Mso::Xsd::Namespaces::c_wzChartE2oShort
0x1802bb86f  lea     rcx, [rsp+310h+var_2A0]
0x1802bb874  call    cs:__imp_??0CWriterEmit@Ofc@@QEAA@AEAUISAXContentHandler@@PEB_W1@Z; Ofc::CWriterEmit::CWriterEmit(ISAXContentHandler &,wchar_t const *,wchar_t const *)
0x1802bb87a  mov     rdx, r15
0x1802bb87d  lea     rcx, [rsp+310h+var_2A0]
0x1802bb882  call    cs:__imp_?EmitStartElement@CWriterEmit@Ofc@@UEAAXAEAUIMXAttributes@@@Z; Ofc::CWriterEmit::EmitStartElement(IMXAttributes &)
0x1802bb888  lea     rcx, [rsp+70h]
0x1802bb88e  call    cs:__imp_?EmitEndElement@CWriterEmit@Ofc@@QEAAXXZ; Ofc::CWriterEmit::EmitEndElement(void)
0x1802bb894  mov     eax, ebx
0x1802bb896  mov     rcx, [rbp+210h+var_38]
0x1802bb89d  xor     rcx, rsp; StackCookie
0x1802bb8a0  call    __security_check_cookie
0x1802bb8a5  mov     rbx, [rsp+310h+arg_0]
0x1802bb8ad  add     rsp, 2E0h
0x1802bb8b4  pop     r15
0x1802bb8b6  pop     r14
0x1802bb8b8  pop     r13
0x1802bb8ba  pop     r12
0x1802bb8bc  pop     rdi
0x1802bb8bd  pop     rsi
0x1802bb8be  pop     rbp
0x1802bb8bf  retn
0x1803252e4  call    cs:__imp__errno
0x1803252ea  mov     dword ptr [rax], 22h ; '"'
0x1803252f0  call    cs:__imp__invalid_parameter_noinfo
0x1803252f6  jmp     loc_1802BB608
0x1803252fb  call    cs:__imp__errno
0x180325301  mov     dword ptr [rax], 16h
0x180325307  jmp     short loc_180325315
0x180325309  call    cs:__imp__errno
0x18032530f  mov     dword ptr [rax], 22h ; '"'
0x180325315  call    cs:__imp__invalid_parameter_noinfo
0x18032531b  jmp     loc_1802BB66C
0x180325320  call    cs:__imp__errno
0x180325326  mov     dword ptr [rax], 16h
0x18032532c  jmp     short loc_18032533A
0x18032532e  call    cs:__imp__errno
0x180325334  mov     dword ptr [rax], 22h ; '"'
0x18032533a  call    cs:__imp__invalid_parameter_noinfo
0x180325340  jmp     loc_1802BB742
0x180325350  xor     r12d, r12d
0x180325353  mov     esi, 8007000Eh
0x180325358  jmp     loc_1802BB7A0
0x18032535d  call    cs:__imp__errno
0x180325363  mov     dword ptr [rax], 22h ; '"'
0x180325369  call    cs:__imp__invalid_parameter_noinfo
0x18032536f  jmp     loc_1802BB802
```
