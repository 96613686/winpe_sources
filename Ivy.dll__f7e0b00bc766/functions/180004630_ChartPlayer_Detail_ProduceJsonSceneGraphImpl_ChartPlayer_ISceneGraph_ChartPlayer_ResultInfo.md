# ChartPlayer::Detail::ProduceJsonSceneGraphImpl(ChartPlayer::ISceneGraph &,ChartPlayer::ResultInfo *)

- ea: `0x180004630`
- end: `0x180004ea0`
- name: `?ProduceJsonSceneGraphImpl@Detail@ChartPlayer@@YAPEAUIString@2@AEAUISceneGraph@2@PEAUResultInfo@2@@Z`
- size: `2160`
- prototype: `struct ChartPlayer::IString *__fastcall(ChartPlayer::Detail *__hidden this, struct ChartPlayer::ISceneGraph *, struct ChartPlayer::ResultInfo *)`
- caller_count: `1`
- callee_count: `23`
- tags: `registry_config`

## callers

- `0x18013c358`

## callees

- `0x180001224`
- `0x180001364`
- `0x18000218c`
- `0x18000440c`
- `0x180004630`
- `0x180005b30`
- `0x180005c90`
- `0x1800066d4`
- `0x18000675c`
- `0x1800067c4`
- `0x180006af8`
- `0x1800076ec`
- `0x180008354`
- `0x180009070`
- `0x180009174`
- `0x180009200`
- `0x1801290b0`
- `0x1801292bc`
- `0x180129300`
- `0x18016c7b0`
- `0x18016cccc`
- `0x18016ea3e`
- `0x18016eaf0`

## import_xrefs

- `MSVCP140!?_Xbad_alloc@std@@YAXXZ` at `0x180004726`
- `MSVCP140!?_Xbad_alloc@std@@YAXXZ` at `0x180004726`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x18000471b`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x18000471b`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180004c26`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180004cb7`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180004c26`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180004cb7`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x180004c1f`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x180004c1f`

## string_xrefs

- `0x180004e17`: `ChartPlayer client didn't return a Deleter.`
- `0x180004e43`: `ChartPlayer client didn't return a Deleter.`

## pseudocode

```c
// Hidden C++ exception states: #wind=29
struct ChartPlayer::IString *__fastcall ChartPlayer::Detail::ProduceJsonSceneGraphImpl(
        ChartPlayer::Detail *this,
        struct ChartPlayer::ISceneGraph *a2,
        struct ChartPlayer::ResultInfo *a3)
{
  __int64 v5; // rax
  _QWORD *v6; // rax
  __int64 v7; // rbx
  __int64 v8; // rbx
  __int64 v9; // r8
  __int64 v10; // r8
  __int64 v11; // r8
  __int64 v12; // rdi
  __int64 v13; // r8
  __int64 v14; // rbx
  __int64 v15; // rdx
  __int64 v16; // rcx
  __int64 v17; // rax
  void *v18; // rcx
  struct ChartPlayer::IString *result; // rax
  _QWORD *v20; // rax
  __int64 *v21; // rax
  __int64 v22; // r14
  void *v23; // rbx
  unsigned int (__fastcall *v24)(ChartPlayer::Detail *); // rdi
  unsigned int v25; // ebx
  void (__fastcall ***v26)(_QWORD, __int64); // rcx
  const ChartPlayer::ChartPlayerError *v27; // rcx
  void *v28; // [rsp+30h] [rbp-288h] BYREF
  __int64 *v29; // [rsp+38h] [rbp-280h]
  __int128 v30; // [rsp+40h] [rbp-278h] BYREF
  void (*v31)(void); // [rsp+50h] [rbp-268h] BYREF
  __int64 v32; // [rsp+58h] [rbp-260h]
  ChartPlayer::Detail **v33; // [rsp+60h] [rbp-258h]
  int v34; // [rsp+68h] [rbp-250h]
  struct ChartPlayer::ISceneGraph *v35; // [rsp+70h] [rbp-248h]
  _BYTE v36[16]; // [rsp+78h] [rbp-240h] BYREF
  _BYTE v37[16]; // [rsp+88h] [rbp-230h] BYREF
  const ChartPlayer::ChartPlayerError *v38; // [rsp+98h] [rbp-220h] BYREF
  const std::exception *v39; // [rsp+A0h] [rbp-218h] BYREF
  _BYTE pExceptionObject[32]; // [rsp+A8h] [rbp-210h] BYREF
  _BYTE v41[32]; // [rsp+C8h] [rbp-1F0h] BYREF
  _BYTE v42[40]; // [rsp+E8h] [rbp-1D0h] BYREF
  ChartPlayer::Detail *v43; // [rsp+110h] [rbp-1A8h] BYREF
  void (*v44)(void); // [rsp+118h] [rbp-1A0h]
  int v45; // [rsp+120h] [rbp-198h]
  __int16 v46; // [rsp+124h] [rbp-194h]
  char v47; // [rsp+126h] [rbp-192h]
  ChartPlayer::Detail *v48; // [rsp+128h] [rbp-190h]
  __int64 v49; // [rsp+130h] [rbp-188h]
  int v50; // [rsp+138h] [rbp-180h]
  void *Block[2]; // [rsp+140h] [rbp-178h] BYREF
  __int64 v52; // [rsp+150h] [rbp-168h]
  _OWORD v53[2]; // [rsp+160h] [rbp-158h] BYREF
  __int128 v54; // [rsp+180h] [rbp-138h] BYREF
  __int64 v55; // [rsp+190h] [rbp-128h]
  __int64 v56; // [rsp+198h] [rbp-120h]
  _BYTE v57[16]; // [rsp+1A0h] [rbp-118h] BYREF
  __int128 v58; // [rsp+1B0h] [rbp-108h] BYREF
  __int64 v59; // [rsp+1C0h] [rbp-F8h]
  __int64 v60; // [rsp+1C8h] [rbp-F0h]
  _BYTE v61[16]; // [rsp+1D0h] [rbp-E8h] BYREF
  __int128 v62; // [rsp+1E0h] [rbp-D8h] BYREF
  __int64 v63; // [rsp+1F0h] [rbp-C8h]
  __int64 v64; // [rsp+1F8h] [rbp-C0h]
  _BYTE v65[16]; // [rsp+200h] [rbp-B8h] BYREF
  __int128 v66; // [rsp+210h] [rbp-A8h] BYREF
  __int64 v67; // [rsp+220h] [rbp-98h]
  __int64 v68; // [rsp+228h] [rbp-90h]
  _BYTE v69[16]; // [rsp+230h] [rbp-88h] BYREF
  __int128 v70; // [rsp+240h] [rbp-78h] BYREF
  __int64 v71; // [rsp+250h] [rbp-68h]
  __int64 v72; // [rsp+258h] [rbp-60h]
  _BYTE v73[16]; // [rsp+260h] [rbp-58h] BYREF
  __int64 v74; // [rsp+270h] [rbp-48h] BYREF

  v35 = a2;
  v34 = 0;
  v43 = this;
  v5 = (**(__int64 (__fastcall ***)(ChartPlayer::Detail *, struct ChartPlayer::ISceneGraph *, struct ChartPlayer::ResultInfo *))this)(
         this,
         a2,
         a3);
  try
  {
    v44 = (void (*)(void))v5;
    v45 = 0;
    v46 = 0;
    v47 = 0;
    if ( !v5 )
    {
      sub_180001224((__int64)pExceptionObject, 2, (__int64)"ChartPlayer client didn't return a Deleter.");
      throw (ChartPlayer::ChartPlayerError *)pExceptionObject;
    }
    v48 = this;
    v49 = 0;
    v50 = 0;
    *(_OWORD *)Block = 0;
    v52 = 0;
    v49 = *(_QWORD *)sub_180009200(&v28);
    sub_180001364(&v43);
    if ( !v44 )
    {
      sub_180001224((__int64)v41, 2, (__int64)"ChartPlayer client didn't return a Deleter.");
      throw (ChartPlayer::ChartPlayerError *)v41;
    }
    v30 = 0;
    v6 = malloc(0x50u);
    if ( !v6 )
      std::_Xbad_alloc();
    *v6 = v6;
    v6[1] = v6;
    v6[2] = v6;
    *((_WORD *)v6 + 12) = 257;
    *(_QWORD *)&v30 = v6;
    v7 = (*(__int64 (__fastcall **)(ChartPlayer::Detail *))(*(_QWORD *)v48 + 88LL))(v48);
    sub_180001364(&v43);
    v31 = v44;
    v32 = v7;
    v33 = &v43;
    sub_180001364(&v43);
    if ( !v32 )
    {
      sub_180001224((__int64)v42, 2, (__int64)"ChartPlayer client didn't return an IElement.");
      throw (ChartPlayer::ChartPlayerError *)v42;
    }
    sub_18000218C(v36, &v31, &v43);
    if ( !(*(unsigned int (__fastcall **)(ChartPlayer::Detail *))(*(_QWORD *)v48 + 8LL))(v48)
      || (*(unsigned int (__fastcall **)(ChartPlayer::Detail *))(*(_QWORD *)v48 + 8LL))(v48) == 3 )
    {
      v28 = &v62;
      v62 = 0;
      v63 = 0;
      v64 = 0;
      v8 = -1;
      v9 = -1;
      do
        ++v9;
      while ( off_18021D0E0[0][v9] );
      sub_180009070(&v62, off_18021D0E0[0]);
      sub_1801292BC(v65, v36);
      (*(void (__fastcall **)(ChartPlayer::Detail *))(*(_QWORD *)v48 + 80LL))(v48);
      sub_180001364(&v43);
      v28 = &v54;
      v54 = 0;
      v55 = 0;
      v56 = 0;
      v10 = -1;
      do
        ++v10;
      while ( *(_BYTE *)(off_18021D0D8 + v10) );
      sub_180009070(&v54, off_18021D0D8);
      sub_1801290B0(v57);
      (*(void (__fastcall **)(ChartPlayer::Detail *))(*(_QWORD *)v48 + 72LL))(v48);
      sub_180001364(&v43);
      v28 = &v58;
      v58 = 0;
      v59 = 0;
      v60 = 0;
      v11 = -1;
      do
        ++v11;
      while ( *(_BYTE *)(off_18021D0D0 + v11) );
      sub_180009070(&v58, off_18021D0D0);
      sub_1801290B0(v61);
      v28 = &v54;
      v29 = (__int64 *)&v62;
      v12 = sub_1800067C4(v37, &v28);
      v28 = &v66;
      v66 = 0;
      v67 = 0;
      v68 = 0;
      v13 = -1;
      do
        ++v13;
      while ( off_18021D0C8[v13] );
      sub_180009070(&v66, off_18021D0C8);
      sub_180129300(v69, v12);
      (*(void (__fastcall **)(ChartPlayer::Detail *))(*(_QWORD *)v48 + 96LL))(v48);
      sub_180001364(&v43);
      v28 = &v70;
      v70 = 0;
      v71 = 0;
      v72 = 0;
      do
        ++v8;
      while ( off_18021D0C0[0][v8] );
      sub_180009070(&v70, off_18021D0C0[0]);
      sub_1801290B0(v73);
      v28 = &v62;
      v29 = &v74;
      v14 = sub_1800067C4(v53, &v28);
      if ( &v30 != (__int128 *)v14 )
      {
        sub_180008354(&v30);
        v15 = v30;
        *(_QWORD *)&v30 = *(_QWORD *)v14;
        *(_QWORD *)v14 = v15;
        v16 = *((_QWORD *)&v30 + 1);
        *((_QWORD *)&v30 + 1) = *(_QWORD *)(v14 + 8);
        *(_QWORD *)(v14 + 8) = v16;
      }
      sub_1800066D4(v53);
      sub_18016CCCC(&v62, 48, 3, sub_1800028F0);
      sub_1800066D4(v37);
      sub_18016CCCC(&v54, 48, 2, sub_1800028F0);
      if ( Block[0] != Block[1] )
      {
        v17 = sub_18000440C(v53, Block);
        sub_180005B30(&v30, v37, off_18021D0B8, v17);
        sub_1800076EC(v53);
      }
    }
    if ( !(*(unsigned int (__fastcall **)(ChartPlayer::Detail *))(*(_QWORD *)v48 + 8LL))(v48)
      || (*(unsigned int (__fastcall **)(ChartPlayer::Detail *))(*(_QWORD *)v48 + 8LL))(v48) == 3 )
    {
      v20 = (_QWORD *)sub_1801292BC(v37, &v30);
      v53[0] = 0;
      v53[1] = _mm_load_si128((const __m128i *)&xmmword_1801BB7D0);
      LOBYTE(v53[0]) = 0;
      v34 = 3;
      (*(void (__fastcall **)(_QWORD, _OWORD *))(*(_QWORD *)*v20 + 24LL))(*v20, v53);
      v21 = (__int64 *)sub_180005C90(&v28, v53);
      v22 = *v21;
      *v21 = 0;
      v23 = v28;
      if ( v28 )
      {
        sub_180009174((char *)v28 + 16);
        free(v23);
      }
      v28 = (void *)19937;
      sub_180009174(v53);
      sub_18000675C(v37);
      if ( (*(unsigned int (__fastcall **)(ChartPlayer::Detail *))(*(_QWORD *)this + 24LL))(this)
        && (v24 = *(unsigned int (__fastcall **)(ChartPlayer::Detail *))(*(_QWORD *)this + 24LL),
            v25 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v22 + 8LL))(v22),
            v25 >= v24(this)) )
      {
        if ( a2 )
          *(_DWORD *)a2 = 6;
        if ( v22 )
        {
          v26 = (void (__fastcall ***)(_QWORD, __int64))(v22 + *(int *)(*(_QWORD *)(v22 + 8) + 4LL) + 8LL);
          (**v26)(v26, 1);
        }
        sub_1800066D4(v36);
        if ( v32 )
          v31();
        v32 = 19937;
        sub_1800066D4(&v30);
        sub_180006AF8(Block);
        result = 0;
      }
      else
      {
        if ( a2 )
          *(_DWORD *)a2 = 1;
        sub_1800066D4(v36);
        if ( v32 )
          v31();
        v32 = 19937;
        sub_1800066D4(&v30);
        sub_180006AF8(Block);
        result = (struct ChartPlayer::IString *)v22;
      }
    }
    else
    {
      if ( a2 )
        *(_DWORD *)a2 = 4;
      sub_1800066D4(v36);
      if ( v32 )
        v31();
      v32 = 19937;
      sub_1800066D4(&v30);
      v18 = Block[0];
      if ( Block[0] )
      {
        if ( ((v52 - (unsigned __int64)Block[0]) & 0xFFFFFFFFFFFFFFF0uLL) >= 0x1000 )
        {
          v18 = (void *)*((_QWORD *)Block[0] - 1);
          if ( (unsigned __int64)((char *)Block[0] - (char *)v18 - 8) > 0x1F )
            invoke_watson(0, 0, 0, 0, 0);
        }
        free(v18);
      }
      result = 0;
    }
  }
  catch ( const ChartPlayer::ChartPlayerError *v38 )
  {
    if ( v35 )
    {
      v27 = v38;
      *(_DWORD *)v35 = *((_DWORD *)v38 + 6);
      sub_1800043D4(v27);
    }
    return 0;
  }
  catch ( const std::exception *v39 )
  {
    if ( v35 )
    {
      *(_DWORD *)v35 = 0;
      sub_1800043D4(v39);
    }
    return 0;
  }
  catch ( ... )
  {
    if ( v35 )
      *(_DWORD *)v35 = 0;
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x180004630  mov     rax, rsp
0x180004633  mov     [rax+18h], rbx
0x180004637  mov     [rax+20h], rsi
0x18000463b  push    rdi
0x18000463c  push    r12
0x18000463e  push    r13
0x180004640  push    r14
0x180004642  push    r15
0x180004644  sub     rsp, 290h
0x18000464b  movaps  xmmword ptr [rax-38h], xmm6
0x18000464f  mov     rax, cs:__security_cookie
0x180004656  xor     rax, rsp
0x180004659  mov     [rsp+2B8h+var_48], rax
0x180004661  mov     r15, rdx
0x180004664  mov     r12, rcx
0x180004667  mov     [rsp+2B8h+var_248], rdx
0x18000466c  xor     r13d, r13d
0x18000466f  mov     [rsp+2B8h+var_250], r13d
0x180004674  mov     [rsp+2B8h+var_1A8], rcx
0x18000467c  mov     rax, [rcx]
0x18000467f  mov     rax, [rax]
0x180004682  call    cs:__guard_dispatch_icall_fptr
0x180004688  mov     [rsp+2B8h+var_1A0], rax
0x180004690  xor     ecx, ecx
0x180004692  mov     [rsp+2B8h+var_198], ecx
0x180004699  mov     [rsp+2B8h+var_194], cx
0x1800046a1  mov     [rsp+2B8h+var_192], cl
0x1800046a8  test    rax, rax
0x1800046ab  jz      loc_180004E17
0x1800046b1  mov     [rsp+2B8h+var_190], r12
0x1800046b9  mov     [rsp+2B8h+var_188], r13
0x1800046c1  mov     [rsp+2B8h+var_180], r13d
0x1800046c9  xorps   xmm0, xmm0
0x1800046cc  movdqa  xmmword ptr [rsp+2B8h+Block], xmm0
0x1800046d5  mov     [rsp+2B8h+var_168], r13
0x1800046dd  lea     rcx, [rsp+2B8h+var_288]
0x1800046e2  call    sub_180009200
0x1800046e7  mov     rcx, [rax]
0x1800046ea  mov     [rsp+2B8h+var_188], rcx
0x1800046f2  lea     rcx, [rsp+2B8h+var_1A8]
0x1800046fa  call    sub_180001364
0x1800046ff  cmp     [rsp+2B8h+var_1A0], r13
0x180004707  jz      loc_180004E43
0x18000470d  xorps   xmm0, xmm0
0x180004710  movdqu  [rsp+2B8h+var_278], xmm0
0x180004716  mov     ecx, 50h ; 'P'; Size
0x18000471b  call    cs:malloc
0x180004721  test    rax, rax
0x180004724  jnz     short loc_18000472C
0x180004726  call    cs:?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
0x18000472c  mov     [rax], rax
0x18000472f  mov     [rax+8], rax
0x180004733  mov     [rax+10h], rax
0x180004737  mov     word ptr [rax+18h], 101h
0x18000473d  mov     qword ptr [rsp+2B8h+var_278], rax
0x180004742  mov     rcx, [rsp+2B8h+var_190]
0x18000474a  mov     rax, [rcx]
0x18000474d  mov     rax, [rax+58h]
0x180004751  call    cs:__guard_dispatch_icall_fptr
0x180004757  mov     rbx, rax
0x18000475a  lea     rcx, [rsp+2B8h+var_1A8]
0x180004762  call    sub_180001364
0x180004767  mov     rcx, [rsp+2B8h+var_1A0]
0x18000476f  mov     [rsp+2B8h+var_268], rcx
0x180004774  mov     [rsp+2B8h+var_260], rbx
0x180004779  lea     rax, [rsp+2B8h+var_1A8]
0x180004781  mov     [rsp+2B8h+var_258], rax
0x180004786  lea     rcx, [rsp+2B8h+var_1A8]
0x18000478e  call    sub_180001364
0x180004793  cmp     [rsp+2B8h+var_260], r13
0x180004798  jz      loc_180004E71
0x18000479e  lea     r8, [rsp+2B8h+var_1A8]
0x1800047a6  lea     rdx, [rsp+2B8h+var_268]
0x1800047ab  lea     rcx, [rsp+2B8h+var_240]
0x1800047b0  call    sub_18000218C
0x1800047b5  mov     rcx, [rsp+2B8h+var_190]
0x1800047bd  mov     rax, [rcx]
0x1800047c0  mov     rax, [rax+8]
0x1800047c4  call    cs:__guard_dispatch_icall_fptr
0x1800047ca  test    eax, eax
0x1800047cc  jz      short loc_1800047EC
0x1800047ce  mov     rcx, [rsp+2B8h+var_190]
0x1800047d6  mov     rax, [rcx]
0x1800047d9  mov     rax, [rax+8]
0x1800047dd  call    cs:__guard_dispatch_icall_fptr
0x1800047e3  cmp     eax, 3
0x1800047e6  jnz     loc_180004B5E
0x1800047ec  lea     rax, [rsp+2B8h+var_D8]
0x1800047f4  mov     [rsp+2B8h+var_288], rax
0x1800047f9  mov     rdx, cs:off_18021D0E0; "root"
0x180004800  xorps   xmm0, xmm0
0x180004803  movups  [rsp+2B8h+var_D8], xmm0
0x18000480b  mov     [rsp+2B8h+var_C8], r13
0x180004813  mov     [rsp+2B8h+var_C0], r13
0x18000481b  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18000481f  mov     r8, rbx
0x180004822  inc     r8
0x180004825  cmp     [rdx+r8], r13b
0x180004829  jnz     short loc_180004822
0x18000482b  lea     rcx, [rsp+2B8h+var_D8]
0x180004833  call    sub_180009070
0x180004838  lea     rdx, [rsp+2B8h+var_240]
0x18000483d  lea     rcx, [rsp+2B8h+var_B8]
0x180004845  call    sub_1801292BC
0x18000484a  mov     rcx, [rsp+2B8h+var_190]
0x180004852  mov     rax, [rcx]
0x180004855  mov     rax, [rax+50h]
0x180004859  call    cs:__guard_dispatch_icall_fptr
0x18000485f  movaps  xmm6, xmm0
0x180004862  lea     rcx, [rsp+2B8h+var_1A8]
0x18000486a  call    sub_180001364
0x18000486f  lea     rax, [rsp+2B8h+var_138]
0x180004877  mov     [rsp+2B8h+var_288], rax
0x18000487c  mov     rdx, cs:off_18021D0D8
0x180004883  xorps   xmm1, xmm1
0x180004886  movups  [rsp+2B8h+var_138], xmm1
0x18000488e  mov     [rsp+2B8h+var_128], r13
0x180004896  mov     [rsp+2B8h+var_120], r13
0x18000489e  mov     r8, rbx
0x1800048a1  inc     r8
0x1800048a4  cmp     [rdx+r8], r13b
0x1800048a8  jnz     short loc_1800048A1
0x1800048aa  lea     rcx, [rsp+2B8h+var_138]
0x1800048b2  call    sub_180009070
0x1800048b7  xorps   xmm1, xmm1
0x1800048ba  cvtss2sd xmm1, xmm6
0x1800048be  lea     rcx, [rsp+2B8h+var_118]
0x1800048c6  call    sub_1801290B0
0x1800048cb  mov     rcx, [rsp+2B8h+var_190]
0x1800048d3  mov     rax, [rcx]
0x1800048d6  mov     rax, [rax+48h]
0x1800048da  call    cs:__guard_dispatch_icall_fptr
0x1800048e0  movaps  xmm6, xmm0
0x1800048e3  lea     rcx, [rsp+2B8h+var_1A8]
0x1800048eb  call    sub_180001364
0x1800048f0  lea     rax, [rsp+2B8h+var_108]
0x1800048f8  mov     [rsp+2B8h+var_288], rax
0x1800048fd  mov     rdx, cs:off_18021D0D0
0x180004904  xorps   xmm1, xmm1
0x180004907  movups  [rsp+2B8h+var_108], xmm1
0x18000490f  mov     [rsp+2B8h+var_F8], r13
0x180004917  mov     [rsp+2B8h+var_F0], r13
0x18000491f  mov     r8, rbx
0x180004922  inc     r8
0x180004925  cmp     [rdx+r8], r13b
0x180004929  jnz     short loc_180004922
0x18000492b  lea     rcx, [rsp+2B8h+var_108]
0x180004933  call    sub_180009070
0x180004938  xorps   xmm1, xmm1
0x18000493b  cvtss2sd xmm1, xmm6
0x18000493f  lea     rcx, [rsp+2B8h+var_E8]
0x180004947  call    sub_1801290B0
0x18000494c  lea     rax, [rsp+2B8h+var_138]
0x180004954  mov     [rsp+2B8h+var_288], rax
0x180004959  lea     rax, [rsp+2B8h+var_D8]
0x180004961  mov     [rsp+2B8h+var_280], rax
0x180004966  lea     rdx, [rsp+2B8h+var_288]
0x18000496b  lea     rcx, [rsp+2B8h+var_230]
0x180004973  call    sub_1800067C4
0x180004978  mov     rdi, rax
0x18000497b  lea     rax, [rsp+2B8h+var_A8]
0x180004983  mov     [rsp+2B8h+var_288], rax
0x180004988  mov     rdx, cs:off_18021D0C8; "size"
0x18000498f  xorps   xmm0, xmm0
0x180004992  movups  [rsp+2B8h+var_A8], xmm0
0x18000499a  mov     [rsp+2B8h+var_98], r13
0x1800049a2  mov     [rsp+2B8h+var_90], r13
0x1800049aa  mov     r8, rbx
0x1800049ad  inc     r8
0x1800049b0  cmp     [rdx+r8], r13b
0x1800049b4  jnz     short loc_1800049AD
0x1800049b6  lea     rcx, [rsp+2B8h+var_A8]
0x1800049be  call    sub_180009070
0x1800049c3  mov     rdx, rdi
0x1800049c6  lea     rcx, [rsp+2B8h+var_88]
0x1800049ce  call    sub_180129300
0x1800049d3  mov     rcx, [rsp+2B8h+var_190]
0x1800049db  mov     rax, [rcx]
0x1800049de  mov     rax, [rax+60h]
0x1800049e2  call    cs:__guard_dispatch_icall_fptr
0x1800049e8  movaps  xmm6, xmm0
0x1800049eb  lea     rcx, [rsp+2B8h+var_1A8]
0x1800049f3  call    sub_180001364
0x1800049f8  lea     rax, [rsp+2B8h+var_78]
0x180004a00  mov     [rsp+2B8h+var_288], rax
0x180004a05  mov     rdx, cs:off_18021D0C0; "borderWidth"
0x180004a0c  xorps   xmm1, xmm1
0x180004a0f  movups  [rsp+2B8h+var_78], xmm1
0x180004a17  mov     [rsp+2B8h+var_68], r13
0x180004a1f  mov     [rsp+2B8h+var_60], r13
0x180004a27  inc     rbx
0x180004a2a  cmp     [rdx+rbx], r13b
0x180004a2e  jnz     short loc_180004A27
0x180004a30  mov     r8, rbx
0x180004a33  lea     rcx, [rsp+2B8h+var_78]
0x180004a3b  call    sub_180009070
0x180004a40  xorps   xmm1, xmm1
0x180004a43  cvtss2sd xmm1, xmm6
0x180004a47  lea     rcx, [rsp+2B8h+var_58]
0x180004a4f  call    sub_1801290B0
0x180004a54  lea     rax, [rsp+2B8h+var_D8]
0x180004a5c  mov     [rsp+2B8h+var_288], rax
0x180004a61  lea     rax, [rsp+2B8h+var_48]
0x180004a69  mov     [rsp+2B8h+var_280], rax
0x180004a6e  lea     rdx, [rsp+2B8h+var_288]
0x180004a73  lea     rcx, [rsp+2B8h+var_158]
0x180004a7b  call    sub_1800067C4
0x180004a80  mov     rbx, rax
0x180004a83  lea     rax, [rsp+2B8h+var_278]
0x180004a88  cmp     rax, rbx
0x180004a8b  jz      short loc_180004AB9
0x180004a8d  lea     rcx, [rsp+2B8h+var_278]
0x180004a92  call    sub_180008354
0x180004a97  mov     rdx, qword ptr [rsp+2B8h+var_278]
0x180004a9c  mov     rcx, [rbx]
0x180004a9f  mov     qword ptr [rsp+2B8h+var_278], rcx
0x180004aa4  mov     [rbx], rdx
0x180004aa7  mov     rcx, qword ptr [rsp+2B8h+var_278+8]
0x180004aac  mov     rax, [rbx+8]
0x180004ab0  mov     qword ptr [rsp+2B8h+var_278+8], rax
0x180004ab5  mov     [rbx+8], rcx
0x180004ab9  lea     rcx, [rsp+2B8h+var_158]
0x180004ac1  call    sub_1800066D4
0x180004ac6  lea     r9, sub_1800028F0
0x180004acd  mov     ebx, 30h ; '0'
0x180004ad2  lea     r8d, [rbx-2Dh]
0x180004ad6  mov     edx, ebx
0x180004ad8  lea     rcx, [rsp+2B8h+var_D8]
0x180004ae0  call    sub_18016CCCC
0x180004ae5  lea     rcx, [rsp+2B8h+var_230]
0x180004aed  call    sub_1800066D4
0x180004af2  lea     r9, sub_1800028F0
0x180004af9  lea     r8d, [rbx-2Eh]
0x180004afd  mov     edx, ebx
0x180004aff  lea     rcx, [rsp+2B8h+var_138]
0x180004b07  call    sub_18016CCCC
0x180004b0c  mov     rax, [rsp+2B8h+Block+8]
0x180004b14  cmp     [rsp+2B8h+Block], rax
0x180004b1c  jz      short loc_180004B5E
0x180004b1e  lea     rdx, [rsp+2B8h+Block]
0x180004b26  lea     rcx, [rsp+2B8h+var_158]
0x180004b2e  call    sub_18000440C
0x180004b33  nop
0x180004b34  mov     r9, rax
0x180004b37  lea     r8, off_18021D0B8; "clipRects"
0x180004b3e  lea     rdx, [rsp+2B8h+var_230]
0x180004b46  lea     rcx, [rsp+2B8h+var_278]
0x180004b4b  call    sub_180005B30
0x180004b50  nop
0x180004b51  lea     rcx, [rsp+2B8h+var_158]
0x180004b59  call    sub_1800076EC
0x180004b5e  mov     rcx, [rsp+2B8h+var_190]
0x180004b66  mov     rax, [rcx]
0x180004b69  mov     rax, [rax+8]
0x180004b6d  call    cs:__guard_dispatch_icall_fptr
0x180004b73  test    eax, eax
0x180004b75  jz      loc_180004C33
0x180004b7b  mov     rcx, [rsp+2B8h+var_190]
0x180004b83  mov     rax, [rcx]
0x180004b86  mov     rax, [rax+8]
0x180004b8a  call    cs:__guard_dispatch_icall_fptr
0x180004b90  cmp     eax, 3
0x180004b93  jz      loc_180004C33
0x180004b99  test    r15, r15
0x180004b9c  jz      short loc_180004BA5
0x180004b9e  mov     dword ptr [r15], 4
0x180004ba5  lea     rcx, [rsp+2B8h+var_240]
0x180004baa  call    sub_1800066D4
0x180004baf  mov     rcx, [rsp+2B8h+var_260]
0x180004bb4  test    rcx, rcx
0x180004bb7  jz      short loc_180004BC4
0x180004bb9  mov     rax, [rsp+2B8h+var_268]
0x180004bbe  call    cs:__guard_dispatch_icall_fptr
0x180004bc4  mov     esi, 4DE1h
0x180004bc9  mov     [rsp+2B8h+var_260], rsi
0x180004bce  lea     rcx, [rsp+2B8h+var_278]
0x180004bd3  call    sub_1800066D4
0x180004bd8  mov     rcx, [rsp+2B8h+Block]; Block
0x180004be0  test    rcx, rcx
0x180004be3  jz      short loc_180004C2C
0x180004be5  mov     rax, [rsp+2B8h+var_168]
0x180004bed  sub     rax, rcx
0x180004bf0  mov     rdx, rcx
0x180004bf3  and     rax, 0FFFFFFFFFFFFFFF0h
0x180004bf7  cmp     rax, 1000h
0x180004bfd  jb      short loc_180004C26
0x180004bff  mov     rcx, [rcx-8]
0x180004c03  sub     rdx, rcx
0x180004c06  lea     rax, [rdx-8]
0x180004c0a  cmp     rax, 1Fh
0x180004c0e  jbe     short loc_180004C26
0x180004c10  mov     [rsp+2B8h+Reserved], r13; Reserved
0x180004c15  xor     r9d, r9d; LineNo
0x180004c18  xor     r8d, r8d; FileName
0x180004c1b  xor     edx, edx; FunctionName
0x180004c1d  xor     ecx, ecx; Expression
0x180004c1f  call    cs:_invoke_watson
0x180004c26  call    cs:free
0x180004c2c  xor     eax, eax
0x180004c2e  jmp     loc_180004DE3
  ... truncated ...
```
