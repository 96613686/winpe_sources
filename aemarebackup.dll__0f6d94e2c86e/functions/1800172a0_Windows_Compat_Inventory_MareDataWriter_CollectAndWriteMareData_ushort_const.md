# Windows::Compat::Inventory::MareDataWriter::CollectAndWriteMareData(ushort const *)

- ea: `0x1800172a0`
- end: `0x18001758a`
- name: `?CollectAndWriteMareData@MareDataWriter@Inventory@Compat@Windows@@SAJPEBG@Z`
- size: `746`
- prototype: `__int64 __fastcall(const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `19`
- tags: `file_ops, registry_config, installer_update, broker_com_uri`

## callers

- `0x180026a18`

## callees

- `0x180004ea0`
- `0x18000529c`
- `0x180006d30`
- `0x180012618`
- `0x180013e2c`
- `0x180013f64`
- `0x180015030`
- `0x180015840`
- `0x180015fd0`
- `0x1800172a0`
- `0x180017778`
- `0x18001e508`
- `0x1800219d8`
- `0x180022014`
- `0x1800257a8`
- `0x180025a20`
- `0x180026774`
- `0x18002b1e0`
- `0x18004c020`

## string_xrefs

- `0x180017381`: `MareDataWriter::QueryOneSettings failed [%#x]`
- `0x180017372`: `Windows::Compat::Inventory::MareDataWriter::CollectAndWriteMareData`
- `0x1800173e8`: `MareDataWriter::UpdateCacheBeforeCollection failed [%#x]`
- `0x180017451`: `MareDataWriter::CollectMareData failed [%#x]`
- `0x18001748f`: `MareDataWriter::UpdateCacheAfterCollection failed [%#x]`
- `0x1800174cd`: `MareDataWriter::CreateDataFiles failed [%#x]`
- `0x18001750e`: `MareDataWriter::WriteDataFiles failed [%#x]`

## pseudocode

```c
__int64 __fastcall Windows::Compat::Inventory::MareDataWriter::CollectAndWriteMareData(const unsigned __int16 *a1)
{
  Windows::Compat::Inventory::InventoryWatchdog *v1; // rax
  Windows::Compat::Inventory::InventoryWatchdog *v2; // rbx
  int v3; // eax
  int updated; // eax
  int v5; // edi
  int v6; // esi
  int v7; // edi
  int v8; // eax
  int v9; // edi
  int DataFiles; // eax
  int v11; // eax
  bool v13; // [rsp+30h] [rbp-D0h] BYREF
  bool v14; // [rsp+31h] [rbp-CFh] BYREF
  unsigned int v15; // [rsp+34h] [rbp-CCh] BYREF
  unsigned __int64 v16[3]; // [rsp+38h] [rbp-C8h] BYREF
  _BYTE v17[368]; // [rsp+50h] [rbp-B0h] BYREF

  Windows::Compat::Inventory::MareDataWriter::MareDataWriter((Windows::Compat::Inventory::MareDataWriter *)v17, a1);
  v16[1] = 0;
  v1 = (Windows::Compat::Inventory::InventoryWatchdog *)operator new(
                                                          0x40u,
                                                          (const struct std::nothrow_t *)&std::nothrow);
  v2 = v1;
  if ( v1 )
  {
    *(_DWORD *)v1 = 60000;
    *((_QWORD *)v1 + 1) = 0;
    *((_QWORD *)v1 + 2) = 0;
    *((_QWORD *)v1 + 3) = 0;
    *((_QWORD *)v1 + 4) = 0;
    *((_QWORD *)v1 + 5) = 0;
    *((_QWORD *)v1 + 6) = 0;
    *((_QWORD *)v1 + 7) = 0;
  }
  else
  {
    v2 = 0;
  }
  v16[2] = (unsigned __int64)v2;
  if ( v2 )
    Windows::Compat::Inventory::InventoryWatchdog::Initialize(v2);
  v14 = 0;
  v13 = 0;
  v16[0] = 0;
  v15 = 0;
  v3 = Windows::Compat::Inventory::MareDataWriter::QueryOneSettings(
         (Windows::Compat::Inventory::MareDataWriter *)v17,
         &v14,
         v16,
         &v15,
         &v13);
  if ( v3 < 0 )
    AslLogCallPrintf(
      3,
      "Windows::Compat::Inventory::MareDataWriter::CollectAndWriteMareData",
      61,
      "MareDataWriter::QueryOneSettings failed [%#x]",
      v3);
  if ( v16[0] )
    Windows::Compat::Inventory::MareApplication::s_defaultFarAttributes = v16[0] | 2;
  if ( v13 )
    Windows::Compat::Inventory::MareApplication::s_keepHiddenArps = 1;
  if ( v2 )
    Windows::Compat::Inventory::InventoryWatchdog::RenewTimer(v2);
  updated = Windows::Compat::Inventory::MareDataWriter::UpdateCacheBeforeCollection(
              (Windows::Compat::Inventory::MareDataWriter *)v17,
              v14);
  v5 = updated;
  if ( updated >= 0 )
  {
    v6 = 0;
    if ( updated == 1 )
      goto LABEL_39;
  }
  else
  {
    AslLogCallPrintf(
      1,
      "Windows::Compat::Inventory::MareDataWriter::CollectAndWriteMareData",
      84,
      "MareDataWriter::UpdateCacheBeforeCollection failed [%#x]",
      updated);
    v6 = v5;
  }
  if ( v2 )
    Windows::Compat::Inventory::InventoryWatchdog::RenewTimer(v2);
  v7 = Windows::Compat::Inventory::MareDataWriter::AddAppsFromCache((Windows::Compat::Inventory::MareDataWriter *)v17);
  if ( v7 < 0
    || (v7 = Windows::Compat::Inventory::MareDataWriter::AddMareDataFromCache((Windows::Compat::Inventory::MareDataWriter *)v17),
        v7 < 0)
    || (v7 = Windows::Compat::Inventory::MareDataWriter::AddAUMIDFilesFromCache((Windows::Compat::Inventory::MareDataWriter *)v17),
        v7 < 0) )
  {
    AslLogCallPrintf(
      1,
      "Windows::Compat::Inventory::MareDataWriter::CollectAndWriteMareData",
      107,
      "MareDataWriter::CollectMareData failed [%#x]",
      v7);
    if ( v6 >= 0 )
      v6 = v7;
  }
  if ( v2 )
    Windows::Compat::Inventory::InventoryWatchdog::RenewTimer(v2);
  v8 = Windows::Compat::Inventory::MareDataWriter::UpdateCacheAfterCollection((Windows::Compat::Inventory::MareDataWriter *)v17);
  v9 = v8;
  if ( v8 < 0 )
  {
    AslLogCallPrintf(
      1,
      "Windows::Compat::Inventory::MareDataWriter::CollectAndWriteMareData",
      125,
      "MareDataWriter::UpdateCacheAfterCollection failed [%#x]",
      v8);
    if ( v6 >= 0 )
      v6 = v9;
  }
  if ( v2 )
    Windows::Compat::Inventory::InventoryWatchdog::RenewTimer(v2);
  DataFiles = Windows::Compat::Inventory::MareDataWriter::CreateDataFiles((Windows::Compat::Inventory::MareDataWriter *)v17);
  v5 = DataFiles;
  if ( DataFiles >= 0 )
  {
    if ( v2 )
      Windows::Compat::Inventory::InventoryWatchdog::RenewTimer(v2);
    v11 = Windows::Compat::Inventory::MareDataWriter::WriteDataFiles((Windows::Compat::Inventory::MareDataWriter *)v17);
    v5 = v11;
    if ( v11 < 0 )
    {
      AslLogCallPrintf(
        1,
        "Windows::Compat::Inventory::MareDataWriter::CollectAndWriteMareData",
        159,
        "MareDataWriter::WriteDataFiles failed [%#x]",
        v11);
      if ( v6 >= 0 )
        v6 = v5;
    }
  }
  else
  {
    AslLogCallPrintf(
      1,
      "Windows::Compat::Inventory::MareDataWriter::CollectAndWriteMareData",
      143,
      "MareDataWriter::CreateDataFiles failed [%#x]",
      DataFiles);
    if ( v6 >= 0 )
      v6 = v5;
  }
LABEL_39:
  Windows::Compat::Inventory::MareDataWriter::SendFinalTelemtry((Windows::Compat::Inventory::MareDataWriter *)v17, v5);
  if ( v2 )
  {
    Windows::Compat::Inventory::InventoryWatchdog::~InventoryWatchdog(v2);
    operator delete(v2, (const struct std::nothrow_t *)0x40);
  }
  Windows::Compat::Inventory::MareDataWriter::~MareDataWriter((Windows::Compat::Inventory::MareDataWriter *)v17);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1800172a0  mov     [rsp-8+arg_8], rbx
0x1800172a5  mov     [rsp-8+arg_10], rsi
0x1800172aa  push    rbp
0x1800172ab  push    rdi
0x1800172ac  push    r12
0x1800172ae  push    r14
0x1800172b0  push    r15
0x1800172b2  lea     rbp, [rsp-0D0h]
0x1800172ba  sub     rsp, 1D0h
0x1800172c1  mov     rax, cs:__security_cookie
0x1800172c8  xor     rax, rsp
0x1800172cb  mov     [rbp+0F0h+var_30], rax
0x1800172d2  mov     rdx, rcx; unsigned __int16 *
0x1800172d5  lea     rcx, [rsp+1F0h+var_1A0]; this
0x1800172da  call    ??0MareDataWriter@Inventory@Compat@Windows@@QEAA@PEBG@Z; Windows::Compat::Inventory::MareDataWriter::MareDataWriter(ushort const *)
0x1800172df  nop
0x1800172e0  xor     r14d, r14d
0x1800172e3  mov     [rsp+1F0h+var_1B0], r14
0x1800172e8  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800172ef  lea     ecx, [r14+40h]; unsigned __int64
0x1800172f3  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800172f8  mov     rbx, rax
0x1800172fb  test    rax, rax
0x1800172fe  jz      short loc_180017326
0x180017300  mov     dword ptr [rax], 0EA60h
0x180017306  mov     [rax+8], r14
0x18001730a  mov     [rax+10h], r14
0x18001730e  xor     eax, eax
0x180017310  mov     [rbx+18h], rax
0x180017314  mov     [rbx+20h], r14
0x180017318  mov     [rbx+28h], r14
0x18001731c  mov     [rbx+30h], r14
0x180017320  mov     [rbx+38h], r14
0x180017324  jmp     short loc_180017329
0x180017326  mov     rbx, r14
0x180017329  mov     [rsp+1F0h+var_1A8], rbx
0x18001732e  test    rbx, rbx
0x180017331  jz      short loc_18001733B
0x180017333  mov     rcx, rbx; this
0x180017336  call    ?Initialize@InventoryWatchdog@Inventory@Compat@Windows@@QEAAJXZ; Windows::Compat::Inventory::InventoryWatchdog::Initialize(void)
0x18001733b  mov     [rsp+1F0h+var_1BF], r14b
0x180017340  mov     [rsp+1F0h+var_1C0], r14b
0x180017345  mov     [rsp+1F0h+var_1B8], r14
0x18001734a  mov     [rsp+1F0h+var_1BC], r14d
0x18001734f  lea     rax, [rsp+1F0h+var_1C0]
0x180017354  mov     [rsp+1F0h+var_1D0], rax; bool *
0x180017359  lea     r9, [rsp+1F0h+var_1BC]; unsigned int *
0x18001735e  lea     r8, [rsp+1F0h+var_1B8]; unsigned __int64 *
0x180017363  lea     rdx, [rsp+1F0h+var_1BF]; bool *
0x180017368  lea     rcx, [rsp+1F0h+var_1A0]; this
0x18001736d  call    ?QueryOneSettings@MareDataWriter@Inventory@Compat@Windows@@QEAAJAEA_NAEA_KAEAK0@Z; Windows::Compat::Inventory::MareDataWriter::QueryOneSettings(bool &,unsigned __int64 &,ulong &,bool &)
0x180017372  lea     r12, aWindowsCompatI_49; "Windows::Compat::Inventory::MareDataWri"...
0x180017379  test    eax, eax
0x18001737b  jns     short loc_18001739A
0x18001737d  mov     dword ptr [rsp+1F0h+var_1D0], eax
0x180017381  lea     r9, aMaredatawriter_1; "MareDataWriter::QueryOneSettings failed"...
0x180017388  mov     r8d, 3Dh ; '='
0x18001738e  mov     rdx, r12
0x180017391  lea     ecx, [r8-3Ah]
0x180017395  call    AslLogCallPrintf
0x18001739a  mov     rax, [rsp+1F0h+var_1B8]
0x18001739f  test    rax, rax
0x1800173a2  jz      short loc_1800173AF
0x1800173a4  or      rax, 2
0x1800173a8  mov     cs:?s_defaultFarAttributes@MareApplication@Inventory@Compat@Windows@@0_KA, rax; unsigned __int64 Windows::Compat::Inventory::MareApplication::s_defaultFarAttributes
0x1800173af  mov     r15d, 1
0x1800173b5  cmp     [rsp+1F0h+var_1C0], r14b
0x1800173ba  jz      short loc_1800173C3
0x1800173bc  mov     cs:?s_keepHiddenArps@MareApplication@Inventory@Compat@Windows@@0_NA, r15b; bool Windows::Compat::Inventory::MareApplication::s_keepHiddenArps
0x1800173c3  test    rbx, rbx
0x1800173c6  jz      short loc_1800173D0
0x1800173c8  mov     rcx, rbx; this
0x1800173cb  call    ?RenewTimer@InventoryWatchdog@Inventory@Compat@Windows@@QEAA_NXZ; Windows::Compat::Inventory::InventoryWatchdog::RenewTimer(void)
0x1800173d0  mov     dl, [rsp+1F0h+var_1BF]; bool
0x1800173d4  lea     rcx, [rsp+1F0h+var_1A0]; this
0x1800173d9  call    ?UpdateCacheBeforeCollection@MareDataWriter@Inventory@Compat@Windows@@AEAAJ_N@Z; Windows::Compat::Inventory::MareDataWriter::UpdateCacheBeforeCollection(bool)
0x1800173de  mov     edi, eax
0x1800173e0  test    eax, eax
0x1800173e2  jns     short loc_180017404
0x1800173e4  mov     dword ptr [rsp+1F0h+var_1D0], eax
0x1800173e8  lea     r9, aMaredatawriter; "MareDataWriter::UpdateCacheBeforeCollec"...
0x1800173ef  mov     r8d, 54h ; 'T'
0x1800173f5  mov     rdx, r12
0x1800173f8  mov     ecx, r15d
0x1800173fb  call    AslLogCallPrintf
0x180017400  mov     esi, edi
0x180017402  jmp     short loc_180017410
0x180017404  mov     esi, r14d
0x180017407  cmp     edi, r15d
0x18001740a  jz      loc_18001752B
0x180017410  test    rbx, rbx
0x180017413  jz      short loc_18001741D
0x180017415  mov     rcx, rbx; this
0x180017418  call    ?RenewTimer@InventoryWatchdog@Inventory@Compat@Windows@@QEAA_NXZ; Windows::Compat::Inventory::InventoryWatchdog::RenewTimer(void)
0x18001741d  lea     rcx, [rsp+1F0h+var_1A0]; this
0x180017422  call    ?AddAppsFromCache@MareDataWriter@Inventory@Compat@Windows@@AEAAJXZ; Windows::Compat::Inventory::MareDataWriter::AddAppsFromCache(void)
0x180017427  mov     edi, eax
0x180017429  test    eax, eax
0x18001742b  js      short loc_18001744D
0x18001742d  lea     rcx, [rsp+1F0h+var_1A0]; this
0x180017432  call    ?AddMareDataFromCache@MareDataWriter@Inventory@Compat@Windows@@AEAAJXZ; Windows::Compat::Inventory::MareDataWriter::AddMareDataFromCache(void)
0x180017437  mov     edi, eax
0x180017439  test    eax, eax
0x18001743b  js      short loc_18001744D
0x18001743d  lea     rcx, [rsp+1F0h+var_1A0]; this
0x180017442  call    ?AddAUMIDFilesFromCache@MareDataWriter@Inventory@Compat@Windows@@AEAAJXZ; Windows::Compat::Inventory::MareDataWriter::AddAUMIDFilesFromCache(void)
0x180017447  mov     edi, eax
0x180017449  test    eax, eax
0x18001744b  jns     short loc_18001746E
0x18001744d  mov     dword ptr [rsp+1F0h+var_1D0], edi
0x180017451  lea     r9, aMaredatawriter_2; "MareDataWriter::CollectMareData failed "...
0x180017458  mov     r8d, 6Bh ; 'k'
0x18001745e  mov     rdx, r12
0x180017461  mov     ecx, r15d
0x180017464  call    AslLogCallPrintf
0x180017469  test    esi, esi
0x18001746b  cmovns  esi, edi
0x18001746e  test    rbx, rbx
0x180017471  jz      short loc_18001747B
0x180017473  mov     rcx, rbx; this
0x180017476  call    ?RenewTimer@InventoryWatchdog@Inventory@Compat@Windows@@QEAA_NXZ; Windows::Compat::Inventory::InventoryWatchdog::RenewTimer(void)
0x18001747b  lea     rcx, [rsp+1F0h+var_1A0]; this
0x180017480  call    ?UpdateCacheAfterCollection@MareDataWriter@Inventory@Compat@Windows@@AEAAJXZ; Windows::Compat::Inventory::MareDataWriter::UpdateCacheAfterCollection(void)
0x180017485  mov     edi, eax
0x180017487  test    eax, eax
0x180017489  jns     short loc_1800174AC
0x18001748b  mov     dword ptr [rsp+1F0h+var_1D0], eax
0x18001748f  lea     r9, aMaredatawriter_4; "MareDataWriter::UpdateCacheAfterCollect"...
0x180017496  mov     r8d, 7Dh ; '}'
0x18001749c  mov     rdx, r12
0x18001749f  mov     ecx, r15d
0x1800174a2  call    AslLogCallPrintf
0x1800174a7  test    esi, esi
0x1800174a9  cmovns  esi, edi
0x1800174ac  test    rbx, rbx
0x1800174af  jz      short loc_1800174B9
0x1800174b1  mov     rcx, rbx; this
0x1800174b4  call    ?RenewTimer@InventoryWatchdog@Inventory@Compat@Windows@@QEAA_NXZ; Windows::Compat::Inventory::InventoryWatchdog::RenewTimer(void)
0x1800174b9  lea     rcx, [rsp+1F0h+var_1A0]; this
0x1800174be  call    ?CreateDataFiles@MareDataWriter@Inventory@Compat@Windows@@AEAAJXZ; Windows::Compat::Inventory::MareDataWriter::CreateDataFiles(void)
0x1800174c3  mov     edi, eax
0x1800174c5  test    eax, eax
0x1800174c7  jns     short loc_1800174ED
0x1800174c9  mov     dword ptr [rsp+1F0h+var_1D0], eax
0x1800174cd  lea     r9, aMaredatawriter_3; "MareDataWriter::CreateDataFiles failed "...
0x1800174d4  mov     r8d, 8Fh
0x1800174da  mov     rdx, r12
0x1800174dd  mov     ecx, r15d
0x1800174e0  call    AslLogCallPrintf
0x1800174e5  test    esi, esi
0x1800174e7  js      short loc_18001752B
0x1800174e9  mov     esi, edi
0x1800174eb  jmp     short loc_18001752B
0x1800174ed  test    rbx, rbx
0x1800174f0  jz      short loc_1800174FA
0x1800174f2  mov     rcx, rbx; this
0x1800174f5  call    ?RenewTimer@InventoryWatchdog@Inventory@Compat@Windows@@QEAA_NXZ; Windows::Compat::Inventory::InventoryWatchdog::RenewTimer(void)
0x1800174fa  lea     rcx, [rsp+1F0h+var_1A0]; this
0x1800174ff  call    ?WriteDataFiles@MareDataWriter@Inventory@Compat@Windows@@AEAAJXZ; Windows::Compat::Inventory::MareDataWriter::WriteDataFiles(void)
0x180017504  mov     edi, eax
0x180017506  test    eax, eax
0x180017508  jns     short loc_18001752B
0x18001750a  mov     dword ptr [rsp+1F0h+var_1D0], eax
0x18001750e  lea     r9, aMaredatawriter_0; "MareDataWriter::WriteDataFiles failed ["...
0x180017515  mov     r8d, 9Fh
0x18001751b  mov     rdx, r12
0x18001751e  mov     ecx, r15d
0x180017521  call    AslLogCallPrintf
0x180017526  test    esi, esi
0x180017528  cmovns  esi, edi
0x18001752b  mov     edx, edi; int
0x18001752d  lea     rcx, [rsp+1F0h+var_1A0]; this
0x180017532  call    ?SendFinalTelemtry@MareDataWriter@Inventory@Compat@Windows@@AEAAXJ@Z; Windows::Compat::Inventory::MareDataWriter::SendFinalTelemtry(long)
0x180017537  nop
0x180017538  test    rbx, rbx
0x18001753b  jz      short loc_180017553
0x18001753d  mov     rcx, rbx; this
0x180017540  call    ??1InventoryWatchdog@Inventory@Compat@Windows@@QEAA@XZ; Windows::Compat::Inventory::InventoryWatchdog::~InventoryWatchdog(void)
0x180017545  mov     edx, 40h ; '@'; struct std::nothrow_t *
0x18001754a  mov     rcx, rbx; void *
0x18001754d  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180017552  nop
0x180017553  lea     rcx, [rsp+1F0h+var_1A0]; this
0x180017558  call    ??1MareDataWriter@Inventory@Compat@Windows@@QEAA@XZ; Windows::Compat::Inventory::MareDataWriter::~MareDataWriter(void)
0x18001755d  mov     eax, esi
0x18001755f  mov     rcx, [rbp+0F0h+var_30]
0x180017566  xor     rcx, rsp; StackCookie
0x180017569  call    __security_check_cookie
0x18001756e  lea     r11, [rsp+1F0h+var_20]
0x180017576  mov     rbx, [r11+38h]
0x18001757a  mov     rsi, [r11+40h]
0x18001757e  mov     rsp, r11
0x180017581  pop     r15
0x180017583  pop     r14
0x180017585  pop     r12
0x180017587  pop     rdi
0x180017588  pop     rbp
0x180017589  retn
```
