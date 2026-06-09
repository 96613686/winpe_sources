# TrackedProcessConsumer::ComputeStatistics(void)

- ea: `0x1800258a0`
- end: `0x180025b34`
- name: `?ComputeStatistics@TrackedProcessConsumer@@UEAA?AUTrackedProcessStatistics@@XZ`
- size: `660`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x1800047f0`
- `0x18000fc54`
- `0x180011274`
- `0x1800254d8`
- `0x1800255a4`
- `0x1800258a0`
- `0x180025b3c`

## pseudocode

```c
__int64 __fastcall TrackedProcessConsumer::ComputeStatistics(__int64 a1, __int64 a2)
{
  __int64 v4; // r8
  __int64 v5; // rdx
  _QWORD *PipelineStateObject; // rax
  __int64 v7; // rcx
  __int128 v8; // xmm1
  __int128 v9; // xmm2
  __int128 v10; // xmm3
  __int128 v11; // xmm4
  __int128 v12; // xmm5
  __int128 v13; // xmm6
  __int128 v14; // xmm7
  __int128 v15; // xmm8
  __int128 v16; // xmm9
  __int128 v17; // xmm10
  __int128 v18; // xmm11
  __int128 *Resident; // rax
  __int128 v20; // xmm0
  __int128 v21; // xmm1
  __int128 v22; // xmm2
  __int128 v23; // xmm3
  __int128 v24; // xmm4
  __int128 v25; // xmm5
  __int128 v26; // xmm6
  __int128 v27; // xmm7
  __int128 v28; // xmm8
  __int128 v29; // xmm9
  __int128 v30; // xmm10
  __int128 v31; // xmm11
  __int128 v32; // xmm12
  __int128 v33; // xmm0
  _QWORD v35[24]; // [rsp+20h] [rbp-148h] BYREF
  __int128 v36; // [rsp+E0h] [rbp-88h]

  *(_QWORD *)a2 = 0;
  *(_QWORD *)(a2 + 8) = 0;
  *(_QWORD *)(a2 + 16) = 0;
  *(_QWORD *)(a2 + 24) = 0;
  *(_QWORD *)(a2 + 32) = 0;
  memset_0((void *)(a2 + 40), 0, 0xA0u);
  *(_QWORD *)(a2 + 200) = 0;
  *(_QWORD *)(a2 + 208) = 0;
  *(_QWORD *)(a2 + 216) = 0;
  *(_QWORD *)(a2 + 224) = 0;
  *(_QWORD *)(a2 + 232) = 0;
  memset_0((void *)(a2 + 240), 0, 0xA0u);
  *(_QWORD *)(a2 + 400) = 0;
  LOBYTE(v4) = 3;
  LOBYTE(v5) = 1;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_GPM_CreatePSOTracking>::ReportUsage(
    `wil::Feature<__WilFeatureTraits_Feature_GPM_CreatePSOTracking>::GetImpl'::`2'::impl,
    v5,
    v4);
  PipelineStateObject = ComputeTimeMsHistogramStats<CreatePipelineStateObjectStatistics>(v35, (__int64 *)(a1 + 8));
  v7 = PipelineStateObject[24];
  v8 = *((_OWORD *)PipelineStateObject + 1);
  v9 = *((_OWORD *)PipelineStateObject + 2);
  v10 = *((_OWORD *)PipelineStateObject + 3);
  v11 = *((_OWORD *)PipelineStateObject + 4);
  v12 = *((_OWORD *)PipelineStateObject + 5);
  v13 = *((_OWORD *)PipelineStateObject + 6);
  v14 = *((_OWORD *)PipelineStateObject + 7);
  v15 = *((_OWORD *)PipelineStateObject + 8);
  v16 = *((_OWORD *)PipelineStateObject + 9);
  v17 = *((_OWORD *)PipelineStateObject + 10);
  v18 = *((_OWORD *)PipelineStateObject + 11);
  *(_OWORD *)a2 = *(_OWORD *)PipelineStateObject;
  *(_OWORD *)(a2 + 16) = v8;
  *(_OWORD *)(a2 + 32) = v9;
  *(_OWORD *)(a2 + 48) = v10;
  *(_OWORD *)(a2 + 64) = v11;
  *(_OWORD *)(a2 + 80) = v12;
  *(_OWORD *)(a2 + 96) = v13;
  *(_OWORD *)(a2 + 112) = v14;
  *(_OWORD *)(a2 + 128) = v15;
  *(_OWORD *)(a2 + 144) = v16;
  *(_OWORD *)(a2 + 160) = v17;
  *(_OWORD *)(a2 + 176) = v18;
  *(_QWORD *)(a2 + 192) = v7;
  if ( wil::details::FeatureImpl<__WilFeatureTraits_Feature_GPM_ResidencyTracking>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_GPM_ResidencyTracking>::GetImpl'::`2'::impl) )
  {
    Resident = (__int128 *)ComputeTimeMsHistogramStats<MakeResidentStatistics>(v35, (__int64 *)(a1 + 104));
    v20 = Resident[12];
    v21 = *Resident;
    v22 = Resident[1];
    v23 = Resident[2];
    v24 = Resident[3];
    v25 = Resident[4];
    v26 = Resident[5];
    v27 = Resident[6];
    v28 = Resident[7];
    v29 = Resident[8];
    v30 = Resident[9];
    v31 = Resident[10];
    v32 = Resident[11];
    LODWORD(Resident) = *(_DWORD *)(a1 + 200);
    *(_OWORD *)(a2 + 200) = v21;
    *(_OWORD *)(a2 + 216) = v22;
    *(_OWORD *)(a2 + 232) = v23;
    *(_OWORD *)(a2 + 248) = v24;
    *(_OWORD *)(a2 + 264) = v25;
    *(_OWORD *)(a2 + 280) = v26;
    *(_OWORD *)(a2 + 296) = v27;
    *(_OWORD *)(a2 + 312) = v28;
    *(_OWORD *)(a2 + 328) = v29;
    *(_OWORD *)(a2 + 344) = v30;
    v36 = v20;
    DWORD2(v36) = (_DWORD)Resident;
    v33 = v36;
    *(_OWORD *)(a2 + 360) = v31;
    *(_OWORD *)(a2 + 376) = v32;
    *(_OWORD *)(a2 + 392) = v33;
  }
  TrackedProcessConsumer::ResetStatistics((TrackedProcessConsumer *)a1);
  return a2;
}

```

## disassembly

```asm
0x1800258a0  mov     rax, rsp
0x1800258a3  mov     [rax+8], rbx
0x1800258a7  push    rdi
0x1800258a8  sub     rsp, 160h
0x1800258af  movaps  xmmword ptr [rax-18h], xmm6
0x1800258b3  mov     rdi, rcx
0x1800258b6  movaps  xmmword ptr [rax-28h], xmm7
0x1800258ba  lea     rcx, [rdx+28h]; void *
0x1800258be  movaps  xmmword ptr [rax-38h], xmm8
0x1800258c3  mov     rbx, rdx
0x1800258c6  movaps  xmmword ptr [rax-48h], xmm9
0x1800258cb  mov     r8d, 0A0h; Size
0x1800258d1  movaps  xmmword ptr [rax-58h], xmm10
0x1800258d6  mov     qword ptr [rdx], 0
0x1800258dd  mov     qword ptr [rdx+8], 0
0x1800258e5  mov     qword ptr [rdx+10h], 0
0x1800258ed  mov     qword ptr [rdx+18h], 0
0x1800258f5  mov     qword ptr [rdx+20h], 0
0x1800258fd  xor     edx, edx; Val
0x1800258ff  movaps  xmmword ptr [rax-68h], xmm11
0x180025904  movaps  xmmword ptr [rax-78h], xmm12
0x180025909  call    memset_0
0x18002590e  lea     rcx, [rbx+0F0h]; void *
0x180025915  mov     qword ptr [rbx+0C8h], 0
0x180025920  xor     edx, edx; Val
0x180025922  mov     qword ptr [rbx+0D0h], 0
0x18002592d  mov     r8d, 0A0h; Size
0x180025933  mov     qword ptr [rbx+0D8h], 0
0x18002593e  mov     qword ptr [rbx+0E0h], 0
0x180025949  mov     qword ptr [rbx+0E8h], 0
0x180025954  call    memset_0
0x180025959  mov     qword ptr [rbx+190h], 0
0x180025964  mov     r8b, 3
0x180025967  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_GPM_CreatePSOTracking@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_GPM_CreatePSOTracking@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_GPM_CreatePSOTracking> `wil::Feature<__WilFeatureTraits_Feature_GPM_CreatePSOTracking>::GetImpl(void)'::`2'::impl
0x18002596e  mov     dl, 1
0x180025970  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_GPM_CreatePSOTracking@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_GPM_CreatePSOTracking>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x180025975  lea     rdx, [rdi+8]
0x180025979  lea     rcx, [rsp+168h+var_148]
0x18002597e  call    ??$ComputeTimeMsHistogramStats@UCreatePipelineStateObjectStatistics@@@@YA?AUCreatePipelineStateObjectStatistics@@AEBVTimeMsHistogram@@@Z; ComputeTimeMsHistogramStats<CreatePipelineStateObjectStatistics>(TimeMsHistogram const &)
0x180025983  movups  xmm0, xmmword ptr [rax]
0x180025986  mov     rcx, [rax+0C0h]
0x18002598d  movups  xmm1, xmmword ptr [rax+10h]
0x180025991  movups  xmm2, xmmword ptr [rax+20h]
0x180025995  movups  xmm3, xmmword ptr [rax+30h]
0x180025999  movups  xmm4, xmmword ptr [rax+40h]
0x18002599d  movups  xmm5, xmmword ptr [rax+50h]
0x1800259a1  movups  xmm6, xmmword ptr [rax+60h]
0x1800259a5  movups  xmm7, xmmword ptr [rax+70h]
0x1800259a9  movups  xmm8, xmmword ptr [rax+80h]
0x1800259b1  movups  xmm9, xmmword ptr [rax+90h]
0x1800259b9  movups  xmm10, xmmword ptr [rax+0A0h]
0x1800259c1  movups  xmm11, xmmword ptr [rax+0B0h]
0x1800259c9  movups  xmmword ptr [rbx], xmm0
0x1800259cc  movups  xmmword ptr [rbx+10h], xmm1
0x1800259d0  movups  xmmword ptr [rbx+20h], xmm2
0x1800259d4  movups  xmmword ptr [rbx+30h], xmm3
0x1800259d8  movups  xmmword ptr [rbx+40h], xmm4
0x1800259dc  movups  xmmword ptr [rbx+50h], xmm5
0x1800259e0  movups  xmmword ptr [rbx+60h], xmm6
0x1800259e4  movups  xmmword ptr [rbx+70h], xmm7
0x1800259e8  movups  xmmword ptr [rbx+80h], xmm8
0x1800259f0  movups  xmmword ptr [rbx+90h], xmm9
0x1800259f8  movups  xmmword ptr [rbx+0A0h], xmm10
0x180025a00  movups  xmmword ptr [rbx+0B0h], xmm11
0x180025a08  mov     [rbx+0C0h], rcx
0x180025a0f  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_GPM_ResidencyTracking@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_GPM_ResidencyTracking@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_GPM_ResidencyTracking> `wil::Feature<__WilFeatureTraits_Feature_GPM_ResidencyTracking>::GetImpl(void)'::`2'::impl
0x180025a16  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_GPM_ResidencyTracking@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_GPM_ResidencyTracking>::__private_IsEnabled(void)
0x180025a1b  test    al, al
0x180025a1d  jz      loc_180025AF5
0x180025a23  lea     rdx, [rdi+68h]
0x180025a27  lea     rcx, [rsp+168h+var_148]
0x180025a2c  call    ??$ComputeTimeMsHistogramStats@UMakeResidentStatistics@@@@YA?AUMakeResidentStatistics@@AEBVTimeMsHistogram@@@Z; ComputeTimeMsHistogramStats<MakeResidentStatistics>(TimeMsHistogram const &)
0x180025a31  movups  xmm0, xmmword ptr [rax+0C0h]
0x180025a38  movups  xmm1, xmmword ptr [rax]
0x180025a3b  movups  xmm2, xmmword ptr [rax+10h]
0x180025a3f  movups  xmm3, xmmword ptr [rax+20h]
0x180025a43  movups  xmm4, xmmword ptr [rax+30h]
0x180025a47  movups  xmm5, xmmword ptr [rax+40h]
0x180025a4b  movups  xmm6, xmmword ptr [rax+50h]
0x180025a4f  movups  xmm7, xmmword ptr [rax+60h]
0x180025a53  movups  xmm8, xmmword ptr [rax+70h]
0x180025a58  movups  xmm9, xmmword ptr [rax+80h]
0x180025a60  movups  xmm10, xmmword ptr [rax+90h]
0x180025a68  movups  xmm11, xmmword ptr [rax+0A0h]
0x180025a70  movups  xmm12, xmmword ptr [rax+0B0h]
0x180025a78  mov     eax, [rdi+0C8h]
0x180025a7e  movups  xmmword ptr [rbx+0C8h], xmm1
0x180025a85  movups  xmmword ptr [rbx+0D8h], xmm2
0x180025a8c  movups  xmmword ptr [rbx+0E8h], xmm3
0x180025a93  movups  xmmword ptr [rbx+0F8h], xmm4
0x180025a9a  movups  xmmword ptr [rbx+108h], xmm5
0x180025aa1  movups  xmmword ptr [rbx+118h], xmm6
0x180025aa8  movups  xmmword ptr [rbx+128h], xmm7
0x180025aaf  movups  xmmword ptr [rbx+138h], xmm8
0x180025ab7  movups  xmmword ptr [rbx+148h], xmm9
0x180025abf  movups  xmmword ptr [rbx+158h], xmm10
0x180025ac7  movups  [rsp+168h+var_88], xmm0
0x180025acf  mov     dword ptr [rsp+168h+var_88+8], eax
0x180025ad6  movaps  xmm0, [rsp+168h+var_88]
0x180025ade  movups  xmmword ptr [rbx+168h], xmm11
0x180025ae6  movups  xmmword ptr [rbx+178h], xmm12
0x180025aee  movups  xmmword ptr [rbx+188h], xmm0
0x180025af5  mov     rcx, rdi; this
0x180025af8  call    ?ResetStatistics@TrackedProcessConsumer@@AEAAXXZ; TrackedProcessConsumer::ResetStatistics(void)
0x180025afd  lea     r11, [rsp+168h+var_8]
0x180025b05  mov     rax, rbx
0x180025b08  mov     rbx, [r11+10h]
0x180025b0c  movaps  xmm6, xmmword ptr [r11-10h]
0x180025b11  movaps  xmm7, xmmword ptr [r11-20h]
0x180025b16  movaps  xmm8, xmmword ptr [r11-30h]
0x180025b1b  movaps  xmm9, xmmword ptr [r11-40h]
0x180025b20  movaps  xmm10, xmmword ptr [r11-50h]
0x180025b25  movaps  xmm11, xmmword ptr [r11-60h]
0x180025b2a  movaps  xmm12, xmmword ptr [r11-70h]
0x180025b2f  mov     rsp, r11
0x180025b32  pop     rdi
0x180025b33  retn
```
