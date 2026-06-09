# CRdpBaseProtocol::HandleConfigDataPdu(ulong,uchar *)

- ea: `0x1800db928`
- end: `0x1800dc04f`
- name: `?HandleConfigDataPdu@CRdpBaseProtocol@@IEAAJKPEAE@Z`
- size: `1831`
- prototype: `__int64 __fastcall(CRdpBaseProtocol *__hidden this, unsigned int, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `16`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800db6a0`

## callees

- `0x18000ce04`
- `0x18000ce34`
- `0x180010d14`
- `0x180010d44`
- `0x18002aafc`
- `0x18004f5bc`
- `0x180076090`
- `0x180079770`
- `0x180079d2c`
- `0x18007a404`
- `0x18007a664`
- `0x18007f390`
- `0x1800a1dc8`
- `0x1800db928`
- `0x1800df340`
- `0x1800dfee8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800dbc86`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800dbc86`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800dbca3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800dbca3`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800dbc4b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800dbc4b`

## pseudocode

```c
__int64 __fastcall CRdpBaseProtocol::HandleConfigDataPdu(CRdpBaseProtocol *this, unsigned int a2, unsigned __int8 *a3)
{
  int v3; // r13d
  RdpGfxEchoChannelHandler *v5; // rbx
  int v7; // r14d
  __int64 v8; // r15
  char v9; // al
  int v10; // r14d
  unsigned int CurrentThreadActivityIdPrefix; // eax
  unsigned int v12; // eax
  __int64 v13; // r11
  unsigned int v14; // r10d
  __int64 v15; // r9
  __int64 v16; // rdx
  int v17; // ecx
  int v18; // eax
  int v19; // eax
  int v20; // r10d
  DWORD v21; // r14d
  LSTATUS v22; // eax
  PVOID *v23; // rcx
  unsigned int v24; // eax
  const wchar_t *v25; // rcx
  unsigned int v26; // eax
  int v27; // eax
  __int64 v28; // r8
  __int64 v29; // rax
  _OWORD *v30; // rcx
  unsigned __int8 *v31; // rdx
  __int64 v32; // rax
  __int128 v33; // xmm1
  __int64 v34; // rcx
  __int64 v35; // rax
  _OWORD *v36; // rcx
  unsigned __int8 *v37; // rdx
  __int64 v38; // rax
  __int128 v39; // xmm1
  DWORD v40; // r14d
  unsigned int v41; // eax
  unsigned int v42; // eax
  BYTE Data[4]; // [rsp+30h] [rbp-40h] BYREF
  DWORD cbData; // [rsp+34h] [rbp-3Ch] BYREF
  RdpGfxEchoChannelHandler *v46; // [rsp+38h] [rbp-38h] BYREF
  __int64 v47; // [rsp+40h] [rbp-30h] BYREF
  HKEY hKey; // [rsp+48h] [rbp-28h] BYREF
  __int64 v49; // [rsp+50h] [rbp-20h] BYREF
  int v50; // [rsp+58h] [rbp-18h]
  DWORD v51; // [rsp+5Ch] [rbp-14h]
  _DWORD v52[4]; // [rsp+60h] [rbp-10h] BYREF
  char *v54; // [rsp+C0h] [rbp+50h] BYREF
  DWORD Type; // [rsp+C8h] [rbp+58h] BYREF

  v3 = 0;
  v47 = 0;
  v5 = 0;
  v46 = 0;
  hKey = 0;
  if ( !a3 || a2 < 0x24C )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 74, &WPP_4cda253553793e3fbb44ff49f99c4e58_Traceguids);
    }
    v7 = -2147024809;
    goto LABEL_78;
  }
  v7 = 0;
  v54 = (char *)this + 128;
  CTSCriticalSection::Lock((CRdpBaseProtocol *)((char *)this + 128));
  if ( *((_DWORD *)this + 20) != 1 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 75, &WPP_4cda253553793e3fbb44ff49f99c4e58_Traceguids);
    }
    CTSAutoLock::~CTSAutoLock((CTSAutoLock *)&v54);
    goto LABEL_79;
  }
  *((_DWORD *)this + 20) = 2;
  v8 = 0;
  if ( *((_QWORD *)this + 12) )
  {
    TCntPtr<IRdpVCMgr>::SafeRelease(&v47);
    v8 = *((_QWORD *)this + 12);
    v47 = v8;
    TCntPtr<IRDPWDUMX_StackEx>::SafeAddRef(&v47);
  }
  if ( *((_QWORD *)this + 1335) )
  {
    TCntPtr<ClearCompressor>::SafeRelease(&v46);
    v5 = (RdpGfxEchoChannelHandler *)*((_QWORD *)this + 1335);
    v46 = v5;
    TCntPtr<CaProgressiveSurfaceContext>::SafeAddRef(&v46);
  }
  CTSAutoLock::~CTSAutoLock((CTSAutoLock *)&v54);
  if ( v8 )
  {
    v9 = ~(unsigned __int8)(*((_DWORD *)a3 + 1) >> 11);
    LODWORD(v54) = 0;
    v10 = 16;
    *((_DWORD *)this + 2637) = v9 & 1;
    *((_DWORD *)this + 2636) = (*((_DWORD *)a3 + 1) >> 19) & 7;
    *((_DWORD *)this + 2635) = *((_DWORD *)a3 + 1) & 0xF;
    *((_DWORD *)this + 2632) = (*((_DWORD *)a3 + 1) >> 4) & 0x3F;
    *((_DWORD *)this + 149) = *((_DWORD *)a3 + 2);
    if ( *((_DWORD *)this + 2638) || *((_DWORD *)this + 2639) )
    {
      if ( (*((_DWORD *)a3 + 1) & 0x1000) != 0 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        {
          CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            76,
            &WPP_4cda253553793e3fbb44ff49f99c4e58_Traceguids,
            CurrentThreadActivityIdPrefix);
        }
        *((_DWORD *)this + 2632) = 16;
      }
      else
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        {
          v12 = RdpWppGetCurrentThreadActivityIdPrefix();
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 77, &WPP_4cda253553793e3fbb44ff49f99c4e58_Traceguids, v12);
        }
        *((_DWORD *)this + 2632) = 32;
      }
    }
    if ( *((_DWORD *)this + 149) <= 0x10u )
      v10 = *((_DWORD *)this + 149);
    else
      *((_DWORD *)this + 149) = 16;
    v13 = 0;
    v49 = 0;
    v50 = 0;
    Type = 0;
    v14 = 0;
    v51 = 0;
    if ( v10 )
    {
      do
      {
        v15 = 32LL * v14;
        v16 = 5LL * v14;
        v17 = *(_DWORD *)&a3[v15 + 12];
        v52[1] = *(_DWORD *)&a3[v15 + 16];
        v18 = *(_DWORD *)&a3[v15 + 20] + 1;
        v52[0] = v17;
        v52[2] = v18;
        v52[3] = *(_DWORD *)&a3[v15 + 24] + 1;
        *((_DWORD *)this + 5 * v14 + 150) = v17;
        *((_DWORD *)this + v16 + 151) = *(_DWORD *)&a3[v15 + 16];
        *((_DWORD *)this + v16 + 152) = *(_DWORD *)&a3[v15 + 20];
        *((_DWORD *)this + v16 + 153) = *(_DWORD *)&a3[v15 + 24];
        v19 = v13;
        LOBYTE(v19) = *(_DWORD *)&a3[v15 + 40] != (_DWORD)v13;
        *((_DWORD *)this + v16 + 154) = v19;
        *((_DWORD *)this + v16 + 232) = *(_DWORD *)&a3[v15 + 36];
        *((_DWORD *)this + v16 + 231) = *(_DWORD *)&a3[v15 + 32];
        *((_DWORD *)this + 5 * v14 + 230) = *(_DWORD *)&a3[v15 + 28];
        *(_QWORD *)((char *)this + 4 * v16 + 932) = v13;
        RdpRect::Union((RdpRect *)&v49, (const struct RdpRect *)v52);
        v14 = v20 + 1;
      }
      while ( v14 < *((_DWORD *)this + 149) );
      v21 = v51;
      v3 = v50;
    }
    else
    {
      v21 = Type;
    }
    if ( !RegOpenKeyExW(
            HKEY_LOCAL_MACHINE,
            L"SYSTEM\\CurrentControlSet\\Control\\Terminal Server\\WinStations",
            0,
            0x20019u,
            &hKey) )
    {
      *(_DWORD *)Data = 0;
      Type = 0;
      cbData = 4;
      v22 = RegQueryValueExW(hKey, L"IgnoreClientDesktopScaleFactor", 0, &Type, Data, &cbData);
      if ( !v22 && Type == 4 )
      {
        LOBYTE(v22) = *(_DWORD *)Data != 0;
        LODWORD(v54) = v22;
      }
      RegCloseKey(hKey);
    }
    v23 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      v24 = RdpWppGetCurrentThreadActivityIdPrefix();
      v25 = L"TRUE";
      if ( (_DWORD)v54 != 1 )
        v25 = L"FALSE";
      WPP_SF_DS(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        78,
        (unsigned int)&WPP_4cda253553793e3fbb44ff49f99c4e58_Traceguids,
        v24,
        (__int64)v25);
      v23 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( (*((_DWORD *)a3 + 1) & 0x78000u) >= 0x8000 && a2 >= 0x248C )
    {
      if ( v23 != &WPP_GLOBAL_Control && (*((_DWORD *)v23 + 7) & 0x100) != 0 && *((_BYTE *)v23 + 25) >= 4u )
      {
        v26 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 79, &WPP_4cda253553793e3fbb44ff49f99c4e58_Traceguids, v26);
      }
      v27 = *((_DWORD *)this + 149);
      v28 = 0;
      if ( (_DWORD)v54 )
      {
        if ( v27 )
        {
          do
          {
            *((_DWORD *)this + 5 * v28 + 234) = *(_DWORD *)&a3[4 * v28 + 652];
            v29 = 540LL * (unsigned int)v28;
            v30 = (_OWORD *)((char *)this + v29 + 1240);
            v31 = &a3[v29 + 716];
            v32 = 4;
            do
            {
              *v30 = *(_OWORD *)v31;
              v30[1] = *((_OWORD *)v31 + 1);
              v30[2] = *((_OWORD *)v31 + 2);
              v30[3] = *((_OWORD *)v31 + 3);
              v30[4] = *((_OWORD *)v31 + 4);
              v30[5] = *((_OWORD *)v31 + 5);
              v30[6] = *((_OWORD *)v31 + 6);
              v33 = *((_OWORD *)v31 + 7);
              v31 += 128;
              v30[7] = v33;
              v30 += 8;
              --v32;
            }
            while ( v32 );
            v28 = (unsigned int)(v28 + 1);
            *v30 = *(_OWORD *)v31;
            *(_OWORD *)((char *)v30 + 12) = *(_OWORD *)(v31 + 12);
          }
          while ( (unsigned int)v28 < *((_DWORD *)this + 149) );
        }
      }
      else if ( v27 )
      {
        do
        {
          v34 = 5 * v28;
          *((_DWORD *)this + v34 + 233) = *(_DWORD *)&a3[4 * v28 + 588];
          *((_DWORD *)this + v34 + 234) = *(_DWORD *)&a3[4 * v28 + 652];
          v35 = 540LL * (unsigned int)v28;
          v36 = (_OWORD *)((char *)this + v35 + 1240);
          v37 = &a3[v35 + 716];
          v38 = 4;
          do
          {
            *v36 = *(_OWORD *)v37;
            v36[1] = *((_OWORD *)v37 + 1);
            v36[2] = *((_OWORD *)v37 + 2);
            v36[3] = *((_OWORD *)v37 + 3);
            v36[4] = *((_OWORD *)v37 + 4);
            v36[5] = *((_OWORD *)v37 + 5);
            v36[6] = *((_OWORD *)v37 + 6);
            v39 = *((_OWORD *)v37 + 7);
            v37 += 128;
            v36[7] = v39;
            v36 += 8;
            --v38;
          }
          while ( v38 );
          v28 = (unsigned int)(v28 + 1);
          *v36 = *(_OWORD *)v37;
          *(_OWORD *)((char *)v36 + 12) = *(_OWORD *)(v37 + 12);
        }
        while ( (unsigned int)v28 < *((_DWORD *)this + 149) );
      }
    }
    v40 = v21 - HIDWORD(v49);
    *((_DWORD *)this + 2633) = v3 - v49;
    *((_DWORD *)this + 2634) = v40;
    memcpy_s((char *)this + 10932, 0x40u, a3 + 524, 0x40u);
    if ( !*((_DWORD *)this + 2637)
      && v5
      && (int)RdpGfxEchoChannelHandler::OpenEchoChannel(v5) < 0
      && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
    {
      v41 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 80, &WPP_4cda253553793e3fbb44ff49f99c4e58_Traceguids, v41);
    }
    v7 = CRdpBaseProtocol::ResetShare(
           this,
           *((_DWORD *)this + 2633),
           *((_DWORD *)this + 2634),
           *((_DWORD *)this + 149),
           (struct tagRFX_GFX_MONITOR_INFO *)(a3 + 12));
    if ( v7 < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v42 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_DsD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          81,
          (unsigned int)&WPP_4cda253553793e3fbb44ff49f99c4e58_Traceguids,
          v42,
          (__int64)"Failed to restart share",
          v7);
      }
LABEL_78:
      *((_DWORD *)this + 20) = 7;
    }
  }
LABEL_79:
  TCntPtr<ClearCompressor>::SafeRelease(&v46);
  TCntPtr<IRdpVCMgr>::SafeRelease(&v47);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1800db928  mov     [rsp-38h+arg_8], edx
0x1800db92c  push    rbp
0x1800db92d  push    rbx
0x1800db92e  push    rsi
0x1800db92f  push    rdi
0x1800db930  push    r13
0x1800db932  push    r14
0x1800db934  push    r15
0x1800db936  mov     rbp, rsp
0x1800db939  sub     rsp, 70h
0x1800db93d  xor     r13d, r13d
0x1800db940  mov     rsi, r8
0x1800db943  mov     [rbp+var_30], r13
0x1800db947  mov     ebx, r13d
0x1800db94a  mov     [rbp+var_38], rbx
0x1800db94e  mov     eax, edx
0x1800db950  mov     [rbp+hKey], r13
0x1800db954  mov     rdi, rcx
0x1800db957  test    r8, r8
0x1800db95a  jz      loc_1800DBFEA
0x1800db960  cmp     eax, 24Ch
0x1800db965  jb      loc_1800DBFEA
0x1800db96b  sub     rcx, 0FFFFFFFFFFFFFF80h; this
0x1800db96f  mov     r14d, r13d
0x1800db972  mov     [rbp+arg_10], rcx
0x1800db976  call    ?Lock@CTSCriticalSection@@QEAAXXZ; CTSCriticalSection::Lock(void)
0x1800db97b  cmp     dword ptr [rdi+50h], 1
0x1800db97f  jz      short loc_1800DB9C2
0x1800db981  mov     rcx, cs:WPP_GLOBAL_Control
0x1800db988  lea     r15, WPP_GLOBAL_Control
0x1800db98f  cmp     rcx, r15
0x1800db992  jz      short loc_1800DB9B4
0x1800db994  test    byte ptr [rcx+1Ch], 8
0x1800db998  jz      short loc_1800DB9B4
0x1800db99a  cmp     byte ptr [rcx+19h], 1
0x1800db99e  jb      short loc_1800DB9B4
0x1800db9a0  mov     rcx, [rcx+10h]
0x1800db9a4  lea     edx, [r13+4Bh]
0x1800db9a8  lea     r8, WPP_4cda253553793e3fbb44ff49f99c4e58_Traceguids
0x1800db9af  call    WPP_SF_
0x1800db9b4  lea     rcx, [rbp+arg_10]; this
0x1800db9b8  call    ??1CTSAutoLock@@QEAA@XZ; CTSAutoLock::~CTSAutoLock(void)
0x1800db9bd  jmp     loc_1800DC02B
0x1800db9c2  mov     dword ptr [rdi+50h], 2
0x1800db9c9  mov     r15, r13
0x1800db9cc  cmp     [rdi+60h], r13
0x1800db9d0  jz      short loc_1800DB9EC
0x1800db9d2  lea     rcx, [rbp+var_30]
0x1800db9d6  call    ?SafeRelease@?$TCntPtr@UIRdpVCMgr@@@@AEAAXXZ; TCntPtr<IRdpVCMgr>::SafeRelease(void)
0x1800db9db  mov     r15, [rdi+60h]
0x1800db9df  lea     rcx, [rbp+var_30]
0x1800db9e3  mov     [rbp+var_30], r15
0x1800db9e7  call    ?SafeAddRef@?$TCntPtr@UIRDPWDUMX_StackEx@@@@AEAAXXZ; TCntPtr<IRDPWDUMX_StackEx>::SafeAddRef(void)
0x1800db9ec  cmp     [rdi+29B8h], r13
0x1800db9f3  jz      short loc_1800DBA12
0x1800db9f5  lea     rcx, [rbp+var_38]
0x1800db9f9  call    ?SafeRelease@?$TCntPtr@VClearCompressor@@@@AEAAXXZ; TCntPtr<ClearCompressor>::SafeRelease(void)
0x1800db9fe  mov     rbx, [rdi+29B8h]
0x1800dba05  lea     rcx, [rbp+var_38]
0x1800dba09  mov     [rbp+var_38], rbx
0x1800dba0d  call    ?SafeAddRef@?$TCntPtr@VCaProgressiveSurfaceContext@@@@AEAAXXZ; TCntPtr<CaProgressiveSurfaceContext>::SafeAddRef(void)
0x1800dba12  lea     rcx, [rbp+arg_10]; this
0x1800dba16  call    ??1CTSAutoLock@@QEAA@XZ; CTSAutoLock::~CTSAutoLock(void)
0x1800dba1b  test    r15, r15
0x1800dba1e  jz      loc_1800DC02B
0x1800dba24  mov     eax, [rsi+4]
0x1800dba27  lea     r15, WPP_GLOBAL_Control
0x1800dba2e  shr     eax, 0Bh
0x1800dba31  mov     ecx, 100h
0x1800dba36  not     eax
0x1800dba38  mov     dword ptr [rbp+arg_10], r13d
0x1800dba3c  and     eax, 1
0x1800dba3f  mov     r14d, 10h
0x1800dba45  mov     [rdi+2934h], eax
0x1800dba4b  mov     eax, [rsi+4]
0x1800dba4e  shr     eax, 13h
0x1800dba51  and     eax, 7
0x1800dba54  mov     [rdi+2930h], eax
0x1800dba5a  mov     eax, [rsi+4]
0x1800dba5d  and     eax, 0Fh
0x1800dba60  mov     [rdi+292Ch], eax
0x1800dba66  mov     eax, [rsi+4]
0x1800dba69  shr     eax, 4
0x1800dba6c  and     eax, 3Fh
0x1800dba6f  mov     [rdi+2920h], eax
0x1800dba75  mov     eax, [rsi+8]
0x1800dba78  mov     [rdi+254h], eax
0x1800dba7e  cmp     [rdi+2938h], r13d
0x1800dba85  jnz     short loc_1800DBA94
0x1800dba87  cmp     [rdi+293Ch], r13d
0x1800dba8e  jz      loc_1800DBB26
0x1800dba94  test    dword ptr [rsi+4], 1000h
0x1800dba9b  jz      short loc_1800DBAE1
0x1800dba9d  mov     rax, cs:WPP_GLOBAL_Control
0x1800dbaa4  cmp     rax, r15
0x1800dbaa7  jz      short loc_1800DBAD8
0x1800dbaa9  test    [rax+1Ch], ecx
0x1800dbaac  jz      short loc_1800DBAD8
0x1800dbaae  cmp     byte ptr [rax+19h], 4
0x1800dbab2  jb      short loc_1800DBAD8
0x1800dbab4  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800dbab9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800dbac0  lea     r8, WPP_4cda253553793e3fbb44ff49f99c4e58_Traceguids
0x1800dbac7  mov     edx, 4Ch ; 'L'
0x1800dbacc  mov     r9d, eax
0x1800dbacf  mov     rcx, [rcx+10h]
0x1800dbad3  call    WPP_SF_d
0x1800dbad8  mov     [rdi+2920h], r14d
0x1800dbadf  jmp     short loc_1800DBB26
0x1800dbae1  mov     rax, cs:WPP_GLOBAL_Control
0x1800dbae8  cmp     rax, r15
0x1800dbaeb  jz      short loc_1800DBB1C
0x1800dbaed  test    [rax+1Ch], ecx
0x1800dbaf0  jz      short loc_1800DBB1C
0x1800dbaf2  cmp     byte ptr [rax+19h], 4
0x1800dbaf6  jb      short loc_1800DBB1C
0x1800dbaf8  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800dbafd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800dbb04  lea     r8, WPP_4cda253553793e3fbb44ff49f99c4e58_Traceguids
0x1800dbb0b  mov     edx, 4Dh ; 'M'
0x1800dbb10  mov     r9d, eax
0x1800dbb13  mov     rcx, [rcx+10h]
0x1800dbb17  call    WPP_SF_d
0x1800dbb1c  mov     dword ptr [rdi+2920h], 20h ; ' '
0x1800dbb26  mov     eax, [rdi+254h]
0x1800dbb2c  cmp     eax, r14d
0x1800dbb2f  jbe     short loc_1800DBB3A
0x1800dbb31  mov     [rdi+254h], r14d
0x1800dbb38  jmp     short loc_1800DBB3D
0x1800dbb3a  mov     r14d, eax
0x1800dbb3d  xor     r11d, r11d
0x1800dbb40  mov     [rbp+var_20], r13
0x1800dbb44  mov     [rbp+var_18], r13d
0x1800dbb48  mov     eax, r11d
0x1800dbb4b  mov     [rbp+Type], eax
0x1800dbb4e  mov     r10d, r11d
0x1800dbb51  mov     [rbp+var_14], eax
0x1800dbb54  test    r14d, r14d
0x1800dbb57  jz      loc_1800DBC27
0x1800dbb5d  mov     r8d, r10d
0x1800dbb60  mov     r9d, r10d
0x1800dbb63  shl     r9, 5
0x1800dbb67  lea     rdx, [r8+r8*4]
0x1800dbb6b  mov     eax, [r9+rsi+10h]
0x1800dbb70  mov     ecx, [r9+rsi+0Ch]
0x1800dbb75  mov     [rbp+var_C], eax
0x1800dbb78  mov     eax, [r9+rsi+14h]
0x1800dbb7d  inc     eax
0x1800dbb7f  mov     [rbp+var_10], ecx
0x1800dbb82  mov     [rbp+var_8], eax
0x1800dbb85  mov     eax, [r9+rsi+18h]
0x1800dbb8a  inc     eax
0x1800dbb8c  mov     [rbp+var_4], eax
0x1800dbb8f  lea     rax, [r8+r8*4]
0x1800dbb93  mov     [rdi+rax*4+258h], ecx
0x1800dbb9a  lea     rcx, [r8+r8*4]
0x1800dbb9e  mov     eax, [r9+rsi+10h]
0x1800dbba3  mov     [rdi+rdx*4+25Ch], eax
0x1800dbbaa  mov     eax, [r9+rsi+14h]
0x1800dbbaf  mov     [rdi+rdx*4+260h], eax
0x1800dbbb6  mov     eax, [r9+rsi+18h]
0x1800dbbbb  mov     [rdi+rdx*4+264h], eax
0x1800dbbc2  mov     eax, r11d
0x1800dbbc5  cmp     [r9+rsi+28h], r11d
0x1800dbbca  setnz   al
0x1800dbbcd  mov     [rdi+rdx*4+268h], eax
0x1800dbbd4  mov     eax, [r9+rsi+24h]
0x1800dbbd9  mov     [rdi+rdx*4+3A0h], eax
0x1800dbbe0  mov     eax, [r9+rsi+20h]
0x1800dbbe5  mov     [rdi+rdx*4+39Ch], eax
0x1800dbbec  mov     eax, [r9+rsi+1Ch]
0x1800dbbf1  mov     [rdi+rcx*4+398h], eax
0x1800dbbf8  lea     rcx, [rbp+var_20]; this
0x1800dbbfc  mov     [rdi+rdx*4+3A4h], r11
0x1800dbc04  lea     rdx, [rbp+var_10]; struct RdpRect *
0x1800dbc08  call    ?Union@RdpRect@@QEAA_NAEBU1@@Z; RdpRect::Union(RdpRect const &)
0x1800dbc0d  inc     r10d
0x1800dbc10  cmp     r10d, [rdi+254h]
0x1800dbc17  jb      loc_1800DBB5D
0x1800dbc1d  mov     r14d, [rbp+var_14]
0x1800dbc21  mov     r13d, [rbp+var_18]
0x1800dbc25  jmp     short loc_1800DBC2B
0x1800dbc27  mov     r14d, [rbp+Type]
0x1800dbc2b  lea     rax, [rbp+hKey]
0x1800dbc2f  mov     r9d, 20019h; samDesired
0x1800dbc35  xor     r8d, r8d; ulOptions
0x1800dbc38  mov     [rsp+70h+phkResult], rax; phkResult
0x1800dbc3d  lea     rdx, aSystemCurrentc_1; "SYSTEM\\CurrentControlSet\\Control\\Ter"...
0x1800dbc44  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800dbc4b  call    cs:__imp_RegOpenKeyExW
0x1800dbc51  test    eax, eax
0x1800dbc53  jnz     short loc_1800DBCA9
0x1800dbc55  mov     rcx, [rbp+hKey]; hKey
0x1800dbc59  lea     r9, [rbp+Type]; lpType
0x1800dbc5d  mov     dword ptr [rbp+Data], eax
0x1800dbc60  lea     rdx, aIgnoreclientde; "IgnoreClientDesktopScaleFactor"
0x1800dbc67  mov     [rbp+Type], eax
0x1800dbc6a  xor     r8d, r8d; lpReserved
0x1800dbc6d  lea     rax, [rbp+cbData]
0x1800dbc71  mov     [rbp+cbData], 4
0x1800dbc78  mov     [rsp+70h+lpcbData], rax; lpcbData
0x1800dbc7d  lea     rax, [rbp+Data]
0x1800dbc81  mov     [rsp+70h+phkResult], rax; lpData
0x1800dbc86  call    cs:__imp_RegQueryValueExW
0x1800dbc8c  test    eax, eax
0x1800dbc8e  jnz     short loc_1800DBC9F
0x1800dbc90  cmp     [rbp+Type], 4
0x1800dbc94  jnz     short loc_1800DBC9F
0x1800dbc96  cmp     dword ptr [rbp+Data], eax
0x1800dbc99  setnz   al
0x1800dbc9c  mov     dword ptr [rbp+arg_10], eax
0x1800dbc9f  mov     rcx, [rbp+hKey]; hKey
0x1800dbca3  call    cs:__imp_RegCloseKey
0x1800dbca9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800dbcb0  cmp     rcx, r15
0x1800dbcb3  jz      short loc_1800DBD0A
0x1800dbcb5  test    dword ptr [rcx+1Ch], 100h
0x1800dbcbc  jz      short loc_1800DBD0A
0x1800dbcbe  cmp     byte ptr [rcx+19h], 4
0x1800dbcc2  jb      short loc_1800DBD0A
0x1800dbcc4  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800dbcc9  cmp     dword ptr [rbp+arg_10], 1
0x1800dbccd  lea     rdx, aFalse_0; "FALSE"
0x1800dbcd4  lea     rcx, aTrue_0; "TRUE"
0x1800dbcdb  mov     r9d, eax
0x1800dbcde  cmovnz  rcx, rdx
0x1800dbce2  lea     r8, WPP_4cda253553793e3fbb44ff49f99c4e58_Traceguids
0x1800dbce9  mov     [rsp+70h+phkResult], rcx
0x1800dbcee  mov     edx, 4Eh ; 'N'
0x1800dbcf3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800dbcfa  mov     rcx, [rcx+10h]
0x1800dbcfe  call    WPP_SF_DS
0x1800dbd03  mov     rcx, cs:WPP_GLOBAL_Control
0x1800dbd0a  mov     eax, [rsi+4]
0x1800dbd0d  and     eax, 78000h
0x1800dbd12  cmp     eax, 8000h
0x1800dbd17  jb      loc_1800DBEE1
0x1800dbd1d  cmp     [rbp+arg_8], 248Ch
0x1800dbd24  jb      loc_1800DBEE1
0x1800dbd2a  cmp     rcx, r15
0x1800dbd2d  jz      short loc_1800DBD62
0x1800dbd2f  test    dword ptr [rcx+1Ch], 100h
0x1800dbd36  jz      short loc_1800DBD62
0x1800dbd38  cmp     byte ptr [rcx+19h], 4
0x1800dbd3c  jb      short loc_1800DBD62
0x1800dbd3e  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800dbd43  mov     rcx, cs:WPP_GLOBAL_Control
0x1800dbd4a  lea     r8, WPP_4cda253553793e3fbb44ff49f99c4e58_Traceguids
0x1800dbd51  mov     edx, 4Fh ; 'O'
0x1800dbd56  mov     r9d, eax
0x1800dbd59  mov     rcx, [rcx+10h]
0x1800dbd5d  call    WPP_SF_d
0x1800dbd62  mov     eax, [rdi+254h]
0x1800dbd68  xor     r8d, r8d
0x1800dbd6b  cmp     dword ptr [rbp+arg_10], r8d
0x1800dbd6f  jz      loc_1800DBE26
0x1800dbd75  test    eax, eax
0x1800dbd77  jz      loc_1800DBEE1
0x1800dbd7d  mov     r9d, 80h
0x1800dbd83  mov     eax, [rsi+r8*4+28Ch]
0x1800dbd8b  lea     rcx, [r8+r8*4]
0x1800dbd8f  mov     [rdi+rcx*4+3A8h], eax
0x1800dbd96  lea     rcx, [rdi+4D8h]
0x1800dbd9d  mov     edx, r8d
0x1800dbda0  imul    rax, rdx, 21Ch
0x1800dbda7  lea     rdx, [rsi+2CCh]
0x1800dbdae  add     rcx, rax
0x1800dbdb1  add     rdx, rax
0x1800dbdb4  mov     eax, 4
0x1800dbdb9  movups  xmm0, xmmword ptr [rdx]
0x1800dbdbc  movups  xmmword ptr [rcx], xmm0
0x1800dbdbf  movups  xmm1, xmmword ptr [rdx+10h]
0x1800dbdc3  movups  xmmword ptr [rcx+10h], xmm1
0x1800dbdc7  movups  xmm0, xmmword ptr [rdx+20h]
0x1800dbdcb  movups  xmmword ptr [rcx+20h], xmm0
0x1800dbdcf  movups  xmm1, xmmword ptr [rdx+30h]
0x1800dbdd3  movups  xmmword ptr [rcx+30h], xmm1
0x1800dbdd7  movups  xmm0, xmmword ptr [rdx+40h]
0x1800dbddb  movups  xmmword ptr [rcx+40h], xmm0
0x1800dbddf  movups  xmm1, xmmword ptr [rdx+50h]
0x1800dbde3  movups  xmmword ptr [rcx+50h], xmm1
0x1800dbde7  movups  xmm0, xmmword ptr [rdx+60h]
0x1800dbdeb  movups  xmmword ptr [rcx+60h], xmm0
0x1800dbdef  movups  xmm1, xmmword ptr [rdx+70h]
0x1800dbdf3  add     rdx, r9
0x1800dbdf6  movups  xmmword ptr [rcx+70h], xmm1
0x1800dbdfa  add     rcx, r9
0x1800dbdfd  sub     rax, 1
0x1800dbe01  jnz     short loc_1800DBDB9
0x1800dbe03  movups  xmm0, xmmword ptr [rdx]
0x1800dbe06  inc     r8d
0x1800dbe09  movups  xmmword ptr [rcx], xmm0
0x1800dbe0c  movups  xmm1, xmmword ptr [rdx+0Ch]
0x1800dbe10  movups  xmmword ptr [rcx+0Ch], xmm1
0x1800dbe14  cmp     r8d, [rdi+254h]
0x1800dbe1b  jb      loc_1800DBD83
0x1800dbe21  jmp     loc_1800DBEE1
0x1800dbe26  test    eax, eax
0x1800dbe28  jz      loc_1800DBEE1
0x1800dbe2e  mov     r9d, 80h
  ... truncated ...
```
