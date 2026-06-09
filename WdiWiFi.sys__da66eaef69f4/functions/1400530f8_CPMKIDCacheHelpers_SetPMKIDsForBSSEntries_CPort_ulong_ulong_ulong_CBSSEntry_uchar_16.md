# CPMKIDCacheHelpers::SetPMKIDsForBSSEntries(CPort *,ulong,ulong,ulong *,CBSSEntry * *,uchar (* *)[16])

- ea: `0x1400530f8`
- end: `0x140053604`
- name: `?SetPMKIDsForBSSEntries@CPMKIDCacheHelpers@@SAHPEAVCPort@@KKPEAKPEAPEAVCBSSEntry@@PEAPEAY0BA@E@Z`
- size: `1292`
- prototype: `__int64 __fastcall(struct CPort *, unsigned int, unsigned int, unsigned int *, struct CBSSEntry **, unsigned __int8 (**)[16])`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x140052bcc`

## callees

- `0x1400109f8`
- `0x140012214`
- `0x140013000`
- `0x140034e04`
- `0x140034ec4`
- `0x1400530f8`
- `0x14005360c`
- `0x1400707e8`
- `0x1400da680`

## import_xrefs

- `ntoskrnl!RtlCompareMemory` at `0x14005322f`
- `ntoskrnl!RtlCompareMemory` at `0x14005322f`

## pseudocode

```c
__int64 __fastcall CPMKIDCacheHelpers::SetPMKIDsForBSSEntries(
        struct CPort *a1,
        unsigned int a2,
        int a3,
        unsigned int *a4,
        struct CBSSEntry **a5,
        unsigned __int8 (**a6)[16])
{
  unsigned __int16 v6; // bp
  struct CPort *v8; // rax
  unsigned int v9; // ebx
  int v10; // edx
  __int64 v11; // r8
  unsigned int PropertyBuffer; // r15d
  unsigned __int8 *v13; // rsi
  int v14; // edx
  __int64 v15; // rax
  unsigned int j; // edi
  __int64 v17; // r14
  __int64 v18; // r12
  unsigned __int8 (**v19)[16]; // r12
  char v20; // r14
  char v21; // r13
  unsigned __int8 PropertyBooleanOrDefault; // al
  int v23; // edx
  int v24; // r8d
  char v25; // r12
  struct CBSSEntry **v27; // rbp
  unsigned int v28; // eax
  struct CBSSEntry *v29; // r10
  __int64 v30; // r9
  unsigned __int8 *v31; // r11
  unsigned int v32; // ebp
  unsigned __int16 v33; // di
  unsigned __int8 (**v34)[16]; // r15
  struct CBSSEntry **v35; // r12
  __int64 v36; // r14
  __int64 v37; // rax
  __int64 v38; // [rsp+28h] [rbp-90h]
  char i; // [rsp+50h] [rbp-68h]
  char v40; // [rsp+54h] [rbp-64h]
  unsigned __int8 *v41; // [rsp+60h] [rbp-58h] BYREF
  unsigned int v43; // [rsp+C8h] [rbp+10h]
  unsigned int v44; // [rsp+D0h] [rbp+18h] BYREF
  unsigned int *v45; // [rsp+D8h] [rbp+20h]

  v45 = a4;
  v43 = a2;
  v6 = 0;
  v41 = 0;
  v44 = 0;
  v8 = a1;
  if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    LOBYTE(a2) = 5;
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      a2,
      1,
      45,
      (__int64)WPP_4ce070d3319431f0750a2f0fcbe8aee5_Traceguids);
    v8 = a1;
  }
  if ( a4 )
  {
    v9 = *a4;
    if ( v9 && v9 <= 0x28 )
    {
      PropertyBuffer = CPropertyCache::GetPropertyBuffer(&v8->m_PortPropertyCache, 0x2Bu, &v44, &v41);
      if ( PropertyBuffer || v44 < 0xC )
      {
        if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED )
          return PropertyBuffer;
        LOBYTE(v10) = 2;
        WPP_RECORDER_SF_D(
          WPP_GLOBAL_Control->DeviceExtension,
          v10,
          1,
          47,
          (__int64)WPP_4ce070d3319431f0750a2f0fcbe8aee5_Traceguids,
          PropertyBuffer);
      }
      else
      {
        v13 = v41;
        v40 = 0;
        v14 = 0;
        for ( i = 0; (unsigned int)(unsigned __int16)v14 < *((_DWORD *)v13 + 1); *(_DWORD *)&v13[28 * v15 + 36] = 0 )
        {
          v15 = (unsigned __int16)v14;
          LOWORD(v14) = v14 + 1;
        }
        v44 = v9;
        for ( j = 0; j < v9; ++j )
        {
          v17 = j;
          while ( (unsigned int)v6 < *((_DWORD *)v13 + 1) )
          {
            v17 = j;
            v18 = 28LL * v6;
            if ( RtlCompareMemory(a5[v17]->m_BssID, &v13[v18 + 12], 6u) == 6 )
            {
              ++v40;
              a6[v17] = (unsigned __int8 (*)[16])&v13[v18 + 18];
              *(_DWORD *)&v13[v18 + 36] = 1;
              break;
            }
            ++v6;
          }
          v19 = a6;
          v6 = 0;
          if ( !a6[v17] && v43 )
          {
            if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED
              || BYTE1(WPP_GLOBAL_Control->Timer) < 5u && !LOWORD(WPP_GLOBAL_Control->DeviceType) )
            {
              v27 = a5;
            }
            else
            {
              v27 = a5;
              LOBYTE(v14) = 5;
              WPP_RECORDER_SF_d_MAC_(
                WPP_GLOBAL_Control->DeviceExtension,
                v14,
                v11,
                48,
                (__int64)WPP_4ce070d3319431f0750a2f0fcbe8aee5_Traceguids,
                j,
                (__int64)a5[v17]->m_BssID);
            }
            v28 = j;
            v29 = v27[v17];
            v30 = v44 - 1;
            v31 = (unsigned __int8 *)v19[v17];
            if ( j < (unsigned int)v30 )
            {
              do
              {
                v11 = v28 + 1;
                v27[v28] = v27[v11];
                v19[v28++] = v19[v11];
              }
              while ( (unsigned int)v11 < (unsigned int)v30 );
            }
            v27[v30] = v29;
            --v9;
            v19[v30] = (unsigned __int8 (*)[16])v31;
            --j;
            v6 = 0;
          }
        }
        PropertyBuffer = 0;
        v20 = v43;
        v21 = 0;
        PropertyBooleanOrDefault = CPropertyCache::GetPropertyBooleanOrDefault(&a1->m_PortPropertyCache, 0x2Eu, 0);
        LOBYTE(v44) = PropertyBooleanOrDefault;
        v25 = PropertyBooleanOrDefault;
        if ( v43 && !PropertyBooleanOrDefault && v9 < 0x28 )
        {
          v32 = v43;
          if ( *((_DWORD *)v13 + 1) < v43 )
            v32 = *((_DWORD *)v13 + 1);
          v33 = 0;
          if ( v32 )
          {
            v34 = a6;
            v35 = a5;
            do
            {
              v36 = 28LL * v33;
              if ( !*(_DWORD *)&v13[v36 + 36] )
              {
                v37 = a1->m_pAdapter->m_ExtStaBSSList.FindBSSEntry(
                        &a1->m_pAdapter->m_ExtStaBSSList,
                        (const unsigned __int8 (*)[6])&v13[v36 + 12]);
                if ( !v37 || *(_BYTE *)(v37 + 787) )
                {
                  v21 = i;
                }
                else
                {
                  v35[v9] = (struct CBSSEntry *)v37;
                  v34[v9++] = (unsigned __int8 (*)[16])&v13[v36 + 18];
                  *(_DWORD *)&v13[v36 + 36] = 1;
                  v21 = ++i;
                  if ( v9 >= 0x28 )
                    break;
                }
              }
              ++v33;
            }
            while ( v33 < v32 );
            PropertyBuffer = 0;
            v25 = v44;
            v20 = v43;
          }
        }
        if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(v23) = 4;
          WPP_RECORDER_SF_ddddd(
            WPP_GLOBAL_Control->DeviceExtension,
            v23,
            v24,
            49,
            (__int64)WPP_4ce070d3319431f0750a2f0fcbe8aee5_Traceguids,
            v20,
            v9,
            v40,
            v21,
            v25);
        }
        if ( v9 )
          *v45 = v9;
      }
      goto LABEL_22;
    }
  }
  else
  {
    LOBYTE(v9) = 0;
  }
  PropertyBuffer = 0;
  if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED )
    return PropertyBuffer;
  LOBYTE(a2) = 2;
  WPP_RECORDER_SF_Ld(
    WPP_GLOBAL_Control->DeviceExtension,
    a2,
    a3,
    46,
    (__int64)WPP_4ce070d3319431f0750a2f0fcbe8aee5_Traceguids,
    v9,
    40);
LABEL_22:
  if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    LODWORD(v38) = PropertyBuffer;
    LOBYTE(v23) = 5;
    WPP_RECORDER_SF_D(
      WPP_GLOBAL_Control->DeviceExtension,
      v23,
      1,
      50,
      (__int64)WPP_4ce070d3319431f0750a2f0fcbe8aee5_Traceguids,
      v38);
  }
  return PropertyBuffer;
}

```

## disassembly

```asm
0x1400530f8  mov     r11, rsp
0x1400530fb  mov     [r11+20h], r9
0x1400530ff  mov     [r11+18h], r8d
0x140053103  mov     [rsp+arg_8], edx
0x140053107  mov     [r11+8], rcx
0x14005310b  push    rbx
0x14005310c  push    rbp
0x14005310d  push    rsi
0x14005310e  push    rdi
0x14005310f  push    r12
0x140053111  push    r13
0x140053113  push    r14
0x140053115  push    r15
0x140053117  sub     rsp, 78h
0x14005311b  xor     ebp, ebp
0x14005311d  mov     rbx, r9
0x140053120  mov     [r11-58h], rbp
0x140053124  mov     r14d, edx
0x140053127  mov     [r11+18h], ebp
0x14005312b  mov     rax, rcx
0x14005312e  lea     rcx, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140053135  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x14005313c  lea     rsi, WPP_4ce070d3319431f0750a2f0fcbe8aee5_Traceguids
0x140053143  lea     edi, [rbp+1]
0x140053146  jnz     loc_14005336D
0x14005314c  test    rbx, rbx
0x14005314f  jz      loc_140053394
0x140053155  mov     ebx, [rbx]
0x140053157  test    ebx, ebx
0x140053159  jz      loc_140053396
0x14005315f  cmp     ebx, 28h ; '('
0x140053162  ja      loc_140053396
0x140053168  lea     rcx, [rax+3A8h]; this
0x14005316f  mov     edx, 2Bh ; '+'; unsigned int
0x140053174  lea     r9, [rsp+0B8h+var_58]; unsigned __int8 **
0x140053179  lea     r8, [rsp+0B8h+arg_10]; unsigned int *
0x140053181  call    ?GetPropertyBuffer@CPropertyCache@@QEAAHKPEAKPEAPEAE@Z; CPropertyCache::GetPropertyBuffer(ulong,ulong *,uchar * *)
0x140053186  mov     [rsp+0B8h+var_60], eax
0x14005318a  mov     r15d, eax
0x14005318d  test    eax, eax
0x14005318f  jnz     loc_1400533D0
0x140053195  cmp     [rsp+0B8h+arg_10], 0Ch
0x14005319d  jb      loc_1400533D0
0x1400531a3  mov     rsi, [rsp+0B8h+var_58]
0x1400531a8  mov     r13d, ebp
0x1400531ab  mov     [rsp+0B8h+var_64], ebp
0x1400531af  mov     edx, ebp
0x1400531b1  mov     [rsp+0B8h+var_68], ebp
0x1400531b5  cmp     [rsi+4], ebp
0x1400531b8  jbe     short loc_1400531D0
0x1400531ba  movzx   eax, dx
0x1400531bd  add     dx, di
0x1400531c0  imul    rcx, rax, 1Ch
0x1400531c4  movzx   eax, dx
0x1400531c7  mov     [rcx+rsi+24h], ebp
0x1400531cb  cmp     eax, [rsi+4]
0x1400531ce  jb      short loc_1400531BA
0x1400531d0  mov     [rsp+0B8h+arg_10], ebx
0x1400531d7  mov     edi, ebp
0x1400531d9  test    ebx, ebx
0x1400531db  jz      loc_14005329A
0x1400531e1  mov     r15d, [rsp+0B8h+arg_8]
0x1400531e9  mov     r13d, edi
0x1400531ec  lea     r14, ds:0[r13*8]
0x1400531f4  movzx   eax, bp
0x1400531f7  cmp     eax, [rsi+4]
0x1400531fa  jnb     loc_140053434
0x140053200  movzx   eax, bp
0x140053203  lea     r14, ds:0[r13*8]
0x14005320b  imul    r12, rax, 1Ch
0x14005320f  mov     rax, [rsp+0B8h+arg_20]
0x140053217  lea     rdx, [rsi+0Ch]
0x14005321b  add     rdx, r12; Source2
0x14005321e  mov     r8d, 6; Length
0x140053224  mov     rcx, [r14+rax]
0x140053228  add     rcx, 1BCh; Source1
0x14005322f  call    cs:__imp_RtlCompareMemory
0x140053236  nop     dword ptr [rax+rax+00h]
0x14005323b  cmp     rax, 6
0x14005323f  jz      short loc_140053246
0x140053241  inc     bp
0x140053244  jmp     short loc_1400531F4
0x140053246  mov     rcx, [rsp+0B8h+arg_28]
0x14005324e  lea     rax, [rsi+12h]
0x140053252  add     rax, r12
0x140053255  mov     r13d, 1
0x14005325b  add     [rsp+0B8h+var_64], r13d
0x140053260  mov     [r14+rcx], rax
0x140053264  mov     [r12+rsi+24h], r13d
0x140053269  mov     r12, [rsp+0B8h+arg_28]
0x140053271  xor     ebp, ebp
0x140053273  cmp     [r14+r12], rbp
0x140053277  jz      loc_14005343F
0x14005327d  add     edi, r13d
0x140053280  cmp     edi, ebx
0x140053282  jb      loc_1400531E9
0x140053288  mov     r15d, [rsp+0B8h+var_60]
0x14005328d  mov     r14d, [rsp+0B8h+arg_8]
0x140053295  mov     r13d, [rsp+0B8h+var_68]
0x14005329a  mov     rcx, [rsp+0B8h+arg_0]
0x1400532a2  xor     r8d, r8d; unsigned __int8
0x1400532a5  add     rcx, 3A8h; this
0x1400532ac  lea     edx, [r8+2Eh]; unsigned int
0x1400532b0  call    ?GetPropertyBooleanOrDefault@CPropertyCache@@QEAAEKE@Z; CPropertyCache::GetPropertyBooleanOrDefault(ulong,uchar)
0x1400532b5  mov     byte ptr [rsp+0B8h+arg_10], al
0x1400532bc  mov     r12b, al
0x1400532bf  test    r14d, r14d
0x1400532c2  jnz     loc_1400534FE
0x1400532c8  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x1400532cf  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400532d6  lea     rsi, WPP_4ce070d3319431f0750a2f0fcbe8aee5_Traceguids
0x1400532dd  jz      short loc_14005331A
0x1400532df  mov     rcx, cs:WPP_GLOBAL_Control
0x1400532e6  mov     r9d, 31h ; '1'
0x1400532ec  movzx   eax, r12b
0x1400532f0  mov     dl, 4
0x1400532f2  mov     [rsp+0B8h+var_70], eax
0x1400532f6  mov     eax, [rsp+0B8h+var_64]
0x1400532fa  mov     rcx, [rcx+40h]
0x1400532fe  mov     [rsp+0B8h+var_78], r13d
0x140053303  mov     [rsp+0B8h+var_80], eax
0x140053307  mov     dword ptr [rsp+0B8h+var_88], ebx
0x14005330b  mov     dword ptr [rsp+0B8h+var_90], r14d
0x140053310  mov     [rsp+0B8h+var_98], rsi
0x140053315  call    WPP_RECORDER_SF_ddddd
0x14005331a  mov     edi, 1
0x14005331f  test    ebx, ebx
0x140053321  jz      short loc_14005332D
0x140053323  mov     rax, [rsp+0B8h+arg_18]
0x14005332b  mov     [rax], ebx
0x14005332d  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140053334  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14005333b  jz      short loc_140053358
0x14005333d  mov     rcx, cs:WPP_GLOBAL_Control
0x140053344  cmp     byte ptr [rcx+29h], 5
0x140053348  jnb     loc_1400535E1
0x14005334e  cmp     [rcx+48h], bp
0x140053352  jnz     loc_1400535E1
0x140053358  mov     eax, r15d
0x14005335b  add     rsp, 78h
0x14005335f  pop     r15
0x140053361  pop     r14
0x140053363  pop     r13
0x140053365  pop     r12
0x140053367  pop     rdi
0x140053368  pop     rsi
0x140053369  pop     rbp
0x14005336a  pop     rbx
0x14005336b  retn
0x14005336d  mov     rcx, cs:WPP_GLOBAL_Control
0x140053374  cmp     byte ptr [rcx+29h], 5
0x140053378  jnb     loc_14005340E
0x14005337e  cmp     [rcx+48h], bp
0x140053382  jnz     loc_14005340E
0x140053388  lea     rcx, WPP_RECORDER_INITIALIZED
0x14005338f  jmp     loc_14005314C
0x140053394  mov     ebx, ebp
0x140053396  cmp     cs:WPP_RECORDER_INITIALIZED, rcx; __annotation("TMF:",
0x14005339d  mov     r15d, ebp
0x1400533a0  jz      short loc_140053358
0x1400533a2  mov     rcx, cs:WPP_GLOBAL_Control
0x1400533a9  mov     r9d, 2Eh ; '.'
0x1400533af  mov     dword ptr [rsp+0B8h+var_88], 28h ; '('
0x1400533b7  mov     dl, 2
0x1400533b9  mov     dword ptr [rsp+0B8h+var_90], ebx
0x1400533bd  mov     [rsp+0B8h+var_98], rsi
0x1400533c2  mov     rcx, [rcx+40h]
0x1400533c6  call    WPP_RECORDER_SF_Ld
0x1400533cb  jmp     loc_14005332D
0x1400533d0  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x1400533d7  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400533de  jz      loc_140053358
0x1400533e4  mov     rcx, cs:WPP_GLOBAL_Control
0x1400533eb  mov     r9d, 2Fh ; '/'
0x1400533f1  mov     dword ptr [rsp+0B8h+var_90], r15d
0x1400533f6  mov     r8d, edi
0x1400533f9  mov     dl, 2
0x1400533fb  mov     [rsp+0B8h+var_98], rsi
0x140053400  mov     rcx, [rcx+40h]
0x140053404  call    WPP_RECORDER_SF_D
0x140053409  jmp     loc_14005332D
0x14005340e  mov     rcx, [rcx+40h]
0x140053412  mov     r9d, 2Dh ; '-'
0x140053418  mov     r8d, edi
0x14005341b  mov     [rsp+0B8h+var_98], rsi
0x140053420  mov     dl, 5
0x140053422  call    WPP_RECORDER_SF_
0x140053427  mov     rax, [rsp+0B8h+arg_0]
0x14005342f  jmp     loc_140053388
0x140053434  mov     r13d, 1
0x14005343a  jmp     loc_140053269
0x14005343f  test    r15d, r15d
0x140053442  jz      loc_14005327D
0x140053448  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14005344f  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140053456  jz      short loc_1400534A5
0x140053458  mov     rcx, cs:WPP_GLOBAL_Control
0x14005345f  cmp     byte ptr [rcx+29h], 5
0x140053463  jnb     short loc_14005346B
0x140053465  cmp     [rcx+48h], bp
0x140053469  jz      short loc_1400534A5
0x14005346b  mov     rbp, [rsp+0B8h+arg_20]
0x140053473  mov     r9d, 30h ; '0'
0x140053479  mov     rcx, [rcx+40h]
0x14005347d  mov     dl, 5
0x14005347f  mov     rax, [r14+rbp]
0x140053483  add     rax, 1BCh
0x140053489  mov     [rsp+0B8h+var_88], rax
0x14005348e  lea     rax, WPP_4ce070d3319431f0750a2f0fcbe8aee5_Traceguids
0x140053495  mov     dword ptr [rsp+0B8h+var_90], edi
0x140053499  mov     [rsp+0B8h+var_98], rax
0x14005349e  call    WPP_RECORDER_SF_d_MAC_
0x1400534a3  jmp     short loc_1400534AD
0x1400534a5  mov     rbp, [rsp+0B8h+arg_20]
0x1400534ad  mov     r9d, [rsp+0B8h+arg_10]
0x1400534b5  mov     eax, edi
0x1400534b7  mov     r10, [r14+rbp]
0x1400534bb  dec     r9d
0x1400534be  mov     r11, [r14+r12]
0x1400534c2  cmp     edi, r9d
0x1400534c5  jnb     short loc_1400534E7
0x1400534c7  mov     ecx, eax
0x1400534c9  lea     r8d, [rax+1]
0x1400534cd  mov     rax, [rbp+r8*8+0]
0x1400534d2  mov     [rbp+rcx*8+0], rax
0x1400534d7  mov     rax, [r12+r8*8]
0x1400534db  mov     [r12+rcx*8], rax
0x1400534df  mov     eax, r8d
0x1400534e2  cmp     r8d, r9d
0x1400534e5  jb      short loc_1400534C7
0x1400534e7  or      eax, 0FFFFFFFFh
0x1400534ea  mov     [rbp+r9*8+0], r10
0x1400534ef  add     ebx, eax
0x1400534f1  mov     [r12+r9*8], r11
0x1400534f5  add     edi, eax
0x1400534f7  xor     ebp, ebp
0x1400534f9  jmp     loc_14005327D
0x1400534fe  test    al, al
0x140053500  jnz     loc_1400532C8
0x140053506  cmp     ebx, 28h ; '('
0x140053509  jnb     loc_1400532C8
0x14005350f  mov     ecx, [rsi+4]
0x140053512  mov     ebp, r14d
0x140053515  cmp     ecx, r14d
0x140053518  cmovb   ebp, ecx
0x14005351b  xor     edi, edi
0x14005351d  test    ebp, ebp
0x14005351f  jz      loc_1400535DA
0x140053525  mov     r15, [rsp+0B8h+arg_28]
0x14005352d  mov     r12, [rsp+0B8h+arg_20]
0x140053535  movzx   eax, di
0x140053538  imul    r14, rax, 1Ch
0x14005353c  cmp     dword ptr [r14+rsi+24h], 0
0x140053542  jnz     short loc_1400535B2
0x140053544  mov     rax, [rsp+0B8h+arg_0]
0x14005354c  lea     r13, [r14+rsi]
0x140053550  lea     rdx, [r13+0Ch]
0x140053554  mov     rcx, [rax+58h]
0x140053558  add     rcx, 568h
0x14005355f  mov     rax, [rcx]
0x140053562  mov     rax, [rax]
0x140053565  call    _guard_dispatch_icall
0x14005356a  test    rax, rax
0x14005356d  jz      short loc_1400535AD
0x14005356f  cmp     byte ptr [rax+313h], 0
0x140053576  jnz     short loc_1400535AD
0x140053578  mov     ecx, ebx
0x14005357a  mov     [r12+rcx*8], rax
0x14005357e  lea     rax, [r13+12h]
0x140053582  mov     r13d, 1
0x140053588  mov     [r15+rcx*8], rax
0x14005358c  add     ebx, r13d
0x14005358f  mov     [r14+rsi+24h], r13d
0x140053594  mov     r13d, [rsp+0B8h+var_68]
0x140053599  mov     eax, 1
0x14005359e  add     r13d, eax
0x1400535a1  mov     [rsp+0B8h+var_68], r13d
0x1400535a6  cmp     ebx, 28h ; '('
0x1400535a9  jb      short loc_1400535B7
0x1400535ab  jmp     short loc_1400535C5
0x1400535ad  mov     r13d, [rsp+0B8h+var_68]
0x1400535b2  mov     eax, 1
0x1400535b7  add     di, ax
0x1400535ba  movzx   eax, di
0x1400535bd  cmp     eax, ebp
0x1400535bf  jb      loc_140053535
0x1400535c5  mov     r15d, [rsp+0B8h+var_60]
0x1400535ca  mov     r12b, byte ptr [rsp+0B8h+arg_10]
0x1400535d2  mov     r14d, [rsp+0B8h+arg_8]
0x1400535da  xor     ebp, ebp
0x1400535dc  jmp     loc_1400532C8
0x1400535e1  mov     rcx, [rcx+40h]
0x1400535e5  mov     r9d, 32h ; '2'
0x1400535eb  mov     dword ptr [rsp+0B8h+var_90], r15d
0x1400535f0  mov     r8d, edi
0x1400535f3  mov     dl, 5
0x1400535f5  mov     [rsp+0B8h+var_98], rsi
0x1400535fa  call    WPP_RECORDER_SF_D
0x1400535ff  jmp     loc_140053358
```
