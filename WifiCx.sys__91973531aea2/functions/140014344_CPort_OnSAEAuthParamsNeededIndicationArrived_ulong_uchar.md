# CPort::OnSAEAuthParamsNeededIndicationArrived(ulong,uchar *)

- ea: `0x140014344`
- end: `0x140014b2a`
- name: `?OnSAEAuthParamsNeededIndicationArrived@CPort@@QEAAXKPEAE@Z`
- size: `2022`
- prototype: `void __fastcall(CPort *this, int, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `25`
- tags: `file_ops, loader_planting`

## callers

- `0x140026010`

## callees

- `0x140009420`
- `0x14000c940`
- `0x140014344`
- `0x140014b30`
- `0x1400151e0`
- `0x140018270`
- `0x140019d44`
- `0x14001e2c0`
- `0x14001eed0`
- `0x14002aaec`
- `0x14002c0b4`
- `0x14003895c`
- `0x1400417ac`
- `0x140050dc8`
- `0x1400747c4`
- `0x140083c68`
- `0x140083cec`
- `0x14008e600`
- `0x14008e854`
- `0x14008f458`
- `0x14008f714`
- `0x1400dfd00`
- `0x1400dfd40`
- `0x1400dfe00`
- `0x1400e0100`

## string_xrefs

- `0x140014952`: `Replacing Bss Link address with Mld`
- `0x1400149df`: `Replacing Bss Link address with Mld`

## pseudocode

```c
void __fastcall CPort::OnSAEAuthParamsNeededIndicationArrived(CPort *this, int a2, unsigned __int8 *a3)
{
  unsigned __int8 *v5; // rdx
  __int64 v6; // r8
  int v7; // eax
  int v8; // edx
  int v9; // r8d
  unsigned int v10; // r12d
  unsigned int PropertyULongOrDefault; // eax
  int v12; // r8d
  unsigned int v13; // r15d
  int v14; // edx
  int v15; // edx
  int v16; // r9d
  int v17; // r9d
  _DWORD *v18; // rax
  int v19; // edx
  int v20; // r8d
  _DWORD *v21; // rbx
  __int64 v22; // rax
  int PropertyList; // eax
  int v24; // edx
  int v25; // r8d
  unsigned __int8 *v26; // rax
  _DWORD *v27; // r14
  __int64 v28; // rax
  CBSSEntry *v29; // r15
  enum _DOT11_CIPHER_ALGORITHM *v30; // r8
  int v31; // edx
  const char *v32; // r8
  const char *v33; // r9
  const char *v34; // r8
  const char *v35; // r9
  size_t v36; // rax
  void *v37; // rdx
  enum _DOT11_CIPHER_ALGORITHM *v38; // [rsp+20h] [rbp-B9h]
  enum _DOT11_CIPHER_ALGORITHM *v39; // [rsp+30h] [rbp-A9h]
  __int16 v40; // [rsp+30h] [rbp-A9h]
  __int64 v41; // [rsp+38h] [rbp-A1h]
  char v42; // [rsp+40h] [rbp-99h]
  unsigned int v43; // [rsp+80h] [rbp-59h] BYREF
  unsigned __int8 *v44[2]; // [rsp+88h] [rbp-51h] BYREF
  unsigned int v45; // [rsp+A0h] [rbp-39h] BYREF
  int v46; // [rsp+A4h] [rbp-35h] BYREF
  __int16 v47; // [rsp+A8h] [rbp-31h]
  __int64 v48; // [rsp+ACh] [rbp-2Dh] BYREF
  void *Src; // [rsp+B8h] [rbp-21h]
  char v50; // [rsp+C0h] [rbp-19h]
  size_t Size; // [rsp+C8h] [rbp-11h] BYREF
  void *v52; // [rsp+D0h] [rbp-9h]
  char v53; // [rsp+D8h] [rbp-1h]
  __int64 v54; // [rsp+E0h] [rbp+7h]
  __int16 v55; // [rsp+E8h] [rbp+Fh]

  v45 &= 0xFFFFFFF0;
  v48 = 0;
  Src = 0;
  v50 = 0;
  v46 = 0;
  v47 = 0;
  v5 = a3 + 48;
  v6 = *((_QWORD *)this + 17);
  v55 = 0;
  LODWORD(Size) = 0;
  v52 = 0;
  v53 = 0;
  v54 = 0;
  v7 = ParseWdiIndicationSaeAuthParamsNeededFromIhv((unsigned int)(a2 - 48), v5, v6 + 5384, &v45);
  if ( !v7 )
  {
    v43 = 0;
    v10 = 612;
    PropertyULongOrDefault = CPropertyCache::GetPropertyULongOrDefault((CPort *)((char *)this + 480), 0x86u, 0);
    v12 = v48;
    v13 = PropertyULongOrDefault;
    v14 = v48;
    switch ( (_DWORD)v48 )
    {
      case 0:
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(v14) = 4;
          WPP_RECORDER_SF_qD_MAC_(
            WPP_GLOBAL_Control->DeviceExtension,
            v14,
            0,
            102,
            (__int64)WPP_ec9f566a4d91355929b7c1dd2a1777a1_Traceguids,
            (char)this,
            *((_WORD *)this + 74),
            (__int64)&v46);
        }
        CPropertyCache::SetPropertyULong((CPort *)((char *)this + 480), 0x86u, ++v13);
        goto LABEL_38;
      case 1:
        v15 = v45 & 1;
        if ( (v45 & 1) == 0 || !HIDWORD(v48) )
        {
          if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            goto LABEL_74;
          v17 = 104;
          goto LABEL_21;
        }
        v10 = HIDWORD(v48) + 612;
        if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          goto LABEL_38;
        v16 = 103;
        v42 = BYTE4(v48);
        break;
      case 2:
        v15 = Size;
        if ( ((v45 >> 1) & 1) == 0 || !(_DWORD)Size )
        {
          if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            goto LABEL_74;
          v17 = 106;
          goto LABEL_21;
        }
        v10 = Size + 612;
        if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          goto LABEL_38;
        v16 = 105;
        v42 = Size;
        break;
      default:
        v15 = v48 - 3;
        if ( (_DWORD)v48 != 3 )
        {
          if ( (_DWORD)v48 != 4 )
          {
            if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            {
              LOBYTE(v15) = 2;
              WPP_RECORDER_SF_qD_MAC_d(
                WPP_GLOBAL_Control->DeviceExtension,
                v15,
                v48,
                110,
                (__int64)WPP_ec9f566a4d91355929b7c1dd2a1777a1_Traceguids,
                (char)this,
                *((_WORD *)this + 74),
                (__int64)&v46,
                v48);
            }
            goto LABEL_74;
          }
          v43 = 50;
          if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            LOBYTE(v15) = 4;
            WPP_RECORDER_SF_qD_MAC_(
              WPP_GLOBAL_Control->DeviceExtension,
              v15,
              v48,
              107,
              (__int64)WPP_ec9f566a4d91355929b7c1dd2a1777a1_Traceguids,
              (char)this,
              *((_WORD *)this + 74),
              (__int64)&v46);
          }
LABEL_38:
          v18 = operator new(v10);
          v21 = v18;
          if ( !v18 )
          {
            if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            {
              LOBYTE(v19) = 2;
              WPP_RECORDER_SF_qD(
                WPP_GLOBAL_Control->DeviceExtension,
                v19,
                v20,
                111,
                (__int64)WPP_ec9f566a4d91355929b7c1dd2a1777a1_Traceguids,
                (char)this,
                *((_WORD *)this + 74));
            }
            goto LABEL_74;
          }
          memset(v18, 0, v10);
          *v21 = 40108416;
          v21[13] = v46;
          *((_WORD *)v21 + 28) = v47;
          *(_DWORD *)((char *)v21 + 58) = v46;
          *((_WORD *)v21 + 31) = v47;
          v21[16] = v43;
          v21[3] = v13;
          v22 = *((_QWORD *)this + 17);
          *(_OWORD *)v44 = 0;
          v43 = 0;
          v21[1] = *(_DWORD *)(v22 + 4648);
          PropertyList = CPropertyCache::GetPropertyList(
                           (CPort *)((char *)this + 480),
                           5u,
                           &v43,
                           (unsigned __int16 *)v44,
                           &v44[1]);
          if ( PropertyList )
          {
            if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            {
              LODWORD(v41) = PropertyList;
              LOBYTE(v24) = 2;
              WPP_RECORDER_SF_qDD(
                WPP_GLOBAL_Control->DeviceExtension,
                v24,
                v25,
                112,
                (__int64)WPP_ec9f566a4d91355929b7c1dd2a1777a1_Traceguids,
                (char)this,
                *((_WORD *)this + 74),
                v41);
            }
            goto LABEL_42;
          }
          if ( v43 >= 0x24 )
          {
            v26 = v44[1];
            *((_OWORD *)v21 + 1) = *(_OWORD *)v44[1];
            *((_OWORD *)v21 + 2) = *((_OWORD *)v26 + 1);
            v21[12] = *((_DWORD *)v26 + 8);
          }
          if ( (unsigned int)Feature_Bugfix_56955488__private_IsEnabledDeviceUsageNoInline() )
          {
            *((_WORD *)v21 + 34) = 1;
            v21[18] = 145493760;
            v21[19] = 78384896;
            v21[20] = 9;
            v21[21] = 4;
          }
          else
          {
            v21[118] = 65537;
            v21[119] = 145493760;
            v21[134] = 4;
          }
          v27 = 0;
          if ( (*((_DWORD *)this + 38) & 0xC) == 0 )
          {
            v28 = (**(__int64 (__fastcall ***)(__int64, int *))(*((_QWORD *)this + 17) + 1336LL))(
                    *((_QWORD *)this + 17) + 1336LL,
                    &v46);
            v29 = (CBSSEntry *)v28;
            if ( v28 )
            {
              v21[2] = *(_DWORD *)(v28 + 888);
              if ( (v45 & 8) != 0 )
              {
                if ( *(_BYTE *)(v28 + 44) )
                {
                  v27 = (_DWORD *)(v28 + 38);
                  if ( v28 != -38 )
                  {
                    v21[13] = *v27;
                    *((_WORD *)v21 + 28) = *(_WORD *)(v28 + 42);
                  }
                }
              }
              if ( (unsigned int)Feature_Bugfix_56955488__private_IsEnabledDeviceUsageNoInline() )
              {
                *((_WORD *)v21 + 34) = 25;
                CBSSEntry::GetRsnAkmCipherPairs(
                  v29,
                  0,
                  v30,
                  (unsigned __int16 *)v21 + 34,
                  (struct DOT11_AUTH_AKM_CIPHER *)(v21 + 18));
              }
              else
              {
                CBSSEntry::GetRsnAkmsAndCiphers(
                  v29,
                  (unsigned __int16 *)v21 + 236,
                  (unsigned __int16 *)v21 + 237,
                  (enum RSNA_AKM_SUITE *)(v21 + 119),
                  (enum _DOT11_CIPHER_ALGORITHM *)v21 + 134,
                  0,
                  v39);
              }
            }
          }
          if ( (unsigned int)Feature_Bugfix_56955488__private_IsEnabledDeviceUsageNoInline() )
          {
            if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            {
              v32 = "Replacing Bss Link address with Mld";
              v33 = "MLO";
              if ( !v27 )
              {
                v32 = "Using Bss";
                v33 = "non-MLO";
              }
              WPP_RECORDER_SF_qDs_MAC_s_MAC_DDd(
                WPP_GLOBAL_Control->DeviceExtension,
                v31,
                (_DWORD)v32,
                (_DWORD)v33,
                (_DWORD)v38,
                (char)this,
                *((_WORD *)this + 74),
                (__int64)v33,
                (__int64)&v46,
                (__int64)v32,
                (__int64)(v21 + 13),
                v21[1],
                v21[2],
                *((_WORD *)v21 + 34));
            }
          }
          else if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            v34 = "Replacing Bss Link address with Mld";
            v35 = "MLO";
            if ( !v27 )
            {
              v34 = "Using Bss";
              v35 = "non-MLO";
            }
            WPP_RECORDER_SF_qDs_MAC_s_MAC_DDdd(
              WPP_GLOBAL_Control->DeviceExtension,
              *((unsigned __int16 *)v21 + 236),
              (_DWORD)v34,
              (_DWORD)v35,
              (__int64)v38,
              (char)this,
              *((_WORD *)this + 74),
              (__int64)v35,
              (__int64)&v46,
              (__int64)v34,
              (__int64)(v21 + 13),
              v21[1],
              v21[2],
              *((_WORD *)v21 + 236),
              *((_WORD *)v21 + 237));
          }
          if ( (_DWORD)v48 == 1 )
          {
            v21[149] = 612;
            v36 = HIDWORD(v48);
            v21[150] = HIDWORD(v48);
            v37 = Src;
          }
          else
          {
            if ( (_DWORD)v48 != 2 )
            {
LABEL_71:
              CAdapter::IndicateStatus(*((CAdapter **)this + 17), *((_DWORD *)this + 36), 1073938480, 0, v21, v10);
LABEL_42:
              operator delete(v21);
              goto LABEL_74;
            }
            v21[151] = 612;
            v36 = (unsigned int)Size;
            v21[152] = Size;
            v37 = v52;
          }
          memmove(v21 + 153, v37, v36);
          goto LABEL_71;
        }
        v12 = v54;
        if ( ((v45 >> 2) & 1) != 0 && (_DWORD)v54 )
        {
          v43 = CWabiToDot11Converter::MapSAEStatus((unsigned int)v54);
          if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            goto LABEL_38;
          v42 = v12;
          v16 = 108;
          v40 = *((_WORD *)this + 74);
          goto LABEL_18;
        }
        if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
LABEL_74:
          _WDI_INDICATION_SAE_AUTH_PARAMS_NEEDED_PARAMETERS::~_WDI_INDICATION_SAE_AUTH_PARAMS_NEEDED_PARAMETERS((_WDI_INDICATION_SAE_AUTH_PARAMS_NEEDED_PARAMETERS *)&v45);
          return;
        }
        v17 = 109;
LABEL_21:
        WPP_RECORDER_SF_qD_MAC_Dd(WPP_GLOBAL_Control->DeviceExtension, v15, v12, v17);
        goto LABEL_74;
    }
    v40 = *((_WORD *)this + 74);
LABEL_18:
    LOBYTE(v15) = 4;
    WPP_RECORDER_SF_qD_MAC_d(
      WPP_GLOBAL_Control->DeviceExtension,
      v15,
      v12,
      v16,
      (__int64)WPP_ec9f566a4d91355929b7c1dd2a1777a1_Traceguids,
      (char)this,
      v40,
      (__int64)&v46,
      v42);
    goto LABEL_38;
  }
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v8) = 2;
    WPP_RECORDER_SF_qDD(
      WPP_GLOBAL_Control->DeviceExtension,
      v8,
      v9,
      101,
      (__int64)WPP_ec9f566a4d91355929b7c1dd2a1777a1_Traceguids,
      (char)this,
      *((_WORD *)this + 74),
      v7);
  }
  ArrayOfElements<WiFiCxTLVStaging::_WDI_P2P_AP_INFO_LIST_ENTRY_CONTAINER>::Cleanup(&Size);
  ArrayOfElements<WiFiCxTLVStaging::_WDI_P2P_AP_INFO_LIST_ENTRY_CONTAINER>::Cleanup((char *)&v48 + 4);
}

```

## disassembly

```asm
0x140014344  mov     [rsp-8+arg_18], rbx
0x140014349  push    rbp
0x14001434a  push    rsi
0x14001434b  push    rdi
0x14001434c  push    r12
0x14001434e  push    r13
0x140014350  push    r14
0x140014352  push    r15
0x140014354  lea     rbp, [rsp-27h]
0x140014359  sub     rsp, 100h
0x140014360  mov     rax, cs:__security_cookie
0x140014367  xor     rax, rsp
0x14001436a  mov     [rbp+57h+var_40], rax
0x14001436e  and     [rbp+57h+var_90], 0FFFFFFF0h
0x140014372  xor     esi, esi
0x140014374  mov     r9, r8
0x140014377  mov     [rbp+57h+var_84], rsi
0x14001437b  mov     rdi, rcx
0x14001437e  mov     [rbp+57h+Src], rsi
0x140014382  xor     ecx, ecx
0x140014384  mov     [rbp+57h+var_70], sil
0x140014388  mov     eax, edx
0x14001438a  mov     [rbp+57h+var_8C], ecx
0x14001438d  mov     [rbp+57h+var_88], cx
0x140014391  lea     rdx, [r9+30h]
0x140014395  mov     r8, [rdi+88h]
0x14001439c  lea     r9, [rbp+57h+var_90]
0x1400143a0  mov     [rbp+57h+var_48], cx
0x1400143a4  add     r8, 1508h
0x1400143ab  lea     ecx, [rax-30h]
0x1400143ae  mov     dword ptr [rbp+57h+Size], esi
0x1400143b1  mov     [rbp+57h+var_60], rsi
0x1400143b5  mov     [rbp+57h+var_58], sil
0x1400143b9  mov     [rbp+57h+var_50], rsi
0x1400143bd  call    ParseWdiIndicationSaeAuthParamsNeededFromIhv
0x1400143c2  test    eax, eax
0x1400143c4  jz      short loc_140014425
0x1400143c6  lea     rsi, WPP_RECORDER_INITIALIZED
0x1400143cd  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x1400143d4  jz      short loc_14001440E
0x1400143d6  movzx   ecx, word ptr [rdi+94h]
0x1400143dd  lea     r14, WPP_ec9f566a4d91355929b7c1dd2a1777a1_Traceguids
0x1400143e4  mov     dword ptr [rsp+130h+var_F8], eax
0x1400143e8  mov     r9d, 65h ; 'e'
0x1400143ee  mov     dword ptr [rsp+130h+var_100], ecx
0x1400143f2  mov     dl, 2
0x1400143f4  mov     rcx, cs:WPP_GLOBAL_Control
0x1400143fb  mov     [rsp+130h+var_108], rdi
0x140014400  mov     [rsp+130h+var_110], r14
0x140014405  mov     rcx, [rcx+40h]
0x140014409  call    WPP_RECORDER_SF_qDD
0x14001440e  lea     rcx, [rbp+57h+Size]; void *
0x140014412  call    ?Cleanup@?$ArrayOfElements@U_WDI_P2P_AP_INFO_LIST_ENTRY_CONTAINER@WiFiCxTLVStaging@@@@QEAAXXZ; ArrayOfElements<WiFiCxTLVStaging::_WDI_P2P_AP_INFO_LIST_ENTRY_CONTAINER>::Cleanup(void)
0x140014417  lea     rcx, [rbp+57h+var_84+4]; void *
0x14001441b  call    ?Cleanup@?$ArrayOfElements@U_WDI_P2P_AP_INFO_LIST_ENTRY_CONTAINER@WiFiCxTLVStaging@@@@QEAAXXZ; ArrayOfElements<WiFiCxTLVStaging::_WDI_P2P_AP_INFO_LIST_ENTRY_CONTAINER>::Cleanup(void)
0x140014420  jmp     loc_140014B02
0x140014425  lea     rbx, [rdi+1E0h]
0x14001442c  mov     [rbp+57h+var_B0], esi
0x14001442f  mov     rcx, rbx; this
0x140014432  xor     r8d, r8d; unsigned int
0x140014435  mov     edx, 86h; unsigned int
0x14001443a  mov     r12d, 264h
0x140014440  call    ?GetPropertyULongOrDefault@CPropertyCache@@QEAAKKK@Z; CPropertyCache::GetPropertyULongOrDefault(ulong,ulong)
0x140014445  mov     r8d, dword ptr [rbp+57h+var_84]
0x140014449  lea     r14, WPP_ec9f566a4d91355929b7c1dd2a1777a1_Traceguids
0x140014450  mov     r15d, eax
0x140014453  mov     edx, r8d
0x140014456  mov     r13d, 1
0x14001445c  test    r8d, r8d
0x14001445f  jz      loc_1400146C7
0x140014465  sub     edx, r13d
0x140014468  jz      loc_14001466A
0x14001446e  sub     edx, r13d
0x140014471  jz      loc_1400145F8
0x140014477  sub     edx, r13d
0x14001447a  jz      loc_140014534
0x140014480  cmp     edx, r13d
0x140014483  jz      short loc_1400144DE
0x140014485  lea     rsi, WPP_RECORDER_INITIALIZED
0x14001448c  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x140014493  jz      loc_140014AF9
0x140014499  movzx   eax, word ptr [rdi+94h]
0x1400144a0  lea     rcx, [rbp+57h+var_8C]
0x1400144a4  mov     dword ptr [rsp+130h+var_F0], r8d
0x1400144a9  lea     r14, WPP_ec9f566a4d91355929b7c1dd2a1777a1_Traceguids
0x1400144b0  mov     [rsp+130h+var_F8], rcx
0x1400144b5  lea     r9d, [r13+6Dh]
0x1400144b9  mov     rcx, cs:WPP_GLOBAL_Control
0x1400144c0  mov     dl, 2
0x1400144c2  mov     dword ptr [rsp+130h+var_100], eax
0x1400144c6  mov     [rsp+130h+var_108], rdi
0x1400144cb  mov     [rsp+130h+var_110], r14
0x1400144d0  mov     rcx, [rcx+40h]
0x1400144d4  call    WPP_RECORDER_SF_qD_MAC_d
0x1400144d9  jmp     loc_140014AF9
0x1400144de  mov     [rbp+57h+var_B0], 32h ; '2'
0x1400144e5  lea     rsi, WPP_RECORDER_INITIALIZED
0x1400144ec  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x1400144f3  jz      loc_140014720
0x1400144f9  movzx   eax, word ptr [rdi+94h]
0x140014500  lea     rcx, [rbp+57h+var_8C]
0x140014504  mov     [rsp+130h+var_F8], rcx
0x140014509  mov     r9d, 6Bh ; 'k'
0x14001450f  mov     rcx, cs:WPP_GLOBAL_Control
0x140014516  mov     dl, 4
0x140014518  mov     dword ptr [rsp+130h+var_100], eax
0x14001451c  mov     [rsp+130h+var_108], rdi
0x140014521  mov     [rsp+130h+var_110], r14
0x140014526  mov     rcx, [rcx+40h]
0x14001452a  call    WPP_RECORDER_SF_qD_MAC_
0x14001452f  jmp     loc_140014720
0x140014534  mov     ecx, [rbp+57h+var_90]
0x140014537  mov     r8d, dword ptr [rbp+57h+var_50]
0x14001453b  shr     ecx, 2
0x14001453e  and     ecx, r13d
0x140014541  jz      short loc_1400145A7
0x140014543  test    r8d, r8d
0x140014546  jz      short loc_1400145A7
0x140014548  mov     ecx, r8d
0x14001454b  call    ?MapSAEStatus@CWabiToDot11Converter@@SA?AW4_DOT11_SAE_STATUS@@W4_WDI_SAE_STATUS@@@Z; CWabiToDot11Converter::MapSAEStatus(_WDI_SAE_STATUS)
0x140014550  mov     [rbp+57h+var_B0], eax
0x140014553  lea     rsi, WPP_RECORDER_INITIALIZED
0x14001455a  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x140014561  jz      loc_140014720
0x140014567  movzx   ecx, word ptr [rdi+94h]
0x14001456e  lea     rax, [rbp+57h+var_8C]
0x140014572  mov     dword ptr [rsp+130h+var_F0], r8d
0x140014577  mov     r9d, 6Ch ; 'l'
0x14001457d  mov     [rsp+130h+var_F8], rax
0x140014582  mov     dword ptr [rsp+130h+var_100], ecx
0x140014586  mov     rcx, cs:WPP_GLOBAL_Control
0x14001458d  mov     dl, 4
0x14001458f  mov     [rsp+130h+var_108], rdi
0x140014594  mov     [rsp+130h+var_110], r14
0x140014599  mov     rcx, [rcx+40h]
0x14001459d  call    WPP_RECORDER_SF_qD_MAC_d
0x1400145a2  jmp     loc_140014720
0x1400145a7  lea     rsi, WPP_RECORDER_INITIALIZED
0x1400145ae  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x1400145b5  jz      loc_140014AF9
0x1400145bb  mov     r9d, 6Dh ; 'm'
0x1400145c1  mov     dword ptr [rsp+130h+var_E8], r8d
0x1400145c6  mov     dword ptr [rsp+130h+var_F0], ecx
0x1400145ca  movzx   eax, word ptr [rdi+94h]
0x1400145d1  lea     rcx, [rbp+57h+var_8C]
0x1400145d5  mov     [rsp+130h+var_F8], rcx
0x1400145da  mov     rcx, cs:WPP_GLOBAL_Control
0x1400145e1  mov     dword ptr [rsp+130h+var_100], eax
0x1400145e5  mov     [rsp+130h+var_108], rdi
0x1400145ea  mov     rcx, [rcx+40h]
0x1400145ee  call    WPP_RECORDER_SF_qD_MAC_Dd
0x1400145f3  jmp     loc_140014AF9
0x1400145f8  mov     ecx, [rbp+57h+var_90]
0x1400145fb  mov     edx, dword ptr [rbp+57h+Size]
0x1400145fe  shr     ecx, 1
0x140014600  and     ecx, r13d
0x140014603  jz      short loc_140014647
0x140014605  test    edx, edx
0x140014607  jz      short loc_140014647
0x140014609  lea     r12d, [rdx+264h]
0x140014610  lea     rsi, WPP_RECORDER_INITIALIZED
0x140014617  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x14001461e  jz      loc_140014720
0x140014624  mov     r9d, 69h ; 'i'
0x14001462a  mov     dword ptr [rsp+130h+var_F0], edx
0x14001462e  movzx   eax, word ptr [rdi+94h]
0x140014635  lea     rcx, [rbp+57h+var_8C]
0x140014639  mov     [rsp+130h+var_F8], rcx
0x14001463e  mov     dword ptr [rsp+130h+var_100], eax
0x140014642  jmp     loc_140014586
0x140014647  lea     rsi, WPP_RECORDER_INITIALIZED
0x14001464e  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x140014655  jz      loc_140014AF9
0x14001465b  mov     r9d, 6Ah ; 'j'
0x140014661  mov     dword ptr [rsp+130h+var_E8], edx
0x140014665  jmp     loc_1400145C6
0x14001466a  mov     edx, [rbp+57h+var_90]
0x14001466d  mov     ecx, dword ptr [rbp+57h+var_84+4]
0x140014670  and     edx, r13d
0x140014673  jz      short loc_1400146A0
0x140014675  test    ecx, ecx
0x140014677  jz      short loc_1400146A0
0x140014679  lea     r12d, [rcx+264h]
0x140014680  lea     rsi, WPP_RECORDER_INITIALIZED
0x140014687  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x14001468e  jz      loc_140014720
0x140014694  mov     r9d, 67h ; 'g'
0x14001469a  mov     dword ptr [rsp+130h+var_F0], ecx
0x14001469e  jmp     short loc_14001462E
0x1400146a0  lea     rsi, WPP_RECORDER_INITIALIZED
0x1400146a7  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x1400146ae  jz      loc_140014AF9
0x1400146b4  mov     dword ptr [rsp+130h+var_E8], ecx
0x1400146b8  mov     r9d, 68h ; 'h'
0x1400146be  mov     dword ptr [rsp+130h+var_F0], edx
0x1400146c2  jmp     loc_1400145CA
0x1400146c7  lea     rsi, WPP_RECORDER_INITIALIZED
0x1400146ce  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x1400146d5  jz      short loc_14001470D
0x1400146d7  movzx   eax, word ptr [rdi+94h]
0x1400146de  lea     rcx, [rbp+57h+var_8C]
0x1400146e2  mov     [rsp+130h+var_F8], rcx
0x1400146e7  mov     r9d, 66h ; 'f'
0x1400146ed  mov     rcx, cs:WPP_GLOBAL_Control
0x1400146f4  mov     dl, 4
0x1400146f6  mov     dword ptr [rsp+130h+var_100], eax; enum _DOT11_CIPHER_ALGORITHM *
0x1400146fa  mov     [rsp+130h+var_108], rdi
0x1400146ff  mov     [rsp+130h+var_110], r14
0x140014704  mov     rcx, [rcx+40h]
0x140014708  call    WPP_RECORDER_SF_qD_MAC_
0x14001470d  add     r15d, r13d
0x140014710  mov     edx, 86h; unsigned int
0x140014715  mov     r8d, r15d; unsigned int
0x140014718  mov     rcx, rbx; this
0x14001471b  call    ?SetPropertyULong@CPropertyCache@@QEAAHKK@Z; CPropertyCache::SetPropertyULong(ulong,ulong)
0x140014720  mov     ecx, r12d; unsigned __int64
0x140014723  mov     r13d, r12d
0x140014726  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14001472b  mov     rbx, rax
0x14001472e  test    rax, rax
0x140014731  jz      loc_140014AC3
0x140014737  mov     r8d, r13d; Size
0x14001473a  xor     edx, edx; Val
0x14001473c  mov     rcx, rax; void *
0x14001473f  call    memset
0x140014744  mov     dword ptr [rbx], 2640180h
0x14001474a  lea     r13, [rbx+34h]
0x14001474e  mov     eax, [rbp+57h+var_8C]
0x140014751  lea     r9, [rbp+57h+var_A8]; unsigned __int16 *
0x140014755  mov     [r13+0], eax
0x140014759  lea     r8, [rbp+57h+var_B0]; unsigned int *
0x14001475d  movzx   eax, [rbp+57h+var_88]
0x140014761  lea     rcx, [rdi+1E0h]; this
0x140014768  mov     [r13+4], ax
0x14001476d  xorps   xmm0, xmm0
0x140014770  mov     eax, [rbp+57h+var_8C]
0x140014773  mov     [rbx+3Ah], eax
0x140014776  movzx   eax, [rbp+57h+var_88]
0x14001477a  mov     [rbx+3Eh], ax
0x14001477e  mov     eax, [rbp+57h+var_B0]
0x140014781  mov     [rbx+40h], eax
0x140014784  mov     [rbx+0Ch], r15d
0x140014788  mov     rax, [rdi+88h]
0x14001478f  movups  xmmword ptr [rbp+57h+var_A8], xmm0
0x140014793  mov     [rbp+57h+var_B0], 0
0x14001479a  mov     edx, [rax+1228h]
0x1400147a0  lea     rax, [rbp+57h+var_A8+8]
0x1400147a4  mov     [rbx+4], edx
0x1400147a7  mov     edx, 5; unsigned int
0x1400147ac  mov     [rsp+130h+var_110], rax; unsigned __int8 **
0x1400147b1  call    ?GetPropertyList@CPropertyCache@@QEBAHKPEAKPEAGPEAPEAE@Z; CPropertyCache::GetPropertyList(ulong,ulong *,ushort *,uchar * *)
0x1400147b6  test    eax, eax
0x1400147b8  jz      short loc_140014801
0x1400147ba  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x1400147c1  jz      short loc_1400147F4
0x1400147c3  movzx   ecx, word ptr [rdi+94h]
0x1400147ca  mov     r9d, 70h ; 'p'
0x1400147d0  mov     dword ptr [rsp+130h+var_F8], eax
0x1400147d4  mov     dl, 2
0x1400147d6  mov     dword ptr [rsp+130h+var_100], ecx
0x1400147da  mov     rcx, cs:WPP_GLOBAL_Control
0x1400147e1  mov     [rsp+130h+var_108], rdi
0x1400147e6  mov     [rsp+130h+var_110], r14
0x1400147eb  mov     rcx, [rcx+40h]
0x1400147ef  call    WPP_RECORDER_SF_qDD
0x1400147f4  mov     rcx, rbx; void *
0x1400147f7  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1400147fc  jmp     loc_140014AF9
0x140014801  cmp     [rbp+57h+var_B0], 24h ; '$'
0x140014805  jb      short loc_140014820
0x140014807  mov     rax, [rbp+57h+var_A8+8]
0x14001480b  movups  xmm0, xmmword ptr [rax]
0x14001480e  movups  xmmword ptr [rbx+10h], xmm0
0x140014812  movups  xmm1, xmmword ptr [rax+10h]
0x140014816  movups  xmmword ptr [rbx+20h], xmm1
0x14001481a  mov     eax, [rax+20h]
0x14001481d  mov     [rbx+30h], eax
0x140014820  call    Feature_Bugfix_56955488__private_IsEnabledDeviceUsageNoInline
0x140014825  test    eax, eax
0x140014827  jz      short loc_14001484D
0x140014829  mov     word ptr [rbx+44h], 1
0x14001482f  mov     dword ptr [rbx+48h], 8AC0F00h
0x140014836  mov     dword ptr [rbx+4Ch], 4AC0F00h
0x14001483d  mov     dword ptr [rbx+50h], 9
0x140014844  mov     dword ptr [rbx+54h], 4
0x14001484b  jmp     short loc_14001486B
0x14001484d  mov     dword ptr [rbx+1D8h], 10001h
0x140014857  mov     dword ptr [rbx+1DCh], 8AC0F00h
0x140014861  mov     dword ptr [rbx+218h], 4
0x14001486b  mov     eax, [rdi+98h]
0x140014871  xor     r14d, r14d
0x140014874  test    al, 0Ch
0x140014876  jnz     loc_140014929
0x14001487c  mov     rcx, [rdi+88h]
0x140014883  lea     rdx, [rbp+57h+var_8C]
0x140014887  add     rcx, 538h
0x14001488e  mov     rax, [rcx]
0x140014891  mov     rax, [rax]
0x140014894  call    _guard_dispatch_icall
0x140014899  mov     r15, rax
  ... truncated ...
```
