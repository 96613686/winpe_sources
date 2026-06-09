# ZtUpdateRulesGlobal(_ZTDNS_SETTINGS_TYPE,ulong,_DNS_ZT_RULE *,int,DnsZtRuleMap * *)

- ea: `0x180011548`
- end: `0x180011852`
- name: `?ZtUpdateRulesGlobal@@YAJW4_ZTDNS_SETTINGS_TYPE@@KPEAU_DNS_ZT_RULE@@HPEAPEAVDnsZtRuleMap@@@Z`
- size: `778`
- prototype: `__int64 __fastcall(unsigned int, unsigned int, __int64, int, DnsZtRuleMap **)`
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, registry_config, installer_update`

## callers

- `0x18000ddec`

## callees

- `0x180007414`
- `0x18000759c`
- `0x180007630`
- `0x180007674`
- `0x180009eac`
- `0x18001107c`
- `0x1800110b8`
- `0x18001115c`
- `0x180011548`
- `0x1800126d8`
- `0x180012838`
- `0x180015008`
- `0x180016750`

## pseudocode

```c
__int64 __fastcall ZtUpdateRulesGlobal(unsigned int a1, unsigned int a2, __int64 a3, int a4, DnsZtRuleMap **a5)
{
  DnsZtRuleNode *v5; // rbx
  DnsZtRuleMap *v6; // rsi
  DnsZtRuleMap *v7; // r14
  DnsZtRuleNode *v8; // rdi
  unsigned int v10; // r8d
  unsigned int v12; // edx
  signed int v13; // r15d
  int v14; // eax
  int v15; // eax
  int v16; // eax
  __int64 i; // r12
  int v18; // eax
  unsigned int v19; // eax
  unsigned int v20; // r15d
  DnsZtRuleNode *v22; // [rsp+48h] [rbp-29h] BYREF
  unsigned int v23; // [rsp+50h] [rbp-21h]
  unsigned int v24; // [rsp+54h] [rbp-1Dh]
  DnsZtRuleNode *v25; // [rsp+58h] [rbp-19h] BYREF
  struct DnsZtRuleMap *v26; // [rsp+60h] [rbp-11h] BYREF
  __int64 v27; // [rsp+68h] [rbp-9h]
  __int64 v28; // [rsp+70h] [rbp-1h] BYREF
  DnsZtRuleMap *v29[2]; // [rsp+78h] [rbp+7h]

  v5 = 0;
  v6 = 0;
  v27 = a3;
  v7 = 0;
  v24 = a2;
  v8 = 0;
  v23 = a1;
  v25 = 0;
  v10 = a2;
  v26 = 0;
  v22 = 0;
  v12 = a1;
  v28 = 0;
  *(_OWORD *)v29 = 0;
  if ( (BYTE1(xmmword_18001F260) & 8) != 0 )
  {
    WPP_SF_ddql(a1, a1, v10, a1, v10, a3);
    v12 = v23;
    v10 = v24;
  }
  if ( a5 )
    *a5 = 0;
  if ( (v10 == 0) == (a3 == 0) )
  {
    if ( v12 <= 1 )
    {
      v14 = DnsZtRuleMap::CreateInstance(&v26);
      v6 = v26;
      v13 = v14;
      if ( v14 >= 0 )
      {
        if ( a4 )
        {
          CWxRefMap<DnsZtRuleMap,DnsZtRuleNode>::CWxIter::Attach(&v28, g_rgspDnsZtRuleMap[v23]);
          while ( 1 )
          {
            if ( v8 )
            {
              DnsZtRuleNode::Release(v8);
              v25 = 0;
            }
            v15 = CWxRefMap<DnsZtRuleMap,DnsZtRuleNode>::CWxIter::Next(&v28, &v25);
            v8 = v25;
            v13 = v15;
            if ( v15 < 0 )
              break;
            if ( v15 == 1 || !v25 )
              goto LABEL_26;
            v16 = DnsZtRuleNode::CreateCopy(v25, &v22);
            v13 = v16;
            if ( v16 > 0 )
              v13 = (unsigned __int16)v16 | 0x80070000;
            v5 = v22;
            if ( v13 < 0 )
              break;
            v13 = CWxRefMap<DnsZtRuleMap,DnsZtRuleNode>::Insert(v6, v22);
            if ( v13 < 0 )
              break;
            if ( v5 )
            {
              DnsZtRuleNode::Release(v5);
              v5 = 0;
              v22 = 0;
            }
          }
        }
        else
        {
LABEL_26:
          for ( i = 0; (unsigned int)i < v24; i = (unsigned int)(i + 1) )
          {
            v18 = DnsZtRuleNode::CreateInstance(
                    *(_DWORD *)(v27 + 48 * i),
                    *(_QWORD *)(v27 + 48 * i + 8),
                    *(unsigned __int16 *const *)(v27 + 48 * i + 16),
                    *(unsigned __int16 *const *)(v27 + 48 * i + 24),
                    *(const struct _DNS_ZT_SUBNET **)(v27 + 48 * i + 32),
                    *(_DWORD *)(v27 + 48 * i + 40),
                    &v22);
            v5 = v22;
            v13 = v18;
            if ( v18 < 0 )
              goto LABEL_37;
            CWxRefMap<DnsZtRuleMap,DnsZtRuleNode>::Delete((__int64)v6, (__int64)v22);
            v13 = CWxRefMap<DnsZtRuleMap,DnsZtRuleNode>::Insert(v6, v5);
            if ( v13 < 0 )
              goto LABEL_37;
            if ( v5 )
            {
              DnsZtRuleNode::Release(v5);
              v5 = 0;
              v22 = 0;
            }
          }
          v7 = (DnsZtRuleMap *)g_rgspDnsZtRuleMap[v23];
          g_rgspDnsZtRuleMap[v23] = (__int64)v6;
          v6 = 0;
          if ( a5 )
          {
            *a5 = v7;
            v7 = 0;
          }
        }
      }
    }
    else
    {
      v13 = -2147024809;
    }
  }
  else
  {
    v13 = -2147024809;
  }
LABEL_37:
  if ( (BYTE1(xmmword_18001F260) & 8) != 0 )
  {
    v19 = WX_WIN32_FROM_HR((unsigned int)v13);
    WPP_SF_d(1035, 13, WPP_948d2a298210377da68aa16776f92aa2_Traceguids, v19);
  }
  v20 = WX_WIN32_FROM_HR((unsigned int)v13);
  if ( v29[0] )
    DnsZtRuleMap::Release(v29[0]);
  if ( v8 )
    DnsZtRuleNode::Release(v8);
  if ( v5 )
    DnsZtRuleNode::Release(v5);
  if ( v6 )
    DnsZtRuleMap::Release(v6);
  if ( v7 )
    DnsZtRuleMap::Release(v7);
  return v20;
}

```

## disassembly

```asm
0x180011548  mov     [rsp-8+arg_8], rbx
0x18001154d  push    rbp
0x18001154e  push    rsi
0x18001154f  push    rdi
0x180011550  push    r12
0x180011552  push    r13
0x180011554  push    r14
0x180011556  push    r15
0x180011558  lea     rbp, [rsp-1Fh]
0x18001155d  sub     rsp, 90h
0x180011564  mov     r13, [rbp+4Fh+arg_20]
0x180011568  xor     ebx, ebx
0x18001156a  xor     esi, esi
0x18001156c  mov     [rbp+4Fh+var_58], r8
0x180011570  xor     r14d, r14d
0x180011573  mov     [rbp+4Fh+var_6C], edx
0x180011576  xor     edi, edi
0x180011578  mov     [rbp+4Fh+var_70], ecx
0x18001157b  mov     r15, r8
0x18001157e  mov     [rbp+4Fh+var_68], rdi
0x180011582  xorps   xmm0, xmm0
0x180011585  mov     [rbp+4Fh+var_7C], 0
0x18001158c  mov     r8d, edx
0x18001158f  mov     [rbp+4Fh+var_60], rsi
0x180011593  mov     r12d, r9d
0x180011596  mov     [rbp+4Fh+var_78], rbx
0x18001159a  mov     edx, ecx
0x18001159c  mov     [rbp+4Fh+var_50], rbx
0x1800115a0  movdqu  xmmword ptr [rbp+4Fh+var_48], xmm0
0x1800115a5  test    byte ptr cs:xmmword_18001F260+1, 8
0x1800115ac  jz      short loc_1800115CC
0x1800115ae  mov     dword ptr [rsp+0C0h+var_90], r9d
0x1800115b3  mov     r9d, ecx
0x1800115b6  mov     qword ptr [rsp+0C0h+var_98], r15
0x1800115bb  mov     dword ptr [rsp+0C0h+var_A0], r8d
0x1800115c0  call    WPP_SF_ddql
0x1800115c5  mov     edx, [rbp+4Fh+var_70]
0x1800115c8  mov     r8d, [rbp+4Fh+var_6C]
0x1800115cc  test    r13, r13
0x1800115cf  jz      short loc_1800115D5
0x1800115d1  mov     [r13+0], rbx
0x1800115d5  xor     ecx, ecx
0x1800115d7  test    r15, r15
0x1800115da  setz    cl
0x1800115dd  xor     eax, eax
0x1800115df  test    r8d, r8d
0x1800115e2  setz    al
0x1800115e5  cmp     eax, ecx
0x1800115e7  jz      short loc_1800115FB
0x1800115e9  mov     r15d, 80070057h
0x1800115ef  mov     [rbp+4Fh+var_7C], 33h ; '3'
0x1800115f6  jmp     loc_1800117BD
0x1800115fb  cmp     edx, 1
0x1800115fe  jbe     short loc_180011612
0x180011600  mov     r15d, 80070057h
0x180011606  mov     [rbp+4Fh+var_7C], 35h ; '5'
0x18001160d  jmp     loc_1800117BD
0x180011612  lea     rcx, [rbp+4Fh+var_60]; struct DnsZtRuleMap **
0x180011616  call    ?CreateInstance@DnsZtRuleMap@@SAJPEAPEAV1@@Z; DnsZtRuleMap::CreateInstance(DnsZtRuleMap * *)
0x18001161b  mov     rsi, [rbp+4Fh+var_60]
0x18001161f  mov     r15d, eax
0x180011622  test    eax, eax
0x180011624  jns     short loc_180011632
0x180011626  mov     [rbp+4Fh+var_7C], 3Bh ; ';'
0x18001162d  jmp     loc_1800117BD
0x180011632  lea     rcx, ?g_rgspDnsZtRuleMap@@3PAV?$AutoInterface@VDnsZtRuleMap@@@@A; AutoInterface<DnsZtRuleMap> near * g_rgspDnsZtRuleMap
0x180011639  test    r12d, r12d
0x18001163c  jz      loc_1800116FB
0x180011642  movsxd  rdx, [rbp+4Fh+var_70]
0x180011646  mov     rdx, [rcx+rdx*8]
0x18001164a  lea     rcx, [rbp+4Fh+var_50]
0x18001164e  call    ?Attach@CWxIter@?$CWxRefMap@VDnsZtRuleMap@@VDnsZtRuleNode@@@@QEAAJPEAVDnsZtRuleMap@@@Z; CWxRefMap<DnsZtRuleMap,DnsZtRuleNode>::CWxIter::Attach(DnsZtRuleMap *)
0x180011653  test    rdi, rdi
0x180011656  jz      short loc_180011664
0x180011658  mov     rcx, rdi; this
0x18001165b  call    ?Release@DnsZtRuleNode@@QEAAKXZ; DnsZtRuleNode::Release(void)
0x180011660  mov     [rbp+4Fh+var_68], r14
0x180011664  lea     rdx, [rbp+4Fh+var_68]
0x180011668  lea     rcx, [rbp+4Fh+var_50]
0x18001166c  call    ?Next@CWxIter@?$CWxRefMap@VDnsZtRuleMap@@VDnsZtRuleNode@@@@QEAAJPEAPEAVDnsZtRuleNode@@@Z; CWxRefMap<DnsZtRuleMap,DnsZtRuleNode>::CWxIter::Next(DnsZtRuleNode * *)
0x180011671  mov     rdi, [rbp+4Fh+var_68]
0x180011675  mov     r15d, eax
0x180011678  test    eax, eax
0x18001167a  js      short loc_1800116EF
0x18001167c  cmp     eax, 1
0x18001167f  jz      short loc_1800116FB
0x180011681  test    rdi, rdi
0x180011684  jz      short loc_1800116FB
0x180011686  lea     rdx, [rbp+4Fh+var_78]; struct DnsZtRuleNode **
0x18001168a  mov     rcx, rdi; this
0x18001168d  call    ?CreateCopy@DnsZtRuleNode@@QEAAJPEAPEAV1@@Z; DnsZtRuleNode::CreateCopy(DnsZtRuleNode * *)
0x180011692  mov     r15d, eax
0x180011695  test    eax, eax
0x180011697  jle     short loc_1800116A4
0x180011699  movzx   r15d, ax
0x18001169d  or      r15d, 80070000h
0x1800116a4  mov     rbx, [rbp+4Fh+var_78]
0x1800116a8  test    r15d, r15d
0x1800116ab  js      short loc_1800116E3
0x1800116ad  mov     rdx, rbx
0x1800116b0  mov     rcx, rsi
0x1800116b3  call    ?Insert@?$CWxRefMap@VDnsZtRuleMap@@VDnsZtRuleNode@@@@QEAAJPEAVDnsZtRuleNode@@PEAPEAV2@@Z; CWxRefMap<DnsZtRuleMap,DnsZtRuleNode>::Insert(DnsZtRuleNode *,DnsZtRuleNode * *)
0x1800116b8  mov     r15d, eax
0x1800116bb  test    eax, eax
0x1800116bd  js      short loc_1800116D7
0x1800116bf  test    rbx, rbx
0x1800116c2  jz      short loc_180011653
0x1800116c4  mov     rcx, rbx; this
0x1800116c7  call    ?Release@DnsZtRuleNode@@QEAAKXZ; DnsZtRuleNode::Release(void)
0x1800116cc  xor     ebx, ebx
0x1800116ce  mov     [rbp+4Fh+var_78], rbx
0x1800116d2  jmp     loc_180011653
0x1800116d7  mov     [rbp+4Fh+var_7C], 56h ; 'V'
0x1800116de  jmp     loc_1800117BD
0x1800116e3  mov     [rbp+4Fh+var_7C], 54h ; 'T'
0x1800116ea  jmp     loc_1800117BD
0x1800116ef  mov     [rbp+4Fh+var_7C], 48h ; 'H'
0x1800116f6  jmp     loc_1800117BD
0x1800116fb  xor     r12d, r12d
0x1800116fe  cmp     r12d, [rbp+4Fh+var_6C]
0x180011702  jnb     loc_18001179C
0x180011708  mov     r10, [rbp+4Fh+var_58]
0x18001170c  lea     rax, [rbp+4Fh+var_78]
0x180011710  mov     [rsp+0C0h+var_90], rax; struct DnsZtRuleNode **
0x180011715  lea     rcx, [r12+r12*2]
0x180011719  add     rcx, rcx
0x18001171c  mov     eax, [r10+rcx*8+28h]
0x180011721  mov     r9, [r10+rcx*8+18h]; unsigned __int16 *
0x180011726  mov     r8, [r10+rcx*8+10h]; unsigned __int16 *
0x18001172b  mov     rdx, [r10+rcx*8+8]; unsigned __int64
0x180011730  mov     [rsp+0C0h+var_98], eax; unsigned int
0x180011734  mov     rax, [r10+rcx*8+20h]
0x180011739  mov     ecx, [r10+rcx*8]; unsigned int
0x18001173d  mov     [rsp+0C0h+var_A0], rax; struct _DNS_ZT_SUBNET *
0x180011742  call    ?CreateInstance@DnsZtRuleNode@@SAJK_KQEAG1PEBU_DNS_ZT_SUBNET@@KPEAPEAV1@@Z; DnsZtRuleNode::CreateInstance(ulong,unsigned __int64,ushort * const,ushort * const,_DNS_ZT_SUBNET const *,ulong,DnsZtRuleNode * *)
0x180011747  mov     rbx, [rbp+4Fh+var_78]
0x18001174b  mov     r15d, eax
0x18001174e  test    eax, eax
0x180011750  js      short loc_180011793
0x180011752  mov     rdx, rbx
0x180011755  mov     rcx, rsi
0x180011758  call    ?Delete@?$CWxRefMap@VDnsZtRuleMap@@VDnsZtRuleNode@@@@QEAAJPEAVDnsZtRuleNode@@@Z; CWxRefMap<DnsZtRuleMap,DnsZtRuleNode>::Delete(DnsZtRuleNode *)
0x18001175d  mov     rdx, rbx
0x180011760  mov     rcx, rsi
0x180011763  call    ?Insert@?$CWxRefMap@VDnsZtRuleMap@@VDnsZtRuleNode@@@@QEAAJPEAVDnsZtRuleNode@@PEAPEAV2@@Z; CWxRefMap<DnsZtRuleMap,DnsZtRuleNode>::Insert(DnsZtRuleNode *,DnsZtRuleNode * *)
0x180011768  mov     r15d, eax
0x18001176b  test    eax, eax
0x18001176d  js      short loc_18001178A
0x18001176f  test    rbx, rbx
0x180011772  jz      short loc_180011782
0x180011774  mov     rcx, rbx; this
0x180011777  call    ?Release@DnsZtRuleNode@@QEAAKXZ; DnsZtRuleNode::Release(void)
0x18001177c  xor     ebx, ebx
0x18001177e  mov     [rbp+4Fh+var_78], rbx
0x180011782  inc     r12d
0x180011785  jmp     loc_1800116FE
0x18001178a  mov     [rbp+4Fh+var_7C], 6Ah ; 'j'
0x180011791  jmp     short loc_1800117BD
0x180011793  mov     [rbp+4Fh+var_7C], 67h ; 'g'
0x18001179a  jmp     short loc_1800117BD
0x18001179c  movsxd  rax, [rbp+4Fh+var_70]
0x1800117a0  lea     rcx, ?g_rgspDnsZtRuleMap@@3PAV?$AutoInterface@VDnsZtRuleMap@@@@A; AutoInterface<DnsZtRuleMap> near * g_rgspDnsZtRuleMap
0x1800117a7  mov     r14, [rcx+rax*8]
0x1800117ab  mov     [rcx+rax*8], rsi
0x1800117af  xor     esi, esi
0x1800117b1  test    r13, r13
0x1800117b4  jz      short loc_1800117BD
0x1800117b6  mov     [r13+0], r14
0x1800117ba  xor     r14d, r14d
0x1800117bd  test    byte ptr cs:xmmword_18001F260+1, 8
0x1800117c4  jz      short loc_1800117E7
0x1800117c6  mov     ecx, r15d
0x1800117c9  call    WX_WIN32_FROM_HR
0x1800117ce  mov     r9d, eax
0x1800117d1  lea     r8, WPP_948d2a298210377da68aa16776f92aa2_Traceguids
0x1800117d8  mov     edx, 0Dh
0x1800117dd  mov     ecx, 40Bh
0x1800117e2  call    WPP_SF_d
0x1800117e7  mov     ecx, r15d
0x1800117ea  call    WX_WIN32_FROM_HR
0x1800117ef  mov     rcx, [rbp+4Fh+var_48]; this
0x1800117f3  mov     r15d, eax
0x1800117f6  test    rcx, rcx
0x1800117f9  jz      short loc_180011800
0x1800117fb  call    ?Release@DnsZtRuleMap@@QEAAKXZ; DnsZtRuleMap::Release(void)
0x180011800  test    rdi, rdi
0x180011803  jz      short loc_18001180D
0x180011805  mov     rcx, rdi; this
0x180011808  call    ?Release@DnsZtRuleNode@@QEAAKXZ; DnsZtRuleNode::Release(void)
0x18001180d  test    rbx, rbx
0x180011810  jz      short loc_18001181A
0x180011812  mov     rcx, rbx; this
0x180011815  call    ?Release@DnsZtRuleNode@@QEAAKXZ; DnsZtRuleNode::Release(void)
0x18001181a  test    rsi, rsi
0x18001181d  jz      short loc_180011827
0x18001181f  mov     rcx, rsi; this
0x180011822  call    ?Release@DnsZtRuleMap@@QEAAKXZ; DnsZtRuleMap::Release(void)
0x180011827  test    r14, r14
0x18001182a  jz      short loc_180011834
0x18001182c  mov     rcx, r14; this
0x18001182f  call    ?Release@DnsZtRuleMap@@QEAAKXZ; DnsZtRuleMap::Release(void)
0x180011834  mov     rbx, [rsp+0C0h+arg_8]
0x18001183c  mov     eax, r15d
0x18001183f  add     rsp, 90h
0x180011846  pop     r15
0x180011848  pop     r14
0x18001184a  pop     r13
0x18001184c  pop     r12
0x18001184e  pop     rdi
0x18001184f  pop     rsi
0x180011850  pop     rbp
0x180011851  retn
```
