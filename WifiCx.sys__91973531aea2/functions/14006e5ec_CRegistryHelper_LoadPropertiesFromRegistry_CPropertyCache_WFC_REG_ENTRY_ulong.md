# CRegistryHelper::LoadPropertiesFromRegistry(CPropertyCache *,_WFC_REG_ENTRY *,ulong)

- ea: `0x14006e5ec`
- end: `0x14006e945`
- name: `?LoadPropertiesFromRegistry@CRegistryHelper@@QEAAHPEAVCPropertyCache@@PEAU_WFC_REG_ENTRY@@K@Z`
- size: `857`
- prototype: `__int64 __fastcall(CRegistryHelper *__hidden this, struct CPropertyCache *, struct _WFC_REG_ENTRY *, unsigned int)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, loader_planting`

## callers

- `0x140033378`

## callees

- `0x14000c778`
- `0x140024a20`
- `0x14002a9f8`
- `0x14002aaec`
- `0x140050574`
- `0x140059b78`
- `0x1400683ac`
- `0x140068474`
- `0x14006e5ec`
- `0x14006e94c`
- `0x14006ea14`
- `0x14006ebc8`
- `0x1400dfd00`

## pseudocode

```c
__int64 __fastcall CRegistryHelper::LoadPropertiesFromRegistry(
        CRegistryHelper *this,
        struct CPropertyCache *a2,
        struct _WFC_REG_ENTRY *a3)
{
  int v5; // eax
  int v6; // edx
  unsigned int i; // edi
  struct _WFC_REG_ENTRY near **v8; // rbx
  int v9; // edx
  __int64 v10; // r8
  int v11; // edx
  unsigned int v12; // eax
  unsigned int v13; // ebx
  int v14; // eax
  int v15; // edx
  int v16; // r8d
  int v17; // eax
  int v18; // r9d
  __int64 v20; // [rsp+28h] [rbp-51h]
  char v21; // [rsp+28h] [rbp-51h]
  char v22; // [rsp+30h] [rbp-49h]
  unsigned int v23; // [rsp+50h] [rbp-29h] BYREF
  unsigned int v24; // [rsp+54h] [rbp-25h] BYREF
  unsigned __int8 v25; // [rsp+58h] [rbp-21h] BYREF
  __int128 v26; // [rsp+59h] [rbp-20h]
  __int128 v27; // [rsp+69h] [rbp-10h]
  _BYTE v28[19]; // [rsp+79h] [rbp+0h] BYREF

  v24 = 52;
  v25 = 0;
  memset(v28, 0, sizeof(v28));
  v26 = 0;
  v27 = 0;
  if ( !*((_QWORD *)this + 1) )
  {
    v5 = CRegistryHelper::Open(this);
    if ( v5 )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v6) = 2;
        WPP_RECORDER_SF_d(
          WPP_GLOBAL_Control->DeviceExtension,
          v6,
          1,
          11,
          (__int64)WPP_4654a1ddfe193c37415c2a79da985a84_Traceguids,
          v5);
      }
    }
  }
  for ( i = 0; ; ++i )
  {
    if ( i >= 0x2D )
    {
      v14 = CRegistryHelper::ReadAdapterRegistryBinaries(this, L"StaLastConnectedAP", &v24, &v25);
      if ( v14 )
      {
        if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          return 0;
        LODWORD(v20) = v14;
        v18 = 18;
      }
      else
      {
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(v15) = 4;
          WPP_RECORDER_SF__MAC_Ddd(
            WPP_GLOBAL_Control->DeviceExtension,
            v15,
            v16,
            16,
            (__int64)WPP_4654a1ddfe193c37415c2a79da985a84_Traceguids,
            (__int64)&v25,
            SBYTE7(v26),
            SBYTE11(v26),
            SHIBYTE(v26));
        }
        v17 = CPropertyCache::SetPropertyBuffer(a2, 0x44u, v24, &v25);
        if ( !v17 || WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          return 0;
        LODWORD(v20) = v17;
        v18 = 17;
      }
      LOBYTE(v15) = 2;
      WPP_RECORDER_SF_d(
        WPP_GLOBAL_Control->DeviceExtension,
        v15,
        1,
        v18,
        (__int64)WPP_4654a1ddfe193c37415c2a79da985a84_Traceguids,
        v20);
      return 0;
    }
    v23 = 0;
    v8 = &g_AdapterRegTable + 5 * i;
    if ( !*((_QWORD *)this + 1) )
    {
      v9 = -1073741823;
LABEL_15:
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
        && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
      {
        v22 = v9;
        LOBYTE(v9) = 5;
        WPP_RECORDER_SF_dDd(
          WPP_GLOBAL_Control->DeviceExtension,
          v9,
          (_DWORD)a3,
          13,
          (__int64)WPP_4654a1ddfe193c37415c2a79da985a84_Traceguids,
          *((_DWORD *)v8 + 6),
          v22,
          *((_DWORD *)v8 + 7));
      }
      if ( *((_BYTE *)v8 + 16) > 1u )
        continue;
LABEL_20:
      v10 = *((unsigned int *)v8 + 7);
      goto LABEL_21;
    }
    v9 = CRegistryHelper::ReadAdapterRegistryDword(this, (struct _UNICODE_STRING *)(&g_AdapterRegTable + 5 * i), &v23);
    if ( v9 )
      goto LABEL_15;
    if ( *((_BYTE *)v8 + 16) > 1u )
      continue;
    v10 = v23;
    if ( v23 < *((_DWORD *)v8 + 8) || v23 > *((_DWORD *)v8 + 9) )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v9) = 2;
        WPP_RECORDER_SF_dDd(
          WPP_GLOBAL_Control->DeviceExtension,
          v9,
          v23,
          12,
          (__int64)WPP_4654a1ddfe193c37415c2a79da985a84_Traceguids,
          v23,
          *((_DWORD *)v8 + 6),
          *((_DWORD *)v8 + 7));
      }
      goto LABEL_20;
    }
LABEL_21:
    v11 = *((_DWORD *)v8 + 5);
    if ( v11 != 1 )
      break;
    v12 = CPropertyCache::SetPropertyULong(a2, *((_DWORD *)v8 + 6), v10);
LABEL_27:
    v13 = v12;
    if ( v12 )
      goto LABEL_32;
  }
  if ( *((_DWORD *)v8 + 5) == 2 )
  {
    LOBYTE(v10) = (_DWORD)v10 != 0;
    v12 = CPropertyCache::SetPropertyBoolean(a2, *((unsigned int *)v8 + 6), v10);
    goto LABEL_27;
  }
  if ( *((_DWORD *)v8 + 5) == 3 )
  {
    v12 = CPropertyCache::SetPropertyUchar(a2, *((_DWORD *)v8 + 6), v10);
    goto LABEL_27;
  }
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    v21 = v11;
    LOBYTE(v11) = 2;
    WPP_RECORDER_SF_Ld(
      WPP_GLOBAL_Control->DeviceExtension,
      v11,
      v10,
      14,
      (__int64)WPP_4654a1ddfe193c37415c2a79da985a84_Traceguids,
      v21,
      *((_DWORD *)v8 + 6));
  }
  v13 = -1073676267;
LABEL_32:
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LODWORD(v20) = v13;
    LOBYTE(v11) = 2;
    WPP_RECORDER_SF_d(
      WPP_GLOBAL_Control->DeviceExtension,
      v11,
      1,
      15,
      (__int64)WPP_4654a1ddfe193c37415c2a79da985a84_Traceguids,
      v20);
  }
  return v13;
}

```

## disassembly

```asm
0x14006e5ec  mov     [rsp-8+arg_10], rbx
0x14006e5f1  push    rbp
0x14006e5f2  push    rsi
0x14006e5f3  push    rdi
0x14006e5f4  push    r12
0x14006e5f6  push    r13
0x14006e5f8  push    r14
0x14006e5fa  push    r15
0x14006e5fc  lea     rbp, [rsp-27h]
0x14006e601  sub     rsp, 0A0h
0x14006e608  mov     rax, cs:__security_cookie
0x14006e60f  xor     rax, rsp
0x14006e612  mov     [rbp+57h+var_40], rax
0x14006e616  xor     r15d, r15d
0x14006e619  mov     [rbp+57h+var_7C], 34h ; '4'
0x14006e620  xorps   xmm0, xmm0
0x14006e623  mov     [rbp+57h+var_78], r15b
0x14006e627  xor     eax, eax
0x14006e629  lea     rbx, WPP_4654a1ddfe193c37415c2a79da985a84_Traceguids
0x14006e630  lea     r12, WPP_RECORDER_INITIALIZED
0x14006e637  mov     r14, rdx
0x14006e63a  lea     r13d, [r15+1]
0x14006e63e  mov     rsi, rcx
0x14006e641  movups  xmmword ptr [rbp+57h+var_57], xmm0
0x14006e645  mov     dword ptr [rbp+57h+var_57+0Fh], eax
0x14006e648  movups  [rbp+57h+var_77], xmm0
0x14006e64c  movups  [rbp+57h+var_67], xmm0
0x14006e650  cmp     [rcx+8], r15
0x14006e654  jnz     short loc_14006E68A
0x14006e656  call    ?Open@CRegistryHelper@@AEAAHXZ; CRegistryHelper::Open(void)
0x14006e65b  test    eax, eax
0x14006e65d  jz      short loc_14006E68A
0x14006e65f  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x14006e666  jz      short loc_14006E68A
0x14006e668  mov     rcx, cs:WPP_GLOBAL_Control
0x14006e66f  lea     r9d, [r15+0Bh]
0x14006e673  mov     dword ptr [rsp+0D0h+var_A8], eax
0x14006e677  mov     r8d, r13d
0x14006e67a  mov     dl, 2
0x14006e67c  mov     [rsp+0D0h+var_B0], rbx
0x14006e681  mov     rcx, [rcx+40h]
0x14006e685  call    WPP_RECORDER_SF_d
0x14006e68a  mov     edi, r15d
0x14006e68d  cmp     edi, 2Dh ; '-'
0x14006e690  jnb     loc_14006E84D
0x14006e696  mov     eax, edi
0x14006e698  mov     [rbp+57h+var_80], r15d
0x14006e69c  lea     rcx, [rax+rax*4]
0x14006e6a0  lea     rax, ?g_AdapterRegTable@@3PAU_WFC_REG_ENTRY@@A; " \""
0x14006e6a7  lea     rbx, [rax+rcx*8]
0x14006e6ab  cmp     [rsi+8], r15
0x14006e6af  jz      short loc_14006E72A
0x14006e6b1  lea     r8, [rbp+57h+var_80]; unsigned int *
0x14006e6b5  mov     rdx, rbx; struct _UNICODE_STRING *
0x14006e6b8  mov     rcx, rsi; this
0x14006e6bb  call    ?ReadAdapterRegistryDword@CRegistryHelper@@QEAAHPEAU_UNICODE_STRING@@PEAK@Z; CRegistryHelper::ReadAdapterRegistryDword(_UNICODE_STRING *,ulong *)
0x14006e6c0  mov     edx, eax
0x14006e6c2  test    eax, eax
0x14006e6c4  jnz     short loc_14006E72F
0x14006e6c6  cmp     [rbx+10h], r13b
0x14006e6ca  ja      loc_14006E7CB
0x14006e6d0  mov     r8d, [rbp+57h+var_80]
0x14006e6d4  cmp     r8d, [rbx+20h]
0x14006e6d8  jb      short loc_14006E6E4
0x14006e6da  cmp     r8d, [rbx+24h]
0x14006e6de  jbe     loc_14006E785
0x14006e6e4  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x14006e6eb  jz      loc_14006E781
0x14006e6f1  mov     eax, [rbx+1Ch]
0x14006e6f4  mov     r9d, 0Ch
0x14006e6fa  mov     rcx, cs:WPP_GLOBAL_Control
0x14006e701  mov     dl, 2
0x14006e703  mov     [rsp+0D0h+var_98], eax
0x14006e707  mov     eax, [rbx+18h]
0x14006e70a  mov     dword ptr [rsp+0D0h+var_A0], eax
0x14006e70e  lea     rax, WPP_4654a1ddfe193c37415c2a79da985a84_Traceguids
0x14006e715  mov     rcx, [rcx+40h]
0x14006e719  mov     dword ptr [rsp+0D0h+var_A8], r8d
0x14006e71e  mov     [rsp+0D0h+var_B0], rax
0x14006e723  call    WPP_RECORDER_SF_dDd
0x14006e728  jmp     short loc_14006E781
0x14006e72a  mov     edx, 0C0000001h
0x14006e72f  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x14006e736  jz      short loc_14006E77B
0x14006e738  mov     rcx, cs:WPP_GLOBAL_Control
0x14006e73f  cmp     byte ptr [rcx+29h], 5
0x14006e743  jnb     short loc_14006E74C
0x14006e745  cmp     [rcx+48h], r15w
0x14006e74a  jz      short loc_14006E77B
0x14006e74c  mov     eax, [rbx+1Ch]
0x14006e74f  mov     r9d, 0Dh
0x14006e755  mov     rcx, [rcx+40h]
0x14006e759  mov     [rsp+0D0h+var_98], eax
0x14006e75d  mov     eax, [rbx+18h]
0x14006e760  mov     dword ptr [rsp+0D0h+var_A0], edx
0x14006e764  mov     dl, 5
0x14006e766  mov     dword ptr [rsp+0D0h+var_A8], eax
0x14006e76a  lea     rax, WPP_4654a1ddfe193c37415c2a79da985a84_Traceguids
0x14006e771  mov     [rsp+0D0h+var_B0], rax
0x14006e776  call    WPP_RECORDER_SF_dDd
0x14006e77b  cmp     [rbx+10h], r13b
0x14006e77f  ja      short loc_14006E7CB
0x14006e781  mov     r8d, [rbx+1Ch]; unsigned int
0x14006e785  mov     edx, [rbx+14h]
0x14006e788  mov     ecx, edx
0x14006e78a  sub     ecx, r13d
0x14006e78d  jz      short loc_14006E7BA
0x14006e78f  sub     ecx, r13d
0x14006e792  jz      short loc_14006E7A6
0x14006e794  cmp     ecx, r13d
0x14006e797  jnz     short loc_14006E7D3
0x14006e799  mov     edx, [rbx+18h]; unsigned int
0x14006e79c  mov     rcx, r14; this
0x14006e79f  call    ?SetPropertyUchar@CPropertyCache@@QEAAHKE@Z; CPropertyCache::SetPropertyUchar(ulong,uchar)
0x14006e7a4  jmp     short loc_14006E7C5
0x14006e7a6  mov     edx, [rbx+18h]; unsigned int
0x14006e7a9  test    r8d, r8d
0x14006e7ac  mov     rcx, r14; this
0x14006e7af  setnz   r8b; unsigned __int8
0x14006e7b3  call    ?SetPropertyBoolean@CPropertyCache@@QEAAHKE@Z; CPropertyCache::SetPropertyBoolean(ulong,uchar)
0x14006e7b8  jmp     short loc_14006E7C5
0x14006e7ba  mov     edx, [rbx+18h]; unsigned int
0x14006e7bd  mov     rcx, r14; this
0x14006e7c0  call    ?SetPropertyULong@CPropertyCache@@QEAAHKK@Z; CPropertyCache::SetPropertyULong(ulong,ulong)
0x14006e7c5  mov     ebx, eax
0x14006e7c7  test    eax, eax
0x14006e7c9  jnz     short loc_14006E810
0x14006e7cb  add     edi, r13d
0x14006e7ce  jmp     loc_14006E68D
0x14006e7d3  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x14006e7da  jz      short loc_14006E80B
0x14006e7dc  mov     eax, [rbx+18h]
0x14006e7df  mov     r9d, 0Eh
0x14006e7e5  mov     rcx, cs:WPP_GLOBAL_Control
0x14006e7ec  mov     dword ptr [rsp+0D0h+var_A0], eax
0x14006e7f0  lea     rax, WPP_4654a1ddfe193c37415c2a79da985a84_Traceguids
0x14006e7f7  mov     dword ptr [rsp+0D0h+var_A8], edx
0x14006e7fb  mov     dl, 2
0x14006e7fd  mov     [rsp+0D0h+var_B0], rax
0x14006e802  mov     rcx, [rcx+40h]
0x14006e806  call    WPP_RECORDER_SF_Ld
0x14006e80b  mov     ebx, 0C0010015h
0x14006e810  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x14006e817  jz      loc_14006E91B
0x14006e81d  mov     rcx, cs:WPP_GLOBAL_Control
0x14006e824  lea     rax, WPP_4654a1ddfe193c37415c2a79da985a84_Traceguids
0x14006e82b  mov     r9d, 0Fh
0x14006e831  mov     dword ptr [rsp+0D0h+var_A8], ebx
0x14006e835  mov     r8d, r13d
0x14006e838  mov     [rsp+0D0h+var_B0], rax
0x14006e83d  mov     dl, 2
0x14006e83f  mov     rcx, [rcx+40h]
0x14006e843  call    WPP_RECORDER_SF_d
0x14006e848  jmp     loc_14006E91B
0x14006e84d  lea     r9, [rbp+57h+var_78]; unsigned __int8 *
0x14006e851  mov     rcx, rsi; this
0x14006e854  lea     r8, [rbp+57h+var_7C]; unsigned int *
0x14006e858  lea     rdx, aStalastconnect; "StaLastConnectedAP"
0x14006e85f  call    ?ReadAdapterRegistryBinaries@CRegistryHelper@@QEAAHPEBGPEAKPEAE@Z; CRegistryHelper::ReadAdapterRegistryBinaries(ushort const *,ulong *,uchar *)
0x14006e864  test    eax, eax
0x14006e866  jnz     short loc_14006E8E4
0x14006e868  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x14006e86f  lea     rbx, WPP_4654a1ddfe193c37415c2a79da985a84_Traceguids
0x14006e876  jz      short loc_14006E8B1
0x14006e878  mov     rcx, cs:WPP_GLOBAL_Control
0x14006e87f  lea     r9d, [rax+10h]
0x14006e883  mov     eax, dword ptr [rbp+57h+var_77+0Fh]
0x14006e886  mov     dl, 4
0x14006e888  mov     [rsp+0D0h+var_90], eax
0x14006e88c  mov     eax, dword ptr [rbp+57h+var_77+0Bh]
0x14006e88f  mov     rcx, [rcx+40h]
0x14006e893  mov     [rsp+0D0h+var_98], eax
0x14006e897  mov     eax, dword ptr [rbp+57h+var_77+7]
0x14006e89a  mov     dword ptr [rsp+0D0h+var_A0], eax
0x14006e89e  lea     rax, [rbp+57h+var_78]
0x14006e8a2  mov     [rsp+0D0h+var_A8], rax
0x14006e8a7  mov     [rsp+0D0h+var_B0], rbx
0x14006e8ac  call    WPP_RECORDER_SF__MAC_Ddd
0x14006e8b1  mov     r8d, [rbp+57h+var_7C]; unsigned int
0x14006e8b5  lea     r9, [rbp+57h+var_78]; unsigned __int8 *
0x14006e8b9  mov     edx, 44h ; 'D'; unsigned int
0x14006e8be  mov     rcx, r14; this
0x14006e8c1  call    ?SetPropertyBuffer@CPropertyCache@@QEAAHKKPEBE@Z; CPropertyCache::SetPropertyBuffer(ulong,ulong,uchar const *)
0x14006e8c6  test    eax, eax
0x14006e8c8  jz      short loc_14006E918
0x14006e8ca  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x14006e8d1  jz      short loc_14006E918
0x14006e8d3  mov     dword ptr [rsp+0D0h+var_A8], eax
0x14006e8d7  mov     r9d, 11h
0x14006e8dd  mov     [rsp+0D0h+var_B0], rbx
0x14006e8e2  jmp     short loc_14006E903
0x14006e8e4  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x14006e8eb  jz      short loc_14006E918
0x14006e8ed  mov     dword ptr [rsp+0D0h+var_A8], eax
0x14006e8f1  mov     r9d, 12h
0x14006e8f7  lea     rax, WPP_4654a1ddfe193c37415c2a79da985a84_Traceguids
0x14006e8fe  mov     [rsp+0D0h+var_B0], rax
0x14006e903  mov     rcx, cs:WPP_GLOBAL_Control
0x14006e90a  mov     r8d, r13d
0x14006e90d  mov     dl, 2
0x14006e90f  mov     rcx, [rcx+40h]
0x14006e913  call    WPP_RECORDER_SF_d
0x14006e918  mov     ebx, r15d
0x14006e91b  mov     eax, ebx
0x14006e91d  mov     rcx, [rbp+57h+var_40]
0x14006e921  xor     rcx, rsp; StackCookie
0x14006e924  call    __security_check_cookie
0x14006e929  mov     rbx, [rsp+0D0h+arg_10]
0x14006e931  add     rsp, 0A0h
0x14006e938  pop     r15
0x14006e93a  pop     r14
0x14006e93c  pop     r13
0x14006e93e  pop     r12
0x14006e940  pop     rdi
0x14006e941  pop     rsi
0x14006e942  pop     rbp
0x14006e943  retn
```
