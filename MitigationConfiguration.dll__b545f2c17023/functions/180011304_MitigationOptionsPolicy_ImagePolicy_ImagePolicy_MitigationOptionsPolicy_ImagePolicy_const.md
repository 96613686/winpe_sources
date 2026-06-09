# MitigationOptionsPolicy::ImagePolicy::ImagePolicy(MitigationOptionsPolicy::ImagePolicy const &)

- ea: `0x180011304`
- end: `0x180011850`
- name: `??0ImagePolicy@MitigationOptionsPolicy@@QEAA@AEBV01@@Z`
- size: `1356`
- prototype: `MitigationOptionsPolicy::ImagePolicy *__fastcall(MitigationOptionsPolicy::ImagePolicy *this, const struct MitigationOptionsPolicy::ImagePolicy *)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180011028`
- `0x1800127a8`

## callees

- `0x180010634`
- `0x180010750`
- `0x180011304`

## pseudocode

```c
MitigationOptionsPolicy::ImagePolicy *__fastcall MitigationOptionsPolicy::ImagePolicy::ImagePolicy(
        MitigationOptionsPolicy::ImagePolicy *this,
        const struct MitigationOptionsPolicy::ImagePolicy *a2)
{
  __int64 v4; // r8
  __int64 v5; // r8
  __int64 v6; // r8
  __int64 v7; // r8
  __int64 v8; // r8
  __int64 v9; // r8
  __int64 v10; // r8
  __int64 v11; // r8
  __int64 v12; // r8
  __int64 v13; // r8
  __int64 v14; // r8
  _OWORD *v15; // rax
  _OWORD *v16; // rcx
  __int64 v17; // rdx
  __int64 v18; // r8
  _OWORD *v19; // rax
  _OWORD *v20; // rcx
  __int64 v21; // r8
  __int64 v22; // r8
  __int64 v23; // r8
  __int64 v24; // r8
  __int64 v25; // r8

  std::wstring::wstring((__int64)this, (__int64)a2);
  LOBYTE(v4) = *((_BYTE *)a2 + 72);
  MitigationOptionsPolicy::Policy::Policy((char *)this + 32, (char *)a2 + 40, v4);
  *((_QWORD *)this + 4) = &MitigationOptionsPolicy::AslrPolicy::`vftable';
  *((_OWORD *)this + 5) = *((_OWORD *)a2 + 5);
  *((_QWORD *)this + 12) = *((_QWORD *)a2 + 12);
  *(_OWORD *)((char *)this + 104) = *(_OWORD *)((char *)a2 + 104);
  *((_QWORD *)this + 15) = *((_QWORD *)a2 + 15);
  LOBYTE(v5) = *((_BYTE *)a2 + 168);
  MitigationOptionsPolicy::Policy::Policy((char *)this + 128, (char *)a2 + 136, v5);
  *((_QWORD *)this + 16) = &MitigationOptionsPolicy::DataExecutionPolicy::`vftable';
  *((_QWORD *)this + 22) = *((_QWORD *)a2 + 22);
  *((_QWORD *)this + 23) = *((_QWORD *)a2 + 23);
  LOBYTE(v6) = *((_BYTE *)a2 + 232);
  MitigationOptionsPolicy::Policy::Policy((char *)this + 192, (char *)a2 + 200, v6);
  *((_QWORD *)this + 24) = &MitigationOptionsPolicy::HandlePolicy::`vftable';
  *((_QWORD *)this + 30) = *((_QWORD *)a2 + 30);
  *((_QWORD *)this + 31) = *((_QWORD *)a2 + 31);
  LOBYTE(v7) = *((_BYTE *)a2 + 296);
  MitigationOptionsPolicy::Policy::Policy((char *)this + 256, (char *)a2 + 264, v7);
  *((_QWORD *)this + 32) = &MitigationOptionsPolicy::SysCallPolicy::`vftable';
  *((_OWORD *)this + 19) = *((_OWORD *)a2 + 19);
  *((_OWORD *)this + 20) = *((_OWORD *)a2 + 20);
  LOBYTE(v8) = *((_BYTE *)a2 + 376);
  MitigationOptionsPolicy::Policy::Policy((char *)this + 336, (char *)a2 + 344, v8);
  *((_QWORD *)this + 42) = &MitigationOptionsPolicy::ExtensionPointPolicy::`vftable';
  *((_QWORD *)this + 48) = *((_QWORD *)a2 + 48);
  *((_QWORD *)this + 49) = *((_QWORD *)a2 + 49);
  LOBYTE(v9) = *((_BYTE *)a2 + 440);
  MitigationOptionsPolicy::Policy::Policy((char *)this + 400, (char *)a2 + 408, v9);
  *((_QWORD *)this + 50) = &MitigationOptionsPolicy::DynamicCodePolicy::`vftable';
  *((_QWORD *)this + 56) = *((_QWORD *)a2 + 56);
  *((_QWORD *)this + 57) = *((_QWORD *)a2 + 57);
  LOBYTE(v10) = *((_BYTE *)a2 + 504);
  MitigationOptionsPolicy::Policy::Policy((char *)this + 464, (char *)a2 + 472, v10);
  *((_QWORD *)this + 58) = &MitigationOptionsPolicy::ControlFlowGuardPolicy::`vftable';
  *((_OWORD *)this + 32) = *((_OWORD *)a2 + 32);
  *((_OWORD *)this + 33) = *((_OWORD *)a2 + 33);
  LOBYTE(v11) = *((_BYTE *)a2 + 584);
  MitigationOptionsPolicy::Policy::Policy((char *)this + 544, (char *)a2 + 552, v11);
  *((_QWORD *)this + 68) = &MitigationOptionsPolicy::BinarySigningPolicy::`vftable';
  *((_OWORD *)this + 37) = *((_OWORD *)a2 + 37);
  *((_OWORD *)this + 38) = *((_OWORD *)a2 + 38);
  LOBYTE(v12) = *((_BYTE *)a2 + 664);
  MitigationOptionsPolicy::Policy::Policy((char *)this + 624, (char *)a2 + 632, v12);
  *((_QWORD *)this + 78) = &MitigationOptionsPolicy::FontPolicy::`vftable';
  *((_QWORD *)this + 84) = *((_QWORD *)a2 + 84);
  *((_QWORD *)this + 85) = *((_QWORD *)a2 + 85);
  LOBYTE(v13) = *((_BYTE *)a2 + 728);
  MitigationOptionsPolicy::Policy::Policy((char *)this + 688, (char *)a2 + 696, v13);
  *((_QWORD *)this + 86) = &MitigationOptionsPolicy::ImageLoadPolicy::`vftable';
  *((_OWORD *)this + 46) = *((_OWORD *)a2 + 46);
  *((_QWORD *)this + 94) = *((_QWORD *)a2 + 94);
  *(_OWORD *)((char *)this + 760) = *(_OWORD *)((char *)a2 + 760);
  *((_QWORD *)this + 97) = *((_QWORD *)a2 + 97);
  LOBYTE(v14) = *((_BYTE *)a2 + 824);
  MitigationOptionsPolicy::Policy::Policy((char *)this + 784, (char *)a2 + 792, v14);
  *((_QWORD *)this + 98) = &MitigationOptionsPolicy::PayloadRestrictionPolicy::`vftable';
  v15 = (_OWORD *)((char *)this + 832);
  v16 = (_OWORD *)((char *)a2 + 832);
  v17 = 8;
  v18 = 8;
  do
  {
    *v15 = *v16;
    v15[1] = v16[1];
    v15[2] = v16[2];
    v15[3] = v16[3];
    v15[4] = v16[4];
    v15[5] = v16[5];
    v15[6] = v16[6];
    v15[7] = v16[7];
    v15 += 8;
    v16 += 8;
    --v18;
  }
  while ( v18 );
  *v15 = *v16;
  v15[1] = v16[1];
  v15[2] = v16[2];
  v19 = (_OWORD *)((char *)this + 1904);
  v20 = (_OWORD *)((char *)a2 + 1904);
  do
  {
    *v19 = *v20;
    v19[1] = v20[1];
    v19[2] = v20[2];
    v19[3] = v20[3];
    v19[4] = v20[4];
    v19[5] = v20[5];
    v19[6] = v20[6];
    v19[7] = v20[7];
    v19 += 8;
    v20 += 8;
    --v17;
  }
  while ( v17 );
  *v19 = *v20;
  v19[1] = v20[1];
  v19[2] = v20[2];
  LOBYTE(v18) = *((_BYTE *)a2 + 3016);
  MitigationOptionsPolicy::Policy::Policy((char *)this + 2976, (char *)a2 + 2984, v18);
  *((_QWORD *)this + 372) = &MitigationOptionsPolicy::SehopPolicy::`vftable';
  *((_QWORD *)this + 378) = *((_QWORD *)a2 + 378);
  *((_QWORD *)this + 379) = *((_QWORD *)a2 + 379);
  LOBYTE(v21) = *((_BYTE *)a2 + 3080);
  MitigationOptionsPolicy::Policy::Policy((char *)this + 3040, (char *)a2 + 3048, v21);
  *((_QWORD *)this + 380) = &MitigationOptionsPolicy::HeapPolicy::`vftable';
  *((_QWORD *)this + 386) = *((_QWORD *)a2 + 386);
  *((_QWORD *)this + 387) = *((_QWORD *)a2 + 387);
  LOBYTE(v22) = *((_BYTE *)a2 + 3144);
  MitigationOptionsPolicy::Policy::Policy((char *)this + 3104, (char *)a2 + 3112, v22);
  *((_QWORD *)this + 388) = &MitigationOptionsPolicy::ChildProcessPolicy::`vftable';
  *((_QWORD *)this + 394) = *((_QWORD *)a2 + 394);
  *((_QWORD *)this + 395) = *((_QWORD *)a2 + 395);
  LOBYTE(v23) = *((_BYTE *)a2 + 3208);
  MitigationOptionsPolicy::Policy::Policy((char *)this + 3168, (char *)a2 + 3176, v23);
  *((_QWORD *)this + 396) = &MitigationOptionsPolicy::UserShadowStackPolicy::`vftable';
  *((_OWORD *)this + 201) = *((_OWORD *)a2 + 201);
  *((_QWORD *)this + 404) = *((_QWORD *)a2 + 404);
  *(_OWORD *)((char *)this + 3240) = *(_OWORD *)((char *)a2 + 3240);
  *((_QWORD *)this + 407) = *((_QWORD *)a2 + 407);
  LOBYTE(v24) = *((_BYTE *)a2 + 3304);
  MitigationOptionsPolicy::Policy::Policy((char *)this + 3264, (char *)a2 + 3272, v24);
  *((_QWORD *)this + 408) = &MitigationOptionsPolicy::UserPointerAuthPolicy::`vftable';
  *((_QWORD *)this + 414) = *((_QWORD *)a2 + 414);
  *((_QWORD *)this + 415) = *((_QWORD *)a2 + 415);
  LOBYTE(v25) = *((_BYTE *)a2 + 3368);
  MitigationOptionsPolicy::Policy::Policy((char *)this + 3328, (char *)a2 + 3336, v25);
  *((_QWORD *)this + 416) = &MitigationOptionsPolicy::RedirectionTrustPolicy::`vftable';
  *((_QWORD *)this + 422) = *((_QWORD *)a2 + 422);
  *((_QWORD *)this + 423) = *((_QWORD *)a2 + 423);
  return this;
}

```

## disassembly

```asm
0x180011304  mov     [rsp+arg_8], rbx
0x180011309  mov     [rsp+arg_10], rsi
0x18001130e  mov     [rsp+arg_0], rcx
0x180011313  push    rdi
0x180011314  sub     rsp, 20h
0x180011318  mov     rdi, rdx
0x18001131b  mov     rsi, rcx
0x18001131e  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180011323  nop
0x180011324  lea     rdx, [rdi+28h]
0x180011328  mov     r8b, [rdi+48h]
0x18001132c  lea     rcx, [rsi+20h]
0x180011330  call    ??0Policy@MitigationOptionsPolicy@@QEAA@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_N@Z; MitigationOptionsPolicy::Policy::Policy(std::wstring const &,bool)
0x180011335  lea     rax, ??_7AslrPolicy@MitigationOptionsPolicy@@6B@; const MitigationOptionsPolicy::AslrPolicy::`vftable'
0x18001133c  mov     [rsi+20h], rax
0x180011340  movups  xmm0, xmmword ptr [rdi+50h]
0x180011344  movups  xmmword ptr [rsi+50h], xmm0
0x180011348  movsd   xmm1, qword ptr [rdi+60h]
0x18001134d  movsd   qword ptr [rsi+60h], xmm1
0x180011352  movups  xmm0, xmmword ptr [rdi+68h]
0x180011356  movups  xmmword ptr [rsi+68h], xmm0
0x18001135a  movsd   xmm1, qword ptr [rdi+78h]
0x18001135f  movsd   qword ptr [rsi+78h], xmm1
0x180011364  lea     rbx, [rsi+80h]
0x18001136b  lea     rdx, [rdi+88h]
0x180011372  mov     r8b, [rdi+0A8h]
0x180011379  mov     rcx, rbx
0x18001137c  call    ??0Policy@MitigationOptionsPolicy@@QEAA@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_N@Z; MitigationOptionsPolicy::Policy::Policy(std::wstring const &,bool)
0x180011381  lea     rax, ??_7DataExecutionPolicy@MitigationOptionsPolicy@@6B@; const MitigationOptionsPolicy::DataExecutionPolicy::`vftable'
0x180011388  mov     [rbx], rax
0x18001138b  mov     rax, [rdi+0B0h]
0x180011392  mov     [rbx+30h], rax
0x180011396  mov     rax, [rdi+0B8h]
0x18001139d  mov     [rbx+38h], rax
0x1800113a1  lea     rbx, [rsi+0C0h]
0x1800113a8  lea     rdx, [rdi+0C8h]
0x1800113af  mov     r8b, [rdi+0E8h]
0x1800113b6  mov     rcx, rbx
0x1800113b9  call    ??0Policy@MitigationOptionsPolicy@@QEAA@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_N@Z; MitigationOptionsPolicy::Policy::Policy(std::wstring const &,bool)
0x1800113be  lea     rax, ??_7HandlePolicy@MitigationOptionsPolicy@@6B@; const MitigationOptionsPolicy::HandlePolicy::`vftable'
0x1800113c5  mov     [rbx], rax
0x1800113c8  mov     rax, [rdi+0F0h]
0x1800113cf  mov     [rbx+30h], rax
0x1800113d3  mov     rax, [rdi+0F8h]
0x1800113da  mov     [rbx+38h], rax
0x1800113de  lea     rbx, [rsi+100h]
0x1800113e5  lea     rdx, [rdi+108h]
0x1800113ec  mov     r8b, [rdi+128h]
0x1800113f3  mov     rcx, rbx
0x1800113f6  call    ??0Policy@MitigationOptionsPolicy@@QEAA@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_N@Z; MitigationOptionsPolicy::Policy::Policy(std::wstring const &,bool)
0x1800113fb  lea     rax, ??_7SysCallPolicy@MitigationOptionsPolicy@@6B@; const MitigationOptionsPolicy::SysCallPolicy::`vftable'
0x180011402  mov     [rbx], rax
0x180011405  movups  xmm0, xmmword ptr [rdi+130h]
0x18001140c  movdqu  xmmword ptr [rbx+30h], xmm0
0x180011411  movups  xmm1, xmmword ptr [rdi+140h]
0x180011418  movdqu  xmmword ptr [rbx+40h], xmm1
0x18001141d  lea     rbx, [rsi+150h]
0x180011424  lea     rdx, [rdi+158h]
0x18001142b  mov     r8b, [rdi+178h]
0x180011432  mov     rcx, rbx
0x180011435  call    ??0Policy@MitigationOptionsPolicy@@QEAA@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_N@Z; MitigationOptionsPolicy::Policy::Policy(std::wstring const &,bool)
0x18001143a  lea     rax, ??_7ExtensionPointPolicy@MitigationOptionsPolicy@@6B@; const MitigationOptionsPolicy::ExtensionPointPolicy::`vftable'
0x180011441  mov     [rbx], rax
0x180011444  mov     rax, [rdi+180h]
0x18001144b  mov     [rbx+30h], rax
0x18001144f  mov     rax, [rdi+188h]
0x180011456  mov     [rbx+38h], rax
0x18001145a  lea     rbx, [rsi+190h]
0x180011461  lea     rdx, [rdi+198h]
0x180011468  mov     r8b, [rdi+1B8h]
0x18001146f  mov     rcx, rbx
0x180011472  call    ??0Policy@MitigationOptionsPolicy@@QEAA@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_N@Z; MitigationOptionsPolicy::Policy::Policy(std::wstring const &,bool)
0x180011477  lea     rax, ??_7DynamicCodePolicy@MitigationOptionsPolicy@@6B@; const MitigationOptionsPolicy::DynamicCodePolicy::`vftable'
0x18001147e  mov     [rbx], rax
0x180011481  mov     rax, [rdi+1C0h]
0x180011488  mov     [rbx+30h], rax
0x18001148c  mov     rax, [rdi+1C8h]
0x180011493  mov     [rbx+38h], rax
0x180011497  lea     rbx, [rsi+1D0h]
0x18001149e  lea     rdx, [rdi+1D8h]
0x1800114a5  mov     r8b, [rdi+1F8h]
0x1800114ac  mov     rcx, rbx
0x1800114af  call    ??0Policy@MitigationOptionsPolicy@@QEAA@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_N@Z; MitigationOptionsPolicy::Policy::Policy(std::wstring const &,bool)
0x1800114b4  lea     rax, ??_7ControlFlowGuardPolicy@MitigationOptionsPolicy@@6B@; const MitigationOptionsPolicy::ControlFlowGuardPolicy::`vftable'
0x1800114bb  mov     [rbx], rax
0x1800114be  movups  xmm0, xmmword ptr [rdi+200h]
0x1800114c5  movdqu  xmmword ptr [rbx+30h], xmm0
0x1800114ca  movups  xmm1, xmmword ptr [rdi+210h]
0x1800114d1  movdqu  xmmword ptr [rbx+40h], xmm1
0x1800114d6  lea     rbx, [rsi+220h]
0x1800114dd  lea     rdx, [rdi+228h]
0x1800114e4  mov     r8b, [rdi+248h]
0x1800114eb  mov     rcx, rbx
0x1800114ee  call    ??0Policy@MitigationOptionsPolicy@@QEAA@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_N@Z; MitigationOptionsPolicy::Policy::Policy(std::wstring const &,bool)
0x1800114f3  lea     rax, ??_7BinarySigningPolicy@MitigationOptionsPolicy@@6B@; const MitigationOptionsPolicy::BinarySigningPolicy::`vftable'
0x1800114fa  mov     [rbx], rax
0x1800114fd  movups  xmm0, xmmword ptr [rdi+250h]
0x180011504  movdqu  xmmword ptr [rbx+30h], xmm0
0x180011509  movups  xmm1, xmmword ptr [rdi+260h]
0x180011510  movdqu  xmmword ptr [rbx+40h], xmm1
0x180011515  lea     rbx, [rsi+270h]
0x18001151c  lea     rdx, [rdi+278h]
0x180011523  mov     r8b, [rdi+298h]
0x18001152a  mov     rcx, rbx
0x18001152d  call    ??0Policy@MitigationOptionsPolicy@@QEAA@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_N@Z; MitigationOptionsPolicy::Policy::Policy(std::wstring const &,bool)
0x180011532  lea     rax, ??_7FontPolicy@MitigationOptionsPolicy@@6B@; const MitigationOptionsPolicy::FontPolicy::`vftable'
0x180011539  mov     [rbx], rax
0x18001153c  mov     rax, [rdi+2A0h]
0x180011543  mov     [rbx+30h], rax
0x180011547  mov     rax, [rdi+2A8h]
0x18001154e  mov     [rbx+38h], rax
0x180011552  lea     rbx, [rsi+2B0h]
0x180011559  lea     rdx, [rdi+2B8h]
0x180011560  mov     r8b, [rdi+2D8h]
0x180011567  mov     rcx, rbx
0x18001156a  call    ??0Policy@MitigationOptionsPolicy@@QEAA@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_N@Z; MitigationOptionsPolicy::Policy::Policy(std::wstring const &,bool)
0x18001156f  lea     rax, ??_7ImageLoadPolicy@MitigationOptionsPolicy@@6B@; const MitigationOptionsPolicy::ImageLoadPolicy::`vftable'
0x180011576  mov     [rbx], rax
0x180011579  movups  xmm0, xmmword ptr [rdi+2E0h]
0x180011580  movups  xmmword ptr [rbx+30h], xmm0
0x180011584  movsd   xmm1, qword ptr [rdi+2F0h]
0x18001158c  movsd   qword ptr [rbx+40h], xmm1
0x180011591  movups  xmm0, xmmword ptr [rdi+2F8h]
0x180011598  movups  xmmword ptr [rbx+48h], xmm0
0x18001159c  movsd   xmm1, qword ptr [rdi+308h]
0x1800115a4  movsd   qword ptr [rbx+58h], xmm1
0x1800115a9  lea     rbx, [rsi+310h]
0x1800115b0  lea     rdx, [rdi+318h]
0x1800115b7  mov     r8b, [rdi+338h]
0x1800115be  mov     rcx, rbx
0x1800115c1  call    ??0Policy@MitigationOptionsPolicy@@QEAA@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_N@Z; MitigationOptionsPolicy::Policy::Policy(std::wstring const &,bool)
0x1800115c6  lea     rax, ??_7PayloadRestrictionPolicy@MitigationOptionsPolicy@@6B@; const MitigationOptionsPolicy::PayloadRestrictionPolicy::`vftable'
0x1800115cd  mov     [rbx], rax
0x1800115d0  lea     rax, [rbx+30h]
0x1800115d4  lea     rcx, [rdi+340h]
0x1800115db  mov     edx, 8
0x1800115e0  mov     r8d, edx
0x1800115e3  lea     r9d, [rdx+78h]
0x1800115e7  movups  xmm0, xmmword ptr [rcx]
0x1800115ea  movups  xmmword ptr [rax], xmm0
0x1800115ed  movups  xmm1, xmmword ptr [rcx+10h]
0x1800115f1  movups  xmmword ptr [rax+10h], xmm1
0x1800115f5  movups  xmm0, xmmword ptr [rcx+20h]
0x1800115f9  movups  xmmword ptr [rax+20h], xmm0
0x1800115fd  movups  xmm1, xmmword ptr [rcx+30h]
0x180011601  movups  xmmword ptr [rax+30h], xmm1
0x180011605  movups  xmm0, xmmword ptr [rcx+40h]
0x180011609  movups  xmmword ptr [rax+40h], xmm0
0x18001160d  movups  xmm1, xmmword ptr [rcx+50h]
0x180011611  movups  xmmword ptr [rax+50h], xmm1
0x180011615  movups  xmm0, xmmword ptr [rcx+60h]
0x180011619  movups  xmmword ptr [rax+60h], xmm0
0x18001161d  movups  xmm1, xmmword ptr [rcx+70h]
0x180011621  movups  xmmword ptr [rax+70h], xmm1
0x180011625  add     rax, r9
0x180011628  add     rcx, r9
0x18001162b  sub     r8, 1
0x18001162f  jnz     short loc_1800115E7
0x180011631  movups  xmm0, xmmword ptr [rcx]
0x180011634  movups  xmmword ptr [rax], xmm0
0x180011637  movups  xmm1, xmmword ptr [rcx+10h]
0x18001163b  movups  xmmword ptr [rax+10h], xmm1
0x18001163f  movups  xmm0, xmmword ptr [rcx+20h]
0x180011643  movups  xmmword ptr [rax+20h], xmm0
0x180011647  lea     rax, [rbx+460h]
0x18001164e  lea     rcx, [rdi+770h]
0x180011655  movups  xmm0, xmmword ptr [rcx]
0x180011658  movups  xmmword ptr [rax], xmm0
0x18001165b  movups  xmm1, xmmword ptr [rcx+10h]
0x18001165f  movups  xmmword ptr [rax+10h], xmm1
0x180011663  movups  xmm0, xmmword ptr [rcx+20h]
0x180011667  movups  xmmword ptr [rax+20h], xmm0
0x18001166b  movups  xmm1, xmmword ptr [rcx+30h]
0x18001166f  movups  xmmword ptr [rax+30h], xmm1
0x180011673  movups  xmm0, xmmword ptr [rcx+40h]
0x180011677  movups  xmmword ptr [rax+40h], xmm0
0x18001167b  movups  xmm1, xmmword ptr [rcx+50h]
0x18001167f  movups  xmmword ptr [rax+50h], xmm1
0x180011683  movups  xmm0, xmmword ptr [rcx+60h]
0x180011687  movups  xmmword ptr [rax+60h], xmm0
0x18001168b  movups  xmm1, xmmword ptr [rcx+70h]
0x18001168f  movups  xmmword ptr [rax+70h], xmm1
0x180011693  add     rax, r9
0x180011696  add     rcx, r9
0x180011699  sub     rdx, 1
0x18001169d  jnz     short loc_180011655
0x18001169f  movups  xmm0, xmmword ptr [rcx]
0x1800116a2  movups  xmmword ptr [rax], xmm0
0x1800116a5  movups  xmm1, xmmword ptr [rcx+10h]
0x1800116a9  movups  xmmword ptr [rax+10h], xmm1
0x1800116ad  movups  xmm0, xmmword ptr [rcx+20h]
0x1800116b1  movups  xmmword ptr [rax+20h], xmm0
0x1800116b5  lea     rbx, [rsi+0BA0h]
0x1800116bc  lea     rdx, [rdi+0BA8h]
0x1800116c3  mov     r8b, [rdi+0BC8h]
0x1800116ca  mov     rcx, rbx
0x1800116cd  call    ??0Policy@MitigationOptionsPolicy@@QEAA@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_N@Z; MitigationOptionsPolicy::Policy::Policy(std::wstring const &,bool)
0x1800116d2  lea     rax, ??_7SehopPolicy@MitigationOptionsPolicy@@6B@; const MitigationOptionsPolicy::SehopPolicy::`vftable'
0x1800116d9  mov     [rbx], rax
0x1800116dc  mov     rax, [rdi+0BD0h]
0x1800116e3  mov     [rbx+30h], rax
0x1800116e7  mov     rax, [rdi+0BD8h]
0x1800116ee  mov     [rbx+38h], rax
0x1800116f2  lea     rbx, [rsi+0BE0h]
0x1800116f9  lea     rdx, [rdi+0BE8h]
0x180011700  mov     r8b, [rdi+0C08h]
0x180011707  mov     rcx, rbx
0x18001170a  call    ??0Policy@MitigationOptionsPolicy@@QEAA@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_N@Z; MitigationOptionsPolicy::Policy::Policy(std::wstring const &,bool)
0x18001170f  lea     rax, ??_7HeapPolicy@MitigationOptionsPolicy@@6B@; const MitigationOptionsPolicy::HeapPolicy::`vftable'
0x180011716  mov     [rbx], rax
0x180011719  mov     rax, [rdi+0C10h]
0x180011720  mov     [rbx+30h], rax
0x180011724  mov     rax, [rdi+0C18h]
0x18001172b  mov     [rbx+38h], rax
0x18001172f  lea     rbx, [rsi+0C20h]
0x180011736  lea     rdx, [rdi+0C28h]
0x18001173d  mov     r8b, [rdi+0C48h]
0x180011744  mov     rcx, rbx
0x180011747  call    ??0Policy@MitigationOptionsPolicy@@QEAA@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_N@Z; MitigationOptionsPolicy::Policy::Policy(std::wstring const &,bool)
0x18001174c  lea     rax, ??_7ChildProcessPolicy@MitigationOptionsPolicy@@6B@; const MitigationOptionsPolicy::ChildProcessPolicy::`vftable'
0x180011753  mov     [rbx], rax
0x180011756  mov     rax, [rdi+0C50h]
0x18001175d  mov     [rbx+30h], rax
0x180011761  mov     rax, [rdi+0C58h]
0x180011768  mov     [rbx+38h], rax
0x18001176c  lea     rbx, [rsi+0C60h]
0x180011773  lea     rdx, [rdi+0C68h]
0x18001177a  mov     r8b, [rdi+0C88h]
0x180011781  mov     rcx, rbx
0x180011784  call    ??0Policy@MitigationOptionsPolicy@@QEAA@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_N@Z; MitigationOptionsPolicy::Policy::Policy(std::wstring const &,bool)
0x180011789  lea     rax, ??_7UserShadowStackPolicy@MitigationOptionsPolicy@@6B@; const MitigationOptionsPolicy::UserShadowStackPolicy::`vftable'
0x180011790  mov     [rbx], rax
0x180011793  movups  xmm0, xmmword ptr [rdi+0C90h]
0x18001179a  movups  xmmword ptr [rbx+30h], xmm0
0x18001179e  movsd   xmm1, qword ptr [rdi+0CA0h]
0x1800117a6  movsd   qword ptr [rbx+40h], xmm1
0x1800117ab  movups  xmm0, xmmword ptr [rdi+0CA8h]
0x1800117b2  movups  xmmword ptr [rbx+48h], xmm0
0x1800117b6  movsd   xmm1, qword ptr [rdi+0CB8h]
0x1800117be  movsd   qword ptr [rbx+58h], xmm1
0x1800117c3  lea     rbx, [rsi+0CC0h]
0x1800117ca  lea     rdx, [rdi+0CC8h]
0x1800117d1  mov     r8b, [rdi+0CE8h]
0x1800117d8  mov     rcx, rbx
0x1800117db  call    ??0Policy@MitigationOptionsPolicy@@QEAA@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_N@Z; MitigationOptionsPolicy::Policy::Policy(std::wstring const &,bool)
0x1800117e0  lea     rax, ??_7UserPointerAuthPolicy@MitigationOptionsPolicy@@6B@; const MitigationOptionsPolicy::UserPointerAuthPolicy::`vftable'
0x1800117e7  mov     [rbx], rax
0x1800117ea  mov     rax, [rdi+0CF0h]
0x1800117f1  mov     [rbx+30h], rax
0x1800117f5  mov     rax, [rdi+0CF8h]
0x1800117fc  mov     [rbx+38h], rax
0x180011800  lea     rbx, [rsi+0D00h]
0x180011807  lea     rdx, [rdi+0D08h]
0x18001180e  mov     r8b, [rdi+0D28h]
0x180011815  mov     rcx, rbx
0x180011818  call    ??0Policy@MitigationOptionsPolicy@@QEAA@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_N@Z; MitigationOptionsPolicy::Policy::Policy(std::wstring const &,bool)
0x18001181d  lea     rax, ??_7RedirectionTrustPolicy@MitigationOptionsPolicy@@6B@; const MitigationOptionsPolicy::RedirectionTrustPolicy::`vftable'
0x180011824  mov     [rbx], rax
0x180011827  mov     rax, [rdi+0D30h]
0x18001182e  mov     [rbx+30h], rax
0x180011832  mov     rax, [rdi+0D38h]
0x180011839  mov     [rbx+38h], rax
0x18001183d  mov     rax, rsi
0x180011840  mov     rbx, [rsp+28h+arg_8]
0x180011845  mov     rsi, [rsp+28h+arg_10]
0x18001184a  add     rsp, 20h
0x18001184e  pop     rdi
0x18001184f  retn
```
