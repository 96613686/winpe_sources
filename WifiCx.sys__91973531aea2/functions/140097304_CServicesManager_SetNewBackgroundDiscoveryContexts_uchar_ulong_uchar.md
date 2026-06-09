# CServicesManager::SetNewBackgroundDiscoveryContexts(uchar,ulong,uchar *)

- ea: `0x140097304`
- end: `0x14009772e`
- name: `?SetNewBackgroundDiscoveryContexts@CServicesManager@@QEAAHEKPEAE@Z`
- size: `1066`
- prototype: `__int64 __fastcall(CServicesManager *__hidden this, unsigned __int8, unsigned int, unsigned __int8 *)`
- caller_count: `3`
- callee_count: `10`
- tags: `loader_planting, service_task`

## callers

- `0x140069fb0`
- `0x1400bdb24`
- `0x1400be280`

## callees

- `0x140009420`
- `0x14000c778`
- `0x14000d054`
- `0x140023fec`
- `0x140054e04`
- `0x1400953c8`
- `0x140097304`
- `0x14009a8c0`
- `0x14009b3f0`
- `0x1400e0100`

## import_xrefs

- `ntoskrnl!tolower` at `0x1400975c8`
- `ntoskrnl!tolower` at `0x1400975c8`

## pseudocode

```c
__int64 __fastcall CServicesManager::SetNewBackgroundDiscoveryContexts(
        CServicesManager ***this,
        char a2,
        unsigned int a3,
        unsigned __int8 *a4)
{
  char v6; // r13
  __int64 v8; // rdx
  int NdisPortNumberForPortType; // eax
  int v10; // edx
  int v11; // r9d
  unsigned int v12; // ebx
  int v13; // r14d
  unsigned int i; // ebp
  CServicesManager *v15; // rax
  CServicesManager *v16; // rbx
  __int64 v17; // rax
  int v18; // r8d
  CServicesManager **v19; // rcx
  __int64 v20; // rbp
  unsigned int v21; // r12d
  unsigned __int8 *v22; // r15
  _QWORD *v23; // rax
  _QWORD *v24; // r14
  __int64 v25; // rax
  char v26; // r8
  char v27; // dl
  int v28; // r8d
  int v29; // r9d
  unsigned int j; // r13d
  CServicesManager **v31; // rcx
  int v32; // ecx
  char v33; // al
  CServicesManager **v34; // rcx
  bool v35; // zf
  int v37; // [rsp+20h] [rbp-58h]
  __int64 v38; // [rsp+28h] [rbp-50h]

  v6 = a2;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      5,
      1,
      204,
      (__int64)WPP_3599b95ca20c3e0ba686e8b05788690d_Traceguids);
  }
  CServicesManager::FlushDiscoveryContexts((CServicesManager *)this);
  NdisPortNumberForPortType = CAdapter::GetNdisPortNumberForPortType(this[1], v8, this + 3);
  v11 = 0;
  v12 = NdisPortNumberForPortType;
  if ( NdisPortNumberForPortType )
  {
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      return v12;
    LOBYTE(v10) = 2;
    WPP_RECORDER_SF_d(
      WPP_GLOBAL_Control->DeviceExtension,
      v10,
      1,
      205,
      (__int64)WPP_3599b95ca20c3e0ba686e8b05788690d_Traceguids,
      NdisPortNumberForPortType);
    LOWORD(v11) = 0;
  }
  else
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
      && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
    {
      LOBYTE(v10) = 5;
      WPP_RECORDER_SF_d(
        WPP_GLOBAL_Control->DeviceExtension,
        v10,
        1,
        206,
        (__int64)WPP_3599b95ca20c3e0ba686e8b05788690d_Traceguids,
        *((_DWORD *)a4 + 5));
      v11 = 0;
    }
    v13 = *((_DWORD *)a4 + 4);
    for ( i = 0; i < *((_DWORD *)a4 + 5); ++i )
    {
      v15 = (CServicesManager *)operator new(0x30u);
      v11 = 0;
      v16 = v15;
      if ( !v15 )
        break;
      *((_QWORD *)v15 + 3) = 0;
      *((_BYTE *)v15 + 32) = 0;
      InitializeCppListEntry(v15, v15);
      v10 = v13;
      *(_DWORD *)(v17 + 40) = *(_DWORD *)&a4[v13];
      *(_WORD *)(v17 + 44) = *(_WORD *)&a4[v13 + 4];
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
        && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType) != (_WORD)v11) )
      {
        WPP_RECORDER_SF_d_MAC_(
          WPP_GLOBAL_Control->DeviceExtension,
          v13,
          v18,
          207,
          (__int64)WPP_3599b95ca20c3e0ba686e8b05788690d_Traceguids,
          *((_DWORD *)this + 23),
          v17 + 40);
        v11 = 0;
      }
      v19 = this[8];
      if ( *v19 != (CServicesManager *)(this + 7) )
LABEL_42:
        __fastfail(3u);
      *(_QWORD *)v16 = this + 7;
      v13 += 6;
      *((_QWORD *)v16 + 1) = v19;
      *v19 = v16;
      this[8] = (CServicesManager **)v16;
      ++*((_DWORD *)this + 23);
    }
    if ( *((_DWORD *)a4 + 14) )
    {
      v20 = *((unsigned int *)a4 + 15);
      if ( a3 > (unsigned int)v20 )
      {
        v21 = a3 - v20;
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
          && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType) != (_WORD)v11) )
        {
          LODWORD(v38) = *((_DWORD *)a4 + 14);
          LOBYTE(v10) = 5;
          WPP_RECORDER_SF_d(
            WPP_GLOBAL_Control->DeviceExtension,
            v10,
            1,
            208,
            (__int64)WPP_3599b95ca20c3e0ba686e8b05788690d_Traceguids,
            v38);
          v11 = 0;
        }
        v22 = &a4[v20];
        while ( *((_DWORD *)this + 22) < *((_DWORD *)a4 + 14) )
        {
          if ( v21 < 2 )
            break;
          if ( v21 < (unsigned int)*v22 + 1 )
            break;
          v23 = operator new(0x130u);
          v11 = 0;
          v24 = v23;
          if ( !v23 )
            break;
          v23[3] = 0;
          *((_BYTE *)v23 + 32) = 0;
          InitializeCppListEntry(v23, (struct _CPP_LIST_ENTRY *)v23);
          v27 = -1;
          if ( v26 != -1 )
            v27 = v26;
          *(_BYTE *)(v25 + 40) = v27;
          memset((void *)(v25 + 41), 0, 0x100u);
          for ( j = 0; j < *((unsigned __int8 *)v24 + 40); ++j )
            *((_BYTE *)v24 + j + 41) = tolower(v22[j + 1]);
          if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
            && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
          {
            WPP_RECORDER_SF_dds(
              WPP_GLOBAL_Control->DeviceExtension,
              *v22,
              v28,
              v29,
              v37,
              *((_DWORD *)this + 22),
              *v22,
              (__int64)v24 + 41);
          }
          v31 = this[10];
          if ( *v31 != (CServicesManager *)(this + 9) )
            goto LABEL_42;
          *v24 = this + 9;
          v24[1] = v31;
          *v31 = (CServicesManager *)v24;
          this[10] = (CServicesManager **)v24;
          ++*((_DWORD *)this + 22);
          v32 = *v22;
          LODWORD(v20) = v32 + v20 + 1;
          v21 += -1 - v32;
          v22 = &a4[(unsigned int)v20];
          v11 = 0;
        }
        v6 = a2;
      }
    }
    *((_BYTE *)this + 53) = v6;
    if ( v6 || *((_DWORD *)this + 23) != v11 || (v33 = v11, *((_DWORD *)this + 22) != v11) )
      v33 = 1;
    v12 = 0;
    *((_BYTE *)this + 52) = v33;
    v34 = this[1];
    v35 = *((_DWORD *)v34 + 442) == 4;
    *((_BYTE *)v34 + 1796) = v33;
    if ( v35 )
    {
      v10 = -994967296;
      v34[227] = (CServicesManager *)((-(__int64)(v33 != 0) & 0xC4B20100LL) + 300000000);
    }
  }
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType) != (_WORD)v11) )
  {
    LODWORD(v38) = v12;
    LOBYTE(v10) = 5;
    WPP_RECORDER_SF_d(
      WPP_GLOBAL_Control->DeviceExtension,
      v10,
      1,
      210,
      (__int64)WPP_3599b95ca20c3e0ba686e8b05788690d_Traceguids,
      v38);
  }
  return v12;
}

```

## disassembly

```asm
0x140097304  mov     [rsp+arg_10], rbx
0x140097309  mov     [rsp+arg_8], dl
0x14009730d  push    rbp
0x14009730e  push    rsi
0x14009730f  push    rdi
0x140097310  push    r12
0x140097312  push    r13
0x140097314  push    r14
0x140097316  push    r15
0x140097318  sub     rsp, 40h
0x14009731c  mov     rsi, r9
0x14009731f  mov     r12d, r8d
0x140097322  mov     r13b, dl
0x140097325  mov     rdi, rcx
0x140097328  lea     r15, WPP_RECORDER_INITIALIZED
0x14009732f  xor     eax, eax
0x140097331  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x140097338  lea     rbp, WPP_3599b95ca20c3e0ba686e8b05788690d_Traceguids
0x14009733f  jz      short loc_140097370
0x140097341  mov     rcx, cs:WPP_GLOBAL_Control
0x140097348  cmp     byte ptr [rcx+29h], 5
0x14009734c  jnb     short loc_140097354
0x14009734e  cmp     [rcx+48h], ax
0x140097352  jz      short loc_140097370
0x140097354  mov     rcx, [rcx+40h]
0x140097358  mov     r9d, 0CCh
0x14009735e  mov     r8d, 1
0x140097364  mov     [rsp+78h+var_58], rbp
0x140097369  mov     dl, 5
0x14009736b  call    WPP_RECORDER_SF_
0x140097370  mov     rcx, rdi; this
0x140097373  call    ?FlushDiscoveryContexts@CServicesManager@@AEAAXXZ; CServicesManager::FlushDiscoveryContexts(void)
0x140097378  mov     rcx, [rdi+8]
0x14009737c  lea     r8, [rdi+18h]
0x140097380  call    ?GetNdisPortNumberForPortType@CAdapter@@QEAAHW4_WFC_PORT_TYPE@@PEAK@Z; CAdapter::GetNdisPortNumberForPortType(_WFC_PORT_TYPE,ulong *)
0x140097385  xor     r9d, r9d
0x140097388  mov     [rsp+78h+arg_0], eax
0x14009738f  mov     ebx, eax
0x140097391  test    eax, eax
0x140097393  jz      short loc_1400973D1
0x140097395  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x14009739c  jz      loc_140097713
0x1400973a2  mov     rcx, cs:WPP_GLOBAL_Control
0x1400973a9  mov     r9d, 0CDh
0x1400973af  mov     dword ptr [rsp+78h+var_50], eax
0x1400973b3  mov     r8d, 1
0x1400973b9  mov     dl, 2
0x1400973bb  mov     [rsp+78h+var_58], rbp
0x1400973c0  mov     rcx, [rcx+40h]
0x1400973c4  call    WPP_RECORDER_SF_d
0x1400973c9  xor     r9d, r9d
0x1400973cc  jmp     loc_1400976D6
0x1400973d1  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x1400973d8  jz      short loc_140097414
0x1400973da  mov     rcx, cs:WPP_GLOBAL_Control
0x1400973e1  cmp     byte ptr [rcx+29h], 5
0x1400973e5  jnb     short loc_1400973EE
0x1400973e7  cmp     [rcx+48h], r9w
0x1400973ec  jz      short loc_140097414
0x1400973ee  mov     eax, [rsi+14h]
0x1400973f1  mov     r9d, 0CEh
0x1400973f7  mov     rcx, [rcx+40h]
0x1400973fb  mov     r8d, 1
0x140097401  mov     dword ptr [rsp+78h+var_50], eax
0x140097405  mov     dl, 5
0x140097407  mov     [rsp+78h+var_58], rbp
0x14009740c  call    WPP_RECORDER_SF_d
0x140097411  xor     r9d, r9d
0x140097414  mov     r14d, [rsi+10h]
0x140097418  mov     ebp, r9d
0x14009741b  cmp     ebp, [rsi+14h]
0x14009741e  jnb     loc_1400974DA
0x140097424  mov     ecx, 30h ; '0'; unsigned __int64
0x140097429  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14009742e  xor     r9d, r9d
0x140097431  mov     rbx, rax
0x140097434  test    rax, rax
0x140097437  jz      loc_1400974DA
0x14009743d  mov     rdx, rax; struct _CPP_LIST_ENTRY *
0x140097440  mov     [rax+18h], r9
0x140097444  mov     rcx, rax; void *
0x140097447  mov     [rax+20h], r9b
0x14009744b  call    ?InitializeCppListEntry@@YAXPEAXPEAU_CPP_LIST_ENTRY@@@Z; InitializeCppListEntry(void *,_CPP_LIST_ENTRY *)
0x140097450  mov     edx, r14d
0x140097453  mov     ecx, [rdx+rsi]
0x140097456  mov     [rax+28h], ecx
0x140097459  movzx   ecx, word ptr [rdx+rsi+4]
0x14009745e  mov     [rax+2Ch], cx
0x140097462  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x140097469  jz      short loc_1400974AD
0x14009746b  mov     rcx, cs:WPP_GLOBAL_Control
0x140097472  cmp     byte ptr [rcx+29h], 5
0x140097476  jnb     short loc_14009747F
0x140097478  cmp     [rcx+48h], r9w
0x14009747d  jz      short loc_1400974AD
0x14009747f  mov     rcx, [rcx+40h]
0x140097483  add     rax, 28h ; '('
0x140097487  mov     [rsp+78h+var_48], rax
0x14009748c  mov     r9d, 0CFh
0x140097492  mov     eax, [rdi+5Ch]
0x140097495  mov     dword ptr [rsp+78h+var_50], eax
0x140097499  lea     rax, WPP_3599b95ca20c3e0ba686e8b05788690d_Traceguids
0x1400974a0  mov     [rsp+78h+var_58], rax
0x1400974a5  call    WPP_RECORDER_SF_d_MAC_
0x1400974aa  xor     r9d, r9d
0x1400974ad  lea     rax, [rdi+38h]
0x1400974b1  mov     rcx, [rax+8]
0x1400974b5  cmp     [rcx], rax
0x1400974b8  jnz     loc_140097668
0x1400974be  mov     [rbx], rax
0x1400974c1  add     r14d, 6
0x1400974c5  mov     [rbx+8], rcx
0x1400974c9  mov     [rcx], rbx
0x1400974cc  mov     [rax+8], rbx
0x1400974d0  inc     dword ptr [rdi+5Ch]
0x1400974d3  inc     ebp
0x1400974d5  jmp     loc_14009741B
0x1400974da  mov     eax, [rsi+38h]
0x1400974dd  test    eax, eax
0x1400974df  jz      loc_14009767E
0x1400974e5  mov     ebp, [rsi+3Ch]
0x1400974e8  cmp     r12d, ebp
0x1400974eb  jbe     loc_14009767E
0x1400974f1  sub     r12d, ebp
0x1400974f4  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x1400974fb  jz      short loc_14009753B
0x1400974fd  mov     rcx, cs:WPP_GLOBAL_Control
0x140097504  cmp     byte ptr [rcx+29h], 5
0x140097508  jnb     short loc_140097511
0x14009750a  cmp     [rcx+48h], r9w
0x14009750f  jz      short loc_14009753B
0x140097511  mov     rcx, [rcx+40h]
0x140097515  mov     r9d, 0D0h
0x14009751b  mov     dword ptr [rsp+78h+var_50], eax
0x14009751f  mov     r8d, 1
0x140097525  lea     rax, WPP_3599b95ca20c3e0ba686e8b05788690d_Traceguids
0x14009752c  mov     dl, 5
0x14009752e  mov     [rsp+78h+var_58], rax
0x140097533  call    WPP_RECORDER_SF_d
0x140097538  xor     r9d, r9d
0x14009753b  lea     r15, [rsi+rbp]
0x14009753f  mov     eax, [rsi+38h]
0x140097542  cmp     [rdi+58h], eax
0x140097545  jnb     loc_14009766F
0x14009754b  cmp     r12d, 2
0x14009754f  jb      loc_14009766F
0x140097555  movzx   eax, byte ptr [r15]
0x140097559  inc     eax
0x14009755b  cmp     r12d, eax
0x14009755e  jb      loc_14009766F
0x140097564  mov     ecx, 130h; unsigned __int64
0x140097569  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14009756e  xor     r9d, r9d
0x140097571  mov     r14, rax
0x140097574  test    rax, rax
0x140097577  jz      loc_14009766F
0x14009757d  movzx   r8d, byte ptr [r15]
0x140097581  mov     rdx, rax; struct _CPP_LIST_ENTRY *
0x140097584  mov     rcx, rax; void *
0x140097587  mov     [rax+18h], r9
0x14009758b  mov     [rax+20h], r9b
0x14009758f  call    ?InitializeCppListEntry@@YAXPEAXPEAU_CPP_LIST_ENTRY@@@Z; InitializeCppListEntry(void *,_CPP_LIST_ENTRY *)
0x140097594  mov     edx, 0FFh
0x140097599  lea     rcx, [rax+29h]; void *
0x14009759d  cmp     r8b, dl
0x1400975a0  cmovb   edx, r8d
0x1400975a4  mov     r8d, 100h; Size
0x1400975aa  mov     [rax+28h], dl
0x1400975ad  xor     edx, edx; Val
0x1400975af  call    memset
0x1400975b4  xor     eax, eax
0x1400975b6  mov     r13d, eax
0x1400975b9  cmp     [r14+28h], al
0x1400975bd  jbe     short loc_1400975E8
0x1400975bf  mov     ebx, r13d
0x1400975c2  movzx   ecx, byte ptr [rbx+r15+1]; C
0x1400975c8  call    cs:__imp_tolower
0x1400975cf  nop     dword ptr [rax+rax+00h]
0x1400975d4  mov     [rbx+r14+29h], al
0x1400975d9  inc     r13d
0x1400975dc  movzx   eax, byte ptr [r14+28h]
0x1400975e1  cmp     r13d, eax
0x1400975e4  jb      short loc_1400975BF
0x1400975e6  xor     eax, eax
0x1400975e8  lea     rcx, WPP_RECORDER_INITIALIZED
0x1400975ef  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x1400975f6  jz      short loc_14009762C
0x1400975f8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400975ff  cmp     byte ptr [rcx+29h], 5
0x140097603  jnb     short loc_14009760B
0x140097605  cmp     [rcx+48h], ax
0x140097609  jz      short loc_14009762C
0x14009760b  movzx   edx, byte ptr [r15]
0x14009760f  lea     rax, [r14+29h]
0x140097613  mov     rcx, [rcx+40h]
0x140097617  mov     [rsp+78h+var_40], rax
0x14009761c  mov     eax, [rdi+58h]
0x14009761f  mov     dword ptr [rsp+78h+var_48], edx
0x140097623  mov     dword ptr [rsp+78h+var_50], eax
0x140097627  call    WPP_RECORDER_SF_dds
0x14009762c  lea     rax, [rdi+48h]
0x140097630  mov     rcx, [rax+8]
0x140097634  cmp     [rcx], rax
0x140097637  jnz     short loc_140097668
0x140097639  mov     [r14], rax
0x14009763c  inc     ebp
0x14009763e  mov     [r14+8], rcx
0x140097642  mov     [rcx], r14
0x140097645  mov     [rax+8], r14
0x140097649  or      eax, 0FFFFFFFFh
0x14009764c  inc     dword ptr [rdi+58h]
0x14009764f  movzx   ecx, byte ptr [r15]
0x140097653  add     ebp, ecx
0x140097655  sub     eax, ecx
0x140097657  mov     r15d, ebp
0x14009765a  add     r12d, eax
0x14009765d  add     r15, rsi
0x140097660  xor     r9d, r9d
0x140097663  jmp     loc_14009753F
0x140097668  mov     ecx, 3
0x14009766d  int     29h; Win8: RtlFailFast(ecx)
0x14009766f  mov     r13b, [rsp+78h+arg_8]
0x140097677  lea     r15, WPP_RECORDER_INITIALIZED
0x14009767e  mov     [rdi+35h], r13b
0x140097682  test    r13b, r13b
0x140097685  jnz     short loc_140097696
0x140097687  cmp     [rdi+5Ch], r9d
0x14009768b  jnz     short loc_140097696
0x14009768d  mov     al, r9b
0x140097690  cmp     [rdi+58h], r9d
0x140097694  jz      short loc_140097698
0x140097696  mov     al, 1
0x140097698  mov     ebx, [rsp+78h+arg_0]
0x14009769f  lea     rbp, WPP_3599b95ca20c3e0ba686e8b05788690d_Traceguids
0x1400976a6  mov     [rdi+34h], al
0x1400976a9  mov     rcx, [rdi+8]
0x1400976ad  cmp     dword ptr [rcx+6E8h], 4
0x1400976b4  mov     [rcx+704h], al
0x1400976ba  jnz     short loc_1400976D6
0x1400976bc  neg     al
0x1400976be  mov     edx, 0C4B20100h
0x1400976c3  sbb     rax, rax
0x1400976c6  and     rax, rdx
0x1400976c9  add     rax, 11E1A300h
0x1400976cf  mov     [rcx+718h], rax
0x1400976d6  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x1400976dd  jz      short loc_140097713
0x1400976df  mov     rcx, cs:WPP_GLOBAL_Control
0x1400976e6  cmp     byte ptr [rcx+29h], 5
0x1400976ea  jnb     short loc_1400976F3
0x1400976ec  cmp     [rcx+48h], r9w
0x1400976f1  jz      short loc_140097713
0x1400976f3  mov     rcx, [rcx+40h]
0x1400976f7  mov     r9d, 0D2h
0x1400976fd  mov     dword ptr [rsp+78h+var_50], ebx
0x140097701  mov     r8d, 1
0x140097707  mov     dl, 5
0x140097709  mov     [rsp+78h+var_58], rbp
0x14009770e  call    WPP_RECORDER_SF_d
0x140097713  mov     eax, ebx
0x140097715  mov     rbx, [rsp+78h+arg_10]
0x14009771d  add     rsp, 40h
0x140097721  pop     r15
0x140097723  pop     r14
0x140097725  pop     r13
0x140097727  pop     r12
0x140097729  pop     rdi
0x14009772a  pop     rsi
0x14009772b  pop     rbp
0x14009772c  retn
```
