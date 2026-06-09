# Dossier::GetRTMBuild(ulong,ulong,ulong,ulong &)

- ea: `0x18000dd50`
- end: `0x18000df3a`
- name: `?GetRTMBuild@Dossier@@UEAAJKKKAEAK@Z`
- size: `490`
- prototype: `int(Dossier *__hidden this, unsigned int, unsigned int, unsigned int, unsigned int *)`
- caller_count: `0`
- callee_count: `6`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x18000b2d8`
- `0x18000dd50`
- `0x18000efec`
- `0x180018a50`
- `0x18001972e`
- `0x18001b010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000ddee`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000de68`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000deab`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000df0d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000df1a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000ddee`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000de68`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000deab`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000df0d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000df1a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x18000de16`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x18000de16`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000dd8a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000dd8a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000de70`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000de70`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000de5d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000de5d`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Dossier::GetRTMBuild(Dossier *this, unsigned int a2, int a3, int a4, unsigned int *a5)
{
  int v6; // r14d
  unsigned int v7; // r15d
  unsigned __int16 *v9; // rax
  unsigned __int16 *v10; // rbx
  int v11; // eax
  unsigned int v12; // edi
  __int64 v13; // rax
  int v14; // esi
  void *v15; // r12
  LPVOID *v16; // r14
  void *v17; // r15
  DWORD LastError; // edi
  int v20; // [rsp+20h] [rbp-40h]
  int v21; // [rsp+20h] [rbp-40h]
  int v22; // [rsp+28h] [rbp-38h]
  unsigned int v23; // [rsp+30h] [rbp-30h] BYREF
  unsigned int v24; // [rsp+34h] [rbp-2Ch] BYREF
  unsigned int v25; // [rsp+38h] [rbp-28h] BYREF
  unsigned int v26; // [rsp+3Ch] [rbp-24h] BYREF
  LPVOID pv; // [rsp+40h] [rbp-20h] BYREF
  LPVOID *p_pv; // [rsp+48h] [rbp-18h]
  void *v29; // [rsp+50h] [rbp-10h] BYREF
  char v30; // [rsp+58h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+38h]

  v6 = a3;
  v7 = a2;
  pv = 0;
  v9 = (unsigned __int16 *)CoTaskMemAlloc(0x208u);
  v10 = v9;
  if ( v9 )
    memset_0(v9, 0, 0x208u);
  v22 = a4;
  v20 = v6;
  v11 = StringCchPrintfW(v10, 0x104u, L"%d.%d.%d.RTM", v7, v20, v22);
  v12 = v11;
  if ( v11 >= 0 )
  {
    if ( v10 )
    {
      v13 = -1;
      do
        ++v13;
      while ( v10[v13] );
      v10 = (unsigned __int16 *)CoTaskMemRealloc(v10, 2LL * (unsigned int)(v13 + 1));
    }
    p_pv = &pv;
    v29 = 0;
    v30 = 1;
    v14 = (*(__int64 (__fastcall **)(Dossier *, unsigned __int16 *, void **))(*(_QWORD *)this + 48LL))(this, v10, &v29);
    if ( v30 )
    {
      v15 = v29;
      v16 = p_pv;
      v17 = *p_pv;
      if ( *p_pv )
      {
        LastError = GetLastError();
        CoTaskMemFree(v17);
        SetLastError(LastError);
      }
      *v16 = v15;
      v6 = a3;
      v7 = a2;
    }
    if ( v14 >= 0 )
    {
      v23 = 0;
      v24 = 0;
      v25 = 0;
      v26 = 0;
      if ( (unsigned int)GetVersionElements((const unsigned __int16 *)pv, &v23, &v24, &v25, &v26) == 4
        && v23 == v7
        && v24 == v6
        && v25 == a4 )
      {
        *a5 = v26;
      }
      if ( pv )
        CoTaskMemFree(pv);
      v12 = 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x148,
        (unsigned int)"onecore\\enduser\\waasassessment\\dossier\\dossier.cpp",
        (const char *)(unsigned int)v14,
        v21);
      if ( pv )
        CoTaskMemFree(pv);
      v12 = v14;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x144,
      (unsigned int)"onecore\\enduser\\waasassessment\\dossier\\dossier.cpp",
      (const char *)(unsigned int)v11,
      v21);
  }
  CoTaskMemFree(v10);
  return v12;
}

```

## disassembly

```asm
0x18000dd50  mov     [rsp-38h+arg_0], rbx
0x18000dd55  mov     [rsp-38h+arg_10], r8d
0x18000dd5a  mov     [rsp-38h+arg_8], edx
0x18000dd5e  push    rbp
0x18000dd5f  push    rsi
0x18000dd60  push    rdi
0x18000dd61  push    r12
0x18000dd63  push    r13
0x18000dd65  push    r14
0x18000dd67  push    r15
0x18000dd69  mov     rbp, rsp
0x18000dd6c  sub     rsp, 60h
0x18000dd70  mov     r13d, r9d
0x18000dd73  mov     r14d, r8d
0x18000dd76  mov     r15d, edx
0x18000dd79  mov     rsi, rcx
0x18000dd7c  xor     r12d, r12d
0x18000dd7f  mov     [rbp+pv], r12
0x18000dd83  mov     edi, 208h
0x18000dd88  mov     ecx, edi; cb
0x18000dd8a  call    cs:__imp_CoTaskMemAlloc
0x18000dd90  mov     rbx, rax
0x18000dd93  test    rax, rax
0x18000dd96  jz      short loc_18000DDA5
0x18000dd98  mov     r8d, edi; Size
0x18000dd9b  xor     edx, edx; Val
0x18000dd9d  mov     rcx, rax; void *
0x18000dda0  call    memset_0
0x18000dda5  mov     [rsp+60h+var_38], r13d
0x18000ddaa  mov     dword ptr [rsp+60h+var_40], r14d; int
0x18000ddaf  mov     r9d, r15d
0x18000ddb2  lea     r8, aDDDRtm; "%d.%d.%d.RTM"
0x18000ddb9  mov     edx, 104h; unsigned __int64
0x18000ddbe  mov     rcx, rbx; unsigned __int16 *
0x18000ddc1  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000ddc6  mov     edi, eax
0x18000ddc8  test    eax, eax
0x18000ddca  jns     short loc_18000DDFA
0x18000ddcc  mov     rcx, [rbp+38h]; this
0x18000ddd0  mov     r9d, eax; char *
0x18000ddd3  lea     r8, aOnecoreEnduser_1; "onecore\\enduser\\waasassessment\\dossi"...
0x18000ddda  mov     edx, 144h; void *
0x18000dddf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000dde4  nop
0x18000dde5  mov     rcx, [rbp+pv]; pv
0x18000dde9  test    rcx, rcx
0x18000ddec  jz      short loc_18000DDF5
0x18000ddee  call    cs:__imp_CoTaskMemFree
0x18000ddf4  nop
0x18000ddf5  jmp     loc_18000DF17
0x18000ddfa  test    rbx, rbx
0x18000ddfd  jz      short loc_18000DE1F
0x18000ddff  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000de03  inc     rax
0x18000de06  cmp     [rbx+rax*2], r12w
0x18000de0b  jnz     short loc_18000DE03
0x18000de0d  lea     edx, [rax+1]
0x18000de10  add     rdx, rdx; cb
0x18000de13  mov     rcx, rbx; pv
0x18000de16  call    cs:__imp_CoTaskMemRealloc
0x18000de1c  mov     rbx, rax
0x18000de1f  lea     rax, [rbp+pv]
0x18000de23  mov     [rbp+var_18], rax
0x18000de27  mov     [rbp+var_10], r12
0x18000de2b  mov     [rbp+var_8], 1
0x18000de2f  mov     rax, [rsi]
0x18000de32  lea     r8, [rbp+var_10]
0x18000de36  mov     rdx, rbx
0x18000de39  mov     rcx, rsi
0x18000de3c  mov     rax, [rax+30h]
0x18000de40  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000de45  mov     esi, eax
0x18000de47  cmp     [rbp+var_8], r12b
0x18000de4b  jz      short loc_18000DE85
0x18000de4d  mov     r12, [rbp+var_10]
0x18000de51  mov     r14, [rbp+var_18]
0x18000de55  mov     r15, [r14]
0x18000de58  test    r15, r15
0x18000de5b  jz      short loc_18000DE77
0x18000de5d  call    cs:__imp_GetLastError
0x18000de63  mov     edi, eax
0x18000de65  mov     rcx, r15; pv
0x18000de68  call    cs:__imp_CoTaskMemFree
0x18000de6e  mov     ecx, edi; dwErrCode
0x18000de70  call    cs:__imp_SetLastError
0x18000de76  nop
0x18000de77  mov     [r14], r12
0x18000de7a  mov     r14d, [rbp+arg_10]
0x18000de7e  mov     r15d, [rbp+arg_8]
0x18000de82  xor     r12d, r12d
0x18000de85  test    esi, esi
0x18000de87  jns     short loc_18000DEB6
0x18000de89  mov     rcx, [rbp+38h]; this
0x18000de8d  mov     r9d, esi; char *
0x18000de90  lea     r8, aOnecoreEnduser_1; "onecore\\enduser\\waasassessment\\dossi"...
0x18000de97  mov     edx, 148h; void *
0x18000de9c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000dea1  nop
0x18000dea2  mov     rcx, [rbp+pv]; pv
0x18000dea6  test    rcx, rcx
0x18000dea9  jz      short loc_18000DEB2
0x18000deab  call    cs:__imp_CoTaskMemFree
0x18000deb1  nop
0x18000deb2  mov     edi, esi
0x18000deb4  jmp     short loc_18000DF17
0x18000deb6  mov     [rbp+var_30], r12d
0x18000deba  mov     [rbp+var_2C], r12d
0x18000debe  mov     [rbp+var_28], r12d
0x18000dec2  mov     [rbp+var_24], r12d
0x18000dec6  lea     rax, [rbp+var_24]
0x18000deca  mov     [rsp+60h+var_40], rax; unsigned int *
0x18000decf  lea     r9, [rbp+var_28]; unsigned int *
0x18000ded3  lea     r8, [rbp+var_2C]; unsigned int *
0x18000ded7  lea     rdx, [rbp+var_30]; unsigned int *
0x18000dedb  mov     rcx, [rbp+pv]; unsigned __int16 *
0x18000dedf  call    ?GetVersionElements@@YAHPEBGAEAK111@Z; GetVersionElements(ushort const *,ulong &,ulong &,ulong &,ulong &)
0x18000dee4  cmp     eax, 4
0x18000dee7  jnz     short loc_18000DF04
0x18000dee9  cmp     [rbp+var_30], r15d
0x18000deed  jnz     short loc_18000DF04
0x18000deef  cmp     [rbp+var_2C], r14d
0x18000def3  jnz     short loc_18000DF04
0x18000def5  cmp     [rbp+var_28], r13d
0x18000def9  jnz     short loc_18000DF04
0x18000defb  mov     rcx, [rbp+arg_20]
0x18000deff  mov     eax, [rbp+var_24]
0x18000df02  mov     [rcx], eax
0x18000df04  mov     rcx, [rbp+pv]; pv
0x18000df08  test    rcx, rcx
0x18000df0b  jz      short loc_18000DF14
0x18000df0d  call    cs:__imp_CoTaskMemFree
0x18000df13  nop
0x18000df14  mov     edi, r12d
0x18000df17  mov     rcx, rbx; pv
0x18000df1a  call    cs:__imp_CoTaskMemFree
0x18000df20  mov     eax, edi
0x18000df22  mov     rbx, [rsp+60h+arg_0]
0x18000df2a  add     rsp, 60h
0x18000df2e  pop     r15
0x18000df30  pop     r14
0x18000df32  pop     r13
0x18000df34  pop     r12
0x18000df36  pop     rdi
0x18000df37  pop     rsi
0x18000df38  pop     rbp
0x18000df39  retn
```
