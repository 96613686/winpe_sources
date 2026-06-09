# DiagnosisTextBuilderImpl::GetXML(ushort * *)

- ea: `0x18000afd8`
- end: `0x18000b3db`
- name: `?GetXML@DiagnosisTextBuilderImpl@@QEAAJPEAPEAG@Z`
- size: `1027`
- prototype: `__int64 __fastcall(DiagnosisTextBuilderImpl *__hidden this, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180005e60`

## callees

- `0x180005c60`
- `0x18000ac50`
- `0x18000ae28`
- `0x18000afd8`
- `0x18000c572`
- `0x18000e010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000b08b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000b08b`

## string_xrefs

- `0x18000b17f`: `</Parameters><Extensions>`
- `0x18000b1be`: `</Extensions></DiagnosticsText>`
- `0x18000b253`: `<Extension><Name><![CDATA[%s]]></Name><Value><![CDATA[%s]]></Value></Extension>`

## pseudocode

```c
__int64 __fastcall DiagnosisTextBuilderImpl::GetXML(DiagnosisTextBuilderImpl *this, unsigned __int16 **a2)
{
  unsigned int v3; // r12d
  const unsigned __int16 *v4; // rsi
  __int64 *v5; // rbx
  const unsigned __int16 *v6; // rdi
  __int64 *v7; // rbx
  unsigned __int64 v8; // r14
  unsigned __int16 *v9; // rax
  unsigned __int16 *v10; // rbx
  __int64 v11; // rax
  __int64 v12; // r11
  __int64 v13; // rax
  __int64 v14; // r11
  __int64 v15; // rax
  __int64 v16; // r11
  __int64 v17; // rax
  __int64 v18; // r11
  __int64 v19; // rax
  __int64 v20; // r11
  __int64 v21; // rax
  __int64 v22; // r11
  __int64 v23; // rax
  __int64 v24; // r11
  __int64 v25; // rax
  unsigned int v26; // r11d
  __int64 v27; // rdi
  __int64 *i; // rax
  __int64 *v29; // rcx
  __int64 v30; // rdi
  __int64 *j; // rax
  __int64 *v32; // rcx
  __int64 v34; // [rsp+20h] [rbp-48h] BYREF
  ATL::CAtlException *v35; // [rsp+28h] [rbp-40h] BYREF
  __int64 v37; // [rsp+80h] [rbp+18h] BYREF
  const unsigned __int16 *v38; // [rsp+88h] [rbp+20h] BYREF

  v3 = 0;
  v4 = (const unsigned __int16 *)(((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24);
  v38 = v4;
  v5 = (__int64 *)**((_QWORD **)this + 3);
  if ( __eh34_try(-1, 0) )
  {
    __eh34_scope_strut(0);
    while ( 1 )
    {
      if ( v5 == *((__int64 **)this + 3) )
      {
        v6 = (const unsigned __int16 *)(((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24);
        v37 = (__int64)v6;
        v7 = (__int64 *)**((_QWORD **)this + 5);
        while ( 1 )
        {
          if ( v7 == *((__int64 **)this + 5) )
          {
            v8 = *((int *)v6 - 4)
               + *(int *)(*((_QWORD *)this + 1) - 16LL)
               + 152LL
               + *(int *)(*((_QWORD *)this + 2) - 16LL)
               + *((int *)v4 - 4);
            v9 = (unsigned __int16 *)CoTaskMemAlloc(2 * v8);
            v10 = v9;
            if ( v9 )
            {
              memset_0(v9, 0, 2 * v8);
              StringCchCopyW(v10, v8, L"<DiagnosticsText><Title><![CDATA[");
              v11 = -1;
              do
                ++v11;
              while ( v10[v11] );
              StringCchCopyW(&v10[v11], v8 - v11, *((unsigned __int16 **)this + 1));
              v13 = v12;
              do
                ++v13;
              while ( v10[v13] );
              StringCchCopyW(&v10[v13], v8 - v13, L"]]></Title><Description><![CDATA[");
              v15 = v14;
              do
                ++v15;
              while ( v10[v15] );
              StringCchCopyW(&v10[v15], v8 - v15, *((unsigned __int16 **)this + 2));
              v17 = v16;
              do
                ++v17;
              while ( v10[v17] );
              StringCchCopyW(&v10[v17], v8 - v17, L"]]></Description><Parameters>");
              v19 = v18;
              do
                ++v19;
              while ( v10[v19] );
              StringCchCopyW(&v10[v19], v8 - v19, (unsigned __int16 *)v4);
              v21 = v20;
              do
                ++v21;
              while ( v10[v21] );
              StringCchCopyW(&v10[v21], v8 - v21, L"</Parameters><Extensions>");
              v23 = v22;
              do
                ++v23;
              while ( v10[v23] );
              StringCchCopyW(&v10[v23], v8 - v23, (unsigned __int16 *)v6);
              v25 = v24;
              do
                ++v25;
              while ( v10[v25] );
              StringCchCopyW(&v10[v25], v8 - v25, L"</Extensions></DiagnosticsText>");
              *a2 = v10;
            }
            else
            {
              v3 = -2147024882;
              v26 = -1;
            }
            if ( (int)(v26 + _InterlockedExchangeAdd((volatile signed __int32 *)v6 - 2, v26)) <= 0 )
            {
              (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v6 - 3) + 8LL))(*((_QWORD *)v6 - 3));
              v26 = -1;
            }
            if ( (int)(v26 + _InterlockedExchangeAdd((volatile signed __int32 *)v4 - 2, v26)) <= 0 )
              (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v4 - 3) + 8LL))(*((_QWORD *)v4 - 3));
            return v3;
          }
          v34 = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
          ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Format(
            &v34,
            L"<Extension><Name><![CDATA[%s]]></Name><Value><![CDATA[%s]]></Value></Extension>",
            v7[4],
            v7[5]);
          v27 = v34;
          ATL::CSimpleStringT<unsigned short,0>::Append(&v37, v34, *(unsigned int *)(v34 - 16));
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v27 - 24 + 16), 0xFFFFFFFF) <= 1 )
            (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(v27 - 24) + 8LL))(*(_QWORD *)(v27 - 24));
          if ( !*((_BYTE *)v7 + 25) )
          {
            i = (__int64 *)v7[2];
            if ( *((_BYTE *)i + 25) )
            {
              for ( i = (__int64 *)v7[1]; !*((_BYTE *)i + 25) && v7 == (__int64 *)i[2]; i = (__int64 *)i[1] )
                v7 = i;
LABEL_36:
              v7 = i;
              goto LABEL_37;
            }
            v29 = (__int64 *)*i;
            if ( *(_BYTE *)(*i + 25) )
              goto LABEL_36;
            do
            {
              v7 = v29;
              v29 = (__int64 *)*v29;
            }
            while ( !*((_BYTE *)v29 + 25) );
          }
LABEL_37:
          v6 = (const unsigned __int16 *)v37;
        }
      }
      v37 = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Format(
        &v37,
        L"<Parameter><Name><![CDATA[%s]]></Name><Value><![CDATA[%s]]></Value></Parameter>",
        v5[4],
        v5[5]);
      v30 = v37;
      ATL::CSimpleStringT<unsigned short,0>::Append(&v38, v37, *(unsigned int *)(v37 - 16));
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v30 - 24 + 16), 0xFFFFFFFF) <= 1 )
        (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(v30 - 24) + 8LL))(*(_QWORD *)(v30 - 24));
      if ( !*((_BYTE *)v5 + 25) )
      {
        j = (__int64 *)v5[2];
        if ( *((_BYTE *)j + 25) )
        {
          for ( j = (__int64 *)v5[1]; !*((_BYTE *)j + 25) && v5 == (__int64 *)j[2]; j = (__int64 *)j[1] )
            v5 = j;
LABEL_50:
          v5 = j;
          goto LABEL_51;
        }
        v32 = (__int64 *)*j;
        if ( *(_BYTE *)(*j + 25) )
          goto LABEL_50;
        do
        {
          v5 = v32;
          v32 = (__int64 *)*v32;
        }
        while ( !*((_BYTE *)v32 + 25) );
      }
LABEL_51:
      v4 = v38;
    }
  }
  if ( __eh34_catch(0) )
  {
    if ( __eh34_catch_type(0, &ATL::CAtlException `RTTI Type Descriptor', &v35) )
    {
      LODWORD(v37) = *(_DWORD *)v35;
      v3 = v37;
      __eh34_try_continuation(0, &ATL::CAtlException `RTTI Type Descriptor', &loc_18000B3C0);
    }
  }
  return v3;
}

```

## disassembly

```asm
0x18000afd8  mov     [rsp+arg_8], rdx
0x18000afdd  push    rbx
0x18000afde  push    rsi
0x18000afdf  push    rdi
0x18000afe0  push    r12
0x18000afe2  push    r13
0x18000afe4  push    r14
0x18000afe6  push    r15
0x18000afe8  sub     rsp, 30h
0x18000afec  mov     r13, rcx
0x18000afef  xor     r14d, r14d
0x18000aff2  mov     r12d, r14d
0x18000aff5  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x18000affc  lea     r15, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x18000b003  mov     rcx, r15
0x18000b006  mov     rax, [rax+18h]
0x18000b00a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b00f  lea     rsi, [rax+18h]
0x18000b013  mov     [rsp+68h+arg_18], rsi
0x18000b01b  mov     rbx, [r13+18h]
0x18000b01f  mov     rbx, [rbx]
0x18000b022  cmp     rbx, [r13+18h]
0x18000b026  jnz     loc_18000B2F3
0x18000b02c  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x18000b033  mov     rcx, r15
0x18000b036  mov     rax, [rax+18h]
0x18000b03a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b03f  lea     rdi, [rax+18h]
0x18000b043  mov     [rsp+68h+arg_10], rdi
0x18000b04b  mov     rbx, [r13+28h]
0x18000b04f  mov     rbx, [rbx]
0x18000b052  cmp     rbx, [r13+28h]
0x18000b056  jnz     loc_18000B22F
0x18000b05c  mov     rax, [r13+10h]
0x18000b060  movsxd  rdx, dword ptr [rax-10h]
0x18000b064  mov     rax, [r13+8]
0x18000b068  movsxd  rcx, dword ptr [rax-10h]
0x18000b06c  add     rcx, 98h
0x18000b073  movsxd  rax, dword ptr [rdi-10h]
0x18000b077  add     rdx, rcx
0x18000b07a  movsxd  r14, dword ptr [rsi-10h]
0x18000b07e  add     rdx, rax
0x18000b081  add     r14, rdx
0x18000b084  lea     r15, [r14+r14]
0x18000b088  mov     rcx, r15; cb
0x18000b08b  call    cs:__imp_CoTaskMemAlloc
0x18000b091  mov     rbx, rax
0x18000b094  test    rax, rax
0x18000b097  jz      loc_18000B1D7
0x18000b09d  mov     r8, r15; Size
0x18000b0a0  xor     edx, edx; Val
0x18000b0a2  mov     rcx, rax; void *
0x18000b0a5  call    memset_0
0x18000b0aa  lea     r8, aDiagnosticstex; "<DiagnosticsText><Title><![CDATA["
0x18000b0b1  mov     rdx, r14; unsigned __int64
0x18000b0b4  mov     rcx, rbx; unsigned __int16 *
0x18000b0b7  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000b0bc  or      r11, 0FFFFFFFFFFFFFFFFh
0x18000b0c0  mov     rax, r11
0x18000b0c3  xor     r15d, r15d
0x18000b0c6  inc     rax
0x18000b0c9  cmp     [rbx+rax*2], r15w
0x18000b0ce  jnz     short loc_18000B0C6
0x18000b0d0  mov     rdx, r14
0x18000b0d3  sub     rdx, rax; unsigned __int64
0x18000b0d6  lea     rcx, [rbx+rax*2]; unsigned __int16 *
0x18000b0da  mov     r8, [r13+8]; unsigned __int16 *
0x18000b0de  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000b0e3  mov     rax, r11
0x18000b0e6  inc     rax
0x18000b0e9  cmp     [rbx+rax*2], r15w
0x18000b0ee  jnz     short loc_18000B0E6
0x18000b0f0  mov     rdx, r14
0x18000b0f3  sub     rdx, rax; unsigned __int64
0x18000b0f6  lea     rcx, [rbx+rax*2]; unsigned __int16 *
0x18000b0fa  lea     r8, aTitleDescripti; "]]></Title><Description><![CDATA["
0x18000b101  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000b106  mov     rax, r11
0x18000b109  inc     rax
0x18000b10c  cmp     [rbx+rax*2], r15w
0x18000b111  jnz     short loc_18000B109
0x18000b113  mov     rdx, r14
0x18000b116  sub     rdx, rax; unsigned __int64
0x18000b119  lea     rcx, [rbx+rax*2]; unsigned __int16 *
0x18000b11d  mov     r8, [r13+10h]; unsigned __int16 *
0x18000b121  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000b126  mov     rax, r11
0x18000b129  inc     rax
0x18000b12c  cmp     [rbx+rax*2], r15w
0x18000b131  jnz     short loc_18000B129
0x18000b133  mov     rdx, r14
0x18000b136  sub     rdx, rax; unsigned __int64
0x18000b139  lea     rcx, [rbx+rax*2]; unsigned __int16 *
0x18000b13d  lea     r8, aDescriptionPar; "]]></Description><Parameters>"
0x18000b144  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000b149  mov     rax, r11
0x18000b14c  inc     rax
0x18000b14f  cmp     [rbx+rax*2], r15w
0x18000b154  jnz     short loc_18000B14C
0x18000b156  mov     rdx, r14
0x18000b159  sub     rdx, rax; unsigned __int64
0x18000b15c  lea     rcx, [rbx+rax*2]; unsigned __int16 *
0x18000b160  mov     r8, rsi; unsigned __int16 *
0x18000b163  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000b168  mov     rax, r11
0x18000b16b  inc     rax
0x18000b16e  cmp     [rbx+rax*2], r15w
0x18000b173  jnz     short loc_18000B16B
0x18000b175  mov     rdx, r14
0x18000b178  sub     rdx, rax; unsigned __int64
0x18000b17b  lea     rcx, [rbx+rax*2]; unsigned __int16 *
0x18000b17f  lea     r8, aParametersExte; "</Parameters><Extensions>"
0x18000b186  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000b18b  mov     rax, r11
0x18000b18e  inc     rax
0x18000b191  cmp     [rbx+rax*2], r15w
0x18000b196  jnz     short loc_18000B18E
0x18000b198  mov     rdx, r14
0x18000b19b  sub     rdx, rax; unsigned __int64
0x18000b19e  lea     rcx, [rbx+rax*2]; unsigned __int16 *
0x18000b1a2  mov     r8, rdi; unsigned __int16 *
0x18000b1a5  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000b1aa  mov     rax, r11
0x18000b1ad  inc     rax
0x18000b1b0  cmp     [rbx+rax*2], r15w
0x18000b1b5  jnz     short loc_18000B1AD
0x18000b1b7  sub     r14, rax
0x18000b1ba  lea     rcx, [rbx+rax*2]; unsigned __int16 *
0x18000b1be  lea     r8, aExtensionsDiag; "</Extensions></DiagnosticsText>"
0x18000b1c5  mov     rdx, r14; unsigned __int64
0x18000b1c8  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000b1cd  mov     r10, [rsp+68h+arg_8]
0x18000b1d2  mov     [r10], rbx
0x18000b1d5  jmp     short loc_18000B1E1
0x18000b1d7  mov     r12d, 8007000Eh
0x18000b1dd  or      r11, 0FFFFFFFFFFFFFFFFh
0x18000b1e1  lea     rdx, [rdi-18h]
0x18000b1e5  mov     eax, r11d
0x18000b1e8  lock xadd [rdx+10h], eax
0x18000b1ed  add     eax, r11d
0x18000b1f0  test    eax, eax
0x18000b1f2  jg      short loc_18000B207
0x18000b1f4  mov     rcx, [rdx]
0x18000b1f7  mov     rax, [rcx]
0x18000b1fa  mov     rax, [rax+8]
0x18000b1fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b203  or      r11, 0FFFFFFFFFFFFFFFFh
0x18000b207  lea     rdx, [rsi-18h]
0x18000b20b  mov     eax, r11d
0x18000b20e  lock xadd [rdx+10h], eax
0x18000b213  add     eax, r11d
0x18000b216  test    eax, eax
0x18000b218  jg      short loc_18000B22A
0x18000b21a  mov     rcx, [rdx]
0x18000b21d  mov     rax, [rcx]
0x18000b220  mov     rax, [rax+8]
0x18000b224  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b229  nop
0x18000b22a  jmp     loc_18000B3C8
0x18000b22f  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x18000b236  mov     rcx, r15
0x18000b239  mov     rax, [rax+18h]
0x18000b23d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b242  add     rax, 18h
0x18000b246  mov     [rsp+68h+var_48], rax
0x18000b24b  mov     r9, [rbx+28h]
0x18000b24f  mov     r8, [rbx+20h]
0x18000b253  lea     rdx, aExtensionNameC; "<Extension><Name><![CDATA[%s]]></Name><"...
0x18000b25a  lea     rcx, [rsp+68h+var_48]
0x18000b25f  call    ?Format@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Format(ushort const *,...)
0x18000b264  mov     rdi, [rsp+68h+var_48]
0x18000b269  mov     r8d, [rdi-10h]
0x18000b26d  mov     rdx, rdi
0x18000b270  lea     rcx, [rsp+68h+arg_10]
0x18000b278  call    ?Append@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::Append(ushort const *,int)
0x18000b27d  nop
0x18000b27e  lea     rdx, [rdi-18h]
0x18000b282  or      eax, 0FFFFFFFFh
0x18000b285  lock xadd [rdx+10h], eax
0x18000b28a  sub     eax, 1
0x18000b28d  jg      short loc_18000B29E
0x18000b28f  mov     rcx, [rdx]
0x18000b292  mov     rax, [rcx]
0x18000b295  mov     rax, [rax+8]
0x18000b299  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b29e  cmp     [rbx+19h], r14b
0x18000b2a2  jnz     short loc_18000B2CB
0x18000b2a4  mov     rax, [rbx+10h]
0x18000b2a8  cmp     [rax+19h], r14b
0x18000b2ac  jnz     short loc_18000B2D8
0x18000b2ae  mov     rcx, [rax]
0x18000b2b1  cmp     [rcx+19h], r14b
0x18000b2b5  jnz     short loc_18000B2C8
0x18000b2b7  mov     rbx, rcx
0x18000b2ba  mov     rax, [rcx]
0x18000b2bd  mov     rcx, rax
0x18000b2c0  cmp     [rax+19h], r14b
0x18000b2c4  jz      short loc_18000B2B7
0x18000b2c6  jmp     short loc_18000B2CB
0x18000b2c8  mov     rbx, rax
0x18000b2cb  mov     rdi, [rsp+68h+arg_10]
0x18000b2d3  jmp     loc_18000B052
0x18000b2d8  mov     rax, [rbx+8]
0x18000b2dc  jmp     short loc_18000B2EB
0x18000b2de  cmp     rbx, [rax+10h]
0x18000b2e2  jnz     short loc_18000B2C8
0x18000b2e4  mov     rbx, rax
0x18000b2e7  mov     rax, [rax+8]
0x18000b2eb  cmp     [rax+19h], r14b
0x18000b2ef  jz      short loc_18000B2DE
0x18000b2f1  jmp     short loc_18000B2C8
0x18000b2f3  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x18000b2fa  mov     rcx, r15
0x18000b2fd  mov     rax, [rax+18h]
0x18000b301  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b306  add     rax, 18h
0x18000b30a  mov     [rsp+68h+arg_10], rax
0x18000b312  mov     r9, [rbx+28h]
0x18000b316  mov     r8, [rbx+20h]
0x18000b31a  lea     rdx, aParameterNameC; "<Parameter><Name><![CDATA[%s]]></Name><"...
0x18000b321  lea     rcx, [rsp+68h+arg_10]
0x18000b329  call    ?Format@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Format(ushort const *,...)
0x18000b32e  mov     rdi, [rsp+68h+arg_10]
0x18000b336  mov     r8d, [rdi-10h]
0x18000b33a  mov     rdx, rdi
0x18000b33d  lea     rcx, [rsp+68h+arg_18]
0x18000b345  call    ?Append@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::Append(ushort const *,int)
0x18000b34a  nop
0x18000b34b  lea     rdx, [rdi-18h]
0x18000b34f  or      eax, 0FFFFFFFFh
0x18000b352  lock xadd [rdx+10h], eax
0x18000b357  sub     eax, 1
0x18000b35a  jg      short loc_18000B36B
0x18000b35c  mov     rcx, [rdx]
0x18000b35f  mov     rax, [rcx]
0x18000b362  mov     rax, [rax+8]
0x18000b366  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b36b  cmp     [rbx+19h], r14b
0x18000b36f  jnz     short loc_18000B398
0x18000b371  mov     rax, [rbx+10h]
0x18000b375  cmp     [rax+19h], r14b
0x18000b379  jnz     short loc_18000B3A5
0x18000b37b  mov     rcx, [rax]
0x18000b37e  cmp     [rcx+19h], r14b
0x18000b382  jnz     short loc_18000B395
0x18000b384  mov     rbx, rcx
0x18000b387  mov     rax, [rcx]
0x18000b38a  mov     rcx, rax
0x18000b38d  cmp     [rax+19h], r14b
0x18000b391  jz      short loc_18000B384
0x18000b393  jmp     short loc_18000B398
0x18000b395  mov     rbx, rax
0x18000b398  mov     rsi, [rsp+68h+arg_18]
0x18000b3a0  jmp     loc_18000B022
0x18000b3a5  mov     rax, [rbx+8]
0x18000b3a9  jmp     short loc_18000B3B8
0x18000b3ab  cmp     rbx, [rax+10h]
0x18000b3af  jnz     short loc_18000B395
0x18000b3b1  mov     rbx, rax
0x18000b3b4  mov     rax, [rax+8]
0x18000b3b8  cmp     [rax+19h], r14b
0x18000b3bc  jz      short loc_18000B3AB
0x18000b3be  jmp     short loc_18000B395
0x18000b3c0  mov     r12d, dword ptr [rsp+68h+arg_10]
0x18000b3c8  mov     eax, r12d
0x18000b3cb  add     rsp, 30h
0x18000b3cf  pop     r15
0x18000b3d1  pop     r14
0x18000b3d3  pop     r13
0x18000b3d5  pop     r12
0x18000b3d7  pop     rdi
0x18000b3d8  pop     rsi
0x18000b3d9  pop     rbx
0x18000b3da  retn
```
