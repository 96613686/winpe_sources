# PresentTraceConsumerCore::PresentTraceConsumerCore(PresentTraceConsumerCore::Config const &,ushort const *,ushort const *)

- ea: `0x18001794c`
- end: `0x180017c4b`
- name: `??0PresentTraceConsumerCore@@QEAA@AEBUConfig@0@PEBG1@Z`
- size: `767`
- prototype: `PresentTraceConsumerCore *__fastcall(PresentTraceConsumerCore *__hidden this, const struct PresentTraceConsumerCore::Config *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, service_task`

## callers

- `0x180011630`

## callees

- `0x180003ebc`
- `0x18000fcec`
- `0x180017898`
- `0x18001794c`
- `0x18001b36c`
- `0x180026950`
- `0x1800289b8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x1800179ab`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x1800179ab`

## pseudocode

```c
PresentTraceConsumerCore *__fastcall PresentTraceConsumerCore::PresentTraceConsumerCore(
        PresentTraceConsumerCore *this,
        const struct PresentTraceConsumerCore::Config *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4)
{
  char v6; // bp
  _QWORD *v7; // rax
  PMTraceConsumer *v8; // rax
  _QWORD *v9; // rax
  _QWORD *v10; // rax
  _QWORD *v11; // rax
  _QWORD *v12; // rax
  __int64 v13; // rdx

  *(_QWORD *)this = &PresentTraceConsumerCore::`vftable'{for `ITraceConsumer'};
  *((_QWORD *)this + 1) = &ServiceTraceConsumer::`vftable'{for `ITelemetryCounters'};
  TraceSession::TraceSession((PresentTraceConsumerCore *)((char *)this + 16), (const unsigned __int16 *)a2, a3);
  *((_WORD *)this + 76) = 256;
  v6 = 1;
  InitializeCriticalSectionEx((LPCRITICAL_SECTION)this + 4, 0, 0);
  *((_QWORD *)this + 25) = 0;
  *((_QWORD *)this + 26) = 0;
  v7 = operator new(0x50u);
  *v7 = v7;
  v7[1] = v7;
  v7[2] = v7;
  *((_WORD *)v7 + 12) = 257;
  *((_QWORD *)this + 25) = v7;
  *((_BYTE *)this + 216) = 0;
  *((_QWORD *)this + 28) = 0;
  *((_QWORD *)this + 29) = &dxg::pmrlite::memory_resource_one_at_a_time::`vftable';
  *((_QWORD *)this + 30) = 0;
  *((_QWORD *)this + 31) = 0;
  *((_QWORD *)this + 32) = 0;
  v8 = (PMTraceConsumer *)operator new(0x2E0u);
  *((_QWORD *)this + 33) = PMTraceConsumer::PMTraceConsumer(v8);
  *((_OWORD *)this + 17) = *(_OWORD *)a2;
  *(_OWORD *)((char *)this + 284) = *(_OWORD *)((char *)a2 + 12);
  PresentTraceConsumerCore::Counters::Counters((PresentTraceConsumerCore *)((char *)this + 304));
  *((_DWORD *)this + 130) = 0;
  *((_QWORD *)this + 66) = 0;
  *((_QWORD *)this + 67) = 0;
  v9 = operator new(0x20u);
  *v9 = v9;
  v9[1] = v9;
  *((_QWORD *)this + 66) = v9;
  *((_QWORD *)this + 68) = 0;
  *((_QWORD *)this + 69) = 0;
  *((_QWORD *)this + 70) = 0;
  *((_QWORD *)this + 71) = 7;
  *((_QWORD *)this + 72) = 8;
  *((_DWORD *)this + 130) = 1065353216;
  std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<unsigned __int64 const,unsigned int>>>>>>::_Assign_grow(
    (char *)this + 544,
    16,
    *((_QWORD *)this + 66));
  *((_QWORD *)this + 73) = 0;
  *((_DWORD *)this + 148) = 0;
  *((_QWORD *)this + 75) = 0;
  *((_QWORD *)this + 76) = 0;
  v10 = operator new(0x20u);
  *v10 = v10;
  v10[1] = v10;
  *((_QWORD *)this + 75) = v10;
  *((_QWORD *)this + 77) = 0;
  *((_QWORD *)this + 78) = 0;
  *((_QWORD *)this + 79) = 0;
  *((_QWORD *)this + 80) = 7;
  *((_QWORD *)this + 81) = 8;
  *((_DWORD *)this + 148) = 1065353216;
  std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<unsigned __int64 const,unsigned int>>>>>>::_Assign_grow(
    (char *)this + 616,
    16,
    *((_QWORD *)this + 75));
  *((_DWORD *)this + 164) = 0;
  *((_QWORD *)this + 83) = 0;
  *((_QWORD *)this + 84) = 0;
  v11 = operator new(0x28u);
  *v11 = v11;
  v11[1] = v11;
  *((_QWORD *)this + 83) = v11;
  *((_QWORD *)this + 85) = 0;
  *((_QWORD *)this + 86) = 0;
  *((_QWORD *)this + 87) = 0;
  *((_QWORD *)this + 88) = 7;
  *((_QWORD *)this + 89) = 8;
  *((_DWORD *)this + 164) = 1065353216;
  std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<unsigned __int64 const,unsigned int>>>>>>::_Assign_grow(
    (char *)this + 680,
    16,
    *((_QWORD *)this + 83));
  *((_DWORD *)this + 180) = 0;
  *((_QWORD *)this + 91) = 0;
  *((_QWORD *)this + 92) = 0;
  v12 = operator new(0x38u);
  *v12 = v12;
  v12[1] = v12;
  *((_QWORD *)this + 91) = v12;
  *((_QWORD *)this + 93) = 0;
  *((_QWORD *)this + 94) = 0;
  *((_QWORD *)this + 95) = 0;
  *((_QWORD *)this + 96) = 7;
  *((_QWORD *)this + 97) = 8;
  *((_DWORD *)this + 180) = 1065353216;
  std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<unsigned __int64 const,unsigned int>>>>>>::_Assign_grow(
    (char *)this + 744,
    16,
    *((_QWORD *)this + 91));
  v13 = 0;
  *((_DWORD *)this + 196) = 0;
  *((_QWORD *)this + 99) = 0;
  *((_QWORD *)this + 100) = 0;
  *((_QWORD *)this + 101) = 0;
  *(_BYTE *)(*((_QWORD *)this + 33) + 64LL) = 0;
  *(_BYTE *)(*((_QWORD *)this + 33) + 66LL) = 1;
  *(_BYTE *)(*((_QWORD *)this + 33) + 65LL) = 1;
  *(_BYTE *)(*((_QWORD *)this + 33) + 67LL) = (*((_DWORD *)this + 70) & 0x10) != 0;
  if ( (*((_BYTE *)this + 280) & 0x20) != 0 )
  {
    LOBYTE(v13) = 1;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_GPM_MultiMon>::ReportUsage(
      `wil::Feature<__WilFeatureTraits_Feature_GPM_MultiMon>::GetImpl'::`2'::impl,
      v13);
  }
  else
  {
    v6 = 0;
  }
  *(_BYTE *)(*((_QWORD *)this + 33) + 608LL) = v6;
  return this;
}

```

## disassembly

```asm
0x18001794c  mov     rax, rsp
0x18001794f  mov     [rax+10h], rbx
0x180017953  mov     [rax+18h], rbp
0x180017957  mov     [rax+20h], r9
0x18001795b  mov     [rax+8], rcx
0x18001795f  push    rsi
0x180017960  push    rdi
0x180017961  push    r12
0x180017963  push    r14
0x180017965  push    r15
0x180017967  sub     rsp, 20h
0x18001796b  mov     rdi, rdx
0x18001796e  mov     rsi, rcx
0x180017971  lea     rax, ??_7PresentTraceConsumerCore@@6BITraceConsumer@@@; const PresentTraceConsumerCore::`vftable'{for `ITraceConsumer'}
0x180017978  mov     [rcx], rax
0x18001797b  lea     rax, ??_7ServiceTraceConsumer@@6BITelemetryCounters@@@; const ServiceTraceConsumer::`vftable'{for `ITelemetryCounters'}
0x180017982  mov     [rcx+8], rax
0x180017986  add     rcx, 10h; this
0x18001798a  call    ??0TraceSession@@QEAA@PEBG0@Z; TraceSession::TraceSession(ushort const *,ushort const *)
0x18001798f  nop
0x180017990  xor     r14d, r14d
0x180017993  mov     word ptr [rsi+98h], 100h
0x18001799c  mov     bpl, 1
0x18001799f  lea     rcx, [rsi+0A0h]; lpCriticalSection
0x1800179a6  xor     r8d, r8d; Flags
0x1800179a9  xor     edx, edx; dwSpinCount
0x1800179ab  call    cs:__imp_InitializeCriticalSectionEx
0x1800179b1  nop
0x1800179b2  lea     rbx, [rsi+0C8h]
0x1800179b9  mov     [rbx], r14
0x1800179bc  mov     [rbx+8], r14
0x1800179c0  lea     ecx, [r14+50h]; Size
0x1800179c4  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800179c9  mov     [rax], rax
0x1800179cc  mov     [rax+8], rax
0x1800179d0  mov     [rax+10h], rax
0x1800179d4  mov     word ptr [rax+18h], 101h
0x1800179da  mov     [rbx], rax
0x1800179dd  mov     [rsi+0D8h], r14b
0x1800179e4  mov     [rsi+0E0h], r14
0x1800179eb  lea     rax, ??_7memory_resource_one_at_a_time@pmrlite@dxg@@6B@; const dxg::pmrlite::memory_resource_one_at_a_time::`vftable'
0x1800179f2  mov     [rsi+0E8h], rax
0x1800179f9  mov     [rsi+0F0h], r14
0x180017a00  mov     [rsi+0F8h], r14
0x180017a07  mov     [rsi+100h], r14
0x180017a0e  mov     ecx, 2E0h; Size
0x180017a13  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180017a18  mov     [rsp+48h+arg_18], rax
0x180017a1d  mov     rcx, rax; this
0x180017a20  call    ??0PMTraceConsumer@@QEAA@XZ; PMTraceConsumer::PMTraceConsumer(void)
0x180017a25  nop
0x180017a26  mov     [rsi+108h], rax
0x180017a2d  movups  xmm0, xmmword ptr [rdi]
0x180017a30  movups  xmmword ptr [rsi+110h], xmm0
0x180017a37  movups  xmm1, xmmword ptr [rdi+0Ch]
0x180017a3b  movups  xmmword ptr [rsi+11Ch], xmm1
0x180017a42  lea     rcx, [rsi+130h]; this
0x180017a49  call    ??0Counters@PresentTraceConsumerCore@@QEAA@XZ; PresentTraceConsumerCore::Counters::Counters(void)
0x180017a4e  nop
0x180017a4f  lea     rbx, [rsi+208h]
0x180017a56  mov     [rsp+48h+arg_18], rbx
0x180017a5b  mov     [rbx], r14d
0x180017a5e  mov     [rbx+8], r14
0x180017a62  mov     [rbx+10h], r14
0x180017a66  lea     ecx, [r14+20h]; Size
0x180017a6a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180017a6f  mov     [rax], rax
0x180017a72  mov     [rax+8], rax
0x180017a76  mov     [rbx+8], rax
0x180017a7a  lea     rcx, [rbx+18h]
0x180017a7e  mov     [rcx], r14
0x180017a81  mov     [rcx+8], r14
0x180017a85  mov     [rcx+10h], r14
0x180017a89  lea     r12d, [r14+7]
0x180017a8d  mov     [rbx+30h], r12
0x180017a91  lea     r15d, [r14+8]
0x180017a95  mov     [rbx+38h], r15
0x180017a99  mov     r14d, 3F800000h
0x180017a9f  mov     [rbx], r14d
0x180017aa2  mov     r8, [rbx+8]
0x180017aa6  lea     edi, [r12+9]
0x180017aab  mov     edx, edi
0x180017aad  call    ?_Assign_grow@?$_Hash_vec@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CB_KI@std@@@std@@@std@@@std@@@std@@@std@@QEAAX_KV?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CB_KI@std@@@std@@@std@@@2@@Z; std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<unsigned __int64 const,uint>>>>>>::_Assign_grow(unsigned __int64,std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<unsigned __int64 const,uint>>>>)
0x180017ab2  nop
0x180017ab3  xor     eax, eax
0x180017ab5  mov     [rsi+248h], rax
0x180017abc  lea     rbx, [rsi+250h]
0x180017ac3  mov     [rsp+48h+arg_18], rbx
0x180017ac8  mov     [rbx], eax
0x180017aca  mov     [rbx+8], rax
0x180017ace  mov     [rbx+10h], rax
0x180017ad2  lea     ecx, [rdi+10h]; Size
0x180017ad5  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180017ada  mov     [rax], rax
0x180017add  mov     [rax+8], rax
0x180017ae1  mov     [rbx+8], rax
0x180017ae5  lea     rcx, [rbx+18h]
0x180017ae9  xor     eax, eax
0x180017aeb  mov     [rcx], rax
0x180017aee  mov     [rcx+8], rax
0x180017af2  mov     [rcx+10h], rax
0x180017af6  mov     [rbx+30h], r12
0x180017afa  mov     [rbx+38h], r15
0x180017afe  mov     [rbx], r14d
0x180017b01  mov     r8, [rbx+8]
0x180017b05  mov     edx, edi
0x180017b07  call    ?_Assign_grow@?$_Hash_vec@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CB_KI@std@@@std@@@std@@@std@@@std@@@std@@QEAAX_KV?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CB_KI@std@@@std@@@std@@@2@@Z; std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<unsigned __int64 const,uint>>>>>>::_Assign_grow(unsigned __int64,std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<unsigned __int64 const,uint>>>>)
0x180017b0c  nop
0x180017b0d  lea     rbx, [rsi+290h]
0x180017b14  mov     [rsp+48h+arg_18], rbx
0x180017b19  xor     eax, eax
0x180017b1b  mov     [rbx], eax
0x180017b1d  mov     [rbx+8], rax
0x180017b21  mov     [rbx+10h], rax
0x180017b25  lea     ecx, [rdi+18h]; Size
0x180017b28  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180017b2d  mov     [rax], rax
0x180017b30  mov     [rax+8], rax
0x180017b34  mov     [rbx+8], rax
0x180017b38  lea     rcx, [rbx+18h]
0x180017b3c  xor     eax, eax
0x180017b3e  mov     [rcx], rax
0x180017b41  mov     [rcx+8], rax
0x180017b45  mov     [rcx+10h], rax
0x180017b49  mov     [rbx+30h], r12
0x180017b4d  mov     [rbx+38h], r15
0x180017b51  mov     [rbx], r14d
0x180017b54  mov     r8, [rbx+8]
0x180017b58  mov     edx, edi
0x180017b5a  call    ?_Assign_grow@?$_Hash_vec@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CB_KI@std@@@std@@@std@@@std@@@std@@@std@@QEAAX_KV?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CB_KI@std@@@std@@@std@@@2@@Z; std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<unsigned __int64 const,uint>>>>>>::_Assign_grow(unsigned __int64,std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<unsigned __int64 const,uint>>>>)
0x180017b5f  nop
0x180017b60  lea     rbx, [rsi+2D0h]
0x180017b67  mov     [rsp+48h+arg_18], rbx
0x180017b6c  xor     eax, eax
0x180017b6e  mov     [rbx], eax
0x180017b70  mov     [rbx+8], rax
0x180017b74  mov     [rbx+10h], rax
0x180017b78  lea     ecx, [rdi+28h]; Size
0x180017b7b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180017b80  mov     [rax], rax
0x180017b83  mov     [rax+8], rax
0x180017b87  mov     [rbx+8], rax
0x180017b8b  lea     rcx, [rbx+18h]
0x180017b8f  xor     eax, eax
0x180017b91  mov     [rcx], rax
0x180017b94  mov     [rcx+8], rax
0x180017b98  mov     [rcx+10h], rax
0x180017b9c  mov     [rbx+30h], r12
0x180017ba0  mov     [rbx+38h], r15
0x180017ba4  mov     [rbx], r14d
0x180017ba7  mov     r8, [rbx+8]
0x180017bab  mov     edx, edi
0x180017bad  call    ?_Assign_grow@?$_Hash_vec@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CB_KI@std@@@std@@@std@@@std@@@std@@@std@@QEAAX_KV?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CB_KI@std@@@std@@@std@@@2@@Z; std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<unsigned __int64 const,uint>>>>>>::_Assign_grow(unsigned __int64,std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<unsigned __int64 const,uint>>>>)
0x180017bb2  nop
0x180017bb3  xor     edx, edx
0x180017bb5  mov     [rsi+310h], edx
0x180017bbb  mov     [rsi+318h], rdx
0x180017bc2  mov     [rsi+320h], rdx
0x180017bc9  mov     [rsi+328h], rdx
0x180017bd0  mov     rax, [rsi+108h]
0x180017bd7  mov     [rax+40h], dl
0x180017bda  mov     rax, [rsi+108h]
0x180017be1  mov     [rax+42h], bpl
0x180017be5  mov     rax, [rsi+108h]
0x180017bec  mov     [rax+41h], bpl
0x180017bf0  mov     ecx, [rsi+118h]
0x180017bf6  shr     ecx, 4
0x180017bf9  and     cl, bpl
0x180017bfc  mov     rax, [rsi+108h]
0x180017c03  mov     [rax+43h], cl
0x180017c06  test    byte ptr [rsi+118h], 20h
0x180017c0d  jz      short loc_180017C20
0x180017c0f  mov     dl, bpl
0x180017c12  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_GPM_MultiMon@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_GPM_MultiMon@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_GPM_MultiMon> `wil::Feature<__WilFeatureTraits_Feature_GPM_MultiMon>::GetImpl(void)'::`2'::impl
0x180017c19  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_GPM_MultiMon@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_GPM_MultiMon>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x180017c1e  jmp     short loc_180017C23
0x180017c20  mov     bpl, dl
0x180017c23  mov     rax, [rsi+108h]
0x180017c2a  mov     [rax+260h], bpl
0x180017c31  mov     rax, rsi
0x180017c34  mov     rbx, [rsp+48h+arg_8]
0x180017c39  mov     rbp, [rsp+48h+arg_10]
0x180017c3e  add     rsp, 20h
0x180017c42  pop     r15
0x180017c44  pop     r14
0x180017c46  pop     r12
0x180017c48  pop     rdi
0x180017c49  pop     rsi
0x180017c4a  retn
```
