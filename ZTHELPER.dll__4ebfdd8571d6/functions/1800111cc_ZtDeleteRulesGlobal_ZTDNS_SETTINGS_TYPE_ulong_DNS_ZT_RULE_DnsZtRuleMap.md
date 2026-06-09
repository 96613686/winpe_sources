# ZtDeleteRulesGlobal(_ZTDNS_SETTINGS_TYPE,ulong,_DNS_ZT_RULE *,DnsZtRuleMap * *)

- ea: `0x1800111cc`
- end: `0x180011489`
- name: `?ZtDeleteRulesGlobal@@YAJW4_ZTDNS_SETTINGS_TYPE@@KPEAU_DNS_ZT_RULE@@PEAPEAVDnsZtRuleMap@@@Z`
- size: `701`
- prototype: `__int64 __fastcall(int, unsigned int, __int64, DnsZtRuleMap **)`
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, registry_config`

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
- `0x1800111cc`
- `0x1800126d8`
- `0x180012838`
- `0x180015008`
- `0x1800166c8`

## pseudocode

```c
__int64 __fastcall ZtDeleteRulesGlobal(int a1, unsigned int a2, __int64 a3, DnsZtRuleMap **a4)
{
  DnsZtRuleNode *v4; // rbx
  DnsZtRuleMap *v5; // rsi
  DnsZtRuleMap *v6; // r14
  DnsZtRuleNode *v7; // rdi
  __int64 v8; // r12
  signed int v11; // r15d
  __int64 v12; // r13
  int v13; // eax
  int v14; // eax
  __int64 i; // r12
  int v16; // eax
  unsigned int v17; // eax
  unsigned int v18; // r15d
  DnsZtRuleNode *v20; // [rsp+40h] [rbp-29h] BYREF
  int v21; // [rsp+4Ch] [rbp-1Dh]
  DnsZtRuleNode *v22; // [rsp+50h] [rbp-19h] BYREF
  unsigned int v23; // [rsp+58h] [rbp-11h]
  struct DnsZtRuleMap *v24; // [rsp+60h] [rbp-9h] BYREF
  __int64 v25; // [rsp+68h] [rbp-1h]
  DnsZtRuleMap **v26; // [rsp+70h] [rbp+7h]
  __int64 v27; // [rsp+78h] [rbp+Fh] BYREF
  DnsZtRuleMap *v28[2]; // [rsp+80h] [rbp+17h]

  v4 = 0;
  v26 = a4;
  v5 = 0;
  v25 = a3;
  v6 = 0;
  v23 = a2;
  v7 = 0;
  v8 = a1;
  v22 = 0;
  v21 = 0;
  v24 = 0;
  v20 = 0;
  v27 = 0;
  *(_OWORD *)v28 = 0;
  if ( (BYTE1(xmmword_18001F260) & 8) != 0 )
    WPP_SF_ddq(a1, a2, a3, a1, a2, a3);
  if ( (a2 == 0) == (a3 == 0) )
  {
    if ( (unsigned int)v8 <= 1 )
    {
      v11 = DnsZtRuleMap::CreateInstance(&v24);
      if ( v11 >= 0 )
      {
        v12 = v8;
        CWxRefMap<DnsZtRuleMap,DnsZtRuleNode>::CWxIter::Attach(&v27, g_rgspDnsZtRuleMap[v8]);
        v5 = v24;
        while ( 1 )
        {
          if ( v7 )
          {
            DnsZtRuleNode::Release(v7);
            v22 = 0;
          }
          v13 = CWxRefMap<DnsZtRuleMap,DnsZtRuleNode>::CWxIter::Next(&v27, &v22);
          v7 = v22;
          v11 = v13;
          if ( v13 < 0 )
          {
            v21 = 284;
            goto LABEL_33;
          }
          if ( v13 == 1 || !v22 )
            break;
          v14 = DnsZtRuleNode::CreateCopy(v22, &v20);
          v11 = v14;
          if ( v14 > 0 )
            v11 = (unsigned __int16)v14 | 0x80070000;
          v4 = v20;
          if ( v11 < 0 )
          {
            v21 = 296;
            goto LABEL_33;
          }
          v11 = CWxRefMap<DnsZtRuleMap,DnsZtRuleNode>::Insert(v5, v20);
          if ( v11 < 0 )
          {
            v21 = 298;
            goto LABEL_33;
          }
          if ( v4 )
          {
            DnsZtRuleNode::Release(v4);
            v4 = 0;
            v20 = 0;
          }
        }
        for ( i = 0; (unsigned int)i < v23; i = (unsigned int)(i + 1) )
        {
          v16 = DnsZtRuleNode::CreateInstance(
                  1,
                  0,
                  *(unsigned __int16 *const *)(v25 + 48 * i + 16),
                  (unsigned __int16 *const)&Format,
                  0,
                  0,
                  &v20);
          v4 = v20;
          v11 = v16;
          if ( v16 < 0 )
          {
            v21 = 310;
            goto LABEL_33;
          }
          CWxRefMap<DnsZtRuleMap,DnsZtRuleNode>::Delete((__int64)v5, (__int64)v20);
          if ( v4 )
          {
            DnsZtRuleNode::Release(v4);
            v4 = 0;
            v20 = 0;
          }
        }
        v6 = (DnsZtRuleMap *)g_rgspDnsZtRuleMap[v12];
        g_rgspDnsZtRuleMap[v12] = (__int64)v5;
        v5 = 0;
        if ( v26 )
        {
          *v26 = v6;
          v6 = 0;
        }
      }
      else
      {
        v5 = v24;
        v21 = 277;
      }
    }
    else
    {
      v11 = -2147024809;
      v21 = 275;
    }
  }
  else
  {
    v11 = -2147024809;
    v21 = 273;
  }
LABEL_33:
  if ( (BYTE1(xmmword_18001F260) & 8) != 0 )
  {
    v17 = WX_WIN32_FROM_HR((unsigned int)v11);
    WPP_SF_d(1035, 18, WPP_948d2a298210377da68aa16776f92aa2_Traceguids, v17);
  }
  v18 = WX_WIN32_FROM_HR((unsigned int)v11);
  if ( v28[0] )
    DnsZtRuleMap::Release(v28[0]);
  if ( v7 )
    DnsZtRuleNode::Release(v7);
  if ( v4 )
    DnsZtRuleNode::Release(v4);
  if ( v5 )
    DnsZtRuleMap::Release(v5);
  if ( v6 )
    DnsZtRuleMap::Release(v6);
  return v18;
}

```

## disassembly

```asm
0x1800111cc  mov     [rsp-8+arg_8], rbx
0x1800111d1  push    rbp
0x1800111d2  push    rsi
0x1800111d3  push    rdi
0x1800111d4  push    r12
0x1800111d6  push    r13
0x1800111d8  push    r14
0x1800111da  push    r15
0x1800111dc  lea     rbp, [rsp-27h]
0x1800111e1  sub     rsp, 90h
0x1800111e8  xor     ebx, ebx
0x1800111ea  mov     [rbp+57h+var_50], r9
0x1800111ee  xor     esi, esi
0x1800111f0  mov     [rbp+57h+var_58], r8
0x1800111f4  xor     r14d, r14d
0x1800111f7  mov     [rbp+57h+var_68], edx
0x1800111fa  xor     edi, edi
0x1800111fc  movsxd  r12, ecx
0x1800111ff  xorps   xmm0, xmm0
0x180011202  mov     [rbp+57h+var_70], rdi
0x180011206  mov     r13, r8
0x180011209  mov     [rbp+57h+var_74], 0
0x180011210  mov     r15d, edx
0x180011213  mov     [rbp+57h+var_60], rsi
0x180011217  mov     [rbp+57h+var_80], rbx
0x18001121b  mov     [rbp+57h+var_48], rbx
0x18001121f  movdqu  xmmword ptr [rbp+57h+var_40], xmm0
0x180011224  test    byte ptr cs:xmmword_18001F260+1, 8
0x18001122b  jz      short loc_18001123E
0x18001122d  mov     qword ptr [rsp+0C0h+var_98], r8
0x180011232  mov     r9d, r12d
0x180011235  mov     dword ptr [rsp+0C0h+var_A0], edx
0x180011239  call    WPP_SF_ddq
0x18001123e  xor     ecx, ecx
0x180011240  test    r13, r13
0x180011243  setz    cl
0x180011246  xor     eax, eax
0x180011248  test    r15d, r15d
0x18001124b  setz    al
0x18001124e  cmp     eax, ecx
0x180011250  jz      short loc_180011264
0x180011252  mov     r15d, 80070057h
0x180011258  mov     [rbp+57h+var_74], 111h
0x18001125f  jmp     loc_1800113F4
0x180011264  cmp     r12d, 1
0x180011268  jbe     short loc_18001127C
0x18001126a  mov     r15d, 80070057h
0x180011270  mov     [rbp+57h+var_74], 113h
0x180011277  jmp     loc_1800113F4
0x18001127c  lea     rcx, [rbp+57h+var_60]; struct DnsZtRuleMap **
0x180011280  call    ?CreateInstance@DnsZtRuleMap@@SAJPEAPEAV1@@Z; DnsZtRuleMap::CreateInstance(DnsZtRuleMap * *)
0x180011285  mov     r15d, eax
0x180011288  test    eax, eax
0x18001128a  jns     short loc_18001129C
0x18001128c  mov     rsi, [rbp+57h+var_60]
0x180011290  mov     [rbp+57h+var_74], 115h
0x180011297  jmp     loc_1800113F4
0x18001129c  lea     rax, ?g_rgspDnsZtRuleMap@@3PAV?$AutoInterface@VDnsZtRuleMap@@@@A; AutoInterface<DnsZtRuleMap> near * g_rgspDnsZtRuleMap
0x1800112a3  mov     r13, r12
0x1800112a6  mov     rdx, [rax+r12*8]
0x1800112aa  lea     rcx, [rbp+57h+var_48]
0x1800112ae  call    ?Attach@CWxIter@?$CWxRefMap@VDnsZtRuleMap@@VDnsZtRuleNode@@@@QEAAJPEAVDnsZtRuleMap@@@Z; CWxRefMap<DnsZtRuleMap,DnsZtRuleNode>::CWxIter::Attach(DnsZtRuleMap *)
0x1800112b3  mov     rsi, [rbp+57h+var_60]
0x1800112b7  test    rdi, rdi
0x1800112ba  jz      short loc_1800112C8
0x1800112bc  mov     rcx, rdi; this
0x1800112bf  call    ?Release@DnsZtRuleNode@@QEAAKXZ; DnsZtRuleNode::Release(void)
0x1800112c4  mov     [rbp+57h+var_70], r14
0x1800112c8  lea     rdx, [rbp+57h+var_70]
0x1800112cc  lea     rcx, [rbp+57h+var_48]
0x1800112d0  call    ?Next@CWxIter@?$CWxRefMap@VDnsZtRuleMap@@VDnsZtRuleNode@@@@QEAAJPEAPEAVDnsZtRuleNode@@@Z; CWxRefMap<DnsZtRuleMap,DnsZtRuleNode>::CWxIter::Next(DnsZtRuleNode * *)
0x1800112d5  mov     rdi, [rbp+57h+var_70]
0x1800112d9  mov     r15d, eax
0x1800112dc  test    eax, eax
0x1800112de  js      loc_1800113ED
0x1800112e4  cmp     eax, 1
0x1800112e7  jz      short loc_180011357
0x1800112e9  test    rdi, rdi
0x1800112ec  jz      short loc_180011357
0x1800112ee  lea     rdx, [rbp+57h+var_80]; struct DnsZtRuleNode **
0x1800112f2  mov     rcx, rdi; this
0x1800112f5  call    ?CreateCopy@DnsZtRuleNode@@QEAAJPEAPEAV1@@Z; DnsZtRuleNode::CreateCopy(DnsZtRuleNode * *)
0x1800112fa  mov     r15d, eax
0x1800112fd  test    eax, eax
0x1800112ff  jle     short loc_18001130C
0x180011301  movzx   r15d, ax
0x180011305  or      r15d, 80070000h
0x18001130c  mov     rbx, [rbp+57h+var_80]
0x180011310  test    r15d, r15d
0x180011313  js      short loc_18001134B
0x180011315  mov     rdx, rbx
0x180011318  mov     rcx, rsi
0x18001131b  call    ?Insert@?$CWxRefMap@VDnsZtRuleMap@@VDnsZtRuleNode@@@@QEAAJPEAVDnsZtRuleNode@@PEAPEAV2@@Z; CWxRefMap<DnsZtRuleMap,DnsZtRuleNode>::Insert(DnsZtRuleNode *,DnsZtRuleNode * *)
0x180011320  mov     r15d, eax
0x180011323  test    eax, eax
0x180011325  js      short loc_18001133F
0x180011327  test    rbx, rbx
0x18001132a  jz      short loc_1800112B7
0x18001132c  mov     rcx, rbx; this
0x18001132f  call    ?Release@DnsZtRuleNode@@QEAAKXZ; DnsZtRuleNode::Release(void)
0x180011334  xor     ebx, ebx
0x180011336  mov     [rbp+57h+var_80], rbx
0x18001133a  jmp     loc_1800112B7
0x18001133f  mov     [rbp+57h+var_74], 12Ah
0x180011346  jmp     loc_1800113F4
0x18001134b  mov     [rbp+57h+var_74], 128h
0x180011352  jmp     loc_1800113F4
0x180011357  xor     r12d, r12d
0x18001135a  cmp     r12d, [rbp+57h+var_68]
0x18001135e  jnb     short loc_1800113CB
0x180011360  lea     rax, [rbp+57h+var_80]
0x180011364  xor     edx, edx; unsigned __int64
0x180011366  mov     [rsp+0C0h+var_90], rax; struct DnsZtRuleNode **
0x18001136b  lea     r8, [r12+r12*2]
0x18001136f  mov     rax, [rbp+57h+var_58]
0x180011373  lea     r9, Format; unsigned __int16 *
0x18001137a  add     r8, r8
0x18001137d  mov     [rsp+0C0h+var_98], r14d; unsigned int
0x180011382  lea     ecx, [rdx+1]; unsigned int
0x180011385  mov     [rsp+0C0h+var_A0], r14; struct _DNS_ZT_SUBNET *
0x18001138a  mov     r8, [rax+r8*8+10h]; unsigned __int16 *
0x18001138f  call    ?CreateInstance@DnsZtRuleNode@@SAJK_KQEAG1PEBU_DNS_ZT_SUBNET@@KPEAPEAV1@@Z; DnsZtRuleNode::CreateInstance(ulong,unsigned __int64,ushort * const,ushort * const,_DNS_ZT_SUBNET const *,ulong,DnsZtRuleNode * *)
0x180011394  mov     rbx, [rbp+57h+var_80]
0x180011398  mov     r15d, eax
0x18001139b  test    eax, eax
0x18001139d  js      short loc_1800113C2
0x18001139f  mov     rdx, rbx
0x1800113a2  mov     rcx, rsi
0x1800113a5  call    ?Delete@?$CWxRefMap@VDnsZtRuleMap@@VDnsZtRuleNode@@@@QEAAJPEAVDnsZtRuleNode@@@Z; CWxRefMap<DnsZtRuleMap,DnsZtRuleNode>::Delete(DnsZtRuleNode *)
0x1800113aa  test    rbx, rbx
0x1800113ad  jz      short loc_1800113BD
0x1800113af  mov     rcx, rbx; this
0x1800113b2  call    ?Release@DnsZtRuleNode@@QEAAKXZ; DnsZtRuleNode::Release(void)
0x1800113b7  xor     ebx, ebx
0x1800113b9  mov     [rbp+57h+var_80], rbx
0x1800113bd  inc     r12d
0x1800113c0  jmp     short loc_18001135A
0x1800113c2  mov     [rbp+57h+var_74], 136h
0x1800113c9  jmp     short loc_1800113F4
0x1800113cb  lea     rax, ?g_rgspDnsZtRuleMap@@3PAV?$AutoInterface@VDnsZtRuleMap@@@@A; AutoInterface<DnsZtRuleMap> near * g_rgspDnsZtRuleMap
0x1800113d2  mov     r14, [rax+r13*8]
0x1800113d6  mov     [rax+r13*8], rsi
0x1800113da  xor     esi, esi
0x1800113dc  mov     rax, [rbp+57h+var_50]
0x1800113e0  test    rax, rax
0x1800113e3  jz      short loc_1800113F4
0x1800113e5  mov     [rax], r14
0x1800113e8  xor     r14d, r14d
0x1800113eb  jmp     short loc_1800113F4
0x1800113ed  mov     [rbp+57h+var_74], 11Ch
0x1800113f4  test    byte ptr cs:xmmword_18001F260+1, 8
0x1800113fb  jz      short loc_18001141E
0x1800113fd  mov     ecx, r15d
0x180011400  call    WX_WIN32_FROM_HR
0x180011405  mov     r9d, eax
0x180011408  lea     r8, WPP_948d2a298210377da68aa16776f92aa2_Traceguids
0x18001140f  mov     edx, 12h
0x180011414  mov     ecx, 40Bh
0x180011419  call    WPP_SF_d
0x18001141e  mov     ecx, r15d
0x180011421  call    WX_WIN32_FROM_HR
0x180011426  mov     rcx, [rbp+57h+var_40]; this
0x18001142a  mov     r15d, eax
0x18001142d  test    rcx, rcx
0x180011430  jz      short loc_180011437
0x180011432  call    ?Release@DnsZtRuleMap@@QEAAKXZ; DnsZtRuleMap::Release(void)
0x180011437  test    rdi, rdi
0x18001143a  jz      short loc_180011444
0x18001143c  mov     rcx, rdi; this
0x18001143f  call    ?Release@DnsZtRuleNode@@QEAAKXZ; DnsZtRuleNode::Release(void)
0x180011444  test    rbx, rbx
0x180011447  jz      short loc_180011451
0x180011449  mov     rcx, rbx; this
0x18001144c  call    ?Release@DnsZtRuleNode@@QEAAKXZ; DnsZtRuleNode::Release(void)
0x180011451  test    rsi, rsi
0x180011454  jz      short loc_18001145E
0x180011456  mov     rcx, rsi; this
0x180011459  call    ?Release@DnsZtRuleMap@@QEAAKXZ; DnsZtRuleMap::Release(void)
0x18001145e  test    r14, r14
0x180011461  jz      short loc_18001146B
0x180011463  mov     rcx, r14; this
0x180011466  call    ?Release@DnsZtRuleMap@@QEAAKXZ; DnsZtRuleMap::Release(void)
0x18001146b  mov     rbx, [rsp+0C0h+arg_8]
0x180011473  mov     eax, r15d
0x180011476  add     rsp, 90h
0x18001147d  pop     r15
0x18001147f  pop     r14
0x180011481  pop     r13
0x180011483  pop     r12
0x180011485  pop     rdi
0x180011486  pop     rsi
0x180011487  pop     rbp
0x180011488  retn
```
