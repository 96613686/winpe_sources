# MicrodomImplementation::CDomLayoutCache::GetNodeChildren(ulong,BUCL::CVector<Windows::Microdom::Rtl::Node,BUCL::Rtl::CCallDisposition> *,unsigned __int64 *,unsigned __int64 *)

- ea: `0x1800057b0`
- end: `0x180005a88`
- name: `?GetNodeChildren@CDomLayoutCache@MicrodomImplementation@@QEAAJKPEAV?$CVector@UNode@Rtl@Microdom@Windows@@VCCallDisposition@2BUCL@@@BUCL@@PEA_K1@Z`
- size: `728`
- prototype: ``
- caller_count: `5`
- callee_count: `8`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180004b18`
- `0x180004c00`
- `0x180004f44`
- `0x180005300`
- `0x180006304`

## callees

- `0x1800057b0`
- `0x180006a40`
- `0x180018aa8`
- `0x18001f840`
- `0x180026dc0`
- `0x180026e18`
- `0x18002d2b0`
- `0x18009e020`

## import_xrefs

- `ntdll!RtlRaiseStatus` at `0x180005a71`
- `ntdll!RtlRaiseStatus` at `0x180005a71`

## string_xrefs

- `0x180005952`: `onecore\base\xml\udom_microdom.cpp`
- `0x180005a14`: `onecore\base\xml\udom_microdom.cpp`
- `0x18000596c`: `MicrodomImplementation::CDomLayoutCache::GetNodeChildren`
- `0x180005a2e`: `MicrodomImplementation::CDomLayoutCache::GetNodeChildren`
- `0x180005986`: `BUCL::Rtl::Add(pCachedInfo->m_ulChildCount, pCachedInfo->m_ulAttributeCount, cNecessary)`

## pseudocode

```c
__int64 __fastcall MicrodomImplementation::CDomLayoutCache::GetNodeChildren(
        MicrodomImplementation::CDomLayoutCache *a1,
        unsigned int a2,
        __int64 a3,
        _QWORD *a4,
        _QWORD *a5)
{
  __int64 v6; // r12
  __int64 v8; // rbx
  __int64 result; // rax
  __int64 v10; // rbp
  unsigned int v11; // ecx
  unsigned int v12; // edx
  __int64 v13; // rbx
  char *v14; // rsi
  char *v15; // r15
  unsigned int v16; // ebx
  int v17; // eax
  __int64 v18; // rdi
  bool v19; // zf
  unsigned int v20; // r12d
  int v21; // eax
  __int64 v22; // rdi
  void *v23; // rcx
  _QWORD *v24; // rdx
  size_t v25; // rdi
  char *v26; // rax
  __int64 v27; // rax
  unsigned int v28; // ebx
  char *v29; // [rsp+20h] [rbp-B8h]
  __int128 v30; // [rsp+28h] [rbp-B0h] BYREF
  __int64 v31; // [rsp+38h] [rbp-A0h]
  const char *v32; // [rsp+40h] [rbp-98h]
  __int64 v33; // [rsp+48h] [rbp-90h]
  _QWORD *v34; // [rsp+50h] [rbp-88h]
  _QWORD *v35; // [rsp+58h] [rbp-80h]
  _QWORD v36[4]; // [rsp+60h] [rbp-78h] BYREF
  unsigned int v37; // [rsp+80h] [rbp-58h] BYREF

  v35 = a5;
  v37 = 0;
  v6 = a3;
  v34 = a4;
  v33 = a3;
  v8 = a2;
  result = MicrodomImplementation::CDomLayoutCache::AdvanceCachedPointer(a1, a2);
  if ( (int)result >= 0 )
  {
    v10 = *(_QWORD *)a1 + 40 * v8;
    v11 = *(_DWORD *)(v10 + 16);
    if ( v11 || *(_DWORD *)(v10 + 20) )
    {
      v12 = v11 + *(_DWORD *)(v10 + 20);
      if ( v12 < v11 )
      {
        v31 = 3819;
        *(_QWORD *)&v30 = "onecore\\base\\xml\\udom_microdom.cpp";
        *((_QWORD *)&v30 + 1) = "MicrodomImplementation::CDomLayoutCache::GetNodeChildren";
        v32 = "BUCL::Rtl::Add(pCachedInfo->m_ulChildCount, pCachedInfo->m_ulAttributeCount, cNecessary)";
        return Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateNtStatus(
                 &v37,
                 &v30,
                 3221225621LL);
      }
      v29 = 0;
      v31 = 0;
      v13 = v12;
      v30 = 0;
      if ( v12 )
      {
        v25 = 16LL * v12;
        v26 = (char *)operator new(v25);
        v15 = v26;
        if ( !v26 )
        {
          v36[2] = 3823;
          v36[0] = "onecore\\base\\xml\\udom_microdom.cpp";
          v36[1] = "MicrodomImplementation::CDomLayoutCache::GetNodeChildren";
          v36[3] = "TmpNodes.Resize(cNecessary)";
          v28 = Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateNtStatus(
                  &v37,
                  v36,
                  3221225495LL);
          BUCL::CVector<Windows::Microdom::Rtl::Node,BUCL::Rtl::CCallDisposition>::Close(&v30);
          return v28;
        }
        v14 = v26;
        v29 = &v26[v25];
        do
        {
          if ( v14 )
            *(_OWORD *)v14 = 0;
          v14 += 16;
        }
        while ( v13 != (v14 - v26) >> 4 );
        v11 = *(_DWORD *)(v10 + 16);
      }
      else
      {
        v14 = (char *)*((_QWORD *)&v30 + 1);
        v15 = (char *)v30;
      }
      v16 = 0;
      if ( v11 )
      {
        do
        {
          v17 = (*((__int64 (__fastcall **)(_QWORD, _QWORD))a1 + 7))(*(_QWORD *)(v10 + 24), v16);
          v18 = 2LL * v16++;
          *(_DWORD *)&v15[8 * v18 + 8] = v17;
        }
        while ( v16 < *(_DWORD *)(v10 + 16) );
      }
      v19 = *(_DWORD *)(v10 + 20) == 0;
      v37 = 0;
      if ( !v19 )
      {
        v20 = v37;
        do
        {
          v21 = (*((__int64 (__fastcall **)(_QWORD, _QWORD))a1 + 7))(*(_QWORD *)(v10 + 32), v20);
          v22 = 2LL * v16++;
          ++v20;
          *(_DWORD *)&v15[8 * v22 + 8] = v21;
        }
        while ( v20 < *(_DWORD *)(v10 + 20) );
        v6 = v33;
      }
      if ( v16 != (v14 - v15) >> 4 )
        RtlRaiseStatus(-1073741595);
      v23 = *(void **)v6;
      v24 = v34;
      *(_QWORD *)v6 = v15;
      *(_QWORD *)(v6 + 8) = v14;
      *(_QWORD *)(v6 + 16) = v29;
      *v24 = *(unsigned int *)(v10 + 16);
      *v35 = *(unsigned int *)(v10 + 20);
      if ( v23 )
        operator delete(v23);
    }
    else
    {
      v27 = *(_QWORD *)(v6 + 8);
      if ( *(_QWORD *)v6 != v27 )
      {
        do
          v27 -= 16;
        while ( *(_QWORD *)v6 != v27 );
        *(_QWORD *)(v6 + 8) = v27;
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
0x1800057b0  push    rbx
0x1800057b2  push    rsi
0x1800057b3  push    rdi
0x1800057b4  push    r12
0x1800057b6  push    r13
0x1800057b8  push    r15
0x1800057ba  sub     rsp, 0A8h
0x1800057c1  mov     rax, cs:__security_cookie
0x1800057c8  xor     rax, rsp
0x1800057cb  mov     [rsp+0D8h+var_50], rax
0x1800057d3  mov     rsi, [rsp+0D8h+arg_20]
0x1800057db  xor     r15d, r15d
0x1800057de  mov     [rsp+0D8h+var_80], rsi
0x1800057e3  mov     rdi, r9
0x1800057e6  mov     [rsp+0D8h+var_58], r15d
0x1800057ee  mov     r12, r8
0x1800057f1  mov     [rsp+0D8h+var_88], r9
0x1800057f6  mov     r13, rcx
0x1800057f9  mov     [rsp+0D8h+var_90], r8
0x1800057fe  mov     ebx, edx
0x180005800  call    ?AdvanceCachedPointer@CDomLayoutCache@MicrodomImplementation@@AEAAJK@Z; MicrodomImplementation::CDomLayoutCache::AdvanceCachedPointer(ulong)
0x180005805  test    eax, eax
0x180005807  js      loc_180005930
0x18000580d  mov     rax, [r13+0]
0x180005811  lea     rcx, [rbx+rbx*4]
0x180005815  mov     [rsp+0D8h+var_38], rbp
0x18000581d  mov     [rsp+0D8h+var_40], r14
0x180005825  lea     rbp, [rax+rcx*8]
0x180005829  mov     ecx, [rax+rcx*8+10h]
0x18000582d  test    ecx, ecx
0x18000582f  jz      loc_180005A08
0x180005835  mov     edx, [rbp+14h]
0x180005838  add     edx, ecx
0x18000583a  cmp     edx, ecx
0x18000583c  jb      loc_180005952
0x180005842  mov     [rsp+0D8h+var_B8], r15
0x180005847  xorps   xmm0, xmm0
0x18000584a  mov     [rsp+0D8h+var_A0], r15
0x18000584f  mov     ebx, edx
0x180005851  movdqu  [rsp+0D8h+var_B0], xmm0
0x180005857  test    edx, edx
0x180005859  jnz     loc_180005999
0x18000585f  mov     rsi, qword ptr [rsp+0D8h+var_B0+8]
0x180005864  mov     r15, qword ptr [rsp+0D8h+var_B0]
0x180005869  xor     ebx, ebx
0x18000586b  test    ecx, ecx
0x18000586d  jz      short loc_180005890
0x18000586f  nop
0x180005870  mov     rcx, [rbp+18h]
0x180005874  mov     edx, ebx
0x180005876  mov     rax, [r13+38h]
0x18000587a  mov     edi, ebx
0x18000587c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005881  add     rdi, rdi
0x180005884  inc     ebx
0x180005886  mov     [r15+rdi*8+8], eax
0x18000588b  cmp     ebx, [rbp+10h]
0x18000588e  jb      short loc_180005870
0x180005890  cmp     dword ptr [rbp+14h], 0
0x180005894  mov     [rsp+0D8h+var_58], 0
0x18000589f  jbe     short loc_1800058D3
0x1800058a1  mov     r12d, [rsp+0D8h+var_58]
0x1800058a9  mov     rcx, [rbp+20h]
0x1800058ad  mov     edx, r12d
0x1800058b0  mov     rax, [r13+38h]
0x1800058b4  mov     edi, ebx
0x1800058b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800058bb  add     rdi, rdi
0x1800058be  inc     ebx
0x1800058c0  inc     r12d
0x1800058c3  mov     [r15+rdi*8+8], eax
0x1800058c8  cmp     r12d, [rbp+14h]
0x1800058cc  jb      short loc_1800058A9
0x1800058ce  mov     r12, [rsp+0D8h+var_90]
0x1800058d3  mov     rax, rsi
0x1800058d6  mov     ecx, ebx
0x1800058d8  sub     rax, r15
0x1800058db  sar     rax, 4
0x1800058df  cmp     rcx, rax
0x1800058e2  jnz     loc_180005A6C
0x1800058e8  mov     rcx, [r12]
0x1800058ec  mov     rax, [rsp+0D8h+var_B8]
0x1800058f1  mov     rdx, [rsp+0D8h+var_88]
0x1800058f6  mov     [r12], r15
0x1800058fa  mov     [r12+8], rsi
0x1800058ff  mov     [r12+10h], rax
0x180005904  mov     eax, [rbp+10h]
0x180005907  mov     [rdx], rax
0x18000590a  mov     rdx, [rsp+0D8h+var_80]
0x18000590f  mov     eax, [rbp+14h]
0x180005912  mov     [rdx], rax
0x180005915  test    rcx, rcx
0x180005918  jnz     loc_180005A7E
0x18000591e  xor     eax, eax
0x180005920  mov     rbp, [rsp+0D8h+var_38]
0x180005928  mov     r14, [rsp+0D8h+var_40]
0x180005930  mov     rcx, [rsp+0D8h+var_50]
0x180005938  xor     rcx, rsp; StackCookie
0x18000593b  call    __security_check_cookie
0x180005940  add     rsp, 0A8h
0x180005947  pop     r15
0x180005949  pop     r13
0x18000594b  pop     r12
0x18000594d  pop     rdi
0x18000594e  pop     rsi
0x18000594f  pop     rbx
0x180005950  retn
0x180005952  lea     rax, aOnecoreBaseXml_1; "onecore\\base\\xml\\udom_microdom.cpp"
0x180005959  mov     [rsp+0D8h+var_A0], 0EEBh
0x180005962  mov     qword ptr [rsp+0D8h+var_B0], rax
0x180005967  lea     rdx, [rsp+0D8h+var_B0]
0x18000596c  lea     rax, aMicrodomimplem_45; "MicrodomImplementation::CDomLayoutCache"...
0x180005973  mov     r8d, 0C0000095h
0x180005979  mov     qword ptr [rsp+0D8h+var_B0+8], rax
0x18000597e  lea     rcx, [rsp+0D8h+var_58]
0x180005986  lea     rax, aBuclRtlAddPcac; "BUCL::Rtl::Add(pCachedInfo->m_ulChildCo"...
0x18000598d  mov     [rsp+0D8h+var_98], rax
0x180005992  call    ?OriginateNtStatus@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@J@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateNtStatus(Windows::ErrorHandling::_RTL_CALL_SITE const &,long)
0x180005997  jmp     short loc_180005920
0x180005999  mov     rdi, rbx
0x18000599c  shl     rdi, 4
0x1800059a0  mov     rcx, rdi; Size
0x1800059a3  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800059a8  mov     r15, rax
0x1800059ab  test    rax, rax
0x1800059ae  jz      short loc_180005A14
0x1800059b0  mov     rsi, rax
0x1800059b3  add     rax, rdi
0x1800059b6  mov     [rsp+0D8h+var_B8], rax
0x1800059bb  test    rsi, rsi
0x1800059be  jz      short loc_1800059C6
0x1800059c0  xorps   xmm0, xmm0
0x1800059c3  movups  xmmword ptr [rsi], xmm0
0x1800059c6  add     rsi, 10h
0x1800059ca  mov     rax, rsi
0x1800059cd  sub     rax, r15
0x1800059d0  sar     rax, 4
0x1800059d4  cmp     rbx, rax
0x1800059d7  jnz     short loc_1800059BB
0x1800059d9  mov     ecx, [rbp+10h]
0x1800059dc  jmp     loc_180005869
0x1800059e1  mov     rcx, [r12]
0x1800059e5  mov     rax, [r12+8]
0x1800059ea  cmp     rcx, rax
0x1800059ed  jz      short loc_1800059FD
0x1800059ef  add     rax, 0FFFFFFFFFFFFFFF0h
0x1800059f3  cmp     rcx, rax
0x1800059f6  jnz     short loc_1800059EF
0x1800059f8  mov     [r12+8], rax
0x1800059fd  mov     [rdi], r15
0x180005a00  mov     [rsi], r15
0x180005a03  jmp     loc_18000591E
0x180005a08  cmp     [rbp+14h], r15d
0x180005a0c  ja      loc_180005835
0x180005a12  jmp     short loc_1800059E1
0x180005a14  lea     rax, aOnecoreBaseXml_1; "onecore\\base\\xml\\udom_microdom.cpp"
0x180005a1b  mov     [rsp+0D8h+var_68], 0EEFh
0x180005a24  mov     [rsp+0D8h+var_78], rax
0x180005a29  lea     rdx, [rsp+0D8h+var_78]
0x180005a2e  lea     rax, aMicrodomimplem_45; "MicrodomImplementation::CDomLayoutCache"...
0x180005a35  mov     r8d, 0C0000017h
0x180005a3b  mov     [rsp+0D8h+var_70], rax
0x180005a40  lea     rcx, [rsp+0D8h+var_58]
0x180005a48  lea     rax, aTmpnodesResize; "TmpNodes.Resize(cNecessary)"
0x180005a4f  mov     [rsp+0D8h+var_60], rax
0x180005a54  call    ?OriginateNtStatus@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@J@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateNtStatus(Windows::ErrorHandling::_RTL_CALL_SITE const &,long)
0x180005a59  lea     rcx, [rsp+0D8h+var_B0]
0x180005a5e  mov     ebx, eax
0x180005a60  call    ?Close@?$CVector@UNode@Rtl@Microdom@Windows@@VCCallDisposition@2BUCL@@@BUCL@@QEAAXXZ; BUCL::CVector<Windows::Microdom::Rtl::Node,BUCL::Rtl::CCallDisposition>::Close(void)
0x180005a65  mov     eax, ebx
0x180005a67  jmp     loc_180005920
0x180005a6c  mov     ecx, 0C00000E5h; Status
0x180005a71  call    cs:__imp_RtlRaiseStatus
0x180005a78  nop     dword ptr [rax+rax+00h]
0x180005a7d  int     3; Trap to Debugger
0x180005a7e  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180005a83  jmp     loc_18000591E
```
