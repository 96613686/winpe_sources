# GenADTG::SaveResultRow(unsigned __int64,ADTGTOKENTYPEENUM,uchar *)

- ea: `0x1800089a8`
- end: `0x180008c08`
- name: `?SaveResultRow@GenADTG@@QEAAX_KW4ADTGTOKENTYPEENUM@@PEAE@Z`
- size: `608`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `service_task, installer_update`

## callers

- `0x180008c10`

## callees

- `0x18000266c`
- `0x180003abc`
- `0x1800041f8`
- `0x1800064d8`
- `0x1800076d4`
- `0x1800089a8`
- `0x180008f3c`
- `0x180009490`
- `0x180009654`
- `0x18001a6c8`
- `0x18002cd54`
- `0x180030010`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x180008be9`
- `ole32!CoTaskMemFree` at `0x180008be9`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall GenADTG::SaveResultRow(__int64 a1, __int64 a2, unsigned int a3, __int64 a4)
{
  __int64 v7; // rdx
  __int64 v8; // r8
  __int64 v9; // rbx
  int v10; // eax
  int v11; // ebx
  unsigned int v12; // r14d
  unsigned __int16 i; // bx
  __int64 v14; // r8
  __int64 v15; // r15
  unsigned __int16 v16; // dx
  unsigned __int16 Type; // ax
  __int64 v18; // r8
  __int64 v19; // r11
  __int16 v20; // r10
  unsigned int v21; // ecx
  int v22; // eax
  unsigned int v23; // edx
  LPVOID pv; // [rsp+30h] [rbp-20h] BYREF
  __int64 v25; // [rsp+38h] [rbp-18h] BYREF
  __int64 v26; // [rsp+40h] [rbp-10h] BYREF
  unsigned __int64 v27; // [rsp+48h] [rbp-8h] BYREF
  unsigned int v28; // [rsp+90h] [rbp+40h] BYREF

  v28 = a3;
  v27 = 0;
  v26 = 0;
  pv = 0;
  v25 = 0;
  GenADTG::SaveToBuffer((GenADTG *)a1, (const unsigned __int8 *)&v28, 1u);
  v8 = v28;
  if ( (v28 & 0x80u) != 0 )
  {
    GenADTG::SaveToBuffer((GenADTG *)a1, (const unsigned __int8 *)(a1 + 284), 4u);
    v8 = v28;
  }
  LODWORD(v8) = v8 & 0xFFFFFF7F;
  v28 = v8;
  if ( (_DWORD)v8 != 12 )
  {
    if ( (_DWORD)v8 == 10 || (_DWORD)v8 == 13 )
    {
      v25 = 0;
      if ( !*(_QWORD *)(a1 + 48) )
      {
        (***(void (__fastcall ****)(_QWORD, GUID *, __int64))(a1 + 24))(*(_QWORD *)(a1 + 24), &IID_IUpdateInfo, a1 + 48);
        v8 = v28;
      }
      v9 = *(_QWORD *)(a1 + 48);
      if ( v9 )
      {
        v25 = *(_QWORD *)(a1 + 48);
        (*(void (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v9 + 8LL))(v9, v7, v8);
        v10 = (*(__int64 (__fastcall **)(__int64, __int64, __int64 *, LPVOID *))(*(_QWORD *)v9 + 24LL))(
                v9,
                a2,
                &v26,
                &pv);
        v11 = v10;
        if ( v10 < 0 )
        {
          if ( (bidGblFlags & 2) != 0 )
          {
            if ( off_180048550[0] )
              bidTraceW(off_1800481C0[0], 1902592, off_180048550[0], (unsigned int)v10, 1858);
          }
          ThrowHR(v11);
        }
        v8 = v28;
      }
    }
    GenADTG::SaveRowMaps(a1, v7, v8, a4, v26, pv);
    v12 = 0;
    for ( i = 0; i < *(_WORD *)(a1 + 64); ++i )
    {
      if ( (unsigned int)GenADTG::FShouldSave(a1, v28, i, v26, pv) )
        GenADTG::SaveColumnData(a1, i, v14, &v27, a4);
      v15 = *(_QWORD *)(a1 + 56);
      CMetaData::mdGetFlags((CMetaData *)(a1 + 128), *(_WORD *)(88LL * i + v15) - 1);
      Type = CMetaData::mdGetType((CMetaData *)(a1 + 128), v16);
      if ( (v20 & 0x2000) != 0 || Type == 136 )
      {
        v21 = *(_DWORD *)(*(unsigned int *)(v19 + v15 + 24) + a4);
        if ( v21 <= 0xD )
        {
          v22 = 8209;
          if ( _bittest(&v22, v21) )
          {
            GenADTG::SaveColumnData(a1, i, v18, &v27, a4);
            v23 = v12++;
            GenADTG::SetChildHChapter((GenADTG *)a1, v23, v27);
          }
        }
      }
    }
  }
  CAutoRefc<IWinInetHttpInfo>::~CAutoRefc<IWinInetHttpInfo>(&v25);
  CoTaskMemFree(pv);
}

```

## disassembly

```asm
0x1800089a8  mov     [rsp-28h+arg_0], rbx
0x1800089ad  mov     [rsp-28h+arg_8], rsi
0x1800089b2  mov     [rsp-28h+arg_10], r8d
0x1800089b7  push    rbp
0x1800089b8  push    rdi
0x1800089b9  push    r12
0x1800089bb  push    r14
0x1800089bd  push    r15
0x1800089bf  mov     rbp, rsp
0x1800089c2  sub     rsp, 50h
0x1800089c6  mov     rsi, r9
0x1800089c9  mov     r14, rdx
0x1800089cc  mov     rdi, rcx
0x1800089cf  mov     [rbp+var_8], 0
0x1800089d7  mov     [rbp+var_10], 0
0x1800089df  mov     [rbp+pv], 0
0x1800089e7  mov     [rbp+var_18], 0
0x1800089ef  mov     r8d, 1; unsigned int
0x1800089f5  lea     rdx, [rbp+arg_10]; unsigned __int8 *
0x1800089f9  call    ?SaveToBuffer@GenADTG@@AEAAXPEBEK@Z; GenADTG::SaveToBuffer(uchar const *,ulong)
0x1800089fe  mov     r8d, [rbp+arg_10]
0x180008a02  test    r8b, r8b
0x180008a05  jns     short loc_180008A20
0x180008a07  lea     rdx, [rdi+11Ch]; unsigned __int8 *
0x180008a0e  mov     r8d, 4; unsigned int
0x180008a14  mov     rcx, rdi; this
0x180008a17  call    ?SaveToBuffer@GenADTG@@AEAAXPEBEK@Z; GenADTG::SaveToBuffer(uchar const *,ulong)
0x180008a1c  mov     r8d, [rbp+arg_10]
0x180008a20  btr     r8d, 7
0x180008a25  mov     [rbp+arg_10], r8d
0x180008a29  cmp     r8d, 0Ch
0x180008a2d  jz      loc_180008BDB
0x180008a33  cmp     r8d, 0Ah
0x180008a37  jz      short loc_180008A43
0x180008a39  cmp     r8d, 0Dh
0x180008a3d  jnz     loc_180008AF1
0x180008a43  mov     [rbp+var_18], 0
0x180008a4b  lea     rbx, [rdi+30h]
0x180008a4f  cmp     qword ptr [rbx], 0
0x180008a53  jnz     short loc_180008A72
0x180008a55  mov     rcx, [rdi+18h]
0x180008a59  mov     rax, [rcx]
0x180008a5c  mov     r8, rbx
0x180008a5f  lea     rdx, ?IID_IUpdateInfo@@3U_GUID@@B; _GUID const IID_IUpdateInfo
0x180008a66  mov     rax, [rax]
0x180008a69  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008a6e  mov     r8d, [rbp+arg_10]
0x180008a72  mov     rbx, [rbx]
0x180008a75  test    rbx, rbx
0x180008a78  jz      short loc_180008AF1
0x180008a7a  mov     [rbp+var_18], rbx
0x180008a7e  mov     rax, [rbx]
0x180008a81  mov     rcx, rbx
0x180008a84  mov     rax, [rax+8]
0x180008a88  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008a8d  mov     rax, [rbx]
0x180008a90  lea     r9, [rbp+pv]
0x180008a94  lea     r8, [rbp+var_10]
0x180008a98  mov     rdx, r14
0x180008a9b  mov     rcx, rbx
0x180008a9e  mov     rax, [rax+18h]
0x180008aa2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008aa7  mov     ebx, eax
0x180008aa9  test    eax, eax
0x180008aab  jns     short loc_180008AED
0x180008aad  test    byte ptr cs:_bidGblFlags, 2
0x180008ab4  jz      short loc_180008AE5
0x180008ab6  mov     rcx, cs:off_180048550; "<GenADTG::SaveResultRow|ADO|ERR>  HRESU"...
0x180008abd  test    rcx, rcx
0x180008ac0  jz      short loc_180008AE5
0x180008ac2  mov     dword ptr [rsp+50h+var_30], 742h
0x180008aca  mov     r9d, eax
0x180008acd  mov     r8, cs:off_180048550; "<GenADTG::SaveResultRow|ADO|ERR>  HRESU"...
0x180008ad4  mov     edx, 1D0800h
0x180008ad9  mov     rcx, cs:off_1800481C0; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x180008ae0  call    _bidTraceW
0x180008ae5  mov     ecx, ebx; int
0x180008ae7  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
0x180008aed  mov     r8d, [rbp+arg_10]
0x180008af1  mov     rax, [rbp+pv]
0x180008af5  mov     [rsp+50h+var_28], rax
0x180008afa  mov     rax, [rbp+var_10]
0x180008afe  mov     [rsp+50h+var_30], rax
0x180008b03  mov     r9, rsi
0x180008b06  mov     rcx, rdi
0x180008b09  call    ?SaveRowMaps@GenADTG@@AEAAX_KW4ADTGTOKENTYPEENUM@@PEAE0PEA_K@Z; GenADTG::SaveRowMaps(unsigned __int64,ADTGTOKENTYPEENUM,uchar *,unsigned __int64,unsigned __int64 *)
0x180008b0e  xor     r14d, r14d
0x180008b11  xor     ebx, ebx
0x180008b13  xor     eax, eax
0x180008b15  cmp     ax, [rdi+40h]
0x180008b19  jnb     loc_180008BDB
0x180008b1f  lea     r12, [rdi+80h]
0x180008b26  movzx   r8d, bx
0x180008b2a  mov     rax, [rbp+pv]
0x180008b2e  mov     [rsp+50h+var_30], rax
0x180008b33  mov     r9, [rbp+var_10]
0x180008b37  mov     edx, [rbp+arg_10]
0x180008b3a  mov     rcx, rdi
0x180008b3d  call    ?FShouldSave@GenADTG@@AEAAHW4ADTGTOKENTYPEENUM@@K_KPEA_K@Z; GenADTG::FShouldSave(ADTGTOKENTYPEENUM,ulong,unsigned __int64,unsigned __int64 *)
0x180008b42  test    eax, eax
0x180008b44  jz      short loc_180008B5A
0x180008b46  mov     [rsp+50h+var_30], rsi
0x180008b4b  lea     r9, [rbp+var_8]
0x180008b4f  movzx   edx, bx
0x180008b52  mov     rcx, rdi
0x180008b55  call    ?SaveColumnData@GenADTG@@AEAAXGW4ADTGTOKENTYPEENUM@@PEA_KPEAE@Z; GenADTG::SaveColumnData(ushort,ADTGTOKENTYPEENUM,unsigned __int64 *,uchar *)
0x180008b5a  movzx   eax, bx
0x180008b5d  imul    r11, rax, 58h ; 'X'
0x180008b61  mov     r15, [rdi+38h]
0x180008b65  movzx   edx, word ptr [r11+r15]
0x180008b6a  dec     dx; unsigned __int16
0x180008b6d  mov     rcx, r12; this
0x180008b70  call    ?mdGetFlags@CMetaData@@QEAAKG@Z; CMetaData::mdGetFlags(ushort)
0x180008b75  mov     r10d, eax
0x180008b78  mov     rcx, r12; this
0x180008b7b  call    ?mdGetType@CMetaData@@QEAAGG@Z; CMetaData::mdGetType(ushort)
0x180008b80  bt      r10d, 0Dh
0x180008b85  jb      short loc_180008B91
0x180008b87  mov     ecx, 88h
0x180008b8c  cmp     ax, cx
0x180008b8f  jnz     short loc_180008BCE
0x180008b91  mov     eax, [r11+r15+18h]
0x180008b96  mov     ecx, [rax+rsi]
0x180008b99  cmp     ecx, 0Dh
0x180008b9c  ja      short loc_180008BCE
0x180008b9e  mov     eax, 2011h
0x180008ba3  bt      eax, ecx
0x180008ba6  jnb     short loc_180008BCE
0x180008ba8  mov     [rsp+50h+var_30], rsi
0x180008bad  lea     r9, [rbp+var_8]
0x180008bb1  movzx   edx, bx
0x180008bb4  mov     rcx, rdi
0x180008bb7  call    ?SaveColumnData@GenADTG@@AEAAXGW4ADTGTOKENTYPEENUM@@PEA_KPEAE@Z; GenADTG::SaveColumnData(ushort,ADTGTOKENTYPEENUM,unsigned __int64 *,uchar *)
0x180008bbc  mov     edx, r14d; unsigned int
0x180008bbf  inc     r14d
0x180008bc2  mov     r8, [rbp+var_8]; unsigned __int64
0x180008bc6  mov     rcx, rdi; this
0x180008bc9  call    ?SetChildHChapter@GenADTG@@AEAAXK_K@Z; GenADTG::SetChildHChapter(ulong,unsigned __int64)
0x180008bce  inc     bx
0x180008bd1  cmp     bx, [rdi+40h]
0x180008bd5  jb      loc_180008B26
0x180008bdb  lea     rcx, [rbp+var_18]
0x180008bdf  call    ??1?$CAutoRefc@UIWinInetHttpInfo@@@@QEAA@XZ; CAutoRefc<IWinInetHttpInfo>::~CAutoRefc<IWinInetHttpInfo>(void)
0x180008be4  nop
0x180008be5  mov     rcx, [rbp+pv]; pv
0x180008be9  call    cs:__imp_CoTaskMemFree
0x180008bef  lea     r11, [rsp+50h+var_s0]
0x180008bf4  mov     rbx, [r11+30h]
0x180008bf8  mov     rsi, [r11+38h]
0x180008bfc  mov     rsp, r11
0x180008bff  pop     r15
0x180008c01  pop     r14
0x180008c03  pop     r12
0x180008c05  pop     rdi
0x180008c06  pop     rbp
0x180008c07  retn
```
