# CQueryStatisticsJob::OnDeviceCommandCompletion(int,ulong,uchar *,void *,uint,uint *,uint *)

- ea: `0x140019290`
- end: `0x1400198ad`
- name: `?OnDeviceCommandCompletion@CQueryStatisticsJob@@UEAAHHKPEAEPEAXIPEAI2@Z`
- size: `1565`
- prototype: `__int64 __fastcall(CQueryStatisticsJob *this, __int64, __int64, unsigned __int8 *, _QWORD *, size_t Size, unsigned int *, unsigned int *)`
- caller_count: `0`
- callee_count: `12`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x14000c778`
- `0x140016d00`
- `0x140019290`
- `0x140019c78`
- `0x140019d44`
- `0x14001e2c0`
- `0x14001eed0`
- `0x14002eeb8`
- `0x140040eac`
- `0x140071720`
- `0x1400dfd40`
- `0x1400e0100`

## pseudocode

```c
__int64 __fastcall CQueryStatisticsJob::OnDeviceCommandCompletion(
        CQueryStatisticsJob *this,
        __int64 a2,
        __int64 a3,
        unsigned __int8 *a4,
        _QWORD *a5,
        size_t Size,
        unsigned int *a7,
        unsigned int *a8)
{
  int v9; // r14d
  unsigned int PropertyULong; // ebx
  CPropertyCache *AdapterPropertyCache; // rax
  unsigned int PropertyList; // eax
  int v14; // r9d
  unsigned int v15; // ecx
  _QWORD *v16; // r15
  unsigned int v17; // r12d
  unsigned int v18; // r14d
  int v19; // eax
  __int64 v20; // r10
  __int64 v21; // r9
  unsigned int i; // r12d
  __int64 v23; // rcx
  unsigned int v24; // esi
  __int64 v25; // rax
  __int64 v26; // r8
  unsigned int v27; // edx
  __int64 v28; // r14
  bool v29; // cc
  __int64 v30; // rax
  unsigned int v31; // ecx
  int v32; // r14d
  CPropertyCache *PortPropertyCache; // rax
  int v34; // edx
  int v35; // r8d
  __int64 v37; // [rsp+38h] [rbp-49h]
  __int64 v38; // [rsp+40h] [rbp-41h] BYREF
  unsigned __int8 *v39; // [rsp+48h] [rbp-39h] BYREF
  unsigned int v40; // [rsp+50h] [rbp-31h] BYREF
  __int64 v41; // [rsp+58h] [rbp-29h]
  char v42; // [rsp+60h] [rbp-21h]
  unsigned int v43; // [rsp+68h] [rbp-19h] BYREF
  __int64 v44; // [rsp+70h] [rbp-11h]
  char v45; // [rsp+78h] [rbp-9h]
  unsigned int v46; // [rsp+D8h] [rbp+57h] BYREF

  LOWORD(v46) = 0;
  v9 = a3;
  LODWORD(v38) = 0;
  PropertyULong = a2;
  v40 = 0;
  v41 = 0;
  v42 = 0;
  v43 = 0;
  v44 = 0;
  v45 = 0;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    LOBYTE(a2) = 5;
    WPP_RECORDER_SF_qD(
      WPP_GLOBAL_Control->DeviceExtension,
      a2,
      a3,
      128,
      (__int64)WPP_2d39e0cebfc73daf8408a6f3c3e3de18_Traceguids,
      (char)this,
      *((_DWORD *)this + 4));
  }
  if ( PropertyULong )
    goto LABEL_71;
  AdapterPropertyCache = CJobBase::get_AdapterPropertyCache(this);
  PropertyList = CPropertyCache::GetPropertyList(
                   AdapterPropertyCache,
                   4u,
                   (unsigned int *)&v38,
                   (unsigned __int16 *)&v46,
                   &v39);
  PropertyULong = PropertyList;
  if ( PropertyList )
  {
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_75;
    v14 = 129;
LABEL_9:
    LOBYTE(a2) = 2;
    WPP_RECORDER_SF_qDD(
      WPP_GLOBAL_Control->DeviceExtension,
      a2,
      a3,
      v14,
      (__int64)WPP_2d39e0cebfc73daf8408a6f3c3e3de18_Traceguids,
      (char)this,
      *((_DWORD *)this + 4),
      PropertyList,
      v38);
    goto LABEL_71;
  }
  v15 = 144 * (unsigned __int16)v46 + 256;
  *a8 = v15;
  if ( (unsigned int)Size < v15 )
  {
    PropertyULong = -2147483643;
    goto LABEL_71;
  }
  v16 = a5;
  memset(a5, 0, (unsigned int)Size);
  *(_DWORD *)v16 = 26214784;
  v16[1] = 0;
  v16[2] = 0;
  PropertyList = ParseWdiGetStatisticsFromIhv((unsigned int)(v9 - 48), a4 + 48, *((_QWORD *)this + 67) + 5384LL, &v40);
  PropertyULong = PropertyList;
  if ( PropertyList )
  {
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_75;
    v14 = 130;
    goto LABEL_9;
  }
  v17 = v40;
  v18 = 0;
  if ( v40 )
  {
    a2 = v41;
    do
    {
      a3 = 112LL * v18;
      if ( *(_BYTE *)(a3 + a2) != 0xFF
        || *(_BYTE *)(a3 + a2 + 1) != 0xFF
        || *(_BYTE *)(a3 + a2 + 2) != 0xFF
        || *(_BYTE *)(a3 + a2 + 3) != 0xFF
        || *(_BYTE *)(a3 + a2 + 4) != 0xFF
        || (v19 = 1, *(_BYTE *)(a3 + a2 + 5) != 0xFF) )
      {
        v19 = 0;
      }
      v20 = 18;
      if ( v19 != 1 )
        v20 = 4;
      v21 = 0;
      v16[v20] += *(_QWORD *)(a3 + a2 + 8);
      v16[v20 + 1] += *(_QWORD *)(a3 + a2 + 16);
      do
      {
        v16[v20 + 4 + v21] += *(_QWORD *)(112LL * v18 + 24 + 8 * v21 + a2);
        ++v21;
      }
      while ( v21 != 4 );
      ++v18;
      v16[v20 + 8] += *(_QWORD *)(a3 + a2 + 64);
      v16[v20 + 9] += *(_QWORD *)(a3 + a2 + 72);
      v16[v20 + 10] += *(_QWORD *)(a3 + a2 + 104);
      v16[v20 + 11] += *(_QWORD *)(a3 + a2 + 88);
      v16[v20 + 12] += *(_QWORD *)(a3 + a2 + 96);
      v16[v20 + 13] += *(_QWORD *)(a3 + a2 + 104);
    }
    while ( v18 < v17 );
  }
  for ( i = 0; ; ++i )
  {
    if ( i >= v43 )
    {
      *a7 = *a8;
      goto LABEL_71;
    }
    v23 = *((_QWORD *)this + 62);
    v24 = 0;
    v46 = 0;
    v25 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v23 + 8LL))(v23);
    v27 = 0;
    v28 = 0;
    v29 = *(_DWORD *)(v25 + 8) <= 4u;
    LODWORD(v38) = *(_DWORD *)(v44 + 152LL * i);
    if ( !v29 )
    {
      v30 = *(_QWORD *)(v25 + 16);
      if ( *(_BYTE *)(v30 + 232) )
      {
        v28 = v30 + 224;
      }
      else
      {
        if ( !*(_QWORD *)(v30 + 272) )
        {
          if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            LOBYTE(v27) = 4;
            WPP_RECORDER_SF_d(
              WPP_GLOBAL_Control->DeviceExtension,
              v27,
              1,
              20,
              (__int64)WPP_3ddeec0b7fee33ed2b3cc846f6231af9_Traceguids,
              4);
          }
          PropertyULong = -1073741436;
          goto LABEL_42;
        }
        v28 = *(_QWORD *)(v30 + 272);
      }
      PropertyULong = 0;
      goto LABEL_42;
    }
    PropertyULong = -1073741811;
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_56;
    LOBYTE(v27) = 2;
    WPP_RECORDER_SF_d(
      WPP_GLOBAL_Control->DeviceExtension,
      v27,
      1,
      19,
      (__int64)WPP_3ddeec0b7fee33ed2b3cc846f6231af9_Traceguids,
      4);
LABEL_42:
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_46;
    if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || (v27 = 0, LOWORD(WPP_GLOBAL_Control->DeviceType)) )
    {
      LOBYTE(v27) = 5;
      WPP_RECORDER_SF_d(
        WPP_GLOBAL_Control->DeviceExtension,
        v27,
        1,
        22,
        (__int64)WPP_3ddeec0b7fee33ed2b3cc846f6231af9_Traceguids,
        PropertyULong);
LABEL_46:
      v27 = 0;
    }
    if ( PropertyULong )
    {
LABEL_56:
      v32 = PropertyULong;
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v27) = 2;
        WPP_RECORDER_SF_d(
          WPP_GLOBAL_Control->DeviceExtension,
          v27,
          1,
          33,
          (__int64)WPP_3ddeec0b7fee33ed2b3cc846f6231af9_Traceguids,
          PropertyULong);
      }
      goto LABEL_58;
    }
    v26 = *(_QWORD *)(v28 + 24);
    v31 = 0;
    v27 = *(unsigned __int16 *)(v28 + 40);
    while ( v31 < v27 )
    {
      if ( *(_DWORD *)(v26 + 4LL * v31) == (_DWORD)v38 )
      {
        v24 = v31;
        v46 = v31;
        goto LABEL_59;
      }
      ++v31;
    }
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v27) = 2;
      WPP_RECORDER_SF_d(
        WPP_GLOBAL_Control->DeviceExtension,
        v27,
        1,
        34,
        (__int64)WPP_3ddeec0b7fee33ed2b3cc846f6231af9_Traceguids,
        v38);
    }
    v32 = 65537;
    PropertyULong = 65537;
LABEL_58:
    if ( *(_DWORD *)(v44 + 152LL * i) )
      break;
LABEL_59:
    if ( !*(_DWORD *)(v44 + 152LL * i) )
    {
      PortPropertyCache = COidJobBase::GetPortPropertyCache(this);
      PropertyULong = CPropertyCache::GetPropertyULong(PortPropertyCache, 0x34u, &v46);
      if ( PropertyULong )
      {
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(v34) = 2;
          LODWORD(v37) = PropertyULong;
          WPP_RECORDER_SF_qDD(
            WPP_GLOBAL_Control->DeviceExtension,
            v34,
            v35,
            133,
            (__int64)WPP_2d39e0cebfc73daf8408a6f3c3e3de18_Traceguids,
            (char)this,
            *((_DWORD *)this + 4),
            v37);
        }
        v24 = 0;
      }
      else
      {
        v24 = v46;
      }
    }
    a2 = 0;
    a3 = (__int64)&v16[18 * v24];
    do
    {
      *(_QWORD *)(a3 + 8 * a2 + 256) += *(_QWORD *)(152LL * i + 8 * a2 + v44 + 8);
      ++a2;
    }
    while ( a2 != 18 );
  }
  if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    goto LABEL_75;
  LODWORD(v37) = v32;
  LOBYTE(v27) = 2;
  WPP_RECORDER_SF_qDD(
    WPP_GLOBAL_Control->DeviceExtension,
    v27,
    v26,
    132,
    (__int64)WPP_2d39e0cebfc73daf8408a6f3c3e3de18_Traceguids,
    (char)this,
    *((_DWORD *)this + 4),
    v37);
LABEL_71:
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    LOBYTE(a2) = 5;
    LODWORD(v37) = PropertyULong;
    WPP_RECORDER_SF_qDD(
      WPP_GLOBAL_Control->DeviceExtension,
      a2,
      a3,
      134,
      (__int64)WPP_2d39e0cebfc73daf8408a6f3c3e3de18_Traceguids,
      (char)this,
      *((_DWORD *)this + 4),
      v37);
  }
LABEL_75:
  ArrayOfElements<_WDI_PHY_STATISTICS_PARAMETERS>::Cleanup(&v43);
  ArrayOfElements<_WDI_PHY_STATISTICS_PARAMETERS>::Cleanup(&v40);
  return PropertyULong;
}

```

## disassembly

```asm
0x140019290  push    rbp
0x140019292  push    rbx
0x140019293  push    rsi
0x140019294  push    rdi
0x140019295  push    r12
0x140019297  push    r13
0x140019299  push    r14
0x14001929b  push    r15
0x14001929d  lea     rbp, [rsp-7]
0x1400192a2  sub     rsp, 88h
0x1400192a9  xor     r13d, r13d
0x1400192ac  mov     rsi, r9
0x1400192af  mov     word ptr [rbp+3Fh+arg_8], r13w
0x1400192b4  mov     r14d, r8d
0x1400192b7  mov     dword ptr [rbp+3Fh+var_80], r13d
0x1400192bb  mov     ebx, edx
0x1400192bd  mov     [rbp+3Fh+var_70], r13d
0x1400192c1  mov     rdi, rcx
0x1400192c4  mov     [rbp+3Fh+var_68], r13
0x1400192c8  mov     [rbp+3Fh+var_60], r13b
0x1400192cc  mov     [rbp+3Fh+var_58], r13d
0x1400192d0  mov     [rbp+3Fh+var_50], r13
0x1400192d4  mov     [rbp+3Fh+var_48], r13b
0x1400192d8  lea     r12, WPP_RECORDER_INITIALIZED
0x1400192df  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x1400192e6  lea     r15, WPP_2d39e0cebfc73daf8408a6f3c3e3de18_Traceguids
0x1400192ed  jz      short loc_140019325
0x1400192ef  mov     rcx, cs:WPP_GLOBAL_Control
0x1400192f6  cmp     byte ptr [rcx+29h], 5
0x1400192fa  jnb     short loc_140019303
0x1400192fc  cmp     [rcx+48h], r13w
0x140019301  jz      short loc_140019325
0x140019303  mov     eax, [rdi+10h]
0x140019306  mov     r9d, 80h
0x14001930c  mov     rcx, [rcx+40h]
0x140019310  mov     dl, 5
0x140019312  mov     [rsp+0C0h+var_90], eax
0x140019316  mov     [rsp+0C0h+var_98], rdi
0x14001931b  mov     [rsp+0C0h+var_A0], r15
0x140019320  call    WPP_RECORDER_SF_qD
0x140019325  test    ebx, ebx
0x140019327  jnz     loc_140019841
0x14001932d  mov     rcx, rdi; this
0x140019330  call    ?get_AdapterPropertyCache@CJobBase@@IEAAPEAVCAdapterPropertyCache@@XZ; CJobBase::get_AdapterPropertyCache(void)
0x140019335  lea     rcx, [rbp+3Fh+var_78]
0x140019339  mov     [rsp+0C0h+var_A0], rcx; unsigned __int8 **
0x14001933e  lea     r9, [rbp+3Fh+arg_8]; unsigned __int16 *
0x140019342  mov     rcx, rax; this
0x140019345  lea     r8, [rbp+3Fh+var_80]; unsigned int *
0x140019349  lea     edx, [rbx+4]; unsigned int
0x14001934c  call    ?GetPropertyList@CPropertyCache@@QEBAHKPEAKPEAGPEAPEAE@Z; CPropertyCache::GetPropertyList(ulong,ulong *,ushort *,uchar * *)
0x140019351  mov     ebx, eax
0x140019353  test    eax, eax
0x140019355  jz      short loc_140019396
0x140019357  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x14001935e  jz      loc_140019884
0x140019364  mov     r9d, 81h
0x14001936a  mov     rcx, cs:WPP_GLOBAL_Control
0x140019371  mov     dl, 2
0x140019373  mov     dword ptr [rsp+0C0h+var_88], eax
0x140019377  mov     eax, [rdi+10h]
0x14001937a  mov     [rsp+0C0h+var_90], eax
0x14001937e  mov     rcx, [rcx+40h]
0x140019382  mov     [rsp+0C0h+var_98], rdi
0x140019387  mov     [rsp+0C0h+var_A0], r15
0x14001938c  call    WPP_RECORDER_SF_qDD
0x140019391  jmp     loc_140019841
0x140019396  movzx   eax, word ptr [rbp+3Fh+arg_8]
0x14001939a  mov     r13, [rbp+3Fh+arg_38]
0x1400193a1  lea     ecx, [rax+rax*8]
0x1400193a4  shl     ecx, 4
0x1400193a7  add     ecx, 100h
0x1400193ad  mov     [r13+0], ecx
0x1400193b1  cmp     dword ptr [rbp+3Fh+Size], ecx
0x1400193b4  jnb     short loc_1400193C3
0x1400193b6  mov     ebx, 80000005h
0x1400193bb  xor     r13d, r13d
0x1400193be  jmp     loc_140019841
0x1400193c3  mov     r15, [rbp+3Fh+arg_20]
0x1400193c7  xor     edx, edx; Val
0x1400193c9  mov     r8d, dword ptr [rbp+3Fh+Size]; Size
0x1400193cd  mov     rcx, r15; void *
0x1400193d0  call    memset
0x1400193d5  xor     r13d, r13d
0x1400193d8  mov     dword ptr [r15], 1900180h
0x1400193df  mov     [r15+8], r13
0x1400193e3  lea     rdx, [rsi+30h]
0x1400193e7  mov     [r15+10h], r13
0x1400193eb  lea     ecx, [r14-30h]
0x1400193ef  mov     r8, [rdi+218h]
0x1400193f6  lea     r9, [rbp+3Fh+var_70]
0x1400193fa  add     r8, 1508h
0x140019401  call    ParseWdiGetStatisticsFromIhv
0x140019406  mov     ebx, eax
0x140019408  test    eax, eax
0x14001940a  jz      short loc_14001942B
0x14001940c  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x140019413  jz      loc_140019884
0x140019419  mov     r9d, 82h
0x14001941f  lea     r15, WPP_2d39e0cebfc73daf8408a6f3c3e3de18_Traceguids
0x140019426  jmp     loc_14001936A
0x14001942b  mov     r12d, [rbp+3Fh+var_70]
0x14001942f  mov     r14d, r13d
0x140019432  test    r12d, r12d
0x140019435  jz      loc_14001950B
0x14001943b  mov     rdx, [rbp+3Fh+var_68]
0x14001943f  mov     al, 0FFh
0x140019441  mov     ecx, r14d
0x140019444  imul    r8, rcx, 70h ; 'p'
0x140019448  cmp     [r8+rdx], al
0x14001944c  jnz     short loc_140019476
0x14001944e  cmp     [r8+rdx+1], al
0x140019453  jnz     short loc_140019476
0x140019455  cmp     [r8+rdx+2], al
0x14001945a  jnz     short loc_140019476
0x14001945c  cmp     [r8+rdx+3], al
0x140019461  jnz     short loc_140019476
0x140019463  cmp     [r8+rdx+4], al
0x140019468  jnz     short loc_140019476
0x14001946a  cmp     [r8+rdx+5], al
0x14001946f  mov     eax, 1
0x140019474  jz      short loc_140019479
0x140019476  mov     eax, r13d
0x140019479  cmp     eax, 1
0x14001947c  mov     r10d, 90h
0x140019482  mov     rax, [r8+rdx+8]
0x140019487  lea     r9d, [r10-70h]
0x14001948b  cmovnz  r10d, r9d
0x14001948f  mov     r9, r13
0x140019492  imul    rsi, rcx, 70h ; 'p'
0x140019496  lea     r11, [r10+r15]
0x14001949a  add     [r11], rax
0x14001949d  mov     rax, [r8+rdx+10h]
0x1400194a2  add     [r15+r10+8], rax
0x1400194a7  add     rsi, 18h
0x1400194ab  lea     rax, [rsi+r9*8]
0x1400194af  mov     rcx, [rax+rdx]
0x1400194b3  add     [r11+r9*8+20h], rcx
0x1400194b8  inc     r9
0x1400194bb  cmp     r9, 4
0x1400194bf  jnz     short loc_1400194AB
0x1400194c1  mov     rax, [r8+rdx+40h]
0x1400194c6  inc     r14d
0x1400194c9  add     [r10+r15+40h], rax
0x1400194ce  mov     rax, [r8+rdx+48h]
0x1400194d3  add     [r15+r10+48h], rax
0x1400194d8  mov     rax, [r8+rdx+68h]
0x1400194dd  add     [r15+r10+50h], rax
0x1400194e2  mov     rax, [r8+rdx+58h]
0x1400194e7  add     [r10+r15+58h], rax
0x1400194ec  mov     rax, [r8+rdx+60h]
0x1400194f1  add     [r10+r15+60h], rax
0x1400194f6  mov     rax, [r8+rdx+68h]
0x1400194fb  add     [r10+r15+68h], rax
0x140019500  mov     al, 0FFh
0x140019502  cmp     r14d, r12d
0x140019505  jb      loc_140019441
0x14001950b  mov     r12d, r13d
0x14001950e  cmp     r12d, [rbp+3Fh+var_58]
0x140019512  jnb     loc_140019824
0x140019518  mov     rcx, [rdi+1F0h]
0x14001951f  mov     esi, r13d
0x140019522  mov     [rbp+3Fh+arg_8], r13d
0x140019526  mov     rax, [rcx]
0x140019529  mov     rax, [rax+8]
0x14001952d  call    _guard_dispatch_icall
0x140019532  mov     ecx, r12d
0x140019535  xor     edx, edx
0x140019537  imul    r13, rcx, 98h
0x14001953e  mov     rcx, [rbp+3Fh+var_50]
0x140019542  mov     r14d, edx
0x140019545  cmp     dword ptr [rax+8], 4
0x140019549  mov     ecx, [rcx+r13]
0x14001954d  mov     dword ptr [rbp+3Fh+var_80], ecx
0x140019550  jbe     short loc_1400195BF
0x140019552  mov     rax, [rax+10h]
0x140019556  cmp     [rax+0E8h], dl
0x14001955c  jnz     short loc_1400195B4
0x14001955e  mov     rcx, [rax+110h]
0x140019565  test    rcx, rcx
0x140019568  jnz     short loc_1400195AF
0x14001956a  lea     rax, WPP_RECORDER_INITIALIZED
0x140019571  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140019578  jz      short loc_1400195A8
0x14001957a  mov     rcx, cs:WPP_GLOBAL_Control
0x140019581  lea     r9d, [rdx+14h]
0x140019585  lea     rax, WPP_3ddeec0b7fee33ed2b3cc846f6231af9_Traceguids
0x14001958c  mov     dword ptr [rsp+0C0h+var_98], 4
0x140019594  lea     r8d, [rdx+1]
0x140019598  mov     [rsp+0C0h+var_A0], rax
0x14001959d  mov     dl, 4
0x14001959f  mov     rcx, [rcx+40h]
0x1400195a3  call    WPP_RECORDER_SF_d
0x1400195a8  mov     ebx, 0C0000184h
0x1400195ad  jmp     short loc_140019608
0x1400195af  mov     r14, rcx
0x1400195b2  jmp     short loc_1400195BB
0x1400195b4  lea     r14, [rax+0E0h]
0x1400195bb  mov     ebx, edx
0x1400195bd  jmp     short loc_140019608
0x1400195bf  mov     ebx, 0C000000Dh
0x1400195c4  lea     rax, WPP_RECORDER_INITIALIZED
0x1400195cb  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400195d2  jz      loc_1400196D1
0x1400195d8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400195df  lea     rax, WPP_3ddeec0b7fee33ed2b3cc846f6231af9_Traceguids
0x1400195e6  mov     r9d, 13h
0x1400195ec  mov     dword ptr [rsp+0C0h+var_98], 4
0x1400195f4  mov     dl, 2
0x1400195f6  mov     [rsp+0C0h+var_A0], rax
0x1400195fb  mov     rcx, [rcx+40h]
0x1400195ff  lea     r8d, [r9-12h]
0x140019603  call    WPP_RECORDER_SF_d
0x140019608  lea     rax, WPP_RECORDER_INITIALIZED
0x14001960f  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140019616  jz      short loc_140019659
0x140019618  mov     rcx, cs:WPP_GLOBAL_Control
0x14001961f  cmp     byte ptr [rcx+29h], 5
0x140019623  jnb     short loc_14001962D
0x140019625  xor     edx, edx
0x140019627  cmp     [rcx+48h], dx
0x14001962b  jz      short loc_14001965B
0x14001962d  mov     rcx, [rcx+40h]
0x140019631  lea     rax, WPP_3ddeec0b7fee33ed2b3cc846f6231af9_Traceguids
0x140019638  mov     r9d, 16h
0x14001963e  mov     dword ptr [rsp+0C0h+var_98], ebx
0x140019642  mov     dl, 5
0x140019644  mov     [rsp+0C0h+var_A0], rax
0x140019649  lea     r8d, [r9-15h]
0x14001964d  call    WPP_RECORDER_SF_d
0x140019652  lea     rax, WPP_RECORDER_INITIALIZED
0x140019659  xor     edx, edx
0x14001965b  test    ebx, ebx
0x14001965d  jnz     short loc_1400196D1
0x14001965f  mov     r8, [r14+18h]
0x140019663  mov     ecx, edx
0x140019665  movzx   edx, word ptr [r14+28h]
0x14001966a  mov     r10d, dword ptr [rbp+3Fh+var_80]
0x14001966e  cmp     ecx, edx
0x140019670  jnb     short loc_140019688
0x140019672  mov     eax, ecx
0x140019674  cmp     [r8+rax*4], r10d
0x140019678  jz      short loc_14001967E
0x14001967a  inc     ecx
0x14001967c  jmp     short loc_14001966E
0x14001967e  mov     esi, ecx
0x140019680  mov     [rbp+3Fh+arg_8], ecx
0x140019683  jmp     loc_140019718
0x140019688  lea     rax, WPP_RECORDER_INITIALIZED
0x14001968f  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140019696  jz      short loc_1400196C5
0x140019698  mov     rcx, cs:WPP_GLOBAL_Control
0x14001969f  lea     rax, WPP_3ddeec0b7fee33ed2b3cc846f6231af9_Traceguids
0x1400196a6  mov     r9d, 22h ; '"'
0x1400196ac  mov     dword ptr [rsp+0C0h+var_98], r10d
0x1400196b1  mov     dl, 2
0x1400196b3  mov     [rsp+0C0h+var_A0], rax
0x1400196b8  mov     rcx, [rcx+40h]
0x1400196bc  lea     r8d, [r9-21h]
0x1400196c0  call    WPP_RECORDER_SF_d
0x1400196c5  mov     eax, 10001h
0x1400196ca  mov     r14d, eax
0x1400196cd  mov     ebx, eax
0x1400196cf  jmp     short loc_140019709
0x1400196d1  mov     r14d, ebx
0x1400196d4  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400196db  jz      short loc_140019709
0x1400196dd  mov     rcx, cs:WPP_GLOBAL_Control
0x1400196e4  lea     rax, WPP_3ddeec0b7fee33ed2b3cc846f6231af9_Traceguids
0x1400196eb  mov     r9d, 21h ; '!'
0x1400196f1  mov     dword ptr [rsp+0C0h+var_98], ebx
0x1400196f5  mov     dl, 2
0x1400196f7  mov     [rsp+0C0h+var_A0], rax
0x1400196fc  mov     rcx, [rcx+40h]
0x140019700  lea     r8d, [r9-20h]
0x140019704  call    WPP_RECORDER_SF_d
0x140019709  mov     rax, [rbp+3Fh+var_50]
0x14001970d  cmp     dword ptr [rax+r13], 0
0x140019712  jnz     loc_1400197D6
0x140019718  mov     rax, [rbp+3Fh+var_50]
0x14001971c  cmp     dword ptr [rax+r13], 0
0x140019721  jnz     short loc_140019793
0x140019723  mov     rcx, rdi; this
0x140019726  call    ?GetPortPropertyCache@COidJobBase@@IEAAPEAVCPortPropertyCache@@XZ; COidJobBase::GetPortPropertyCache(void)
0x14001972b  lea     r8, [rbp+3Fh+arg_8]; unsigned int *
0x14001972f  mov     edx, 34h ; '4'; unsigned int
0x140019734  mov     rcx, rax; this
0x140019737  call    ?GetPropertyULong@CPropertyCache@@QEAAHKPEAK@Z; CPropertyCache::GetPropertyULong(ulong,ulong *)
0x14001973c  xor     r13d, r13d
0x14001973f  mov     ebx, eax
0x140019741  test    eax, eax
0x140019743  jz      short loc_14001978E
0x140019745  lea     rax, WPP_RECORDER_INITIALIZED
0x14001974c  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140019753  jz      short loc_140019789
0x140019755  mov     eax, [rdi+10h]
0x140019758  mov     r9d, 85h
0x14001975e  mov     rcx, cs:WPP_GLOBAL_Control
0x140019765  mov     dl, 2
0x140019767  mov     dword ptr [rsp+0C0h+var_88], ebx
  ... truncated ...
```
