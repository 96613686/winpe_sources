# DiscoverPeriodicityCharacteristicsForFormat(IMMDevice *,AUDIO_DIRECTION,__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001,_GUID,tWAVEFORMATEX const *,PacketSizeConstraints *,DPCF_OPTIONS,__int64,uint *,uint *,uint *,uint *,uint *)

- ea: `0x180020034`
- end: `0x1800205eb`
- name: `?DiscoverPeriodicityCharacteristicsForFormat@@YAJPEAUIMMDevice@@W4AUDIO_DIRECTION@@W4__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001@@U_GUID@@PEBUtWAVEFORMATEX@@PEAUPacketSizeConstraints@@W4DPCF_OPTIONS@@_JPEAI8888@Z`
- size: `1463`
- prototype: `__int64(__int64, unsigned int, unsigned int, struct _GUID *, ...)`
- caller_count: `2`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800197e4`
- `0x180019ce8`

## callees

- `0x180010da8`
- `0x180020034`
- `0x1800205f4`
- `0x180035c70`
- `0x18003f78c`
- `0x18005e994`
- `0x180068010`

## import_xrefs

- `MMDevAPI!__imp_GetClassFromEndpointId` at `0x180020133`
- `MMDevAPI!__imp_GetClassFromEndpointId` at `0x180020133`
- `MMDevAPI!__imp_GetSessionIdFromEndpointId` at `0x18002029a`
- `MMDevAPI!__imp_GetSessionIdFromEndpointId` at `0x18002029a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180020270`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180020270`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002011f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800201df`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180020247`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002030f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180020336`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180020349`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800203e7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800203fa`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002046c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800205a9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800205de`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002011f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800201df`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180020247`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002030f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180020336`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180020349`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800203e7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800203fa`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002046c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800205a9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800205de`

## pseudocode

```c
// Hidden C++ exception states: #wind=23
__int64 DiscoverPeriodicityCharacteristicsForFormat(
        __int64 a1,
        unsigned int a2,
        unsigned int a3,
        struct _GUID *a4,
        ...)
{
  __int64 v6; // rcx
  unsigned __int16 *v7; // r13
  double v8; // xmm1_8
  unsigned int *v9; // r14
  unsigned int *v10; // r15
  unsigned int *v11; // r12
  unsigned int *v12; // rbx
  int v13; // eax
  unsigned int v14; // edi
  struct PacketSizeConstraints *v16; // rdi
  int PacketSizesFromConstraints; // eax
  unsigned int v18; // esi
  unsigned int v19; // eax
  unsigned int v20; // eax
  unsigned int *v21; // rax
  unsigned int *v22; // rsi
  int v23; // eax
  unsigned int v24; // ebx
  unsigned int v25; // eax
  int v26; // eax
  unsigned int v27; // r15d
  unsigned int v28; // eax
  int v29; // eax
  unsigned int v30; // edi
  int i; // eax
  unsigned int v32; // edi
  unsigned int v33; // eax
  int v34; // [rsp+28h] [rbp-61h]
  int v35; // [rsp+28h] [rbp-61h]
  int v36; // [rsp+28h] [rbp-61h]
  unsigned __int64 v37; // [rsp+30h] [rbp-59h]
  unsigned __int64 v38; // [rsp+38h] [rbp-51h]
  unsigned __int64 v39; // [rsp+68h] [rbp-21h]
  struct _GUID v40; // [rsp+78h] [rbp-11h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D0h] [rbp+47h]
  __int64 v42; // [rsp+D8h] [rbp+4Fh] BYREF
  unsigned int v43; // [rsp+E0h] [rbp+57h]
  unsigned int v44; // [rsp+E8h] [rbp+5Fh] BYREF
  struct _GUID *v45; // [rsp+F0h] [rbp+67h]
  void *Src; // [rsp+F8h] [rbp+6Fh] BYREF
  va_list Srca; // [rsp+F8h] [rbp+6Fh]
  struct PacketSizeConstraints *v48; // [rsp+100h] [rbp+77h]
  __int64 v49; // [rsp+108h] [rbp+7Fh]
  __int64 v50; // [rsp+110h] [rbp+87h] BYREF
  va_list va1; // [rsp+110h] [rbp+87h]
  unsigned int *v52; // [rsp+118h] [rbp+8Fh]
  unsigned int *v53; // [rsp+120h] [rbp+97h]
  LPVOID pv; // [rsp+128h] [rbp+9Fh] BYREF
  va_list pva; // [rsp+128h] [rbp+9Fh]
  unsigned int *v56; // [rsp+130h] [rbp+A7h] BYREF
  va_list va3; // [rsp+130h] [rbp+A7h]
  unsigned int *v58; // [rsp+138h] [rbp+AFh]
  va_list va4; // [rsp+140h] [rbp+B7h] BYREF

  va_start(va4, a4);
  va_start(va3, a4);
  va_start(pva, a4);
  va_start(va1, a4);
  va_start(Srca, a4);
  Src = va_arg(va1, void *);
  v48 = va_arg(va1, struct PacketSizeConstraints *);
  v49 = va_arg(va1, _QWORD);
  va_copy(pva, va1);
  v50 = va_arg(pva, _QWORD);
  v52 = va_arg(pva, unsigned int *);
  v53 = va_arg(pva, unsigned int *);
  va_copy(va3, pva);
  pv = va_arg(va3, LPVOID);
  va_copy(va4, va3);
  v56 = va_arg(va4, unsigned int *);
  v58 = va_arg(va4, unsigned int *);
  v45 = a4;
  v44 = a3;
  v43 = a2;
  v42 = a1;
  v6 = 100000;
  if ( v50 )
    v6 = v50;
  v39 = v6;
  v7 = (unsigned __int16 *)Src;
  v8 = (double)(int)v6 * (double)*((int *)Src + 1) / 10000000.0 + 0.5;
  v9 = v56;
  *v56 = (int)v8;
  v10 = (unsigned int *)pv;
  *(_DWORD *)pv = (int)v8;
  v11 = v53;
  *v53 = (int)v8;
  v12 = v52;
  *v52 = (int)v8;
  pv = 0;
  v13 = (*(__int64 (__fastcall **)(__int64, LPVOID *))(*(_QWORD *)a1 + 40LL))(a1, (LPVOID *)pva);
  v14 = v13;
  if ( v13 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x227,
      (unsigned int)"avcore\\audiocore\\server\\lib\\audioengineutil\\endpointutil.cpp",
      (const char *)(unsigned int)v13,
      v34);
LABEL_5:
    if ( pv )
      CoTaskMemFree(pv);
    return v14;
  }
  if ( (unsigned int)GetClassFromEndpointId(pv) )
    goto LABEL_20;
  v16 = v48;
  if ( v48 && (v49 & 2) != 0 )
  {
    v44 = 0;
    LODWORD(v42) = 0;
    LODWORD(Src) = 0;
    LODWORD(v56) = 0;
    v40 = *a4;
    PacketSizesFromConstraints = GetPacketSizesFromConstraints(
                                   v48,
                                   *((_DWORD *)v7 + 2),
                                   v7[6],
                                   &v40,
                                   v39,
                                   v37,
                                   v38,
                                   &v44,
                                   (unsigned int *)&v42,
                                   (unsigned int *)Srca,
                                   (unsigned int *)va3);
    v18 = PacketSizesFromConstraints;
    if ( PacketSizesFromConstraints < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x23C,
        (unsigned int)"avcore\\audiocore\\server\\lib\\audioengineutil\\endpointutil.cpp",
        (const char *)(unsigned int)PacketSizesFromConstraints,
        v35);
      if ( pv )
        CoTaskMemFree(pv);
      return v18;
    }
    v19 = v44;
    *v9 = v44;
    *v10 = v19;
    *v11 = v19;
    *v12 = v19;
    if ( !v50 )
    {
      *v11 = v42;
      *v10 = (unsigned int)Src;
      if ( v43 != 1 || (v20 = (unsigned int)v56, !*(_BYTE *)v16) )
        v20 = *v12;
      *v9 = v20;
    }
    goto LABEL_20;
  }
  LODWORD(Src) = v7[8] + 64;
  v21 = (unsigned int *)CoTaskMemAlloc((unsigned int)Src);
  v22 = v21;
  v53 = v21;
  if ( !v21 )
  {
    v24 = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x25A,
      (unsigned int)"avcore\\audiocore\\server\\lib\\audioengineutil\\endpointutil.cpp",
      (const char *)0x8007000ELL,
      v34);
    goto LABEL_62;
  }
  *v21 = v7[8] + 64;
  v21[1] = GetSessionIdFromEndpointId(pv);
  v22[2] = 0;
  *(struct _GUID *)(v22 + 3) = *v45;
  memcpy_0(v22 + 11, v7, v7[8] + 18LL);
  v44 = 0;
  v23 = CheckConnectorSupportForPeriodicity(v42, v43, v22, (unsigned int)Src);
  LODWORD(v56) = v23;
  if ( v23 >= 0 )
  {
    v25 = v44;
    *v9 = v44;
    *v10 = v25;
    *v11 = v25;
    *v12 = v25;
    if ( !v50 )
    {
      if ( v16 )
      {
        LODWORD(v42) = 0;
        v40 = *v45;
        v26 = GetPacketSizesFromConstraints(
                v16,
                *((_DWORD *)v7 + 2),
                v7[6],
                &v40,
                0x186A0u,
                (unsigned __int64)&v44,
                v38,
                v12,
                v11,
                v10,
                (unsigned int *)&v42);
        v27 = v26;
        if ( v26 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x282,
            (unsigned int)"avcore\\audiocore\\server\\lib\\audioengineutil\\endpointutil.cpp",
            (const char *)(unsigned int)v26,
            v36);
          CoTaskMemFree(v22);
          if ( pv )
            CoTaskMemFree(pv);
          return v27;
        }
        if ( v43 != 1 || (v28 = v42, !*(_BYTE *)v16) )
          v28 = *v12;
        *v9 = v28;
      }
      else if ( (v49 & 1) != 0 )
      {
        LODWORD(v50) = 0;
        v29 = HnsToBlocksRU(0x61A8u, *((_DWORD *)v7 + 2), v7[6], (unsigned int *)va1);
        v14 = v29;
        if ( v29 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x293,
            (unsigned int)"avcore\\audiocore\\server\\lib\\audioengineutil\\endpointutil.cpp",
            (const char *)(unsigned int)v29,
            v39);
          CoTaskMemFree(v22);
          goto LABEL_5;
        }
        v30 = (v50 - 1) & 0xFFFFFFE0;
        while ( 1 )
        {
          v30 += 32;
          if ( v30 >= *v12 )
            break;
          if ( (int)CheckConnectorSupportForPeriodicity(v42, v43, v22, (unsigned int)Src) >= 0 && v30 == v44 )
          {
            *v10 = v44;
            break;
          }
        }
        if ( *v10 < *v12 )
        {
          for ( i = 0; ; i = v50 + 1 )
          {
            LODWORD(v50) = i;
            if ( i >= 3 )
              break;
            v32 = 32 * (1 << i);
            LODWORD(v56) = v32 * ((*v10 - 1) / v32 + 1);
            if ( (unsigned int)v56 < *v12
              && (int)CheckConnectorSupportForPeriodicity(v42, v43, v22, (unsigned int)Src) >= 0
              && v44 == (_DWORD)v56 )
            {
              *v11 = v32;
              break;
            }
          }
          v33 = *v12;
          if ( *v11 == *v12 )
          {
            *v11 = v33;
            *v10 = v33;
          }
        }
      }
    }
    CoTaskMemFree(v22);
LABEL_20:
    *v58 = *v9;
    if ( *v9 > *v12 )
      *v9 = *v12;
    if ( pv )
      CoTaskMemFree(pv);
    return 0;
  }
  v24 = -2005139404;
  if ( v23 == -2005139404 )
  {
    CoTaskMemFree(v22);
LABEL_62:
    if ( pv )
      CoTaskMemFree(pv);
    return v24;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x267,
    (unsigned int)"avcore\\audiocore\\server\\lib\\audioengineutil\\endpointutil.cpp",
    (const char *)(unsigned int)v23,
    v39);
  CoTaskMemFree(v22);
  if ( pv )
    CoTaskMemFree(pv);
  return (unsigned int)v56;
}

```

## disassembly

```asm
0x180020034  mov     rax, rsp
0x180020037  mov     [rax+20h], r9
0x18002003b  mov     [rax+18h], r8d
0x18002003f  mov     [rax+10h], edx
0x180020042  mov     [rax+8], rcx
0x180020046  push    rbp
0x180020047  push    rbx
0x180020048  push    rsi
0x180020049  push    rdi
0x18002004a  push    r12
0x18002004c  push    r13
0x18002004e  push    r14
0x180020050  push    r15
0x180020052  lea     rbp, [rax-47h]
0x180020056  sub     rsp, 88h
0x18002005d  mov     rsi, r9
0x180020060  mov     r8, rcx
0x180020063  mov     ecx, 186A0h
0x180020068  mov     rax, [rbp+3Fh+arg_38]
0x18002006f  test    rax, rax
0x180020072  cmovnz  rcx, rax
0x180020076  mov     [rbp+3Fh+var_60], rcx
0x18002007a  mov     r13, [rbp+3Fh+Src]
0x18002007e  xorps   xmm1, xmm1
0x180020081  cvtsi2sd xmm1, rcx
0x180020086  mov     eax, [r13+4]
0x18002008a  xorps   xmm0, xmm0
0x18002008d  cvtsi2sd xmm0, rax
0x180020092  mulsd   xmm1, xmm0
0x180020096  divsd   xmm1, cs:__real@416312d000000000
0x18002009e  addsd   xmm1, cs:__real@3fe0000000000000
0x1800200a6  cvttsd2si rax, xmm1
0x1800200ab  mov     r14, [rbp+3Fh+arg_58]
0x1800200b2  mov     [r14], eax
0x1800200b5  mov     r15, [rbp+3Fh+pv]
0x1800200bc  mov     [r15], eax
0x1800200bf  mov     r12, [rbp+3Fh+arg_48]
0x1800200c6  mov     [r12], eax
0x1800200ca  mov     rbx, [rbp+3Fh+arg_40]
0x1800200d1  mov     [rbx], eax
0x1800200d3  mov     [rbp+3Fh+pv], 0
0x1800200de  mov     rax, [r8]
0x1800200e1  lea     rdx, [rbp+3Fh+pv]
0x1800200e8  mov     rcx, r8
0x1800200eb  mov     rax, [rax+28h]
0x1800200ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800200f4  mov     edi, eax
0x1800200f6  test    eax, eax
0x1800200f8  jns     short loc_18002012C
0x1800200fa  mov     rcx, [rbp+47h]; this
0x1800200fe  mov     r9d, eax; char *
0x180020101  lea     r8, aAvcoreAudiocor_15; "avcore\\audiocore\\server\\lib\\audioen"...
0x180020108  mov     edx, 227h; void *
0x18002010d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180020112  nop
0x180020113  mov     rcx, [rbp+3Fh+pv]; pv
0x18002011a  test    rcx, rcx
0x18002011d  jz      short loc_180020125
0x18002011f  call    cs:__imp_CoTaskMemFree
0x180020125  mov     eax, edi
0x180020127  jmp     loc_18002024F
0x18002012c  mov     rcx, [rbp+3Fh+pv]
0x180020133  call    cs:__imp_GetClassFromEndpointId
0x180020139  test    eax, eax
0x18002013b  jnz     loc_180020225
0x180020141  mov     rdi, [rbp+3Fh+arg_28]
0x180020145  test    rdi, rdi
0x180020148  jz      loc_180020263
0x18002014e  test    byte ptr [rbp+3Fh+arg_30], 2
0x180020152  jz      loc_180020263
0x180020158  mov     [rbp+3Fh+arg_10], eax
0x18002015b  mov     dword ptr [rbp+3Fh+arg_0], eax
0x18002015e  mov     dword ptr [rbp+3Fh+Src], eax
0x180020161  mov     dword ptr [rbp+3Fh+arg_58], eax
0x180020167  movaps  xmm0, xmmword ptr [rsi]
0x18002016a  movdqa  xmmword ptr [rbp+3Fh+var_50.Data1], xmm0
0x18002016f  lea     rax, [rbp+3Fh+arg_58]
0x180020176  mov     [rsp+50h], rax; unsigned int *
0x18002017b  lea     rax, [rbp+3Fh+Src]
0x18002017f  mov     [rsp+0C0h+var_78], rax; unsigned int *
0x180020184  lea     rax, [rbp+3Fh+arg_0]
0x180020188  mov     [rsp+0C0h+var_80], rax; unsigned int *
0x18002018d  lea     rax, [rbp+3Fh+arg_10]
0x180020191  mov     [rsp+0C0h+var_88], rax; unsigned int *
0x180020196  mov     rax, [rbp+3Fh+var_60]
0x18002019a  mov     [rsp+0C0h+var_A0], rax; int
0x18002019f  lea     r9, [rbp+3Fh+var_50]; struct _GUID *
0x1800201a3  movzx   r8d, word ptr [r13+0Ch]; unsigned __int16
0x1800201a8  mov     edx, [r13+8]; unsigned int
0x1800201ac  mov     rcx, rdi; struct PacketSizeConstraints *
0x1800201af  call    ?GetPacketSizesFromConstraints@@YAJPEBUPacketSizeConstraints@@KGU_GUID@@_K22PEAI333@Z; GetPacketSizesFromConstraints(PacketSizeConstraints const *,ulong,ushort,_GUID,unsigned __int64,unsigned __int64,unsigned __int64,uint *,uint *,uint *,uint *)
0x1800201b4  mov     esi, eax
0x1800201b6  test    eax, eax
0x1800201b8  jns     short loc_1800201E9
0x1800201ba  mov     rcx, [rbp+47h]; this
0x1800201be  mov     r9d, eax; char *
0x1800201c1  lea     r8, aAvcoreAudiocor_15; "avcore\\audiocore\\server\\lib\\audioen"...
0x1800201c8  mov     edx, 23Ch; void *
0x1800201cd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800201d2  nop
0x1800201d3  mov     rcx, [rbp+3Fh+pv]; pv
0x1800201da  test    rcx, rcx
0x1800201dd  jz      short loc_1800201E5
0x1800201df  call    cs:__imp_CoTaskMemFree
0x1800201e5  mov     eax, esi
0x1800201e7  jmp     short loc_18002024F
0x1800201e9  mov     eax, [rbp+3Fh+arg_10]
0x1800201ec  mov     [r14], eax
0x1800201ef  mov     [r15], eax
0x1800201f2  mov     [r12], eax
0x1800201f6  mov     [rbx], eax
0x1800201f8  cmp     [rbp+3Fh+arg_38], 0
0x180020200  jnz     short loc_180020225
0x180020202  mov     eax, dword ptr [rbp+3Fh+arg_0]
0x180020205  mov     [r12], eax
0x180020209  mov     eax, dword ptr [rbp+3Fh+Src]
0x18002020c  mov     [r15], eax
0x18002020f  cmp     [rbp+3Fh+arg_8], 1
0x180020213  jnz     short loc_180020220
0x180020215  cmp     byte ptr [rdi], 0
0x180020218  mov     eax, dword ptr [rbp+3Fh+arg_58]
0x18002021e  jnz     short loc_180020222
0x180020220  mov     eax, [rbx]
0x180020222  mov     [r14], eax
0x180020225  mov     ecx, [r14]
0x180020228  mov     rax, [rbp+3Fh+arg_60]
0x18002022f  mov     [rax], ecx
0x180020231  mov     eax, [rbx]
0x180020233  cmp     [r14], eax
0x180020236  jbe     short loc_18002023B
0x180020238  mov     [r14], eax
0x18002023b  mov     rcx, [rbp+3Fh+pv]; pv
0x180020242  test    rcx, rcx
0x180020245  jz      short loc_18002024D
0x180020247  call    cs:__imp_CoTaskMemFree
0x18002024d  xor     eax, eax
0x18002024f  add     rsp, 88h
0x180020256  pop     r15
0x180020258  pop     r14
0x18002025a  pop     r13
0x18002025c  pop     r12
0x18002025e  pop     rdi
0x18002025f  pop     rsi
0x180020260  pop     rbx
0x180020261  pop     rbp
0x180020262  retn
0x180020263  movzx   eax, word ptr [r13+10h]
0x180020268  add     eax, 40h ; '@'
0x18002026b  mov     dword ptr [rbp+3Fh+Src], eax
0x18002026e  mov     ecx, eax; cb
0x180020270  call    cs:__imp_CoTaskMemAlloc
0x180020276  mov     rsi, rax
0x180020279  mov     [rbp+3Fh+arg_48], rax
0x180020280  test    rax, rax
0x180020283  jz      loc_1800205B4
0x180020289  movzx   ecx, word ptr [r13+10h]
0x18002028e  add     ecx, 40h ; '@'
0x180020291  mov     [rax], ecx
0x180020293  mov     rcx, [rbp+3Fh+pv]
0x18002029a  call    cs:__imp_GetSessionIdFromEndpointId
0x1800202a0  mov     [rsi+4], eax
0x1800202a3  mov     dword ptr [rsi+8], 0
0x1800202aa  mov     rax, [rbp+3Fh+arg_18]
0x1800202ae  movaps  xmm0, xmmword ptr [rax]
0x1800202b1  movdqu  xmmword ptr [rsi+0Ch], xmm0
0x1800202b6  movzx   r8d, word ptr [r13+10h]
0x1800202bb  add     r8, 12h; Size
0x1800202bf  lea     rcx, [rsi+2Ch]; void *
0x1800202c3  mov     rdx, r13; Src
0x1800202c6  call    memcpy_0
0x1800202cb  mov     [rbp+3Fh+arg_10], 0
0x1800202d2  lea     rax, [rbp+3Fh+arg_10]
0x1800202d6  mov     [rsp+28h], rax; unsigned __int64
0x1800202db  mov     rax, [rbp+3Fh+var_60]
0x1800202df  mov     [rsp+0C0h+var_A0], rax; int
0x1800202e4  mov     r9d, dword ptr [rbp+3Fh+Src]
0x1800202e8  mov     r8, rsi
0x1800202eb  mov     edx, [rbp+3Fh+arg_8]
0x1800202ee  mov     rcx, [rbp+3Fh+arg_0]
0x1800202f2  call    ?CheckConnectorSupportForPeriodicity@@YAJPEAUIMMDevice@@W4AUDIO_DIRECTION@@PEAUAUDIO_ENDPOINT_SHARED_CREATE_PARAMS_FOR_KS_ENDPOINTS@@I_JPEAI@Z; CheckConnectorSupportForPeriodicity(IMMDevice *,AUDIO_DIRECTION,AUDIO_ENDPOINT_SHARED_CREATE_PARAMS_FOR_KS_ENDPOINTS *,uint,__int64,uint *)
0x1800202f7  mov     dword ptr [rbp+3Fh+arg_58], eax
0x1800202fd  xor     ecx, ecx
0x1800202ff  test    eax, eax
0x180020301  jns     short loc_18002035A
0x180020303  mov     ebx, 887C0034h
0x180020308  cmp     eax, ebx
0x18002030a  jnz     short loc_18002031A
0x18002030c  mov     rcx, rsi; pv
0x18002030f  call    cs:__imp_CoTaskMemFree
0x180020315  jmp     loc_1800205D2
0x18002031a  mov     rcx, [rbp+47h]; this
0x18002031e  mov     r9d, eax; char *
0x180020321  lea     r8, aAvcoreAudiocor_15; "avcore\\audiocore\\server\\lib\\audioen"...
0x180020328  mov     edx, 267h; void *
0x18002032d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180020332  nop
0x180020333  mov     rcx, rsi; pv
0x180020336  call    cs:__imp_CoTaskMemFree
0x18002033c  nop
0x18002033d  mov     rcx, [rbp+3Fh+pv]; pv
0x180020344  test    rcx, rcx
0x180020347  jz      short loc_18002034F
0x180020349  call    cs:__imp_CoTaskMemFree
0x18002034f  mov     eax, dword ptr [rbp+3Fh+arg_58]
0x180020355  jmp     loc_18002024F
0x18002035a  mov     eax, [rbp+3Fh+arg_10]
0x18002035d  mov     [r14], eax
0x180020360  mov     [r15], eax
0x180020363  mov     [r12], eax
0x180020367  mov     [rbx], eax
0x180020369  cmp     [rbp+3Fh+arg_38], rcx
0x180020370  jnz     loc_1800205A6
0x180020376  test    rdi, rdi
0x180020379  jz      loc_180020420
0x18002037f  mov     dword ptr [rbp+3Fh+arg_0], ecx
0x180020382  mov     rax, [rbp+3Fh+arg_18]
0x180020386  movaps  xmm0, xmmword ptr [rax]
0x180020389  movdqa  xmmword ptr [rbp+3Fh+var_50.Data1], xmm0
0x18002038e  lea     rax, [rbp+3Fh+arg_0]
0x180020392  mov     [rsp+50h], rax; unsigned int *
0x180020397  mov     [rsp+0C0h+var_78], r15; unsigned int *
0x18002039c  mov     [rsp+0C0h+var_80], r12; unsigned int *
0x1800203a1  mov     [rsp+0C0h+var_88], rbx; unsigned int *
0x1800203a6  mov     [rsp+0C0h+var_A0], 186A0h; int
0x1800203af  lea     r9, [rbp+3Fh+var_50]; struct _GUID *
0x1800203b3  movzx   r8d, word ptr [r13+0Ch]; unsigned __int16
0x1800203b8  mov     edx, [r13+8]; unsigned int
0x1800203bc  mov     rcx, rdi; struct PacketSizeConstraints *
0x1800203bf  call    ?GetPacketSizesFromConstraints@@YAJPEBUPacketSizeConstraints@@KGU_GUID@@_K22PEAI333@Z; GetPacketSizesFromConstraints(PacketSizeConstraints const *,ulong,ushort,_GUID,unsigned __int64,unsigned __int64,unsigned __int64,uint *,uint *,uint *,uint *)
0x1800203c4  mov     r15d, eax
0x1800203c7  test    eax, eax
0x1800203c9  jns     short loc_180020408
0x1800203cb  mov     rcx, [rbp+47h]; this
0x1800203cf  mov     r9d, eax; char *
0x1800203d2  lea     r8, aAvcoreAudiocor_15; "avcore\\audiocore\\server\\lib\\audioen"...
0x1800203d9  mov     edx, 282h; void *
0x1800203de  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800203e3  nop
0x1800203e4  mov     rcx, rsi; pv
0x1800203e7  call    cs:__imp_CoTaskMemFree
0x1800203ed  nop
0x1800203ee  mov     rcx, [rbp+3Fh+pv]; pv
0x1800203f5  test    rcx, rcx
0x1800203f8  jz      short loc_180020400
0x1800203fa  call    cs:__imp_CoTaskMemFree
0x180020400  mov     eax, r15d
0x180020403  jmp     loc_18002024F
0x180020408  cmp     [rbp+3Fh+arg_8], 1
0x18002040c  jnz     short loc_180020416
0x18002040e  cmp     byte ptr [rdi], 0
0x180020411  mov     eax, dword ptr [rbp+3Fh+arg_0]
0x180020414  jnz     short loc_180020418
0x180020416  mov     eax, [rbx]
0x180020418  mov     [r14], eax
0x18002041b  jmp     loc_1800205A6
0x180020420  test    byte ptr [rbp+3Fh+arg_30], 1
0x180020424  jz      loc_1800205A6
0x18002042a  mov     dword ptr [rbp+3Fh+arg_38], ecx
0x180020430  movzx   r8d, word ptr [r13+0Ch]; unsigned int
0x180020435  lea     r9, [rbp+3Fh+arg_38]; unsigned int *
0x18002043c  mov     edx, [r13+8]; unsigned int
0x180020440  mov     ecx, 61A8h; unsigned __int64
0x180020445  call    ?HnsToBlocksRU@@YAJ_KKKPEAK@Z; HnsToBlocksRU(unsigned __int64,ulong,ulong,ulong *)
0x18002044a  mov     edi, eax
0x18002044c  test    eax, eax
0x18002044e  jns     short loc_180020477
0x180020450  mov     rcx, [rbp+47h]; this
0x180020454  mov     r9d, eax; char *
0x180020457  lea     r8, aAvcoreAudiocor_15; "avcore\\audiocore\\server\\lib\\audioen"...
0x18002045e  mov     edx, 293h; void *
0x180020463  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180020468  nop
0x180020469  mov     rcx, rsi; pv
0x18002046c  call    cs:__imp_CoTaskMemFree
0x180020472  jmp     loc_180020113
0x180020477  mov     edi, dword ptr [rbp+3Fh+arg_38]
0x18002047d  dec     edi
0x18002047f  and     edi, 0FFFFFFE0h
0x180020482  add     edi, 20h ; ' '
0x180020485  cmp     edi, [rbx]
0x180020487  jnb     short loc_1800204E7
0x180020489  mov     eax, edi
0x18002048b  xorps   xmm1, xmm1
0x18002048e  cvtsi2sd xmm1, rax
0x180020493  mulsd   xmm1, cs:__real@416312d000000000
0x18002049b  mov     eax, [r13+4]
0x18002049f  xorps   xmm0, xmm0
0x1800204a2  cvtsi2sd xmm0, rax
0x1800204a7  divsd   xmm1, xmm0
0x1800204ab  addsd   xmm1, cs:__real@3fe0000000000000
0x1800204b3  cvttsd2si rax, xmm1
0x1800204b8  lea     rcx, [rbp+3Fh+arg_10]
0x1800204bc  mov     [rsp+28h], rcx
0x1800204c1  mov     [rsp+0C0h+var_A0], rax
0x1800204c6  mov     r9d, dword ptr [rbp+3Fh+Src]
0x1800204ca  mov     r8, rsi
0x1800204cd  mov     edx, [rbp+3Fh+arg_8]
0x1800204d0  mov     rcx, [rbp+3Fh+arg_0]
0x1800204d4  call    ?CheckConnectorSupportForPeriodicity@@YAJPEAUIMMDevice@@W4AUDIO_DIRECTION@@PEAUAUDIO_ENDPOINT_SHARED_CREATE_PARAMS_FOR_KS_ENDPOINTS@@I_JPEAI@Z; CheckConnectorSupportForPeriodicity(IMMDevice *,AUDIO_DIRECTION,AUDIO_ENDPOINT_SHARED_CREATE_PARAMS_FOR_KS_ENDPOINTS *,uint,__int64,uint *)
0x1800204d9  test    eax, eax
  ... truncated ...
```
