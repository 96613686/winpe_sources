# GetLatestKey(_SECURITY_DESCRIPTOR *,ulong,uchar * *,ulong *,uchar *,ulong,ulong)

- ea: `0x1800196cc`
- end: `0x180019a65`
- name: `?GetLatestKey@@YAJPEAU_SECURITY_DESCRIPTOR@@KPEAPEAEPEAKPEAEKK@Z`
- size: `921`
- prototype: `__int64 __fastcall(struct _SECURITY_DESCRIPTOR *, unsigned int, unsigned __int8 **, unsigned int *, unsigned __int8 *, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180019a6c`

## callees

- `0x180001f7c`
- `0x180003e08`
- `0x18000b310`
- `0x18000ce40`
- `0x18000fe30`
- `0x180010624`
- `0x180010950`
- `0x1800187ec`
- `0x180018c7c`
- `0x180019274`
- `0x1800196cc`
- `0x18001a450`

## string_xrefs

- `0x180019751`: `onecore\ds\security\keyman\sidkeyprov\rpcclient\sidkeyrpcclient.cxx`
- `0x1800198c6`: `onecore\ds\security\keyman\sidkeyprov\rpcclient\sidkeyrpcclient.cxx`
- `0x180019923`: `onecore\ds\security\keyman\sidkeyprov\rpcclient\sidkeyrpcclient.cxx`
- `0x180019991`: `onecore\ds\security\keyman\sidkeyprov\rpcclient\sidkeyrpcclient.cxx`
- `0x1800198bd`: `hrCache`

## pseudocode

```c
__int64 __fastcall GetLatestKey(
        struct _SECURITY_DESCRIPTOR *a1,
        unsigned int a2,
        unsigned __int8 **a3,
        unsigned int *a4,
        unsigned __int8 *a5,
        unsigned int a6,
        unsigned int a7)
{
  struct _SID_KEY_HEADER *v8; // rdi
  unsigned __int8 *v9; // r12
  unsigned int v10; // r13d
  unsigned __int16 *v11; // r14
  unsigned __int16 *v12; // rsi
  signed int CachedMachineDomainInfo; // eax
  unsigned int v14; // ebx
  unsigned int v15; // r9d
  unsigned __int16 *v16; // rdi
  __int64 v17; // rax
  int KeyInCache; // eax
  int v19; // r15d
  int KeyFromKdsService; // eax
  int KeyForOfflineUsage; // eax
  unsigned int v22; // r9d
  const char *v23; // rdx
  unsigned int v24; // ecx
  signed int v25; // eax
  signed int v26; // eax
  __int64 v27; // rax
  struct _SID_KEY_HEADER *v28; // rcx
  int v30; // [rsp+78h] [rbp-41h] BYREF
  int v31; // [rsp+7Ch] [rbp-3Dh] BYREF
  unsigned int v32; // [rsp+80h] [rbp-39h] BYREF
  struct _SID_KEY_HEADER *Src; // [rsp+88h] [rbp-31h] BYREF
  unsigned __int16 *v34; // [rsp+90h] [rbp-29h] BYREF
  unsigned __int8 *v35; // [rsp+98h] [rbp-21h] BYREF
  void *lpMem; // [rsp+A0h] [rbp-19h] BYREF
  unsigned __int16 *v37; // [rsp+A8h] [rbp-11h] BYREF
  unsigned __int16 *v38; // [rsp+B0h] [rbp-9h] BYREF

  Src = 0;
  a6 = 0;
  v8 = 0;
  v35 = 0;
  v9 = 0;
  v32 = 0;
  v10 = 0;
  lpMem = 0;
  v11 = 0;
  v37 = 0;
  v12 = 0;
  v30 = 0;
  v34 = 0;
  v31 = 0;
  if ( !a1 || !a3 )
  {
    v14 = -2147024809;
    goto LABEL_33;
  }
  CachedMachineDomainInfo = IsLowbox(&v31);
  v14 = CachedMachineDomainInfo;
  if ( CachedMachineDomainInfo < 0 )
  {
    v15 = 1816;
LABEL_5:
    SidKeyDebugTraceError(
      CachedMachineDomainInfo,
      "hr",
      "onecore\\ds\\security\\keyman\\sidkeyprov\\rpcclient\\sidkeyrpcclient.cxx",
      v15);
    return v14;
  }
  CachedMachineDomainInfo = GetCachedMachineDomainInfo(&v38, &v34);
  v14 = CachedMachineDomainInfo;
  if ( CachedMachineDomainInfo < 0 )
  {
    v15 = 1827;
    goto LABEL_5;
  }
  v16 = v34;
  v17 = -1;
  do
    ++v17;
  while ( v34[v17] );
  LODWORD(v34) = 2 * v17 + 2;
  KeyInCache = FindKeyInCache(0, a1, a2, (unsigned int)v31, 1, v16, (_DWORD)v34, &v30, &Src, &a6, &v37, &lpMem);
  v11 = (unsigned __int16 *)lpMem;
  v12 = v37;
  if ( KeyInCache >= 0 )
  {
    v19 = v30;
    if ( v30 )
      goto LABEL_21;
  }
  v30 = 0;
  v19 = 0;
  KeyFromKdsService = GetKeyFromKdsService(
                        &a1->Revision,
                        a2,
                        0,
                        -1,
                        -1,
                        -1,
                        v31,
                        a7,
                        0,
                        0,
                        0,
                        (unsigned __int8 **)&Src,
                        &a6);
  v14 = KeyFromKdsService;
  if ( KeyFromKdsService >= 0 )
    goto LABEL_21;
  if ( KeyFromKdsService == -2147024891 || !v11 || !v12 )
  {
    v22 = 1904;
    v23 = "hr";
    v24 = KeyFromKdsService;
    goto LABEL_18;
  }
  KeyForOfflineUsage = FindKeyForOfflineUsage(0, v12, v16, (unsigned int)v34, &v30, &Src, &a6);
  if ( KeyForOfflineUsage >= 0 )
  {
    v19 = v30;
    if ( !v30 )
      goto LABEL_19;
LABEL_21:
    v8 = Src;
    v25 = GenerateSIDKey(Src, a6, 0, 2, &v35, &v32, a5);
    v14 = v25;
    if ( v25 >= 0 )
    {
      if ( !v19 )
      {
        if ( v11 )
        {
          if ( v12 )
          {
            v26 = WriteSIDKeyInCache(v8, a6, &a1->Revision, a2, v12, v11);
            v14 = v26;
            if ( v26 < 0 )
            {
              SidKeyDebugTraceError(
                v26,
                "hr",
                "onecore\\ds\\security\\keyman\\sidkeyprov\\rpcclient\\sidkeyrpcclient.cxx",
                0x792u);
              v14 = 0;
            }
          }
        }
      }
      v10 = v32;
      *a3 = v35;
      *a4 = v10;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, WPP_b22aa97707d93c78e27dc2ffaf6f95cb_Traceguids);
    }
    else
    {
      SidKeyDebugTraceError(
        v25,
        "hr",
        "onecore\\ds\\security\\keyman\\sidkeyprov\\rpcclient\\sidkeyrpcclient.cxx",
        0x780u);
      v9 = v35;
      v10 = v32;
    }
    goto LABEL_33;
  }
  v22 = 1891;
  v23 = "hrCache";
  v24 = KeyForOfflineUsage;
LABEL_18:
  SidKeyDebugTraceError(v24, v23, "onecore\\ds\\security\\keyman\\sidkeyprov\\rpcclient\\sidkeyrpcclient.cxx", v22);
LABEL_19:
  v8 = Src;
LABEL_33:
  if ( v11 )
    SIDKeyProvFree(v11);
  if ( v12 )
    SIDKeyProvFree(v12);
  if ( v9 )
  {
    memset_0(v9, 0, v10);
    SIDKeyProvFree(v9);
  }
  if ( v8 )
  {
    v27 = a6;
    v28 = v8;
    if ( a6 )
    {
      do
      {
        *(_BYTE *)v28 = 0;
        v28 = (struct _SID_KEY_HEADER *)((char *)v28 + 1);
        --v27;
      }
      while ( v27 );
    }
    SIDKeyProvFree(v8);
  }
  return v14;
}

```

## disassembly

```asm
0x1800196cc  mov     rax, rsp
0x1800196cf  mov     [rax+20h], r9
0x1800196d3  mov     [rax+18h], r8
0x1800196d7  mov     [rax+10h], edx
0x1800196da  mov     [rax+8], rcx
0x1800196de  push    rbp
0x1800196df  push    rbx
0x1800196e0  push    rsi
0x1800196e1  push    rdi
0x1800196e2  push    r12
0x1800196e4  push    r13
0x1800196e6  push    r14
0x1800196e8  push    r15
0x1800196ea  lea     rbp, [rax-47h]
0x1800196ee  sub     rsp, 0B8h
0x1800196f5  xor     ebx, ebx
0x1800196f7  mov     rax, r8
0x1800196fa  mov     [rbp+3Fh+Src], rbx
0x1800196fe  mov     r15, rcx
0x180019701  mov     [rbp+3Fh+arg_28], ebx
0x180019704  mov     edi, ebx
0x180019706  mov     [rbp+3Fh+var_60], rbx
0x18001970a  mov     r12d, ebx
0x18001970d  mov     [rbp+3Fh+var_78], ebx
0x180019710  mov     r13d, ebx
0x180019713  mov     [rbp+3Fh+lpMem], rbx
0x180019717  mov     r14d, ebx
0x18001971a  mov     [rbp+3Fh+var_50], rbx
0x18001971e  mov     esi, ebx
0x180019720  mov     [rbp+3Fh+var_80], ebx
0x180019723  mov     [rbp+3Fh+var_68], rbx
0x180019727  mov     [rbp+3Fh+var_7C], ebx
0x18001972a  test    rcx, rcx
0x18001972d  jz      loc_1800199EF
0x180019733  test    rax, rax
0x180019736  jz      loc_1800199EF
0x18001973c  lea     rcx, [rbp+3Fh+var_7C]; int *
0x180019740  call    ?IsLowbox@@YAJPEAH@Z; IsLowbox(int *)
0x180019745  mov     ebx, eax
0x180019747  test    eax, eax
0x180019749  jns     short loc_18001976B
0x18001974b  mov     r9d, 718h; unsigned int
0x180019751  lea     r8, aOnecoreDsSecur_11; "onecore\\ds\\security\\keyman\\sidkeypr"...
0x180019758  mov     ecx, eax; unsigned int
0x18001975a  lea     rdx, aHr; "hr"
0x180019761  call    ?SidKeyDebugTraceError@@YAXKPEBD0K@Z; SidKeyDebugTraceError(ulong,char const *,char const *,ulong)
0x180019766  jmp     loc_180019A4F
0x18001976b  lea     rdx, [rbp+3Fh+var_68]; unsigned __int16 **
0x18001976f  lea     rcx, [rbp+3Fh+var_48]; unsigned __int16 **
0x180019773  call    ?GetCachedMachineDomainInfo@@YAJPEAPEAG0@Z; GetCachedMachineDomainInfo(ushort * *,ushort * *)
0x180019778  mov     ebx, eax
0x18001977a  test    eax, eax
0x18001977c  jns     short loc_180019786
0x18001977e  mov     r9d, 723h
0x180019784  jmp     short loc_180019751
0x180019786  mov     rdi, [rbp+3Fh+var_68]
0x18001978a  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001978e  inc     rax
0x180019791  cmp     [rdi+rax*2], si
0x180019795  jnz     short loc_18001978E
0x180019797  mov     ebx, [rbp+3Fh+arg_8]
0x18001979a  lea     eax, ds:2[rax*2]
0x1800197a1  mov     r9d, [rbp+3Fh+var_7C]
0x1800197a5  lea     rcx, [rbp+3Fh+lpMem]
0x1800197a9  mov     [rsp+0F0h+var_98], rcx
0x1800197ae  mov     r8d, ebx
0x1800197b1  lea     rcx, [rbp+3Fh+var_50]
0x1800197b5  mov     dword ptr [rbp+3Fh+var_68], eax
0x1800197b8  mov     [rsp+0F0h+var_A0], rcx
0x1800197bd  mov     rdx, r15
0x1800197c0  lea     rcx, [rbp+3Fh+arg_28]
0x1800197c4  mov     qword ptr [rsp+0F0h+var_A8], rcx
0x1800197c9  lea     rcx, [rbp+3Fh+Src]
0x1800197cd  mov     [rsp+0F0h+var_B0], rcx
0x1800197d2  lea     rcx, [rbp+3Fh+var_80]
0x1800197d6  mov     qword ptr [rsp+0F0h+var_B8], rcx
0x1800197db  xor     ecx, ecx
0x1800197dd  mov     dword ptr [rsp+0F0h+var_C0], eax
0x1800197e1  mov     [rsp+0F0h+var_C8], rdi
0x1800197e6  mov     dword ptr [rsp+0F0h+var_D0], 1
0x1800197ee  call    FindKeyInCache
0x1800197f3  mov     r14, [rbp+3Fh+lpMem]
0x1800197f7  xor     ecx, ecx
0x1800197f9  mov     rsi, [rbp+3Fh+var_50]
0x1800197fd  test    eax, eax
0x1800197ff  js      short loc_18001980E
0x180019801  mov     r15d, [rbp+3Fh+var_80]
0x180019805  test    r15d, r15d
0x180019808  jnz     loc_1800198E4
0x18001980e  lea     rax, [rbp+3Fh+arg_28]
0x180019812  mov     [rbp+3Fh+var_80], ecx
0x180019815  mov     [rsp+60h], rax; unsigned int *
0x18001981a  mov     r15d, ecx
0x18001981d  lea     rax, [rbp+3Fh+Src]
0x180019821  or      r9d, 0FFFFFFFFh; int
0x180019825  mov     [rsp+0F0h+var_98], rax; unsigned __int8 **
0x18001982a  xor     r8d, r8d; struct _GUID *
0x18001982d  mov     eax, [rbp+3Fh+arg_30]
0x180019830  mov     edx, ebx; unsigned int
0x180019832  mov     [rsp+0F0h+var_A0], rcx; unsigned __int16 *
0x180019837  mov     [rsp+0F0h+var_A8], ecx; unsigned int
0x18001983b  mov     [rsp+0F0h+var_B0], rcx; unsigned __int16 *
0x180019840  mov     rcx, [rbp+3Fh+arg_0]; unsigned __int8 *
0x180019844  mov     [rsp+0F0h+var_B8], eax; unsigned int
0x180019848  mov     eax, [rbp+3Fh+var_7C]
0x18001984b  mov     dword ptr [rsp+0F0h+var_C0], eax; int
0x18001984f  mov     dword ptr [rsp+0F0h+var_C8], 0FFFFFFFFh; int
0x180019857  mov     dword ptr [rsp+0F0h+var_D0], 0FFFFFFFFh; int
0x18001985f  call    ?GetKeyFromKdsService@@YAJPEAEKPEAU_GUID@@JJJHKPEBGK2PEAPEAEPEAK@Z; GetKeyFromKdsService(uchar *,ulong,_GUID *,long,long,long,int,ulong,ushort const *,ulong,ushort const *,uchar * *,ulong *)
0x180019864  mov     ebx, eax
0x180019866  test    eax, eax
0x180019868  jns     short loc_1800198E4
0x18001986a  cmp     eax, 80070005h
0x18001986f  jz      loc_180019945
0x180019875  test    r14, r14
0x180019878  jz      loc_180019945
0x18001987e  test    rsi, rsi
0x180019881  jz      loc_180019945
0x180019887  mov     r9d, dword ptr [rbp+3Fh+var_68]; unsigned int
0x18001988b  lea     rax, [rbp+3Fh+arg_28]
0x18001988f  mov     [rsp+0F0h+var_C0], rax; unsigned int *
0x180019894  mov     r8, rdi; unsigned __int16 *
0x180019897  lea     rax, [rbp+3Fh+Src]
0x18001989b  mov     rdx, rsi; unsigned __int16 *
0x18001989e  mov     [rsp+0F0h+var_C8], rax; struct _SID_KEY_HEADER **
0x1800198a3  xor     ecx, ecx; int
0x1800198a5  lea     rax, [rbp+3Fh+var_80]
0x1800198a9  mov     [rsp+0F0h+var_D0], rax; int *
0x1800198ae  call    ?FindKeyForOfflineUsage@@YAJHPEBG0KPEAHPEAPEAU_SID_KEY_HEADER@@PEAK@Z; FindKeyForOfflineUsage(int,ushort const *,ushort const *,ulong,int *,_SID_KEY_HEADER * *,ulong *)
0x1800198b3  test    eax, eax
0x1800198b5  jns     short loc_1800198DB
0x1800198b7  mov     r9d, 763h; unsigned int
0x1800198bd  lea     rdx, aHrcache; "hrCache"
0x1800198c4  mov     ecx, eax; unsigned int
0x1800198c6  lea     r8, aOnecoreDsSecur_11; "onecore\\ds\\security\\keyman\\sidkeypr"...
0x1800198cd  call    ?SidKeyDebugTraceError@@YAXKPEBD0K@Z; SidKeyDebugTraceError(ulong,char const *,char const *,ulong)
0x1800198d2  mov     rdi, [rbp+3Fh+Src]
0x1800198d6  jmp     loc_1800199F4
0x1800198db  mov     r15d, [rbp+3Fh+var_80]
0x1800198df  test    r15d, r15d
0x1800198e2  jz      short loc_1800198D2
0x1800198e4  mov     rax, [rbp+3Fh+arg_20]
0x1800198e8  mov     r9d, 2
0x1800198ee  mov     rdi, [rbp+3Fh+Src]
0x1800198f2  xor     r8d, r8d
0x1800198f5  mov     edx, [rbp+3Fh+arg_28]
0x1800198f8  mov     rcx, rdi
0x1800198fb  mov     [rsp+0F0h+var_C0], rax
0x180019900  lea     rax, [rbp+3Fh+var_78]
0x180019904  mov     [rsp+0F0h+var_C8], rax
0x180019909  lea     rax, [rbp+3Fh+var_60]
0x18001990d  mov     [rsp+0F0h+var_D0], rax
0x180019912  call    ?GenerateSIDKey@@YAJQEAEKPEAU_KEK_KEY_INFO@@W4_SID_KEY_BLOB_VER@@PEAPEAEPEAKPEAEK@Z; GenerateSIDKey(uchar * const,ulong,_KEK_KEY_INFO *,_SID_KEY_BLOB_VER,uchar * *,ulong *,uchar *,ulong)
0x180019917  mov     ebx, eax
0x180019919  test    eax, eax
0x18001991b  jns     short loc_180019959
0x18001991d  mov     r9d, 780h; unsigned int
0x180019923  lea     r8, aOnecoreDsSecur_11; "onecore\\ds\\security\\keyman\\sidkeypr"...
0x18001992a  lea     rdx, aHr; "hr"
0x180019931  mov     ecx, eax; unsigned int
0x180019933  call    ?SidKeyDebugTraceError@@YAXKPEBD0K@Z; SidKeyDebugTraceError(ulong,char const *,char const *,ulong)
0x180019938  mov     r12, [rbp+3Fh+var_60]
0x18001993c  mov     r13d, [rbp+3Fh+var_78]
0x180019940  jmp     loc_1800199F4
0x180019945  mov     r9d, 770h
0x18001994b  lea     rdx, aHr; "hr"
0x180019952  mov     ecx, ebx
0x180019954  jmp     loc_1800198C6
0x180019959  test    r15d, r15d
0x18001995c  jnz     short loc_1800199A9
0x18001995e  test    r14, r14
0x180019961  jz      short loc_1800199A9
0x180019963  test    rsi, rsi
0x180019966  jz      short loc_1800199A9
0x180019968  mov     r9d, [rbp+3Fh+arg_8]; unsigned int
0x18001996c  mov     rcx, rdi; Src
0x18001996f  mov     r8, [rbp+3Fh+arg_0]; unsigned __int8 *
0x180019973  mov     edx, [rbp+3Fh+arg_28]; unsigned int
0x180019976  mov     [rsp+0F0h+var_C8], r14; unsigned __int16 *
0x18001997b  mov     [rsp+0F0h+var_D0], rsi; unsigned __int16 *
0x180019980  call    ?WriteSIDKeyInCache@@YAJPEAU_SID_KEY_HEADER@@KPEAEKPEBG2@Z; WriteSIDKeyInCache(_SID_KEY_HEADER *,ulong,uchar *,ulong,ushort const *,ushort const *)
0x180019985  mov     ebx, eax
0x180019987  test    eax, eax
0x180019989  jns     short loc_1800199A9
0x18001998b  mov     r9d, 792h; unsigned int
0x180019991  lea     r8, aOnecoreDsSecur_11; "onecore\\ds\\security\\keyman\\sidkeypr"...
0x180019998  lea     rdx, aHr; "hr"
0x18001999f  mov     ecx, eax; unsigned int
0x1800199a1  call    ?SidKeyDebugTraceError@@YAXKPEBD0K@Z; SidKeyDebugTraceError(ulong,char const *,char const *,ulong)
0x1800199a6  mov     ebx, r12d
0x1800199a9  mov     rax, [rbp+3Fh+var_60]
0x1800199ad  mov     rcx, [rbp+3Fh+arg_10]
0x1800199b1  mov     r13d, [rbp+3Fh+var_78]
0x1800199b5  mov     [rcx], rax
0x1800199b8  mov     rax, [rbp+3Fh+arg_18]
0x1800199bc  mov     [rax], r13d
0x1800199bf  mov     rcx, cs:WPP_GLOBAL_Control
0x1800199c6  lea     rax, WPP_GLOBAL_Control
0x1800199cd  cmp     rcx, rax
0x1800199d0  jz      short loc_1800199F4
0x1800199d2  test    byte ptr [rcx+1Ch], 4
0x1800199d6  jz      short loc_1800199F4
0x1800199d8  mov     rcx, [rcx+10h]
0x1800199dc  lea     r8, WPP_b22aa97707d93c78e27dc2ffaf6f95cb_Traceguids
0x1800199e3  mov     edx, 14h
0x1800199e8  call    WPP_SF_
0x1800199ed  jmp     short loc_1800199F4
0x1800199ef  mov     ebx, 80070057h
0x1800199f4  xor     r15d, r15d
0x1800199f7  test    r14, r14
0x1800199fa  jz      short loc_180019A04
0x1800199fc  mov     rcx, r14; lpMem
0x1800199ff  call    ?SIDKeyProvFree@@YAXPEAX@Z; SIDKeyProvFree(void *)
0x180019a04  test    rsi, rsi
0x180019a07  jz      short loc_180019A11
0x180019a09  mov     rcx, rsi; lpMem
0x180019a0c  call    ?SIDKeyProvFree@@YAXPEAX@Z; SIDKeyProvFree(void *)
0x180019a11  test    r12, r12
0x180019a14  jz      short loc_180019A2B
0x180019a16  mov     r8d, r13d; Size
0x180019a19  xor     edx, edx; Val
0x180019a1b  mov     rcx, r12; void *
0x180019a1e  call    memset_0
0x180019a23  mov     rcx, r12; lpMem
0x180019a26  call    ?SIDKeyProvFree@@YAXPEAX@Z; SIDKeyProvFree(void *)
0x180019a2b  test    rdi, rdi
0x180019a2e  jz      short loc_180019A4F
0x180019a30  mov     eax, [rbp+3Fh+arg_28]
0x180019a33  mov     rcx, rdi
0x180019a36  test    rax, rax
0x180019a39  jz      short loc_180019A47
0x180019a3b  mov     [rcx], r15b
0x180019a3e  inc     rcx
0x180019a41  sub     rax, 1
0x180019a45  jnz     short loc_180019A3B
0x180019a47  mov     rcx, rdi; lpMem
0x180019a4a  call    ?SIDKeyProvFree@@YAXPEAX@Z; SIDKeyProvFree(void *)
0x180019a4f  mov     eax, ebx
0x180019a51  add     rsp, 0B8h
0x180019a58  pop     r15
0x180019a5a  pop     r14
0x180019a5c  pop     r13
0x180019a5e  pop     r12
0x180019a60  pop     rdi
0x180019a61  pop     rsi
0x180019a62  pop     rbx
0x180019a63  pop     rbp
0x180019a64  retn
```
