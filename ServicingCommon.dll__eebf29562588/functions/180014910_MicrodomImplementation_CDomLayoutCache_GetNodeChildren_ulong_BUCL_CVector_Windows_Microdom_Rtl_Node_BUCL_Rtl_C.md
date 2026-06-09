# MicrodomImplementation::CDomLayoutCache::GetNodeChildren(ulong,BUCL::CVector<Windows::Microdom::Rtl::Node,BUCL::Rtl::CCallDisposition> *,unsigned __int64 *,unsigned __int64 *)

- ea: `0x180014910`
- end: `0x180014b51`
- name: `?GetNodeChildren@CDomLayoutCache@MicrodomImplementation@@QEAAJKPEAV?$CVector@UNode@Rtl@Microdom@Windows@@VCCallDisposition@2BUCL@@@BUCL@@PEA_K1@Z`
- size: `577`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x1800134d0`

## callees

- `0x1800031e0`
- `0x18000e780`
- `0x18000e8d8`
- `0x180012790`
- `0x180014910`
- `0x18001fd10`
- `0x180022f08`
- `0x1800a0020`

## string_xrefs

- `0x1800149ab`: `onecore\base\xml\udom_microdom.cpp`
- `0x180014a21`: `onecore\base\xml\udom_microdom.cpp`
- `0x1800149c7`: `MicrodomImplementation::CDomLayoutCache::GetNodeChildren`
- `0x180014a3d`: `MicrodomImplementation::CDomLayoutCache::GetNodeChildren`
- `0x1800149de`: `BUCL::Rtl::Add(pCachedInfo->m_ulChildCount, pCachedInfo->m_ulAttributeCount, cNecessary)`

## pseudocode

```c
__int64 __fastcall MicrodomImplementation::CDomLayoutCache::GetNodeChildren(
        MicrodomImplementation::CDomLayoutCache *a1,
        unsigned int a2,
        __int64 a3,
        _QWORD *a4,
        _QWORD *a5)
{
  __int64 v8; // rbx
  __int64 result; // rax
  __int64 v10; // rbp
  unsigned int v11; // ecx
  __int64 v12; // rax
  unsigned int v13; // edx
  unsigned int v14; // edi
  int v15; // ebx
  unsigned int v16; // esi
  __int64 i; // r12
  int v18; // eax
  __int64 v19; // rbx
  int v20; // eax
  __int64 v21; // rbx
  void *v22; // rcx
  __int64 v23; // rax
  _QWORD *v24; // rdx
  __int128 v25; // [rsp+20h] [rbp-A8h] BYREF
  __int64 v26; // [rsp+30h] [rbp-98h]
  const char *v27; // [rsp+38h] [rbp-90h]
  _BYTE v28[8]; // [rsp+40h] [rbp-88h] BYREF
  _QWORD *v29; // [rsp+48h] [rbp-80h]
  _QWORD *v30; // [rsp+50h] [rbp-78h]
  _QWORD v31[6]; // [rsp+58h] [rbp-70h] BYREF

  v30 = a5;
  v29 = a4;
  v8 = a2;
  result = MicrodomImplementation::CDomLayoutCache::AdvanceCachedPointer(a1, a2);
  if ( (int)result >= 0 )
  {
    v10 = *(_QWORD *)a1 + 40 * v8;
    v11 = *(_DWORD *)(v10 + 16);
    if ( v11 || *(_DWORD *)(v10 + 20) )
    {
      v13 = v11 + *(_DWORD *)(v10 + 20);
      if ( v13 < v11 )
      {
        v26 = 3819;
        *(_QWORD *)&v25 = "onecore\\base\\xml\\udom_microdom.cpp";
        *((_QWORD *)&v25 + 1) = "MicrodomImplementation::CDomLayoutCache::GetNodeChildren";
        v27 = "BUCL::Rtl::Add(pCachedInfo->m_ulChildCount, pCachedInfo->m_ulAttributeCount, cNecessary)";
        RtlReportErrorOrigination(&v25, &GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab, 3221225621LL);
        return 3221225621LL;
      }
      v14 = 0;
      v26 = 0;
      v25 = 0;
      v15 = *(_DWORD *)BUCL::CVector<Windows::Microdom::Rtl::Node,BUCL::Rtl::CCallDisposition>::Resize(&v25, v28, v13);
      if ( v15 < 0 )
      {
        v31[2] = 3823;
        v31[0] = "onecore\\base\\xml\\udom_microdom.cpp";
        v31[1] = "MicrodomImplementation::CDomLayoutCache::GetNodeChildren";
        v31[3] = "TmpNodes.Resize(cNecessary)";
        RtlReportErrorOrigination(v31, &GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab, (unsigned int)v15);
        BUCL::CVector<Windows::Microdom::Rtl::Node,BUCL::Rtl::CCallDisposition>::Close(&v25);
        return (unsigned int)v15;
      }
      v16 = 0;
      for ( i = v25; v16 < *(_DWORD *)(v10 + 16); *(_DWORD *)(i + 8 * v19 + 8) = v18 )
      {
        v18 = (*((__int64 (__fastcall **)(_QWORD, _QWORD))a1 + 7))(*(_QWORD *)(v10 + 24), v16);
        v19 = 2LL * v16++;
      }
      if ( *(_DWORD *)(v10 + 20) )
      {
        do
        {
          v20 = (*((__int64 (__fastcall **)(_QWORD, _QWORD))a1 + 7))(*(_QWORD *)(v10 + 32), v14);
          v21 = 2LL * v16++;
          ++v14;
          *(_DWORD *)(i + 8 * v21 + 8) = v20;
        }
        while ( v14 < *(_DWORD *)(v10 + 20) );
      }
      if ( v16 != (*((_QWORD *)&v25 + 1) - i) >> 4 )
      {
        INTERNAL_ERROR_ACTION(-1073741595);
        JUMPOUT(0x180014B50LL);
      }
      v22 = *(void **)a3;
      v23 = v26;
      *(_QWORD *)(a3 + 8) = *((_QWORD *)&v25 + 1);
      v24 = v29;
      *(_QWORD *)a3 = i;
      *(_QWORD *)(a3 + 16) = v23;
      *v24 = *(unsigned int *)(v10 + 16);
      *v30 = *(unsigned int *)(v10 + 20);
      if ( v22 )
        operator delete(v22);
    }
    else
    {
      v12 = *(_QWORD *)(a3 + 8);
      if ( *(_QWORD *)a3 != v12 )
      {
        do
          v12 -= 16;
        while ( *(_QWORD *)a3 != v12 );
        *(_QWORD *)(a3 + 8) = v12;
      }
      *a4 = 0;
      *a5 = 0;
    }
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x180014910  push    rbx
0x180014912  push    rsi
0x180014913  push    r12
0x180014915  push    r13
0x180014917  push    r14
0x180014919  sub     rsp, 0A0h
0x180014920  mov     r12, [rsp+0C8h+arg_20]
0x180014928  mov     rsi, r9
0x18001492b  mov     [rsp+0C8h+var_78], r12
0x180014930  mov     r14, r8
0x180014933  mov     [rsp+0C8h+var_80], r9
0x180014938  mov     r13, rcx
0x18001493b  mov     ebx, edx
0x18001493d  call    ?AdvanceCachedPointer@CDomLayoutCache@MicrodomImplementation@@AEAAJK@Z; MicrodomImplementation::CDomLayoutCache::AdvanceCachedPointer(ulong)
0x180014942  test    eax, eax
0x180014944  js      loc_180014B35
0x18001494a  mov     rax, [r13+0]
0x18001494e  lea     rcx, [rbx+rbx*4]
0x180014952  mov     [rsp+0C8h+var_30], rbp
0x18001495a  mov     [rsp+0C8h+var_38], rdi
0x180014962  mov     [rsp+0C8h+var_40], r15
0x18001496a  lea     rbp, [rax+rcx*8]
0x18001496e  mov     ecx, [rax+rcx*8+10h]
0x180014972  test    ecx, ecx
0x180014974  jnz     short loc_1800149A2
0x180014976  cmp     [rbp+14h], ecx
0x180014979  ja      short loc_1800149A2
0x18001497b  mov     rcx, [r14]
0x18001497e  mov     rax, [r14+8]
0x180014982  cmp     rcx, rax
0x180014985  jz      short loc_180014994
0x180014987  add     rax, 0FFFFFFFFFFFFFFF0h
0x18001498b  cmp     rcx, rax
0x18001498e  jnz     short loc_180014987
0x180014990  mov     [r14+8], rax
0x180014994  xor     edi, edi
0x180014996  mov     [rsi], rdi
0x180014999  mov     [r12], rdi
0x18001499d  jmp     loc_180014B1B
0x1800149a2  mov     edx, [rbp+14h]
0x1800149a5  add     edx, ecx
0x1800149a7  cmp     edx, ecx
0x1800149a9  jnb     short loc_1800149F9
0x1800149ab  lea     rax, aOnecoreBaseXml_1; "onecore\\base\\xml\\udom_microdom.cpp"
0x1800149b2  mov     [rsp+0C8h+var_98], 0EEBh
0x1800149bb  mov     qword ptr [rsp+0C8h+var_A8], rax
0x1800149c0  lea     rdx, _GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab
0x1800149c7  lea     rax, aMicrodomimplem_45; "MicrodomImplementation::CDomLayoutCache"...
0x1800149ce  mov     r8d, 0C0000095h
0x1800149d4  mov     qword ptr [rsp+0C8h+var_A8+8], rax
0x1800149d9  lea     rcx, [rsp+0C8h+var_A8]
0x1800149de  lea     rax, aBuclRtlAddPcac; "BUCL::Rtl::Add(pCachedInfo->m_ulChildCo"...
0x1800149e5  mov     [rsp+0C8h+var_90], rax
0x1800149ea  call    RtlReportErrorOrigination
0x1800149ef  mov     eax, 0C0000095h
0x1800149f4  jmp     loc_180014B1D
0x1800149f9  xorps   xmm0, xmm0
0x1800149fc  mov     r8d, edx
0x1800149ff  xor     edi, edi
0x180014a01  lea     rdx, [rsp+0C8h+var_88]
0x180014a06  lea     rcx, [rsp+0C8h+var_A8]
0x180014a0b  mov     [rsp+0C8h+var_98], rdi
0x180014a10  movdqu  [rsp+0C8h+var_A8], xmm0
0x180014a16  call    ?Resize@?$CVector@UNode@Rtl@Microdom@Windows@@VCCallDisposition@2BUCL@@@BUCL@@QEAA?AVCCallDisposition@Rtl@2@_K@Z; BUCL::CVector<Windows::Microdom::Rtl::Node,BUCL::Rtl::CCallDisposition>::Resize(unsigned __int64)
0x180014a1b  mov     ebx, [rax]
0x180014a1d  test    ebx, ebx
0x180014a1f  jns     short loc_180014A73
0x180014a21  lea     rax, aOnecoreBaseXml_1; "onecore\\base\\xml\\udom_microdom.cpp"
0x180014a28  mov     [rsp+0C8h+var_60], 0EEFh
0x180014a31  mov     [rsp+0C8h+var_70], rax
0x180014a36  lea     rdx, _GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab
0x180014a3d  lea     rax, aMicrodomimplem_45; "MicrodomImplementation::CDomLayoutCache"...
0x180014a44  mov     r8d, ebx
0x180014a47  mov     [rsp+0C8h+var_68], rax
0x180014a4c  lea     rcx, [rsp+0C8h+var_70]
0x180014a51  lea     rax, aTmpnodesResize; "TmpNodes.Resize(cNecessary)"
0x180014a58  mov     [rsp+0C8h+var_58], rax
0x180014a5d  call    RtlReportErrorOrigination
0x180014a62  lea     rcx, [rsp+0C8h+var_A8]
0x180014a67  call    ?Close@?$CVector@UNode@Rtl@Microdom@Windows@@VCCallDisposition@2BUCL@@@BUCL@@QEAAXXZ; BUCL::CVector<Windows::Microdom::Rtl::Node,BUCL::Rtl::CCallDisposition>::Close(void)
0x180014a6c  mov     eax, ebx
0x180014a6e  jmp     loc_180014B1D
0x180014a73  mov     esi, edi
0x180014a75  mov     r12, qword ptr [rsp+0C8h+var_A8]
0x180014a7a  cmp     [rbp+10h], edi
0x180014a7d  jbe     short loc_180014AA0
0x180014a7f  nop
0x180014a80  mov     rcx, [rbp+18h]
0x180014a84  mov     edx, esi
0x180014a86  mov     rax, [r13+38h]
0x180014a8a  mov     ebx, esi
0x180014a8c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014a91  add     rbx, rbx
0x180014a94  inc     esi
0x180014a96  mov     [r12+rbx*8+8], eax
0x180014a9b  cmp     esi, [rbp+10h]
0x180014a9e  jb      short loc_180014A80
0x180014aa0  cmp     [rbp+14h], edi
0x180014aa3  jbe     short loc_180014AD2
0x180014aa5  nop     word ptr [rax+rax+00000000h]
0x180014ab0  mov     rcx, [rbp+20h]
0x180014ab4  mov     edx, edi
0x180014ab6  mov     rax, [r13+38h]
0x180014aba  mov     ebx, esi
0x180014abc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014ac1  add     rbx, rbx
0x180014ac4  inc     esi
0x180014ac6  inc     edi
0x180014ac8  mov     [r12+rbx*8+8], eax
0x180014acd  cmp     edi, [rbp+14h]
0x180014ad0  jb      short loc_180014AB0
0x180014ad2  mov     rdx, qword ptr [rsp+0C8h+var_A8+8]
0x180014ad7  mov     rax, rdx
0x180014ada  mov     ecx, esi
0x180014adc  sub     rax, r12
0x180014adf  sar     rax, 4
0x180014ae3  cmp     rcx, rax
0x180014ae6  jnz     short loc_180014B46
0x180014ae8  mov     rcx, [r14]; Block
0x180014aeb  mov     rax, [rsp+0C8h+var_98]
0x180014af0  mov     [r14+8], rdx
0x180014af4  mov     rdx, [rsp+0C8h+var_80]
0x180014af9  mov     [r14], r12
0x180014afc  mov     [r14+10h], rax
0x180014b00  mov     eax, [rbp+10h]
0x180014b03  mov     [rdx], rax
0x180014b06  mov     rdx, [rsp+0C8h+var_78]
0x180014b0b  mov     eax, [rbp+14h]
0x180014b0e  mov     [rdx], rax
0x180014b11  test    rcx, rcx
0x180014b14  jz      short loc_180014B1B
0x180014b16  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180014b1b  xor     eax, eax
0x180014b1d  mov     rdi, [rsp+0C8h+var_38]
0x180014b25  mov     rbp, [rsp+0C8h+var_30]
0x180014b2d  mov     r15, [rsp+0C8h+var_40]
0x180014b35  add     rsp, 0A0h
0x180014b3c  pop     r14
0x180014b3e  pop     r13
0x180014b40  pop     r12
0x180014b42  pop     rsi
0x180014b43  pop     rbx
0x180014b44  retn
0x180014b46  mov     ecx, 0C00000E5h; int
0x180014b4b  call    ?INTERNAL_ERROR_ACTION@@YAXJ@Z; INTERNAL_ERROR_ACTION(long)
```
