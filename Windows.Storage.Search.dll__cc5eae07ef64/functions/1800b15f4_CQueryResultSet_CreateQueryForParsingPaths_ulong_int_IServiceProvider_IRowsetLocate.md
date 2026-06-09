# CQueryResultSet::_CreateQueryForParsingPaths(ulong *,int,IServiceProvider *,IRowsetLocate * *)

- ea: `0x1800b15f4`
- end: `0x1800b192f`
- name: `?_CreateQueryForParsingPaths@CQueryResultSet@@AEAAJPEAKHPEAUIServiceProvider@@PEAPEAUIRowsetLocate@@@Z`
- size: `827`
- prototype: `__int64 __fastcall(CQueryResultSet *__hidden this, unsigned int *, int, struct IServiceProvider *, struct IRowsetLocate **)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800aa260`

## callees

- `0x180006fb8`
- `0x18001db40`
- `0x180063a68`
- `0x180071dc0`
- `0x1800a9de4`
- `0x1800b15f4`
- `0x1800c08b4`
- `0x1800e4c10`
- `0x1800ea010`

## import_xrefs

- `SHCORE!IUnknown_SetSite` at `0x1800b1692`
- `SHCORE!IUnknown_SetSite` at `0x1800b18bf`
- `SHCORE!IUnknown_SetSite` at `0x1800b1692`
- `SHCORE!IUnknown_SetSite` at `0x1800b18bf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800b18a7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800b18b2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800b18a7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800b18b2`

## string_xrefs

- `0x1800b1804`: `SELECT path FROM "%s".SystemIndex WHERE (%s) AND (%s)`

## pseudocode

```c
__int64 __fastcall CQueryResultSet::_CreateQueryForParsingPaths(
        CQueryResultSet *this,
        unsigned int *a2,
        int a3,
        struct IServiceProvider *a4)
{
  __int64 v4; // rcx
  struct IServiceProvider *v7; // rdx
  int ProviderSession; // ebx
  int v9; // edi
  int v10; // edi
  int v11; // eax
  void *v13; // [rsp+20h] [rbp-E0h]
  IUnknown *punk; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v15; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v16; // [rsp+50h] [rbp-B0h] BYREF
  struct IProviderConfig *v17; // [rsp+58h] [rbp-A8h] BYREF
  LPVOID pv; // [rsp+60h] [rbp-A0h] BYREF
  LPVOID v19; // [rsp+68h] [rbp-98h] BYREF
  int v20[2]; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int16 v21[264]; // [rsp+80h] [rbp-80h] BYREF
  unsigned __int16 v22[2048]; // [rsp+290h] [rbp+190h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+12B8h] [rbp+11B8h]

  v4 = *((_QWORD *)this + 32);
  v17 = 0;
  ProviderSession = (*(__int64 (__fastcall **)(__int64, _QWORD, GUID *, struct IProviderConfig **))(*(_QWORD *)v4 + 32LL))(
                      v4,
                      0,
                      &GUID_b445e1e5_d442_4865_9faf_36a64be62b09,
                      &v17);
  if ( ProviderSession < 0 )
    goto LABEL_25;
  punk = 0;
  ProviderSession = GetProviderSession(v17, v7, (struct IDBCreateCommand **)&punk);
  if ( ProviderSession < 0 )
    goto LABEL_24;
  IUnknown_SetSite(punk, 0);
  ProviderSession = QueryContinueOnSite(0);
  if ( ProviderSession >= 0 )
  {
    pv = 0;
    v19 = 0;
    v15 = 0;
    ProviderSession = (*(__int64 (__fastcall **)(struct IProviderConfig *, GUID *, __int64 *))(*(_QWORD *)v17 + 32LL))(
                        v17,
                        &GUID_71604b0f_97b0_4764_8577_2f13e98a1422,
                        &v15);
    if ( ProviderSession < 0 )
      goto LABEL_22;
    ProviderSession = INamedPropertyStore_GetString(v15, L"MachineName", &pv);
    if ( ProviderSession >= 0 )
      ProviderSession = INamedPropertyStore_GetString(v15, L"Scope", &v19);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
    if ( ProviderSession < 0 )
      goto LABEL_22;
    v16 = 0;
    ProviderSession = ((__int64 (__fastcall *)(IUnknown *, _QWORD, GUID *, __int64 *))punk->lpVtbl[1].QueryInterface)(
                        punk,
                        0,
                        &GUID_0c733a27_2a1c_11ce_ade5_00aa0044773d,
                        &v16);
    if ( ProviderSession >= 0 )
    {
      ProviderSession = QueryContinueOnSite(0);
      if ( ProviderSession >= 0 )
      {
        v9 = a3 - 1;
        if ( v9 )
        {
          v10 = v9 - 1;
          if ( v10 )
          {
            if ( v10 != 1 )
            {
              ProviderSession = -2147024809;
              goto LABEL_21;
            }
            LODWORD(v13) = a2[1];
            v11 = StringCchPrintfW(v21, 0x104u, L"(workid=%d) or (workid=%d) or (workid=%d)", *a2);
          }
          else
          {
            LODWORD(v13) = a2[1];
            v11 = StringCchPrintfW(v21, 0x104u, L"(workid=%d) or (workid=%d)", *a2);
          }
        }
        else
        {
          v11 = StringCchPrintfW(v21, 0x104u, L"(workid=%d)", *a2);
        }
        ProviderSession = v11;
        if ( v11 >= 0 )
        {
          v13 = v21;
          ProviderSession = StringCchPrintfW(
                              v22,
                              0x800u,
                              L"SELECT path FROM \"%s\".SystemIndex WHERE (%s) AND (%s)",
                              pv);
          if ( ProviderSession >= 0 )
          {
            ProviderSession = (*(__int64 (__fastcall **)(__int64, const GUID *, unsigned __int16 *))(*(_QWORD *)v16 + 56LL))(
                                v16,
                                &DBGUID_DEFAULT,
                                v22);
            if ( ProviderSession >= 0 )
            {
              *(_QWORD *)v20 = 0;
              v13 = v20;
              ProviderSession = (*(__int64 (__fastcall **)(__int64, _QWORD, GUID *, _QWORD))(*(_QWORD *)v16 + 32LL))(
                                  v16,
                                  0,
                                  &IID_IRowsetLocate,
                                  0);
            }
          }
        }
      }
    }
LABEL_21:
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
LABEL_22:
    CoTaskMemFree(pv);
    CoTaskMemFree(v19);
  }
  IUnknown_SetSite(punk, 0);
  ((void (__fastcall *)(IUnknown *))punk->lpVtbl->Release)(punk);
LABEL_24:
  (*(void (__fastcall **)(struct IProviderConfig *))(*(_QWORD *)v17 + 16LL))(v17);
  if ( ProviderSession < 0 )
LABEL_25:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x13B5,
      (unsigned int)"onecoreuap\\shell\\windows.storage.search\\resultsetfactory.cpp",
      (const char *)(unsigned int)ProviderSession,
      (int)v13);
  return (unsigned int)ProviderSession;
}

```

## disassembly

```asm
0x1800b15f4  mov     [rsp-8+arg_10], rbx
0x1800b15f9  mov     [rsp-8+arg_18], rsi
0x1800b15fe  push    rbp
0x1800b15ff  push    rdi
0x1800b1600  push    r14
0x1800b1602  lea     rbp, [rsp-11A0h]
0x1800b160a  mov     eax, 12A0h
0x1800b160f  call    _alloca_probe
0x1800b1614  sub     rsp, rax
0x1800b1617  mov     rax, cs:__security_cookie
0x1800b161e  xor     rax, rsp
0x1800b1621  mov     [rbp+11B0h+var_20], rax
0x1800b1628  mov     rcx, [rcx+100h]
0x1800b162f  lea     r9, [rsp+12B0h+var_1258]
0x1800b1634  mov     r14, [rbp+11B0h+arg_20]
0x1800b163b  mov     edi, r8d
0x1800b163e  mov     [rsp+12B0h+var_1258], 0
0x1800b1647  lea     r8, _GUID_b445e1e5_d442_4865_9faf_36a64be62b09
0x1800b164e  mov     rsi, rdx
0x1800b1651  xor     edx, edx
0x1800b1653  mov     rax, [rcx]
0x1800b1656  mov     rax, [rax+20h]
0x1800b165a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b165f  mov     ebx, eax
0x1800b1661  test    eax, eax
0x1800b1663  js      loc_1800B18EB
0x1800b1669  mov     rcx, [rsp+12B0h+var_1258]; struct IProviderConfig *
0x1800b166e  lea     r8, [rsp+12B0h+punk]; struct IDBCreateCommand **
0x1800b1673  mov     [rsp+12B0h+punk], 0
0x1800b167c  call    ?GetProviderSession@@YAJPEAUIProviderConfig@@PEAUIServiceProvider@@PEAPEAUIDBCreateCommand@@@Z; GetProviderSession(IProviderConfig *,IServiceProvider *,IDBCreateCommand * *)
0x1800b1681  mov     ebx, eax
0x1800b1683  test    eax, eax
0x1800b1685  js      loc_1800B18D6
0x1800b168b  mov     rcx, [rsp+12B0h+punk]; punk
0x1800b1690  xor     edx, edx; punkSite
0x1800b1692  call    cs:__imp_IUnknown_SetSite
0x1800b1698  xor     ecx, ecx; struct IUnknown *
0x1800b169a  call    ?QueryContinueOnSite@@YAJPEAUIUnknown@@@Z; QueryContinueOnSite(IUnknown *)
0x1800b169f  mov     ebx, eax
0x1800b16a1  test    eax, eax
0x1800b16a3  js      loc_1800B18B8
0x1800b16a9  mov     rcx, [rsp+12B0h+var_1258]
0x1800b16ae  lea     r8, [rsp+12B0h+var_1268]
0x1800b16b3  mov     [rsp+12B0h+pv], 0
0x1800b16bc  lea     rdx, _GUID_71604b0f_97b0_4764_8577_2f13e98a1422
0x1800b16c3  mov     [rsp+12B0h+var_1248], 0
0x1800b16cc  mov     [rsp+12B0h+var_1268], 0
0x1800b16d5  mov     rax, [rcx]
0x1800b16d8  mov     rax, [rax+20h]
0x1800b16dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b16e1  mov     ebx, eax
0x1800b16e3  test    eax, eax
0x1800b16e5  js      loc_1800B18A2
0x1800b16eb  mov     rcx, [rsp+12B0h+var_1268]
0x1800b16f0  lea     r8, [rsp+12B0h+pv]
0x1800b16f5  lea     rdx, aMachinename; "MachineName"
0x1800b16fc  call    INamedPropertyStore_GetString
0x1800b1701  mov     ebx, eax
0x1800b1703  test    eax, eax
0x1800b1705  js      short loc_1800B171F
0x1800b1707  mov     rcx, [rsp+12B0h+var_1268]
0x1800b170c  lea     r8, [rsp+12B0h+var_1248]
0x1800b1711  lea     rdx, aScope_0; "Scope"
0x1800b1718  call    INamedPropertyStore_GetString
0x1800b171d  mov     ebx, eax
0x1800b171f  mov     rcx, [rsp+12B0h+var_1268]
0x1800b1724  mov     rax, [rcx]
0x1800b1727  mov     rax, [rax+10h]
0x1800b172b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b1730  test    ebx, ebx
0x1800b1732  js      loc_1800B18A2
0x1800b1738  mov     rcx, [rsp+12B0h+punk]
0x1800b173d  lea     r9, [rsp+12B0h+var_1260]
0x1800b1742  mov     [rsp+12B0h+var_1260], 0
0x1800b174b  lea     r8, _GUID_0c733a27_2a1c_11ce_ade5_00aa0044773d
0x1800b1752  xor     edx, edx
0x1800b1754  mov     rax, [rcx]
0x1800b1757  mov     rax, [rax+18h]
0x1800b175b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b1760  mov     ebx, eax
0x1800b1762  test    eax, eax
0x1800b1764  js      loc_1800B1891
0x1800b176a  xor     ecx, ecx; struct IUnknown *
0x1800b176c  call    ?QueryContinueOnSite@@YAJPEAUIUnknown@@@Z; QueryContinueOnSite(IUnknown *)
0x1800b1771  mov     ebx, eax
0x1800b1773  test    eax, eax
0x1800b1775  js      loc_1800B1891
0x1800b177b  sub     edi, 1
0x1800b177e  jz      short loc_1800B17DD
0x1800b1780  sub     edi, 1
0x1800b1783  jz      short loc_1800B17BC
0x1800b1785  cmp     edi, 1
0x1800b1788  jz      short loc_1800B1794
0x1800b178a  mov     ebx, 80070057h
0x1800b178f  jmp     loc_1800B1891
0x1800b1794  mov     eax, [rsi+8]
0x1800b1797  lea     r8, aWorkidDOrWorki_0; "(workid=%d) or (workid=%d) or (workid=%"...
0x1800b179e  mov     r9d, [rsi]
0x1800b17a1  lea     rcx, [rbp+11B0h+var_1230]; unsigned __int16 *
0x1800b17a5  mov     dword ptr [rsp+12B0h+var_1288], eax
0x1800b17a9  mov     edx, 104h; unsigned __int64
0x1800b17ae  mov     eax, [rsi+4]
0x1800b17b1  mov     [rsp+12B0h+var_1290], eax
0x1800b17b5  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800b17ba  jmp     short loc_1800B17F5
0x1800b17bc  mov     eax, [rsi+4]
0x1800b17bf  lea     r8, aWorkidDOrWorki; "(workid=%d) or (workid=%d)"
0x1800b17c6  mov     r9d, [rsi]
0x1800b17c9  lea     rcx, [rbp+11B0h+var_1230]; unsigned __int16 *
0x1800b17cd  mov     edx, 104h; unsigned __int64
0x1800b17d2  mov     [rsp+12B0h+var_1290], eax
0x1800b17d6  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800b17db  jmp     short loc_1800B17F5
0x1800b17dd  mov     r9d, [rsi]
0x1800b17e0  lea     r8, aWorkidD; "(workid=%d)"
0x1800b17e7  mov     edx, 104h; unsigned __int64
0x1800b17ec  lea     rcx, [rbp+11B0h+var_1230]; unsigned __int16 *
0x1800b17f0  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800b17f5  mov     ebx, eax
0x1800b17f7  test    eax, eax
0x1800b17f9  js      loc_1800B1891
0x1800b17ff  mov     rax, [rsp+12B0h+var_1248]
0x1800b1804  lea     r8, aSelectPathFrom; "SELECT path FROM \"%s\".SystemIndex WHE"...
0x1800b180b  mov     r9, [rsp+12B0h+pv]
0x1800b1810  lea     rcx, [rbp+11B0h+var_1020]; unsigned __int16 *
0x1800b1817  mov     [rsp+12B0h+var_1288], rax
0x1800b181c  mov     edx, 800h; unsigned __int64
0x1800b1821  lea     rax, [rbp+11B0h+var_1230]
0x1800b1825  mov     qword ptr [rsp+12B0h+var_1290], rax
0x1800b182a  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800b182f  mov     ebx, eax
0x1800b1831  test    eax, eax
0x1800b1833  js      short loc_1800B1891
0x1800b1835  mov     rcx, [rsp+12B0h+var_1260]
0x1800b183a  lea     r8, [rbp+11B0h+var_1020]
0x1800b1841  lea     rdx, DBGUID_DEFAULT
0x1800b1848  mov     rax, [rcx]
0x1800b184b  mov     rax, [rax+38h]
0x1800b184f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b1854  mov     ebx, eax
0x1800b1856  test    eax, eax
0x1800b1858  js      short loc_1800B1891
0x1800b185a  mov     rcx, [rsp+12B0h+var_1260]
0x1800b185f  lea     rdx, [rsp+12B0h+var_1240]
0x1800b1864  mov     qword ptr [rsp+12B0h+var_1240], 0
0x1800b186d  lea     r8, IID_IRowsetLocate
0x1800b1874  mov     [rsp+12B0h+var_1288], r14
0x1800b1879  xor     r9d, r9d
0x1800b187c  mov     qword ptr [rsp+12B0h+var_1290], rdx; int
0x1800b1881  xor     edx, edx
0x1800b1883  mov     rax, [rcx]
0x1800b1886  mov     rax, [rax+20h]
0x1800b188a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b188f  mov     ebx, eax
0x1800b1891  mov     rcx, [rsp+12B0h+var_1260]
0x1800b1896  mov     rax, [rcx]
0x1800b1899  mov     rax, [rax+10h]
0x1800b189d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b18a2  mov     rcx, [rsp+12B0h+pv]; pv
0x1800b18a7  call    cs:__imp_CoTaskMemFree
0x1800b18ad  mov     rcx, [rsp+12B0h+var_1248]; pv
0x1800b18b2  call    cs:__imp_CoTaskMemFree
0x1800b18b8  mov     rcx, [rsp+12B0h+punk]; punk
0x1800b18bd  xor     edx, edx; punkSite
0x1800b18bf  call    cs:__imp_IUnknown_SetSite
0x1800b18c5  mov     rcx, [rsp+12B0h+punk]
0x1800b18ca  mov     rax, [rcx]
0x1800b18cd  mov     rax, [rax+10h]
0x1800b18d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b18d6  mov     rcx, [rsp+12B0h+var_1258]
0x1800b18db  mov     rax, [rcx]
0x1800b18de  mov     rax, [rax+10h]
0x1800b18e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b18e7  test    ebx, ebx
0x1800b18e9  jns     short loc_1800B1906
0x1800b18eb  mov     rcx, [rbp+11B8h]; this
0x1800b18f2  lea     r8, aOnecoreuapShel_21; "onecoreuap\\shell\\windows.storage.sear"...
0x1800b18f9  mov     r9d, ebx; char *
0x1800b18fc  mov     edx, 13B5h; void *
0x1800b1901  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b1906  mov     eax, ebx
0x1800b1908  mov     rcx, [rbp+11B0h+var_20]
0x1800b190f  xor     rcx, rsp; StackCookie
0x1800b1912  call    __security_check_cookie
0x1800b1917  lea     r11, [rsp+12B0h+var_10]
0x1800b191f  mov     rbx, [r11+30h]
0x1800b1923  mov     rsi, [r11+38h]
0x1800b1927  mov     rsp, r11
0x1800b192a  pop     r14
0x1800b192c  pop     rdi
0x1800b192d  pop     rbp
0x1800b192e  retn
```
