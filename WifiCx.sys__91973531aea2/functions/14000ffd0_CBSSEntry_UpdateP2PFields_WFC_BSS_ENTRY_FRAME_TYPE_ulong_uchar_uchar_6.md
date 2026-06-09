# CBSSEntry::UpdateP2PFields(_WFC_BSS_ENTRY_FRAME_TYPE,ulong,uchar *,uchar (*)[6])

- ea: `0x14000ffd0`
- end: `0x14001050d`
- name: `?UpdateP2PFields@CBSSEntry@@QEAAXW4_WFC_BSS_ENTRY_FRAME_TYPE@@KPEAEPEAY05E@Z`
- size: `1341`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `16`
- tags: `file_ops, authz_impersonation, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x140014bf0`
- `0x140014f20`

## callees

- `0x140009420`
- `0x14000c940`
- `0x14000d054`
- `0x14000f400`
- `0x14000ffd0`
- `0x140024a20`
- `0x140050574`
- `0x1400684cc`
- `0x14009a714`
- `0x1400db09c`
- `0x1400dc0ac`
- `0x1400dc238`
- `0x1400dc380`
- `0x1400dcce0`
- `0x1400dfd00`
- `0x1400e0100`

## pseudocode

```c
void __fastcall CBSSEntry::UpdateP2PFields(__int64 a1, int a2, unsigned int a3, unsigned __int8 *a4, __int64 a5)
{
  __int64 v9; // r8
  unsigned __int16 *v10; // rdi
  __int128 v11; // xmm6
  __int128 v12; // xmm7
  __int128 v13; // xmm0
  char *v14; // r13
  char v15; // al
  _UNKNOWN **v16; // rcx
  __int64 *v17; // rdx
  bool v18; // al
  int v19; // edx
  int v20; // r8d
  int v21; // r14d
  unsigned __int16 v22; // ax
  int v23; // r13d
  size_t v24; // rax
  char *v25; // rax
  int v26; // edx
  int v27; // r8d
  int v28; // ecx
  int v29; // edx
  int v30; // r8d
  unsigned __int16 v31; // ax
  char *v32; // rcx
  int v33; // r9d
  int v34; // edx
  unsigned __int16 v35; // di
  int v36; // eax
  __int64 v37; // r8
  int v38; // [rsp+28h] [rbp-E0h]
  char v39; // [rsp+40h] [rbp-C8h]
  int v40; // [rsp+58h] [rbp-B0h] BYREF
  int v41; // [rsp+5Ch] [rbp-ACh] BYREF
  int v42; // [rsp+60h] [rbp-A8h] BYREF
  int v43; // [rsp+64h] [rbp-A4h]
  char *v44; // [rsp+68h] [rbp-A0h]
  size_t Size; // [rsp+70h] [rbp-98h]
  size_t Size_8[2]; // [rsp+78h] [rbp-90h] BYREF
  _OWORD v47[2]; // [rsp+88h] [rbp-80h] BYREF
  _DWORD v48[132]; // [rsp+A8h] [rbp-60h] BYREF

  memset(v47, 0, 28);
  *(_OWORD *)Size_8 = 0;
  memset(v48, 0, 0x208u);
  v10 = 0;
  LOWORD(v40) = 0;
  LOWORD(v41) = 0;
  if ( !a4 || !a3 || !a5 )
    goto LABEL_2;
  LODWORD(Size_8[0]) = *(_DWORD *)a5;
  v14 = 0;
  WORD2(Size_8[0]) = *(_WORD *)(a5 + 4);
  v15 = WfdParseWpsIe(a4, a3, v9, v48);
  v16 = &WPP_RECORDER_INITIALIZED;
  v17 = WPP_3599b95ca20c3e0ba686e8b05788690d_Traceguids;
  if ( v15 && (v48[0] & 0x40000) != 0 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v17) = 4;
      WPP_RECORDER_SF_(
        WPP_GLOBAL_Control->DeviceExtension,
        (_DWORD)v17,
        1,
        61,
        (__int64)WPP_3599b95ca20c3e0ba686e8b05788690d_Traceguids);
    }
    v18 = v48[6] != 0;
  }
  else
  {
    v18 = 0;
  }
  if ( a2 == 1 )
    *(_BYTE *)(a1 + 869) = v18;
  else
    *(_BYTE *)(a1 + 870) = v18;
  v21 = WFDGetAdvertisedServiceInfoSizeAndCount((_DWORD)v16, (_DWORD)a4, a3, (unsigned int)&v40, (__int64)&v41);
  if ( v21 >= 0 )
  {
    v22 = v41;
    if ( (_WORD)v41 )
    {
      v23 = (unsigned __int16)v40;
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v19) = 4;
        WPP_RECORDER_SF_Ld(
          WPP_GLOBAL_Control->DeviceExtension,
          v19,
          v20,
          62,
          (__int64)WPP_3599b95ca20c3e0ba686e8b05788690d_Traceguids,
          v41,
          v40);
        v22 = v41;
      }
      v42 = v22;
      LODWORD(v44) = v23;
      v24 = v23 + 8 + 524 * (unsigned int)v22;
      v43 = v24;
      Size = v24;
      v25 = (char *)operator new((unsigned int)v24);
      v14 = v25;
      if ( v25 )
      {
        memset(v25, 0, Size);
        *((_WORD *)v14 + 2) = 8;
        v44 = v14 + 8;
        v21 = WFDGetAdvertisedServiceInfo(v28, (int)a4, a3, (int)&v40, (unsigned __int8 *)v14 + 8);
        if ( v21 < 0 )
        {
          if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            LOBYTE(v29) = 4;
            WPP_RECORDER_SF_dDd(
              WPP_GLOBAL_Control->DeviceExtension,
              v29,
              v30,
              65,
              (__int64)WPP_3599b95ca20c3e0ba686e8b05788690d_Traceguids,
              v21,
              v40,
              v42);
          }
          operator delete(v14);
          v14 = 0;
        }
        else
        {
          v31 = v40;
          v32 = v14 + 8;
          v33 = 0;
          v42 = 0;
          while ( 1 )
          {
            LOWORD(v43) = v31;
            if ( (unsigned __int16)v33 >= (unsigned __int16)v41 || v31 <= 7u )
              break;
            v34 = (unsigned __int8)v32[6];
            v35 = v34 + 7;
            if ( (unsigned __int16)(v34 + 7) > v31 )
            {
              if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
              {
                v39 = v34 + 7;
                LOBYTE(v34) = 4;
                WPP_RECORDER_SF_dddd(
                  WPP_GLOBAL_Control->DeviceExtension,
                  v34,
                  (unsigned __int16)v33,
                  63,
                  (__int64)WPP_3599b95ca20c3e0ba686e8b05788690d_Traceguids,
                  v33,
                  v32[6],
                  v39,
                  v31);
                LOWORD(v33) = v42;
              }
              break;
            }
            LOWORD(v33) = v33 + 1;
            v42 = v33;
            if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
              && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
            {
              WPP_RECORDER_SF_dDDds(
                WPP_GLOBAL_Control->DeviceExtension,
                v34,
                *((unsigned __int16 *)v32 + 2),
                (unsigned __int16)v33,
                v38,
                v33,
                *(_DWORD *)v32,
                *((_WORD *)v32 + 2),
                v34,
                (__int64)(v32 + 7));
              v33 = v42;
              v32 = v44;
            }
            v32 += v35;
            v31 = v43 - v35;
            v44 = v32;
          }
          *((_WORD *)v14 + 3) = v40;
          *(_WORD *)v14 = v33;
          if ( a2 )
          {
            v10 = *(unsigned __int16 **)(a1 + 920);
            *(_QWORD *)(a1 + 920) = v14;
          }
          else
          {
            v10 = *(unsigned __int16 **)(a1 + 912);
            *(_QWORD *)(a1 + 912) = v14;
          }
        }
      }
      else if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v26) = 4;
        WPP_RECORDER_SF_dddd(
          WPP_GLOBAL_Control->DeviceExtension,
          v26,
          v27,
          66,
          (__int64)WPP_3599b95ca20c3e0ba686e8b05788690d_Traceguids,
          v42,
          12,
          (char)v44,
          v43);
      }
    }
  }
  if ( !*(_BYTE *)(a1 + 908) )
  {
    v36 = 1;
    v42 = 1;
    if ( v14 != (char *)v10 )
    {
      if ( v14 && v10 )
      {
        v21 = WFDCompareAdvertisedServiceInfo(
                *((unsigned __int16 *)v14 + 3),
                (unsigned int)v14 + *((unsigned __int16 *)v14 + 2),
                v10[3],
                (unsigned int)v10 + v10[2],
                (__int64)&v42);
        v36 = v42;
      }
      else
      {
        v36 = 0;
      }
    }
    if ( !v21 && !v36 )
      *(_BYTE *)(a1 + 908) = 1;
  }
  if ( !(unsigned int)Dot11CopySSIDFromIEBlob(a4, a3, (struct _DOT11_SSID *)&Size_8[1])
    && (int)WFDGetCapability(a4, a3, v37, a1 + 868) >= 0 )
  {
    v11 = *(_OWORD *)((char *)v47 + 12);
    v12 = *(_OWORD *)Size_8;
  }
  else
  {
LABEL_2:
    v11 = 0;
    v12 = 0;
    memset(v47, 0, 28);
  }
  if ( v10 )
    operator delete(v10);
  v13 = v47[0];
  *(_OWORD *)(a1 + 824) = v12;
  *(_OWORD *)(a1 + 840) = v13;
  *(_OWORD *)(a1 + 852) = v11;
}

```

## disassembly

```asm
0x14000ffd0  mov     r11, rsp
0x14000ffd3  push    rbp
0x14000ffd4  push    rbx
0x14000ffd5  push    rdi
0x14000ffd6  lea     rbp, [r11-218h]
0x14000ffdd  sub     rsp, 300h
0x14000ffe4  movaps  xmmword ptr [r11-48h], xmm6
0x14000ffe9  movaps  xmmword ptr [r11-58h], xmm7
0x14000ffee  mov     rax, cs:__security_cookie
0x14000fff5  xor     rax, rsp
0x14000fff8  mov     [rbp+210h+var_60], rax
0x14000ffff  mov     [r11+10h], rsi
0x140010003  xorps   xmm0, xmm0
0x140010006  mov     [r11-20h], r12
0x14001000a  mov     rbx, rcx
0x14001000d  mov     [r11-30h], r14
0x140010011  lea     rcx, [rbp+210h+var_270]; void *
0x140010015  mov     r14, [rbp+210h+arg_20]
0x14001001c  mov     r12d, edx
0x14001001f  mov     [r11-38h], r15
0x140010023  xor     edx, edx; Val
0x140010025  mov     r15d, r8d
0x140010028  mov     rsi, r9
0x14001002b  movups  xmmword ptr [rbp+210h+var_298.ucSSID+4], xmm0
0x14001002f  mov     r8d, 208h; Size
0x140010035  movups  xmmword ptr [rsp+310h+Size+8], xmm0
0x14001003a  movups  xmmword ptr [rbp+210h+var_298.ucSSID+10h], xmm0
0x14001003e  call    memset
0x140010043  xor     eax, eax
0x140010045  xor     edi, edi
0x140010047  mov     word ptr [rsp+310h+var_2C0], ax
0x14001004c  mov     word ptr [rsp+310h+var_2BC], ax
0x140010051  test    rsi, rsi
0x140010054  jnz     short loc_1400100D1
0x140010056  xorps   xmm6, xmm6
0x140010059  xorps   xmm7, xmm7
0x14001005c  movups  xmmword ptr [rbp+210h+var_298.ucSSID+4], xmm6
0x140010060  movups  xmmword ptr [rbp+210h+var_298.ucSSID+10h], xmm6
0x140010064  mov     r15, [rsp+310h+var_30]
0x14001006c  mov     r14, [rsp+310h+var_28]
0x140010074  mov     r12, [rsp+2F8h]
0x14001007c  mov     rsi, [rsp+310h+arg_8]
0x140010084  test    rdi, rdi
0x140010087  jnz     loc_140010500
0x14001008d  movups  xmm0, xmmword ptr [rbp+210h+var_298.ucSSID+4]
0x140010091  movups  xmmword ptr [rbx+338h], xmm7
0x140010098  movups  xmmword ptr [rbx+348h], xmm0
0x14001009f  movups  xmmword ptr [rbx+354h], xmm6
0x1400100a6  mov     rcx, [rbp+210h+var_60]
0x1400100ad  xor     rcx, rsp; StackCookie
0x1400100b0  call    __security_check_cookie
0x1400100b5  movaps  xmm6, [rsp+310h+var_48+8]
0x1400100bd  movaps  xmm7, [rsp+310h+var_58+8]
0x1400100c5  add     rsp, 300h
0x1400100cc  pop     rdi
0x1400100cd  pop     rbx
0x1400100ce  pop     rbp
0x1400100cf  retn
0x1400100d1  test    r15d, r15d
0x1400100d4  jz      short loc_140010056
0x1400100d6  test    r14, r14
0x1400100d9  jz      loc_140010056
0x1400100df  mov     eax, [r14]
0x1400100e2  lea     r9, [rbp+210h+var_270]
0x1400100e6  mov     dword ptr [rsp+310h+Size+8], eax
0x1400100ea  mov     edx, r15d
0x1400100ed  movzx   eax, word ptr [r14+4]
0x1400100f2  mov     rcx, rsi
0x1400100f5  mov     [rsp+310h+var_20], r13
0x1400100fd  xor     r13d, r13d
0x140010100  mov     word ptr [rsp+310h+Size+0Ch], ax
0x140010105  call    WfdParseWpsIe
0x14001010a  lea     rcx, WPP_RECORDER_INITIALIZED
0x140010111  lea     rdx, WPP_3599b95ca20c3e0ba686e8b05788690d_Traceguids
0x140010118  test    al, al
0x14001011a  jz      short loc_140010159
0x14001011c  test    [rbp+210h+var_270], 40000h
0x140010123  jz      short loc_140010159
0x140010125  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x14001012c  jz      short loc_140010151
0x14001012e  mov     rcx, cs:WPP_GLOBAL_Control
0x140010135  mov     r9d, 3Dh ; '='
0x14001013b  mov     [rsp+310h+var_2F0], rdx
0x140010140  mov     r8d, 1
0x140010146  mov     dl, 4
0x140010148  mov     rcx, [rcx+40h]
0x14001014c  call    WPP_RECORDER_SF_
0x140010151  cmp     [rbp+210h+var_258], edi
0x140010154  setnz   al
0x140010157  jmp     short loc_14001015B
0x140010159  xor     al, al
0x14001015b  cmp     r12d, 1
0x14001015f  jnz     short loc_140010169
0x140010161  mov     [rbx+365h], al
0x140010167  jmp     short loc_14001016F
0x140010169  mov     [rbx+366h], al
0x14001016f  lea     rax, [rsp+310h+var_2BC]
0x140010174  mov     r8d, r15d
0x140010177  lea     r9, [rsp+310h+var_2C0]
0x14001017c  mov     [rsp+310h+var_2F0], rax
0x140010181  mov     rdx, rsi
0x140010184  call    WFDGetAdvertisedServiceInfoSizeAndCount
0x140010189  mov     r14d, eax
0x14001018c  test    eax, eax
0x14001018e  js      loc_140010453
0x140010194  movzx   eax, word ptr [rsp+310h+var_2BC]
0x140010199  test    ax, ax
0x14001019c  jz      loc_140010453
0x1400101a2  movzx   r13d, word ptr [rsp+310h+var_2C0]
0x1400101a8  lea     rcx, WPP_RECORDER_INITIALIZED
0x1400101af  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x1400101b6  jz      short loc_1400101EA
0x1400101b8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400101bf  mov     r9d, 3Eh ; '>'
0x1400101c5  mov     [rsp+310h+var_2E0], r13d
0x1400101ca  mov     dl, 4
0x1400101cc  mov     [rsp+310h+var_2E8], eax
0x1400101d0  lea     rax, WPP_3599b95ca20c3e0ba686e8b05788690d_Traceguids
0x1400101d7  mov     [rsp+310h+var_2F0], rax
0x1400101dc  mov     rcx, [rcx+40h]
0x1400101e0  call    WPP_RECORDER_SF_Ld
0x1400101e5  movzx   eax, word ptr [rsp+310h+var_2BC]
0x1400101ea  movzx   eax, ax
0x1400101ed  mov     ecx, r13d
0x1400101f0  mov     dword ptr [rsp+310h+var_2B8], eax
0x1400101f4  imul    eax, 20Ch
0x1400101fa  mov     dword ptr [rsp+310h+var_2B0], ecx
0x1400101fe  add     ecx, 8
0x140010201  add     eax, ecx
0x140010203  mov     ecx, eax; unsigned __int64
0x140010205  mov     dword ptr [rsp+310h+var_2B8+4], eax
0x140010209  mov     [rsp+310h+Size], rax
0x14001020e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140010213  mov     r13, rax
0x140010216  test    rax, rax
0x140010219  jz      loc_1400103FF
0x14001021f  mov     r8, [rsp+310h+Size]; Size
0x140010224  xor     edx, edx; Val
0x140010226  mov     rcx, rax; void *
0x140010229  call    memset
0x14001022e  lea     rax, [r13+8]
0x140010232  mov     word ptr [r13+4], 8
0x140010239  lea     r9, [rsp+310h+var_2C0]; int
0x14001023e  mov     [rsp+310h+var_2B0], rax
0x140010243  mov     r8d, r15d; int
0x140010246  mov     [rsp+310h+var_2F0], rax; unsigned __int8 *
0x14001024b  mov     rdx, rsi; int
0x14001024e  call    WFDGetAdvertisedServiceInfo
0x140010253  mov     r14d, eax
0x140010256  test    eax, eax
0x140010258  js      loc_1400103A8
0x14001025e  movzx   eax, word ptr [rsp+310h+var_2C0]
0x140010263  lea     rcx, [r13+8]
0x140010267  xor     r9d, r9d
0x14001026a  lea     r8, WPP_RECORDER_INITIALIZED
0x140010271  mov     dword ptr [rsp+310h+var_2B8], r9d
0x140010276  mov     word ptr [rsp+310h+var_2B8+4], ax
0x14001027b  cmp     r9w, word ptr [rsp+310h+var_2BC]
0x140010281  jnb     loc_14001036E
0x140010287  cmp     ax, 7
0x14001028b  jbe     loc_14001036E
0x140010291  movzx   edx, byte ptr [rcx+6]
0x140010295  lea     edi, [rdx+7]
0x140010298  cmp     di, ax
0x14001029b  ja      loc_140010321
0x1400102a1  inc     r9w
0x1400102a5  mov     dword ptr [rsp+310h+var_2B8], r9d
0x1400102aa  cmp     cs:WPP_RECORDER_INITIALIZED, r8
0x1400102b1  jz      short loc_140010309
0x1400102b3  mov     r10, cs:WPP_GLOBAL_Control
0x1400102ba  cmp     byte ptr [r10+29h], 5
0x1400102bf  jnb     short loc_1400102C9
0x1400102c1  cmp     word ptr [r10+48h], 0
0x1400102c7  jz      short loc_140010309
0x1400102c9  movzx   r8d, word ptr [rcx+4]
0x1400102ce  lea     rax, [rcx+7]
0x1400102d2  mov     qword ptr [rsp+310h+var_2C8], rax
0x1400102d7  mov     eax, [rcx]
0x1400102d9  mov     rcx, [r10+40h]
0x1400102dd  mov     dword ptr [rsp+310h+var_2D0], edx
0x1400102e1  mov     dword ptr [rsp+310h+var_2D8], r8d
0x1400102e6  movzx   r9d, r9w
0x1400102ea  mov     [rsp+310h+var_2E0], eax
0x1400102ee  mov     [rsp+310h+var_2E8], r9d
0x1400102f3  call    WPP_RECORDER_SF_dDDds
0x1400102f8  mov     r9d, dword ptr [rsp+310h+var_2B8]
0x1400102fd  lea     r8, WPP_RECORDER_INITIALIZED
0x140010304  mov     rcx, [rsp+310h+var_2B0]
0x140010309  movzx   eax, di
0x14001030c  add     rcx, rax
0x14001030f  movzx   eax, word ptr [rsp+310h+var_2B8+4]
0x140010314  sub     ax, di
0x140010317  mov     [rsp+310h+var_2B0], rcx
0x14001031c  jmp     loc_140010276
0x140010321  cmp     cs:WPP_RECORDER_INITIALIZED, r8
0x140010328  jz      short loc_14001036E
0x14001032a  movzx   eax, ax
0x14001032d  mov     dword ptr [rsp+310h+var_2D0], eax
0x140010331  lea     rax, WPP_3599b95ca20c3e0ba686e8b05788690d_Traceguids
0x140010338  movzx   r8d, r9w
0x14001033c  mov     r9d, 3Fh ; '?'
0x140010342  movzx   ecx, di
0x140010345  mov     dword ptr [rsp+310h+var_2D8], ecx
0x140010349  mov     rcx, cs:WPP_GLOBAL_Control
0x140010350  mov     [rsp+310h+var_2E0], edx
0x140010354  mov     dl, 4
0x140010356  mov     [rsp+310h+var_2E8], r8d
0x14001035b  mov     [rsp+310h+var_2F0], rax
0x140010360  mov     rcx, [rcx+40h]
0x140010364  call    WPP_RECORDER_SF_dddd
0x140010369  mov     r9d, dword ptr [rsp+310h+var_2B8]
0x14001036e  movzx   eax, word ptr [rsp+310h+var_2C0]
0x140010373  mov     [r13+6], ax
0x140010378  mov     [r13+0], r9w
0x14001037d  test    r12d, r12d
0x140010380  jnz     short loc_140010395
0x140010382  mov     rdi, [rbx+390h]
0x140010389  mov     [rbx+390h], r13
0x140010390  jmp     loc_140010453
0x140010395  mov     rdi, [rbx+398h]
0x14001039c  mov     [rbx+398h], r13
0x1400103a3  jmp     loc_140010453
0x1400103a8  lea     rax, WPP_RECORDER_INITIALIZED
0x1400103af  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400103b6  jz      short loc_1400103F2
0x1400103b8  mov     ecx, dword ptr [rsp+310h+var_2B8]
0x1400103bc  mov     r9d, 41h ; 'A'
0x1400103c2  movzx   eax, word ptr [rsp+310h+var_2C0]
0x1400103c7  mov     dl, 4
0x1400103c9  mov     dword ptr [rsp+310h+var_2D8], ecx
0x1400103cd  mov     rcx, cs:WPP_GLOBAL_Control
0x1400103d4  mov     [rsp+310h+var_2E0], eax
0x1400103d8  lea     rax, WPP_3599b95ca20c3e0ba686e8b05788690d_Traceguids
0x1400103df  mov     [rsp+310h+var_2E8], r14d
0x1400103e4  mov     [rsp+310h+var_2F0], rax
0x1400103e9  mov     rcx, [rcx+40h]
0x1400103ed  call    WPP_RECORDER_SF_dDd
0x1400103f2  mov     rcx, r13; void *
0x1400103f5  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1400103fa  xor     r13d, r13d
0x1400103fd  jmp     short loc_140010453
0x1400103ff  lea     rax, WPP_RECORDER_INITIALIZED
0x140010406  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14001040d  jz      short loc_140010453
0x14001040f  mov     eax, dword ptr [rsp+310h+var_2B8+4]
0x140010413  mov     r9d, 42h ; 'B'
0x140010419  mov     ecx, dword ptr [rsp+310h+var_2B8]
0x14001041d  mov     dl, 4
0x14001041f  mov     dword ptr [rsp+310h+var_2D0], eax
0x140010423  mov     eax, dword ptr [rsp+310h+var_2B0]
0x140010427  mov     dword ptr [rsp+310h+var_2D8], eax
0x14001042b  lea     rax, WPP_3599b95ca20c3e0ba686e8b05788690d_Traceguids
0x140010432  mov     [rsp+310h+var_2E0], 20Ch
0x14001043a  mov     [rsp+310h+var_2E8], ecx
0x14001043e  mov     rcx, cs:WPP_GLOBAL_Control
0x140010445  mov     [rsp+310h+var_2F0], rax
0x14001044a  mov     rcx, [rcx+40h]
0x14001044e  call    WPP_RECORDER_SF_dddd
0x140010453  cmp     byte ptr [rbx+38Ch], 0
0x14001045a  jnz     short loc_1400104B8
0x14001045c  mov     eax, 1
0x140010461  mov     dword ptr [rsp+310h+var_2B8], eax
0x140010465  cmp     r13, rdi
0x140010468  jz      short loc_1400104A8
0x14001046a  test    r13, r13
0x14001046d  jz      short loc_1400104A6
0x14001046f  test    rdi, rdi
0x140010472  jz      short loc_1400104A6
0x140010474  movzx   r9d, word ptr [rdi+4]
0x140010479  lea     rax, [rsp+310h+var_2B8]
0x14001047e  movzx   edx, word ptr [r13+4]
0x140010483  add     r9, rdi
0x140010486  movzx   r8d, word ptr [rdi+6]
0x14001048b  add     rdx, r13
0x14001048e  movzx   ecx, word ptr [r13+6]
0x140010493  mov     [rsp+310h+var_2F0], rax
0x140010498  call    WFDCompareAdvertisedServiceInfo
0x14001049d  mov     r14d, eax
0x1400104a0  mov     eax, dword ptr [rsp+310h+var_2B8]
0x1400104a4  jmp     short loc_1400104A8
0x1400104a6  xor     eax, eax
0x1400104a8  test    r14d, r14d
0x1400104ab  jnz     short loc_1400104B8
0x1400104ad  test    eax, eax
0x1400104af  jnz     short loc_1400104B8
0x1400104b1  mov     byte ptr [rbx+38Ch], 1
0x1400104b8  lea     r8, [rsp+310h+var_298]; struct _DOT11_SSID *
0x1400104bd  mov     edx, r15d; unsigned int
0x1400104c0  mov     rcx, rsi; unsigned __int8 *
0x1400104c3  call    ?Dot11CopySSIDFromIEBlob@@YAHPEAEKPEAU_DOT11_SSID@@@Z; Dot11CopySSIDFromIEBlob(uchar *,ulong,_DOT11_SSID *)
0x1400104c8  mov     r13, [rsp+310h+var_20]
0x1400104d0  test    eax, eax
0x1400104d2  jnz     loc_140010056
0x1400104d8  lea     r9, [rbx+364h]
0x1400104df  mov     edx, r15d
0x1400104e2  mov     rcx, rsi
0x1400104e5  call    WFDGetCapability
0x1400104ea  test    eax, eax
0x1400104ec  js      loc_140010056
0x1400104f2  movups  xmm6, xmmword ptr [rbp+210h+var_298.ucSSID+10h]
  ... truncated ...
```
