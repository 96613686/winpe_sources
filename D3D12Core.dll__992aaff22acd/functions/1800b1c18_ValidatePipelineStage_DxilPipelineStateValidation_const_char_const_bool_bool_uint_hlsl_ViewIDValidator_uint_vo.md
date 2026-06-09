# ValidatePipelineStage(DxilPipelineStateValidation const *,char const *,bool &,bool &,uint,hlsl::ViewIDValidator *,uint,void *,void (*)(void *,D3D12_MESSAGE_ID,char const *),char const *)

- ea: `0x1800b1c18`
- end: `0x1800b2041`
- name: `?ValidatePipelineStage@@YAIPEBVDxilPipelineStateValidation@@PEBDAEA_N2IPEAVViewIDValidator@hlsl@@IPEAXP6AX4W4D3D12_MESSAGE_ID@@1@Z1@Z`
- size: `1065`
- prototype: `unsigned int __fastcall(const struct DxilPipelineStateValidation *, const char *, bool *, bool *, unsigned int, struct hlsl::ViewIDValidator *, unsigned int, void *, void (*)(void *, enum D3D12_MESSAGE_ID, const char *), const char *)`
- caller_count: `2`
- callee_count: `8`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800b16c8`
- `0x18016cbe0`

## callees

- `0x18009fd4c`
- `0x1800b1c18`
- `0x1800bb480`
- `0x1800cc130`
- `0x1800e85b0`
- `0x1800eb674`
- `0x180102704`
- `0x180262020`

## import_xrefs

- `msvcp_win!??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@H@Z` at `0x1800b1e3c`
- `msvcp_win!??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@H@Z` at `0x1800b1eec`
- `msvcp_win!??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@H@Z` at `0x1800b1f9c`
- `msvcp_win!??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@H@Z` at `0x1800b1e3c`
- `msvcp_win!??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@H@Z` at `0x1800b1eec`
- `msvcp_win!??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@H@Z` at `0x1800b1f9c`
- `msvcp_win!??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@I@Z` at `0x1800b1e57`
- `msvcp_win!??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@I@Z` at `0x1800b1f07`
- `msvcp_win!??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@I@Z` at `0x1800b1fb7`
- `msvcp_win!??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@I@Z` at `0x1800b1e57`
- `msvcp_win!??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@I@Z` at `0x1800b1f07`
- `msvcp_win!??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@I@Z` at `0x1800b1fb7`

## string_xrefs

- `0x1800b1e60`: `), based on the compiler's component packing rules.`
- `0x1800b1f10`: `), based on the compiler's component packing rules.`
- `0x1800b1fc0`: `), based on the compiler's component packing rules.`
- `0x1800b1e45`: ` components when accounting for expansion of components that are dependent on ViewID by the declared ViewInstanceCount (`
- `0x1800b1ef5`: ` components when accounting for expansion of components that are dependent on ViewID by the declared ViewInstanceCount (`
- `0x1800b1fa5`: ` components when accounting for expansion of components that are dependent on ViewID by the declared ViewInstanceCount (`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall ValidatePipelineStage(
        const struct DxilPipelineStateValidation *a1,
        const char *a2,
        bool *a3,
        bool *a4,
        unsigned int a5,
        struct hlsl::ViewIDValidator *a6,
        unsigned int a7,
        void *a8,
        void (*a9)(void *, enum D3D12_MESSAGE_ID, const char *))
{
  bool *v9; // rsi
  unsigned int v11; // ebx
  int v12; // eax
  __int64 v13; // rax
  __int64 v14; // rax
  _QWORD *v15; // r8
  __int64 v16; // rax
  __int64 v17; // rax
  __int64 v18; // rax
  _QWORD *v19; // r8
  __int64 v20; // rax
  __int64 v21; // rax
  __int64 v22; // rax
  __int64 v23; // rax
  __int64 v24; // rax
  __int64 v25; // rax
  _QWORD *v26; // r8
  __int64 v27; // rax
  __int64 v28; // rax
  __int64 v29; // rax
  __int64 v30; // rax
  __int64 v31; // rax
  __int64 v32; // rax
  _QWORD *v33; // r8
  __int64 v34; // rax
  __int64 v35; // rax
  __int64 v36; // rax
  __int64 v37; // rax
  __int64 v38; // rax
  __int64 v39; // rax
  _QWORD *v40; // r8
  _DWORD v42[4]; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v43[8]; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v44[232]; // [rsp+48h] [rbp-B8h] BYREF
  _QWORD v45[3]; // [rsp+130h] [rbp+30h] BYREF
  unsigned __int64 v46; // [rsp+148h] [rbp+48h]

  v9 = a3;
  if ( a1 && !*a4 )
  {
    if ( *a3 )
      *a4 = 1;
    v11 = 0;
    v42[0] = 0;
    LOBYTE(a3) = a5 == 0;
    LOBYTE(a4) = *v9;
    v12 = (*(__int64 (__fastcall **)(struct hlsl::ViewIDValidator *, const struct DxilPipelineStateValidation *, bool *, bool *, _DWORD *))(*(_QWORD *)a6 + 8LL))(
            a6,
            a1,
            a3,
            a4,
            v42);
    if ( v12 == 1 )
    {
      *v9 = 1;
    }
    else
    {
      switch ( v12 )
      {
        case 2:
          std::ostringstream::ostringstream(v43);
          v34 = std::operator<<<std::char_traits<char>>(v43, Src);
          v35 = std::operator<<<std::char_traits<char>>(v34, a2);
          v36 = std::operator<<<std::char_traits<char>>(v35, " stage inputs do not fit within maximum vertex size of");
          v37 = std::ostream::operator<<(v36, 128);
          v38 = std::operator<<<std::char_traits<char>>(
                  v37,
                  " components when accounting for expansion of components that are dependent on ViewID by the declared V"
                  "iewInstanceCount (");
          v39 = std::ostream::operator<<(v38, a7);
          std::operator<<<std::char_traits<char>>(v39, "), based on the compiler's component packing rules.");
          if ( a9 )
          {
            std::stringbuf::str(v44, v45);
            v40 = v45;
            if ( v46 > 0xF )
              v40 = (_QWORD *)v45[0];
            ((void (__fastcall *)(void *, __int64, _QWORD *))a9)(a8, 1104, v40);
            std::string::_Tidy_deallocate(v45);
          }
          break;
        case 3:
          std::ostringstream::ostringstream(v43);
          v27 = std::operator<<<std::char_traits<char>>(v43, Src);
          v28 = std::operator<<<std::char_traits<char>>(v27, a2);
          v29 = std::operator<<<std::char_traits<char>>(v28, " stage outputs do not fit within maximum vertex size of");
          v30 = std::ostream::operator<<(v29, 128);
          v31 = std::operator<<<std::char_traits<char>>(
                  v30,
                  " components when accounting for expansion of components that are dependent on ViewID by the declared V"
                  "iewInstanceCount (");
          v32 = std::ostream::operator<<(v31, a7);
          std::operator<<<std::char_traits<char>>(v32, "), based on the compiler's component packing rules.");
          if ( a9 )
          {
            std::stringbuf::str(v44, v45);
            v33 = v45;
            if ( v46 > 0xF )
              v33 = (_QWORD *)v45[0];
            ((void (__fastcall *)(void *, __int64, _QWORD *))a9)(a8, 1104, v33);
            std::string::_Tidy_deallocate(v45);
          }
          break;
        case 4:
          std::ostringstream::ostringstream(v43);
          v20 = std::operator<<<std::char_traits<char>>(v43, Src);
          v21 = std::operator<<<std::char_traits<char>>(v20, a2);
          v22 = std::operator<<<std::char_traits<char>>(
                  v21,
                  " stage patch constant inputs do not fit within maximum vertex size of");
          v23 = std::ostream::operator<<(v22, 128);
          v24 = std::operator<<<std::char_traits<char>>(
                  v23,
                  " components when accounting for expansion of components that are dependent on ViewID by the declared V"
                  "iewInstanceCount (");
          v25 = std::ostream::operator<<(v24, a7);
          std::operator<<<std::char_traits<char>>(v25, "), based on the compiler's component packing rules.");
          if ( a9 )
          {
            std::stringbuf::str(v44, v45);
            v26 = v45;
            if ( v46 > 0xF )
              v26 = (_QWORD *)v45[0];
            ((void (__fastcall *)(void *, __int64, _QWORD *))a9)(a8, 1104, v26);
            std::string::_Tidy_deallocate(v45);
          }
          break;
        case 5:
        case 6:
        case 7:
          std::ostringstream::ostringstream(v43);
          v16 = std::operator<<<std::char_traits<char>>(v43, Src);
          v17 = std::operator<<<std::char_traits<char>>(v16, "Internal runtime error validating");
          v18 = std::operator<<<std::char_traits<char>>(v17, a2);
          std::operator<<<std::char_traits<char>>(v18, " stage in a PSOs used with view instancing.");
          if ( a9 )
          {
            std::stringbuf::str(v44, v45);
            v19 = v45;
            if ( v46 > 0xF )
              v19 = (_QWORD *)v45[0];
            ((void (__fastcall *)(void *, __int64, _QWORD *))a9)(a8, 1105, v19);
            std::string::_Tidy_deallocate(v45);
          }
          break;
        case 8:
        case 9:
          std::ostringstream::ostringstream(v43);
          v13 = std::operator<<<std::char_traits<char>>(v43, Src);
          v14 = std::operator<<<std::char_traits<char>>(v13, a2);
          std::operator<<<std::char_traits<char>>(
            v14,
            " stage validation metadata required for PSOs used with view instancing is invalid or incorrect version.");
          if ( a9 )
          {
            std::stringbuf::str(v44, v45);
            v15 = v45;
            if ( v46 > 0xF )
              v15 = (_QWORD *)v45[0];
            ((void (__fastcall *)(void *, __int64, _QWORD *))a9)(a8, 1105, v15);
            std::string::_Tidy_deallocate(v45);
          }
          break;
        default:
          return v11;
      }
      std::ostringstream::`vbase destructor'(v43);
      return 1;
    }
    return v11;
  }
  return 0;
}

```

## disassembly

```asm
0x1800b1c18  push    rbp
0x1800b1c1a  push    rbx
0x1800b1c1b  push    rsi
0x1800b1c1c  push    rdi
0x1800b1c1d  push    r12
0x1800b1c1f  push    r13
0x1800b1c21  push    r14
0x1800b1c23  push    r15
0x1800b1c25  lea     rbp, [rsp-68h]
0x1800b1c2a  sub     rsp, 168h
0x1800b1c31  mov     rax, cs:__security_cookie
0x1800b1c38  xor     rax, rsp
0x1800b1c3b  mov     [rbp+0A0h+var_50], rax
0x1800b1c3f  mov     rsi, r8
0x1800b1c42  mov     r15, rdx
0x1800b1c45  mov     r10, [rbp+0A0h+arg_28]
0x1800b1c4c  mov     r12d, [rbp+0A0h+arg_30]
0x1800b1c53  mov     r14, [rbp+0A0h+arg_38]
0x1800b1c5a  mov     rdi, [rbp+0A0h+arg_40]
0x1800b1c61  xor     edx, edx
0x1800b1c63  test    rcx, rcx
0x1800b1c66  jz      loc_1800B201F
0x1800b1c6c  cmp     [r9], dl
0x1800b1c6f  jnz     loc_1800B201F
0x1800b1c75  lea     r13d, [rdx+1]
0x1800b1c79  cmp     [r8], dl
0x1800b1c7c  jz      short loc_1800B1C81
0x1800b1c7e  mov     [r9], r13b
0x1800b1c81  mov     ebx, edx
0x1800b1c83  mov     [rsp+1A0h+var_170], edx
0x1800b1c87  mov     rax, [r10]
0x1800b1c8a  cmp     [rbp+0A0h+arg_20], edx
0x1800b1c90  setz    r8b
0x1800b1c94  lea     rdx, [rsp+1A0h+var_170]
0x1800b1c99  mov     [rsp+1A0h+var_180], rdx
0x1800b1c9e  mov     r9b, [rsi]
0x1800b1ca1  mov     rdx, rcx
0x1800b1ca4  mov     rcx, r10
0x1800b1ca7  mov     rax, [rax+8]
0x1800b1cab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b1cb0  mov     ecx, eax
0x1800b1cb2  sub     ecx, r13d
0x1800b1cb5  jz      loc_1800B2018
0x1800b1cbb  sub     ecx, r13d
0x1800b1cbe  jz      loc_1800B1F5E
0x1800b1cc4  sub     ecx, r13d
0x1800b1cc7  jz      loc_1800B1EAE
0x1800b1ccd  sub     ecx, r13d
0x1800b1cd0  jz      loc_1800B1DFE
0x1800b1cd6  sub     ecx, r13d
0x1800b1cd9  jz      loc_1800B1D77
0x1800b1cdf  sub     ecx, r13d
0x1800b1ce2  jz      loc_1800B1D77
0x1800b1ce8  sub     ecx, r13d
0x1800b1ceb  jz      loc_1800B1D77
0x1800b1cf1  sub     ecx, r13d
0x1800b1cf4  jz      short loc_1800B1CFF
0x1800b1cf6  cmp     ecx, r13d
0x1800b1cf9  jnz     loc_1800B201B
0x1800b1cff  lea     rcx, [rsp+1A0h+var_160]
0x1800b1d04  call    ??0?$basic_ostringstream@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::ostringstream::ostringstream(void)
0x1800b1d09  nop
0x1800b1d0a  lea     rdx, Src
0x1800b1d11  lea     rcx, [rsp+1A0h+var_160]
0x1800b1d16  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x1800b1d1b  mov     rcx, rax
0x1800b1d1e  mov     rdx, r15
0x1800b1d21  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x1800b1d26  mov     rcx, rax
0x1800b1d29  lea     rdx, aStageValidatio; " stage validation metadata required for"...
0x1800b1d30  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x1800b1d35  test    rdi, rdi
0x1800b1d38  jz      short loc_1800B1D72
0x1800b1d3a  lea     rdx, [rbp+0A0h+var_70]
0x1800b1d3e  lea     rcx, [rsp+1A0h+var_158]
0x1800b1d43  call    ?str@?$basic_stringbuf@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEBA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@XZ; std::stringbuf::str(void)
0x1800b1d48  nop
0x1800b1d49  lea     r8, [rbp+0A0h+var_70]
0x1800b1d4d  cmp     [rbp+0A0h+var_58], 0Fh
0x1800b1d52  cmova   r8, [rbp+0A0h+var_70]
0x1800b1d57  mov     edx, 451h
0x1800b1d5c  mov     rcx, r14
0x1800b1d5f  mov     rax, rdi
0x1800b1d62  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b1d67  nop
0x1800b1d68  lea     rcx, [rbp+0A0h+var_70]
0x1800b1d6c  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1800b1d71  nop
0x1800b1d72  jmp     loc_1800B2009
0x1800b1d77  lea     rcx, [rsp+1A0h+var_160]
0x1800b1d7c  call    ??0?$basic_ostringstream@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::ostringstream::ostringstream(void)
0x1800b1d81  nop
0x1800b1d82  lea     rdx, Src
0x1800b1d89  lea     rcx, [rsp+1A0h+var_160]
0x1800b1d8e  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x1800b1d93  mov     rcx, rax
0x1800b1d96  lea     rdx, aInternalRuntim; "Internal runtime error validating"
0x1800b1d9d  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x1800b1da2  mov     rcx, rax
0x1800b1da5  mov     rdx, r15
0x1800b1da8  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x1800b1dad  mov     rcx, rax
0x1800b1db0  lea     rdx, aStageInAPsosUs; " stage in a PSOs used with view instanc"...
0x1800b1db7  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x1800b1dbc  test    rdi, rdi
0x1800b1dbf  jz      short loc_1800B1DF9
0x1800b1dc1  lea     rdx, [rbp+0A0h+var_70]
0x1800b1dc5  lea     rcx, [rsp+1A0h+var_158]
0x1800b1dca  call    ?str@?$basic_stringbuf@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEBA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@XZ; std::stringbuf::str(void)
0x1800b1dcf  nop
0x1800b1dd0  lea     r8, [rbp+0A0h+var_70]
0x1800b1dd4  cmp     [rbp+0A0h+var_58], 0Fh
0x1800b1dd9  cmova   r8, [rbp+0A0h+var_70]
0x1800b1dde  mov     edx, 451h
0x1800b1de3  mov     rcx, r14
0x1800b1de6  mov     rax, rdi
0x1800b1de9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b1dee  nop
0x1800b1def  lea     rcx, [rbp+0A0h+var_70]
0x1800b1df3  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1800b1df8  nop
0x1800b1df9  jmp     loc_1800B2009
0x1800b1dfe  lea     rcx, [rsp+1A0h+var_160]
0x1800b1e03  call    ??0?$basic_ostringstream@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::ostringstream::ostringstream(void)
0x1800b1e08  nop
0x1800b1e09  lea     rdx, Src
0x1800b1e10  lea     rcx, [rsp+1A0h+var_160]
0x1800b1e15  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x1800b1e1a  mov     rcx, rax
0x1800b1e1d  mov     rdx, r15
0x1800b1e20  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x1800b1e25  mov     rcx, rax
0x1800b1e28  lea     rdx, aStagePatchCons; " stage patch constant inputs do not fit"...
0x1800b1e2f  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x1800b1e34  mov     edx, 80h
0x1800b1e39  mov     rcx, rax
0x1800b1e3c  call    cs:__imp_??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@H@Z; std::ostream::operator<<(int)
0x1800b1e42  mov     rcx, rax
0x1800b1e45  lea     rdx, aComponentsWhen; " components when accounting for expansi"...
0x1800b1e4c  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x1800b1e51  mov     edx, r12d
0x1800b1e54  mov     rcx, rax
0x1800b1e57  call    cs:__imp_??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@I@Z; std::ostream::operator<<(uint)
0x1800b1e5d  mov     rcx, rax
0x1800b1e60  lea     rdx, aBasedOnTheComp; "), based on the compiler's component pa"...
0x1800b1e67  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x1800b1e6c  test    rdi, rdi
0x1800b1e6f  jz      short loc_1800B1EA9
0x1800b1e71  lea     rdx, [rbp+0A0h+var_70]
0x1800b1e75  lea     rcx, [rsp+1A0h+var_158]
0x1800b1e7a  call    ?str@?$basic_stringbuf@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEBA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@XZ; std::stringbuf::str(void)
0x1800b1e7f  nop
0x1800b1e80  lea     r8, [rbp+0A0h+var_70]
0x1800b1e84  cmp     [rbp+0A0h+var_58], 0Fh
0x1800b1e89  cmova   r8, [rbp+0A0h+var_70]
0x1800b1e8e  mov     edx, 450h
0x1800b1e93  mov     rcx, r14
0x1800b1e96  mov     rax, rdi
0x1800b1e99  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b1e9e  nop
0x1800b1e9f  lea     rcx, [rbp+0A0h+var_70]
0x1800b1ea3  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1800b1ea8  nop
0x1800b1ea9  jmp     loc_1800B2009
0x1800b1eae  lea     rcx, [rsp+1A0h+var_160]
0x1800b1eb3  call    ??0?$basic_ostringstream@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::ostringstream::ostringstream(void)
0x1800b1eb8  nop
0x1800b1eb9  lea     rdx, Src
0x1800b1ec0  lea     rcx, [rsp+1A0h+var_160]
0x1800b1ec5  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x1800b1eca  mov     rcx, rax
0x1800b1ecd  mov     rdx, r15
0x1800b1ed0  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x1800b1ed5  mov     rcx, rax
0x1800b1ed8  lea     rdx, aStageOutputsDo; " stage outputs do not fit within maximu"...
0x1800b1edf  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x1800b1ee4  mov     edx, 80h
0x1800b1ee9  mov     rcx, rax
0x1800b1eec  call    cs:__imp_??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@H@Z; std::ostream::operator<<(int)
0x1800b1ef2  mov     rcx, rax
0x1800b1ef5  lea     rdx, aComponentsWhen; " components when accounting for expansi"...
0x1800b1efc  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x1800b1f01  mov     edx, r12d
0x1800b1f04  mov     rcx, rax
0x1800b1f07  call    cs:__imp_??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@I@Z; std::ostream::operator<<(uint)
0x1800b1f0d  mov     rcx, rax
0x1800b1f10  lea     rdx, aBasedOnTheComp; "), based on the compiler's component pa"...
0x1800b1f17  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x1800b1f1c  test    rdi, rdi
0x1800b1f1f  jz      short loc_1800B1F59
0x1800b1f21  lea     rdx, [rbp+0A0h+var_70]
0x1800b1f25  lea     rcx, [rsp+1A0h+var_158]
0x1800b1f2a  call    ?str@?$basic_stringbuf@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEBA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@XZ; std::stringbuf::str(void)
0x1800b1f2f  nop
0x1800b1f30  lea     r8, [rbp+0A0h+var_70]
0x1800b1f34  cmp     [rbp+0A0h+var_58], 0Fh
0x1800b1f39  cmova   r8, [rbp+0A0h+var_70]
0x1800b1f3e  mov     edx, 450h
0x1800b1f43  mov     rcx, r14
0x1800b1f46  mov     rax, rdi
0x1800b1f49  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b1f4e  nop
0x1800b1f4f  lea     rcx, [rbp+0A0h+var_70]
0x1800b1f53  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1800b1f58  nop
0x1800b1f59  jmp     loc_1800B2009
0x1800b1f5e  lea     rcx, [rsp+1A0h+var_160]
0x1800b1f63  call    ??0?$basic_ostringstream@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::ostringstream::ostringstream(void)
0x1800b1f68  nop
0x1800b1f69  lea     rdx, Src
0x1800b1f70  lea     rcx, [rsp+1A0h+var_160]
0x1800b1f75  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x1800b1f7a  mov     rcx, rax
0x1800b1f7d  mov     rdx, r15
0x1800b1f80  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x1800b1f85  mov     rcx, rax
0x1800b1f88  lea     rdx, aStageInputsDoN; " stage inputs do not fit within maximum"...
0x1800b1f8f  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x1800b1f94  mov     edx, 80h
0x1800b1f99  mov     rcx, rax
0x1800b1f9c  call    cs:__imp_??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@H@Z; std::ostream::operator<<(int)
0x1800b1fa2  mov     rcx, rax
0x1800b1fa5  lea     rdx, aComponentsWhen; " components when accounting for expansi"...
0x1800b1fac  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x1800b1fb1  mov     edx, r12d
0x1800b1fb4  mov     rcx, rax
0x1800b1fb7  call    cs:__imp_??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@I@Z; std::ostream::operator<<(uint)
0x1800b1fbd  mov     rcx, rax
0x1800b1fc0  lea     rdx, aBasedOnTheComp; "), based on the compiler's component pa"...
0x1800b1fc7  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x1800b1fcc  test    rdi, rdi
0x1800b1fcf  jz      short loc_1800B2009
0x1800b1fd1  lea     rdx, [rbp+0A0h+var_70]
0x1800b1fd5  lea     rcx, [rsp+1A0h+var_158]
0x1800b1fda  call    ?str@?$basic_stringbuf@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEBA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@XZ; std::stringbuf::str(void)
0x1800b1fdf  nop
0x1800b1fe0  lea     r8, [rbp+0A0h+var_70]
0x1800b1fe4  cmp     [rbp+0A0h+var_58], 0Fh
0x1800b1fe9  cmova   r8, [rbp+0A0h+var_70]
0x1800b1fee  mov     edx, 450h
0x1800b1ff3  mov     rcx, r14
0x1800b1ff6  mov     rax, rdi
0x1800b1ff9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b1ffe  nop
0x1800b1fff  lea     rcx, [rbp+0A0h+var_70]
0x1800b2003  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1800b2008  nop
0x1800b2009  lea     rcx, [rsp+1A0h+var_160]
0x1800b200e  call    ??_D?$basic_ostringstream@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAXXZ; std::ostringstream::`vbase destructor'(void)
0x1800b2013  mov     ebx, r13d
0x1800b2016  jmp     short loc_1800B201B
0x1800b2018  mov     [rsi], r13b
0x1800b201b  mov     eax, ebx
0x1800b201d  jmp     short loc_1800B2021
0x1800b201f  xor     eax, eax
0x1800b2021  mov     rcx, [rbp+0A0h+var_50]
0x1800b2025  xor     rcx, rsp; StackCookie
0x1800b2028  call    __security_check_cookie
0x1800b202d  add     rsp, 168h
0x1800b2034  pop     r15
0x1800b2036  pop     r14
0x1800b2038  pop     r13
0x1800b203a  pop     r12
0x1800b203c  pop     rdi
0x1800b203d  pop     rsi
0x1800b203e  pop     rbx
0x1800b203f  pop     rbp
0x1800b2040  retn
```
