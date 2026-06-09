# ValidateTessellationSignature(CSignatureParser const *,CSignatureParser const *,CSignatureParser const *,CSignatureParser const *,void *,void (*)(void *,D3D12_MESSAGE_ID,char const *),char const *)

- ea: `0x1801793d0`
- end: `0x180179d03`
- name: `?ValidateTessellationSignature@@YAIPEBVCSignatureParser@@000PEAXP6AX1W4D3D12_MESSAGE_ID@@PEBD@Z3@Z`
- size: `2355`
- prototype: `unsigned int __fastcall(const struct CSignatureParser *, const struct CSignatureParser *, const struct CSignatureParser *, const struct CSignatureParser *, void *, void (*)(void *, enum D3D12_MESSAGE_ID, const char *), const char *)`
- caller_count: `2`
- callee_count: `8`
- tags: `reparse_path, installer_update, broker_com_uri`

## callers

- `0x18015055c`
- `0x18016d260`

## callees

- `0x18009fd4c`
- `0x1800bb480`
- `0x1800cc130`
- `0x1800e85b0`
- `0x1800eb674`
- `0x180102704`
- `0x1801793d0`
- `0x180262020`

## import_xrefs

- `msvcp_win!??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@I@Z` at `0x180179592`
- `msvcp_win!??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@I@Z` at `0x18017969e`
- `msvcp_win!??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@I@Z` at `0x1801796d7`
- `msvcp_win!??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@I@Z` at `0x180179700`
- `msvcp_win!??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@I@Z` at `0x180179592`
- `msvcp_win!??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@I@Z` at `0x18017969e`
- `msvcp_win!??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@I@Z` at `0x1801796d7`
- `msvcp_win!??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@I@Z` at `0x180179700`
- `api-ms-win-crt-private-l1-1-0!_o__stricmp` at `0x180179525`
- `api-ms-win-crt-private-l1-1-0!_o__stricmp` at `0x180179525`

## string_xrefs

- `0x1801797b9`: ` between stages are incompatible. `
- `0x180179894`: ` between stages are incompatible. `
- `0x18017996f`: ` between stages are incompatible. `
- `0x180179a4a`: ` between stages are incompatible. `
- `0x180179b2e`: ` between stages are incompatible. `
- `0x180179c18`: ` between stages are incompatible. `
- `0x18017999a`: `' in each signature have different component masks, when they must be identical. This is a stricter requirement than the linkage between other shader stages.`
- `0x180179552`: `Hull Shader to Domain Shader linkage error: Signatures for `
- `0x18017965e`: `Hull Shader to Domain Shader linkage error: Signatures for `
- `0x18017978c`: `Hull Shader to Domain Shader linkage error: Signatures for `
- `0x180179867`: `Hull Shader to Domain Shader linkage error: Signatures for `
- `0x180179942`: `Hull Shader to Domain Shader linkage error: Signatures for `
- `0x180179a1d`: `Hull Shader to Domain Shader linkage error: Signatures for `
- `0x180179b01`: `Hull Shader to Domain Shader linkage error: Signatures for `
- `0x180179beb`: `Hull Shader to Domain Shader linkage error: Signatures for `
- `0x18017946a`: `Hull Shader to Domain Shader linkage error: Signatures `
- `0x18017949f`: `The signatures for both Patch Constant Data and Control Points between Hull Shader and Domain Shader must match exactly. This is a stricter requirement than the linkage between other shader stages.`
- `0x180179b59`: `' is always read by the Domain Shader, `

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall ValidateTessellationSignature(
        const struct CSignatureParser *a1,
        const struct CSignatureParser *a2,
        const struct CSignatureParser *a3,
        const struct CSignatureParser *a4,
        void *a5,
        void (*a6)(void *, enum D3D12_MESSAGE_ID, const char *))
{
  const struct CSignatureParser *v6; // rax
  unsigned int v7; // edi
  unsigned int i; // r15d
  const struct CSignatureParser *v9; // rsi
  const struct CSignatureParser *v10; // r12
  unsigned int v11; // eax
  __int64 v12; // rax
  __int64 v13; // rax
  const char *v14; // rdx
  __int64 v15; // rax
  __int64 v16; // rax
  _QWORD *v17; // r8
  __int64 v18; // rsi
  __int64 v19; // r12
  __int64 v20; // rax
  __int64 v21; // rbx
  __int64 v22; // rax
  __int64 v23; // rax
  const char *v24; // rdx
  __int64 v25; // rax
  __int64 v26; // rax
  __int64 v27; // rax
  __int64 v28; // rax
  __int64 v29; // rax
  __int64 v30; // rax
  __int64 v31; // rax
  __int64 v32; // rax
  _QWORD *v33; // r8
  __int64 v34; // rax
  __int64 v35; // rax
  const char *v36; // rdx
  __int64 v37; // rax
  __int64 v38; // rax
  __int64 v39; // rax
  __int64 v40; // rax
  __int64 v41; // rax
  __int64 v42; // rax
  __int64 v43; // rax
  __int64 v44; // rax
  __int64 v45; // rax
  __int64 v46; // rax
  _QWORD *v47; // r8
  __int64 v48; // rax
  __int64 v49; // rax
  const char *v50; // rdx
  __int64 v51; // rax
  __int64 v52; // rax
  __int64 v53; // rax
  __int64 v54; // rax
  _QWORD *v55; // r8
  __int64 v56; // rax
  __int64 v57; // rax
  const char *v58; // rdx
  __int64 v59; // rax
  __int64 v60; // rax
  __int64 v61; // rax
  __int64 v62; // rax
  _QWORD *v63; // r8
  __int64 v64; // rax
  __int64 v65; // rax
  const char *v66; // rdx
  __int64 v67; // rax
  __int64 v68; // rax
  __int64 v69; // rax
  __int64 v70; // rax
  _QWORD *v71; // r8
  __int64 v72; // rax
  __int64 v73; // rax
  const char *v74; // rdx
  __int64 v75; // rax
  __int64 v76; // rax
  __int64 v77; // rax
  __int64 v78; // rax
  _QWORD *v79; // r8
  __int64 v80; // rax
  __int64 v81; // rax
  const char *v82; // rdx
  __int64 v83; // rax
  __int64 v84; // rax
  __int64 v85; // rax
  __int64 v86; // rax
  __int64 v87; // rax
  _QWORD *v88; // r8
  __int64 v89; // rax
  __int64 v90; // rax
  const char *v91; // rdx
  __int64 v92; // rax
  __int64 v93; // rax
  __int64 v94; // rax
  __int64 v95; // rax
  _QWORD *v96; // r8
  unsigned int v98; // [rsp+20h] [rbp-E0h]
  unsigned int v99; // [rsp+24h] [rbp-DCh]
  __int64 v100; // [rsp+28h] [rbp-D8h]
  const struct CSignatureParser *v101; // [rsp+30h] [rbp-D0h]
  const struct CSignatureParser *v102; // [rsp+38h] [rbp-C8h]
  const struct CSignatureParser *v103; // [rsp+40h] [rbp-C0h]
  _BYTE v105[8]; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v106[232]; // [rsp+58h] [rbp-A8h] BYREF
  _QWORD v107[3]; // [rsp+140h] [rbp+40h] BYREF
  unsigned __int64 v108; // [rsp+158h] [rbp+58h]

  v6 = a4;
  v101 = a3;
  v102 = a2;
  v103 = a1;
  v7 = 0;
  for ( i = 0; i < 2; ++i )
  {
    v9 = a2;
    if ( i )
      v9 = v6;
    v10 = a1;
    if ( i )
      v10 = a3;
    v11 = *((_DWORD *)v9 + 4);
    v99 = v11;
    if ( v11 == *((_DWORD *)v10 + 4) )
    {
      v18 = *(_QWORD *)v9;
      v19 = *(_QWORD *)v10;
      v98 = 0;
      if ( !v11 )
        goto LABEL_82;
      v20 = 0;
      v100 = 0;
      while ( 1 )
      {
        v21 = 5 * v20;
        if ( (unsigned int)_o__stricmp(*(_QWORD *)(v18 + 40 * v20 + 8), *(_QWORD *)(v19 + 40 * v20 + 8)) )
          break;
        if ( *(_DWORD *)(v18 + 8 * v21 + 16) != *(_DWORD *)(v19 + 8 * v21 + 16) )
        {
          std::ostringstream::ostringstream(v105);
          v34 = std::operator<<<std::char_traits<char>>(v105, Src);
          v35 = std::operator<<<std::char_traits<char>>(
                  v34,
                  "Hull Shader to Domain Shader linkage error: Signatures for ");
          v36 = "Patch Constant Data";
          if ( i != 1 )
            v36 = "Control Points";
          v37 = std::operator<<<std::char_traits<char>>(v35, v36);
          v38 = std::operator<<<std::char_traits<char>>(v37, " entry [");
          v39 = std::ostream::operator<<(v38, v98);
          v40 = std::operator<<<std::char_traits<char>>(v39, "] have different semantic indices. ");
          v41 = std::operator<<<std::char_traits<char>>(v40, "The Hull Shader outputs '");
          v42 = std::operator<<<std::char_traits<char>>(v41, *(_QWORD *)(v19 + 8 * v21 + 8));
          v43 = std::ostream::operator<<(v42, *(unsigned int *)(v19 + 8 * v21 + 16));
          v44 = std::operator<<<std::char_traits<char>>(v43, "', while the Domain Shader inputs '");
          v45 = std::operator<<<std::char_traits<char>>(v44, *(_QWORD *)(v18 + 8 * v21 + 8));
          v46 = std::ostream::operator<<(v45, *(unsigned int *)(v18 + 8 * v21 + 16));
          std::operator<<<std::char_traits<char>>(v46, "'.");
          if ( a6 )
          {
            std::stringbuf::str(v106, v107);
            v47 = v107;
            if ( v108 > 0xF )
              v47 = (_QWORD *)v107[0];
            ((void (__fastcall *)(void *, __int64, _QWORD *))a6)(a5, 659, v47);
            std::string::_Tidy_deallocate(v107);
          }
          goto LABEL_31;
        }
LABEL_32:
        if ( *(_DWORD *)(v18 + 8 * v21 + 28) != *(_DWORD *)(v19 + 8 * v21 + 28) )
        {
          std::ostringstream::ostringstream(v105);
          v48 = std::operator<<<std::char_traits<char>>(v105, Src);
          v49 = std::operator<<<std::char_traits<char>>(
                  v48,
                  "Hull Shader to Domain Shader linkage error: Signatures for ");
          v50 = "Patch Constant Data";
          if ( i != 1 )
            v50 = "Control Points";
          v51 = std::operator<<<std::char_traits<char>>(v49, v50);
          v52 = std::operator<<<std::char_traits<char>>(v51, " between stages are incompatible. ");
          v53 = std::operator<<<std::char_traits<char>>(v52, "Semantic '");
          v54 = std::operator<<<std::char_traits<char>>(v53, *(_QWORD *)(v18 + 8 * v21 + 8));
          std::operator<<<std::char_traits<char>>(
            v54,
            "' is defined for mismatched hardware registers between the output stage and input stage.");
          if ( a6 )
          {
            std::stringbuf::str(v106, v107);
            v55 = v107;
            if ( v108 > 0xF )
              v55 = (_QWORD *)v107[0];
            ((void (__fastcall *)(void *, __int64, _QWORD *))a6)(a5, 660, v55);
            std::string::_Tidy_deallocate(v107);
          }
          std::ostringstream::`vbase destructor'(v105);
          ++v7;
        }
        if ( *(_DWORD *)(v18 + 8 * v21 + 24) != *(_DWORD *)(v19 + 8 * v21 + 24) )
        {
          std::ostringstream::ostringstream(v105);
          v56 = std::operator<<<std::char_traits<char>>(v105, Src);
          v57 = std::operator<<<std::char_traits<char>>(
                  v56,
                  "Hull Shader to Domain Shader linkage error: Signatures for ");
          v58 = "Patch Constant Data";
          if ( i != 1 )
            v58 = "Control Points";
          v59 = std::operator<<<std::char_traits<char>>(v57, v58);
          v60 = std::operator<<<std::char_traits<char>>(v59, " between stages are incompatible. ");
          v61 = std::operator<<<std::char_traits<char>>(v60, "Semantic '");
          v62 = std::operator<<<std::char_traits<char>>(v61, *(_QWORD *)(v18 + 8 * v21 + 8));
          std::operator<<<std::char_traits<char>>(
            v62,
            "' has mismatched data types between the output stage and input stage.");
          if ( a6 )
          {
            std::stringbuf::str(v106, v107);
            v63 = v107;
            if ( v108 > 0xF )
              v63 = (_QWORD *)v107[0];
            ((void (__fastcall *)(void *, __int64, _QWORD *))a6)(a5, 661, v63);
            std::string::_Tidy_deallocate(v107);
          }
          std::ostringstream::`vbase destructor'(v105);
          ++v7;
        }
        if ( *(_BYTE *)(v18 + 8 * v21 + 32) != *(_BYTE *)(v19 + 8 * v21 + 32) )
        {
          std::ostringstream::ostringstream(v105);
          v64 = std::operator<<<std::char_traits<char>>(v105, Src);
          v65 = std::operator<<<std::char_traits<char>>(
                  v64,
                  "Hull Shader to Domain Shader linkage error: Signatures for ");
          v66 = "Patch Constant Data";
          if ( i != 1 )
            v66 = "Control Points";
          v67 = std::operator<<<std::char_traits<char>>(v65, v66);
          v68 = std::operator<<<std::char_traits<char>>(v67, " between stages are incompatible. ");
          v69 = std::operator<<<std::char_traits<char>>(v68, "Semantic '");
          v70 = std::operator<<<std::char_traits<char>>(v69, *(_QWORD *)(v18 + 8 * v21 + 8));
          std::operator<<<std::char_traits<char>>(
            v70,
            "' in each signature have different component masks, when they must be identical. This is a stricter requirem"
            "ent than the linkage between other shader stages.");
          if ( a6 )
          {
            std::stringbuf::str(v106, v107);
            v71 = v107;
            if ( v108 > 0xF )
              v71 = (_QWORD *)v107[0];
            ((void (__fastcall *)(void *, __int64, _QWORD *))a6)(a5, 662, v71);
            std::string::_Tidy_deallocate(v107);
          }
          std::ostringstream::`vbase destructor'(v105);
          ++v7;
        }
        if ( *(_DWORD *)(v18 + 8 * v21 + 20) != *(_DWORD *)(v19 + 8 * v21 + 20) )
        {
          std::ostringstream::ostringstream(v105);
          v72 = std::operator<<<std::char_traits<char>>(v105, Src);
          v73 = std::operator<<<std::char_traits<char>>(
                  v72,
                  "Hull Shader to Domain Shader linkage error: Signatures for ");
          v74 = "Patch Constant Data";
          if ( i != 1 )
            v74 = "Control Points";
          v75 = std::operator<<<std::char_traits<char>>(v73, v74);
          v76 = std::operator<<<std::char_traits<char>>(v75, " between stages are incompatible. ");
          v77 = std::operator<<<std::char_traits<char>>(v76, "Semantic '");
          v78 = std::operator<<<std::char_traits<char>>(v77, *(_QWORD *)(v18 + 8 * v21 + 8));
          std::operator<<<std::char_traits<char>>(
            v78,
            "' has different System Value defined for the input vs output stages.");
          if ( a6 )
          {
            std::stringbuf::str(v106, v107);
            v79 = v107;
            if ( v108 > 0xF )
              v79 = (_QWORD *)v107[0];
            ((void (__fastcall *)(void *, __int64, _QWORD *))a6)(a5, 663, v79);
            std::string::_Tidy_deallocate(v107);
          }
          std::ostringstream::`vbase destructor'(v105);
          ++v7;
        }
        if ( ((unsigned __int8)(*(_BYTE *)(v18 + 8 * v21 + 32)
                              & *(_BYTE *)(v18 + 8 * v21 + 33)
                              & *(_BYTE *)(v19 + 8 * v21 + 33))
            & *(_BYTE *)(v19 + 8 * v21 + 32)) != 0 )
        {
          std::ostringstream::ostringstream(v105);
          v80 = std::operator<<<std::char_traits<char>>(v105, Src);
          v81 = std::operator<<<std::char_traits<char>>(
                  v80,
                  "Hull Shader to Domain Shader linkage error: Signatures for ");
          v82 = "Patch Constant Data";
          if ( i != 1 )
            v82 = "Control Points";
          v83 = std::operator<<<std::char_traits<char>>(v81, v82);
          v84 = std::operator<<<std::char_traits<char>>(v83, " between stages are incompatible. ");
          v85 = std::operator<<<std::char_traits<char>>(v84, "Semantic '");
          v86 = std::operator<<<std::char_traits<char>>(v85, *(_QWORD *)(v18 + 8 * v21 + 8));
          v87 = std::operator<<<std::char_traits<char>>(v86, "' is always read by the Domain Shader, ");
          std::operator<<<std::char_traits<char>>(
            v87,
            "but never written by the Hull Shader (even though the semantic is present in its output signature).");
          if ( a6 )
          {
            std::stringbuf::str(v106, v107);
            v88 = v107;
            if ( v108 > 0xF )
              v88 = (_QWORD *)v107[0];
            ((void (__fastcall *)(void *, __int64, _QWORD *))a6)(a5, 664, v88);
            std::string::_Tidy_deallocate(v107);
          }
          std::ostringstream::`vbase destructor'(v105);
          ++v7;
        }
        if ( *(_DWORD *)(v18 + 8 * v21 + 36) != *(_DWORD *)(v19 + 8 * v21 + 36) )
        {
          std::ostringstream::ostringstream(v105);
          v89 = std::operator<<<std::char_traits<char>>(v105, Src);
          v90 = std::operator<<<std::char_traits<char>>(
                  v89,
                  "Hull Shader to Domain Shader linkage error: Signatures for ");
          v91 = "Patch Constant Data";
          if ( i != 1 )
            v91 = "Control Points";
          v92 = std::operator<<<std::char_traits<char>>(v90, v91);
          v93 = std::operator<<<std::char_traits<char>>(v92, " between stages are incompatible. ");
          v94 = std::operator<<<std::char_traits<char>>(v93, "Semantic '");
          v95 = std::operator<<<std::char_traits<char>>(v94, *(_QWORD *)(v18 + 8 * v21 + 8));
          std::operator<<<std::char_traits<char>>(
            v95,
            "' in each signature have different min precision levels, when they must be identical. ");
          if ( a6 )
          {
            std::stringbuf::str(v106, v107);
            v96 = v107;
            if ( v108 > 0xF )
              v96 = (_QWORD *)v107[0];
            ((void (__fastcall *)(void *, __int64, _QWORD *))a6)(a5, 665, v96);
            std::string::_Tidy_deallocate(v107);
          }
          std::ostringstream::`vbase destructor'(v105);
          ++v7;
        }
        ++v98;
        v20 = ++v100;
        if ( v98 >= v99 )
          goto LABEL_81;
      }
      std::ostringstream::ostringstream(v105);
      v22 = std::operator<<<std::char_traits<char>>(v105, Src);
      v23 = std::operator<<<std::char_traits<char>>(v22, "Hull Shader to Domain Shader linkage error: Signatures for ");
      v24 = "Patch Constant Data";
      if ( i != 1 )
        v24 = "Control Points";
      v25 = std::operator<<<std::char_traits<char>>(v23, v24);
      v26 = std::operator<<<std::char_traits<char>>(v25, " entry [");
      v27 = std::ostream::operator<<(v26, v98);
      v28 = std::operator<<<std::char_traits<char>>(v27, "] have different names. ");
      v29 = std::operator<<<std::char_traits<char>>(v28, "The Hull Shader outputs '");
      v30 = std::operator<<<std::char_traits<char>>(v29, *(_QWORD *)(v19 + 8 * v21 + 8));
      v31 = std::operator<<<std::char_traits<char>>(v30, "', while the Domain Shader inputs '");
      v32 = std::operator<<<std::char_traits<char>>(v31, *(_QWORD *)(v18 + 8 * v21 + 8));
      std::operator<<<std::char_traits<char>>(v32, "'.");
      if ( a6 )
      {
        std::stringbuf::str(v106, v107);
        v33 = v107;
        if ( v108 > 0xF )
          v33 = (_QWORD *)v107[0];
        ((void (__fastcall *)(void *, __int64, _QWORD *))a6)(a5, 659, v33);
        std::string::_Tidy_deallocate(v107);
      }
LABEL_31:
      std::ostringstream::`vbase destructor'(v105);
      ++v7;
      goto LABEL_32;
    }
    std::ostringstream::ostringstream(v105);
    v12 = std::operator<<<std::char_traits<char>>(v105, Src);
    v13 = std::operator<<<std::char_traits<char>>(v12, "Hull Shader to Domain Shader linkage error: Signatures ");
    v14 = "Patch Constant Data";
    if ( i != 1 )
      v14 = "Control Points";
    v15 = std::operator<<<std::char_traits<char>>(v13, v14);
    v16 = std::operator<<<std::char_traits<char>>(v15, " between stages are different lengths. ");
    std::operator<<<std::char_traits<char>>(
      v16,
      "The signatures for both Patch Constant Data and Control Points between Hull Shader and Domain Shader must match ex"
      "actly. This is a stricter requirement than the linkage between other shader stages.");
    if ( a6 )
    {
      std::stringbuf::str(v106, v107);
      v17 = v107;
      if ( v108 > 0xF )
        v17 = (_QWORD *)v107[0];
      ((void (__fastcall *)(void *, __int64, _QWORD *))a6)(a5, 659, v17);
      std::string::_Tidy_deallocate(v107);
    }
    std::ostringstream::`vbase destructor'(v105);
    ++v7;
LABEL_81:
    a1 = v103;
    a2 = v102;
    a3 = v101;
LABEL_82:
    v6 = a4;
  }
  return v7;
}

```

## disassembly

```asm
0x1801793d0  push    rbp
0x1801793d2  push    rbx
0x1801793d3  push    rsi
0x1801793d4  push    rdi
0x1801793d5  push    r12
0x1801793d7  push    r13
0x1801793d9  push    r14
0x1801793db  push    r15
0x1801793dd  lea     rbp, [rsp-78h]
0x1801793e2  sub     rsp, 178h
0x1801793e9  mov     rax, cs:__security_cookie
0x1801793f0  xor     rax, rsp
0x1801793f3  mov     [rbp+0B0h+var_50], rax
0x1801793f7  mov     rax, r9
0x1801793fa  mov     [rsp+1B0h+var_168], rax
0x1801793ff  mov     [rsp+1B0h+var_180], r8
0x180179404  mov     [rsp+1B0h+var_178], rdx
0x180179409  mov     [rsp+1B0h+var_170], rcx
0x18017940e  mov     r13, [rbp+0B0h+arg_20]
0x180179415  mov     r14, [rbp+0B0h+arg_28]
0x18017941c  xor     edi, edi
0x18017941e  xor     r15d, r15d
0x180179421  lea     rbx, aControlPoints; "Control Points"
0x180179428  mov     rsi, rdx
0x18017942b  test    r15d, r15d
0x18017942e  cmovnz  rsi, rax
0x180179432  mov     r12, rcx
0x180179435  cmovnz  r12, r8
0x180179439  mov     eax, [rsi+10h]
0x18017943c  mov     [rsp+1B0h+var_18C], eax
0x180179440  cmp     eax, [r12+10h]
0x180179445  jz      loc_1801794F9
0x18017944b  lea     rcx, [rsp+1B0h+var_160]
0x180179450  call    ??0?$basic_ostringstream@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::ostringstream::ostringstream(void)
0x180179455  nop
0x180179456  lea     rdx, Src
0x18017945d  lea     rcx, [rsp+1B0h+var_160]
0x180179462  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x180179467  mov     rcx, rax
0x18017946a  lea     rdx, aHullShaderToDo; "Hull Shader to Domain Shader linkage er"...
0x180179471  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x180179476  lea     rdx, aPatchConstantD; "Patch Constant Data"
0x18017947d  cmp     r15d, 1
0x180179481  cmovnz  rdx, rbx
0x180179485  mov     rcx, rax
0x180179488  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18017948d  mov     rcx, rax
0x180179490  lea     rdx, aBetweenStagesA_0; " between stages are different lengths. "
0x180179497  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18017949c  mov     rcx, rax
0x18017949f  lea     rdx, aTheSignaturesF; "The signatures for both Patch Constant "...
0x1801794a6  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x1801794ab  test    r14, r14
0x1801794ae  jz      short loc_1801794E8
0x1801794b0  lea     rdx, [rbp+0B0h+var_70]
0x1801794b4  lea     rcx, [rsp+1B0h+var_158]
0x1801794b9  call    ?str@?$basic_stringbuf@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEBA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@XZ; std::stringbuf::str(void)
0x1801794be  nop
0x1801794bf  lea     r8, [rbp+0B0h+var_70]
0x1801794c3  cmp     [rbp+0B0h+var_58], 0Fh
0x1801794c8  cmova   r8, [rbp+0B0h+var_70]
0x1801794cd  mov     edx, 293h
0x1801794d2  mov     rcx, r13
0x1801794d5  mov     rax, r14
0x1801794d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801794dd  nop
0x1801794de  lea     rcx, [rbp+0B0h+var_70]
0x1801794e2  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1801794e7  nop
0x1801794e8  lea     rcx, [rsp+1B0h+var_160]
0x1801794ed  call    ??_D?$basic_ostringstream@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAXXZ; std::ostringstream::`vbase destructor'(void)
0x1801794f2  inc     edi
0x1801794f4  jmp     loc_180179CC0
0x1801794f9  mov     rsi, [rsi]
0x1801794fc  mov     r12, [r12]
0x180179500  mov     [rsp+1B0h+var_190], 0
0x180179508  test    eax, eax
0x18017950a  jz      loc_180179CCF
0x180179510  xor     eax, eax
0x180179512  mov     [rsp+1B0h+var_188], rax
0x180179517  lea     rbx, [rax+rax*4]
0x18017951b  mov     rdx, [r12+rbx*8+8]
0x180179520  mov     rcx, [rsi+rbx*8+8]
0x180179525  call    cs:__imp__o__stricmp
0x18017952b  test    eax, eax
0x18017952d  jz      loc_180179630
0x180179533  lea     rcx, [rsp+1B0h+var_160]
0x180179538  call    ??0?$basic_ostringstream@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::ostringstream::ostringstream(void)
0x18017953d  nop
0x18017953e  lea     rdx, Src
0x180179545  lea     rcx, [rsp+1B0h+var_160]
0x18017954a  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18017954f  mov     rcx, rax
0x180179552  lea     rdx, aHullShaderToDo_0; "Hull Shader to Domain Shader linkage er"...
0x180179559  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18017955e  lea     rdx, aPatchConstantD; "Patch Constant Data"
0x180179565  cmp     r15d, 1
0x180179569  lea     rcx, aControlPoints; "Control Points"
0x180179570  cmovnz  rdx, rcx
0x180179574  mov     rcx, rax
0x180179577  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18017957c  mov     rcx, rax
0x18017957f  lea     rdx, aEntry; " entry ["
0x180179586  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18017958b  mov     edx, [rsp+1B0h+var_190]
0x18017958f  mov     rcx, rax
0x180179592  call    cs:__imp_??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@I@Z; std::ostream::operator<<(uint)
0x180179598  mov     rcx, rax
0x18017959b  lea     rdx, aHaveDifferentN; "] have different names. "
0x1801795a2  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x1801795a7  mov     rcx, rax
0x1801795aa  lea     rdx, aTheHullShaderO; "The Hull Shader outputs '"
0x1801795b1  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x1801795b6  mov     rdx, [r12+rbx*8+8]
0x1801795bb  mov     rcx, rax
0x1801795be  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x1801795c3  mov     rcx, rax
0x1801795c6  lea     rdx, aWhileTheDomain; "', while the Domain Shader inputs '"
0x1801795cd  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x1801795d2  mov     rdx, [rsi+rbx*8+8]
0x1801795d7  mov     rcx, rax
0x1801795da  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x1801795df  mov     rcx, rax
0x1801795e2  lea     rdx, asc_1802D0998; "'."
0x1801795e9  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x1801795ee  test    r14, r14
0x1801795f1  jz      short loc_18017962B
0x1801795f3  lea     rdx, [rbp+0B0h+var_70]
0x1801795f7  lea     rcx, [rsp+1B0h+var_158]
0x1801795fc  call    ?str@?$basic_stringbuf@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEBA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@XZ; std::stringbuf::str(void)
0x180179601  nop
0x180179602  lea     r8, [rbp+0B0h+var_70]
0x180179606  cmp     [rbp+0B0h+var_58], 0Fh
0x18017960b  cmova   r8, [rbp+0B0h+var_70]
0x180179610  mov     edx, 293h
0x180179615  mov     rcx, r13
0x180179618  mov     rax, r14
0x18017961b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180179620  nop
0x180179621  lea     rcx, [rbp+0B0h+var_70]
0x180179625  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18017962a  nop
0x18017962b  jmp     loc_180179752
0x180179630  mov     eax, [r12+rbx*8+10h]
0x180179635  cmp     [rsi+rbx*8+10h], eax
0x180179639  jz      loc_18017975E
0x18017963f  lea     rcx, [rsp+1B0h+var_160]
0x180179644  call    ??0?$basic_ostringstream@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::ostringstream::ostringstream(void)
0x180179649  nop
0x18017964a  lea     rdx, Src
0x180179651  lea     rcx, [rsp+1B0h+var_160]
0x180179656  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18017965b  mov     rcx, rax
0x18017965e  lea     rdx, aHullShaderToDo_0; "Hull Shader to Domain Shader linkage er"...
0x180179665  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18017966a  lea     rdx, aPatchConstantD; "Patch Constant Data"
0x180179671  cmp     r15d, 1
0x180179675  lea     rcx, aControlPoints; "Control Points"
0x18017967c  cmovnz  rdx, rcx
0x180179680  mov     rcx, rax
0x180179683  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x180179688  mov     rcx, rax
0x18017968b  lea     rdx, aEntry; " entry ["
0x180179692  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x180179697  mov     edx, [rsp+1B0h+var_190]
0x18017969b  mov     rcx, rax
0x18017969e  call    cs:__imp_??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@I@Z; std::ostream::operator<<(uint)
0x1801796a4  mov     rcx, rax
0x1801796a7  lea     rdx, aHaveDifferentS; "] have different semantic indices. "
0x1801796ae  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x1801796b3  mov     rcx, rax
0x1801796b6  lea     rdx, aTheHullShaderO; "The Hull Shader outputs '"
0x1801796bd  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x1801796c2  mov     rdx, [r12+rbx*8+8]
0x1801796c7  mov     rcx, rax
0x1801796ca  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x1801796cf  mov     edx, [r12+rbx*8+10h]
0x1801796d4  mov     rcx, rax
0x1801796d7  call    cs:__imp_??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@I@Z; std::ostream::operator<<(uint)
0x1801796dd  mov     rcx, rax
0x1801796e0  lea     rdx, aWhileTheDomain; "', while the Domain Shader inputs '"
0x1801796e7  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x1801796ec  mov     rdx, [rsi+rbx*8+8]
0x1801796f1  mov     rcx, rax
0x1801796f4  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x1801796f9  mov     edx, [rsi+rbx*8+10h]
0x1801796fd  mov     rcx, rax
0x180179700  call    cs:__imp_??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@I@Z; std::ostream::operator<<(uint)
0x180179706  mov     rcx, rax
0x180179709  lea     rdx, asc_1802D0998; "'."
0x180179710  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x180179715  test    r14, r14
0x180179718  jz      short loc_180179752
0x18017971a  lea     rdx, [rbp+0B0h+var_70]
0x18017971e  lea     rcx, [rsp+1B0h+var_158]
0x180179723  call    ?str@?$basic_stringbuf@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEBA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@XZ; std::stringbuf::str(void)
0x180179728  nop
0x180179729  lea     r8, [rbp+0B0h+var_70]
0x18017972d  cmp     [rbp+0B0h+var_58], 0Fh
0x180179732  cmova   r8, [rbp+0B0h+var_70]
0x180179737  mov     edx, 293h
0x18017973c  mov     rcx, r13
0x18017973f  mov     rax, r14
0x180179742  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180179747  nop
0x180179748  lea     rcx, [rbp+0B0h+var_70]
0x18017974c  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180179751  nop
0x180179752  lea     rcx, [rsp+1B0h+var_160]
0x180179757  call    ??_D?$basic_ostringstream@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAXXZ; std::ostringstream::`vbase destructor'(void)
0x18017975c  inc     edi
0x18017975e  mov     eax, [r12+rbx*8+1Ch]
0x180179763  cmp     [rsi+rbx*8+1Ch], eax
0x180179767  jz      loc_180179839
0x18017976d  lea     rcx, [rsp+1B0h+var_160]
0x180179772  call    ??0?$basic_ostringstream@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::ostringstream::ostringstream(void)
0x180179777  nop
0x180179778  lea     rdx, Src
0x18017977f  lea     rcx, [rsp+1B0h+var_160]
0x180179784  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x180179789  mov     rcx, rax
0x18017978c  lea     rdx, aHullShaderToDo_0; "Hull Shader to Domain Shader linkage er"...
0x180179793  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x180179798  lea     rdx, aPatchConstantD; "Patch Constant Data"
0x18017979f  cmp     r15d, 1
0x1801797a3  lea     rcx, aControlPoints; "Control Points"
0x1801797aa  cmovnz  rdx, rcx
0x1801797ae  mov     rcx, rax
0x1801797b1  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x1801797b6  mov     rcx, rax
0x1801797b9  lea     rdx, aBetweenStagesA; " between stages are incompatible. "
0x1801797c0  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x1801797c5  mov     rcx, rax
0x1801797c8  lea     rdx, aSemantic; "Semantic '"
0x1801797cf  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x1801797d4  mov     rdx, [rsi+rbx*8+8]
0x1801797d9  mov     rcx, rax
0x1801797dc  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x1801797e1  mov     rcx, rax
0x1801797e4  lea     rdx, aIsDefinedForMi; "' is defined for mismatched hardware re"...
0x1801797eb  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x1801797f0  test    r14, r14
0x1801797f3  jz      short loc_18017982D
0x1801797f5  lea     rdx, [rbp+0B0h+var_70]
0x1801797f9  lea     rcx, [rsp+1B0h+var_158]
0x1801797fe  call    ?str@?$basic_stringbuf@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEBA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@XZ; std::stringbuf::str(void)
0x180179803  nop
0x180179804  lea     r8, [rbp+0B0h+var_70]
0x180179808  cmp     [rbp+0B0h+var_58], 0Fh
0x18017980d  cmova   r8, [rbp+0B0h+var_70]
0x180179812  mov     edx, 294h
0x180179817  mov     rcx, r13
0x18017981a  mov     rax, r14
0x18017981d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180179822  nop
0x180179823  lea     rcx, [rbp+0B0h+var_70]
0x180179827  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18017982c  nop
0x18017982d  lea     rcx, [rsp+1B0h+var_160]
0x180179832  call    ??_D?$basic_ostringstream@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAXXZ; std::ostringstream::`vbase destructor'(void)
0x180179837  inc     edi
0x180179839  mov     eax, [r12+rbx*8+18h]
0x18017983e  cmp     [rsi+rbx*8+18h], eax
0x180179842  jz      loc_180179914
0x180179848  lea     rcx, [rsp+1B0h+var_160]
0x18017984d  call    ??0?$basic_ostringstream@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::ostringstream::ostringstream(void)
0x180179852  nop
0x180179853  lea     rdx, Src
0x18017985a  lea     rcx, [rsp+1B0h+var_160]
0x18017985f  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x180179864  mov     rcx, rax
0x180179867  lea     rdx, aHullShaderToDo_0; "Hull Shader to Domain Shader linkage er"...
0x18017986e  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x180179873  lea     rdx, aPatchConstantD; "Patch Constant Data"
0x18017987a  cmp     r15d, 1
0x18017987e  lea     rcx, aControlPoints; "Control Points"
0x180179885  cmovnz  rdx, rcx
0x180179889  mov     rcx, rax
0x18017988c  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x180179891  mov     rcx, rax
0x180179894  lea     rdx, aBetweenStagesA; " between stages are incompatible. "
0x18017989b  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x1801798a0  mov     rcx, rax
0x1801798a3  lea     rdx, aSemantic; "Semantic '"
0x1801798aa  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x1801798af  mov     rdx, [rsi+rbx*8+8]
0x1801798b4  mov     rcx, rax
0x1801798b7  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x1801798bc  mov     rcx, rax
0x1801798bf  lea     rdx, aHasMismatchedD; "' has mismatched data types between the"...
0x1801798c6  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x1801798cb  test    r14, r14
0x1801798ce  jz      short loc_180179908
0x1801798d0  lea     rdx, [rbp+0B0h+var_70]
0x1801798d4  lea     rcx, [rsp+1B0h+var_158]
0x1801798d9  call    ?str@?$basic_stringbuf@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEBA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@XZ; std::stringbuf::str(void)
0x1801798de  nop
0x1801798df  lea     r8, [rbp+0B0h+var_70]
0x1801798e3  cmp     [rbp+0B0h+var_58], 0Fh
0x1801798e8  cmova   r8, [rbp+0B0h+var_70]
  ... truncated ...
```
