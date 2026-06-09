# GetSIDKeyLdapWorker(_SECURITY_DESCRIPTOR *,ulong,ulong,ulong,_GUID *,ulong,ulong,ulong,int,uchar * *,ulong *)

- ea: `0x180008eb4`
- end: `0x180009141`
- name: `?GetSIDKeyLdapWorker@@YAJPEAU_SECURITY_DESCRIPTOR@@KKKPEAU_GUID@@KKKHPEAPEAEPEAK@Z`
- size: `653`
- prototype: `int(struct _SECURITY_DESCRIPTOR *, unsigned int, unsigned int, unsigned int, struct _GUID *, unsigned int, unsigned int, unsigned int, int, unsigned __int8 **, unsigned int *)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180009828`

## callees

- `0x180001630`
- `0x180004d5c`
- `0x180007e98`
- `0x1800080e8`
- `0x180008240`
- `0x180008528`
- `0x18000898c`
- `0x180008eb4`
- `0x180009148`
- `0x180010270`
- `0x180010950`
- `0x18001a450`

## import_xrefs

- `WLDAP32!__imp_ldap_unbind` at `0x18000911b`
- `WLDAP32!__imp_ldap_unbind` at `0x18000911b`

## string_xrefs

- `0x180008f4e`: `onecore\ds\security\keyman\sidkeyprov\kdscli\sidkeyldap.cxx`
- `0x18000905f`: `onecore\ds\security\keyman\sidkeyprov\kdscli\sidkeyldap.cxx`
- `0x1800090d6`: `onecore\ds\security\keyman\sidkeyprov\kdscli\sidkeyldap.cxx`

## pseudocode

```c
__int64 __fastcall GetSIDKeyLdapWorker(
        struct _SECURITY_DESCRIPTOR *a1,
        unsigned int a2,
        ULONG a3,
        unsigned int a4,
        struct _GUID *a5,
        unsigned int a6,
        unsigned int a7,
        unsigned int a8,
        int a9,
        unsigned __int8 **a10,
        unsigned int *a11)
{
  void *v11; // rdi
  unsigned __int64 v12; // rsi
  signed int SnapshotBrowserLdapBinding; // eax
  unsigned int v15; // ebx
  unsigned int v16; // r9d
  signed int L0Key; // eax
  struct _L0_key *v18; // rsi
  unsigned int v19; // r9d
  signed int v20; // eax
  size_t v22; // [rsp+40h] [rbp-C0h]
  size_t v23; // [rsp+60h] [rbp-A0h] BYREF
  LDAP *ld; // [rsp+68h] [rbp-98h] BYREF
  unsigned int v25; // [rsp+70h] [rbp-90h]
  void *lpMem; // [rsp+78h] [rbp-88h] BYREF
  struct _AD_LDAP_BROWSER_STATE *v27; // [rsp+80h] [rbp-80h] BYREF
  unsigned __int64 v28; // [rsp+88h] [rbp-78h] BYREF
  struct _L0_key *v29; // [rsp+90h] [rbp-70h] BYREF
  UUID *Uuid; // [rsp+98h] [rbp-68h]
  unsigned __int8 *p_Revision; // [rsp+A0h] [rbp-60h]
  unsigned int *v32; // [rsp+A8h] [rbp-58h]
  unsigned __int8 **v33; // [rsp+B0h] [rbp-50h]
  unsigned __int8 v34[64]; // [rsp+C0h] [rbp-40h] BYREF
  unsigned __int8 v35[64]; // [rsp+100h] [rbp+0h] BYREF

  p_Revision = &a1->Revision;
  Uuid = a5;
  v11 = 0;
  v12 = 0;
  v25 = a2;
  v33 = a10;
  *a10 = 0;
  v32 = a11;
  *a11 = 0;
  lpMem = 0;
  ld = 0;
  LODWORD(v23) = 0;
  v29 = 0;
  v28 = 0;
  v27 = 0;
  SnapshotBrowserLdapBinding = GetSnapshotBrowserLdapBinding(a3, &v27, &ld);
  v15 = SnapshotBrowserLdapBinding;
  if ( SnapshotBrowserLdapBinding < 0 )
  {
    v16 = 1772;
LABEL_3:
    SidKeyDebugTraceError(
      SnapshotBrowserLdapBinding,
      "hr",
      "onecore\\ds\\security\\keyman\\sidkeyprov\\kdscli\\sidkeyldap.cxx",
      v16);
    goto LABEL_23;
  }
  if ( a4 - 1 <= 1 )
  {
    SnapshotBrowserLdapBinding = GetIntervalStartTime(0x53D1AC1000uLL, a6, a7, a8, &v28);
    v15 = SnapshotBrowserLdapBinding;
    if ( SnapshotBrowserLdapBinding < 0 )
    {
      v16 = 1788;
      goto LABEL_3;
    }
    v12 = v28;
  }
  L0Key = GetL0Key(ld, Uuid, a6, a4, v12, &v29);
  v18 = v29;
  v15 = L0Key;
  if ( L0Key < 0 )
  {
    v19 = 1803;
LABEL_18:
    SidKeyDebugTraceError(L0Key, "hr", "onecore\\ds\\security\\keyman\\sidkeyprov\\kdscli\\sidkeyldap.cxx", v19);
    goto LABEL_19;
  }
  L0Key = ComputeSIDPrivateKeyLdap(v29, p_Revision, v25, a7, a8, a9, v34, v35);
  v15 = L0Key;
  if ( L0Key < 0 )
  {
    v19 = 1819;
    goto LABEL_18;
  }
  if ( a9 )
  {
    v20 = ComputeSIDPubKeyLdap(v18, v35, (unsigned __int8 **)&lpMem, (unsigned int *)&v23);
    v15 = v20;
    if ( v20 < 0 )
    {
      SidKeyDebugTraceError(v20, "hr", "onecore\\ds\\security\\keyman\\sidkeyprov\\kdscli\\sidkeyldap.cxx", 0x729u);
      v11 = lpMem;
      goto LABEL_19;
    }
    v11 = lpMem;
  }
  LODWORD(v22) = v23;
  L0Key = FormatReturnBlobLdap(
            *((unsigned __int16 **)v27 + 4),
            *((unsigned __int16 **)v27 + 5),
            v18,
            v34,
            a7,
            v35,
            a8,
            (size_t)v11,
            v22,
            v33,
            v32);
  v15 = L0Key;
  if ( L0Key < 0 )
  {
    v19 = 1853;
    goto LABEL_18;
  }
LABEL_19:
  if ( v18 )
    FreeL0Key(v18);
  if ( v11 )
    SIDKeyProvFree(v11);
LABEL_23:
  FreeLdapBrowserState(v27);
  if ( ld )
    ldap_unbind(ld);
  return v15;
}

```

## disassembly

```asm
0x180008eb4  push    rbp
0x180008eb6  push    rbx
0x180008eb7  push    rsi
0x180008eb8  push    rdi
0x180008eb9  push    r12
0x180008ebb  push    r13
0x180008ebd  push    r14
0x180008ebf  lea     rbp, [rsp-50h]
0x180008ec4  sub     rsp, 150h
0x180008ecb  mov     rax, cs:__security_cookie
0x180008ed2  xor     rax, rsp
0x180008ed5  mov     [rbp+80h+var_40], rax
0x180008ed9  mov     [rbp+80h+var_E0], rcx
0x180008edd  mov     eax, r8d
0x180008ee0  mov     rcx, [rbp+80h+arg_20]
0x180008ee7  xor     r8d, r8d
0x180008eea  mov     [rbp+80h+Uuid], rcx
0x180008eee  mov     edi, r8d
0x180008ef1  mov     rcx, [rbp+80h+arg_48]
0x180008ef8  mov     esi, r8d
0x180008efb  mov     [rsp+180h+var_110], edx
0x180008eff  mov     r14d, r9d
0x180008f02  mov     rdx, [rbp+80h+arg_50]
0x180008f09  mov     [rbp+80h+var_D0], rcx
0x180008f0d  mov     [rcx], r8
0x180008f10  mov     ecx, eax; PortNumber
0x180008f12  mov     [rbp+80h+var_D8], rdx
0x180008f16  mov     [rdx], r8d
0x180008f19  lea     rdx, [rbp+80h+var_100]; struct _AD_LDAP_BROWSER_STATE **
0x180008f1d  mov     [rsp+180h+lpMem], r8
0x180008f22  mov     [rsp+180h+ld], r8
0x180008f27  mov     dword ptr [rsp+180h+var_120], r8d
0x180008f2c  mov     [rbp+80h+var_F0], r8
0x180008f30  mov     [rbp+80h+var_F8], r8
0x180008f34  mov     [rbp+80h+var_100], r8
0x180008f38  lea     r8, [rsp+180h+ld]; struct ldap **
0x180008f3d  call    ?GetSnapshotBrowserLdapBinding@@YAJKPEAPEAU_AD_LDAP_BROWSER_STATE@@PEAPEAUldap@@@Z; GetSnapshotBrowserLdapBinding(ulong,_AD_LDAP_BROWSER_STATE * *,ldap * *)
0x180008f42  mov     ebx, eax
0x180008f44  test    eax, eax
0x180008f46  jns     short loc_180008F68
0x180008f48  mov     r9d, 6ECh; unsigned int
0x180008f4e  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\keyman\\sidkeypr"...
0x180008f55  mov     ecx, eax; unsigned int
0x180008f57  lea     rdx, aHr; "hr"
0x180008f5e  call    ?SidKeyDebugTraceError@@YAXKPEBD0K@Z; SidKeyDebugTraceError(ulong,char const *,char const *,ulong)
0x180008f63  jmp     loc_180009105
0x180008f68  mov     r12d, [rbp+80h+arg_38]
0x180008f6f  lea     eax, [r14-1]
0x180008f73  mov     r13d, [rbp+80h+arg_30]
0x180008f7a  cmp     eax, 1
0x180008f7d  ja      short loc_180008FB5
0x180008f7f  mov     edx, [rbp+80h+arg_28]; unsigned int
0x180008f85  lea     rax, [rbp+80h+var_F8]
0x180008f89  mov     r9d, r12d; unsigned int
0x180008f8c  mov     [rsp+180h+var_160], rax; unsigned __int64 *
0x180008f91  mov     r8d, r13d; unsigned int
0x180008f94  mov     rcx, 53D1AC1000h; unsigned __int64
0x180008f9e  call    ?GetIntervalStartTime@@YAJ_KKKKPEA_K@Z; GetIntervalStartTime(unsigned __int64,ulong,ulong,ulong,unsigned __int64 *)
0x180008fa3  mov     ebx, eax
0x180008fa5  test    eax, eax
0x180008fa7  jns     short loc_180008FB1
0x180008fa9  mov     r9d, 6FCh
0x180008faf  jmp     short loc_180008F4E
0x180008fb1  mov     rsi, [rbp+80h+var_F8]
0x180008fb5  mov     r8d, [rbp+80h+arg_28]; unsigned int
0x180008fbc  lea     rax, [rbp+80h+var_F0]
0x180008fc0  mov     rdx, [rbp+80h+Uuid]; Uuid
0x180008fc4  mov     r9d, r14d; unsigned int
0x180008fc7  mov     rcx, [rsp+180h+ld]; struct ldap *
0x180008fcc  mov     [rsp+180h+var_158], rax; struct _L0_key **
0x180008fd1  mov     [rsp+180h+var_160], rsi; unsigned __int64
0x180008fd6  call    ?GetL0Key@@YAJPEAUldap@@PEAU_GUID@@KK_KPEAPEAU_L0_key@@@Z; GetL0Key(ldap *,_GUID *,ulong,ulong,unsigned __int64,_L0_key * *)
0x180008fdb  mov     rsi, [rbp+80h+var_F0]
0x180008fdf  mov     ebx, eax
0x180008fe1  test    eax, eax
0x180008fe3  jns     short loc_180008FF0
0x180008fe5  mov     r9d, 70Bh
0x180008feb  jmp     loc_1800090D6
0x180008ff0  mov     r14d, [rbp+80h+arg_40]
0x180008ff7  lea     rax, [rbp+80h+var_80]
0x180008ffb  mov     r8d, [rsp+180h+var_110]; unsigned int
0x180009000  mov     r9d, r13d; unsigned int
0x180009003  mov     rdx, [rbp+80h+var_E0]; unsigned __int8 *
0x180009007  mov     rcx, rsi; struct _L0_key *
0x18000900a  mov     [rsp+180h+var_148], rax; unsigned __int8 *
0x18000900f  lea     rax, [rbp+80h+var_C0]
0x180009013  mov     [rsp+180h+var_150], rax; unsigned __int8 *
0x180009018  mov     dword ptr [rsp+180h+var_158], r14d; int
0x18000901d  mov     dword ptr [rsp+180h+var_160], r12d; unsigned int
0x180009022  call    ?ComputeSIDPrivateKeyLdap@@YAJPEAU_L0_key@@PEAEKKKHQEAE2@Z; ComputeSIDPrivateKeyLdap(_L0_key *,uchar *,ulong,ulong,ulong,int,uchar * const,uchar * const)
0x180009027  mov     ebx, eax
0x180009029  test    eax, eax
0x18000902b  jns     short loc_180009038
0x18000902d  mov     r9d, 71Bh
0x180009033  jmp     loc_1800090D6
0x180009038  test    r14d, r14d
0x18000903b  jz      short loc_180009080
0x18000903d  lea     r9, [rsp+180h+var_120]; unsigned int *
0x180009042  mov     rcx, rsi; struct _L0_key *
0x180009045  lea     r8, [rsp+180h+lpMem]; unsigned __int8 **
0x18000904a  lea     rdx, [rbp+80h+var_80]; unsigned __int8 *
0x18000904e  call    ?ComputeSIDPubKeyLdap@@YAJPEAU_L0_key@@QEAEPEAPEAEPEAK@Z; ComputeSIDPubKeyLdap(_L0_key *,uchar * const,uchar * *,ulong *)
0x180009053  mov     ebx, eax
0x180009055  test    eax, eax
0x180009057  jns     short loc_18000907B
0x180009059  mov     r9d, 729h; unsigned int
0x18000905f  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\keyman\\sidkeypr"...
0x180009066  lea     rdx, aHr; "hr"
0x18000906d  mov     ecx, eax; unsigned int
0x18000906f  call    ?SidKeyDebugTraceError@@YAXKPEBD0K@Z; SidKeyDebugTraceError(ulong,char const *,char const *,ulong)
0x180009074  mov     rdi, [rsp+180h+lpMem]
0x180009079  jmp     short loc_1800090EB
0x18000907b  mov     rdi, [rsp+180h+lpMem]
0x180009080  mov     rax, [rbp+80h+var_D8]
0x180009084  lea     r9, [rbp+80h+var_C0]; unsigned __int8 *
0x180009088  mov     [rsp+180h+var_130], rax; unsigned int *
0x18000908d  mov     r8, rsi; struct _L0_key *
0x180009090  mov     rax, [rbp+80h+var_D0]
0x180009094  mov     [rsp+180h+var_138], rax; unsigned __int8 **
0x180009099  mov     eax, dword ptr [rsp+180h+var_120]
0x18000909d  mov     dword ptr [rsp+180h+var_140], eax; size_t
0x1800090a1  lea     rax, [rbp+80h+var_80]
0x1800090a5  mov     [rsp+180h+var_148], rdi; size_t
0x1800090aa  mov     dword ptr [rsp+180h+var_150], r12d; unsigned int
0x1800090af  mov     [rsp+180h+var_158], rax; unsigned __int8 *
0x1800090b4  mov     rax, [rbp+80h+var_100]
0x1800090b8  mov     dword ptr [rsp+180h+var_160], r13d; unsigned int
0x1800090bd  mov     rdx, [rax+28h]; unsigned __int16 *
0x1800090c1  mov     rcx, [rax+20h]; unsigned __int16 *
0x1800090c5  call    ?FormatReturnBlobLdap@@YAJPEAG0PEAU_L0_key@@QEAEK2KPEAEKPEAPEAEPEAK@Z; FormatReturnBlobLdap(ushort *,ushort *,_L0_key *,uchar * const,ulong,uchar * const,ulong,uchar *,ulong,uchar * *,ulong *)
0x1800090ca  mov     ebx, eax
0x1800090cc  test    eax, eax
0x1800090ce  jns     short loc_1800090EB
0x1800090d0  mov     r9d, 73Dh; unsigned int
0x1800090d6  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\keyman\\sidkeypr"...
0x1800090dd  mov     ecx, eax; unsigned int
0x1800090df  lea     rdx, aHr; "hr"
0x1800090e6  call    ?SidKeyDebugTraceError@@YAXKPEBD0K@Z; SidKeyDebugTraceError(ulong,char const *,char const *,ulong)
0x1800090eb  test    rsi, rsi
0x1800090ee  jz      short loc_1800090F8
0x1800090f0  mov     rcx, rsi; lpMem
0x1800090f3  call    ?FreeL0Key@@YAXPEAU_L0_key@@@Z; FreeL0Key(_L0_key *)
0x1800090f8  test    rdi, rdi
0x1800090fb  jz      short loc_180009105
0x1800090fd  mov     rcx, rdi; lpMem
0x180009100  call    ?SIDKeyProvFree@@YAXPEAX@Z; SIDKeyProvFree(void *)
0x180009105  mov     rcx, [rbp+80h+var_100]; struct _AD_LDAP_BROWSER_STATE *
0x180009109  call    ?FreeLdapBrowserState@@YAXPEAU_AD_LDAP_BROWSER_STATE@@@Z; FreeLdapBrowserState(_AD_LDAP_BROWSER_STATE *)
0x18000910e  cmp     [rsp+180h+ld], 0
0x180009114  jz      short loc_180009121
0x180009116  mov     rcx, [rsp+180h+ld]; ld
0x18000911b  call    cs:__imp_ldap_unbind
0x180009121  mov     eax, ebx
0x180009123  mov     rcx, [rbp+80h+var_40]
0x180009127  xor     rcx, rsp; StackCookie
0x18000912a  call    __security_check_cookie
0x18000912f  add     rsp, 150h
0x180009136  pop     r14
0x180009138  pop     r13
0x18000913a  pop     r12
0x18000913c  pop     rdi
0x18000913d  pop     rsi
0x18000913e  pop     rbx
0x18000913f  pop     rbp
0x180009140  retn
```
