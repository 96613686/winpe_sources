# CContainerProps::RebuildBloomFilter(void)

- ea: `0x18007fdc4`
- end: `0x18008058c`
- name: `?RebuildBloomFilter@CContainerProps@@QEAAJXZ`
- size: `1992`
- prototype: `__int64 __fastcall(CContainerProps *__hidden this)`
- caller_count: `1`
- callee_count: `18`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180122370`

## callees

- `0x180021360`
- `0x180025910`
- `0x18007ec9c`
- `0x18007fdc4`
- `0x180081d90`
- `0x180083d00`
- `0x180083dc4`
- `0x18014a7a0`
- `0x180154882`
- `0x1801abdac`
- `0x1801e0700`
- `0x1801e0ff0`
- `0x1801e1790`
- `0x1801e1b00`
- `0x1801e28b0`
- `0x1801e3c78`
- `0x1801e490c`
- `0x1801ee010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007fe9e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007ff82`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007ffdb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180080358`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007fe9e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007ff82`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007ffdb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180080358`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18007fe5c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18007ffc1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800802a6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18007fe5c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18007ffc1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800802a6`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800800d8`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800800d8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18008013c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18008013c`
- `ESENT!JetRetrieveColumn` at `0x18008018c`
- `ESENT!JetRetrieveColumn` at `0x18008018c`
- `ESENT!JetRollback` at `0x1800804fb`
- `ESENT!JetRollback` at `0x1800804fb`
- `ESENT!JetBeginTransaction` at `0x18007feea`
- `ESENT!JetBeginTransaction` at `0x18007feea`
- `ESENT!JetMove` at `0x18007fffa`
- `ESENT!JetMove` at `0x18007fffa`

## pseudocode

```c
__int64 __fastcall CContainerProps::RebuildBloomFilter(CContainerProps *this)
{
  struct _RTL_CRITICAL_SECTION *v1; // rsi
  int v2; // r12d
  CContainerProps *v3; // r14
  char *v4; // rdi
  __int64 *v5; // rbx
  unsigned __int8 *v6; // r15
  unsigned int v7; // eax
  int v8; // eax
  unsigned int v9; // r9d
  JET_SESID *v10; // r13
  int v11; // ebx
  JET_ERR v12; // eax
  CBloomFilterPartition **v13; // r12
  int i; // esi
  struct _RTL_CRITICAL_SECTION *v16; // rbx
  int v17; // eax
  int v18; // edi
  JET_ERR v19; // eax
  int v20; // edx
  int v21; // r8d
  JET_SESID v22; // rax
  JET_TABLEID v23; // r12
  JET_SESID v24; // r13
  JET_COLUMNID v25; // r15d
  unsigned int v26; // ecx
  int v27; // eax
  unsigned int v28; // edx
  unsigned int v29; // esi
  __int64 v30; // rcx
  _WORD *v31; // rax
  _WORD *v32; // rbx
  WCHAR *v33; // rdi
  JET_ERR v34; // r8d
  __int64 v35; // rax
  __int64 v36; // rax
  _WORD *v37; // rbx
  __int64 v38; // r14
  _WORD *v39; // r8
  unsigned int v40; // esi
  int v41; // edx
  unsigned __int16 v42; // ax
  unsigned int v43; // edi
  unsigned __int16 *v44; // rcx
  unsigned int v45; // r11d
  unsigned int v46; // r10d
  unsigned int v47; // r9d
  unsigned int v48; // ebx
  unsigned int j; // edi
  unsigned int v50; // eax
  unsigned int v51; // ebx
  __int64 v52; // r15
  unsigned int v53; // r10d
  unsigned int v54; // r9d
  unsigned int v55; // r11d
  int k; // edi
  unsigned int v57; // eax
  __int64 v58; // rax
  int v59; // [rsp+40h] [rbp-49h]
  unsigned int v60; // [rsp+48h] [rbp-41h]
  struct CJetContext *v61; // [rsp+50h] [rbp-39h] BYREF
  int v62; // [rsp+58h] [rbp-31h]
  unsigned __int8 *v63; // [rsp+60h] [rbp-29h]
  int v64; // [rsp+6Ch] [rbp-1Dh]
  unsigned __int8 *v65; // [rsp+70h] [rbp-19h] BYREF
  CContainerProps *v66; // [rsp+78h] [rbp-11h]
  unsigned int pcbActual; // [rsp+80h] [rbp-9h] BYREF
  void *Src; // [rsp+88h] [rbp-1h] BYREF
  __int64 v69; // [rsp+90h] [rbp+7h]

  v66 = this;
  Src = (void *)&Data;
  v1 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 32);
  v69 = 0;
  v2 = 0;
  v61 = 0;
  v3 = this;
  v59 = 0;
  v4 = (char *)this + 208;
  v5 = (__int64 *)((char *)this + 200);
  if ( (BYTE1(xmmword_180266B60) & 0x10) != 0 )
    WPP_SF_qqD(1036, 35, (unsigned int)&WPP_4b302e6b786c3b7f389fd4681ef43772_Traceguids, (_DWORD)this, *v5);
  if ( v1 )
  {
    EnterCriticalSection(v1);
    v2 = 1;
    v59 = 1;
  }
  v6 = (unsigned __int8 *)*v5;
  v63 = v6;
  if ( v6 )
  {
    v7 = *(_DWORD *)v4;
    *(_DWORD *)v4 = 0;
    LODWORD(v4) = 0;
    v62 = 0;
    v65 = v6;
    *v5 = 0;
    v60 = v7;
    if ( v1 && v2 )
    {
      LeaveCriticalSection(v1);
      v2 = 0;
      v59 = 0;
    }
    v8 = CJetContextList::AcquireContext(*((CJetContextList **)v3 + 19), &v61, 0);
    v10 = (JET_SESID *)v61;
    v11 = v8;
    if ( v8 >= 0 )
    {
      v11 = CJetContext::SetCurrentIndex(v61, 0, L"HashEntryIdIndex", v9);
      if ( v11 >= 0 )
      {
        v12 = JetBeginTransaction(v10[2]);
        v11 = HRESULTFromJET_ERR(v12, 1);
        if ( v11 >= 0 )
        {
          v62 = 1;
          v13 = (CBloomFilterPartition **)((char *)v3 + 192);
          for ( i = 0x80000000; ; i = 1 )
          {
            v4 = *(char **)(*((_QWORD *)v3 + 3) + 240LL);
            if ( !v4 )
            {
LABEL_14:
              CBloomFilterPartition::CommitUpdate(*v13, &v65, v60);
              v6 = v65;
              v11 = (int)v4;
              goto LABEL_15;
            }
            v16 = (struct _RTL_CRITICAL_SECTION *)(v4 + 8);
            v17 = 0;
            if ( v4 != (char *)-8LL )
            {
              EnterCriticalSection((LPCRITICAL_SECTION)(v4 + 8));
              v17 = 1;
            }
            v18 = *((_DWORD *)v4 + 22);
            if ( v17 && v16 )
              LeaveCriticalSection(v16);
            if ( v18 == 2 )
            {
              LODWORD(v4) = 0;
              v13 = (CBloomFilterPartition **)((char *)v3 + 192);
              if ( _InterlockedCompareExchange((volatile signed __int32 *)&CCacheStore::g_ulQuickTerminate, 0, 0) )
                goto LABEL_14;
            }
            else
            {
              LODWORD(v4) = 0;
            }
            v19 = JetMove(v10[2], v10[4], i, 0);
            v13 = (CBloomFilterPartition **)((char *)v3 + 192);
            if ( v19 == -1603 )
              goto LABEL_14;
            v11 = HRESULTFromJET_ERR(v19, 1);
            if ( v11 < 0 )
              goto LABEL_15;
            v22 = v10[5];
            v23 = v10[4];
            v24 = v10[2];
            pcbActual = 32;
            v25 = *(_DWORD *)(*(_QWORD *)(v22 + 8) + 16LL);
            v64 = 0;
            if ( (BYTE1(xmmword_180266B60) & 0x10) != 0 )
              WPP_SF_iiiq((unsigned int)&Src, v20, v21, v24, v23, v25, (__int64)&Src);
            if ( (_DWORD)v69 )
            {
              LODWORD(v69) = 0;
              *(_WORD *)Src = 0;
            }
            while ( 1 )
            {
              v11 = 0;
              if ( HIDWORD(v69) < (pcbActual >> 1) + 5 )
              {
                v26 = (pcbActual >> 1) + 7;
                v27 = 256;
                if ( v26 > 0x100 )
                {
                  if ( v26 > 0x400 )
                  {
                    v27 = 4096;
                    if ( v26 <= 0x1000 )
                      v27 = 1024;
                  }
                }
                else
                {
                  v27 = 64;
                }
                v28 = -v27 & (v27 + (pcbActual >> 1) + 6);
                v29 = v28 - 1;
                if ( v28 - 1 > 0xFFFFFFE )
                {
                  v11 = -2147024809;
LABEL_89:
                  v64 = 137;
                  goto LABEL_59;
                }
                v30 = 2 * v28;
                v64 = 0;
                if ( g_fWxHeapExtensionInitialized )
                  v31 = (_WORD *)((__int64 (__fastcall *)(__int64))qword_180268420)(v30);
                else
                  v31 = HeapAlloc(g_hWxProcessHeap, 0, (unsigned int)v30);
                v32 = v31;
                if ( !v31 )
                {
                  v64 = 52;
                  v11 = -2147024882;
                  goto LABEL_89;
                }
                *v31 = 0;
                v33 = (WCHAR *)Src;
                memcpy_0(v31, Src, 2LL * (unsigned int)v69);
                v32[(unsigned int)v69] = 0;
                HIDWORD(v69) = v29;
                Src = v32;
                v11 = 0;
                if ( !v33 || v33 == &Data )
                {
                  LODWORD(v4) = 0;
                }
                else
                {
                  if ( g_fWxHeapExtensionInitialized )
                    g_WxHeapExtensionInterfaces(v33);
                  else
                    HeapFree(g_hWxProcessHeap, 0, v33);
                  LODWORD(v4) = 0;
                }
              }
              v34 = JetRetrieveColumn(v24, v23, v25, Src, 2 * HIDWORD(v69) - 2, &pcbActual, 0, 0);
              if ( !v34 || v34 == 1004 )
                break;
              if ( Src != &Data )
              {
                *(_WORD *)Src = 0;
                v58 = -1;
                do
                  ++v58;
                while ( *((_WORD *)Src + v58) );
                LODWORD(v69) = v58;
              }
              if ( v34 != 1006 )
              {
                v11 = HRESULTFromJET_ERR(v34, 1);
                if ( v11 >= 0 )
                {
                  v11 = -2147418113;
                  v64 = 154;
                }
                goto LABEL_59;
              }
            }
            if ( Src != &Data )
            {
              v35 = HIDWORD(v69);
              if ( HIDWORD(v69) >= pcbActual >> 1 )
                v35 = pcbActual >> 1;
              *((_WORD *)Src + v35) = 0;
              v36 = -1;
              do
                ++v36;
              while ( *((_WORD *)Src + v36) );
              LODWORD(v69) = v36;
            }
LABEL_59:
            if ( (BYTE1(xmmword_180266B60) & 0x10) != 0 )
              WPP_SF_d(1036, 13, &WPP_70a08f364de0374d8b8fa0ef849ee242_Traceguids, (unsigned int)v11);
            if ( v11 < 0 )
              break;
            v37 = Src;
            v13 = (CBloomFilterPartition **)((char *)v3 + 192);
            v38 = *((_QWORD *)v3 + 24);
            pcbActual = 0;
            v6 = v63;
            if ( (BYTE1(xmmword_180266B60) & 0x10) != 0 )
              WPP_SF_qSq(
                1036,
                22,
                (unsigned int)&WPP_fd8c4a12b4fc3ea928353dabf2ce535f_Traceguids,
                v38,
                (__int64)Src,
                (__int64)v63);
            v39 = v37;
            v40 = 0;
            v41 = 0;
            if ( v37 )
            {
              do
              {
                v40 = dword_180226530[(unsigned __int64)(unsigned __int16)*v39 >> 8]
                    ^ __ROL4__(dword_180226530[(unsigned __int8)*v39] ^ __ROL4__(v40, 1), 1);
                if ( !*v39 )
                  break;
                ++v39;
                ++v41;
              }
              while ( v41 != -1 );
            }
            v42 = *v37;
            v43 = 5381;
            if ( *v37 )
            {
              v44 = v37;
              do
              {
                ++v44;
                v43 = v42 ^ (33 * v43);
                v42 = *v44;
              }
              while ( *v44 );
            }
            if ( v38 != -16 )
            {
              EnterCriticalSection((LPCRITICAL_SECTION)(v38 + 16));
              pcbActual = 1;
            }
            if ( v6 )
            {
              if ( (BYTE1(xmmword_180266B60) & 0x10) != 0 )
                WPP_SF_Sd(
                  1036,
                  23,
                  (unsigned int)&WPP_fd8c4a12b4fc3ea928353dabf2ce535f_Traceguids,
                  (_DWORD)v37,
                  *(_DWORD *)(v38 + 80));
              v45 = *(_DWORD *)(v38 + 88);
              v46 = 0;
              v47 = 8 * v60;
              v48 = v40 % (8 * v60);
              for ( j = v43 % (8 * v60); v46 < v45; j = v50 % v47 )
              {
                v6[(unsigned __int64)v48 >> 3] |= 1 << (v48 & 7);
                v50 = v46 + j;
                ++v46;
                v48 = (j + v48) % v47;
              }
            }
            else
            {
              if ( (BYTE1(xmmword_180266B60) & 0x10) != 0 )
                WPP_SF_S(1036, 24, &WPP_fd8c4a12b4fc3ea928353dabf2ce535f_Traceguids, v37);
              v51 = *(_DWORD *)(v38 + 88);
              v52 = *(_QWORD *)(v38 + 64);
              v53 = 0;
              v54 = 8 * *(_DWORD *)(v38 + 84);
              v55 = v40 % v54;
              for ( k = v43 % v54; v53 < v51; k = v57 % v54 )
              {
                *(_BYTE *)(((unsigned __int64)v55 >> 3) + v52) |= 1 << (v55 & 7);
                v57 = v53 + k;
                ++v53;
                v55 = (k + v55) % v54;
              }
              v6 = v63;
            }
            if ( (BYTE1(xmmword_180266B60) & 0x10) != 0 )
              WPP_SF_(1036, 25, &WPP_fd8c4a12b4fc3ea928353dabf2ce535f_Traceguids);
            if ( pcbActual && v38 != -16 )
              LeaveCriticalSection((LPCRITICAL_SECTION)(v38 + 16));
            v3 = v66;
            v10 = (JET_SESID *)v61;
          }
          v6 = v63;
          v10 = (JET_SESID *)v61;
LABEL_15:
          v2 = v59;
          v1 = (struct _RTL_CRITICAL_SECTION *)((char *)v3 + 32);
        }
      }
    }
    if ( v6 )
      CBloomFilterPartition::AbortUpdate(*((CBloomFilterPartition **)v3 + 24), &v65);
    if ( v62 != (_DWORD)v4 )
      JetRollback(v10[2], 0);
  }
  else
  {
    v11 = 0;
  }
  CContainerProps::ReleaseEntryContext(v3, &v61);
  if ( (BYTE1(xmmword_180266B60) & 0x10) != 0 )
    WPP_SF_d(1036, 36, &WPP_4b302e6b786c3b7f389fd4681ef43772_Traceguids, (unsigned int)v11);
  if ( v2 && v1 )
    LeaveCriticalSection(v1);
  CWxString::_Release((CWxString *)&Src);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x18007fdc4  push    rbp
0x18007fdc6  push    rbx
0x18007fdc7  push    rsi
0x18007fdc8  push    rdi
0x18007fdc9  push    r12
0x18007fdcb  push    r13
0x18007fdcd  push    r14
0x18007fdcf  push    r15
0x18007fdd1  lea     rbp, [rsp-1Fh]
0x18007fdd6  sub     rsp, 0A8h
0x18007fddd  mov     rax, cs:__security_cookie
0x18007fde4  xor     rax, rsp
0x18007fde7  mov     [rbp+57h+var_48], rax
0x18007fdeb  xor     r13d, r13d
0x18007fdee  mov     [rbp+57h+var_68], rcx
0x18007fdf2  lea     rax, Data
0x18007fdf9  mov     [rbp+57h+var_94], r13d
0x18007fdfd  mov     [rbp+57h+Src], rax
0x18007fe01  lea     rsi, [rcx+20h]
0x18007fe05  mov     [rbp+57h+var_50], r13
0x18007fe09  mov     r12d, r13d
0x18007fe0c  mov     [rbp+57h+var_90], r13
0x18007fe10  mov     r14, rcx
0x18007fe13  mov     [rbp+57h+var_A0], r13d
0x18007fe17  test    byte ptr cs:xmmword_180266B60+1, 10h
0x18007fe1e  lea     rdi, [rcx+0D0h]
0x18007fe25  lea     rbx, [rcx+0C8h]
0x18007fe2c  jz      short loc_18007FE54
0x18007fe2e  mov     eax, [rdi]
0x18007fe30  lea     edx, [r13+23h]
0x18007fe34  mov     dword ptr [rsp+0E0h+pcbActual], eax
0x18007fe38  lea     r8, WPP_4b302e6b786c3b7f389fd4681ef43772_Traceguids
0x18007fe3f  mov     rax, [rbx]
0x18007fe42  mov     ecx, 40Ch
0x18007fe47  mov     r9, r14
0x18007fe4a  mov     qword ptr [rsp+0E0h+cbData], rax
0x18007fe4f  call    WPP_SF_qqD
0x18007fe54  test    rsi, rsi
0x18007fe57  jz      short loc_18007FE6C
0x18007fe59  mov     rcx, rsi; lpCriticalSection
0x18007fe5c  call    cs:__imp_EnterCriticalSection
0x18007fe62  mov     r12d, 1
0x18007fe68  mov     [rbp+57h+var_A0], r12d
0x18007fe6c  mov     r15, [rbx]
0x18007fe6f  mov     [rbp+57h+var_80], r15
0x18007fe73  test    r15, r15
0x18007fe76  jz      loc_1800804EC
0x18007fe7c  mov     eax, [rdi]
0x18007fe7e  mov     [rdi], r13d
0x18007fe81  xor     edi, edi
0x18007fe83  mov     [rbp+57h+var_88], r13d
0x18007fe87  mov     [rbp+57h+var_70], r15
0x18007fe8b  mov     [rbx], r13
0x18007fe8e  mov     [rbp+57h+var_98], eax
0x18007fe91  test    rsi, rsi
0x18007fe94  jz      short loc_18007FEAA
0x18007fe96  test    r12d, r12d
0x18007fe99  jz      short loc_18007FEAA
0x18007fe9b  mov     rcx, rsi; lpCriticalSection
0x18007fe9e  call    cs:__imp_LeaveCriticalSection
0x18007fea4  mov     r12d, edi
0x18007fea7  mov     [rbp+57h+var_A0], edi
0x18007feaa  mov     rcx, [r14+98h]; this
0x18007feb1  lea     rdx, [rbp+57h+var_90]; struct CJetContext **
0x18007feb5  xor     r8d, r8d; int *
0x18007feb8  call    ?AcquireContext@CJetContextList@@QEAAJPEAPEAVCJetContext@@PEAH@Z; CJetContextList::AcquireContext(CJetContext * *,int *)
0x18007febd  mov     r13, [rbp+57h+var_90]
0x18007fec1  mov     ebx, eax
0x18007fec3  test    eax, eax
0x18007fec5  js      loc_180080517
0x18007fecb  lea     r8, aHashentryidind; "HashEntryIdIndex"
0x18007fed2  xor     edx, edx; unsigned int
0x18007fed4  mov     rcx, r13; this
0x18007fed7  call    ?SetCurrentIndex@CJetContext@@QEAAJKPEBGK@Z; CJetContext::SetCurrentIndex(ulong,ushort const *,ulong)
0x18007fedc  mov     ebx, eax
0x18007fede  test    eax, eax
0x18007fee0  js      loc_180080523
0x18007fee6  mov     rcx, [r13+10h]; sesid
0x18007feea  call    cs:__imp_JetBeginTransaction
0x18007fef0  mov     ecx, eax; int
0x18007fef2  mov     edx, 1; int
0x18007fef7  call    ?HRESULTFromJET_ERR@@YAJJH@Z; HRESULTFromJET_ERR(long,int)
0x18007fefc  mov     ebx, eax
0x18007fefe  test    eax, eax
0x18007ff00  js      short loc_18007FF4A
0x18007ff02  mov     [rbp+57h+var_88], 1
0x18007ff09  lea     r12, [r14+0C0h]
0x18007ff10  mov     esi, 80000000h
0x18007ff15  xor     ecx, ecx
0x18007ff17  mov     rax, [r14+18h]
0x18007ff1b  mov     rdi, [rax+0F0h]
0x18007ff22  test    rdi, rdi
0x18007ff25  jnz     loc_18007FFB3
0x18007ff2b  mov     r8d, [rbp+57h+var_98]; unsigned int
0x18007ff2f  lea     rdx, [rbp+57h+var_70]; unsigned __int8 **
0x18007ff33  mov     rcx, [r12]; this
0x18007ff37  call    ?CommitUpdate@CBloomFilterPartition@@QEAAXPEAPEAEK@Z; CBloomFilterPartition::CommitUpdate(uchar * *,ulong)
0x18007ff3c  mov     r15, [rbp+57h+var_70]
0x18007ff40  mov     ebx, edi
0x18007ff42  mov     r12d, [rbp+57h+var_A0]
0x18007ff46  lea     rsi, [r14+20h]
0x18007ff4a  test    r15, r15
0x18007ff4d  jnz     loc_180080577
0x18007ff53  cmp     [rbp+57h+var_88], edi
0x18007ff56  jnz     loc_1800804F5
0x18007ff5c  lea     rdx, [rbp+57h+var_90]; struct CJetContext **
0x18007ff60  mov     rcx, r14; this
0x18007ff63  call    ?ReleaseEntryContext@CContainerProps@@QEAAXPEAPEAVCJetContext@@@Z; CContainerProps::ReleaseEntryContext(CJetContext * *)
0x18007ff68  test    byte ptr cs:xmmword_180266B60+1, 10h
0x18007ff6f  jnz     loc_1800804CE
0x18007ff75  test    r12d, r12d
0x18007ff78  jz      short loc_18007FF88
0x18007ff7a  test    rsi, rsi
0x18007ff7d  jz      short loc_18007FF88
0x18007ff7f  mov     rcx, rsi; lpCriticalSection
0x18007ff82  call    cs:__imp_LeaveCriticalSection
0x18007ff88  lea     rcx, [rbp+57h+Src]; this
0x18007ff8c  call    ?_Release@CWxString@@AEAAXXZ; CWxString::_Release(void)
0x18007ff91  mov     eax, ebx
0x18007ff93  mov     rcx, [rbp+57h+var_48]
0x18007ff97  xor     rcx, rsp; StackCookie
0x18007ff9a  call    __security_check_cookie
0x18007ff9f  add     rsp, 0A8h
0x18007ffa6  pop     r15
0x18007ffa8  pop     r14
0x18007ffaa  pop     r13
0x18007ffac  pop     r12
0x18007ffae  pop     rdi
0x18007ffaf  pop     rsi
0x18007ffb0  pop     rbx
0x18007ffb1  pop     rbp
0x18007ffb2  retn
0x18007ffb3  lea     rbx, [rdi+8]
0x18007ffb7  mov     eax, ecx
0x18007ffb9  test    rbx, rbx
0x18007ffbc  jz      short loc_18007FFCC
0x18007ffbe  mov     rcx, rbx; lpCriticalSection
0x18007ffc1  call    cs:__imp_EnterCriticalSection
0x18007ffc7  mov     eax, 1
0x18007ffcc  mov     edi, [rdi+58h]
0x18007ffcf  test    eax, eax
0x18007ffd1  jz      short loc_18007FFE1
0x18007ffd3  test    rbx, rbx
0x18007ffd6  jz      short loc_18007FFE1
0x18007ffd8  mov     rcx, rbx; lpCriticalSection
0x18007ffdb  call    cs:__imp_LeaveCriticalSection
0x18007ffe1  cmp     edi, 2
0x18007ffe4  jz      loc_18008052F
0x18007ffea  xor     edi, edi
0x18007ffec  mov     rdx, [r13+20h]; tableid
0x18007fff0  xor     r9d, r9d; grbit
0x18007fff3  mov     rcx, [r13+10h]; sesid
0x18007fff7  mov     r8d, esi; cRow
0x18007fffa  call    cs:__imp_JetMove
0x180080000  lea     r12, [r14+0C0h]
0x180080007  cmp     eax, 0FFFFF9BDh
0x18008000c  jz      loc_18007FF2B
0x180080012  mov     edx, 1; int
0x180080017  mov     ecx, eax; int
0x180080019  call    ?HRESULTFromJET_ERR@@YAJJH@Z; HRESULTFromJET_ERR(long,int)
0x18008001e  mov     ebx, eax
0x180080020  test    eax, eax
0x180080022  js      loc_18007FF42
0x180080028  mov     rax, [r13+28h]
0x18008002c  mov     r12, [r13+20h]
0x180080030  mov     r13, [r13+10h]
0x180080034  mov     [rbp+57h+var_60], 20h ; ' '
0x18008003b  mov     rcx, [rax+8]
0x18008003f  mov     r15d, [rcx+10h]
0x180080043  mov     [rbp+57h+var_74], edi
0x180080046  test    byte ptr cs:xmmword_180266B60+1, 10h
0x18008004d  jz      short loc_18008006A
0x18008004f  lea     rcx, [rbp+57h+Src]
0x180080053  mov     r9, r13
0x180080056  mov     qword ptr [rsp+0E0h+grbit], rcx
0x18008005b  mov     [rsp+0E0h+pcbActual], r15
0x180080060  mov     qword ptr [rsp+0E0h+cbData], r12
0x180080065  call    WPP_SF_iiiq
0x18008006a  cmp     dword ptr [rbp+57h+var_50], edi
0x18008006d  jnz     loc_180080146
0x180080073  lea     rsi, Data
0x18008007a  mov     ecx, [rbp+57h+var_60]
0x18008007d  mov     ebx, edi
0x18008007f  shr     ecx, 1
0x180080081  add     ecx, 5
0x180080084  cmp     dword ptr [rbp+57h+var_50+4], ecx
0x180080087  jnb     loc_180080157
0x18008008d  add     ecx, 2
0x180080090  mov     eax, 100h
0x180080095  cmp     ecx, eax
0x180080097  ja      loc_18008043D
0x18008009d  mov     eax, 40h ; '@'
0x1800800a2  lea     edx, [rcx-1]
0x1800800a5  add     edx, eax
0x1800800a7  neg     eax
0x1800800a9  and     edx, eax
0x1800800ab  lea     esi, [rdx-1]
0x1800800ae  cmp     esi, 0FFFFFFEh
0x1800800b4  ja      loc_18008042C
0x1800800ba  cmp     cs:?g_fWxHeapExtensionInitialized@@3HA, edi; int g_fWxHeapExtensionInitialized
0x1800800c0  lea     ecx, [rdx+rdx]
0x1800800c3  mov     [rbp+57h+var_74], edi
0x1800800c6  jnz     loc_180080506
0x1800800cc  mov     r8d, ecx; dwBytes
0x1800800cf  xor     edx, edx; dwFlags
0x1800800d1  mov     rcx, cs:g_hWxProcessHeap; hHeap
0x1800800d8  call    cs:__imp_HeapAlloc
0x1800800de  mov     rbx, rax
0x1800800e1  test    rax, rax
0x1800800e4  jz      loc_18008045E
0x1800800ea  mov     [rax], di
0x1800800ed  mov     rcx, rax; void *
0x1800800f0  mov     rdi, [rbp+57h+Src]
0x1800800f4  mov     r8d, dword ptr [rbp+57h+var_50]
0x1800800f8  mov     rdx, rdi; Src
0x1800800fb  add     r8, r8; Size
0x1800800fe  call    memcpy_0
0x180080103  mov     ecx, dword ptr [rbp+57h+var_50]
0x180080106  xor     edx, edx; dwFlags
0x180080108  mov     [rbx+rcx*2], dx
0x18008010c  mov     dword ptr [rbp+57h+var_50+4], esi
0x18008010f  mov     [rbp+57h+Src], rbx
0x180080113  lea     rsi, Data
0x18008011a  mov     ebx, edx
0x18008011c  test    rdi, rdi
0x18008011f  jz      short loc_180080155
0x180080121  cmp     rdi, rsi
0x180080124  jz      short loc_180080155
0x180080126  cmp     cs:?g_fWxHeapExtensionInitialized@@3HA, edx; int g_fWxHeapExtensionInitialized
0x18008012c  jnz     loc_18008054F
0x180080132  mov     rcx, cs:g_hWxProcessHeap; hHeap
0x180080139  mov     r8, rdi; lpMem
0x18008013c  call    cs:__imp_HeapFree
0x180080142  xor     edi, edi
0x180080144  jmp     short loc_18008015F
0x180080146  mov     rax, [rbp+57h+Src]
0x18008014a  mov     dword ptr [rbp+57h+var_50], edi
0x18008014d  mov     [rax], di
0x180080150  jmp     loc_180080073
0x180080155  xor     edi, edi
0x180080157  test    ebx, ebx
0x180080159  js      loc_180080431
0x18008015f  mov     eax, dword ptr [rbp+57h+var_50+4]
0x180080162  lea     rcx, [rbp+57h+var_60]
0x180080166  mov     r9, [rbp+57h+Src]; pvData
0x18008016a  mov     r8d, r15d; columnid
0x18008016d  mov     [rsp+0E0h+pretinfo], rdi; pretinfo
0x180080172  mov     rdx, r12; tableid
0x180080175  mov     [rsp+0E0h+grbit], edi; grbit
0x180080179  mov     [rsp+0E0h+pcbActual], rcx; pcbActual
0x18008017e  lea     eax, ds:0FFFFFFFFFFFFFFFEh[rax*2]
0x180080185  mov     rcx, r13; sesid
0x180080188  mov     [rsp+0E0h+cbData], eax; cbData
0x18008018c  call    cs:__imp_JetRetrieveColumn
0x180080192  mov     r8d, eax
0x180080195  test    eax, eax
0x180080197  jnz     loc_18008046C
0x18008019d  mov     rdx, [rbp+57h+Src]
0x1800801a1  cmp     rdx, rsi
0x1800801a4  jz      short loc_1800801CB
0x1800801a6  mov     eax, dword ptr [rbp+57h+var_50+4]
0x1800801a9  mov     ecx, [rbp+57h+var_60]
0x1800801ac  shr     ecx, 1
0x1800801ae  cmp     eax, ecx
0x1800801b0  cmovnb  eax, ecx
0x1800801b3  mov     [rdx+rax*2], di
0x1800801b7  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800801bb  mov     rcx, [rbp+57h+Src]
0x1800801bf  inc     rax
0x1800801c2  cmp     [rcx+rax*2], di
0x1800801c6  jnz     short loc_1800801BF
0x1800801c8  mov     dword ptr [rbp+57h+var_50], eax
0x1800801cb  test    byte ptr cs:xmmword_180266B60+1, 10h
0x1800801d2  jz      short loc_1800801ED
0x1800801d4  mov     edx, 0Dh
0x1800801d9  lea     r8, WPP_70a08f364de0374d8b8fa0ef849ee242_Traceguids
0x1800801e0  mov     ecx, 40Ch
0x1800801e5  mov     r9d, ebx
0x1800801e8  call    WPP_SF_d
0x1800801ed  test    ebx, ebx
0x1800801ef  js      loc_180080563
0x1800801f5  mov     rbx, [rbp+57h+Src]
0x1800801f9  lea     r12, [r14+0C0h]
0x180080200  mov     r14, [r12]
0x180080204  mov     [rbp+57h+var_60], edi
0x180080207  lea     r13, [r14+10h]
0x18008020b  test    byte ptr cs:xmmword_180266B60+1, 10h
0x180080212  mov     r15, [rbp+57h+var_80]
0x180080216  jz      short loc_18008023B
0x180080218  mov     edx, 16h
0x18008021d  mov     [rsp+0E0h+pcbActual], r15
0x180080222  mov     ecx, 40Ch
0x180080227  mov     qword ptr [rsp+0E0h+cbData], rbx
0x18008022c  mov     r9, r14
0x18008022f  lea     r8, WPP_fd8c4a12b4fc3ea928353dabf2ce535f_Traceguids
0x180080236  call    WPP_SF_qSq
0x18008023b  mov     r8, rbx
0x18008023e  mov     esi, edi
0x180080240  mov     edx, edi
0x180080242  test    rbx, rbx
  ... truncated ...
```
