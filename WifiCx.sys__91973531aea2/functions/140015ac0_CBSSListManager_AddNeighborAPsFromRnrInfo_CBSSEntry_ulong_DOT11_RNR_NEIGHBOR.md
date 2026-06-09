# CBSSListManager::AddNeighborAPsFromRnrInfo(CBSSEntry *,ulong,DOT11_RNR_NEIGHBOR *)

- ea: `0x140015ac0`
- end: `0x1400161db`
- name: `?AddNeighborAPsFromRnrInfo@CBSSListManager@@QEAAHPEAVCBSSEntry@@KPEAUDOT11_RNR_NEIGHBOR@@@Z`
- size: `1819`
- prototype: `__int64 __fastcall(CBSSListManager *__hidden this, struct CBSSEntry *, unsigned int, struct DOT11_RNR_NEIGHBOR *)`
- caller_count: `3`
- callee_count: `16`
- tags: `file_ops, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x14000c110`
- `0x14000d120`
- `0x140010520`

## callees

- `0x140009420`
- `0x14000c778`
- `0x14000c940`
- `0x140015a40`
- `0x140015ac0`
- `0x1400161e4`
- `0x140016280`
- `0x1400291fc`
- `0x1400684cc`
- `0x14009adbc`
- `0x14009af20`
- `0x14009b07c`
- `0x14009b634`
- `0x14009b79c`
- `0x1400dfd00`
- `0x1400dfd40`

## import_xrefs

- `ntoskrnl!RtlCompareMemory` at `0x140015ef8`
- `ntoskrnl!RtlCompareMemory` at `0x140015ef8`

## pseudocode

```c
__int64 __fastcall CBSSListManager::AddNeighborAPsFromRnrInfo(
        CBSSListManager *this,
        struct CBSSEntry *a2,
        unsigned int a3,
        struct DOT11_RNR_NEIGHBOR *a4)
{
  struct DOT11_RNR_NEIGHBOR *v6; // r12
  int v7; // edx
  void *v8; // rdi
  unsigned int v9; // ebx
  __int64 i; // rsi
  __int64 v11; // rdx
  __int64 v12; // r8
  unsigned int v13; // r11d
  __int64 v14; // r10
  __int64 v15; // r9
  __int64 v16; // r11
  __int64 v17; // rcx
  __int64 v18; // rax
  void *v19; // rcx
  __int64 v20; // rax
  int v21; // r8d
  int v22; // r9d
  unsigned int v23; // ebp
  char *v24; // rax
  __int64 v25; // rsi
  int v26; // r8d
  unsigned __int8 v27; // dl
  int v28; // edx
  unsigned int v29; // r14d
  unsigned __int8 v30; // bl
  __int128 *v31; // r9
  char *v32; // r15
  unsigned __int8 IsHiddenSSID; // al
  __int128 *v34; // rcx
  __int64 v35; // r8
  __int64 v36; // rax
  int v37; // edx
  int v38; // r8d
  char v39; // r12
  const char *v40; // rax
  __int64 result; // rax
  int v42; // [rsp+20h] [rbp-148h]
  int v43; // [rsp+A4h] [rbp-C4h]
  char v45; // [rsp+C0h] [rbp-A8h]
  unsigned int v47; // [rsp+D0h] [rbp-98h]
  __int128 *v48; // [rsp+D8h] [rbp-90h]
  char *v50; // [rsp+E8h] [rbp-80h]
  __int128 v51; // [rsp+F0h] [rbp-78h] BYREF
  __int128 v52; // [rsp+100h] [rbp-68h]
  int v53; // [rsp+110h] [rbp-58h]

  v53 = 0;
  v43 = 0;
  v51 = 0;
  v52 = 0;
  v6 = a4;
  v8 = operator new(saturated_mul(a3, 0x28u));
  if ( v8 )
  {
    for ( i = 0; (unsigned int)i < *((_DWORD *)a2 + 175); i = (unsigned int)(i + 1) )
    {
      v11 = 0;
      v12 = *(_QWORD *)(*((_QWORD *)a2 + 88) + 40 * i);
      v13 = *(_DWORD *)(v12 + 712);
      while ( (unsigned int)v11 < v13 )
      {
        v14 = *(_QWORD *)(v12 + 720);
        v15 = v14 + 40 * v11;
        if ( *(struct CBSSEntry **)v15 == a2 )
        {
          v16 = v13 - 1;
          if ( (unsigned int)v11 < (unsigned int)v16 )
          {
            *(_OWORD *)v15 = *(_OWORD *)(v14 + 40 * v16);
            *(_OWORD *)(v15 + 16) = *(_OWORD *)(v14 + 40 * v16 + 16);
            *(_QWORD *)(v15 + 32) = *(_QWORD *)(v14 + 40 * v16 + 32);
          }
          v17 = 5LL * (unsigned int)(*(_DWORD *)(v12 + 712) - 1);
          v18 = *(_QWORD *)(v12 + 720);
          *(_OWORD *)(v18 + 8 * v17) = 0;
          *(_OWORD *)(v18 + 8 * v17 + 16) = 0;
          *(_QWORD *)(v18 + 8 * v17 + 32) = 0;
          --*(_DWORD *)(v12 + 712);
          goto LABEL_14;
        }
        v11 = (unsigned int)(v11 + 1);
      }
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        WPP_RECORDER_SF_qddq_MAC_q_MAC_(
          WPP_GLOBAL_Control->DeviceExtension,
          v11,
          v12,
          287,
          v42,
          v12,
          v13,
          *(_DWORD *)(v12 + 700),
          (char)a2,
          (__int64)a2 + 32,
          v12,
          v12 + 32);
LABEL_14:
      ;
    }
    v19 = (void *)*((_QWORD *)a2 + 88);
    if ( v19 )
      operator delete(v19);
    v20 = *(_QWORD *)a2;
    *((_QWORD *)a2 + 88) = v8;
    *((_DWORD *)a2 + 175) = 0;
    *((_DWORD *)a2 + 173) = a3;
    (*(void (__fastcall **)(struct CBSSEntry *, __int128 *))(v20 + 16))(a2, &v51);
    v47 = *((_DWORD *)a2 + 172);
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
      && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
    {
      WPP_RECORDER_SF_q_SSID_D_MAC_d(
        WPP_GLOBAL_Control->DeviceExtension,
        *((_DWORD *)a2 + 172),
        v21,
        v22,
        v42,
        (char)a2,
        (__int64)&v51,
        *((_DWORD *)a2 + 172),
        (__int64)a2 + 32,
        a3);
    }
    v23 = 0;
    if ( !a3 )
    {
      v9 = 0;
      goto LABEL_59;
    }
    v24 = (char *)a2 + 901;
    v25 = 0;
    v50 = (char *)a2 + 901;
    while ( 1 )
    {
      v45 = ConvertCountryCodeOperatingClassToBand(v24, *((unsigned __int8 *)v6 + 20 * v25 + 2));
      Feature_Bugfix_54405666__private_IsEnabledDeviceUsageNoInline();
      v27 = *((_BYTE *)v6 + 20 * v25 + 1);
      if ( (unsigned __int8)(v27 - 8) <= 1u )
      {
        v30 = *((_BYTE *)v6 + 20 * v25 + 11);
        v29 = 0;
      }
      else if ( (unsigned __int8)(v27 - 12) <= 1u )
      {
        v29 = *(_DWORD *)((char *)v6 + 20 * v25 + 11);
        v30 = *((_BYTE *)v6 + 20 * v25 + 15);
      }
      else
      {
        if ( v27 <= 0xFu )
        {
          if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            v28 = v43 + 1;
            LOBYTE(v28) = 2;
            WPP_RECORDER_SF_dddd(
              WPP_GLOBAL_Control->DeviceExtension,
              v28,
              v26,
              161,
              (__int64)WPP_3599b95ca20c3e0ba686e8b05788690d_Traceguids,
              v43 + 1,
              v23 + 1,
              a3,
              *((_BYTE *)v6 + 20 * v25 + 1));
          }
          goto LABEL_50;
        }
        v29 = *(_DWORD *)((char *)v6 + 20 * v25 + 11);
        v30 = *((_BYTE *)v6 + 20 * v25 + 15);
      }
      LODWORD(v31) = 0;
      v48 = 0;
      v32 = (char *)a4 + 20 * v25 + 5;
      if ( v47 )
      {
        if ( (((*((_WORD *)a4 + 10 * v25) & 4) == 0) & (unsigned __int8)~(v30 >> 1)) != 0 || v29 )
        {
          if ( v29 != v47 )
            goto LABEL_39;
        }
        else
        {
          v29 = v47;
        }
        IsHiddenSSID = Dot11IsHiddenSSID((unsigned __int8 *)&v51 + 4, v51);
        v34 = &v51;
        if ( IsHiddenSSID )
          v34 = v31;
        v48 = v34;
      }
LABEL_39:
      if ( !v29 || RtlCompareMemory(v32, (char *)a2 + 32, 6u) == 6 )
      {
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
          && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
        {
          v6 = a4;
          WPP_RECORDER_SF_dddD_MAC_d(
            WPP_GLOBAL_Control->DeviceExtension,
            v23 + 1,
            v43 + 1,
            (_DWORD)v31,
            v42,
            v43 + 1,
            v23 + 1,
            a3,
            v29,
            (__int64)v32,
            *((_BYTE *)a4 + 20 * v25 + 1));
          goto LABEL_50;
        }
      }
      else
      {
        LOWORD(v42) = *((_WORD *)a4 + 10 * v25);
        v36 = CBSSListManager::AddNeighborAP(this, a2, v35, v29);
        v39 = v36;
        if ( v36 )
        {
          if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
            && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
          {
            v40 = "Same";
            if ( !v48 )
              v40 = "None";
            WPP_RECORDER_SF_dddqqddDD_MAC_D_SSID__MAC_Ds(
              WPP_GLOBAL_Control->DeviceExtension,
              v30,
              *((unsigned __int16 *)a4 + 10 * v25),
              *((unsigned __int8 *)a4 + 20 * v25 + 3),
              v42,
              v43 + 1,
              v23 + 1,
              a3,
              (char)a2,
              v39,
              v45,
              *((_BYTE *)a4 + 20 * v25 + 3),
              *((_WORD *)a4 + 10 * v25),
              v30,
              (__int64)a2 + 32,
              *((_DWORD *)a2 + 172),
              (__int64)&v51,
              (__int64)v32,
              v29,
              (__int64)v40);
          }
          ++v43;
        }
        else if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(v37) = 2;
          WPP_RECORDER_SF_dddD_MAC__MAC_(
            WPP_GLOBAL_Control->DeviceExtension,
            v37,
            v38,
            164,
            (__int64)WPP_3599b95ca20c3e0ba686e8b05788690d_Traceguids,
            v43 + 1,
            v23 + 1,
            a3,
            v29,
            (__int64)a2 + 32,
            (__int64)v32);
        }
      }
      v6 = a4;
LABEL_50:
      v24 = v50;
      ++v23;
      ++v25;
      if ( v23 >= a3 )
      {
        v9 = 0;
        goto LABEL_59;
      }
    }
  }
  v9 = -1073741670;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v7) = 2;
    WPP_RECORDER_SF_d(
      WPP_GLOBAL_Control->DeviceExtension,
      v7,
      1,
      159,
      (__int64)WPP_3599b95ca20c3e0ba686e8b05788690d_Traceguids,
      a3);
  }
LABEL_59:
  result = 0;
  if ( !v43 )
    return v9;
  return result;
}

```

## disassembly

```asm
0x140015ac0  mov     r11, rsp
0x140015ac3  push    rbx
0x140015ac4  push    rdi
0x140015ac5  push    r12
0x140015ac7  push    r13
0x140015ac9  push    r14
0x140015acb  sub     rsp, 140h
0x140015ad2  mov     rax, cs:__security_cookie
0x140015ad9  xor     rax, rsp
0x140015adc  mov     [rsp+168h+var_50], rax
0x140015ae4  xor     eax, eax
0x140015ae6  mov     [rsp+168h+var_88], rcx
0x140015aee  mov     [r11-58h], eax
0x140015af2  xorps   xmm0, xmm0
0x140015af5  mov     [rsp+168h+var_C4], eax
0x140015afc  mov     r14, rdx
0x140015aff  mov     r13d, r8d
0x140015b02  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x140015b09  mov     [rsp+168h+var_A0], rdx
0x140015b11  mov     eax, 28h ; '('
0x140015b16  mul     r13
0x140015b19  movups  xmmword ptr [r11-78h], xmm0
0x140015b1e  movups  xmmword ptr [r11-68h], xmm0
0x140015b23  mov     r12, r9
0x140015b26  mov     [rsp+168h+var_C0], r9
0x140015b2e  cmovb   rax, rcx
0x140015b32  mov     rcx, rax; unsigned __int64
0x140015b35  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140015b3a  mov     rdi, rax
0x140015b3d  test    rax, rax
0x140015b40  jnz     short loc_140015B8F
0x140015b42  mov     ebx, 0C000009Ah
0x140015b47  lea     rax, WPP_RECORDER_INITIALIZED
0x140015b4e  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140015b55  jz      loc_1400161AE
0x140015b5b  mov     rcx, cs:WPP_GLOBAL_Control
0x140015b62  lea     rax, WPP_3599b95ca20c3e0ba686e8b05788690d_Traceguids
0x140015b69  mov     r9d, 9Fh
0x140015b6f  mov     dword ptr [rsp+168h+var_140], r13d
0x140015b74  mov     r8d, 1
0x140015b7a  mov     [rsp+168h+var_148], rax
0x140015b7f  mov     dl, 2
0x140015b81  mov     rcx, [rcx+40h]
0x140015b85  call    WPP_RECORDER_SF_d
0x140015b8a  jmp     loc_1400161AE
0x140015b8f  mov     [rsp+168h+var_30], rbp
0x140015b97  mov     [rsp+168h+var_38], rsi
0x140015b9f  xor     esi, esi
0x140015ba1  mov     [rsp+168h+var_40], r15
0x140015ba9  lea     r15, WPP_RECORDER_INITIALIZED
0x140015bb0  mov     [rsp+168h+var_A4], 0
0x140015bbb  cmp     [r14+2BCh], esi
0x140015bc2  jbe     loc_140015CBA
0x140015bc8  mov     rax, [r14+2C0h]
0x140015bcf  lea     rcx, [rsi+rsi*4]
0x140015bd3  xor     edx, edx
0x140015bd5  mov     r8, [rax+rcx*8]
0x140015bd9  mov     r11d, [r8+2C8h]
0x140015be0  cmp     edx, r11d
0x140015be3  jnb     short loc_140015C5B
0x140015be5  mov     r10, [r8+2D0h]
0x140015bec  lea     rcx, [rdx+rdx*4]
0x140015bf0  cmp     [r10+rcx*8], r14
0x140015bf4  lea     r9, [r10+rcx*8]
0x140015bf8  jz      short loc_140015BFE
0x140015bfa  inc     edx
0x140015bfc  jmp     short loc_140015BE0
0x140015bfe  dec     r11d
0x140015c01  cmp     edx, r11d
0x140015c04  jnb     short loc_140015C2B
0x140015c06  lea     rcx, [r11+r11*4]
0x140015c0a  movups  xmm0, xmmword ptr [r10+rcx*8]
0x140015c0f  movups  xmmword ptr [r9], xmm0
0x140015c13  movups  xmm1, xmmword ptr [r10+rcx*8+10h]
0x140015c19  movups  xmmword ptr [r9+10h], xmm1
0x140015c1e  movsd   xmm0, qword ptr [r10+rcx*8+20h]
0x140015c25  movsd   qword ptr [r9+20h], xmm0
0x140015c2b  mov     eax, [r8+2C8h]
0x140015c32  xorps   xmm0, xmm0
0x140015c35  dec     eax
0x140015c37  xor     edx, edx
0x140015c39  lea     rcx, [rax+rax*4]
0x140015c3d  mov     rax, [r8+2D0h]
0x140015c44  movups  xmmword ptr [rax+rcx*8], xmm0
0x140015c48  movups  xmmword ptr [rax+rcx*8+10h], xmm0
0x140015c4d  mov     [rax+rcx*8+20h], rdx
0x140015c52  dec     dword ptr [r8+2C8h]
0x140015c59  jmp     short loc_140015CAB
0x140015c5b  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x140015c62  jz      short loc_140015CAB
0x140015c64  lea     rax, [r8+20h]
0x140015c68  mov     r9d, 11Fh
0x140015c6e  mov     [rsp+168h+var_110], rax
0x140015c73  lea     rcx, [r14+20h]
0x140015c77  mov     eax, [r8+2BCh]
0x140015c7e  mov     [rsp+168h+var_118], r8
0x140015c83  mov     [rsp+168h+var_120], rcx
0x140015c88  mov     rcx, cs:WPP_GLOBAL_Control
0x140015c8f  mov     [rsp+168h+var_128], r14
0x140015c94  mov     dword ptr [rsp+168h+var_130], eax
0x140015c98  mov     dword ptr [rsp+168h+var_138], r11d
0x140015c9d  mov     rcx, [rcx+40h]
0x140015ca1  mov     [rsp+168h+var_140], r8
0x140015ca6  call    WPP_RECORDER_SF_qddq_MAC_q_MAC_
0x140015cab  inc     esi
0x140015cad  cmp     esi, [r14+2BCh]
0x140015cb4  jb      loc_140015BC8
0x140015cba  mov     rcx, [r14+2C0h]; void *
0x140015cc1  test    rcx, rcx
0x140015cc4  jz      short loc_140015CCB
0x140015cc6  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140015ccb  mov     rax, [r14]
0x140015cce  lea     rdx, [rsp+168h+var_78]
0x140015cd6  mov     rcx, r14
0x140015cd9  mov     [r14+2C0h], rdi
0x140015ce0  mov     dword ptr [r14+2BCh], 0
0x140015ceb  mov     [r14+2B4h], r13d
0x140015cf2  mov     rax, [rax+10h]
0x140015cf6  call    _guard_dispatch_icall
0x140015cfb  mov     edx, [r14+2B0h]
0x140015d02  mov     [rsp+168h+var_98], edx
0x140015d09  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x140015d10  jz      short loc_140015D53
0x140015d12  mov     rcx, cs:WPP_GLOBAL_Control
0x140015d19  cmp     byte ptr [rcx+29h], 5
0x140015d1d  jnb     short loc_140015D26
0x140015d1f  cmp     word ptr [rcx+48h], 0
0x140015d24  jz      short loc_140015D53
0x140015d26  mov     rcx, [rcx+40h]
0x140015d2a  lea     rax, [r14+20h]
0x140015d2e  mov     dword ptr [rsp+168h+var_120], r13d
0x140015d33  mov     [rsp+168h+var_128], rax
0x140015d38  lea     rax, [rsp+168h+var_78]
0x140015d40  mov     dword ptr [rsp+168h+var_130], edx
0x140015d44  mov     [rsp+168h+var_138], rax
0x140015d49  mov     [rsp+168h+var_140], r14
0x140015d4e  call    WPP_RECORDER_SF_q_SSID_D_MAC_d
0x140015d53  xor     ebp, ebp
0x140015d55  test    r13d, r13d
0x140015d58  jz      loc_140016194
0x140015d5e  lea     rax, [r14+385h]
0x140015d65  xor     esi, esi
0x140015d67  mov     [rsp+168h+var_80], rax
0x140015d6f  lea     rbx, WPP_3599b95ca20c3e0ba686e8b05788690d_Traceguids
0x140015d76  nop     word ptr [rax+rax+00000000h]
0x140015d80  xor     ecx, ecx
0x140015d82  lea     rdi, [rsi+rsi*4]
0x140015d86  movzx   edx, byte ptr [r12+rdi*4+2]
0x140015d8c  mov     [rsp+168h+var_A7], cx
0x140015d94  mov     [rsp+168h+var_C8], cl
0x140015d9b  mov     rcx, rax
0x140015d9e  call    ConvertCountryCodeOperatingClassToBand
0x140015da3  mov     [rsp+0C0h], eax
0x140015daa  call    Feature_Bugfix_54405666__private_IsEnabledDeviceUsageNoInline
0x140015daf  movzx   edx, byte ptr [r12+rdi*4+1]
0x140015db5  lea     ecx, [rdx-8]
0x140015db8  cmp     cl, 1
0x140015dbb  jbe     loc_140015E4C
0x140015dc1  lea     ecx, [rdx-0Ch]
0x140015dc4  cmp     cl, 1
0x140015dc7  jbe     short loc_140015E3C
0x140015dc9  cmp     dl, 0Fh
0x140015dcc  ja      short loc_140015E1C
0x140015dce  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x140015dd5  jz      loc_14001608C
0x140015ddb  mov     eax, edx
0x140015ddd  lea     ecx, [rbp+1]
0x140015de0  mov     edx, [rsp+168h+var_C4]
0x140015de7  mov     r9d, 0A1h
0x140015ded  mov     dword ptr [rsp+168h+var_128], eax
0x140015df1  inc     edx
0x140015df3  mov     dword ptr [rsp+168h+var_130], r13d
0x140015df8  mov     dword ptr [rsp+168h+var_138], ecx
0x140015dfc  mov     rcx, cs:WPP_GLOBAL_Control
0x140015e03  mov     dword ptr [rsp+168h+var_140], edx
0x140015e07  mov     dl, 2
0x140015e09  mov     [rsp+168h+var_148], rbx
0x140015e0e  mov     rcx, [rcx+40h]
0x140015e12  call    WPP_RECORDER_SF_dddd
0x140015e17  jmp     loc_14001608C
0x140015e1c  movzx   eax, byte ptr [r12+rdi*4+11h]
0x140015e22  mov     r14d, [r12+rdi*4+0Bh]
0x140015e27  movzx   ebx, byte ptr [r12+rdi*4+0Fh]
0x140015e2d  movzx   r12d, word ptr [r12+rdi*4+12h]
0x140015e33  mov     [rsp+168h+var_C8], al
0x140015e3a  jmp     short loc_140015E5B
0x140015e3c  mov     r14d, [r12+rdi*4+0Bh]
0x140015e41  movzx   ebx, byte ptr [r12+rdi*4+0Fh]
0x140015e47  xor     r12d, r12d
0x140015e4a  jmp     short loc_140015E5B
0x140015e4c  movzx   ebx, byte ptr [r12+rdi*4+0Bh]
0x140015e52  xor     r14d, r14d
0x140015e55  xor     eax, eax
0x140015e57  movzx   r12d, ax
0x140015e5b  mov     rax, [rsp+168h+var_C0]
0x140015e63  xor     r9d, r9d
0x140015e66  mov     edx, [rsp+168h+var_98]
0x140015e6d  mov     [rsp+168h+var_90], r9
0x140015e75  lea     r15, [rax+5]
0x140015e79  lea     r15, [r15+rdi*4]
0x140015e7d  test    edx, edx
0x140015e7f  jz      short loc_140015EDA
0x140015e81  movzx   eax, word ptr [rax+rdi*4]
0x140015e85  movzx   ecx, bl
0x140015e88  shr     cl, 1
0x140015e8a  mov     r8d, 2
0x140015e90  bt      ax, r8w
0x140015e95  not     cl
0x140015e97  setnb   al
0x140015e9a  and     cl, al
0x140015e9c  test    cl, 1
0x140015e9f  jnz     short loc_140015EAB
0x140015ea1  test    r14d, r14d
0x140015ea4  jnz     short loc_140015EAB
0x140015ea6  mov     r14d, edx
0x140015ea9  jmp     short loc_140015EB0
0x140015eab  cmp     r14d, edx
0x140015eae  jnz     short loc_140015EDA
0x140015eb0  mov     edx, [rsp+168h+var_78]; unsigned int
0x140015eb7  lea     rcx, [rsp+168h+var_74]; unsigned __int8 *
0x140015ebf  call    ?Dot11IsHiddenSSID@@YAEPEAEK@Z; Dot11IsHiddenSSID(uchar *,ulong)
0x140015ec4  test    al, al
0x140015ec6  lea     rcx, [rsp+168h+var_78]
0x140015ece  cmovnz  rcx, r9
0x140015ed2  mov     [rsp+168h+var_90], rcx
0x140015eda  test    r14d, r14d
0x140015edd  jz      loc_14001611B
0x140015ee3  mov     rdx, [rsp+168h+var_A0]
0x140015eeb  mov     r8d, 6; Length
0x140015ef1  add     rdx, 20h ; ' '; Source2
0x140015ef5  mov     rcx, r15; Source1
0x140015ef8  call    cs:__imp_RtlCompareMemory
0x140015eff  nop     dword ptr [rax+rax+00h]
0x140015f04  cmp     rax, 6
0x140015f08  jz      loc_14001611B
0x140015f0e  movzx   eax, [rsp+168h+var_C8]
0x140015f16  mov     r9d, r14d
0x140015f19  mov     rcx, [rsp+168h+var_C0]
0x140015f21  mov     rdx, [rsp+168h+var_A0]
0x140015f29  mov     [rsp+168h+var_B8], al
0x140015f30  mov     [rsp+168h+var_B7], r12w
0x140015f39  movzx   eax, byte ptr [rcx+rdi*4+3]
0x140015f3e  mov     byte ptr [rsp+168h+var_120], al
0x140015f42  mov     eax, [rsp+0C0h]
0x140015f49  mov     dword ptr [rsp+168h+var_128], eax
0x140015f4d  lea     rax, [rsp+168h+var_B8]
0x140015f55  mov     [rsp+168h+var_130], r15
0x140015f5a  mov     [rsp+168h+var_138], rax
0x140015f5f  movzx   eax, word ptr [rcx+rdi*4]
0x140015f63  mov     rcx, [rsp+168h+var_88]
0x140015f6b  mov     byte ptr [rsp+168h+var_140], bl
0x140015f6f  mov     word ptr [rsp+168h+var_148], ax
0x140015f74  call    ?AddNeighborAP@CBSSListManager@@QEAAPEAVCBSSEntry@@PEAV2@QEAU_DOT11_SSID@@ITDOT11_TBTT_INFORMATION_HEADER@@TDOT11_BSS_PARAMETERS@@TDOT11_MLD_PARAMETERS@@PEAY05EW4_DOT11_BAND_ID@@E@Z; CBSSListManager::AddNeighborAP(CBSSEntry *,_DOT11_SSID * const,uint,DOT11_TBTT_INFORMATION_HEADER,DOT11_BSS_PARAMETERS,DOT11_MLD_PARAMETERS,uchar (*)[6],_DOT11_BAND_ID,uchar)
0x140015f79  mov     r12, rax
0x140015f7c  test    rax, rax
0x140015f7f  jz      loc_1400160AE
0x140015f85  lea     rax, WPP_RECORDER_INITIALIZED
0x140015f8c  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140015f93  jz      loc_14001606F
0x140015f99  mov     rcx, cs:WPP_GLOBAL_Control
0x140015fa0  cmp     byte ptr [rcx+29h], 5
0x140015fa4  jnb     short loc_140015FB1
0x140015fa6  cmp     word ptr [rcx+48h], 0
0x140015fab  jz      loc_14001606F
0x140015fb1  mov     r9, [rsp+168h+var_C0]
0x140015fb9  lea     rdx, aNone; "None"
0x140015fc0  cmp     [rsp+168h+var_90], 0
0x140015fc9  lea     r10d, [rbp+1]
0x140015fcd  mov     r11d, [rsp+168h+var_C4]
0x140015fd5  lea     rax, aSame; "Same"
0x140015fdc  mov     rcx, [rcx+40h]
0x140015fe0  cmovz   rax, rdx
0x140015fe4  movzx   r8d, word ptr [r9+rdi*4]
0x140015fe9  inc     r11d
0x140015fec  movzx   r9d, byte ptr [r9+rdi*4+3]
0x140015ff2  mov     rdi, [rsp+168h+var_A0]
0x140015ffa  mov     [rsp+168h+var_D0], rax
0x140016002  lea     rax, [rsp+168h+var_78]
0x14001600a  mov     [rsp+168h+var_D8], r14d
0x140016012  mov     [rsp+168h+var_E0], r15
0x14001601a  mov     [rsp+168h+var_E8], rax
0x140016022  mov     eax, [rdi+2B0h]
0x140016028  mov     [rsp+168h+var_F0], eax
0x14001602c  mov     eax, [rsp+0C0h]
0x140016033  movzx   edx, bl
0x140016036  lea     rbx, [rdi+20h]
0x14001603a  mov     [rsp+168h+var_F8], rbx
0x14001603f  mov     [rsp+168h+var_100], edx
0x140016043  mov     [rsp+168h+var_108], r8d
0x140016048  mov     dword ptr [rsp+168h+var_110], r9d
0x14001604d  mov     dword ptr [rsp+168h+var_118], eax
0x140016051  mov     [rsp+168h+var_120], r12
0x140016056  mov     [rsp+168h+var_128], rdi
0x14001605b  mov     dword ptr [rsp+168h+var_130], r13d
0x140016060  mov     dword ptr [rsp+168h+var_138], r10d
0x140016065  mov     dword ptr [rsp+168h+var_140], r11d
0x14001606a  call    WPP_RECORDER_SF_dddqqddDD_MAC_D_SSID__MAC_Ds
0x14001606f  inc     [rsp+168h+var_C4]
0x140016076  lea     rbx, WPP_3599b95ca20c3e0ba686e8b05788690d_Traceguids
0x14001607d  mov     r12, [rsp+168h+var_C0]
  ... truncated ...
```
